---
title: 'Como: Exibir uma página da Web de um controle LinkLabel dos Windows Forms (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- LinkLabel1_LinkClicked
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Web pages [Windows Forms], displaying
- linking [Windows Forms], to Web pages from forms
- Windows Forms, linking to Web pages
- LinkLabel control [Windows Forms], examples
ms.assetid: 477a7398-5971-4de3-b24c-f49f32bdb28a
ms.openlocfilehash: 05b127099b85188b0df2f1f7821ceb147cc41e1d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698954"
---
# <a name="how-to-display-a-web-page-from-a-windows-forms-linklabel-control-visual-basic"></a>Como: Exibir uma página da Web de um controle LinkLabel dos Windows Forms (Visual Basic)
Este exemplo exibe uma página da Web no navegador padrão, quando um usuário clica em um Windows Forms <xref:System.Windows.Forms.LinkLabel> controle.  
  
## <a name="example"></a>Exemplo  
  
```vb  
Private Sub Form1_Load(ByVal sender As System.Object, ByVal e _  
As System.EventArgs) Handles MyBase.Load  
    LinkLabel1.Text = "Click here to get more info."  
    LinkLabel1.Links.Add(6, 4, "www.microsoft.com")  
End Sub  
Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, ByVal _  
e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) Handles _  
LinkLabel1.LinkClicked  
    System.Diagnostics.Process.Start(e.Link.LinkData.ToString())  
End Sub  
```  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
-   Um formulário do Windows chamado `Form1`.  
  
-   Um controle <xref:System.Windows.Forms.LinkLabel> chamado `LinkLabel1`.  
  
-   Uma conexão de Internet ativa.  
  
## <a name="net-framework-security"></a>Segurança do .NET Framework  
 A chamada para o <xref:System.Diagnostics.Process.Start%2A> método requer confiança total. Para obter mais informações, consulte <xref:System.Security.SecurityException>.  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Windows.Forms.LinkLabel>
- [Controle LinkLabel](../../../../docs/framework/winforms/controls/linklabel-control-windows-forms.md)
