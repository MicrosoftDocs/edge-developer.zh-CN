---
description: Microsoft Edge 在 Linux 上，改进了 "问题" 工具中的 webhint 提示、新服务工作人员调试功能等。
title: DevTools (Microsoft Edge 88) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 500b64e7b51e0f02c9fcbcb7a83e8273b3a5a0d7
ms.sourcegitcommit: 3234b32e73c9f8362082d995296bd1c5e4286036
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "11205241"
---
# <span data-ttu-id="8ac46-104">DevTools (Microsoft Edge 88) 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="8ac46-104">What's New in DevTools (Microsoft Edge 88)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <span data-ttu-id="8ac46-105">Microsoft Edge 和 Microsoft Edge 驱动程序现已在 Linux 上提供</span><span class="sxs-lookup"><span data-stu-id="8ac46-105">Microsoft Edge and Microsoft Edge Driver now available on Linux</span></span>  

<!-- Title: Microsoft Edge and Microsoft Edge Driver on Linux  -->  
<!-- Subtitle: Get Microsoft Edge Dev on Ubuntu, Debian, Fedora, and openSUSE distributions and start automating in CI/CD environments with Microsoft Edge Driver. -->  

<span data-ttu-id="8ac46-106">Microsoft Edge 开发现在支持 Ubuntu、Debian、Fedora 和 openSUSE 分布。</span><span class="sxs-lookup"><span data-stu-id="8ac46-106">Microsoft Edge Dev is now supported on Ubuntu, Debian, Fedora, and openSUSE distributions.</span></span>  <span data-ttu-id="8ac46-107">`.deb` `.rpm` 直接从[Microsoft Edge 预览体验计划网站][MicrosoftinsiderDownloadPlatformLinux]下载并安装 microsoft edge 开发人员或程序包，或使用 Linux 分发版的标准程序包管理工具。</span><span class="sxs-lookup"><span data-stu-id="8ac46-107">Download and install the Microsoft Edge Dev `.deb` or `.rpm` package directly from the [Microsoft Edge Insider site][MicrosoftinsiderDownloadPlatformLinux] or use the standard package management tools of your Linux distribution.</span></span>  

<span data-ttu-id="8ac46-108">如果你在持续集成和传递 \ (CI/CD \ ) 解决方案中使用 Linux 环境，则在 Linux 上也可以使用 Microsoft Edge 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="8ac46-108">If you are using a Linux environment in your continuous integration and delivery \(CI/CD\) solutions, Microsoft Edge Driver is also available on Linux.</span></span>  <span data-ttu-id="8ac46-109">若要开始使用 Microsoft Edge 驱动程序自动执行 Microsoft Edge 开发，请导航到 [Microsoft Edge 驱动程序下载页面][MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]。</span><span class="sxs-lookup"><span data-stu-id="8ac46-109">To get started automating Microsoft Edge Dev with Microsoft Edge Driver, navigate to [Microsoft Edge Driver Downloads page][MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads].</span></span>  <span data-ttu-id="8ac46-110">若要获取 Microsoft edge 开发人员和 Microsoft Edge 驱动程序的自动化帮助，请导航到 [使用 WebDriver (Chromium) 进行测试自动化][WebDriverChromiumMain]。</span><span class="sxs-lookup"><span data-stu-id="8ac46-110">For help with automating Microsoft Edge Dev along with Microsoft Edge Driver, navigate to [Use WebDriver (Chromium) for test automation][WebDriverChromiumMain].</span></span>  

:::image type="complex" source="../../media/2020/11/edge-on-linux.msft.png" alt-text="DevTools 在 Linux 上的 Microsoft Edge 中" lightbox="../../media/2020/11/edge-on-linux.msft.png":::
   <span data-ttu-id="8ac46-112">DevTools 在 Linux 上的 Microsoft Edge 中</span><span class="sxs-lookup"><span data-stu-id="8ac46-112">DevTools in Microsoft Edge on Linux</span></span>  
:::image-end:::  

## <span data-ttu-id="8ac46-113">改进了 "问题" 工具中的 webhint 和平台提示</span><span class="sxs-lookup"><span data-stu-id="8ac46-113">Improved webhint and platform tips in the Issues tool</span></span>  

<!-- Title: Improvements to Issues tool and webhint integration  -->  
<!-- Subtitle: Categories and third-party filtering make it easier to survey issues in the Issues tool.  Issues surfaced by webhint now have improved code snippets and documentation links to help you fix problems in your website.  -->  

<span data-ttu-id="8ac46-114">开放源代码工具 [webhint][WebhintMain]提供对网站和本地网页的实时反馈。</span><span class="sxs-lookup"><span data-stu-id="8ac46-114">An open-source tool, [webhint][WebhintMain], provides real-time feedback for websites and local webpages.</span></span>  <span data-ttu-id="8ac46-115">从 [Microsoft Edge 版本 85][WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel]开始，在 " [问题][DevtoolsIssuesIndex] " 工具中查看 webhint 反馈。</span><span class="sxs-lookup"><span data-stu-id="8ac46-115">Starting with [Microsoft Edge version 85][WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel], review webhint feedback in the [Issues][DevtoolsIssuesIndex] tool.</span></span>  <span data-ttu-id="8ac46-116">通过添加以下类别，" **问题** " 工具中显示的问题现在更易于查看。</span><span class="sxs-lookup"><span data-stu-id="8ac46-116">Issues that appear in the **Issues** tool are now easier to review with the addition of the following categories.</span></span>  

*   [<span data-ttu-id="8ac46-117">辅助功能</span><span class="sxs-lookup"><span data-stu-id="8ac46-117">Accessibility</span></span>][WebhintUserGuideHintsAccessibility]  
*   [<span data-ttu-id="8ac46-118">兼容性</span><span class="sxs-lookup"><span data-stu-id="8ac46-118">Compatibility</span></span>][WebhintUserGuideHintsCompatibility]  
*   [<span data-ttu-id="8ac46-119">性能</span><span class="sxs-lookup"><span data-stu-id="8ac46-119">Performance</span></span>][WebhintUserGuideHintsPerformance]  
*   [<span data-ttu-id="8ac46-120">陷阱</span><span class="sxs-lookup"><span data-stu-id="8ac46-120">Pitfalls</span></span>][WebhintUserGuideHintsPitfalls]  
*   [<span data-ttu-id="8ac46-121">PWA</span><span class="sxs-lookup"><span data-stu-id="8ac46-121">PWA</span></span>][WebhintUserGuideHintsPwa]  
*   [<span data-ttu-id="8ac46-122">安全性</span><span class="sxs-lookup"><span data-stu-id="8ac46-122">Security</span></span>][WebhintUserGuideHintsSecurity]  
    
<span data-ttu-id="8ac46-123">现在，你可以使用新的复选框筛选出第三方问题。</span><span class="sxs-lookup"><span data-stu-id="8ac46-123">You are now able to filter out third-party issues using a new checkbox.</span></span>  <span data-ttu-id="8ac46-124">筛选器功能可帮助你隐藏与第三方库或其他源中的代码相关的问题。</span><span class="sxs-lookup"><span data-stu-id="8ac46-124">The filter functionality helps you hide issues related to code from third-party libraries or other sources.</span></span>  

