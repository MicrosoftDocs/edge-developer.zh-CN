---
description: Linux 上的 Microsoft Edge、”问题“工具中改进的 Webhint 提示、新的服务工作线程调试功能等。
title: DevTools 中的新增功能 (Microsoft Edge 88)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 6a36029aa97604b6aea20f232d329ce3805a3144
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408365"
---
<!-- Copyright Jecelyn Yeen 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-88"></a><span data-ttu-id="0730c-104">DevTools 中的新增功能 (Microsoft Edge 88)</span><span class="sxs-lookup"><span data-stu-id="0730c-104">What's New in DevTools (Microsoft Edge 88)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="microsoft-edge-and-microsoft-edge-driver-now-available-on-linux"></a><span data-ttu-id="0730c-105">Microsoft Edge 和 Microsoft Edge 驱动程序现在可在 Linux 上使用</span><span class="sxs-lookup"><span data-stu-id="0730c-105">Microsoft Edge and Microsoft Edge Driver now available on Linux</span></span>  

<!-- Title: Microsoft Edge and Microsoft Edge Driver on Linux  -->  
<!-- Subtitle: Get Microsoft Edge Dev on Ubuntu, Debian, Fedora, and openSUSE distributions and start automating in CI/CD environments with Microsoft Edge Driver. -->  

<span data-ttu-id="0730c-106">Microsoft Edge Dev 现已在 Ubuntu、Debian、Fedora 和 openSUSE 发行版上受到支持。</span><span class="sxs-lookup"><span data-stu-id="0730c-106">Microsoft Edge Dev is now supported on Ubuntu, Debian, Fedora, and openSUSE distributions.</span></span>  <span data-ttu-id="0730c-107">直接从 [Microsoft Edge 预览体验成员网站][MicrosoftinsiderDownloadPlatformLinux] 下载并安装 Microsoft Edge Dev `.deb` 或 `.rpm` 程序包，或使用 Linux 发行版的标准程序包管理工具。</span><span class="sxs-lookup"><span data-stu-id="0730c-107">Download and install the Microsoft Edge Dev `.deb` or `.rpm` package directly from the [Microsoft Edge Insider site][MicrosoftinsiderDownloadPlatformLinux] or use the standard package management tools of your Linux distribution.</span></span>  

<span data-ttu-id="0730c-108">如果你在连续集成和交付\(CI/CD\) 解决方案中使用 Linux 环境，Microsoft Edge 驱动程序也可在 Linux 上使用。</span><span class="sxs-lookup"><span data-stu-id="0730c-108">If you are using a Linux environment in your continuous integration and delivery \(CI/CD\) solutions, Microsoft Edge Driver is also available on Linux.</span></span>  <span data-ttu-id="0730c-109">若要开始使用 Microsoft Edge 驱动程序自动执行 Microsoft Edge Dev，请导航至 [Microsoft Edge 驱动程序下载页][MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]。</span><span class="sxs-lookup"><span data-stu-id="0730c-109">To get started automating Microsoft Edge Dev with Microsoft Edge Driver, navigate to [Microsoft Edge Driver Downloads page][MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads].</span></span>  <span data-ttu-id="0730c-110">有关自动执行 Microsoft Edge Dev 以及 Microsoft Edge 驱动程序的帮助，请导航到 [使用 WebDriver (Chromium) 测试自动化][WebDriverChromiumMain]。</span><span class="sxs-lookup"><span data-stu-id="0730c-110">For help with automating Microsoft Edge Dev along with Microsoft Edge Driver, navigate to [Use WebDriver (Chromium) for test automation][WebDriverChromiumMain].</span></span>  

:::image type="complex" source="../../media/2020/11/edge-on-linux.msft.png" alt-text="Microsoft Edge Linux 版中的 DevTools" lightbox="../../media/2020/11/edge-on-linux.msft.png":::
   <span data-ttu-id="0730c-112">Microsoft Edge Linux 版中的 DevTools</span><span class="sxs-lookup"><span data-stu-id="0730c-112">DevTools in Microsoft Edge on Linux</span></span>  
:::image-end:::  

## <a name="improved-webhint-and-platform-tips-in-the-issues-tool"></a><span data-ttu-id="0730c-113">“问题”工具中改进的 Web 提示和平台提示</span><span class="sxs-lookup"><span data-stu-id="0730c-113">Improved webhint and platform tips in the Issues tool</span></span>  

<!-- Title: Improvements to Issues tool and webhint integration  -->  
<!-- Subtitle: Categories and third-party filtering make it easier to survey issues in the Issues tool.  Issues surfaced by webhint now have improved code snippets and documentation links to help you fix problems in your website.  -->  

<span data-ttu-id="0730c-114">开源工具 [Webhint][WebhintMain] 为网站和本地网页提供实时反馈。</span><span class="sxs-lookup"><span data-stu-id="0730c-114">An open-source tool, [webhint][WebhintMain], provides real-time feedback for websites and local webpages.</span></span>  <span data-ttu-id="0730c-115">从 [Microsoft Edge 版本 85][WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel] 开始，在 [问题][DevtoolsIssuesIndex] 工具中审阅 Webhint 反馈。</span><span class="sxs-lookup"><span data-stu-id="0730c-115">Starting with [Microsoft Edge version 85][WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel], review webhint feedback in the [Issues][DevtoolsIssuesIndex] tool.</span></span>  <span data-ttu-id="0730c-116">现在，通过添加以下类别，可以更轻松地审阅 **问题** 工具中出现的问题。</span><span class="sxs-lookup"><span data-stu-id="0730c-116">Issues that appear in the **Issues** tool are now easier to review with the addition of the following categories.</span></span>  

*   [<span data-ttu-id="0730c-117">辅助功能</span><span class="sxs-lookup"><span data-stu-id="0730c-117">Accessibility</span></span>][WebhintUserGuideHintsAccessibility]  
*   [<span data-ttu-id="0730c-118">兼容性</span><span class="sxs-lookup"><span data-stu-id="0730c-118">Compatibility</span></span>][WebhintUserGuideHintsCompatibility]  
*   [<span data-ttu-id="0730c-119">性能</span><span class="sxs-lookup"><span data-stu-id="0730c-119">Performance</span></span>][WebhintUserGuideHintsPerformance]  
*   [<span data-ttu-id="0730c-120">隐患</span><span class="sxs-lookup"><span data-stu-id="0730c-120">Pitfalls</span></span>][WebhintUserGuideHintsPitfalls]  
*   [<span data-ttu-id="0730c-121">PWA</span><span class="sxs-lookup"><span data-stu-id="0730c-121">PWA</span></span>][WebhintUserGuideHintsPwa]  
*   [<span data-ttu-id="0730c-122">安全性</span><span class="sxs-lookup"><span data-stu-id="0730c-122">Security</span></span>][WebhintUserGuideHintsSecurity]  
    
<span data-ttu-id="0730c-123">你现在可以使用新复选框筛选出第三方问题。</span><span class="sxs-lookup"><span data-stu-id="0730c-123">You are now able to filter out third-party issues using a new checkbox.</span></span>  <span data-ttu-id="0730c-124">筛选器功能可帮助你隐藏第三方库或其他源中与代码相关的问题。</span><span class="sxs-lookup"><span data-stu-id="0730c-124">The filter functionality helps you hide issues related to code from third-party libraries or other sources.</span></span>  

<span data-ttu-id="0730c-125">为帮助审阅 [Webhint][WebhintMain] 显示的问题，**问题** 工具现在显示以下信息。</span><span class="sxs-lookup"><span data-stu-id="0730c-125">To help you review issues revealed by [webhint][WebhintMain], the **Issues** tool now displays the following information.</span></span>  

