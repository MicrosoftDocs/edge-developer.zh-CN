---
description: 了解如何调试 WebView2 控件。
title: 调试 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/10/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 6b2cc65e5cb368c29efec2eb3638f0c1772000d9
ms.sourcegitcommit: 4bc904c5d54347185f275bd76441975be471c320
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "10926475"
---
# <span data-ttu-id="31e52-104">如何通过 WebView2 进行调试</span><span class="sxs-lookup"><span data-stu-id="31e52-104">How to Debug with WebView2</span></span>  

<span data-ttu-id="31e52-105">Microsoft Edge WebView2 控件的目标是结合 web 和本机应用程序开发功能和开发人员工具的优势。</span><span class="sxs-lookup"><span data-stu-id="31e52-105">The goal of the Microsoft Edge WebView2 control is combining the best of both the web and native application development features and developer tools.</span></span>  <span data-ttu-id="31e52-106">下页概述了使用 WebView2 控件进行开发时要使用的不同工具。</span><span class="sxs-lookup"><span data-stu-id="31e52-106">The following page outlines the different tools to use when developing with WebView2 controls.</span></span>  

## <span data-ttu-id="31e52-107">Microsoft Edge 开发工具</span><span class="sxs-lookup"><span data-stu-id="31e52-107">Microsoft Edge DevTools</span></span>  

<span data-ttu-id="31e52-108">使用[Microsoft edge (Chromium) 开发人员工具][DevtoolsGuideChromiumMain]来调试在 WebView2 控件中显示的 web 内容，方法与使用 Microsoft Edge 相同。</span><span class="sxs-lookup"><span data-stu-id="31e52-108">Use [Microsoft Edge (Chromium) Developer Tools][DevtoolsGuideChromiumMain] to debug web content displayed in WebView2 controls, in the same way that you use Microsoft Edge.</span></span>  <span data-ttu-id="31e52-109">若要打开 DevTools，请将焦点置于 "Web 视图" 窗口，然后使用以下任一操作。</span><span class="sxs-lookup"><span data-stu-id="31e52-109">To open the DevTools, set focus on the WebView window and then use any of the following actions.</span></span>  
*   <span data-ttu-id="31e52-110">选择 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="31e52-110">Select `F12`.</span></span>  
*   <span data-ttu-id="31e52-111">选择 `Ctrl` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="31e52-111">Select `Ctrl`+`Shift`+`I`.</span></span>  
*   <span data-ttu-id="31e52-112">打开上下文菜单 \ (右键单击 \ ) > 选择 `Inspect` 。</span><span class="sxs-lookup"><span data-stu-id="31e52-112">Open the context menu \(right-click\) > select `Inspect`.</span></span>  

:::image type="complex" source="../media/f12.png" alt-text="Microsoft Edge 开发工具" lightbox="../media/f12.png":::
   <span data-ttu-id="31e52-114">Microsoft Edge 开发工具</span><span class="sxs-lookup"><span data-stu-id="31e52-114">Microsoft Edge DevTools</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="31e52-115">当在 Visual Studio 中调试应用程序时，如果附加了本机调试器，则按下 `F12` 可能会触发本机调试器，而不是开发人员工具。</span><span class="sxs-lookup"><span data-stu-id="31e52-115">When you debug your application in Visual Studio with the native debugger attached, pressing `F12` may trigger the native debugger instead of Developer Tools.</span></span>  <span data-ttu-id="31e52-116">按下 `Ctrl` + `Shift` + `I` 或使用上下文菜单 \ (右键单击 \ ) 以避免这种情况。</span><span class="sxs-lookup"><span data-stu-id="31e52-116">Press `Ctrl`+`Shift`+`I`, or use the context menu \(right-click\) to avoid the situation.</span></span>  

> [!NOTE]
> <span data-ttu-id="31e52-117">`--auto-open-devtools-for-tabs`首次创建 Web 视图时，可以使用命令行参数打开新的 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="31e52-117">You may use the `--auto-open-devtools-for-tabs` command-line argument to open a new DevTools window when you first create a WebView.</span></span>  <!--See `CreateCoreWebView2Controller` documentation for how to provide additional command-line arguments to the browser process.  See `LoaderOverride` registry key to examine different builds of WebView2 without modifying your application in the `CreateCoreWebView2Controller` documentation.  -->  

## <span data-ttu-id="31e52-118">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="31e52-118">Visual Studio</span></span>  

<span data-ttu-id="31e52-119">使用 Visual Studio 2019 版本16.4 预览版2或更高版本中的脚本调试程序在 Visual Studio 中调试你的脚本。</span><span class="sxs-lookup"><span data-stu-id="31e52-119">Use the script debugger in Visual Studio 2019 version 16.4 Preview 2 or later to debug your script in Visual Studio.</span></span>  <span data-ttu-id="31e52-120">验证安装了**c + +** 工作负荷的桌面开发中的**JavaScript 诊断**组件。</span><span class="sxs-lookup"><span data-stu-id="31e52-120">Verify the **JavaScript diagnostics** component in **Desktop development with C++** workload is installed.</span></span>  

:::image type="complex" source="../media/vs-js-diagnostics.jpg" alt-text="Visual Studio JavaScript 诊断":::
   <span data-ttu-id="31e52-122">Visual Studio JavaScript 诊断</span><span class="sxs-lookup"><span data-stu-id="31e52-122">Visual Studio JavaScript diagnostics</span></span>  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

