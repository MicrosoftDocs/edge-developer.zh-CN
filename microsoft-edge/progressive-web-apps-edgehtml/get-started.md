---
description: 本指南概括介绍了如何在 Windows 上构建渐进式 web 应用的 PWA 基础知识和工具。
title: 渐进式 Web 应用入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 web 应用、PWA、Edge、Windows、PWABuilder、web 清单、服务工作人员、推送
ms.openlocfilehash: 84d7c753cfece1591348e06b6728939187e37482
ms.sourcegitcommit: ef6d6adae1f4d18a219fa3e17f91b95b40367a40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934903"
---
# <span data-ttu-id="1f077-104">渐进式 Web 应用入门</span><span class="sxs-lookup"><span data-stu-id="1f077-104">Get started with Progressive Web Apps</span></span>  

<span data-ttu-id="1f077-105">渐进式 Web 应用 \ (PWAs \ ) 只是一种 Web 应用，通过支持平台和浏览器引擎（如从主屏幕安装、脱机支持和推送通知）的本机应用功能 [逐渐增强][WikiProgressiveEnhancement] 。</span><span class="sxs-lookup"><span data-stu-id="1f077-105">Progressive Web Apps \(PWAs\) are simply web apps that are [progressively enhanced][WikiProgressiveEnhancement] with native app-like features on supporting platforms and browser engines, such as launch-from-homescreen installation, offline support, and push notifications.</span></span>  <span data-ttu-id="1f077-106">在使用 Microsoft Edge \ (EdgeHTML \ ) 引擎的 Windows 10 上，PWAs 将独立于浏览器窗口运行的额外优势视为 [通用 Windows 平台][WindowsUwpGetStartedWhat] 应用。</span><span class="sxs-lookup"><span data-stu-id="1f077-106">On Windows 10 with the Microsoft Edge \(EdgeHTML\) engine, PWAs enjoy the added advantage of running independently of the browser window as [Universal Windows Platform][WindowsUwpGetStartedWhat] apps.</span></span>  

<span data-ttu-id="1f077-107">本指南通过 `localhost` 使用 Microsoft Visual Studio 和一些 Pwa 生成器实用工具构建一个简单的 web 应用，为你提供了 pwa 基础知识的概述。</span><span class="sxs-lookup"><span data-stu-id="1f077-107">This guide gives you an overview of PWA basics by building a simple `localhost` web app as a PWA using Microsoft Visual Studio and some PWA Builder utilities.</span></span>  <span data-ttu-id="1f077-108">已完成的产品在任何支持 PWAs 的浏览器中的工作方式都类似。</span><span class="sxs-lookup"><span data-stu-id="1f077-108">The finished product works similarly across any browser that supports PWAs.</span></span>  

> [!TIP]
> <span data-ttu-id="1f077-109">若要快速将现有网站转换为 PWA 并将其打包到 Windows 10 和其他应用平台，请查看 [PWA 生成器][PwaBuilder]。</span><span class="sxs-lookup"><span data-stu-id="1f077-109">For a quick way to convert an existing site to a PWA and package it for Windows 10 and other app platforms, review [PWA Builder][PwaBuilder].</span></span>  

## <span data-ttu-id="1f077-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="1f077-110">Prerequisites</span></span>  

<span data-ttu-id="1f077-111">你可以通过任何 web 开发 IDE 生成 PWAs。</span><span class="sxs-lookup"><span data-stu-id="1f077-111">You may build PWAs with any web development IDE.</span></span>  <span data-ttu-id="1f077-112">以下仅是本指南的先决条件，本指南将指导你完成 Windows 开发人员生态系统中的 PWA 工具支持。</span><span class="sxs-lookup"><span data-stu-id="1f077-112">The following are only prerequisites for this guide, which walks you through PWA tooling support in the Windows developer ecosystem.</span></span>  

*   <span data-ttu-id="1f077-113">下载 \ (闲 \ ) [Visual Studio 社区 2017][VisualStudioDownloads]。</span><span class="sxs-lookup"><span data-stu-id="1f077-113">Download the \(free\) [Visual Studio Community 2017][VisualStudioDownloads].</span></span>  <span data-ttu-id="1f077-114">您也可以使用专业版、企业版或 [预览版][VisualStudioPreview] 。</span><span class="sxs-lookup"><span data-stu-id="1f077-114">You may also use the Professional, Enterprise, or [Preview][VisualStudioPreview] editions.</span></span>  <span data-ttu-id="1f077-115">从 Visual Studio 安装程序中，选择以下工作负荷。</span><span class="sxs-lookup"><span data-stu-id="1f077-115">From the Visual Studio Installer, choose the following Workloads.</span></span>  
    
    *   **<span data-ttu-id="1f077-116">通用 Windows 平台开发</span><span class="sxs-lookup"><span data-stu-id="1f077-116">Universal Windows Platform development</span></span>**  
    *   **<span data-ttu-id="1f077-117">Node.js 开发</span><span class="sxs-lookup"><span data-stu-id="1f077-117">Node.js development</span></span>**  

## <span data-ttu-id="1f077-118">设置基本 web 应用</span><span class="sxs-lookup"><span data-stu-id="1f077-118">Set up a basic web app</span></span>  

<span data-ttu-id="1f077-119">为了简便起见，请使用 Visual Studio [Node.js 和 Express 应用][VisualStudioNodeJsTutorial] 模板来创建用于提供 `localhost` 页面的 web 应用 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="1f077-119">For the sake of simplicity, use the Visual Studio [Node.js and Express app][VisualStudioNodeJsTutorial] template to create `localhost` web app that serves up an `index.html` page.</span></span>  <span data-ttu-id="1f077-120">假设你是作为 PWA 开发的引人注目的全功能 web 应用的占位符。</span><span class="sxs-lookup"><span data-stu-id="1f077-120">Imagine this as a placeholder for the compelling, full-featured web app that you are developing as a PWA.</span></span>  

1.  <span data-ttu-id="1f077-121">启动 Visual Studio，然后启动新项目。</span><span class="sxs-lookup"><span data-stu-id="1f077-121">Launch Visual Studio, and start a new project.</span></span>  
    *   <span data-ttu-id="1f077-122">**文件**  > **新**  > **项目 ...**</span><span class="sxs-lookup"><span data-stu-id="1f077-122">**File** > **New** > **Project...**</span></span>  
    *   `Ctrl`+`Shift`+`N`  
1.  <span data-ttu-id="1f077-123">在 " **JavaScript**" 下，选择 " **基本 Node.js Express 4 应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="1f077-123">Under **JavaScript**, select **Basic Node.js Express 4 Application**.</span></span>  <span data-ttu-id="1f077-124">设置 "名称" 和 "位置"，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="1f077-124">Set the name and location and choose **OK**.</span></span>  
    
    ![在 Visual Studio 中选择 Node.js Express 4 项目模板][ImageVsNodejsExpressTemplate]  
    
1.  <span data-ttu-id="1f077-126">新项目加载后，选择 "**生成**\ (`Ctrl` + `Shift` + `B` \ ) "，然后**开始调试**\ (`F5` \ ) 。</span><span class="sxs-lookup"><span data-stu-id="1f077-126">Once your new project loads, choose **Build** \(`Ctrl`+`Shift`+`B`\) and **Start Debugging** \(`F5`\).</span></span>  <span data-ttu-id="1f077-127">验证在 `index.html` 浏览时是否加载文件 `http://localhost:1337` 。</span><span class="sxs-lookup"><span data-stu-id="1f077-127">Verify that your `index.html` file loads when you browse to `http://localhost:1337`.</span></span>  
    
    ![在 localhost 上运行新网站][ImageVsNodejsExpressIndex]  

## <span data-ttu-id="1f077-129">将应用转换为 PWA</span><span class="sxs-lookup"><span data-stu-id="1f077-129">Turn your app into a PWA</span></span>  

<span data-ttu-id="1f077-130">现在可以将 web 应用的基本 [PWA 要求][PwaEdgehtmlIndexRequirements] 连在一起： *web 应用清单*、 *HTTPS* 和 *服务工作人员*。</span><span class="sxs-lookup"><span data-stu-id="1f077-130">Now it is time to wire up the basic [PWA requirements][PwaEdgehtmlIndexRequirements] for your web app: a *Web App Manifest*, *HTTPS* and *Service Workers*.</span></span>  

