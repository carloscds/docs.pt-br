---
title: "Página de ajuda de serviço HTTP Web do WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63c7c695-44b6-4f31-bb9c-00f2763f525e
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 96c54320c77de766f00bde1e560eb5b0f0df2671
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-web-http-service-help-page"></a><span data-ttu-id="c16f1-102">Página de ajuda de serviço HTTP Web do WCF</span><span class="sxs-lookup"><span data-stu-id="c16f1-102">WCF Web HTTP Service Help Page</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="c16f1-103">Fornece uma página de ajuda automática para serviços WCF WEB HTTP.</span><span class="sxs-lookup"><span data-stu-id="c16f1-103"> provides an automatic help page for WCF WEB HTTP services.</span></span> <span data-ttu-id="c16f1-104">Esta página de Ajuda contém uma descrição de cada operação de solicitação e resposta formatos e esquemas.</span><span class="sxs-lookup"><span data-stu-id="c16f1-104">This help page lists a description of each operation, request and response formats, and schemas.</span></span> <span data-ttu-id="c16f1-105">Essa funcionalidade é desativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="c16f1-105">This functionality is turned off by default.</span></span> <span data-ttu-id="c16f1-106">Quando um usuário navega para um serviço WCF WEB HTTP e acrescenta "/Help" no final da URL, por exemplo http://localhost:8000/clientes/ajuda, é exibida uma página de ajuda com o seguinte.</span><span class="sxs-lookup"><span data-stu-id="c16f1-106">When a user browses to a WCF WEB HTTP service and appends "/Help" on to the end of the URL, for example http://localhost:8000/Customers/Help, a help page like the following is displayed.</span></span>  
  
 <span data-ttu-id="c16f1-107">![Página de Ajuda do WCF REST](../../../../docs/framework/wcf/feature-details/media/wcfresthelppagemain.gif "WCFRESTHELPPAGEMAIN")</span><span class="sxs-lookup"><span data-stu-id="c16f1-107">![WCF REST Help Page](../../../../docs/framework/wcf/feature-details/media/wcfresthelppagemain.gif "WCFRESTHELPPAGEMAIN")</span></span>  
  
 <span data-ttu-id="c16f1-108">O usuário poderá clicar em qualquer método listado na página de Ajuda e a página detalhada para essa operação é exibida mostrando mais informações sobre o método, incluindo os formatos de mensagem e respostas de exemplo.</span><span class="sxs-lookup"><span data-stu-id="c16f1-108">The user can then click any method listed in the help page and detailed page for that operation is displayed showing more information about the method, including message formats and example responses.</span></span> <span data-ttu-id="c16f1-109">A imagem a seguir é um exemplo de uma página de ajuda para um método.</span><span class="sxs-lookup"><span data-stu-id="c16f1-109">The following image is an example of a help page for a method.</span></span>  
  
 <span data-ttu-id="c16f1-110">![Detalhes da página de Ajuda do WCF REST](../../../../docs/framework/wcf/feature-details/media/wcfresthelppagedetail2.gif "WCFRESTHELPPAGEDETAIL2")</span><span class="sxs-lookup"><span data-stu-id="c16f1-110">![WCF REST Help Page Details](../../../../docs/framework/wcf/feature-details/media/wcfresthelppagedetail2.gif "WCFRESTHELPPAGEDETAIL2")</span></span>  
  
## <a name="using-the-wcf-web-http-help-page"></a><span data-ttu-id="c16f1-111">Usando a página de Ajuda do WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="c16f1-111">Using the WCF Web HTTP Help Page</span></span>  
 <span data-ttu-id="c16f1-112">A página de Ajuda do WCF WEB HTTP exibe uma breve descrição de cada operação desde que você especificar um usando o <xref:System.ComponentModel.DescriptionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c16f1-112">The WCF WEB HTTP Help page displays a short description for each operation provided that you specify one using the <xref:System.ComponentModel.DescriptionAttribute>.</span></span> <span data-ttu-id="c16f1-113">Este atributo tem uma cadeia de caracteres que contém uma breve descrição da operação a que será aplicada.</span><span class="sxs-lookup"><span data-stu-id="c16f1-113">This attribute takes a string that contains a short description of the operation it is applied to.</span></span> <span data-ttu-id="c16f1-114">Por exemplo, o código a seguir mostra como usar o <xref:System.ComponentModel.DescriptionAttribute> para fornecer uma breve descrição.</span><span class="sxs-lookup"><span data-stu-id="c16f1-114">For example, the following code shows how to use the <xref:System.ComponentModel.DescriptionAttribute> to provide a short description.</span></span>  
  
