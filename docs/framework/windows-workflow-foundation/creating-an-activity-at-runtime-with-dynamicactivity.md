---
title: "Criando uma atividade em tempo de execução com o DynamicActivity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c984d235521a86c9657630d7ace3341c68f806ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a><span data-ttu-id="b30e6-102">Criando uma atividade em tempo de execução com o DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="b30e6-102">Creating an Activity at Runtime with DynamicActivity</span></span>
<span data-ttu-id="b30e6-103"><xref:System.Activities.DynamicActivity> é um concreto, classe lacradas com um construtor público.</span><span class="sxs-lookup"><span data-stu-id="b30e6-103"><xref:System.Activities.DynamicActivity> is a concrete, sealed class with a public constructor.</span></span> <span data-ttu-id="b30e6-104"><xref:System.Activities.DynamicActivity> pode ser usado para reunir a funcionalidade de atividade em tempo de execução usando os DOM de uma atividade.</span><span class="sxs-lookup"><span data-stu-id="b30e6-104"><xref:System.Activities.DynamicActivity> can be used to assemble activity functionality at runtime using an activity DOM.</span></span>  
  
## <a name="dynamicactivity-features"></a><span data-ttu-id="b30e6-105">Recursos de DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="b30e6-105">DynamicActivity Features</span></span>  
 <span data-ttu-id="b30e6-106"><xref:System.Activities.DynamicActivity> tem acesso às propriedades de execução, os argumentos e variáveis, mas nenhum o acesso aos serviços de tempo de execução como atividades filhos de programação ou o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="b30e6-106"><xref:System.Activities.DynamicActivity> has access to execution properties, arguments and variables, but no access to run-time services such as scheduling child activities or tracking.</span></span>  
  
 <span data-ttu-id="b30e6-107">As propriedades de nível superior podem ser definidas usando objetos de <xref:System.Activities.Argument> de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b30e6-107">Top-level properties can be set using workflow <xref:System.Activities.Argument> objects.</span></span> <span data-ttu-id="b30e6-108">No código obrigatório, esses argumentos são criados usando propriedades de CLR em um novo tipo.</span><span class="sxs-lookup"><span data-stu-id="b30e6-108">In imperative code, these arguments are created using CLR properties on a new type.</span></span> <span data-ttu-id="b30e6-109">Em XAML, são declarados usando `x:Class` e marcas de `x:Member` .</span><span class="sxs-lookup"><span data-stu-id="b30e6-109">In XAML, they are declared using `x:Class` and `x:Member` tags.</span></span>  
  
 <span data-ttu-id="b30e6-110">Atividades construídas usando a interface de <xref:System.Activities.DynamicActivity> com o designer que usa <xref:System.ComponentModel.ICustomTypeDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="b30e6-110">Activities constructed using <xref:System.Activities.DynamicActivity> interface with the designer using <xref:System.ComponentModel.ICustomTypeDescriptor>.</span></span> <span data-ttu-id="b30e6-111">As atividades criadas no designer podem ser carregadas dinamicamente usando <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, como demonstrado no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="b30e6-111">Activities created in the designer can be loaded dynamically using <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, as demonstrated in the following procedure.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a><span data-ttu-id="b30e6-112">Para criar uma atividade em tempo de execução usando o código obrigatório</span><span class="sxs-lookup"><span data-stu-id="b30e6-112">To create an activity at runtime using imperative code</span></span>  
  
