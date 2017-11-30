---
title: "Como substituir metadados para uma propriedade de dependência"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [WPF], overriding for dependency properties
- dependency properties [WPF], overriding metadata for
- overriding metadata for dependency properties [WPF]
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e7cb01c81b5fb24830cbe0cc39befbadaf4405e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-override-metadata-for-a-dependency-property"></a><span data-ttu-id="29119-102">Como substituir metadados para uma propriedade de dependência</span><span class="sxs-lookup"><span data-stu-id="29119-102">How to: Override Metadata for a Dependency Property</span></span>
<span data-ttu-id="29119-103">Este exemplo mostra como substituir os metadados de propriedade de dependência padrão que vêm de uma classe herdada, chamando o <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> método e fornecendo metadados específicos do tipo.</span><span class="sxs-lookup"><span data-stu-id="29119-103">This example shows how to override default dependency property metadata that comes from an inherited class, by calling the <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> method and providing type-specific metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29119-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="29119-104">Example</span></span>  
 <span data-ttu-id="29119-105">Definindo seu <xref:System.Windows.PropertyMetadata>, uma classe pode definir os comportamentos da propriedade de dependência, como seus padrão valor e sistema retornos de chamada.</span><span class="sxs-lookup"><span data-stu-id="29119-105">By defining its <xref:System.Windows.PropertyMetadata>, a class can define the dependency property's behaviors, such as its default value and property system callbacks.</span></span> <span data-ttu-id="29119-106">Muitas classes de propriedades de dependência já tem metadados padrão estabelecido como parte do processo de registro.</span><span class="sxs-lookup"><span data-stu-id="29119-106">Many dependency property classes already have default metadata established as part of their registration process.</span></span> <span data-ttu-id="29119-107">Isso inclui as propriedades de dependência que fazem parte do [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29119-107">This includes the dependency properties that are part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)].</span></span> <span data-ttu-id="29119-108">Uma classe que herda a propriedade de dependência por meio da herança de sua classe pode substituir os metadados originais para que as características da propriedade que podem ser alteradas por meio de metadados corresponderão a qualquer requisito específico de subclasse.</span><span class="sxs-lookup"><span data-stu-id="29119-108">A class that inherits the dependency property through its class inheritance can override the original metadata so that the characteristics of the property that can be altered through metadata will match any subclass-specific requirements.</span></span>  
  
 <span data-ttu-id="29119-109">A substituição de metadados em uma propriedade de dependência deve ser realizada antes da propriedade que está sendo colocada em uso pelo sistema de propriedades (isso é igual ao momento em que instâncias específicas de objetos que registram a propriedade são instanciadas).</span><span class="sxs-lookup"><span data-stu-id="29119-109">Overriding metadata on a dependency property must be done prior to that property being placed in use by the property system (this equates to the time that specific instances of objects that register the property are instantiated).</span></span> <span data-ttu-id="29119-110">Chamadas para <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> devem ser executadas em construtores estáticos do tipo que fornece a próprio como o `forType` parâmetro <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="29119-110">Calls to <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> must be performed within the static constructors of the type that provides itself as the `forType` parameter of <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>.</span></span> <span data-ttu-id="29119-111">Se você tentar alterar os metadados quando existem instâncias do tipo proprietário, isso não gerará exceções, mas resultará em comportamentos inconsistentes no sistema de propriedade.</span><span class="sxs-lookup"><span data-stu-id="29119-111">If you attempt to change metadata once instances of the owner type exist, this will not raise exceptions, but will result in inconsistent behaviors in the property system.</span></span> <span data-ttu-id="29119-112">Além disso, metadados só podem ser substituído uma vez por tipo.</span><span class="sxs-lookup"><span data-stu-id="29119-112">Also, metadata can only be overridden once per type.</span></span> <span data-ttu-id="29119-113">Tentativas subsequentes de substituir os metadados no mesmo tipo gerarão uma exceção.</span><span class="sxs-lookup"><span data-stu-id="29119-113">Subsequent attempts to override metadata on the same type will raise an exception.</span></span>  
  
 <span data-ttu-id="29119-114">No exemplo a seguir, a classe personalizada `MyAdvancedStateControl` substitui os metadados fornecidos para `StateProperty` por `MyAdvancedStateControl` com os novos metadados de propriedade.</span><span class="sxs-lookup"><span data-stu-id="29119-114">In the following example, the custom class `MyAdvancedStateControl` overrides the metadata provided for `StateProperty` by `MyAdvancedStateControl` with new property metadata.</span></span> <span data-ttu-id="29119-115">Por exemplo, o valor padrão do `StateProperty` agora é `true` quando a propriedade é consultada em uma instância `MyAdvancedStateControl` recém construída.</span><span class="sxs-lookup"><span data-stu-id="29119-115">For instance, the default value of the `StateProperty` is now `true` when the property is queried on a newly constructed `MyAdvancedStateControl` instance.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="29119-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="29119-116">See Also</span></span>  
 <xref:System.Windows.DependencyProperty>  
 [<span data-ttu-id="29119-117">Visão geral das propriedades da dependência</span><span class="sxs-lookup"><span data-stu-id="29119-117">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="29119-118">Propriedades de dependência personalizadas</span><span class="sxs-lookup"><span data-stu-id="29119-118">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="29119-119">Tópicos explicativos</span><span class="sxs-lookup"><span data-stu-id="29119-119">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)