---
description: 了解 Chromium 扩展名以及渐进式构建完整的图片查看扩展，包括选项、内容注入、后台脚本、存储等。
title: Microsoft Edge （Chromium）扩展入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/05/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: a271514f39ed8bbe379116c33e23c973d3eb6adb
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563375"
---
# <span data-ttu-id="ec27e-104">Microsoft Edge \ （Chromium \）扩展入门</span><span class="sxs-lookup"><span data-stu-id="ec27e-104">Getting Started With Microsoft Edge \(Chromium\) Extensions</span></span>  

<span data-ttu-id="ec27e-105">如果要直接跳转到构建您的第一个扩展，请转到构建第1天的 NASA 图片。</span><span class="sxs-lookup"><span data-stu-id="ec27e-105">If you want to jump directly into building your first Extension, go to part 1 of building a NASA picture of the day Extension.</span></span>  

<span data-ttu-id="ec27e-106">如果你不熟悉扩展概念和体系结构，请继续阅读，并了解有关哪些扩展的信息。</span><span class="sxs-lookup"><span data-stu-id="ec27e-106">If you are not familiar with the Extension concepts and architecture, continue reading, and learn all about what Extensions are.</span></span>  <span data-ttu-id="ec27e-107">此信息有助于你更轻松地构建扩展，因为你了解它们背后的动机和体系结构。</span><span class="sxs-lookup"><span data-stu-id="ec27e-107">This information helps you build Extensions much easier since you understand the motivations and architecture behind them.</span></span>  

## <span data-ttu-id="ec27e-108">构建日分机的 NASA 图片</span><span class="sxs-lookup"><span data-stu-id="ec27e-108">Build a NASA picture of the day Extension</span></span>  

<span data-ttu-id="ec27e-109">每个部分在其中引用了已完成的扩展源安装包。</span><span class="sxs-lookup"><span data-stu-id="ec27e-109">Each section has the completed Extension source installation package referenced in it.</span></span>  

*   [<span data-ttu-id="ec27e-110">构建一个简单的扩展名，它会弹出一天的 NASA 图片</span><span class="sxs-lookup"><span data-stu-id="ec27e-110">Build a simple Extension that pops up NASA picture of the day</span></span>](part1-simple-extension.md)  
    *   <span data-ttu-id="ec27e-111">创建清单</span><span class="sxs-lookup"><span data-stu-id="ec27e-111">Creating a Manifest</span></span>  
    *   <span data-ttu-id="ec27e-112">分配扩展名图标</span><span class="sxs-lookup"><span data-stu-id="ec27e-112">Assign Extension icons</span></span>  
    *   <span data-ttu-id="ec27e-113">显示弹出窗口</span><span class="sxs-lookup"><span data-stu-id="ec27e-113">Displaying a Pop-up Window</span></span>  
    *   <span data-ttu-id="ec27e-114">在浏览器中本地运行扩展 \ （侧面加载 \）</span><span class="sxs-lookup"><span data-stu-id="ec27e-114">Run your Extension locally in your browser \(side-loading\)</span></span>  

*   [<span data-ttu-id="ec27e-115">在页面正文标记下动态插入 NASA 图片</span><span class="sxs-lookup"><span data-stu-id="ec27e-115">Dynamically insert NASA picture below the page body tag</span></span>](part2-content-scripts.md)  
    *   <span data-ttu-id="ec27e-116">创建插入动态内容脚本的 JavaScript</span><span class="sxs-lookup"><span data-stu-id="ec27e-116">Create JavaScript that inserts dynamic content script</span></span>  
    *   <span data-ttu-id="ec27e-117">在清单中定义页面获取内容脚本</span><span class="sxs-lookup"><span data-stu-id="ec27e-117">Define in manifest which pages get content script</span></span>  
    *   <span data-ttu-id="ec27e-118">以声明方式插入内容脚本</span><span class="sxs-lookup"><span data-stu-id="ec27e-118">Inject content script declaratively</span></span>  
    *   <span data-ttu-id="ec27e-119">在弹出窗口中添加一个按钮以向内容脚本发送消息</span><span class="sxs-lookup"><span data-stu-id="ec27e-119">Add a Button on Pop-up to send a message to content script</span></span>  
    *   <span data-ttu-id="ec27e-120">在内容脚本内接收消息</span><span class="sxs-lookup"><span data-stu-id="ec27e-120">Receive a message inside a content script</span></span>  

## <span data-ttu-id="ec27e-121">在引入扩展之前了解浏览器</span><span class="sxs-lookup"><span data-stu-id="ec27e-121">Understanding the browser before Extensions are introduced</span></span>  

