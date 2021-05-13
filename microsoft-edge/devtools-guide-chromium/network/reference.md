---
description: Microsoft Edge 开发人员工具网络面板功能的综合参考。
title: 网络分析参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: bdb1145e7ee8ed7865b68f9fd632c4b1a30007e9
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564831"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="network-analysis-reference"></a><span data-ttu-id="4a9a6-104">网络分析参考</span><span class="sxs-lookup"><span data-stu-id="4a9a6-104">Network Analysis reference</span></span>  

<span data-ttu-id="4a9a6-105">在此 Microsoft Edge 开发工具网络分析功能的全面参考中，探索分析页面加载方式的新方法。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-105">Discover new ways to analyze how your page loads in this comprehensive reference of Microsoft Edge DevTools network analysis features.</span></span>  

## <a name="record-network-requests"></a><span data-ttu-id="4a9a6-106">记录网络请求</span><span class="sxs-lookup"><span data-stu-id="4a9a6-106">Record network requests</span></span>  

<span data-ttu-id="4a9a6-107">默认情况下，只要开发人员工具处于打开状态，它就会在“**网络**”工具中记录所有网络请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-107">By default, DevTools record all network requests in the **Network** tool, so long as DevTools is open.</span></span>  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="“网络”面板" lightbox="../media/network-network-panel.msft.png":::
   <span data-ttu-id="4a9a6-109">“**网络**”工具</span><span class="sxs-lookup"><span data-stu-id="4a9a6-109">The **Network** tool</span></span>  
:::image-end:::  

### <a name="stop-recording-network-requests"></a><span data-ttu-id="4a9a6-110">停止记录网络请求</span><span class="sxs-lookup"><span data-stu-id="4a9a6-110">Stop recording network requests</span></span>  

<span data-ttu-id="4a9a6-111">若要停止记录请求，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-111">To stop recording requests, complete the following steps.</span></span>  

1.  <span data-ttu-id="4a9a6-112">在“**网络**”工具上，选择“**停止记录网络日志**（“![停止记录网络日志](../media/record-on-icon.msft.png)”）。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-112">On the **Network** tool, choose **Stop recording network log** \(![Stop recording network log](../media/record-on-icon.msft.png)\).</span></span>  <span data-ttu-id="4a9a6-113">它变为灰色，表示开发人员工具不再记录请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-113">It turns grey to indicate that DevTools is no longer recording requests.</span></span>  
1.  <span data-ttu-id="4a9a6-114">当“**网络**”工具成为焦点时，选择 `Control`+`E`（Windows、Linux）或 `Command`+`E`(macOS)。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-114">Select `Control`+`E` \(Windows, Linux\) or `Command`+`E` \(macOS\) while the **Network** tool is in focus.</span></span>  

### <a name="clear-requests"></a><span data-ttu-id="4a9a6-115">清除请求</span><span class="sxs-lookup"><span data-stu-id="4a9a6-115">Clear requests</span></span>  

<span data-ttu-id="4a9a6-116">在“**网络**”工具上选择“**清除**”（“![清除](../media/clear-requests-icon.msft.png)”），从“请求”表中清除所有请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-116">Choose **Clear** \(![Clear](../media/clear-requests-icon.msft.png)\) on the **Network** tool to clear all requests from the Requests table.</span></span>  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text="“清除”按钮" lightbox="../media/network-network-clear-button.msft.png":::
   <span data-ttu-id="4a9a6-118">“**清除**”按钮</span><span class="sxs-lookup"><span data-stu-id="4a9a6-118">The **Clear** button</span></span>  
:::image-end:::  

### <a name="save-requests-across-page-loads"></a><span data-ttu-id="4a9a6-119">跨页面加载保存请求</span><span class="sxs-lookup"><span data-stu-id="4a9a6-119">Save requests across page loads</span></span>  

<span data-ttu-id="4a9a6-120">若要跨页面加载保存请求，请在“**网络**”工具上启用“**保留日志**”复选框。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-120">To save requests across page loads, on the **Network** tool, turn on the **Preserve log** checkbox.</span></span>  <span data-ttu-id="4a9a6-121">开发人员工具将保存所有请求，直到禁用“**保留日志**”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-121">DevTools saves all requests until you disable **Preserve log**.</span></span>  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text="“保留日志”复选框" lightbox="../media/network-network-preserve-log.msft.png":::
   <span data-ttu-id="4a9a6-123">“**保留日志**”复选框</span><span class="sxs-lookup"><span data-stu-id="4a9a6-123">The **Preserve Log** checkbox</span></span>  
:::image-end:::  

### <a name="capture-screenshots-during-page-load"></a><span data-ttu-id="4a9a6-124">在页面加载期间捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="4a9a6-124">Capture screenshots during page load</span></span>  

<span data-ttu-id="4a9a6-125">捕获屏幕截图以分析在等待页面加载时为用户显示的内容。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-125">Capture screenshots to analyze what displays for users while waiting for your page to load.</span></span>  

<span data-ttu-id="4a9a6-126">若要启用屏幕截图，请选择“**网络设置**”，然后在“**网络**”工具上，启用“**捕获屏幕截图**”复选框。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-126">To enable screenshots, choose **Network settings**, and on the **Network** tool, turn on the **Capture screenshots** checkbox.</span></span>  

<span data-ttu-id="4a9a6-127">在“**网络**”工具成为焦点时刷新页面以捕获屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-127">Refresh the page while the **Network** tool is in focus to capture screenshots.</span></span>  

<span data-ttu-id="4a9a6-128">截图后，可通过以下方式与之交互。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-128">After capturing a screenshot, you interact with it in the following ways.</span></span>  

*   <span data-ttu-id="4a9a6-129">将鼠标悬停在屏幕截图上以显示截图的位置。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-129">Hover on a screenshot to display the point at which that screenshot was captured.</span></span>  <span data-ttu-id="4a9a6-130">“**概述**”格上将显示一条黄线。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-130">A yellow line is displayed on the **Overview** pane.</span></span>  
*   <span data-ttu-id="4a9a6-131">选择屏幕的缩略图以过滤截图后发生的任何请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-131">Choose the thumbnail of a screen to filter out any requests that occurred after the screenshot was captured.</span></span>  
*   <span data-ttu-id="4a9a6-132">双击缩略图可将其放大。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-132">Double-click a thumbnail to zoom into it.</span></span>  

:::image type="complex" source="../media/network-network-screenshot-hover.msft.png" alt-text="将鼠标悬停在屏幕截图上" lightbox="../media/network-network-screenshot-hover.msft.png":::
   <span data-ttu-id="4a9a6-134">将鼠标悬停在屏幕截图上</span><span class="sxs-lookup"><span data-stu-id="4a9a6-134">Hover on a screenshot</span></span>  
:::image-end:::  

<!--  ### Replay XHR request  -->

<!--  To replay an XHR request, hover on the request in the Requests table, open the contextual menu \(right-click\), and choose **Replay XHR**.  -->

<!--  
:::image type="complex" source="../media/network-replay-xhr.msft.png" alt-text="Choose Replay XHR" lightbox="../media/network-replay-xhr.msft.png":::
   Choose Replay XHR  
:::image-end:::  
-->  

## <a name="change-loading-behavior"></a><span data-ttu-id="4a9a6-135">更改加载行为</span><span class="sxs-lookup"><span data-stu-id="4a9a6-135">Change loading behavior</span></span>  

### <a name="emulate-a-first-time-visitor-by-disabling-the-browser-cache"></a><span data-ttu-id="4a9a6-136">通过禁用浏览器缓存来模拟首次访问者</span><span class="sxs-lookup"><span data-stu-id="4a9a6-136">Emulate a first-time visitor by disabling the browser cache</span></span>  

<span data-ttu-id="4a9a6-137">要模拟首次用户体验你的网站的方式，请启用“**禁用缓存**”复选框。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-137">To emulate how a first-time user experiences your site, turn on the **Disable cache** checkbox.</span></span>  <span data-ttu-id="4a9a6-138">开发工具禁用浏览器缓存。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-138">DevTools disables the browser cache.</span></span>  <span data-ttu-id="4a9a6-139">此功能更准确地模拟了首次用户的体验，因为在重复访问时，请求是从浏览器缓存中获得的。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-139">This feature more accurately emulates a first-time user's experience, because requests are served from the browser cache on repeat visits.</span></span>  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text="“禁用缓存”复选框" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   <span data-ttu-id="4a9a6-141">“**禁用缓存**”复选框</span><span class="sxs-lookup"><span data-stu-id="4a9a6-141">The **Disable Cache** checkbox</span></span>  
:::image-end:::  

#### <a name="disable-the-browser-cache-from-the-network-conditions-drawer"></a><span data-ttu-id="4a9a6-142">从“网络条件”抽屉中禁用浏览器缓存</span><span class="sxs-lookup"><span data-stu-id="4a9a6-142">Disable the browser cache from the Network Conditions drawer</span></span>  

<span data-ttu-id="4a9a6-143">如果要在其他开发工具面板中工作时禁用缓存，请使用“网络条件”抽屉。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-143">If you want to disable the cache while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="4a9a6-144">打开“**网络条件**”抽屉。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-144">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="4a9a6-145">启用\（或关闭\）“**禁用缓存**”复选框。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-145">Turn on \(or off\) the **Disable cache** checkbox.</span></span>  

<!--todo: add network condition section when available -->  