```  
[OperationContract]  
[WebGet(UriTemplate="/template1", BodyStyle = WebMessageBodyStyle.Bare)]  
[Description("Description for GET /template1")]  
SyndicationFeedFormatter GetTemplate1();  
```  
  
 <span data-ttu-id="c16f1-115">Para ativar a página de Ajuda do WCF WEB HTTP, você deve adicionar um comportamento de ponto de extremidade para os pontos de extremidade do serviço.</span><span class="sxs-lookup"><span data-stu-id="c16f1-115">To turn on the WCF WEB HTTP Help page, you must add an endpoint behavior to your service's endpoints.</span></span> <span data-ttu-id="c16f1-116">Isso pode ser feito na configuração ou código.</span><span class="sxs-lookup"><span data-stu-id="c16f1-116">This can be done in configuration or code.</span></span> <span data-ttu-id="c16f1-117">Para habilitar a idade de WCF WEB HTTP ajuda na configuração, adicione um comportamento de ponto de extremidade com um `<webHttp>` elemento, defina `enableHelp` para `true`, adicione um ponto de extremidade e configurá-lo para usar o comportamento de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="c16f1-117">To enable the WCF WEB HTTP Help age in configuration, add an endpoint behavior with a `<webHttp>` element, set `enableHelp` to `true`, and add an endpoint and configure it to use the endpoint behavior.</span></span> <span data-ttu-id="c16f1-118">O código de configuração a seguir mostra como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="c16f1-118">The following configuration code shows how to do this.</span></span>  
  
```xml  
<endpointBehaviors>  
   <behavior name="RESTEndpointBehavior">  
      <webHttp enableHelp="true"/>  
   </behavior>  
</endpointBehaviors>  
<!-- ... -->  
<services>  
   <service behaviorConfiguration="RESTWebServiceBehavior" name="RESTWebService">      <endpoint address="" kind="webHttpEndpoint" behaviorConfiguration="RESTEndpointBehavior" contract="IHello" />  
  
      <!-- ... -->  
   </service>  
</services>  
```  
  
 <span data-ttu-id="c16f1-119">Para habilitar a página de Ajuda do WCF Web HTTP no código, adicione um ponto de extremidade de serviço e adicione um <xref:System.ServiceModel.Description.WebHttpBehavior> para a configuração de ponto de extremidade <!--zz <xref:System.ServiceModel.Description.WebHttpBehavior.EnableHelp%2A>--> `EnableHelp` para `true`.</span><span class="sxs-lookup"><span data-stu-id="c16f1-119">To enable the WCF Web HTTP Help page in code, add a service endpoint and add a <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint setting <!--zz <xref:System.ServiceModel.Description.WebHttpBehavior.EnableHelp%2A>--> `EnableHelp` to `true`.</span></span> <span data-ttu-id="c16f1-120">O código a seguir mostra como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="c16f1-120">The following code shows how to do this.</span></span>  
  
```  
using (WebServiceHost host = new WebServiceHost(typeof(Service), new Uri("http://localhost:8000/Customers")))  
{  
   host.AddServiceEndpoint(typeof(ICustomerCollection), new WebHttpBinding(), "");               
   host.Description.Endpoints[0].Behaviors.Add(new WebHttpBehavior { EnableHelp = true });  
   // ...  
}  
```  
  
 <span data-ttu-id="c16f1-121">A página de Ajuda é XHTML baseado em com marcação que identifica as diferentes partes da página.</span><span class="sxs-lookup"><span data-stu-id="c16f1-121">The help page is XHTML based with mark-up that identifies the different parts of the page.</span></span> <span data-ttu-id="c16f1-122">Isso permite que os clientes acessem programaticamente usando a página <xref:System.Xml.Linq.XElement> ou outras APIs XLinq.</span><span class="sxs-lookup"><span data-stu-id="c16f1-122">This enables clients to programmatically access the page using <xref:System.Xml.Linq.XElement> or other XLinq APIs.</span></span>  
  
