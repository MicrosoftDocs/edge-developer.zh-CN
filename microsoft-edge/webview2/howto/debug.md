---
description: 了解如何调试 WebView2 控件。
title: 开始调试 WebView2 应用程序
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/13/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: dcdeeadc2c25bcf50834176706b8d181f06f994a
ms.sourcegitcommit: 6c7ededf8677fd7add5e4060e92f9ec4cfdb6952
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "10927893"
---
# <span data-ttu-id="c469d-104">开始调试 WebView2 应用程序</span><span class="sxs-lookup"><span data-stu-id="c469d-104">Get started debugging WebView2 applications</span></span>  

<span data-ttu-id="c469d-105">Microsoft Edge WebView2 控件的目标是结合 web 和本机应用程序开发功能和工具的优势。</span><span class="sxs-lookup"><span data-stu-id="c469d-105">The goal of the Microsoft Edge WebView2 control is to combine the best of both the web and native application development features and tools.</span></span>  <span data-ttu-id="c469d-106">开发 WebView2 应用程序时，应调试你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c469d-106">When you develop your WebView2 application, you should debug your application.</span></span>  <span data-ttu-id="c469d-107">本文概述了用于在 WebView2 应用程序中调试 web 和本机代码的不同工具。</span><span class="sxs-lookup"><span data-stu-id="c469d-107">This article outlines the different tools to use to debug both your web and native code in your WebView2 application.</span></span>  

## [<span data-ttu-id="c469d-108">Microsoft Edge 开发工具</span><span class="sxs-lookup"><span data-stu-id="c469d-108">Microsoft Edge DevTools</span></span>](#tab/devtools)  

<span data-ttu-id="c469d-109">使用 [Microsoft edge (Chromium) 开发人员工具][DevtoolsGuideChromiumMain] 来调试在 WebView2 控件中显示的 web 内容，其方式与你对 Microsoft Edge 中显示的其他网页的调试方式相同。</span><span class="sxs-lookup"><span data-stu-id="c469d-109">Use [Microsoft Edge (Chromium) Developer Tools][DevtoolsGuideChromiumMain] to debug web content displayed in WebView2 controls, in the same way that you may debug for another webpage displayed in Microsoft Edge.</span></span>  <span data-ttu-id="c469d-110">若要打开 DevTools，请将焦点置于 "Web 视图" 控件上，然后使用下列操作之一。</span><span class="sxs-lookup"><span data-stu-id="c469d-110">To open the DevTools, set focus on the WebView control and then use one of the following actions.</span></span>  

*   <span data-ttu-id="c469d-111">选择 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="c469d-111">Select `F12`.</span></span>  
*   <span data-ttu-id="c469d-112">选择 `Ctrl` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="c469d-112">Select `Ctrl`+`Shift`+`I`.</span></span>  
*   <span data-ttu-id="c469d-113">打开上下文菜单 \ (右键单击 \ ) 并选择 `Inspect` 。</span><span class="sxs-lookup"><span data-stu-id="c469d-113">Open the context menu \(right-click\) and choose `Inspect`.</span></span>  

<span data-ttu-id="c469d-114">有关详细信息，请参阅 [DevTools 概述][DevtoolsGuideChromiumMain]。</span><span class="sxs-lookup"><span data-stu-id="c469d-114">For more information, see [DevTools overview][DevtoolsGuideChromiumMain].</span></span>  

:::image type="complex" source="./media/f12.png" alt-text="DevTools 调试" lightbox="./media/f12.png":::
   <span data-ttu-id="c469d-116">DevTools 调试</span><span class="sxs-lookup"><span data-stu-id="c469d-116">DevTools debugging</span></span>  
:::image-end:::  

## [<span data-ttu-id="c469d-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c469d-117">Visual Studio</span></span>](#tab/visualstudio)  

