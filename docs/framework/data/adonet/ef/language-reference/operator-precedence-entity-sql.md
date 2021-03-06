---
title: Precedência do operador (Entity SQL)
ms.date: 03/30/2017
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
ms.openlocfilehash: c68ac6d89426896b708ac74de1268f8ea8f193c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506830"
---
# <a name="operator-precedence-entity-sql"></a>Precedência do operador (Entity SQL)
Quando um [!INCLUDE[esql](../../../../../../includes/esql-md.md)] consulta tem vários operadores, precedência de operador determina a sequência na qual as operações são executadas. A ordem de execução pode impactar significativamente no resultado da consulta.  
  
 Os operadores têm os níveis de precedência mostrados na tabela a seguir. Um operador com um nível mais alto é avaliada antes de um operador com um nível inferior.  
  
|Nível|Tipo de operação|Operador|  
|-----------|--------------------|--------------|  
|1|Primária|`. , [] ()`|  
|2|Unário|`! not`|  
|3|Multiplicativo|`* / %`|  
|4|Aditivo|`+ -`|  
|5|Ordenando|`< > <= >=`|  
|6|Igualdade|`= != <>`|  
|7|AND condicional|`and &&`|  
|8|OR condicional|`or &#124;&#124;`|  
  
 Quando dois operadores em uma expressão têm o mesmo nível de precedência de operadores, são avaliados esquerda para a direita, com base na sua posição na consulta. Por exemplo, `x+y-z` é avaliado como `(x+y)-z`.  
  
 Você pode usar parênteses para substituir a precedência de operadores definida em uma consulta. Todos dentro dos parênteses é avaliado primeiro para produzir um único resultado antes que o resultado pode ser usado por qualquer operador fora dos parênteses. Por exemplo, `x+y*z` multiplica `y` pela `z` e, em seguida, adiciona `x`, mas `(x+y)*z` adiciona `x` para `y` e, em seguida, multiplica o resultado por `z`.  
  
## <a name="see-also"></a>Consulte também
- [Visão geral do Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
