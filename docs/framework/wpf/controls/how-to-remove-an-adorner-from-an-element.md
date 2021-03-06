---
title: 'Como: Remover um adorno de um elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: eeefa83703ef9a4ffa7653042745d9acd58536f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695748"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a>Como: Remover um adorno de um elemento
Este exemplo mostra como remover um adorno de um de forma programática <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Exemplo  
 Este exemplo de código detalhado remove o primeiro adorno na matriz de adornos retornados por <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  Este exemplo acontece recupera os adornos em um <xref:System.Windows.UIElement> nomeado *myTextBox*.  Se o elemento especificado na chamada para <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> não tiver adornos, `null` será retornado.  Esse código verifica explicitamente uma matriz nula e é mais adequado para aplicativos em que se espera uma matriz nula relativamente comum.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a>Exemplo  
 Este exemplo de código condensada é funcionalmente equivalente ao exemplo detalhado mostrado acima. Esse código não verifica explicitamente uma matriz nula, portanto, é possível que um <xref:System.NullReferenceException> exceção poderá ser gerada.  Esse código é mais adequado para aplicativos em que se espera uma matriz nula rara.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a>Consulte também
- [Visão geral de adornos](../../../../docs/framework/wpf/controls/adorners-overview.md)