### <span data-ttu-id="ec27e-122">每个浏览器选项卡都独立于每个其他选项卡</span><span class="sxs-lookup"><span data-stu-id="ec27e-122">Each browser tab is isolated from every other tab</span></span>  

<span data-ttu-id="ec27e-123">若要了解 Microsoft Edge \ （Chromium \）扩展的内容，我们首先需要完全了解多选项卡浏览器，如 Microsoft Edge 主要的内容。</span><span class="sxs-lookup"><span data-stu-id="ec27e-123">To understand what a Microsoft Edge \(Chromium\) Extension is, we first need to fully understand what a multi tab browser, like Microsoft Edge does primarily.</span></span>  <span data-ttu-id="ec27e-124">若要开始，每个浏览器选项卡都在一个单独的线程中运行，该线程有效地与其他浏览器选项卡 \ （或线程 \）隔离。</span><span class="sxs-lookup"><span data-stu-id="ec27e-124">To start, each browser tab runs in an individual thread that effectively isolates it from other browser tabs \(or threads\).</span></span>  

![每个 "浏览器" 选项卡的一个线程](media/index-image1-browsertabs.png)  

### <span data-ttu-id="ec27e-126">每个选项卡处理一个 GET 请求</span><span class="sxs-lookup"><span data-stu-id="ec27e-126">Each tab handles one GET request</span></span>  

<span data-ttu-id="ec27e-127">每个选项卡实质上使用 URL \ （也称为统一资源定位器 \）获取单个数据流，这种数据流通常是 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="ec27e-127">Each tab essentially use the URL \(also known as the uniform resource locator\) to get a single stream of data which is typically an HTML document.</span></span>  <span data-ttu-id="ec27e-128">这种单流 \ （或 page \）通常包括说明 \ （如 JavaScript 包括标记、图像引用、CSS 引用等）。</span><span class="sxs-lookup"><span data-stu-id="ec27e-128">That single stream \(or page\), often includes instructions \(like JavaScript include tags, image references, CSS references, and more\).</span></span>  <span data-ttu-id="ec27e-129">最终，所需的所有资源都将下载到该选项卡页，通常会出现一个可视化的可视化对象，并在浏览器选项卡中完全呈现。</span><span class="sxs-lookup"><span data-stu-id="ec27e-129">Ultimately, all the resources needed are downloaded to that one tab page and typically a visualization appears which we see in the browser tab completely rendered.</span></span>  

### <span data-ttu-id="ec27e-130">来自每个选项卡的所有通信都将指向远程服务器</span><span class="sxs-lookup"><span data-stu-id="ec27e-130">All communication from each tab is to remote servers</span></span>  

<span data-ttu-id="ec27e-131">了解每个选项卡在隔离环境中运行意味着这些选项卡彼此隔离，而不是更大的 internet。</span><span class="sxs-lookup"><span data-stu-id="ec27e-131">Understanding that each tab runs in an isolated environment means that these tabs are isolated from each other, but not the greater internet.</span></span>  <span data-ttu-id="ec27e-132">通常，这些选项卡运行 JavaScript 作为编程语言，将其与服务器进行通信，并将其视为在浏览器选项卡顶部的 URL 栏中输入的第一个 GET 请求的发起服务器。</span><span class="sxs-lookup"><span data-stu-id="ec27e-132">Typically, these tabs, running JavaScript as there programming language, communicate back to the server, that should be thought of as the originating server for that first GET request that was entered into the URL bar at the top of the browser tab.</span></span>  

## <span data-ttu-id="ec27e-133">扩展模型将所有内容倒置</span><span class="sxs-lookup"><span data-stu-id="ec27e-133">The Extension model turns everything upside down</span></span>  

<span data-ttu-id="ec27e-134">与选项卡页一样，扩展名在单独的线程中运行，该线程完全独立于讨论的所有选项卡页线程。</span><span class="sxs-lookup"><span data-stu-id="ec27e-134">An Extension, just like tab pages, runs in a individual thread which is completely isolated from all tab page threads that are discussed.</span></span>  <span data-ttu-id="ec27e-135">不同于其作业通常向远程服务器发出单个 GET 请求的选项卡，然后在浏览器中显示该数据的可视化效果，另一种情况下，扩展是指以前驻留在从浏览器选项卡上的 internet 连接另一端的服务器。</span><span class="sxs-lookup"><span data-stu-id="ec27e-135">Unlike the tabs whose job is to typically issue a single GET request to a remote server, then display a visualization of that data in the browser, the Extension, on the other hand is the server, that previously resided on the other end of the internet connection made from a browser tab.</span></span>  