<span data-ttu-id="31e52-123">若要启用 WebView2 脚本调试，请打开上下文菜单 \ (右键单击项目上的 \ ) > 选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="31e52-123">To enable WebView2 script debugging, open the context menu \(right-click\) on your project > select **Properties**.</span></span>  

*   <span data-ttu-id="31e52-124">在**配置属性**上，选择 "**调试**"。</span><span class="sxs-lookup"><span data-stu-id="31e52-124">On **Configuration Properties**, select **Debugging**.</span></span>  
*   <span data-ttu-id="31e52-125">在 "**调试器类型**" 属性中，从选项列表中选择 " \*\*JavaScript (WebView2") \*\* 。</span><span class="sxs-lookup"><span data-stu-id="31e52-125">On the **Debugger Type** property, select **JavaScript (WebView2)** from the list of options.</span></span> 

:::image type="complex" source="../media/vs-script-debugger.jpg" alt-text="Visual Studio JavaScript 调试器":::
   <span data-ttu-id="31e52-127">Visual Studio JavaScript 调试器</span><span class="sxs-lookup"><span data-stu-id="31e52-127">Visual Studio JavaScript Debugger</span></span>  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

<span data-ttu-id="31e52-128">你已准备好进行调试。</span><span class="sxs-lookup"><span data-stu-id="31e52-128">You are all set up and ready to debug.</span></span>  

<span data-ttu-id="31e52-129">若要进行调试，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="31e52-129">To Debug, complete the following actions.</span></span>  

1.  <span data-ttu-id="31e52-130">设置断点</span><span class="sxs-lookup"><span data-stu-id="31e52-130">Set Breakpoints</span></span>  
    *   <span data-ttu-id="31e52-131">打开脚本文件，并将断点设置为所需位置。</span><span class="sxs-lookup"><span data-stu-id="31e52-131">Open the script file and set the breakpoint where you want it.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="31e52-132">JS/TS 调试适配器不执行源路径映射。</span><span class="sxs-lookup"><span data-stu-id="31e52-132">The JS/TS debug adapter does not do source path mapping.</span></span><span data-ttu-id="31e52-133">您必须打开与您的 WebView2 相关联的完全相同的路径。</span><span class="sxs-lookup"><span data-stu-id="31e52-133">  You must open the exact same path associated with your WebView2.</span></span>  
        
1.  <span data-ttu-id="31e52-134">运行代码</span><span class="sxs-lookup"><span data-stu-id="31e52-134">Run Code</span></span>  
    *   <span data-ttu-id="31e52-135">选择适当的构建风格和运行时环境，然后启动本地 windows 调试器。</span><span class="sxs-lookup"><span data-stu-id="31e52-135">Select your appropriate build flavor and runtime environment and then start the local windows debugger.</span></span>  
1.  <span data-ttu-id="31e52-136">查看调试控制台</span><span class="sxs-lookup"><span data-stu-id="31e52-136">View Debug Console</span></span>  
    *   <span data-ttu-id="31e52-137">在创建第一个 webview2 后，你的应用程序运行和调试程序将连接。</span><span class="sxs-lookup"><span data-stu-id="31e52-137">You application runs and the debugger connects after the first webview2 is created.</span></span><span data-ttu-id="31e52-138">将显示任何挂起的调试输出。</span><span class="sxs-lookup"><span data-stu-id="31e52-138">  Any pending debug output is displayed.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="31e52-139">此调试方法当前仅限于 Win32 应用程序和 Office 外接程序。</span><span class="sxs-lookup"><span data-stu-id="31e52-139">This method of debugging is currently restricted to Win32 applications and Office add-ins.</span></span>  
        
## <span data-ttu-id="31e52-140">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="31e52-140">Visual Studio Code</span></span>  

<span data-ttu-id="31e52-141">你可以使用 Visual Studio 代码调试在 WebView2 控件中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="31e52-141">You may use Visual Studio Code to debug scripts that run in WebView2 controls.</span></span>  <span data-ttu-id="31e52-142">有关详细信息，请参阅[Microsoft Edge (Chromium) Web 视图应用程序][GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]。</span><span class="sxs-lookup"><span data-stu-id="31e52-142">For more information, see [Microsoft Edge (Chromium) WebView Applications][GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications].</span></span>  

<!--todo:  add See also heading  -->  

## <span data-ttu-id="31e52-143">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="31e52-143">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!--## Debugging  

Open DevTools with the normal shortcuts: `F12` or `Ctrl+Shift+I`. You can use the `--auto-open-devtools-for-tabs` command argument switch to have the DevTools window open immediately when first creating a WebView. See CreateCoreWebView2Controller documentation for how to provide additional command line arguments to the browser process. Check out the LoaderOverride registry key for trying out different builds of WebView2 without modifying your application in the CreateCoreWebView2Controller documentation.  -->  

<!-- links -->  

[DevtoolsGuideChromiumMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发人员工具"  

[GithubMicrosoftedgeWebviewfeedbackMain]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftVscodeEdgeDebug2ReadmeChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge (Chromium) Web 视图应用程序-VS 代码-Microsoft Edge 的调试器-microsoft/vscode-debug2 |GitHub"  