### <a name="manually-clear-the-browser-cache"></a><span data-ttu-id="4a9a6-146">手动清除浏览器缓存</span><span class="sxs-lookup"><span data-stu-id="4a9a6-146">Manually clear the browser cache</span></span>  

<span data-ttu-id="4a9a6-147">要随时手动清除浏览器缓存，请打开“请求”表中任意位置的上下文菜单\（右键单击\），然后选择“**清除浏览器缓存**”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-147">To manually clear the browser cache at any time, open the contextual menu \(right-click\) anywhere in the Requests table and choose **Clear Browser Cache**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="选择“清除浏览器缓存”" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   <span data-ttu-id="4a9a6-149">选择“**清除浏览器缓存**”</span><span class="sxs-lookup"><span data-stu-id="4a9a6-149">Choose **Clear Browser Cache**</span></span>  
:::image-end:::  

### <a name="emulate-offline"></a><span data-ttu-id="4a9a6-150">模拟脱机</span><span class="sxs-lookup"><span data-stu-id="4a9a6-150">Emulate offline</span></span>  

<span data-ttu-id="4a9a6-151">一种称为“[渐进式 Web 应用][DevtoolsProgressiveWebApps]”的新 web 应用程序，，可在**服务人员**的帮助下脱机运行。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-151">A new class of web apps, named [Progressive Web Apps][DevtoolsProgressiveWebApps], functions offline with the help of **service workers**.</span></span>  <span data-ttu-id="4a9a6-152">在构建这种类型的应用程序时，快速模拟没有数据连接的设备可能会很有用。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-152">You may find it useful to quickly simulate a device that has no data connection when you are building this type of app.</span></span>  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

<span data-ttu-id="4a9a6-153">选择“**联机**”下拉菜单，在“**预设**”下搜索，然后选择“**脱机**”以模拟脱机网络体验。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-153">Choose the **Online** dropdown menu, search under **Presets**, and choose **Offline** to simulate an offline network experience.</span></span>  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text="“脱机”下拉菜单" lightbox="../media/network-network-offline-dropdown.msft.png":::
   <span data-ttu-id="4a9a6-155">“**脱机**”下拉菜单</span><span class="sxs-lookup"><span data-stu-id="4a9a6-155">The **Offline** dropdown menu</span></span>  
:::image-end:::  

### <a name="emulate-slow-network-connections"></a><span data-ttu-id="4a9a6-156">模拟慢速网络连接</span><span class="sxs-lookup"><span data-stu-id="4a9a6-156">Emulate slow network connections</span></span>  

<span data-ttu-id="4a9a6-157">从“**在线**”下拉菜单中模拟慢速 3G、快速 3G 和其他连接速度。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-157">Emulate Slow 3G, Fast 3G, and other connection speeds from the **Online** dropdown menu.</span></span>  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text="“限制”下拉菜单" lightbox="../media/network-network-throttling-menu.msft.png":::
   <span data-ttu-id="4a9a6-159">“**限制**”下拉菜单</span><span class="sxs-lookup"><span data-stu-id="4a9a6-159">The **Throttling** dropdown menu</span></span>  
:::image-end:::  

<span data-ttu-id="4a9a6-160">可以选择不同的预设，如慢速 3G 或快速 3G。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-160">You may choose from different presets, such as Slow 3G or Fast 3G.</span></span>  <span data-ttu-id="4a9a6-161">若要添加自定义预设，请打开“限制”菜单，然后选择“**自定义**” > “**添加**”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-161">To add your own custom presets, open the Throttling menu, and choose **Custom** > **Add**.</span></span>  

<span data-ttu-id="4a9a6-162">开发人员工具会在“**网络**”工具旁边显示一个警告图标，提醒已启用限制。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-162">DevTools displays a warning icon next to the **Network** tool to remind you that throttling is enabled.</span></span>  

#### <a name="emulate-slow-network-connections-from-the-network-conditions-drawer"></a><span data-ttu-id="4a9a6-163">从“网络条件”抽屉模拟慢速网络连接</span><span class="sxs-lookup"><span data-stu-id="4a9a6-163">Emulate slow network connections from the Network Conditions drawer</span></span>  

<span data-ttu-id="4a9a6-164">如果要在其他开发工具面板中工作时限制网络连接，请使用“网络条件”抽屉。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-164">If you want to throttle the network connection while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="4a9a6-165">打开“**网络条件**”抽屉。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-165">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="4a9a6-166">从“**限制**”菜单中选择连接速度。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-166">Choose your connection speed from the **Throttling** menu.</span></span>  

<!--todo: add network condition section when available -->  

### <a name="manually-clear-browser-cookies"></a><span data-ttu-id="4a9a6-167">手动清除浏览器 Cookie</span><span class="sxs-lookup"><span data-stu-id="4a9a6-167">Manually clear browser cookies</span></span>  

<span data-ttu-id="4a9a6-168">若要随时手动清除浏览器 Cookie，请将鼠标悬停在“请求”表中的任意位置，打开上下文菜单\（右键单击\），然后选择“**清除浏览器 Cookie**”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-168">To manually clear browser cookies at any time, hover anywhere in the Requests table, open the contextual menu \(right-click\), and choose **Clear Browser Cookies**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="选择“清除浏览器 Cookie”" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   <span data-ttu-id="4a9a6-170">选择“**清除浏览器 Cookie**”</span><span class="sxs-lookup"><span data-stu-id="4a9a6-170">Choose **Clear Browser Cookies**</span></span>  
:::image-end:::  

### <a name="override-the-user-agent"></a><span data-ttu-id="4a9a6-171">替代用户代理</span><span class="sxs-lookup"><span data-stu-id="4a9a6-171">Override the user agent</span></span>  

<span data-ttu-id="4a9a6-172">要手动替代用户代理，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-172">To manually override the user agent, use the following steps.</span></span>  

1.  <span data-ttu-id="4a9a6-173">打开“**网络条件**”抽屉。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-173">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="4a9a6-174">关闭“**自动选择**”复选框。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-174">Turn off the **Select automatically** checkbox.</span></span>  
1.  <span data-ttu-id="4a9a6-175">从菜单中选择用户代理选项，或在文本框中输入自定义选项。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-175">Choose a user agent option from the menu, or enter a custom one in the text box.</span></span>  

<!--todo: add network condition section when available -->  

## <a name="filter-requests"></a><span data-ttu-id="4a9a6-176">筛选请求</span><span class="sxs-lookup"><span data-stu-id="4a9a6-176">Filter requests</span></span>  

### <a name="filter-requests-by-properties"></a><span data-ttu-id="4a9a6-177">按属性筛选请求</span><span class="sxs-lookup"><span data-stu-id="4a9a6-177">Filter requests by properties</span></span>  

<span data-ttu-id="4a9a6-178">使用“**筛选器**”本框按属性（如请求的域或大小）筛选请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-178">Use the **Filter** text box to filter requests by properties, such as the domain or size of the request.</span></span>  

