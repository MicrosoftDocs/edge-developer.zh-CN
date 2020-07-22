---
description: 了解如何调试 WebView2 控件。
title: 调试 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 232104abc360cfa660d567ffb66535213fcb3ae0
ms.sourcegitcommit: a82aa5fc1ada35cd8274490fbff3c0a850785835
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "10888576"
---
# <span data-ttu-id="251d3-104">如何通过 WebView2 进行调试</span><span class="sxs-lookup"><span data-stu-id="251d3-104">How to Debug with WebView2</span></span>  

<span data-ttu-id="251d3-105">Microsoft Edge WebView2 控件的目标是结合 web 和本机应用程序开发功能和开发人员工具的优势。</span><span class="sxs-lookup"><span data-stu-id="251d3-105">The goal of the Microsoft Edge WebView2 control is combining the best of both the web and native application development features and developer tools.</span></span>  <span data-ttu-id="251d3-106">下页概述了使用 WebView2 控件进行开发时要使用的不同工具。</span><span class="sxs-lookup"><span data-stu-id="251d3-106">The following page outlines the different tools to use when developing with WebView2 controls.</span></span>  

## <span data-ttu-id="251d3-107">Microsoft Edge 开发工具</span><span class="sxs-lookup"><span data-stu-id="251d3-107">Microsoft Edge DevTools</span></span>  

<span data-ttu-id="251d3-108">使用[Microsoft edge （Chromium）开发人员工具][DevtoolsMain]来调试在 WebView2 控件中显示的 web 内容，方法与你使用 Microsoft Edge 的方式相同。</span><span class="sxs-lookup"><span data-stu-id="251d3-108">Use [Microsoft Edge (Chromium) Developer Tools][DevtoolsMain] to debug web content displayed in WebView2 controls, in the same way that you would if you were using Microsoft Edge.</span></span>  <span data-ttu-id="251d3-109">若要打开 DevTools，请将焦点置于 "Web 视图" 窗口，然后使用以下任一操作。</span><span class="sxs-lookup"><span data-stu-id="251d3-109">To open the DevTools, set focus on the WebView window and then use any of the following actions.</span></span>  

*   <span data-ttu-id="251d3-110">选择 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="251d3-110">Select `F12`.</span></span>  
*   <span data-ttu-id="251d3-111">选择 `Ctrl` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="251d3-111">Select `Ctrl`+`Shift`+`I`.</span></span>  
*   <span data-ttu-id="251d3-112">打开上下文菜单 \ （右键单击 \），然后选择 `Inspect` 。</span><span class="sxs-lookup"><span data-stu-id="251d3-112">Open the context menu \(right-click\) and select `Inspect`.</span></span>  

:::image type="complex" source="../media/f12.png" alt-text="Microsoft Edge 开发工具" lightbox="../media/f12.png":::
   <span data-ttu-id="251d3-114">Microsoft Edge 开发工具</span><span class="sxs-lookup"><span data-stu-id="251d3-114">Microsoft Edge DevTools</span></span>  
:::image-end:::  

> [!IMPORTANT]
> <span data-ttu-id="251d3-115">在附加了本机调试器的 Visual Studio 中调试应用程序时，选择 " `F12` 可能会触发本机调试器，而不是开发工具"。</span><span class="sxs-lookup"><span data-stu-id="251d3-115">When you debug your application in Visual Studio with the native debugger attached, selecting `F12` may trigger the native debugger instead of Developer Tools.</span></span>  <span data-ttu-id="251d3-116">使用 `Ctrl` + `Shift` + `I` 或使用上下文菜单 \ （右键单击 \）以避免这种情况。</span><span class="sxs-lookup"><span data-stu-id="251d3-116">Use `Ctrl`+`Shift`+`I`, or use the context menu \(right-click\) to avoid the situation.</span></span>  

## <span data-ttu-id="251d3-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="251d3-117">Visual Studio</span></span>  

<span data-ttu-id="251d3-118">你可以使用 Visual Studio 同时开发应用程序代码和调试脚本。</span><span class="sxs-lookup"><span data-stu-id="251d3-118">You may use Visual Studio to develop application code and debug scripts at the same time.</span></span>  

<span data-ttu-id="251d3-119">请记住以下事项。</span><span class="sxs-lookup"><span data-stu-id="251d3-119">Keep the following things in mind.</span></span>  

