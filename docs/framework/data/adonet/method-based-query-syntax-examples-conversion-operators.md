---
title: "Exemplos de sintaxe da consulta com base em método: Operadores de conversão (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a084c16b-9b55-4690-aefd-f8e0810a92c3
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 65f583bf7aaa223107d9ae23ede8660d2b6804ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="method-based-query-syntax-examples-conversion-operators-linq-to-dataset"></a><span data-ttu-id="753cb-102">Exemplos de sintaxe da consulta com base em método: Operadores de conversão (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="753cb-102">Method-Based Query Syntax Examples: Conversion Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="753cb-103">Os exemplos neste tópico demonstram como usar <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, e métodos de <xref:System.Linq.Enumerable.ToList%2A> para executar imediatamente uma expressão de consulta.</span><span class="sxs-lookup"><span data-stu-id="753cb-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, and <xref:System.Linq.Enumerable.ToList%2A> methods to immediately execute a query expression.</span></span>  
  
 <span data-ttu-id="753cb-104">O `FillDataSet` método usado nesses exemplos é especificado em [carregar dados em um conjunto de dados](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="753cb-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="753cb-105">Os exemplos neste tópico usam as tabelas Contact, Address, Product, SalesOrderHeader e SalesOrderDetail no banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="753cb-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="753cb-106">Os exemplos neste tópico usam o seguinte `using` / `Imports` instruções:</span><span class="sxs-lookup"><span data-stu-id="753cb-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="753cb-107">Para obter mais informações, consulte [como: criar um LINQ to DataSet de projeto no Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="753cb-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="toarray"></a><span data-ttu-id="753cb-108">ToArray</span><span class="sxs-lookup"><span data-stu-id="753cb-108">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="753cb-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="753cb-109">Example</span></span>  
 <span data-ttu-id="753cb-110">Este exemplo usa o método de <xref:System.Linq.Enumerable.ToArray%2A> para avaliar imediatamente uma sequência em uma matriz.</span><span class="sxs-lookup"><span data-stu-id="753cb-110">This example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="753cb-111">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="753cb-111">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="753cb-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="753cb-112">Example</span></span>  
 <span data-ttu-id="753cb-113">Este exemplo usa o método de <xref:System.Linq.Enumerable.ToDictionary%2A> para avaliar imediatamente uma sequência e uma expressão chave relacionadas em um dicionário.</span><span class="sxs-lookup"><span data-stu-id="753cb-113">This example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="753cb-114">ToList</span><span class="sxs-lookup"><span data-stu-id="753cb-114">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="753cb-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="753cb-115">Example</span></span>  
 <span data-ttu-id="753cb-116">Este exemplo usa o método de <xref:System.Linq.Enumerable.ToList%2A> para avaliar imediatamente uma sequência em <xref:System.Collections.Generic.List%601>, onde `T` é do tipo <xref:System.Data.DataRow>.</span><span class="sxs-lookup"><span data-stu-id="753cb-116">This example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#tolist)]
 [!code-vb[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="753cb-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="753cb-117">See Also</span></span>  
 [<span data-ttu-id="753cb-118">Carregar dados em um conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="753cb-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="753cb-119">LINQ para exemplos de conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="753cb-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)  
 [<span data-ttu-id="753cb-120">Visão Geral de Operadores de Consulta Padrão</span><span class="sxs-lookup"><span data-stu-id="753cb-120">Standard Query Operators Overview</span></span>](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)