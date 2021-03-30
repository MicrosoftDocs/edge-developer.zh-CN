---
description: 使用本机应用功能逐步增强适用于 Windows 的 PWA
title: 定制适用于 Windows (EdgeHTML) PWA
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 Web 应用， PWA， Edge， Windows， WinRT， UWP， EdgeHTML
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 59612d8292d4c4d4d7073b843386364d1ac55c5d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232438"
---
# <span data-ttu-id="d7ecd-104">定制适用于 Windows (EdgeHTML) PWA</span><span class="sxs-lookup"><span data-stu-id="d7ecd-104">Tailor your PWA (EdgeHTML) for Windows</span></span>  

<span data-ttu-id="d7ecd-105">安装在 Windows 10 上的[][PwaIndexWindows10]PWA 享受作为通用 Windows 平台[\(UWP\) ][WindowsUWPGetStartedGuide]应用运行的所有优势，包括通过 Windows 应用沙盒安全性和对 Windows 运行时[\(WinRT\) ) ][UwpApiIndex] API 的完全访问权限的保护，包括以下这些 API：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-105">PWAs installed on Windows 10 enjoy [all the benefits][PwaIndexWindows10] of running as [Universal Windows Platform \(UWP\)][WindowsUWPGetStartedGuide] apps, including protection through Windows app sandboxing security and full access to [Windows Runtime \(WinRT\))][UwpApiIndex] APIs, including those for:</span></span>  

*   <span data-ttu-id="d7ecd-106">控制设备功能 \(例如相机、麦克风、GPS\) </span><span class="sxs-lookup"><span data-stu-id="d7ecd-106">Controlling device features \(such as camera, microphone, GPS\)</span></span>  
*   <span data-ttu-id="d7ecd-107">访问用户资源 \(例如日历、联系人、文档、音乐\) </span><span class="sxs-lookup"><span data-stu-id="d7ecd-107">Accessing user resources \(such as calendar, contacts, documents, music\)</span></span>  
*   <span data-ttu-id="d7ecd-108">通过 Cortana 语音命令启动/导航应用</span><span class="sxs-lookup"><span data-stu-id="d7ecd-108">Launching / navigating your app through Cortana voice commands</span></span>  
*   <span data-ttu-id="d7ecd-109">通过 Windows 操作中心 (桌面任务栏和上下文菜单\) </span><span class="sxs-lookup"><span data-stu-id="d7ecd-109">Integrating with the Windows OS \(through the Windows Action Center, desktop taskbar, and context menus\)</span></span>  
    
<span data-ttu-id="d7ecd-110">这些只是 Windows 上 PWA \(EdgeHTML\) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-110">These are only a few of the added possibilities for your PWA \(EdgeHTML\) on Windows.</span></span>  

<span data-ttu-id="d7ecd-111">本文介绍了如何作为 Windows 10 应用安装、运行和增强 PWA \(EdgeHTML\) ，同时仍确保跨浏览器和跨平台兼容性。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-111">This article shows you how to install, run, and enhance your PWA \(EdgeHTML\) as a Windows 10 app, while still ensuring cross-browser and cross-platform compatibility.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="d7ecd-112">本文中的示例和步骤需要 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-112">The examples and steps in this article require Visual Studio 2017.</span></span> <span data-ttu-id="d7ecd-113">Visual Studio 2019 中不包含本文中使用的模板。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-113">Visual Studio 2019 does not include the template used in this article.</span></span> <span data-ttu-id="d7ecd-114">若要下载 Visual Studio 2017，请参阅 Visual Studio [Downloads - 2017， 2015 &旧版本][PreviousVSDownloads]</span><span class="sxs-lookup"><span data-stu-id="d7ecd-114">To download Visual Studio 2017, see [Visual Studio Downloads - 2017, 2015 & Previous Versions][PreviousVSDownloads]</span></span>  


## <span data-ttu-id="d7ecd-115">必备条件</span><span class="sxs-lookup"><span data-stu-id="d7ecd-115">Prerequisites</span></span>  

*   <span data-ttu-id="d7ecd-116">现有的 PWA \(或托管 Web 应用\) ，可以是实时或本地主机网站。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-116">An existing PWA \(or hosted web app\), either a live or localhost site.</span></span>  <span data-ttu-id="d7ecd-117">本指南使用渐进式 Web 应用入门[中的示例 PWA。][PwaGetStarted]</span><span class="sxs-lookup"><span data-stu-id="d7ecd-117">This guide uses the sample PWA from [Get started with Progressive Web Apps][PwaGetStarted].</span></span>  
*   <span data-ttu-id="d7ecd-118">下载 \(free\) Visual Studio Community [2017][MicrosoftVisualStudio|::ref1::|]。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-118">Download the \(free\) [Visual Studio Community 2017][MicrosoftVisualStudio|::ref1::|].</span></span>  <span data-ttu-id="d7ecd-119">您还可以使用专业版、企业版或 [预览][MicrosoftVisualStudioPreview] 版。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-119">You are also able to use the Professional, Enterprise, or [Preview][MicrosoftVisualStudioPreview] editions.</span></span>  <span data-ttu-id="d7ecd-120">从Visual Studio安装程序中，选择以下工作负载：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-120">From the Visual Studio Installer, choose the following Workloads:</span></span>  
    *   **<span data-ttu-id="d7ecd-121">通用 Windows 平台开发</span><span class="sxs-lookup"><span data-stu-id="d7ecd-121">Universal Windows Platform development</span></span>**  
        
## <span data-ttu-id="d7ecd-122">设置并运行通用 Windows 应用</span><span class="sxs-lookup"><span data-stu-id="d7ecd-122">Set up and run your Universal Windows app</span></span>  

<span data-ttu-id="d7ecd-123">作为 Windows 10 应用安装的 PWA \(EdgeHTML\) 在独立的 \(`WWAHost.exe` process\) 窗口中独立于浏览器运行。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-123">A PWA \(EdgeHTML\) installed as a Windows 10 app runs independently from the browser, in a standalone \(`WWAHost.exe` process\) window.</span></span>  <span data-ttu-id="d7ecd-124">启用此功能只需一个轻型应用包装器，其中包含托管的 Web 应用，您可以使用项目模板快速Visual Studio `Progressive Web App (Universal Windows)` 设置。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-124">Enabling this simply requires a lightweight app wrapper that contains your hosted web app, which you are able to quickly set up using the Visual Studio `Progressive Web App (Universal Windows)` project template.</span></span>  <span data-ttu-id="d7ecd-125">\(所有应用逻辑（包括发送本机 Windows 运行时 API 请求）仍发生在原始 Web 应用代码中。\) </span><span class="sxs-lookup"><span data-stu-id="d7ecd-125">\(All your app logic, including sending native Windows Runtime API requests, still happens in your original web app code.\)</span></span>  

<span data-ttu-id="d7ecd-126">在 windows 应用中设置 Windows 应用Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-126">Set up your Windows app development environment in Visual Studio.</span></span>  