*   <span data-ttu-id="251d3-120">Visual Studio 仅支持在从 Visual Studio 内部启动应用时调试脚本。</span><span class="sxs-lookup"><span data-stu-id="251d3-120">Visual Studio only supports debugging scripts when the app is launched from within Visual Studio.</span></span>  <span data-ttu-id="251d3-121">\ （不支持附加正在运行的进程进行调试。）</span><span class="sxs-lookup"><span data-stu-id="251d3-121">\(Attaching a running process for debugging is not supported.\)</span></span>  
*   <span data-ttu-id="251d3-122">不支持目标 Web 视图调试方案。</span><span class="sxs-lookup"><span data-stu-id="251d3-122">The targeted WebView debugging scenario is not supported.</span></span>  

<span data-ttu-id="251d3-123">使用 Visual Studio 2019 版本16.4 预览版2或更高版本中的脚本调试程序在 Visual Studio 中调试你的脚本。</span><span class="sxs-lookup"><span data-stu-id="251d3-123">Use the script debugger in Visual Studio 2019 version 16.4 Preview 2 or later to debug your script in Visual Studio.</span></span>  

<span data-ttu-id="251d3-124">设置调试器。</span><span class="sxs-lookup"><span data-stu-id="251d3-124">Set up the debugger.</span></span>  

*   <span data-ttu-id="251d3-125">验证安装了**c + +** 工作负荷的桌面开发中的**JavaScript 诊断**组件。</span><span class="sxs-lookup"><span data-stu-id="251d3-125">Verify the **JavaScript diagnostics** component in **Desktop development with C++** workload is installed.</span></span>  
    
    1.  <span data-ttu-id="251d3-126">导航到 Windows 中的**应用 & 功能**设置。</span><span class="sxs-lookup"><span data-stu-id="251d3-126">Navigate to **Apps & features** settings in Windows.</span></span>  <span data-ttu-id="251d3-127">使用 Windows 任务条搜索它。</span><span class="sxs-lookup"><span data-stu-id="251d3-127">Search for it using the Windows task bar.</span></span>  
    1.  <span data-ttu-id="251d3-128">选择 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="251d3-128">Choose **Modify**.</span></span>  
    1.  <span data-ttu-id="251d3-129">验证是否已选中 " **c + +** " 复选框中的**Javascript 诊断**和桌面开发。</span><span class="sxs-lookup"><span data-stu-id="251d3-129">Verify the **Javascript diagnostics** and **Desktop Development in C++** checkboxes are selected.</span></span>  
        
        :::image type="complex" source="../media/appsandfeatures.png" alt-text="应用和功能" lightbox="../media/appsandfeatures.png":::
           <span data-ttu-id="251d3-131">应用和功能</span><span class="sxs-lookup"><span data-stu-id="251d3-131">Apps & Features</span></span>  
        :::image-end:::  
        
*   <span data-ttu-id="251d3-132">启用 WebView2 脚本调试。</span><span class="sxs-lookup"><span data-stu-id="251d3-132">Enable WebView2 script debugging.</span></span>  
    1.  <span data-ttu-id="251d3-133">将鼠标悬停在项目上，打开上下文菜单 \ （右键单击 \），然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="251d3-133">Hover on your project, open the context menu \(right-click\), and select **Properties**.</span></span>  
    1.  <span data-ttu-id="251d3-134">在**配置属性**上，选择 "**调试**"。</span><span class="sxs-lookup"><span data-stu-id="251d3-134">On **Configuration Properties**, select **Debugging**.</span></span>  
    1.  <span data-ttu-id="251d3-135">在 "**调试器类型**" 属性中，搜索选项列表，然后选择 " **JavaScript （WebView2）**"。</span><span class="sxs-lookup"><span data-stu-id="251d3-135">On the **Debugger Type** property, search the the list of options, and select **JavaScript (WebView2)**.</span></span>  
        
        :::image type="complex" source="../media/enbjs.png" alt-text="Visual Studio JavaScript 调试器" lightbox="../media/enbjs.png":::
           <span data-ttu-id="251d3-137">Visual Studio JavaScript 调试器</span><span class="sxs-lookup"><span data-stu-id="251d3-137">Visual Studio JavaScript Debugger</span></span>  
        :::image-end:::  
        
<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

