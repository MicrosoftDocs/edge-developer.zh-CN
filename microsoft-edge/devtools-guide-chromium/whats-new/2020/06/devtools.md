---
title: '开发工具包 Microsoft Edge 85 (中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f569414a95336278c93b1bbafd57153ca902df12
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942193"
---
# <span data-ttu-id="5e059-103">Microsoft Edge 85 实用 (版的新增) </span><span class="sxs-lookup"><span data-stu-id="5e059-103">What's New In DevTools (Microsoft Edge 85)</span></span>  

## <span data-ttu-id="5e059-104">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="5e059-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="5e059-105">以下部分是你可能在 Microsoft Edge DevTools 团队中错过的通知的列表。</span><span class="sxs-lookup"><span data-stu-id="5e059-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="5e059-106">查看公告，尝试使用 DevTools 中的新功能、VS 代码扩展等。</span><span class="sxs-lookup"><span data-stu-id="5e059-106">See the announcements to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="5e059-107">若要在开发工具中了解最新和最出色功能，请下载 [Microsoft Edge 预览渠道并][MicrosoftEdgePreviewChannels] 在 Twitter 上按照 [Microsoft Edge DevTools 团队一并关注 Microsoft Edge DevTools 团队][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="5e059-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow the Microsoft Edge DevTools team on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="5e059-108">CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="5e059-108">CSS grid debugging features</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实质功能":::
   <span data-ttu-id="5e059-110">实质功能</span><span class="sxs-lookup"><span data-stu-id="5e059-110">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="5e059-111">Microsoft Edge 开发工具团队与 Chrome DevTools 团队和 Chromium 社区进行协作，为 DevTools 添加新的 CSS 网格调试功能。</span><span class="sxs-lookup"><span data-stu-id="5e059-111">The Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new CSS grid debugging features to DevTools.</span></span>  <span data-ttu-id="5e059-112">您现在能够将网格行的数字、网格行和扩展的网格线显示为页面覆盖。</span><span class="sxs-lookup"><span data-stu-id="5e059-112">You are now able to display grid line numbers, grid gaps, and extended grid lines as an on-page overlay.</span></span>  <span data-ttu-id="5e059-113">此外，即将推出对网格工具的更多改进。</span><span class="sxs-lookup"><span data-stu-id="5e059-113">Plus, more improvements to the grid tools are coming soon.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-grid.msft.png" alt-text="CSS 网格调试功能" lightbox="../../media/2020/06/experiments-grid.msft.png":::
   <span data-ttu-id="5e059-115">CSS 网格调试功能</span><span class="sxs-lookup"><span data-stu-id="5e059-115">CSS grid debugging features</span></span>
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="5e059-116">若要启用实用功能，请参阅" [启用实用功能"][DevtoolsExperimentalFeaturesTurnOn] 并选中"启用 **新 CSS 网格调试功能"旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="5e059-116">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable new CSS Grid debugging features**.</span></span>  
> 
> <span data-ttu-id="5e059-117">要试用示例，请参阅 [CSS 网格规划器示例][CodepenRachelweilYzwBzKM]。</span><span class="sxs-lookup"><span data-stu-id="5e059-117">To try out the experiment with a sample, see [CSS Grid planner example][CodepenRachelweilYzwBzKM].</span></span>  

