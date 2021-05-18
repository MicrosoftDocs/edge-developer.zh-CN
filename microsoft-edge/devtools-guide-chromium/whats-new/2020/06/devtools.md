---
description: CSS 网格调试功能、使用网络控制台编辑和重播请求等。
title: 'DevTools (Microsoft Edge 85) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 75642a7f0fa8d6fae2f4daead84e2fc77df21e29
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564926"
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
# <a name="whats-new-in-devtools-microsoft-edge-85"></a><span data-ttu-id="e5fe1-104">DevTools 85 (Microsoft Edge中的新增) </span><span class="sxs-lookup"><span data-stu-id="e5fe1-104">What's New In DevTools (Microsoft Edge 85)</span></span>  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a><span data-ttu-id="e5fe1-105">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="e5fe1-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="e5fe1-106">以下各节列出了你可能从 DevTools 团队中错过Microsoft Edge通知。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="e5fe1-107">请查看公告以试用 DevTools、Microsoft Visual Studio代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-107">Check out the announcements to try new features in the DevTools, Microsoft Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="e5fe1-108">若要随时了解开发人员工具中所有最新且最最好的功能，请下载[Microsoft Edge 预览][MicrosoftEdgePreviewChannels]频道，并按照 Twitter 上的[Microsoft Edge DevTools 团队。][EdgeDevToolsTwitterAccount]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow the Microsoft Edge DevTools team on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <a name="css-grid-debugging-features"></a><span data-ttu-id="e5fe1-109">CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="e5fe1-109">CSS grid debugging features</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   <span data-ttu-id="e5fe1-111">试验功能</span><span class="sxs-lookup"><span data-stu-id="e5fe1-111">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="e5fe1-112">开发人员Microsoft Edge团队正在与 Chrome DevTools 团队和 Chromium 社区协作，以将新的 CSS 网格调试功能添加到 DevTools。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-112">The Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new CSS grid debugging features to DevTools.</span></span>  <span data-ttu-id="e5fe1-113">现在，你可以将网格线号、网格间隔和扩展网格线显示为页面上覆盖。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-113">You are now able to display grid line numbers, grid gaps, and extended grid lines as an on-page overlay.</span></span>  <span data-ttu-id="e5fe1-114">此外，网格工具的更多改进即将推出。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-114">Plus, more improvements to the grid tools are coming soon.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="CSS 网格调试功能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   <span data-ttu-id="e5fe1-116">CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="e5fe1-116">CSS grid debugging features</span></span>
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="e5fe1-117">若要启用实验，请导航到" [打开实验][DevtoolsExperimentalFeaturesTurnOn] 功能"，然后选中"启用新的 CSS 网格调试功能 **"旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-117">To enable the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable new CSS Grid debugging features**.</span></span>  
> 
> <span data-ttu-id="e5fe1-118">若要使用示例试用实验，请导航到 [CSS 网格规划器示例][CodepenRachelweilYzwBzKM]。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-118">To try out the experiment with a sample, navigate to [CSS Grid planner example][CodepenRachelweilYzwBzKM].</span></span>  

