---
title: Aplicativos monolíticos
description: Entenda os conceitos principais para implantar aplicativos monolíticos em contêineres.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: eff764472b4a9fc5b699545fc9629cc12d0186ca
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747256"
---
# <a name="monolithic-applications"></a>Aplicativos monolíticos

Nesse cenário, você é criar um aplicativo web único e monolítico ou serviço e implantá-lo como um contêiner. Dentro do aplicativo, a estrutura pode não ser monolítica; ele pode ser composto por várias bibliotecas, componentes ou até mesmo camadas (camada de aplicativo, camada de domínio, camada de acesso a dados, etc.). Externamente, ele é um único contêiner, como um único processo, um único aplicativo web ou um único serviço.

Para gerenciar esse modelo, implante um contêiner único para representar o aplicativo. Para dimensioná-lo, basta Adicione algumas cópias mais com um balanceador de carga na frente. A simplicidade é proveniente do gerenciamento de uma única implantação em um único contêiner ou uma máquina virtual (VM).

A entidade que faz uma coisa só um contêiner e faz isso em um processo, a seguir o padrão monolítico está em conflito. Você pode incluir vários componentes/bibliotecas ou camadas internas em cada contêiner, conforme ilustrado na Figura 4-1.

![Um aplicativo monolítico tem todos ou a maioria das suas funcionalidades dentro de um único processo ou contêiner e ele é dividida em componentes em bibliotecas ou camadas internas.](./media/image1.png)

**Figura 4-1.** Um exemplo de arquitetura de aplicativos monolíticos

A desvantagem dessa abordagem vem se ou quando o aplicativo cresce, a necessidade de dimensioná-lo. Se o aplicativo inteiro for dimensionado, isso não será realmente um problema. No entanto, na maioria dos casos, algumas partes do aplicativo são os pontos de redução que exigem o dimensionamento, enquanto outros componentes são usados com menos.

Usando o exemplo típico de comércio eletrônico, o que é provável que você precisa é dimensionar o componente de informações do produto. Uma quantidade muito maior de clientes procura produtos em vez de comprá-los. Mais clientes usam o carrinho em vez do pipeline de pagamento. Menos clientes fazem comentários ou exibem o histórico de compras. E você provavelmente tem apenas um punhado de funcionários, em uma única região, o que precisa para gerenciar o conteúdo e campanhas de marketing. Dimensionando o design monolítico, todo o código é implantado várias vezes.

Além de "escala-tudo o que" o problema, as alterações para um único componente exigem testar novamente todo o aplicativo, bem como uma reimplantação completa de todas as instâncias.

A abordagem monolítica é comum e muitas organizações estão desenvolvendo com esse método de arquitetura. Muitos aproveitam bons resultados suficientes, enquanto outros limites de encontrar. Muitas criaram seus aplicativos nesse modelo porque as ferramentas e a infraestrutura eram muito difíceis de criar SOAs, e eles não viam a necessidade – até que o aplicativo cresceu.

Da perspectiva de infraestrutura, cada servidor pode executar vários aplicativos no mesmo host e ter um índice de eficiência de seu uso de recursos, conforme mostrado na Figura 4-2.

![Um único host pode executar vários aplicativos em contêineres separados.](./media/image2.png)

**Figura 4-2.** Um host executando vários aplicativos/contêineres

Por fim, de uma perspectiva de disponibilidade, aplicativos monolíticos devem ser implantados como um todo; Isso significa que, no caso de você deve *parar e iniciar*, todas as funcionalidades e todos os usuários serão afetados durante a janela de implantação. Em determinadas situações, o uso do Azure e contêineres pode minimizar essas situações e reduzir a probabilidade do tempo de inatividade do seu aplicativo, como você pode ver na Figura 4-3.

Você pode implantar aplicativos monolíticos no Azure por meio de VMs dedicadas para cada instância. Usando o [conjuntos de dimensionamento de VM do Azure](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), você pode dimensionar as VMs com facilidade.

