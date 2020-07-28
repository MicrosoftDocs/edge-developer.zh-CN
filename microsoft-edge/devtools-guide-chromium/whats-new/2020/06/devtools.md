---
title: DevTools 中的新增功能（Microsoft Edge 85）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 7b0193d25fb1d081e5746ec1271ca7b9f4e60c23
ms.sourcegitcommit: ad5eb43172280974b8c063867c2097f7c5c0e77d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/27/2020
ms.locfileid: "10898247"
---
# <span data-ttu-id="f843d-103">DevTools 中的新增功能（Microsoft Edge 85）</span><span class="sxs-lookup"><span data-stu-id="f843d-103">What's New In DevTools (Microsoft Edge 85)</span></span>  

## <span data-ttu-id="f843d-104">Microsoft Edge DevTools 团队的公告</span><span class="sxs-lookup"><span data-stu-id="f843d-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="f843d-105">以下部分是您可能已错过的 Microsoft Edge DevTools 团队的公告列表。</span><span class="sxs-lookup"><span data-stu-id="f843d-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="f843d-106">请参阅公告以尝试 DevTools 中的新功能，与代码扩展，等等。</span><span class="sxs-lookup"><span data-stu-id="f843d-106">See the announcements to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="f843d-107">若要随时了解开发人员工具中的所有最新功能和最新功能，请下载[Microsoft edge 预览频道][MicrosoftEdgePreviewChannels]并[关注 Twitter 上的 microsoft edge DevTools 团队][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="f843d-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow the Microsoft Edge DevTools team on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="f843d-108">CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="f843d-108">CSS grid debugging features</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   <span data-ttu-id="f843d-110">实验性功能</span><span class="sxs-lookup"><span data-stu-id="f843d-110">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="f843d-111">Microsoft Edge DevTools 团队正与 Chrome DevTools 团队和 Chromium 社区协作，将新的 CSS 网格调试功能添加到 DevTools。</span><span class="sxs-lookup"><span data-stu-id="f843d-111">The Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new CSS grid debugging features to DevTools.</span></span>  <span data-ttu-id="f843d-112">现在，你可以将网格线编号、网格间距和扩展网格线显示为页面覆盖。</span><span class="sxs-lookup"><span data-stu-id="f843d-112">You are now able to display grid line numbers, grid gaps, and extended grid lines as an on-page overlay.</span></span>  <span data-ttu-id="f843d-113">此外，即将推出对网格工具的更多改进。</span><span class="sxs-lookup"><span data-stu-id="f843d-113">Plus, more improvements to the grid tools are coming soon.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="CSS 网格调试功能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   <span data-ttu-id="f843d-115">CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="f843d-115">CSS grid debugging features</span></span>
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="f843d-116">若要启用实验，请参阅启用[实验功能][DevtoolsExperimentalFeaturesTurnOn]，然后选中 "**启用新 CSS 网格调试功能**" 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="f843d-116">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable new CSS Grid debugging features**.</span></span>  
> 
> <span data-ttu-id="f843d-117">若要试用有关示例的实验，请参阅[CSS 网格 planner 示例][CodepenRachelweilYzwBzKM]。</span><span class="sxs-lookup"><span data-stu-id="f843d-117">To try out the experiment with a sample, see [CSS Grid planner example][CodepenRachelweilYzwBzKM].</span></span>  

