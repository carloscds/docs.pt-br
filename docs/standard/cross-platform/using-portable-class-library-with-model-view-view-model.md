---
title: "Usando a Biblioteca de Classes Portátil com Modelo MVVM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e39a8df5c8aee05414e778f15a29bbeda8dba930
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="5e544-102">Usando a Biblioteca de Classes Portátil com Modelo MVVM</span><span class="sxs-lookup"><span data-stu-id="5e544-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="5e544-103">Você pode usar o .NET Framework [biblioteca de classes portátil](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) para implementar o padrão do modo de exibição de modelo modelo MVVM () e compartilhar assemblies em várias plataformas.</span><span class="sxs-lookup"><span data-stu-id="5e544-103">You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>  
  
 <span data-ttu-id="5e544-104">MVVM é um padrão de aplicativo que isola a interface do usuário da lógica de negócios subjacente.</span><span class="sxs-lookup"><span data-stu-id="5e544-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="5e544-105">Você pode implementar classes de modelo do modelo e o modo de exibição em uma [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project no [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]e, em seguida, criar modos de exibição personalizados para diferentes plataformas.</span><span class="sxs-lookup"><span data-stu-id="5e544-105">You can implement the model and view model classes in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], and then create views that are customized for different platforms.</span></span> <span data-ttu-id="5e544-106">Essa abordagem permite que você grave os dados de modelo e lógica de negócios apenas uma vez e usar esse código do .NET Framework, Silverlight, Windows Phone, e [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicativos, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="5e544-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="5e544-107">![Portátil com diagrama MVVM](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span><span class="sxs-lookup"><span data-stu-id="5e544-107">![Portable with MVVM diagram](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span></span>  
  
 <span data-ttu-id="5e544-108">Este tópico fornece informações gerais sobre o padrão MVVM.</span><span class="sxs-lookup"><span data-stu-id="5e544-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="5e544-109">Ele só fornece informações sobre como usar [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] para implementar MVVM.</span><span class="sxs-lookup"><span data-stu-id="5e544-109">It only provides information about how to use [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] to implement MVVM.</span></span> <span data-ttu-id="5e544-110">Para obter mais informações sobre MVVM, consulte o [MVVM Quickstart](http://go.microsoft.com/fwlink/?LinkId=234934).</span><span class="sxs-lookup"><span data-stu-id="5e544-110">For more information about MVVM, see the [MVVM Quickstart](http://go.microsoft.com/fwlink/?LinkId=234934).</span></span>  
  
## <a name="classes-that-support-mvvm"></a><span data-ttu-id="5e544-111">Classes que oferecem suporte MVVM</span><span class="sxs-lookup"><span data-stu-id="5e544-111">Classes That Support MVVM</span></span>  
 <span data-ttu-id="5e544-112">Quando você seleciona o [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight ou Windows Phone 7.5 para seu [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] projeto, as classes a seguir estão disponíveis para implementar o padrão MVVM:</span><span class="sxs-lookup"><span data-stu-id="5e544-112">When you target the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, or Windows Phone 7.5 for your [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, the following classes are available for implementing the MVVM pattern:</span></span>  
  
-   <span data-ttu-id="5e544-113">Classe <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5e544-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="5e544-114">Classe <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5e544-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="5e544-115">Classe <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5e544-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="5e544-116">Classe <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5e544-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="5e544-117">Classe <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5e544-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="5e544-118">Classe <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5e544-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="5e544-119">Classe <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5e544-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="5e544-120">Classe <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5e544-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="5e544-121">Classe <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5e544-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="5e544-122">Classe <xref:System.Windows.Input.ICommand?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5e544-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>  
  
-   <span data-ttu-id="5e544-123">Todas as classes de <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span><span class="sxs-lookup"><span data-stu-id="5e544-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>  
  
## <a name="implementing-mvvm"></a><span data-ttu-id="5e544-124">Implementando MVVM</span><span class="sxs-lookup"><span data-stu-id="5e544-124">Implementing MVVM</span></span>  
 <span data-ttu-id="5e544-125">Para implementar MVVM, você normalmente cria o modelo e o modelo de exibição em uma [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] projeto, porque um [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] projeto não pode fazer referência a um projeto não portátil.</span><span class="sxs-lookup"><span data-stu-id="5e544-125">To implement MVVM, you typically create both the model and the view model in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, because a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project cannot reference a non-portable project.</span></span> <span data-ttu-id="5e544-126">O modelo e o modelo de exibição podem ser no mesmo projeto ou em projetos separados.</span><span class="sxs-lookup"><span data-stu-id="5e544-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="5e544-127">Se você usar projetos separados, adicione uma referência do projeto do modelo de exibição para o projeto de modelo.</span><span class="sxs-lookup"><span data-stu-id="5e544-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>  
  
 <span data-ttu-id="5e544-128">Depois de compilar o modelo e exibir projetos de modelo, você pode referenciar os assemblies no aplicativo que contém a exibição.</span><span class="sxs-lookup"><span data-stu-id="5e544-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="5e544-129">Se o modo de exibição interage somente com o modelo de exibição, você só precisa fazer referência ao assembly que contém o modelo de exibição.</span><span class="sxs-lookup"><span data-stu-id="5e544-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>  
  
### <a name="model"></a><span data-ttu-id="5e544-130">Modelo</span><span class="sxs-lookup"><span data-stu-id="5e544-130">Model</span></span>  
 <span data-ttu-id="5e544-131">O exemplo a seguir mostra uma classe de modelo simplificado que pode residir em um [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] projeto.</span><span class="sxs-lookup"><span data-stu-id="5e544-131">The following example shows a simplified model class that could reside in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 <span data-ttu-id="5e544-132">O exemplo a seguir mostra uma maneira simple de popular, recuperar e atualizar os dados em um [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] projeto.</span><span class="sxs-lookup"><span data-stu-id="5e544-132">The following example shows a simple way to populate, retrieve, and update the data in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span> <span data-ttu-id="5e544-133">Em um aplicativo real, você deve recuperar os dados de uma fonte, como um serviço do Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="5e544-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### <a name="view-model"></a><span data-ttu-id="5e544-134">Modelo de exibição</span><span class="sxs-lookup"><span data-stu-id="5e544-134">View Model</span></span>  
 <span data-ttu-id="5e544-135">Uma classe base para exibir modelos com frequência é adicionada ao implementar o padrão MVVM.</span><span class="sxs-lookup"><span data-stu-id="5e544-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="5e544-136">O exemplo a seguir mostra uma classe base.</span><span class="sxs-lookup"><span data-stu-id="5e544-136">The following example shows a base class.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 <span data-ttu-id="5e544-137">Uma implementação de <xref:System.Windows.Input.ICommand> interface é frequentemente usada com o padrão MVVM.</span><span class="sxs-lookup"><span data-stu-id="5e544-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="5e544-138">O exemplo a seguir mostra uma implementação do <xref:System.Windows.Input.ICommand> interface.</span><span class="sxs-lookup"><span data-stu-id="5e544-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 <span data-ttu-id="5e544-139">O exemplo a seguir mostra um modelo de exibição simplificada.</span><span class="sxs-lookup"><span data-stu-id="5e544-139">The following example shows a simplified view model.</span></span>  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="5e544-140">Exibir</span><span class="sxs-lookup"><span data-stu-id="5e544-140">View</span></span>  
 <span data-ttu-id="5e544-141">De um [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] aplicativo, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] um aplicativo, com base no Silverlight ou aplicativo do Windows Phone 7.5, você pode referenciar o assembly que contém os projetos de modelo do modelo e o modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="5e544-141">From a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="5e544-142">Você criar uma exibição que interage com o modelo de exibição.</span><span class="sxs-lookup"><span data-stu-id="5e544-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="5e544-143">O exemplo a seguir mostra um aplicativo do Windows Presentation Foundation (WPF) simplificado que recupera e atualiza os dados do modelo de exibição.</span><span class="sxs-lookup"><span data-stu-id="5e544-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="5e544-144">Você pode criar modos de exibição semelhantes no Silverlight, Windows Phone, ou [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicativos.</span><span class="sxs-lookup"><span data-stu-id="5e544-144">You could create similar views in Silverlight, Windows Phone, or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="5e544-145">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5e544-145">See Also</span></span>  
 [<span data-ttu-id="5e544-146">Biblioteca de classes portátil</span><span class="sxs-lookup"><span data-stu-id="5e544-146">Portable Class Library</span></span>](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)