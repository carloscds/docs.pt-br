---
title: 'Como: Melhorar o desempenho de um TreeView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: 3c7bd151e1c8a5f318660cc45702b5b9c98534a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500688"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>Como: Melhorar o desempenho de um TreeView
Se um <xref:System.Windows.Controls.TreeView> contém muitos itens, a quantidade de tempo que leva para carregar pode causar um atraso significativo na interface do usuário. Você pode melhorar o tempo de carregamento, definindo o `VirtualizingStackPanel.IsVirtualizing` anexado à propriedade `true`.  A interface do usuário também pode ser lento para reagir quando o usuário rola a <xref:System.Windows.Controls.TreeView> usando a roda do mouse ou arrastando o controle de posição de uma barra de rolagem. Você pode melhorar o desempenho do <xref:System.Windows.Controls.TreeView> quando o usuário rola, definindo o `VirtualizingStackPanel.VirtualizationMode` anexado à propriedade <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Exemplo  
  
## <a name="description"></a>Descrição  
O exemplo a seguir cria uma <xref:System.Windows.Controls.TreeView> que define o `VirtualizingStackPanel.IsVirtualizing` propriedade anexada como true e o `VirtualizingStackPanel.VirtualizationMode` anexado à propriedade <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> para otimizar o desempenho.  
  
## <a name="code"></a>Código  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 O exemplo a seguir mostra os dados que o exemplo anterior usa.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>Consulte também
- [Controles](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
