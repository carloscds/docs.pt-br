---
title: 'Como: Preencher uma forma com um padrão em hachura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: 3fb5b443aac710a5490a238e2a571ed899dec463
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512381"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>Como: Preencher uma forma com um padrão em hachura
Um padrão de hachura é feito de duas cores: um para o plano de fundo e outro para as linhas que formam o padrão no plano de fundo. Para preencher uma forma fechada com um padrão de hachura, use um <xref:System.Drawing.Drawing2D.HatchBrush> objeto. O exemplo a seguir demonstra como preencher uma elipse com um padrão de hachura:  
  
## <a name="example"></a>Exemplo  
 O <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> construtor usa três argumentos: o estilo de hachura, a cor da linha de hachura e a cor do plano de fundo. O argumento de estilo de hachura pode ser qualquer valor da <xref:System.Drawing.Drawing2D.HatchStyle> enumeração. Há mais de 50 elementos no <xref:System.Drawing.Drawing2D.HatchStyle> enumeração; alguns deles elementos são mostrados na lista a seguir:  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 A ilustração a seguir mostra a elipse preenchida.  
  
 ![Hatch Pattern](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 O exemplo anterior foi projetado para uso com o Windows Forms e requer <xref:System.Windows.Forms.PaintEventArgs> `e`, que é um parâmetro do <xref:System.Windows.Forms.Control.Paint> manipulador de eventos.  
  
## <a name="see-also"></a>Consulte também
- [Usando um pincel para preencher formas](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