1.  <span data-ttu-id="d7ecd-127">在 Windows 设置中，打开 [开发人员模式][WindowsUWPGetStartedEnable]。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-127">In your Windows Settings, turn on [Developer mode][WindowsUWPGetStartedEnable].</span></span>  <span data-ttu-id="d7ecd-128">\(在 Windows `developer mode` 搜索栏中键入以查找它。\) </span><span class="sxs-lookup"><span data-stu-id="d7ecd-128">\(Type `developer mode` in the Windows searchbar to find it.\)</span></span>  
1.  <span data-ttu-id="d7ecd-129">启动Visual Studio并选择 **"新建项目..."。**</span><span class="sxs-lookup"><span data-stu-id="d7ecd-129">Launch Visual Studio and select **Create a new project...**.</span></span>  
1.  <span data-ttu-id="d7ecd-130">Choose **Javascript**  >  **Windows Universal** and select Progressive Web App (Universal Windows )  from the list of project types in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="d7ecd-130">Choose **Javascript** > **Windows Universal** and select **Progressive Web App (Universal Windows)** from the list of project types in Visual Studio 2017.</span></span>  
1.  <span data-ttu-id="d7ecd-131">选择默认的 Windows 10 `Target version` \(最新版\) 和 `Minimum version` \(版本 10586 或更高版本\) 选择"确定"。 </span><span class="sxs-lookup"><span data-stu-id="d7ecd-131">Select the default Windows 10 `Target version` \(most recent release\) and `Minimum version` \(build 10586 or higher\) and choose **OK**.</span></span>  
    
    ![Visual Studio UWP 项目目标版本选择对话框](media/vs-target-min-version.png)  
    
    <span data-ttu-id="d7ecd-133">当 package.appxmanifest 设计器打开时，将加载新项目。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-133">Your new project loads with the package.appxmanifest designer open.</span></span>  <span data-ttu-id="d7ecd-134">这是配置应用详细信息的地方，包括程序包标识、程序包依赖项、所需功能、视觉元素和扩展点。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-134">This is where you configure the details of your app, including package identity, package dependencies, required capabilities, visual elements, and extensibility points.</span></span>  <span data-ttu-id="d7ecd-135">这是在应用开发期间使用的应用包清单的易于配置的临时版本。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-135">This is an easily configurable, temporary version of the app package manifest used during app development.</span></span>  
    <span data-ttu-id="d7ecd-136">生成应用项目时，Visual Studio元数据[][UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest]生成一AppxManifest.xml文件，该文件用于安装和运行应用。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-136">When you build your app project, [Visual Studio generates an AppxManifest.xml][UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest] file from this metadata, which is used to install and run your app.</span></span>  <span data-ttu-id="d7ecd-137">每当更新 `package.appxmanifest` 文件时，请务必重新生成项目，以便在运行时反映 `AppxManifest.xml` 这两者。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-137">Whenever you update your `package.appxmanifest` file, be sure to rebuild the project so both are reflected in your `AppxManifest.xml` at runtime.</span></span>  
    
