---
title: Windows Forms e aplicativos não gerenciados
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: f54f039fd3477c380a2236a93ad8d80b4f7153b2
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2019
ms.locfileid: "56441808"
---
# <a name="windows-forms-and-unmanaged-applications"></a>Windows Forms e aplicativos não gerenciados
Aplicativos do Windows Forms e controles podem interoperar com aplicativos não gerenciados, com algumas restrições. As seções a seguir descrevem os cenários e as configurações com suporte em controles e aplicativos do Windows Forms e aqueles que não têm suporte.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Visão Geral dos Aplicativos dos Windows Forms e Aplicativos Não Gerenciados](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)  
 Oferece informações gerais sobre como usar e implementar controles de formulários do Windows que funcionam com aplicativos não gerenciados.  
  
 [Como: Dar suporte à interoperabilidade com exibindo um formulário do Windows com o método ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 Fornece um exemplo de código que mostra como usar o <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> método para executar um formulário do Windows em um aplicativo não gerenciado.  
  
 [Como: Dar suporte à interoperabilidade com exibindo cada formulário do Windows em seu próprio Thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 Fornece um exemplo de código que mostra como executar um formulário do Windows em seu próprio thread.  
  
 Consulte também [passo a passo: Dando suporte à interoperabilidade com exibindo cada formulário do Windows em seu próprio Thread](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).  
  
## <a name="reference"></a>Referência  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 Usado para criar um thread separado para um formulário do Windows.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 Inicia um loop de mensagem para um thread.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 Realiza marshaling de chamadas de um aplicativo não gerenciado a um formulário.  
  
## <a name="related-sections"></a>Seções relacionadas  
 [Expondo componentes do .NET Framework ao COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Oferece informações gerais sobre como usar tipos do .NET Framework em aplicativos não gerenciados.