<span data-ttu-id="251d3-138">你已准备好进行调试。</span><span class="sxs-lookup"><span data-stu-id="251d3-138">You are all set up and ready to debug.</span></span>  

<span data-ttu-id="251d3-139">若要进行调试，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="251d3-139">To Debug, complete the following actions.</span></span>  

1.  <span data-ttu-id="251d3-140">设置断点</span><span class="sxs-lookup"><span data-stu-id="251d3-140">Set Breakpoints</span></span>  
    *   <span data-ttu-id="251d3-141">打开脚本文件，并将断点设置为所需位置。</span><span class="sxs-lookup"><span data-stu-id="251d3-141">Open the script file and set the breakpoint where you want it.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="251d3-142">JS/TS 调试适配器不执行源路径映射。</span><span class="sxs-lookup"><span data-stu-id="251d3-142">The JS/TS debug adapter does not do source path mapping.</span></span><span data-ttu-id="251d3-143">您必须打开与您的 WebView2 相关联的完全相同的路径。</span><span class="sxs-lookup"><span data-stu-id="251d3-143">  You must open the exact same path associated with your WebView2.</span></span>  
        
1.  <span data-ttu-id="251d3-144">运行代码</span><span class="sxs-lookup"><span data-stu-id="251d3-144">Run Code</span></span>  
    *   <span data-ttu-id="251d3-145">选择适当的构建风格和运行时环境，然后启动本地 windows 调试器。</span><span class="sxs-lookup"><span data-stu-id="251d3-145">Select your appropriate build flavor and runtime environment and then start the local windows debugger.</span></span>  
1.  <span data-ttu-id="251d3-146">查看调试控制台</span><span class="sxs-lookup"><span data-stu-id="251d3-146">View Debug Console</span></span>  
    *   <span data-ttu-id="251d3-147">在创建第一个 webview2 后，你的应用程序运行和调试程序将连接。</span><span class="sxs-lookup"><span data-stu-id="251d3-147">You application runs and the debugger connects after the first webview2 is created.</span></span><span data-ttu-id="251d3-148">将显示任何挂起的调试输出。</span><span class="sxs-lookup"><span data-stu-id="251d3-148">  Any pending debug output is displayed.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="251d3-149">此调试方法当前仅限于 Win32 应用程序和 Office 外接程序。</span><span class="sxs-lookup"><span data-stu-id="251d3-149">This method of debugging is currently restricted to Win32 applications and Office add-ins.</span></span>  
        
## <span data-ttu-id="251d3-150">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="251d3-150">Visual Studio Code</span></span>  

<span data-ttu-id="251d3-151">你可以使用 Visual Studio 代码调试在 WebView2 控件中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="251d3-151">You may use Visual Studio Code to debug scripts that run in WebView2 controls.</span></span>  <span data-ttu-id="251d3-152">有关详细信息，请参阅[Microsoft Edge （Chromium） Web 视图应用程序][GithubMicrosoftVscodeEdgeDebug2MainChromiumWebviewApplications]。</span><span class="sxs-lookup"><span data-stu-id="251d3-152">For more information, see [Microsoft Edge (Chromium) WebView Applications][GithubMicrosoftVscodeEdgeDebug2MainChromiumWebviewApplications].</span></span>  

<!--todo:  add See also heading  -->  

## <span data-ttu-id="251d3-153">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="251d3-153">Getting in touch with the Microsoft Edge WebView team</span></span>  

<span data-ttu-id="251d3-154">通过分享你的反馈来帮助构建更丰富的 WebView2 体验。</span><span class="sxs-lookup"><span data-stu-id="251d3-154">Help build a richer WebView2 experience by sharing your feedback.</span></span>  <span data-ttu-id="251d3-155">访问[反馈][GithubMicrosoftedgeWebviewfeedback]存储库以提交功能请求或 bug 报告。</span><span class="sxs-lookup"><span data-stu-id="251d3-155">Visit the [feedback repo][GithubMicrosoftedgeWebviewfeedback] to submit feature requests or bug reports.</span></span>  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发工具 |Microsoft 文档"  

[GithubMicrosoftVscodeEdgeDebug2MainChromiumWebviewApplications]: https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications "Microsoft Edge （Chromium） Web 视图应用程序-VS 代码-Microsoft Edge 调试程序 |GitHub"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  
