---
title: "Como modificar o conteúdo de uma cadeia de caracteres – Guia de C#"
ms.date: 02/26/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- strings [C#], modifying
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 830ca207c4cd5bd24dbb667328465cafb2509409
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2018
---
# <a name="how-to-modify-string-contents-in-c"></a><span data-ttu-id="abf26-102">Como modificar o conteúdo de uma cadeia de caracteres em C#</span><span class="sxs-lookup"><span data-stu-id="abf26-102">How to: Modify string contents in C#</span></span> #

<span data-ttu-id="abf26-103">Este artigo demonstra várias técnicas para produzir um `string` modificando um `string` existente.</span><span class="sxs-lookup"><span data-stu-id="abf26-103">This article demonstrates several techniques to produce a `string` by modifying an existing `string`.</span></span> <span data-ttu-id="abf26-104">Todas as técnicas demonstradas retornam o resultado das modificações como um novo objeto `string`.</span><span class="sxs-lookup"><span data-stu-id="abf26-104">All the techniques demonstrated return the result of the modifications as a new `string` object.</span></span> <span data-ttu-id="abf26-105">Para demonstrar isso claramente, todos os exemplos armazenam o resultado em uma nova variável.</span><span class="sxs-lookup"><span data-stu-id="abf26-105">To clearly demonstrate this, the examples all store the result in a new variable.</span></span> <span data-ttu-id="abf26-106">Em seguida, você pode examinar o `string` original e o `string` resultante da modificação quando você executa cada exemplo.</span><span class="sxs-lookup"><span data-stu-id="abf26-106">You can then examine both the original `string` and the `string` resulting from the modification when you run each example.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="abf26-107">Há várias técnicas demonstradas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="abf26-107">There are several techniques demonstrated in this article.</span></span> <span data-ttu-id="abf26-108">Você pode substituir o texto existente.</span><span class="sxs-lookup"><span data-stu-id="abf26-108">You can replace existing text.</span></span> <span data-ttu-id="abf26-109">Você pode procurar padrões e substituir o texto correspondente com outro texto.</span><span class="sxs-lookup"><span data-stu-id="abf26-109">You can search for patterns and replace matching text with other text.</span></span> <span data-ttu-id="abf26-110">Você pode tratar uma cadeia de caracteres como uma sequência de caracteres.</span><span class="sxs-lookup"><span data-stu-id="abf26-110">You can treat a string as a sequence of characters.</span></span> <span data-ttu-id="abf26-111">Você também pode usar métodos de conveniência que removem o espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="abf26-111">You can also use convenience methods that remove white space.</span></span> <span data-ttu-id="abf26-112">Você deve escolher as técnicas que mais se aproximam do seu cenário.</span><span class="sxs-lookup"><span data-stu-id="abf26-112">You should choose the techniques that most closely match your scenario.</span></span>

## <a name="replace-text"></a><span data-ttu-id="abf26-113">Substituir texto</span><span class="sxs-lookup"><span data-stu-id="abf26-113">Replace text</span></span>

<span data-ttu-id="abf26-114">O código a seguir cria uma nova cadeia de caracteres, substituindo o texto existente por um substituto.</span><span class="sxs-lookup"><span data-stu-id="abf26-114">The following code creates a new string by replacing existing text with a substitute.</span></span>

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#1)]

<span data-ttu-id="abf26-115">O código anterior demonstra essa propriedade *immutable* de cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="abf26-115">The preceding code demonstrates this *immutable* property of strings.</span></span> <span data-ttu-id="abf26-116">Você pode ver no exemplo anterior que a cadeia de caracteres original, `source`, não é modificada.</span><span class="sxs-lookup"><span data-stu-id="abf26-116">You can see in the preceding example that the original string, `source`, is not modified.</span></span> <span data-ttu-id="abf26-117">O método <xref:System.String.Replace%2A?displayProperty=nameWithType> cria uma nova `string` contendo as modificações.</span><span class="sxs-lookup"><span data-stu-id="abf26-117">The <xref:System.String.Replace%2A?displayProperty=nameWithType> method creates a new `string` containing the modifications.</span></span>

<span data-ttu-id="abf26-118">O método <xref:System.String.Replace%2A> pode substituir cadeias de caracteres ou caracteres únicos.</span><span class="sxs-lookup"><span data-stu-id="abf26-118">The <xref:System.String.Replace%2A> method can replace either strings or single characters.</span></span> <span data-ttu-id="abf26-119">Em ambos os casos, todas as ocorrências do texto pesquisado são substituídas.</span><span class="sxs-lookup"><span data-stu-id="abf26-119">In both cases, every occurrence of the sought text is replaced.</span></span>  <span data-ttu-id="abf26-120">O exemplo a seguir substitui todos os caracteres ' ' com '\_':</span><span class="sxs-lookup"><span data-stu-id="abf26-120">The following example replaces all ' ' characters with '\_':</span></span>

[!code-csharp-interactive[replace characters](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#2)]

<span data-ttu-id="abf26-121">A cadeia de caracteres de origem não é alterada e uma nova cadeia de caracteres é retornada com a substituição.</span><span class="sxs-lookup"><span data-stu-id="abf26-121">The source string is unchanged, and a new string is returned with the replacement.</span></span>

## <a name="trim-white-space"></a><span data-ttu-id="abf26-122">Cortar espaço em branco</span><span class="sxs-lookup"><span data-stu-id="abf26-122">Trim white space</span></span>

<span data-ttu-id="abf26-123">Você pode usar os métodos <xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType> e <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> para remover espaços em branco à esquerda ou à direita.</span><span class="sxs-lookup"><span data-stu-id="abf26-123">You can use the <xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType>, and <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> methods to remove any leading or trailing white space.</span></span>  <span data-ttu-id="abf26-124">O código a seguir mostra um exemplo de cada um desses casos.</span><span class="sxs-lookup"><span data-stu-id="abf26-124">The following code shows an example of each.</span></span> <span data-ttu-id="abf26-125">A cadeia de caracteres de origem não é alterada; esses métodos retornam uma nova cadeia de caracteres com o conteúdo modificado.</span><span class="sxs-lookup"><span data-stu-id="abf26-125">The source string does not change; these methods return a new string with the modified contents.</span></span>

[!code-csharp-interactive[trim white space](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#3)]

## <a name="remove-text"></a><span data-ttu-id="abf26-126">Remover texto</span><span class="sxs-lookup"><span data-stu-id="abf26-126">Remove text</span></span>

<span data-ttu-id="abf26-127">Você pode remover texto de uma cadeia de caracteres usando o método <xref:System.String.Remove%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="abf26-127">You can remove text from a string using the <xref:System.String.Remove%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="abf26-128">Esse método remove um número de caracteres começando em um índice específico.</span><span class="sxs-lookup"><span data-stu-id="abf26-128">This method removes a number of characters starting at a specific index.</span></span> <span data-ttu-id="abf26-129">O exemplo a seguir mostra como usar <xref:System.String.IndexOf%2A?displayProperty=nameWithType> seguido por <xref:System.String.Remove%2A> para remover texto de uma cadeia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="abf26-129">The following example shows how to use <xref:System.String.IndexOf%2A?displayProperty=nameWithType> followed by <xref:System.String.Remove%2A> to remove text from a string:</span></span>

[!code-csharp-interactive[remove text](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#4)]

## <a name="replace-matching-patterns"></a><span data-ttu-id="abf26-130">Substituir padrões correspondentes</span><span class="sxs-lookup"><span data-stu-id="abf26-130">Replace matching patterns</span></span>

<span data-ttu-id="abf26-131">Você pode usar [expressões regulares](../../standard/base-types/regular-expressions.md) para substituir padrões correspondentes de texto com um novo texto, possivelmente definido por um padrão.</span><span class="sxs-lookup"><span data-stu-id="abf26-131">You can use [regular expressions](../../standard/base-types/regular-expressions.md) to replace text matching patterns with new text, possibly defined by a pattern.</span></span> <span data-ttu-id="abf26-132">O exemplo a seguir usa a classe <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> para localizar um padrão em uma cadeia de caracteres de origem e substituí-lo pela capitalização correta.</span><span class="sxs-lookup"><span data-stu-id="abf26-132">The following example uses the <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> class to find a pattern in a source string and replace it with proper capitalization.</span></span> <span data-ttu-id="abf26-133">O método <xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> usa uma função que fornece a lógica de substituição como um de seus argumentos.</span><span class="sxs-lookup"><span data-stu-id="abf26-133">The <xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> method takes a function that provides the logic of the replacement as one of its arguments.</span></span> <span data-ttu-id="abf26-134">Neste exemplo, essa função `LocalReplaceMatchCase` é uma **função local** declarada dentro do método de exemplo.</span><span class="sxs-lookup"><span data-stu-id="abf26-134">In this example, that function, `LocalReplaceMatchCase` is a **local function** declared inside the sample method.</span></span> <span data-ttu-id="abf26-135">`LocalReplaceMatchCase` usa a classe <xref:System.Text.StringBuilder?displayProperty=nameWithType> para criar a cadeia de caracteres de substituição com a capitalização correta.</span><span class="sxs-lookup"><span data-stu-id="abf26-135">`LocalReplaceMatchCase` uses the <xref:System.Text.StringBuilder?displayProperty=nameWithType> class to build the replacement string with proper capitalization.</span></span>

<span data-ttu-id="abf26-136">Expressões regulares são mais úteis para localizar e substituir texto que segue um padrão, em vez de texto conhecido.</span><span class="sxs-lookup"><span data-stu-id="abf26-136">Regular expressions are most useful for searching and replacing text that follows a pattern, rather than known text.</span></span> <span data-ttu-id="abf26-137">Consulte [Como pesquisar cadeias de caracteres](search-strings.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="abf26-137">See [How to: search strings](search-strings.md) for more details.</span></span> <span data-ttu-id="abf26-138">O padrão de pesquisa "the\s" procura a palavra "the" seguida por um caractere de espaço em branco.</span><span class="sxs-lookup"><span data-stu-id="abf26-138">The search pattern, "the\s" searches for the word "the" followed by a white-space character.</span></span> <span data-ttu-id="abf26-139">Essa parte do padrão garante que isso não corresponda a "there" na cadeia de caracteres de origem.</span><span class="sxs-lookup"><span data-stu-id="abf26-139">That part of the pattern ensures that it doesn't match "there" in the source string.</span></span> <span data-ttu-id="abf26-140">Para obter mais informações sobre elementos de linguagem de expressão regular, consulte [Linguagem de expressão regular – referência rápida](../../standard/base-types/regular-expression-language-quick-reference.md).</span><span class="sxs-lookup"><span data-stu-id="abf26-140">For more information on regular expression language elements, see [Regular Expression Language - Quick Reference](../../standard/base-types/regular-expression-language-quick-reference.md).</span></span>

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#5)]

<span data-ttu-id="abf26-141">O método <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> retorna uma cadeia de caracteres imutável com o conteúdo no objeto <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="abf26-141">The <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> method returns an immutable string with the contents in the <xref:System.Text.StringBuilder> object.</span></span>

## <a name="modifying-individual-characters"></a><span data-ttu-id="abf26-142">Modificar caracteres individuais</span><span class="sxs-lookup"><span data-stu-id="abf26-142">Modifying individual characters</span></span>

<span data-ttu-id="abf26-143">Você pode produzir uma matriz de caracteres de uma cadeia de caracteres, modificar o conteúdo da matriz e, em seguida, criar uma nova cadeia de caracteres com base no conteúdo modificado da matriz.</span><span class="sxs-lookup"><span data-stu-id="abf26-143">You can produce a character array from a string, modify the contents of the array, and then create a new string from the modified contents of the array.</span></span>

<span data-ttu-id="abf26-144">O exemplo a seguir mostra como substituir um conjunto de caracteres em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="abf26-144">The following example shows how to replace a set of characters in a string.</span></span> <span data-ttu-id="abf26-145">Primeiro, ele usa o método <xref:System.String.ToCharArray?displayProperty=nameWithName> para criar uma matriz de caracteres.</span><span class="sxs-lookup"><span data-stu-id="abf26-145">First, it uses the <xref:System.String.ToCharArray?displayProperty=nameWithName> method to create an array of characters.</span></span> <span data-ttu-id="abf26-146">Ele usa o método <xref:System.String.IndexOf%2A> para localizar o índice inicial da palavra "fox".</span><span class="sxs-lookup"><span data-stu-id="abf26-146">It uses the <xref:System.String.IndexOf%2A> method to find the starting index of the word "fox."</span></span> <span data-ttu-id="abf26-147">Os próximos três caracteres são substituídos por uma palavra diferente.</span><span class="sxs-lookup"><span data-stu-id="abf26-147">The next three characters are replaced with a different word.</span></span> <span data-ttu-id="abf26-148">Por fim, uma nova cadeia de caracteres é construída com a matriz de caracteres atualizada.</span><span class="sxs-lookup"><span data-stu-id="abf26-148">Finally, a new string is constructed from the updated character array.</span></span>

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#6)]

## <a name="unsafe-modifications-to-string"></a><span data-ttu-id="abf26-149">Modificações não seguras à cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="abf26-149">Unsafe modifications to string</span></span>

<span data-ttu-id="abf26-150">Usando código **não seguro**, é possível modificar uma cadeia de caracteres "no local" depois que ela é criada.</span><span class="sxs-lookup"><span data-stu-id="abf26-150">Using **unsafe** code, you can modify a string "in place" after it has been created.</span></span> <span data-ttu-id="abf26-151">Código não seguro usa muitos dos recursos do .NET projetados para minimizar determinados tipos de bugs no código.</span><span class="sxs-lookup"><span data-stu-id="abf26-151">Unsafe code bypasses many of the features of .NET designed to minimize certain types of bugs in code.</span></span> <span data-ttu-id="abf26-152">Você precisa usar o código não seguro para modificar uma cadeia de caracteres em vigor porque a classe de cadeia de caracteres foi projetada como um tipo **immutable**.</span><span class="sxs-lookup"><span data-stu-id="abf26-152">You need to use unsafe code to modify a string in place because the string class is designed as an **immutable** type.</span></span> <span data-ttu-id="abf26-153">Depois de ela ser criada, seu valor não é alterado.</span><span class="sxs-lookup"><span data-stu-id="abf26-153">Once it has been created, its value does not change.</span></span> <span data-ttu-id="abf26-154">O código não seguro contorna a essa propriedade, acessando e modificando a memória usada por um `string` sem usar métodos `string` normais.</span><span class="sxs-lookup"><span data-stu-id="abf26-154">Unsafe code circumvents this property by accessing and modifying the memory used by a `string` without using normal `string` methods.</span></span>
<span data-ttu-id="abf26-155">O exemplo a seguir é fornecido para as raras situações em que você deseja modificar uma cadeia de caracteres no local usando código não seguro.</span><span class="sxs-lookup"><span data-stu-id="abf26-155">The following example is provided for those rare situations where you want to modify a string in-place using unsafe code.</span></span> <span data-ttu-id="abf26-156">O exemplo mostra como usar a palavra-chave `fixed`.</span><span class="sxs-lookup"><span data-stu-id="abf26-156">The example shows how to use the `fixed` keyword.</span></span> <span data-ttu-id="abf26-157">A palavra-chave `fixed` impede que o GC (coletor de lixo) mova o objeto de cadeia de caracteres na memória enquanto o código acessa a memória usando o ponteiro não seguro.</span><span class="sxs-lookup"><span data-stu-id="abf26-157">The `fixed` keyword prevents the garbage collector (GC) from moving the string object in memory while code accesses the memory using the unsafe pointer.</span></span> <span data-ttu-id="abf26-158">Ele também demonstra um possível efeito colateral das operações não seguras em cadeias de caracteres, que resultam da forma com que o compilador C# armazena (interna) as cadeias de caracteres internamente.</span><span class="sxs-lookup"><span data-stu-id="abf26-158">It also demonstrates one possible side effect of unsafe operations on strings that results from the way that the C# compiler stores (interns) strings internally.</span></span> <span data-ttu-id="abf26-159">Em geral, você não deve usar essa técnica, a menos que seja absolutamente necessário.</span><span class="sxs-lookup"><span data-stu-id="abf26-159">In general, you shouldn't use this technique unless it is absolutely necessary.</span></span> <span data-ttu-id="abf26-160">É possível aprender mais sobre [não seguro](../language-reference/keywords/unsafe.md) e [fixo](../language-reference/keywords/fixed-statement.md) nos artigos.</span><span class="sxs-lookup"><span data-stu-id="abf26-160">You can learn more in the articles on [unsafe](../language-reference/keywords/unsafe.md) and [fixed](../language-reference/keywords/fixed-statement.md).</span></span> <span data-ttu-id="abf26-161">A referência à API para <xref:System.String.Intern%2A> inclui informações sobre centralização de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="abf26-161">The API reference for <xref:System.String.Intern%2A> includes inforamtion on string interning.</span></span>

[!code-csharp-interactive[unsafe ways to create a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#7)]

<span data-ttu-id="abf26-162">Você pode experimentar estes exemplos examinando o código em nosso [repositório GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings).</span><span class="sxs-lookup"><span data-stu-id="abf26-162">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings).</span></span> <span data-ttu-id="abf26-163">Ou então, você pode baixar os exemplos [como um arquivo zip](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings.zip).</span><span class="sxs-lookup"><span data-stu-id="abf26-163">Or you can download the samples [as a zip file](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings.zip).</span></span>

## <a name="see-also"></a><span data-ttu-id="abf26-164">Consulte também</span><span class="sxs-lookup"><span data-stu-id="abf26-164">See also</span></span>

[<span data-ttu-id="abf26-165">Expressões regulares do .NET Framework</span><span class="sxs-lookup"><span data-stu-id="abf26-165">.NET Framework Regular Expressions</span></span>](../../standard/base-types/regular-expressions.md)  
 [<span data-ttu-id="abf26-166">Linguagem de expressão regular – referência rápida</span><span class="sxs-lookup"><span data-stu-id="abf26-166">Regular Expression Language - Quick Reference</span></span>](../../standard/base-types/regular-expression-language-quick-reference.md)  