![扩展模型将服务器模型倒置](media/index-image3-upsidedown.png)  

<span data-ttu-id="ec27e-137">理解这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="ec27e-137">This is really important to understand.</span></span>  <span data-ttu-id="ec27e-138">一旦创建了扩展，并在浏览器中安装它，就会创建一个独立的 web 服务器，该服务器在浏览器内保持活动状态，但仍与在该浏览器上运行的每个选项卡页隔离。</span><span class="sxs-lookup"><span data-stu-id="ec27e-138">Once you create an Extension, and install it in your browser, you've created a standalone web server that is living and breathing inside of your browser but still isolated from every tab page running on that browser.</span></span>  

### <span data-ttu-id="ec27e-139">扩展 web 服务器捆绑</span><span class="sxs-lookup"><span data-stu-id="ec27e-139">The Extension web server bundle</span></span>  

<span data-ttu-id="ec27e-140">什么是扩展名？</span><span class="sxs-lookup"><span data-stu-id="ec27e-140">So what is an Extension?</span></span> <span data-ttu-id="ec27e-141">它是捆绑的 web 资源的捆绑（或称为 zip 文件 \），它与 web 开发人员在 web 服务器上发布的内容不同。</span><span class="sxs-lookup"><span data-stu-id="ec27e-141">It is a bundle \(or referred to as a zip file\) of web resources that are no different than what a web developer publishes to a web server.</span></span>  

<span data-ttu-id="ec27e-142">该 zip 文件包含用于制作网页的 HTML、CSS、JavaScript、图像和所有必要的资源。</span><span class="sxs-lookup"><span data-stu-id="ec27e-142">That zip file includes HTML, CSS, JavaScript, images and all the necessary assets to make a web page.</span></span>  <span data-ttu-id="ec27e-143">但是，此 zip 文件的根中需要一个额外的文件，并且该文件名为 `manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="ec27e-143">There is however, one extra file that is required in the root of this zip file, and that file is named `manifest.json`.</span></span>  <span data-ttu-id="ec27e-144">它是你的扩展的蓝图，其中包括你的扩展版本、标题、需要哪些权限才能运行以及更多其他内容。</span><span class="sxs-lookup"><span data-stu-id="ec27e-144">It is the blueprint for your Extension that includes things like what is the version of your Extension, what is the title, what privileges does it need to run and lots more.</span></span>  

![Zip 中的文件视图](media/index-image5-filemanager-view.png)  

### <span data-ttu-id="ec27e-146">启动扩展服务器</span><span class="sxs-lookup"><span data-stu-id="ec27e-146">Launching the Extension server</span></span>  

<span data-ttu-id="ec27e-147">当您部署到 web 服务器时，无论是 Apache、IIS、NGINX 还是任何其他 web 服务器，都包含 web 包。</span><span class="sxs-lookup"><span data-stu-id="ec27e-147">When you deploy to a web server, that web server, whether it is Apache, IIS, NGINX or any other, contains your web bundle.</span></span>  <span data-ttu-id="ec27e-148">当浏览器导航到服务器上的 URL 时，将 `index.html` 下载 web 服务器上的文件。</span><span class="sxs-lookup"><span data-stu-id="ec27e-148">When a browser navigates to a URL on a server, the `index.html` file on the web server is downloaded.</span></span>  <span data-ttu-id="ec27e-149">浏览器使用证书、配置文件等进行导航。</span><span class="sxs-lookup"><span data-stu-id="ec27e-149">The browser navigated using certificates, configuration files, and more.</span></span>  <span data-ttu-id="ec27e-150">`index.html`存储在 web 服务器上某个特殊位置的文件。</span><span class="sxs-lookup"><span data-stu-id="ec27e-150">The `index.html` file stored at some special location on the web server.</span></span>   <span data-ttu-id="ec27e-151">您的扩展对同一内容有何影响？</span><span class="sxs-lookup"><span data-stu-id="ec27e-151">How does your Extension do the same thing?</span></span>  <span data-ttu-id="ec27e-152">尤其是，您的浏览器的选项卡页如何能够访问此 zip 文件 \ （您的扩展名 \）？</span><span class="sxs-lookup"><span data-stu-id="ec27e-152">Particularly, how is the tab pages of your browser able to get to this zip file \(your Extension\)?</span></span>  <span data-ttu-id="ec27e-153">这是扩展运行时对你的影响。</span><span class="sxs-lookup"><span data-stu-id="ec27e-153">That is what the Extension runtime does for you.</span></span>  

<span data-ttu-id="ec27e-154">扩展程序通过 URL \ （统一资源定位器 \）以名称提供所有文件 `extension://{some-long-unique-identifier}/index.html` 。</span><span class="sxs-lookup"><span data-stu-id="ec27e-154">The extension serves the files all from the URL \(uniform resource locator\) at the name `extension://{some-long-unique-identifier}/index.html`.</span></span>  <span data-ttu-id="ec27e-155">我放在方括号中的名称 `{some-long-unique-identifier}` 是分配给你安装的扩展的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ec27e-155">The name I put in brackets, `{some-long-unique-identifier}` is a unique identifier assigned to the Extension that you installed.</span></span>  <span data-ttu-id="ec27e-156">这意味着，如果你在浏览器上安装了10个唯一的扩展，每个扩展都有一个唯一标识符，指向在你的浏览器内部安装的 zip 文件 \ （或扩展绑定 \）。</span><span class="sxs-lookup"><span data-stu-id="ec27e-156">That means, if you have 10 unique Extensions installed on your browser, each Extension has a unique identifier that points at the zip file \(or Extension bundle\) installed inside your browser.</span></span>  

