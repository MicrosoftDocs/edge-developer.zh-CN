---
description: 通过本机应用功能逐步增强 PWA for Windows
title: 定制你的 PWA for Windows
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 web 应用、PWA、Edge、Windows、WinRT、UWP、EdgeHTML
ms.openlocfilehash: 5bad708db5b13517fd1887214a5e1d5457796ee2
ms.sourcegitcommit: e07de36ee9fbe20422ffc2c62b98839851e1b02b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2020
ms.locfileid: "10604009"
---
# <span data-ttu-id="789bf-104">定制你的 PWA （EdgeHTML） for Windows</span><span class="sxs-lookup"><span data-stu-id="789bf-104">Tailor your PWA (EdgeHTML) for Windows</span></span>  

<span data-ttu-id="789bf-105">Windows 10 上安装的 PWAs 可享受以[通用 Windows 平台 \ （UWP \）][WindowsUWPGetStartedGuide]应用的形式运行的[所有好处][PwaIndexWindows10]，包括通过 windows 应用沙盒沙盒安全和对 Windows 运行时的完全访问权限[\ （WinRT \））][UwpApiIndex] api，包括以下内容的保护：</span><span class="sxs-lookup"><span data-stu-id="789bf-105">PWAs installed on Windows 10 enjoy [all the benefits][PwaIndexWindows10] of running as [Universal Windows Platform \(UWP\)][WindowsUWPGetStartedGuide] apps, including protection through Windows app sandboxing security and full access to [Windows Runtime \(WinRT\))][UwpApiIndex] APIs, including those for:</span></span>  

*   <span data-ttu-id="789bf-106">控制设备功能 \ （如相机、麦克风、GPS \）</span><span class="sxs-lookup"><span data-stu-id="789bf-106">Controlling device features \(such as camera, microphone, GPS\)</span></span>  
*   <span data-ttu-id="789bf-107">访问用户资源 \ （如 "日历"、"联系人"、"文档"、"音乐"）</span><span class="sxs-lookup"><span data-stu-id="789bf-107">Accessing user resources \(such as calendar, contacts, documents, music\)</span></span>  
*   <span data-ttu-id="789bf-108">通过 Cortana 语音命令启动/浏览应用</span><span class="sxs-lookup"><span data-stu-id="789bf-108">Launching / navigating your app through Cortana voice commands</span></span>  
*   <span data-ttu-id="789bf-109">与 Windows 操作系统集成 \ （通过 Windows 操作中心、桌面任务栏和上下文菜单 \）</span><span class="sxs-lookup"><span data-stu-id="789bf-109">Integrating with the Windows OS \(through the Windows Action Center, desktop taskbar, and context menus\)</span></span>  

<span data-ttu-id="789bf-110">...这些只是 Windows 上的 PWA 的几个新增可能性 \ （EdgeHTML \）！</span><span class="sxs-lookup"><span data-stu-id="789bf-110">... and these are only a few of the added possibilities for your PWA \(EdgeHTML\) on Windows!</span></span>  

<span data-ttu-id="789bf-111">本指南介绍如何以 Windows 10 应用的形式安装、运行和增强 PWA \ （EdgeHTML \），同时还可确保跨浏览器和跨平台兼容性。</span><span class="sxs-lookup"><span data-stu-id="789bf-111">This guide shows you how to install, run, and enhance your PWA \(EdgeHTML\) as a Windows 10 app, while still ensuring cross-browser and cross-platform compatibility.</span></span>  

## <span data-ttu-id="789bf-112">必备条件</span><span class="sxs-lookup"><span data-stu-id="789bf-112">Prerequisites</span></span>  

*   <span data-ttu-id="789bf-113">现有 PWA \ （或托管 web 应用 \），它可以是实时网站或 localhost 网站。</span><span class="sxs-lookup"><span data-stu-id="789bf-113">An existing PWA \(or hosted web app\), either a live or localhost site.</span></span>  <span data-ttu-id="789bf-114">本指南使用[渐进式 Web 应用][PwaGetStarted]中的示例 PWA。</span><span class="sxs-lookup"><span data-stu-id="789bf-114">This guide uses the sample PWA from [Get started with Progressive Web Apps][PwaGetStarted].</span></span>  
*   <span data-ttu-id="789bf-115">下载 \ （免费 \） [Visual Studio 社区 2017][MicrosoftVisualStudio|::ref1::|]。</span><span class="sxs-lookup"><span data-stu-id="789bf-115">Download the \(free\) [Visual Studio Community 2017][MicrosoftVisualStudio|::ref1::|].</span></span>  <span data-ttu-id="789bf-116">你还可以使用专业版、企业版或[预览版][MicrosoftVisualStudioPreview]版本。</span><span class="sxs-lookup"><span data-stu-id="789bf-116">You are also able to use the Professional, Enterprise, or [Preview][MicrosoftVisualStudioPreview] editions.</span></span>  <span data-ttu-id="789bf-117">从 Visual Studio 安装程序中，选择以下工作负荷：</span><span class="sxs-lookup"><span data-stu-id="789bf-117">From the Visual Studio Installer, choose the following Workloads:</span></span>  
    *   **<span data-ttu-id="789bf-118">通用 Windows 平台开发</span><span class="sxs-lookup"><span data-stu-id="789bf-118">Universal Windows Platform development</span></span>**  

## <span data-ttu-id="789bf-119">设置和运行通用 Windows 应用</span><span class="sxs-lookup"><span data-stu-id="789bf-119">Set up and run your Universal Windows app</span></span>  

<span data-ttu-id="789bf-120">作为 Windows 10 应用安装的 PWA \ （EdgeHTML \）独立于浏览器运行，位于单独的 \ （ `WWAHost.exe` 进程 \）窗口中。</span><span class="sxs-lookup"><span data-stu-id="789bf-120">A PWA \(EdgeHTML\) installed as a Windows 10 app runs independently from the browser, in a standalone \(`WWAHost.exe` process\) window.</span></span>  <span data-ttu-id="789bf-121">启用此操作只需要一个包含托管 web 应用的轻型应用包装程序，你可以使用 Visual Studio 项目模板快速设置该包装 `Progressive Web App (Universal Windows)` 。</span><span class="sxs-lookup"><span data-stu-id="789bf-121">Enabling this simply requires a lightweight app wrapper that contains your hosted web app, which you are able to quickly set up using the Visual Studio `Progressive Web App (Universal Windows)` project template.</span></span>  <span data-ttu-id="789bf-122">\ （所有应用逻辑，包括发送本机 Windows 运行时 API 请求，仍在原始 web 应用代码中发生。）</span><span class="sxs-lookup"><span data-stu-id="789bf-122">\(All your app logic, including sending native Windows Runtime API requests, still happens in your original web app code.\)</span></span>  

<span data-ttu-id="789bf-123">在 Visual Studio 中设置 Windows 应用开发环境。</span><span class="sxs-lookup"><span data-stu-id="789bf-123">Set up your Windows app development environment in Visual Studio.</span></span>  

