---
title: Características de aplicativos Web modernos
description: Arquitetar aplicativos Web modernos com o ASP.NET Core e o Azure | Características de aplicativos Web modernos
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: f4fe18d7361f7d67c29fb7dab53132237f709280
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68672903"
---
# <a name="characteristics-of-modern-web-applications"></a><span data-ttu-id="431af-103">Características de aplicativos Web modernos</span><span class="sxs-lookup"><span data-stu-id="431af-103">Characteristics of Modern Web Applications</span></span>

> <span data-ttu-id="431af-104">"…</span><span class="sxs-lookup"><span data-stu-id="431af-104">"…</span></span> <span data-ttu-id="431af-105">com o design correto, os recursos são obtidos sem esforços.</span><span class="sxs-lookup"><span data-stu-id="431af-105">with proper design, the features come cheaply.</span></span> <span data-ttu-id="431af-106">Essa abordagem é árdua, mas continua a ter êxito."</span><span class="sxs-lookup"><span data-stu-id="431af-106">This approach is arduous, but continues to succeed."</span></span>  
> <span data-ttu-id="431af-107">_\- Dennis Ritchie_</span><span class="sxs-lookup"><span data-stu-id="431af-107">_\- Dennis Ritchie_</span></span>

<span data-ttu-id="431af-108">Os aplicativos Web modernos têm maiores expectativas de usuário e maiores demandas do que nunca.</span><span class="sxs-lookup"><span data-stu-id="431af-108">Modern web applications have higher user expectations and greater demands than ever before.</span></span> <span data-ttu-id="431af-109">Os aplicativos Web de hoje devem estar disponíveis 24/7 em qualquer lugar do mundo e ser utilizáveis praticamente em qualquer dispositivo ou tamanho de tela.</span><span class="sxs-lookup"><span data-stu-id="431af-109">Today's web apps are expected to be available 24/7 from anywhere in the world, and usable from virtually any device or screen size.</span></span> <span data-ttu-id="431af-110">Os aplicativos Web precisam ser seguros, flexíveis e escalonáveis para atender aos picos da demanda.</span><span class="sxs-lookup"><span data-stu-id="431af-110">Web applications must be secure, flexible, and scalable to meet spikes in demand.</span></span> <span data-ttu-id="431af-111">Cada vez mais, os cenários complexos devem ser tratados por experiências avançadas do usuário criadas no cliente por meio de JavaScript e pela comunicação eficiente por meio de APIs Web.</span><span class="sxs-lookup"><span data-stu-id="431af-111">Increasingly, complex scenarios should be handled by rich user experiences built on the client using JavaScript, and communicating efficiently through web APIs.</span></span>

<span data-ttu-id="431af-112">O ASP.NET Core é otimizado para aplicativos Web modernos e cenários de hospedagem baseada em nuvem.</span><span class="sxs-lookup"><span data-stu-id="431af-112">ASP.NET Core is optimized for modern web applications and cloud-based hosting scenarios.</span></span> <span data-ttu-id="431af-113">Seu design modular permite que os aplicativos dependam somente dos recursos que realmente usarem, melhorando o desempenho e a segurança do aplicativo e, ao mesmo tempo, reduzindo os requisitos de recursos de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="431af-113">Its modular design enables applications to depend on only those features they actually use, improving application security and performance while reducing hosting resource requirements.</span></span>

## <a name="reference-application-eshoponweb"></a><span data-ttu-id="431af-114">Referência de aplicativo: eShopOnWeb</span><span class="sxs-lookup"><span data-stu-id="431af-114">Reference application: eShopOnWeb</span></span>

<span data-ttu-id="431af-115">Estas diretrizes incluem um aplicativo de referência, o _eShopOnWeb_, que demonstra alguns dos princípios e das recomendações.</span><span class="sxs-lookup"><span data-stu-id="431af-115">This guidance includes a reference application, _eShopOnWeb_, that demonstrates some of the principles and recommendations.</span></span> <span data-ttu-id="431af-116">O aplicativo é uma loja online simples compatível com navegação em um catálogo de camisetas, canecas e outros itens de marketing.</span><span class="sxs-lookup"><span data-stu-id="431af-116">The application is a simple online store which supports browsing through a catalog of shirts, coffee mugs, and other marketing items.</span></span> <span data-ttu-id="431af-117">O aplicativo de referência é deliberadamente simples para facilitar o entendimento.</span><span class="sxs-lookup"><span data-stu-id="431af-117">The reference application is deliberately simple in order to make it easy to understand.</span></span>

