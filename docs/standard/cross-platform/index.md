---
title: "Desenvolvendo para várias plataformas com o .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6ad765ca133b9757d7649f55b9dc100084a753e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="developing-for-multiple-platforms-with-the-net-framework"></a><span data-ttu-id="34640-102">Desenvolvendo para várias plataformas com o .NET Framework</span><span class="sxs-lookup"><span data-stu-id="34640-102">Developing for Multiple Platforms with the .NET Framework</span></span>
<span data-ttu-id="34640-103">Você pode desenvolver aplicativos para plataformas Microsoft e não Microsoft usando o .NET Framework e o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="34640-103">You can develop apps for both Microsoft and non-Microsoft platforms by using the .NET Framework and Visual Studio.</span></span>  
  
## <a name="options-for-cross-platform-development"></a><span data-ttu-id="34640-104">Opções para o desenvolvimento de plataforma cruzada</span><span class="sxs-lookup"><span data-stu-id="34640-104">Options for cross-platform development</span></span>  
 <span data-ttu-id="34640-105">Para desenvolver várias plataformas, é possível compartilhar código-fonte ou binários, além de fazer chamadas entre o código do .NET Framework e as APIs do Tempo de Execução do Windows.</span><span class="sxs-lookup"><span data-stu-id="34640-105">To develop for multiple platforms, you can share source code or binaries, and you can make calls between .NET Framework code and Windows Runtime APIs.</span></span>  
  