<span data-ttu-id="c469d-118">Visual Studio 在 WebView2 应用程序中提供了用于 web 和本机代码的各种调试工具。</span><span class="sxs-lookup"><span data-stu-id="c469d-118">Visual Studio provides various debugging tools for web and native code in WebView2 applications.</span></span>  <span data-ttu-id="c469d-119">在 Visual Studio 部分中，主要关注的是调试 Web 视图控件，但在 Visual Studio 中调试的其他方法通常是可用的。</span><span class="sxs-lookup"><span data-stu-id="c469d-119">In the Visual Studio section, the primarily focus is debugging WebView controls, however the other methods of debugging in Visual Studio are available as usual.</span></span>  <span data-ttu-id="c469d-120">使用以下过程仅在 Win32 应用程序或 Office 外接程序中调试 web 和本机代码。</span><span class="sxs-lookup"><span data-stu-id="c469d-120">Use the following process to debug web and native code in Win32 applications or Office add-ins only.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="c469d-121">在附加了本机调试器的 Visual Studio 中调试应用程序时，选择 " `F12` 可能会触发本机调试器，而不是开发工具"。</span><span class="sxs-lookup"><span data-stu-id="c469d-121">When you debug your application in Visual Studio with the native debugger attached, selecting `F12` may trigger the native debugger instead of Developer Tools.</span></span>  <span data-ttu-id="c469d-122">选择 `Ctrl` + `Shift` + `I` 或使用上下文菜单 \ (右键单击 \ ) 以避免这种情况。</span><span class="sxs-lookup"><span data-stu-id="c469d-122">Select `Ctrl`+`Shift`+`I`, or use the context menu \(right-click\) to avoid the situation.</span></span>  

<span data-ttu-id="c469d-123">开始之前，请确保满足以下要求。</span><span class="sxs-lookup"><span data-stu-id="c469d-123">Before you begin, ensure the following requirements are met.</span></span>  

*   <span data-ttu-id="c469d-124">若要调试脚本，应用必须从 Visual Studio 内部启动。</span><span class="sxs-lookup"><span data-stu-id="c469d-124">To debug scripts, the app must be launched from within Visual Studio.</span></span>  
*   <span data-ttu-id="c469d-125">不能将调试程序附加到正在运行的 WebView2 进程。</span><span class="sxs-lookup"><span data-stu-id="c469d-125">You cannot attach a debugger to a running WebView2 process.</span></span>  
*   <span data-ttu-id="c469d-126">安装 Visual Studio 2019 版本16.4 预览版2或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c469d-126">Install Visual Studio 2019 version 16.4 Preview 2 or later.</span></span>  

<span data-ttu-id="c469d-127">在 Visual Studio 中安装和设置脚本调试程序工具。</span><span class="sxs-lookup"><span data-stu-id="c469d-127">Install and set up the script debugger tools in Visual Studio.</span></span>  

