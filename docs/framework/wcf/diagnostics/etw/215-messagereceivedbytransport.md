---
title: 215 - MessageReceivedByTransport
ms.date: 03/30/2017
ms.assetid: bb32aa60-5207-4711-9f08-110e8ac327e5
ms.openlocfilehash: a8ba90b88ef8dbe3c8651bc565da61aae16a0a4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460897"
---
# <a name="215---messagereceivedbytransport"></a>215 - MessageReceivedByTransport
## <a name="properties"></a>Propriedades  
  
|||  
|-|-|  
|ID|215|  
|Palavras-chave|Solução de problemas, ServiceModel|  
|Nível|Informações|  
|Canal|Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico|  
  
## <a name="description"></a>Descrição  
 Esse evento ocorre quando um transporte baseado em TCP recebe uma mensagem. Observe que, no nível de transporte, várias mensagens podem ser trocadas entre clientes e serviços para uma única operação. Isso pode ser devido ao comportamento de infraestrutura, a segurança é um bom exemplo. Portanto, o número de `MessageReceivedByTransport` eventos que são emitidos variam com base na associação do serviço e sua configuração.  
  
> [!NOTE]
>  Esse evento não é emitido para transportes unidirecionais.  
  
## <a name="message"></a>Mensagem  
 O transporte recebeu uma mensagem de '%1'.  
  
## <a name="details"></a>Detalhes  
  
|Nome do item de dados|Tipo de item de dados|Descrição|  
|--------------------|--------------------|-----------------|  
|Endereço de escuta|`xs:string`|O endereço que recebeu a mensagem.|  
|HostReference|`xs:string`|Para serviços hospedados na Web, este campo identifica exclusivamente o serviço na hierarquia da Web. O formato é definido como ' caminho Virtual do aplicativo Web Site nome&#124;caminho Virtual do serviço&#124;ServiceName'. Exemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.|