## <a name="schemas-used-in-the-wcf-web-http-service-help-page"></a><span data-ttu-id="c16f1-123">Página de ajuda de esquemas usados no serviço WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="c16f1-123">Schemas Used in the WCF Web HTTP Service Help Page</span></span>  
 <span data-ttu-id="c16f1-124">Os seguintes esquemas são usados na página de ajuda de serviço WCF Web HTTP.</span><span class="sxs-lookup"><span data-stu-id="c16f1-124">The following schemas are used in the WCF Web HTTP service help page.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/" attributeFormDefault="qualified" elementFormDefault="qualified" targetNamespace="http://schemas.microsoft.com/2003/10/Serialization/" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="anyType" nillable="true" type="xs:anyType" />  
  <xs:element name="anyURI" nillable="true" type="xs:anyURI" />  
  <xs:element name="base64Binary" nillable="true" type="xs:base64Binary" />  
  <xs:element name="boolean" nillable="true" type="xs:boolean" />  
  <xs:element name="byte" nillable="true" type="xs:byte" />  
  <xs:element name="dateTime" nillable="true" type="xs:dateTime" />  
  <xs:element name="decimal" nillable="true" type="xs:decimal" />  
  <xs:element name="double" nillable="true" type="xs:double" />  
  <xs:element name="float" nillable="true" type="xs:float" />  
  <xs:element name="int" nillable="true" type="xs:int" />  
  <xs:element name="long" nillable="true" type="xs:long" />  
  <xs:element name="QName" nillable="true" type="xs:QName" />  
  <xs:element name="short" nillable="true" type="xs:short" />  
  <xs:element name="string" nillable="true" type="xs:string" />  
  <xs:element name="unsignedByte" nillable="true" type="xs:unsignedByte" />  
  <xs:element name="unsignedInt" nillable="true" type="xs:unsignedInt" />  
  <xs:element name="unsignedLong" nillable="true" type="xs:unsignedLong" />  
  <xs:element name="unsignedShort" nillable="true" type="xs:unsignedShort" />  
  <xs:element name="char" nillable="true" type="tns:char" />  
  <xs:simpleType name="char">  
    <xs:restriction base="xs:int" />  
  </xs:simpleType>  
  <xs:element name="duration" nillable="true" type="tns:duration" />  
  <xs:simpleType name="duration">  
    <xs:restriction base="xs:duration">  
      <xs:pattern value="\-?P(\d*D)?(T(\d*H)?(\d*M)?(\d*(\.\d*)?S)?)?" />  
      <xs:minInclusive value="-P10675199DT2H48M5.4775808S" />  
      <xs:maxInclusive value="P10675199DT2H48M5.4775807S" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:element name="guid" nillable="true" type="tns:guid" />  
  <xs:simpleType name="guid">  
    <xs:restriction base="xs:string">  
      <xs:pattern value="[\da-fA-F]{8}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{12}" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:attribute name="FactoryType" type="xs:QName" />  
  <xs:attribute name="Id" type="xs:ID" />  
  <xs:attribute name="Ref" type="xs:IDREF" />  
</xs:schema>  
  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:tns="http://microsoft.com/wsdl/types/" elementFormDefault="qualified" targetNamespace="http://microsoft.com/wsdl/types/" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:simpleType name="guid">  
    <xs:restriction base="xs:string">  
      <xs:pattern value="[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="char">  
    <xs:restriction base="xs:unsignedShort" />  
  </xs:simpleType>  
