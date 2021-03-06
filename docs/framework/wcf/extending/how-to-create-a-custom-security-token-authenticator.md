---
title: 'Como: criar um autenticador de token de segurança personalizadas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: 10e245f7-d31e-42e7-82a2-d5780325d372
ms.openlocfilehash: df45f943da62624b92d483851e788dad0e240f47
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261122"
---
# <a name="how-to-create-a-custom-security-token-authenticator"></a>Como: criar um autenticador de token de segurança personalizadas
Este tópico mostra como criar um autenticador de token de segurança personalizada e como integrá-lo com um Gerenciador de token de segurança personalizada. Um autenticador de token de segurança valida o conteúdo de um token de segurança fornecido com uma mensagem de entrada. Se a validação for bem-sucedida, o autenticador retorna uma coleção de <xref:System.IdentityModel.Policy.IAuthorizationPolicy> instâncias que, quando avaliado, retorna um conjunto de declarações.  
  
 Para usar um autenticador de token de segurança personalizadas no Windows Communication Foundation (WCF), você deve primeiro criar segurança e credenciais personalizadas do Gerenciador de token implementações. Para obter mais informações sobre a criação de credenciais personalizadas e uma segurança Gerenciador de token, consulte [passo a passo: Criação de credenciais de serviço e personalizadas do cliente](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).
  
## <a name="procedures"></a>Procedimentos  
  
#### <a name="to-create-a-custom-security-token-authenticator"></a>Para criar um autenticador de token de segurança personalizadas  
  
1.  Definir uma nova classe que deriva de <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> classe.  
  
2.  Substituir o método <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.CanValidateTokenCore%2A>. O método retornará `true` ou `false` dependendo se o autenticador personalizado pode validar o tipo de token de entrada ou não.  
  
3.  Substituir o método <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.ValidateTokenCore%2A>. Esse método precisa validar o conteúdo do token adequadamente. Se o token passa a etapa de validação, ele retorna uma coleção de <xref:System.IdentityModel.Policy.IAuthorizationPolicy> instâncias. O exemplo a seguir usa uma implementação de política de autorização personalizada que será criada no próximo procedimento.  
  
     [!code-csharp[C_CustomTokenAuthenticator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#1)]
     [!code-vb[C_CustomTokenAuthenticator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#1)]  
  
 O código anterior retorna uma coleção de políticas de autorização no <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.CanValidateToken%28System.IdentityModel.Tokens.SecurityToken%29> método. O WCF não fornece uma implementação dessa interface pública. O procedimento a seguir mostra como fazer isso para seus próprios requisitos.  
  
#### <a name="to-create-a-custom-authorization-policy"></a>Para criar uma política de autorização personalizada  
  
1.  Definir uma nova classe implementando o <xref:System.IdentityModel.Policy.IAuthorizationPolicy> interface.  
  
2.  Implementar o <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> propriedade somente leitura. Uma maneira de implementar essa propriedade é gerar um identificador global exclusivo (GUID) no construtor da classe e retorná-lo toda vez que o valor dessa propriedade é solicitado.  
  
3.  Implementar o <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> propriedade somente leitura. Esta propriedade precisa retornar um emissor dos conjuntos de declarações que são obtidos do token. Esse emissor deve corresponder ao emissor do token ou uma autoridade que é responsável por validar o conteúdo do token. O exemplo a seguir usa a declaração do emissor que passados para essa classe do autenticador de token de segurança personalizada criado no procedimento anterior. O autenticador de token de segurança personalizada usa o conjunto de declarações fornecidas pelo sistema (retornado pela <xref:System.IdentityModel.Claims.ClaimSet.System%2A> propriedade) para representar o emissor do token de nome de usuário.  
  
4.  Implementar o método de <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A> . Esse método popula uma instância da <xref:System.IdentityModel.Policy.EvaluationContext> (transmitida como um argumento) da classe com declarações que se baseiam no conteúdo do token de segurança entrada. O método retorna `true` quando ele é feito com a avaliação. Em casos quando a implementação se baseia na presença de outras políticas de autorização que fornecem informações adicionais para o contexto de avaliação, esse método pode retornar `false` se não houver as informações necessárias ainda no contexto de avaliação. Nesse caso, o WCF chamará o método novamente depois de avaliar todas as demais diretivas de autorização geradas para a mensagem de entrada se pelo menos uma dessas políticas de autorização tiver modificado o contexto de avaliação.  
  
     [!code-csharp[c_CustomTokenAuthenticator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#3)]
     [!code-vb[c_CustomTokenAuthenticator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#3)]  

 [Passo a passo: Criação de credenciais de serviço e personalizadas do cliente](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md) descreve como criar uma segurança personalizada e credenciais personalizadas do Gerenciador de token. Para usar o autenticador de token de segurança personalizada criado aqui, uma implementação do Gerenciador de token de segurança é modificada para retornar o autenticador personalizado do <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> método. O método retorna um autenticador quando um requisito de token de segurança apropriado é passado.  
  
#### <a name="to-integrate-a-custom-security-token-authenticator-with-a-custom-security-token-manager"></a>Integrar um autenticador de token de segurança personalizada com um Gerenciador de token de segurança personalizadas  
  
1.  Substituir o <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> método em sua implementação do Gerenciador de token de segurança personalizada.  
  
2.  Adicionar lógica para o método para habilitá-lo retornar o autenticador de token de segurança personalizada com base no <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parâmetro. O exemplo a seguir retorna um autenticador de token de segurança personalizada, se o tipo de token de requisitos de token é um nome de usuário (representado pelo <xref:System.IdentityModel.Tokens.SecurityTokenTypes.UserName%2A> propriedade) e a direção da mensagem para os quais o autenticador de token de segurança está sendo solicitado é de entrada ( representado pelo <xref:System.ServiceModel.Description.MessageDirection.Input> campo).  
  
     [!code-csharp[c_CustomTokenAuthenticator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#2)]
     [!code-vb[c_CustomTokenAuthenticator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#2)]  
 
## <a name="see-also"></a>Consulte também
- <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.IdentityModel.Tokens.UserNameSecurityToken>
- [Passo a passo: Criação de credenciais de serviço e personalizadas do cliente](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)
- [Como: Criar um provedor de Token de segurança personalizadas](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)