|<span data-ttu-id="34640-106">Se desejar...</span><span class="sxs-lookup"><span data-stu-id="34640-106">If you want to...</span></span>|<span data-ttu-id="34640-107">Use...</span><span class="sxs-lookup"><span data-stu-id="34640-107">Use...</span></span>|  
|-----------------------|------------|  
|<span data-ttu-id="34640-108">Compartilhar código-fonte entre os aplicativos do Windows Phone 8.1 e do Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="34640-108">Share source code between Windows Phone 8.1 and Windows 8.1 apps</span></span>|<span data-ttu-id="34640-109">**Projetos compartilhados** (modelo de aplicativos Universal no Visual Studio 2013 atualização 2).</span><span class="sxs-lookup"><span data-stu-id="34640-109">**Shared projects** (Universal Apps template in Visual Studio 2013, Update 2).</span></span><br /><br /> <span data-ttu-id="34640-110">-No momento, não há suporte do Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="34640-110">-   Currently no Visual Basic support.</span></span><br /><span data-ttu-id="34640-111">-Você pode separar o código específico da plataforma usando #`if` instruções.</span><span class="sxs-lookup"><span data-stu-id="34640-111">-   You can separate platform-specific code by using #`if` statements.</span></span><br /><br /> <span data-ttu-id="34640-112">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="34640-112">For details, see:</span></span><br /><br /> <span data-ttu-id="34640-113">-   [Criar aplicativos para Windows e Windows Phone usando o Visual Studio](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx) (artigo do MSDN)</span><span class="sxs-lookup"><span data-stu-id="34640-113">-   [Build apps that target Windows and Windows Phone by using Visual Studio](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx) (MSDN article)</span></span><br /><span data-ttu-id="34640-114">-   [Usando o Visual Studio para criar aplicativos XAML Universal](http://blogs.msdn.com/b/visualstudio/archive/2014/04/14/using-visual-studio-to-build-universal-xaml-apps.aspx) (postagem do blog)</span><span class="sxs-lookup"><span data-stu-id="34640-114">-   [Using Visual Studio to build Universal XAML Apps](http://blogs.msdn.com/b/visualstudio/archive/2014/04/14/using-visual-studio-to-build-universal-xaml-apps.aspx) (blog post)</span></span><br /><span data-ttu-id="34640-115">-   [Usando o Visual Studio para criar aplicativos do XAML convergido](http://channel9.msdn.com/Events/Build/2014/3-591) (vídeo)</span><span class="sxs-lookup"><span data-stu-id="34640-115">-   [Using Visual Studio to Build XAML Converged Apps](http://channel9.msdn.com/Events/Build/2014/3-591) (video)</span></span>|  
|<span data-ttu-id="34640-116">Compartilhar binários entre aplicativos destinados a plataformas diferentes</span><span class="sxs-lookup"><span data-stu-id="34640-116">Share binaries between apps that target different platforms</span></span>|<span data-ttu-id="34640-117">**Projetos de biblioteca de classes portátil** para o código que é independente de plataforma.</span><span class="sxs-lookup"><span data-stu-id="34640-117">**Portable Class Library projects** for code that is platform-agnostic.</span></span><br /><br /> <span data-ttu-id="34640-118">-Essa abordagem geralmente é usada para o código que implementa a lógica de negócios.</span><span class="sxs-lookup"><span data-stu-id="34640-118">-   This approach is typically used for code that implements business logic.</span></span><br /><span data-ttu-id="34640-119">-Você pode usar o Visual Basic ou c#.</span><span class="sxs-lookup"><span data-stu-id="34640-119">-   You can use Visual Basic or C#.</span></span><br /><span data-ttu-id="34640-120">-Suporte a API varia por plataforma.</span><span class="sxs-lookup"><span data-stu-id="34640-120">-   API support varies by platform.</span></span><br /><span data-ttu-id="34640-121">-Portáteis projetos de biblioteca de classes que usam o Windows 8.1 e Windows Phone 8.1 oferecem suporte a APIs do Windows Runtime e XAML.</span><span class="sxs-lookup"><span data-stu-id="34640-121">-   Portable Class Library projects that target Windows 8.1 and Windows Phone 8.1 support Windows Runtime APIs and XAML.</span></span> <span data-ttu-id="34640-122">Esses recursos não estão disponíveis em versões anteriores da Biblioteca de Classes Portátil.</span><span class="sxs-lookup"><span data-stu-id="34640-122">These features aren't available in older versions of the Portable Class Library.</span></span><br /><span data-ttu-id="34640-123">-Se necessário, você pode abstrair o código específico da plataforma usando interfaces ou classes abstratas.</span><span class="sxs-lookup"><span data-stu-id="34640-123">-   If needed, you can abstract out platform-specific code by using interfaces or abstract classes.</span></span><br /><br /> <span data-ttu-id="34640-124">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="34640-124">For details, see:</span></span><br /><br /> <span data-ttu-id="34640-125">-   [Biblioteca de classes portátil](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) (artigo do MSDN)</span><span class="sxs-lookup"><span data-stu-id="34640-125">-   [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) (MSDN article)</span></span><br /><span data-ttu-id="34640-126">-   [Como fazer trabalhar de bibliotecas de classe portátil para você](http://blogs.msdn.com/b/dsplaisted/archive/2012/08/27/how-to-make-portable-class-libraries-work-for-you.aspx) (postagem do blog)</span><span class="sxs-lookup"><span data-stu-id="34640-126">-   [How to Make Portable Class Libraries Work for You](http://blogs.msdn.com/b/dsplaisted/archive/2012/08/27/how-to-make-portable-class-libraries-work-for-you.aspx) (blog post)</span></span><br /><span data-ttu-id="34640-127">-   [Usando a biblioteca de classes portátil com modelo MVVM](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md) (artigo do MSDN)</span><span class="sxs-lookup"><span data-stu-id="34640-127">-   [Using Portable Class Library with MVVM](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md) (MSDN article)</span></span><br /><span data-ttu-id="34640-128">-   [Recursos do aplicativo para bibliotecas que várias plataformas de destino](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md) (artigo do MSDN)</span><span class="sxs-lookup"><span data-stu-id="34640-128">-   [App Resources for Libraries That Target Multiple Platforms](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md) (MSDN article)</span></span><br /><span data-ttu-id="34640-129">-   [Analisador de portabilidade do .NET](http://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b) (extensão do Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="34640-129">-   [.NET Portability Analyzer](http://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b) (Visual Studio extension)</span></span>|  
|<span data-ttu-id="34640-130">Compartilhar código-fonte entre aplicativos para plataformas diferentes do Windows 8.1 e do Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="34640-130">Share source code between apps for platforms other than Windows 8.1 and Windows Phone 8.1</span></span>|<span data-ttu-id="34640-131">**Adicionar como vínculo** recurso.</span><span class="sxs-lookup"><span data-stu-id="34640-131">**Add as link** feature.</span></span><br /><br /> <span data-ttu-id="34640-132">-Esta abordagem é adequada para a lógica de aplicativo que é comum para ambos os aplicativos, mas não portátil, por alguma razão.</span><span class="sxs-lookup"><span data-stu-id="34640-132">-   This approach is suitable for app logic that's common to both apps but not portable, for some reason.</span></span> <span data-ttu-id="34640-133">É possível usar esse recurso para o código do C# ou do Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="34640-133">You can use this feature for C# or Visual Basic code.</span></span><br />     <span data-ttu-id="34640-134">Por exemplo, o Windows Phone 8 e o Windows 8 compartilham as APIs do Tempo de Execução do Windows, mas as Bibliotecas de Classes Portáteis não oferecem suporte ao Tempo de Execução do Windows para essas plataformas.</span><span class="sxs-lookup"><span data-stu-id="34640-134">For example, Windows Phone 8 and Windows 8 share Windows Runtime APIs, but Portable Class Libraries do not support Windows Runtime for those platforms.</span></span> <span data-ttu-id="34640-135">É possível usar `Add as link` para compartilhar o código do Tempo de Execução do Windows entre um aplicativo do Windows Phone 8 e um aplicativo da Windows Store destinado ao Windows 8.</span><span class="sxs-lookup"><span data-stu-id="34640-135">You can use `Add as link` to share common Windows Runtime code between a Windows Phone 8 app and a Windows Store app that targets Windows 8.</span></span><br /><br /> <span data-ttu-id="34640-136">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="34640-136">For details, see:</span></span><br /><br /> <span data-ttu-id="34640-137">-   [Compartilhar código com Adicionar como vínculo](http://msdn.microsoft.com/library/windowsphone/develop/jj714082\(v=vs.105\).aspx) (artigo do MSDN)</span><span class="sxs-lookup"><span data-stu-id="34640-137">-   [Share code with Add as Link](http://msdn.microsoft.com/library/windowsphone/develop/jj714082\(v=vs.105\).aspx) (MSDN article)</span></span><br /><span data-ttu-id="34640-138">-   [Como: adicionar itens existentes a um projeto](http://msdn.microsoft.com/library/vstudio/9f4t9t92\(v=vs.100\).aspx) (artigo do MSDN)</span><span class="sxs-lookup"><span data-stu-id="34640-138">-   [How to: Add Existing Items to a Project](http://msdn.microsoft.com/library/vstudio/9f4t9t92\(v=vs.100\).aspx) (MSDN article)</span></span>|  
|<span data-ttu-id="34640-139">Gravar aplicativos da Windows Store usando o .NET Framework ou chamar APIs do Tempo de Execução do Windows do código do .NET Framework</span><span class="sxs-lookup"><span data-stu-id="34640-139">Write Windows Store apps using the .NET Framework or call Windows Runtime APIs from .NET Framework code</span></span>|<span data-ttu-id="34640-140">**APIs do Windows Runtime** do seu código .NET Framework c# ou Visual Basic e usa o .NET Framework para criar aplicativos da Windows Store.</span><span class="sxs-lookup"><span data-stu-id="34640-140">**Windows Runtime APIs** from your .NET Framework C# or Visual Basic code, and use the .NET Framework to create Windows Store apps.</span></span> <span data-ttu-id="34640-141">Você deve saber as diferenças de API entre as duas plataformas.</span><span class="sxs-lookup"><span data-stu-id="34640-141">You should be aware of API differences between the two platforms.</span></span> <span data-ttu-id="34640-142">Porém, existem classes que ajudam a trabalhar com essas diferenças.</span><span class="sxs-lookup"><span data-stu-id="34640-142">However, there are classes to help you work with those differences.</span></span><br /><br /> <span data-ttu-id="34640-143">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="34640-143">For details, see:</span></span><br /><br /> <span data-ttu-id="34640-144">-   [.NET framework suporte para aplicativos da Windows Store e tempo de execução do Windows](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (artigo do MSDN)</span><span class="sxs-lookup"><span data-stu-id="34640-144">-   [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (MSDN article)</span></span><br /><span data-ttu-id="34640-145">-   [Passando um URI para o tempo de execução do Windows](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md) (artigo do MSDN)</span><span class="sxs-lookup"><span data-stu-id="34640-145">-   [Passing a URI to the Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md) (MSDN article)</span></span><br /><span data-ttu-id="34640-146">-   <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>-->`System.IO.WindowsRuntimeStreamExtensions` (Página de referência de API do MSDN)</span><span class="sxs-lookup"><span data-stu-id="34640-146">-   <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions` (MSDN API reference page)</span></span><br /><span data-ttu-id="34640-147">-   <!--zz <xref:System.WindowsRuntimeSystemExtensions>-->`System.WindowsRuntimeSystemExtensions` (Página de referência de API do MSDN)</span><span class="sxs-lookup"><span data-stu-id="34640-147">-   <!--zz <xref:System.WindowsRuntimeSystemExtensions>--> `System.WindowsRuntimeSystemExtensions` (MSDN API reference page)</span></span>|  
|<span data-ttu-id="34640-148">Compilar aplicativos do .NET Framework para plataformas que não sejam da Microsoft</span><span class="sxs-lookup"><span data-stu-id="34640-148">Build .NET Framework apps for non-Microsoft platforms</span></span>|<span data-ttu-id="34640-149">**Assemblies de referência de biblioteca de classes portátil** no .NET Framework e uma ferramenta de terceiros ou extensão do Visual Studio como Xamarin.</span><span class="sxs-lookup"><span data-stu-id="34640-149">**Portable Class Library reference assemblies** in the .NET Framework, and a Visual Studio extension or third-party tool such as Xamarin.</span></span><br /><br /> <span data-ttu-id="34640-150">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="34640-150">For details, see:</span></span><br /><br /> <span data-ttu-id="34640-151">-   [Biblioteca de classes portátil agora está disponível em todas as plataformas.](http://blogs.msdn.com/b/dotnet/archive/2013/10/14/portable-class-library-pcl-now-available-on-all-platforms.aspx)</span><span class="sxs-lookup"><span data-stu-id="34640-151">-   [Portable Class Library now available on all platforms.](http://blogs.msdn.com/b/dotnet/archive/2013/10/14/portable-class-library-pcl-now-available-on-all-platforms.aspx)</span></span> <span data-ttu-id="34640-152">(publicação de blog)</span><span class="sxs-lookup"><span data-stu-id="34640-152">(blog post)</span></span><br /><span data-ttu-id="34640-153">-   [Xamarin](http://xamarin.com/visual-studio) (Xamarin site)</span><span class="sxs-lookup"><span data-stu-id="34640-153">-   [Xamarin](http://xamarin.com/visual-studio) (Xamarin website)</span></span>|  
|<span data-ttu-id="34640-154">Usar JavaScript e HTML para desenvolvimento de plataforma cruzada</span><span class="sxs-lookup"><span data-stu-id="34640-154">Use JavaScript and HTML for cross-platform development</span></span>|<span data-ttu-id="34640-155">**Modelos de aplicativo universais** no Visual Studio 2013, atualização 2 para desenvolver com APIs do Windows Runtime para Windows 8.1 e Windows Phone 8.1.</span><span class="sxs-lookup"><span data-stu-id="34640-155">**Universal App templates** in Visual Studio 2013, Update 2 to develop against Windows Runtime APIs for Windows 8.1 and Windows Phone 8.1.</span></span> <span data-ttu-id="34640-156">Atualmente, não é possível usar JavaScript e HTML com APIs do .NET Framework para desenvolver aplicativos de plataforma cruzada.</span><span class="sxs-lookup"><span data-stu-id="34640-156">Currently, you can’t use JavaScript and HTML with .NET Framework APIs to develop cross-platform apps.</span></span><br /><br /> <span data-ttu-id="34640-157">Para obter detalhes, consulte:</span><span class="sxs-lookup"><span data-stu-id="34640-157">For details, see:</span></span><br /><br /> <span data-ttu-id="34640-158">-   [Modelos de projeto de JavaScript](http://msdn.microsoft.com/library/windows/apps/hh758331.aspx)</span><span class="sxs-lookup"><span data-stu-id="34640-158">-   [JavaScript Project Templates](http://msdn.microsoft.com/library/windows/apps/hh758331.aspx)</span></span><br /><span data-ttu-id="34640-159">-   [Portando um aplicativo de tempo de execução do Windows usando JavaScript para Windows Phone](http://msdn.microsoft.com/library/windows/apps/dn636144.aspx)</span><span class="sxs-lookup"><span data-stu-id="34640-159">-   [Porting a Windows Runtime app using JavaScript to Windows Phone](http://msdn.microsoft.com/library/windows/apps/dn636144.aspx)</span></span>|