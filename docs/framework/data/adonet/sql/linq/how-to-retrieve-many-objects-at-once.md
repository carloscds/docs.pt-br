---
title: 'Como: Recuperar vários objetos ao mesmo tempo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: 31091b6634c9d95c008929680620fb66d95d473c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653782"
---
# <a name="how-to-retrieve-many-objects-at-once"></a>Como: Recuperar vários objetos ao mesmo tempo
Você pode recuperar vários objetos em uma consulta usando <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>.  
  
## <a name="example"></a>Exemplo  
 O código a seguir usa o método de <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> para recuperar `Customer` e objetos de `Order` .  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a>Consulte também
- [Conceitos de consulta](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