<span data-ttu-id="4a9a6-179">如果未显示文本框，则“**筛选器**”窗格可能已隐藏。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-179">If the text box is not displayed, the **Filters** pane is probably hidden.</span></span>  
<span data-ttu-id="4a9a6-180">有关详细信息，请导航到[“隐藏筛选器”窗格](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-180">For more information, navigate to [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text="“筛选器”文本框" lightbox="../media/network-network-filters-textbox.msft.png":::
   <span data-ttu-id="4a9a6-182">“**筛选器**”文本框</span><span class="sxs-lookup"><span data-stu-id="4a9a6-182">The **Filter** text box</span></span>  
:::image-end:::  

<span data-ttu-id="4a9a6-183">用空格分隔每个属性，可以同时使用多个属性。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-183">You may use multiple properties simultaneously by separating each property with a space.</span></span>  <span data-ttu-id="4a9a6-184">例如，`mime-type:image/png larger-than:1K` 显示大于 1 KB 的所有 PNG。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-184">For example, `mime-type:image/png larger-than:1K` displays all PNGs that are larger than 1 kilobyte.</span></span>  <span data-ttu-id="4a9a6-185">多属性筛选器相当于 `AND` 操作。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-185">The multi-property filters are equivalent to `AND` operations.</span></span>  `OR` <span data-ttu-id="4a9a6-186">当前不支持操作。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-186">operations are currently not supported.</span></span>  

<span data-ttu-id="4a9a6-187">支持属性的完整列表。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-187">The complete list of supported properties.</span></span>  

| <span data-ttu-id="4a9a6-188">属性</span><span class="sxs-lookup"><span data-stu-id="4a9a6-188">Property</span></span> | <span data-ttu-id="4a9a6-189">详细信息</span><span class="sxs-lookup"><span data-stu-id="4a9a6-189">Details</span></span> |  
|:--- | :--- |  
| `domain` | <span data-ttu-id="4a9a6-190">仅显示指定域中的资源。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-190">Only display resources from the specified domain.</span></span>  <span data-ttu-id="4a9a6-191">可以使用通配符\(`*`\) 包含多个域。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-191">You may use a wildcard character \(`*`\) to include multiple domains.</span></span>  <span data-ttu-id="4a9a6-192">例如，`*.com` 显示以 `.com` 结尾的所有域名中的资源。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-192">For example, `*.com` displays resources from all domain names ending in `.com`.</span></span>  <span data-ttu-id="4a9a6-193">开发工具在自动完成下拉菜单中填充找到的所有域。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-193">DevTools populate the autocomplete dropdown menu with all of the domains that are found.</span></span> |  
| `has-response-header` | <span data-ttu-id="4a9a6-194">显示包含指定 HTTP 响应头的资源。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-194">Displays the resources that contain the specified HTTP response header.</span></span>  <span data-ttu-id="4a9a6-195">开发工具用找到的所有响应头填充“自动完成”下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-195">DevTools populate the autocomplete dropdown with all of the response headers that are found.</span></span> |  
| `is` | <span data-ttu-id="4a9a6-196">用 `is:running` 查找 `WebSocket` 资源。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-196">Use `is:running` to find `WebSocket` resources.</span></span> |  
| `larger-than` | <span data-ttu-id="4a9a6-197">以字节为单位显示大于指定大小的资源。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-197">Displays resources that are larger than the specified size, in bytes.</span></span>  <span data-ttu-id="4a9a6-198">将值设置为 `1000` 相当于将值设置为 `1k`。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-198">Setting a value of `1000` is equivalent to setting a value of `1k`.</span></span> |  
| `method` | <span data-ttu-id="4a9a6-199">显示通过指定的 HTTP 方法类型检索的资源。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-199">Displays resources that were retrieved over a specified HTTP method type.</span></span>  <span data-ttu-id="4a9a6-200">开发工具用找到的所有 HTTP 方法填充下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-200">DevTools populate the dropdown with all of the HTTP methods  that are found.</span></span> |  
| `mime-type` | <span data-ttu-id="4a9a6-201">显示指定 MIME 类型的资源。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-201">Displays resources of a specified MIME type.</span></span>  <span data-ttu-id="4a9a6-202">开发工具用找到的所有 MIME 类型填充下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-202">DevTools populate the dropdown with all MIME types  that are found.</span></span> |  
| `mixed-content` | <span data-ttu-id="4a9a6-203">显示所有混合内容资源 \(`mixed-content:all`\) 或仅显示当前显示的内容资源 \(`mixed-content:displayed`\)。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-203">Show all mixed content resources \(`mixed-content:all`\) or just the ones that are currently displayed \(`mixed-content:displayed`\).</span></span> |  
| `scheme` | <span data-ttu-id="4a9a6-204">显示通过未受保护的 HTTP \(`scheme:http`\) 或受保护的 HTTPS \(`scheme:https`\) 检索的资源。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-204">Displays resources retrieved over unprotected HTTP \(`scheme:http`\) or protected HTTPS \(`scheme:https`\).</span></span> |  
| `set-cookie-domain` | <span data-ttu-id="4a9a6-205">显示具有与指定值匹配的 `Domain` 属性的 `Set-Cookie` 标头的资源。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-205">Displays resources that have a `Set-Cookie` header with a `Domain` attribute that matches the specified value.</span></span>  <span data-ttu-id="4a9a6-206">开发工具用找到的所有 Cookie 域填充“自动完成”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-206">DevTools populate the autocomplete with all of the cookie domains that are found.</span></span> |  
| `set-cookie-name` | <span data-ttu-id="4a9a6-207">显示具有名称与指定值匹配的 `Set-Cookie` 标头的资源。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-207">Displays resources that have a `Set-Cookie` header with a name that matches the specified value.</span></span>  <span data-ttu-id="4a9a6-208">开发工具用找到的所有 Cookie 名称填充“自动完成”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-208">DevTools populate the autocomplete with all of the cookie names that are found.</span></span> |  
| `set-cookie-value` | <span data-ttu-id="4a9a6-209">显示具有值与指定值匹配的 `Set-Cookie` 标头的资源。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-209">Displays resources that have a `Set-Cookie` header with a value that matches the specified value.</span></span>  <span data-ttu-id="4a9a6-210">开发工具用找到的所有 Cookie 值填充“自动完成”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-210">DevTools populate the autocomplete with all of the cookie values that are found.</span></span> |  
| `status-code` | <span data-ttu-id="4a9a6-211">显示与特定 HTTP 状态代码匹配的资源。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-211">Displays resources that match the specific HTTP status code.</span></span>  <span data-ttu-id="4a9a6-212">开发工具用找到的所有状态代码填充“自动完成”下拉菜单。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-212">DevTools populates the autocomplete dropdown menu with all of the status codes that are found.</span></span> |  

### <a name="filter-requests-by-type"></a><span data-ttu-id="4a9a6-213">按类型筛选请求</span><span class="sxs-lookup"><span data-stu-id="4a9a6-213">Filter requests by type</span></span>  

<span data-ttu-id="4a9a6-214">若要按请求类型筛选请求，请选择“**网络**”工具上的以下按钮之一。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-214">To filter requests by request type, choose the one of the following buttons on the **Network** tool.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-215">XHR</span><span class="sxs-lookup"><span data-stu-id="4a9a6-215">XHR</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-216">JS</span><span class="sxs-lookup"><span data-stu-id="4a9a6-216">JS</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-217">CSS</span><span class="sxs-lookup"><span data-stu-id="4a9a6-217">CSS</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-218">Img</span><span class="sxs-lookup"><span data-stu-id="4a9a6-218">Img</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-219">Media</span><span class="sxs-lookup"><span data-stu-id="4a9a6-219">Media</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-220">字体</span><span class="sxs-lookup"><span data-stu-id="4a9a6-220">Font</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-221">Doc</span><span class="sxs-lookup"><span data-stu-id="4a9a6-221">Doc</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-222">WS</span><span class="sxs-lookup"><span data-stu-id="4a9a6-222">WS</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-223">WebSocket。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-223">WebSocket.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-224">Manifest</span><span class="sxs-lookup"><span data-stu-id="4a9a6-224">Manifest</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-225">Other</span><span class="sxs-lookup"><span data-stu-id="4a9a6-225">Other</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-226">未列出的任何其他类型。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-226">Any other type not listed.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="4a9a6-227">如果按钮不显示，则“**筛选器**”窗格可能会隐藏。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-227">If the buttons do not display, the **Filters** pane may be hidden.</span></span>  
<span data-ttu-id="4a9a6-228">有关详细信息，请导航到[“隐藏筛选器”窗格](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-228">For more information, navigate to [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

<span data-ttu-id="4a9a6-229">要同时启用多个类型筛选器，请按住 `Control` \(Windows、Linux\) 或 `Command` \(macOS\)，然后选择。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-229">To enable multiple type filters simultaneously, hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and then choose.</span></span>  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="使用类型筛选器来显示 JS、CSS 和文档资源" lightbox="../media/network-network-type-filters.msft.png":::
   <span data-ttu-id="4a9a6-231">使用类型筛选器来显示 JS、CSS 和文档资源</span><span class="sxs-lookup"><span data-stu-id="4a9a6-231">Use the Type filters to display JS, CSS, and Document resources</span></span>  
:::image-end:::  

### <a name="filter-requests-by-time"></a><span data-ttu-id="4a9a6-232">按时间筛选请求</span><span class="sxs-lookup"><span data-stu-id="4a9a6-232">Filter requests by time</span></span>  

<span data-ttu-id="4a9a6-233">在“**概述**”窗格中选择并向左或向右拖动，以仅显示在该时间段内处于活动状态的请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-233">Choose and drag left or right on the **Overview** pane to only display requests that were active during that time frame.</span></span>  <span data-ttu-id="4a9a6-234">筛选器为非独占。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-234">The filter is inclusive.</span></span>  <span data-ttu-id="4a9a6-235">将显示在突出显示的时间内处于活动状态的任何请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-235">Any request that was active during the highlighted time is shown.</span></span>  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="筛选出处于非活动状态约 300 毫秒的所有请求" lightbox="../media/network-network-overview-filter.msft.png":::
   <span data-ttu-id="4a9a6-237">筛选出处于非活动状态约 300 毫秒的所有请求</span><span class="sxs-lookup"><span data-stu-id="4a9a6-237">Filter out any requests that were inactive around 300 ms</span></span>  
:::image-end:::  

### <a name="hide-data-urls"></a><span data-ttu-id="4a9a6-238">隐藏数据 URL</span><span class="sxs-lookup"><span data-stu-id="4a9a6-238">Hide data URLs</span></span>  

<span data-ttu-id="4a9a6-239">[数据 URL][MDNHTTPDataURIs] 是嵌入到其他文档中的小文件。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-239">[Data URLs][MDNHTTPDataURIs] are small files embedded into other documents.</span></span>  <span data-ttu-id="4a9a6-240">任何显示在“请求”表中以 `data:` 开头的请求都是数据 URL。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-240">Any request that displays in the Requests table that starts with `data:` is a data URL.</span></span>  

<span data-ttu-id="4a9a6-241">若要隐藏请求，请关闭“**隐藏数据 URL**”复选框。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-241">To hide the requests, turn off the **Hide data URLs** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text="“隐藏数据 URL”复选框" lightbox="../media/network-network-hide-data-urls.msft.png":::
   <span data-ttu-id="4a9a6-243">“**隐藏数据 URL**”复选框</span><span class="sxs-lookup"><span data-stu-id="4a9a6-243">The **Hide Data URLs** checkbox</span></span>  
:::image-end:::  

## <a name="sort-requests"></a><span data-ttu-id="4a9a6-244">排序请求</span><span class="sxs-lookup"><span data-stu-id="4a9a6-244">Sort requests</span></span>  

<span data-ttu-id="4a9a6-245">默认情况下，“请求”表中的请求按启动时间排序，但可使用其他条件对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-245">By default, the requests in the Requests table are sorted by initiation time, but you may sort the table using other criteria.</span></span>  

### <a name="sort-by-column"></a><span data-ttu-id="4a9a6-246">按列排序</span><span class="sxs-lookup"><span data-stu-id="4a9a6-246">Sort by column</span></span>  

<span data-ttu-id="4a9a6-247">选择“请求”中任何列的标题以按该列对请求进行排序。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-247">Choose the header of any column in the Requests to sort requests by that column.</span></span>  

### <a name="sort-by-activity-phase"></a><span data-ttu-id="4a9a6-248">按活动阶段排序</span><span class="sxs-lookup"><span data-stu-id="4a9a6-248">Sort by activity phase</span></span>  

<span data-ttu-id="4a9a6-249">要更改瀑布对请求的排序方式，请将鼠标悬停在“请求”表的标题上，打开上下文菜单 \（右键单击\），将鼠标悬停在“**瀑布**”上，然后选择以下选项之一。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-249">To change how the Waterfall sorts requests, hover on the header of the Requests table, open the contextual menu \(right-click\), hover on **Waterfall**, and choose one of the following options.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-250">开始时间</span><span class="sxs-lookup"><span data-stu-id="4a9a6-250">Start Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-251">启动的首个请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-251">The first request that was initiated is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-252">响应时间</span><span class="sxs-lookup"><span data-stu-id="4a9a6-252">Response Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-253">开始下载的首个请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-253">The first request that started downloading is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-254">结束时间</span><span class="sxs-lookup"><span data-stu-id="4a9a6-254">End Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-255">完成的首个请求在顶部。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-255">The first request that finished is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-256">总持续时间</span><span class="sxs-lookup"><span data-stu-id="4a9a6-256">Total Duration</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-257">具有最短连接设置和请求或响应的请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-257">The request with the shortest connection settings and request or response is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-258">延迟</span><span class="sxs-lookup"><span data-stu-id="4a9a6-258">Latency</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-259">等待响应时间最短的请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-259">The request that waited the shortest time for a response is at the top.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="4a9a6-260">这些描述假设每个选项按最短到最长进行排列。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-260">These descriptions assume that each respective option is ranked from shortest to longest.</span></span>  <span data-ttu-id="4a9a6-261">选择“**瀑布**”列的标题以反转顺序。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-261">Choose the header of the **Waterfall** column to reverse the order.</span></span>  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="按总持续时间排序“瀑布”" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   <span data-ttu-id="4a9a6-263">按总持续时间对瀑布进行排序\（每栏中较浅的部分是等待时间，较深的部分是下载字节的时间\）</span><span class="sxs-lookup"><span data-stu-id="4a9a6-263">Sort the Waterfall by total duration  \(The lighter portion of each bar is time spent waiting and the darker portion is time spent downloading bytes\)</span></span>  
:::image-end:::  

## <a name="analyze-requests"></a><span data-ttu-id="4a9a6-264">分析请求</span><span class="sxs-lookup"><span data-stu-id="4a9a6-264">Analyze requests</span></span>  

<span data-ttu-id="4a9a6-265">只要开发人员工具处于打开状态，它就会在“**网络**”工具中记录所有请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-265">So long as DevTools are open, it logs all requests in the **Network** tool.</span></span>  
<span data-ttu-id="4a9a6-266">使用“网络”面板分析请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-266">Use the Network panel to analyze requests.</span></span>  

### <a name="display-a-log-of-requests"></a><span data-ttu-id="4a9a6-267">显示请求日志</span><span class="sxs-lookup"><span data-stu-id="4a9a6-267">Display a log of requests</span></span>  

<span data-ttu-id="4a9a6-268">使用“请求”表可以显示开发工具打开时发出的所有请求的日志。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-268">Use the Requests table to display a log of all requests made while DevTools have been open.</span></span>  <span data-ttu-id="4a9a6-269">若要显示有关每个项目的详细信息，请选择或将鼠标悬停在请求上。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-269">To reveals more information about each item, choose or hover on requests.</span></span>  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="“请求”表" lightbox="../media/network-network-requests-table.msft.png":::
   <span data-ttu-id="4a9a6-271">“请求”表</span><span class="sxs-lookup"><span data-stu-id="4a9a6-271">The Requests table</span></span>  
:::image-end:::  

<span data-ttu-id="4a9a6-272">默认情况下，“请求”表显示以下列。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-272">The Requests table displays the following columns by default.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-273">名称</span><span class="sxs-lookup"><span data-stu-id="4a9a6-273">Name</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-274">资源的文件名或标识符。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-274">The filename of, or an identifier for, the resource.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-275">状态</span><span class="sxs-lookup"><span data-stu-id="4a9a6-275">Status</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-276">HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-276">The HTTP status code.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-277">类型</span><span class="sxs-lookup"><span data-stu-id="4a9a6-277">Type</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-278">请求资源的 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-278">The MIME type of the requested resource.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-279">发起程序</span><span class="sxs-lookup"><span data-stu-id="4a9a6-279">Initiator</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-280">以下对象或进程启动请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-280">The following objects or processes initiate requests.</span></span>  
      
      *   <span data-ttu-id="4a9a6-281">**分析程序** Microsoft Edge 的 HTML 分析程序。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-281">**Parser**  The HTML parser for Microsoft Edge.</span></span>  
      *   <span data-ttu-id="4a9a6-282">**重定向**  HTTP 重定向。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-282">**Redirect**  An HTTP redirect.</span></span>  
      *   <span data-ttu-id="4a9a6-283">**脚本**  JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-283">**Script**  A JavaScript function.</span></span>  
      *   <span data-ttu-id="4a9a6-284">**其他** 其他一些过程或操作，例如使用链接导航到页面或在地址栏中输入 URL。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-284">**Other**  Some other process or action, such as navigating to a page using a link or entering a URL in the address bar.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-285">大小</span><span class="sxs-lookup"><span data-stu-id="4a9a6-285">Size</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-286">服务器传递的响应头和响应正文的组合大小。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-286">The combined size of the response headers plus the response body, as delivered by the server.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-287">时间</span><span class="sxs-lookup"><span data-stu-id="4a9a6-287">Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-288">从请求开始到收到响应中最后一个字节的总持续时间。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-288">The total duration, from the start of the request to the receipt of the final byte in the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="4a9a6-289">瀑布</span><span class="sxs-lookup"><span data-stu-id="4a9a6-289">Waterfall</span></span>](#display-the-timing-relationship-of-requests)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-290">每个请求的活动的可视细分。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-290">A visual breakdown of the activity for each request.</span></span>  
   :::column-end:::
:::row-end:::  

#### <a name="add-or-remove-columns"></a><span data-ttu-id="4a9a6-291">添加或删除列</span><span class="sxs-lookup"><span data-stu-id="4a9a6-291">Add or remove columns</span></span>  

<span data-ttu-id="4a9a6-292">将鼠标悬停在“请求”表的标题上，打开上下文菜单 \（右键单击\），然后选择选项来隐藏或显示它。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-292">Hover on the header of the Requests table, open the contextual menu \(right-click\), and choose an option to hide or show it.</span></span>  <span data-ttu-id="4a9a6-293">当前显示的选项旁边都有复选标记。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-293">Currently displayed options have checkmarks next to each item.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="向“请求”表中添加列" lightbox="../media/network-network-requests-add-column.msft.png":::
   <span data-ttu-id="4a9a6-295">向“请求”表中添加列</span><span class="sxs-lookup"><span data-stu-id="4a9a6-295">Add a column to the Requests table</span></span>  
:::image-end:::  

#### <a name="add-custom-columns"></a><span data-ttu-id="4a9a6-296">添加自定义列</span><span class="sxs-lookup"><span data-stu-id="4a9a6-296">Add custom columns</span></span>  

<span data-ttu-id="4a9a6-297">要向“请求”表中添加自定义列，请将鼠标悬停在“请求”表的标题上，打开上下文菜单\（右键单击\），然后选择“**响应标题**” > “**管理标题列**”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-297">To add a custom column to the Requests table, hover on the header of the Requests table, open the contextual menu \(right-click\), and choose **Response Headers** > **Manage Header Columns**.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="向“请求”表添加自定义列" lightbox="../media/network-network-requests-add-custom.msft.png":::
   <span data-ttu-id="4a9a6-299">向“请求”表添加自定义列</span><span class="sxs-lookup"><span data-stu-id="4a9a6-299">Add a custom column to the Requests table</span></span>  
:::image-end:::  

### <a name="display-the-timing-relationship-of-requests"></a><span data-ttu-id="4a9a6-300">显示请求的计时关系</span><span class="sxs-lookup"><span data-stu-id="4a9a6-300">Display the timing relationship of requests</span></span>  

<span data-ttu-id="4a9a6-301">使用瀑布显示请求的计时关系。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-301">Use the Waterfall to display the timing relationships of requests.</span></span>  
<span data-ttu-id="4a9a6-302">默认情况下，瀑布是按请求的开始时间进行组织的。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-302">The default organization of the Waterfall uses the start time of the requests.</span></span>  
<span data-ttu-id="4a9a6-303">因此，最左边的请求比最右边的请求更早开始。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-303">So, requests that are farther to the left started earlier than the requests that are farther to the right.</span></span>  

<span data-ttu-id="4a9a6-304">要查看对瀑布进行排序的不同方法，请导航到“[按活动阶段排序](#sort-by-activity-phase)”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-304">To review the different ways that you may sort the Waterfall, navigate to [Sort by activity phase](#sort-by-activity-phase).</span></span>  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text="“请求”窗格的“瀑布”列。" lightbox="../media/network-network-requests-waterfall.msft.png":::
   <span data-ttu-id="4a9a6-306">“**请求**”窗格的“瀑布”列。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-306">The Waterfall column of the **Requests** pane</span></span>  
:::image-end:::  

<!-- ### Analyze the frames of a WebSocket Connection  -->

<!--To review the frames of a WebSocket connection, use the following steps.  

1.  Choose the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Choose the **Frames** panel.  The table shows the last 100 frames.  

To refresh the table, re-choose the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
:::image type="complex" source="../media/network-frames.msft.png" alt-text="The Frames panel" lightbox="../media/network-frames.msft.png":::
   The **Frames** panel  
:::image-end:::  
-->

<!--The table contains the following three columns.  

*   **Data**.  The message payload.  If the message is plain text, it is displayed here.  For binary opcodes, this column displays the name and code of the opcode.  The following opcodes are supported: Continuation Frame, Binary Frame, Connection Close Frame, Ping Frame, and Pong Frame.  
*   **Length**.  The length of the message payload, in bytes.  
*   **Time**.  The time when the message was received or sent.  -->

<!--Messages are color-coded according to each type.  

*   Outgoing text messages are light-green.  
*   Incoming text messages are white.  
*   WebSocket opcodes are light-yellow.  
*   Errors are light-red.  -->

### <a name="display-a-preview-of-a-response-body"></a><span data-ttu-id="4a9a6-307">显示响应正文的预览</span><span class="sxs-lookup"><span data-stu-id="4a9a6-307">Display a preview of a response body</span></span>  

<span data-ttu-id="4a9a6-308">若要显示响应正文的预览，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-308">To display a preview of a response body, use the following steps.</span></span>  

1.  <span data-ttu-id="4a9a6-309">在“请求”表的“**名称**”列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-309">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="4a9a6-310">选择“**预览**”面板。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-310">Choose the **Preview** panel.</span></span>  

<span data-ttu-id="4a9a6-311">“预览”选项卡在显示图像时最有用。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-311">The Preview tab is mostly useful to display images.</span></span>  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text="“预览”面板" lightbox="../media/network-network-resources-preview.msft.png":::
   <span data-ttu-id="4a9a6-313">“**预览**”面板</span><span class="sxs-lookup"><span data-stu-id="4a9a6-313">The **Preview** panel</span></span>  
:::image-end:::  

### <a name="display-a-response-body"></a><span data-ttu-id="4a9a6-314">显示响应正文</span><span class="sxs-lookup"><span data-stu-id="4a9a6-314">Display a response body</span></span>  

<span data-ttu-id="4a9a6-315">要显示请求的响应主体，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-315">To display the response body to a request, use the following steps.</span></span>  

1.  <span data-ttu-id="4a9a6-316">在“请求”表的“**名称**”列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-316">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="4a9a6-317">选择“**响应**”面板。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-317">Choose the **Response** panel.</span></span>  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text="“响应”面板" lightbox="../media/network-network-resources-response.msft.png":::
   <span data-ttu-id="4a9a6-319">“**响应**”面板</span><span class="sxs-lookup"><span data-stu-id="4a9a6-319">The **Response** panel</span></span>  
:::image-end:::  

### <a name="display-http-headers"></a><span data-ttu-id="4a9a6-320">显示 HTTP 标头</span><span class="sxs-lookup"><span data-stu-id="4a9a6-320">Display HTTP headers</span></span>  

<span data-ttu-id="4a9a6-321">要显示有关请求的 HTTP 标头数据，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-321">To display HTTP header data about a request, use the following steps.</span></span>  

1.  <span data-ttu-id="4a9a6-322">在“请求”表的“**名称**”列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-322">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="4a9a6-323">选择“**标头**”面板。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-323">Choose the **Headers** psanel.</span></span>  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text="“标头”面板" lightbox="../media/network-resources-headers.msft.png":::
   <span data-ttu-id="4a9a6-325">“**标头**”面板</span><span class="sxs-lookup"><span data-stu-id="4a9a6-325">The **Headers** panel</span></span>  
:::image-end:::  

#### <a name="display-http-header-source"></a><span data-ttu-id="4a9a6-326">显示 HTTP 标头源</span><span class="sxs-lookup"><span data-stu-id="4a9a6-326">Display HTTP header source</span></span>  

<span data-ttu-id="4a9a6-327">默认情况下，“**标头**”面板按字母顺序显示标头名称。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-327">By default, the **Headers** panel shows header names alphabetically.</span></span>  <span data-ttu-id="4a9a6-328">若要按接收的顺序显示 HTTP 标头名称，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-328">To dsiplay the HTTP header names in the order received, use the following steps.</span></span>  

1.  <span data-ttu-id="4a9a6-329">打开感兴趣的请求的“**标头**”面板。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-329">Open the **Headers** panel for the request that interests you.</span></span>  <span data-ttu-id="4a9a6-330">有关详细信息，请导航到“[显示 HTTP 标头](#display-http-headers)”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-330">For more information, navigate to [Display HTTP headers](#display-http-headers).</span></span>  
1.  <span data-ttu-id="4a9a6-331">单击“**请求标题**”或“**响应标题**”部分旁边的**查看源**。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-331">Choose **view source**, next to the **Request Header** or **Response Header** section.</span></span>  

### <a name="display-query-string-parameters"></a><span data-ttu-id="4a9a6-332">显示查询字符串参数</span><span class="sxs-lookup"><span data-stu-id="4a9a6-332">Display query string parameters</span></span>  

<span data-ttu-id="4a9a6-333">若要以可读格式显示 URL 的查询字符串参数，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-333">To display the query string parameters of a URL in a human-readable format, use the following steps.</span></span>  

1.  <span data-ttu-id="4a9a6-334">打开感兴趣的请求的“**标头**”面板。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-334">Open the **Headers** panel for the request that interests you.</span></span>  <span data-ttu-id="4a9a6-335">有关详细信息，请导航到“[显示 HTTP 标头](#display-http-headers)”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-335">For more information, navigate to [Display HTTP headers](#display-http-headers).</span></span>  
1.  <span data-ttu-id="4a9a6-336">导航到“**查询字符串参数**”部分。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-336">Navigate to the **Query String Parameters** section.</span></span>  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text="“查询字符串参数”部分" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   <span data-ttu-id="4a9a6-338">“**查询字符串参数**”部分</span><span class="sxs-lookup"><span data-stu-id="4a9a6-338">The **Query String Parameters** section</span></span>  
:::image-end:::  

#### <a name="display-query-string-parameters-source"></a><span data-ttu-id="4a9a6-339">显示查询字符串参数源</span><span class="sxs-lookup"><span data-stu-id="4a9a6-339">Display query string parameters source</span></span>  

<span data-ttu-id="4a9a6-340">若要显示请求的查询字符串参数源，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-340">To display the query string parameter source of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="4a9a6-341">导航到“查询字符串参数”部分。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-341">Navigate to the Query String Parameters section.</span></span>  <span data-ttu-id="4a9a6-342">有关详细信息，请导航到“[显示查询字符串参数](#display-query-string-parameters)”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-342">For more information, navigate to [Display query string parameters](#display-query-string-parameters).</span></span>  
1.  <span data-ttu-id="4a9a6-343">选择“**查看源**”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-343">Choose **view source**.</span></span>  

#### <a name="display-url-encoded-query-string-parameters"></a><span data-ttu-id="4a9a6-344">显示 URL 编码的查询字符串参数</span><span class="sxs-lookup"><span data-stu-id="4a9a6-344">Display URL-encoded query string parameters</span></span>  

<span data-ttu-id="4a9a6-345">若要以可读格式显示查询字符串参数，但保留编码，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-345">To display query string parameters in a human-readable format, but with encodings preserved, use the following steps.</span></span>  

1.  <span data-ttu-id="4a9a6-346">导航到“查询字符串参数”部分。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-346">Navigate to the Query String Parameters section.</span></span>  <span data-ttu-id="4a9a6-347">有关详细信息，请导航到“[显示查询字符串参数](#display-query-string-parameters)”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-347">For more information, navigate to [Display query string parameters](#display-query-string-parameters).</span></span>  
1.  <span data-ttu-id="4a9a6-348">选择**查看 URL 编码**。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-348">Choose **view URL encoded**.</span></span>  

### <a name="display-cookies"></a><span data-ttu-id="4a9a6-349">显示 Cookie</span><span class="sxs-lookup"><span data-stu-id="4a9a6-349">Display cookies</span></span>  

<span data-ttu-id="4a9a6-350">若要显示请求的 HTTP 标头中发送的 Cookie，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-350">To display the cookies sent in the HTTP header of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="4a9a6-351">在“请求”表的“**名称**”列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-351">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="4a9a6-352">选择“**Cookie**”面板。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-352">Choose the **Cookies** panel.</span></span>  

<!--For more information about each of the columns, navigate to [Fields][ManageDataCookiesFields].  -->  

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->  
<!--TODO: add link when section is available -->  

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text="“Cookie”面板" lightbox="../media/network-network-resources-cookies.msft.png":::
   <span data-ttu-id="4a9a6-354">“Cookie”面板</span><span class="sxs-lookup"><span data-stu-id="4a9a6-354">The Cookies panel</span></span>  
:::image-end:::  

### <a name="display-the-timing-breakdown-of-a-request"></a><span data-ttu-id="4a9a6-355">显示请求的计时细分</span><span class="sxs-lookup"><span data-stu-id="4a9a6-355">Display the timing breakdown of a request</span></span>  

<span data-ttu-id="4a9a6-356">若要显示请求的计时细分，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-356">To display the timing breakdown of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="4a9a6-357">在“请求”表的“**名称**”列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-357">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="4a9a6-358">选择“**计时**”面板。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-358">Choose the **Timing** panel.</span></span>  

<span data-ttu-id="4a9a6-359">若要更快地访问数据，请导航到“[预览计时细分](#preview-a-timing-breakdown)”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-359">For a faster way to access the data, navigate to [Preview a timing breakdown](#preview-a-timing-breakdown).</span></span>  

<span data-ttu-id="4a9a6-360">有关“**计时**”面板中可能显示的各阶段详细信息，请导航到“[计时细分阶段说明](#timing-breakdown-phases-explained)”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-360">For more information about each of the phases that may be displayed in the **Timing** panel, navigate to [Timing breakdown phases explained](#timing-breakdown-phases-explained).</span></span>  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text="“计时”面板" lightbox="../media/network-network-resources-timing.msft.png":::
   <span data-ttu-id="4a9a6-362">“**计时**”面板</span><span class="sxs-lookup"><span data-stu-id="4a9a6-362">The **Timing** panel</span></span>  
:::image-end:::  

<span data-ttu-id="4a9a6-363">有关各阶段的更多信息。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-363">More information about each of the phases.</span></span>  

<span data-ttu-id="4a9a6-364">有关访问视图的详细信息，请导航至“[显示计时明细](#display-the-timing-breakdown-of-a-request)”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-364">For more information about accessing the display, navigate to [Display timing breakdown](#display-the-timing-breakdown-of-a-request).</span></span>  

#### <a name="preview-a-timing-breakdown"></a><span data-ttu-id="4a9a6-365">预览计时细分</span><span class="sxs-lookup"><span data-stu-id="4a9a6-365">Preview a timing breakdown</span></span>  

<span data-ttu-id="4a9a6-366">要显示请求的计时细分预览，请在“请求”表的“**瀑布**”列中，将鼠标悬停在请求的条目上。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-366">To display a preview of the timing breakdown of a request, in the **Waterfall** column of the Requests table, hover on the entry for the request.</span></span>  

<span data-ttu-id="4a9a6-367">有关如何在不悬停的情况下访问数据的详细信息，请导航至“[显示请求的计时细分](#display-the-timing-breakdown-of-a-request)”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-367">For more information about how to access the data without hovering, navigate to [Display the timing breakdown of a request](#display-the-timing-breakdown-of-a-request).</span></span>  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text="> 预览请求的计时细分" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   <span data-ttu-id="4a9a6-369">预览请求的计时细分</span><span class="sxs-lookup"><span data-stu-id="4a9a6-369">Preview the timing breakdown of a request</span></span>  
:::image-end:::  

#### <a name="timing-breakdown-phases-explained"></a><span data-ttu-id="4a9a6-370">计时细分阶段说明</span><span class="sxs-lookup"><span data-stu-id="4a9a6-370">Timing breakdown phases explained</span></span>  

<span data-ttu-id="4a9a6-371">有关“**计时**”面板中可能显示的各阶段的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-371">More information about each of the phases that may display in the **Timing** panel.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-372">排队</span><span class="sxs-lookup"><span data-stu-id="4a9a6-372">Queueing</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-373">浏览器在以下情况下将请求排队。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-373">The browser queues requests when any of the following are true.</span></span>  
      
      *   <span data-ttu-id="4a9a6-374">存在更高优先级的请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-374">Higher priority requests exist.</span></span>  
      *   <span data-ttu-id="4a9a6-375">已为同一来源打开了六个（上限）TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-375">Six TCP connections are open for the same origin, which is the limit.</span></span>  <span data-ttu-id="4a9a6-376">仅适用于 HTTP/1.0 和 HTTP/1.1。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-376">Applies to HTTP/1.0 and HTTP/1.1 only.</span></span>  
      *   <span data-ttu-id="4a9a6-377">浏览器正在磁盘缓存中短暂分配空间。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-377">The browser is briefly allocating space in the disk cache.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-378">停止</span><span class="sxs-lookup"><span data-stu-id="4a9a6-378">Stalled</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-379">该请求可能由于“**排队**”中描述的任何原因而停止。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-379">The request is stalled for any of the reasons described in **Queueing**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-380">DNS 查找</span><span class="sxs-lookup"><span data-stu-id="4a9a6-380">DNS Lookup</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-381">浏览器正在解析请求的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-381">The browser is resolving the IP address for the request.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-382">初始连接</span><span class="sxs-lookup"><span data-stu-id="4a9a6-382">Initial connection</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-383">浏览器正在建立包括 TCP 握手/重试的连接和协商安全套接字层。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-383">The browser establishes a connection including TCP handshakes, TCP retries, and negotiates a Secure Socket Layer.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-384">代理协商</span><span class="sxs-lookup"><span data-stu-id="4a9a6-384">Proxy negotiation</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-385">浏览器正在与[代理服务器][WikiProxyServer]协商请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-385">The browser is negotiating the request with a [proxy server][WikiProxyServer].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-386">已发送请求</span><span class="sxs-lookup"><span data-stu-id="4a9a6-386">Request sent</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-387">正在发送请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-387">The request is being sent.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-388">ServiceWorker 准备</span><span class="sxs-lookup"><span data-stu-id="4a9a6-388">ServiceWorker Preparation</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-389">浏览器正在启动服务工作进程。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-389">The browser is starting the service worker.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-390">向 ServiceWorker 请求</span><span class="sxs-lookup"><span data-stu-id="4a9a6-390">Request to ServiceWorker</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-391">请求正在发送到服务工作进程。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-391">The request is being sent to the service worker.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-392">等待中 (TTFB)</span><span class="sxs-lookup"><span data-stu-id="4a9a6-392">Waiting \(TTFB\)</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-393">浏览器正在等待响应的首个字节。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-393">The browser is waiting for the first byte of a response.</span></span>  <span data-ttu-id="4a9a6-394">TTFB 代表到首个字节的时间。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-394">TTFB stands for Time To First Byte.</span></span>  <span data-ttu-id="4a9a6-395">此计时包括一次往返延迟和服务器准备响应所用的时间。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-395">This timing includes one round trip of latency and the time the server took to prepare the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-396">内容下载</span><span class="sxs-lookup"><span data-stu-id="4a9a6-396">Content Download</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-397">浏览器正在接收响应。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-397">The browser is receiving the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-398">接收推送</span><span class="sxs-lookup"><span data-stu-id="4a9a6-398">Receiving Push</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-399">浏览器正在通过 HTTP/2 服务器推送接收此响应的数据。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-399">The browser is receiving data for this response via HTTP/2 Server Push.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="4a9a6-400">读取推送</span><span class="sxs-lookup"><span data-stu-id="4a9a6-400">Reading Push</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4a9a6-401">浏览器正在读取以前接收的本地数据。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-401">The browser is reading the local data previously received.</span></span>  
   :::column-end:::
:::row-end:::  

### <a name="display-initiators-and-dependencies"></a><span data-ttu-id="4a9a6-402">显示发起程序和依赖项</span><span class="sxs-lookup"><span data-stu-id="4a9a6-402">Display initiators and dependencies</span></span>  

<span data-ttu-id="4a9a6-403">若要显示请求的发起程序和依赖项，请按住 `Shift` 并将鼠标悬停在“请求”表中的请求上。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-403">To display the initiators and dependencies of a request, hold `Shift`and hover on the request in the Requests table.</span></span>  <span data-ttu-id="4a9a6-404">开发工具颜色：发起程序显示为绿色，依赖项显示为红色。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-404">DevTools colors: initiators are shown in green and dependencies are shown in red.</span></span>  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="显示请求的发起程序和依赖项" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   <span data-ttu-id="4a9a6-406">显示请求的发起程序和依赖项</span><span class="sxs-lookup"><span data-stu-id="4a9a6-406">Display the initiators and dependencies of a request</span></span>  
:::image-end:::  

<span data-ttu-id="4a9a6-407">当“请求”表按时间顺序排列时，如果将鼠标悬停在某一行上，则它前面的行将显示绿色请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-407">When the Requests table is ordered chronologically, if you hover on a line, the line preceding it displays a green request.</span></span>  <span data-ttu-id="4a9a6-408">绿色请求是依赖项的发起程序。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-408">The green request is the initiator of the dependency.</span></span>  <span data-ttu-id="4a9a6-409">如果在此之上还有另一个绿色请求，则该更高的请求是发起程序的发起程序。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-409">If another green request is displayed on the line before that, that higher request is the initiator of the initiator.</span></span>  <span data-ttu-id="4a9a6-410">等等。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-410">And so on.</span></span>  

### <a name="display-load-events"></a><span data-ttu-id="4a9a6-411">显示加载事件</span><span class="sxs-lookup"><span data-stu-id="4a9a6-411">Display load events</span></span>  

<span data-ttu-id="4a9a6-412">开发人员工具在“**网络**”工具的多个位置显示 `DOMContentLoaded` 和 `load` 事件的计时。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-412">DevTools displays the timing of the `DOMContentLoaded` and `load` events in multiple places on the **Network** tool.</span></span>  <span data-ttu-id="4a9a6-413">`DOMContentLoaded` 事件颜色为蓝色，`load` 事件颜色为红色。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-413">The `DOMContentLoaded` event is colored blue, and the `load` event is red.</span></span>  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="“网络”面板上 DOMContentLoaded 和加载事件的位置" lightbox="../media/network-network-requests-load-events.msft.png":::
   <span data-ttu-id="4a9a6-415">“**网络**”工具上 `DOMContentLoaded` 和 `load` 事件的位置</span><span class="sxs-lookup"><span data-stu-id="4a9a6-415">The locations of the `DOMContentLoaded` and `load` events on the **Network** tool</span></span>  
:::image-end:::  

### <a name="display-the-total-number-of-requests"></a><span data-ttu-id="4a9a6-416">显示请求总数</span><span class="sxs-lookup"><span data-stu-id="4a9a6-416">Display the total number of requests</span></span>  

<span data-ttu-id="4a9a6-417">请求总数列在“**网络**”工具底部的“**摘要**”窗格中。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-417">The total number of requests is listed in the **Summary** pane, at the bottom of the **Network** tool.</span></span>  

> [!CAUTION]
> <span data-ttu-id="4a9a6-418">此数字仅跟踪自打开开发人员工具以来记录的请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-418">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="4a9a6-419">如果在打开开发工具之前发生了其他请求，则不计算这些请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-419">If other requests occurred before DevTools was opened, those requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="自打开开发工具以来的请求总数" lightbox="../media/network-network-total-requests.msft.png":::
   <span data-ttu-id="4a9a6-421">自打开开发工具以来的请求总数</span><span class="sxs-lookup"><span data-stu-id="4a9a6-421">The total number of requests since DevTools were opened</span></span>  
:::image-end:::  

### <a name="display-the-total-download-size"></a><span data-ttu-id="4a9a6-422">显示总下载大小</span><span class="sxs-lookup"><span data-stu-id="4a9a6-422">Display the total download size</span></span>  

<span data-ttu-id="4a9a6-423">请求的总下载大小列在“**网络**”工具底部的“**摘要**”窗格中。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-423">The total download size of requests is listed in the **Summary** pane, at the bottom of the **Network** tool.</span></span>  

> [!CAUTION]
> <span data-ttu-id="4a9a6-424">此数字仅跟踪自打开开发人员工具以来记录的请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-424">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="4a9a6-425">如果在打开开发工具之前发生了其他请求，则不计算以前的请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-425">If other requests occurred before DevTools was opened, the previous requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="请求的总下载大小" lightbox="../media/network-network-total-download-size.msft.png":::
   <span data-ttu-id="4a9a6-427">请求的总下载大小</span><span class="sxs-lookup"><span data-stu-id="4a9a6-427">The total download size of requests</span></span>  
:::image-end:::  

<span data-ttu-id="4a9a6-428">若要在浏览器解压缩每个项目后验证资源的大小，请导航到“[显示资源的未压缩大小](#display-the-uncompressed-size-of-a-resource)”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-428">To verify how large resources are after the browser uncompresses each item, navigate to [display the uncompressed size of a resource](#display-the-uncompressed-size-of-a-resource).</span></span>  

### <a name="display-the-stack-trace-that-caused-a-request"></a><span data-ttu-id="4a9a6-429">显示导致请求的堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="4a9a6-429">Display the stack trace that caused a request</span></span>  

<span data-ttu-id="4a9a6-430">JavaScript 语句请求资源后，将鼠标悬停在“**发起程序**”列上以显示请求之前的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-430">After a JavaScript statement requests a resource, hover on the **Initiator** column to display the stack trace leading up to the request.</span></span>  

<!-- [codepen.io/contoso/pen/yLBrOWa?editors=0010#0](https://codepen.io/contoso/pen/yLBrOWa?editors=0010#0) -->  

<!--
```javascript
function init() {
  getData();
}

function getData() {
  fetch('https:/httpbin.org/get?message=hi');
}

init();
```  
-->  

:::image type="complex" source="../media/network-network-requests-initiator-stack.msft.png" alt-text="导致资源请求的堆栈跟踪" lightbox="../media/network-network-requests-initiator-stack.msft.png":::
   <span data-ttu-id="4a9a6-432">导致资源请求的堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="4a9a6-432">The stack trace leading up to a resource request</span></span>  
:::image-end:::  

### <a name="display-the-uncompressed-size-of-a-resource"></a><span data-ttu-id="4a9a6-433">显示资源的未压缩大小</span><span class="sxs-lookup"><span data-stu-id="4a9a6-433">Display the uncompressed size of a resource</span></span>  

<span data-ttu-id="4a9a6-434">启用“**使用大请求行**”复选框，然后查看“**大小**”列的底部值。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-434">Turn on the **Use large request rows** checkbox and then review the bottom value of the **Size** column.</span></span>  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="未压缩资源的示例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   <span data-ttu-id="4a9a6-436">未压缩资源的示例\（通过网络发送的 `jquery-3.3.1.min.js` 文件的压缩大小为 `29.9 KB`，而未压缩大小为`84.9 KB`\）</span><span class="sxs-lookup"><span data-stu-id="4a9a6-436">An example of uncompressed resources  \(The compressed size of the `jquery-3.3.1.min.js` file that was sent over the network was `29.9 KB`, whereas the uncompressed size was `84.9 KB`\)</span></span>  
:::image-end:::  

## <a name="export-requests-data"></a><span data-ttu-id="4a9a6-437">导出请求数据</span><span class="sxs-lookup"><span data-stu-id="4a9a6-437">Export requests data</span></span>  

### <a name="save-all-network-requests-to-a-har-file"></a><span data-ttu-id="4a9a6-438">将所有网络请求保存到 HAR 文件</span><span class="sxs-lookup"><span data-stu-id="4a9a6-438">Save all network requests to a HAR file</span></span>  

<span data-ttu-id="4a9a6-439">若要将所有网络请求保存到 HAR 文件，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-439">To save all network requests to a HAR file, complete the following steps.</span></span>  

1.  <span data-ttu-id="4a9a6-440">将鼠标悬停在“请求”表中的任何请求上，然后打开上下文菜单\（右键单击\）。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-440">Hover on any request in the Requests table and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="4a9a6-441">选择“**另存为具有内容的 HAR**”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-441">Choose **Save as HAR with Content**.</span></span>  <span data-ttu-id="4a9a6-442">开发工具将自打开开发工具以来发生的所有请求保存到 HAR 文件中。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-442">DevTools saves all requests that have occurred since you opened DevTools to the HAR file.</span></span>  <span data-ttu-id="4a9a6-443">无法筛选请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-443">You are not able to filter requests.</span></span>  <span data-ttu-id="4a9a6-444">也无法保存一个请求。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-444">You are also not able to save a single request.</span></span>  

<span data-ttu-id="4a9a6-445">保存 HAR 文件后，可以将其导入开发工具进行分析。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-445">Once you save a HAR file, you may import it back into DevTools for analysis.</span></span>  <span data-ttu-id="4a9a6-446">只需将 HAR 文件拖放到“请求”表中。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-446">Just drag-and-drop the HAR file into the Requests table.</span></span>  
<!--For more information, navigate to also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="选择“另存为具有内容的 HAR”" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   <span data-ttu-id="4a9a6-448">选择“**另存为具有内容的 HAR**”</span><span class="sxs-lookup"><span data-stu-id="4a9a6-448">Choose **Save as HAR with Content**</span></span>  
:::image-end:::  

### <a name="copy-one-or-more-requests-to-the-clipboard"></a><span data-ttu-id="4a9a6-449">将一个或多个请求复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="4a9a6-449">Copy one or more requests to the clipboard</span></span>  

<span data-ttu-id="4a9a6-450">在“请求”表的“**名称**”列下，将鼠标悬停在请求上，打开上下文菜单 \（右键单击\），将鼠标悬停在“**复制**”上，然后选择以下选项之一。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-450">Under the **Name** column of the Requests table, hover on a request, open the contextual menu \(right-click\), hover on **Copy**, and choose one of the following options.</span></span>  

| <span data-ttu-id="4a9a6-451">名称</span><span class="sxs-lookup"><span data-stu-id="4a9a6-451">Name</span></span> | <span data-ttu-id="4a9a6-452">详细信息</span><span class="sxs-lookup"><span data-stu-id="4a9a6-452">Details</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="4a9a6-453">复制链接地址</span><span class="sxs-lookup"><span data-stu-id="4a9a6-453">Copy Link Address</span></span>** | <span data-ttu-id="4a9a6-454">将请求的 URL 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-454">Copy the URL of the request to the clipboard.</span></span> |  
| **<span data-ttu-id="4a9a6-455">复制响应</span><span class="sxs-lookup"><span data-stu-id="4a9a6-455">Copy Response</span></span>** | <span data-ttu-id="4a9a6-456">将响应正文复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-456">Copy the response body to the clipboard.</span></span> |  
| **<span data-ttu-id="4a9a6-457">复制为 Fetch</span><span class="sxs-lookup"><span data-stu-id="4a9a6-457">Copy as Fetch</span></span>** | &nbsp; |  
| **<span data-ttu-id="4a9a6-458">复制为 cURL</span><span class="sxs-lookup"><span data-stu-id="4a9a6-458">Copy as cURL</span></span>** | <span data-ttu-id="4a9a6-459">将请求复制为 cURL 命令。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-459">Copy the request as a cURL command.</span></span> |  
| **<span data-ttu-id="4a9a6-460">全部复制为 Fetch</span><span class="sxs-lookup"><span data-stu-id="4a9a6-460">Copy All as Fetch</span></span>** | &nbsp; |  
| **<span data-ttu-id="4a9a6-461">全部复制为 cURL</span><span class="sxs-lookup"><span data-stu-id="4a9a6-461">Copy All as cURL</span></span>** | <span data-ttu-id="4a9a6-462">将所有请求复制为一系列 cURL 命令。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-462">Copy all requests as a chain of cURL commands.</span></span> |  
| **<span data-ttu-id="4a9a6-463">全部复制为 HAR</span><span class="sxs-lookup"><span data-stu-id="4a9a6-463">Copy All as HAR</span></span>** | <span data-ttu-id="4a9a6-464">将所有请求复制为 HAR 数据。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-464">Copy all requests as HAR data.</span></span> |  

<!--
:::row:::
   :::column span="1":::
      **Copy Link Address**  
   :::column-end:::
   :::column span="2":::
      Copy the URL of the request to the clipboard.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy Response**  
   :::column-end:::
   :::column span="2":::
      Copy the response body to the clipboard.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy as Fetch**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy as cURL**  
   :::column-end:::
   :::column span="2":::
      Copy the request as a cURL command.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy All as Fetch**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy All as cURL**  
   :::column-end:::
   :::column span="2":::
      Copy all requests as a chain of cURL commands.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy All as HAR**  
   :::column-end:::
   :::column span="2":::
      Copy all requests as HAR data.  
   :::column-end:::
:::row-end:::  
-->  

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="选择“复制响应”" lightbox="../media/network-network-requests-copy-response.msft.png":::
   <span data-ttu-id="4a9a6-466">选择“**复制响应**”</span><span class="sxs-lookup"><span data-stu-id="4a9a6-466">Choose **Copy Response**</span></span>  
:::image-end:::  

### <a name="copy-formatted-response-json-to-the-clipboard"></a><span data-ttu-id="4a9a6-467">将格式化响应 JSON 复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="4a9a6-467">Copy formatted response JSON to the clipboard</span></span>  

<span data-ttu-id="4a9a6-468">选择网络请求并导航到“**标头**”窗格。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-468">Choose a network request and navigate to the **Headers** pane.</span></span>  <span data-ttu-id="4a9a6-469">要复制响应的 JSON 值，请导航到 **“请求”有效负载**，将鼠标悬停在 JSON 响应内容上，打开上下文菜单\（右键单击\），然后选择“**复制值**”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-469">To copy the JSON value of a response, navigate to **Request payload**, hover on the JSON response content, open the contextual menu \(right-click\), and choose **Copy Value**.</span></span>  

:::row:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-copy-property-value.msft.png" alt-text="复制上下文菜单中的值" lightbox="../media/network-header-copy-property-value.msft.png":::
          <span data-ttu-id="4a9a6-471">上下文菜单中的“**复制值**”</span><span class="sxs-lookup"><span data-stu-id="4a9a6-471">**Copy Value** in contextual menu</span></span>  
        :::image-end:::  
   :::column-end:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-paste-property-value.msft.png" alt-text="具有格式化响应 JSON 的 Microsoft Visual Studio Code" lightbox="../media/network-header-paste-property-value.msft.png":::
          <span data-ttu-id="4a9a6-473">在 Microsoft Visual Studio Code 中粘贴格式化响应 JSON</span><span class="sxs-lookup"><span data-stu-id="4a9a6-473">Pasting formatted response JSON in Microsoft Visual Studio Code</span></span>  
        :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="copy-property-values-from-network-requests-to-your-clipboard"></a><span data-ttu-id="4a9a6-474">将属性值从网络请求复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="4a9a6-474">Copy property values from network requests to your clipboard</span></span>  

<span data-ttu-id="4a9a6-475">要将属性值从网络请求复制到剪贴板，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-475">To copy property values from network requests to your clipboard, complete the following actions.</span></span>  

1.  <span data-ttu-id="4a9a6-476">打开“**标头**”窗格。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-476">Open the **Headers** pane.</span></span>  
1.  <span data-ttu-id="4a9a6-477">打开以下其中一个标头部分。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-477">Open one of the following header sections.</span></span>  
    *   <span data-ttu-id="4a9a6-478">请求有效负载 \(JSON\)</span><span class="sxs-lookup"><span data-stu-id="4a9a6-478">Request payload \(JSON\)</span></span>  
    *   <span data-ttu-id="4a9a6-479">窗体数据</span><span class="sxs-lookup"><span data-stu-id="4a9a6-479">Form Data</span></span>  
    *   <span data-ttu-id="4a9a6-480">查询字符串参数</span><span class="sxs-lookup"><span data-stu-id="4a9a6-480">Query String Parameters</span></span>  
    *   <span data-ttu-id="4a9a6-481">请求标头</span><span class="sxs-lookup"><span data-stu-id="4a9a6-481">Request Headers</span></span>  
    *   <span data-ttu-id="4a9a6-482">响应标头</span><span class="sxs-lookup"><span data-stu-id="4a9a6-482">Response Headers</span></span>  
1.  <span data-ttu-id="4a9a6-483">打开上下文菜单（右键单击）>“**复制值**”。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-483">Open the contextual menu \(right-click\) > **Copy value**.</span></span>  <span data-ttu-id="4a9a6-484">现在可以将该值粘贴到任何编辑器中以查看它。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-484">You may now paste the value into any editor to review it.</span></span>  
    
## <a name="change-the-layout-of-the-network-panel"></a><span data-ttu-id="4a9a6-485">更改“网络”面板的布局</span><span class="sxs-lookup"><span data-stu-id="4a9a6-485">Change the layout of the Network panel</span></span>  

<span data-ttu-id="4a9a6-486">可以展开或折叠“**网络**”工具用户界面的各部分，以集中重要信息。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-486">You may expand or collapse sections of the **Network** tool UI to focus important information.</span></span>  

### <a name="hide-the-filters-pane"></a><span data-ttu-id="4a9a6-487">隐藏“筛选器”窗格</span><span class="sxs-lookup"><span data-stu-id="4a9a6-487">Hide the Filters pane</span></span>  

<span data-ttu-id="4a9a6-488">默认情况下，开发工具显示“**筛选器**”窗格。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-488">By default, DevTools show the **Filters** pane.</span></span>  
<span data-ttu-id="4a9a6-489">选择**筛选器** \(![筛选器](../media/filter-icon.msft.png)\)来隐藏它。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-489">Choose **Filter** \(![Filter](../media/filter-icon.msft.png)\) to hide it.</span></span>  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text="“隐藏筛选器”按钮" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   <span data-ttu-id="4a9a6-491">“隐藏筛选器”按钮</span><span class="sxs-lookup"><span data-stu-id="4a9a6-491">The Hide Filters button</span></span>  
:::image-end:::  

### <a name="use-large-request-rows"></a><span data-ttu-id="4a9a6-492">使用大请求行</span><span class="sxs-lookup"><span data-stu-id="4a9a6-492">Use large request rows</span></span>  

<span data-ttu-id="4a9a6-493">如需网络请求表中有更多空白，请使用大行。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-493">Use large rows when you want more whitespace in your network requests table.</span></span>  <span data-ttu-id="4a9a6-494">在使用大行时，有些列还提供了更多的信息。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-494">Some columns also provide a little more information when using large rows.</span></span>  <span data-ttu-id="4a9a6-495">例如，“**大小**”列的底部值是请求的未压缩大小。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-495">For example, the bottom value of the **Size** column is the uncompressed size of a request.</span></span>  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text="“请求”窗格中大请求行的示例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   <span data-ttu-id="4a9a6-497">“**请求**”窗格中大请求行的示例</span><span class="sxs-lookup"><span data-stu-id="4a9a6-497">An example of large request rows in the **Requests** pane</span></span>  
:::image-end:::  

<span data-ttu-id="4a9a6-498">要启用大行，请启用“**使用大请求行**”复选框。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-498">To enable large rows, turn on the **Use large request rows** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text="“使用大请求行”复选框" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   <span data-ttu-id="4a9a6-500">“**使用大请求行**”复选框</span><span class="sxs-lookup"><span data-stu-id="4a9a6-500">The **Use large request rows** checkbox</span></span>  
:::image-end:::  

### <a name="hide-the-overview-pane"></a><span data-ttu-id="4a9a6-501">隐藏概述窗格</span><span class="sxs-lookup"><span data-stu-id="4a9a6-501">Hide the Overview pane</span></span>  

<span data-ttu-id="4a9a6-502">默认情况下，开发工具显示“**概述**”窗格。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-502">By default, DevTools displays the **Overview** pane.</span></span>  <span data-ttu-id="4a9a6-503">若要隐藏它，请关闭“**显示概述**”复选框。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-503">To hide it, turn off the **Show Overview** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text="“显示概述”复选框" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   <span data-ttu-id="4a9a6-505">“**显示概述**”复选框</span><span class="sxs-lookup"><span data-stu-id="4a9a6-505">The **Show Overview** checkbox</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="4a9a6-506">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="4a9a6-506">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsProgressiveWebApps]: ../progressive-web-apps/index.md "调试渐进式 Web 应用 | Microsoft Docs"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions | Microsoft Docs"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "数据 URL | MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "代理服务器 - 维基百科"  

> [!NOTE]
> <span data-ttu-id="4a9a6-510">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-510">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4a9a6-511">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-511">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="4a9a6-513">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="4a9a6-513">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
