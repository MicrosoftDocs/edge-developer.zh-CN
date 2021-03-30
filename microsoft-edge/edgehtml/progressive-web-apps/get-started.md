---
description: 本指南概述了在 Windows 上生成渐进式 Web 应用的 PWA 基础知识和工具。
title: 渐进式 Web 应用入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 Web 应用， PWA， Edge， Windows， PWABuilder， Web 清单， 服务工作者， 推送
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9a76399616ab7645b82242b94dd4757b73b37f60
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232020"
---
# <span data-ttu-id="e00b8-104">渐进式 Web 应用入门</span><span class="sxs-lookup"><span data-stu-id="e00b8-104">Get started with Progressive Web Apps</span></span>  

<span data-ttu-id="e00b8-105">渐进式 Web 应用 \(PWA\) 只是 Web 应用，[][WikiProgressiveEnhancement]通过支持平台和浏览器引擎上的本机类似应用功能（如从主屏幕启动、脱机支持和推送通知）逐渐增强。</span><span class="sxs-lookup"><span data-stu-id="e00b8-105">Progressive Web Apps \(PWAs\) are simply web apps that are [progressively enhanced][WikiProgressiveEnhancement] with native app-like features on supporting platforms and browser engines, such as launch-from-homescreen installation, offline support, and push notifications.</span></span>  <span data-ttu-id="e00b8-106">在具有 Microsoft Edge \(EdgeHTML\) 引擎的 Windows 10 上，PWA 享受独立于浏览器窗口作为通用 [Windows 平台应用运行的附加][WindowsUwpGetStartedWhat] 优势。</span><span class="sxs-lookup"><span data-stu-id="e00b8-106">On Windows 10 with the Microsoft Edge \(EdgeHTML\) engine, PWAs enjoy the added advantage of running independently of the browser window as [Universal Windows Platform][WindowsUwpGetStartedWhat] apps.</span></span>  

<span data-ttu-id="e00b8-107">本指南通过使用 Microsoft Visual Studio 和一些 PWA 生成器实用程序将简单的 Web 应用 `localhost` 构建为 PWA，概述了 PWA 基础知识。</span><span class="sxs-lookup"><span data-stu-id="e00b8-107">This guide gives you an overview of PWA basics by building a simple `localhost` web app as a PWA using Microsoft Visual Studio and some PWA Builder utilities.</span></span>  <span data-ttu-id="e00b8-108">完成的产品在支持 PWA 的任何浏览器中的工作方式类似。</span><span class="sxs-lookup"><span data-stu-id="e00b8-108">The finished product works similarly across any browser that supports PWAs.</span></span>  

> [!TIP]
> <span data-ttu-id="e00b8-109">若要快速将现有网站转换为 PWA 并将其打包用于 Windows 10 和其他应用平台，请查看 [PWA 生成器][PwaBuilder]。</span><span class="sxs-lookup"><span data-stu-id="e00b8-109">For a quick way to convert an existing site to a PWA and package it for Windows 10 and other app platforms, review [PWA Builder][PwaBuilder].</span></span>  

## <span data-ttu-id="e00b8-110">必备条件</span><span class="sxs-lookup"><span data-stu-id="e00b8-110">Prerequisites</span></span>  

<span data-ttu-id="e00b8-111">可以使用任何 Web 开发 IDE 生成 PWA。</span><span class="sxs-lookup"><span data-stu-id="e00b8-111">You may build PWAs with any web development IDE.</span></span>  <span data-ttu-id="e00b8-112">下面只是本指南的先决条件，它可指导你完成 Windows 开发人员生态系统中的 PWA 工具支持。</span><span class="sxs-lookup"><span data-stu-id="e00b8-112">The following are only prerequisites for this guide, which walks you through PWA tooling support in the Windows developer ecosystem.</span></span>  

*   <span data-ttu-id="e00b8-113">下载 \(free\) Visual Studio Community [2017][VisualStudioDownloads]。</span><span class="sxs-lookup"><span data-stu-id="e00b8-113">Download the \(free\) [Visual Studio Community 2017][VisualStudioDownloads].</span></span>  <span data-ttu-id="e00b8-114">您还可以使用专业版、企业版 [或预览][VisualStudioPreview] 版。</span><span class="sxs-lookup"><span data-stu-id="e00b8-114">You may also use the Professional, Enterprise, or [Preview][VisualStudioPreview] editions.</span></span>  <span data-ttu-id="e00b8-115">从Visual Studio安装程序中，选择以下工作负载。</span><span class="sxs-lookup"><span data-stu-id="e00b8-115">From the Visual Studio Installer, choose the following Workloads.</span></span>  
    
    *   **<span data-ttu-id="e00b8-116">通用 Windows 平台开发</span><span class="sxs-lookup"><span data-stu-id="e00b8-116">Universal Windows Platform development</span></span>**  
    *   **<span data-ttu-id="e00b8-117">Node.js开发</span><span class="sxs-lookup"><span data-stu-id="e00b8-117">Node.js development</span></span>**  

## <span data-ttu-id="e00b8-118">设置基本 Web 应用</span><span class="sxs-lookup"><span data-stu-id="e00b8-118">Set up a basic web app</span></span>  

<span data-ttu-id="e00b8-119">为简单起见，请使用 Visual Studio [Node.js 和 Express][VisualStudioNodeJsTutorial] 应用模板来创建提供页面的 Web `localhost` `index.html` 应用。</span><span class="sxs-lookup"><span data-stu-id="e00b8-119">For the sake of simplicity, use the Visual Studio [Node.js and Express app][VisualStudioNodeJsTutorial] template to create `localhost` web app that serves up an `index.html` page.</span></span>  <span data-ttu-id="e00b8-120">假设这是一个占位符，用于作为 PWA 进行开发且功能齐全的 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="e00b8-120">Imagine this as a placeholder for the compelling, full-featured web app that you are developing as a PWA.</span></span>  

1.  <span data-ttu-id="e00b8-121">启动Visual Studio，然后启动新项目。</span><span class="sxs-lookup"><span data-stu-id="e00b8-121">Launch Visual Studio, and start a new project.</span></span>  
    *   <span data-ttu-id="e00b8-122">**文件**  > **新建**  > **项目...**</span><span class="sxs-lookup"><span data-stu-id="e00b8-122">**File** > **New** > **Project...**</span></span>  
    *   `Ctrl`+`Shift`+`N`  
1.  <span data-ttu-id="e00b8-123">在 **JavaScript**下，选择 **Node.js Express 4 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="e00b8-123">Under **JavaScript**, select **Basic Node.js Express 4 Application**.</span></span>  <span data-ttu-id="e00b8-124">设置名称和位置，然后选择"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="e00b8-124">Set the name and location and choose **OK**.</span></span>  
    
    ![选择Node.js Express 4 项目模板Visual Studio][ImageVsNodejsExpressTemplate]  
    
1.  <span data-ttu-id="e00b8-126">加载新项目后，**选择"生成**\(`Ctrl` + `Shift` + `B` \) "，然后启动调试 \(`F5` \) 。</span><span class="sxs-lookup"><span data-stu-id="e00b8-126">Once your new project loads, choose **Build** \(`Ctrl`+`Shift`+`B`\) and **Start Debugging** \(`F5`\).</span></span>  <span data-ttu-id="e00b8-127">验证在 `index.html` 浏览到 时文件是否加载 `http://localhost:1337` 。</span><span class="sxs-lookup"><span data-stu-id="e00b8-127">Verify that your `index.html` file loads when you browse to `http://localhost:1337`.</span></span>  
    
    ![在 localhost 上运行新网站][ImageVsNodejsExpressIndex]  