<span data-ttu-id="8ac46-125">为了帮助你查看 [webhint][WebhintMain]显示的问题，" **问题** " 工具现在显示以下信息。</span><span class="sxs-lookup"><span data-stu-id="8ac46-125">To help you review issues revealed by [webhint][WebhintMain], the **Issues** tool now displays the following information.</span></span>  

*   <span data-ttu-id="8ac46-126">改进的代码段。</span><span class="sxs-lookup"><span data-stu-id="8ac46-126">Improved code snippets.</span></span>  
*   <span data-ttu-id="8ac46-127">指向其他相关面板的链接。</span><span class="sxs-lookup"><span data-stu-id="8ac46-127">Links to other relevant panels.</span></span>  
*   <span data-ttu-id="8ac46-128">指向帮助你解决网站中的问题的文档的链接。</span><span class="sxs-lookup"><span data-stu-id="8ac46-128">Links to documentation to help you fix problems in your website.</span></span>  
    
:::image type="complex" source="../../media/2020/11/issues-webhints.msft.png" alt-text="问题工具" lightbox="../../media/2020/11/issues-webhints.msft.png":::
   <span data-ttu-id="8ac46-130">**问题** 工具</span><span class="sxs-lookup"><span data-stu-id="8ac46-130">**Issues** tool</span></span>  
:::image-end:::  

## <span data-ttu-id="8ac46-131">复合图层现在位于3D 视图中</span><span class="sxs-lookup"><span data-stu-id="8ac46-131">Composited Layers are now in 3D View</span></span>  

<!-- Title: 3D View is now integrated with Composited Layers  -->  
<!-- Subtitle: Composited Layers are now in 3D View.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::

<span data-ttu-id="8ac46-132">现在，你可以将 **层** 内容与 z 索引值和文档对象模型（ (DOM \ ) ）可视化。</span><span class="sxs-lookup"><span data-stu-id="8ac46-132">You may now visualize **Layers** content alongside z-index values and the Document Object Model \(DOM\).</span></span>  <span data-ttu-id="8ac46-133">此功能可帮助你在不切换 [3d 视图][Devtools3dViewIndex] 和 **分层** 工具的情况下进行调试。</span><span class="sxs-lookup"><span data-stu-id="8ac46-133">This feature helps you debug without switching between the [3D view][Devtools3dViewIndex] and **Layers** tools as often.</span></span>  <span data-ttu-id="8ac46-134">为了获得全面的可视化调试体验， [现在组合了3D 视图和复合图层][DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]。</span><span class="sxs-lookup"><span data-stu-id="8ac46-134">For a comprehensive visual debugging experience, the [3D View and Composited Layers are now combined][DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView].</span></span>  

:::image type="complex" source="../../media/2020/11/experiments-layers.msft.png" alt-text=""复合图层" 窗格" lightbox="../../media/2020/11/experiments-layers.msft.png":::
   <span data-ttu-id="8ac46-136">"**复合图层**" 窗格</span><span class="sxs-lookup"><span data-stu-id="8ac46-136">**Composited Layers** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="8ac46-137">"样式" 窗格中的 CSS 变量定义</span><span class="sxs-lookup"><span data-stu-id="8ac46-137">CSS variable definitions in Styles pane</span></span>  

<!-- Title: Jump to CSS variable definitions  -->  
<!-- Subtitle: Choose any CSS variable to navigate directly to the definition in the Styles tool. -->  

<span data-ttu-id="8ac46-138">在 " **样式** " 窗格中， [CSS 变量][MdnUsingCssCustomProperties] 现在直接链接到每个定义。</span><span class="sxs-lookup"><span data-stu-id="8ac46-138">In the **Styles** pane, [CSS variables][MdnUsingCssCustomProperties] now link directly to each definition.</span></span>  <span data-ttu-id="8ac46-139">选择变量以轻松查看或更改 CSS 变量定义。</span><span class="sxs-lookup"><span data-stu-id="8ac46-139">Choose the variable to easily view or change the CSS variable definition.</span></span>  <span data-ttu-id="8ac46-140">在此示例中，DevTools 显示元素的 CSS 属性 `body` 。</span><span class="sxs-lookup"><span data-stu-id="8ac46-140">In the example, DevTools displays the CSS attributes for the `body` element.</span></span>  <span data-ttu-id="8ac46-141">若要显示 CSS 变量的变量定义 `--theme-body-background` ，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8ac46-141">To display the variable definition for the `--theme-body-background` CSS variable, complete the following actions.</span></span>  

1.  <span data-ttu-id="8ac46-142">在 " **样式** " 窗格中，选择 `var(--theme-body-background)` 。</span><span class="sxs-lookup"><span data-stu-id="8ac46-142">In the **Styles** pane, choose `var(--theme-body-background)`.</span></span>  
1.  <span data-ttu-id="8ac46-143">" **样式** " 窗格现在显示了 `--theme-body-background` CSS 变量的定义。</span><span class="sxs-lookup"><span data-stu-id="8ac46-143">The **Styles** pane now displays the definition of the `--theme-body-background` CSS variable.</span></span>  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support.msft.png" alt-text="链接到样式的 CSS 变量" lightbox="../../media/2020/11/css-variable-support.msft.png":::
         <span data-ttu-id="8ac46-145">链接到样式的 CSS 变量</span><span class="sxs-lookup"><span data-stu-id="8ac46-145">CSS variable linked to the style</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support-target.msft.png" alt-text="链接到样式目标的 CSS 变量" lightbox="../../media/2020/11/css-variable-support-target.msft.png":::
         <span data-ttu-id="8ac46-147">链接到样式目标的 CSS 变量</span><span class="sxs-lookup"><span data-stu-id="8ac46-147">CSS variable linked to style target</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="8ac46-148">服务工作人员调试改进</span><span class="sxs-lookup"><span data-stu-id="8ac46-148">Service worker debugging improvements</span></span>  

<!-- Title:  Service worker debugging improvements in the Network, Application, and Sources tools  -->  
<!-- Subtitle:  Making service workers easier to debug for progressive web applications and more.  -->  

