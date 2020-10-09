---
description: 了解 Chromium 扩展和构建扩展的核心概念。
title: Microsoft Edge (Chromium) 扩展概念和体系结构
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/01/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: 8ffdd19e1a1e36a4d10fdd80bd7dd5654d543527
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104726"
---
# <span data-ttu-id="6de32-104">扩展概念和体系结构</span><span class="sxs-lookup"><span data-stu-id="6de32-104">Extension concepts and architecture</span></span>

<span data-ttu-id="6de32-105">本文提供了在构建扩展时有助于的概念的简要介绍。</span><span class="sxs-lookup"><span data-stu-id="6de32-105">This article provides a brief introduction to concepts that help when building extensions.</span></span> <span data-ttu-id="6de32-106">若要了解 Microsoft Edge \ (Chromium \ ) 扩展，我们首先讨论多选项卡浏览器的工作方式。</span><span class="sxs-lookup"><span data-stu-id="6de32-106">To understand Microsoft Edge \(Chromium\) extensions, we first discuss how multi-tab browsers work.</span></span>


## <span data-ttu-id="6de32-107">了解浏览器的工作方式</span><span class="sxs-lookup"><span data-stu-id="6de32-107">Understand how browsers work</span></span>

<span data-ttu-id="6de32-108">下表列出了在构建扩展之前需要了解的有用信息。</span><span class="sxs-lookup"><span data-stu-id="6de32-108">The following list outlines helpful information to understand before building your extension.</span></span>

1.  <span data-ttu-id="6de32-109">每个浏览器选项卡都独立于每个其他选项卡。 每个选项卡都在其自己的独立于其他浏览器选项卡和线程的线程中运行。</span><span class="sxs-lookup"><span data-stu-id="6de32-109">Each browser tab is isolated from every other tab.  Each tab runs in its own thread that's isolated from other browser tabs and threads.</span></span>

    ![每个 "浏览器" 选项卡的一个线程](media/index-image1-browsertabs.png)  

2.  <span data-ttu-id="6de32-111">每个选项卡处理一个 GET 请求。</span><span class="sxs-lookup"><span data-stu-id="6de32-111">Each tab handles one GET request.</span></span>  <span data-ttu-id="6de32-112">每个选项卡都使用 URL 获取单个数据流，它通常是 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="6de32-112">Each tab uses a URL to get a single stream of data, which is normally an HTML document.</span></span>  <span data-ttu-id="6de32-113">此单个流或页面，包括有关 JavaScript 包括标记、图像引用、CSS 引用等的说明。</span><span class="sxs-lookup"><span data-stu-id="6de32-113">That single stream or page, includes instructions like JavaScript include tags, image references, CSS references, and more.</span></span>  <span data-ttu-id="6de32-114">所有资源都将下载到该选项卡页，然后在该选项卡中呈现页面。</span><span class="sxs-lookup"><span data-stu-id="6de32-114">All resources are downloaded to that one tab page, and then the page is rendered in the tab.</span></span>  

3.  <span data-ttu-id="6de32-115">在每个选项卡和远程服务器之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="6de32-115">Communication occurs between each tab and remote servers.</span></span>  <span data-ttu-id="6de32-116">每个选项卡都在隔离的环境中运行。</span><span class="sxs-lookup"><span data-stu-id="6de32-116">Each tab runs in an isolated environment.</span></span> <span data-ttu-id="6de32-117">它们仍连接到 internet，但与其他选项卡隔离。</span><span class="sxs-lookup"><span data-stu-id="6de32-117">They're still connected to the internet but they're isolated from other tabs.</span></span>  <span data-ttu-id="6de32-118">选项卡可能运行 JavaScript 以与服务器通信。</span><span class="sxs-lookup"><span data-stu-id="6de32-118">Tabs may run JavaScript to communicate with servers.</span></span> <span data-ttu-id="6de32-119">这些服务器是在选项卡的 URL 栏中输入的第一个 GET 请求的原始服务器。</span><span class="sxs-lookup"><span data-stu-id="6de32-119">These servers are the originating server for the first GET request that was entered into the URL bar of the tab.</span></span>  