<!--![Unique URLS for Extensions](media/index-image4-uniqueurls.png)  -->  

<!--todo: add image for unique URLs  -->  

### <span data-ttu-id="ec27e-157">扩展管理和与选项卡和浏览器工具栏通信</span><span class="sxs-lookup"><span data-stu-id="ec27e-157">Extensions manage and communicate with tabs and the browser toolbar</span></span>  

<span data-ttu-id="ec27e-158">扩展与浏览器工具栏交互，每个都能够以一种安全的方式管理所有其他运行的选项卡页，以及操作所有这些选项卡页的 DOM。</span><span class="sxs-lookup"><span data-stu-id="ec27e-158">Extensions interact with the browsers toolbar, each is able to manage all the other running tab pages in a safe way, as well as manipulating the DOM of all those tab pages.</span></span>  <span data-ttu-id="ec27e-159">内置于 Chromium 浏览器是一种消息 API，允许在扩展和选项卡页之间进行通信，以使此操作正常发生。</span><span class="sxs-lookup"><span data-stu-id="ec27e-159">Built into the Chromium browser is a message API that allows for communications between the Extensions and the tab pages to allow this to happen gracefully.</span></span>  <span data-ttu-id="ec27e-160">此 API （也称为扩展 API）提供了许多功能，包括通知管理、存储管理等。</span><span class="sxs-lookup"><span data-stu-id="ec27e-160">This API, also known as the Extensions API gives a lots of capabilities including notification management, storage management, and much more.</span></span>  

<span data-ttu-id="ec27e-161">与 web 服务器一样，扩展功能始终可以在浏览器运行时持续运行 \ （或等待通知 \）。</span><span class="sxs-lookup"><span data-stu-id="ec27e-161">Just like web servers, Extensions are able to continually run \(or sleep waiting for notifications\) all the time that the browser is running.</span></span>  <span data-ttu-id="ec27e-162">你可以将扩展视为浏览器的 orchestrator。</span><span class="sxs-lookup"><span data-stu-id="ec27e-162">You may think of an Extension as an orchestrator for the browser.</span></span>  <span data-ttu-id="ec27e-163">同样，扩展运行完全独立于选项卡页，但通过扩展 API 以及授予扩展的自愿加入权限，每个扩展都能够虚拟地控制浏览器中运行的任何选项卡页。</span><span class="sxs-lookup"><span data-stu-id="ec27e-163">Again, the Extension runs completely isolated from the tab pages, but through the Extensions API, and opt-in permissions granted to the Extension, each Extension is able to virtually control any and all tab pages running in the browser.</span></span>  

### <span data-ttu-id="ec27e-164">扩展在安装时提供选择项安全模型</span><span class="sxs-lookup"><span data-stu-id="ec27e-164">Extensions provide an opt-in at install time security model</span></span>  

<span data-ttu-id="ec27e-165">通过文件中的声明，每个扩展都 `manifest.json` 允许安装扩展的用户授予不同级别的机构。</span><span class="sxs-lookup"><span data-stu-id="ec27e-165">Each Extension, through a declaration in the `manifest.json` file allows the person installing the Extension to give it different levels of authority.</span></span>  <span data-ttu-id="ec27e-166">当用户安装时，此权限允许扩展，以便扩展能够提取任何信息，并通过扩展处理该数据。</span><span class="sxs-lookup"><span data-stu-id="ec27e-166">This authority allows Extensions, when installed by a user, to opt-in so that the Extension is able to extract any information, and process that data through the Extension.</span></span>  

<!-- image links -->  

<!-- links -->  
