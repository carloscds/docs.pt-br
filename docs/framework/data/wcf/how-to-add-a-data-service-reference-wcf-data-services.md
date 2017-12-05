---
title: "Como: adicionar uma referência de serviço de dados (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 702eda2d4641dc2efdac40f9d730228063e306a8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>Como: adicionar uma referência de serviço de dados (WCF Data Services)
Você pode usar o **adicionar referência de serviço** caixa de diálogo no Visual Studio para adicionar uma referência a [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Isso permite que você acesse mais facilmente um serviço de dados em um aplicativo cliente que você desenvolver no Visual Studio. Quando você concluir este procedimento, classes de dados são gerados com base nos metadados que é obtido do serviço de dados. Para obter mais informações, consulte [gerando a biblioteca de cliente do serviço de dados](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md).  
  
### <a name="to-add-a-data-service-reference"></a>Para adicionar uma referência de serviço de dados  
  
1.  (Opcional) Se o serviço de dados não faz parte da solução e não está sendo executado, inicie o serviço de dados e observe o URI do serviço de dados.  
  
2.  O projeto de cliente e, em seguida, selecione **adicionar referência de serviço**.  
  
3.  Se o serviço de dados é parte da solução atual, clique em **Discover**.  
  
     -ou-  
  
     No **endereço** caixa de texto, digite a URL base do serviço de dados, como `http://localhost:1234/Northwind.svc`e, em seguida, clique em **vá**.  
  
4.  Clique em **OK**.  
  
     Isso adiciona um novo arquivo de código que contém as classes de dados que são usadas para acessar e interagir com os recursos de serviço de dados como objetos.  
  
## <a name="see-also"></a>Consulte também  
 [Quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) (Início rápido)