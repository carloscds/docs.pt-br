---
title: Sintaxe de expressão de consulta para operadores de consulta padrão (C#)
ms.date: 07/20/2015
ms.assetid: e1e17ef2-68ff-4c26-b6e2-015668227fa5
ms.openlocfilehash: 232793e63673ef51b650d8188fea5733d02fd1b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501760"
---
# <a name="query-expression-syntax-for-standard-query-operators-c"></a>Sintaxe de expressão de consulta para operadores de consulta padrão (C#)
Alguns dos operadores de consulta padrão mais usados têm uma sintaxe de palavra-chave de linguagem C# dedicada que possibilita que eles sejam chamados como parte de uma *expressão de consulta*. Uma expressão de consulta é uma maneira diferente e mais legível de expressar uma consulta do que seu equivalente *baseado em método*. As cláusulas de expressão de consulta são convertidas em chamadas para os métodos de consulta em tempo de compilação.  
  
## <a name="query-expression-syntax-table"></a>Tabela de sintaxe de expressão de consulta  
 A tabela a seguir lista os operadores de consulta padrão que têm cláusulas de expressão de consulta equivalentes.  
  
|Método|Sintaxe de expressão de consulta C#|  
|------------|---------------------------------|  
|<xref:System.Linq.Enumerable.Cast%2A>|Use uma variável de intervalo de tipo explícito, por exemplo:<br /><br /> `from int i in numbers`<br /><br /> (Para obter mais informações, consulte [Cláusula from](../../../../csharp/language-reference/keywords/from-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupBy%2A>|`group … by`<br /><br /> - ou -<br /><br /> `group … by … into …`<br /><br /> (Para obter mais informações, consulte [Cláusula group](../../../../csharp/language-reference/keywords/group-clause.md).)|  
|<xref:System.Linq.Enumerable.GroupJoin%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2C%60%603%7D%29>|`join … in … on … equals … into …`<br /><br /> (Para obter mais informações, consulte [Cláusula join](../../../../csharp/language-reference/keywords/join-clause.md).)|  
|<xref:System.Linq.Enumerable.Join%60%604%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Collections.Generic.IEnumerable%7B%60%601%7D%2CSystem.Func%7B%60%600%2C%60%602%7D%2CSystem.Func%7B%60%601%2C%60%602%7D%2CSystem.Func%7B%60%600%2C%60%601%2C%60%603%7D%29>|`join … in … on … equals …`<br /><br /> (Para obter mais informações, consulte [Cláusula join](../../../../csharp/language-reference/keywords/join-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderBy%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby`<br /><br /> (Para obter mais informações, consulte [Cláusula orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.OrderByDescending%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby … descending`<br /><br /> (Para obter mais informações, consulte [Cláusula orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.Select%2A>|`select`<br /><br /> (Para obter mais informações, consulte [Cláusula select](../../../../csharp/language-reference/keywords/select-clause.md).)|  
|<xref:System.Linq.Enumerable.SelectMany%2A>|Várias cláusulas `from`.<br /><br /> (Para obter mais informações, consulte [Cláusula from](../../../../csharp/language-reference/keywords/from-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenBy%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, …`<br /><br /> (Para obter mais informações, consulte [Cláusula orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.ThenByDescending%60%602%28System.Linq.IOrderedEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29>|`orderby …, … descending`<br /><br /> (Para obter mais informações, consulte [Cláusula orderby](../../../../csharp/language-reference/keywords/orderby-clause.md).)|  
|<xref:System.Linq.Enumerable.Where%2A>|`where`<br /><br /> (Para obter mais informações, consulte [Cláusula where](../../../../csharp/language-reference/keywords/where-clause.md).)|  
  
## <a name="see-also"></a>Consulte também

- <xref:System.Linq.Enumerable>
- <xref:System.Linq.Queryable>
- [Visão geral de operadores de consulta padrão (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Classificação de operadores de consulta padrão pelo modo de execução (C#)](../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md)