*   <span data-ttu-id="0730c-126">改进的代码段。</span><span class="sxs-lookup"><span data-stu-id="0730c-126">Improved code snippets.</span></span>  
*   <span data-ttu-id="0730c-127">指向其他相关面板的链接。</span><span class="sxs-lookup"><span data-stu-id="0730c-127">Links to other relevant panels.</span></span>  
*   <span data-ttu-id="0730c-128">指向文档的链接，可帮助你修复网站中的问题。</span><span class="sxs-lookup"><span data-stu-id="0730c-128">Links to documentation to help you fix problems in your website.</span></span>  
    
:::image type="complex" source="../../media/2020/11/issues-webhints.msft.png" alt-text="问题工具" lightbox="../../media/2020/11/issues-webhints.msft.png":::
   <span data-ttu-id="0730c-130">**问题** 工具</span><span class="sxs-lookup"><span data-stu-id="0730c-130">**Issues** tool</span></span>  
:::image-end:::  

## <a name="composited-layers-are-now-in-3d-view"></a><span data-ttu-id="0730c-131">复合层现在采用 3D 视图</span><span class="sxs-lookup"><span data-stu-id="0730c-131">Composited Layers are now in 3D View</span></span>  

<!-- Title: 3D View is now integrated with Composited Layers  -->  
<!-- Subtitle: Composited Layers are now in 3D View.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="0730c-132">现在，你可以可视化显示 **Layers** 内容与 z-index 值和文档对象模型\ (DOM\)。</span><span class="sxs-lookup"><span data-stu-id="0730c-132">You may now visualize **Layers** content alongside z-index values and the Document Object Model \(DOM\).</span></span>  <span data-ttu-id="0730c-133">此功能可帮助你进行调试，无需在 [3D 视图][Devtools3dViewIndex] 和 **图层工具** 之间切换。</span><span class="sxs-lookup"><span data-stu-id="0730c-133">This feature helps you debug without switching between the [3D view][Devtools3dViewIndex] and **Layers** tools as often.</span></span>  <span data-ttu-id="0730c-134">为获得全面的视觉调试体验， [已将3D 视图和复合层组合到一起][DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]。</span><span class="sxs-lookup"><span data-stu-id="0730c-134">For a comprehensive visual debugging experience, the [3D View and Composited Layers are now combined][DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView].</span></span>  

:::image type="complex" source="../../media/2020/11/experiments-layers.msft.png" alt-text="复合层窗格" lightbox="../../media/2020/11/experiments-layers.msft.png":::
   <span data-ttu-id="0730c-136">**复合层** 窗格</span><span class="sxs-lookup"><span data-stu-id="0730c-136">**Composited Layers** pane</span></span>  
:::image-end:::  

## <a name="css-variable-definitions-in-styles-pane"></a><span data-ttu-id="0730c-137">“样式”窗格中的 CSS 变量定义</span><span class="sxs-lookup"><span data-stu-id="0730c-137">CSS variable definitions in Styles pane</span></span>  

<!-- Title: Jump to CSS variable definitions  -->  
<!-- Subtitle: Choose any CSS variable to navigate directly to the definition in the Styles tool. -->  

<span data-ttu-id="0730c-138">在 **样式** 窗格中，[CSS变量][MdnUsingCssCustomProperties] 现在直接链接到每个定义。</span><span class="sxs-lookup"><span data-stu-id="0730c-138">In the **Styles** pane, [CSS variables][MdnUsingCssCustomProperties] now link directly to each definition.</span></span>  <span data-ttu-id="0730c-139">选择变量以轻松查看或更改 CSS 变量定义。</span><span class="sxs-lookup"><span data-stu-id="0730c-139">Choose the variable to easily view or change the CSS variable definition.</span></span>  <span data-ttu-id="0730c-140">在示例中，DevTools 显示 `body` 元素的 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="0730c-140">In the example, DevTools displays the CSS attributes for the `body` element.</span></span>  <span data-ttu-id="0730c-141">若要显示 `--theme-body-background` CSS 变量的变量定义，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="0730c-141">To display the variable definition for the `--theme-body-background` CSS variable, complete the following actions.</span></span>  

1.  <span data-ttu-id="0730c-142">在 **样式** 窗格中，选择 `var(--theme-body-background)`。</span><span class="sxs-lookup"><span data-stu-id="0730c-142">In the **Styles** pane, choose `var(--theme-body-background)`.</span></span>  
1.  <span data-ttu-id="0730c-143">**样式** 窗格现在显示 `--theme-body-background` CSS 变量的定义。</span><span class="sxs-lookup"><span data-stu-id="0730c-143">The **Styles** pane now displays the definition of the `--theme-body-background` CSS variable.</span></span>  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support.msft.png" alt-text="链接到样式的 CSS 变量" lightbox="../../media/2020/11/css-variable-support.msft.png":::
         <span data-ttu-id="0730c-145">链接到样式的 CSS 变量</span><span class="sxs-lookup"><span data-stu-id="0730c-145">CSS variable linked to the style</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/css-variable-support-target.msft.png" alt-text="链接到样式目标的 CSS 变量" lightbox="../../media/2020/11/css-variable-support-target.msft.png":::
         <span data-ttu-id="0730c-147">链接到样式目标的 CSS 变量</span><span class="sxs-lookup"><span data-stu-id="0730c-147">CSS variable linked to style target</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="service-worker-debugging-improvements"></a><span data-ttu-id="0730c-148">服务工作线程调试改进</span><span class="sxs-lookup"><span data-stu-id="0730c-148">Service worker debugging improvements</span></span>  

<!-- Title:  Service worker debugging improvements in the Network, Application, and Sources tools  -->  
<!-- Subtitle:  Making service workers easier to debug for progressive web applications and more.  -->  