### <span data-ttu-id="1f077-131">Web App 清单</span><span class="sxs-lookup"><span data-stu-id="1f077-131">Web App Manifest</span></span>  

<span data-ttu-id="1f077-132">[Web 应用清单][MDNWebAppManifest]是一个 JSON 元数据文件，用于描述你的应用，包括名称、作者、条目页面 URL 和一个或多个图标。</span><span class="sxs-lookup"><span data-stu-id="1f077-132">A [Web App Manifest][MDNWebAppManifest] is a JSON metadata file describing your app, including the name, author, entry page URL, and one or more icons.</span></span>  <span data-ttu-id="1f077-133">由于它遵循 [基于标准的架构][W3cWebAppManifest]，因此你必须仅为你在支持 PWAs 的任何平台、操作系统和设备组合上安装的 PWA 提供单个 web 应用清单。</span><span class="sxs-lookup"><span data-stu-id="1f077-133">Because it follows a [standards-based schema][W3cWebAppManifest], you must only supply a single web app manifest for the PWA that you are installing on any platform, OS, and device combination that supports PWAs.</span></span>  <span data-ttu-id="1f077-134">在 Windows 生态系统中，你的 web 应用清单向 Bing web app 清单发出通知，表明你的 PWA 是 Microsoft Store 中自动包含的候选 web 索引器，在这种情况下，可能会在 [Microsoft Store][PwaEdgehtmlMicrosoftStore]中将几乎700000000的每月活动用户作为 Windows 10 应用</span><span class="sxs-lookup"><span data-stu-id="1f077-134">In the Windows ecosystem, your web app manifest signals to the Bing web indexer that your PWA is a candidate for automatic inclusion in the [Microsoft Store][PwaEdgehtmlMicrosoftStore], where it may reach nearly 700 million active monthly users as a Windows 10 app.</span></span>  

<span data-ttu-id="1f077-135">如果这是一个现有的实时网站，你可以使用 [PWA 生成器][PwaBuilder]生成 web 应用清单。</span><span class="sxs-lookup"><span data-stu-id="1f077-135">If this were an existing live site, you may generate a web app manifest using [PWA Builder][PwaBuilder].</span></span>  <span data-ttu-id="1f077-136">由于它仍是未发布的项目，因此请复制示例清单。</span><span class="sxs-lookup"><span data-stu-id="1f077-136">Since it is still an unpublished project, copy a sample manifest.</span></span>  

1.  <span data-ttu-id="1f077-137">在 Visual Studio "*解决方案资源管理器*" 中，右键单击*公用*文件夹，然后选择 "**添加**  >  **新文件 ...**"，将 `manifest.json` 其指定为项目名称。</span><span class="sxs-lookup"><span data-stu-id="1f077-137">In the Visual Studio *Solution Explorer*, right-click the *public* folder and select **Add** > **New File...**, specifying `manifest.json` as the item name.</span></span>  
1.  <span data-ttu-id="1f077-138">在 `manifest.json` 文件中，复制以下代码。</span><span class="sxs-lookup"><span data-stu-id="1f077-138">In the `manifest.json` file, copy the following code.</span></span>  

    ```json
    {
        "dir": "ltr",
        "lang": "en-us",
        "name": "My Sample PWA",
        "scope": "/",
        "display": "browser",
        "start_url": "https://PLACEHOLDER-FOR-PWA-URL",
        "short_name": "SamplePWA",
        "theme_color": "transparent",
        "description": "A sample PWA for testing purposes",
        "orientation": "any",
        "background_color": "transparent",
        "related_applications": [],
        "prefer_related_applications": false,
        "icons": []
    }
    ```  
    
    <span data-ttu-id="1f077-139">在真正的 PWA 中，下一步是自定义 *名称*、 *start_url*、 *short_name*、 *说明*和 *图标* \ (图标将在下一步 \ ) 中介绍。</span><span class="sxs-lookup"><span data-stu-id="1f077-139">In a real PWA, the next step is to customize *name*, *start_url*, *short_name*, *description*, and *icons* \(icons are covered in the next step\).</span></span>  
    
    <span data-ttu-id="1f077-140">若要了解有关不同成员值和关联用途的详细信息，请参阅 [Web App 清单][MDNWebAppManifest] 参考。</span><span class="sxs-lookup"><span data-stu-id="1f077-140">To learn more about the different member values and associated purposes, see the [Web App Manifest][MDNWebAppManifest] reference.</span></span>  
    
1.  <span data-ttu-id="1f077-141">接下来， `icons` 使用 PWA 生成器应用图像生成器，使用实际图像路径填充空数组。</span><span class="sxs-lookup"><span data-stu-id="1f077-141">Next, fill in the empty `icons` array with actual image paths by using the PWA Builder App Image Generator.</span></span>  
    
    1.  <span data-ttu-id="1f077-142">使用 web 浏览器，下载此 [示例 512X512 PWA 图像][ImagePwa]。</span><span class="sxs-lookup"><span data-stu-id="1f077-142">Using a web browser, download this [sample 512x512 PWA image][ImagePwa].</span></span>  
    1.  <span data-ttu-id="1f077-143">转到 PWA 生成器 [应用图像生成器][PwaBuilderAppImageGenerator]，选择 `pwa.png` 刚保存为 **输入图像** 的图像，然后选择 " **下载** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="1f077-143">Go to the PWA Builder [App Image Generator][PwaBuilderAppImageGenerator], and select the `pwa.png` image you just saved as the **Input Image** and then choose the **Download** button.</span></span>  
    1.  <span data-ttu-id="1f077-144">**打开** 并 **解压缩** zip 文件。</span><span class="sxs-lookup"><span data-stu-id="1f077-144">**Open** and **Extract** the zip file.</span></span>  
    1.  <span data-ttu-id="1f077-145">在 Visual Studio 的 "解决方案资源管理器" 中，右键单击 `public` 文件夹，然后 **在文件资源管理器中打开文件夹**。</span><span class="sxs-lookup"><span data-stu-id="1f077-145">In the Visual Studio Solution Explorer, right-click the `public` folder and **Open Folder in File Explorer**.</span></span>  <span data-ttu-id="1f077-146">创建一个名为的 **新文件夹** `images` 。</span><span class="sxs-lookup"><span data-stu-id="1f077-146">Create a **New folder** named `images`.</span></span>  
    1.  <span data-ttu-id="1f077-147">将所有平台文件夹 \ (`android` 、、等 `chrome` `windows10` \ ) 从提取的 zip 复制到 `images` 文件夹，然后关闭 "文件资源管理器" 窗口。</span><span class="sxs-lookup"><span data-stu-id="1f077-147">Copy all of the platform folders \(`android`, `chrome`, `windows10`, and so on\) from your extracted zip to the `images` folder and close the file explorer window.</span></span>  <span data-ttu-id="1f077-148">将文件夹添加到 "解决方案资源管理器" 中的 Visual Studio 项目 \ (中，右键单击 `images` "文件夹"，然后选择 "**添加**  >  **现有文件夹 ...** "，为每个文件夹 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="1f077-148">Add the folders to your Visual Studio project \(in Solution Explorer, right-click `images` folder and select **Add** > **Existing folder...** for each of the folders\).</span></span>  
    1.  <span data-ttu-id="1f077-149">在 Visual Studio 或任何编辑器 \ ) 中打开 \ (`icons.json` 来自提取的 zip 的文件，并将该 `"icons": [...]` 数组复制到 `manifest.json` 项目文件中。</span><span class="sxs-lookup"><span data-stu-id="1f077-149">Open \(with Visual Studio or any editor\) the `icons.json` file from the extracted zip and copy the `"icons": [...]` array into the `manifest.json` file of your project.</span></span>  

1.  <span data-ttu-id="1f077-150">现在，你必须将 web 应用清单与你的应用相关联。</span><span class="sxs-lookup"><span data-stu-id="1f077-150">Now you must associate your web app manifest with your app.</span></span>  <span data-ttu-id="1f077-151">打开 " `layout.pug` 文件 \ (" `views` 文件夹 \ ) 中的 "编辑"，然后在 "样式表" 链接后立即添加此行。</span><span class="sxs-lookup"><span data-stu-id="1f077-151">Open the `layout.pug` file \(in `views` folder\) for editing, and add this line right after the stylesheet link.</span></span>  <span data-ttu-id="1f077-152">\ (只是节点 [pug][PugAttributes] 模板的简写形式 `<link rel='manifest' href='/manifest.json'>` \ ) 。</span><span class="sxs-lookup"><span data-stu-id="1f077-152">\(It is simply the Node [pug][PugAttributes] template shorthand for `<link rel='manifest' href='/manifest.json'>`\).</span></span>  
    
    ```html
    link(rel='manifest', href='/manifest.json')
    ```  
    