1.  <span data-ttu-id="b30e6-113">Abra[!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b30e6-113">Open[!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="b30e6-114">Selecione **arquivo**, **novo**, **projeto**.</span><span class="sxs-lookup"><span data-stu-id="b30e6-114">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="b30e6-115">Selecione **Workflow 4.0** em **Visual C#** no **tipos de projeto** janela e selecione o **v2010** nó.</span><span class="sxs-lookup"><span data-stu-id="b30e6-115">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="b30e6-116">Selecione **aplicativo de Console de fluxo de trabalho sequencial** no **modelos** janela.</span><span class="sxs-lookup"><span data-stu-id="b30e6-116">Select **Sequential Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="b30e6-117">Nomeie o novo projeto DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="b30e6-117">Name the new project DynamicActivitySample.</span></span>  
  
3.  <span data-ttu-id="b30e6-118">Workflow1.xaml no projeto HelloActivity e selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="b30e6-118">Right-click Workflow1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="b30e6-119">Abra Module.vb.</span><span class="sxs-lookup"><span data-stu-id="b30e6-119">Open Program.cs.</span></span> <span data-ttu-id="b30e6-120">Adicione a seguinte diretiva para a parte superior do arquivo.</span><span class="sxs-lookup"><span data-stu-id="b30e6-120">Add the following directive to the top of the file.</span></span>  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
5.  <span data-ttu-id="b30e6-121">Substitua o conteúdo do método de `Main` com o código a seguir, que cria uma atividade de <xref:System.Activities.Statements.Sequence> que contém uma única atividade de <xref:System.Activities.Statements.WriteLine> e a atribui à propriedade de <xref:System.Activities.DynamicActivity.Implementation%2A> de uma nova atividade dinâmico.</span><span class="sxs-lookup"><span data-stu-id="b30e6-121">Replace the contents of the `Main` method with the following code, which creates a <xref:System.Activities.Statements.Sequence> activity that contains a single <xref:System.Activities.Statements.WriteLine> activity and assigns it to the <xref:System.Activities.DynamicActivity.Implementation%2A> property of a new dynamic activity.</span></span>  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =   
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =   
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6.  <span data-ttu-id="b30e6-122">Executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b30e6-122">Execute the application.</span></span> <span data-ttu-id="b30e6-123">Uma janela de console com o texto "Olá, mundo!"</span><span class="sxs-lookup"><span data-stu-id="b30e6-123">A console window with the text "Hello World!"</span></span> <span data-ttu-id="b30e6-124">Exibe.</span><span class="sxs-lookup"><span data-stu-id="b30e6-124">displays.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a><span data-ttu-id="b30e6-125">Para criar uma atividade em tempo de execução usando XAML</span><span class="sxs-lookup"><span data-stu-id="b30e6-125">To create an activity at runtime using XAML</span></span>  
  
1.  <span data-ttu-id="b30e6-126">Abra [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b30e6-126">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="b30e6-127">Selecione **arquivo**, **novo**, **projeto**.</span><span class="sxs-lookup"><span data-stu-id="b30e6-127">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="b30e6-128">Selecione **Workflow 4.0** em **Visual C#** no **tipos de projeto** janela e selecione o **v2010** nó.</span><span class="sxs-lookup"><span data-stu-id="b30e6-128">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="b30e6-129">Selecione **aplicativo de Console do fluxo de trabalho** no **modelos** janela.</span><span class="sxs-lookup"><span data-stu-id="b30e6-129">Select  **Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="b30e6-130">Nomeie o novo projeto DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="b30e6-130">Name the new project DynamicActivitySample.</span></span>  
  
3.  <span data-ttu-id="b30e6-131">Workflow1.xaml aberto no projeto de HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="b30e6-131">Open Workflow1.xaml in the HelloActivity project.</span></span> <span data-ttu-id="b30e6-132">Clique o **argumentos** opção na parte inferior do designer.</span><span class="sxs-lookup"><span data-stu-id="b30e6-132">Click the **Arguments** option at the bottom of the designer.</span></span> <span data-ttu-id="b30e6-133">Crie um novo argumento de `In` chamado `TextToWrite` de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="b30e6-133">Create a new `In` argument called `TextToWrite` of type `String`.</span></span>  
  
4.  <span data-ttu-id="b30e6-134">Arraste um **WriteLine** atividade a partir de **primitivos** seção da caixa de ferramentas para a superfície de designer.</span><span class="sxs-lookup"><span data-stu-id="b30e6-134">Drag a **WriteLine** activity from the **Primitives** section of the toolbox onto the designer surface.</span></span> <span data-ttu-id="b30e6-135">Atribuir o valor `TextToWrite` para o **texto** propriedade da atividade.</span><span class="sxs-lookup"><span data-stu-id="b30e6-135">Assign the value `TextToWrite` to the **Text** property of the activity.</span></span>  
  
5.  <span data-ttu-id="b30e6-136">Abra Module.vb.</span><span class="sxs-lookup"><span data-stu-id="b30e6-136">Open Program.cs.</span></span> <span data-ttu-id="b30e6-137">Adicione a seguinte diretiva para a parte superior do arquivo.</span><span class="sxs-lookup"><span data-stu-id="b30e6-137">Add the following directive to the top of the file.</span></span>  
  
    ```  
    using System.Activities.XamlIntegration;  
    ```  
  
6.  <span data-ttu-id="b30e6-138">Substitua o conteúdo do método de `Main` com o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="b30e6-138">Replace the contents of the `Main` method with the following code.</span></span>  
  
    ```  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7.  <span data-ttu-id="b30e6-139">Executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b30e6-139">Execute the application.</span></span> <span data-ttu-id="b30e6-140">Uma janela de console com o texto "Olá, mundo!"</span><span class="sxs-lookup"><span data-stu-id="b30e6-140">A console window with the text "Hello World!"</span></span> <span data-ttu-id="b30e6-141">é exibida.</span><span class="sxs-lookup"><span data-stu-id="b30e6-141">appears.</span></span>  
  
8.  <span data-ttu-id="b30e6-142">Clique no arquivo Workflow1.xaml no **Solution Explorer** e selecione **Exibir código**.</span><span class="sxs-lookup"><span data-stu-id="b30e6-142">Right-click the Workflow1.xaml file in the **Solution Explorer** and select **View Code**.</span></span> <span data-ttu-id="b30e6-143">Observe que a classe da atividade é criada com `x:Class` e a propriedade é criada com `x:Property`.</span><span class="sxs-lookup"><span data-stu-id="b30e6-143">Note that the activity class is created with `x:Class` and the property is created with `x:Property`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b30e6-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b30e6-144">See Also</span></span>  
 [<span data-ttu-id="b30e6-145">Criando fluxos de trabalho, atividades e expressões de design usando o código obrigatório</span><span class="sxs-lookup"><span data-stu-id="b30e6-145">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)  
 [<span data-ttu-id="b30e6-146">Criação de DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="b30e6-146">DynamicActivity Creation</span></span>](../../../docs/framework/windows-workflow-foundation/samples/dynamicactivity-creation.md)