1.  <span data-ttu-id="c469d-128">完成以下操作以在**桌面开发中用 c + +** 安装**JavaScript 诊断**组件。</span><span class="sxs-lookup"><span data-stu-id="c469d-128">Complete the following actions to install the **JavaScript diagnostics** component in **Desktop development with C++**.</span></span>  

    1. <span data-ttu-id="c469d-129">在 Windows 资源管理器栏中，键入 `Visual Studio Installer` 。</span><span class="sxs-lookup"><span data-stu-id="c469d-129">In the Windows Explorer bar, type `Visual Studio Installer`.</span></span>  
    1. <span data-ttu-id="c469d-130">选择 " **Visual Studio 安装程序** " 将其打开。</span><span class="sxs-lookup"><span data-stu-id="c469d-130">Choose **Visual Studio Installer** to open it.</span></span>  
    1. <span data-ttu-id="c469d-131">在 Visual Studio 安装程序的已安装版本上，选择 " **更多** " 按钮，然后选择 " **修改**"。</span><span class="sxs-lookup"><span data-stu-id="c469d-131">In the Visual Studio Installer, on the installed version, choose the **More** button, and then choose **Modify**.</span></span>  
    1. <span data-ttu-id="c469d-132">在 Visual Studio 中的 " **工作量**" 下，选择 " **在 c + + 中的桌面开发** " 设置。</span><span class="sxs-lookup"><span data-stu-id="c469d-132">In Visual Studio, under **Workloads**, choose the **Desktop Development in C++** setting.</span></span>  
        
        :::image type="complex" source="./media/workloads.png" alt-text="Visual Studio 修改工作负荷屏幕" lightbox="./media/workloads.png":::
            <span data-ttu-id="c469d-134">Visual Studio 修改工作负荷屏幕</span><span class="sxs-lookup"><span data-stu-id="c469d-134">Visual Studio Modifying Workloads Screen</span></span> :::image-end:::  
        
    1.  <span data-ttu-id="c469d-135">选择 **单个组件**。</span><span class="sxs-lookup"><span data-stu-id="c469d-135">Choose **Individual components**.</span></span>  
    1.  <span data-ttu-id="c469d-136">在 "搜索" 框中，输入 `JavaScript diagnostics` 。</span><span class="sxs-lookup"><span data-stu-id="c469d-136">In the search box, enter `JavaScript diagnostics`.</span></span>  
    1.  <span data-ttu-id="c469d-137">选择 " **JavaScript 诊断** " 设置。</span><span class="sxs-lookup"><span data-stu-id="c469d-137">Choose the **JavaScript diagnostics** setting.</span></span>  
    1.  <span data-ttu-id="c469d-138">选择 " **修改**"。</span><span class="sxs-lookup"><span data-stu-id="c469d-138">Choose **Modify**.</span></span> 
        
        :::image type="complex" source="./media/indivcomp.png" alt-text="Visual Studio 修改单个组件选项卡" lightbox="./media/indivcomp.png":::
           <span data-ttu-id="c469d-140">Visual Studio 修改单个组件选项卡</span><span class="sxs-lookup"><span data-stu-id="c469d-140">Visual Studio Modifying Individual Components Tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="c469d-141">为 WebView2 应用程序启用脚本调试。</span><span class="sxs-lookup"><span data-stu-id="c469d-141">Enable script debugging for WebView2 applications.</span></span>  
    1.  <span data-ttu-id="c469d-142">在 WebView2 项目中，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **属性**"。</span><span class="sxs-lookup"><span data-stu-id="c469d-142">In your WebView2 project, open the context menu \(right-click\), and choose **Properties**.</span></span>  
    1.  <span data-ttu-id="c469d-143">在 " **配置" 属性**下，选择 " **调试**"。</span><span class="sxs-lookup"><span data-stu-id="c469d-143">Under the **Configuration Properties**, choose **Debugging**.</span></span>  
    1.  <span data-ttu-id="c469d-144">在 " **调试器类型**" 下，选择 " \*\*JavaScript (WebView2") \*\*。</span><span class="sxs-lookup"><span data-stu-id="c469d-144">Under the **Debugger Type**, choose **JavaScript (WebView2)**.</span></span>  
        
        :::image type="complex" source="./media/enbjs.png" alt-text="Visual Studio 调试配置属性" lightbox="./media/enbjs.png":::
           <span data-ttu-id="c469d-146">Visual Studio **调试** 配置属性</span><span class="sxs-lookup"><span data-stu-id="c469d-146">Visual Studio **Debugging** Configuration Property</span></span>  
        :::image-end:::  
        
<span data-ttu-id="c469d-147">完成以下操作以调试你的 WebView2 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c469d-147">Complete the following actions to debug your WebView2 application.</span></span>  

