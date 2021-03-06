---
title: Como o modelo de objeto de sindicalização do WCF mapeia para Atom e RSS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0365eb37-98cc-4b13-80fb-f1e78847a748
ms.openlocfilehash: 7619dbfcdb0a3a219c9245d30518ffec8b586360
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671415"
---
# <a name="how-the-wcf-syndication-object-model-maps-to-atom-and-rss"></a>Como o modelo de objeto de sindicalização do WCF mapeia para Atom e RSS
Ao desenvolver um serviço de distribuição do Windows Communication Foundation (WCF), você deve criar feeds e itens usando as classes a seguir:  
  
-   <xref:System.ServiceModel.Syndication.SyndicationFeed>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationItem>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationPerson>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationLink>  
  
-   <xref:System.ServiceModel.Syndication.SyndicationCategory>  
  
-   <xref:System.ServiceModel.Syndication.TextSyndicationContent>  
  
-   <xref:System.ServiceModel.Syndication.UrlSyndicationContent>  
  
-   <xref:System.ServiceModel.Syndication.XmlSyndicationContent>  
  
 Um <xref:System.ServiceModel.Syndication.SyndicationFeed> pode ser serializado em qualquer formato de distribuição para o qual um formatador é definido. O WCF é fornecido com dois formatadores: <xref:System.ServiceModel.Syndication.Atom10FeedFormatter> e <xref:System.ServiceModel.Syndication.Rss20FeedFormatter>.  
  
 O modelo de objeto em torno <xref:System.ServiceModel.Syndication.SyndicationFeed> e <xref:System.ServiceModel.Syndication.SyndicationItem> é alinhado mais estreitamente com a especificação Atom 1.0 que a especificação RSS 2.0. Isso ocorre porque o Atom 1.0 é uma especificação mais significativa que define os elementos que são ambíguas ou omitida da especificação do RSS 2.0. Por isso, muitos itens no modelo de objeto de sindicalização do WCF não tem nenhuma representação direta na especificação do RSS 2.0. Ao serializar <xref:System.ServiceModel.Syndication.SyndicationFeed> e <xref:System.ServiceModel.Syndication.SyndicationItem> objetos em RSS 2.0, o WCF permite que você serializar os elementos de dados específicos do Atom como elementos de extensão qualificado de namespace que se adequa à especificação do Atom. Você pode controlar isso com um parâmetro passado para o <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> construtor.  
  
 Os exemplos de código neste tópico usam um destes dois métodos definidos aqui para fazer a serialização real.  
  
 `SerializeFeed` serializa um feed de sindicalização.  
  
 [!code-csharp[SyndicationMapping#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#10)]
 [!code-vb[SyndicationMapping#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#10)]  
  
 `SerializeItem` serializa um item de sindicalização.  
  
 [!code-csharp[SyndicationMapping#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#11)]
 [!code-vb[SyndicationMapping#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#11)]  
  
## <a name="syndicationfeed"></a>SyndicationFeed  
 O exemplo de código a seguir mostra como serializar o <xref:System.ServiceModel.Syndication.SyndicationFeed> classe Atom 1.0 e RSS 2.0.  
  
 [!code-csharp[SyndicationMapping#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#0)]
 [!code-vb[SyndicationMapping#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#0)]  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.SyndicationFeed> é serializado para Atom 1.0.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<feed xml:lang="EN-US" xmlns="http://www.w3.org/2005/Atom">  
  <title type="text">My Feed Title</title>  
  <subtitle type="text">My Feed Description</subtitle>  
  <id>FeedID</id>  
  <rights type="text">Copyright 2007</rights>  
  <updated>2007-08-29T13:57:17-07:00</updated>  
  <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
  <logo>http://server/image.jpg</logo>  
  <generator>Sample Code</generator>  
  <link rel="alternate" href="http://myfeeduri/" />  
  <entry>  
    <id>ItemID</id>  
    <title type="text">Item Title</title>  
    <summary type="text">Item Summary</summary>  
    <published>2007-08-29T00:00:00-07:00</published>  
    <updated>2007-08-29T13:57:17-07:00</updated>  
    <author>  
      <name>Jesper Aaberg</name>  
      <uri>http://Jesper/Aaberg</uri>  
      <email>Jesper@Aaberg.com</email>  
    </author>  
    <contributor>  
      <name>Lene Aaling</name>  
      <uri>http://Lene/Aaling</uri>  
      <email>Lene@Aaling.com</email>  
    </contributor>  
    <link rel="alternate" href="http://myitemuri/" />  
    <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
    <content type="text">Item Content</content>  
    <rights type="text">Copyright 2007</rights>  
    <source>  
      <title type="text">My Feed Title</title>  
      <subtitle type="text">My Feed Description</subtitle>  
      <id>FeedID</id>  
      <rights type="text">Copyright 2007</rights>  
      <updated>2007-08-29T13:57:17-07:00</updated>  
      <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
      <logo>http://server/image.jpg</logo>  
      <generator>Sample Code</generator>  
      <link rel="alternate" href="http://myfeeduri/" />  
    </source>  
  </entry>  
</feed>  
```  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.SyndicationFeed> é serializado em RSS 2.0.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<rss xmlns:a10="http://www.w3.org/2005/Atom" version="2.0">  
  <channel>  
    <title>My Feed Title</title>  
    <link>http://myfeeduri/</link>  
    <description>My Feed Description</description>  
    <language>EN-US</language>  
    <copyright>Copyright 2007</copyright>  
    <lastBuildDate>Wed, 29 Aug 2007 13:57:17 -0700</lastBuildDate>  
    <category domain="categoryScheme">categoryName</category>  
    <generator>Sample Code</generator>  
    <image>  
      <url>http://server/image.jpg</url>  
      <title>My Feed Title</title>  
      <link>http://myfeeduri/</link>  
    </image>  
    <a10:id>FeedID</a10:id>  
    <item>  
      <guid isPermaLink="false">ItemID</guid>  
      <link>http://myitemuri/</link>  
      <author>Jesper@Aaberg.com</author>  
      <category domain="categoryScheme">categoryName</category>  
      <title>Item Title</title>  
      <description>Item Summary</description>  
      <source>My Feed Title</source>  
      <pubDate>Wed, 29 Aug 2007 00:00:00 -0700</pubDate>  
      <a10:updated>2007-08-29T13:57:17-07:00</a10:updated>  
      <a10:rights type="text">Copyright 2007</a10:rights>  
      <a10:content type="text">Item Content</a10:content>  
      <a10:contributor>  
        <a10:name>Lene Aaling</a10:name>  
        <a10:uri>http://Lene/Aaling</a10:uri>  
        <a10:email>Lene@Aaling.com</a10:email>  
      </a10:contributor>  
    </item>  
  </channel>  
</rss>  
```  
  
## <a name="syndicationitem"></a>SyndicationItem  
 O exemplo de código a seguir mostra como serializar o <xref:System.ServiceModel.Syndication.SyndicationItem> classe Atom 1.0 e RSS 2.0.  
  
 [!code-csharp[SyndicationMapping#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#1)]
 [!code-vb[SyndicationMapping#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#1)]  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.SyndicationItem> é serializado para Atom 1.0.  
  
```xml  
<entry xmlns="http://www.w3.org/2005/Atom">  
  <id>ItemID</id>  
  <title type="text">Item Title</title>  
  <summary type="text">Item Summary</summary>  
  <published>2007-08-29T00:00:00-07:00</published>  
  <updated>2007-08-29T14:07:09-07:00</updated>  
  <author>  
    <name>Jesper Aaberg</name>  
    <uri>http://Contoso/Aaberg</uri>  
    <email>Jesper.Aaberg@contoso.com</email>  
  </author>  
  <author>  
    <name>Syed Abbas</name>  
    <uri>http://Contoso/Abbas</uri>  
    <email>Syed.Abbas@contoso.com</email>  
  </author>  
  <contributor>  
    <name>Lene Aaling</name>  
    <uri>http://Contoso/Aaling</uri>  
    <email>Lene.Aaling@contoso.com</email>  
  </contributor>  
  <contributor>  
    <name>Kim Abercrombie</name>  
    <uri>http://Contoso/Abercrombie</uri>  
    <email>Kim.Abercrombie@contoso.com</email>  
  </contributor>  
  <link rel="alternate" href="http://myitemuri/" />  
  <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
  <category term="categoryName" label="categoryLabel" scheme="categoryScheme" />  
  <content type="text">Item Content</content>  
  <rights type="text">Copyright 2007</rights>  
  <source>  
    <title type="text">My Feed Title</title>  
    <subtitle type="text">My Feed Description</subtitle>  
    <link rel="alternate" href="http://myfeeduri/" />  
  </source>  
</entry>  
```  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.SyndicationItem> é serializado em RSS 2.0.  
  
```xml  
<item>  
  <guid isPermaLink="false">ItemID</guid>  
  <link>http://myitemuri/</link>  
  <author xmlns="http://www.w3.org/2005/Atom">  
    <name>Jesper Aaberg</name>  
    <uri>http://Jesper/Aaberg</uri>  
    <email>Jesper@Aaberg.com</email>  
  </author>  
  <author xmlns="http://www.w3.org/2005/Atom">  
    <name>Syed Abbas</name>  
    <uri>http://Contoso/Abbas</uri>  
    <email>Syed.Abbas@contoso.com</email>  
  </author>  
  <category domain="categoryScheme">categoryName</category>  
  <category domain="categoryScheme">categoryName</category>  
  <title>Item Title</title>  
  <description>Item Summary</description>  
  <source>My Feed Title</source>  
  <pubDate>Wed, 29 Aug 2007 00:00:00 -0700</pubDate>  
  <updated xmlns="http://www.w3.org/2005/Atom">2007-08-29T14:07:09-07:00</updated>  
  <rights type="text" xmlns="http://www.w3.org/2005/Atom">Copyright 2007</rights>  
  <content type="text" xmlns="http://www.w3.org/2005/Atom">Item Content</content>  
  <contributor xmlns="http://www.w3.org/2005/Atom">  
    <name>Lene Aaling</name>  
    <uri>http://Contoso/Aaling</uri>  
    <email>Lene.Aaling@contoso.com</email>  
  </contributor>  
  <contributor xmlns="http://www.w3.org/2005/Atom">  
    <name>Kim Abercrombie</name>  
    <uri>http://Contoso/Abercrombie</uri>  
    <email>Kim.Abercrombie@contoso.com</email>  
  </contributor>  
</item>  
```  
  
## <a name="syndicationperson"></a>SyndicationPerson  
 O exemplo de código a seguir mostra como serializar o <xref:System.ServiceModel.Syndication.SyndicationPerson> classe Atom 1.0 e RSS 2.0.  
  
 [!code-csharp[SyndicationMapping#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#2)]
 [!code-vb[SyndicationMapping#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#2)]  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.SyndicationPerson> é serializado para Atom 1.0.  
  
```xml  
  <author>  
    <name>Jesper Aaberg</name>  
    <uri>http://Contoso/Aaberg</uri>  
    <email>Jesper.Aaberg@contoso.com</email>  
  </author>  
<contributor>  
    <name>Lene Aaling</name>  
    <uri>http://Contoso/Aaling</uri>  
    <email>Lene.Aaling@contoso.com</email>  
  </contributor>  
```  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.SyndicationPerson> classe é serializada em RSS 2.0, se houver apenas uma <xref:System.ServiceModel.Syndication.SyndicationPerson> existe na `Authors` ou `Contributors` coleções, respectivamente.  
  
```xml  
<author>Jesper.Aaberg@contoso.com</author>  
<a10:contributor>  
    <a10:name>Lene Aaling</a10:name>  
    <a10:uri>http://Contoso/Aaling</a10:uri>  
    <a10:email>Lene.Aaling@contoso.com</a10:email>  
</a10:contributor>  
```  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.SyndicationPerson> classe é serializada em RSS 2.0, se houver mais de um <xref:System.ServiceModel.Syndication.SyndicationPerson> existe na `Authors` ou `Contributors` coleções, respectivamente.  
  
```xml  
<a10:author>  
    <a10:name>Jesper Aaberg</a10:name>  
    <a10:uri>http://Contoso/Aaberg</a10:uri>  
    <a10:email>Jesper.Aaberg@contoso.com</a10:email>  
</a10:author>  
<a10:author>  
    <a10:name>Syed Abbas</a10:name>  
    <a10:uri>http://Contoso/Abbas</a10:uri>  
    <a10:email>Syed.Abbas@contoso.com</a10:email>  
</a10:author>  
<a10:contributor>  
    <a10:name>Lene Aaling</a10:name>  
    <a10:uri>http://Contoso/Aaling</a10:uri>  
    <a10:email>Lene.Aaling@contoso.com</a10:email>  
</a10:contributor>  
<a10:contributor>  
    <a10:name>Kim Abercrombie</a10:name>  
    <a10:uri>http://Contoso/Abercrombie</a10:uri>  
    <a10:email>Kim.Abercrombie@contoso.com</a10:email>  
</a10:contributor>  
```  
  
## <a name="syndicationlink"></a>SyndicationLink  
 O exemplo de código a seguir mostra como serializar o <xref:System.ServiceModel.Syndication.SyndicationLink> classe Atom 1.0 e RSS 2.0.  
  
 [!code-csharp[SyndicationMapping#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#3)]
 [!code-vb[SyndicationMapping#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#3)]  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.SyndicationLink> é serializado para Atom 1.0.  
  
 `<link rel="alternate" type="text/html" title="My Link Title" length="2048" href="http://contoso/MyLink" />`  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.SyndicationLink> é serializado em RSS 2.0.  
  
 `<a10:link rel="alternate" type="text/html" title="My Link Title" length="2048" href="http://contoso/MyLink" />`  
  
## <a name="syndicationcategory"></a>SyndicationCategory  
 O exemplo de código a seguir mostra como serializar o <xref:System.ServiceModel.Syndication.SyndicationCategory> classe Atom 1.0 e RSS 2.0.  
  
 [!code-csharp[SyndicationMapping#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#4)]
 [!code-vb[SyndicationMapping#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#4)]  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.SyndicationCategory> é serializado para Atom 1.0.  
  
 `<category term="categoryName" label="categoryLabel" scheme="categoryScheme" />`  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.SyndicationCategory> é serializado em RSS 2.0.  
  
 `<category domain="categoryScheme">categoryName</category>`  
  
## <a name="textsyndicationcontent"></a>TextSyndicationContent  
 O exemplo de código a seguir mostra como serializar o <xref:System.ServiceModel.Syndication.TextSyndicationContent> classe Atom 1.0 e RSS 2.0 quando <xref:System.ServiceModel.Syndication.TextSyndicationContent> é criado com um conteúdo HTML.  
  
 [!code-csharp[SyndicationMapping#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#5)]
 [!code-vb[SyndicationMapping#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#5)]  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.TextSyndicationContent> classe com um conteúdo HTML é serializado para Atom 1.0.  
  
 `<content type="html"><html> some html </html></content>`  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.TextSyndicationContent> classe com um conteúdo HTML é serializada em RSS 2.0.  
  
 `<description><html> some html </html></description>`  
  
 O exemplo de código a seguir mostra como serializar o <xref:System.ServiceModel.Syndication.TextSyndicationContent> classe Atom 1.0 e RSS 2.0 quando <xref:System.ServiceModel.Syndication.TextSyndicationContent> é criado com o conteúdo de texto sem formatação.  
  
 [!code-csharp[SyndicationMapping#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#6)]
 [!code-vb[SyndicationMapping#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#6)]  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.TextSyndicationContent> classe com o conteúdo de texto sem formatação é serializado para Atom 1.0.  
  
 `<content type="text">Some Plain Text</content>`  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.TextSyndicationContent> classe com o conteúdo de texto sem formatação é serializada em RSS 2.0.  
  
 `<description>Some Plain Text</description>`  
  
 O exemplo de código a seguir mostra como serializar o <xref:System.ServiceModel.Syndication.TextSyndicationContent> classe Atom 1.0 e RSS 2.0 quando <xref:System.ServiceModel.Syndication.TextSyndicationContent> é criado com o conteúdo XHTML.  
  
 [!code-csharp[SyndicationMapping#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#7)]
 [!code-vb[SyndicationMapping#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#7)]  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.TextSyndicationContent> classe com conteúdo XHTML é serializado para Atom 1.0.  
  
 `<content type="xhtml">`  
  
 `<html> some xhtml </html>`  
  
 `</content>`  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.TextSyndicationContent> classe com o conteúdo XHTML é serializada em RSS 2.0.  
  
 `<description><html> some xhtml </html></description>`  
  
## <a name="urlsyndicationcontent"></a>UrlSyndicationContent  
 O exemplo de código a seguir mostra como serializar o <xref:System.ServiceModel.Syndication.UrlSyndicationContent> classe Atom 1.0 e RSS 2.0.  
  
 [!code-csharp[SyndicationMapping#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#8)]
 [!code-vb[SyndicationMapping#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#8)]  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.UrlSyndicationContent> classe é serializada para Atom 1.0.  
  
 `<content type="audio" src="http://someurl/" />`  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.UrlSyndicationContent> classe com o conteúdo XHTML é serializada em RSS 2.0.  
  
 `<description />`  
  
 `<content type="audio" src="http://Contoso/someurl/" xmlns="http://www.w3.org/2005/Atom" />`  
  
## <a name="xmlsyndicationcontent"></a>XmlSyndicationContent  
 O exemplo de código a seguir mostra como serializar o <xref:System.ServiceModel.Syndication.XmlSyndicationContent> classe Atom 1.0 e RSS 2.0.  
  
 [!code-csharp[SyndicationMapping#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/syndicationmapping/cs/snippets.cs#9)]
 [!code-vb[SyndicationMapping#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/syndicationmapping/vb/snippets.vb#9)]  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.XmlSyndicationContent> classe é serializada para Atom 1.0.  
  
 `<content type="mytype">`  
  
 `<SomeData xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.datacontract.org/2004/07/FeedMapping" />`  
  
 `</content>`  
  
 O XML a seguir mostra como o <xref:System.ServiceModel.Syndication.XmlSyndicationContent> classe com o conteúdo XHTML é serializada em RSS 2.0.  
  
 `<content type="mytype" xmlns="http://www.w3.org/2005/Atom">`  
  
 `<SomeData xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.datacontract.org/2004/07/FeedMapping" />`  
  
 `</content>`  
  
## <a name="see-also"></a>Consulte também
- [Visão geral de sindicalização do WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)
- [Arquitetura de sindicalização](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)
- [Como: Criar um RSS Feed básico](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-rss-feed.md)
- [Como: Criar um Feed Atom básico](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-atom-feed.md)
- [Como: Expor um Feed como Atom e RSS](../../../../docs/framework/wcf/feature-details/how-to-expose-a-feed-as-both-atom-and-rss.md)