<span data-ttu-id="5e059-118">Chromium [#1047356][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="5e059-118">Chromium issue [#1047356][CR1047356]</span></span>  

### <span data-ttu-id="5e059-119">使用网络控制台编辑和重播请求</span><span class="sxs-lookup"><span data-stu-id="5e059-119">Edit and Replay requests with the Network Console</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实质功能":::
   <span data-ttu-id="5e059-121">实质功能</span><span class="sxs-lookup"><span data-stu-id="5e059-121">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="5e059-122">你现在可以使用" **网络网络控制台** "在 [网络日志中的][DevtoolsNetworkIndexLogActivity] 请求上进行 **编辑和重播**。</span><span class="sxs-lookup"><span data-stu-id="5e059-122">You are now able to use **Edit and Replay** on requests in the [Network Log][DevtoolsNetworkIndexLogActivity] using the **Network Console**.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png" alt-text="使用网络控制台编辑和重播 NetworkLog 中的请求" lightbox="../../media/2020/06/experiments-network-console-edit-and-replay.msft.png":::
   <span data-ttu-id="5e059-124">使用网络控制台编辑并重播 [NetworkLog][DevtoolsNetworkIndexLogActivity] **中的请求**</span><span class="sxs-lookup"><span data-stu-id="5e059-124">Edit and Replay a request in the [NetworkLog][DevtoolsNetworkIndexLogActivity] with the **Network Console**</span></span>  
:::image-end:::  

<span data-ttu-id="5e059-125">新面板将在**Network Console**[DevTools 绘][DevtoolsCustomizeIndexDrawer]图器中打开网络控制台，并用 HTTP 请求的信息自动填充。</span><span class="sxs-lookup"><span data-stu-id="5e059-125">A new panel, the **Network Console** opens in the [DevTools Drawer][DevtoolsCustomizeIndexDrawer] and automatically populates with information for the HTTP request.</span></span>  <span data-ttu-id="5e059-126">若要查看从服务器返回的响应，请编辑请求 \ (如需要它）并 ) 选择 **"发送**"。</span><span class="sxs-lookup"><span data-stu-id="5e059-126">To see the response returned from the server, edit the request \(if needed\) and select **Send**.</span></span>  

<span data-ttu-id="5e059-127">您也可以使用" **网络控制台"** 直接从 DevTools 创建并发送 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="5e059-127">You may also use the **Network Console** to create and send HTTP requests directly from the DevTools.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-network-console.msft.png" alt-text=""网络控制台"面板" lightbox="../../media/2020/06/experiments-network-console.msft.png":::
   <span data-ttu-id="5e059-129">" **网络控制台"** 面板</span><span class="sxs-lookup"><span data-stu-id="5e059-129">The **Network Console** panel</span></span>  
:::image-end:::  

> [!TIP]
> <span data-ttu-id="5e059-130">若要查看 **主** \ (top\) 面板中"网络控制台"而不是 [DevTools Drawer，][DevtoolsCustomizeIndexDrawer]请参阅在 [面板之间移动工具](#move-tools-between-panels)。</span><span class="sxs-lookup"><span data-stu-id="5e059-130">To see **Network Console** in the main \(top\) panel instead of the [DevTools Drawer][DevtoolsCustomizeIndexDrawer], see [moving tools between panels](#move-tools-between-panels).</span></span>  

> [!NOTE]
> <span data-ttu-id="5e059-131">若要启用实例，请参阅" [启用实用功能][DevtoolsExperimentalFeaturesTurnOn] "，并选中"启用网络控制台 **"旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="5e059-131">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable Network Console**.</span></span>  
> 
> <span data-ttu-id="5e059-132">打开网络 [日志][DevtoolsNetworkIndexLogActivity]，打开上下文菜单 \ (右键单击\) ，然后选择" **编辑"和"重播**"。</span><span class="sxs-lookup"><span data-stu-id="5e059-132">Open the [Network Log][DevtoolsNetworkIndexLogActivity], open the contextual menu \(right-click\), and select **Edit and Replay**.</span></span>  

<span data-ttu-id="5e059-133">Chromium [问题#1093687][CR1093687]</span><span class="sxs-lookup"><span data-stu-id="5e059-133">Chromium issue [#1093687][CR1093687]</span></span>  

### <span data-ttu-id="5e059-134">在"计时"选项卡中的服务工作者响应事件</span><span class="sxs-lookup"><span data-stu-id="5e059-134">Service worker respondWith events in the Timing tab</span></span>  

<span data-ttu-id="5e059-135">" **网络"面板** 的"计 **时** "选项卡现包含 `respondWith` 服务工作者事件。</span><span class="sxs-lookup"><span data-stu-id="5e059-135">The **Timing** tab of the **Network** panel now includes `respondWith` service worker events.</span></span>  <span data-ttu-id="5e059-136">服务工作者事件会在服务工作者事件处理程序开始在设置处理程序 `respondWith` `fetch` `respondWith` promise 时开始运行至该时间之前的 `fetch` 持续时间。</span><span class="sxs-lookup"><span data-stu-id="5e059-136">The `respondWith` service worker event shows the duration from the time immediately before the service worker `fetch` event handler starts running to the time when the `respondWith` promise of the `fetch` handler is settled.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab.msft.png" alt-text="The service Worker 事件（网页板的"计时"选项卡）中的 respondWith Service Worker 事件" lightbox="../../media/2020/06/timing-tab.msft.png":::
   <span data-ttu-id="5e059-138">" `respondWith` 网络"面板的"**计时"选项卡**中的服务**Network**工作者事件</span><span class="sxs-lookup"><span data-stu-id="5e059-138">The `respondWith` service worker event in the **Timing** tab of the **Network** panel</span></span>  
:::image-end:::  

<span data-ttu-id="5e059-139">展开收到 **的响应，** 查看来自回复的更多 `fetch` 信息，如与响应 `CacheStorageCacheName` `serviceWorkerResponseSource` 之间的其他 `ResponseTime` 信息。</span><span class="sxs-lookup"><span data-stu-id="5e059-139">Expand **Response received** to see additional information from the `fetch` response like `CacheStorageCacheName`, `serviceWorkerResponseSource`, and `ResponseTime`.</span></span>  

:::image type="complex" source="../../media/2020/06/timing-tab2.msft.png" alt-text="展开收到的响应以查看来自提取响应的更多信息" lightbox="../../media/2020/06/timing-tab2.msft.png":::
   <span data-ttu-id="5e059-141">展开 **收到的响应** 以查看来自回复 `fetch` 的更多信息</span><span class="sxs-lookup"><span data-stu-id="5e059-141">Expand **Response received** to see additional information from the `fetch` response</span></span>  
:::image-end:::  

<span data-ttu-id="5e059-142">Chromium [问题#1066579][CR1066579]</span><span class="sxs-lookup"><span data-stu-id="5e059-142">Chromium issue [#1066579][CR1066579]</span></span>  

### <span data-ttu-id="5e059-143">问题面板中的 WebHint 反馈</span><span class="sxs-lookup"><span data-stu-id="5e059-143">webhint feedback in the Issues panel</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实质功能":::
   <span data-ttu-id="5e059-145">实质功能</span><span class="sxs-lookup"><span data-stu-id="5e059-145">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="5e059-146">[webhint 是][WebhintMain] 一款开源工具，可提供有关辅助功能、跨浏览器兼容性、安全性、性能、PWA 和其他常见网站开发问题的实时反馈。</span><span class="sxs-lookup"><span data-stu-id="5e059-146">[webhint][WebhintMain] is an open-source tool that provides real-time feedback on the accessibility, cross-browser compatibility, security, performance, PWAs, and other common web development issues of websites.</span></span>  <span data-ttu-id="5e059-147">现在你可以在问题面板中查看网络 [提示反][DevtoolsIssues] 馈。</span><span class="sxs-lookup"><span data-stu-id="5e059-147">You are now able to see webhint feedback in the [Issues][DevtoolsIssues] panel.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-webhint.msft.png" alt-text="问题面板中的 WebHint 反馈" lightbox="../../media/2020/06/experiments-webhint.msft.png":::
   <span data-ttu-id="5e059-149">问题面板中的 WebHint 反馈</span><span class="sxs-lookup"><span data-stu-id="5e059-149">webhint feedback in the Issues panel</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="5e059-150">若要启用实用功能，请参见 ["启用实用功能"，][DevtoolsExperimentalFeaturesTurnOn] 并选中"启用 **webhint"旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="5e059-150">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable webhint**.</span></span>  
> 
> <span data-ttu-id="5e059-151">打开问题 [面板][DevtoolsIssues] ，以查看来自 Webhint 的反馈。</span><span class="sxs-lookup"><span data-stu-id="5e059-151">Open the [Issues][DevtoolsIssues] panel to see feedback from webhint.</span></span>  

<span data-ttu-id="5e059-152">Chromium [问题#1070378][CR1070378]</span><span class="sxs-lookup"><span data-stu-id="5e059-152">Chromium issue [#1070378][CR1070378]</span></span>  

### <span data-ttu-id="5e059-153">在面板之间移动工具</span><span class="sxs-lookup"><span data-stu-id="5e059-153">Move tools between panels</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实质功能":::
   <span data-ttu-id="5e059-155">实质功能</span><span class="sxs-lookup"><span data-stu-id="5e059-155">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="5e059-156">通常，元素和网络**等**工具只能在**Network**DevTools 的主 \ (top\) 面板中打开。</span><span class="sxs-lookup"><span data-stu-id="5e059-156">Normally, tools such as **Elements** and **Network** may only be opened in the main \(top\) panel of DevTools.</span></span>  <span data-ttu-id="5e059-157">同样 **，3D 视图** 和 **问题** 等工具只能在 DevTools 绘图器 \ (底\) 面板中打开。</span><span class="sxs-lookup"><span data-stu-id="5e059-157">Similarly, tools such as **3D View** and **Issues** may only be opened in the drawer \(bottom\) panel of DevTools.</span></span>  <span data-ttu-id="5e059-158">现在你可以通过在顶部和底部面板之间移动工具自定义 DevTools 布局。</span><span class="sxs-lookup"><span data-stu-id="5e059-158">You are now able to customize your DevTools layout by moving tools between the top and bottom panels.</span></span>  

:::image type="complex" source="../../media/2020/06/experiments-move-panels.msft.png" alt-text="在面板之间移动选项卡" lightbox="../../media/2020/06/experiments-move-panels.msft.png":::
   <span data-ttu-id="5e059-160">在面板之间移动选项卡</span><span class="sxs-lookup"><span data-stu-id="5e059-160">Moving tabs between panels</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="5e059-161">若要启用实效果，请参阅" [启用实用功能"并][DevtoolsExperimentalFeaturesTurnOn] 选中"启用支持 **"在面板之间移动选项卡旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="5e059-161">To enable the experiment, see [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOn] and select the checkbox next to **Enable support to move tabs between panels**.</span></span>  

<span data-ttu-id="5e059-162">Chromium [问题#897944][CR897944]</span><span class="sxs-lookup"><span data-stu-id="5e059-162">Chromium issue [#897944][CR897944]</span></span>  

### <span data-ttu-id="5e059-163">改进了网络面板中的"初始平行器工具提示"</span><span class="sxs-lookup"><span data-stu-id="5e059-163">Improved Initiator tooltip in the Network panel</span></span>  

<span data-ttu-id="5e059-164">在 Microsoft Edge 83 和 84 中，"初始窗口"列的工具提示，其中显示资源请求的起始结点，即在 [显示了][DevtoolsNetworkIndexLogActivity] 水平滚动条的"网络日志"中。</span><span class="sxs-lookup"><span data-stu-id="5e059-164">In Microsoft Edge 83 and 84, tooltips for the Initiator column, which shows the cause of the resource request, in the [Network Log][DevtoolsNetworkIndexLogActivity] displayed with a horizontal scrollbar.</span></span>  <span data-ttu-id="5e059-165">您只能看到通过在工具提示中水平滚动来发出请求的调用堆叠。</span><span class="sxs-lookup"><span data-stu-id="5e059-165">You were only able to see the call stack that initiated the request by scrolling horizontally in the tooltip.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-84.msft.png" alt-text="Microsoft Edge 84 中的初始方工具提示" lightbox="../../media/2020/06/initiator-tooltip-84.msft.png":::
   <span data-ttu-id="5e059-167">Microsoft Edge 84 中的初始方工具提示</span><span class="sxs-lookup"><span data-stu-id="5e059-167">The Initiator tooltip in Microsoft Edge 84</span></span>  
:::image-end:::  

<span data-ttu-id="5e059-168">从 Microsoft Edge 85 开始，你现在可以看到工具提示中的初始呼叫堆叠，无需水平滚动。</span><span class="sxs-lookup"><span data-stu-id="5e059-168">Starting with Microsoft Edge 85, you are now able to see the Initiator call stack in the tooltip without scrolling horizontally.</span></span>  

:::image type="complex" source="../../media/2020/06/initiator-tooltip-85.msft.png" alt-text="Microsoft Edge 85 中的初始表工具提示" lightbox="../../media/2020/06/initiator-tooltip-85.msft.png":::
   <span data-ttu-id="5e059-170">Microsoft Edge 85 中的初始表工具提示</span><span class="sxs-lookup"><span data-stu-id="5e059-170">The Initiator tooltip in Microsoft Edge 85</span></span>
:::image-end:::  

<span data-ttu-id="5e059-171">Chromium [问题#1069404][CR1069404]</span><span class="sxs-lookup"><span data-stu-id="5e059-171">Chromium issue [#1069404][CR1069404]</span></span>  

## <span data-ttu-id="5e059-172">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="5e059-172">Announcements from the Chromium project</span></span>  

<span data-ttu-id="5e059-173">以下部分公布给开源 Chromium 项目的 Microsoft Edge 85 中可用的其他功能。</span><span class="sxs-lookup"><span data-stu-id="5e059-173">The following sections announce additional features available in Microsoft Edge 85 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="5e059-174">CSS 内的 CSS 框架的样式编辑</span><span class="sxs-lookup"><span data-stu-id="5e059-174">Style editing for CSS-in-JS frameworks</span></span>  

<span data-ttu-id="5e059-175">" **样式** "窗格现在支持更好的支持编辑 [使用 CSS 对象模型和 CSSOM (或 API 创建) ][CsswgDraftsCssom] 样式。</span><span class="sxs-lookup"><span data-stu-id="5e059-175">The **Styles** pane now has better support for editing styles that were created with the [CSS Object Model (CSSOM)][CsswgDraftsCssom] APIs.</span></span>  <span data-ttu-id="5e059-176">许多 CSS 内的 JS 框架和库都使用本机下的 CSSOM API 构造样式。</span><span class="sxs-lookup"><span data-stu-id="5e059-176">Many CSS-in-JS frameworks and libraries use the CSSOM APIs under the hood to construct styles.</span></span>  

<span data-ttu-id="5e059-177">你现在可以使用构造样式表编辑 JavaScript [中添加的样式][WicgConstructStylesheet]。</span><span class="sxs-lookup"><span data-stu-id="5e059-177">You are now able to edit styles added in JavaScript using [Constructable Stylesheets][WicgConstructStylesheet].</span></span>  <span data-ttu-id="5e059-178">在使用 Shadow DOM 时，构造样式表是一种用于创建和分发 [可重复使用的样式的新方法][MdnShadowDom]。</span><span class="sxs-lookup"><span data-stu-id="5e059-178">Constructable Stylesheets are a new way to create and distribute reusable styles when using [Shadow DOM][MdnShadowDom].</span></span>  

<span data-ttu-id="5e059-179">例如，使用 `h1` `CSSStyleSheet` \ (CSSOM API 添加的样式之前) 不可编辑。</span><span class="sxs-lookup"><span data-stu-id="5e059-179">For example, the `h1` styles added with `CSSStyleSheet` \(CSSOM APIs\) were not editable previously.</span></span>  <span data-ttu-id="5e059-180">现在，这些样式在"样式"窗格中 **可编辑** 。</span><span class="sxs-lookup"><span data-stu-id="5e059-180">The styles are editable now in the **Styles** pane.</span></span>  

:::image type="complex" source="../../media/2020/06/css-in-js.msft.png" alt-text="更改 h1 样式的背景属性以 CSSStyleSheet 的形式从头更改为浅蓝色" lightbox="../../media/2020/06/css-in-js.msft.png":::
   <span data-ttu-id="5e059-182">更改添加的 `background` 样式 `h1` 的属性来自 `CSSStyleSheet` 其他 `pink` 位置 `lightblue` 。</span><span class="sxs-lookup"><span data-stu-id="5e059-182">Changing the `background` property of the `h1` styles added with `CSSStyleSheet` from `pink` to `lightblue`.</span></span>
:::image-end:::  

<span data-ttu-id="5e059-183">请让此功能试用 [使用 CSS 内 JS 的示例][CodepenZoherghadyaliAbdgrpz]。</span><span class="sxs-lookup"><span data-stu-id="5e059-183">Give this feature a try with a [sample that uses CSS-in-JS][CodepenZoherghadyaliAbdgrpz].</span></span>

<span data-ttu-id="5e059-184">Chromium [问题#946975][CR946975]</span><span class="sxs-lookup"><span data-stu-id="5e059-184">Chromium issue [#946975][CR946975]</span></span>  

### <span data-ttu-id="5e059-185">Lighthouse 面板中的浅色 6</span><span class="sxs-lookup"><span data-stu-id="5e059-185">Lighthouse 6 in the Lighthouse panel</span></span>  

<span data-ttu-id="5e059-186">**光照面板**现在运行了浅色house 6。</span><span class="sxs-lookup"><span data-stu-id="5e059-186">The **Lighthouse** panel is now running Lighthouse 6.</span></span>  <span data-ttu-id="5e059-187">有关所有更改的完整列表，请 [访问 v6.0.0 发行说明][GithubGoogleChromeLighthouse600]。</span><span class="sxs-lookup"><span data-stu-id="5e059-187">For a full list of all changes, see [v6.0.0 release notes][GithubGoogleChromeLighthouse600].</span></span>  

<span data-ttu-id="5e059-188">Lighthouse 6.0 向报表中引入了三个新的指标：内容最大画图 \ (LCP\) 、累计布局 Shift \ (CLS\) 和总阻止时间 \ (TBT\) 。</span><span class="sxs-lookup"><span data-stu-id="5e059-188">Lighthouse 6.0 introduces three new metrics to the report:  Largest Contentful Paint \(LCP\), Cumulative Layout Shift \(CLS\), and Total Blocking Time \(TBT\).</span></span>  

<span data-ttu-id="5e059-189">性能分数公式也经过重新正确对分析，可更好地反射用户的加载体验。</span><span class="sxs-lookup"><span data-stu-id="5e059-189">The performance score formula has also been reweighted to better reflect the loading experience of the user.</span></span>  

<span data-ttu-id="5e059-190">Chromium [问题#772558][CR772558]</span><span class="sxs-lookup"><span data-stu-id="5e059-190">Chromium issue [#772558][CR772558]</span></span>  

#### <span data-ttu-id="5e059-191">First Meaningful Paint deprecation</span><span class="sxs-lookup"><span data-stu-id="5e059-191">First Meaningful Paint deprecation</span></span>  

<span data-ttu-id="5e059-192">First Meaningful Paint \ (FMP\) in Lighthouse 6.0 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="5e059-192">First Meaningful Paint \(FMP\) is deprecated in Lighthouse 6.0.</span></span>  <span data-ttu-id="5e059-193">"性能"面板也已删除 FMP。 **Performance**</span><span class="sxs-lookup"><span data-stu-id="5e059-193">FMP has also been removed from the **Performance** panel.</span></span>  <span data-ttu-id="5e059-194">**建议 FMP 使用最** 大的内容画图替换。</span><span class="sxs-lookup"><span data-stu-id="5e059-194">**Largest Contentful Paint** is the recommended replacement for FMP.</span></span>  <!--See [First Meaningful Paint][WebDevFirstMeaningfulPaint] for an explanation of why it was deprecated.  -->  

<!--todo: add Largest Contentful Paint when section available  -->  
<!--todo: add First Meaningful Paint link and note when available  -->  

<span data-ttu-id="5e059-195">Chromium [问题#1096008][CR1096008]</span><span class="sxs-lookup"><span data-stu-id="5e059-195">Chromium issue [#1096008][CR1096008]</span></span>  

### <span data-ttu-id="5e059-196">支持新的 JavaScript 功能</span><span class="sxs-lookup"><span data-stu-id="5e059-196">Support for new JavaScript features</span></span>  

<span data-ttu-id="5e059-197">DevTools 现在支持某些最新的 JavaScript 语言功能。</span><span class="sxs-lookup"><span data-stu-id="5e059-197">DevTools now has better support for some of the latest JavaScript language features.</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="5e059-198">[可选][V8DevOptionalChaining] 交换语法自动完成</span><span class="sxs-lookup"><span data-stu-id="5e059-198">[Optional chaining][V8DevOptionalChaining] syntax autocompletion</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="5e059-199">现在，主机中的属性 **自动完成** 功能自动完成（例如，你现在也可在此效果上有  `name?.` `name.` 效 `name[` ）。</span><span class="sxs-lookup"><span data-stu-id="5e059-199">Property auto-completion in the **Console** now supports optional chaining syntax, for example,  `name?.` now works in addition to `name.` and `name[`.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="5e059-200">私有字段的语法 [突出显示][V8DevClassFieldsPrivate]</span><span class="sxs-lookup"><span data-stu-id="5e059-200">Syntax highlighting for [private fields][V8DevClassFieldsPrivate]</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="5e059-201">私有类字段现在可以在"源"面板中正确突出显示、预先 **打印的语法** 。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="5e059-201">private class fields are now properly syntax-highlighted and pretty-printed in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      <span data-ttu-id="5e059-202">Nullish 成本运 [算符的语法突出显示][V8DevNullishCoalescing]</span><span class="sxs-lookup"><span data-stu-id="5e059-202">Syntax highlighting for [Nullish coalescing operator][V8DevNullishCoalescing]</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="5e059-203">DevTools 现在可以正确地预先打印源面板中的 Nullish 副本 **运算** 符。</span><span class="sxs-lookup"><span data-stu-id="5e059-203">DevTools now properly pretty-prints the nullish coalescing operator in the **Sources** panel.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="5e059-204">Chromium [#1073903、][CR1073903] [#1083214][CR1083214]等 [#1083797][CR1083797]</span><span class="sxs-lookup"><span data-stu-id="5e059-204">Chromium issues [#1073903][CR1073903], [#1083214][CR1083214], [#1083797][CR1083797]</span></span>  

### <span data-ttu-id="5e059-205">清单窗格中的新应用快捷方式警告</span><span class="sxs-lookup"><span data-stu-id="5e059-205">New app shortcut warnings in the Manifest pane</span></span>  

<span data-ttu-id="5e059-206">**应用快捷方式** 可帮助用户在 Web 应用中快速启动常规任务或推荐的任务。</span><span class="sxs-lookup"><span data-stu-id="5e059-206">**App shortcuts** help users quickly start common or recommended tasks within a web app.</span></span>  

<!--todo: add App shortcuts when section is live  -->  

<span data-ttu-id="5e059-207">清 **单窗格** 现在显示以下条件的警告。</span><span class="sxs-lookup"><span data-stu-id="5e059-207">The **Manifest** pane now shows warnings for the following conditions.</span></span>  

* <span data-ttu-id="5e059-208">应用快捷方式图标小于 96x96 像素</span><span class="sxs-lookup"><span data-stu-id="5e059-208">The app shortcut icons are smaller than 96x96 pixels</span></span>  
* <span data-ttu-id="5e059-209">应用快捷方式图标和清单图标不是方形 \ (，，由于图标被忽略\) </span><span class="sxs-lookup"><span data-stu-id="5e059-209">The app shortcut icons and manifest icons are not square \(since the icons are ignored\)</span></span>  

:::image type="complex" source="../../media/2020/06/app-shortcut-warnings.msft.png" alt-text="应用快捷方式警告" lightbox="../../media/2020/06/app-shortcut-warnings.msft.png":::
   <span data-ttu-id="5e059-211">应用快捷方式警告</span><span class="sxs-lookup"><span data-stu-id="5e059-211">App shortcut warnings</span></span>  
:::image-end:::  

<span data-ttu-id="5e059-212">Chromium [问题#955497][CR955497]</span><span class="sxs-lookup"><span data-stu-id="5e059-212">Chromium issue [#955497][CR955497]</span></span>  

### <span data-ttu-id="5e059-213">"计算"窗格的一个一体显示</span><span class="sxs-lookup"><span data-stu-id="5e059-213">Consistent display of the Computed pane</span></span>  

<span data-ttu-id="5e059-214">"**元素"面**板中的计算后**Elements**面板现在所有视区大小上以一个窗格形式显示一定。</span><span class="sxs-lookup"><span data-stu-id="5e059-214">The **Computed** pane in the **Elements** panel now displays consistently as a pane across all viewport sizes.</span></span>  <span data-ttu-id="5e059-215">如果 DevTools**视口的**宽度缩小**Styles**，则以前计算的窗格会合并到"样式"窗格中。</span><span class="sxs-lookup"><span data-stu-id="5e059-215">Previously the **Computed** pane merged inside the **Styles** pane when the width of the DevTools viewport was narrow.</span></span>  

:::image type="complex" source="../../media/2020/06/computed-pane.msft.png" alt-text="计算的窗格一直显示为单独的窗格，即使 DevTools 变窄时也是如此" lightbox="../../media/2020/06/computed-pane.msft.png":::
   <span data-ttu-id="5e059-217">计算 **的窗格** 一直显示为单独的窗格，即使 DevTools 变窄时也是如此。</span><span class="sxs-lookup"><span data-stu-id="5e059-217">The **Computed** pane consistently displays as a separate pane even when the DevTools are narrow.</span></span>
:::image-end:::  

<span data-ttu-id="5e059-218">Chromium [问题#1073899][CR1073899]</span><span class="sxs-lookup"><span data-stu-id="5e059-218">Chromium issue [#1073899][CR1073899]</span></span>  

### <span data-ttu-id="5e059-219">WebAssembly 文件的字节码偏移</span><span class="sxs-lookup"><span data-stu-id="5e059-219">Bytecode offsets for WebAssembly files</span></span>  

<span data-ttu-id="5e059-220">DevTools 现在使用字节码偏移量来显示以人区分的数目形式显示。</span><span class="sxs-lookup"><span data-stu-id="5e059-220">DevTools now uses bytecode offsets for displaying line numbers of Wasm disassembly.</span></span>  
<span data-ttu-id="5e059-221">使用行号，你可以更清楚地查看库数据，与 Wasm 运行时引用位置的方式更加一一体。</span><span class="sxs-lookup"><span data-stu-id="5e059-221">The line numbers make it clearer that you are looking at binary data, and is more consistent with how the Wasm runtime references locations.</span></span>  

<span data-ttu-id="5e059-222">Chromium [问题#1071432][CR1071432]</span><span class="sxs-lookup"><span data-stu-id="5e059-222">Chromium issue [#1071432][CR1071432]</span></span>  

### <span data-ttu-id="5e059-223">"源面板"中的行复制和剪切</span><span class="sxs-lookup"><span data-stu-id="5e059-223">Line-wise copy and cut in Sources Panel</span></span>  

<span data-ttu-id="5e059-224">在源面板编辑器中执行不带选择内容的复制或剪 [切时][DevtoolsSourcesEditCssJavascript]，DevTools 会复制或剪切当前内容行。</span><span class="sxs-lookup"><span data-stu-id="5e059-224">When performing copy or cut with no selection in the [Sources panel editor][DevtoolsSourcesEditCssJavascript], DevTools copies or cuts the current line of content.</span></span>  

:::image type="complex" source="../../media/2020/06/line-wise-cut.msft.png" alt-text="光标位于第 5 行的末尾，从 DevTools pen.js复制整行并粘贴 VS 代码" lightbox="../../media/2020/06/line-wise-cut.msft.png":::
   <span data-ttu-id="5e059-226">光标位于第 5 行的末尾，从开发pen.js复制整个行 **pen.js** 见并粘贴 [VS 代码][VSCode]。</span><span class="sxs-lookup"><span data-stu-id="5e059-226">With the cursor at the end of Line 5, copying the whole line from **pen.js** in the DevTools and pasting in [VS Code][VSCode].</span></span>
:::image-end:::  

<span data-ttu-id="5e059-227">Chromium [问题#800028][CR800028]</span><span class="sxs-lookup"><span data-stu-id="5e059-227">Chromium issue [#800028][CR800028]</span></span>

### <span data-ttu-id="5e059-228">主机设置更新</span><span class="sxs-lookup"><span data-stu-id="5e059-228">Console Settings updates</span></span>  

#### <span data-ttu-id="5e059-229">取消组合相同主机消息</span><span class="sxs-lookup"><span data-stu-id="5e059-229">Ungroup same console messages</span></span>  

<span data-ttu-id="5e059-230">**现将在控制台**设置中的组相似的切换按钮用于重复的邮件。</span><span class="sxs-lookup"><span data-stu-id="5e059-230">The **Group similar** toggle in Console Settings now applies to duplicate messages.</span></span>  <span data-ttu-id="5e059-231">以前它仅应用于类似的邮件。</span><span class="sxs-lookup"><span data-stu-id="5e059-231">Previously it just applied to similar messages.</span></span>  

<span data-ttu-id="5e059-232">例如，以前，甚至不取消组合邮件 `hello` ，即使 **未选中相** 似的组也是如此。</span><span class="sxs-lookup"><span data-stu-id="5e059-232">For example, previously, DevTools did not ungroup the `hello` messages even though **Group similar** is unchecked.</span></span>  <span data-ttu-id="5e059-233">现在， `hello` 将取消组合该消息。</span><span class="sxs-lookup"><span data-stu-id="5e059-233">Now, the `hello` messages are ungrouped.</span></span>  

:::image type="complex" source="../../media/2020/06/ungroup-similar.msft.png" alt-text="取消选中相似形状时，头堆消息会取消组合" lightbox="../../media/2020/06/ungroup-similar.msft.png":::
   <span data-ttu-id="5e059-235">取消 **选中相似的组合** 后，会 `hello` 取消组合该邮件。</span><span class="sxs-lookup"><span data-stu-id="5e059-235">When **Group similar** is unchecked, the `hello` messages are ungrouped.</span></span>
:::image-end:::  

<span data-ttu-id="5e059-236">请尝试以下 [功能，它具有向主机发送重复消息的示例][CodepenZoherghadyaliZyrjgdJ]。</span><span class="sxs-lookup"><span data-stu-id="5e059-236">Give this feature a try with a [sample that sends duplicate messages to the Console][CodepenZoherghadyaliZyrjgdJ].</span></span>  

<span data-ttu-id="5e059-237">Chromium [问题#1082963][CR1082963]</span><span class="sxs-lookup"><span data-stu-id="5e059-237">Chromium issue [#1082963][CR1082963]</span></span>  

### <span data-ttu-id="5e059-238">仅保存所选上下文设置</span><span class="sxs-lookup"><span data-stu-id="5e059-238">Persisting Selected context only settings</span></span>  

<span data-ttu-id="5e059-239">现在 **将持久保存主** 机设置中的选定上下文设置。</span><span class="sxs-lookup"><span data-stu-id="5e059-239">The **Selected context only** settings in Console Settings is now persisted.</span></span>  <span data-ttu-id="5e059-240">以前，每次关闭并重新打开 VvTools 后都会重置设置。</span><span class="sxs-lookup"><span data-stu-id="5e059-240">Previously the settings were reset every time you closed and reopened DevTools.</span></span>  <span data-ttu-id="5e059-241">更改使设置行为与其他"主机设置"选项一一一一然。</span><span class="sxs-lookup"><span data-stu-id="5e059-241">The change makes the setting behavior consistent with other Console Settings options.</span></span>  

:::image type="complex" source="../../media/2020/06/selected-context.msft.png" alt-text="所选上下文仅设置" lightbox="../../media/2020/06/selected-context.msft.png":::
   <span data-ttu-id="5e059-243">**所选上下文仅** 设置</span><span class="sxs-lookup"><span data-stu-id="5e059-243">**Selected context only** setting</span></span>  
:::image-end:::  

<span data-ttu-id="5e059-244">Chromium [问题#1055875][CR1055875]</span><span class="sxs-lookup"><span data-stu-id="5e059-244">Chromium issue [#1055875][CR1055875]</span></span>  

### <span data-ttu-id="5e059-245">性能面板更新</span><span class="sxs-lookup"><span data-stu-id="5e059-245">Performance panel updates</span></span>  

#### <span data-ttu-id="5e059-246">JavaScript 编译缓存信息（Performance 面板中）</span><span class="sxs-lookup"><span data-stu-id="5e059-246">JavaScript compilation cache information in Performance panel</span></span>  

<span data-ttu-id="5e059-247">[JavaScript 编译缓存信息现在][V8DevCodeCaching] 始终显示在性能面板的"摘要"选项卡中。</span><span class="sxs-lookup"><span data-stu-id="5e059-247">[JavaScript compilation cache information][V8DevCodeCaching] is now always displayed in the Summary tab of the Performance panel.</span></span>  <span data-ttu-id="5e059-248">以前，如果未发生代码代码并未显示与代码转换相关的任何内容，则 DevTools 未显示任何与代码转换相关内容。</span><span class="sxs-lookup"><span data-stu-id="5e059-248">Previously, DevTools did not show anything related to code caching if code caching did not happen.</span></span>  

:::image type="complex" source="../../media/2020/06/js-compilation-cache.msft.png" alt-text="JavaScript 编译缓存信息" lightbox="../../media/2020/06/js-compilation-cache.msft.png":::
   <span data-ttu-id="5e059-250">JavaScript 编译缓存信息</span><span class="sxs-lookup"><span data-stu-id="5e059-250">JavaScript compilation cache information</span></span>  
:::image-end:::  

<span data-ttu-id="5e059-251">Chromium [#912581][CR912581]</span><span class="sxs-lookup"><span data-stu-id="5e059-251">Chromium issue [#912581][CR912581]</span></span>  

#### <span data-ttu-id="5e059-252">"性能"面板中的导航计时对齐方式</span><span class="sxs-lookup"><span data-stu-id="5e059-252">Navigation timing alignment in the Performance panel</span></span>  

<span data-ttu-id="5e059-253">用于 **根据** 录制开始时间在标尺中显示时间的时间面板。</span><span class="sxs-lookup"><span data-stu-id="5e059-253">The **Performance** panel used to show times in the rulers based on when the recording started.</span></span>  <span data-ttu-id="5e059-254">对于用户导航的录制计时，计时已更改，其中 DevTools 现在显示相对于导航的标尺时间。</span><span class="sxs-lookup"><span data-stu-id="5e059-254">The timing has now changed for recordings where the user navigates, where DevTools now shows ruler times relative to the navigation instead.</span></span>  

:::image type="complex" source="../../media/2020/06/nav-timing.msft.png" alt-text="在 Performance 面板中对齐导航计时" lightbox="../../media/2020/06/nav-timing.msft.png":::
   <span data-ttu-id="5e059-256">在 Performance 面板中对齐 **导航计** 时</span><span class="sxs-lookup"><span data-stu-id="5e059-256">Align navigation timing in **Performance** panel</span></span>  
:::image-end:::  

<span data-ttu-id="5e059-257">"首次画图"、"第一画图"、"第一画图"和"最大内容画图"事件更新为相对于导航 `DOMContentLoaded` 开始的开头，这意味着计时匹配由你报告的排时 `PerformanceObserver` 匹配。</span><span class="sxs-lookup"><span data-stu-id="5e059-257">The times for `DOMContentLoaded`, First Paint, First Contentful Paint, and Largest Contentful Paint events are updated to be relative to the start of the navigation, which means the timing matches the timings reported by `PerformanceObserver`.</span></span>  

<span data-ttu-id="5e059-258">Chromium [问题#974550][CR974550]</span><span class="sxs-lookup"><span data-stu-id="5e059-258">Chromium issue [#974550][CR974550]</span></span>  

### <span data-ttu-id="5e059-259">断点、条件断点和日志点的新图标</span><span class="sxs-lookup"><span data-stu-id="5e059-259">New icons for breakpoints, conditional breakpoints, and logpoints</span></span>  

<span data-ttu-id="5e059-260">" **源** 语言"面板提供用于断点、条件断点和逻辑的新设计。</span><span class="sxs-lookup"><span data-stu-id="5e059-260">The **Sources** panel has new designs for breakpoints, conditional breakpoints, and logpoints.</span></span>  <span data-ttu-id="5e059-261">断点由复数环表示，就像[VS][VSCode]代码和信[Visual Studio。][VS]</span><span class="sxs-lookup"><span data-stu-id="5e059-261">Breakpoints are represented by a red circle, just like [VS Code][VSCode] and [Visual Studio][VS].</span></span>  <span data-ttu-id="5e059-262">为区分条件断点和登录点都添加图标。</span><span class="sxs-lookup"><span data-stu-id="5e059-262">Icons are added to differentiate conditional breakpoints and logpoints.</span></span>  

:::image type="complex" source="../../media/2020/06/breakpoints.msft.png" alt-text="断点" lightbox="../../media/2020/06/breakpoints.msft.png":::
   <span data-ttu-id="5e059-264">断点</span><span class="sxs-lookup"><span data-stu-id="5e059-264">Breakpoints</span></span>  
:::image-end:::  

<span data-ttu-id="5e059-265">Chromium [问题#1041830][CR1041830]</span><span class="sxs-lookup"><span data-stu-id="5e059-265">Chromium issue [#1041830][CR1041830]</span></span>  

## <span data-ttu-id="5e059-266">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="5e059-266">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="5e059-267">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="5e059-267">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="5e059-268">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="5e059-268">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="5e059-269">与 Microsoft Edge DevTools 团队联系</span><span class="sxs-lookup"><span data-stu-id="5e059-269">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge (Chromium) 开发人员工具 |Microsoft 文档"  
[DevtoolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu "使用 Microsoft Edge DevTools 命令菜单 |Microsoft 文档"
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "绘图器 - 自定义 Microsoft Edge 开发工具 |Microsoft 文档"
[DevtoolsExperimentalFeaturesTurnOn]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "启用实用功能 - 实用功能 |Microsoft 文档"  
[DevtoolsIssues]: /microsoft-edge/devtools-guide-chromium/issues "查找并解决 Microsoft Edge DevTools 问题工具的问题 |Microsoft 文档"
[DevtoolsSourcesEditCssJavascript]: /microsoft-edge/devtools-guide-chromium/sources#edit-css-and-javascript "编辑 CSS 和 JavaScript - 源面板概述 |Microsoft 文档"  
[DevtoolsNetworkIndexLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "记录网络活动 - 在 Microsoft Edge DevTools 中检查网络活动 |Microsoft 文档"

[CodepenZoherghadyaliAbdgrpz]: https://codepen.io/zoherghadyali/full/abdGrPZ "CSS 内的框架的样式编辑 |CodePen"
[CodepenZoherghadyaliZyrjgdJ]: https://codepen.io/zoherghadyali/full/zYrjgdJ "将重复的消息发送到控制台 |CodePen"
[CodepenRachelweilYzwBzKM]: https://codepen.io/hxlnt/full/YzwBzKM "CSS 网格规划器示例 |CodePen"

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  

[CR772558]: https://crbug.com/772558 "DevTools：更新到修简版 |Chromium bug"  
[CR800028]: https://crbug.com/800028 "Chrome 更新 | 后，开发人员工具编辑器中的重复线快捷方式无法正常工作 |Chromium bug"  
[CR912581]: https://crbug.com/912581 "公开 DevTools 中的 V8 编码存档的脚本/about：tracing |Chromium bug"  
[CR946975]: https://crbug.com/946975 "DevTools 样式边栏不支持构造样式表 |Chromium bug"  
[CR955497]: https://crbug.com/955497 "PWA 的应用图标快捷菜单|Chromium bug"  
[CR974550]: https://crbug.com/974550 "指标在 Perf 面板和性能Observer |Chromium bug"  
[CR1041830]: https://crbug.com/1041830 "改善断点的颜色 |Chromium bug"  
[CR1055875]: https://crbug.com/1055875 "关闭并重新打开开发人员工具 |后，选定上下文设置仅保留主机设置的值Chromium bug"  
[CR1066579]: https://crbug.com/1066579 "DevTools：在网络面板中显示对每个请求的 ServiceWorkers 提取时间线 |Chromium bug"  
[CR1071432]: https://crbug.com/1071432 "很多普通开发人员体验 |Chromium bug"  
[CR1073899]: https://crbug.com/1073899 "已计算的样式选项卡在响应模式中消失|Chromium bug"  
[CR1073903]: https://crbug.com/1073903 "DevTools：语法突出显示不适用于私有字段 |Chromium bug"  
[CR1082963]: https://crbug.com/1082963 "无法禁用主机类似消息行为|Chromium bug"  
[CR1083214]: https://crbug.com/1083214 "该链接不支持可选链接 |Chromium bug"  
[CR1083797]: https://crbug.com/1083797 "为 Nullish coal 定向考虑预出打印中断的问题Chromium bug"  
[CR1096008]: https://crbug.com/1096008 "删除 FMP |Chromium bug"  
[CR1047356]: https://crbug.com/1047356 "CSS 网格/弹性 Xbox/表格工具 |Chromium bug"  
[CR1093687]: https://crbug.com/1093687 "创建用于创建和重播合规网络请求的工具 |Chromium bug"  
[CR1070378]: https://crbug.com/1070378 "将 Webhint 集成到 DevTools |Chromium bug"  
[CR1069404]: https://crbug.com/1069404 "[开发工具] 小组件弹出窗口太窄]Chromium bug"  
[CR897944]: https://crbug.com/897944 "可拖动开发人员面板 |Chromium bug"

[GithubGoogleChromeLighthouse600]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.0.0 "v6.0.0 - GoogleChrome/lighthouse |GitHub"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新问题 - MicrosoftDocs/edge-developer"  

[MdnShadowDom]: https://developer.mozilla.org/docs/Web/Web_Components/Using_shadow_DOM "使用"shadow DOM"MDN"

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download/ "Microsoft Edge 预览频道"  

[VS]: https://visualstudio.microsoft.com/ "Visual Studio"
[VSCode]: https://code.visualstudio.com/ "Visual Studio代码"  

[CsswgDraftsCssom]: https://drafts.csswg.org/cssom "CSS 对象模型 (CSSOM) |工作组编辑器草稿的 W3C CSS 工作"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  

[V8DevClassFieldsPrivate]: https://v8.dev/features/class-fields#private-class-fields "私有类字段 - 公共类字段和私有类字段 |V8。开发者"  
[V8DevCodeCaching]: https://v8.dev/blog/code-caching-for-devs "适用于 JavaScript 开发人员的代码库 |V8。开发者"  
[V8DevNullishCoalescing]: https://v8.dev/features/nullish-coalescing "Nullish coalescing |V8。开发者"  
[V8DevOptionalChaining]: https://v8.dev/features/optional-chaining "可选链接 |V8。开发者"  

[WebhintMain]: https://webhint.io "Webhint"  

[WicgConstructStylesheet]: https://wicg.github.io/construct-stylesheets/ "构造样式表对象 |Web Incubator CG"

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
> <span data-ttu-id="5e059-318">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="5e059-318">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5e059-319">原始页面位于此处，[由 Jecelyn Yeen][JecelynYeen] \ (Developer advocate， Chrome DevTools\) 。 [here](https://developers.google.com/web/updates/2020/06/devtools/index)</span><span class="sxs-lookup"><span data-stu-id="5e059-319">The original page is found [here](https://developers.google.com/web/updates/2020/06/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="5e059-321">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="5e059-321">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