4.  <span data-ttu-id="6de32-120">扩展模型使用不同的通信模型。</span><span class="sxs-lookup"><span data-stu-id="6de32-120">The extension model uses a different communication model.</span></span>  <span data-ttu-id="6de32-121">与选项卡页类似，扩展在独立于所有选项卡页线程的单个线程中运行。</span><span class="sxs-lookup"><span data-stu-id="6de32-121">Similar to tab pages, extensions run in individual threads that are isolated from all tab page threads.</span></span>  <span data-ttu-id="6de32-122">选项卡向远程服务器发出单个 GET 请求，然后呈现页面。</span><span class="sxs-lookup"><span data-stu-id="6de32-122">Tabs issue single GET requests to remote servers, and then renders the page.</span></span> <span data-ttu-id="6de32-123">但是，扩展功能类似于远程服务器。</span><span class="sxs-lookup"><span data-stu-id="6de32-123">However, extensions function similar to a remote server.</span></span> <span data-ttu-id="6de32-124">在浏览器中安装扩展将在浏览器中创建独立的 web 服务器。</span><span class="sxs-lookup"><span data-stu-id="6de32-124">Installing extensions in your browser creates a standalone web server in the browser.</span></span> <span data-ttu-id="6de32-125">该扩展与所有选项卡页隔离。</span><span class="sxs-lookup"><span data-stu-id="6de32-125">The extension is isolated from all tab pages.</span></span>  

    ![扩展使用不同的通信模型](media/index-image3-upsidedown.png)  

## <span data-ttu-id="6de32-127">扩展体系结构</span><span class="sxs-lookup"><span data-stu-id="6de32-127">Extension architecture</span></span>

<span data-ttu-id="6de32-128">下表列出了与扩展体系结构相关的有用信息。</span><span class="sxs-lookup"><span data-stu-id="6de32-128">The following list outlines helpful information as it relates to the architecture of an extension.</span></span>  

1.  <span data-ttu-id="6de32-129">扩展 web 服务器捆绑包。</span><span class="sxs-lookup"><span data-stu-id="6de32-129">The Extension web server bundle.</span></span>  <span data-ttu-id="6de32-130">扩展名是 web 资源的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="6de32-130">An extension is a bundle of web resources.</span></span> <span data-ttu-id="6de32-131">这些 web 资源与 web 开发人员发布到 web 服务器的其他资源类似。</span><span class="sxs-lookup"><span data-stu-id="6de32-131">These web resources are similar to other resources that web developers publish to web servers.</span></span> <span data-ttu-id="6de32-132">开发人员在构建扩展时，将这些 web 资源捆绑到一个 zip 文件中。</span><span class="sxs-lookup"><span data-stu-id="6de32-132">Developers bundle these web resources into a zip file when building an extension.</span></span>
    
    <span data-ttu-id="6de32-133">Zip 文件包括 HTML、CSS、JavaScript 和图像文件。</span><span class="sxs-lookup"><span data-stu-id="6de32-133">The zip file includes HTML, CSS, JavaScript, and image files.</span></span>  <span data-ttu-id="6de32-134">Zip 文件的根中需要另一个文件。</span><span class="sxs-lookup"><span data-stu-id="6de32-134">There's one additional file that is required in the root of the zip file.</span></span> <span data-ttu-id="6de32-135">此文件是清单文件，其名称为 `manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="6de32-135">This file is the manifest file, and is named `manifest.json`.</span></span>  <span data-ttu-id="6de32-136">它是您的扩展的蓝图，包括您的扩展的版本、标题、运行扩展所需的权限等。</span><span class="sxs-lookup"><span data-stu-id="6de32-136">It's the blueprint of  your extension and includes the version of your extension, the title, permissions needed for the extension to run, and so on.</span></span>

2.  <span data-ttu-id="6de32-137">启动扩展服务器。</span><span class="sxs-lookup"><span data-stu-id="6de32-137">Launching the extension server.</span></span>  <span data-ttu-id="6de32-138">Web 服务器包含您的 web 包。</span><span class="sxs-lookup"><span data-stu-id="6de32-138">Web servers contain your web bundle.</span></span> <span data-ttu-id="6de32-139">浏览器导航到服务器上的 Url，并下载要在浏览器中呈现的文件。</span><span class="sxs-lookup"><span data-stu-id="6de32-139">Browsers navigate to URLs on the server, and download the file to render in the browser.</span></span> <span data-ttu-id="6de32-140">浏览器使用证书、配置文件等进行导航。</span><span class="sxs-lookup"><span data-stu-id="6de32-140">Browsers navigate using certificates, configuration files, and so on.</span></span>  <span data-ttu-id="6de32-141">如果存在 `index.html` 文件，则该文件存储在 web 服务器上的特殊位置。</span><span class="sxs-lookup"><span data-stu-id="6de32-141">If there's an `index.html` file, that's stored at a special location on the web server.</span></span>  

    <span data-ttu-id="6de32-142">使用扩展时，浏览器的选项卡页使用扩展运行时获取您的扩展的 web 包。</span><span class="sxs-lookup"><span data-stu-id="6de32-142">When we use extensions, the tab page of your browser gets to the web bundle of your extension using the extension runtime.</span></span>  <span data-ttu-id="6de32-143">扩展运行时提供 URL 中的文件 `extension://{some-long-unique-identifier}/index.html` ，其中 `{some-long-unique-identifier}` 是在安装时分配给扩展名的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6de32-143">The extension runtime serves the files from the URL `extension://{some-long-unique-identifier}/index.html`, where `{some-long-unique-identifier}` is a unique identifier assigned to the extension when it's installed.</span></span>  <span data-ttu-id="6de32-144">每个扩展都使用不同的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6de32-144">Each extension uses a different unique identifier.</span></span> <span data-ttu-id="6de32-145">每个标识符指向您的浏览器中安装的 web 包。</span><span class="sxs-lookup"><span data-stu-id="6de32-145">Each identifier points to the web bundle that's installed in your browser.</span></span>   