</xs:schema>  
  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:tns="http://schemas.datacontract.org/2004/07/System" elementFormDefault="qualified" targetNamespace="http://schemas.datacontract.org/2004/07/System" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:import namespace="http://schemas.microsoft.com/2003/10/Serialization/" />  
  <xs:complexType name="DateTimeOffset">  
    <xs:annotation>  
      <xs:appinfo>  
        <IsValueType xmlns="http://schemas.microsoft.com/2003/10/Serialization/">true</IsValueType>  
      </xs:appinfo>  
    </xs:annotation>  
    <xs:sequence>  
      <xs:element name="DateTime" type="xs:dateTime" />  
      <xs:element name="OffsetMinutes" type="xs:short" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="DateTimeOffset" nillable="true" type="tns:DateTimeOffset" />  
  <xs:complexType name="DBNull">  
    <xs:sequence />  
  </xs:complexType>  
  <xs:element name="DBNull" nillable="true" type="tns:DBNull" />  
</xs:schema>  
  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:ser="http://schemas.microsoft.com/2003/10/Serialization/" elementFormDefault="qualified" targetNamespace="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:import namespace="http://schemas.microsoft.com/2003/10/Serialization/" />  
  <xs:complexType name="ArrayOfboolean">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="boolean" type="xs:boolean" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfboolean" nillable="true" type="tns:ArrayOfboolean" />  
  <xs:complexType name="ArrayOfchar">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="char" type="ser:char" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfchar" nillable="true" type="tns:ArrayOfchar" />  
  <xs:complexType name="ArrayOfdateTime">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="dateTime" type="xs:dateTime" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfdateTime" nillable="true" type="tns:ArrayOfdateTime" />  
  <xs:complexType name="ArrayOfdecimal">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="decimal" type="xs:decimal" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfdecimal" nillable="true" type="tns:ArrayOfdecimal" />  
  <xs:complexType name="ArrayOfdouble">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="double" type="xs:double" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfdouble" nillable="true" type="tns:ArrayOfdouble" />  
  <xs:complexType name="ArrayOffloat">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="float" type="xs:float" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOffloat" nillable="true" type="tns:ArrayOffloat" />  
  <xs:complexType name="ArrayOfguid">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="guid" type="ser:guid" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfguid" nillable="true" type="tns:ArrayOfguid" />  
  <xs:complexType name="ArrayOfint">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="int" type="xs:int" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfint" nillable="true" type="tns:ArrayOfint" />  
  <xs:complexType name="ArrayOflong">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="long" type="xs:long" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOflong" nillable="true" type="tns:ArrayOflong" />  
  <xs:complexType name="ArrayOfshort">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="short" type="xs:short" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfshort" nillable="true" type="tns:ArrayOfshort" />  
  <xs:complexType name="ArrayOfstring">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="string" nillable="true" type="xs:string" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfstring" nillable="true" type="tns:ArrayOfstring" />  
  <xs:complexType name="ArrayOfduration">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="duration" type="ser:duration" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfduration" nillable="true" type="tns:ArrayOfduration" />  
  <xs:complexType name="ArrayOfunsignedInt">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="unsignedInt" type="xs:unsignedInt" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfunsignedInt" nillable="true" type="tns:ArrayOfunsignedInt" />  
  <xs:complexType name="ArrayOfunsignedLong">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="unsignedLong" type="xs:unsignedLong" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfunsignedLong" nillable="true" type="tns:ArrayOfunsignedLong" />  
  <xs:complexType name="ArrayOfunsignedShort">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="unsignedShort" type="xs:unsignedShort" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfunsignedShort" nillable="true" type="tns:ArrayOfunsignedShort" />  
  <xs:complexType name="ArrayOfQName">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="unbounded" name="QName" nillable="true" type="xs:QName" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:element name="ArrayOfQName" nillable="true" type="tns:ArrayOfQName" />  
</xs:schema>  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c16f1-125">o esquema de serialização de contrato de dados, consulte [referência de esquema de contrato de dados](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="c16f1-125"> the data contract serialization schema, see [Data Contract Schema Reference](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).</span></span>