<span data-ttu-id="8ac46-149">[网络](#network-tool)、[应用程序](#application-tool)和[源](#sources-tool)工具中的以下新增功能可帮助你构建[PWA][ProgressiveWebAppsChromiumIndex]。</span><span class="sxs-lookup"><span data-stu-id="8ac46-149">The following new features in the [Network](#network-tool), [Application](#application-tool), and [Sources](#sources-tool) tools help you build your [PWA][ProgressiveWebAppsChromiumIndex].</span></span>  <span data-ttu-id="8ac46-150">如果在调试服务工作人员时遇到困难，请使用以下功能。</span><span class="sxs-lookup"><span data-stu-id="8ac46-150">Use the following features when you have difficulty debugging your service worker.</span></span>  

<span data-ttu-id="8ac46-151">请求路由显示 `startup` `fetch` 基于通过服务工作人员运行的网络请求的和事件。</span><span class="sxs-lookup"><span data-stu-id="8ac46-151">Request routing displays the `startup` and `fetch` events based on the network requests that run through service workers.</span></span>  <span data-ttu-id="8ac46-152">可从 " **应用程序** " 或 " **网络** " 工具访问时间线。</span><span class="sxs-lookup"><span data-stu-id="8ac46-152">The timelines are accessed from either the **Application** or **Network** tool.</span></span>  <span data-ttu-id="8ac46-153">时间线可帮助你在服务工作人员遇到问题时希望查看是否有某些内容出现错误 `startup` `fetch` 。</span><span class="sxs-lookup"><span data-stu-id="8ac46-153">The timelines help when you are having trouble with service workers and want to see if something is wrong with the `startup` or `fetch` event.</span></span>  

### <span data-ttu-id="8ac46-154">应用程序工具</span><span class="sxs-lookup"><span data-stu-id="8ac46-154">Application tool</span></span>  

<!-- Title: Open Network tool from the Service Workers pane  -->  
<!-- Subtitle: Display additional context when debugging a service worker.  -->  

<span data-ttu-id="8ac46-155">查看 "新的 **网络请求** " 链接中的所有服务工作人员请求路由信息。</span><span class="sxs-lookup"><span data-stu-id="8ac46-155">View all service worker request routing information with the new **Network requests** link.</span></span>  <span data-ttu-id="8ac46-156">若要在调试服务工作人员时显示其他上下文，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8ac46-156">To display additional context when debugging the service worker, complete the following actions.</span></span>  

1.  <span data-ttu-id="8ac46-157">导航到**应用程序**  >  **服务工作人员**。</span><span class="sxs-lookup"><span data-stu-id="8ac46-157">Navigate to **Application** > **Service Workers**.</span></span>  
1.  <span data-ttu-id="8ac46-158">选择 " **网络请求**"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-158">Choose **Network requests**.</span></span>  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-requests.msft.png" alt-text="从 "服务工作人员" 窗格打开网络工具" lightbox="../../media/2020/11/service-worker-application-network-requests.msft.png":::
       <span data-ttu-id="8ac46-160">从 "**服务工作人员**" 窗格打开**网络**工具</span><span class="sxs-lookup"><span data-stu-id="8ac46-160">Open **Network** tool from the **Service Workers** pane</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="8ac46-161">**网络**工具将在**抽屉**中打开，并显示与服务工作人员相关的所有网络请求。</span><span class="sxs-lookup"><span data-stu-id="8ac46-161">The **Network** tool opens in the **drawer** and displays all service worker-related network requests.</span></span>  <span data-ttu-id="8ac46-162">将使用筛选网络请求 `is:service-worker-intercepted` 。</span><span class="sxs-lookup"><span data-stu-id="8ac46-162">The network requests are filtered using `is:service-worker-intercepted`.</span></span>  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-drawer.msft.png" alt-text="抽屉中的网络工具" lightbox="../../media/2020/11/service-worker-application-network-drawer.msft.png":::
       <span data-ttu-id="8ac46-164">**抽屉**中的**网络**工具</span><span class="sxs-lookup"><span data-stu-id="8ac46-164">**Network** tool in **drawer**</span></span>  
    :::image-end:::
    
1. <span data-ttu-id="8ac46-165">若要将 **网络** 工具恢复到顶部面板，请关闭 **抽屉**。</span><span class="sxs-lookup"><span data-stu-id="8ac46-165">To return the **Network** tool to the top panel, close the **drawer**.</span></span>  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-return.msft.png" alt-text="关闭抽屉以返回网络工具" lightbox="../../media/2020/11/service-worker-application-network-return.msft.png":::
       <span data-ttu-id="8ac46-167">关闭 **抽屉** 以返回 **网络** 工具</span><span class="sxs-lookup"><span data-stu-id="8ac46-167">Close the **drawer** to return **Network** tool</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="8ac46-168">网络工具</span><span class="sxs-lookup"><span data-stu-id="8ac46-168">Network tool</span></span>  

<span data-ttu-id="8ac46-169">通过服务工作人员调试运行的网络请求。</span><span class="sxs-lookup"><span data-stu-id="8ac46-169">Debug network requests that run through service workers.</span></span>  <span data-ttu-id="8ac46-170">您也可以从 " **应用程序** " 工具打开网络请求。</span><span class="sxs-lookup"><span data-stu-id="8ac46-170">You may also open network requests from the **Application** tool.</span></span>  <span data-ttu-id="8ac46-171">对于每个请求，DevTools 在 [计时][DevtoolsNetworkReferenceViewTimingBreakdownRequest] 窗格中显示以下信息。</span><span class="sxs-lookup"><span data-stu-id="8ac46-171">For each request, DevTools display the following information in the [Timing][DevtoolsNetworkReferenceViewTimingBreakdownRequest] pane.</span></span>  

*   <span data-ttu-id="8ac46-172">请求的开始时间和引导的持续时间。</span><span class="sxs-lookup"><span data-stu-id="8ac46-172">The start of a request and duration of the bootstrap.</span></span>  
*   <span data-ttu-id="8ac46-173">对服务工作人员注册的更改。</span><span class="sxs-lookup"><span data-stu-id="8ac46-173">Changes to service worker registration.</span></span>  
*   <span data-ttu-id="8ac46-174">`fetch`事件处理程序的运行时。</span><span class="sxs-lookup"><span data-stu-id="8ac46-174">The runtime of a `fetch` event handler.</span></span>  
*   <span data-ttu-id="8ac46-175">`fetch`用于加载客户端的所有事件的运行时。</span><span class="sxs-lookup"><span data-stu-id="8ac46-175">The runtime of all `fetch` events for loading a client.</span></span>  
    
:::image type="complex" source="../../media/2020/11/network-timing-service-worker.msft.png" alt-text="计时窗格" lightbox="../../media/2020/11/network-timing-service-worker.msft.png":::
   <span data-ttu-id="8ac46-177">**计时** 窗格</span><span class="sxs-lookup"><span data-stu-id="8ac46-177">**Timing** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="8ac46-178">源工具</span><span class="sxs-lookup"><span data-stu-id="8ac46-178">Sources tool</span></span>  

<span data-ttu-id="8ac46-179">在早期版本的 Microsoft Edge 中，调用堆栈中的深度级别限制为服务工作人员中的 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="8ac46-179">In previous versions of Microsoft Edge, the level of depth in the call stack was limited to the JavaScript code in your service worker.</span></span>  <span data-ttu-id="8ac46-180">在 Microsoft Edge 88 中，调用堆栈现在显示通过您的服务工作者运行的请求的发起者。</span><span class="sxs-lookup"><span data-stu-id="8ac46-180">In Microsoft Edge 88, the call stack now displays the initiator of requests that run through your service worker.</span></span>  

<span data-ttu-id="8ac46-181">若要找到请求的发起程序，请使用服务工作人员中的 JavaScript 代码的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="8ac46-181">To locate the initiator of the request, use the call stack of your JavaScript code in the service worker.</span></span>  <span data-ttu-id="8ac46-182">下图中的调用堆栈从你的服务工作人员的 JavaScript 代码开始，并将对原始网页请求的引用显示为 `(index):157` 。</span><span class="sxs-lookup"><span data-stu-id="8ac46-182">The call stack in the following figures starts with the JavaScript code in your service worker and displays a reference to the original webpage request as `(index):157`.</span></span>  <span data-ttu-id="8ac46-183">在第二个图中，将选择该引用并打开发出请求的发起程序。</span><span class="sxs-lookup"><span data-stu-id="8ac46-183">In the second figure, the reference is chosen and opened the initiator that made the request.</span></span>  <span data-ttu-id="8ac46-184">第二个图中的发起方是网页。</span><span class="sxs-lookup"><span data-stu-id="8ac46-184">The initiator in the second figure is the webpage.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png" alt-text="service-worker.js 文件和调用堆栈突出显示请求原始发件人" lightbox="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png":::
         <span data-ttu-id="8ac46-186">`service-worker.js`文件和调用堆栈的突出显示请求原始发件人</span><span class="sxs-lookup"><span data-stu-id="8ac46-186">The `service-worker.js` file and call stack highlighting request originator</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-call-stack-target.msft.png" alt-text=" (索引) 网页是请求发起方" lightbox="../../media/2020/11/service-worker-sources-call-stack-target.msft.png":::
         <span data-ttu-id="8ac46-188">该 `(index)` 网页是请求发起方</span><span class="sxs-lookup"><span data-stu-id="8ac46-188">The `(index)` webpage is the request initiator</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="8ac46-189">复制网络请求的属性值</span><span class="sxs-lookup"><span data-stu-id="8ac46-189">Copy property value of a network request</span></span>  

<!-- Title: Copy response JSON in Network tool using the contextual menu  -->  
<!-- Subtitle:  The Network tool now has a more consistent UX.  Easily copy the JSON response using the contextual menu.  -->  

<span data-ttu-id="8ac46-190">在 " **网络** " 工具中，使用新的 " **复制值** " 选项复制网络请求的属性值。</span><span class="sxs-lookup"><span data-stu-id="8ac46-190">In the **Network** tool, copy the property value of a network request using the new **Copy value** option.</span></span>  <span data-ttu-id="8ac46-191">将该属性值复制为解码后的 JSON 值。</span><span class="sxs-lookup"><span data-stu-id="8ac46-191">The property value is copied as a decoded JSON value.</span></span>  <span data-ttu-id="8ac46-192">在早期版本的 Microsoft Edge 中，你必须使用下列操作之一复制值。</span><span class="sxs-lookup"><span data-stu-id="8ac46-192">In previous versions of Microsoft Edge, you had to copy a value using one of the following actions.</span></span>  

*   <span data-ttu-id="8ac46-193">突出显示整个文本并进行复制。</span><span class="sxs-lookup"><span data-stu-id="8ac46-193">Highlight the entire text and copy it.</span></span>  
*   <span data-ttu-id="8ac46-194">将值存储为全局变量（如果适用），并从 DevTools [控制台][DevtoolsConsoleIndex]复制它。</span><span class="sxs-lookup"><span data-stu-id="8ac46-194">Store the value as global variable, as applicable, and copy it from the DevTools [Console][DevtoolsConsoleIndex].</span></span>  
    
<span data-ttu-id="8ac46-195">若要将属性值复制到剪贴板，请导航到 [剪贴板上的 "将已设置格式的响应 JSON 复制到剪贴板"][DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]。</span><span class="sxs-lookup"><span data-stu-id="8ac46-195">To copy the property value to your clipboard, navigate to [Copy formatted response JSON to the clipboard][DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard].</span></span>  <span data-ttu-id="8ac46-196">若要在 Chromium open 源代码项目中查看此功能的历史记录，请导航到 "问题 [1132084][CR1132084]"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-196">To review the history of this feature in the Chromium open-source project, navigate to Issue [1132084][CR1132084].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/copy-property-value.msft.png" alt-text="在 DevTools 中复制属性值" lightbox="../../media/2020/11/copy-property-value.msft.png":::
         <span data-ttu-id="8ac46-198">在 DevTools 中复制属性值</span><span class="sxs-lookup"><span data-stu-id="8ac46-198">Copy property value in DevTools</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/paste-property-value.msft.png" alt-text="在 Visual Studio 代码中粘贴属性值" lightbox="../../media/2020/11/paste-property-value.msft.png":::
         <span data-ttu-id="8ac46-200">在 Visual Studio 代码中粘贴属性值</span><span class="sxs-lookup"><span data-stu-id="8ac46-200">Paste property value in Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="8ac46-201">自定义多路键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="8ac46-201">Customize multi-press keyboard shortcuts</span></span>  

<!-- Title: Customize multi-press keyboard shortcuts  -->  
<!-- Subtitle: Create custom multi-press keyboard shortcuts in the shortcut editor.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::

<span data-ttu-id="8ac46-202">[由于 Microsoft Edge 版本 87][WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]，你可以为 DevTools 中的任何操作自定义键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="8ac46-202">[Since Microsoft Edge version 87][WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings], you may customize keyboard shortcuts for any action in DevTools.</span></span>  <span data-ttu-id="8ac46-203">在 Microsoft Edge 版本88中，你现在可以创建多个键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="8ac46-203">In Microsoft Edge version 88, you may now create multi-press keyboard shortcuts.</span></span>  <span data-ttu-id="8ac46-204">若要在 DevTools 中设置操作的快捷方式，请导航到 "[设置][DevtoolsCustomizeIndexSettings]  >  **试验**"，然后选中 "**启用键盘快捷方式编辑器**" 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="8ac46-204">To set a shortcut for an action in the DevTools, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**  and choose the checkbox next to **Enable keyboard shortcut editor**.</span></span>  <span data-ttu-id="8ac46-205">有关自定义和编辑快捷方式的详细信息，请导航以 [启用键盘快捷方式编辑器实验功能][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。</span><span class="sxs-lookup"><span data-stu-id="8ac46-205">For more information about customizing and editing shortcuts, navigate to [Enable keyboard shortcut editor Experimental feature][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  

<span data-ttu-id="8ac46-206">例如，红色突出显示将显示为 " **开始录制事件** " 操作自定义的多点键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="8ac46-206">For example, the red highlight displays a multi-press keyboard shortcut customized for the **Start recording events** action.</span></span>  <span data-ttu-id="8ac46-207">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 " [问题 #174309][CR174309]"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-207">To review real-time updates on this feature in the Chromium open-source project, navigate to [Issue #174309][CR174309].</span></span>  

:::image type="complex" source="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png" alt-text="Chords 键盘快捷方式" lightbox="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png":::
   <span data-ttu-id="8ac46-209">多按键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="8ac46-209">Multi-press keyboard shortcuts</span></span>  
:::image-end:::  

## <span data-ttu-id="8ac46-210">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="8ac46-210">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <span data-ttu-id="8ac46-211">新的 CSS 角度可视化工具</span><span class="sxs-lookup"><span data-stu-id="8ac46-211">New CSS angle visualization tools</span></span>  

<span data-ttu-id="8ac46-212">DevTools 现在对 CSS 角度调试有更好的支持。</span><span class="sxs-lookup"><span data-stu-id="8ac46-212">DevTools now have better support for CSS angle debugging.</span></span>  <span data-ttu-id="8ac46-213">当页面上的 HTML 元素应用了 CSS 角度时，" **样式** " 工具中的角度旁边将显示一个时钟图标。</span><span class="sxs-lookup"><span data-stu-id="8ac46-213">When an HTML element on your page has CSS angle applied to it, a clock icon is displayed next to the angle in the **Styles** tool.</span></span>  <span data-ttu-id="8ac46-214">若要切换时钟覆盖，请选择时钟图标。</span><span class="sxs-lookup"><span data-stu-id="8ac46-214">To toggle the clock overlay, choose the clock icon.</span></span>  <span data-ttu-id="8ac46-215">若要更改角度，请选择时钟中的任意位置或拖动 "针"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-215">To change the angle, choose anywhere in the clock or drag the needle.</span></span>  <span data-ttu-id="8ac46-216">若要更改 angle 值，您还可以使用鼠标和键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="8ac46-216">To change the angle value, you may also use mouse and keyboard shortcuts.</span></span>  <!--  To learn more, navigate to [Angle Clock][DevtoolsCssReferenceChangeAngleValueWithAngleClock].  -->  <span data-ttu-id="8ac46-217">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [1126178][CR1126178] 和 [1138633][CR1138633]"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-217">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [1126178][CR1126178] and [1138633][CR1138633].</span></span>  

<!--todo:  add link when css angle clock section exists.  -->  

<span data-ttu-id="8ac46-218">此示例使用以下 CSS 角度。</span><span class="sxs-lookup"><span data-stu-id="8ac46-218">The following CSS angle is used for the example.</span></span>  

```css
background: linear-gradient(100deg, lightblue, pink);
```  

:::image type="complex" source="../../media/2020/11/css-angle.msft.png" alt-text="CSS 角度" lightbox="../../media/2020/11/css-angle.msft.png":::
   <span data-ttu-id="8ac46-220">CSS 角度</span><span class="sxs-lookup"><span data-stu-id="8ac46-220">CSS angle</span></span>  
:::image-end:::  

### <span data-ttu-id="8ac46-221">在 "存储" 窗格中模拟存储配额大小</span><span class="sxs-lookup"><span data-stu-id="8ac46-221">Simulate storage quota size in the Storage pane</span></span>  

<span data-ttu-id="8ac46-222">您现在可以在 " **存储** " 窗格中覆盖存储配额大小。</span><span class="sxs-lookup"><span data-stu-id="8ac46-222">You may now override storage quota size in the **Storage** pane.</span></span>  <span data-ttu-id="8ac46-223">此功能允许你模拟不同的设备，并在较少的磁盘可用性方案中测试你的网站或应用的行为。</span><span class="sxs-lookup"><span data-stu-id="8ac46-223">This feature allows you to simulate different devices and test the behavior of your website or app in low disk availability scenarios.</span></span>  <span data-ttu-id="8ac46-224">若要模拟存储配额，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8ac46-224">To simulate the storage quota, complete the following actions.</span></span>  

1.  <span data-ttu-id="8ac46-225">导航到 "**应用程序**  >  **存储**"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-225">Navigate to **Application** > **Storage**.</span></span>  
1.  <span data-ttu-id="8ac46-226">打开 " **模拟自定义存储配额** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="8ac46-226">Turn on the **Simulate custom storage quota** checkbox.</span></span>  
1.  <span data-ttu-id="8ac46-227">输入一个有效号码。</span><span class="sxs-lookup"><span data-stu-id="8ac46-227">Enter a valid number.</span></span>  
    
<span data-ttu-id="8ac46-228">有关如何在 DevTools 中模拟移动设备和其他功能的详细信息，请导航以 [模拟 Microsoft Edge DevTools 中的移动设备 ][DevtoolsDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="8ac46-228">For more information about how to emulate mobile devices and other features in the DevTools, navigate to [Emulate mobile devices in Microsoft Edge DevTools ][DevtoolsDeviceModeIndex].</span></span>  <span data-ttu-id="8ac46-229">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [945786][CR945786] 和 [1146985][CR1146985]"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-229">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [945786][CR945786] and [1146985][CR1146985].</span></span>  

:::image type="complex" source="../../media/2020/11/storage-quota.msft.png" alt-text="模拟存储配额大小" lightbox="../../media/2020/11/storage-quota.msft.png":::
   <span data-ttu-id="8ac46-231">模拟存储配额大小</span><span class="sxs-lookup"><span data-stu-id="8ac46-231">Simulate storage quota size</span></span>  
:::image-end:::  

### <span data-ttu-id="8ac46-232">报告网络工具中的 CORS 错误</span><span class="sxs-lookup"><span data-stu-id="8ac46-232">Report CORS errors in the Network tool</span></span>  

<span data-ttu-id="8ac46-233">通过导航到 [CORS 错误演示][GlitchCorsErrors]来试用此功能。</span><span class="sxs-lookup"><span data-stu-id="8ac46-233">Try out this feature by navigating to [CORS error demo][GlitchCorsErrors].</span></span>  <span data-ttu-id="8ac46-234">打开 " **网络** " 工具，刷新页面，并观察失败的 CORS 网络请求。</span><span class="sxs-lookup"><span data-stu-id="8ac46-234">Open the **Network** tool, refresh the page, and observe the failed CORS network request.</span></span>  <span data-ttu-id="8ac46-235">"状态" 列显示 **CORS 错误**。</span><span class="sxs-lookup"><span data-stu-id="8ac46-235">The status column displays the **CORS error**.</span></span>  <span data-ttu-id="8ac46-236">当您悬停在错误上时，工具提示现在显示错误代码。</span><span class="sxs-lookup"><span data-stu-id="8ac46-236">When you hover on the error, the tooltip now displays the error code.</span></span>  <span data-ttu-id="8ac46-237">在 Microsoft Edge 版本87及更早版本中，DevTools 仅显示的通用 \*\* (失败) \*\* CORS 错误的状态。</span><span class="sxs-lookup"><span data-stu-id="8ac46-237">In Microsoft Edge version 87 and earlier, DevTools only displayed generic **(failed)** status for CORS errors.</span></span>  <span data-ttu-id="8ac46-238">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [1141824][CR1141824]"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-238">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1141824][CR1141824].</span></span>  

:::image type="complex" source="../../media/2020/11/cors-err.msft.png" alt-text="CORS 错误" lightbox="../../media/2020/11/cors-err.msft.png":::
   <span data-ttu-id="8ac46-240">CORS 错误</span><span class="sxs-lookup"><span data-stu-id="8ac46-240">CORS errors</span></span>  
:::image-end:::  

### <span data-ttu-id="8ac46-241">框架详细信息视图更新</span><span class="sxs-lookup"><span data-stu-id="8ac46-241">Frame details view updates</span></span>  

#### <span data-ttu-id="8ac46-242">"框架详细信息" 视图中的跨源隔离信息</span><span class="sxs-lookup"><span data-stu-id="8ac46-242">Cross-origin isolation information in the Frame details view</span></span>  

<span data-ttu-id="8ac46-243">跨原始隔离状态现在显示在 " **安全 & 隔离** " 部分下方。</span><span class="sxs-lookup"><span data-stu-id="8ac46-243">The cross-origin isolated status is now displayed under the **Security & Isolation** section.</span></span>  <span data-ttu-id="8ac46-244">新的 **API 可用性** 部分显示 `SharedArrayBuffer` s (SAB \ ) 的可用性，以及是否可以使用共享缓冲区 `postMessage()` 。</span><span class="sxs-lookup"><span data-stu-id="8ac46-244">The new **API availability** section displays the availability of `SharedArrayBuffer`s \(SAB\) and whether the buffers may be shared using `postMessage()`.</span></span>  <span data-ttu-id="8ac46-245">如果 SAB 和 `postMessage()` 当前可用，但上下文不是跨原点隔离的，则会显示一个弃用警告。</span><span class="sxs-lookup"><span data-stu-id="8ac46-245">A deprecation warning displays if the SAB and `postMessage()` is currently available, but the context is not cross-origin isolated.</span></span>  <span data-ttu-id="8ac46-246">有关跨源隔离以及其功能（如有必要）的详细信息 `SharedArrayBuffers` ，请导航到 [WindowOrWorkerGlobalScope crossOriginIsolated][MdnWindoworworkerglobalscopeCrossoriginisolated]。</span><span class="sxs-lookup"><span data-stu-id="8ac46-246">For more information about cross-origin isolation and why it is required for features like `SharedArrayBuffers`, navigate to [WindowOrWorkerGlobalScope.crossOriginIsolated][MdnWindoworworkerglobalscopeCrossoriginisolated].</span></span>  <span data-ttu-id="8ac46-247">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [1139899][CR1139899]"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-247">To review real-time updates of this feature in the Chromium open-source project, navigate to Issue [1139899][CR1139899].</span></span>  

:::image type="complex" source="../../media/2020/11/frame-cross-origin-isolated-api.msft.png" alt-text="跨源信息" lightbox="../../media/2020/11/frame-cross-origin-isolated-api.msft.png":::
   <span data-ttu-id="8ac46-249">跨源信息</span><span class="sxs-lookup"><span data-stu-id="8ac46-249">Cross-origin information</span></span>  
:::image-end:::  

#### <span data-ttu-id="8ac46-250">"帧详细信息" 视图中的新 Web 工作人员信息</span><span class="sxs-lookup"><span data-stu-id="8ac46-250">New Web Workers information in the Frame details view</span></span>  

<span data-ttu-id="8ac46-251">DevTools 现在将 web 工作者组织在相关的父框架下。</span><span class="sxs-lookup"><span data-stu-id="8ac46-251">DevTools now organizes web workers under the relevant parent frame.</span></span>  <span data-ttu-id="8ac46-252">例如，如果创建了 `someName` 框架 `worker.js` ，则 `worker.js` 会显示在 `someName` " **框架** " 列表中的 "下"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-252">For example, if the `someName` frame creates `worker.js`, then `worker.js` appears under `someName` in the **Frames** list.</span></span>  <span data-ttu-id="8ac46-253">若要查看 web 工作人员的详细信息，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8ac46-253">To view the details of the web worker, complete the following actions.</span></span>  

1.  <span data-ttu-id="8ac46-254">打开 **应用程序** 工具。</span><span class="sxs-lookup"><span data-stu-id="8ac46-254">Open **Application** tool.</span></span>  
1.  <span data-ttu-id="8ac46-255">展开包含 web 工作人员的帧。</span><span class="sxs-lookup"><span data-stu-id="8ac46-255">Expand a frame that contains web workers.</span></span>  
1.  <span data-ttu-id="8ac46-256">展开 " **辅助进程** " 树。</span><span class="sxs-lookup"><span data-stu-id="8ac46-256">Expand the **Workers** tree.</span></span>  
1.  <span data-ttu-id="8ac46-257">选择一个工作人员。</span><span class="sxs-lookup"><span data-stu-id="8ac46-257">Choose a worker.</span></span>  
    
<span data-ttu-id="8ac46-258">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [1122507][CR1122507] 和 [1051466][CR1051466]"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-258">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [1122507][CR1122507] and [1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/11/application-frames-service-workers.msft.png" alt-text="Web 工作人员信息" lightbox="../../media/2020/11/application-frames-service-workers.msft.png":::
   <span data-ttu-id="8ac46-260">Web 工作人员信息</span><span class="sxs-lookup"><span data-stu-id="8ac46-260">Web workers information</span></span>  
:::image-end:::  

#### <span data-ttu-id="8ac46-261">显示打开的窗口的 opener 帧详细信息</span><span class="sxs-lookup"><span data-stu-id="8ac46-261">Display opener frame details for opened windows</span></span>  

<span data-ttu-id="8ac46-262">DevTools 现在将在相关父[框架][MdnWindowFrames]下组织打开的[窗口][MdnWindowConstructors]。</span><span class="sxs-lookup"><span data-stu-id="8ac46-262">DevTools now organizes opened [Windows][MdnWindowConstructors] under the relevant parent [frame][MdnWindowFrames].</span></span>  <span data-ttu-id="8ac46-263">例如，如果 `top` 框架打开 `Window` 到 `https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium` ，则显示在 " `Window` `top` **帧** " 列表中的 "下"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-263">For example, if the `top` frame opens a `Window` to `https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium`, then the `Window` appears under `top` in the **Frames** list.</span></span>  

<span data-ttu-id="8ac46-264">若要显示负责在 " **元素** " 工具中打开另一个窗口的帧，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8ac46-264">To reveal the frame responsible for opening another Window in the **Elements** tool, complete the following actions.</span></span>  

1.  <span data-ttu-id="8ac46-265">打开 " **框架** 树"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-265">Open the **Frames** tree.</span></span>  
1.  <span data-ttu-id="8ac46-266">展开 **打开的窗口** ，然后选择 `Window` 要了解的父框架。</span><span class="sxs-lookup"><span data-stu-id="8ac46-266">Expand **Opened Windows** and choose the `Window` for the parent frame you want to know.</span></span>  
1.  <span data-ttu-id="8ac46-267">选择 " **Opener Frame** " 链接。</span><span class="sxs-lookup"><span data-stu-id="8ac46-267">Choose the **Opener Frame** link.</span></span>  

<span data-ttu-id="8ac46-268">显示有关导致打开另一个帧的帧的详细信息 `Window` 。</span><span class="sxs-lookup"><span data-stu-id="8ac46-268">The details are displayed about which frame caused the opening of another `Window`.</span></span>  <span data-ttu-id="8ac46-269">若要在 " **元素** " 工具中显示 opener，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8ac46-269">To reveal the opener in the **Elements** tool, complete the following actions.</span></span>  

1.  <span data-ttu-id="8ac46-270">打开 " **框架** 树"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-270">Open the **Frames** tree.</span></span>  
1.  <span data-ttu-id="8ac46-271">选择打开的窗口以打开 `Window` 详细信息。</span><span class="sxs-lookup"><span data-stu-id="8ac46-271">Choose an opened window to open the `Window` details.</span></span>  
1.  <span data-ttu-id="8ac46-272">选择 " **Opener Frame** " 链接。</span><span class="sxs-lookup"><span data-stu-id="8ac46-272">Choose the **Opener Frame** link.</span></span>  
    
<span data-ttu-id="8ac46-273">若要在 Chromium open 源代码项目中查看此功能的历史记录，请导航到 "问题 [1107766][CR1107766]"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-273">To review the history of this feature in the Chromium open-source project, navigate to Issue [1107766][CR1107766].</span></span>  

:::image type="complex" source="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png" alt-text="打开的帧详细信息" lightbox="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png":::
   <span data-ttu-id="8ac46-275">打开的帧详细信息</span><span class="sxs-lookup"><span data-stu-id="8ac46-275">Opened frame details</span></span>  
:::image-end:::  

### <span data-ttu-id="8ac46-276">为网络启动器复制 stacktrace</span><span class="sxs-lookup"><span data-stu-id="8ac46-276">Copy stacktrace for network initiator</span></span>  

<span data-ttu-id="8ac46-277">若要将 stacktrace 复制到剪贴板，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8ac46-277">To copy the stacktrace to your clipboard, complete the following actions.</span></span>  

1.  <span data-ttu-id="8ac46-278">打开上下文菜单 \ (右键单击 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="8ac46-278">Open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="8ac46-279">选择 "**复制**  >  **副本 stacktrace**"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-279">Choose **Copy** > **Copy stacktrace**.</span></span>  
    
<span data-ttu-id="8ac46-280">若要在 Chromium open 源代码项目中查看此功能的历史记录，请导航到 "问题 [1139615][CR1139615]"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-280">To review the history of this feature in the Chromium open-source project, navigate to Issue [1139615][CR1139615].</span></span>

:::image type="complex" source="../../media/2020/11/copy-stacktrace.msft.png" alt-text="复制 stacktrace" lightbox="../../media/2020/11/copy-stacktrace.msft.png":::
   <span data-ttu-id="8ac46-282">复制 stacktrace</span><span class="sxs-lookup"><span data-stu-id="8ac46-282">Copy stacktrace</span></span>  
:::image-end:::  

### <span data-ttu-id="8ac46-283">在悬停时预览 Wasm 变量值</span><span class="sxs-lookup"><span data-stu-id="8ac46-283">Preview Wasm variable value on mouseover</span></span>  

<span data-ttu-id="8ac46-284">使用此功能可在代码暂停时查看 WebAssembly \ (Wasm \ ) 变量的值。</span><span class="sxs-lookup"><span data-stu-id="8ac46-284">Use this feature to review the value of a WebAssembly \(Wasm\) variable when your code is paused.</span></span>  <span data-ttu-id="8ac46-285">若要显示变量的当前值，请将鼠标悬停在变量上。</span><span class="sxs-lookup"><span data-stu-id="8ac46-285">To display the current value of a variable, hover on a variable.</span></span>  <span data-ttu-id="8ac46-286">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [1058836][CR1058836] 和 [1071432][CR1071432]"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-286">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [1058836][CR1058836] and [1071432][CR1071432].</span></span>  

:::image type="complex" source="../../media/2020/11/wasm-mouseover.msft.png" alt-text="在悬停时预览 Wasm 变量" lightbox="../../media/2020/11/wasm-mouseover.msft.png":::
   <span data-ttu-id="8ac46-288">在悬停时预览 Wasm 变量</span><span class="sxs-lookup"><span data-stu-id="8ac46-288">Preview Wasm variable on mouseover</span></span>  
:::image-end:::  

### <span data-ttu-id="8ac46-289">文件和内存大小的一致度量单位</span><span class="sxs-lookup"><span data-stu-id="8ac46-289">Consistent units of measurement for sizes of files and memory</span></span>  

<span data-ttu-id="8ac46-290">DevTools 现在一直用于 `kB` 显示文件和内存的大小。</span><span class="sxs-lookup"><span data-stu-id="8ac46-290">DevTools now consistently use `kB` for displaying sizes of files and memory.</span></span>  <span data-ttu-id="8ac46-291">以前 DevTools 混合 `kB` 和 `KiB` 。</span><span class="sxs-lookup"><span data-stu-id="8ac46-291">Previously DevTools mixed `kB` and `KiB`.</span></span>

*   `kB` <span data-ttu-id="8ac46-292">或 kb \ (10 ^ 3 或1000字节 \ ) </span><span class="sxs-lookup"><span data-stu-id="8ac46-292">or kilobyte \(10^3 or 1000 bytes\)</span></span>  
*   `KiB` <span data-ttu-id="8ac46-293">或 kibibyte \ (2 ^ 10 或1024字节 \ ) </span><span class="sxs-lookup"><span data-stu-id="8ac46-293">or kibibyte \(2^10 or 1024 bytes\)</span></span>  
    
<span data-ttu-id="8ac46-294">例如，以前在标签中使用的 **网络** 工具 `kB` ，但 `KiB` 在计算中使用。</span><span class="sxs-lookup"><span data-stu-id="8ac46-294">For example, the **Network** tool previously used `kB` in the labels, but used `KiB` in calculations.</span></span>  <span data-ttu-id="8ac46-295">您的反馈表明这种不一致会造成混淆。</span><span class="sxs-lookup"><span data-stu-id="8ac46-295">Your feedback showed that this inconsistency caused confusion.</span></span>  <span data-ttu-id="8ac46-296">若要在 Chromium open 源代码项目中查看此功能的历史记录，请导航到 "问题 [1035309][CR1035309]"。</span><span class="sxs-lookup"><span data-stu-id="8ac46-296">To review the history of this feature in the Chromium open-source project, navigate to Issue [1035309][CR1035309].</span></span>  

## <span data-ttu-id="8ac46-297">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="8ac46-297">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="8ac46-298">如果你在 Windows、Linux 或 macOS 上，请考虑使用 [Microsoft Edge 预览频道] [MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="8ac46-298">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="8ac46-299">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="8ac46-299">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="8ac46-300">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="8ac46-300">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[Devtools3dViewIndex]: /microsoft-edge/devtools-guide-chromium/3d-view/index "3D 视图 |Microsoft 文档"  
[DevtoolsConsoleIndex]: /microsoft-edge/devtools-guide-chromium/console/index "控制台概述 |Microsoft 文档"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "启用键盘快捷方式编辑器-实验功能 |microsoft 文档"  
[DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-composited-layers-in-3d-view "在3D 视图中打开合成图-实验功能 |Microsoft 文档"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "查找并修复 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"  
[DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]: /microsoft-edge/devtools-guide-chromium/network/reference#copy-formatted-response-json-to-the-clipboard "将带格式的响应 JSON 复制到剪贴板-网络分析参考 |Microsoft 文档"  
[DevtoolsNetworkReferenceViewTimingBreakdownRequest]: /microsoft-edge/devtools-guide-chromium/network/reference#view-the-timing-breakdown-of-a-request "查看请求的计时细目-网络分析参考 |Microsoft 文档"  
[WebDriverChromiumMain]: /microsoft-edge/webdriver-chromium "使用 WebDriver (Chromium) 进行测试自动化 |Microsoft 文档"  

<!--  [DevtoolsCssReferenceChangeAngleValueWithAngleClock]: /microsoft-edge/devtools-guide-chromium/css/reference#change-angle-value-with-the-angle-clock "Change angle value with the Angle Clock - CSS reference | Microsoft Docs"  -->  

[ProgressiveWebAppsChromiumIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上的渐进式 Web 应用 |Microsoft 文档"  

[WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/10/devtools#customize-keyboard-shortcuts-in-settings "在 "设置" 中自定义键盘快捷方式-DevTools 中的新增功能 (Microsoft Edge 87) |Microsoft 文档"  
[WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/06/devtools#webhint-feedback-in-the-issues-panel ""问题" 面板中的 webhint 反馈-DevTools (Microsoft Edge 85) 中的新增功能 |Microsoft 文档"  

[MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "下载 WebDriver |Microsoft 开发人员"  

[MicrosoftinsiderDownloadPlatformLinux]: https://www.microsoftedgeinsider.com/download?platform=linux "下载 Microsoft Edge 预览体验成员频道"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio 代码"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  

[CR174309]: https://crbug.com/174309 "问题174309： DevTools：允许自定义键盘快捷方式/键绑定 |Chromium bug"  
[CR945786]: https://crbug.com/945786 "问题945786： DevTools：允许替代导航器。估计 ( # A1 |Chromium bug"  
[CR1029427]: https://crbug.com/1029427 "问题1029427：减少了在前端的协议消息调度的性能开销Chromium bug"  
[CR1035309]: https://crbug.com/1035309 "问题1035309： DevTools 应始终使用 MB 来表示兆字节，而不是 mebibyte |Chromium bug"  
[CR1051466]: https://crbug.com/1051466 "问题1051466：在 DevTools | 中的支持合作基金/COEP 调试Chromium bug"  
[CR1058836]: https://crbug.com/1058836 "问题1058836： Wasm 调试方面的 UX 问题 |Chromium bug"  
[CR1071432]: https://crbug.com/1071432 "问题1071432：☂️ Wasm Basic 开发人员体验 |Chromium bug"  
[CR1107766]: https://crbug.com/1107766 "问题1107766：显示 "窗口" 生成的帧的相关信息。在框架树中打开 ( # A1 "|Chromium bug"  
[CR1122507]: https://crbug.com/1122507 "问题1122507：框架树视图中的 Surface worker 信息 |Chromium bug"  
[CR1126178]: https://crbug.com/1126178 "问题1126178：☂ DevTools： CSS <键入> 组件 |Chromium bug"  
[CR1130556]: https://crbug.com/1130556 "问题1130556： DevTools：测试图像回退 (仿真) |Chromium bug"  
[CR1132084]: https://crbug.com/1132084 "问题1132084：无法轻松复制 JSON 请求负载 |Chromium bug"  
[CR1136394]: https://crbug.com/1136394 "问题1136394： Flexbox 工具 |Chromium bug"  
[CR1138633]: https://crbug.com/1138633 "问题1138633： DevTools： CSS <角度> 组件应反映它在时钟背景中的驻留属性外观 |Chromium bug"  
[CR1139615]: https://crbug.com/1139615 "问题1139615：网络启动器可提供复制堆栈跟踪的功能 |Chromium bug"  
[CR1139899]: https://crbug.com/1139899 "问题1139899：在 "帧详细信息" 视图中报告封闭 API 可用性 |Chromium bug"  
[CR1139945]: https://crbug.com/1139945 "问题1139945： "样式" 面板中 flexbox CSS 属性的图标 |Chromium bug"  
[CR1141824]: https://crbug.com/1141824 "问题1141824：在 DevTools | 中改进 CORS 错误报告Chromium bug"  
[CR1144090]: https://crbug.com/1144090 "问题1144090：将弹性样式装饰器添加到元素树 |Chromium bug"  
[CR1146985]: https://crbug.com/1146985 "问题1146985：已清除的文本在 "开发工具" 窗口的 "存储" 部分的文本框中仍然可见 |Chromium bug"  

[GlitchCorsErrors]: https://cors-errors.glitch.me "CORS 错误 |故障"  

[MdnCors]: https://developer.mozilla.org/docs/Web/HTTP/CORS "跨源资源共享 (CORS) |MDN"  
[MdnUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "使用 CSS 自定义属性 (变量) |MDN"  
[MdnWindowConstructors]: https://developer.mozilla.org/docs/Web/API/Window#Constructors "构造函数-窗口 |MDN"  
[MdnWindowFrames]: https://developer.mozilla.org/docs/Web/API/Window/frames "窗口。框架 |MDN"  
[MdnWindoworworkerglobalscopeCrossoriginisolated]: https://developer.mozilla.org/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated "WindowOrWorkerGlobalScope crossOriginIsolated |MDN"  

[WebhintMain]: https://webhint.io "webhint"  
[WebhintUserGuideHintsAccessibility]: https://webhint.io/docs/user-guide/hints/accessibility "辅助功能 |webhint"  
[WebhintUserGuideHintsCompatibility]: https://webhint.io/docs/user-guide/hints/compatibility "兼容性 |webhint"  
[WebhintUserGuideHintsPerformance]: https://webhint.io/docs/user-guide/hints/performance "性能 |webhint"  
[WebhintUserGuideHintsPitfalls]: https://webhint.io/docs/user-guide/hints/pitfalls "缺陷 |webhint"  
[WebhintUserGuideHintsPwa]: https://webhint.io/docs/user-guide/hints/pwa "PWA |webhint"  
[WebhintUserGuideHintsSecurity]: https://webhint.io/docs/user-guide/hints/security "安全性 |webhint"  

> [!NOTE]
> <span data-ttu-id="8ac46-351">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="8ac46-351">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8ac46-352">原始页面可在 [此处](https://developers.google.com/web/updates/2020/11/devtools/index) 找到，并由 [Jecelyn Yeen][JecelynYeen] (开发人员和 DevTools，Chrome \ ) 。</span><span class="sxs-lookup"><span data-stu-id="8ac46-352">The original page is found [here](https://developers.google.com/web/updates/2020/11/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="8ac46-354">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="8ac46-354">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