1.  <span data-ttu-id="789bf-124">在 Windows 设置中，启用 "[开发人员模式][WindowsUWPGetStartedEnable]"。</span><span class="sxs-lookup"><span data-stu-id="789bf-124">In your Windows Settings, turn on [Developer mode][WindowsUWPGetStartedEnable].</span></span>  <span data-ttu-id="789bf-125">\ （ `developer mode` 在 Windows searchbar 中键入以找到它。）</span><span class="sxs-lookup"><span data-stu-id="789bf-125">\(Type `developer mode` in the Windows searchbar to find it.\)</span></span>  
1.  <span data-ttu-id="789bf-126">启动 Visual Studio 并**创建新项目 ...**</span><span class="sxs-lookup"><span data-stu-id="789bf-126">Launch Visual Studio and **Create a new project...**</span></span>  
1.  <span data-ttu-id="789bf-127">选择 "c # **Windows 应用程序打包" 项目**模板。</span><span class="sxs-lookup"><span data-stu-id="789bf-127">Select the C# **Windows Application Packaging Project** template.</span></span>  <span data-ttu-id="789bf-128">如果你使用的是早期版本的 Visual Studio，请在 "**托管 Web 应用（通用 windows）** " 或 "**渐进 Web 应用（通用 windows）**" 下查找等效模板。</span><span class="sxs-lookup"><span data-stu-id="789bf-128">If you are using a previous version of Visual Studio, find the equivalent template under **Hosted Web App (Universal Windows)** or **Progressive Web App (Universal Windows)**.</span></span>  
1.  <span data-ttu-id="789bf-129">选择默认的 Windows 10 `Target version` \ （最新版本 \）和 `Minimum version` \ （内部版本10586或更高版本 \），然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="789bf-129">Select the default Windows 10 `Target version` \(most recent release\) and `Minimum version` \(build 10586 or higher\) and click **OK**.</span></span>  

    ![UWP 项目目标版本的 Visual Studio 选择对话框](media/vs-target-min-version.png)  

    <span data-ttu-id="789bf-131">新项目将在 package.appxmanifest 设计器打开的情况中加载。</span><span class="sxs-lookup"><span data-stu-id="789bf-131">Your new project loads with the package.appxmanifest designer open.</span></span>  <span data-ttu-id="789bf-132">你可以在此处配置应用的详细信息，包括程序包标识、程序包依赖项、所需功能、可视化元素和扩展性点。</span><span class="sxs-lookup"><span data-stu-id="789bf-132">This is where you configure the details of your app, including package identity, package dependencies, required capabilities, visual elements, and extensibility points.</span></span>  <span data-ttu-id="789bf-133">这是在应用开发期间使用的应用包清单的一个易于配置的临时版本。</span><span class="sxs-lookup"><span data-stu-id="789bf-133">This is an easily configurable, temporary version of the app package manifest used during app development.</span></span>  
    <span data-ttu-id="789bf-134">当你生成应用项目时，Visual Studio 将从此元数据[生成一个 package.appxmanifest][UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest]文件，用于安装和运行你的应用。</span><span class="sxs-lookup"><span data-stu-id="789bf-134">When you build your app project, [Visual Studio generates an AppxManifest.xml][UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest] file from this metadata, which is used to install and run your app.</span></span>  <span data-ttu-id="789bf-135">每当更新文件时 `package.appxmanifest` ，请确保重新生成项目，这样两个项目都将在 `AppxManifest.xml` 运行时反映出来。</span><span class="sxs-lookup"><span data-stu-id="789bf-135">Whenever you update your `package.appxmanifest` file, be sure to rebuild the project so both are reflected in your `AppxManifest.xml` at runtime.</span></span>  