Você também pode usar [serviços de aplicativo do Azure](https://azure.microsoft.com/services/app-service/) para executar aplicativos monolíticos e dimensiona instâncias facilmente sem a necessidade de gerenciar as VMs. Serviços de aplicativo do Azure pode executar instâncias únicas de contêineres do Docker, também, simplificando a implantação.

Você pode implantar várias VMs como hosts do Docker e executar qualquer número de contêineres por VM. Em seguida, usando um balanceador de carga do Azure, conforme ilustrado na Figura 4-3, você pode gerenciar o dimensionamento.

![Um aplicativo monolítico pode ser expandidos para hosts diferentes em que cada uma delas está executando o aplicativo em contêineres.](./media/image3.png)

**Figura 4-3**. Vários hosts escalando horizontalmente um único aplicativo apps/contêineres do Docker

Você pode gerenciar a implantação de hosts em si por meio de técnicas de implantação tradicionais.

Você pode gerenciar contêineres do Docker da linha de comando usando comandos como `docker run` e `docker-compose up`, e você também pode automatizá-lo em pipelines de CD (entrega contínua) e implantar para hosts do Docker dos serviços de DevOps do Azure, por exemplo.

## <a name="monolithic-application-deployed-as-a-container"></a>Aplicativo monolítico implantado como um contêiner

Há vantagens em usar contêineres para gerenciar implantações monolíticas. O dimensionamento das instâncias de contêineres é muito mais rápido e fácil do que a implantação de VMs adicionais.

Implantar atualizações como imagens do Docker é muito mais rápido e eficiente em termos de rede. Contêineres do docker costumam ser iniciadas em segundos, que agiliza as distribuições. Subdividir um contêiner do Docker é tão fácil quanto invocar o `docker stop` comando, geralmente leva menos de um segundo.

Como os contêineres são inerentemente imutáveis por design, você nunca precisa se preocupar com VMs corrompidas porque se esqueceu de um script de atualização para levar em conta alguma configuração específica ou arquivos deixados no disco.

Embora aplicativos monolíticos podem se beneficiar do Docker, estejamos tocando em apenas as dicas de benefícios. Os maiores benefícios do gerenciamento de contêineres são decorrentes da implantação com orquestradores de contêiner que gerenciam as diversas instâncias e ciclo de vida de cada instância de contêiner. Dividir o aplicativo monolítico em subsistemas que podem ser dimensionados, desenvolvidos e implantados individualmente é o ponto de entrada no universo dos microsserviços.

Para saber mais sobre como "lift and shift" aplicativos monolíticos com contêineres e como você pode modernizar seus aplicativos, você pode ler este guia Microsoft adicional, [modernizar aplicativos .NET existentes com contêineres do Windows e de nuvem do Azure ](https://docs.microsoft.com/dotnet/standard/modernize-with-azure-and-containers/), que também é possível baixar como PDF de <https://aka.ms/LiftAndShiftWithContainersEbook>.

## <a name="publish-a-single-docker-container-app-to-azure-app-service"></a>Publicar um único aplicativo de contêiner do Docker no serviço de aplicativo do Azure

Ou porque você deseja obter uma validação rápida de um contêiner implantado no Azure ou porque o aplicativo é simplesmente um aplicativo de contêiner único, os serviços de aplicativo do Azure fornece uma ótima maneira de fornecer serviços de contêiner único escalonáveis.

Usar o serviço de aplicativo do Azure é intuitiva e você pode começar a trabalhar e em execução rapidamente, pois ele fornece excelente Git integração entrem em seu código, compilá-lo no Microsoft Visual Studio e implantá-lo diretamente do Azure. Mas, tradicionalmente (com nenhum Docker), se você precisasse de outros recursos, estruturas ou dependências que não têm suporte nos serviços de aplicativo, você precisava esperar até que a equipe do Azure atualiza essas dependências no serviço de aplicativo ou alternado para outros serviços, como Service Fabric, serviços de nuvem ou VMs, mesmo sem formatação, para o qual você tenha mais controle e pode instalar um componente obrigatório ou uma estrutura para seu aplicativo.

Agora, conforme mostrado na Figura 4-4, ao usar o Visual Studio 2017, o suporte de contêiner no serviço de aplicativo do Azure oferece a capacidade de incluir tudo o que você deseja em seu ambiente de aplicativo. Se você adicionou uma dependência ao seu aplicativo, porque você o estiver executando em um contêiner, você receberá a capacidade de incluir essas dependências em sua imagem Dockerfile ou o Docker.

![Exibição do Assistente do Visual Studio para publicar em um serviço de aplicativo do Azure, realçando o seletor de registro de contêiner.](./media/image4.png)

**Figura 4-4**. Publicar um contêiner no serviço de aplicativo do Azure de aplicativos do Visual Studio/contêineres

Figura 4-4 também mostra que o fluxo de publicação envia uma imagem por meio de um registro de contêiner, que pode ser o registro de contêiner do Azure (um registro próximo às implantações no Azure e protegido por contas e grupos do Active Directory do Azure) ou qualquer outro registro do Docker como os registros de Hub do Docker ou locais.

>[!div class="step-by-step"]
>[Anterior](common-container-design-principles.md)
>[Próximo](state-and-data-in-docker-applications.md)