<span data-ttu-id="e5fe1-119">Chromium问题[#1047356][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-119">Chromium issue [#1047356][CR1047356]</span></span>  

### <a name="edit-and-replay-requests-with-the-network-console"></a><span data-ttu-id="e5fe1-120">使用网络控制台编辑和重播请求</span><span class="sxs-lookup"><span data-stu-id="e5fe1-120">Edit and Replay requests with the Network Console</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   <span data-ttu-id="e5fe1-122">试验功能</span><span class="sxs-lookup"><span data-stu-id="e5fe1-122">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="e5fe1-123">你现在可以使用网络控制台**在**网络日志中对请求使用[编辑和][DevtoolsNetworkIndexLogActivity]**重播**。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-123">You are now able to use **Edit and Replay** on requests in the [Network Log][DevtoolsNetworkIndexLogActivity] using the **Network Console**.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="使用网络控制台在 NetworkLog 中编辑和重播请求" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   <span data-ttu-id="e5fe1-125">使用网络控制台在 [NetworkLog][DevtoolsNetworkIndexLogActivity] 中编辑和 **重播请求**</span><span class="sxs-lookup"><span data-stu-id="e5fe1-125">Edit and Replay a request in the [NetworkLog][DevtoolsNetworkIndexLogActivity] with the **Network Console**</span></span>  
:::image-end:::  

<span data-ttu-id="e5fe1-126">网络控制台是一个新 **面板，它将** 在 [DevTools"][DevtoolsCustomizeIndexDrawer] 箱"中打开，并自动填充 HTTP 请求的信息。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-126">A new panel, the **Network Console** opens in the [DevTools Drawer][DevtoolsCustomizeIndexDrawer] and automatically populates with information for the HTTP request.</span></span>  <span data-ttu-id="e5fe1-127">若要显示从服务器返回的响应，请编辑请求 \(\) 并选择"发送 **"。**</span><span class="sxs-lookup"><span data-stu-id="e5fe1-127">To display the response returned from the server, edit the request \(if needed\) and select **Send**.</span></span>  

<span data-ttu-id="e5fe1-128">您还可以使用网络 **控制台** 直接从 DevTools 创建和发送 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-128">You may also use the **Network Console** to create and send HTTP requests directly from the DevTools.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text="网络控制台面板" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   <span data-ttu-id="e5fe1-130">网络 **控制台** 面板</span><span class="sxs-lookup"><span data-stu-id="e5fe1-130">The **Network Console** panel</span></span>  
:::image-end:::  

> [!TIP]
> <span data-ttu-id="e5fe1-131">若要在 **主 \(** top\) 面板（而不是 [DevTools 箱][DevtoolsCustomizeIndexDrawer]）中显示网络控制台，请导航到在面板 [之间移动工具](#move-tools-between-panels)。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-131">To display **Network Console** in the main \(top\) panel instead of the [DevTools Drawer][DevtoolsCustomizeIndexDrawer], navigate to [moving tools between panels](#move-tools-between-panels).</span></span>  

> [!NOTE]
> <span data-ttu-id="e5fe1-132">若要启用实验，请导航到打开 [实验][DevtoolsExperimentalFeaturesTurnOn] 功能，然后选择启用网络 **控制台旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-132">To enable the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and choose the checkbox next to **Enable Network Console**.</span></span>  
> 
> <span data-ttu-id="e5fe1-133">打开网络 [日志][DevtoolsNetworkIndexLogActivity]，打开上下文菜单 \(右键单击\) ，然后选择编辑 **和重播**。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-133">Open the [Network Log][DevtoolsNetworkIndexLogActivity], open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  

<span data-ttu-id="e5fe1-134">Chromium问题[#1093687][CR1093687]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-134">Chromium issue [#1093687][CR1093687]</span></span>  

### <a name="service-worker-respondwith-events-in-the-timing-tab"></a><span data-ttu-id="e5fe1-135">服务工作者 respondWith"计时"选项卡中的事件</span><span class="sxs-lookup"><span data-stu-id="e5fe1-135">Service worker respondWith events in the Timing tab</span></span>  

<span data-ttu-id="e5fe1-136">网络 **工具** 的" **计时"** 选项卡现在包括 `respondWith` 服务工作器事件。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-136">The **Timing** tab of the **Network** tool now includes `respondWith` service worker events.</span></span>  <span data-ttu-id="e5fe1-137">服务工作线程事件显示从服务工作进程事件处理程序开始运行前一段时间到处理程序承诺得到实现的时间 `respondWith` `fetch` `respondWith` `fetch` 的持续时间。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-137">The `respondWith` service worker event shows the duration from the time immediately before the service worker `fetch` event handler starts running to the time when the `respondWith` promise of the `fetch` handler is settled.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text="网络面板的计时选项卡中的 respondWith 服务工作线程事件" lightbox="../../media/2020/06/timing-tab.msft.png":::
   <span data-ttu-id="e5fe1-139">网络 `respondWith` 工具的" **计时"** 选项卡中的服务 **工作器** 事件</span><span class="sxs-lookup"><span data-stu-id="e5fe1-139">The `respondWith` service worker event in the **Timing** tab of the **Network** tool</span></span>  
:::image-end:::  

<span data-ttu-id="e5fe1-140">展开 **收到的响应** 以显示来自响应的其他信息， `fetch` 如 `CacheStorageCacheName` 、 `serviceWorkerResponseSource` 和 `ResponseTime` 。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-140">Expand **Response received** to display additional information from the `fetch` response like `CacheStorageCacheName`, `serviceWorkerResponseSource`, and `ResponseTime`.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="展开收到的响应以显示提取响应中的附加信息" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   <span data-ttu-id="e5fe1-142">展开 **收到的响应** 以显示来自响应的其他 `fetch` 信息</span><span class="sxs-lookup"><span data-stu-id="e5fe1-142">Expand **Response received** to display additional information from the `fetch` response</span></span>  
:::image-end:::  

<span data-ttu-id="e5fe1-143">Chromium问题[#1066579][CR1066579]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-143">Chromium issue [#1066579][CR1066579]</span></span>  

### <a name="webhint-feedback-in-the-issues-panel"></a><span data-ttu-id="e5fe1-144">问题面板中的 webhint 反馈</span><span class="sxs-lookup"><span data-stu-id="e5fe1-144">webhint feedback in the Issues panel</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   <span data-ttu-id="e5fe1-146">试验功能</span><span class="sxs-lookup"><span data-stu-id="e5fe1-146">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="e5fe1-147">[webhint][WebhintMain] 是一个开放源代码工具，提供有关网站的辅助功能、跨浏览器兼容性、安全性、性能、PWA 和其他常见 Web 开发问题实时反馈。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-147">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="e5fe1-148">查看"问题"面板中的 [webhint][DevtoolsIssues] 反馈。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-148">To review webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="问题面板中的 webhint 反馈" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   <span data-ttu-id="e5fe1-150">问题面板中的 webhint 反馈</span><span class="sxs-lookup"><span data-stu-id="e5fe1-150">webhint feedback in the Issues panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="e5fe1-151">若要启用实验，请导航到打开 [实验][DevtoolsExperimentalFeaturesTurnOn] 功能，然后选择启用 **Webhint 旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-151">To enable the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and choose the checkbox next to **Enable webhint**.</span></span>  
> 
> <span data-ttu-id="e5fe1-152">打开" [问题][DevtoolsIssues] "面板以显示来自 Webhint 的反馈。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-152">Open the [Issues][DevtoolsIssues] panel to display feedback from webhint.</span></span>  

<span data-ttu-id="e5fe1-153">Chromium问题[#1070378][CR1070378]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-153">Chromium issue [#1070378][CR1070378]</span></span>  

### <a name="move-tools-between-panels"></a><span data-ttu-id="e5fe1-154">在面板之间移动工具</span><span class="sxs-lookup"><span data-stu-id="e5fe1-154">Move tools between panels</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="试验功能":::
   <span data-ttu-id="e5fe1-156">试验功能</span><span class="sxs-lookup"><span data-stu-id="e5fe1-156">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="e5fe1-157">通常，元素和网络等工具\*\*\*\* 只能在\*\*\*\* DevTools 的主 \(\) 面板中打开。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-157">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="e5fe1-158">同样，诸如**3D 视图**和\*\*\*\* 问题等工具可能只能在 DevTools (底部\) 面板中打开。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-158">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="e5fe1-159">现在，你能够通过在顶部和底部面板之间移动工具来自定义 DevTools 布局。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-159">You are now able to customize your DevTools layout by moving tools between the top and bottom panels.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="在面板之间移动工具" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   <span data-ttu-id="e5fe1-161">在面板之间移动工具</span><span class="sxs-lookup"><span data-stu-id="e5fe1-161">Move tools between panels</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="e5fe1-162">若要启用实验，请导航到打开 [实验][DevtoolsExperimentalFeaturesTurnOn] 功能，然后选择启用支持以在面板之间 **移动选项卡旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-162">To enable the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and choose the checkbox next to **Enable support to move tabs between panels**.</span></span>  

<span data-ttu-id="e5fe1-163">Chromium问题[#897944][CR897944]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-163">Chromium issue [#897944][CR897944]</span></span>  

### <a name="improved-initiator-tooltip-in-the-network-panel"></a><span data-ttu-id="e5fe1-164">网络面板中改进的发起人工具提示</span><span class="sxs-lookup"><span data-stu-id="e5fe1-164">Improved Initiator tooltip in the Network panel</span></span>  

<span data-ttu-id="e5fe1-165">在 Microsoft Edge 83 和 84 中，"发起者"列的工具提示显示在使用水平滚动条显示的"网络日志[][DevtoolsNetworkIndexLogActivity]"中，显示资源请求的原因。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-165">In Microsoft Edge 83 and 84, tooltips for the Initiator column, which shows the cause of the resource request, in the [Network Log][DevtoolsNetworkIndexLogActivity] displayed with a horizontal scrollbar.</span></span>  <span data-ttu-id="e5fe1-166">你仅能够在工具提示中水平滚动来显示发起请求的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-166">You were only able to display the call stack that initiated the request by scrolling horizontally in the tooltip.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="84 中的发起Microsoft Edge提示" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   <span data-ttu-id="e5fe1-168">84 中的发起Microsoft Edge提示</span><span class="sxs-lookup"><span data-stu-id="e5fe1-168">The Initiator tooltip in Microsoft Edge 84</span></span>  
:::image-end:::  

<span data-ttu-id="e5fe1-169">从 Microsoft Edge 85 开始，现在可以在工具提示中显示 Initiator 调用堆栈，而无需水平滚动。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-169">Starting with Microsoft Edge 85, you are now able to display the Initiator call stack in the tooltip without scrolling horizontally.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="85 中的发起Microsoft Edge提示" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   <span data-ttu-id="e5fe1-171">85 中的发起Microsoft Edge提示</span><span class="sxs-lookup"><span data-stu-id="e5fe1-171">The Initiator tooltip in Microsoft Edge 85</span></span>
:::image-end:::  

<span data-ttu-id="e5fe1-172">Chromium问题[#1069404][CR1069404]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-172">Chromium issue [#1069404][CR1069404]</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="e5fe1-173">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="e5fe1-173">Announcements from the Chromium project</span></span>  

<span data-ttu-id="e5fe1-174">以下各节宣布 85 Microsoft Edge开放源代码管理项目中提供的其他Chromium功能。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-174">The following sections announce additional features available in Microsoft Edge 85 that were contributed to the open source Chromium project.</span></span>  

### <a name="style-editing-for-css-in-js-frameworks"></a><span data-ttu-id="e5fe1-175">CSS-in-JS 框架的样式编辑</span><span class="sxs-lookup"><span data-stu-id="e5fe1-175">Style editing for CSS-in-JS frameworks</span></span>  

<span data-ttu-id="e5fe1-176">现在 **，"** 样式"窗格更好地支持使用 CSS 对象模型和 [CSSOM ][CsswgDraftsCssom] (API 创建的) 样式。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-176">The **Styles** pane now has better support for editing styles that were created with the [CSS Object Model (CSSOM)][CsswgDraftsCssom] APIs.</span></span>  <span data-ttu-id="e5fe1-177">许多 CSS-in-JS 框架和库在构建样式的底层使用 CSSOM API。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-177">Many CSS-in-JS frameworks and libraries use the CSSOM APIs under the hood to construct styles.</span></span>  

<span data-ttu-id="e5fe1-178">现在您可以使用可构造样式表编辑在 JavaScript [中添加的样式][WicgConstructStylesheet]。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-178">You are now able to edit styles added in JavaScript using [Constructable Stylesheets][WicgConstructStylesheet].</span></span>  <span data-ttu-id="e5fe1-179">可构造的样式表是使用 Shadow DOM 时创建和分发可重用样式 [的一种新方式][MdnShadowDom]。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-179">Constructable Stylesheets are a new way to create and distribute reusable styles when using [Shadow DOM][MdnShadowDom].</span></span>  

<span data-ttu-id="e5fe1-180">例如，使用 `h1` `CSSStyleSheet` \(CSSOM API\) 添加的样式以前不可编辑。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-180">For example, the `h1` styles added with `CSSStyleSheet` \(CSSOM APIs\) were not editable previously.</span></span>  <span data-ttu-id="e5fe1-181">样式现在在"样式"面板中 **可** 编辑。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-181">The styles are editable now in the **Styles** panel.</span></span>  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="将随 CSSStyleSheet 一起添加的 h1 样式的背景属性从粉色更改为浅色" lightbox="../../media/2020/06/css-in-js.msft.png":::
   <span data-ttu-id="e5fe1-183">将 `background` 随 一起 `h1` 添加的样式 `CSSStyleSheet` 的属性从 更改 `pink` 到 `lightblue` 。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-183">Changing the `background` property of the `h1` styles added with `CSSStyleSheet` from `pink` to `lightblue`.</span></span>
:::image-end:::  

<span data-ttu-id="e5fe1-184">通过使用 [CSS-in-JS][CodepenZoherghadyaliAbdgrpz]的示例试用此功能。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-184">Give this feature a try with a [sample that uses CSS-in-JS][CodepenZoherghadyaliAbdgrpz].</span></span>

<span data-ttu-id="e5fe1-185">Chromium问题[#946975][CR946975]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-185">Chromium issue [#946975][CR946975]</span></span>  

### <a name="lighthouse-6-in-the-lighthouse-panel"></a><span data-ttu-id="e5fe1-186">Lighthouse 面板中的"浅楼 6"</span><span class="sxs-lookup"><span data-stu-id="e5fe1-186">Lighthouse 6 in the Lighthouse panel</span></span>  

<span data-ttu-id="e5fe1-187">**"灯楼**"面板现在运行"Lighthouse 6"。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-187">The **Lighthouse** panel is now running Lighthouse 6.</span></span>  <span data-ttu-id="e5fe1-188">有关所有更改的完整列表，请导航到 [v6.0.0 发行说明][GithubGoogleChromeLighthouse600]。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-188">For a full list of all changes, navigate to [v6.0.0 release notes][GithubGoogleChromeLighthouse600].</span></span>  

<span data-ttu-id="e5fe1-189">Lighthouse 6.0 向报告引入了三个新指标：最大内容量 画图 \(LCP\) 、累积布局班次 \(CLS\) 和总阻止时间 \(TBT\) 。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-189">Lighthouse 6.0 introduces three new metrics to the report:  Largest Contentful Paint \(LCP\), Cumulative Layout Shift \(CLS\), and Total Blocking Time \(TBT\).</span></span>  

<span data-ttu-id="e5fe1-190">性能分数公式也进行了重新加权，以更好地反映用户的加载体验。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-190">The performance score formula has also been reweighted to better reflect the loading experience of the user.</span></span>  

<span data-ttu-id="e5fe1-191">Chromium问题[#772558][CR772558]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-191">Chromium issue [#772558][CR772558]</span></span>  

#### <a name="first-meaningful-paint-deprecation"></a><span data-ttu-id="e5fe1-192">First Meaningful 画图弃用</span><span class="sxs-lookup"><span data-stu-id="e5fe1-192">First Meaningful Paint deprecation</span></span>  

<span data-ttu-id="e5fe1-193">First Meaningful 画图 \(FMP\) is deprecated in Lighthouse 6.0.</span><span class="sxs-lookup"><span data-stu-id="e5fe1-193">First Meaningful Paint \(FMP\) is deprecated in Lighthouse 6.0.</span></span>  <span data-ttu-id="e5fe1-194">FMP 也从"性能" **面板中删除** 。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-194">FMP has also been removed from the **Performance** panel.</span></span>  <span data-ttu-id="e5fe1-195">**最大的 Contentful 画图**FMP 的建议替代项。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-195">**Largest Contentful Paint** is the recommended replacement for FMP.</span></span>  <!--For an explanation of why it was deprecated, navigate to [First Meaningful Paint][WebDevFirstMeaningfulPaint].  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

<span data-ttu-id="e5fe1-196">Chromium问题[#1096008][CR1096008]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-196">Chromium issue [#1096008][CR1096008]</span></span>  

### <a name="support-for-new-javascript-features"></a><span data-ttu-id="e5fe1-197">支持新的 JavaScript 功能</span><span class="sxs-lookup"><span data-stu-id="e5fe1-197">Support for new JavaScript features</span></span>  

<span data-ttu-id="e5fe1-198">DevTools 现在更好地支持一些最新的 JavaScript 语言功能。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-198">DevTools now has better support for some of the latest JavaScript language features.</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="e5fe1-199">[可选链接][V8DevOptionalChaining] 语法自动完成</span><span class="sxs-lookup"><span data-stu-id="e5fe1-199">[Optional chaining][V8DevOptionalChaining] syntax autocompletion</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e5fe1-200">控制台中的属性自动完成现在\*\*\*\* 支持可选的链接语法，例如，除了 和 之外， `name?.` 现在也可以 `name.` `name[` 正常工作。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-200">Property auto-completion in the **Console** now supports optional chaining syntax, for example,  `name?.` now works in addition to `name.` and `name[`.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="e5fe1-201">用于私有字段 [的语法突出显示][V8DevClassFieldsPrivate]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-201">Syntax highlighting for [private fields][V8DevClassFieldsPrivate]</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e5fe1-202">私有类字段现在在"源"面板中正确突出显示了语法 **并非常打印** 。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-202">private class fields are now properly syntax-highlighted and pretty-printed in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="e5fe1-203">Nullish [并集运算符的语法突出显示][V8DevNullishCoalescing]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-203">Syntax highlighting for [Nullish coalescing operator][V8DevNullishCoalescing]</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e5fe1-204">DevTools 现在可以在"源"面板中正确打印空的"并 **排"运算符** 。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-204">DevTools now properly pretty-prints the nullish coalescing operator in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="e5fe1-205">[][CR1083797] [][CR1073903]Chromium、#1073903、#1083214、#1083797 [][CR1083214]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-205">Chromium issues [#1073903][CR1073903], [#1083214][CR1083214], [#1083797][CR1083797]</span></span>  

### <a name="new-app-shortcut-warnings-in-the-manifest-pane"></a><span data-ttu-id="e5fe1-206">清单窗格中的新应用快捷方式警告</span><span class="sxs-lookup"><span data-stu-id="e5fe1-206">New app shortcut warnings in the Manifest pane</span></span>  

<span data-ttu-id="e5fe1-207">**应用快捷方式** 可帮助用户在 Web 应用中快速启动常见任务或推荐任务。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-207">**App shortcuts** help users quickly start common or recommended tasks within a web app.</span></span>  

<!--todo: add App shortcuts when section is live  -->  

<span data-ttu-id="e5fe1-208">" **清单** "窗格现在显示针对以下条件的警告。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-208">The **Manifest** pane now shows warnings for the following conditions.</span></span>  

* <span data-ttu-id="e5fe1-209">应用快捷方式图标小于 96x96 像素</span><span class="sxs-lookup"><span data-stu-id="e5fe1-209">The app shortcut icons are smaller than 96x96 pixels</span></span>  
* <span data-ttu-id="e5fe1-210">应用快捷方式图标和清单图标不是方形 \(，因为图标将被忽略\) </span><span class="sxs-lookup"><span data-stu-id="e5fe1-210">The app shortcut icons and manifest icons are not square \(since the icons are ignored\)</span></span>  

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="应用快捷方式警告" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   <span data-ttu-id="e5fe1-212">应用快捷方式警告</span><span class="sxs-lookup"><span data-stu-id="e5fe1-212">App shortcut warnings</span></span>  
:::image-end:::  

<span data-ttu-id="e5fe1-213">Chromium问题[#955497][CR955497]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-213">Chromium issue [#955497][CR955497]</span></span>  

### <a name="consistent-display-of-the-computed-pane"></a><span data-ttu-id="e5fe1-214">"计算"窗格的一致显示</span><span class="sxs-lookup"><span data-stu-id="e5fe1-214">Consistent display of the Computed pane</span></span>  

<span data-ttu-id="e5fe1-215">现在 **，"** 元素"工具\*\*\*\* 中的"计算"窗格在所有视口大小中一致地显示为窗格。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-215">The **Computed** pane in the **Elements** tool now displays consistently as a pane across all viewport sizes.</span></span>  <span data-ttu-id="e5fe1-216">以前 **，当**DevTools\*\*\*\* 视口的宽度较窄时，计算窗格合并在"样式"窗格中。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-216">Previously the **Computed** pane merged inside the **Styles** pane when the width of the DevTools viewport was narrow.</span></span>  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="即使 DevTools 较窄，计算窗格也一致显示为单独的窗格" lightbox="../../media/2020/06/computed-pane.msft.png":::
   <span data-ttu-id="e5fe1-218">即使\*\*\*\* DevTools 较窄，计算窗格也一致显示为单独的窗格。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-218">The **Computed** pane consistently displays as a separate pane even when the DevTools are narrow.</span></span>
:::image-end:::  

<span data-ttu-id="e5fe1-219">Chromium问题[#1073899][CR1073899]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-219">Chromium issue [#1073899][CR1073899]</span></span>  

### <a name="bytecode-offsets-for-webassembly-files"></a><span data-ttu-id="e5fe1-220">WebAssembly 文件的字节码偏移</span><span class="sxs-lookup"><span data-stu-id="e5fe1-220">Bytecode offsets for WebAssembly files</span></span>  

<span data-ttu-id="e5fe1-221">DevTools 现在使用字节码偏移来显示 Wasm 反汇编的行号。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-221">DevTools now uses bytecode offsets for displaying line numbers of Wasm disassembly.</span></span>  
<span data-ttu-id="e5fe1-222">行号使查看二进制数据更加清晰，并且与 Wasm 运行时引用位置的方式更加一致。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-222">The line numbers make it clearer that you are looking at binary data, and is more consistent with how the Wasm runtime references locations.</span></span>  

<span data-ttu-id="e5fe1-223">Chromium问题[#1071432][CR1071432]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-223">Chromium issue [#1071432][CR1071432]</span></span>  

### <a name="line-wise-copy-and-cut-in-sources-panel"></a><span data-ttu-id="e5fe1-224">在"源面板"中按照行进行复制和剪切</span><span class="sxs-lookup"><span data-stu-id="e5fe1-224">Line-wise copy and cut in Sources Panel</span></span>  

<span data-ttu-id="e5fe1-225">当在"源"面板编辑器中执行复制[][DevtoolsSourcesIndexUsingEditorPaneToViewEditFiles]或剪切操作时，DevTools 会复制或剪切当前内容行。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-225">When performing copy or cut with no selection in the [Sources panel editor][DevtoolsSourcesIndexUsingEditorPaneToViewEditFiles], DevTools copies or cuts the current line of content.</span></span>  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="当光标位于第 5 行的末尾时，从 DevTools pen.js复制整行并粘贴到Visual Studio Code" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   <span data-ttu-id="e5fe1-227">当光标位于第 5 行的末尾时，从 DevToolspen.js复制整行，并粘贴到 Visual Studio Code [。][VisualStudioCode] \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e5fe1-227">With the cursor at the end of Line 5, copying the whole line from **pen.js** in the DevTools and pasting in [Visual Studio Code][VisualStudioCode].</span></span>
:::image-end:::  

<span data-ttu-id="e5fe1-228">Chromium问题[#800028][CR800028]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-228">Chromium issue [#800028][CR800028]</span></span>

### <a name="console-settings-updates"></a><span data-ttu-id="e5fe1-229">控制台设置更新</span><span class="sxs-lookup"><span data-stu-id="e5fe1-229">Console Settings updates</span></span>  

#### <a name="ungroup-same-console-messages"></a><span data-ttu-id="e5fe1-230">取消同一控制台消息的组</span><span class="sxs-lookup"><span data-stu-id="e5fe1-230">Ungroup same console messages</span></span>  

<span data-ttu-id="e5fe1-231">控制台**控制台中的**组相似设置现在适用于重复消息。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-231">The **Group similar** toggle in Console Settings now applies to duplicate messages.</span></span>  <span data-ttu-id="e5fe1-232">以前，它只应用于类似的邮件。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-232">Previously it just applied to similar messages.</span></span>  

<span data-ttu-id="e5fe1-233">例如，以前，DevTools 未取消分组邮件，即使未取消选中" `hello` **组** 相似"。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-233">For example, previously, DevTools did not ungroup the `hello` messages even though **Group similar** is unchecked.</span></span>  <span data-ttu-id="e5fe1-234">现在， `hello` 邮件已取消组合。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-234">Now, the `hello` messages are ungrouped.</span></span>  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="取消选中类似组时，hello 消息将取消分组" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   <span data-ttu-id="e5fe1-236">取消 **选中"类似** 组"时 `hello` ，邮件将取消分组</span><span class="sxs-lookup"><span data-stu-id="e5fe1-236">When **Group similar** is unchecked, the `hello` messages are ungrouped</span></span>
:::image-end:::  

<span data-ttu-id="e5fe1-237">通过向控制台发送重复消息的示例试用 [此功能][CodepenZoherghadyaliZyrjgdJ]。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-237">Give this feature a try with a [sample that sends duplicate messages to the Console][CodepenZoherghadyaliZyrjgdJ].</span></span>  

<span data-ttu-id="e5fe1-238">Chromium问题[#1082963][CR1082963]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-238">Chromium issue [#1082963][CR1082963]</span></span>  

### <a name="persisting-selected-context-only-settings"></a><span data-ttu-id="e5fe1-239">持久化"仅选定上下文"设置</span><span class="sxs-lookup"><span data-stu-id="e5fe1-239">Persisting Selected context only settings</span></span>  

<span data-ttu-id="e5fe1-240">控制台**控制台中的"所选**上下文设置现在保留。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-240">The **Selected context only** settings in Console Settings is now persisted.</span></span>  <span data-ttu-id="e5fe1-241">以前，每次关闭并重新打开 DevTools 时，设置都会重置。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-241">Previously the settings were reset every time you closed and reopened DevTools.</span></span>  <span data-ttu-id="e5fe1-242">更改使设置行为与其他控制台选项设置一。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-242">The change makes the setting behavior consistent with other Console Settings options.</span></span>  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="选定的仅上下文设置" lightbox="../../media/2020/06/selected-context.msft.png":::
   <span data-ttu-id="e5fe1-244">**选定的仅上下文** 设置</span><span class="sxs-lookup"><span data-stu-id="e5fe1-244">**Selected context only** setting</span></span>  
:::image-end:::  

<span data-ttu-id="e5fe1-245">Chromium问题[#1055875][CR1055875]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-245">Chromium issue [#1055875][CR1055875]</span></span>  

### <a name="performance-panel-updates"></a><span data-ttu-id="e5fe1-246">性能面板更新</span><span class="sxs-lookup"><span data-stu-id="e5fe1-246">Performance panel updates</span></span>  

#### <a name="javascript-compilation-cache-information-in-performance-tool"></a><span data-ttu-id="e5fe1-247">性能工具中的 JavaScript **编译缓存** 信息</span><span class="sxs-lookup"><span data-stu-id="e5fe1-247">JavaScript compilation cache information in **Performance** tool</span></span>  

<span data-ttu-id="e5fe1-248">[JavaScript 编译缓存信息][V8DevCodeCaching] 现在始终显示在"性能 **"工具的** "摘要 **"面板** 中。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-248">[JavaScript compilation cache information][V8DevCodeCaching] is now always displayed in the **Summary** panel of the **Performance** tool.</span></span>  <span data-ttu-id="e5fe1-249">以前，如果未发生代码缓存，DevTools 不会显示与代码缓存相关的任何内容。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-249">Previously, DevTools did not show anything related to code caching if code caching did not happen.</span></span>  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="JavaScript 编译缓存信息" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   <span data-ttu-id="e5fe1-251">JavaScript 编译缓存信息</span><span class="sxs-lookup"><span data-stu-id="e5fe1-251">JavaScript compilation cache information</span></span>  
:::image-end:::  

<span data-ttu-id="e5fe1-252">Chromium问题[#912581][CR912581]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-252">Chromium issue [#912581][CR912581]</span></span>  

#### <a name="navigation-timing-alignment-in-the-performance-panel"></a><span data-ttu-id="e5fe1-253">"性能"面板中的导航计时对齐方式</span><span class="sxs-lookup"><span data-stu-id="e5fe1-253">Navigation timing alignment in the Performance panel</span></span>  

<span data-ttu-id="e5fe1-254">用于 **根据** 录制开始的时间在标尺中显示时间的性能面板。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-254">The **Performance** panel used to show times in the rulers based on when the recording started.</span></span>  <span data-ttu-id="e5fe1-255">用户导航的录制时间现已更改，其中 DevTools 现在显示相对于导航的标尺时间。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-255">The timing has now changed for recordings where the user navigates, where DevTools now shows ruler times relative to the navigation instead.</span></span>  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="在性能工具中对齐导航计时" lightbox="../../media/2020/06/nav-timing.msft.png":::
   <span data-ttu-id="e5fe1-257">在性能工具中 **对齐导航** 计时</span><span class="sxs-lookup"><span data-stu-id="e5fe1-257">Align navigation timing in **Performance** tool</span></span>  
:::image-end:::  

<span data-ttu-id="e5fe1-258">First 画图、First Contentful 画图 和 Largest Contentful 画图 事件的时间更新为相对于导航的开始，这意味着计时与 报告 `DOMContentLoaded` 的时间匹配 `PerformanceObserver` 。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-258">The times for `DOMContentLoaded`, First Paint, First Contentful Paint, and Largest Contentful Paint events are updated to be relative to the start of the navigation, which means the timing matches the timings reported by `PerformanceObserver`.</span></span>  

<span data-ttu-id="e5fe1-259">Chromium问题[#974550][CR974550]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-259">Chromium issue [#974550][CR974550]</span></span>  

### <a name="new-icons-for-breakpoints-conditional-breakpoints-and-logpoints"></a><span data-ttu-id="e5fe1-260">断点、条件断点和登录点的新图标</span><span class="sxs-lookup"><span data-stu-id="e5fe1-260">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="e5fe1-261">" **源** "面板具有针对断点、条件断点和日志的新设计。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-261">The **Sources** panel has new designs for breakpoints, conditional breakpoints, and logpoints.</span></span>  <span data-ttu-id="e5fe1-262">断点用红色圆圈表示，就像Visual Studio Code Visual Studio [][VisualStudioCode] [。][VisualStudio]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-262">Breakpoints are represented by a red circle, just like [Visual Studio Code][VisualStudioCode] and [Visual Studio][VisualStudio].</span></span>  <span data-ttu-id="e5fe1-263">添加图标以区分条件断点和日志点。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-263">Icons are added to differentiate conditional breakpoints and logpoints.</span></span>  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="断点" lightbox="../../media/2020/06/breakpoints.msft.png":::
   <span data-ttu-id="e5fe1-265">断点</span><span class="sxs-lookup"><span data-stu-id="e5fe1-265">Breakpoints</span></span>  
:::image-end:::  

<span data-ttu-id="e5fe1-266">Chromium 问题 [#1041830][CR1041830]</span><span class="sxs-lookup"><span data-stu-id="e5fe1-266">Chromium issue [#1041830][CR1041830]</span></span>  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="e5fe1-267">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="e5fe1-267">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="e5fe1-268">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-268">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="e5fe1-269">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-269">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="e5fe1-270">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="e5fe1-270">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsIndex]: ../../../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[DevtoolsCommandMenu]: ../../../command-menu.md "使用 Microsoft Edge 开发工具命令菜单运行命令"
[DevtoolsCustomizeIndexDrawer]: ../../../customize/index.md#drawer "设置 - 自定义 Microsoft Edge 开发工具 | Microsoft Docs"
[DevtoolsExperimentalFeaturesTurnOn]: ../../../experimental-features/index.md#turn-on-experimental-features "打开试验功能 - 试验功能 | Microsoft Docs"  
[DevtoolsIssues]: ../../../issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"
[DevtoolsSourcesIndexUsingEditorPaneToViewEditFiles]: ../../../sources/index.md#using-the-editor-pane-to-view-or-edit-files "使用编辑器窗格查看或编辑文件 - 源面板概述|Microsoft Docs"  
[DevtoolsNetworkIndexLogActivity]: ../../../network/index.md#log-network-activity "记录网络活动 - 在 DevTools Microsoft Edge中检查网络|Microsoft Docs"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "CSS-in-JS 框架样式编辑|CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "将重复消息发送到控制台|CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS 网格规划器示例 |CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"  

[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium Bug"  
[CR800028]: https://crbug.com/800028 "在 Chrome 更新后，开发人员工具编辑器中的重复行快捷方式|Chromium Bug"  
[CR912581]: https://crbug.com/912581 "在 DevTools/about：tracing |Chromium Bug"  
[CR946975]: https://crbug.com/946975 "DevTools 样式边栏不能与构造的样式表|Chromium Bug"  
[CR955497]: https://crbug.com/955497 "PBA 应用图标快捷方式菜单|Chromium Bug"  
[CR974550]: https://crbug.com/974550 "Perf 面板和 performanceObserver 组件之间的指标不匹配|Chromium Bug"  
[CR1041830]: https://crbug.com/1041830 "改进断点|Chromium Bug"  
[CR1055875]: https://crbug.com/1055875 "关闭并重新打开&quot;开发人员工具&quot;菜单后，&quot;所选上下文仅控制台&quot;设置的值不会|Chromium Bug"  
[CR1066579]: https://crbug.com/1066579 "DevTools： Show ServiceWorkers Fetch Timeline per request in Network panel |Chromium Bug"  
[CR1071432]: https://crbug.com/1071432 "Wasm Basic Developer Experience |Chromium Bug"  
[CR1073899]: https://crbug.com/1073899 "计算样式选项卡在响应模式下消失|Chromium Bug"  
[CR1073903]: https://crbug.com/1073903 "DevTools：语法突出显示对私有字段|Chromium Bug"  
[CR1082963]: https://crbug.com/1082963 "无法禁用控制台的组类似的邮件行为|Chromium Bug"  
[CR1083214]: https://crbug.com/1083214 "视点不支持可选链接|Chromium Bug"  
[CR1083797]: https://crbug.com/1083797 "为空值并成一体而损坏的|Chromium Bug"  
[CR1096008]: https://crbug.com/1096008 "删除 FMP |Chromium Bug"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table 工具|Chromium Bug"  
[CR1093687]: https://crbug.com/1093687 "创建用于创建和重播综合网络请求|Chromium Bug"  
[CR1070378]: https://crbug.com/1070378 "将 Webhint 集成到 DevTools |Chromium Bug"  
[CR1069404]: https://crbug.com/1069404 "[开发人员工具] 小部件弹出窗口太窄|Chromium Bug"  
[CR897944]: https://crbug.com/897944 "可拖动的开发人员工具|Chromium Bug"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v6.0.0 - GoogleChrome/lighthouse |GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新问题 - MicrosoftDocs/edge-developer"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "使用卷影 DOM |MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge 预览频道"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"
[VisualStudioCode]: https://code.visualstudio.com/ "Visual Studio 代码"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS 对象模型 (CSSOM) |W3C CSS 工作组编辑器草稿"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "私有类字段 - 公共和私有类|V8.开发"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "适用于 JavaScript 开发人员的代码|V8.开发"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "Nullish 将|V8.开发"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "可选链接|V8.开发"  

[WebhintMain]: https://webhint.io "webhint"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "可构造的样式表|Web Incubator CG"

<!--[WebDevLighthouseWhatsNew60]: https://web.dev/lighthouse-whats-new-6.0 "What's New in Lighthouse 6.0 | Web.Dev"  -->  
<!--[WebDevVitalsCoreWeb]: https://web.dev/vitals#core-web-vitals "Core Web Vitals - Web Vitals | Web.Dev"  -->  
<!--[WebdevAppShortcuts]: https://alphabet-dev/app-shortcuts "Get things done quickly with app shortcuts | alphabet-dev"  -->  
<!--[WebdevCls]: https://alphabet-dev/cls "Cumulative Layout Shift (CLS) | alphabet-dev"  -->  
<!--[WebdevControlFocus]: https://alphabet-dev/control-focus-with-tabindex "Control focus with tabindex | alphabet-dev"  -->  
<!--[WebdevMeasureSpeedLabField]: https://alphabet-dev/how-to-measure-speed#lab-data-vs-field-data "Lab data vs Field data - How to measure speed? | alphabet-dev"  -->  
<!--[WebdevLabelsText]: https://alphabet-dev/labels-and-text-alternatives "Labels and text alternatives | alphabet-dev"  -->  
<!--[WebdevTbt]: https://alphabet-dev/tbt "Total Blocking Time (TBT) | alphabet-dev"  -->  
<!--[WebFundamentalComponentsShadowdom]: /web/fundamentals/web-components/shadowdom  -->  
<!--[WebDevLcp]: https://web.dev/lcp "Largest Contentful Paint (LCP) | Web.Dev"  -->  
<!--[WebDevFirstMeaningfulPaint]: https://web.dev/first-meaningful-paint "First Meaningful Paint | Web.Dev"  -->  
<!--[WhatsNew201902ConstructableStylesheets]: ../../2019/02/constructable-stylesheets.md "Constructable Stylesheets: seamless reusable styles | Microsoft Docs"  -->  

[TheWebWeWant]: https://webwewant.fyi/ "我们想要的网络"  

> [!NOTE]
> <span data-ttu-id="e5fe1-319">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-319">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e5fe1-320">原始页面位于 [此处](https://developer.chrome.com/blog/new-in-devtools-85)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-320">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-85) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="e5fe1-322">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="e5fe1-322">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