1.  <span data-ttu-id="d7ecd-138">在清单设计器 **应用程序面板** 中，输入 PWA 的 URL 作为 `Start page` 。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-138">In the manifest designer **Application** panel, enter the URL of your PWA as the `Start page`.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d7ecd-139">所有 https \(、remote\) url 都受支持 `StartPage` 。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-139">Service workers are supported for all https \(secure, remote\) urls specified as the `StartPage`.</span></span>  <span data-ttu-id="d7ecd-140">默认情况下，指定本地起始页的 Web 应用不支持服务工作者。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-140">Service workers are not supported by default for web apps that specify a local start page.</span></span>  <span data-ttu-id="d7ecd-141">若要为这些情况启用服务工作者支持，请向清单中添加一个显式 [ApplicationContentUriRules](#set-application-content-uri-rules-acurs) 条目，例如：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-141">To enable service worker support for these cases, add an explicit [ApplicationContentUriRules](#set-application-content-uri-rules-acurs) entry to the manifest, for example:</span></span> `<uap:Rule Match="http://web-platform.test/" Type="include" uap5:ServiceWorker="true"/>`  
    
    ![package.appxmanifest 设计器的应用程序面板](media/vs-manifest-application.png)  
    
    <span data-ttu-id="d7ecd-143">您还可以根据需要修改 。 `Display name` `Description`</span><span class="sxs-lookup"><span data-stu-id="d7ecd-143">You are able to also modify the `Display name` and `Description` as you like.</span></span>  
1.  <span data-ttu-id="d7ecd-144">将此文件 \(或选择\) 另一个 512x512 映像保存到桌面。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-144">Save this file \(or another 512x512 image of your choosing\) to your desktop.</span></span>  
    <span data-ttu-id="d7ecd-145">然后，在清单设计器**可视化资源**面板中，单击字段 `Source` **...** 按钮，选择它作为源文件，然后单击"生成 **"。**</span><span class="sxs-lookup"><span data-stu-id="d7ecd-145">Then, in the manifest designer **Visual Assets** panel, click on the `Source` field **...** button, select it as your source file, and click **Generate**.</span></span>  <span data-ttu-id="d7ecd-146">\(然后单击" **确定** "覆盖默认占位符图像\) 。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-146">\(Then click **OK** to overwrite the default placeholder images\).</span></span>  
    
    ![package.appxmanifest 设计器的可视化资源面板](media/vs-manifest-visual-assets.png)  
    
    <span data-ttu-id="d7ecd-148">这将生成在应用商店中安装、运行、启动和分发应用的基本视觉资源。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-148">This generates the basic visual assets for installing, running, launching, and distributing your app in the store.</span></span>  
    <span data-ttu-id="d7ecd-149">如果看到任何红色 \(\) 错误，指示缺少图像，则你可以单击 ... 按钮，从生成的图像中手动 `X` 选择文件。 </span><span class="sxs-lookup"><span data-stu-id="d7ecd-149">If you see any red \(`X`\) errors indicating missing images, you are able to click on the **...** buttons to manually select a file from the generated images.</span></span>  
1.  <span data-ttu-id="d7ecd-150">在清单设计器**内容 URI**面板中，将 `http://example.com` PWA \(的位置替换为 `Rule`  =  `include` `WinRT Access`  =  `All` \) 。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-150">In the manifest designer **Content URIs** panel, replace `http://example.com` with the location of your PWA \(such that `Rule` = `include` and `WinRT Access` = `All`\).</span></span>  
    <span data-ttu-id="d7ecd-151">这将授予 PWA 在作为 Windows 10 应用运行时发送本机 Windows 运行时 \(WinRT\) API 请求的权限，稍后将对此进行介绍。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-151">This grants your PWA permission to send native Windows Runtime \(WinRT\) API requests when running as a Windows 10 app, which is covered a bit later.</span></span>   <span data-ttu-id="d7ecd-152">如果你的实际 PWA 不需要 WinRT 访问，你可以将值切换到 `WinRT Access` `None` 。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-152">If your actual PWA does not require WinRT access, you are able to switch the `WinRT Access` value to `None`.</span></span>  <span data-ttu-id="d7ecd-153">无论使用哪种方式，请确保使用 PWA 的 URI 细分默认字符串，否则应用无法 `http://example.com` 在运行时正确加载。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-153">Either way, be sure to sub out the default `http://example.com` string with the URI of your PWA, or your app is not able to properly load at runtime.</span></span>  
    <span data-ttu-id="d7ecd-154">你已准备好作为 Windows 10 应用运行和调试 PWA。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-154">You are ready to run and debug your PWA as a Windows 10 app.</span></span>  <span data-ttu-id="d7ecd-155">如果使用 localhost 网站逐步执行本指南，请确保它正在运行。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-155">If you are using a localhost site to step through this guide, make sure it is running.</span></span>  <span data-ttu-id="d7ecd-156">然后，</span><span class="sxs-lookup"><span data-stu-id="d7ecd-156">Then,</span></span>  
1.  <span data-ttu-id="d7ecd-157">生成 \(`Ctrl` + `Shift` + `F5` \) 并运行 \(`F5` \) PWA 项目。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-157">Build \(`Ctrl`+`Shift`+`F5`\) and Run \(`F5`\) your PWA project.</span></span>  <span data-ttu-id="d7ecd-158">现在，你的网站应在独立应用窗口中启动。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-158">Your website should now launch in a standalone app window.</span></span>  <span data-ttu-id="d7ecd-159">它不仅是一个托管的 Web 应用;它作为安装在 Windows 10 上的渐进 Web 应用运行！</span><span class="sxs-lookup"><span data-stu-id="d7ecd-159">Not only is it a hosted web app; it is running as a Progressive Web App installed on Windows 10!</span></span>  
    
    ![在活动窗口中WWAHost.exe PWA](media/wwahost.png)  
    
## <span data-ttu-id="d7ecd-161">将 PWA \(EdgeHTML\) 作为 Windows 应用调试</span><span class="sxs-lookup"><span data-stu-id="d7ecd-161">Debug your PWA \(EdgeHTML\) as a Windows app</span></span>  

<span data-ttu-id="d7ecd-162">由于 PWA \(EdgeHTML\) 只是一个逐步增强的托管 Web 应用，因此您可以使用常用的 IDE 和工作流调试与任何 Web 应用相同的服务器端代码。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-162">Because a PWA \(EdgeHTML\) is simply a progressively enhanced hosted web app, you are able to debug your server-side code the same as any web app, using your usual IDE and workflow.</span></span>  <span data-ttu-id="d7ecd-163">下一次启动时，实时部署的更改将反映在已安装的 PWA 中 (无需重新部署通用 Windows 应用包\) 。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-163">The changes you deploy live are reflected in your installed PWA the next time you launch it \(no need to redeploy your Universal Windows app package\).</span></span>

<span data-ttu-id="d7ecd-164">对于 Windows 10 应用中的客户端调试，你必须拥有 `Microsoft Edge DevTools Preview` 该应用。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-164">For client-side debugging within your Windows 10 app, you must have the `Microsoft Edge DevTools Preview` app.</span></span>  <span data-ttu-id="d7ecd-165">此独立应用包括原始浏览器内 Microsoft [Edge DevTools][DevToolsGuide] \(的所有功能（包括[PWA 工具][DevToolsGuideServiceWorkers]\) ）以及基本的远程[][DevToolsProtocol01ClientsEdgePreview]调试支持和用于附加到任何正在运行的[][DevToolsGuideMicrosoftStoreApp]EdgeHTML 引擎实例的调试目标选择器，包括适用于 Office、Cortana、应用 Webview 的外接程序，当然还包括在 Windows 上运行的 PWA。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-165">This standalone app includes all the functionality of the original in-browser [Microsoft Edge DevTools][DevToolsGuide] \(including [PWA tools][DevToolsGuideServiceWorkers]\), plus basic [remote debugging][DevToolsProtocol01ClientsEdgePreview] support and a [Debug Target chooser][DevToolsGuideMicrosoftStoreApp] for attaching to any running instance of the EdgeHTML engine, including add-ins for Office, Cortana, app webviews, and of course, PWAs running on Windows.</span></span>  

<span data-ttu-id="d7ecd-166">下面是如何为 PWA \(EdgeHTML\) 。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-166">Here is how to set up debugging for your PWA \(EdgeHTML\).</span></span>  

1.  <span data-ttu-id="d7ecd-167">如果还没有 Microsoft Store，请从 Microsoft Store 安装 Microsoft [Edge DevTools][MicrosoftStoreEdgeDevtoolsPreview] Preview 应用。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-167">Install the [Microsoft Edge DevTools Preview][MicrosoftStoreEdgeDevtoolsPreview] app from the Microsoft Store if you do not already have it.</span></span>  
1.  <span data-ttu-id="d7ecd-168">PWA 网站启动并运行后，启动 DevTools 应用。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-168">With your PWA site up and running, launch the DevTools app.</span></span>  
1.  <span data-ttu-id="d7ecd-169">从Visual Studio，使用 () 命令启动 Windows 10 `Start Without Debugging` `Ctrl` + `F5` 应用。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-169">From Visual Studio, launch your Windows 10 app with the `Start Without Debugging` (`Ctrl`+`F5`) command.</span></span>  <span data-ttu-id="d7ecd-170">\(如果开发人员调试器处于活动状态，则 DevTools Visual Studio未正确附加。\) </span><span class="sxs-lookup"><span data-stu-id="d7ecd-170">\(The DevTools app does not attach properly if the Visual Studio debugger is active.\)</span></span>  
1.  <span data-ttu-id="d7ecd-171">在 DevTools 应用中，单击 本地调试目标选择器中的"刷新"按钮。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-171">In the DevTools app, click the **Refresh** button in the Local debug target chooser.</span></span>  <span data-ttu-id="d7ecd-172">此时应列出您的 PWA \(EdgeHTML\) 网站。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-172">Your PWA \(EdgeHTML\) site should now be listed.</span></span>  <span data-ttu-id="d7ecd-173">\(如果它还在浏览器窗口中运行，则它是列表中的该网站的最后一个实例。\) </span><span class="sxs-lookup"><span data-stu-id="d7ecd-173">\(If it is also running in a browser window, it is the last instance of that site in the list.\)</span></span>  
1.  <span data-ttu-id="d7ecd-174">单击 PWA \(EdgeHTML\) 列表以打开新的 DevTools 实例选项卡并开始调试。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-174">Click on your PWA \(EdgeHTML\) site listing to open a new DevTools instance tab and start debugging.</span></span>  
    
    ![Microsoft Edge DevTools 应用中的本地调试目标选择器](media/devtools-local.png)  
    
1.  <span data-ttu-id="d7ecd-176">你能够验证 DevTools 是否附加到 PWA-running-as-Windows-app。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-176">You are able to verify that DevTools is attached to your PWA-running-as-Windows-app.</span></span>  <span data-ttu-id="d7ecd-177">在 DevTools **控制台中**，键入：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-177">In the DevTools **Console**, type:</span></span>  
    
    ```shell
    window.Windows
    ```  
    
    <span data-ttu-id="d7ecd-178">这将返回包含所有顶级 `Windows Runtime` [WinRT](#find-windows-runtime-winrt-apis)命名空间的全局对象。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-178">This returns the global `Windows Runtime` object containing all of the [top-level WinRT namespaces](#find-windows-runtime-winrt-apis).</span></span>  <span data-ttu-id="d7ecd-179">这是到通用 [Windows][WindowsUWPIndex]平台的 PWA \(EdgeHTML\) 入口点，并且仅在进程运行过程中向作为 Windows 10 应用运行的 Web 应用公开 (在浏览器外部运行 `WWAHost.exe`) 。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-179">This is your PWA \(EdgeHTML\) entrypoint to the [Universal Windows Platform][WindowsUWPIndex], and only exposed to web apps that run as Windows 10 apps (running outside the browser, in a `WWAHost.exe` process).</span></span>  
    
## <span data-ttu-id="d7ecd-180">查找 Windows 运行时 (WinRT) API</span><span class="sxs-lookup"><span data-stu-id="d7ecd-180">Find Windows Runtime (WinRT) APIs</span></span>  

<span data-ttu-id="d7ecd-181">作为已安装的 Windows 应用 [，PWA \(EdgeHTML\) 具有][WindowsRuntime]本机 Windows 运行时 API 的完全访问权限;确定你需要使用哪些内容，获取必要的权限，并使用功能检测在受支持的环境中发送该 API 请求。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-181">As an installed Windows app, your [PWA \(EdgeHTML\) has full access to native Windows Runtime APIs][WindowsRuntime]; identify what you need to use, obtain the requisite permissions, and employ feature detection to send that API request on supported environments.</span></span>  <span data-ttu-id="d7ecd-182">演练此过程，为 PWA 的 Windows 桌面用户添加渐进式增强功能。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-182">Walk through this process to add a progressive enhancement for Windows desktop users of your PWA.</span></span>  

<span data-ttu-id="d7ecd-183">有很多方法可以标识 Windows PWA 所需的通用 Windows 平台 API，包括搜索全面的 [Windows 开发人员中心上的 UWP 文档][uwp/api/]、使用 Visual Studio 下载和运行 [UWP](#uwp-code-samples) 代码示例，以及浏览适用于 Windows 上的 PWA 的常见任务的代码段。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-183">There are a number of ways to identify the Universal Windows Platform APIs you need for your Windows PWA, including searching the comprehensive [UWP docs on Windows Dev Center][uwp/api/], downloading and running [UWP code samples](#uwp-code-samples) with Visual Studio, and browsing code snippets for common tasks for PWAs on Windows.</span></span>

<span data-ttu-id="d7ecd-184">有很多方法可以标识 Windows PWA 所需的通用 Windows 平台 API，包括搜索全面的 [Windows 开发人员中心上的 UWP 文档][uwp/api/]、使用 Visual Studio 下载和运行 [UWP](#uwp-code-samples) 代码示例，以及浏览 [Windows 10 (EdgeHTML) ][PwaIndexWindows10]上的 PWA 常见任务的代码段。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-184">There are a number of ways to identify the Universal Windows Platform APIs you need for your Windows PWA, including searching the comprehensive [UWP docs on Windows Dev Center][uwp/api/], downloading and running [UWP code samples](#uwp-code-samples) with Visual Studio, and browsing code snippets for common tasks for [PWAs on Windows 10 (EdgeHTML)][PwaIndexWindows10].</span></span>  

<span data-ttu-id="d7ecd-185">总之，WinRT API 在 JavaScript 中的运行方式与在 C# 中相同，因此你可以按照通用 [Windows][WindowsUWPIndex] 平台文档和 [API][UwpApiIndex] 参考来使用。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-185">Overall, WinRT APIs work in JavaScript the same way they do in C#, so you may follow the general [Universal Windows Platform documentation][WindowsUWPIndex] and [API Reference][UwpApiIndex] for usage.</span></span>  <span data-ttu-id="d7ecd-186">但是，请注意以下差异：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-186">However, please note the following differences:</span></span>  

*   <span data-ttu-id="d7ecd-187">JavaScript 中的 WinRT 功能  [使用不同的大小写约定][ScriptingJsinrtUsingWinRTCasingConventions]</span><span class="sxs-lookup"><span data-stu-id="d7ecd-187">WinRT features in JavaScript use  [different casing conventions][ScriptingJsinrtUsingWinRTCasingConventions]</span></span>  
*   <span data-ttu-id="d7ecd-188">[事件表示为传递给类方法的][ScriptingJsinrtHandlingWinRTEvents]字符串 `addEventListener` / `removeEventListener` 标识符</span><span class="sxs-lookup"><span data-stu-id="d7ecd-188">[Events are represented as string identifiers][ScriptingJsinrtHandlingWinRTEvents] passed to class `addEventListener`/`removeEventListener` methods</span></span>  
*   <span data-ttu-id="d7ecd-189">[异步方法][ScriptingJsinrtUsingWinRT] 使用 JavaScript Promise 模型</span><span class="sxs-lookup"><span data-stu-id="d7ecd-189">[Asynchronous methods][ScriptingJsinrtUsingWinRT] use the JavaScript Promise model</span></span>  
*   <span data-ttu-id="d7ecd-190">JavaScript 应用不支持命名空间中的 API，而 JavaScript 应用改为使用 `Windows.UI.Xaml` [EdgeHTML][DevGuideWhatsNew] 引擎 Web 呈现堆栈 \(HTML、CSS\) </span><span class="sxs-lookup"><span data-stu-id="d7ecd-190">APIs in the `Windows.UI.Xaml` namespace are not supported for JavaScript apps, which instead use the [EdgeHTML][DevGuideWhatsNew] engine web rendering stack \(HTML, CSS\)</span></span>  
    
<span data-ttu-id="d7ecd-191">有关详细信息，请参阅在 [JavaScript 中使用 Windows 运行时][WindowRuntimeUsingJavascript]。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-191">For more details, see [Using the Windows Runtime in JavaScript][WindowRuntimeUsingJavascript].</span></span>  

### <span data-ttu-id="d7ecd-192">UWP 代码示例</span><span class="sxs-lookup"><span data-stu-id="d7ecd-192">UWP code samples</span></span>  

<span data-ttu-id="d7ecd-193">查看通用 [Windows 平台 \(UWP\) 代码][MicrosoftDeveloperWindowsSamples] 示例存储库，以浏览常见 Windows 10 应用场景的 JavaScript 示例。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-193">Check out the [Universal Windows Platform \(UWP\) Code Samples][MicrosoftDeveloperWindowsSamples] repo to browse JavaScript examples for common Windows 10 app scenarios.</span></span>  <span data-ttu-id="d7ecd-194">尽管这些示例的 JS 版本使用 [WinJS][GithubWinjsWinjs] 库构建示例模板，但发送这些示例中演示的 WinRT API 请求不需要 WinJS。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-194">Although the JS versions of these samples use the [WinJS][GithubWinjsWinjs] library to structure the sample template, WinJS is not required for sending the WinRT API requests demonstrated in these samples.</span></span>  

> [!NOTE]
> <span data-ttu-id="d7ecd-195">如果你需要侦听应用的事件，可以使用以下本机 [`activated`][UwpApiWindowsUiWebuiWebapplicationActivated] WinRT API 完成此操作：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-195">If you need to listen for the [`activated`][UwpApiWindowsUiWebuiWebapplicationActivated] event for the app, you are able to do this using the following native WinRT API:</span></span>  
> 
> **<span data-ttu-id="d7ecd-196">使用此</span><span class="sxs-lookup"><span data-stu-id="d7ecd-196">Use this</span></span>**  
> 
> ```javascript
> Windows.UI.WebUI.WebUIApplication.addEventListener("activated", function (activatedEventArgs) {
>     // Check activatedEventArgs.kind and respond as needed
> });
> ```  
> 
> <span data-ttu-id="d7ecd-197">...与示例中使用的此类 WinJS 请求相反：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-197">... as opposed this type of WinJS request used in the samples:</span></span>  
> 
> **<span data-ttu-id="d7ecd-198">不是</span><span class="sxs-lookup"><span data-stu-id="d7ecd-198">Not this</span></span>**  
> 
> ```javascript
>     var page = WinJS.UI.Pages.define("/html/scenario1-launched.html", {
>         ready: function (element, options) {
>             // Check options.activationKind and respond as needed
>         }
>     });
> ```  

## <span data-ttu-id="d7ecd-199">从 PWA 发送来自 EdgeHTML (WinRT API) </span><span class="sxs-lookup"><span data-stu-id="d7ecd-199">Send WinRT API requests from your PWA (EdgeHTML)</span></span>  

<span data-ttu-id="d7ecd-200">此时，假设你想要为 PWA \(EdgeHTML\) 的 Windows 用户添加自定义上下文菜单，并且已标识 [Windows.UI.Popups][UwpApiWindowsUiPopups] 命名空间中所需的 API。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-200">At this point, pretend you want to add a custom context menu for Windows users of our PWA \(EdgeHTML\) and have identified the APIs you need in the [Windows.UI.Popups][UwpApiWindowsUiPopups] namespace.</span></span>  

<span data-ttu-id="d7ecd-201">为了从 PWA \(EdgeHTML\) 发送任何 WinRT API 请求，首先需要在 Windows 应用包清单 [\(](#set-application-content-uri-rules-acurs) \) 文件中建立必需的权限 \(或应用程序内容 URI 规则 `.appxmanifest` \) 。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-201">In order to send any WinRT APIs requests from our PWA \(EdgeHTML\), you first need to [establish the requisite permissions](#set-application-content-uri-rules-acurs) \(or, Application Content URI Rules\) in your Windows app package manifest \(`.appxmanifest`\) file.</span></span>  

<span data-ttu-id="d7ecd-202">如果其中任何 API 请求涉及访问用户资源（如图片或音乐）或设备功能（如相机或麦克风）的权限，则还需要将应用[](#app-capability-declarations)功能声明添加到应用包清单，以便 Windows 提示用户获取权限。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-202">If any of these API requests involve access to user resources like pictures or music, or to device features like the camera or microphone, you also need to add [app capability declarations](#app-capability-declarations) to the app package manifest in order for Windows to prompt the user for permission.</span></span>  <span data-ttu-id="d7ecd-203">如果稍后将 PWA \(EdgeHTML\) 发布到 Microsoft Store，这些必需的 [应用][MicrosoftSupportWindowsAppPermissions] 权限也会在应用商店一览中说明。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-203">If you later publish your PWA \(EdgeHTML\) to the Microsoft Store, these required [App permissions][MicrosoftSupportWindowsAppPermissions] are also noted in your store listing.</span></span>  

#### <span data-ttu-id="d7ecd-204">设置应用程序内容 URI 规则 (ACU) </span><span class="sxs-lookup"><span data-stu-id="d7ecd-204">Set Application Content URI Rules (ACURs)</span></span>  

<span data-ttu-id="d7ecd-205">通过 ACU（也称为 URL 允许列表）您可以授予 PWA \(EdgeHTML\) 直接访问 Windows 运行时 API 的 URL。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-205">Through ACURs, otherwise known as a URL allow list, you are able to give the URLs of your PWA \(EdgeHTML\) direct access to Windows Runtime APIs.</span></span>  <span data-ttu-id="d7ecd-206">在 Windows 操作系统级别，将正确的策略边界设置为允许 Web 服务器上托管的代码直接发送平台 API 请求。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-206">At the Windows OS level, the right policy bounds are set to allow code hosted on your web server to directly send platform API requests.</span></span>  <span data-ttu-id="d7ecd-207">将 PWA URL 指定为时，在应用程序包清单文件中定义这些边界 `ApplicationContentUriRules` 。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-207">You define these bounds in the app package manifest file when you specify your PWA URLs as `ApplicationContentUriRules`.</span></span>  

<span data-ttu-id="d7ecd-208">规则应包含应用的起始页和您希望作为应用页面包含的其他任何页面。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-208">Your rules should include the start page for your app and any other pages you want included as app pages.</span></span>  <span data-ttu-id="d7ecd-209">如果用户导航到规则中未包含的 URL，Windows 将在 Microsoft Edge 浏览器中打开目标 URL，而不是在独立 PWA \(EdgeHTML\) 窗口 \(process\) 中打开目标 URL。 `WWAHost.exe`</span><span class="sxs-lookup"><span data-stu-id="d7ecd-209">If your user navigates to a URL that is not included in your rules, Windows opens the target URL in the Microsoft Edge browser rather than your standalone PWA \(EdgeHTML\) window \(`WWAHost.exe` process\).</span></span>  <span data-ttu-id="d7ecd-210">还可以排除特定 URL。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-210">You may also exclude specific URLs.</span></span>  

<span data-ttu-id="d7ecd-211">有几种方法在规则中 `Match` 指定 URL：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-211">There are several ways to specify a URL `Match` in your rules:</span></span>  

*   <span data-ttu-id="d7ecd-212">确切的主机名</span><span class="sxs-lookup"><span data-stu-id="d7ecd-212">An exact hostname</span></span>  
*   <span data-ttu-id="d7ecd-213">已包括或排除含有某个主机名的任何子域的 URI 对应的主机名</span><span class="sxs-lookup"><span data-stu-id="d7ecd-213">A hostname for which a URI with any subdomain of that hostname is included or excluded</span></span>  
*   <span data-ttu-id="d7ecd-214">确切的 URI</span><span class="sxs-lookup"><span data-stu-id="d7ecd-214">An exact URI</span></span>  
*   <span data-ttu-id="d7ecd-215">包含查询属性的确切 URI</span><span class="sxs-lookup"><span data-stu-id="d7ecd-215">An exact URI containing a query property</span></span>  
*   <span data-ttu-id="d7ecd-216">部分路径和用于指示包含规则的特定文件扩展名的通配符。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-216">A partial path and a wildcard to indicate a particular file extension for an include rule</span></span>  
*   <span data-ttu-id="d7ecd-217">排除规则的相对路径</span><span class="sxs-lookup"><span data-stu-id="d7ecd-217">Relative paths for exclude rules</span></span>  
    
<span data-ttu-id="d7ecd-218">下面是一个文件中 ACU 的一些 `.appxmanifest` 示例：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-218">Here are a few examples of ACURs in a `.appxmanifest` file:</span></span>  

```xml
<Application
Id="App"
StartPage="https://contoso.com/home">
<uap:ApplicationContentUriRules>
    <uap:Rule Type="include" Match="https://contoso.com/" WindowsRuntimeAccess="all" />
    <uap:Rule Type="include" Match="https://*.contoso.com/" WindowsRuntimeAccess="all" />
    <uap:Rule Type="exclude" Match="https://contoso.com/excludethispage.aspx" />
</uap:ApplicationContentUriRules>
```  

<span data-ttu-id="d7ecd-219">在应用的 ADR 中定义的 URL 可以通过属性（接受以下值）被授予对 Windows 运行时 `WindowsRuntimeAccess` 的权限：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-219">URLs defined within the ACURs for your app are able to be granted permission to the Windows Runtime through the `WindowsRuntimeAccess` attribute, which accepts the following values:</span></span>  

*   `all`<span data-ttu-id="d7ecd-220">：远程 JavaScript 代码可以访问所有 WinRT API 和任何本地封装组件。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-220">: Remote JavaScript code has access to all WinRT APIs and any local packaged components.</span></span>  <span data-ttu-id="d7ecd-221">[Windows \(WinRT\) ) ][UwpApiIndex]命名空间已注入并呈现在脚本引擎中。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-221">The [Windows \(WinRT\))][UwpApiIndex] namespace is injected and present in the script engine.</span></span>  
*   `allowForWeb`<span data-ttu-id="d7ecd-222">：远程 JavaScript 代码访问仅限于本地打包组件，包括自定义 C++/C# 组件。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-222">: Remote JavaScript code access is limited to local packaged components, including custom C++/C# components.</span></span>  
*   `none`<span data-ttu-id="d7ecd-223">：默认值。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-223">: Default.</span></span>  <span data-ttu-id="d7ecd-224">指定的 URL 不具有任何平台访问权限。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-224">The specified URL has no platform access.</span></span>  
    
<span data-ttu-id="d7ecd-225">在本教程中，你已为单页应用设置 \(步骤 6 所需的唯一[](#set-up-and-run-your-universal-windows-app)ACUR，并运行应用部分\) 。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-225">In this tutorial, you already set the only ACUR that you need \(Step 6 of the previous [Set up and run your app](#set-up-and-run-your-universal-windows-app) section\) for your single-page app.</span></span>  <span data-ttu-id="d7ecd-226">你可以从网站设计器的内容 **URI** 面板确认 `package.appxmanifest` Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-226">You are able to confirm this from the **Content URIs** panel of the Visual Studio `package.appxmanifest` designer.</span></span>  

![appxmanifest Visual Studio的内容 URI 面板](media/vs-appxmanifest-editor-acurs.png)  

<span data-ttu-id="d7ecd-228">您还可以通过在解决方案资源管理器中右键单击文件并选择"查看代码 \(\) "来查看清单的原始 `package.appxmanifest` Visual Studio  `F7` XML。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-228">You are also able to view the raw XML of your manifest by right-clicking your `package.appxmanifest` file in Visual Studio Solution Explorer and selecting **View Code** \(`F7`\).</span></span>  <span data-ttu-id="d7ecd-229">若要切换回设计器视图，请选择 **"视图**设计器"\(`Shift` + `F7` \) 。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-229">To toggle back to the Designer view, select **View Designer** \(`Shift`+`F7`\).</span></span>  

#### <span data-ttu-id="d7ecd-230">应用功能声明</span><span class="sxs-lookup"><span data-stu-id="d7ecd-230">App capability declarations</span></span>  

<span data-ttu-id="d7ecd-231">如果你的应用需要以编程方式访问用户资源（如图片或音乐）或设备（如相机或麦克风），则必须在应用包清单文件中[][WindowsUwpPackagingAppCapabilities]包含相应的应用功能声明。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-231">If your app needs programmatic access to user resources like pictures or music, or to devices like a camera or a microphone, you must include the corresponding [App capability declarations][WindowsUwpPackagingAppCapabilities] in your app package manifest file.</span></span>  <span data-ttu-id="d7ecd-232">三种应用功能声明类别如下所示：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-232">There are three app capability declaration categories:</span></span>  

*   <span data-ttu-id="d7ecd-233">适用于大多数常见应用场景的[通用功能][WindowsUwpPackagingAppCapabilitiesGeneralUse]。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-233">[General-use capabilities][WindowsUwpPackagingAppCapabilitiesGeneralUse] that apply to most common app scenarios.</span></span>  
*   <span data-ttu-id="d7ecd-234">允许你的应用访问外围设备和内部设备的[设备功能][WindowsUwpPackagingAppCapabilitiesDevice]。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-234">[Device capabilities][WindowsUwpPackagingAppCapabilitiesDevice] that allow your app to access peripheral and internal devices.</span></span>  
*   <span data-ttu-id="d7ecd-235">[支持企业方案][WindowsUwpPackagingAppCapabilitiesSpecialRestricted] 并需要 Microsoft Store 公司帐户的特殊用途功能。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-235">[Special-use capabilities][WindowsUwpPackagingAppCapabilitiesSpecialRestricted] that support enterprise scenarios and require a Microsoft Store company account.</span></span>  <span data-ttu-id="d7ecd-236">有关公司帐户的详细信息，请参阅[帐户类型、位置和费用][WindowsUwpPublishAccountTypesLocationsFees]。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-236">For more info about company accounts, see [Account types, locations, and fees][WindowsUwpPublishAccountTypesLocationsFees].</span></span>
    
<span data-ttu-id="d7ecd-237">Microsoft Store 应用页面列出了你在应用包清单中声明的所有功能，因此请务必仅指定你的应用实际使用的功能。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-237">Your Microsoft Store app page lists all the capabilities you declare in your app package manifest, so be sure to only specify the capabilities that your app actually uses.</span></span>

<span data-ttu-id="d7ecd-238">某些功能为应用提供对敏感资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-238">Some capabilities provide apps access to sensitive resources.</span></span>  <span data-ttu-id="d7ecd-239">这些资源被视为敏感资源，因为每个资源都能访问用户的个人数据或花费用户金钱。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-239">These resources are considered sensitive because each is able to access the user's personal data or cost the user money.</span></span>  <span data-ttu-id="d7ecd-240">隐私设置由 Windows 10[][BingResultsWindows10Settings]设置应用管理，允许用户动态控制对敏感资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-240">Privacy settings, managed by the Windows 10 [Settings][BingResultsWindows10Settings] app, let the user dynamically control access to sensitive resources.</span></span>  <span data-ttu-id="d7ecd-241">因此，你的应用不要假定敏感资源始终可用，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-241">Thus, it is important that your app does not assume a sensitive resource is always available.</span></span>  <span data-ttu-id="d7ecd-242">有关访问敏感资源的详细信息，请参阅[隐私感知应用指南][WindowsUwpSecurityIndex]。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-242">For more info about accessing sensitive resources, see [Guidelines for privacy-aware apps][WindowsUwpSecurityIndex].</span></span>  

<span data-ttu-id="d7ecd-243">你通过声明应用的程序包清单中的功能来请求访问。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-243">You request access by declaring capabilities in the package manifest for your app.</span></span>  <span data-ttu-id="d7ecd-244">在Visual Studio中，你可以从 package.appxmanifest 设计器的功能面板中完成此操作。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-244">In Visual Studio, you are able to do this from the **Capabilities** panel of the package.appxmanifest designer.</span></span>  

![appxmanifest Visual Studio的功能面板](media/vs-appxmanifest-editor-capabilities.png)  

<span data-ttu-id="d7ecd-246">在本教程中，只需要默认的 Internet \(Client\) 功能，因此无需执行进一步的操作。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-246">In this tutorial, only the default Internet \(Client\) capability is required, so no further action is needed.</span></span>  

### <span data-ttu-id="d7ecd-247">使用功能检测调用 WinRT</span><span class="sxs-lookup"><span data-stu-id="d7ecd-247">Use feature detection to invoke WinRT</span></span>  

<span data-ttu-id="d7ecd-248">为确保 PWA 受众在所有平台上获得质量基线体验，可以使用 WinRT 功能检测逐步增强 Windows 上的 PWA 体验。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-248">To ensure a quality baseline experience for your PWA audience across all platforms, you progressively enhance your PWA experience on Windows using WinRT feature detection.</span></span>  <span data-ttu-id="d7ecd-249">这样，你将能够确保特定于 Windows 的代码仅在 WinRT API 可用且适用的上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-249">This way, you are able to be sure your Windows-specific code is only run in a context where WinRT APIs are available and applicable.</span></span>  

<span data-ttu-id="d7ecd-250">功能检测可能与查找对象 `Windows` \([WinRT][UwpApiIndex]命名空间的入口点 \) 一样简单，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-250">Feature detection may be as simple as looking for the `Windows` object \(the entrypoint to the [WinRT namespace][UwpApiIndex]\) as below:</span></span>  

```javascript
if(window.Windows){
    /*Run code that sends Windows API requests */
}
```  

<span data-ttu-id="d7ecd-251">但是，鉴于并非所有 Windows API 都可用于所有 [Windows 10][UwpExtensionSdkDeviceFamiliesOverview]设备类型，使用更具体的功能检测进一步限定要发送的 API 请求的命名空间通常很有用：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-251">However, given that not all Windows APIs are available on all [Windows 10 device types][UwpExtensionSdkDeviceFamiliesOverview], it is generally useful to use more specific feature detection to further qualify the namespace of the API request you are sending:</span></span>  

```javascript
if(window.Windows && Windows.Media.SpeechRecognition){
    /*Run code that sends Windows API requests */
}
```  

<span data-ttu-id="d7ecd-252">借助该背景，你已准备好添加一些 WinRT 代码来实现自定义上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-252">With that background, you are ready to add some WinRT code to implement a custom context menu.</span></span>  <span data-ttu-id="d7ecd-253">如果你使用的是"渐进 Web 应用入门"中 [的示例][PwaGetStarted]PWA：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-253">If you are using the sample PWA from [Get started with Progressive Web Apps][PwaGetStarted]:</span></span>

1.  <span data-ttu-id="d7ecd-254">打开Visual Studio PWA 网站项目。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-254">Open Visual Studio to your PWA site project.</span></span>  
1.  <span data-ttu-id="d7ecd-255">在解决方案资源管理器中，打开该文件，并添加以下行，它正下方为服务 `views\layout.pug` `script` 工作者的引用：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-255">In Solution Explorer, open the `views\layout.pug` file and add the following line, right below the `script` reference for your service worker:</span></span>
    
    ```xml
    script(src='/javascripts/site.js')
    ```  
    
1.  <span data-ttu-id="d7ecd-256">在解决方案资源管理器中，右键单击 `javascripts` 该文件夹并  >  **添加新文件...**</span><span class="sxs-lookup"><span data-stu-id="d7ecd-256">In Solution Explorer, right-click on the `javascripts` folder and **Add** > **New File...**.</span></span>
1.  <span data-ttu-id="d7ecd-257">将文件命名： `site.js` ，然后复制以下代码：</span><span class="sxs-lookup"><span data-stu-id="d7ecd-257">Name your file: `site.js`, and copy in the following code:</span></span>
    
    ```javascript
    if (window.Windows && Windows.UI.Popups) {
        document.addEventListener('contextmenu', function (e) {

            // Build the context menu
            var menu = new Windows.UI.Popups.PopupMenu();
            menu.commands.append(new Windows.UI.Popups.UICommand("Option 1", null, 1));
            menu.commands.append(new Windows.UI.Popups.UICommandSeparator);
            menu.commands.append(new Windows.UI.Popups.UICommand("Option 2", null, 2));

            // Convert from webpage to WinRT coordinates
            function pageToWinRT(pageX, pageY) {
                var zoomFactor = document.documentElement.msContentZoomFactor;
                return {
                    x: (pageX - window.pageXOffset) * zoomFactor,
                    y: (pageY - window.pageYOffset) * zoomFactor
                };
            }

            // When the menu is invoked, execute the requested command
            menu.showAsync(pageToWinRT(e.pageX, e.pageY)).done(function (invokedCommand) {
                if (invokedCommand !== null) {
                    switch (invokedCommand.id) {
                        case 1:
                            console.log('Option 1 selected');
                            // Invoke code for option 1
                            break;
                        case 2:
                            console.log('Option 2 selected');
                            // Invoke code for option 2
                            break;
                        default:
                            break;
                    }
                } else {
                    // The command is null if no command was invoked.
                    console.log("Context menu dismissed");
                }
            });
        }, false);
    }
    ```
    
1.  <span data-ttu-id="d7ecd-258">比较在浏览器 \(中从 PWA 网站项目\) 运行 PWA 时与从通用 Windows 应用项目\(在 Windows 应用窗口 \) 中运行 `F5` PWA 时上下文菜单行为。 `F5`</span><span class="sxs-lookup"><span data-stu-id="d7ecd-258">Compare the context menu behavior when you run your PWA in the browser \(`F5` from your PWA site project\) versus from inside the Windows app window \(`F5` from your Universal Windows app project\).</span></span>  <span data-ttu-id="d7ecd-259">在浏览器中，右键单击会为你提供 Microsoft Edge 默认上下文菜单，而此时将显示 `WWAHost.exe` 自定义菜单。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-259">In the browser, right-clicking gives you the Microsoft Edge default context menu, whereas in the `WWAHost.exe` process, your custom menu now appears.</span></span>  
    
    | <span data-ttu-id="d7ecd-260">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d7ecd-260">Microsoft Edge</span></span> | <span data-ttu-id="d7ecd-261">Windows 10 应用</span><span class="sxs-lookup"><span data-stu-id="d7ecd-261">Windows 10 app</span></span> |  
    |:--- |:---- |  
    | ![浏览器默认上下文菜单](media/browser-context-menu.png) | ![应用自定义上下文菜单](media/app-context-menu.png) |  
    
<span data-ttu-id="d7ecd-264">希望你现在有一个基础，可以逐步增强 Windows 上的 PBA。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-264">Hopefully you now have a solid foundation for progressively enhancing your PWAs on Windows.</span></span>  <span data-ttu-id="d7ecd-265">如果遇到问题或内容不明确，请发送评论！</span><span class="sxs-lookup"><span data-stu-id="d7ecd-265">If you run into questions or anything is unclear, please send a comment!</span></span>  

## <span data-ttu-id="d7ecd-266">深入探索</span><span class="sxs-lookup"><span data-stu-id="d7ecd-266">Going further</span></span>

<span data-ttu-id="d7ecd-267">[Windows 开发人员中心][MicrosoftDeveloperWindowsApps]是 Windows 应用生成的所有阶段的完整参考，从入门到[][MicrosoftDeveloperWindowsAppsGetStarted]设计、开发和发布到[][MicrosoftDeveloperWindowsAppsDesign]Microsoft [][MicrosoftDeveloperWindowsAppsDevelop]Store。 [][MicrosoftDeveloperStorePublishApps]</span><span class="sxs-lookup"><span data-stu-id="d7ecd-267">The [Windows Dev Center][MicrosoftDeveloperWindowsApps] is your complete reference for all stages of Windows app building, from [getting started][MicrosoftDeveloperWindowsAppsGetStarted], to [designing][MicrosoftDeveloperWindowsAppsDesign], [developing][MicrosoftDeveloperWindowsAppsDevelop], and [publishing][MicrosoftDeveloperStorePublishApps] to the Microsoft Store.</span></span>  

<span data-ttu-id="d7ecd-268">有关通用 Windows 平台 \(UWP\) 以及如何面向不同 Windows 10 设备系列的通用概述，请参阅通用 Windows 平台 [简介][WindowsUWPGetStartedGuide]。</span><span class="sxs-lookup"><span data-stu-id="d7ecd-268">For a general overview on the Universal Windows Platform \(UWP\) and how to target different Windows 10 device families, see [Intro to the Universal Windows Platform][WindowsUWPGetStartedGuide].</span></span>  

<span data-ttu-id="d7ecd-269">当你准备好时，下面是 \(和原因！\) 将 PWA 提交[到 Microsoft Store。](./microsoft-store.md)</span><span class="sxs-lookup"><span data-stu-id="d7ecd-269">And when you are ready, here is how \(and why!\) to [Submit your PWA to the Microsoft Store](./microsoft-store.md).</span></span>  

<!-- links -->  

[PwaGetStarted]: ./get-started.md "渐进式 Web 应用入门 |Microsoft Docs"  
[PwaIndexWindows10]: ./index.md#pwas-on-windows-10-edgehtml "Windows 10 上的 PWA (EdgeHTML) - Windows 上的渐进式 Web 应用 |Microsoft Docs"  
[DevToolsGuide]: ../devtools-guide/index.md "Microsoft Edge (EdgeHTML) 开发人员工具 |Microsoft Docs"  
[DevToolsGuideMicrosoftStoreApp]: ../devtools-guide/index.md#microsoft-store-app "Microsoft Store 应用 - Microsoft Edge (EdgeHTML) 开发人员工具 |Microsoft Docs"  
[DevToolsGuideServiceWorkers]: ../devtools-guide/service-workers.md "服务工作人员 |Microsoft Docs"  
[DevToolsProtocol01ClientsEdgePreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview - DevTools 协议客户端 |Microsoft Docs"  
[DevGuideWhatsNew]: ../dev-guide/whats-new.md "EdgeHTML 中的新增功能 |Microsoft Docs"  
[WindowsRuntime]: ../windows-runtime/index.md "适用于 JavaScript (WinRT) Windows 运行时 |Microsoft Docs"  
[WindowRuntimeUsingJavascript]: ../windows-runtime/using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时 |Microsoft Docs"  

[ScriptingJsinrtHandlingWinRTEvents]: /scripting/jswinrt/handling-windows-runtime-events-in-javascript "在 JavaScript 中处理 Windows 运行时事件 |Microsoft Docs"  
[ScriptingJsinrtUsingWinRT]: /scripting/jswinrt/using-windows-runtime-asynchronous-methods "使用 Windows 运行时异步方法 |Microsoft Docs"  
[ScriptingJsinrtUsingWinRTCasingConventions]:  /scripting/jswinrt/using-the-windows-runtime-in-javascript#casing-conventions-with-windows-runtime-features "Windows 运行时功能的大小写约定 - 在 JavaScript 中使用 Windows 运行时 |Microsoft Docs"  
[UwpApiIndex]: /uwp/api/index "Windows UWP 命名空间 |Microsoft Docs"  
[UwpApiWindowsUiPopups]: /uwp/api/windows.ui.popups "Windows.UI.Popups 命名空间 |Microsoft Docs"  
[UwpApiWindowsUiWebuiWebapplicationActivated]: /uwp/api/windows.ui.webui.webuiapplication.activated "WebUIApplication.Activated 事件 |Microsoft Docs"  
[UwpExtensionSdkDeviceFamiliesOverview]: /uwp/extension-sdks/device-families-overview "设备系列概述 |Microsoft Docs"  
[UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest]: /uwp/schemas/appxpackage/uapmanifestschema/generate-package-manifest "如何Visual Studio应用包清单 |Microsoft Docs"  
[WindowsUWPIndex]: /windows/uwp/index "通用 Windows 平台文档 |Microsoft Docs"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide "什么是通用 Windows 平台 (UWP) 应用？ |Microsoft Docs"  
[WindowsUWPGetStartedEnable]: /windows/uwp/get-started/enable-your-device-for-development "启用设备进行开发 |Microsoft Docs"  
[WindowsUwpSecurityIndex]: /windows/uwp/security/index "安全 |Microsoft Docs"  
[WindowsUwpPublishAccountTypesLocationsFees]: /windows/uwp/publish/account-types-locations-and-fees "帐户类型、位置和费用 |Microsoft Docs"  
[WindowsUwpPackagingAppCapabilitiesSpecialRestricted]: /windows/uwp/packaging/app-capability-declarations#special-and-restricted-capabilities "受限功能 |Microsoft Docs"  
[WindowsUwpPackagingAppCapabilitiesDevice]: /windows/uwp/packaging/app-capability-declarations#device-capabilities "设备功能 |Microsoft Docs"  
[WindowsUwpPackagingAppCapabilitiesGeneralUse]: /windows/uwp/packaging/app-capability-declarations#general-use-capabilities "通用功能 |Microsoft Docs"  
[WindowsUwpPackagingAppCapabilities]: /windows/uwp/packaging/app-capability-declarations "应用功能声明 |Microsoft Docs"  

[BingResultsWindows10Settings]: https://binged.it/2lOGSH0 "windows 10 设置 - 必应"  
[GithubWinjsWinjs]: https://github.com/winjs/winjs "winjs/winjs |GitHub"  
[MicrosoftDeveloperStorePublishApps]: https://developer.microsoft.com/store/publish-apps/index "发布 Windows 应用和游戏"  
[MicrosoftDeveloperWindowsApps]: https://developer.microsoft.com/windows/apps/index "通用 Windows 平台文档"  
[MicrosoftDeveloperWindowsAppsDesign]: https://developer.microsoft.com/windows/apps/design/index "设计和编码 Windows 应用"  
[MicrosoftDeveloperWindowsAppsDevelop]: https://developer.microsoft.com/windows/apps/develop/index "开发 UWP 应用"  
[MicrosoftDeveloperWindowsAppsGetStarted]: https://developer.microsoft.com/windows/apps/getstarted/index "Windows 10 应用入门"  
[MicrosoftDeveloperWindowsSamples]: https://developer.microsoft.com/windows/samples "代码示例"  
[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools Preview"  
[MicrosoftSupportWindowsAppPermissions]: https://support.microsoft.com/help/10557/windows-10-app-permissions "应用权限"  
[MicrosoftVisualStudioDownloads]: https://visualstudio.microsoft.com/downloads "下载"  
[MicrosoftVisualStudioPreview]: https://visualstudio.microsoft.com/vs/preview "Visual Studio预览"  
[PreviousVSDownloads]: https://visualstudio.microsoft.com/vs/older-downloads/ "Visual Studio下载"  