1.  <span data-ttu-id="c469d-148">若要在源代码中设置断点，请将光标悬停在行号的左侧，然后选择设置断点。</span><span class="sxs-lookup"><span data-stu-id="c469d-148">To set a breakpoint in your source code, hover to the left of the line number, and choose to set a breakpoint.</span></span>  <span data-ttu-id="c469d-149">JS/TS 调试适配器不执行源路径映射。</span><span class="sxs-lookup"><span data-stu-id="c469d-149">The JS/TS debug adapter does not perform source path mapping.</span></span>  <span data-ttu-id="c469d-150">您必须打开与您的 WebView2 相关联的完全相同的路径。</span><span class="sxs-lookup"><span data-stu-id="c469d-150">You must open the exact same path associated with your WebView2.</span></span>  
    
    :::image type="complex" source="./media/breakpoint.png" alt-text="Visual Studio 添加断点" lightbox="./media/breakpoint.png"::: 
       <span data-ttu-id="c469d-152">Visual Studio 添加断点</span><span class="sxs-lookup"><span data-stu-id="c469d-152">Visual Studio add breakpoint</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c469d-153">若要运行调试器，请选择平台的位大小，然后选择 " **本地 Windows 调试器**" 旁边的绿色 "播放" 按钮。</span><span class="sxs-lookup"><span data-stu-id="c469d-153">To run the debugger, choose the bit size of the platform, and then choose the green play button next to **Local Windows Debugger**.</span></span>  <span data-ttu-id="c469d-154">应用程序运行，并且调试器连接到创建的第一个 WebView2 进程。</span><span class="sxs-lookup"><span data-stu-id="c469d-154">The application runs and the debugger connects to the first WebView2 process that is created.</span></span>  
    
    :::image type="complex" source="./media/run.png" alt-text=" Visual Studio 本地 Windows 调试器" lightbox="./media/run.png"::: 
       <span data-ttu-id="c469d-156">Visual Studio **本地 Windows 调试器**</span><span class="sxs-lookup"><span data-stu-id="c469d-156">Visual Studio **Local Windows Debugger**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c469d-157">在 **调试控制台**中，查找来自调试器的输出。</span><span class="sxs-lookup"><span data-stu-id="c469d-157">In the **Debug Console**, find the output from the debugger.</span></span>  
    
    :::image type="complex" source="./media/console.png" alt-text=" Visual Studio 调试控制台" lightbox="./media/console.png"::: 
       <span data-ttu-id="c469d-159">Visual Studio **调试控制台**</span><span class="sxs-lookup"><span data-stu-id="c469d-159">Visual Studio **Debug Console**</span></span>  
    :::image-end:::  
    
* * *  

## <span data-ttu-id="c469d-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c469d-160">See also</span></span>  

*   <span data-ttu-id="c469d-161">若要开始使用 WebView2，请参阅 [WebView2 入门指南][Webview2MainGettingStarted]。</span><span class="sxs-lookup"><span data-stu-id="c469d-161">To get started using WebView2, see [WebView2 Getting Started Guides][Webview2MainGettingStarted].</span></span>  
*   <span data-ttu-id="c469d-162">有关 WebView2 功能的完整示例，请参阅 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 存储库。</span><span class="sxs-lookup"><span data-stu-id="c469d-162">For a comprehensive example of WebView2 capabilities, see the [WebView2Samples][GithubMicrosoftedgeWebview2samples] repo on GitHub.</span></span>
*   <span data-ttu-id="c469d-163">有关 WebView2 Api 的更多详细信息，请参阅 [API 参考][Webview2ApiReference]。</span><span class="sxs-lookup"><span data-stu-id="c469d-163">For more detailed information about WebView2 APIs, see [API reference][Webview2ApiReference].</span></span>
*   <span data-ttu-id="c469d-164">有关 WebView2 的详细信息，请参阅 [WebView2 资源][Webview2MainNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="c469d-164">For more information about WebView2, see [WebView2 Resources][Webview2MainNextSteps].</span></span>

## <span data-ttu-id="c469d-165">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="c469d-165">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发人员工具"  

[Webview2ReferenceDotnet09515MicrosoftWebWebview2CoreCorewebview2environmentoptionsAdditionalbrowserarguments]: ../reference/dotnet/0-9-515/microsoft-web-webview2-core-corewebview2environmentoptions.md#additionalbrowserarguments "AdditionalBrowserArguments-0.9.515-WebView2 for CoreWebView2EnvironmentOptions 类 |Microsoft 文档"  
[Webview2ReferenceWin3209538Webview2IdlParameters]: ../reference/win32/0-9-538/webview2-idl.md#createcorewebview2environment  "CreateCoreWebView2Environment-Globals |Microsoft 文档"  
[Webview2ApiReference]: ../webview2-api-reference.md "Microsoft Edge WebView2 API 参考 |Microsoft 文档"  
[Webview2MainNextSteps]: ../index.md#next-steps "后续步骤-Microsoft Edge WebView2 简介 (预览) |Microsoft 文档"  
[Webview2MainGettingStarted]: ../index.md#getting-started "入门-Microsoft Edge WebView2 简介 (预览版) |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftVscodeJSDebugWhatsNew]: https://github.com/microsoft/vscode-js-debug#whats-new "新增功能-适用于 Visual Studio 代码的 JavaScript 调试程序-microsoft/vscode-debug |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) Web 视图应用程序-Visual Studio 代码-Microsoft Edge 的调试器-microsoft/vscode-debug2 |GitHub"  