<span data-ttu-id="0730c-149">[网络](#network-tool)、[应用程序](#application-tool) 和 [源](#sources-tool) 工具中的以下新功能可帮助您构建 [PWA][ProgressiveWebAppsIndex]。</span><span class="sxs-lookup"><span data-stu-id="0730c-149">The following new features in the [Network](#network-tool), [Application](#application-tool), and [Sources](#sources-tool) tools help you build your [PWA][ProgressiveWebAppsIndex].</span></span>  <span data-ttu-id="0730c-150">在调试服务工作线程遇到困难时，请使用以下功能。</span><span class="sxs-lookup"><span data-stu-id="0730c-150">Use the following features when you have difficulty debugging your service worker.</span></span>  

<span data-ttu-id="0730c-151">请求路由显示基于通过服务工作线程运行的网络请求的 `startup` 和 `fetch` 事件。</span><span class="sxs-lookup"><span data-stu-id="0730c-151">Request routing displays the `startup` and `fetch` events based on the network requests that run through service workers.</span></span>  <span data-ttu-id="0730c-152">通过 **应用程序** 或 **网络工具** 访问时间线。</span><span class="sxs-lookup"><span data-stu-id="0730c-152">The timelines are accessed from either the **Application** or **Network** tool.</span></span>  <span data-ttu-id="0730c-153">当你遇到服务工作人员的问题，并且想要在 或 事件出错时显示时间线 `startup` `fetch` 帮助。</span><span class="sxs-lookup"><span data-stu-id="0730c-153">The timelines help when you are having trouble with service workers and want to display if something is wrong with the `startup` or `fetch` event.</span></span>  

### <a name="application-tool"></a><span data-ttu-id="0730c-154">应用程序工具</span><span class="sxs-lookup"><span data-stu-id="0730c-154">Application tool</span></span>  

<!-- Title: Open Network tool from the Service Workers pane  -->  
<!-- Subtitle: Display additional context when debugging a service worker.  -->  

<span data-ttu-id="0730c-155">通过新的 **网络请求**链接查看所有服务工作线程请求路由信息。</span><span class="sxs-lookup"><span data-stu-id="0730c-155">View all service worker request routing information with the new **Network requests** link.</span></span>  <span data-ttu-id="0730c-156">若要在调试服务工作线程时显示其他上下文，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="0730c-156">To display additional context when debugging the service worker, complete the following actions.</span></span>  

1.  <span data-ttu-id="0730c-157">导航到 **应用程序**  >  **服务工作线程**。</span><span class="sxs-lookup"><span data-stu-id="0730c-157">Navigate to **Application** > **Service Workers**.</span></span>  
1.  <span data-ttu-id="0730c-158">选择 **网络请求**。</span><span class="sxs-lookup"><span data-stu-id="0730c-158">Choose **Network requests**.</span></span>  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-requests.msft.png" alt-text="从“服务工作线程”窗格中打开“网络”工具" lightbox="../../media/2020/11/service-worker-application-network-requests.msft.png":::
       <span data-ttu-id="0730c-160">从 **服务工作线程** 窗格中打开 **网络** 工具</span><span class="sxs-lookup"><span data-stu-id="0730c-160">Open **Network** tool from the **Service Workers** pane</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="0730c-161">**网络** 工具在 **工具箱** 中打开，并显示所有与服务工作线程相关的网络请求。</span><span class="sxs-lookup"><span data-stu-id="0730c-161">The **Network** tool opens in the **drawer** and displays all service worker-related network requests.</span></span>  <span data-ttu-id="0730c-162">使用 `is:service-worker-intercepted` 筛选网络请求。</span><span class="sxs-lookup"><span data-stu-id="0730c-162">The network requests are filtered using `is:service-worker-intercepted`.</span></span>  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-drawer.msft.png" alt-text="工具箱中的网络工具" lightbox="../../media/2020/11/service-worker-application-network-drawer.msft.png":::
       <span data-ttu-id="0730c-164">**工具箱** 中的 **网络** 工具</span><span class="sxs-lookup"><span data-stu-id="0730c-164">**Network** tool in **drawer**</span></span>  
    :::image-end:::
    
1. <span data-ttu-id="0730c-165">若要将 **网络** 工具恢复到顶部面板，请关闭 **工具箱**。</span><span class="sxs-lookup"><span data-stu-id="0730c-165">To return the **Network** tool to the top panel, close the **drawer**.</span></span>  
    
    :::image type="complex" source="../../media/2020/11/service-worker-application-network-return.msft.png" alt-text="关闭工具箱以返回网络工具" lightbox="../../media/2020/11/service-worker-application-network-return.msft.png":::
       <span data-ttu-id="0730c-167">关闭 **工具箱** 以返回 **网络** 工具</span><span class="sxs-lookup"><span data-stu-id="0730c-167">Close the **drawer** to return **Network** tool</span></span>  
    :::image-end:::  
    
### <a name="network-tool"></a><span data-ttu-id="0730c-168">网络工具</span><span class="sxs-lookup"><span data-stu-id="0730c-168">Network tool</span></span>  

<span data-ttu-id="0730c-169">调试通过服务工作线程运行的网络请求。</span><span class="sxs-lookup"><span data-stu-id="0730c-169">Debug network requests that run through service workers.</span></span>  <span data-ttu-id="0730c-170">您还可以从 **应用程序** 工具打开网络请求。</span><span class="sxs-lookup"><span data-stu-id="0730c-170">You may also open network requests from the **Application** tool.</span></span>  <span data-ttu-id="0730c-171">对于每个请求，DevTools 在 [计时][DevtoolsNetworkReferenceViewTimingBreakdownRequest] 窗格中显示以下信息。</span><span class="sxs-lookup"><span data-stu-id="0730c-171">For each request, DevTools display the following information in the [Timing][DevtoolsNetworkReferenceViewTimingBreakdownRequest] pane.</span></span>  

*   <span data-ttu-id="0730c-172">请求开示和启动持续时间。</span><span class="sxs-lookup"><span data-stu-id="0730c-172">The start of a request and duration of the bootstrap.</span></span>  
*   <span data-ttu-id="0730c-173">对服务工作线程注册的更改。</span><span class="sxs-lookup"><span data-stu-id="0730c-173">Changes to service worker registration.</span></span>  
*   <span data-ttu-id="0730c-174">`fetch` 事件处理器的运行时。</span><span class="sxs-lookup"><span data-stu-id="0730c-174">The runtime of a `fetch` event handler.</span></span>  
*   <span data-ttu-id="0730c-175">用于加载客户端的所有 `fetch` 事件的运行时。</span><span class="sxs-lookup"><span data-stu-id="0730c-175">The runtime of all `fetch` events for loading a client.</span></span>  
    
:::image type="complex" source="../../media/2020/11/network-timing-service-worker.msft.png" alt-text="计时窗格" lightbox="../../media/2020/11/network-timing-service-worker.msft.png":::
   <span data-ttu-id="0730c-177">**计时** 窗格</span><span class="sxs-lookup"><span data-stu-id="0730c-177">**Timing** pane</span></span>  
:::image-end:::  

### <a name="sources-tool"></a><span data-ttu-id="0730c-178">源工具</span><span class="sxs-lookup"><span data-stu-id="0730c-178">Sources tool</span></span>  

<span data-ttu-id="0730c-179">在旧版 Microsoft Edge 中，调用堆栈的深度级别仅限于服务工作线程中的 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="0730c-179">In previous versions of Microsoft Edge, the level of depth in the call stack was limited to the JavaScript code in your service worker.</span></span>  <span data-ttu-id="0730c-180">在 Microsoft Edge 88 中，调用堆栈现在显示通过服务工作线程运行的请求发起程序。</span><span class="sxs-lookup"><span data-stu-id="0730c-180">In Microsoft Edge 88, the call stack now displays the initiator of requests that run through your service worker.</span></span>  

<span data-ttu-id="0730c-181">若要定位请求发起程序，请使用服务工作线程中 JavaScript 代码的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="0730c-181">To locate the initiator of the request, use the call stack of your JavaScript code in the service worker.</span></span>  <span data-ttu-id="0730c-182">下图中调用堆栈以服务工作线程中的 JavaScript 代码开头，并将对原始网页请求的引用显示为 `(index):157`。</span><span class="sxs-lookup"><span data-stu-id="0730c-182">The call stack in the following figures starts with the JavaScript code in your service worker and displays a reference to the original webpage request as `(index):157`.</span></span>  <span data-ttu-id="0730c-183">第二个图中，选择引用并打开提出请求的发起程序。</span><span class="sxs-lookup"><span data-stu-id="0730c-183">In the second figure, the reference is chosen and opened the initiator that made the request.</span></span>  <span data-ttu-id="0730c-184">第二个图中的发起程序是网页。</span><span class="sxs-lookup"><span data-stu-id="0730c-184">The initiator in the second figure is the webpage.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png" alt-text="此 service-worker.js 文件和调用堆栈突出显示请求原始发起程序。" lightbox="../../media/2020/11/service-worker-sources-stopped-at-breakpoint.msft.png":::
         <span data-ttu-id="0730c-186">`service-worker.js` 文件和调用堆栈突出显示请求原始发起程序</span><span class="sxs-lookup"><span data-stu-id="0730c-186">The `service-worker.js` file and call stack highlighting request originator</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/service-worker-sources-call-stack-target.msft.png" alt-text="（索引）网页是请求发起程序" lightbox="../../media/2020/11/service-worker-sources-call-stack-target.msft.png":::
         <span data-ttu-id="0730c-188">`(index)` 网页是请求发起程序</span><span class="sxs-lookup"><span data-stu-id="0730c-188">The `(index)` webpage is the request initiator</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="copy-property-value-of-a-network-request"></a><span data-ttu-id="0730c-189">复制网络请求的属性值</span><span class="sxs-lookup"><span data-stu-id="0730c-189">Copy property value of a network request</span></span>  

<!-- Title: Copy response JSON in Network tool using the contextual menu  -->  
<!-- Subtitle:  The Network tool now has a more consistent UX.  Easily copy the JSON response using the contextual menu.  -->  

<span data-ttu-id="0730c-190">在 **网络** 工具中，使用新的 **复制值** 选项复制网络请求的属性值。</span><span class="sxs-lookup"><span data-stu-id="0730c-190">In the **Network** tool, copy the property value of a network request using the new **Copy value** option.</span></span>  <span data-ttu-id="0730c-191">将属性值复制为解码的 JSON 值。</span><span class="sxs-lookup"><span data-stu-id="0730c-191">The property value is copied as a decoded JSON value.</span></span>  <span data-ttu-id="0730c-192">在旧版 Microsoft Edge 中，必须执行下列操作之一复制值。</span><span class="sxs-lookup"><span data-stu-id="0730c-192">In previous versions of Microsoft Edge, you had to copy a value using one of the following actions.</span></span>  

*   <span data-ttu-id="0730c-193">突出显示并复制整个文本。</span><span class="sxs-lookup"><span data-stu-id="0730c-193">Highlight the entire text and copy it.</span></span>  
*   <span data-ttu-id="0730c-194">将值存储为全局变量（如果适用），然后从 DevTools [控制台][DevtoolsConsoleIndex] 将其复制。</span><span class="sxs-lookup"><span data-stu-id="0730c-194">Store the value as global variable, as applicable, and copy it from the DevTools [Console][DevtoolsConsoleIndex].</span></span>  
    
<span data-ttu-id="0730c-195">若要将属性值复制到剪贴板，导航至 [复制格式化响应 JSON 到剪贴板][DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]。</span><span class="sxs-lookup"><span data-stu-id="0730c-195">To copy the property value to your clipboard, navigate to [Copy formatted response JSON to the clipboard][DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard].</span></span>  <span data-ttu-id="0730c-196">若要审阅 Chromium 开源项目中此功能的历史记录，请导航至问题[1132084][CR1132084]。</span><span class="sxs-lookup"><span data-stu-id="0730c-196">To review the history of this feature in the Chromium open-source project, navigate to Issue [1132084][CR1132084].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/copy-property-value.msft.png" alt-text="在 DevTools 中复制属性值" lightbox="../../media/2020/11/copy-property-value.msft.png":::
         <span data-ttu-id="0730c-198">在 DevTools 中复制属性值</span><span class="sxs-lookup"><span data-stu-id="0730c-198">Copy property value in DevTools</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/11/paste-property-value.msft.png" alt-text="将属性值粘贴到 Microsoft Visual Studio Code 中" lightbox="../../media/2020/11/paste-property-value.msft.png":::
         <span data-ttu-id="0730c-200">将属性值粘贴到 Microsoft Visual Studio Code 中</span><span class="sxs-lookup"><span data-stu-id="0730c-200">Paste property value in Microsoft Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="customize-multi-press-keyboard-shortcuts"></a><span data-ttu-id="0730c-201">自定义多键连发键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="0730c-201">Customize multi-press keyboard shortcuts</span></span>  

<!-- Title: Customize multi-press keyboard shortcuts  -->  
<!-- Subtitle: Create custom multi-press keyboard shortcuts in the shortcut editor.  -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::

<span data-ttu-id="0730c-202">[自 Microsoft Edge 版本 87][WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings] 起，可以为 DevTools 中任何操作自定义键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0730c-202">[Since Microsoft Edge version 87][WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings], you may customize keyboard shortcuts for any action in DevTools.</span></span>  <span data-ttu-id="0730c-203">在 Microsoft Edge 版本 88 中，现在可以创建多键连发快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0730c-203">In Microsoft Edge version 88, you may now create multi-press keyboard shortcuts.</span></span>  <span data-ttu-id="0730c-204">若要在 DevTools 中为某个操作设置快捷方式，请导航至 [设置][DevtoolsCustomizeIndexSettings] > **实验**，并选中 **启用键盘快捷方式编辑器** 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="0730c-204">To set a shortcut for an action in the DevTools, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**  and choose the checkbox next to **Enable keyboard shortcut editor**.</span></span>  <span data-ttu-id="0730c-205">有关自定义和编辑快捷方式详细信息，请导航至 [启用键盘快捷方式编辑器实验功能][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。</span><span class="sxs-lookup"><span data-stu-id="0730c-205">For more information about customizing and editing shortcuts, navigate to [Enable keyboard shortcut editor Experimental feature][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  

<span data-ttu-id="0730c-206">例如，红色高亮显示的是为 **开始录制事件** 操作而自定义的多键连发键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0730c-206">For example, the red highlight displays a multi-press keyboard shortcut customized for the **Start recording events** action.</span></span>  <span data-ttu-id="0730c-207">若要在 Chromium 开源项目中查看此功能实时更新，请导航至 [问题 #174309][CR174309]。</span><span class="sxs-lookup"><span data-stu-id="0730c-207">To review real-time updates on this feature in the Chromium open-source project, navigate to [Issue #174309][CR174309].</span></span>  

:::image type="complex" source="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png" alt-text="和弦键盘快捷方式" lightbox="../../media/2020/11/multi-press-keyboard-shortcuts.msft.png":::
   <span data-ttu-id="0730c-209">多键连发键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="0730c-209">Multi-press keyboard shortcuts</span></span>  
:::image-end:::  

## <a name="devtools-now-match-browser-language"></a><span data-ttu-id="0730c-210">DevTools 现已匹配浏览器语言</span><span class="sxs-lookup"><span data-stu-id="0730c-210">DevTools now match browser language</span></span>  

<span data-ttu-id="0730c-211">在 Microsoft Edge 版本 87 中，如果在 [DevTools 设置][DevtoolsCustomizeIndexSettings] 中打开 **匹配浏览器语言** 设置，则 DevTools 不会匹配浏览器语言。</span><span class="sxs-lookup"><span data-stu-id="0730c-211">In Microsoft Edge version 87, if you turned on the **Match browser language** setting in [DevTools Settings][DevtoolsCustomizeIndexSettings], DevTools did not match the browser language.</span></span>  <span data-ttu-id="0730c-212">在 Microsoft Edge 版本 88 中，如果打开 **匹配浏览器语言** 设置，则 DevTools 现在与浏览器语言匹配。</span><span class="sxs-lookup"><span data-stu-id="0730c-212">In Microsoft Edge version 88, DevTools now matches the browser language if you turn on the **Match browser language** setting.</span></span>  <span data-ttu-id="0730c-213">有关 **Match 浏览器语言** DevTools 设置的详细信息，请导航至 [更改 DevTools 语言设置][DevtoolsCustomizeLocalization]。</span><span class="sxs-lookup"><span data-stu-id="0730c-213">For more information about the **Match browser language** DevTools Setting, navigate to [Change DevTools language settings][DevtoolsCustomizeLocalization].</span></span>  

:::image type="complex" source="../../media/2020/11/startpage-devtools-settings-japanese.msft.png" alt-text="匹配浏览器语言 DevTools 设置（日语）" lightbox="../../media/2020/11/startpage-devtools-settings-japanese.msft.png":::
   <span data-ttu-id="0730c-215">**匹配浏览器语言** DevTools 设置（日语）</span><span class="sxs-lookup"><span data-stu-id="0730c-215">**Match browser language** DevTools setting in Japanese</span></span>  
:::image-end:::  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="0730c-216">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="0730c-216">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="new-css-angle-visualization-tools"></a><span data-ttu-id="0730c-217">全新 CSS 角度可视化工具</span><span class="sxs-lookup"><span data-stu-id="0730c-217">New CSS angle visualization tools</span></span>  

<span data-ttu-id="0730c-218">现在，DevTools 可以更好地支持 CSS 角度调试。</span><span class="sxs-lookup"><span data-stu-id="0730c-218">DevTools now have better support for CSS angle debugging.</span></span>  <span data-ttu-id="0730c-219">如果页面上 HTML 元素应用 CSS 角度，**样式** 工具中该角度旁边会显示一个时钟图标。</span><span class="sxs-lookup"><span data-stu-id="0730c-219">When an HTML element on your page has CSS angle applied to it, a clock icon is displayed next to the angle in the **Styles** tool.</span></span>  <span data-ttu-id="0730c-220">若要切换时钟覆盖层，请选择时钟图标。</span><span class="sxs-lookup"><span data-stu-id="0730c-220">To toggle the clock overlay, choose the clock icon.</span></span>  <span data-ttu-id="0730c-221">若要更改角度，请选择时钟中的任何位置或拖动指针。</span><span class="sxs-lookup"><span data-stu-id="0730c-221">To change the angle, choose anywhere in the clock or drag the needle.</span></span>  <span data-ttu-id="0730c-222">若要更改角度值，还可使用鼠标和键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0730c-222">To change the angle value, you may also use mouse and keyboard shortcuts.</span></span>  <!--  To learn more, navigate to [Angle Clock][DevtoolsCssReferenceChangeAngleValueWithAngleClock].  -->  <span data-ttu-id="0730c-223">若要在 Chromium 开源项目中查看此功能实时更新，请导航到“问题” [1126178][CR1126178] 和 [1138633][CR1138633]。</span><span class="sxs-lookup"><span data-stu-id="0730c-223">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [1126178][CR1126178] and [1138633][CR1138633].</span></span>  

<!--todo:  add link when css angle clock section exists.  -->  

<span data-ttu-id="0730c-224">示例使用了以下 CSS 角度。</span><span class="sxs-lookup"><span data-stu-id="0730c-224">The following CSS angle is used for the example.</span></span>  

```css
background: linear-gradient(100deg, lightblue, pink);
```  

:::image type="complex" source="../../media/2020/11/css-angle.msft.png" alt-text="CSS 角度" lightbox="../../media/2020/11/css-angle.msft.png":::
   <span data-ttu-id="0730c-226">CSS 角度</span><span class="sxs-lookup"><span data-stu-id="0730c-226">CSS angle</span></span>  
:::image-end:::  

### <a name="simulate-storage-quota-size-in-the-storage-pane"></a><span data-ttu-id="0730c-227">模拟存储窗格中的存储配额大小</span><span class="sxs-lookup"><span data-stu-id="0730c-227">Simulate storage quota size in the Storage pane</span></span>  

<span data-ttu-id="0730c-228">现在，可以在 **存储** 窗格中重写存储配额大小。</span><span class="sxs-lookup"><span data-stu-id="0730c-228">You may now override storage quota size in the **Storage** pane.</span></span>  <span data-ttu-id="0730c-229">此功能允许你模拟不同的设备，并测试网站或应用在低磁盘可用性场景中的行为。</span><span class="sxs-lookup"><span data-stu-id="0730c-229">This feature allows you to simulate different devices and test the behavior of your website or app in low disk availability scenarios.</span></span>  <span data-ttu-id="0730c-230">若要模拟存储配额，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="0730c-230">To simulate the storage quota, complete the following actions.</span></span>  

1.  <span data-ttu-id="0730c-231">导航至 **应用程序** > **存储**。</span><span class="sxs-lookup"><span data-stu-id="0730c-231">Navigate to **Application** > **Storage**.</span></span>  
1.  <span data-ttu-id="0730c-232">打开 **模拟自定义存储配额** 复选框。</span><span class="sxs-lookup"><span data-stu-id="0730c-232">Turn on the **Simulate custom storage quota** checkbox.</span></span>  
1.  <span data-ttu-id="0730c-233">输入有效号码。</span><span class="sxs-lookup"><span data-stu-id="0730c-233">Enter a valid number.</span></span>  
    
<span data-ttu-id="0730c-234">若要了解如何在 DevTools 中模拟移动设备和其他功能的详细信息，请导航至 [在 Microsoft Edge DevTools 中模拟移动设备移动设备][DevtoolsDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="0730c-234">For more information about how to emulate mobile devices and other features in the DevTools, navigate to [Emulate mobile devices in Microsoft Edge DevTools ][DevtoolsDeviceModeIndex].</span></span>  <span data-ttu-id="0730c-235">若要审阅 Chromium 开源项目中此功能的实时更新，请导航至“问题” [945786][CR945786] 和 [1146985][CR1146985]。</span><span class="sxs-lookup"><span data-stu-id="0730c-235">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [945786][CR945786] and [1146985][CR1146985].</span></span>  

:::image type="complex" source="../../media/2020/11/storage-quota.msft.png" alt-text="模拟存储配额大小" lightbox="../../media/2020/11/storage-quota.msft.png":::
   <span data-ttu-id="0730c-237">模拟存储配额大小</span><span class="sxs-lookup"><span data-stu-id="0730c-237">Simulate storage quota size</span></span>  
:::image-end:::  

### <a name="report-cors-errors-in-the-network-tool"></a><span data-ttu-id="0730c-238">报告网络工具中的 CORS 错误</span><span class="sxs-lookup"><span data-stu-id="0730c-238">Report CORS errors in the Network tool</span></span>  

<span data-ttu-id="0730c-239">通过导航至 [CORS 错误演示][GlitchCorsErrors] 尝试此功能。</span><span class="sxs-lookup"><span data-stu-id="0730c-239">Try out this feature by navigating to [CORS error demo][GlitchCorsErrors].</span></span>  <span data-ttu-id="0730c-240">打开 **网络** 工具，刷新页面，并观察失败的 CORS 网络请求。</span><span class="sxs-lookup"><span data-stu-id="0730c-240">Open the **Network** tool, refresh the page, and observe the failed CORS network request.</span></span>  <span data-ttu-id="0730c-241">状态列显示 **CORS 错误**。</span><span class="sxs-lookup"><span data-stu-id="0730c-241">The status column displays the **CORS error**.</span></span>  <span data-ttu-id="0730c-242">将鼠标悬停在错误上时，工具提示现在将显示错误代码。</span><span class="sxs-lookup"><span data-stu-id="0730c-242">When you hover on the error, the tooltip now displays the error code.</span></span>  <span data-ttu-id="0730c-243">在 Microsoft Edge 版本 87 及更早版本中，DevTools 只显示CORS 错误的一般 **（失败）** 状态。</span><span class="sxs-lookup"><span data-stu-id="0730c-243">In Microsoft Edge version 87 and earlier, DevTools only displayed generic **(failed)** status for CORS errors.</span></span>  <span data-ttu-id="0730c-244">若要审阅 Chromium 开源项目中此功能的实时更新，请导航至问题[1141824][CR1141824]。</span><span class="sxs-lookup"><span data-stu-id="0730c-244">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [1141824][CR1141824].</span></span>  

:::image type="complex" source="../../media/2020/11/cors-err.msft.png" alt-text="CORS 错误" lightbox="../../media/2020/11/cors-err.msft.png":::
   <span data-ttu-id="0730c-246">CORS 错误</span><span class="sxs-lookup"><span data-stu-id="0730c-246">CORS errors</span></span>  
:::image-end:::  

### <a name="frame-details-view-updates"></a><span data-ttu-id="0730c-247">框架详细信息视图更新</span><span class="sxs-lookup"><span data-stu-id="0730c-247">Frame details view updates</span></span>  

#### <a name="cross-origin-isolation-information-in-the-frame-details-view"></a><span data-ttu-id="0730c-248">框架详细信息视图中的跨域隔离信息</span><span class="sxs-lookup"><span data-stu-id="0730c-248">Cross-origin isolation information in the Frame details view</span></span>  

<span data-ttu-id="0730c-249">现在，跨域隔离状态在 **安全性和隔离** 区域下显示。</span><span class="sxs-lookup"><span data-stu-id="0730c-249">The cross-origin isolated status is now displayed under the **Security & Isolation** section.</span></span>  <span data-ttu-id="0730c-250">新的 **API 可用性** 区域显示 `SharedArrayBuffer` \ (\) 的可用性，以及是否可以使用 `postMessage()` 共享缓冲区。</span><span class="sxs-lookup"><span data-stu-id="0730c-250">The new **API availability** section displays the availability of `SharedArrayBuffer`s \(SAB\) and whether the buffers may be shared using `postMessage()`.</span></span>  <span data-ttu-id="0730c-251">弃用警告显示 SAB 和 `postMessage()` 当前是否可用，但上下文并非跨域隔离。</span><span class="sxs-lookup"><span data-stu-id="0730c-251">A deprecation warning displays if the SAB and `postMessage()` is currently available, but the context is not cross-origin isolated.</span></span>  <span data-ttu-id="0730c-252">有关跨域隔离以及为何需要如 `SharedArrayBuffers` 一样的功能的详细信息 ，请导航至 [WindowOrWorkerGlobalScope.crossOriginIsolated][MdnWindoworworkerglobalscopeCrossoriginisolated]。</span><span class="sxs-lookup"><span data-stu-id="0730c-252">For more information about cross-origin isolation and why it is required for features like `SharedArrayBuffers`, navigate to [WindowOrWorkerGlobalScope.crossOriginIsolated][MdnWindoworworkerglobalscopeCrossoriginisolated].</span></span>  <span data-ttu-id="0730c-253">若要审阅 Chromium 开源项目中此功能的实时更新，请导航至“问题” [1139899][CR1139899]。</span><span class="sxs-lookup"><span data-stu-id="0730c-253">To review real-time updates of this feature in the Chromium open-source project, navigate to Issue [1139899][CR1139899].</span></span>  

:::image type="complex" source="../../media/2020/11/frame-cross-origin-isolated-api.msft.png" alt-text="跨域信息" lightbox="../../media/2020/11/frame-cross-origin-isolated-api.msft.png":::
   <span data-ttu-id="0730c-255">跨域信息</span><span class="sxs-lookup"><span data-stu-id="0730c-255">Cross-origin information</span></span>  
:::image-end:::  

#### <a name="new-web-workers-information-in-the-frame-details-view"></a><span data-ttu-id="0730c-256">框架详细信息视图中的新 Web 工作线程信息</span><span class="sxs-lookup"><span data-stu-id="0730c-256">New Web Workers information in the Frame details view</span></span>  

<span data-ttu-id="0730c-257">现在，DevTools 在相关的父框架下组织 Web 工作线程。</span><span class="sxs-lookup"><span data-stu-id="0730c-257">DevTools now organizes web workers under the relevant parent frame.</span></span>  <span data-ttu-id="0730c-258">例如，如果 `someName` 框架创建 `worker.js`，则 `worker.js` 出现在 **框架** 列表中的 `someName` 之下。</span><span class="sxs-lookup"><span data-stu-id="0730c-258">For example, if the `someName` frame creates `worker.js`, then `worker.js` appears under `someName` in the **Frames** list.</span></span>  <span data-ttu-id="0730c-259">若要查看 web 工作线程的详细信息，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="0730c-259">To view the details of the web worker, complete the following actions.</span></span>  

1.  <span data-ttu-id="0730c-260">打开 **应用程序** 工具。</span><span class="sxs-lookup"><span data-stu-id="0730c-260">Open **Application** tool.</span></span>  
1.  <span data-ttu-id="0730c-261">展开包含 web 工作线程的框架。</span><span class="sxs-lookup"><span data-stu-id="0730c-261">Expand a frame that contains web workers.</span></span>  
1.  <span data-ttu-id="0730c-262">展开 **工作线程** 树。</span><span class="sxs-lookup"><span data-stu-id="0730c-262">Expand the **Workers** tree.</span></span>  
1.  <span data-ttu-id="0730c-263">选择工作线程。</span><span class="sxs-lookup"><span data-stu-id="0730c-263">Choose a worker.</span></span>  
    
<span data-ttu-id="0730c-264">若要审阅 Chromium 开源项目中此功能的实时更新，请导航至“问题” [1122507][CR1122507] 和 [1051466][CR1051466]。</span><span class="sxs-lookup"><span data-stu-id="0730c-264">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [1122507][CR1122507] and [1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/11/application-frames-service-workers.msft.png" alt-text="Web 工作线程信息" lightbox="../../media/2020/11/application-frames-service-workers.msft.png":::
   <span data-ttu-id="0730c-266">Web 工作线程信息</span><span class="sxs-lookup"><span data-stu-id="0730c-266">Web workers information</span></span>  
:::image-end:::  

#### <a name="display-opener-frame-details-for-opened-windows"></a><span data-ttu-id="0730c-267">显示已打开窗口的原框架详细信息</span><span class="sxs-lookup"><span data-stu-id="0730c-267">Display opener frame details for opened windows</span></span>  

<span data-ttu-id="0730c-268">现在，DevTools 在相关的父 [框架][MdnWindowFrames] 下组织已打开的 [窗口][MdnWindowConstructors]。</span><span class="sxs-lookup"><span data-stu-id="0730c-268">DevTools now organizes opened [Windows][MdnWindowConstructors] under the relevant parent [frame][MdnWindowFrames].</span></span>  <span data-ttu-id="0730c-269">例如，如果 `top` 框架打开 `Window` 到 `https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium`， 则框架 `Window` 将显示在 **列表** 中的 `top` 之下。</span><span class="sxs-lookup"><span data-stu-id="0730c-269">For example, if the `top` frame opens a `Window` to `https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium`, then the `Window` appears under `top` in the **Frames** list.</span></span>  

<span data-ttu-id="0730c-270">若要显示负责在 **元素** 工具中打开另一个窗口的框架，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="0730c-270">To reveal the frame responsible for opening another Window in the **Elements** tool, complete the following actions.</span></span>  

1.  <span data-ttu-id="0730c-271">打开 **框架** 树。</span><span class="sxs-lookup"><span data-stu-id="0730c-271">Open the **Frames** tree.</span></span>  
1.  <span data-ttu-id="0730c-272">展开 **已打开窗口**，然后选择 `Window` 选取希望了解 的父框架。</span><span class="sxs-lookup"><span data-stu-id="0730c-272">Expand **Opened Windows** and choose the `Window` for the parent frame you want to know.</span></span>  
1.  <span data-ttu-id="0730c-273">选择 **原框架** 链接。</span><span class="sxs-lookup"><span data-stu-id="0730c-273">Choose the **Opener Frame** link.</span></span>  

<span data-ttu-id="0730c-274">将显示有关哪个框架导致另一个 `Window` 打开的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0730c-274">The details are displayed about which frame caused the opening of another `Window`.</span></span>  <span data-ttu-id="0730c-275">若要在 **元素** 工具中显示原框架，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="0730c-275">To reveal the opener in the **Elements** tool, complete the following actions.</span></span>  

1.  <span data-ttu-id="0730c-276">打开 **框架** 树。</span><span class="sxs-lookup"><span data-stu-id="0730c-276">Open the **Frames** tree.</span></span>  
1.  <span data-ttu-id="0730c-277">选择已打开窗口以打开 `Window` 详细信息。</span><span class="sxs-lookup"><span data-stu-id="0730c-277">Choose an opened window to open the `Window` details.</span></span>  
1.  <span data-ttu-id="0730c-278">选择 **原框架** 链接。</span><span class="sxs-lookup"><span data-stu-id="0730c-278">Choose the **Opener Frame** link.</span></span>  
    
<span data-ttu-id="0730c-279">若要查看 Chromium 开源项目中此功能的历史记录，请导航到问题 [1107766][CR1107766]。</span><span class="sxs-lookup"><span data-stu-id="0730c-279">To review the history of this feature in the Chromium open-source project, navigate to Issue [1107766][CR1107766].</span></span>  

:::image type="complex" source="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png" alt-text="已打开框架的详细信息" lightbox="../../media/2020/11/application-frames-opened-windows-security-opener-frame.msft.png":::
   <span data-ttu-id="0730c-281">已打开框架的详细信息</span><span class="sxs-lookup"><span data-stu-id="0730c-281">Opened frame details</span></span>  
:::image-end:::  

### <a name="copy-stacktrace-for-network-initiator"></a><span data-ttu-id="0730c-282">复制网络发起程序堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="0730c-282">Copy stacktrace for network initiator</span></span>  

<span data-ttu-id="0730c-283">若要将堆栈跟踪复制到剪贴板，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="0730c-283">To copy the stacktrace to your clipboard, complete the following actions.</span></span>  

1.  <span data-ttu-id="0730c-284">打开上下文菜单\（右键单击\）。</span><span class="sxs-lookup"><span data-stu-id="0730c-284">Open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="0730c-285">选择 **复制** > **复制堆栈跟踪**。</span><span class="sxs-lookup"><span data-stu-id="0730c-285">Choose **Copy** > **Copy stacktrace**.</span></span>  
    
<span data-ttu-id="0730c-286">若要查看 Chromium 开源项目中此功能的历史记录，请导航至问题 [1139615][CR1139615]。</span><span class="sxs-lookup"><span data-stu-id="0730c-286">To review the history of this feature in the Chromium open-source project, navigate to Issue [1139615][CR1139615].</span></span>

:::image type="complex" source="../../media/2020/11/copy-stacktrace.msft.png" alt-text="复制堆栈跟踪" lightbox="../../media/2020/11/copy-stacktrace.msft.png":::
   <span data-ttu-id="0730c-288">复制堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="0730c-288">Copy stacktrace</span></span>  
:::image-end:::  

### <a name="preview-wasm-variable-value-on-mouseover"></a><span data-ttu-id="0730c-289">鼠标悬停时预览 Wasm 变量值</span><span class="sxs-lookup"><span data-stu-id="0730c-289">Preview Wasm variable value on mouseover</span></span>  

<span data-ttu-id="0730c-290">代码暂停时，使用此功能检查 WebAssembly\(Wasm\) 变量的值。</span><span class="sxs-lookup"><span data-stu-id="0730c-290">Use this feature to review the value of a WebAssembly \(Wasm\) variable when your code is paused.</span></span>  <span data-ttu-id="0730c-291">若要显示变量的当前值，请将鼠标悬停在变量上。</span><span class="sxs-lookup"><span data-stu-id="0730c-291">To display the current value of a variable, hover on a variable.</span></span>  <span data-ttu-id="0730c-292">若要审阅 Chromium 开源项目中此功能的实时更新，请导航至“问题” [1058836][CR1058836] 和 [1071432][CR1071432]。</span><span class="sxs-lookup"><span data-stu-id="0730c-292">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [1058836][CR1058836] and [1071432][CR1071432].</span></span>  

:::image type="complex" source="../../media/2020/11/wasm-mouseover.msft.png" alt-text="鼠标悬停时预览 Wasm 变量" lightbox="../../media/2020/11/wasm-mouseover.msft.png":::
   <span data-ttu-id="0730c-294">鼠标悬停时预览 Wasm 变量</span><span class="sxs-lookup"><span data-stu-id="0730c-294">Preview Wasm variable on mouseover</span></span>  
:::image-end:::  

### <a name="consistent-units-of-measurement-for-sizes-of-files-and-memory"></a><span data-ttu-id="0730c-295">文件和内存大小的一致度量单位</span><span class="sxs-lookup"><span data-stu-id="0730c-295">Consistent units of measurement for sizes of files and memory</span></span>  

<span data-ttu-id="0730c-296">现在，DevTools 始终使用 `kB` 显示文件和内存的大小。</span><span class="sxs-lookup"><span data-stu-id="0730c-296">DevTools now consistently use `kB` for displaying sizes of files and memory.</span></span>  <span data-ttu-id="0730c-297">以前的 DevTools 混合 `kB` 和 `KiB`。</span><span class="sxs-lookup"><span data-stu-id="0730c-297">Previously DevTools mixed `kB` and `KiB`.</span></span>

*   `kB` <span data-ttu-id="0730c-298">或千字节\（10^3 或 1000 字节\）</span><span class="sxs-lookup"><span data-stu-id="0730c-298">or kilobyte \(10^3 or 1000 bytes\)</span></span>  
*   `KiB` <span data-ttu-id="0730c-299">或 kibibyte \（2^10 或 1024 字节\）</span><span class="sxs-lookup"><span data-stu-id="0730c-299">or kibibyte \(2^10 or 1024 bytes\)</span></span>  
    
<span data-ttu-id="0730c-300">例如，**网络** 工具以前在标签中使用 `kB`，但在计算中使用 `KiB`。</span><span class="sxs-lookup"><span data-stu-id="0730c-300">For example, the **Network** tool previously used `kB` in the labels, but used `KiB` in calculations.</span></span>  <span data-ttu-id="0730c-301">您的反馈表明这种前后矛盾导致混淆。</span><span class="sxs-lookup"><span data-stu-id="0730c-301">Your feedback showed that this inconsistency caused confusion.</span></span>  <span data-ttu-id="0730c-302">若要查看 Chromium 开源项目中此功能的历史记录，请导航至问题 [1035309][CR1035309]。</span><span class="sxs-lookup"><span data-stu-id="0730c-302">To review the history of this feature in the Chromium open-source project, navigate to Issue [1035309][CR1035309].</span></span>  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="0730c-303">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="0730c-303">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="0730c-304">如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [Microsoft Edge 预览][MicrosoftEdgePreviewChannels] 通道作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="0730c-304">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="0730c-305">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="0730c-305">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="0730c-306">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="0730c-306">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[Devtools3dViewIndex]: /microsoft-edge/devtools-guide-chromium/3d-view/index "3D 视图 | Microsoft Docs"  
[DevtoolsConsoleIndex]: /microsoft-edge/devtools-guide-chromium/console/index "控制台概述 | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeLocalization]: /microsoft-edge/devtools-guide-chromium/customize/localization "更改 DevTools 语言设置 | Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "启用键盘快捷方式编辑器 - 实验功能 | microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnCompositedLayers3dView]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-composited-layers-in-3d-view "在 3D 视图中打开复合层 - 实验功能 | Microsoft Docs"  
[DevtoolsIssuesIndex]: /microsoft-edge/devtools-guide-chromium/issues/index "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  
[DevtoolsNetworkReferenceCopyFormattedResponseJsonClipboard]: /microsoft-edge/devtools-guide-chromium/network/reference#copy-formatted-response-json-to-the-clipboard "将格式化的响应 JSON 复制到剪贴板 - 网络分析参考 | Microsoft Docs"  
[DevtoolsNetworkReferenceViewTimingBreakdownRequest]: /microsoft-edge/devtools-guide-chromium/network/reference#view-the-timing-breakdown-of-a-request "查看请求的时间分析 - 网络分析参考 | Microsoft Docs"  
[WebDriverChromiumMain]: /microsoft-edge/webdriver-chromium "使用 WebDriver (Chromium) 测试自动化 | Microsoft Docs"  

<!--  [DevtoolsCssReferenceChangeAngleValueWithAngleClock]: /microsoft-edge/devtools-guide-chromium/css/reference#change-angle-value-with-the-angle-clock "Change angle value with the Angle Clock - CSS reference | Microsoft Docs"  -->  

[ProgressiveWebAppsIndex]: /microsoft-edge/progressive-web-apps-chromium/index "Windows 上的渐进式 Web 应用 | Microsoft Docs"  

[WhatsNew202010DevtoolsCustomizeKeyboardShortcutsSettings]: ../10/devtools.md#customize-keyboard-shortcuts-in-settings "在“设置”中自定义键盘快捷方式 - DeVTools 的新增功能 (Microsoft Edge 87)| Microsoft Docs"  
[WhatsNew202006DevtoolsWebhintFeedbackInTheIssuesPanel]: ../06/devtools.md#webhint-feedback-in-the-issues-panel "问题面板中的 webhint 反馈 - DeVTools 的新增功能 (Microsoft Edge 85) | Microsoft Docs"  

[MicrosoftDeveloperMicrosoftEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "下载 WebDriver | Microsoft 开发人员"  

[MicrosoftinsiderDownloadPlatformLinux]: https://www.microsoftedgeinsider.com/download?platform=linux "下载 Microsoft Edge 预览体验成员频道"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio 代码"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"  

[CR174309]: https://crbug.com/174309 "问题 174309：DevTools：允许自定义键盘快捷方式/键绑定 | Chromium 漏洞"  
[CR945786]: https://crbug.com/945786 "问题 945786：DevTools：允许替代 navigator.storage.estimate () | Chromium 漏洞"  
[CR1029427]: https://crbug.com/1029427 "问题 1029427：减少前端协议消息调度的性能开销 | Chromium 漏洞"  
[CR1035309]: https://crbug.com/1035309 "问题 1035309：DevTools 应始终使用 MB 而不是 mebibyte 表示兆字节 | Chromium 漏洞"  
[CR1051466]: https://crbug.com/1051466 "问题 1051466：在 DevTools 中支持 COOP/COEP 调试 | Chromium 漏洞"  
[CR1058836]: https://crbug.com/1058836 "问题 1058836：关于 Wasm 调试的 UX 问题 | Chromium 漏洞"  
[CR1071432]: https://crbug.com/1071432 "问题 1071432：☂️ Wasm 基本开发人员体验 | Chromium Bug"  
[CR1107766]: https://crbug.com/1107766 "问题 1107766：显示有关框架树中的 "window.open ()" 生成的框架的信息 |Chromium 漏洞"  
[CR1122507]: https://crbug.com/1122507 "问题 1122507：框架树视图中的 Surface 工作线程信息 | Chromium 漏洞"  
[CR1126178]: https://crbug.com/1126178 "问题 1126178：☂ DevTools：CSS <类型> 组件 | Chromium 漏洞"  
[CR1130556]: https://crbug.com/1130556 "问题 1130556：DevTools：测试映像回退（模拟） | Chromium 漏洞"  
[CR1132084]: https://crbug.com/1132084 "问题 1132084：无法轻松复制 JSON 请求有效负载 | Chromium 漏洞"  
[CR1136394]: https://crbug.com/1136394 "问题 1136394：Flexbox 工具 | Chromium 漏洞"  
[CR1138633]: https://crbug.com/1138633 "问题 1138633：DevTools：CSS <角度> 组件应反映其驻留属性在时钟背景中的外观 | Chromium 漏洞"  
[CR1139615]: https://crbug.com/1139615 "问题 1139615：网络发起程序应提供复制堆栈跟踪的能力 | Chromium 漏洞"  
[CR1139899]: https://crbug.com/1139899 "问题 1139899：在框架详细信息视图中报告封闭的 API 的可用性 | Chromium 漏洞"  
[CR1139945]: https://crbug.com/1139945 "问题 1139945：样式面板中弹性框 CSS 属性的图标 | Chromium 漏洞"  
[CR1141824]: https://crbug.com/1141824 "问题 1141824：改进 DevTools 中的 CORS 错误报告 | Chromium 漏洞"  
[CR1144090]: https://crbug.com/1144090 "问题 1144090：将弹性样式修饰器添加到元素树 |Chromium 漏洞"  
[CR1146985]: https://crbug.com/1146985 "问题 1146985：清除的文本仍显示于 Dev Tools 窗口的“存储”部分文本框中 | Chromium 漏洞"  

[GlitchCorsErrors]: https://cors-errors.glitch.me "CORS 错误 | 小故障"  

[MdnCors]: https://developer.mozilla.org/docs/Web/HTTP/CORS "跨域资源共享 (CORS) | MDN"  
[MdnUsingCssCustomProperties]: https://developer.mozilla.org/docs/Web/CSS/Using_CSS_custom_properties "使用 CSS 自定义属性（变量）| MDN"  
[MdnWindowConstructors]: https://developer.mozilla.org/docs/Web/API/Window#Constructors "构造函数 - 窗口 | MDN"  
[MdnWindowFrames]: https://developer.mozilla.org/docs/Web/API/Window/frames "Window.frames | MDN"  
[MdnWindoworworkerglobalscopeCrossoriginisolated]: https://developer.mozilla.org/docs/Web/API/WindowOrWorkerGlobalScope/crossOriginIsolated "WindowOrWorkerGlobalScope.crossOriginIsolated | MDN"  

[WebhintMain]: https://webhint.io "webhint"  
[WebhintUserGuideHintsAccessibility]: https://webhint.io/docs/user-guide/hints/accessibility "辅助功能 | webhint"  
[WebhintUserGuideHintsCompatibility]: https://webhint.io/docs/user-guide/hints/compatibility "兼容性 | webhint"  
[WebhintUserGuideHintsPerformance]: https://webhint.io/docs/user-guide/hints/performance "性能 | webhint"  
[WebhintUserGuideHintsPitfalls]: https://webhint.io/docs/user-guide/hints/pitfalls "隐患 | webhint"  
[WebhintUserGuideHintsPwa]: https://webhint.io/docs/user-guide/hints/pwa "PWA | webhint"  
[WebhintUserGuideHintsSecurity]: https://webhint.io/docs/user-guide/hints/security "安全 | webhint"  

> [!NOTE]
> <span data-ttu-id="0730c-359">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="0730c-359">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0730c-360">原始页面位于 [此处](https://developers.google.com/web/updates/2020/11/devtools/index)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。</span><span class="sxs-lookup"><span data-stu-id="0730c-360">The original page is found [here](https://developers.google.com/web/updates/2020/11/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="0730c-362">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="0730c-362">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
