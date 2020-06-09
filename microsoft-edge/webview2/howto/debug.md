---
description: 了解如何调试 WebView2 控件。
title: 调试 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2020
ms.topic: how-to
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 7e3ee11de443713a14684023fcd90de3cb1d265a
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697747"
---
# <span data-ttu-id="dda4c-104">如何在与 WebView2 控件一起开发时进行调试</span><span class="sxs-lookup"><span data-stu-id="dda4c-104">How to debug when developing with WebView2 controls</span></span>  

<span data-ttu-id="dda4c-105">Microsoft Edge WebView2 控件的目标是结合 web 和本机应用程序开发功能和开发人员工具的优势。</span><span class="sxs-lookup"><span data-stu-id="dda4c-105">The goal of the Microsoft Edge WebView2 control is combining the best of both the web and native application development features and developer tools.</span></span>  <span data-ttu-id="dda4c-106">本文概述了使用 WebView2 控件进行开发时要使用的不同工具。</span><span class="sxs-lookup"><span data-stu-id="dda4c-106">This article outlines the different tools to use when developing with WebView2 controls.</span></span>  

## <span data-ttu-id="dda4c-107">Microsoft Edge 开发工具</span><span class="sxs-lookup"><span data-stu-id="dda4c-107">Microsoft Edge DevTools</span></span>  

<span data-ttu-id="dda4c-108">使用[Microsoft edge （Chromium）开发人员工具](/microsoft-edge/devtools-guide-chromium)来调试在 WebView2 控件中显示的 web 内容，方法与你使用 Microsoft Edge 的方式相同。</span><span class="sxs-lookup"><span data-stu-id="dda4c-108">Use [Microsoft Edge (Chromium) Developer Tools](/microsoft-edge/devtools-guide-chromium) to debug web content displayed in WebView2 controls, in the same way that you would if you were using Microsoft Edge.</span></span>  <span data-ttu-id="dda4c-109">若要打开 DevTools，请将焦点置于 "Web 视图" 窗口，然后使用以下任一选项。</span><span class="sxs-lookup"><span data-stu-id="dda4c-109">To open the DevTools, set focus on the WebView window and then use any of the following options.</span></span>  
*   <span data-ttu-id="dda4c-110">选择 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="dda4c-110">Select `F12`.</span></span>  
*   <span data-ttu-id="dda4c-111">选择 `Ctrl` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="dda4c-111">Select `Ctrl`+`Shift`+`I`.</span></span>  
*   <span data-ttu-id="dda4c-112">打开上下文菜单 \ （右键单击 \） > 选择 `Inspect` 。</span><span class="sxs-lookup"><span data-stu-id="dda4c-112">Open the context menu \(right-click\) > select `Inspect`.</span></span>  

:::image type="complex" source="../media/f12.png" alt-text="Microsoft Edge 开发工具":::
   <span data-ttu-id="dda4c-114">Microsoft Edge 开发工具</span><span class="sxs-lookup"><span data-stu-id="dda4c-114">Microsoft Edge DevTools</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="dda4c-115">在附加了本机调试器的 Visual Studio 中调试应用程序时，选择 " `F12` 可能会触发本机调试器，而不是开发工具"。</span><span class="sxs-lookup"><span data-stu-id="dda4c-115">When you debug your application in Visual Studio with the native debugger attached, selecting `F12` may trigger the native debugger instead of Developer Tools.</span></span>  <span data-ttu-id="dda4c-116">使用 `Ctrl` + `Shift` + `I` 或使用上下文菜单 \ （右键单击 \）以避免这种情况。</span><span class="sxs-lookup"><span data-stu-id="dda4c-116">Use `Ctrl`+`Shift`+`I`, or use the context menu \(right-click\) to avoid this situation.</span></span>  

## <span data-ttu-id="dda4c-117">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dda4c-117">Visual Studio</span></span>  

<span data-ttu-id="dda4c-118">使用 Visual Studio 2019 版本16.4 预览版2或更高版本中的脚本调试程序在 Visual Studio 中调试你的脚本。</span><span class="sxs-lookup"><span data-stu-id="dda4c-118">Use the script debugger in Visual Studio 2019 version 16.4 Preview 2 or later to debug your script in Visual Studio.</span></span>  <span data-ttu-id="dda4c-119">验证安装了**c + +** 工作负荷的桌面开发中的**JavaScript 诊断**组件。</span><span class="sxs-lookup"><span data-stu-id="dda4c-119">Verify the **JavaScript diagnostics** component in **Desktop development with C++** workload is installed.</span></span>  

:::image type="complex" source="../media/vs-js-diagnostics.jpg" alt-text="Visual Studio JavaScript 诊断":::
   <span data-ttu-id="dda4c-121">Visual Studio JavaScript 诊断</span><span class="sxs-lookup"><span data-stu-id="dda4c-121">Visual Studio JavaScript diagnostics</span></span>  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

<span data-ttu-id="dda4c-122">若要启用 WebView2 脚本调试，请打开项目上的上下文菜单 \ （右键单击 \） > 选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="dda4c-122">To enable WebView2 script debugging, open the context menu \(right-click\) on your project > select **Properties**.</span></span>  <span data-ttu-id="dda4c-123">在**配置属性**上，选择 "**调试**"。</span><span class="sxs-lookup"><span data-stu-id="dda4c-123">On **Configuration Properties**, select **Debugging**.</span></span>  <span data-ttu-id="dda4c-124">在 "**调试器类型**" 属性中，从选项列表中选择 " **JavaScript （WebView2）** "。</span><span class="sxs-lookup"><span data-stu-id="dda4c-124">On the **Debugger Type** property, choose **JavaScript (WebView2)** from the list of options.</span></span> 

:::image type="complex" source="../media/vs-script-debugger.jpg" alt-text="Visual Studio JavaScript 调试器":::
   <span data-ttu-id="dda4c-126">Visual Studio JavaScript 调试器</span><span class="sxs-lookup"><span data-stu-id="dda4c-126">Visual Studio JavaScript Debugger</span></span>  
:::image-end:::  

<!--todo: Please update the image to use a red rectangle to outline the portion of the screen to highlight  -->  

## <span data-ttu-id="dda4c-127">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="dda4c-127">Visual Studio Code</span></span>  

<span data-ttu-id="dda4c-128">你可以使用 Visual Studio 代码调试在 WebView2 控件中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="dda4c-128">You may use Visual Studio Code to debug scripts that run in WebView2 controls.</span></span>  <span data-ttu-id="dda4c-129">有关详细信息，请参阅[Microsoft Edge （Chromium） Web 视图应用程序](https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications)。</span><span class="sxs-lookup"><span data-stu-id="dda4c-129">For more information, see [Microsoft Edge (Chromium) WebView Applications](https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications).</span></span>  

<!--todo:  add See also heading  -->  

## <span data-ttu-id="dda4c-130">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="dda4c-130">Getting in touch with the Microsoft Edge WebView team</span></span>  

<span data-ttu-id="dda4c-131">通过分享你的反馈来帮助构建更丰富的 WebView2 体验。</span><span class="sxs-lookup"><span data-stu-id="dda4c-131">Help build a richer WebView2 experience by sharing your feedback.</span></span>  <span data-ttu-id="dda4c-132">访问[反馈](https://aka.ms/webviewfeedback)存储库以提交功能请求或 bug 报告。</span><span class="sxs-lookup"><span data-stu-id="dda4c-132">Visit the [feedback repo](https://aka.ms/webviewfeedback) to submit feature requests or bug reports.</span></span>  