## <span data-ttu-id="e00b8-129">将应用转换为 PWA</span><span class="sxs-lookup"><span data-stu-id="e00b8-129">Turn your app into a PWA</span></span>  

<span data-ttu-id="e00b8-130">现在，可以连接 Web 应用的基本 [PWA][PwaEdgehtmlIndexRequirements] 要求 *：Web 应用程序*清单 *、HTTPS* *和服务工作者*。</span><span class="sxs-lookup"><span data-stu-id="e00b8-130">Now it is time to wire up the basic [PWA requirements][PwaEdgehtmlIndexRequirements] for your web app: a *Web App Manifest*, *HTTPS* and *Service Workers*.</span></span>  

### <span data-ttu-id="e00b8-131">Web 应用清单</span><span class="sxs-lookup"><span data-stu-id="e00b8-131">Web App Manifest</span></span>  

<span data-ttu-id="e00b8-132">[Web 应用清单][MDNWebAppManifest]是描述应用的 JSON 元数据文件，包括名称、作者、条目页 URL 以及一个或多个图标。</span><span class="sxs-lookup"><span data-stu-id="e00b8-132">A [Web App Manifest][MDNWebAppManifest] is a JSON metadata file describing your app, including the name, author, entry page URL, and one or more icons.</span></span>  <span data-ttu-id="e00b8-133">因为它遵循基于 [标准的][W3cWebAppManifest]架构，因此只能提供要安装在任何支持 PWA 的平台、操作系统和设备组合上的 PWA 的单个 Web 应用清单。</span><span class="sxs-lookup"><span data-stu-id="e00b8-133">Because it follows a [standards-based schema][W3cWebAppManifest], you must only supply a single web app manifest for the PWA that you are installing on any platform, OS, and device combination that supports PWAs.</span></span>  <span data-ttu-id="e00b8-134">在 Windows 生态系统中，Web 应用清单向必应 Web 索引器发出信号，表明您的 PWA 是自动包含在 [Microsoft Store][PwaEdgehtmlMicrosoftStore]中的候选项，其中每月有近 7 亿活跃用户作为 Windows 10 应用。</span><span class="sxs-lookup"><span data-stu-id="e00b8-134">In the Windows ecosystem, your web app manifest signals to the Bing web indexer that your PWA is a candidate for automatic inclusion in the [Microsoft Store][PwaEdgehtmlMicrosoftStore], where it may reach nearly 700 million active monthly users as a Windows 10 app.</span></span>  

<span data-ttu-id="e00b8-135">如果这是一个现有的实时网站，可以使用 PWA 生成器生成 [Web 应用程序清单][PwaBuilder]。</span><span class="sxs-lookup"><span data-stu-id="e00b8-135">If this were an existing live site, you may generate a web app manifest using [PWA Builder][PwaBuilder].</span></span>  <span data-ttu-id="e00b8-136">由于它仍然是一个未发布的项目，因此请复制示例清单。</span><span class="sxs-lookup"><span data-stu-id="e00b8-136">Since it is still an unpublished project, copy a sample manifest.</span></span>  

1.  <span data-ttu-id="e00b8-137">在Visual Studio资源管理器中，右 键单击该公用文件夹，然后选择"添加新文件  >  **..."，** 指定为 `manifest.json` 项目名称。</span><span class="sxs-lookup"><span data-stu-id="e00b8-137">In the Visual Studio *Solution Explorer*, right-click the *public* folder and select **Add** > **New File...**, specifying `manifest.json` as the item name.</span></span>  
1.  <span data-ttu-id="e00b8-138">在 `manifest.json` 文件中，复制以下代码。</span><span class="sxs-lookup"><span data-stu-id="e00b8-138">In the `manifest.json` file, copy the following code.</span></span>  

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
    
    <span data-ttu-id="e00b8-139">在真实的 PWA 中，下一步是自定义 名称、start_url、short_name、说明 和图标*\(* 图标，下一步\) 。  </span><span class="sxs-lookup"><span data-stu-id="e00b8-139">In a real PWA, the next step is to customize *name*, *start_url*, *short_name*, *description*, and *icons* \(icons are covered in the next step\).</span></span>  
    
    <span data-ttu-id="e00b8-140">若要了解有关不同成员值和相关用途的信息，请参阅 [Web 应用清单][MDNWebAppManifest] 参考。</span><span class="sxs-lookup"><span data-stu-id="e00b8-140">To learn more about the different member values and associated purposes, see the [Web App Manifest][MDNWebAppManifest] reference.</span></span>  
    