<span data-ttu-id="431af-118">**Figura 2-1.**</span><span class="sxs-lookup"><span data-stu-id="431af-118">**Figure 2-1.**</span></span> <span data-ttu-id="431af-119">eShopOnWeb</span><span class="sxs-lookup"><span data-stu-id="431af-119">eShopOnWeb</span></span>

![](./media/image2-1.png)

> ### <a name="reference-application"></a><span data-ttu-id="431af-120">Aplicativo de referência</span><span class="sxs-lookup"><span data-stu-id="431af-120">Reference Application</span></span>
>
> - <span data-ttu-id="431af-121">**eShopOnWeb**</span><span class="sxs-lookup"><span data-stu-id="431af-121">**eShopOnWeb**</span></span>  
>   <https://github.com/dotnet/eShopOnWeb>

## <a name="cloud-hosted-and-scalable"></a><span data-ttu-id="431af-122">Hospedado na nuvem e escalonável</span><span class="sxs-lookup"><span data-stu-id="431af-122">Cloud-hosted and scalable</span></span>

<span data-ttu-id="431af-123">O ASP.NET Core é otimizado para a nuvem (nuvem pública, nuvem privada, qualquer nuvem) porque tem baixa memória e alta taxa de transferência.</span><span class="sxs-lookup"><span data-stu-id="431af-123">ASP.NET Core is optimized for the cloud (public cloud, private cloud, any cloud) because it is low-memory and high-throughput.</span></span> <span data-ttu-id="431af-124">Uma superfície menor dos aplicativos ASP.NET Core significa que você pode hospedar mais partes dele no mesmo hardware e pagar por menos recursos quando usar os serviços pré-pagos de hospedagem na nuvem.</span><span class="sxs-lookup"><span data-stu-id="431af-124">The smaller footprint of ASP.NET Core applications means you can host more of them on the same hardware, and you pay for fewer resources when using pay-as-you go cloud hosting services.</span></span> <span data-ttu-id="431af-125">A taxa de transferência mais alta significa que você pode atender mais clientes por meio de um aplicativo considerando o mesmo hardware, reduzindo ainda mais a necessidade de investir em servidores e na infraestrutura de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="431af-125">The higher-throughput means you can serve more customers from an application given the same hardware, further reducing the need to invest in servers and hosting infrastructure.</span></span>

## <a name="cross-platform"></a><span data-ttu-id="431af-126">Plataforma cruzada</span><span class="sxs-lookup"><span data-stu-id="431af-126">Cross platform</span></span>

<span data-ttu-id="431af-127">O ASP.NET Core é multiplataforma e pode ser executado no Windows, no macOS e no Linux.</span><span class="sxs-lookup"><span data-stu-id="431af-127">ASP.NET Core is cross-platform and can run on Linux, macOS, and Windows.</span></span> <span data-ttu-id="431af-128">Isso proporciona muitas novas opções para o desenvolvimento e a implantação de aplicativos criados com o ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="431af-128">This opens up many new options for both development and deployment of apps built with ASP.NET Core.</span></span> <span data-ttu-id="431af-129">Os contêineres do Docker, tanto do Linux quanto do Windows, podem hospedar aplicativos ASP.NET Core, permitindo que eles aproveitem os benefícios de [contêineres e microsserviços](../microservices/index.md).</span><span class="sxs-lookup"><span data-stu-id="431af-129">Docker containers - both Linux and Windows - can host ASP.NET Core applications, allowing them to take advantage of the benefits of [containers and microservices](../microservices/index.md).</span></span>

## <a name="modular-and-loosely-coupled"></a><span data-ttu-id="431af-130">Flexível e acoplado de forma flexível</span><span class="sxs-lookup"><span data-stu-id="431af-130">Modular and loosely coupled</span></span>

