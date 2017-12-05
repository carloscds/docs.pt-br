---
title: "Como acessar serviços com um contrato duplex"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ec8b7f37dc7f04a7ddb2c6373b50e98fe41cf98
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-access-services-with-a-duplex-contract"></a>Como acessar serviços com um contrato duplex
Um recurso de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] é a capacidade de criar um serviço que usa um padrão de mensagens duplex. Esse padrão permite que um serviço para se comunicar com o cliente por meio de um retorno de chamada. Este tópico mostra as etapas para criar um [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente em uma classe de cliente que implementa a interface de retorno de chamada.  
  
 Uma associação dupla expõe o endereço IP do cliente para o serviço. O cliente deve usar a segurança para garantir que ele se conecta apenas para serviços relações de confiança.  
  
 Para obter um tutorial sobre como criar um basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] serviço e cliente, consulte [Tutorial de Introdução](../../../../docs/framework/wcf/getting-started-tutorial.md).  
  
### <a name="to-access-a-duplex-service"></a>Para acessar um serviço duplex  
  
1.  Crie um serviço que contém duas interfaces. É a primeira interface para o serviço, o segundo é para o retorno de chamada. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]criar um serviço duplex, consulte [como: criar um contrato Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
2.  Execute o serviço.  
  
3.  Use o [Ferramenta Utilitária de metadados ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para gerar contratos (interfaces) para o cliente. Para obter informações sobre como fazer isso, consulte [como: criar um cliente](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
4.  Implemente a interface de retorno de chamada na classe do cliente, conforme mostrado no exemplo a seguir.  
  
    ```csharp  
    public class CallbackHandler : ICalculatorDuplexCallback  
    {  
        public void Result(double result)  
        {  
            Console.WriteLine("Result ({0})", result);  
        }  
        public void Equation(string equation)  
        {  
            Console.WriteLine("Equation({0})", equation);  
        }  
    }  
    ```  
  
    ```vb  
    Public Class CallbackHandler   
    Implements ICalculatorDuplexCallback  
       Public Sub Result (ByVal result As Double)  
          Console.WriteLine("Result ({0})", result)  
       End Sub  
        Public Sub Equation(ByVal equation As String)  
            Console.Writeline("Equation({0})", equation)  
        End Sub  
    End Class  
    ```  
  
5.  Crie uma instância da classe <xref:System.ServiceModel.InstanceContext>. O construtor requer uma instância da classe do cliente.  
  
    ```csharp  
    InstanceContext site = new InstanceContext(new CallbackHandler());  
    ```  
  
    ```vb  
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())  
    ```  
  
6.  Criar uma instância do [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente usando o construtor que requer um <xref:System.ServiceModel.InstanceContext> objeto. O segundo parâmetro do construtor é o nome de um ponto de extremidade encontrado no arquivo de configuração.  
  
    ```csharp  
    CalculatorDuplexClient wcfClient =   
    new CalculatorDuplexClient(site, "default")  
    ```  
  
    ```vb  
    Dim wcfClient As New CalculatorDuplexClient(site, "default")  
    ```  
  
7.  Chame os métodos do [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] cliente conforme necessário.  
  
## <a name="example"></a>Exemplo  
 O exemplo de código a seguir demonstra como criar uma classe de cliente que acessa um contrato duplex.  
  
 [!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
 [!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]  
  
## <a name="net-framework-security"></a>Segurança do .NET Framework  
  
## <a name="see-also"></a>Consulte também  
 [Tutorial de Introdução](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Como: criar um contrato Duplex](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) [Ferramenta de utilitário de metadados ServiceModel (Svcutil.exe)]  
 [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md) (Como criar um cliente)  
 [Como: usar o ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)