<span data-ttu-id="1f077-153">使用所有这些功能，你的 web 应用现在正在提供清单和主屏幕应用图标！</span><span class="sxs-lookup"><span data-stu-id="1f077-153">With all that in place, your web app is now serving up a manifest and homescreen-ready app icons!</span></span>  <span data-ttu-id="1f077-154">尝试运行你的应用 \ (`F5` \ ) 并加载清单。</span><span class="sxs-lookup"><span data-stu-id="1f077-154">Try running your app \(`F5`\) and loading up the manifest.</span></span>  

![从 localhost 加载的 Web 应用清单][ImageVsNodejsExpressManifest]  

<span data-ttu-id="1f077-156">和其中一个图标。</span><span class="sxs-lookup"><span data-stu-id="1f077-156">And one of your icons.</span></span>  

![从 localhost 加载的 Square71x71Logo 应用徽标][ImageVsNodejsExpressIcon]  

<span data-ttu-id="1f077-158">如果你使用实际的 \ ) 发布应用 live \ (`start_url` ，必应搜索引擎现在将其标识为对 [Microsoft Store 进行自动打包和提交][PwaEdgehtmlMicrosoftStore] 的候选项，作为可安装的 Windows 10 应用。</span><span class="sxs-lookup"><span data-stu-id="1f077-158">If you publish the app live \(with an actual `start_url`\), the Bing search engine now identifies it as a candidate for [automatic packaging and submission to the Microsoft Store][PwaEdgehtmlMicrosoftStore] as an installable Windows 10 app.</span></span>  <span data-ttu-id="1f077-159">确保 manifest.js"文件" 包含 [用于累进 Web 应用的质量信号][WindowsBlogsPwaEdge] ，其中包含以下各项的必应扫描。</span><span class="sxs-lookup"><span data-stu-id="1f077-159">Ensure that your manifest.json file includes the [Quality signals for Progressive Web Apps][WindowsBlogsPwaEdge] for which Bing scans including the following items.</span></span>   

*   `name`  
*   `description`  
*   <span data-ttu-id="1f077-160">至少有一个图标512px 方形或更大的 \ (，以确保图像来源能够自动生成应用的初始屏幕、应用商店列表、磁贴图像等 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="1f077-160">At least one icon 512px square or larger \(to ensure an image source of sufficient resolution for auto-generating the splash screen of your app, store listing, tile image, and so on\).</span></span>  

<span data-ttu-id="1f077-161">此外，使用 [HTTPS](#https)、 [服务工作者](#service-workers)以及遵守 [Microsoft Store 策略][LegalWindowsAgrementsMicrosoftStorePolicies]。</span><span class="sxs-lookup"><span data-stu-id="1f077-161">In addition, use [HTTPS](#https), [service workers](#service-workers), and comply with [Microsoft Store Policies][LegalWindowsAgrementsMicrosoftStorePolicies].</span></span>  

### <span data-ttu-id="1f077-162">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1f077-162">HTTPS</span></span>  

<span data-ttu-id="1f077-163">适用于服务工作者的[服务工作人员][MDNServiceWorkerApi]和其他关键 PWA 技术 (例如[缓存][MDNCache]、[推送][MDNPushApi]和[后台同步][MDNSyncManager]api \ ) 仅在安全连接中工作，这意味着用于实时网站或调试的[HTTPS][WikiHttps] `localhost` 。</span><span class="sxs-lookup"><span data-stu-id="1f077-163">[Service Workers][MDNServiceWorkerApi] and other key PWA technologies that work with service workers \(such as the [Cache][MDNCache], [Push][MDNPushApi], and [Background Sync][MDNSyncManager] APIs\) only work across secure connections, which means [HTTPS][WikiHttps] for live sites or `localhost` for debugging purposes.</span></span>  

<span data-ttu-id="1f077-164">如果将 [此 web 应用发布为活动网站][VisualStudioNodejsTutorialPublishAzureAppService] \ (例如，通过设置 [Azure 免费帐户][AzureCreateFreeAccount]\ ) ，必须确保服务器配置了 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="1f077-164">If you [publish this web app as a live site][VisualStudioNodejsTutorialPublishAzureAppService] \(for example, by setting up an [Azure free account][AzureCreateFreeAccount]\), you must ensure your server is configured for HTTPS.</span></span>  <span data-ttu-id="1f077-165">如果你使用 [Microsoft Azure 应用服务][AzureWebApps] 托管你的网站，则默认情况下它将通过 HTTPS 进行提供。</span><span class="sxs-lookup"><span data-stu-id="1f077-165">If you use the [Microsoft Azure App Service][AzureWebApps] to host your site, it is served over HTTPS by default.</span></span>  

<span data-ttu-id="1f077-166">对于本指南，请继续 `http://localhost` 将用作提供服务的活动网站的占位符 `https://` 。</span><span class="sxs-lookup"><span data-stu-id="1f077-166">For this guide, continue using `http://localhost` as a placeholder for a live site served over `https://`.</span></span>  

### <span data-ttu-id="1f077-167">服务工作进程</span><span class="sxs-lookup"><span data-stu-id="1f077-167">Service Workers</span></span>  

<span data-ttu-id="1f077-168">服务工作者是 PWAs 背后的关键技术。</span><span class="sxs-lookup"><span data-stu-id="1f077-168">Service Workers is the key technology behind PWAs.</span></span> <span data-ttu-id="1f077-169">服务工作人员充当你的 PWA 和网络之间的代理，使你的网站能够充当服务于脱机方案的已安装本机应用，响应服务器推送通知，并运行后台任务。</span><span class="sxs-lookup"><span data-stu-id="1f077-169">Service Workers act as a proxy between your PWA and the network to enable your website to function as an installed native app that serves up offline scenarios, responds to server push notifications, and runs background tasks.</span></span>  <span data-ttu-id="1f077-170">服务工作者还会打开新的性能策略。</span><span class="sxs-lookup"><span data-stu-id="1f077-170">Service workers also open up new performance strategies.</span></span>  <span data-ttu-id="1f077-171">你无需实现完整的 web 应用，即可为你的网站使用服务工作人员缓存来优化页面加载性能。</span><span class="sxs-lookup"><span data-stu-id="1f077-171">You are not required to implement a full web app to use the service worker cache for fine-tuned page load performance for your website.</span></span>  

<span data-ttu-id="1f077-172">服务工作线程是由 JavaScript 文件运行的事件驱动的后台线程，这些线程与为 web 应用供电的常规脚本一起提供。</span><span class="sxs-lookup"><span data-stu-id="1f077-172">Service workers are event-driven background threads that run from JavaScript files served up alongside the regular scripts that power your web app.</span></span>  <span data-ttu-id="1f077-173">由于服务工作人员不在主 UI 线程上运行，因此服务工作人员不具有 DOM 访问权限，尽管 [UI 线程][MDNWorkerPrototypePostMessage] 和 [工作线程][MDNDedicatedWorkerGlobalScopePostMessage] 能够使用 `postMessage()` 和 `onmessage` 事件处理程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="1f077-173">Because Service workers do not run on the main UI thread, service workers do not have DOM access, though the [UI thread][MDNWorkerPrototypePostMessage] and a [worker thread][MDNDedicatedWorkerGlobalScopePostMessage] is able to communicate using `postMessage()` and `onmessage` event handlers.</span></span>  

<span data-ttu-id="1f077-174">将服务工作者注册到你的应用，方法是将其注册到你的网站 \ (的 URL 来源或在其中 ) 中指定的路径。</span><span class="sxs-lookup"><span data-stu-id="1f077-174">You associate a service worker with your app by registering it to the URL origin of your site \(or a specified path within it\).</span></span>  <span data-ttu-id="1f077-175">注册后，将在用户计算机上下载、安装和激活服务工作人员文件。</span><span class="sxs-lookup"><span data-stu-id="1f077-175">Once registered, the service worker file is then downloaded, installed, and activated on the user machine.</span></span>  <span data-ttu-id="1f077-176">有关详细信息，MDN web 文档提供了有关 [使用服务工作人员][MDNUsingServiceWorkers] 和详细的 [服务工作者 API][MDNServiceWorkerApi] 参考的综合指南。</span><span class="sxs-lookup"><span data-stu-id="1f077-176">For more, MDN web docs has a comprehensive guide on [Using Service Workers][MDNUsingServiceWorkers] and a detailed [Service Worker API][MDNServiceWorkerApi] reference.</span></span>  

<span data-ttu-id="1f077-177">对于本教程，请使用 [PWA 生成器][PwaBuilderServiceWorker]上的脱机页面服务工作脚本。</span><span class="sxs-lookup"><span data-stu-id="1f077-177">For this tutorial, use the Offline page service worker script on [PWA Builder][PwaBuilderServiceWorker].</span></span>  <span data-ttu-id="1f077-178">开始自定义具有更多功能的脚本，具体取决于你的性能要求、网络带宽等。</span><span class="sxs-lookup"><span data-stu-id="1f077-178">Start by customizing the script with more functionality according to your performance requirements, network bandwidth, and so on.</span></span>  <span data-ttu-id="1f077-179">查看由 Mozilla 提供的 [服务工作人员手册][ServiceWorkerCookbook]  ，了解许多有用的服务工作人员缓存创意。</span><span class="sxs-lookup"><span data-stu-id="1f077-179">Review the [Service Worker Cookbook][ServiceWorkerCookbook]  provided by Mozilla for a number of useful service worker caching ideas.</span></span>  

1.  <span data-ttu-id="1f077-180">打开 [https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker] 并选择 \ (默认 \ ) **脱机页面** 服务工作人员，然后单击 " **下载服务辅助角色** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="1f077-180">Open [https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker] and select the \(default\) **Offline page** service worker and click the **Download service worker** button.</span></span>  
1.  <span data-ttu-id="1f077-181">打开下载文件夹并复制以下两个文件</span><span class="sxs-lookup"><span data-stu-id="1f077-181">Open the download folder and copy the following two files</span></span>  

    *   <span data-ttu-id="1f077-182">ServiceWorker1\pwabuilder-sw-register.js</span><span class="sxs-lookup"><span data-stu-id="1f077-182">ServiceWorker1\pwabuilder-sw-register.js</span></span>  
    *   <span data-ttu-id="1f077-183">ServiceWorker1\pwabuilder-sw.js</span><span class="sxs-lookup"><span data-stu-id="1f077-183">ServiceWorker1\pwabuilder-sw.js</span></span>  
    
    <span data-ttu-id="1f077-184">将文件保存到 `public` Visual Studio web app 项目的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1f077-184">Save the files to the `public` folder of your Visual Studio web app project.</span></span>  <span data-ttu-id="1f077-185">\ (从 Visual Studio 中，使用 `Ctrl` + `O` 将文件资源管理器打开到项目并导航到 `public` 文件夹 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="1f077-185">\(From Visual Studio, use `Ctrl`+`O` to open file explorer to your project and navigate to the `public` folder\).</span></span>  
    
    <span data-ttu-id="1f077-186">在 "解决方案资源管理器" 中，打开 `public/pwabuilder-sw.js` 文件，然后将的值更改 `offlineFallbackPage` 为 `offline.html` 。</span><span class="sxs-lookup"><span data-stu-id="1f077-186">In Solution Explorer, open the `public/pwabuilder-sw.js` file, and change the value of `offlineFallbackPage` to `offline.html`.</span></span>  
    
    ```javascript
    const offlineFallbackPage = "offline.html";
    ```
    
    <span data-ttu-id="1f077-187">有必要查看这两个文件中的代码，以获取有关如何注册 () 的服务工作人员 `offline.html` 并在网络获取失败时提供服务的 gist。</span><span class="sxs-lookup"><span data-stu-id="1f077-187">It is worth reviewing the code in both of these files, to get the gist of how to register a service worker that caches a designated page \(`offline.html`\) and serves it when a network fetch fails.</span></span>  <span data-ttu-id="1f077-188">接下来，创建一个简单 `offline.html` 页面作为应用的脱机功能的占位符。</span><span class="sxs-lookup"><span data-stu-id="1f077-188">Next, create a simple `offline.html` page as a placeholder for the offline functionality of your app.</span></span>  
    
1.  <span data-ttu-id="1f077-189">在 "解决方案资源管理器" 中，打开 `views/layout.pug` 文件，然后在链接标记下方添加以下行。</span><span class="sxs-lookup"><span data-stu-id="1f077-189">In Solution Explorer, open the `views/layout.pug` file, and add the following line below your link tags.</span></span>  
    
    ```html
    script(src='/pwabuilder-sw-register.js' type='module')
    ```  
    
    <span data-ttu-id="1f077-190">你的网站将加载并运行你的服务工作人员注册脚本。</span><span class="sxs-lookup"><span data-stu-id="1f077-190">Your site loads and runs your service worker registration script.</span></span>  
    
1.  <span data-ttu-id="1f077-191">在 "解决方案资源管理器" 中，右键单击该 `public` 文件夹，然后选择 "**添加**  >  **新文件 ...**"。 为其命名 `offline.html` ，然后添加一个 `<title>` 和部分正文内容，例如以下代码。</span><span class="sxs-lookup"><span data-stu-id="1f077-191">In Solution Explorer, right-click on the `public` folder and select **Add** > **New File...**.  Name it `offline.html`, and add a `<title>` and some body content, for example the following code.</span></span>  
    
    ```html
    <!DOCTYPE html>
    
    <html xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <meta charset="utf-8" />
        <title>Offline mode</title>
    </head>
    <body>
        You are now offline.
    </body>
    </html>
    ```  
    
    <span data-ttu-id="1f077-192">此时，你的 `public` 文件夹应具有三个新文件。</span><span class="sxs-lookup"><span data-stu-id="1f077-192">At this point, your `public` folder should have three new files.</span></span>  
    
    ![添加到解决方案的公用文件夹的文件][ImageVsNodejsExpressPublic]  
    
1.  <span data-ttu-id="1f077-194">在 "解决方案资源管理器" 中，打开 `routes\index.js` 文件，然后在最后一个命令 \ (\ ) 之前添加以下代码 `module.exports = router;` 。</span><span class="sxs-lookup"><span data-stu-id="1f077-194">In Solution Explorer, open the `routes\index.js` file, and add the following code just before the final command \(`module.exports = router;`\).</span></span>  
    
    ```javascript
    router.get('/offline.html', function (req, res) {
        res.sendFile('public/offline.html');
    });
    ```  
    
    <span data-ttu-id="1f077-195">这会指示你的应用 `offline.html` 在你的服务工作人员为脱机缓存 \ ) 获取文件时为该文件提供服务 (。</span><span class="sxs-lookup"><span data-stu-id="1f077-195">This instructs your app to serve the `offline.html` file \(when your service worker fetches it for the offline cache\).</span></span>  
    
1.  <span data-ttu-id="1f077-196">测试你的 PWA！</span><span class="sxs-lookup"><span data-stu-id="1f077-196">Test out your PWA!</span></span>  <span data-ttu-id="1f077-197">生成 \ (`Ctrl` + `Shift` + `B` \ ) 并运行 \ (`F5` \ ) web 应用启动 Microsoft Edge 并打开您的 `localhost` 页面。</span><span class="sxs-lookup"><span data-stu-id="1f077-197">Build \(`Ctrl`+`Shift`+`B`\) and Run \(`F5`\) your web app to launch Microsoft Edge and open your `localhost` page.</span></span>  <span data-ttu-id="1f077-198">然后完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1f077-198">Then complete the following steps.</span></span>  
    
    1.  <span data-ttu-id="1f077-199">打开边缘 DevTools**控制台**\ (`Ctrl` + `Shift` + `J` \ ) 并验证服务工作人员是否已注册。</span><span class="sxs-lookup"><span data-stu-id="1f077-199">Open the Edge DevTools **Console** \(`Ctrl`+`Shift`+`J`\) and verify the Service worker was registered.</span></span>  
    1.  <span data-ttu-id="1f077-200">在 " **调试器** " 面板中，展开 " **服务工作者** " 控件，然后单击您的来源。</span><span class="sxs-lookup"><span data-stu-id="1f077-200">In the **Debugger** panel, expand the **Service Workers** control and click on your origin.</span></span>  <span data-ttu-id="1f077-201">在 " **服务工作人员概述**" 中，验证你的服务工作人员是否已激活并在运行。</span><span class="sxs-lookup"><span data-stu-id="1f077-201">In the **Service Worker Overview**, verify your service worker is activated and running.</span></span>  
        
        ![Edge DevTools 服务工作者概览][ImageDevtoolsSwOverview]  
        
    1.  <span data-ttu-id="1f077-203">展开 **缓存** 控件并验证 `offline.html` 页面是否已缓存。</span><span class="sxs-lookup"><span data-stu-id="1f077-203">Expand the **Cache** control and verify that the `offline.html` page is cached.</span></span>  
        
        ![Edge DevTools 服务辅助缓存][ImageDevtoolsSwCache]  
        
1.  <span data-ttu-id="1f077-205">尝试将 PWA 作为脱机应用的时间！</span><span class="sxs-lookup"><span data-stu-id="1f077-205">Time to try your PWA as an offline app!</span></span>  <span data-ttu-id="1f077-206">在 Visual Studio 中，**停止调试**\ (`Shift` + `F5` \ ) 你的 web 应用，然后打开 Microsoft Edge \ (或将 \ ) 刷新到你的网站的本地主机地址。</span><span class="sxs-lookup"><span data-stu-id="1f077-206">In Visual Studio, **Stop Debugging** \(`Shift`+`F5`\) your web app, then open Microsoft Edge \(or refresh\) to the localhost address of your website.</span></span>  <span data-ttu-id="1f077-207">`offline.html`由于您的服务工作人员和脱机缓存 \ ) ，它现在应加载页面 \ (！</span><span class="sxs-lookup"><span data-stu-id="1f077-207">It should now load the `offline.html` page \(thanks to your service worker and offline cache\)!</span></span>  
    
    ![http://localhost:1337在 Microsoft Edge 中加载 offline.html][ImageOfflineHtml]  

## <span data-ttu-id="1f077-209">添加推送通知</span><span class="sxs-lookup"><span data-stu-id="1f077-209">Add push notifications</span></span>  

<span data-ttu-id="1f077-210">通过添加推送通知的客户端支持（使用 [推送 api][MDNPushApi] 订阅消息服务和 [通知 API][MDNNotificationsApi] 在接收消息时显示 toast 消息），让 PWA 更多应用。</span><span class="sxs-lookup"><span data-stu-id="1f077-210">Make your PWA more app-like by adding client-side support for push notifications using the [Push API][MDNPushApi] to subscribe to a messaging service and the [Notifications API][MDNNotificationsApi] to display a toast message upon receiving a message.</span></span>  <span data-ttu-id="1f077-211">与服务工作者一样，这些是基于标准的 Api，可跨浏览器使用，因此你只需编写一次代码即可在任何支持 PWAs 的地方工作。</span><span class="sxs-lookup"><span data-stu-id="1f077-211">As with Service Workers, these are standards-based APIs that work cross-browser, so you only have to write the code once for it to work everywhere PWAs are supported.</span></span>  <span data-ttu-id="1f077-212">在服务器端，使用 [Web 推送][NPMWebPush] 开放源代码库来处理向各种浏览器传递推送消息时所涉及的差异。</span><span class="sxs-lookup"><span data-stu-id="1f077-212">On the server side, use the [Web-Push][NPMWebPush] open-source library to handle the differences involved in delivering push messages to various browsers.</span></span>  

<span data-ttu-id="1f077-213">以下各项适用于由 Mozilla 提供的 [服务工作人员手册][ServiceWorkerCookbookPushRichDemo] 中的 "推入大量演示"，它值得检查一下许多其他有用的 Web 推送和服务工作者食谱。</span><span class="sxs-lookup"><span data-stu-id="1f077-213">The following is adapted from the Push Rich Demo in [Service Worker Cookbook][ServiceWorkerCookbookPushRichDemo] provided by Mozilla, which is worth checking out for a number of other useful Web Push and service worker recipes.</span></span>  

### <span data-ttu-id="1f077-214">步骤 1-安装 NPM web 推送库</span><span class="sxs-lookup"><span data-stu-id="1f077-214">Step 1 - Install the NPM web-push library</span></span>  

<span data-ttu-id="1f077-215">在 Visual Studio "解决方案资源管理器" 中，右键单击你的项目，然后 **打开 Node.js 交互式窗口 ...**"。 在其中键入以下代码。</span><span class="sxs-lookup"><span data-stu-id="1f077-215">In Visual Studio Solution Explorer, right-click your project and **Open Node.js Interactive Window...**.  In it, type the following code.</span></span>  

```javascript
.npm install web-push
```  

<span data-ttu-id="1f077-216">这将安装 [Web 推送][NPMWebPush] 库。</span><span class="sxs-lookup"><span data-stu-id="1f077-216">This installs the [Web-Push][NPMWebPush] library.</span></span>  <span data-ttu-id="1f077-217">然后，打开 `index.js` 文件，并在其他要求语句后将以下行添加到文件顶部。</span><span class="sxs-lookup"><span data-stu-id="1f077-217">Then, open up your `index.js` file, and add the following line to the top of your file after the other requirement statements.</span></span>  

```javascript
var webpush = require('web-push');
```  

### <span data-ttu-id="1f077-218">步骤 2-为服务器生成 VAPID 项</span><span class="sxs-lookup"><span data-stu-id="1f077-218">Step 2 - Generate VAPID keys for your server</span></span>  

<span data-ttu-id="1f077-219">接下来，你必须生成 VAPID \ (自愿应用服务器标识 \ ) 密钥，以便你的服务器向 PWA 客户端发送推送消息。</span><span class="sxs-lookup"><span data-stu-id="1f077-219">Next you must generate VAPID \(Voluntary Application Server Identification\) keys for your server to send push messages to the PWA client.</span></span>  <span data-ttu-id="1f077-220">您只需执行 (此操作，即您的服务器只需要 VAPID 的一对键 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="1f077-220">You only have to do this once \(that is, your server only requires a single pair of VAPID keys\).</span></span>  <span data-ttu-id="1f077-221">在 Node.js 交互式窗口中，键入以下代码。</span><span class="sxs-lookup"><span data-stu-id="1f077-221">In the Node.js Interactive Window, type the following code.</span></span>  

```javascript
var webpush = require('web-push');
webpush.generateVAPIDKeys();
```  

<span data-ttu-id="1f077-222">输出应产生一个包含公钥和私钥的 JSON 对象，该对象将复制到你的服务器逻辑中。</span><span class="sxs-lookup"><span data-stu-id="1f077-222">The output should result in a JSON object containing a public and private key, which you copy into your server logic.</span></span>  

<span data-ttu-id="1f077-223">在 `index.js` 文件中，在最后的 \ (`module.exports = router` \ ) 行之前，添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="1f077-223">In your `index.js` file, just before the final  \(`module.exports = router`\) line, add the following code.</span></span>  

```javascript
const vapidKeys = {
    publicKey: '',
    privateKey: ''
};

webpush.setVapidDetails(
    'mailto:pwa@example.com',
    vapidKeys.publicKey,
    vapidKeys.privateKey
);
```  

<span data-ttu-id="1f077-224">复制 `publicKey` `privateKey` 您刚生成的和值。</span><span class="sxs-lookup"><span data-stu-id="1f077-224">Copy the `publicKey` and `privateKey` values that you just generated.</span></span>  <span data-ttu-id="1f077-225">如果 `mailto` 不需要运行此示例 \ ) ，请随意自定义地址和 \ (。</span><span class="sxs-lookup"><span data-stu-id="1f077-225">Feel free to customize the `mailto` address as well \(though it is not required in order to run this sample\).</span></span>  

<span data-ttu-id="1f077-226">如果你对 VAPID 和 WebPush 的工作原理的详细信息感兴趣，则 [Mozilla Services 工程博客][MozillaServicesSendingVapidWebPushNotificationsPush] 对和有很好的 explainer。</span><span class="sxs-lookup"><span data-stu-id="1f077-226">The [Mozilla Services engineering blog][MozillaServicesSendingVapidWebPushNotificationsPush] has a nice explainer on VAPID and WebPush if you are interested in the details of how it works behind the scenes.</span></span>  

### <span data-ttu-id="1f077-227">步骤 3-处理与推送相关的服务器请求</span><span class="sxs-lookup"><span data-stu-id="1f077-227">Step 3 - Handle push-related server requests</span></span>  

<span data-ttu-id="1f077-228">现在设置用于处理来自 PWA 客户端的推送相关请求的路由，包括提供 VAPID 公钥和注册客户端以接收推送。</span><span class="sxs-lookup"><span data-stu-id="1f077-228">Now set up routes for handling push-related requests from the PWA client, including serving up the VAPID public key and registering the client to receive pushes.</span></span>  

<span data-ttu-id="1f077-229">在实际方案中，推送通知可能源自服务器逻辑中的事件。</span><span class="sxs-lookup"><span data-stu-id="1f077-229">In a real scenario, a push notification likely originates from an event in your server logic.</span></span>  <span data-ttu-id="1f077-230">若要简化此处的操作，必须向 PWA 主页添加 " **推送通知** " 按钮，以便从我们的服务器生成推送，以及 `/sendNotification` 用于处理这些请求的终结点 \ (服务器路由 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="1f077-230">To simplify things here, you must add a **Push Notification** button to our PWA homepage for generating pushes from our server, and a `/sendNotification` endpoint \(server route\)for handling those requests.</span></span>  

<span data-ttu-id="1f077-231">在你的 `index.js` 文件中，在 [步骤 2] [#step-2 中添加的 VAPID 初始化代码后，附加以下路由，---生成-VAPID--------------服务器]。</span><span class="sxs-lookup"><span data-stu-id="1f077-231">In your `index.js` file, append the following routes just after the VAPID initialization code you added in [Step 2][#step-2---generate-vapid-keys-for-your-server].</span></span>  

```javascript
router.get('/vapidPublicKey', function (req, res) {
    res.send(vapidKeys.publicKey);
});

router.post('/register', function (req, res) {
    // A real world application stores the subscription info.
    res.sendStatus(201);
});

router.post('/sendNotification', function (req, res) {
    const subscription = req.body.subscription;
    const payload = 'payload';
    const options = null;
    
    webpush.sendNotification(subscription, payload, options)
        .then(function () {
            res.sendStatus(201);
        })
        .catch(function (error) {
            res.sendStatus(500);
            console.log(error);
        });
});
```  

<span data-ttu-id="1f077-232">在 plumb 服务器端代码的情况下，在 PWA 客户端上的推送通知中进行。</span><span class="sxs-lookup"><span data-stu-id="1f077-232">With the server-side code in place, plumb in push notifications on the PWA client.</span></span>  

### <span data-ttu-id="1f077-233">步骤 4-订阅推送通知</span><span class="sxs-lookup"><span data-stu-id="1f077-233">Step 4 - Subscribe to push notifications</span></span>  

<span data-ttu-id="1f077-234">作为 PWA 网络代理的角色的一部分，服务工作者处理推送事件和 toast 通知交互。</span><span class="sxs-lookup"><span data-stu-id="1f077-234">As part of their role as PWA network proxies, service workers handle push events and toast notification interactions.</span></span>  <span data-ttu-id="1f077-235">但是，与首次设置 \ (或注册 \ ) 服务工作人员一样，在 PWA 的主 UI 线程上将 PWA 订阅到服务器推送通知，并且需要网络连接。</span><span class="sxs-lookup"><span data-stu-id="1f077-235">However, as it is with first setting up \(or registering\) a service worker, subscribing the PWA to server push notifications happens on the main UI thread of the PWA and requires network connectivity.</span></span>  <span data-ttu-id="1f077-236">订阅推送通知需要活动的服务工作人员注册，因此必须首先验证服务工作人员是否已安装并处于活动状态，然后再尝试将其订阅到推送通知。</span><span class="sxs-lookup"><span data-stu-id="1f077-236">Subscribing to push notifications requires an active service worker registration, so you must first verify that your service worker is installed and active before trying to subscribe it to push notifications.</span></span>  

<span data-ttu-id="1f077-237">在创建新推送订阅之前，Microsoft Edge 检查用户是否授予了 PWA 接收通知的权限。</span><span class="sxs-lookup"><span data-stu-id="1f077-237">Before a new push subscription is created, Microsoft Edge check if the user granted the PWA permission to receive notifications.</span></span>  <span data-ttu-id="1f077-238">如果不是，则浏览器会提示用户提供权限。</span><span class="sxs-lookup"><span data-stu-id="1f077-238">If not, the user is prompted by the browser for permission.</span></span>  <span data-ttu-id="1f077-239">如果权限被拒绝，则请求 `registration.pushManager.subscribe` 引发 a `DOMException` ，因此你必须处理它。</span><span class="sxs-lookup"><span data-stu-id="1f077-239">If the permission is denied, the request to `registration.pushManager.subscribe` throws a `DOMException`, so you must handle it.</span></span>  <span data-ttu-id="1f077-240">有关权限管理的详细信息，请参阅 [Microsoft Edge 中的推送通知][WindowsBlogsWebNotificationsEdge]。</span><span class="sxs-lookup"><span data-stu-id="1f077-240">For more on permission management, see [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span></span>  

<span data-ttu-id="1f077-241">在 `pwabuilder-sw-register.js` 文件中，附加以下代码。</span><span class="sxs-lookup"><span data-stu-id="1f077-241">In your `pwabuilder-sw-register.js` file, append the following code.</span></span>  

```javascript
// Subscribe this PWA to push notifications from the server
navigator.serviceWorker.ready
    .then(function (registration) {
        // Check if the user has an existing subscription
        return registration.pushManager.getSubscription()
            .then(async function (subscription) {
                if (subscription) {
                    return subscription;
                }
                
                // Otherwise subscribe with the server public key
                const response = await fetch('./vapidPublicKey');
                const vapidPublicKey = await response.text();
                const convertedVapidKey = urlBase64ToUint8Array(vapidPublicKey);
                
                return registration.pushManager.subscribe({
                    userVisibleOnly: true,
                    applicationServerKey: convertedVapidKey
                });
            });
    }).then(function (subscription) {
        // Send the subscription details to the server
        fetch('./register', {
            method: 'post',
            headers: {
                'Content-type': 'application/json'
            },
            body: JSON.stringify({
                subscription: subscription
            }),
        });
        
        // Create a button to mimic server pushes for testing purposes
        var button = document.createElement('input');
        button.type = 'button';
        button.id = 'notify';
        button.value = 'Send Notification';
        document.body.appendChild(button);
        document.getElementById('notify').addEventListener('click', function () {
            fetch('./sendNotification', {
                method: 'post',
                headers: {
                    'Content-type': 'application/json'
                },
                body: JSON.stringify({
                    subscription: subscription
                }),
            });
        });
    });

// Utility function for browser interoperability
function urlBase64ToUint8Array(base64String) {
    var padding = '='.repeat((4 - base64String.length % 4) % 4);
    var base64 = (base64String + padding)
        .replace(/\-/g, '+')
        .replace(/_/g, '/');
        
    var rawData = window.atob(base64);
    var outputArray = new Uint8Array(rawData.length);
    
    for (var i = 0; i < rawData.length; ++i) {
        outputArray[i] = rawData.charCodeAt(i);
    }
    return outputArray;
}
```  

<span data-ttu-id="1f077-242">查看 [PushManager][MDNPushManager] 界面上的 MDN 文档和 [Web 推送][NPMWebPushUsage] 库上的 NPM 文档，以了解有关 api 如何工作以及各种相关选项的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1f077-242">Review the MDN documentation on the [PushManager][MDNPushManager] interface and NPM docs on the [Web-Push][NPMWebPushUsage] library for more details on how the APIs work and various related options.</span></span>  

### <span data-ttu-id="1f077-243">步骤 5-设置推送和 notificationclick 事件处理程序</span><span class="sxs-lookup"><span data-stu-id="1f077-243">Step 5 - Set up push and notificationclick event handlers</span></span>  

<span data-ttu-id="1f077-244">设置了推送套餐后，剩余的工作将在服务工作人员中发生。</span><span class="sxs-lookup"><span data-stu-id="1f077-244">With our push subscription set up, the remainder of the work happens in the service worker.</span></span>  <span data-ttu-id="1f077-245">首先，你必须为服务器发送的推送事件设置处理程序，并使用 toast 通知 \ (（如果授予权限）进行响应 \ ) 显示推送数据负载。</span><span class="sxs-lookup"><span data-stu-id="1f077-245">First you must set up a handler for server-sent push events, and respond with a toast notification \(if permission was granted\) displaying the push data payload.</span></span>  <span data-ttu-id="1f077-246">接下来，为 toast 添加单击处理程序以关闭通知，并对当前打开的窗口的列表进行排序，以打开、焦点或打开所需的 PWA 客户端页面并对其进行焦点。</span><span class="sxs-lookup"><span data-stu-id="1f077-246">Next you add a click handler for the toast to dismiss the notification and sort through a list of currently open windows to open, focus, or open and focus the intended PWA client page.</span></span>  

<span data-ttu-id="1f077-247">在 `pwabuilder-sw.js` 文件中，附加以下处理程序。</span><span class="sxs-lookup"><span data-stu-id="1f077-247">In your `pwabuilder-sw.js` file, append the following handlers.</span></span>  

```javascript
//Respond to a server push with a user notification
self.addEventListener('push', function (event) {
    if ("granted" === Notification.permission) {
        var payload = event.data ? event.data.text() : 'no payload';
        const promiseChain = self.registration.showNotification('Sample PWA', {
            body: payload,
            icon: 'images/windows10/Square44x44Logo.scale-100.png'
        });
        //Ensure the toast notification is displayed before exiting this function
        event.waitUntil(promiseChain);
    }
});
    
//Respond to the user clicking the toast notification
self.addEventListener('notificationclick', function (event) {
    console.log('On notification click: ', event.notification.tag);
    event.notification.close();
    
    // This looks to see if the current is already open and focuses it
    event.waitUntil(clients.matchAll({
        type: 'window'
    }).then(function (clientList) {
        for (var i = 0; i < clientList.length; i++) {
            var client = clientList[i];
            if (client.url == 'http://localhost:1337/' && 'focus' in client)
                return client.focus();
        }
        if (clients.openWindow)
            return clients.openWindow('/');
    }));
});
```  

### <span data-ttu-id="1f077-248">步骤 6-试用</span><span class="sxs-lookup"><span data-stu-id="1f077-248">Step 6 - Try it out</span></span>  

<span data-ttu-id="1f077-249">在 PWA 中测试推送通知的时间！</span><span class="sxs-lookup"><span data-stu-id="1f077-249">Time to test push notifications in your PWA!</span></span>  

1.  <span data-ttu-id="1f077-250">`F5`在浏览器中运行 \ (\ ) PWA。</span><span class="sxs-lookup"><span data-stu-id="1f077-250">Run \(`F5`\) your PWA in the browser.</span></span>  <span data-ttu-id="1f077-251">由于你已修改了服务工作人员代码 \ (`pwabuilder-sw.js` \ ) ，因此必须打开 DevTools 调试程序 \ (`F12` \ ) 到 **服务工作人员概述** 面板，并 **注销** 服务工作人员并重新加载 \ (\ ) 将 `F5` 其重新注册，然后单击 " **更新**\ ("。</span><span class="sxs-lookup"><span data-stu-id="1f077-251">Because you modified the service worker code \(`pwabuilder-sw.js`\), you must open the DevTools Debugger \(`F12`\) to the **Service Worker Overview** panel and **Unregister** the service worker and reload \(`F5`\) the page to re-register it \(or you click **Update**\).</span></span>  <span data-ttu-id="1f077-252">在生产方案中，浏览器将定期检查服务工作人员更新并在后台安装更新。</span><span class="sxs-lookup"><span data-stu-id="1f077-252">In a production scenario, the browser checks regularly check for service worker updates and install the updates in the background.</span></span>  <span data-ttu-id="1f077-253">应在此处强制执行立即结果。</span><span class="sxs-lookup"><span data-stu-id="1f077-253">You should force it here for immediate results.</span></span>  
    
    <span data-ttu-id="1f077-254">当你的服务工作者激活并尝试将你的 PWA 订阅到推送通知时，你应该会在页面底部看到一个权限对话框。</span><span class="sxs-lookup"><span data-stu-id="1f077-254">As your service worker activates and attempts to subscribe your PWA to push notifications, you should see a permission dialog at the bottom of the page.</span></span>  
    
    ![用于启用通知的权限对话框][ImageNotificationPermission]  
    
    <span data-ttu-id="1f077-256">选择 **"是"** 为你的 PWA 启用 toast 通知。</span><span class="sxs-lookup"><span data-stu-id="1f077-256">Choose **Yes** to enable toast notifications for your PWA.</span></span>  
    
1.  <span data-ttu-id="1f077-257">在 "服务工作人员概述" 窗格中，尝试选择 "  **下压** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="1f077-257">From the Service Worker Overview pane, try choosing the  **Push** button.</span></span>  <span data-ttu-id="1f077-258">将显示一个 toast 通知，其中包含 \ (硬编码的 "来自 DevTools 的测试推送消息" \ ) 负载。</span><span class="sxs-lookup"><span data-stu-id="1f077-258">A toast notification with the \(hard-coded "Test push message from DevTools"\) payload should appear.</span></span>  
    
    ![推送来自 DevTools 的通知][ImageDevtoolsPush]  
    
1.  <span data-ttu-id="1f077-260">接下来，尝试在 PWA 的主页上选择 " **发送通知** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="1f077-260">Next try choosing the **Send Notification** button on the homepage of your PWA.</span></span>  <span data-ttu-id="1f077-261">这次将显示来自服务器的负载的 toast。</span><span class="sxs-lookup"><span data-stu-id="1f077-261">This time a toast with the payload from your server appears.</span></span>  
    
    ![推送来自 PWA 服务器的通知][ImagePwaPush]  
    
    <span data-ttu-id="1f077-263">如果您不单击 \ (或激活 \ ) toast 通知，它将在几秒钟后关闭，并在 Windows 操作中心上排队。</span><span class="sxs-lookup"><span data-stu-id="1f077-263">If you do not click \(or activate\) a toast notification, it is dismissed after several seconds and queue up in your Windows Action Center.</span></span>  
    
    ![Windows 操作中心中的通知][ImageWindowsActionCenter]  
    
    <span data-ttu-id="1f077-265">你拥有 PWA 推送通知的基础知识。</span><span class="sxs-lookup"><span data-stu-id="1f077-265">You have the basics of PWA push notifications.</span></span>  <span data-ttu-id="1f077-266">在实际应用中，将以一种方式实现后续步骤，以管理和存储推送订阅以及正确地 [加密][NPMWebPushEncrypt] 通过线路发送的负载数据。</span><span class="sxs-lookup"><span data-stu-id="1f077-266">In a real app, the next steps are implemented in a way to manage and store push subscriptions and to properly [encrypt][NPMWebPushEncrypt] payload data being sent across the wire.</span></span>  
    
## <span data-ttu-id="1f077-267">深入探索</span><span class="sxs-lookup"><span data-stu-id="1f077-267">Going further</span></span>  

<span data-ttu-id="1f077-268">本指南演示了渐进式 Web 应用和 Microsoft PWA 开发工具（包括 Visual Studio、PWA 生成器和 Edge DevTools）的基本解析。</span><span class="sxs-lookup"><span data-stu-id="1f077-268">This guide demonstrated the basic anatomy of a Progressive Web App and Microsoft PWA development tools including Visual Studio, PWA Builder, and Edge DevTools.</span></span>  

<span data-ttu-id="1f077-269">当然，有很多其他内容可使你在此处看到 [一个很好的 PWA][PwaEdgehtmlIndexRequirements] ，包括响应式设计、深度链接、 [跨浏览器测试][BrowserStackTestEdgeBrowser] 和其他 [最佳做法][Webhint] \ (不要提及你的应用功能！ \ ) ，但希望本指南让你能够全面介绍 PWA 基础知识和有关入门的一些想法。</span><span class="sxs-lookup"><span data-stu-id="1f077-269">Of course, there is a lot more that goes into [making a great PWA][PwaEdgehtmlIndexRequirements] beyond what you read here, including responsive design, deep-linking, [cross-browser testing][BrowserStackTestEdgeBrowser] and other [best practices][Webhint] \(not to mention your app functionality!\), but hopefully this guide gave you a solid introduction of PWA basics and some ideas on getting started.</span></span>  <span data-ttu-id="1f077-270">如果在使用 Windows 或 Visual Studio 的 PWA 开发中还有其他问题，请留下评论！</span><span class="sxs-lookup"><span data-stu-id="1f077-270">If you have further questions on PWA development with Windows or with Visual Studio, please leave a comment!</span></span>  

<span data-ttu-id="1f077-271">查看其他 PWA 指南以了解如何提高客户的参与并提供更流畅的操作系统集成的应用体验。</span><span class="sxs-lookup"><span data-stu-id="1f077-271">Review the other PWA guides to learn how to increase customer engagement and provide a more seamless, OS-integrated app experience.</span></span>  

*   <span data-ttu-id="1f077-272">[Windows 定制][PwaEdgehtmlWindowsFeatures]。</span><span class="sxs-lookup"><span data-stu-id="1f077-272">[Windows tailoring][PwaEdgehtmlWindowsFeatures].</span></span> <span data-ttu-id="1f077-273">使用简单的功能检测，你可以通过本机 Windows 运行时 \ (WinRT ) Api （如用于自定义 Windows **开始** 菜单磁贴通知和任务栏 Jumplists 的 api）， (以及在权限 \ ) 处理用户资源（如照片、音乐和日历）的权限，来为 Windows 10 客户逐步增强 PWA。</span><span class="sxs-lookup"><span data-stu-id="1f077-273">Using simple feature detection, you may progressively enhance your PWA for Windows 10 customers through native Windows Runtime \(WinRT\) APIs, such as those for customizing Windows **Start** menu tile notifications and taskbar jumplists, and \(upon permission\) working with user resources, such as photos, music, and calendar.</span></span>  
*   <span data-ttu-id="1f077-274">[Microsoft Store 中的 PWAs][PwaEdgehtmlMicrosoftStore]。</span><span class="sxs-lookup"><span data-stu-id="1f077-274">[PWAs in the Microsoft Store][PwaEdgehtmlMicrosoftStore].</span></span>  <span data-ttu-id="1f077-275">了解有关应用商店分发的优点以及如何提交 PWA 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1f077-275">Learn more about the benefits of app store distribution and how to submit your PWA.</span></span>  

## <span data-ttu-id="1f077-276">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f077-276">See also</span></span>  

*   <span data-ttu-id="1f077-277">[MDN web 文档上的渐进式 Web 应用][MDNProgressiveWebApps] -有关渐进式 web 应用的绝佳指南。</span><span class="sxs-lookup"><span data-stu-id="1f077-277">[Progressive Web Apps on MDN web docs][MDNProgressiveWebApps] - Excellent guide on Progressive Web Apps.</span></span>  
*   <span data-ttu-id="1f077-278">Web[上的渐进式 Web 应用。适用][WebDevProgressiveWebApps]于渐进式 web 应用的优秀指南。</span><span class="sxs-lookup"><span data-stu-id="1f077-278">[Progressive Web Apps on web.dev][WebDevProgressiveWebApps] - Excellent guide on Progressive Web Apps.</span></span>  
*   <span data-ttu-id="1f077-279">[渐进式 Web 应用 rocks][ProgressiveWebApps] 展示 PWAs 的真实示例。</span><span class="sxs-lookup"><span data-stu-id="1f077-279">[Progressive Web Apps rocks][ProgressiveWebApps] - Showcases real-world examples of PWAs.</span></span>  
*   <span data-ttu-id="1f077-280">[作为渐进 Web 应用的黑客新闻阅读器][HackerNewsProgressiveWebApps] -比较不同的框架和性能模式，用于实现示例 \ (黑客新闻阅读器 \ ) PWA。</span><span class="sxs-lookup"><span data-stu-id="1f077-280">[Hacker News readers as Progressive Web Apps][HackerNewsProgressiveWebApps] - Compares different frameworks and performance patterns for implementing a sample \(Hacker News reader\) PWA.</span></span>  

<!-- image links -->  

[ImageDevtoolsPush]: ./media/devtools-push.png  
[ImageDevtoolsSwCache]: ./media/devtools-cache.png  
[ImageDevtoolsSwOverview]: ./media/devtools-sw-overview.png  
[ImageNotificationPermission]: ./media/notification-permission.png  
[ImageOfflineHtml]: ./media/offline-html.png  
[ImagePwa]: ./media/pwa.png  
[ImagePwaPush]: ./media/pwa-push.png  
[ImageVsNodejsExpressIcon]: ./media/vs-nodejs-express-icon.png  
[ImageVsNodejsExpressIndex]: ./media/vs-nodejs-express-index.png  
[ImageVsNodejsExpressManifest]: ./media/vs-nodejs-express-manifest.png  
[ImageVsNodejsExpressPublic]: ./media/vs-nodejs-express-public.png  
[ImageVsNodejsExpressTemplate]: ./media/vs-nodejs-express-template.png  
[ImageWindowsActionCenter]: ./media/windows-action-center.png  

<!-- links -->  

[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps-edgehtml/index.md#requirements "要求-渐进式 Web 应用 \ (EdgeHTML \ ) 在 Windows 上"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps-edgehtml/microsoft-store.md " (EdgeHTML \ ) Microsoft Store 中的渐进式 Web 应用"  
[PwaEdgehtmlWindowsFeatures]: ../progressive-web-apps-edgehtml/windows-features.md "为 Windows 定制你的 PWA \ (EdgeHTML \ ) "  

[LegalWindowsAgrementsMicrosoftStorePolicies]: /legal/windows/agreements/store-policies "Microsoft 应用商店政策 |Microsoft 文档"  

[VisualStudioNodeJsTutorial]: /visualstudio/nodejs/tutorial-nodejs "教程：在 Visual Studio 中创建 Node.js 和 Express 应用 |Microsoft 文档"  
[VisualStudioNodejsTutorialPublishAzureAppService]: /visualstudio/nodejs/tutorial-nodejs#optional-publish-to-azure-app-service "发布到 Azure 应用服务-在 Visual Studio 中创建 Node.js 和 Express 应用 |Microsoft 文档"  

[WindowsUwpGetStartedWhat]: /windows/uwp/get-started/whats-a-uwp "什么是通用 Windows 平台 \ (UWP ) 应用？ |Microsoft 文档"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "创建 Azure 免费帐户 |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web Apps |Microsoft Azure"  

<!--[DeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote/ "page not found"  -->  

[WindowsBlogsPwaEdge]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#4UOdrDJj3124VIkc.97 "将渐进式 Web 应用的欢迎应用到 Microsoft Edge 和 Windows 10 |Windows 博客"  
[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge 中的 Web 通知 |Windows 博客"  

[VisualStudioDownloads]: https://www.visualstudio.com/downloads "下载 |Visual Studio"  
[VisualStudioFree]: https://visualstudio.microsoft.com/free-developer-offers "免费的开发人员软件 & 服务 |Visual Studio"  
[VisualStudioPreview]: https://www.visualstudio.com/vs/preview "Visual Studio 预览版"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 上的免费 Microsoft Edge 浏览器测试 |BrowserStack"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "作为渐进式 Web 应用的黑客新闻阅读器"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "缓存 |MDN"  
[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/DedicatedWorkerGlobalScope/postMessage "DedicatedWorkerGlobalScope. postMessage \ ( \ ) |MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "渐进式 web 应用 (PWAs) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作者 API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "使用服务工作者 |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web App 清单 |MDN"  
[MDNWorkerPrototypePostMessage]: https://developer.mozilla.org/docs/Web/API/Worker/postMessage "PostMessage \ ( \ ) |MDN"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "通过 Mozilla 的推送服务发送 VAPID 标识的 WebPush 通知 |Mozilla 服务"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-推送 |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "加密 (userPublicKey、userAuth、负载、contentEncoding) web 推送 |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用情况-web 推送 |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "渐进式 Web 应用"  

[PugAttributes]: https://pugjs.org/language/attributes.html "属性 |Pug"  

[PwaBuilder]: https://www.pwabuilder.com "PWA 生成器"  
[PwaBuilderAppImageGenerator]: https://www.pwabuilder.com/imageGenerator "应用图像生成器"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "服务工作人员 |PWA 生成器"  

[ServiceWorkerCookbook]: https://serviceworke.rs "ServiceWorker 手册"  
[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "推送丰富的演示 |ServiceWorker 手册"  

[W3cWebAppManifest]: https://www.w3.org/TR/appmanifest "Web App 清单 |W3C"  

[Webhint]: https://sonarwhal.com "webhint，web 最佳做法的提示引擎" 
 
[MDNWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "使用 Web 工作人员" 

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "渐进式 Web 应用 |web 开发"  

[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS |科"  
[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "渐进式增强 |科"  