<span data-ttu-id="431af-131">Os pacotes NuGet são cidadãos de primeira classe no .NET Core, e os aplicativos ASP.NET Core são compostos por muitas bibliotecas por meio do NuGet.</span><span class="sxs-lookup"><span data-stu-id="431af-131">NuGet packages are first-class citizens in .NET Core, and ASP.NET Core apps are composed of many libraries through NuGet.</span></span> <span data-ttu-id="431af-132">Essa granularidade da funcionalidade ajuda a garantir que os aplicativos dependam e implantem somente a funcionalidade de que realmente precisam, reduzindo sua área da superfície de vulnerabilidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="431af-132">This granularity of functionality helps ensure apps only depend on and deploy functionality they actually require, reducing their footprint and security vulnerability surface area.</span></span>

<span data-ttu-id="431af-133">O ASP.NET Core também é totalmente compatível com a [injeção de dependência](https://deviq.com/dependency-injection/), tanto internamente quanto no nível do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="431af-133">ASP.NET Core also fully supports [dependency injection](https://deviq.com/dependency-injection/), both internally and at the application level.</span></span> <span data-ttu-id="431af-134">As interfaces podem ter várias implementações que podem ser alternadas, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="431af-134">Interfaces can have multiple implementations that can be swapped out as needed.</span></span> <span data-ttu-id="431af-135">A injeção de dependência permite que os aplicativos sejam acoplados de modo flexível a essas interfaces, em vez de a implementações específicas, facilitando a extensão, a manutenção e o teste.</span><span class="sxs-lookup"><span data-stu-id="431af-135">Dependency injection allows apps to loosely couple to those interfaces, rather than specific implementations, making them easier to extend, maintain, and test.</span></span>

## <a name="easily-tested-with-automated-tests"></a><span data-ttu-id="431af-136">Testados facilmente com testes automatizados</span><span class="sxs-lookup"><span data-stu-id="431af-136">Easily tested with automated tests</span></span>

<span data-ttu-id="431af-137">Os aplicativos ASP.NET Core são compatíveis com teste de unidade, além disso, o acoplamento flexível e o suporte a injeções de dependência facilitam a alternância de interesses da infraestrutura com implementações fictícias para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="431af-137">ASP.NET Core applications support unit testing, and their loose coupling and support for dependency injection makes it easy to swap infrastructure concerns with fake implementations for test purposes.</span></span> <span data-ttu-id="431af-138">O ASP.NET Core também fornece um TestServer que pode ser usado para hospedar aplicativos em memória.</span><span class="sxs-lookup"><span data-stu-id="431af-138">ASP.NET Core also ships a TestServer that can be used to host apps in memory.</span></span> <span data-ttu-id="431af-139">Os testes funcionais podem então fazer solicitações para esse servidor em memória, exercitando a pilha completa do aplicativo (incluindo middleware, roteamento, model binding, filtros, etc.) e recebendo uma resposta, tudo isso em uma fração do tempo que levaria para hospedar o aplicativo em um servidor real e fazer solicitações por meio da camada de rede.</span><span class="sxs-lookup"><span data-stu-id="431af-139">Functional tests can then make requests to this in-memory server, exercising the full application stack (including middleware, routing, model binding, filters, etc.) and receiving a response, all in a fraction of the time it would take to host the app on a real server and make requests through the network layer.</span></span> <span data-ttu-id="431af-140">Esses testes são especialmente fáceis de serem gravados e significativos para APIs, que são cada vez mais importantes em aplicativos Web modernos.</span><span class="sxs-lookup"><span data-stu-id="431af-140">These tests are especially easy to write, and valuable, for APIs, which are increasingly important in modern web applications.</span></span>

## <a name="traditional-and-spa-behaviors-supported"></a><span data-ttu-id="431af-141">Comportamentos tradicionais e de SPA com suporte</span><span class="sxs-lookup"><span data-stu-id="431af-141">Traditional and SPA behaviors supported</span></span>

<span data-ttu-id="431af-142">Os aplicativos Web tradicionais envolvem pouco comportamento do lado do cliente e, em vez disso, dependem do servidor para todas as consultas, atualizações e navegação que o aplicativo pode precisar fazer.</span><span class="sxs-lookup"><span data-stu-id="431af-142">Traditional web applications have involved little client-side behavior, but instead have relied on the server for all navigation, queries, and updates the app might need to make.</span></span> <span data-ttu-id="431af-143">Cada nova operação feita pelo usuário é convertida em uma nova solicitação da Web, com o resultado sendo um recarregamento de página inteira no navegador do usuário final.</span><span class="sxs-lookup"><span data-stu-id="431af-143">Each new operation made by the user would be translated into a new web request, with the result being a full page reload in the end user's browser.</span></span> <span data-ttu-id="431af-144">As estruturas MVC (Modelo-Exibição-Controlador) clássicas normalmente seguem essa abordagem, com cada nova solicitação correspondente a uma ação de controlador diferente, que, por sua vez, trabalham com um modelo e retornam uma exibição.</span><span class="sxs-lookup"><span data-stu-id="431af-144">Classic Model-View-Controller (MVC) frameworks typically follow this approach, with each new request corresponding to a different controller action, which in turn would work with a model and return a view.</span></span> <span data-ttu-id="431af-145">Algumas operações individuais em determinada página podem ser aprimoradas com a funcionalidade AJAX (Asynchronous JavaScript And XML), mas a arquitetura geral do aplicativo usava muitas diferentes exibições do MVC e pontos de extremidade de URL.</span><span class="sxs-lookup"><span data-stu-id="431af-145">Some individual operations on a given page might be enhanced with AJAX (Asynchronous JavaScript and XML) functionality, but the overall architecture of the app used many different MVC views and URL endpoints.</span></span> <span data-ttu-id="431af-146">Além disso, o ASP.NET Core MVC também é compatível com Razor Pages, uma maneira mais simples para organizar as páginas de estilo MVC.</span><span class="sxs-lookup"><span data-stu-id="431af-146">In addition, ASP.NET Core MVC also supports Razor Pages, a simpler way to organize MVC-style pages.</span></span>

<span data-ttu-id="431af-147">Por outro lado, os SPAs (aplicativos de página única) envolvem muito poucos carregamentos de página do lado do servidor gerados dinamicamente (se houver).</span><span class="sxs-lookup"><span data-stu-id="431af-147">Single Page Applications (SPAs), by contrast, involve very few dynamically generated server-side page loads (if any).</span></span> <span data-ttu-id="431af-148">Muitos SPAs são inicializados em um arquivo HTML estático que carrega as bibliotecas JavaScript necessárias para iniciar e executar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="431af-148">Many SPAs are initialized within a static HTML file that loads the necessary JavaScript libraries to start and run the app.</span></span> <span data-ttu-id="431af-149">Esses aplicativos fazem uso intenso de APIs Web para suas necessidades de dados e podem fornecer experiências do usuário muito mais avançadas.</span><span class="sxs-lookup"><span data-stu-id="431af-149">These apps make heavy usage of web APIs for their data needs and can provide much richer user experiences.</span></span>

<span data-ttu-id="431af-150">Muitos aplicativos Web envolvem uma combinação do comportamento do aplicativo Web tradicional (normalmente para o conteúdo) e SPAs (para a interatividade).</span><span class="sxs-lookup"><span data-stu-id="431af-150">Many web applications involve a combination of traditional web application behavior (typically for content) and SPAs (for interactivity).</span></span> <span data-ttu-id="431af-151">O ASP.NET Core é compatível com o MVC (baseado em Exibições ou em Páginas) e com as APIs Web no mesmo aplicativo, usando o mesmo conjunto de ferramentas e de bibliotecas da estrutura subjacentes.</span><span class="sxs-lookup"><span data-stu-id="431af-151">ASP.NET Core supports both MVC (Views or Page based) and web APIs in the same application, using the same set of tools and underlying framework libraries.</span></span>

## <a name="simple-development-and-deployment"></a><span data-ttu-id="431af-152">Desenvolvimento e implantação simples</span><span class="sxs-lookup"><span data-stu-id="431af-152">Simple development and deployment</span></span>

<span data-ttu-id="431af-153">Os aplicativos ASP.NET Core podem ser escritos com editores de texto e interfaces de linha de comando simples ou com ambientes de desenvolvimento completo como o Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="431af-153">ASP.NET Core applications can be written using simple text editors and command line interfaces, or full-featured development environments like Visual Studio.</span></span> <span data-ttu-id="431af-154">Normalmente, os aplicativos monolíticos são implantados em um único ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="431af-154">Monolithic applications are typically deployed to a single endpoint.</span></span> <span data-ttu-id="431af-155">As implantações podem ser automatizadas com facilidade para ocorrerem como parte de um pipeline de CI (integração contínua) e CD (entrega contínua).</span><span class="sxs-lookup"><span data-stu-id="431af-155">Deployments can easily be automated to occur as part of a continuous integration (CI) and continuous delivery (CD) pipeline.</span></span> <span data-ttu-id="431af-156">Além das ferramentas de CI/CD tradicionais, o Microsoft Azure tem suporte integrado para repositórios Git e pode implantar automaticamente atualizações conforme elas são feitas em um GIT branch ou marcação especificado.</span><span class="sxs-lookup"><span data-stu-id="431af-156">In addition to traditional CI/CD tools, Windows Azure has integrated support for git repositories and can automatically deploy updates as they are made to a specified git branch or tag.</span></span>

## <a name="traditional-aspnet-and-web-forms"></a><span data-ttu-id="431af-157">ASP.NET tradicional e Web Forms</span><span class="sxs-lookup"><span data-stu-id="431af-157">Traditional ASP.NET and Web Forms</span></span>

<span data-ttu-id="431af-158">Além do ASP.NET Core, o ASP.NET 4.x tradicional continua sendo uma plataforma robusta e confiável para a criação de aplicativos Web.</span><span class="sxs-lookup"><span data-stu-id="431af-158">In addition to ASP.NET Core, traditional ASP.NET 4.x continues to be a robust and reliable platform for building web applications.</span></span> <span data-ttu-id="431af-159">O ASP.NET é compatível com modelos de desenvolvimento do MVC e da API Web, bem como ao Web Forms, que é adequado para o desenvolvimento de aplicativos avançados baseados em página e apresenta um ecossistema avançado de componentes de terceiros.</span><span class="sxs-lookup"><span data-stu-id="431af-159">ASP.NET supports MVC and Web API development models, as well as Web Forms, which is well-suited to rich page-based application development and features a rich third-party component ecosystem.</span></span> <span data-ttu-id="431af-160">O Microsoft Azure apresenta um excelente suporte de longa data para aplicativos ASP.NET 4.x e muitos desenvolvedores estão familiarizados com essa plataforma.</span><span class="sxs-lookup"><span data-stu-id="431af-160">Windows Azure has great longstanding support for ASP.NET 4.x applications, and many developers are familiar with this platform.</span></span>

> ### <a name="references--modern-web-applications"></a><span data-ttu-id="431af-161">Referências – Aplicativos Web modernos</span><span class="sxs-lookup"><span data-stu-id="431af-161">References – Modern Web Applications</span></span>
>
> - <span data-ttu-id="431af-162">**Introdução ao ASP.NET Core**</span><span class="sxs-lookup"><span data-stu-id="431af-162">**Introduction to ASP.NET Core**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/>
> - <span data-ttu-id="431af-163">**Seis benefícios principais do ASP.NET Core que o tornam diferente e melhor**</span><span class="sxs-lookup"><span data-stu-id="431af-163">**Six Key Benefits of ASP.NET Core which make it Different and Better**</span></span>  
>   <https://blog.trigent.com/six-key-benefits-of-asp-net-core-1-0-which-make-it-different-better/>
> - <span data-ttu-id="431af-164">**Teste no ASP.NET Core**</span><span class="sxs-lookup"><span data-stu-id="431af-164">**Testing in ASP.NET Core**</span></span>  
>   <https://docs.microsoft.com/aspnet/core/testing/>

>[!div class="step-by-step"]
><span data-ttu-id="431af-165">[Anterior](index.md)
>[Próximo](choose-between-traditional-web-and-single-page-apps.md)</span><span class="sxs-lookup"><span data-stu-id="431af-165">[Previous](index.md)
[Next](choose-between-traditional-web-and-single-page-apps.md)</span></span>