---
title: FilterInputMessage
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
ms.openlocfilehash: c3620e13951afddc8de25c314de17704548d2366
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746160"
---
# <a name="filterinputmessage"></a>FilterInputMessage
Chamado pelo PresentationHost.exe sempre que uma mensagem é recebida, a menos que E_NOTIMPL seja retornado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pMsg`  
  
 [in] A mensagem WM_INPUT enviada para a janela que está obtendo entrada não processada.  
  
## <a name="property-valuereturn-value"></a>Valor da propriedade/valor de retorno  
 HRESULT:  
  
 S_OK – o filtro não processou a mensagem e o processamento adicional pode ocorrer.  
  
 S_FALSE – o filtro processou esta mensagem e nenhum processamento adicional deve ocorrer.  
  
 E_NOTIMPL – Se esse valor for retornado, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) não será chamado novamente. Isso pode ser retornado de um aplicativo host que só está interessado em fornecer progresso personalizado e interfaces de usuário de erro para PresentationHost.exe que não está interessado em receber mensagens de entrada não processada do PresentationHost.exe.  
  
## <a name="remarks"></a>Comentários  
 PresentationHost.exe é o destino de vários dispositivos de entrada não processada, incluindo teclado, mouse e controles remotos. Às vezes, o comportamento no aplicativo host é dependente da entrada que seria consumida pelo PresentationHost.exe. Por exemplo, um aplicativo host pode depender de receber certas mensagens de entrada para determinar se deve ou não exibir elementos de interface do usuário específicos.  
  
 Para permitir que o aplicativo host receba as mensagens de entrada necessárias para fornecer esses comportamentos, o PresentationHost.exe encaminha mensagens apropriadas de entrada não processada para o aplicativo hospedado chamando [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).  
  
 O aplicativo hospedado recebe mensagens de entrada não processada registrando com o conjunto de dispositivos de entrada não processada (dispositivos de interface humana) retornado pelo [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).  
  
## <a name="see-also"></a>Consulte também
- [Mensagem WM_INPUT](/windows/desktop/inputdev/wm-input)
