---
title: Visão geral de anotações
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- highlights [WPF]
- documents [WPF], annotations
- sticky notes [WPF]
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
ms.openlocfilehash: e88383126c1fb618b2a2a96bdf5998560864af50
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746436"
---
# <a name="annotations-overview"></a>Visão geral de anotações
Escrever anotações ou comentários em documentos em papel é uma atividade tão comum que quase não valorizamos. Essas anotações ou comentários são "anotações" que adicionamos a um documento para sinalizar informações ou realçar itens de interesse para referência posterior. Embora gravar anotações em documentos impressos seja fácil e um lugar comum, a capacidade de adicionar comentários pessoais aos documentos eletrônicos normalmente é muito limitada, quando sequer está disponível.  
  
 Este tópico examina vários tipos comuns de anotações, especificamente Notas Autoadesivas e realces e ilustra como o [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] facilita esses tipos de anotações em aplicativos por meio do documento do Windows Presentation Foundation (WPF) controles de exibição.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] controles de exibição de documento que dão suporte a anotações incluem <xref:System.Windows.Controls.FlowDocumentReader> e <xref:System.Windows.Controls.FlowDocumentScrollViewer>, bem como controles derivados de <xref:System.Windows.Controls.Primitives.DocumentViewerBase> como <xref:System.Windows.Controls.DocumentViewer> e <xref:System.Windows.Controls.FlowDocumentPageViewer>.  
  
  
<a name="caf1_type_stickynotes"></a>   
## <a name="sticky-notes"></a>Notas autoadesivas  
 Uma nota autoadesiva típica contém informações gravadas em um pequeno pedaço de papel colorido que é então "colado" a um documento. Notas Autoadesivas digitais fornecem funcionalidade semelhante para documentos eletrônicos, mas com a flexibilidade adicional de incluir muitos outros tipos de conteúdo, como texto digitado, anotações manuscritas (por exemplo, [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)] traços de "tinta") ou links da Web.  
  
 A ilustração a seguir mostra alguns exemplos de realce, nota autoadesiva de texto e anotações em nota autoadesivas de tinta.  
  
 ![Anotações em notas autoadesivas de tinta, texto e realce.](../../../../docs/framework/wpf/advanced/media/caf-stickynote.jpg "CAF_StickyNote")  
  
 O exemplo a seguir mostra o método que você pode usar para habilitar o suporte a anotação em seu aplicativo.  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>   
## <a name="highlights"></a>Destaques  
 As pessoas usam métodos criativos para chamar a atenção para itens de interesse quando marcam um documento em papel, como sublinhar, realçar, circular palavras em uma frase ou desenhar de marcas ou anotações nas margens.  Anotações de realce no [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] fornecem um recurso semelhante para marcação de informações exibidas em controles de exibição de documento [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 A ilustração a seguir mostra um exemplo de uma anotação de realce.  
  
 ![Realçar anotação](../../../../docs/framework/wpf/advanced/media/caf-callouts.png "CAF_Callouts")  
  
 Os usuários geralmente criam anotações selecionando primeiro um texto ou um item de interesse e, em seguida, clicando duas vezes para exibir um <xref:System.Windows.Controls.ContextMenu> das opções de anotação.  A exemplo a seguir mostra a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] você pode usar para declarar um <xref:System.Windows.Controls.ContextMenu> com comandos roteados que os usuários podem acessar para criar e gerenciar as anotações.  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>   
## <a name="data-anchoring"></a>Ancoragem de dados  
 O [!INCLUDE[TLA2#tla_caf](../../../../includes/tla2sharptla-caf-md.md)] associa as anotações aos dados que o usuário seleciona, não apenas para uma posição no modo de exibição. Portanto, se a exibição de documento mudar, como quando o usuário rolar ou redimensionar a janela de exibição, a anotação permanecerá com a seleção de dados à qual está vinculada. Por exemplo, o gráfico a seguir ilustra uma anotação que o usuário fez em uma seleção de texto. Quando a exibição do documento muda (rola, é redimensionada, tem a escala ajustada ou se move de outra maneira), a anotação de realce se move com a seleção de dados original.  
  
 ![Ancoragem de dados de anotação](../../../../docs/framework/wpf/advanced/media/caf-dataanchoring.png "CAF_DataAnchoring")  
  
<a name="matching_annotations_with_annotated_objects"></a>   
## <a name="matching-annotations-with-annotated-objects"></a>Combinando anotações com objetos anotados  
 Você pode combinar anotações com os respectivos objetos anotados. Por exemplo, considere um aplicativo de leitor de documento simples que tenha um painel de comentários. O painel de comentários pode ser uma caixa de listagem que exiba texto de uma lista de anotações ancoradas a um documento. Se o usuário selecionar um item na caixa de listagem, o aplicativo trará para a exibição o parágrafo no documento ao qual o objeto de anotação correspondente está ancorado.  
  
 O exemplo a seguir demonstra como implementar o manipulador de eventos de uma caixa de listagem assim que serve como painel de comentários.  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 Outro cenário de exemplo envolve aplicativos que permitem a troca de anotações e Notas Autoadesivas entre leitores de documento por email. Esse recurso permite que esses aplicativos levem o leitor para a página que contém a anotação que está sendo trocada.  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Windows.Controls.Primitives.DocumentViewerBase>
- <xref:System.Windows.Controls.DocumentViewer>
- <xref:System.Windows.Controls.FlowDocumentPageViewer>
- <xref:System.Windows.Controls.FlowDocumentScrollViewer>
- <xref:System.Windows.Controls.FlowDocumentReader>
- <xref:System.Windows.Annotations.IAnchorInfo>
- [Esquema de anotações](../../../../docs/framework/wpf/advanced/annotations-schema.md)
- [Visão geral de ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md)
- [Visão geral de comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)
- [Visão geral do documento de fluxo](../../../../docs/framework/wpf/advanced/flow-document-overview.md)
- [Como: Adicionar um comando a um MenuItem](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))