<span data-ttu-id="f843d-118">Chromium 问题[#1047356][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="f843d-118">Chromium issue [#1047356][CR1047356]</span></span>  

### <span data-ttu-id="f843d-119">通过网络控制台编辑和重播请求</span><span class="sxs-lookup"><span data-stu-id="f843d-119">Edit and Replay requests with the Network Console</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   <span data-ttu-id="f843d-121">实验性功能</span><span class="sxs-lookup"><span data-stu-id="f843d-121">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="f843d-122">现在，你可以使用**网络控制台**在[网络日志][DevtoolsNetworkIndexLogActivity]中使用 "**编辑和重播**" 请求。</span><span class="sxs-lookup"><span data-stu-id="f843d-122">You are now able to use **Edit and Replay** on requests in the [Network Log][DevtoolsNetworkIndexLogActivity] using the **Network Console**.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="使用网络控制台编辑和重播 NetworkLog 中的请求" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   <span data-ttu-id="f843d-124">使用**网络控制台**编辑和重播[NetworkLog][DevtoolsNetworkIndexLogActivity]中的请求</span><span class="sxs-lookup"><span data-stu-id="f843d-124">Edit and Replay a request in the [NetworkLog][DevtoolsNetworkIndexLogActivity] with the **Network Console**</span></span>  
:::image-end:::  

<span data-ttu-id="f843d-125">新的面板，**网络控制台**将在[DevTools 抽屉][DevtoolsCustomizeIndexDrawer]中打开，并自动填充 HTTP 请求的信息。</span><span class="sxs-lookup"><span data-stu-id="f843d-125">A new panel, the **Network Console** opens in the [DevTools Drawer][DevtoolsCustomizeIndexDrawer] and automatically populates with information for the HTTP request.</span></span>  <span data-ttu-id="f843d-126">若要查看从服务器返回的响应，请编辑请求 \ （如果需要 \），然后选择 "**发送**"。</span><span class="sxs-lookup"><span data-stu-id="f843d-126">To see the response returned from the server, edit the request \(if needed\) and select **Send**.</span></span>  

<span data-ttu-id="f843d-127">您也可以使用**网络控制台**直接从 DevTools 创建和发送 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="f843d-127">You may also use the **Network Console** to create and send HTTP requests directly from the DevTools.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text="网络控制台面板" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   <span data-ttu-id="f843d-129">**网络控制台**面板</span><span class="sxs-lookup"><span data-stu-id="f843d-129">The **Network Console** panel</span></span>  
:::image-end:::  

> [!TIP]
> <span data-ttu-id="f843d-130">若要在主 DevTools 面板（而不是[抽屉][DevtoolsCustomizeIndexDrawer]）中查看**网络控制台**，请参阅[在面板之间移动工具](#move-tools-between-panels)。</span><span class="sxs-lookup"><span data-stu-id="f843d-130">To see **Network Console** in the main \(top\) panel instead of the [DevTools Drawer][DevtoolsCustomizeIndexDrawer], see [moving tools between panels](#move-tools-between-panels).</span></span>  

> [!NOTE]
> <span data-ttu-id="f843d-131">若要启用实验，请参阅启用[实验功能][DevtoolsExperimentalFeaturesTurnOn]和选择**启用网络控制台**旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="f843d-131">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable Network Console**.</span></span>  
> 
> <span data-ttu-id="f843d-132">打开[网络日志][DevtoolsNetworkIndexLogActivity]，打开上下文菜单 \ （右键单击 \），然后选择 "**编辑并重播**"。</span><span class="sxs-lookup"><span data-stu-id="f843d-132">Open the [Network Log][DevtoolsNetworkIndexLogActivity], open the contextual menu \(right-click\), and select **Edit and Replay**.</span></span>  

<span data-ttu-id="f843d-133">Chromium 问题[#1093687][CR1093687]</span><span class="sxs-lookup"><span data-stu-id="f843d-133">Chromium issue [#1093687][CR1093687]</span></span>  

### <span data-ttu-id="f843d-134">"计时" 选项卡中的服务工作人员 respondWith 事件</span><span class="sxs-lookup"><span data-stu-id="f843d-134">Service worker respondWith events in the Timing tab</span></span>  

<span data-ttu-id="f843d-135">"**网络**" 面板的 "**计时**" 选项卡现在包括 `respondWith` 服务辅助事件。</span><span class="sxs-lookup"><span data-stu-id="f843d-135">The **Timing** tab of the **Network** panel now includes `respondWith` service worker events.</span></span>  <span data-ttu-id="f843d-136">`respondWith`服务工作者事件显示在 `fetch` `respondWith` `fetch` 结算处理程序承诺的时间开始运行服务辅助事件处理程序之前的时间段内的持续时间。</span><span class="sxs-lookup"><span data-stu-id="f843d-136">The `respondWith` service worker event shows the duration from the time immediately before the service worker `fetch` event handler starts running to the time when the `respondWith` promise of the `fetch` handler is settled.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text=""网络" 面板的 "计时" 选项卡中的 respondWith 服务辅助事件" lightbox="../../media/2020/06/timing-tab.msft.png":::
   <span data-ttu-id="f843d-138">" `respondWith` **网络**" 面板的 "**计时**" 选项卡中的服务工作人员事件</span><span class="sxs-lookup"><span data-stu-id="f843d-138">The `respondWith` service worker event in the **Timing** tab of the **Network** panel</span></span>  
:::image-end:::  

<span data-ttu-id="f843d-139">展开 "**已收到答复**"，以查看来自 `fetch` 、和的响应的其他信息 `CacheStorageCacheName` `serviceWorkerResponseSource` `ResponseTime` 。</span><span class="sxs-lookup"><span data-stu-id="f843d-139">Expand **Response received** to see additional information from the `fetch` response like `CacheStorageCacheName`, `serviceWorkerResponseSource`, and `ResponseTime`.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="展开 "已收到答复"，以查看来自提取响应的其他信息" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   <span data-ttu-id="f843d-141">展开 "**已收到答复**" 以查看来自响应的其他信息 `fetch`</span><span class="sxs-lookup"><span data-stu-id="f843d-141">Expand **Response received** to see additional information from the `fetch` response</span></span>  
:::image-end:::  

<span data-ttu-id="f843d-142">Chromium 问题[#1066579][CR1066579]</span><span class="sxs-lookup"><span data-stu-id="f843d-142">Chromium issue [#1066579][CR1066579]</span></span>  

### <span data-ttu-id="f843d-143">"问题" 面板中的 webhint 反馈</span><span class="sxs-lookup"><span data-stu-id="f843d-143">webhint feedback in the Issues panel</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   <span data-ttu-id="f843d-145">实验性功能</span><span class="sxs-lookup"><span data-stu-id="f843d-145">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="f843d-146">[webhint][WebhintMain]是一种开放源工具，可提供有关网站的辅助功能、跨浏览器兼容性、安全性、性能、PWAs 和其他常见 web 开发问题的实时反馈。</span><span class="sxs-lookup"><span data-stu-id="f843d-146">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="f843d-147">现在，你可以在 "[问题][DevtoolsIssues]" 面板中看到 webhint 反馈。</span><span class="sxs-lookup"><span data-stu-id="f843d-147">You are now able to see webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text=""问题" 面板中的 webhint 反馈" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   <span data-ttu-id="f843d-149">"问题" 面板中的 webhint 反馈</span><span class="sxs-lookup"><span data-stu-id="f843d-149">webhint feedback in the Issues panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="f843d-150">若要启用实验，请参阅启用[实验功能][DevtoolsExperimentalFeaturesTurnOn]和选择**启用 webhint**旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="f843d-150">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable webhint**.</span></span>  
> 
> <span data-ttu-id="f843d-151">打开 "[问题][DevtoolsIssues]" 面板，查看来自 webhint 的反馈。</span><span class="sxs-lookup"><span data-stu-id="f843d-151">Open the [Issues][DevtoolsIssues] panel to see feedback from webhint.</span></span>  

<span data-ttu-id="f843d-152">Chromium 问题[#1070378][CR1070378]</span><span class="sxs-lookup"><span data-stu-id="f843d-152">Chromium issue [#1070378][CR1070378]</span></span>  

### <span data-ttu-id="f843d-153">在面板之间移动工具</span><span class="sxs-lookup"><span data-stu-id="f843d-153">Move tools between panels</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   <span data-ttu-id="f843d-155">实验性功能</span><span class="sxs-lookup"><span data-stu-id="f843d-155">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="f843d-156">通常，**元素**和**网络**之类的工具只能在 DevTools 的 main \ （top \）面板中打开。</span><span class="sxs-lookup"><span data-stu-id="f843d-156">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="f843d-157">同样， **3D 视图**和**问题**之类的工具可能仅在 DevTools 的抽屉 \ （底部 \）面板中打开。</span><span class="sxs-lookup"><span data-stu-id="f843d-157">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="f843d-158">现在，你可以通过在顶部面板和底部面板之间移动工具来自定义 DevTools 布局。</span><span class="sxs-lookup"><span data-stu-id="f843d-158">You are now able to customize your DevTools layout by moving tools between the top and bottom panels.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="在面板之间移动选项卡" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   <span data-ttu-id="f843d-160">在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="f843d-160">Moving tabs between panels</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="f843d-161">若要启用实验，请参阅启用[实验功能][DevtoolsExperimentalFeaturesTurnOn]，然后选中 "**启用支持" 以在面板之间移动选项卡**旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="f843d-161">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable support to move tabs between panels**.</span></span>  

<span data-ttu-id="f843d-162">Chromium 问题[#897944][CR897944]</span><span class="sxs-lookup"><span data-stu-id="f843d-162">Chromium issue [#897944][CR897944]</span></span>  

### <span data-ttu-id="f843d-163">改进了 "网络" 面板中的发起程序工具提示</span><span class="sxs-lookup"><span data-stu-id="f843d-163">Improved Initiator tooltip in the Network panel</span></span>  

<span data-ttu-id="f843d-164">在 Microsoft Edge 83 和84中，"发起人" 列的工具提示，其中显示了在使用水平滚动条显示的[网络日志][DevtoolsNetworkIndexLogActivity]中的资源请求原因。</span><span class="sxs-lookup"><span data-stu-id="f843d-164">In Microsoft Edge 83 and 84, tooltips for the Initiator column, which shows the cause of the resource request, in the [Network Log][DevtoolsNetworkIndexLogActivity] displayed with a horizontal scrollbar.</span></span>  <span data-ttu-id="f843d-165">你只能通过在工具提示中水平滚动来查看启动请求的调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="f843d-165">You were only able to see the call stack that initiated the request by scrolling horizontally in the tooltip.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="Microsoft Edge 84 中的发起程序工具提示" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   <span data-ttu-id="f843d-167">Microsoft Edge 84 中的发起程序工具提示</span><span class="sxs-lookup"><span data-stu-id="f843d-167">The Initiator tooltip in Microsoft Edge 84</span></span>  
:::image-end:::  

<span data-ttu-id="f843d-168">从 Microsoft Edge 85 开始，您现在可以在工具提示中看到启动器调用堆栈，而无需水平滚动。</span><span class="sxs-lookup"><span data-stu-id="f843d-168">Starting with Microsoft Edge 85, you are now able to see the Initiator call stack in the tooltip without scrolling horizontally.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="Microsoft Edge 85 中的发起程序工具提示" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   <span data-ttu-id="f843d-170">Microsoft Edge 85 中的发起程序工具提示</span><span class="sxs-lookup"><span data-stu-id="f843d-170">The Initiator tooltip in Microsoft Edge 85</span></span>
:::image-end:::  

<span data-ttu-id="f843d-171">Chromium 问题[#1069404][CR1069404]</span><span class="sxs-lookup"><span data-stu-id="f843d-171">Chromium issue [#1069404][CR1069404]</span></span>  

## <span data-ttu-id="f843d-172">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="f843d-172">Announcements from the Chromium project</span></span>  

<span data-ttu-id="f843d-173">以下各节宣布了在 Microsoft Edge 85 中提供的其他功能，这些功能由开放的源 Chromium 项目所参与。</span><span class="sxs-lookup"><span data-stu-id="f843d-173">The following sections announce additional features available in Microsoft Edge 85 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="f843d-174">对 .JS 中的 CSS 框架进行样式编辑</span><span class="sxs-lookup"><span data-stu-id="f843d-174">Style editing for CSS-in-JS frameworks</span></span>  

<span data-ttu-id="f843d-175">现在，"**样式**" 窗格对通过[CSS 对象模型（CSSOM）][CsswgDraftsCssom] api 创建的样式有更好的支持。</span><span class="sxs-lookup"><span data-stu-id="f843d-175">The **Styles** pane now has better support for editing styles that were created with the [CSS Object Model (CSSOM)][CsswgDraftsCssom] APIs.</span></span>  <span data-ttu-id="f843d-176">许多 CSS 中的 CSS 框架和库使用 CSSOM Api 来构建样式。</span><span class="sxs-lookup"><span data-stu-id="f843d-176">Many CSS-in-JS frameworks and libraries use the CSSOM APIs under the hood to construct styles.</span></span>  

<span data-ttu-id="f843d-177">现在，你可以使用[Constructable 样式表][WicgConstructStylesheet]编辑在 JavaScript 中添加的样式。</span><span class="sxs-lookup"><span data-stu-id="f843d-177">You are now able to edit styles added in JavaScript using [Constructable Stylesheets][WicgConstructStylesheet].</span></span>  <span data-ttu-id="f843d-178">Constructable 样式表是在使用[影子 DOM][MdnShadowDom]时创建和分发可重用样式的新方法。</span><span class="sxs-lookup"><span data-stu-id="f843d-178">Constructable Stylesheets are a new way to create and distribute reusable styles when using [Shadow DOM][MdnShadowDom].</span></span>  

<span data-ttu-id="f843d-179">例如， `h1` 通过 `CSSStyleSheet` \ （CSSOM api \）添加的样式先前不可编辑。</span><span class="sxs-lookup"><span data-stu-id="f843d-179">For example, the `h1` styles added with `CSSStyleSheet` \(CSSOM APIs\) were not editable previously.</span></span>  <span data-ttu-id="f843d-180">样式现在可在 "**样式**" 窗格中编辑。</span><span class="sxs-lookup"><span data-stu-id="f843d-180">The styles are editable now in the **Styles** pane.</span></span>  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="将 CSSStyleSheet 中添加的 h1 样式的背景属性从粉红色更改为 lightblue" lightbox="../../media/2020/06/css-in-js.msft.png":::
   <span data-ttu-id="f843d-182">`background` `h1` 将添加的样式的属性更改 `CSSStyleSheet` `pink` 为 `lightblue` 。</span><span class="sxs-lookup"><span data-stu-id="f843d-182">Changing the `background` property of the `h1` styles added with `CSSStyleSheet` from `pink` to `lightblue`.</span></span>
:::image-end:::  

<span data-ttu-id="f843d-183">为此功能提供一个[使用在 .js 中使用 CSS 的示例][CodepenZoherghadyaliAbdgrpz]。</span><span class="sxs-lookup"><span data-stu-id="f843d-183">Give this feature a try with a [sample that uses CSS-in-JS][CodepenZoherghadyaliAbdgrpz].</span></span>

<span data-ttu-id="f843d-184">Chromium 问题[#946975][CR946975]</span><span class="sxs-lookup"><span data-stu-id="f843d-184">Chromium issue [#946975][CR946975]</span></span>  

### <span data-ttu-id="f843d-185">Lighthouse 面板中的 Lighthouse 6</span><span class="sxs-lookup"><span data-stu-id="f843d-185">Lighthouse 6 in the Lighthouse panel</span></span>  

<span data-ttu-id="f843d-186">**Lighthouse**面板现在正在运行 Lighthouse 6。</span><span class="sxs-lookup"><span data-stu-id="f843d-186">The **Lighthouse** panel is now running Lighthouse 6.</span></span>  <span data-ttu-id="f843d-187">有关所有更改的完整列表，请参阅[v 6.0.0 发行说明][GithubGoogleChromeLighthouse600]。</span><span class="sxs-lookup"><span data-stu-id="f843d-187">For a full list of all changes, see [v6.0.0 release notes][GithubGoogleChromeLighthouse600].</span></span>  

<span data-ttu-id="f843d-188">Lighthouse 6.0 将三个新度量值引入到报表：最大的 Contentful 油漆 \ （LCP \）、累积布局班次 \ （CLS \）和总阻塞时间 \ （TBT \）。</span><span class="sxs-lookup"><span data-stu-id="f843d-188">Lighthouse 6.0 introduces three new metrics to the report:  Largest Contentful Paint \(LCP\), Cumulative Layout Shift \(CLS\), and Total Blocking Time \(TBT\).</span></span>  

<span data-ttu-id="f843d-189">性能分数公式也已 reweighted，以更好地反映用户的加载体验。</span><span class="sxs-lookup"><span data-stu-id="f843d-189">The performance score formula has also been reweighted to better reflect the loading experience of the user.</span></span>  

<span data-ttu-id="f843d-190">Chromium 问题[#772558][CR772558]</span><span class="sxs-lookup"><span data-stu-id="f843d-190">Chromium issue [#772558][CR772558]</span></span>  

#### <span data-ttu-id="f843d-191">第一个有意义的画图弃用</span><span class="sxs-lookup"><span data-stu-id="f843d-191">First Meaningful Paint deprecation</span></span>  

<span data-ttu-id="f843d-192">第一个有意义的油漆 \ （FMP \）在 Lighthouse 6.0 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="f843d-192">First Meaningful Paint \(FMP\) is deprecated in Lighthouse 6.0.</span></span>  <span data-ttu-id="f843d-193">FMP 也已从 "**性能**" 面板中删除。</span><span class="sxs-lookup"><span data-stu-id="f843d-193">FMP has also been removed from the **Performance** panel.</span></span>  <span data-ttu-id="f843d-194">**最大 Contentful 画图**是推荐的 FMP 替换。</span><span class="sxs-lookup"><span data-stu-id="f843d-194">**Largest Contentful Paint** is the recommended replacement for FMP.</span></span>  <!--See [First Meaningful Paint][WebDevFirstMeaningfulPaint] for an explanation of why it was deprecated.  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

<span data-ttu-id="f843d-195">Chromium 问题[#1096008][CR1096008]</span><span class="sxs-lookup"><span data-stu-id="f843d-195">Chromium issue [#1096008][CR1096008]</span></span>  

### <span data-ttu-id="f843d-196">对新的 JavaScript 功能的支持</span><span class="sxs-lookup"><span data-stu-id="f843d-196">Support for new JavaScript features</span></span>  

<span data-ttu-id="f843d-197">DevTools 现在对某些最新的 JavaScript 语言功能提供了更好的支持。</span><span class="sxs-lookup"><span data-stu-id="f843d-197">DevTools now has better support for some of the latest JavaScript language features.</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="f843d-198">[可选的链接][V8DevOptionalChaining]语法自动完成</span><span class="sxs-lookup"><span data-stu-id="f843d-198">[Optional chaining][V8DevOptionalChaining] syntax autocompletion</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="f843d-199">现在，**控制台**中的属性自动完成支持可选的链接语法，例如， `name?.` 除了 `name.` 和 `name[` 。</span><span class="sxs-lookup"><span data-stu-id="f843d-199">Property auto-completion in the **Console** now supports optional chaining syntax, for example,  `name?.` now works in addition to `name.` and `name[`.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="f843d-200">[私有字段][V8DevClassFieldsPrivate]的语法突出显示</span><span class="sxs-lookup"><span data-stu-id="f843d-200">Syntax highlighting for [private fields][V8DevClassFieldsPrivate]</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="f843d-201">在 "**源**" 面板中，"专用类" 字段现已正确语法突出显示和打印。</span><span class="sxs-lookup"><span data-stu-id="f843d-201">private class fields are now properly syntax-highlighted and pretty-printed in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="f843d-202">[Nullish 合并运算符][V8DevNullishCoalescing]的语法突出显示</span><span class="sxs-lookup"><span data-stu-id="f843d-202">Syntax highlighting for [Nullish coalescing operator][V8DevNullishCoalescing]</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="f843d-203">DevTools 现已正确打印 "**源**" 面板中的 nullish 合并运算符。</span><span class="sxs-lookup"><span data-stu-id="f843d-203">DevTools now properly pretty-prints the nullish coalescing operator in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="f843d-204">Chromium 问题[#1073903][CR1073903]、 [#1083214][CR1083214] [#1083797][CR1083797]</span><span class="sxs-lookup"><span data-stu-id="f843d-204">Chromium issues [#1073903][CR1073903], [#1083214][CR1083214], [#1083797][CR1083797]</span></span>  

### <span data-ttu-id="f843d-205">清单窗格中的新应用程序快捷方式警告</span><span class="sxs-lookup"><span data-stu-id="f843d-205">New app shortcut warnings in the Manifest pane</span></span>  

<span data-ttu-id="f843d-206">**应用快捷方式**可帮助用户在 web 应用中快速启动常见或建议的任务。</span><span class="sxs-lookup"><span data-stu-id="f843d-206">**App shortcuts** help users quickly start common or recommended tasks within a web app.</span></span>  

<!--todo: add App shortcuts when section is live  -->  

<span data-ttu-id="f843d-207">**清单**窗格现在显示以下条件的警告。</span><span class="sxs-lookup"><span data-stu-id="f843d-207">The **Manifest** pane now shows warnings for the following conditions.</span></span>  

* <span data-ttu-id="f843d-208">应用快捷方式图标小于96x96 像素</span><span class="sxs-lookup"><span data-stu-id="f843d-208">The app shortcut icons are smaller than 96x96 pixels</span></span>  
* <span data-ttu-id="f843d-209">应用快捷方式图标和清单图标不是方形 \ （因为图标被忽略 \）</span><span class="sxs-lookup"><span data-stu-id="f843d-209">The app shortcut icons and manifest icons are not square \(since the icons are ignored\)</span></span>  

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="应用快捷方式警告" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   <span data-ttu-id="f843d-211">应用快捷方式警告</span><span class="sxs-lookup"><span data-stu-id="f843d-211">App shortcut warnings</span></span>  
:::image-end:::  

<span data-ttu-id="f843d-212">Chromium 问题[#955497][CR955497]</span><span class="sxs-lookup"><span data-stu-id="f843d-212">Chromium issue [#955497][CR955497]</span></span>  

### <span data-ttu-id="f843d-213">显示计算窗格的一致显示</span><span class="sxs-lookup"><span data-stu-id="f843d-213">Consistent display of the Computed pane</span></span>  

<span data-ttu-id="f843d-214">"**元素**" 面板中的**计算**窗格现在在所有视区大小中都以窗格的形式一致显示。</span><span class="sxs-lookup"><span data-stu-id="f843d-214">The **Computed** pane in the **Elements** panel now displays consistently as a pane across all viewport sizes.</span></span>  <span data-ttu-id="f843d-215">以前，当 DevTools 视口的宽度很窄时，将在 "**样式**" 窗格内合并**计算**窗格。</span><span class="sxs-lookup"><span data-stu-id="f843d-215">Previously the **Computed** pane merged inside the **Styles** pane when the width of the DevTools viewport was narrow.</span></span>  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="即使 DevTools 较窄，计算窗格也会始终显示为单独的窗格" lightbox="../../media/2020/06/computed-pane.msft.png":::
   <span data-ttu-id="f843d-217">即使 DevTools 较窄，**计算**窗格也会始终显示为单独的窗格。</span><span class="sxs-lookup"><span data-stu-id="f843d-217">The **Computed** pane consistently displays as a separate pane even when the DevTools are narrow.</span></span>
:::image-end:::  

<span data-ttu-id="f843d-218">Chromium 问题[#1073899][CR1073899]</span><span class="sxs-lookup"><span data-stu-id="f843d-218">Chromium issue [#1073899][CR1073899]</span></span>  

### <span data-ttu-id="f843d-219">WebAssembly 文件的字节码偏移量</span><span class="sxs-lookup"><span data-stu-id="f843d-219">Bytecode offsets for WebAssembly files</span></span>  

<span data-ttu-id="f843d-220">DevTools 现在使用字节码偏移来显示 Wasm 反汇编的行号。</span><span class="sxs-lookup"><span data-stu-id="f843d-220">DevTools now uses bytecode offsets for displaying line numbers of Wasm disassembly.</span></span>  
<span data-ttu-id="f843d-221">行号使你查看二进制数据更加清晰，并且更符合 Wasm 运行时引用位置的方式。</span><span class="sxs-lookup"><span data-stu-id="f843d-221">The line numbers make it clearer that you are looking at binary data, and is more consistent with how the Wasm runtime references locations.</span></span>  

<span data-ttu-id="f843d-222">Chromium 问题[#1071432][CR1071432]</span><span class="sxs-lookup"><span data-stu-id="f843d-222">Chromium issue [#1071432][CR1071432]</span></span>  

### <span data-ttu-id="f843d-223">"源" 面板中的行式复制和剪切</span><span class="sxs-lookup"><span data-stu-id="f843d-223">Line-wise copy and cut in Sources Panel</span></span>  

<span data-ttu-id="f843d-224">在 "[源" 面板编辑器][DevtoolsSourcesEditCssJavascript]中执行 "无选择时复制" 或 "剪切" 时，DevTools 将复制或剪切当前内容行。</span><span class="sxs-lookup"><span data-stu-id="f843d-224">When performing copy or cut with no selection in the [Sources panel editor][DevtoolsSourcesEditCssJavascript], DevTools copies or cuts the current line of content.</span></span>  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="将光标放在第5行的末尾，从 DevTools 中的 pen.js 复制整行，并在 VS 代码中粘贴" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   <span data-ttu-id="f843d-226">将光标放在第5行的末尾，将 DevTools 中的整**pen.js**行复制到 "" 和 "在[VS 代码][VSCode]中粘贴"。</span><span class="sxs-lookup"><span data-stu-id="f843d-226">With the cursor at the end of Line 5, copying the whole line from **pen.js** in the DevTools and pasting in [VS Code][VSCode].</span></span>
:::image-end:::  

<span data-ttu-id="f843d-227">Chromium 问题[#800028][CR800028]</span><span class="sxs-lookup"><span data-stu-id="f843d-227">Chromium issue [#800028][CR800028]</span></span>

### <span data-ttu-id="f843d-228">控制台设置更新</span><span class="sxs-lookup"><span data-stu-id="f843d-228">Console Settings updates</span></span>  

#### <span data-ttu-id="f843d-229">取消组合相同的控制台消息</span><span class="sxs-lookup"><span data-stu-id="f843d-229">Ungroup same console messages</span></span>  

<span data-ttu-id="f843d-230">在控制台设置中，**组类似**的切换现在适用于重复邮件。</span><span class="sxs-lookup"><span data-stu-id="f843d-230">The **Group similar** toggle in Console Settings now applies to duplicate messages.</span></span>  <span data-ttu-id="f843d-231">以前它刚刚应用到类似的消息。</span><span class="sxs-lookup"><span data-stu-id="f843d-231">Previously it just applied to similar messages.</span></span>  

<span data-ttu-id="f843d-232">例如，以前，DevTools `hello` 即使未选中 "**组相似**"，也不会对邮件取消分组。</span><span class="sxs-lookup"><span data-stu-id="f843d-232">For example, previously, DevTools did not ungroup the `hello` messages even though **Group similar** is unchecked.</span></span>  <span data-ttu-id="f843d-233">现在， `hello` 邮件已取消分组。</span><span class="sxs-lookup"><span data-stu-id="f843d-233">Now, the `hello` messages are ungrouped.</span></span>  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="取消选中 "组相似" 时，将取消分组 hello 邮件" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   <span data-ttu-id="f843d-235">取消选中 "**组相似**" 时， `hello` 邮件将取消组合。</span><span class="sxs-lookup"><span data-stu-id="f843d-235">When **Group similar** is unchecked, the `hello` messages are ungrouped.</span></span>
:::image-end:::  

<span data-ttu-id="f843d-236">使用[将重复消息发送到控制台的示例，][CodepenZoherghadyaliZyrjgdJ]为此功能提供一次尝试。</span><span class="sxs-lookup"><span data-stu-id="f843d-236">Give this feature a try with a [sample that sends duplicate messages to the Console][CodepenZoherghadyaliZyrjgdJ].</span></span>  

<span data-ttu-id="f843d-237">Chromium 问题[#1082963][CR1082963]</span><span class="sxs-lookup"><span data-stu-id="f843d-237">Chromium issue [#1082963][CR1082963]</span></span>  

### <span data-ttu-id="f843d-238">保留所选仅限上下文设置</span><span class="sxs-lookup"><span data-stu-id="f843d-238">Persisting Selected context only settings</span></span>  

<span data-ttu-id="f843d-239">"**仅**在控制台设置中选择的上下文" 设置现在保持。</span><span class="sxs-lookup"><span data-stu-id="f843d-239">The **Selected context only** settings in Console Settings is now persisted.</span></span>  <span data-ttu-id="f843d-240">以前，每次您关闭并重新打开 DevTools 时，设置都将重置。</span><span class="sxs-lookup"><span data-stu-id="f843d-240">Previously the settings were reset every time you closed and reopened DevTools.</span></span>  <span data-ttu-id="f843d-241">该更改使设置行为与其他控制台设置选项一致。</span><span class="sxs-lookup"><span data-stu-id="f843d-241">The change makes the setting behavior consistent with other Console Settings options.</span></span>  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="仅限所选上下文设置" lightbox="../../media/2020/06/selected-context.msft.png":::
   <span data-ttu-id="f843d-243">**仅限所选上下文**设置</span><span class="sxs-lookup"><span data-stu-id="f843d-243">**Selected context only** setting</span></span>  
:::image-end:::  

<span data-ttu-id="f843d-244">Chromium 问题[#1055875][CR1055875]</span><span class="sxs-lookup"><span data-stu-id="f843d-244">Chromium issue [#1055875][CR1055875]</span></span>  

### <span data-ttu-id="f843d-245">性能面板更新</span><span class="sxs-lookup"><span data-stu-id="f843d-245">Performance panel updates</span></span>  

#### <span data-ttu-id="f843d-246">性能面板中的 JavaScript 编译缓存信息</span><span class="sxs-lookup"><span data-stu-id="f843d-246">JavaScript compilation cache information in Performance panel</span></span>  

<span data-ttu-id="f843d-247">[JavaScript 编译缓存信息][V8DevCodeCaching]现在始终显示在 "性能" 面板的 "摘要" 选项卡中。</span><span class="sxs-lookup"><span data-stu-id="f843d-247">[JavaScript compilation cache information][V8DevCodeCaching] is now always displayed in the Summary tab of the Performance panel.</span></span>  <span data-ttu-id="f843d-248">以前，如果代码缓存未发生，DevTools 不会显示与代码缓存相关的任何内容。</span><span class="sxs-lookup"><span data-stu-id="f843d-248">Previously, DevTools did not show anything related to code caching if code caching did not happen.</span></span>  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="JavaScript 编译缓存信息" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   <span data-ttu-id="f843d-250">JavaScript 编译缓存信息</span><span class="sxs-lookup"><span data-stu-id="f843d-250">JavaScript compilation cache information</span></span>  
:::image-end:::  

<span data-ttu-id="f843d-251">Chromium 问题[#912581][CR912581]</span><span class="sxs-lookup"><span data-stu-id="f843d-251">Chromium issue [#912581][CR912581]</span></span>  

#### <span data-ttu-id="f843d-252">"性能" 面板中的导航计时对齐方式</span><span class="sxs-lookup"><span data-stu-id="f843d-252">Navigation timing alignment in the Performance panel</span></span>  

<span data-ttu-id="f843d-253">"**性能**" 面板，用于根据录制开始时在标尺中显示时间。</span><span class="sxs-lookup"><span data-stu-id="f843d-253">The **Performance** panel used to show times in the rulers based on when the recording started.</span></span>  <span data-ttu-id="f843d-254">对于用户导航的录制，计时现在已更改，其中 DevTools 现在显示相对于导航的标尺时间。</span><span class="sxs-lookup"><span data-stu-id="f843d-254">The timing has now changed for recordings where the user navigates, where DevTools now shows ruler times relative to the navigation instead.</span></span>  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="对齐性能面板中的导航计时" lightbox="../../media/2020/06/nav-timing.msft.png":::
   <span data-ttu-id="f843d-256">对齐**性能**面板中的导航计时</span><span class="sxs-lookup"><span data-stu-id="f843d-256">Align navigation timing in **Performance** panel</span></span>  
:::image-end:::  

<span data-ttu-id="f843d-257">`DOMContentLoaded`第一次绘制、第一个 Contentful 画图和最大 Contentful 绘制事件的时间将更新为相对于导航的开始，这意味着计时计时与所报告的计时相匹配 `PerformanceObserver` 。</span><span class="sxs-lookup"><span data-stu-id="f843d-257">The times for `DOMContentLoaded`, First Paint, First Contentful Paint, and Largest Contentful Paint events are updated to be relative to the start of the navigation, which means the timing matches the timings reported by `PerformanceObserver`.</span></span>  

<span data-ttu-id="f843d-258">Chromium 问题[#974550][CR974550]</span><span class="sxs-lookup"><span data-stu-id="f843d-258">Chromium issue [#974550][CR974550]</span></span>  

### <span data-ttu-id="f843d-259">用于断点、条件断点和 logpoints 的新图标</span><span class="sxs-lookup"><span data-stu-id="f843d-259">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="f843d-260">"**源**" 面板具有新的断点、条件断点和 logpoints 设计。</span><span class="sxs-lookup"><span data-stu-id="f843d-260">The **Sources** panel has new designs for breakpoints, conditional breakpoints, and logpoints.</span></span>  <span data-ttu-id="f843d-261">断点通过红色圆圈表示，就像[与代码][VSCode]和[Visual Studio][VS]一样。</span><span class="sxs-lookup"><span data-stu-id="f843d-261">Breakpoints are represented by a red circle, just like [VS Code][VSCode] and [Visual Studio][VS].</span></span>  <span data-ttu-id="f843d-262">添加图标以区分条件断点和 logpoints。</span><span class="sxs-lookup"><span data-stu-id="f843d-262">Icons are added to differentiate conditional breakpoints and logpoints.</span></span>  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="断点" lightbox="../../media/2020/06/breakpoints.msft.png":::
   <span data-ttu-id="f843d-264">断点</span><span class="sxs-lookup"><span data-stu-id="f843d-264">Breakpoints</span></span>  
:::image-end:::  

<span data-ttu-id="f843d-265">Chromium 问题[#1041830][CR1041830]</span><span class="sxs-lookup"><span data-stu-id="f843d-265">Chromium issue [#1041830][CR1041830]</span></span>  

## <span data-ttu-id="f843d-266">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="f843d-266">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="f843d-267">如果你使用的是 Windows 或 macOS，请考虑将[Microsoft Edge 预览通道][MicrosoftEdgePreviewChannels]用作默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="f843d-267">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="f843d-268">预览频道使您可以访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="f843d-268">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="f843d-269">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="f843d-269">Getting in touch with Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="f843d-270">使用以下选项讨论帖子中的新功能和更改，或与 DevTools 相关的任何其他内容。</span><span class="sxs-lookup"><span data-stu-id="f843d-270">Use the following options to discuss the new features and changes in the post, or anything else related to DevTools.</span></span>  

* <span data-ttu-id="f843d-271">使用 DevTools 中的**反馈**图标发送反馈</span><span class="sxs-lookup"><span data-stu-id="f843d-271">Send your feedback using the **Feedback** icon in the DevTools</span></span>  
* <span data-ttu-id="f843d-272">Tweet [@EdgeDevTools][PostTweetEdgeDevTools]</span><span class="sxs-lookup"><span data-stu-id="f843d-272">Tweet at [@EdgeDevTools][PostTweetEdgeDevTools]</span></span>  
* <span data-ttu-id="f843d-273">向[我们需要的网站][TheWebWeWant]提交建议</span><span class="sxs-lookup"><span data-stu-id="f843d-273">Submit a suggestion to [The Web We Want][TheWebWeWant]</span></span>  
* <span data-ttu-id="f843d-274">此页面上的文件错误在[edge-开发人员][GitHubMicrosoftDocsEdgeDeveloperNewIssue]存储库中</span><span class="sxs-lookup"><span data-stu-id="f843d-274">File bugs on this page in the [edge-developer][GitHubMicrosoftDocsEdgeDeveloperNewIssue] repository</span></span>  

:::image type="complex" source="../../media/2020/05/feedback-icon.msft.png" alt-text="Microsoft Edge DevTools 中的 "反馈" 图标" lightbox="../../media/2020/05/feedback-icon.msft.png":::
  <span data-ttu-id="f843d-276">Microsoft Edge DevTools 中的 "**反馈**" 图标</span><span class="sxs-lookup"><span data-stu-id="f843d-276">The **Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发工具 |Microsoft 文档"  
[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "抽屉-自定义 Microsoft Edge DevTools |Microsoft 文档"
[DevtoolsExperimentalFeaturesTurnOn]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "启用实验功能-实验功能 |Microsoft 文档"  
[DevtoolsIssues]: /microsoft-edge/devtools-guide-chromium/issues "查找并修复 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"
[DevtoolsSourcesEditCssJavascript]: /microsoft-edge/devtools-guide-chromium/sources#edit-css-and-javascript "编辑 CSS 和 JavaScript-源代码面板概述 |Microsoft 文档"  
[DevtoolsNetworkIndexLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "记录网络活动-在 Microsoft Edge DevTools 中检查网络活动 |Microsoft 文档"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "对 JS CSS 中的 CSS 进行样式编辑 |CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "将重复邮件发送到控制台 |CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS 网格 planner 示例 |CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  

[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium bug"  
[CR800028]: https://crbug.com/800028 "在 Chrome 更新后，开发工具编辑器中的 "复制行" 快捷方式不起作用 |Chromium bug"  
[CR912581]: https://crbug.com/912581 "在 DevTools/关于跟踪中公开由 V8 缓存的脚本代码：跟踪 |Chromium bug"  
[CR946975]: https://crbug.com/946975 "DevTools 样式侧栏不适用于构造的样式表 |Chromium bug"  
[CR955497]: https://crbug.com/955497 "适用于 PWAs | 的应用图标快捷菜单Chromium bug"  
[CR974550]: https://crbug.com/974550 "性能面板和 performanceObserver | 之间的跃点数不匹配Chromium bug"  
[CR1041830]: https://crbug.com/1041830 "改善断点的颜色 |Chromium bug"  
[CR1055875]: https://crbug.com/1055875 "在关闭并重新打开开发人员工具 | 后，所选 "仅限上下文" 控制台设置的值不会保留。Chromium bug"  
[CR1066579]: https://crbug.com/1066579 "DevTools：在 "网络" 面板中显示 ServiceWorkers 每个请求的提取时间线 |Chromium bug"  
[CR1071432]: https://crbug.com/1071432 "Wasm Basic 开发人员体验 |Chromium bug"  
[CR1073899]: https://crbug.com/1073899 ""计算样式" 选项卡在 "响应模式" 中消失 |Chromium bug"  
[CR1073903]: https://crbug.com/1073903 "DevTools：语法突出显示不能处理私有字段 |Chromium bug"  
[CR1082963]: https://crbug.com/1082963 "无法禁用控制台的 "分组类似消息" 行为 |Chromium bug"  
[CR1083214]: https://crbug.com/1083214 "acorn 不支持可选的链接 |Chromium bug"  
[CR1083797]: https://crbug.com/1083797 "Nullish 合并的整齐打印中断 |Chromium bug"  
[CR1096008]: https://crbug.com/1096008 "删除 FMP |Chromium bug"  
[CR1047356]: https://crbug.com/1047356 "CSS 网格/Flexbox/表格工具 |Chromium bug"  
[CR1093687]: https://crbug.com/1093687 "创建用于创建和重播合成网络请求的工具 |Chromium bug"  
[CR1070378]: https://crbug.com/1070378 "将 webhint 集成到 DevTools |Chromium bug"  
[CR1069404]: https://crbug.com/1069404 "[开发工具] 小组件弹出组件太窄 |Chromium bug"  
[CR897944]: https://crbug.com/897944 "可拖动的 devtool 面板 |Chromium bug"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v 6.0.0-GoogleChrome/lighthouse |GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新问题-MicrosoftDocs/edge-开发人员"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "使用影子 DOM |MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge 预览频道"  

[VS]: https://visualstudio.microsoft.com/ "Visual Studio"
[VSCode]: https://code.visualstudio.com/ "Visual Studio 代码"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS 对象模型（CSSOM） |W3C CSS 工作组编辑器草稿"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |发布 Tweet"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "私有类字段-公共和私有类字段 |V8.开发"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "适用于 JavaScript 开发人员的代码缓存 |V8.开发"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "Nullish 合并 |V8.开发"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "可选链接 |V8.开发"  

[WebhintMain]: https://webhint.io "webhint"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "Constructable 样式表对象 |Web Incubator CG"

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

[TheWebWeWant]: https://webwewant.fyi/ "我们需要的网站"  

> [!NOTE]
> <span data-ttu-id="f843d-325">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f843d-325">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f843d-326">原始页面位于[此处](https://developers.google.com/web/updates/2020/06/devtools/index)，由[Jecelyn Yeen][JecelynYeen] \ （开发人员和 Chrome DevTools \）创作。</span><span class="sxs-lookup"><span data-stu-id="f843d-326">The original page is found [here](https://developers.google.com/web/updates/2020/06/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="f843d-328">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f843d-328">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