1.  <span data-ttu-id="789bf-136">在清单设计器 "**应用程序**" 面板中，输入 PWA 的 URL 作为 `Start page` 。</span><span class="sxs-lookup"><span data-stu-id="789bf-136">In the manifest designer **Application** panel, enter the URL of your PWA as the `Start page`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="789bf-137">对于指定为的所有 https \ （secure、remote \） url，服务工作者均受支持 `StartPage` 。</span><span class="sxs-lookup"><span data-stu-id="789bf-137">Service workers are supported for all https \(secure, remote\) urls specified as the `StartPage`.</span></span>  <span data-ttu-id="789bf-138">默认情况下，对于指定本地起始页的 web 应用，不支持服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="789bf-138">Service workers are not supported by default for web apps that specify a local start page.</span></span>  <span data-ttu-id="789bf-139">若要启用服务工作人员对这些情况的支持，请将显式[ApplicationContentUriRules](#set-application-content-uri-rules-acurs)条目添加到清单中，例如：</span><span class="sxs-lookup"><span data-stu-id="789bf-139">To enable service worker support for these cases, add an explicit [ApplicationContentUriRules](#set-application-content-uri-rules-acurs) entry to the manifest, for example:</span></span> `<uap:Rule Match="http://web-platform.test/" Type="include" uap5:ServiceWorker="true"/>`  
    
    ![Package.appxmanifest 设计器的应用程序面板](media/vs-manifest-application.png)  
    
    <span data-ttu-id="789bf-141">您也可以根据需要修改 `Display name` 和 `Description` 。</span><span class="sxs-lookup"><span data-stu-id="789bf-141">You are able to also modify the `Display name` and `Description` as you like.</span></span>  
1.  <span data-ttu-id="789bf-142">将此文件 \ （或您选择的另一个512x512 图像）保存到您的桌面。</span><span class="sxs-lookup"><span data-stu-id="789bf-142">Save this file \(or another 512x512 image of your choosing\) to your desktop.</span></span>  
    <span data-ttu-id="789bf-143">然后，在 "清单设计器**视觉资源**" 面板中，单击 " `Source` 字段 **...** " 按钮，将其选择为源文件，然后单击 "**生成**"。</span><span class="sxs-lookup"><span data-stu-id="789bf-143">Then, in the manifest designer **Visual Assets** panel, click on the `Source` field **...** button, select it as your source file, and click **Generate**.</span></span>  <span data-ttu-id="789bf-144">\ （然后单击 **"确定"** 以覆盖默认占位符图像 \）。</span><span class="sxs-lookup"><span data-stu-id="789bf-144">\(Then click **OK** to overwrite the default placeholder images\).</span></span>  
    
    ![程序包 package.appxmanifest 设计器的 "视觉资源" 面板](media/vs-manifest-visual-assets.png)  
    
    <span data-ttu-id="789bf-146">这将生成在应用商店中安装、运行、启动和分发应用的基本视觉资源。</span><span class="sxs-lookup"><span data-stu-id="789bf-146">This generates the basic visual assets for installing, running, launching, and distributing your app in the store.</span></span>  
    <span data-ttu-id="789bf-147">如果看到 `X` 表示缺少图像的任何红色 \ （\）错误，您可以单击 "..." 按钮 **...** ，手动从生成的映像中选择文件。</span><span class="sxs-lookup"><span data-stu-id="789bf-147">If you see any red \(`X`\) errors indicating missing images, you are able to click on the **...** buttons to manually select a file from the generated images.</span></span>  
1.  <span data-ttu-id="789bf-148">在清单设计器的 "**内容 uri** " 面板中， `http://example.com` 将替换为 PWA 的位置 \ （如 `Rule`  =  `include` `WinRT Access`  =  `All` \）。</span><span class="sxs-lookup"><span data-stu-id="789bf-148">In the manifest designer **Content URIs** panel, replace `http://example.com` with the location of your PWA \(such that `Rule` = `include` and `WinRT Access` = `All`\).</span></span>  
    <span data-ttu-id="789bf-149">这将授予 PWA 在作为 Windows 10 应用运行时发送本机 Windows 运行时 \ （WinRT） API 请求的权限，稍后将对此进行介绍。</span><span class="sxs-lookup"><span data-stu-id="789bf-149">This grants your PWA permission to send native Windows Runtime \(WinRT\) API requests when running as a Windows 10 app, which is covered a bit later.</span></span>   <span data-ttu-id="789bf-150">如果你的实际 PWA 不需要 WinRT 访问，你可以将 `WinRT Access` 该值转换为 `None` 。</span><span class="sxs-lookup"><span data-stu-id="789bf-150">If your actual PWA does not require WinRT access, you are able to switch the `WinRT Access` value to `None`.</span></span>  <span data-ttu-id="789bf-151">无论是哪种情况，都要确保将默认 `http://example.com` 字符串与 PWA 的 URI 进行了细分，或者你的应用无法在运行时正确加载。</span><span class="sxs-lookup"><span data-stu-id="789bf-151">Either way, be sure to sub out the default `http://example.com` string with the URI of your PWA, or your app is not able to properly load at runtime.</span></span>  
    <span data-ttu-id="789bf-152">你已准备好将 PWA 作为 Windows 10 应用进行运行和调试。</span><span class="sxs-lookup"><span data-stu-id="789bf-152">You are ready to run and debug your PWA as a Windows 10 app.</span></span>  <span data-ttu-id="789bf-153">如果您使用 localhost 网站逐步完成本指南，请确保它正在运行。</span><span class="sxs-lookup"><span data-stu-id="789bf-153">If you are using a localhost site to step through this guide, make sure it is running.</span></span>  <span data-ttu-id="789bf-154">并</span><span class="sxs-lookup"><span data-stu-id="789bf-154">Then,</span></span>  
1.  <span data-ttu-id="789bf-155">生成 \ （ `Ctrl` + `Shift` + `F5` \）并运行 `F5` PWA 项目。</span><span class="sxs-lookup"><span data-stu-id="789bf-155">Build \(`Ctrl`+`Shift`+`F5`\) and Run \(`F5`\) your PWA project.</span></span>  <span data-ttu-id="789bf-156">您的网站现在应该在独立应用窗口中启动。</span><span class="sxs-lookup"><span data-stu-id="789bf-156">Your website should now launch in a standalone app window.</span></span>  <span data-ttu-id="789bf-157">它不仅是托管 web 应用;它作为在 Windows 10 上安装的渐进式 Web 应用运行！</span><span class="sxs-lookup"><span data-stu-id="789bf-157">Not only is it a hosted web app; it is running as a Progressive Web App installed on Windows 10!</span></span>  

    ![在 WWAHost 窗口中运行的 PWA](media/wwahost.png)  

## <span data-ttu-id="789bf-159">以 Windows 应用的形式调试 PWA \ （EdgeHTML \）</span><span class="sxs-lookup"><span data-stu-id="789bf-159">Debug your PWA \(EdgeHTML\) as a Windows app</span></span>  

<span data-ttu-id="789bf-160">由于 PWA \ （EdgeHTML \）只是一个渐进增强的托管 web 应用，因此你可以使用常规的 IDE 和工作流来调试你的服务器端代码与任意 web 应用一样。</span><span class="sxs-lookup"><span data-stu-id="789bf-160">Because a PWA \(EdgeHTML\) is simply a progressively enhanced hosted web app, you are able to debug your server-side code the same as any web app, using your usual IDE and workflow.</span></span>  <span data-ttu-id="789bf-161">你的实时部署更改将在你下次启动时反映在已安装的 PWA 中（无需重新部署你的通用 Windows 应用包 \）。</span><span class="sxs-lookup"><span data-stu-id="789bf-161">The changes you deploy live are reflected in your installed PWA the next time you launch it \(no need to redeploy your Universal Windows app package\).</span></span>

<span data-ttu-id="789bf-162">对于你的 Windows 10 应用中的客户端调试，你必须具有该 `Microsoft Edge DevTools Preview` 应用。</span><span class="sxs-lookup"><span data-stu-id="789bf-162">For client-side debugging within your Windows 10 app, you must have the `Microsoft Edge DevTools Preview` app.</span></span>  <span data-ttu-id="789bf-163">此独立应用包括原始的浏览器[Microsoft Edge DevTools][DevToolsGuide] \ （包括[PWA 工具][DevToolsGuideServiceWorkers]\），以及基本的[远程调试][DevToolsProtocol01ClientsEdgePreview]支持和[调试目标选择器][DevToolsGuideMicrosoftStoreApp]，用于附加到 EdgeHTML 引擎的任何运行的实例，包括 Office、Cortana、应用 Webviews 的加载项、当然 PWAs 在 Windows 上运行的加载项。</span><span class="sxs-lookup"><span data-stu-id="789bf-163">This standalone app includes all the functionality of the original in-browser [Microsoft Edge DevTools][DevToolsGuide] \(including [PWA tools][DevToolsGuideServiceWorkers]\), plus basic [remote debugging][DevToolsProtocol01ClientsEdgePreview] support and a [Debug Target chooser][DevToolsGuideMicrosoftStoreApp] for attaching to any running instance of the EdgeHTML engine, including add-ins for Office, Cortana, app webviews, and of course, PWAs running on Windows.</span></span>  

<span data-ttu-id="789bf-164">下面介绍如何为 PWA 设置调试 \ （EdgeHTML \）。</span><span class="sxs-lookup"><span data-stu-id="789bf-164">Here is how to set up debugging for your PWA \(EdgeHTML\).</span></span>  

1.  <span data-ttu-id="789bf-165">从 Microsoft Store 中安装[Microsoft Edge DevTools Preview][MicrosoftStoreEdgeDevtoolsPreview]应用（如果尚未安装）。</span><span class="sxs-lookup"><span data-stu-id="789bf-165">Install the [Microsoft Edge DevTools Preview][MicrosoftStoreEdgeDevtoolsPreview] app from the Microsoft Store if you do not already have it.</span></span>  
1.  <span data-ttu-id="789bf-166">在 PWA 网站启动并运行后，启动 DevTools 应用。</span><span class="sxs-lookup"><span data-stu-id="789bf-166">With your PWA site up and running, launch the DevTools app.</span></span>  
1.  <span data-ttu-id="789bf-167">在 Visual Studio 中，通过 `Start Without Debugging` （ `Ctrl` + `F5` ）命令启动 Windows 10 应用。</span><span class="sxs-lookup"><span data-stu-id="789bf-167">From Visual Studio, launch your Windows 10 app with the `Start Without Debugging` (`Ctrl`+`F5`) command.</span></span>  <span data-ttu-id="789bf-168">\ （如果 Visual Studio 调试器处于活动状态，DevTools 应用不会正确附加。）</span><span class="sxs-lookup"><span data-stu-id="789bf-168">\(The DevTools app does not attach properly if the Visual Studio debugger is active.\)</span></span>  
1.  <span data-ttu-id="789bf-169">在 DevTools 应用中，单击本地调试目标选择器中的 "**刷新**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="789bf-169">In the DevTools app, click the **Refresh** button in the Local debug target chooser.</span></span>  <span data-ttu-id="789bf-170">您的 PWA \ （EdgeHTML \）网站现在应该已列出。</span><span class="sxs-lookup"><span data-stu-id="789bf-170">Your PWA \(EdgeHTML\) site should now be listed.</span></span>  <span data-ttu-id="789bf-171">\ （如果它也在浏览器窗口中运行，则是该网站在列表中的最后一个实例。）</span><span class="sxs-lookup"><span data-stu-id="789bf-171">\(If it is also running in a browser window, it is the last instance of that site in the list.\)</span></span>  
1.  <span data-ttu-id="789bf-172">单击 PWA \ （EdgeHTML \）网站清单以打开新的 DevTools "实例" 选项卡，然后开始调试。</span><span class="sxs-lookup"><span data-stu-id="789bf-172">Click on your PWA \(EdgeHTML\) site listing to open a new DevTools instance tab and start debugging.</span></span>  
    
    ![Microsoft Edge DevTools 应用中的本地调试目标选择器](media/devtools-local.png)  
    
1.  <span data-ttu-id="789bf-174">你可以验证 DevTools 是否已连接到你的 PWA 运行的 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="789bf-174">You are able to verify that DevTools is attached to your PWA-running-as-Windows-app.</span></span>  <span data-ttu-id="789bf-175">在 DevTools**控制台**中，键入：</span><span class="sxs-lookup"><span data-stu-id="789bf-175">In the DevTools **Console**, type:</span></span>  
    
    ```shell
    window.Windows
    ```  
    
    <span data-ttu-id="789bf-176">这将返回 `Windows Runtime` 包含所有[顶级 WinRT 命名空间](#find-windows-runtime-winrt-apis)的全局对象。</span><span class="sxs-lookup"><span data-stu-id="789bf-176">This returns the global `Windows Runtime` object containing all of the [top-level WinRT namespaces](#find-windows-runtime-winrt-apis).</span></span>  <span data-ttu-id="789bf-177">这是[通用 Windows 平台][WindowsUWPIndex]的 PWA \ （EdgeHTML \）入口点，并仅向作为 Windows 10 应用（在浏览器外运行）运行的 web 应用公开 `WWAHost.exe` 。</span><span class="sxs-lookup"><span data-stu-id="789bf-177">This is your PWA \(EdgeHTML\) entrypoint to the [Universal Windows Platform][WindowsUWPIndex], and only exposed to web apps that run as Windows 10 apps (running outside the browser, in a `WWAHost.exe` process).</span></span>  
    
## <span data-ttu-id="789bf-178">查找 Windows 运行时 \ （WinRT） Api</span><span class="sxs-lookup"><span data-stu-id="789bf-178">Find Windows Runtime \(WinRT\) APIs</span></span>  

<span data-ttu-id="789bf-179">作为已安装的 Windows 应用， [PWA \ （EdgeHTML \）对本机 Windows 运行时 api 具有完全访问权限][WindowsRuntime];确定需要使用的内容，获取必要的权限，并使用功能检测在受支持的环境中发送该 API 请求。</span><span class="sxs-lookup"><span data-stu-id="789bf-179">As an installed Windows app, your [PWA \(EdgeHTML\) has full access to native Windows Runtime APIs][WindowsRuntime]; identify what you need to use, obtain the requisite permissions, and employ feature detection to send that API request on supported environments.</span></span>  <span data-ttu-id="789bf-180">浏览此过程，为 PWA 的 Windows 桌面用户添加渐进式增强。</span><span class="sxs-lookup"><span data-stu-id="789bf-180">Walk through this process to add a progressive enhancement for Windows desktop users of your PWA.</span></span>  

<span data-ttu-id="789bf-181">可通过多种方法来标识 Windows PWA 所需的通用 Windows 平台 Api，包括在 windows 开发人员中心上搜索全面 [UWP 文档] [UWP/api/]、下载并运行适用于 Windows 的[uwp 代码示例](#uwp-code-samples)以及浏览 PWAs 的常见任务。</span><span class="sxs-lookup"><span data-stu-id="789bf-181">There are a number of ways to identify the Universal Windows Platform APIs you need for your Windows PWA, including searching the comprehensive [UWP docs on Windows Dev Center][uwp/api/], downloading and running [UWP code samples](#uwp-code-samples) with Visual Studio, and browsing code snippets for common tasks for PWAs on Windows.</span></span>

<span data-ttu-id="789bf-182">有多种方法可用于标识你为 Windows PWA 所需的通用 Windows 平台 Api，包括在 windows 开发人员中心上搜索全面 [UWP 文档] [uwp/api/]、下载并运行适用于 Visual Studio 的[uwp 代码示例](#uwp-code-samples)以及[在 Windows 10 （EdgeHTML）上浏览 PWAs][PwaIndexWindows10]的常见任务的代码片段。</span><span class="sxs-lookup"><span data-stu-id="789bf-182">There are a number of ways to identify the Universal Windows Platform APIs you need for your Windows PWA, including searching the comprehensive [UWP docs on Windows Dev Center][uwp/api/], downloading and running [UWP code samples](#uwp-code-samples) with Visual Studio, and browsing code snippets for common tasks for [PWAs on Windows 10 (EdgeHTML)][PwaIndexWindows10].</span></span>  

<span data-ttu-id="789bf-183">总之，WinRT Api 在 JavaScript 中的工作方式与它们在 c # 中的工作方式相同，因此你可以遵循通用的[通用 Windows 平台文档][WindowsUWPIndex]和[API 参考][UwpApiIndex]以了解用法。</span><span class="sxs-lookup"><span data-stu-id="789bf-183">Overall, WinRT APIs work in JavaScript the same way they do in C#, so you may follow the general [Universal Windows Platform documentation][WindowsUWPIndex] and [API Reference][UwpApiIndex] for usage.</span></span>  <span data-ttu-id="789bf-184">但是，请注意以下差异：</span><span class="sxs-lookup"><span data-stu-id="789bf-184">However, please note the following differences:</span></span>  

*   <span data-ttu-id="789bf-185">JavaScript 中的 WinRT 功能使用[不同的大小写约定][ScriptingJsinrtUsingWinRTCasingConventions]</span><span class="sxs-lookup"><span data-stu-id="789bf-185">WinRT features in JavaScript use  [different casing conventions][ScriptingJsinrtUsingWinRTCasingConventions]</span></span>  
*   <span data-ttu-id="789bf-186">[事件表示为][ScriptingJsinrtHandlingWinRTEvents]传递到类 `addEventListener` / `removeEventListener` 方法的字符串标识符</span><span class="sxs-lookup"><span data-stu-id="789bf-186">[Events are represented as string identifiers][ScriptingJsinrtHandlingWinRTEvents] passed to class `addEventListener`/`removeEventListener` methods</span></span>  
*   <span data-ttu-id="789bf-187">[异步方法][ScriptingJsinrtUsingWinRT]使用 JavaScript 承诺模型</span><span class="sxs-lookup"><span data-stu-id="789bf-187">[Asynchronous methods][ScriptingJsinrtUsingWinRT] use the JavaScript Promise model</span></span>  
*   <span data-ttu-id="789bf-188">`Windows.UI.Xaml`JavaScript 应用不支持命名空间中的 api，而 JavaScript 应用则使用[EdgeHTML][DevGuideWhatsNew]引擎 web 呈现堆栈 \ （HTML、CSS \）</span><span class="sxs-lookup"><span data-stu-id="789bf-188">APIs in the `Windows.UI.Xaml` namespace are not supported for JavaScript apps, which instead use the [EdgeHTML][DevGuideWhatsNew] engine web rendering stack \(HTML, CSS\)</span></span>  

<span data-ttu-id="789bf-189">有关更多详细信息，请参阅[在 JavaScript 中使用 Windows 运行时][WindowRuntimeUsingJavascript]。</span><span class="sxs-lookup"><span data-stu-id="789bf-189">For more details, see [Using the Windows Runtime in JavaScript][WindowRuntimeUsingJavascript].</span></span>  

### <span data-ttu-id="789bf-190">UWP 代码示例</span><span class="sxs-lookup"><span data-stu-id="789bf-190">UWP code samples</span></span>  

<span data-ttu-id="789bf-191">查看[通用 Windows 平台 \ （UWP \）代码示例][MicrosoftDeveloperWindowsSamples]存储库，浏览常见 windows 10 应用方案的 JavaScript 示例。</span><span class="sxs-lookup"><span data-stu-id="789bf-191">Check out the [Universal Windows Platform \(UWP\) Code Samples][MicrosoftDeveloperWindowsSamples] repo to browse JavaScript examples for common Windows 10 app scenarios.</span></span>  <span data-ttu-id="789bf-192">虽然这些示例的 JS 版本使用[WinJS][GithubWinjsWinjs]库来构造示例模板，但发送这些示例中所示的 WinRT API 请求不需要 WinJS。</span><span class="sxs-lookup"><span data-stu-id="789bf-192">Although the JS versions of these samples use the [WinJS][GithubWinjsWinjs] library to structure the sample template, WinJS is not required for sending the WinRT API requests demonstrated in these samples.</span></span>  

> [!NOTE]
> <span data-ttu-id="789bf-193">如果需要侦听 [`activated`][UwpApiWindowsUiWebuiWebapplicationActivated] 应用的事件，可以使用以下本机 WINRT API 执行此操作：</span><span class="sxs-lookup"><span data-stu-id="789bf-193">If you need to listen for the [`activated`][UwpApiWindowsUiWebuiWebapplicationActivated] event for the app, you are able to do this using the following native WinRT API:</span></span>  
> 
> **<span data-ttu-id="789bf-194">使用此</span><span class="sxs-lookup"><span data-stu-id="789bf-194">Use this</span></span>**  
> 
> ```javascript
> Windows.UI.WebUI.WebUIApplication.addEventListener("activated", function (activatedEventArgs) {
>     // Check activatedEventArgs.kind and respond as needed
> });
> ```  
> 
> <span data-ttu-id="789bf-195">...与示例中使用的此类型的 WinJS 请求相比：</span><span class="sxs-lookup"><span data-stu-id="789bf-195">... as opposed this type of WinJS request used in the samples:</span></span>  
> 
> **<span data-ttu-id="789bf-196">不是这种情况</span><span class="sxs-lookup"><span data-stu-id="789bf-196">Not this</span></span>**  
> 
> ```javascript
>     var page = WinJS.UI.Pages.define("/html/scenario1-launched.html", {
>         ready: function (element, options) {
>             // Check options.activationKind and respond as needed
>         }
>     });
> ```  

## <span data-ttu-id="789bf-197">从 PWA 发送 WinRT API 请求（EdgeHTML）</span><span class="sxs-lookup"><span data-stu-id="789bf-197">Send WinRT API requests from your PWA (EdgeHTML)</span></span>  

<span data-ttu-id="789bf-198">此时，假设你想要为 PWA \ （EdgeHTML \）的 Windows 用户添加自定义上下文菜单，并且已在[WINDOWS UI 弹出][UwpApiWindowsUiPopups]命名空间中标识了所需的 api。</span><span class="sxs-lookup"><span data-stu-id="789bf-198">At this point, pretend you want to add a custom context menu for Windows users of our PWA \(EdgeHTML\) and have identified the APIs you need in the [Windows.UI.Popups][UwpApiWindowsUiPopups] namespace.</span></span>  

<span data-ttu-id="789bf-199">为了从我们的 PWA \ （EdgeHTML \）发送任何 WinRT Api 请求，首先需要在 Windows 应用包清单 \ （\）文件中[建立必要的权限](#set-application-content-uri-rules-acurs)\ （或应用程序内容 URI 规则 \） `.appxmanifest` 。</span><span class="sxs-lookup"><span data-stu-id="789bf-199">In order to send any WinRT APIs requests from our PWA \(EdgeHTML\), you first need to [establish the requisite permissions](#set-application-content-uri-rules-acurs) \(or, Application Content URI Rules\) in your Windows app package manifest \(`.appxmanifest`\) file.</span></span>  

<span data-ttu-id="789bf-200">如果这些 API 请求中的任何一个涉及访问用户资源（如图片或音乐）或设备功能（如相机或麦克风），则还需要将[应用功能声明](#app-capability-declarations)添加到应用包清单中，以便 Windows 提示用户获得权限。</span><span class="sxs-lookup"><span data-stu-id="789bf-200">If any of these API requests involve access to user resources like pictures or music, or to device features like the camera or microphone, you also need to add [app capability declarations](#app-capability-declarations) to the app package manifest in order for Windows to prompt the user for permission.</span></span>  <span data-ttu-id="789bf-201">如果你后来将 PWA \ （EdgeHTML \）发布到 Microsoft Store，则你的应用商店中还会注明这些必需的[应用权限][MicrosoftSupportWindowsAppPermissions]。</span><span class="sxs-lookup"><span data-stu-id="789bf-201">If you later publish your PWA \(EdgeHTML\) to the Microsoft Store, these required [App permissions][MicrosoftSupportWindowsAppPermissions] are also noted in your store listing.</span></span>  

#### <span data-ttu-id="789bf-202">设置应用程序内容 URI 规则（Acur）</span><span class="sxs-lookup"><span data-stu-id="789bf-202">Set Application Content URI Rules (ACURs)</span></span>  

<span data-ttu-id="789bf-203">通过 Acur （也称为 URL 允许列表），你可以为 Windows 运行时 Api 提供 PWA 的 Url \ （EdgeHTML \）直接访问。</span><span class="sxs-lookup"><span data-stu-id="789bf-203">Through ACURs, otherwise known as a URL allow list, you are able to give the URLs of your PWA \(EdgeHTML\) direct access to Windows Runtime APIs.</span></span>  <span data-ttu-id="789bf-204">在 Windows 操作系统级别，适当的策略边界设置为允许 web 服务器上托管的代码直接发送平台 API 请求。</span><span class="sxs-lookup"><span data-stu-id="789bf-204">At the Windows OS level, the right policy bounds are set to allow code hosted on your web server to directly send platform API requests.</span></span>  <span data-ttu-id="789bf-205">将 PWA Url 指定为时，可以在应用包清单文件中定义这些界限 `ApplicationContentUriRules` 。</span><span class="sxs-lookup"><span data-stu-id="789bf-205">You define these bounds in the app package manifest file when you specify your PWA URLs as `ApplicationContentUriRules`.</span></span>  

<span data-ttu-id="789bf-206">你的规则应包括你的应用的起始页以及你希望作为应用页面包含的任何其他页面。</span><span class="sxs-lookup"><span data-stu-id="789bf-206">Your rules should include the start page for your app and any other pages you want included as app pages.</span></span>  <span data-ttu-id="789bf-207">如果你的用户导航到你的规则中未包含的 URL，Windows 将在 Microsoft Edge 浏览器中打开目标 URL，而不是独立的 PWA \ （EdgeHTML \）窗口 \ （ `WWAHost.exe` process \）。</span><span class="sxs-lookup"><span data-stu-id="789bf-207">If your user navigates to a URL that is not included in your rules, Windows opens the target URL in the Microsoft Edge browser rather than your standalone PWA \(EdgeHTML\) window \(`WWAHost.exe` process\).</span></span>  <span data-ttu-id="789bf-208">您也可以排除特定的 Url。</span><span class="sxs-lookup"><span data-stu-id="789bf-208">You may also exclude specific URLs.</span></span>  

<span data-ttu-id="789bf-209">可通过多种方法 `Match` 在规则中指定 URL：</span><span class="sxs-lookup"><span data-stu-id="789bf-209">There are several ways to specify a URL `Match` in your rules:</span></span>  

*   <span data-ttu-id="789bf-210">确切的主机名</span><span class="sxs-lookup"><span data-stu-id="789bf-210">An exact hostname</span></span>  
*   <span data-ttu-id="789bf-211">已包括或排除含有某个主机名的任何子域的 URI 对应的主机名</span><span class="sxs-lookup"><span data-stu-id="789bf-211">A hostname for which a URI with any subdomain of that hostname is included or excluded</span></span>  
*   <span data-ttu-id="789bf-212">确切的 URI</span><span class="sxs-lookup"><span data-stu-id="789bf-212">An exact URI</span></span>  
*   <span data-ttu-id="789bf-213">包含查询属性的确切 URI</span><span class="sxs-lookup"><span data-stu-id="789bf-213">An exact URI containing a query property</span></span>  
*   <span data-ttu-id="789bf-214">部分路径和用于指示包含规则的特定文件扩展名的通配符。</span><span class="sxs-lookup"><span data-stu-id="789bf-214">A partial path and a wildcard to indicate a particular file extension for an include rule</span></span>  
*   <span data-ttu-id="789bf-215">排除规则的相对路径</span><span class="sxs-lookup"><span data-stu-id="789bf-215">Relative paths for exclude rules</span></span>  

<span data-ttu-id="789bf-216">下面是一个文件中的一些 Acur 示例 `.appxmanifest` ：</span><span class="sxs-lookup"><span data-stu-id="789bf-216">Here are a few examples of ACURs in a `.appxmanifest` file:</span></span>  

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

<span data-ttu-id="789bf-217">在你的应用的 Acur 内定义的 Url 可以通过该属性授予对 Windows 运行时的权限 `WindowsRuntimeAccess` ，这将接受以下值：</span><span class="sxs-lookup"><span data-stu-id="789bf-217">URLs defined within the ACURs for your app are able to be granted permission to the Windows Runtime through the `WindowsRuntimeAccess` attribute, which accepts the following values:</span></span>  

*   `all`<span data-ttu-id="789bf-218">：远程 JavaScript 代码可以访问所有 WinRT Api 和任何本地打包的组件。</span><span class="sxs-lookup"><span data-stu-id="789bf-218">: Remote JavaScript code has access to all WinRT APIs and any local packaged components.</span></span>  <span data-ttu-id="789bf-219">[Windows \ （WinRT））][UwpApiIndex]命名空间被注入并存在于脚本引擎中。</span><span class="sxs-lookup"><span data-stu-id="789bf-219">The [Windows \(WinRT\))][UwpApiIndex] namespace is injected and present in the script engine.</span></span>  
*   `allowForWeb`<span data-ttu-id="789bf-220">：远程 JavaScript 代码访问仅限于本地打包的组件，包括自定义 c + +/C # 组件。</span><span class="sxs-lookup"><span data-stu-id="789bf-220">: Remote JavaScript code access is limited to local packaged components, including custom C++/C# components.</span></span>  
*   `none`<span data-ttu-id="789bf-221">默认.</span><span class="sxs-lookup"><span data-stu-id="789bf-221">: Default.</span></span>  <span data-ttu-id="789bf-222">指定的 URL 不具有任何平台访问权限。</span><span class="sxs-lookup"><span data-stu-id="789bf-222">The specified URL has no platform access.</span></span>  

<span data-ttu-id="789bf-223">在本教程中，你已经为单页应用设置了你需要的唯一 ACUR \ （上一次[设置和运行应用](#set-up-and-run-your-universal-windows-app)的第6部分）。</span><span class="sxs-lookup"><span data-stu-id="789bf-223">In this tutorial, you already set the only ACUR that you need \(Step 6 of the previous [Set up and run your app](#set-up-and-run-your-universal-windows-app) section\) for your single-page app.</span></span>  <span data-ttu-id="789bf-224">你可以从 Visual Studio 设计器的 "**内容 uri** " 面板中进行确认 `package.appxmanifest` 。</span><span class="sxs-lookup"><span data-stu-id="789bf-224">You are able to confirm this from the **Content URIs** panel of the Visual Studio `package.appxmanifest` designer.</span></span>  

![Visual Studio package.appxmanifest designer 的内容 URI 面板](media/vs-appxmanifest-editor-acurs.png)  

<span data-ttu-id="789bf-226">你还可以通过右键单击 `package.appxmanifest` Visual Studio 解决方案资源管理器中的文件并选择 "**查看代码**\ （\）" 来查看清单的原始 XML `F7` 。</span><span class="sxs-lookup"><span data-stu-id="789bf-226">You are also able to view the raw XML of your manifest by right-clicking your `package.appxmanifest` file in Visual Studio Solution Explorer and selecting **View Code** \(`F7`\).</span></span>  <span data-ttu-id="789bf-227">若要切换回设计器视图，请选择 "**视图设计器**\ （ `Shift` + `F7` \）"。</span><span class="sxs-lookup"><span data-stu-id="789bf-227">To toggle back to the Designer view, select **View Designer** \(`Shift`+`F7`\).</span></span>  

#### <span data-ttu-id="789bf-228">应用功能声明</span><span class="sxs-lookup"><span data-stu-id="789bf-228">App capability declarations</span></span>  

<span data-ttu-id="789bf-229">如果你的应用需要以编程方式访问用户资源（如图片或音乐）或设备（如相机或麦克风），则必须在你的应用包清单文件中包含相应的[应用功能声明][WindowsUwpPackagingAppCapabilities]。</span><span class="sxs-lookup"><span data-stu-id="789bf-229">If your app needs programmatic access to user resources like pictures or music, or to devices like a camera or a microphone, you must include the corresponding [App capability declarations][WindowsUwpPackagingAppCapabilities] in your app package manifest file.</span></span>  <span data-ttu-id="789bf-230">三种应用功能声明类别如下所示：</span><span class="sxs-lookup"><span data-stu-id="789bf-230">There are three app capability declaration categories:</span></span>  

*   <span data-ttu-id="789bf-231">适用于大多数常见应用场景的[通用功能][WindowsUwpPackagingAppCapabilitiesGeneralUse]。</span><span class="sxs-lookup"><span data-stu-id="789bf-231">[General-use capabilities][WindowsUwpPackagingAppCapabilitiesGeneralUse] that apply to most common app scenarios.</span></span>  
*   <span data-ttu-id="789bf-232">允许你的应用访问外围设备和内部设备的[设备功能][WindowsUwpPackagingAppCapabilitiesDevice]。</span><span class="sxs-lookup"><span data-stu-id="789bf-232">[Device capabilities][WindowsUwpPackagingAppCapabilitiesDevice] that allow your app to access peripheral and internal devices.</span></span>  
*   <span data-ttu-id="789bf-233">支持企业方案并需要 Microsoft Store 公司帐户的[特殊用途功能][WindowsUwpPackagingAppCapabilitiesSpecialRestricted]。</span><span class="sxs-lookup"><span data-stu-id="789bf-233">[Special-use capabilities][WindowsUwpPackagingAppCapabilitiesSpecialRestricted] that support enterprise scenarios and require a Microsoft Store company account.</span></span>  <span data-ttu-id="789bf-234">有关公司帐户的详细信息，请参阅[帐户类型、位置和费用][WindowsUwpPublishAccountTypesLocationsFees]。</span><span class="sxs-lookup"><span data-stu-id="789bf-234">For more info about company accounts, see [Account types, locations, and fees][WindowsUwpPublishAccountTypesLocationsFees].</span></span>

<span data-ttu-id="789bf-235">你的 Microsoft Store 应用页面列出你在应用包清单中声明的所有功能，因此请确保仅指定你的应用实际使用的功能。</span><span class="sxs-lookup"><span data-stu-id="789bf-235">Your Microsoft Store app page lists all the capabilities you declare in your app package manifest, so be sure to only specify the capabilities that your app actually uses.</span></span>

<span data-ttu-id="789bf-236">某些功能为应用提供对敏感资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="789bf-236">Some capabilities provide apps access to sensitive resources.</span></span>  <span data-ttu-id="789bf-237">这些资源被认为是敏感资源，因为每个资源都能够访问用户的个人资料或为用户收费。</span><span class="sxs-lookup"><span data-stu-id="789bf-237">These resources are considered sensitive because each is able to access the user's personal data or cost the user money.</span></span>  <span data-ttu-id="789bf-238">隐私设置由 Windows 10 "[设置][BingResultsWindows10Settings]" 应用托管，让用户能够动态控制对敏感资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="789bf-238">Privacy settings, managed by the Windows 10 [Settings][BingResultsWindows10Settings] app, let the user dynamically control access to sensitive resources.</span></span>  <span data-ttu-id="789bf-239">因此，你的应用不会假设敏感资源始终可用，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="789bf-239">Thus, it is important that your app does not assume a sensitive resource is always available.</span></span>  <span data-ttu-id="789bf-240">有关访问敏感资源的详细信息，请参阅[隐私感知应用指南][WindowsUwp|::ref2::|Index]。</span><span class="sxs-lookup"><span data-stu-id="789bf-240">For more info about accessing sensitive resources, see [Guidelines for privacy-aware apps][WindowsUwp|::ref2::|Index].</span></span>  

<span data-ttu-id="789bf-241">你可以通过在你的应用的程序包清单中声明功能来请求访问权限。</span><span class="sxs-lookup"><span data-stu-id="789bf-241">You request access by declaring capabilities in the package manifest for your app.</span></span>  <span data-ttu-id="789bf-242">在 Visual Studio 中，你可以从 package.appxmanifest designer 的 "**功能**" 面板中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="789bf-242">In Visual Studio, you are able to do this from the **Capabilities** panel of the package.appxmanifest designer.</span></span>  

![Visual Studio package.appxmanifest designer 的 "功能" 面板](media/vs-appxmanifest-editor-capabilities.png)  

<span data-ttu-id="789bf-244">在本教程中，仅需要默认的 Internet \ （客户端 \）功能，因此无需执行进一步操作。</span><span class="sxs-lookup"><span data-stu-id="789bf-244">In this tutorial, only the default Internet \(Client\) capability is required, so no further action is needed.</span></span>  

### <span data-ttu-id="789bf-245">使用功能检测来调用 WinRT</span><span class="sxs-lookup"><span data-stu-id="789bf-245">Use feature detection to invoke WinRT</span></span>  

<span data-ttu-id="789bf-246">为了确保所有平台上的 PWA 受众的质量基准体验，你可以通过 WinRT 功能检测逐步增强你在 Windows 上的 PWA 体验。</span><span class="sxs-lookup"><span data-stu-id="789bf-246">To ensure a quality baseline experience for your PWA audience across all platforms, you progressively enhance your PWA experience on Windows using WinRT feature detection.</span></span>  <span data-ttu-id="789bf-247">这样，你就能够确保仅在 WinRT Api 可用且适用的上下文中运行特定于 Windows 的代码。</span><span class="sxs-lookup"><span data-stu-id="789bf-247">This way, you are able to be sure your Windows-specific code is only run in a context where WinRT APIs are available and applicable.</span></span>  

<span data-ttu-id="789bf-248">功能检测可能非常简单，只需按如下方式查找 `Windows` 对象 \ （ [WinRT 命名空间][UwpApiIndex]\ 的入口点 \）：</span><span class="sxs-lookup"><span data-stu-id="789bf-248">Feature detection may be as simple as looking for the `Windows` object \(the entrypoint to the [WinRT namespace][UwpApiIndex]\) as below:</span></span>  

```javascript
if(window.Windows){
    /*Run code that sends Windows API requests */
}
```  

<span data-ttu-id="789bf-249">但是，如果并非所有 Windows Api 在所有[windows 10 设备类型][UwpExtensionSdkDeviceFamiliesOverview]上都可用，则使用更具体的功能检测来进一步限定你正在发送的 API 请求的命名空间通常非常有用：</span><span class="sxs-lookup"><span data-stu-id="789bf-249">However, given that not all Windows APIs are available on all [Windows 10 device types][UwpExtensionSdkDeviceFamiliesOverview], it is generally useful to use more specific feature detection to further qualify the namespace of the API request you are sending:</span></span>  

```javascript
if(window.Windows && Windows.Media.SpeechRecognition){
    /*Run code that sends Windows API requests */
}
```  

<span data-ttu-id="789bf-250">使用该背景，您可以添加一些 WinRT 代码来实现自定义上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="789bf-250">With that background, you are ready to add some WinRT code to implement a custom context menu.</span></span>  <span data-ttu-id="789bf-251">如果你使用的是来自[开始使用渐进的 Web 应用][PwaGetStarted]的示例 PWA：</span><span class="sxs-lookup"><span data-stu-id="789bf-251">If you are using the sample PWA from [Get started with Progressive Web Apps][PwaGetStarted]:</span></span>

1.  <span data-ttu-id="789bf-252">打开 Visual Studio 到 PWA 网站项目。</span><span class="sxs-lookup"><span data-stu-id="789bf-252">Open Visual Studio to your PWA site project.</span></span>

1.  <span data-ttu-id="789bf-253">在 "解决方案资源管理器" 中，打开 `views\layout.pug` 文件并在 `script` 服务工作人员参考的下方添加以下行：</span><span class="sxs-lookup"><span data-stu-id="789bf-253">In Solution Explorer, open the `views\layout.pug` file and add the following line, right below the `script` reference for your service worker:</span></span>
    
    ```xml
    script(src='/javascripts/site.js')
    ```  

1.  <span data-ttu-id="789bf-254">在 "解决方案资源管理器" 中，右键单击 `javascripts` 文件夹，然后单击 "**添加**  >  **新文件 ...**"。</span><span class="sxs-lookup"><span data-stu-id="789bf-254">In Solution Explorer, right-click on the `javascripts` folder and **Add** > **New File...**.</span></span>

1.  <span data-ttu-id="789bf-255">为文件命名： `site.js` ，并复制以下代码：</span><span class="sxs-lookup"><span data-stu-id="789bf-255">Name your file: `site.js`, and copy in the following code:</span></span>
    
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

1.  <span data-ttu-id="789bf-256">比较在浏览器中运行 PWA 时的上下文菜单行为 \ （ `F5` 从 PWA 网站项目 \），而不是从 windows 应用窗口 \ 中（ `F5` 从通用 Windows 应用项目 \）中运行。</span><span class="sxs-lookup"><span data-stu-id="789bf-256">Compare the context menu behavior when you run your PWA in the browser \(`F5` from your PWA site project\) versus from inside the Windows app window \(`F5` from your Universal Windows app project\).</span></span>  <span data-ttu-id="789bf-257">在浏览器中，右键单击为你提供 Microsoft Edge 默认上下文菜单，而在该 `WWAHost.exe` 过程中，你的自定义菜单现在将显示。</span><span class="sxs-lookup"><span data-stu-id="789bf-257">In the browser, right-clicking gives you the Microsoft Edge default context menu, whereas in the `WWAHost.exe` process, your custom menu now appears.</span></span>  

    | <span data-ttu-id="789bf-258">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="789bf-258">Microsoft Edge</span></span> | <span data-ttu-id="789bf-259">Windows 10 应用</span><span class="sxs-lookup"><span data-stu-id="789bf-259">Windows 10 app</span></span> |  
    |:--- |:---- |  
    | ![浏览器默认上下文菜单](media/browser-context-menu.png) | ![应用自定义上下文菜单](media/app-context-menu.png) |  

<span data-ttu-id="789bf-262">希望你现在有坚实的基础，可在 Windows 上逐步增强你的 PWAs。</span><span class="sxs-lookup"><span data-stu-id="789bf-262">Hopefully you now have a solid foundation for progressively enhancing your PWAs on Windows.</span></span>  <span data-ttu-id="789bf-263">如果遇到问题或不清楚任何问题，请发送评论！</span><span class="sxs-lookup"><span data-stu-id="789bf-263">If you run into questions or anything is unclear, please send a comment!</span></span>  

## <span data-ttu-id="789bf-264">深入探索</span><span class="sxs-lookup"><span data-stu-id="789bf-264">Going further</span></span>

<span data-ttu-id="789bf-265">[Windows 开发人员中心][MicrosoftDeveloperWindowsApps]是有关 windows 应用构建的所有[阶段的完整参考，从入门][MicrosoftDeveloperWindowsAppsGetStarted]到[设计][MicrosoftDeveloperWindowsAppsDesign]、[开发][MicrosoftDeveloperWindowsAppsDevelop]和[发布][MicrosoftDeveloperStorePublishApps]到 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="789bf-265">The [Windows Dev Center][MicrosoftDeveloperWindowsApps] is your complete reference for all stages of Windows app building, from [getting started][MicrosoftDeveloperWindowsAppsGetStarted], to [designing][MicrosoftDeveloperWindowsAppsDesign], [developing][MicrosoftDeveloperWindowsAppsDevelop], and [publishing][MicrosoftDeveloperStorePublishApps] to the Microsoft Store.</span></span>  

<span data-ttu-id="789bf-266">有关通用 Windows 平台 \ （UWP \）和如何面向不同的 Windows 10 设备系列的一般概述，请参阅[通用 Windows 平台简介][WindowsUWPGetStartedGuide]。</span><span class="sxs-lookup"><span data-stu-id="789bf-266">For a general overview on the Universal Windows Platform \(UWP\) and how to target different Windows 10 device families, see [Intro to the Universal Windows Platform][WindowsUWPGetStartedGuide].</span></span>  

<span data-ttu-id="789bf-267">准备就绪后，下面是如何将[PWA 提交到 Microsoft Store 的](./microsoft-store.md)"（和为什么！ \）"。</span><span class="sxs-lookup"><span data-stu-id="789bf-267">And when you are ready, here is how \(and why!\) to [Submit your PWA to the Microsoft Store](./microsoft-store.md).</span></span>  

<!-- image links -->  

<!-- links -->  

[PwaGetStarted]: ./get-started.md "渐进式 Web 应用入门"  
[PwaIndexWindows10]: ./index.md#pwas-on-windows-10-edgehtml "Windows 10 上的 PWAs （EdgeHTML）-在 Windows 上渐进 Web 应用"  
[DevToolsGuide]: ../devtools-guide.md "Microsoft Edge （EdgeHTML）开发人员工具"  
[DevToolsGuideMicrosoftStoreApp]: ../devtools-guide.md#microsoft-store-app "Microsoft Store 应用-Microsoft Edge （EdgeHTML）开发人员工具"  
[DevToolsGuideServiceWorkers]: ../devtools-guide/service-workers.md "服务工作人员"  
[DevToolsProtocol01ClientsEdgePreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview-DevTools 协议客户端"  
[DevGuideWhatsNew]: ../dev-guide/whats-new.md "EdgeHTML 中的新增功能"  
[WindowsRuntime]: ../windows-runtime/index.md "适用于 JavaScript 的 Windows 运行时（WinRT）"  
[WindowRuntimeUsingJavascript]: ../windows-runtime/using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时"  

[ScriptingJsinrtHandlingWinRTEvents]: /scripting/jswinrt/handling-windows-runtime-events-in-javascript "处理 JavaScript 中的 Windows 运行时事件"  
[ScriptingJsinrtUsingWinRT]: /scripting/jswinrt/using-windows-runtime-asynchronous-methods "使用 Windows 运行时异步方法"  
[ScriptingJsinrtUsingWinRTCasingConventions]:  /scripting/jswinrt/using-the-windows-runtime-in-javascript#casing-conventions-with-windows-runtime-features "带有 Windows 运行时功能的大小写约定-在 JavaScript 中使用 Windows 运行时"  
[UwpApiIndex]: /uwp/api/index "Windows UWP 命名空间"  
[UwpApiWindowsUiPopups]: /uwp/api/windows.ui.popups "Windows UI 弹出命名空间"  
[UwpApiWindowsUiWebuiWebapplicationActivated]: /uwp/api/windows.ui.webui.webuiapplication.activated "WebUIApplication 事件"  
[UwpExtensionSdkDeviceFamiliesOverview]: /uwp/extension-sdks/device-families-overview "设备系列概述"  
[UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest]: /uwp/schemas/appxpackage/uapmanifestschema/generate-package-manifest "Visual Studio 如何生成应用包清单"  
[WindowsUWPIndex]: /windows/uwp/index "通用 Windows 平台文档"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide "什么是通用 Windows 平台（UWP）应用？"  
[WindowsUWPGetStartedEnable]: /windows/uwp/get-started/enable-your-device-for-development "启用设备进行开发"  
[WindowsUwpSecurityIndex]: /windows/uwp/security/index "安全"  
[WindowsUwpPublishAccountTypesLocationsFees]: /windows/uwp/publish/account-types-locations-and-fees "帐户类型、位置和费用"  
[WindowsUwpPackagingAppCapabilitiesSpecialRestricted]: /windows/uwp/packaging/app-capability-declarations#special-and-restricted-capabilities "受限功能"  
[WindowsUwpPackagingAppCapabilitiesDevice]: /windows/uwp/packaging/app-capability-declarations#device-capabilities "设备功能"  
[WindowsUwpPackagingAppCapabilitiesGeneralUse]: /windows/uwp/packaging/app-capability-declarations#general-use-capabilities "常规-使用功能"  
[WindowsUwpPackagingAppCapabilities]: /windows/uwp/packaging/app-capability-declarations "应用功能声明"  

[BingResultsWindows10Settings]: https://binged.it/2lOGSH0 "windows 10 设置-Bing"  
[GithubWinjsWinjs]: https://github.com/winjs/winjs "winjs/winjs |GitHub"  
[MicrosoftDeveloperStorePublishApps]: https://developer.microsoft.com/store/publish-apps/index "发布 Windows 应用和游戏"  
[MicrosoftDeveloperWindowsApps]: https://developer.microsoft.com/windows/apps/index "通用 Windows 平台文档"  
[MicrosoftDeveloperWindowsAppsDesign]: https://developer.microsoft.com/windows/apps/design/index "设计和代码 Windows 应用"  
[MicrosoftDeveloperWindowsAppsDevelop]: https://developer.microsoft.com/windows/apps/develop/index "开发 UWP 应用"  
[MicrosoftDeveloperWindowsAppsGetStarted]: https://developer.microsoft.com/windows/apps/getstarted/index "Windows 10 应用入门"  
[MicrosoftDeveloperWindowsSamples]: https://developer.microsoft.com/windows/samples "代码示例"  
[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools 预览"  
[MicrosoftSupportWindowsAppPermissions]: https://support.microsoft.com/help/10557/windows-10-app-permissions "应用权限"  
[MicrosoftVisualStudioDownloads]: https://visualstudio.microsoft.com/downloads "下载"  
[MicrosoftVisualStudioPreview]: https://visualstudio.microsoft.com/vs/preview "Visual Studio 预览版"  