1.  <span data-ttu-id="e00b8-141">接下来，使用 PWA 生成器应用图像生成器使用实际图像路径 `icons` 填充空数组。</span><span class="sxs-lookup"><span data-stu-id="e00b8-141">Next, fill in the empty `icons` array with actual image paths by using the PWA Builder App Image Generator.</span></span>  
    
    1.  <span data-ttu-id="e00b8-142">使用 Web 浏览器，下载此示例 [512x512 PWA 图像][ImagePwa]。</span><span class="sxs-lookup"><span data-stu-id="e00b8-142">Using a web browser, download this [sample 512x512 PWA image][ImagePwa].</span></span>  
    1.  <span data-ttu-id="e00b8-143">转到 PWA 生成器 [应用图像][PwaBuilderAppImageGenerator]生成器，选择刚保存为输入图像 `pwa.png` **的图像** ，然后选择"下载 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e00b8-143">Go to the PWA Builder [App Image Generator][PwaBuilderAppImageGenerator], and select the `pwa.png` image you just saved as the **Input Image** and then choose the **Download** button.</span></span>  
    1.  <span data-ttu-id="e00b8-144">**打开** 并 **提取** zip 文件。</span><span class="sxs-lookup"><span data-stu-id="e00b8-144">**Open** and **Extract** the zip file.</span></span>  
    1.  <span data-ttu-id="e00b8-145">在Visual Studio资源管理器中，右键单击文件夹，在文件 `public` **资源管理器中打开文件夹**。</span><span class="sxs-lookup"><span data-stu-id="e00b8-145">In the Visual Studio Solution Explorer, right-click the `public` folder and **Open Folder in File Explorer**.</span></span>  <span data-ttu-id="e00b8-146">创建一 **个名为 "新建"** 的文件夹 `images` 。</span><span class="sxs-lookup"><span data-stu-id="e00b8-146">Create a **New folder** named `images`.</span></span>  
    1.  <span data-ttu-id="e00b8-147">将提取的 zip 的所有平台文件夹 \(， ，等等\) 复制到文件夹并 `android` `chrome` `windows10` `images` 关闭文件资源管理器窗口。</span><span class="sxs-lookup"><span data-stu-id="e00b8-147">Copy all of the platform folders \(`android`, `chrome`, `windows10`, and so on\) from your extracted zip to the `images` folder and close the file explorer window.</span></span>  <span data-ttu-id="e00b8-148">将文件夹添加到解决方案资源管理器Visual Studio \(项目 \(，右键单击文件夹，然后针对每个文件夹选择"添加现有文件夹 `images`   >  ..."\) 。</span><span class="sxs-lookup"><span data-stu-id="e00b8-148">Add the folders to your Visual Studio project \(in Solution Explorer, right-click `images` folder and select **Add** > **Existing folder...** for each of the folders\).</span></span>  
    1.  <span data-ttu-id="e00b8-149">从 (zip 中打开 \Visual Studio 或任何编辑器\) 文件，将数组复制到 `icons.json` `"icons": [...]` `manifest.json` 项目文件中。</span><span class="sxs-lookup"><span data-stu-id="e00b8-149">Open \(with Visual Studio or any editor\) the `icons.json` file from the extracted zip and copy the `"icons": [...]` array into the `manifest.json` file of your project.</span></span>  

1.  <span data-ttu-id="e00b8-150">现在，必须将 Web 应用清单与你的应用关联。</span><span class="sxs-lookup"><span data-stu-id="e00b8-150">Now you must associate your web app manifest with your app.</span></span>  <span data-ttu-id="e00b8-151">在 folder\(中打开文件 \) 进行编辑，然后直接在样式表链接后 `layout.pug` `views` 添加此行。</span><span class="sxs-lookup"><span data-stu-id="e00b8-151">Open the `layout.pug` file \(in `views` folder\) for editing, and add this line right after the stylesheet link.</span></span>  <span data-ttu-id="e00b8-152">\(它只是 [\) ][PugAttributes] 的 Node pug `<link rel='manifest' href='/manifest.json'>` 模板简写。</span><span class="sxs-lookup"><span data-stu-id="e00b8-152">\(It is simply the Node [pug][PugAttributes] template shorthand for `<link rel='manifest' href='/manifest.json'>`\).</span></span>  
    
    ```html
    link(rel='manifest', href='/manifest.json')
    ```  
    
<span data-ttu-id="e00b8-153">所有这些就绪后，Web 应用现在即可提供清单和主屏幕就绪应用图标！</span><span class="sxs-lookup"><span data-stu-id="e00b8-153">With all that in place, your web app is now serving up a manifest and homescreen-ready app icons!</span></span>  <span data-ttu-id="e00b8-154">尝试运行应用 \(`F5` \) 并加载清单。</span><span class="sxs-lookup"><span data-stu-id="e00b8-154">Try running your app \(`F5`\) and loading up the manifest.</span></span>  

![从 localhost 加载 Web 应用清单][ImageVsNodejsExpressManifest]  

<span data-ttu-id="e00b8-156">以及你的图标之一。</span><span class="sxs-lookup"><span data-stu-id="e00b8-156">And one of your icons.</span></span>  

![从 localhost 加载 Square71x71Logo 应用徽标][ImageVsNodejsExpressIcon]  

<span data-ttu-id="e00b8-158">如果使用实际 \) 发布实时 \(应用，必应搜索引擎现在将其标识为自动打包并提交到 Microsoft Store 的候选项，作为可安装的 `start_url` Windows 10 应用。 [][PwaEdgehtmlMicrosoftStore]</span><span class="sxs-lookup"><span data-stu-id="e00b8-158">If you publish the app live \(with an actual `start_url`\), the Bing search engine now identifies it as a candidate for [automatic packaging and submission to the Microsoft Store][PwaEdgehtmlMicrosoftStore] as an installable Windows 10 app.</span></span>  <span data-ttu-id="e00b8-159">确保你的manifest.js文件包含必应扫描的渐进式 [Web 应用][WindowsBlogsPwaEdge] 的质量信号，包括以下项目。</span><span class="sxs-lookup"><span data-stu-id="e00b8-159">Ensure that your manifest.json file includes the [Quality signals for Progressive Web Apps][WindowsBlogsPwaEdge] for which Bing scans including the following items.</span></span>   

*   `name`  
*   `description`  
*   <span data-ttu-id="e00b8-160">至少一个图标 512px 正方形或更大的 \(以确保图像源具有足够的分辨率，以便自动生成应用的初始屏幕、应用商店一览、磁贴图像等\) 。</span><span class="sxs-lookup"><span data-stu-id="e00b8-160">At least one icon 512px square or larger \(to ensure an image source of sufficient resolution for auto-generating the splash screen of your app, store listing, tile image, and so on\).</span></span>  

<span data-ttu-id="e00b8-161">此外，使用[HTTPS，](#https)[服务工作者](#service-workers)，并遵守[Microsoft Store 策略][LegalWindowsAgrementsMicrosoftStorePolicies]。</span><span class="sxs-lookup"><span data-stu-id="e00b8-161">In addition, use [HTTPS](#https), [service workers](#service-workers), and comply with [Microsoft Store Policies][LegalWindowsAgrementsMicrosoftStorePolicies].</span></span>  

### <span data-ttu-id="e00b8-162">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e00b8-162">HTTPS</span></span>  

<span data-ttu-id="e00b8-163">[][MDNServiceWorkerApi]服务工作人员和其他关键 PWA 技术与服务工作人员 \(（如缓存、推送和后台[][MDNCache]同步[][MDNPushApi]API\) ）仅跨安全连接工作，这意味着[HTTPS][WikiHttps]用于实时网站或调试目的。 [][MDNSyncManager] `localhost`</span><span class="sxs-lookup"><span data-stu-id="e00b8-163">[Service Workers][MDNServiceWorkerApi] and other key PWA technologies that work with service workers \(such as the [Cache][MDNCache], [Push][MDNPushApi], and [Background Sync][MDNSyncManager] APIs\) only work across secure connections, which means [HTTPS][WikiHttps] for live sites or `localhost` for debugging purposes.</span></span>  

<span data-ttu-id="e00b8-164">如果你将 [此 Web][VisualStudioNodejsTutorialPublishAzureAppService] 应用发布为实时网站 \(例如，通过设置 [Azure][AzureCreateFreeAccount]免费帐户 \) ，则必须确保服务器已针对 HTTPS 进行配置。</span><span class="sxs-lookup"><span data-stu-id="e00b8-164">If you [publish this web app as a live site][VisualStudioNodejsTutorialPublishAzureAppService] \(for example, by setting up an [Azure free account][AzureCreateFreeAccount]\), you must ensure your server is configured for HTTPS.</span></span>  <span data-ttu-id="e00b8-165">如果使用 Microsoft [Azure 应用服务][AzureWebApps] 托管网站，默认情况下通过 HTTPS 提供服务。</span><span class="sxs-lookup"><span data-stu-id="e00b8-165">If you use the [Microsoft Azure App Service][AzureWebApps] to host your site, it is served over HTTPS by default.</span></span>  

<span data-ttu-id="e00b8-166">对于本指南，继续使用 `http://localhost` 作为所服务实时网站的占位符 `https://` 。</span><span class="sxs-lookup"><span data-stu-id="e00b8-166">For this guide, continue using `http://localhost` as a placeholder for a live site served over `https://`.</span></span>  

### <span data-ttu-id="e00b8-167">服务工作者</span><span class="sxs-lookup"><span data-stu-id="e00b8-167">Service Workers</span></span>  

<span data-ttu-id="e00b8-168">服务工作人员是 PBA 背后的关键技术。</span><span class="sxs-lookup"><span data-stu-id="e00b8-168">Service Workers is the key technology behind PWAs.</span></span> <span data-ttu-id="e00b8-169">服务工作人员充当 PWA 和网络之间的代理，以使您的网站能够充当已安装的本机应用，提供脱机方案、响应服务器推送通知和运行后台任务。</span><span class="sxs-lookup"><span data-stu-id="e00b8-169">Service Workers act as a proxy between your PWA and the network to enable your website to function as an installed native app that serves up offline scenarios, responds to server push notifications, and runs background tasks.</span></span>  <span data-ttu-id="e00b8-170">服务工作人员还打开了新的性能策略。</span><span class="sxs-lookup"><span data-stu-id="e00b8-170">Service workers also open up new performance strategies.</span></span>  <span data-ttu-id="e00b8-171">无需实现完整的 Web 应用，就需使用服务工作器缓存来为网站微调页面加载性能。</span><span class="sxs-lookup"><span data-stu-id="e00b8-171">You are not required to implement a full web app to use the service worker cache for fine-tuned page load performance for your website.</span></span>  

<span data-ttu-id="e00b8-172">服务工作者是事件驱动的后台线程，从 JavaScript 文件运行，与支持 Web 应用的常规脚本一起提供。</span><span class="sxs-lookup"><span data-stu-id="e00b8-172">Service workers are event-driven background threads that run from JavaScript files served up alongside the regular scripts that power your web app.</span></span>  <span data-ttu-id="e00b8-173">由于服务工作者不在主 UI 线程上运行，因此服务工作者没有 DOM 访问权限，尽管[UI][MDNWorkerPrototypePostMessage]线程和[][MDNDedicatedWorkerGlobalScopePostMessage]工作线程能够使用和事件 `postMessage()` `onmessage` 处理程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="e00b8-173">Because Service workers do not run on the main UI thread, service workers do not have DOM access, though the [UI thread][MDNWorkerPrototypePostMessage] and a [worker thread][MDNDedicatedWorkerGlobalScopePostMessage] is able to communicate using `postMessage()` and `onmessage` event handlers.</span></span>  

<span data-ttu-id="e00b8-174">将服务工作者注册到网站 \(的 URL 源或其中指定的路径\) 。</span><span class="sxs-lookup"><span data-stu-id="e00b8-174">You associate a service worker with your app by registering it to the URL origin of your site \(or a specified path within it\).</span></span>  <span data-ttu-id="e00b8-175">注册后，将在用户计算机上下载、安装和激活服务工作文件。</span><span class="sxs-lookup"><span data-stu-id="e00b8-175">Once registered, the service worker file is then downloaded, installed, and activated on the user machine.</span></span>  <span data-ttu-id="e00b8-176">有关详细信息，MDN Web 文档具有有关使用 [服务][MDNUsingServiceWorkers] 工作者的综合指南和详细的 [服务工作者 API][MDNServiceWorkerApi] 参考。</span><span class="sxs-lookup"><span data-stu-id="e00b8-176">For more, MDN web docs has a comprehensive guide on [Using Service Workers][MDNUsingServiceWorkers] and a detailed [Service Worker API][MDNServiceWorkerApi] reference.</span></span>  

<span data-ttu-id="e00b8-177">对于本教程，请使用 PWA 生成器上的脱机页面服务 [工作器脚本][PwaBuilderServiceWorker]。</span><span class="sxs-lookup"><span data-stu-id="e00b8-177">For this tutorial, use the Offline page service worker script on [PWA Builder][PwaBuilderServiceWorker].</span></span>  <span data-ttu-id="e00b8-178">首先，根据性能要求、网络带宽等自定义具有更多功能的脚本。</span><span class="sxs-lookup"><span data-stu-id="e00b8-178">Start by customizing the script with more functionality according to your performance requirements, network bandwidth, and so on.</span></span>  <span data-ttu-id="e00b8-179">查看 [Mozilla 提供的][ServiceWorkerCookbook]  服务工作者手册，了解许多有用的服务工作者缓存想法。</span><span class="sxs-lookup"><span data-stu-id="e00b8-179">Review the [Service Worker Cookbook][ServiceWorkerCookbook]  provided by Mozilla for a number of useful service worker caching ideas.</span></span>  

1.  <span data-ttu-id="e00b8-180">打开 [https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker] 并选择 \(default\) **脱机页面** 服务工作线程，然后单击 **"下载服务工作线程"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e00b8-180">Open [https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker] and select the \(default\) **Offline page** service worker and click the **Download service worker** button.</span></span>  
1.  <span data-ttu-id="e00b8-181">打开下载文件夹并复制以下两个文件</span><span class="sxs-lookup"><span data-stu-id="e00b8-181">Open the download folder and copy the following two files</span></span>  

    *   <span data-ttu-id="e00b8-182">ServiceWorker1\pwabuilder-sw-register.js</span><span class="sxs-lookup"><span data-stu-id="e00b8-182">ServiceWorker1\pwabuilder-sw-register.js</span></span>  
    *   <span data-ttu-id="e00b8-183">ServiceWorker1\pwabuilder-sw.js</span><span class="sxs-lookup"><span data-stu-id="e00b8-183">ServiceWorker1\pwabuilder-sw.js</span></span>  
    
    <span data-ttu-id="e00b8-184">将文件保存到 `public` Web 应用项目Visual Studio文件夹。</span><span class="sxs-lookup"><span data-stu-id="e00b8-184">Save the files to the `public` folder of your Visual Studio web app project.</span></span>  <span data-ttu-id="e00b8-185">\(From Visual Studio， use `Ctrl` + `O` to open file explorer to your project and navigate to the `public` folder\) .</span><span class="sxs-lookup"><span data-stu-id="e00b8-185">\(From Visual Studio, use `Ctrl`+`O` to open file explorer to your project and navigate to the `public` folder\).</span></span>  
    
    <span data-ttu-id="e00b8-186">在解决方案资源管理器中 `public/pwabuilder-sw.js` ，打开文件，将值 `offlineFallbackPage` 更改为 `offline.html` 。</span><span class="sxs-lookup"><span data-stu-id="e00b8-186">In Solution Explorer, open the `public/pwabuilder-sw.js` file, and change the value of `offlineFallbackPage` to `offline.html`.</span></span>  
    
    ```javascript
    const offlineFallbackPage = "offline.html";
    ```
    
    <span data-ttu-id="e00b8-187">值得一看这两个文件的代码，以了解如何注册缓存指定页面 \(\) 的服务工作器，在网络提取失败时提供服务。 `offline.html`</span><span class="sxs-lookup"><span data-stu-id="e00b8-187">It is worth reviewing the code in both of these files, to get the gist of how to register a service worker that caches a designated page \(`offline.html`\) and serves it when a network fetch fails.</span></span>  <span data-ttu-id="e00b8-188">接下来，创建一 `offline.html` 个简单的页面作为应用的脱机功能的占位符。</span><span class="sxs-lookup"><span data-stu-id="e00b8-188">Next, create a simple `offline.html` page as a placeholder for the offline functionality of your app.</span></span>  
    
1.  <span data-ttu-id="e00b8-189">在解决方案资源管理器中， `views/layout.pug` 打开该文件，并添加链接标记下方的以下行。</span><span class="sxs-lookup"><span data-stu-id="e00b8-189">In Solution Explorer, open the `views/layout.pug` file, and add the following line below your link tags.</span></span>  
    
    ```html
    script(src='/pwabuilder-sw-register.js' type='module')
    ```  
    
    <span data-ttu-id="e00b8-190">您的网站加载并运行服务工作者注册脚本。</span><span class="sxs-lookup"><span data-stu-id="e00b8-190">Your site loads and runs your service worker registration script.</span></span>  
    
1.  <span data-ttu-id="e00b8-191">在解决方案资源管理器中，右键单击该 `public` 文件夹，然后选择 **"**  >  **添加新文件..."。** 将其命名 `offline.html` ，并添加 `<title>` 一个和一些正文内容，例如以下代码。</span><span class="sxs-lookup"><span data-stu-id="e00b8-191">In Solution Explorer, right-click on the `public` folder and select **Add** > **New File...**.  Name it `offline.html`, and add a `<title>` and some body content, for example the following code.</span></span>  
    
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
    
    <span data-ttu-id="e00b8-192">此时，你的 `public` 文件夹应具有三个新文件。</span><span class="sxs-lookup"><span data-stu-id="e00b8-192">At this point, your `public` folder should have three new files.</span></span>  
    
    ![添加到解决方案的公用文件夹的文件][ImageVsNodejsExpressPublic]  
    
1.  <span data-ttu-id="e00b8-194">在解决方案资源管理器中，打开该文件，并添加以下代码，然后最后一个命令 `routes\index.js` \(`module.exports = router;` \) 。</span><span class="sxs-lookup"><span data-stu-id="e00b8-194">In Solution Explorer, open the `routes\index.js` file, and add the following code just before the final command \(`module.exports = router;`\).</span></span>  
    
    ```javascript
    router.get('/offline.html', function (req, res) {
        res.sendFile('public/offline.html');
    });
    ```  
    
    <span data-ttu-id="e00b8-195">这会指示你的应用在服务工作线程为脱机缓存 `offline.html` \(提取文件时为该文件 \) 。</span><span class="sxs-lookup"><span data-stu-id="e00b8-195">This instructs your app to serve the `offline.html` file \(when your service worker fetches it for the offline cache\).</span></span>  
    
1.  <span data-ttu-id="e00b8-196">测试 PWA！</span><span class="sxs-lookup"><span data-stu-id="e00b8-196">Test out your PWA!</span></span>  <span data-ttu-id="e00b8-197">生成 \(\) 并运行 \(\) Web 应用以启动 `Ctrl` + `Shift` + `B` Microsoft `F5` Edge 并打开 `localhost` 你的页面。</span><span class="sxs-lookup"><span data-stu-id="e00b8-197">Build \(`Ctrl`+`Shift`+`B`\) and Run \(`F5`\) your web app to launch Microsoft Edge and open your `localhost` page.</span></span>  <span data-ttu-id="e00b8-198">然后完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e00b8-198">Then complete the following steps.</span></span>  
    
    1.  <span data-ttu-id="e00b8-199">打开 Edge DevTools**控制台**\(`Ctrl` + `Shift` + `J` \) 并验证服务工作者已注册。</span><span class="sxs-lookup"><span data-stu-id="e00b8-199">Open the Edge DevTools **Console** \(`Ctrl`+`Shift`+`J`\) and verify the Service worker was registered.</span></span>  
    1.  <span data-ttu-id="e00b8-200">在 **调试器面板** 中，展开 **服务工作者** 控件并单击源。</span><span class="sxs-lookup"><span data-stu-id="e00b8-200">In the **Debugger** panel, expand the **Service Workers** control and click on your origin.</span></span>  <span data-ttu-id="e00b8-201">在 **"服务工作器概述**"中，验证服务工作器是否激活并正在运行。</span><span class="sxs-lookup"><span data-stu-id="e00b8-201">In the **Service Worker Overview**, verify your service worker is activated and running.</span></span>  
        
        ![Edge DevTools Service Worker 概述][ImageDevtoolsSwOverview]  
        
    1.  <span data-ttu-id="e00b8-203">展开 **缓存** 控件并验证 `offline.html` 页面是否缓存。</span><span class="sxs-lookup"><span data-stu-id="e00b8-203">Expand the **Cache** control and verify that the `offline.html` page is cached.</span></span>  
        
        ![Edge DevTools 服务工作器缓存][ImageDevtoolsSwCache]  
        
1.  <span data-ttu-id="e00b8-205">尝试将 PWA 作为脱机应用的时间！</span><span class="sxs-lookup"><span data-stu-id="e00b8-205">Time to try your PWA as an offline app!</span></span>  <span data-ttu-id="e00b8-206">In Visual Studio， **Stop Debugging** \(`Shift` + `F5` \) your web app， then open Microsoft Edge \(or refresh\) to the localhost address of your website.</span><span class="sxs-lookup"><span data-stu-id="e00b8-206">In Visual Studio, **Stop Debugging** \(`Shift`+`F5`\) your web app, then open Microsoft Edge \(or refresh\) to the localhost address of your website.</span></span>  <span data-ttu-id="e00b8-207">它现在应该会加载 `offline.html` 页面 \(，这要归功于服务工作线程和脱机缓存\) ！</span><span class="sxs-lookup"><span data-stu-id="e00b8-207">It should now load the `offline.html` page \(thanks to your service worker and offline cache\)!</span></span>  
    
    ![offline.htmmicrosoft Edge http://localhost:1337 中加载的 l][ImageOfflineHtml]  

## <span data-ttu-id="e00b8-209">添加推送通知</span><span class="sxs-lookup"><span data-stu-id="e00b8-209">Add push notifications</span></span>  

<span data-ttu-id="e00b8-210">通过添加对推送通知的客户端支持（使用推送 [API][MDNPushApi] 订阅消息传递服务和通知 [API，][MDNNotificationsApi] 以在收到消息时显示 Toast 消息）使 PWA 更像应用。</span><span class="sxs-lookup"><span data-stu-id="e00b8-210">Make your PWA more app-like by adding client-side support for push notifications using the [Push API][MDNPushApi] to subscribe to a messaging service and the [Notifications API][MDNNotificationsApi] to display a toast message upon receiving a message.</span></span>  <span data-ttu-id="e00b8-211">与服务工作人员一样，这些 API 是基于标准的 API，可跨浏览器工作，因此只需编写代码一次，它才能在支持 PWA 的任何地方工作。</span><span class="sxs-lookup"><span data-stu-id="e00b8-211">As with Service Workers, these are standards-based APIs that work cross-browser, so you only have to write the code once for it to work everywhere PWAs are supported.</span></span>  <span data-ttu-id="e00b8-212">在服务器端，使用 Web [推送][NPMWebPush] 开放源代码库处理将推送消息发送到各种浏览器所涉及的差异。</span><span class="sxs-lookup"><span data-stu-id="e00b8-212">On the server side, use the [Web-Push][NPMWebPush] open-source library to handle the differences involved in delivering push messages to various browsers.</span></span>  

<span data-ttu-id="e00b8-213">以下内容改编自 Mozilla 提供的"服务[][ServiceWorkerCookbookPushRichDemo]工作者手册中的推送丰富演示"，值得查看其他一些有用的 Web 推送和服务工作者方法。</span><span class="sxs-lookup"><span data-stu-id="e00b8-213">The following is adapted from the Push Rich Demo in [Service Worker Cookbook][ServiceWorkerCookbookPushRichDemo] provided by Mozilla, which is worth checking out for a number of other useful Web Push and service worker recipes.</span></span>  

### <span data-ttu-id="e00b8-214">步骤 1 - 安装 NPM Web 推送库</span><span class="sxs-lookup"><span data-stu-id="e00b8-214">Step 1 - Install the NPM web-push library</span></span>  

<span data-ttu-id="e00b8-215">在Visual Studio资源管理器中，右键单击您的项目，然后打开Node.js **交互窗口...** 在它内，键入以下代码。</span><span class="sxs-lookup"><span data-stu-id="e00b8-215">In Visual Studio Solution Explorer, right-click your project and **Open Node.js Interactive Window...**.  In it, type the following code.</span></span>  

```javascript
.npm install web-push
```  

<span data-ttu-id="e00b8-216">这将安装 [Web 推送][NPMWebPush] 库。</span><span class="sxs-lookup"><span data-stu-id="e00b8-216">This installs the [Web-Push][NPMWebPush] library.</span></span>  <span data-ttu-id="e00b8-217">然后，打开文件，在其他要求语句之后将以下行 `index.js` 添加到文件顶部。</span><span class="sxs-lookup"><span data-stu-id="e00b8-217">Then, open up your `index.js` file, and add the following line to the top of your file after the other requirement statements.</span></span>  

```javascript
var webpush = require('web-push');
```  

### <span data-ttu-id="e00b8-218">步骤 2 - 为服务器生成 VAPID 密钥</span><span class="sxs-lookup"><span data-stu-id="e00b8-218">Step 2 - Generate VAPID keys for your server</span></span>  

<span data-ttu-id="e00b8-219">接下来，必须生成 VAPID \(自愿应用程序服务器标识\) 密钥，服务器向 PWA 客户端发送推送消息。</span><span class="sxs-lookup"><span data-stu-id="e00b8-219">Next you must generate VAPID \(Voluntary Application Server Identification\) keys for your server to send push messages to the PWA client.</span></span>  <span data-ttu-id="e00b8-220">只需执行一次 \(，即服务器只需要一对 VAPID 密钥\) 。</span><span class="sxs-lookup"><span data-stu-id="e00b8-220">You only have to do this once \(that is, your server only requires a single pair of VAPID keys\).</span></span>  <span data-ttu-id="e00b8-221">在Node.js窗口中，键入以下代码。</span><span class="sxs-lookup"><span data-stu-id="e00b8-221">In the Node.js Interactive Window, type the following code.</span></span>  

```javascript
var webpush = require('web-push');
webpush.generateVAPIDKeys();
```  

<span data-ttu-id="e00b8-222">输出结果应包含一个公钥和私钥的 JSON 对象，你可以将其复制到服务器逻辑中。</span><span class="sxs-lookup"><span data-stu-id="e00b8-222">The output should result in a JSON object containing a public and private key, which you copy into your server logic.</span></span>  

<span data-ttu-id="e00b8-223">在文件 `index.js` 的最后一个 \(`module.exports = router` \) 行之前，添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="e00b8-223">In your `index.js` file, just before the final  \(`module.exports = router`\) line, add the following code.</span></span>  

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

<span data-ttu-id="e00b8-224">复制 `publicKey` 刚 `privateKey` 生成的和值。</span><span class="sxs-lookup"><span data-stu-id="e00b8-224">Copy the `publicKey` and `privateKey` values that you just generated.</span></span>  <span data-ttu-id="e00b8-225">可以随意自定义 `mailto` \(，尽管运行此示例不需要\) 。</span><span class="sxs-lookup"><span data-stu-id="e00b8-225">Feel free to customize the `mailto` address as well \(though it is not required in order to run this sample\).</span></span>  

<span data-ttu-id="e00b8-226">如果你对 VAPID 和 WebPush 的后台工作原理的详细信息感兴趣 [，Mozilla][MozillaServicesSendingVapidWebPushNotificationsPush] 服务工程博客有一个很好的解释者。</span><span class="sxs-lookup"><span data-stu-id="e00b8-226">The [Mozilla Services engineering blog][MozillaServicesSendingVapidWebPushNotificationsPush] has a nice explainer on VAPID and WebPush if you are interested in the details of how it works behind the scenes.</span></span>  

### <span data-ttu-id="e00b8-227">步骤 3 - 处理与推送相关的服务器请求</span><span class="sxs-lookup"><span data-stu-id="e00b8-227">Step 3 - Handle push-related server requests</span></span>  

<span data-ttu-id="e00b8-228">现在设置用于处理来自 PWA 客户端的推送相关请求的路由，包括提供 VAPID 公钥和注册客户端以接收推送。</span><span class="sxs-lookup"><span data-stu-id="e00b8-228">Now set up routes for handling push-related requests from the PWA client, including serving up the VAPID public key and registering the client to receive pushes.</span></span>  

<span data-ttu-id="e00b8-229">在真实方案中，推送通知可能源自服务器逻辑中的事件。</span><span class="sxs-lookup"><span data-stu-id="e00b8-229">In a real scenario, a push notification likely originates from an event in your server logic.</span></span>  <span data-ttu-id="e00b8-230">若要简化此处的一些操作，必须将 推送通知按钮添加到 PWA 主页以从我们的服务器生成推送，并添加终结点 `/sendNotification` \(服务器路由\) 来处理这些请求。</span><span class="sxs-lookup"><span data-stu-id="e00b8-230">To simplify things here, you must add a **Push Notification** button to our PWA homepage for generating pushes from our server, and a `/sendNotification` endpoint \(server route\)for handling those requests.</span></span>  

<span data-ttu-id="e00b8-231">在文件中，将以下路由附加到在 `index.js` [步骤 2][#step-2---generate-vapid-keys-for-your-server] 中添加的 VAPID 初始化代码之后。</span><span class="sxs-lookup"><span data-stu-id="e00b8-231">In your `index.js` file, append the following routes just after the VAPID initialization code you added in [Step 2][#step-2---generate-vapid-keys-for-your-server].</span></span>  

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

<span data-ttu-id="e00b8-232">在服务器端代码就位后，PWA 客户端上的推送通知就位。</span><span class="sxs-lookup"><span data-stu-id="e00b8-232">With the server-side code in place, plumb in push notifications on the PWA client.</span></span>  

### <span data-ttu-id="e00b8-233">步骤 4 - 订阅推送通知</span><span class="sxs-lookup"><span data-stu-id="e00b8-233">Step 4 - Subscribe to push notifications</span></span>  

<span data-ttu-id="e00b8-234">作为 PWA 网络代理角色的一部分，服务工作人员处理推送事件和 Toast 通知交互。</span><span class="sxs-lookup"><span data-stu-id="e00b8-234">As part of their role as PWA network proxies, service workers handle push events and toast notification interactions.</span></span>  <span data-ttu-id="e00b8-235">但是，与首次设置 \(或注册\) 服务工作者一样，将 PWA 订阅到服务器推送通知发生在 PWA 的主 UI 线程上，并且需要网络连接。</span><span class="sxs-lookup"><span data-stu-id="e00b8-235">However, as it is with first setting up \(or registering\) a service worker, subscribing the PWA to server push notifications happens on the main UI thread of the PWA and requires network connectivity.</span></span>  <span data-ttu-id="e00b8-236">订阅推送通知需要活动的服务工作者注册，因此必须先验证服务工作者是否已安装并处于活动状态，然后再尝试订阅推送通知。</span><span class="sxs-lookup"><span data-stu-id="e00b8-236">Subscribing to push notifications requires an active service worker registration, so you must first verify that your service worker is installed and active before trying to subscribe it to push notifications.</span></span>  

<span data-ttu-id="e00b8-237">在新建推送订阅之前，Microsoft Edge 会检查用户是否授予了 PWA 接收通知的权限。</span><span class="sxs-lookup"><span data-stu-id="e00b8-237">Before a new push subscription is created, Microsoft Edge check if the user granted the PWA permission to receive notifications.</span></span>  <span data-ttu-id="e00b8-238">如果没有，浏览器会提示用户授予权限。</span><span class="sxs-lookup"><span data-stu-id="e00b8-238">If not, the user is prompted by the browser for permission.</span></span>  <span data-ttu-id="e00b8-239">如果权限被拒绝，则会引发 `registration.pushManager.subscribe` 一个 `DOMException` 请求，因此您必须处理它。</span><span class="sxs-lookup"><span data-stu-id="e00b8-239">If the permission is denied, the request to `registration.pushManager.subscribe` throws a `DOMException`, so you must handle it.</span></span>  <span data-ttu-id="e00b8-240">有关权限管理 More on permission management， see [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span><span class="sxs-lookup"><span data-stu-id="e00b8-240">For more on permission management, see [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span></span>  

<span data-ttu-id="e00b8-241">在 `pwabuilder-sw-register.js` 文件中，附加以下代码。</span><span class="sxs-lookup"><span data-stu-id="e00b8-241">In your `pwabuilder-sw-register.js` file, append the following code.</span></span>  

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

<span data-ttu-id="e00b8-242">查看有关 [PushManager][MDNPushManager] 接口的 MDN 文档和 Web [推送][NPMWebPushUsage] 库上的 NPM 文档，了解有关 API 如何工作以及各种相关选项的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="e00b8-242">Review the MDN documentation on the [PushManager][MDNPushManager] interface and NPM docs on the [Web-Push][NPMWebPushUsage] library for more details on how the APIs work and various related options.</span></span>  

### <span data-ttu-id="e00b8-243">步骤 5 - 设置推送和 notificationclick 事件处理程序</span><span class="sxs-lookup"><span data-stu-id="e00b8-243">Step 5 - Set up push and notificationclick event handlers</span></span>  

<span data-ttu-id="e00b8-244">设置推送订阅后，剩余工作将发生在服务工作者中。</span><span class="sxs-lookup"><span data-stu-id="e00b8-244">With our push subscription set up, the remainder of the work happens in the service worker.</span></span>  <span data-ttu-id="e00b8-245">首先，您必须为服务器发送的推送事件设置处理程序，并响应 toast 通知 \(如果授予权限\) 显示推送数据负载。</span><span class="sxs-lookup"><span data-stu-id="e00b8-245">First you must set up a handler for server-sent push events, and respond with a toast notification \(if permission was granted\) displaying the push data payload.</span></span>  <span data-ttu-id="e00b8-246">接下来，为 Toast 添加一个单击处理程序以关闭通知，并浏览当前打开的窗口的列表，以打开、聚焦或打开并聚焦预期的 PWA 客户端页面。</span><span class="sxs-lookup"><span data-stu-id="e00b8-246">Next you add a click handler for the toast to dismiss the notification and sort through a list of currently open windows to open, focus, or open and focus the intended PWA client page.</span></span>  

<span data-ttu-id="e00b8-247">在 `pwabuilder-sw.js` 文件中，追加以下处理程序。</span><span class="sxs-lookup"><span data-stu-id="e00b8-247">In your `pwabuilder-sw.js` file, append the following handlers.</span></span>  

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

### <span data-ttu-id="e00b8-248">步骤 6 - 试用</span><span class="sxs-lookup"><span data-stu-id="e00b8-248">Step 6 - Try it out</span></span>  

<span data-ttu-id="e00b8-249">在 PWA 中测试推送通知的时间！</span><span class="sxs-lookup"><span data-stu-id="e00b8-249">Time to test push notifications in your PWA!</span></span>  

1.  <span data-ttu-id="e00b8-250">在浏览器中 (`F5` \) \) PWA。</span><span class="sxs-lookup"><span data-stu-id="e00b8-250">Run \(`F5`\) your PWA in the browser.</span></span>  <span data-ttu-id="e00b8-251">由于修改了服务工作器代码 \(\) ，因此您必须打开 `pwabuilder-sw.js` DevTools Debugger \(\) 到"服务工作者概述"面板并注销服务工作器并重新加载 \(\) 页面以重新注册它 \(或者单击"更新 `F12`  `F5` ") 。 </span><span class="sxs-lookup"><span data-stu-id="e00b8-251">Because you modified the service worker code \(`pwabuilder-sw.js`\), you must open the DevTools Debugger \(`F12`\) to the **Service Worker Overview** panel and **Unregister** the service worker and reload \(`F5`\) the page to re-register it \(or you click **Update**\).</span></span>  <span data-ttu-id="e00b8-252">在生产方案中，浏览器会定期检查服务工作者更新，并在后台安装更新。</span><span class="sxs-lookup"><span data-stu-id="e00b8-252">In a production scenario, the browser checks regularly check for service worker updates and install the updates in the background.</span></span>  <span data-ttu-id="e00b8-253">你应在此处强制它，以立即获得结果。</span><span class="sxs-lookup"><span data-stu-id="e00b8-253">You should force it here for immediate results.</span></span>  
    
    <span data-ttu-id="e00b8-254">当服务工作者激活并尝试订阅 PWA 以推送通知时，您应在页面底部看到一个权限对话框。</span><span class="sxs-lookup"><span data-stu-id="e00b8-254">As your service worker activates and attempts to subscribe your PWA to push notifications, you should see a permission dialog at the bottom of the page.</span></span>  
    
    ![用于启用通知的权限对话框][ImageNotificationPermission]  
    
    <span data-ttu-id="e00b8-256">选择 **"是** "为 PWA 启用 Toast 通知。</span><span class="sxs-lookup"><span data-stu-id="e00b8-256">Choose **Yes** to enable toast notifications for your PWA.</span></span>  
    
1.  <span data-ttu-id="e00b8-257">从"服务工作者概述"窗格中，尝试选择  **"推送"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="e00b8-257">From the Service Worker Overview pane, try choosing the  **Push** button.</span></span>  <span data-ttu-id="e00b8-258">应显示包含 \(硬编码的"从 DevTools 测试推送消息"\) 通知。</span><span class="sxs-lookup"><span data-stu-id="e00b8-258">A toast notification with the \(hard-coded "Test push message from DevTools"\) payload should appear.</span></span>  
    
    ![从 DevTools 推送通知][ImageDevtoolsPush]  
    
1.  <span data-ttu-id="e00b8-260">接下来 **，尝试选择** PWA 主页上的"发送通知"按钮。</span><span class="sxs-lookup"><span data-stu-id="e00b8-260">Next try choosing the **Send Notification** button on the homepage of your PWA.</span></span>  <span data-ttu-id="e00b8-261">此时将显示包含服务器有效负载的 Toast。</span><span class="sxs-lookup"><span data-stu-id="e00b8-261">This time a toast with the payload from your server appears.</span></span>  
    
    ![从 PWA 服务器推送通知][ImagePwaPush]  
    
    <span data-ttu-id="e00b8-263">如果不单击 \(或 activate\) toast 通知，它将在几秒钟后关闭，并排入 Windows 操作中心。</span><span class="sxs-lookup"><span data-stu-id="e00b8-263">If you do not click \(or activate\) a toast notification, it is dismissed after several seconds and queue up in your Windows Action Center.</span></span>  
    
    ![Windows 操作中心中的通知][ImageWindowsActionCenter]  
    
    <span data-ttu-id="e00b8-265">您具有 PWA 推送通知的基础知识。</span><span class="sxs-lookup"><span data-stu-id="e00b8-265">You have the basics of PWA push notifications.</span></span>  <span data-ttu-id="e00b8-266">在真实的应用中，通过管理和存储推送订阅以及正确加密通过线路发送的有效负载数据的方式实现接下来的步骤。 [][NPMWebPushEncrypt]</span><span class="sxs-lookup"><span data-stu-id="e00b8-266">In a real app, the next steps are implemented in a way to manage and store push subscriptions and to properly [encrypt][NPMWebPushEncrypt] payload data being sent across the wire.</span></span>  
    
## <span data-ttu-id="e00b8-267">深入探索</span><span class="sxs-lookup"><span data-stu-id="e00b8-267">Going further</span></span>  

<span data-ttu-id="e00b8-268">本指南演示了渐进式 Web 应用和 Microsoft PWA 开发工具（包括 Visual Studio、PWA 生成器和 Edge DevTools）的基本分析。</span><span class="sxs-lookup"><span data-stu-id="e00b8-268">This guide demonstrated the basic anatomy of a Progressive Web App and Microsoft PWA development tools including Visual Studio, PWA Builder, and Edge DevTools.</span></span>  

<span data-ttu-id="e00b8-269">当然，除了您在此处阅读的 PWA 之外，制作出色的[PWA][PwaEdgehtmlIndexRequirements]还涉及很多内容，包括响应式设计、深度链接[][BrowserStackTestEdgeBrowser]、跨浏览器测试和其他最佳实践[\(][Webhint]不要提及您的应用程序功能！\) ，但希望本指南能够深入介绍 PWA 基础知识和入门的一些想法。</span><span class="sxs-lookup"><span data-stu-id="e00b8-269">Of course, there is a lot more that goes into [making a great PWA][PwaEdgehtmlIndexRequirements] beyond what you read here, including responsive design, deep-linking, [cross-browser testing][BrowserStackTestEdgeBrowser] and other [best practices][Webhint] \(not to mention your app functionality!\), but hopefully this guide gave you a solid introduction of PWA basics and some ideas on getting started.</span></span>  <span data-ttu-id="e00b8-270">如果你对 Windows 或 windows 的 PWA 开发有进一Visual Studio，请留下评论！</span><span class="sxs-lookup"><span data-stu-id="e00b8-270">If you have further questions on PWA development with Windows or with Visual Studio, please leave a comment!</span></span>  

<span data-ttu-id="e00b8-271">查看其他 PWA 指南，了解如何提高客户参与度并提供更加无缝、与操作系统集成的应用体验。</span><span class="sxs-lookup"><span data-stu-id="e00b8-271">Review the other PWA guides to learn how to increase customer engagement and provide a more seamless, OS-integrated app experience.</span></span>  

*   <span data-ttu-id="e00b8-272">[Windows 定制][PwaEdgehtmlWindowsFeatures]。</span><span class="sxs-lookup"><span data-stu-id="e00b8-272">[Windows tailoring][PwaEdgehtmlWindowsFeatures].</span></span> <span data-ttu-id="e00b8-273">使用简单的功能检测，可以通过本机 Windows 运行时 \(WinRT\) API 逐步增强适用于 Windows 10 客户的 PWA，例如用于自定义 **Windows"** 开始"菜单磁贴通知和任务栏跳转列表的 API，以及使用用户资源（如照片、音乐和日历）的 \(权限\) 。</span><span class="sxs-lookup"><span data-stu-id="e00b8-273">Using simple feature detection, you may progressively enhance your PWA for Windows 10 customers through native Windows Runtime \(WinRT\) APIs, such as those for customizing Windows **Start** menu tile notifications and taskbar jumplists, and \(upon permission\) working with user resources, such as photos, music, and calendar.</span></span>  
*   <span data-ttu-id="e00b8-274">[Microsoft Store 中的 PWA。][PwaEdgehtmlMicrosoftStore]</span><span class="sxs-lookup"><span data-stu-id="e00b8-274">[PWAs in the Microsoft Store][PwaEdgehtmlMicrosoftStore].</span></span>  <span data-ttu-id="e00b8-275">详细了解应用商店分发的好处以及如何提交 PWA。</span><span class="sxs-lookup"><span data-stu-id="e00b8-275">Learn more about the benefits of app store distribution and how to submit your PWA.</span></span>  

## <span data-ttu-id="e00b8-276">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e00b8-276">See also</span></span>  

*   <span data-ttu-id="e00b8-277">[MDN Web 文档上的渐进][MDNProgressiveWebApps] Web 应用 - 关于渐进式 Web 应用的出色指南。</span><span class="sxs-lookup"><span data-stu-id="e00b8-277">[Progressive Web Apps on MDN web docs][MDNProgressiveWebApps] - Excellent guide on Progressive Web Apps.</span></span>  
*   <span data-ttu-id="e00b8-278">[Web.dev 上的][WebDevProgressiveWebApps] 渐进 Web 应用 - 关于渐进式 Web 应用的出色指南。</span><span class="sxs-lookup"><span data-stu-id="e00b8-278">[Progressive Web Apps on web.dev][WebDevProgressiveWebApps] - Excellent guide on Progressive Web Apps.</span></span>  
*   <span data-ttu-id="e00b8-279">[渐进式 Web 应用中心][ProgressiveWebApps] - 展示 PBA 的真实示例。</span><span class="sxs-lookup"><span data-stu-id="e00b8-279">[Progressive Web Apps rocks][ProgressiveWebApps] - Showcases real-world examples of PWAs.</span></span>  
*   <span data-ttu-id="e00b8-280">[作为渐进式 Web][HackerNewsProgressiveWebApps] 应用的黑客新闻阅读器 - 比较用于实现示例 \(黑客新闻阅读器\) PWA 的不同框架和性能模式。</span><span class="sxs-lookup"><span data-stu-id="e00b8-280">[Hacker News readers as Progressive Web Apps][HackerNewsProgressiveWebApps] - Compares different frameworks and performance patterns for implementing a sample \(Hacker News reader\) PWA.</span></span>  

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

[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps/index.md#requirements "要求 - Windows 上的渐进式 Web 应用 \(EdgeHTML\) |Microsoft Docs"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps/microsoft-store.md "渐进式 Web 应用 \(Microsoft Store ) EdgeHTML\) |Microsoft Docs"  
[PwaEdgehtmlWindowsFeatures]: ../progressive-web-apps/windows-features.md "定制适用于 Windows 的 PWA \(EdgeHTML\) |Microsoft Docs"  

[LegalWindowsAgrementsMicrosoftStorePolicies]: /legal/windows/agreements/store-policies "Microsoft Store 策略 |Microsoft Docs"  

[VisualStudioNodeJsTutorial]: /visualstudio/nodejs/tutorial-nodejs "教程：在 Node.js 创建应用和 Express Visual Studio |Microsoft Docs"  
[VisualStudioNodejsTutorialPublishAzureAppService]: /visualstudio/nodejs/tutorial-nodejs#optional-publish-to-azure-app-service "发布到 Azure 应用服务 - 在 Node.js 和 Express Visual Studio |Microsoft Docs"  

[WindowsUwpGetStartedWhat]: /windows/uwp/get-started/whats-a-uwp "什么是通用 Windows 平台 \(UWP\) 应用？ |Microsoft Docs"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "创建 Azure 免费帐户 |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web 应用 |Microsoft Azure"  

<!--[DeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote/ "page not found"  -->  

[WindowsBlogsPwaEdge]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#4UOdrDJj3124VIkc.97 "使渐进式 Web 应用与 Microsoft Edge 和 Windows 10 保持一致 |Windows 博客"  
[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge 中的 Web 通知 |Windows 博客"  

[VisualStudioDownloads]: https://www.visualstudio.com/downloads "下载 |Visual Studio"  
[VisualStudioFree]: https://visualstudio.microsoft.com/free-developer-offers "免费开发人员软件&服务 |Visual Studio"  
[VisualStudioPreview]: https://www.visualstudio.com/vs/preview "Visual Studio预览"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 上的免费 Microsoft Edge 浏览器测试 |BrowserStack"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "作为渐进式 Web 应用的黑客新闻阅读器"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "缓存 |MDN"  
[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/DedicatedWorkerGlobalScope/postMessage "DedicatedWorkerGlobalScope.postMessage\(\) |MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "渐进式 Web 应用 \(PWA) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作者 API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "使用服务工作者 |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web 应用清单 |MDN"  
[MDNWorkerPrototypePostMessage]: https://developer.mozilla.org/docs/Web/API/Worker/postMessage "Worker.prototype.postMessage\(\) |MDN"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "通过 Mozilla 推送服务发送 VAPID 标识的 WebPush 通知 |Mozilla 服务"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "Web 推送 |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "encrypt (userPublicKey， userAuth， payload， contentEncoding) - web-push |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "用法 - Web 推送 |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "渐进式 Web 应用"  

[PugAttributes]: https://pugjs.org/language/attributes.html "属性 |Pug"  

[PwaBuilder]: https://www.pwabuilder.com "PWA 生成器"  
[PwaBuilderAppImageGenerator]: https://www.pwabuilder.com/imageGenerator "应用映像生成器"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "服务工作者 |PWA 生成器"  

[ServiceWorkerCookbook]: https://serviceworke.rs "ServiceWorker 手册"  
[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "推送丰富演示 |ServiceWorker 手册"  

[W3cWebAppManifest]: https://www.w3.org/TR/appmanifest "Web 应用清单 |W3C"  

[Webhint]: https://sonarwhal.com "webhint，Web 最佳实践的提示引擎" 
 
[MDNWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "使用 Web 工作人员" 

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "渐进式 Web 应用 |web.dev"  

[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS |Wikipedia"  
[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "渐进式增强 |Wikipedia"  