3.  <span data-ttu-id="6de32-146">扩展可以与选项卡和浏览器工具栏通信。</span><span class="sxs-lookup"><span data-stu-id="6de32-146">Extensions can communicate with tabs and the browser toolbar.</span></span>   <span data-ttu-id="6de32-147">扩展可以与浏览器的工具栏交互。</span><span class="sxs-lookup"><span data-stu-id="6de32-147">Extensions can interact with the toolbar of your browser.</span></span> <span data-ttu-id="6de32-148">每个扩展都在单独的线程中管理运行的选项卡页，并且每个选项卡页上的 DOM 操作是独立的</span><span class="sxs-lookup"><span data-stu-id="6de32-148">Each extension manages running tab pages in separate threads, and DOM manipulation on each tab page is isolated.</span></span>  <span data-ttu-id="6de32-149">扩展使用扩展 API 在扩展和选项卡页之间通信。</span><span class="sxs-lookup"><span data-stu-id="6de32-149">Extensions use the extensions API to communicate between the extension and tab pages.</span></span>  <span data-ttu-id="6de32-150">此扩展 API 提供了其他功能，包括通知管理、存储管理等。</span><span class="sxs-lookup"><span data-stu-id="6de32-150">This extension API provides additional capabilities that include notification management, storage management, and so on.</span></span>  

    <span data-ttu-id="6de32-151">与 web 服务器一样，打开浏览器时，扩展会等待通知。</span><span class="sxs-lookup"><span data-stu-id="6de32-151">Just like web servers, extensions wait on notifications when the browser is open.</span></span>  <span data-ttu-id="6de32-152">扩展和选项卡页在彼此隔离的线程中运行。</span><span class="sxs-lookup"><span data-stu-id="6de32-152">Extensions and tab pages run in threads that are isolated from each other.</span></span> <span data-ttu-id="6de32-153">但是，开发人员可以使用扩展 API 和清单文件中的权限来允许扩展处理任何选项卡页。</span><span class="sxs-lookup"><span data-stu-id="6de32-153">However, developers can use the extensions API, and permissions in the manifest file to allow an extension to work with any tab page.</span></span>  

4. <span data-ttu-id="6de32-154">扩展在安装时提供自愿加入权限。</span><span class="sxs-lookup"><span data-stu-id="6de32-154">Extensions provide opt-in permissions at install time.</span></span>  <span data-ttu-id="6de32-155">扩展权限由开发人员在文件中指定 `manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="6de32-155">Extension permissions are specified by the developer in the `manifest.json` file.</span></span> <span data-ttu-id="6de32-156">安装扩展时，将向用户显示有关该扩展需要运行的权限的信息。</span><span class="sxs-lookup"><span data-stu-id="6de32-156">When installing extensions, users are presented with information on the permissions that the extension needs to run.</span></span> <span data-ttu-id="6de32-157">根据所需的权限类型，扩展可以提取和使用浏览器中的信息。</span><span class="sxs-lookup"><span data-stu-id="6de32-157">Based on the type of permission required, the extension may extract and use information from the browser.</span></span>


## <span data-ttu-id="6de32-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6de32-158">Next steps</span></span>

 <span data-ttu-id="6de32-159">有关 "扩展" 入门的信息，请参阅 [创建扩展教程][CreateAnExtensionPart1]。</span><span class="sxs-lookup"><span data-stu-id="6de32-159">For information on getting started with extensions, see [Create an extension tutorial][CreateAnExtensionPart1].</span></span> 



<!-- image links -->  

<!-- links -->  

[CreateAnExtensionPart1]: ./part1-simple-extension.md "创建扩展教程-第1部分 |Microsoft 文档"  