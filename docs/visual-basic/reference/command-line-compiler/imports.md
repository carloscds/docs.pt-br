---
title: -Importa (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 9e5adcce85c4ca4863d28784a7d7f61c441a06c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588438"
---
# <a name="-imports-visual-basic"></a>-Importa (Visual Basic)
Importa namespaces de um assembly especificado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
-imports:namespaceList  
```  
  
## <a name="arguments"></a>Arguments  
  
|Termo|Definição|  
|---|---|  
|`namespaceList`|Necessário. Lista delimitada por vírgula de namespaces a serem importados.|  
  
## <a name="remarks"></a>Comentários  
 O `-imports` opção importa qualquer namespace definido dentro do conjunto atual de arquivos de origem ou de qualquer assembly referenciado.  
  
 Os membros no namespace especificado com `-imports` estão disponíveis para todos os arquivos de código-fonte na compilação. Use o [instrução Imports (tipo e Namespace .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para utilizar um namespace em um arquivo de código-fonte única.  
  
|Para definir /Imports no ambiente de desenvolvimento integrado do Visual Studio|  
|---|  
|1.  Selecione um projeto no **Gerenciador de Soluções**. No menu **Projeto**, clique em **Propriedades**. <br />2.  Clique na guia **Referências**.<br />3.  Insira o nome do namespace na caixa ao lado de **Adicionar importação de usuário** botão.<br />4.  Clique o **Adicionar importação de usuário** botão.|  
  
## <a name="example"></a>Exemplo  
 O código a seguir compila quando `/imports:system.globalization` for especificado. Sem ele, compilação bem-sucedida requer que um `Imports System.Globalization` instrução ser incluído no início do arquivo de código fonte ou a propriedade ser totalmente qualificada como `System.Globalization.CultureInfo.CurrentCulture.Name`. 
  
 [!code-vb[imports example](codesnippet/VisualBasic/imports_2.vb)]  
  
## <a name="see-also"></a>Consulte também
- [Compilador de linha de comando do Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Referências e a Instrução Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Linhas de Comando de Compilação de Exemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
