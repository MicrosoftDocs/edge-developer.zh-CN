---
title: 网络分析参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 460ad05983e7615e8739953ce3cb7d559492bc90
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611838"
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







# <span data-ttu-id="b5533-103">网络分析参考</span><span class="sxs-lookup"><span data-stu-id="b5533-103">Network Analysis Reference</span></span>   



<span data-ttu-id="b5533-104">了解在 Microsoft Edge DevTools 网络分析功能的这一全面参考中，分析页面加载方式的新方法。</span><span class="sxs-lookup"><span data-stu-id="b5533-104">Discover new ways to analyze how your page loads in this comprehensive reference of Microsoft Edge DevTools network analysis features.</span></span>  

<!--
> [!NOTE]
> This reference is based on Microsoft Edge 58.  If you use another version of Microsoft Edge, the UI, and features of DevTools may be different.  Check `edge://help` to see what version of Microsoft Edge you are running.  
-->

## <span data-ttu-id="b5533-105">记录网络请求</span><span class="sxs-lookup"><span data-stu-id="b5533-105">Record network requests</span></span>   

<span data-ttu-id="b5533-106">默认情况下，DevTools 将在网络面板中记录所有网络请求，只要 DevTools 已打开。</span><span class="sxs-lookup"><span data-stu-id="b5533-106">By default, DevTools records all network requests in the Network panel, so long as DevTools is open.</span></span>  

> ##### <span data-ttu-id="b5533-107">图 1</span><span class="sxs-lookup"><span data-stu-id="b5533-107">Figure 1</span></span>  
> <span data-ttu-id="b5533-108">网络面板</span><span class="sxs-lookup"><span data-stu-id="b5533-108">The Network panel</span></span>  
> ![网络面板][ImageNetworkPanel]  

### <span data-ttu-id="b5533-110">停止记录网络请求</span><span class="sxs-lookup"><span data-stu-id="b5533-110">Stop recording network requests</span></span>   

<span data-ttu-id="b5533-111">要停止录制请求，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5533-111">To stop recording requests:</span></span>  

*   <span data-ttu-id="b5533-112">选择 "**停止录制网络日志**" ![ 停止 ][ImageRecordOnIcon] 在**网络**面板上记录网络日志。</span><span class="sxs-lookup"><span data-stu-id="b5533-112">Select **Stop recording network log** ![Stop recording network log][ImageRecordOnIcon] on the **Network** panel.</span></span>  <span data-ttu-id="b5533-113">它将变为灰色，指示 DevTools 不再录制请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-113">It turns grey to indicate that DevTools is no longer recording requests.</span></span>  
*   <span data-ttu-id="b5533-114">`Control` + `E` 在 "网络" 面板处于聚焦状态时，按 \ （Windows \）或 `Command` + `E` \ （macOS \）。 **Network**</span><span class="sxs-lookup"><span data-stu-id="b5533-114">Press `Control`+`E` \(Windows\) or `Command`+`E` \(macOS\) while the **Network** panel is in focus.</span></span>  

### <span data-ttu-id="b5533-115">清除请求</span><span class="sxs-lookup"><span data-stu-id="b5533-115">Clear requests</span></span>   

<span data-ttu-id="b5533-116">**Clear** ![ ][ImageClearIcon] 在 "网络" 面板上选择 "清除清除"，清除 "请求" 表中的所有请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-116">Select **Clear** ![Clear][ImageClearIcon] on the Network panel to clear all requests from the Requests table.</span></span>  

> ##### <span data-ttu-id="b5533-117">图 2</span><span class="sxs-lookup"><span data-stu-id="b5533-117">Figure 2</span></span>  
> <span data-ttu-id="b5533-118">"清除" 按钮</span><span class="sxs-lookup"><span data-stu-id="b5533-118">The Clear button</span></span>  
> !["清除" 按钮][ImageClearButton]  

### <span data-ttu-id="b5533-120">跨页面加载保存请求</span><span class="sxs-lookup"><span data-stu-id="b5533-120">Save requests across page loads</span></span>   

<span data-ttu-id="b5533-121">若要在每个页面加载期间保存请求，请选中 "网络" 面板上的 "**保留日志**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="b5533-121">To save requests across page loads, check the **Preserve log** checkbox on the Network panel.</span></span>  <span data-ttu-id="b5533-122">DevTools 将保存所有请求，直到你禁用**保留日志**。</span><span class="sxs-lookup"><span data-stu-id="b5533-122">DevTools saves all requests until you disable **Preserve log**.</span></span>  

> ##### <span data-ttu-id="b5533-123">图 3</span><span class="sxs-lookup"><span data-stu-id="b5533-123">Figure 3</span></span>  
> <span data-ttu-id="b5533-124">"保留日志" 复选框</span><span class="sxs-lookup"><span data-stu-id="b5533-124">The Preserve Log checkbox</span></span>  
> !["保留日志" 复选框][ImagePreserveLogCheckBox]  

### <span data-ttu-id="b5533-126">在页面加载期间捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="b5533-126">Capture screenshots during page load</span></span>   

<span data-ttu-id="b5533-127">捕获屏幕截图，分析用户在等待页面加载时看到的内容。</span><span class="sxs-lookup"><span data-stu-id="b5533-127">Capture screenshots to analyze what users see as they wait for your page to load.</span></span>  

<span data-ttu-id="b5533-128">若要启用屏幕截图，请选择 "**网络设置**"，然后选择**网络**面板上的 "**捕获屏幕截图**" 复选框</span><span class="sxs-lookup"><span data-stu-id="b5533-128">To enable screenshots, select **Network settings** and select **Capture screenshots** checkbox on the **Network** panel.</span></span>  

<span data-ttu-id="b5533-129">在 "**网络**" 面板处于焦点时重新加载页面以捕获屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="b5533-129">Reload the page while the **Network** panel is in focus to capture screenshots.</span></span>  

<span data-ttu-id="b5533-130">捕获屏幕截图后，可通过以下方式与之交互。</span><span class="sxs-lookup"><span data-stu-id="b5533-130">After capturing a screenshot, you interact with it in the following ways.</span></span>  

*   <span data-ttu-id="b5533-131">将鼠标悬停在屏幕截图上以查看捕获该屏幕截图的位置。</span><span class="sxs-lookup"><span data-stu-id="b5533-131">Hover over a screenshot to view the point at which that screenshot was captured.</span></span>  <span data-ttu-id="b5533-132">"**概述**" 窗格上将显示一个黄色线条。</span><span class="sxs-lookup"><span data-stu-id="b5533-132">A yellow line appears on the **Overview** pane.</span></span>  
*   <span data-ttu-id="b5533-133">选择屏幕的缩略图，以筛选出捕获屏幕截图后发生的任何请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-133">Select the thumbnail of a screen to filter out any requests that occurred after the screenshot was captured.</span></span>  
*   <span data-ttu-id="b5533-134">双击缩略图以放大缩略图。</span><span class="sxs-lookup"><span data-stu-id="b5533-134">Double-click a thumbnail to zoom in on it.</span></span>  

> ##### <span data-ttu-id="b5533-135">图 4</span><span class="sxs-lookup"><span data-stu-id="b5533-135">Figure 4</span></span>  
> <span data-ttu-id="b5533-136">将鼠标悬停在屏幕截图上</span><span class="sxs-lookup"><span data-stu-id="b5533-136">Hovering over a screenshot</span></span>  
> ![将鼠标悬停在屏幕截图上][ImageScreenshotHover]  

<!--  ### Replay XHR request   -->

<!--  To replay an XHR request, right-click the request in the Requests table and select **Replay XHR**.  -->

<!--  
> ##### Old Figure 5  
> Selecting Replay XHR  
> ![Selecting Replay XHR][ImageReplayXHR]  
-->  

## <span data-ttu-id="b5533-138">更改加载行为</span><span class="sxs-lookup"><span data-stu-id="b5533-138">Change loading behavior</span></span>  

### <span data-ttu-id="b5533-139">通过禁用浏览器缓存来模拟首次访问者</span><span class="sxs-lookup"><span data-stu-id="b5533-139">Emulate a first-time visitor by disabling the browser cache</span></span>   

<span data-ttu-id="b5533-140">若要模拟首次用户体验你的网站的情况，请选中 "**禁用缓存**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="b5533-140">To emulate how a first-time user experiences your site, check the **Disable cache** checkbox.</span></span>  <span data-ttu-id="b5533-141">DevTools 禁用浏览器缓存。</span><span class="sxs-lookup"><span data-stu-id="b5533-141">DevTools disables the browser cache.</span></span>  <span data-ttu-id="b5533-142">这将更准确地模拟第一次用户的体验，因为在重复访问时从浏览器缓存提供请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-142">This more accurately emulates a first-time user's experience, because requests are served from the browser cache on repeat visits.</span></span>  

> ##### <span data-ttu-id="b5533-143">图 5</span><span class="sxs-lookup"><span data-stu-id="b5533-143">Figure 5</span></span>  
> <span data-ttu-id="b5533-144">"禁用缓存" 复选框</span><span class="sxs-lookup"><span data-stu-id="b5533-144">The Disable Cache checkbox</span></span>  
> <span data-ttu-id="b5533-145">![禁用缓存复选框][ImageDisableCacheCheckBox]</span><span class="sxs-lookup"><span data-stu-id="b5533-145">![The Disable Cache checkbox][ImageDisableCacheCheckBox]</span></span>  

#### <span data-ttu-id="b5533-146">从网络条件抽屉中禁用浏览器缓存</span><span class="sxs-lookup"><span data-stu-id="b5533-146">Disable the browser cache from the Network Conditions drawer</span></span>   

<span data-ttu-id="b5533-147">如果想要在其他 DevTools 面板中工作时禁用缓存，请使用网络条件抽屉。</span><span class="sxs-lookup"><span data-stu-id="b5533-147">If you want to disable the cache while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="b5533-148">打开**网络条件**抽屉。</span><span class="sxs-lookup"><span data-stu-id="b5533-148">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="b5533-149">选中或取消选中 "**禁用缓存**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="b5533-149">Check or uncheck the **Disable cache** checkbox.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="b5533-150">手动清除浏览器缓存</span><span class="sxs-lookup"><span data-stu-id="b5533-150">Manually clear the browser cache</span></span>   

<span data-ttu-id="b5533-151">若要随时手动清除浏览器缓存，请右键单击 "请求" 表中的任意位置，然后选择 "**清除浏览器缓存**"。</span><span class="sxs-lookup"><span data-stu-id="b5533-151">To manually clear the browser cache at any time, right-click anywhere in the Requests table and select **Clear Browser Cache**.</span></span>  

> ##### <span data-ttu-id="b5533-152">图 6</span><span class="sxs-lookup"><span data-stu-id="b5533-152">Figure 6</span></span>  
> <span data-ttu-id="b5533-153">选择 "清除浏览器缓存"</span><span class="sxs-lookup"><span data-stu-id="b5533-153">Selecting Clear Browser Cache</span></span>  
> <span data-ttu-id="b5533-154">![选择 "清除浏览器缓存"][ImageClearBrowserCache]</span><span class="sxs-lookup"><span data-stu-id="b5533-154">![Selecting Clear Browser Cache][ImageClearBrowserCache]</span></span>  

### <span data-ttu-id="b5533-155">模拟脱机</span><span class="sxs-lookup"><span data-stu-id="b5533-155">Emulate offline</span></span>   

<span data-ttu-id="b5533-156">新的 web 应用类（称为[累进 Web 应用][DevtoolsProgressiveWebApps]）和**服务工作人员**帮助脱机工作。</span><span class="sxs-lookup"><span data-stu-id="b5533-156">A new class of web apps, called [Progressive Web Apps][DevtoolsProgressiveWebApps], functions offline with the help of **service workers**.</span></span>  <span data-ttu-id="b5533-157">你可能会发现，在你构建此类型的应用时，快速模拟没有数据连接的设备非常有用。</span><span class="sxs-lookup"><span data-stu-id="b5533-157">You may find it useful to quickly simulate a device that has no data connection when you are building this type of app.</span></span>  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

<span data-ttu-id="b5533-158">选择 "**联机**" 下拉菜单，在 "**预置**" 下搜索，然后选择 "**脱机**" 以模拟完全脱机的网络体验。</span><span class="sxs-lookup"><span data-stu-id="b5533-158">Select the **Online** dropdown menu, search under **Presets**, and select **Offline** to simulate a completely offline network experience.</span></span>  

> ##### <span data-ttu-id="b5533-159">图 7</span><span class="sxs-lookup"><span data-stu-id="b5533-159">Figure 7</span></span>  
> <span data-ttu-id="b5533-160">"脱机" 下拉菜单</span><span class="sxs-lookup"><span data-stu-id="b5533-160">The Offline dropdown menu</span></span>  
> <span data-ttu-id="b5533-161">![脱机下拉菜单][ImageOfflineDropdown]</span><span class="sxs-lookup"><span data-stu-id="b5533-161">![The Offline dropdown menu][ImageOfflineDropdown]</span></span>  

### <span data-ttu-id="b5533-162">模拟慢速网络连接</span><span class="sxs-lookup"><span data-stu-id="b5533-162">Emulate slow network connections</span></span>   

<span data-ttu-id="b5533-163">从 "**联机**" 下拉菜单中模拟慢速3G、快速3g 和其他连接速度。</span><span class="sxs-lookup"><span data-stu-id="b5533-163">Emulate Slow 3G, Fast 3G, and other connection speeds from the **Online** dropdown menu.</span></span>  

> ##### <span data-ttu-id="b5533-164">图 8</span><span class="sxs-lookup"><span data-stu-id="b5533-164">Figure 8</span></span>  
> <span data-ttu-id="b5533-165">限制下拉菜单</span><span class="sxs-lookup"><span data-stu-id="b5533-165">The Throttling dropdown menu</span></span>  
> <span data-ttu-id="b5533-166">![限制下拉菜单][ImageNetworkThrottlingMenu]</span><span class="sxs-lookup"><span data-stu-id="b5533-166">![The Throttling dropdown menu][ImageNetworkThrottlingMenu]</span></span>  

<span data-ttu-id="b5533-167">您可以从各种预设（如低速3G 或快速3G）中进行选择。</span><span class="sxs-lookup"><span data-stu-id="b5533-167">You may select from a variety of presets, such as Slow 3G or Fast 3G.</span></span>  <span data-ttu-id="b5533-168">您也可以通过打开 "限制" 菜单并选择 "**自定义**添加" 来添加自己的自定义预设  >  **Add**。</span><span class="sxs-lookup"><span data-stu-id="b5533-168">You may also add your own custom presets by opening the Throttling menu and selecting **Custom** > **Add**.</span></span>  

<span data-ttu-id="b5533-169">DevTools 将在 "**网络**" 选项卡旁显示一个警告图标，提醒你已启用限制。</span><span class="sxs-lookup"><span data-stu-id="b5533-169">DevTools displays a warning icon next to the **Network** tab to remind you that throttling is enabled.</span></span>  

#### <span data-ttu-id="b5533-170">从网络条件抽屉中模拟慢速网络连接</span><span class="sxs-lookup"><span data-stu-id="b5533-170">Emulate slow network connections from the Network Conditions drawer</span></span>   

<span data-ttu-id="b5533-171">如果您希望在其他 DevTools 面板中工作时限制网络连接，请使用网络条件抽屉。</span><span class="sxs-lookup"><span data-stu-id="b5533-171">If you want to throttle the network connection while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="b5533-172">打开**网络条件**抽屉。</span><span class="sxs-lookup"><span data-stu-id="b5533-172">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="b5533-173">从 "**限制**" 菜单中选择所需的连接速度。</span><span class="sxs-lookup"><span data-stu-id="b5533-173">Select your desired connection speed from the **Throttling** menu.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="b5533-174">手动清除浏览器 cookie</span><span class="sxs-lookup"><span data-stu-id="b5533-174">Manually clear browser cookies</span></span>   

<span data-ttu-id="b5533-175">若要随时手动清除浏览器 cookie，请右键单击 "请求" 表中的任意位置，然后选择 "**清除浏览器 cookie**"。</span><span class="sxs-lookup"><span data-stu-id="b5533-175">To manually clear browser cookies at any time, right-click anywhere in the Requests table and select **Clear Browser Cookies**.</span></span>  

> ##### <span data-ttu-id="b5533-176">图 9</span><span class="sxs-lookup"><span data-stu-id="b5533-176">Figure 9</span></span>  
> <span data-ttu-id="b5533-177">选择 "清除浏览器 Cookie"</span><span class="sxs-lookup"><span data-stu-id="b5533-177">Selecting Clear Browser Cookies</span></span>  
> <span data-ttu-id="b5533-178">![选择 "清除浏览器 Cookie"][ImageClearBrowserCookies]</span><span class="sxs-lookup"><span data-stu-id="b5533-178">![Selecting Clear Browser Cookies][ImageClearBrowserCookies]</span></span>  

### <span data-ttu-id="b5533-179">替代用户代理</span><span class="sxs-lookup"><span data-stu-id="b5533-179">Override the user agent</span></span>   

<span data-ttu-id="b5533-180">要手动替代用户代理，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5533-180">To manually override the user agent:</span></span>  

1.  <span data-ttu-id="b5533-181">打开**网络条件**抽屉。</span><span class="sxs-lookup"><span data-stu-id="b5533-181">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="b5533-182">取消选中 "**自动**"。</span><span class="sxs-lookup"><span data-stu-id="b5533-182">Uncheck **Select automatically**.</span></span>  
1.  <span data-ttu-id="b5533-183">从菜单中选择用户代理选项，或在文本框中输入自定义选项。</span><span class="sxs-lookup"><span data-stu-id="b5533-183">Choose a user agent option from the menu, or enter a custom one in the text box.</span></span>  

<!--todo: add network condition section when available -->  

## <span data-ttu-id="b5533-184">筛选请求</span><span class="sxs-lookup"><span data-stu-id="b5533-184">Filter requests</span></span>   

### <span data-ttu-id="b5533-185">按属性筛选请求</span><span class="sxs-lookup"><span data-stu-id="b5533-185">Filter requests by properties</span></span>   

<span data-ttu-id="b5533-186">使用 "**筛选**" 文本框筛选按属性（如请求的域或大小）的请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-186">Use the **Filter** text box to filter requests by properties, such as the domain or size of the request.</span></span>  

<span data-ttu-id="b5533-187">如果看不到文本框，则 "筛选器" 窗格可能已隐藏。</span><span class="sxs-lookup"><span data-stu-id="b5533-187">If you do not see the text box, the Filters pane is probably hidden.</span></span>  
<span data-ttu-id="b5533-188">请参阅[隐藏筛选器窗格](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="b5533-188">See [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

> ##### <span data-ttu-id="b5533-189">图 10</span><span class="sxs-lookup"><span data-stu-id="b5533-189">Figure 10</span></span>  
> <span data-ttu-id="b5533-190">"筛选" 文本框</span><span class="sxs-lookup"><span data-stu-id="b5533-190">The Filters text box</span></span>  
> <span data-ttu-id="b5533-191">![筛选器文本框][ImageFilterTextBox]</span><span class="sxs-lookup"><span data-stu-id="b5533-191">![The Filters text box][ImageFilterTextBox]</span></span>  

<span data-ttu-id="b5533-192">你可以通过使用空格分隔每个属性来同时使用多个属性。</span><span class="sxs-lookup"><span data-stu-id="b5533-192">You may use multiple properties simultaneously by separating each property with a space.</span></span>  <span data-ttu-id="b5533-193">例如， `mime-type:image/png larger-than:1K` 显示大于 1 kb 的所有 PNGs。</span><span class="sxs-lookup"><span data-stu-id="b5533-193">For example, `mime-type:image/png larger-than:1K` displays all PNGs that are larger than one kilobyte.</span></span>  <span data-ttu-id="b5533-194">这些多属性筛选器等效于 `AND` 操作。</span><span class="sxs-lookup"><span data-stu-id="b5533-194">These multi-property filters are equivalent to `AND` operations.</span></span>  `OR` <span data-ttu-id="b5533-195">当前不支持操作。</span><span class="sxs-lookup"><span data-stu-id="b5533-195">operations are currently not supported.</span></span>  

<span data-ttu-id="b5533-196">受支持的属性的完整列表。</span><span class="sxs-lookup"><span data-stu-id="b5533-196">The complete list of supported properties.</span></span>  

| <span data-ttu-id="b5533-197">属性</span><span class="sxs-lookup"><span data-stu-id="b5533-197">Property</span></span> | <span data-ttu-id="b5533-198">详细信息</span><span class="sxs-lookup"><span data-stu-id="b5533-198">Details</span></span> |  
|:--- | :--- |  
| `domain` | <span data-ttu-id="b5533-199">仅显示指定域中的资源。</span><span class="sxs-lookup"><span data-stu-id="b5533-199">Only display resources from the specified domain.</span></span>  <span data-ttu-id="b5533-200">您可以使用通配符 \ （ `*` \）包含多个域。</span><span class="sxs-lookup"><span data-stu-id="b5533-200">You may use a wildcard character \(`*`\) to include multiple domains.</span></span>  <span data-ttu-id="b5533-201">例如， `*.com` 显示所有以结尾的域名的资源 `.com` 。</span><span class="sxs-lookup"><span data-stu-id="b5533-201">For example, `*.com` displays resources from all domain names ending in `.com`.</span></span>  <span data-ttu-id="b5533-202">DevTools 将填充 "自动完成" 下拉菜单，其中包含它遇到的所有域。</span><span class="sxs-lookup"><span data-stu-id="b5533-202">DevTools populates the autocomplete dropdown menu with all of the domains it has encountered.</span></span> |  
| `has-response-header` | <span data-ttu-id="b5533-203">显示包含指定的 HTTP 响应标头的资源。</span><span class="sxs-lookup"><span data-stu-id="b5533-203">Show the resources that contain the specified HTTP response header.</span></span>  <span data-ttu-id="b5533-204">DevTools 将填充 "自动完成" 下拉列表，其中包含已遇到的所有响应标题。</span><span class="sxs-lookup"><span data-stu-id="b5533-204">DevTools populates the autocomplete dropdown with all of the response headers that it has encountered.</span></span> |  
| `is` | <span data-ttu-id="b5533-205">用于 `is:running` 查找 `WebSocket` 资源。</span><span class="sxs-lookup"><span data-stu-id="b5533-205">Use `is:running` to find `WebSocket` resources.</span></span> |  
| `larger-than` | <span data-ttu-id="b5533-206">显示大于指定大小的资源（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b5533-206">Show resources that are larger than the specified size, in bytes.</span></span>  <span data-ttu-id="b5533-207">设置值 `1000` 等效于将值设置为 `1k` 。</span><span class="sxs-lookup"><span data-stu-id="b5533-207">Setting a value of `1000` is equivalent to setting a value of `1k`.</span></span> |  
| `method` | <span data-ttu-id="b5533-208">显示通过指定的 HTTP 方法类型检索的资源。</span><span class="sxs-lookup"><span data-stu-id="b5533-208">Show resources that were retrieved over a specified HTTP method type.</span></span>  <span data-ttu-id="b5533-209">DevTools 将用它遇到的所有 HTTP 方法填充下拉列表。</span><span class="sxs-lookup"><span data-stu-id="b5533-209">DevTools populates the dropdown with all of the HTTP methods it has encountered.</span></span> |  
| `mime-type` | <span data-ttu-id="b5533-210">显示指定 MIME 类型的资源。</span><span class="sxs-lookup"><span data-stu-id="b5533-210">Show resources of a specified MIME type.</span></span>  <span data-ttu-id="b5533-211">DevTools 将用遇到的所有 MIME 类型填充下拉列表。</span><span class="sxs-lookup"><span data-stu-id="b5533-211">DevTools populates the dropdown with all MIME types it has encountered.</span></span> |  
| `mixed-content` | <span data-ttu-id="b5533-212">显示所有混合内容资源 \ （ `mixed-content:all` \）或仅显示当前显示的所有混合内容资源 \ （ `mixed-content:displayed` \）。</span><span class="sxs-lookup"><span data-stu-id="b5533-212">Show all mixed content resources \(`mixed-content:all`\) or just the ones that are currently displayed \(`mixed-content:displayed`\).</span></span> |  
| `scheme` | <span data-ttu-id="b5533-213">显示通过未受保护的 HTTP \ （ `scheme:http` \）或受保护的 HTTPS \ （ `scheme:https` \）检索的资源。</span><span class="sxs-lookup"><span data-stu-id="b5533-213">Show resources retrieved over unprotected HTTP \(`scheme:http`\) or protected HTTPS \(`scheme:https`\).</span></span> |  
| `set-cookie-domain` | <span data-ttu-id="b5533-214">显示具有 `Set-Cookie` 与指定值匹配的属性的标题的资源 `Domain` 。</span><span class="sxs-lookup"><span data-stu-id="b5533-214">Show the resources that have a `Set-Cookie` header with a `Domain` attribute that matches the specified value.</span></span>  <span data-ttu-id="b5533-215">DevTools 将填充所遇到的所有 cookie 域的自动完成功能。</span><span class="sxs-lookup"><span data-stu-id="b5533-215">DevTools populates the autocomplete with all of the cookie domains that it has encountered.</span></span> |  
| `set-cookie-name` | <span data-ttu-id="b5533-216">显示具有 `Set-Cookie` 与指定值匹配的名称的标题的资源。</span><span class="sxs-lookup"><span data-stu-id="b5533-216">Show the resources that have a `Set-Cookie` header with a name that matches the specified value.</span></span>  <span data-ttu-id="b5533-217">DevTools 将用遇到的所有 cookie 名称填充记忆式键入。</span><span class="sxs-lookup"><span data-stu-id="b5533-217">DevTools populates the autocomplete with all of the cookie names that it has encountered.</span></span> |  
| `set-cookie-value` | <span data-ttu-id="b5533-218">显示具有与 `Set-Cookie` 指定值匹配的值的标题的资源。</span><span class="sxs-lookup"><span data-stu-id="b5533-218">Show the resources that have a `Set-Cookie` header with a value that matches the specified value.</span></span>  <span data-ttu-id="b5533-219">DevTools 将用遇到的所有 cookie 值填充记忆式键入。</span><span class="sxs-lookup"><span data-stu-id="b5533-219">DevTools populates the autocomplete with all of the cookie values that it has encountered.</span></span> |  
| `status-code` | <span data-ttu-id="b5533-220">仅显示 HTTP 状态代码与指定代码匹配的资源。</span><span class="sxs-lookup"><span data-stu-id="b5533-220">Show only the resources for which the HTTP status code matches the specified code.</span></span>  <span data-ttu-id="b5533-221">DevTools 将填充 "自动完成" 下拉菜单，其中包含遇到的所有状态代码。</span><span class="sxs-lookup"><span data-stu-id="b5533-221">DevTools populates the autocomplete dropdown menu with all of the status codes it has encountered.</span></span> |  

### <span data-ttu-id="b5533-222">按类型筛选请求</span><span class="sxs-lookup"><span data-stu-id="b5533-222">Filter requests by type</span></span>   

<span data-ttu-id="b5533-223">若要按请求类型筛选请求，请选择 "网络" 面板上的**XHR**、 **JS**、 **CSS**、 **Img**、**媒体**、**字体**、**文档**、 **WS** \ （WebSocket \）、**清单**或**其他**\ （此处未列出的任何其他类型 \）按钮。</span><span class="sxs-lookup"><span data-stu-id="b5533-223">To filter requests by request type, select the **XHR**, **JS**, **CSS**, **Img**, **Media**, **Font**, **Doc**, **WS** \(WebSocket\), **Manifest**, or **Other** \(any other type not listed here\) buttons on the Network panel.</span></span>  

<span data-ttu-id="b5533-224">如果看不到这些按钮，则 "筛选器" 窗格可能处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="b5533-224">If you do not see these buttons, the Filters pane is probably hidden.</span></span>  
<span data-ttu-id="b5533-225">请参阅[隐藏筛选器窗格](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="b5533-225">See [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

<span data-ttu-id="b5533-226">若要同时启用多个类型筛选器，请按住 `Control` \ （Windows \）或 `Command` \ （macOS \），然后选择。</span><span class="sxs-lookup"><span data-stu-id="b5533-226">To enable multiple type filters simultaneously, hold `Control` \(Windows\) or `Command` \(macOS\) and then select.</span></span>  

> ##### <span data-ttu-id="b5533-227">图 11</span><span class="sxs-lookup"><span data-stu-id="b5533-227">Figure 11</span></span>  
> <span data-ttu-id="b5533-228">使用类型筛选器显示 JS、CSS 和文档资源</span><span class="sxs-lookup"><span data-stu-id="b5533-228">Using the Type filters to display JS, CSS, and Document resources</span></span>  
> <span data-ttu-id="b5533-229">![使用类型筛选器显示 JS、CSS 和文档资源][ImageMultiTypeFilter]</span><span class="sxs-lookup"><span data-stu-id="b5533-229">![Using the Type filters to display JS, CSS, and Document resources][ImageMultiTypeFilter]</span></span>  

### <span data-ttu-id="b5533-230">按时间筛选请求</span><span class="sxs-lookup"><span data-stu-id="b5533-230">Filter requests by time</span></span>   

<span data-ttu-id="b5533-231">在 "概述" 窗格中选择并向左或向右拖动，以仅显示在该时间范围内处于活动状态的请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-231">Select and drag left or right on the Overview pane to only display requests that were active during that time frame.</span></span>  <span data-ttu-id="b5533-232">筛选器是包含的。</span><span class="sxs-lookup"><span data-stu-id="b5533-232">The filter is inclusive.</span></span>  <span data-ttu-id="b5533-233">显示在突出显示的时间内处于活动状态的任何请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-233">Any request that was active during the highlighted time is shown.</span></span>  

> ##### <span data-ttu-id="b5533-234">图 12</span><span class="sxs-lookup"><span data-stu-id="b5533-234">Figure 12</span></span>  
> <span data-ttu-id="b5533-235">筛选出在300ms 周围处于非活动状态的任何请求</span><span class="sxs-lookup"><span data-stu-id="b5533-235">Filtering out any requests that were inactive around 300ms</span></span>  
> <span data-ttu-id="b5533-236">![筛选掉在300ms 上处于非活动状态的所有请求][ImageOverviewFilter]</span><span class="sxs-lookup"><span data-stu-id="b5533-236">![Filtering out any requests that were inactive around 300ms][ImageOverviewFilter]</span></span>  

### <span data-ttu-id="b5533-237">隐藏数据 Url</span><span class="sxs-lookup"><span data-stu-id="b5533-237">Hide data URLs</span></span>  

<span data-ttu-id="b5533-238">[数据 url][MDNHTTPDataURIs]是嵌入到其他文档中的小文件。</span><span class="sxs-lookup"><span data-stu-id="b5533-238">[Data URLs][MDNHTTPDataURIs] are small files embedded into other documents.</span></span>  <span data-ttu-id="b5533-239">在 "请求" 表中看到的以数据 URL 开头的任何请求 `data:` 。</span><span class="sxs-lookup"><span data-stu-id="b5533-239">Any request that you see in the Requests table that starts with `data:` is a data URL.</span></span>  

<span data-ttu-id="b5533-240">选中 "**隐藏数据 url** " 复选框以隐藏这些请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-240">Check the **Hide data URLs** checkbox to hide these requests.</span></span>  

> ##### <span data-ttu-id="b5533-241">图 13</span><span class="sxs-lookup"><span data-stu-id="b5533-241">Figure 13</span></span>  
> <span data-ttu-id="b5533-242">"隐藏数据 Url" 复选框</span><span class="sxs-lookup"><span data-stu-id="b5533-242">The Hide Data URLs checkbox</span></span>  
> <span data-ttu-id="b5533-243">!["隐藏数据 Url" 复选框][ImageHideDataURLsCheckBox]</span><span class="sxs-lookup"><span data-stu-id="b5533-243">![The Hide Data URLs checkbox][ImageHideDataURLsCheckBox]</span></span>  

## <span data-ttu-id="b5533-244">排序请求</span><span class="sxs-lookup"><span data-stu-id="b5533-244">Sort requests</span></span>  

<span data-ttu-id="b5533-245">默认情况下，请求表中的请求按初始时间排序，但你可以使用其他条件对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="b5533-245">By default, the requests in the Requests table are sorted by initiation time, but you may sort the table using other criteria.</span></span>  

### <span data-ttu-id="b5533-246">按列排序</span><span class="sxs-lookup"><span data-stu-id="b5533-246">Sort by column</span></span>   

<span data-ttu-id="b5533-247">选择请求中的任何列的标题，对该列的请求进行排序。</span><span class="sxs-lookup"><span data-stu-id="b5533-247">Select the header of any column in the Requests to sort requests by that column.</span></span>  

### <span data-ttu-id="b5533-248">按活动阶段排序</span><span class="sxs-lookup"><span data-stu-id="b5533-248">Sort by activity phase</span></span>   

<span data-ttu-id="b5533-249">若要更改瀑布对请求的排序方式，请右键单击 "请求" 表的标题，将鼠标悬停在**瀑布**上，然后选择下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="b5533-249">To change how the Waterfall sorts requests, right-click the header of the Requests table, hover over **Waterfall**, and select one of the following options.</span></span>  

*   <span data-ttu-id="b5533-250">**开始时间**。</span><span class="sxs-lookup"><span data-stu-id="b5533-250">**Start Time**.</span></span>  <span data-ttu-id="b5533-251">启动的第一个请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="b5533-251">The first request that was initiated is at the top.</span></span>  
*   <span data-ttu-id="b5533-252">**响应时间**。</span><span class="sxs-lookup"><span data-stu-id="b5533-252">**Response Time**.</span></span>  <span data-ttu-id="b5533-253">开始下载的第一个请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="b5533-253">The first request that started downloading is at the top.</span></span>  
*   <span data-ttu-id="b5533-254">**结束时间**。</span><span class="sxs-lookup"><span data-stu-id="b5533-254">**End Time**.</span></span>  <span data-ttu-id="b5533-255">第一个已完成的请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="b5533-255">The first request that finished is at the top.</span></span>  
*   <span data-ttu-id="b5533-256">**总工期**。</span><span class="sxs-lookup"><span data-stu-id="b5533-256">**Total Duration**.</span></span>  <span data-ttu-id="b5533-257">具有最短连接设置和请求/响应的请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="b5533-257">The request with the shortest connection setup and request / response is at the top.</span></span>  
*   <span data-ttu-id="b5533-258">**延迟**。</span><span class="sxs-lookup"><span data-stu-id="b5533-258">**Latency**.</span></span>  <span data-ttu-id="b5533-259">等待响应时间最短的请求位于最前面。</span><span class="sxs-lookup"><span data-stu-id="b5533-259">The request that waited the shortest time for a response is at the top.</span></span>  

<span data-ttu-id="b5533-260">这些说明假定每个各自的选项均按最短到最长的排序。</span><span class="sxs-lookup"><span data-stu-id="b5533-260">These descriptions assume that each respective option is ranked from shortest to longest.</span></span>  <span data-ttu-id="b5533-261">选择**瀑布**栏的标题将反转顺序。</span><span class="sxs-lookup"><span data-stu-id="b5533-261">Selecting the header of the **Waterfall** column reverses the order.</span></span>  

> ##### <span data-ttu-id="b5533-262">图 14</span><span class="sxs-lookup"><span data-stu-id="b5533-262">Figure 14</span></span>  
> <span data-ttu-id="b5533-263">按总工期对瀑布图进行排序 \ （每个条形图的较亮部分是等待的时间，较暗的部分是下载字节所花费的时间）</span><span class="sxs-lookup"><span data-stu-id="b5533-263">Sorting the Waterfall by total duration  \(The lighter portion of each bar is time spent waiting and the darker portion is time spent downloading bytes\)</span></span>  
> <span data-ttu-id="b5533-264">![按总工期对瀑布图进行排序][ImageWaterfallTotalDuration]</span><span class="sxs-lookup"><span data-stu-id="b5533-264">![Sorting the Waterfall by total duration][ImageWaterfallTotalDuration]</span></span>  

## <span data-ttu-id="b5533-265">分析请求</span><span class="sxs-lookup"><span data-stu-id="b5533-265">Analyze requests</span></span>   

<span data-ttu-id="b5533-266">只要 DevTools 打开，它就会在 "网络" 面板中记录所有请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-266">So long as DevTools is open, it logs all requests in the Network panel.</span></span>  
<span data-ttu-id="b5533-267">使用 "网络" 面板分析请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-267">Use the Network panel to analyze requests.</span></span>  

### <span data-ttu-id="b5533-268">查看请求日志</span><span class="sxs-lookup"><span data-stu-id="b5533-268">View a log of requests</span></span>   

<span data-ttu-id="b5533-269">使用 "请求" 表查看在 DevTools 打开时发出的所有请求的日志。</span><span class="sxs-lookup"><span data-stu-id="b5533-269">Use the Requests table to view a log of all requests made while DevTools has been open.</span></span>  <span data-ttu-id="b5533-270">选择或悬停的请求将显示有关每个项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b5533-270">Selecting or hovering over requests reveals more information about each item.</span></span>  

> ##### <span data-ttu-id="b5533-271">图 15</span><span class="sxs-lookup"><span data-stu-id="b5533-271">Figure 15</span></span>  
> <span data-ttu-id="b5533-272">请求表</span><span class="sxs-lookup"><span data-stu-id="b5533-272">The Requests table</span></span>  
> <span data-ttu-id="b5533-273">![请求表][ImageRequestsTable]</span><span class="sxs-lookup"><span data-stu-id="b5533-273">![The Requests table][ImageRequestsTable]</span></span>  

<span data-ttu-id="b5533-274">"请求" 表默认情况下显示以下列：</span><span class="sxs-lookup"><span data-stu-id="b5533-274">The Requests table displays the following columns by default:</span></span>  

*   <span data-ttu-id="b5533-275">**名称**。</span><span class="sxs-lookup"><span data-stu-id="b5533-275">**Name**.</span></span>  <span data-ttu-id="b5533-276">资源的文件名或标识符。</span><span class="sxs-lookup"><span data-stu-id="b5533-276">The filename of, or an identifier for, the resource.</span></span>  
*   <span data-ttu-id="b5533-277">**状态**。</span><span class="sxs-lookup"><span data-stu-id="b5533-277">**Status**.</span></span>  <span data-ttu-id="b5533-278">HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="b5533-278">The HTTP status code.</span></span>  
*   <span data-ttu-id="b5533-279">**类型**。</span><span class="sxs-lookup"><span data-stu-id="b5533-279">**Type**.</span></span>  <span data-ttu-id="b5533-280">所请求的资源的 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="b5533-280">The MIME type of the requested resource.</span></span>  
*   <span data-ttu-id="b5533-281">**启动器**。</span><span class="sxs-lookup"><span data-stu-id="b5533-281">**Initiator**.</span></span>  <span data-ttu-id="b5533-282">以下对象或进程启动请求：</span><span class="sxs-lookup"><span data-stu-id="b5533-282">The following objects or processes initiate requests:</span></span>  
    *   <span data-ttu-id="b5533-283">**分析器**。</span><span class="sxs-lookup"><span data-stu-id="b5533-283">**Parser**.</span></span>  <span data-ttu-id="b5533-284">Microsoft Edge 的 HTML 分析程序。</span><span class="sxs-lookup"><span data-stu-id="b5533-284">The HTML parser for Microsoft Edge.</span></span>  
    *   <span data-ttu-id="b5533-285">**重定向**。</span><span class="sxs-lookup"><span data-stu-id="b5533-285">**Redirect**.</span></span>  <span data-ttu-id="b5533-286">HTTP 重定向。</span><span class="sxs-lookup"><span data-stu-id="b5533-286">An HTTP redirect.</span></span>  
    *   <span data-ttu-id="b5533-287">**脚本**。</span><span class="sxs-lookup"><span data-stu-id="b5533-287">**Script**.</span></span>  <span data-ttu-id="b5533-288">JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="b5533-288">A JavaScript function.</span></span>  
    *   <span data-ttu-id="b5533-289">**其他**。</span><span class="sxs-lookup"><span data-stu-id="b5533-289">**Other**.</span></span>  <span data-ttu-id="b5533-290">某些其他进程或操作，例如通过链接导航到页面或在地址栏中输入 URL。</span><span class="sxs-lookup"><span data-stu-id="b5533-290">Some other process or action, such as navigating to a page via a link or entering a URL in the address bar.</span></span>  
*   <span data-ttu-id="b5533-291">**大小**。</span><span class="sxs-lookup"><span data-stu-id="b5533-291">**Size**.</span></span>  <span data-ttu-id="b5533-292">由服务器发送的响应标题和响应正文的合并大小。</span><span class="sxs-lookup"><span data-stu-id="b5533-292">The combined size of the response headers plus the response body, as delivered by the server.</span></span>  
*   <span data-ttu-id="b5533-293">**时间**。</span><span class="sxs-lookup"><span data-stu-id="b5533-293">**Time**.</span></span>  <span data-ttu-id="b5533-294">从请求开始到响应中最后一个字节的接收的总持续时间。</span><span class="sxs-lookup"><span data-stu-id="b5533-294">The total duration, from the start of the request to the receipt of the final byte in the response.</span></span>  
*   <span data-ttu-id="b5533-295">[**瀑布**](#view-the-timing-of-requests-in-relation-to-one-another)图。</span><span class="sxs-lookup"><span data-stu-id="b5533-295">[**Waterfall**](#view-the-timing-of-requests-in-relation-to-one-another).</span></span>  <span data-ttu-id="b5533-296">每个请求的活动的可视化细目。</span><span class="sxs-lookup"><span data-stu-id="b5533-296">A visual breakdown of the activity for each request.</span></span>  

#### <span data-ttu-id="b5533-297">添加或删除列</span><span class="sxs-lookup"><span data-stu-id="b5533-297">Add or remove columns</span></span>   

<span data-ttu-id="b5533-298">右键单击 "请求" 表的标题，然后选择一个选项以隐藏或显示它。</span><span class="sxs-lookup"><span data-stu-id="b5533-298">Right-click the header of the Requests table and select an option to hide or show it.</span></span>  <span data-ttu-id="b5533-299">当前显示的选项在每个项目旁边都有复选标记。</span><span class="sxs-lookup"><span data-stu-id="b5533-299">Currently displayed options have checkmarks next to each item.</span></span>  

> ##### <span data-ttu-id="b5533-300">图 16</span><span class="sxs-lookup"><span data-stu-id="b5533-300">Figure 16</span></span>  
> <span data-ttu-id="b5533-301">将列添加到 "请求" 表</span><span class="sxs-lookup"><span data-stu-id="b5533-301">Adding a column to the Requests table</span></span>  
> <span data-ttu-id="b5533-302">![向请求表添加列][ImageRequestsTableAddColumn]</span><span class="sxs-lookup"><span data-stu-id="b5533-302">![Adding a column to the Requests table][ImageRequestsTableAddColumn]</span></span>  

#### <span data-ttu-id="b5533-303">添加自定义列</span><span class="sxs-lookup"><span data-stu-id="b5533-303">Add custom columns</span></span>   

<span data-ttu-id="b5533-304">若要向 "请求" 表添加自定义列，请右键单击 "请求" 表的标题，然后选择 "**响应标题**" "  >  **管理标题列**"。</span><span class="sxs-lookup"><span data-stu-id="b5533-304">To add a custom column to the Requests table, right-click the header of the Requests table and select **Response Headers** > **Manage Header Columns**.</span></span>  

> ##### <span data-ttu-id="b5533-305">图 17</span><span class="sxs-lookup"><span data-stu-id="b5533-305">Figure 17</span></span>  
> <span data-ttu-id="b5533-306">向请求表添加自定义列</span><span class="sxs-lookup"><span data-stu-id="b5533-306">Adding a custom column to the Requests table</span></span>  
> <span data-ttu-id="b5533-307">![向请求表添加自定义列][ImageRequestsTableCustomColumn]</span><span class="sxs-lookup"><span data-stu-id="b5533-307">![Adding a custom column to the Requests table][ImageRequestsTableCustomColumn]</span></span>  

### <span data-ttu-id="b5533-308">查看请求之间的相对计时</span><span class="sxs-lookup"><span data-stu-id="b5533-308">View the timing of requests in relation to one another</span></span>   

<span data-ttu-id="b5533-309">使用瀑布图查看请求相对于另一个时间的计时。</span><span class="sxs-lookup"><span data-stu-id="b5533-309">Use the Waterfall to view the timing of requests in relation to one another.</span></span>  
<span data-ttu-id="b5533-310">默认情况下，瀑布图按请求的开始时间进行组织。</span><span class="sxs-lookup"><span data-stu-id="b5533-310">By default, the Waterfall is organized by the start time of the requests.</span></span>  
<span data-ttu-id="b5533-311">因此，比右侧更远的时间开始向左的请求更远。</span><span class="sxs-lookup"><span data-stu-id="b5533-311">So, requests that are farther to the left started earlier than those that are farther to the right.</span></span>  

<span data-ttu-id="b5533-312">请参阅 "[按活动排序" 阶段](#sort-by-activity-phase)以查看可对瀑布图进行排序的不同方式。</span><span class="sxs-lookup"><span data-stu-id="b5533-312">See [Sort by activity phase](#sort-by-activity-phase) to see the different ways that you may sort the Waterfall.</span></span>  

> ##### <span data-ttu-id="b5533-313">图18</span><span class="sxs-lookup"><span data-stu-id="b5533-313">Figure 18</span></span>  
> <span data-ttu-id="b5533-314">"请求" 窗格的瀑布栏</span><span class="sxs-lookup"><span data-stu-id="b5533-314">The Waterfall column of the Requests pane</span></span>  
> <span data-ttu-id="b5533-315">![请求窗格的瀑布列][ImageRequestsTableWaterfallColumn]</span><span class="sxs-lookup"><span data-stu-id="b5533-315">![The Waterfall column of the Requests pane][ImageRequestsTableWaterfallColumn]</span></span>  

<!-- ### Analyze the frames of a WebSocket Connection   -->

<!--To view the frames of a WebSocket connection:  

1.  Select the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Select the **Frames** tab.  The table shows the last 100 frames.  

To refresh the table, re-click the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
> ##### Old Figure 20  
> The Frames tab  
> ![The Frames tab][ImageFrames]  
-->

<!--The table contains three columns:  

*   **Data**.  The message payload.  If the message is plain text, it is displayed here.  For binary opcodes, this column displays the name and code of the opcode.  The following opcodes are supported: Continuation Frame, Binary Frame, Connection Close Frame, Ping Frame, and Pong Frame.  
*   **Length**.  The length of the message payload, in bytes.  
*   **Time**.  The time when the message was received or sent.  -->

<!--Messages are color-coded according to their type:  

*   Outgoing text messages are light-green.  
*   Incoming text messages are white.  
*   WebSocket opcodes are light-yellow.  
*   Errors are light-red.  -->

### <span data-ttu-id="b5533-316">查看答复正文的预览</span><span class="sxs-lookup"><span data-stu-id="b5533-316">View a preview of a response body</span></span>   

<span data-ttu-id="b5533-317">若要查看响应正文的预览，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5533-317">To view a preview of a response body:</span></span>  

1.  <span data-ttu-id="b5533-318">在 "请求" 表的 "**名称**" 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="b5533-318">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="b5533-319">选择 "**预览**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b5533-319">Select the **Preview** tab.</span></span>  

<span data-ttu-id="b5533-320">此选项卡最适用于查看图像。</span><span class="sxs-lookup"><span data-stu-id="b5533-320">This tab is mostly useful for viewing images.</span></span>  

> ##### <span data-ttu-id="b5533-321">图19</span><span class="sxs-lookup"><span data-stu-id="b5533-321">Figure 19</span></span>  
> <span data-ttu-id="b5533-322">"预览" 选项卡</span><span class="sxs-lookup"><span data-stu-id="b5533-322">The Preview tab</span></span>  
> <span data-ttu-id="b5533-323">![预览选项卡][ImagePreview]</span><span class="sxs-lookup"><span data-stu-id="b5533-323">![The Preview tab][ImagePreview]</span></span>  

### <span data-ttu-id="b5533-324">查看答复正文</span><span class="sxs-lookup"><span data-stu-id="b5533-324">View a response body</span></span>   

<span data-ttu-id="b5533-325">要查看请求的响应正文，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5533-325">To view the response body to a request:</span></span>  

1.  <span data-ttu-id="b5533-326">在 "请求" 表的 "**名称**" 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="b5533-326">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="b5533-327">选择 "**响应**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b5533-327">Select the **Response** tab.</span></span>  

> ##### <span data-ttu-id="b5533-328">图20</span><span class="sxs-lookup"><span data-stu-id="b5533-328">Figure 20</span></span>  
> <span data-ttu-id="b5533-329">"响应" 选项卡</span><span class="sxs-lookup"><span data-stu-id="b5533-329">The Response tab</span></span>  
> <span data-ttu-id="b5533-330">![响应选项卡][ImageResponse]</span><span class="sxs-lookup"><span data-stu-id="b5533-330">![The Response tab][ImageResponse]</span></span>  

### <span data-ttu-id="b5533-331">查看 HTTP 标头</span><span class="sxs-lookup"><span data-stu-id="b5533-331">View HTTP headers</span></span>   

<span data-ttu-id="b5533-332">查看有关请求的 HTTP 头数据：</span><span class="sxs-lookup"><span data-stu-id="b5533-332">To view HTTP header data about a request:</span></span>  

1.  <span data-ttu-id="b5533-333">在 "请求" 表的 "**名称**" 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="b5533-333">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="b5533-334">选择 "**页眉**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b5533-334">Select the **Headers** tab.</span></span>  

> ##### <span data-ttu-id="b5533-335">图21</span><span class="sxs-lookup"><span data-stu-id="b5533-335">Figure 21</span></span>  
> <span data-ttu-id="b5533-336">"页眉" 选项卡</span><span class="sxs-lookup"><span data-stu-id="b5533-336">The Headers tab</span></span>  
> <span data-ttu-id="b5533-337">![标题选项卡][ImageHeaders]</span><span class="sxs-lookup"><span data-stu-id="b5533-337">![The Headers tab][ImageHeaders]</span></span>  

#### <span data-ttu-id="b5533-338">查看 HTTP 域名源</span><span class="sxs-lookup"><span data-stu-id="b5533-338">View HTTP header source</span></span>   

<span data-ttu-id="b5533-339">默认情况下，"页眉" 选项卡按字母顺序显示标题名称。</span><span class="sxs-lookup"><span data-stu-id="b5533-339">By default, the Headers tab shows header names alphabetically.</span></span>  <span data-ttu-id="b5533-340">若要按接收的顺序查看 HTTP 标头名称，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5533-340">To view the HTTP header names in the order they were received:</span></span>  

1.  <span data-ttu-id="b5533-341">打开您感兴趣的请求的 "**标题**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b5533-341">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="b5533-342">请参阅[查看 HTTP 标头](#view-http-headers)。</span><span class="sxs-lookup"><span data-stu-id="b5533-342">See [View HTTP headers](#view-http-headers).</span></span>  
1.  <span data-ttu-id="b5533-343">选择 "**请求标头**" 或 "**响应标题**" 部分旁边的 "**查看源**"。</span><span class="sxs-lookup"><span data-stu-id="b5533-343">Select **view source**, next to the **Request Header** or **Response Header** section.</span></span>  

### <span data-ttu-id="b5533-344">查看查询字符串参数</span><span class="sxs-lookup"><span data-stu-id="b5533-344">View query string parameters</span></span>   

<span data-ttu-id="b5533-345">若要以可读的格式查看 URL 的查询字符串参数，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5533-345">To view the query string parameters of a URL in a human-readable format:</span></span>  

1.  <span data-ttu-id="b5533-346">打开您感兴趣的请求的 "**标题**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b5533-346">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="b5533-347">请参阅[查看 HTTP 标头](#view-http-headers)。</span><span class="sxs-lookup"><span data-stu-id="b5533-347">See [View HTTP headers](#view-http-headers).</span></span>  
1.  <span data-ttu-id="b5533-348">转到 "**查询字符串参数**" 部分。</span><span class="sxs-lookup"><span data-stu-id="b5533-348">Go to the **Query String Parameters** section.</span></span>  

> ##### <span data-ttu-id="b5533-349">图22</span><span class="sxs-lookup"><span data-stu-id="b5533-349">Figure 22</span></span>  
> <span data-ttu-id="b5533-350">"查询字符串参数" 部分</span><span class="sxs-lookup"><span data-stu-id="b5533-350">The Query String Parameters section</span></span>  
> <span data-ttu-id="b5533-351">![查询字符串参数部分][ImageQueryStringParameters]</span><span class="sxs-lookup"><span data-stu-id="b5533-351">![The Query String Parameters section][ImageQueryStringParameters]</span></span>  

#### <span data-ttu-id="b5533-352">查看查询字符串参数源</span><span class="sxs-lookup"><span data-stu-id="b5533-352">View query string parameters source</span></span>   

<span data-ttu-id="b5533-353">要查看请求的查询字符串参数源，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5533-353">To view the query string parameter source of a request:</span></span>  

1.  <span data-ttu-id="b5533-354">转到 "查询字符串参数" 部分。</span><span class="sxs-lookup"><span data-stu-id="b5533-354">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="b5533-355">请参阅[查看查询字符串参数](#view-query-string-parameters)。</span><span class="sxs-lookup"><span data-stu-id="b5533-355">See [View query string parameters](#view-query-string-parameters).</span></span>  
1.  <span data-ttu-id="b5533-356">选择 "**查看源**"。</span><span class="sxs-lookup"><span data-stu-id="b5533-356">Select **view source**.</span></span>  

#### <span data-ttu-id="b5533-357">查看 URL 编码查询字符串参数</span><span class="sxs-lookup"><span data-stu-id="b5533-357">View URL-encoded query string parameters</span></span>   

<span data-ttu-id="b5533-358">以人类可读格式查看查询字符串参数，但保留编码：</span><span class="sxs-lookup"><span data-stu-id="b5533-358">To view query string parameters in a human-readable format, but with encodings preserved:</span></span>  

1.  <span data-ttu-id="b5533-359">转到 "查询字符串参数" 部分。</span><span class="sxs-lookup"><span data-stu-id="b5533-359">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="b5533-360">请参阅[查看查询字符串参数](#view-query-string-parameters)。</span><span class="sxs-lookup"><span data-stu-id="b5533-360">See [View query string parameters](#view-query-string-parameters).</span></span>  
1.  <span data-ttu-id="b5533-361">选择 "**查看 URL 编码**"。</span><span class="sxs-lookup"><span data-stu-id="b5533-361">Select **view URL encoded**.</span></span>  

### <span data-ttu-id="b5533-362">查看 cookie</span><span class="sxs-lookup"><span data-stu-id="b5533-362">View cookies</span></span>   

<span data-ttu-id="b5533-363">若要查看在请求的 HTTP 头中发送的 cookie，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5533-363">To view the cookies sent in the HTTP header of a request:</span></span>  

1.  <span data-ttu-id="b5533-364">在 "请求" 表的 "**名称**" 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="b5533-364">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="b5533-365">选择 " **cookie** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b5533-365">Select the **Cookies** tab.</span></span>  

<!--See [Fields][ManageDataCookiesFields] for a description of each of the columns.  -->

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->
<!--TODO: add link when section is available -->

> ##### <span data-ttu-id="b5533-366">图23</span><span class="sxs-lookup"><span data-stu-id="b5533-366">Figure 23</span></span>  
> <span data-ttu-id="b5533-367">"Cookie" 选项卡</span><span class="sxs-lookup"><span data-stu-id="b5533-367">The Cookies tab</span></span>  
> <span data-ttu-id="b5533-368">![Cookies 选项卡][ImageCookies]</span><span class="sxs-lookup"><span data-stu-id="b5533-368">![The Cookies tab][ImageCookies]</span></span>  

### <span data-ttu-id="b5533-369">查看请求的计时细目</span><span class="sxs-lookup"><span data-stu-id="b5533-369">View the timing breakdown of a request</span></span>   

<span data-ttu-id="b5533-370">要查看请求的计时细目，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5533-370">To view the timing breakdown of a request:</span></span>  

1.  <span data-ttu-id="b5533-371">在 "请求" 表的 "**名称**" 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="b5533-371">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="b5533-372">选择 "**计时**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b5533-372">Select the **Timing** tab.</span></span>  

<span data-ttu-id="b5533-373">请参阅[预览计时细目](#preview-a-timing-breakdown)以获得更快的访问此数据的方式。</span><span class="sxs-lookup"><span data-stu-id="b5533-373">See [Preview a timing breakdown](#preview-a-timing-breakdown) for a faster way to access this data.</span></span>  

<span data-ttu-id="b5533-374">有关你在 "计时" 选项卡中看到的每个阶段的详细信息，请参阅[介绍的计时分解阶段](#timing-breakdown-phases-explained)。</span><span class="sxs-lookup"><span data-stu-id="b5533-374">See [Timing breakdown phases explained](#timing-breakdown-phases-explained) for more information about each of the phases that you may see in the Timing tab.</span></span>  

> ##### <span data-ttu-id="b5533-375">图24</span><span class="sxs-lookup"><span data-stu-id="b5533-375">Figure 24</span></span>  
> <span data-ttu-id="b5533-376">"计时" 选项卡</span><span class="sxs-lookup"><span data-stu-id="b5533-376">The Timing tab</span></span>  
> <span data-ttu-id="b5533-377">![计时选项卡][ImageTiming]</span><span class="sxs-lookup"><span data-stu-id="b5533-377">![The Timing tab][ImageTiming]</span></span>  

<span data-ttu-id="b5533-378">有关每个阶段的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b5533-378">More information about each of the phases.</span></span>  

<span data-ttu-id="b5533-379">请参阅[查看计时细目](#view-the-timing-breakdown-of-a-request)以了解另一种访问此视图的方式。</span><span class="sxs-lookup"><span data-stu-id="b5533-379">See [View timing breakdown](#view-the-timing-breakdown-of-a-request) for another way to access this view.</span></span>  

#### <span data-ttu-id="b5533-380">预览计时细目</span><span class="sxs-lookup"><span data-stu-id="b5533-380">Preview a timing breakdown</span></span>   

<span data-ttu-id="b5533-381">若要查看请求的计时分解的预览，请将鼠标悬停在 "请求" 表的 "**瀑布**图" 列中请求的条目上。</span><span class="sxs-lookup"><span data-stu-id="b5533-381">To view a preview of the timing breakdown of a request, hover over the entry for the request in the **Waterfall** column of the Requests table.</span></span>  

<span data-ttu-id="b5533-382">请参阅[查看请求的计时细目](#view-the-timing-breakdown-of-a-request)以了解访问不需要悬停的数据的方式。</span><span class="sxs-lookup"><span data-stu-id="b5533-382">See [View the timing breakdown of a request](#view-the-timing-breakdown-of-a-request) for a way to access this data that does not require hovering.</span></span>  

> ##### <span data-ttu-id="b5533-383">图25</span><span class="sxs-lookup"><span data-stu-id="b5533-383">Figure 25</span></span>  
> <span data-ttu-id="b5533-384">预览请求的计时细目</span><span class="sxs-lookup"><span data-stu-id="b5533-384">Previewing the timing breakdown of a request</span></span>  
> <span data-ttu-id="b5533-385">![预览请求的计时细目][ImageWaterfallHover]</span><span class="sxs-lookup"><span data-stu-id="b5533-385">![Previewing the timing breakdown of a request][ImageWaterfallHover]</span></span>  

#### <span data-ttu-id="b5533-386">已解释的计时分解阶段</span><span class="sxs-lookup"><span data-stu-id="b5533-386">Timing breakdown phases explained</span></span>   

<span data-ttu-id="b5533-387">有关 "计时" 选项卡中可能会显示的每个阶段的详细信息：</span><span class="sxs-lookup"><span data-stu-id="b5533-387">More information about each of the phases you may see in the Timing tab:</span></span>  

*   <span data-ttu-id="b5533-388">**排队**。</span><span class="sxs-lookup"><span data-stu-id="b5533-388">**Queueing**.</span></span>  <span data-ttu-id="b5533-389">浏览器在以下情况中对请求进行排队：</span><span class="sxs-lookup"><span data-stu-id="b5533-389">The browser queues requests when:</span></span>  
    *   <span data-ttu-id="b5533-390">优先级较高的请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-390">There are higher priority requests.</span></span>  
    *   <span data-ttu-id="b5533-391">已为此来源打开6个 TCP 连接，这是限制。</span><span class="sxs-lookup"><span data-stu-id="b5533-391">There are already six TCP connections open for this origin, which is the limit.</span></span>  <span data-ttu-id="b5533-392">仅适用于 HTTP/1.0 和 HTTP/1.1。</span><span class="sxs-lookup"><span data-stu-id="b5533-392">Applies to HTTP/1.0 and HTTP/1.1 only.</span></span>  
    *   <span data-ttu-id="b5533-393">浏览器在磁盘缓存中短暂分配空间。</span><span class="sxs-lookup"><span data-stu-id="b5533-393">The browser is briefly allocating space in the disk cache.</span></span>  
*   <span data-ttu-id="b5533-394">**停止**。</span><span class="sxs-lookup"><span data-stu-id="b5533-394">**Stalled**.</span></span>  <span data-ttu-id="b5533-395">由于 "**排队**" 中所述的任何原因，请求可能停止。</span><span class="sxs-lookup"><span data-stu-id="b5533-395">The request could be stalled for any of the reasons described in **Queueing**.</span></span>  
*   <span data-ttu-id="b5533-396">**DNS 查找**。</span><span class="sxs-lookup"><span data-stu-id="b5533-396">**DNS Lookup**.</span></span>  <span data-ttu-id="b5533-397">浏览器正在解析请求的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b5533-397">The browser is resolving the IP address for the request.</span></span>  
*   <span data-ttu-id="b5533-398">**代理协商**。</span><span class="sxs-lookup"><span data-stu-id="b5533-398">**Proxy negotiation**.</span></span>  <span data-ttu-id="b5533-399">浏览器正使用[代理服务器][WikiProxyServer]协商请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-399">The browser is negotiating the request with a [proxy server][WikiProxyServer].</span></span>  
*   <span data-ttu-id="b5533-400">**请求已发送**。</span><span class="sxs-lookup"><span data-stu-id="b5533-400">**Request sent**.</span></span>  <span data-ttu-id="b5533-401">正在发送请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-401">The request is being sent.</span></span>  
*   <span data-ttu-id="b5533-402">**ServiceWorker 准备**。</span><span class="sxs-lookup"><span data-stu-id="b5533-402">**ServiceWorker Preparation**.</span></span>  <span data-ttu-id="b5533-403">浏览器正在启动服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="b5533-403">The browser is starting up the service worker.</span></span>  
*   <span data-ttu-id="b5533-404">**对 ServiceWorker 的请求**。</span><span class="sxs-lookup"><span data-stu-id="b5533-404">**Request to ServiceWorker**.</span></span>  <span data-ttu-id="b5533-405">请求将发送给服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="b5533-405">The request is being sent to the service worker.</span></span>  
*   <span data-ttu-id="b5533-406">**等待 \ （TTFB \）**。</span><span class="sxs-lookup"><span data-stu-id="b5533-406">**Waiting \(TTFB\)**.</span></span>  <span data-ttu-id="b5533-407">浏览器正在等待响应的第一个字节。</span><span class="sxs-lookup"><span data-stu-id="b5533-407">The browser is waiting for the first byte of a response.</span></span>  
  <span data-ttu-id="b5533-408">TTFB 代表第一个字节的时间。</span><span class="sxs-lookup"><span data-stu-id="b5533-408">TTFB stands for Time To First Byte.</span></span>  <span data-ttu-id="b5533-409">此计时包括延迟的1次往返行程以及服务器准备响应的时间。</span><span class="sxs-lookup"><span data-stu-id="b5533-409">This timing includes 1 round trip of latency and the time the server took to prepare the response.</span></span>  
*   <span data-ttu-id="b5533-410">**内容下载**。</span><span class="sxs-lookup"><span data-stu-id="b5533-410">**Content Download**.</span></span>  <span data-ttu-id="b5533-411">浏览器正在接收响应。</span><span class="sxs-lookup"><span data-stu-id="b5533-411">The browser is receiving the response.</span></span>  
*   <span data-ttu-id="b5533-412">**接收推送**。</span><span class="sxs-lookup"><span data-stu-id="b5533-412">**Receiving Push**.</span></span>  <span data-ttu-id="b5533-413">浏览器正在通过 HTTP/2 服务器推送接收此响应的数据。</span><span class="sxs-lookup"><span data-stu-id="b5533-413">The browser is receiving data for this response via HTTP/2 Server Push.</span></span>  
*   <span data-ttu-id="b5533-414">**正在读取推送**。</span><span class="sxs-lookup"><span data-stu-id="b5533-414">**Reading Push**.</span></span>  <span data-ttu-id="b5533-415">浏览器正在读取以前收到的本地数据。</span><span class="sxs-lookup"><span data-stu-id="b5533-415">The browser is reading the local data previously received.</span></span>  

### <span data-ttu-id="b5533-416">查看启动器和相关性</span><span class="sxs-lookup"><span data-stu-id="b5533-416">View initiators and dependencies</span></span>   

<span data-ttu-id="b5533-417">若要查看请求的发起程序和依赖关系，请 `Shift` 在请求表中保留并悬停请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-417">To view the initiators and dependencies of a request, hold `Shift`and hover over the request in the Requests table.</span></span>  <span data-ttu-id="b5533-418">DevTools 颜色：启动器显示为绿色，相关性显示为红色。</span><span class="sxs-lookup"><span data-stu-id="b5533-418">DevTools colors: initiators are shown in green and dependencies are shown in red.</span></span>  

> ##### <span data-ttu-id="b5533-419">图26</span><span class="sxs-lookup"><span data-stu-id="b5533-419">Figure 26</span></span>  
> <span data-ttu-id="b5533-420">查看请求的发起人和相关性</span><span class="sxs-lookup"><span data-stu-id="b5533-420">Viewing the initiators and dependencies of a request</span></span>  
> <span data-ttu-id="b5533-421">![查看请求的发起人和依赖关系][ImageRequestInitiatorsDependencies]</span><span class="sxs-lookup"><span data-stu-id="b5533-421">![Viewing the initiators and dependencies of a request][ImageRequestInitiatorsDependencies]</span></span>  

<span data-ttu-id="b5533-422">当请求表按时间顺序排序时，悬停的第一个绿色请求上方是依赖项的发起程序。</span><span class="sxs-lookup"><span data-stu-id="b5533-422">When the Requests table is ordered chronologically, the first green request above the one you are hovering is the initiator of the dependency.</span></span>  <span data-ttu-id="b5533-423">如果在上面显示了另一个绿色请求，则该请求是发起方的发起方。</span><span class="sxs-lookup"><span data-stu-id="b5533-423">If another green request appears above that, that higher request is the initiator of the initiator.</span></span>  <span data-ttu-id="b5533-424">以此类推。</span><span class="sxs-lookup"><span data-stu-id="b5533-424">And so on.</span></span>  

### <span data-ttu-id="b5533-425">查看加载事件</span><span class="sxs-lookup"><span data-stu-id="b5533-425">View load events</span></span>   

<span data-ttu-id="b5533-426">DevTools 显示 `DOMContentLoaded` `load` 网络面板上多个位置的和事件的计时。</span><span class="sxs-lookup"><span data-stu-id="b5533-426">DevTools displays the timing of the `DOMContentLoaded` and `load` events in multiple places on the Network panel.</span></span>  <span data-ttu-id="b5533-427">`DOMContentLoaded`事件颜色为蓝色， `load` 事件为红色。</span><span class="sxs-lookup"><span data-stu-id="b5533-427">The `DOMContentLoaded` event is colored blue, and the `load` event is red.</span></span>  

> ##### <span data-ttu-id="b5533-428">图27</span><span class="sxs-lookup"><span data-stu-id="b5533-428">Figure 27</span></span>  
> <span data-ttu-id="b5533-429">" `DOMContentLoaded` `load` 网络" 面板上的 "和" 事件的位置</span><span class="sxs-lookup"><span data-stu-id="b5533-429">The locations of the `DOMContentLoaded` and `load` events on the Network panel</span></span>  
> <span data-ttu-id="b5533-430">![网络面板上 DOMContentLoaded 和加载事件的位置][ImageNetworkPanelDOMContentLoadedLoadEvents]</span><span class="sxs-lookup"><span data-stu-id="b5533-430">![The locations of the DOMContentLoaded and load events on the Network panel][ImageNetworkPanelDOMContentLoadedLoadEvents]</span></span>  

### <span data-ttu-id="b5533-431">查看请求总数</span><span class="sxs-lookup"><span data-stu-id="b5533-431">View the total number of requests</span></span>   

<span data-ttu-id="b5533-432">请求总数将列在 "摘要" 窗格中的 "网络" 面板底部。</span><span class="sxs-lookup"><span data-stu-id="b5533-432">The total number of requests is listed in the Summary pane, at the bottom of the Network panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="b5533-433">此号码仅跟踪自 DevTools 打开以来已记录的请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-433">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="b5533-434">如果在 DevTools 打开之前发生了其他请求，则不会对这些请求进行计数。</span><span class="sxs-lookup"><span data-stu-id="b5533-434">If other requests occurred before DevTools was opened, those requests are not counted.</span></span>  

> ##### <span data-ttu-id="b5533-435">图28</span><span class="sxs-lookup"><span data-stu-id="b5533-435">Figure 28</span></span>  
> <span data-ttu-id="b5533-436">自 DevTools 打开以来的请求总数</span><span class="sxs-lookup"><span data-stu-id="b5533-436">The total number of requests since DevTools was opened</span></span>  
> <span data-ttu-id="b5533-437">![自 DevTools 打开以来的请求总数][ImageTotalRequests]</span><span class="sxs-lookup"><span data-stu-id="b5533-437">![The total number of requests since DevTools was opened][ImageTotalRequests]</span></span>  

### <span data-ttu-id="b5533-438">查看总下载大小</span><span class="sxs-lookup"><span data-stu-id="b5533-438">View the total download size</span></span>   

<span data-ttu-id="b5533-439">请求的总下载大小列在 "摘要" 窗格中的 "网络" 面板底部。</span><span class="sxs-lookup"><span data-stu-id="b5533-439">The total download size of requests is listed in the Summary pane, at the bottom of the Network panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="b5533-440">此号码仅跟踪自 DevTools 打开以来已记录的请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-440">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="b5533-441">如果在 DevTools 打开之前发生了其他请求，则不会对这些请求进行计数。</span><span class="sxs-lookup"><span data-stu-id="b5533-441">If other requests occurred before DevTools was opened, those requests are not counted.</span></span>  

> ##### <span data-ttu-id="b5533-442">图29</span><span class="sxs-lookup"><span data-stu-id="b5533-442">Figure 29</span></span>  
> <span data-ttu-id="b5533-443">请求的总下载大小</span><span class="sxs-lookup"><span data-stu-id="b5533-443">The total download size of requests</span></span>  
> <span data-ttu-id="b5533-444">![请求的总下载大小][ImageTotalSize]</span><span class="sxs-lookup"><span data-stu-id="b5533-444">![The total download size of requests][ImageTotalSize]</span></span>  

<span data-ttu-id="b5533-445">请参阅[查看资源的未压缩大小](#view-the-uncompressed-size-of-a-resource)，以查看浏览器 uncompresses 每个项目后的大资源。</span><span class="sxs-lookup"><span data-stu-id="b5533-445">See [View the uncompressed size of a resource](#view-the-uncompressed-size-of-a-resource) to see how large resources are after the browser uncompresses each item.</span></span>  

### <span data-ttu-id="b5533-446">查看导致请求的堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="b5533-446">View the stack trace that caused a request</span></span>   

<span data-ttu-id="b5533-447">在 JavaScript 语句请求资源后，将鼠标悬停在**发起程序**列上以查看该请求的最后一个堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="b5533-447">After a JavaScript statement requests a resource, hover over the **Initiator** column to view the stack trace leading up to the request.</span></span>  

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

> ##### <span data-ttu-id="b5533-448">图30</span><span class="sxs-lookup"><span data-stu-id="b5533-448">Figure 30</span></span>  
> <span data-ttu-id="b5533-449">堆栈跟踪导致资源请求</span><span class="sxs-lookup"><span data-stu-id="b5533-449">The stack trace leading up to a resource request</span></span>  
> <span data-ttu-id="b5533-450">![导致资源请求的堆栈跟踪][ImageInitiatorStack]</span><span class="sxs-lookup"><span data-stu-id="b5533-450">![The stack trace leading up to a resource request][ImageInitiatorStack]</span></span>  

### <span data-ttu-id="b5533-451">查看资源的未压缩大小</span><span class="sxs-lookup"><span data-stu-id="b5533-451">View the uncompressed size of a resource</span></span>   

<span data-ttu-id="b5533-452">选中 "**使用大型请求行**" 复选框，然后查看 "**大小**" 列的底部值。</span><span class="sxs-lookup"><span data-stu-id="b5533-452">Select the **Use large request rows** checkbox and then look at the bottom value of the **Size** column.</span></span>  

> ##### <span data-ttu-id="b5533-453">图31</span><span class="sxs-lookup"><span data-stu-id="b5533-453">Figure 31</span></span>  
> <span data-ttu-id="b5533-454">未压缩资源的示例 \ （ `jquery-3.3.1.min.js` 通过网络发送的文件的压缩大小是 `29.9 KB` ，未压缩的大小为 `84.9 KB` \）</span><span class="sxs-lookup"><span data-stu-id="b5533-454">An example of uncompressed resources  \(The compressed size of the `jquery-3.3.1.min.js` file that was sent over the network was `29.9 KB`, whereas the uncompressed size was `84.9 KB`\)</span></span>  
> <span data-ttu-id="b5533-455">![未压缩资源的示例][ImageUncompressedResources]</span><span class="sxs-lookup"><span data-stu-id="b5533-455">![An example of uncompressed resources][ImageUncompressedResources]</span></span>  

## <span data-ttu-id="b5533-456">导出请求数据</span><span class="sxs-lookup"><span data-stu-id="b5533-456">Export requests data</span></span>   

### <span data-ttu-id="b5533-457">将所有网络请求保存到 HAR 文件</span><span class="sxs-lookup"><span data-stu-id="b5533-457">Save all network requests to a HAR file</span></span>   

<span data-ttu-id="b5533-458">要将所有网络请求保存到 HAR 文件，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b5533-458">To save all network requests to a HAR file:</span></span>  

1.  <span data-ttu-id="b5533-459">右键单击 "请求" 表中的任何请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-459">Right-click any request in the Requests table.</span></span>  
1.  <span data-ttu-id="b5533-460">选择 "**另存为 HAR 和内容**"。</span><span class="sxs-lookup"><span data-stu-id="b5533-460">Select **Save as HAR with Content**.</span></span>  <span data-ttu-id="b5533-461">DevTools 将打开 DevTools 后出现的所有请求保存到 HAR 文件。</span><span class="sxs-lookup"><span data-stu-id="b5533-461">DevTools saves all requests that have occurred since you opened DevTools to the HAR file.</span></span>  <span data-ttu-id="b5533-462">无法筛选请求，或仅保存单个请求。</span><span class="sxs-lookup"><span data-stu-id="b5533-462">There is no way to filter requests, or to save just a single request.</span></span>  

<span data-ttu-id="b5533-463">保存 HAR 文件后，可将其导入 DevTools 进行分析。</span><span class="sxs-lookup"><span data-stu-id="b5533-463">Once you save a HAR file, you may import it back into DevTools for analysis.</span></span>  <span data-ttu-id="b5533-464">只需将 HAR 文件拖放到 "请求" 表中。</span><span class="sxs-lookup"><span data-stu-id="b5533-464">Just drag-and-drop the HAR file into the Requests table.</span></span>  
<!--See also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

> ##### <span data-ttu-id="b5533-465">图32</span><span class="sxs-lookup"><span data-stu-id="b5533-465">Figure 32</span></span>  
> <span data-ttu-id="b5533-466">选择 "另存为 HAR 和内容"</span><span class="sxs-lookup"><span data-stu-id="b5533-466">Selecting Save as HAR with Content</span></span>  
> <span data-ttu-id="b5533-467">![选择 "另存为 HAR，含内容]"[ImageSaveAsHAR]</span><span class="sxs-lookup"><span data-stu-id="b5533-467">![Selecting Save as HAR with Content][ImageSaveAsHAR]</span></span>  

### <span data-ttu-id="b5533-468">将一个或多个请求复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="b5533-468">Copy one or more requests to the clipboard</span></span>   

<span data-ttu-id="b5533-469">在 "请求" 表的 "**名称**" 列下，右键单击请求，将鼠标悬停在 "**复制**" 上，然后选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="b5533-469">Under the **Name** column of the Requests table, right-click a request, hover over **Copy**, and select one of the following options:</span></span>  

*   <span data-ttu-id="b5533-470">**复制链接地址**。</span><span class="sxs-lookup"><span data-stu-id="b5533-470">**Copy Link Address**.</span></span>  <span data-ttu-id="b5533-471">将请求的 URL 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="b5533-471">Copy the URL of the request to the clipboard.</span></span>  
*   <span data-ttu-id="b5533-472">**复制响应**。</span><span class="sxs-lookup"><span data-stu-id="b5533-472">**Copy Response**.</span></span>  <span data-ttu-id="b5533-473">将响应正文复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="b5533-473">Copy the response body to the clipboard.</span></span>  
*   <span data-ttu-id="b5533-474">**复制为提取**。</span><span class="sxs-lookup"><span data-stu-id="b5533-474">**Copy as Fetch**.</span></span>  
*   <span data-ttu-id="b5533-475">**复制为卷曲**。</span><span class="sxs-lookup"><span data-stu-id="b5533-475">**Copy as cURL**.</span></span>  <span data-ttu-id="b5533-476">将请求复制为卷曲命令。</span><span class="sxs-lookup"><span data-stu-id="b5533-476">Copy the request as a cURL command.</span></span>  
*   <span data-ttu-id="b5533-477">**全部复制为 "提取**"。</span><span class="sxs-lookup"><span data-stu-id="b5533-477">**Copy All as Fetch**.</span></span>  
*   <span data-ttu-id="b5533-478">**全部复制为卷曲**。</span><span class="sxs-lookup"><span data-stu-id="b5533-478">**Copy All as cURL**.</span></span>  <span data-ttu-id="b5533-479">将所有请求复制为一个卷曲命令链。</span><span class="sxs-lookup"><span data-stu-id="b5533-479">Copy all requests as a chain of cURL commands.</span></span>  
*   <span data-ttu-id="b5533-480">**全部复制为 HAR**。</span><span class="sxs-lookup"><span data-stu-id="b5533-480">**Copy All as HAR**.</span></span>  <span data-ttu-id="b5533-481">将所有请求复制到 HAR 数据。</span><span class="sxs-lookup"><span data-stu-id="b5533-481">Copy all requests as HAR data.</span></span>  

> ##### <span data-ttu-id="b5533-482">图33</span><span class="sxs-lookup"><span data-stu-id="b5533-482">Figure 33</span></span>  
> <span data-ttu-id="b5533-483">选择 "复制响应"</span><span class="sxs-lookup"><span data-stu-id="b5533-483">Selecting Copy Response</span></span>  
> <span data-ttu-id="b5533-484">![选择复制答复][ImageCopyResponse]</span><span class="sxs-lookup"><span data-stu-id="b5533-484">![Selecting Copy Response][ImageCopyResponse]</span></span>  

## <span data-ttu-id="b5533-485">更改网络面板的布局</span><span class="sxs-lookup"><span data-stu-id="b5533-485">Change the layout of the Network panel</span></span>  

<span data-ttu-id="b5533-486">你可以展开或折叠 "网络面板" UI 的各个部分以重点介绍重要信息。</span><span class="sxs-lookup"><span data-stu-id="b5533-486">You may expand or collapse sections of the Network panel UI to focus important information.</span></span>  

### <span data-ttu-id="b5533-487">隐藏 "筛选器" 窗格</span><span class="sxs-lookup"><span data-stu-id="b5533-487">Hide the Filters pane</span></span>   

<span data-ttu-id="b5533-488">默认情况下，DevTools 显示 "**筛选器" 窗格**。</span><span class="sxs-lookup"><span data-stu-id="b5533-488">By default, DevTools shows the **Filters pane**.</span></span>  
<span data-ttu-id="b5533-489">选择 "**筛选** ![ 筛选" ][ImageFilterIcon] 以将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="b5533-489">Select **Filter** ![Filter][ImageFilterIcon]  to hide it.</span></span>  

> ##### <span data-ttu-id="b5533-490">图34</span><span class="sxs-lookup"><span data-stu-id="b5533-490">Figure 34</span></span>  
> <span data-ttu-id="b5533-491">"隐藏筛选器" 按钮</span><span class="sxs-lookup"><span data-stu-id="b5533-491">The Hide Filters button</span></span>  
> <span data-ttu-id="b5533-492">!["隐藏筛选器" 按钮][ImageHideFiltersButton]</span><span class="sxs-lookup"><span data-stu-id="b5533-492">![The Hide Filters button][ImageHideFiltersButton]</span></span>  

### <span data-ttu-id="b5533-493">使用大型请求行</span><span class="sxs-lookup"><span data-stu-id="b5533-493">Use large request rows</span></span>   

<span data-ttu-id="b5533-494">如果需要在网络请求表中有更多的空格，请使用较大的行。</span><span class="sxs-lookup"><span data-stu-id="b5533-494">Use large rows when you want more whitespace in your network requests table.</span></span>  <span data-ttu-id="b5533-495">在使用较大的行时，某些列还提供了一些更多的信息。</span><span class="sxs-lookup"><span data-stu-id="b5533-495">Some columns also provide a little more information when using large rows.</span></span>  <span data-ttu-id="b5533-496">例如， **Size**列的底部值是请求的未压缩大小。</span><span class="sxs-lookup"><span data-stu-id="b5533-496">For example, the bottom value of the **Size** column is the uncompressed size of a request.</span></span>  

> ##### <span data-ttu-id="b5533-497">图35</span><span class="sxs-lookup"><span data-stu-id="b5533-497">Figure 35</span></span>  
> <span data-ttu-id="b5533-498">请求窗格中的大型请求行的示例</span><span class="sxs-lookup"><span data-stu-id="b5533-498">An example of large request rows in the Requests pane</span></span>  
> <span data-ttu-id="b5533-499">![请求窗格中的大型请求行的示例][ImageLargeRequestRows]</span><span class="sxs-lookup"><span data-stu-id="b5533-499">![An example of large request rows in the Requests pane][ImageLargeRequestRows]</span></span>  

<span data-ttu-id="b5533-500">选中 "**使用大请求行**" 复选框以启用大行。</span><span class="sxs-lookup"><span data-stu-id="b5533-500">Select the **Use large request rows** checkbox to enable large rows.</span></span>  

> ##### <span data-ttu-id="b5533-501">图36</span><span class="sxs-lookup"><span data-stu-id="b5533-501">Figure 36</span></span>  
> <span data-ttu-id="b5533-502">"大型请求行" 复选框</span><span class="sxs-lookup"><span data-stu-id="b5533-502">The Large Request Rows checkbox</span></span>  
> <span data-ttu-id="b5533-503">!["大请求行" 复选框][ImageLargeRequestRowsCheckbox]</span><span class="sxs-lookup"><span data-stu-id="b5533-503">![The Large Request Rows checkbox][ImageLargeRequestRowsCheckbox]</span></span>  

### <span data-ttu-id="b5533-504">隐藏 "概述" 窗格</span><span class="sxs-lookup"><span data-stu-id="b5533-504">Hide the Overview pane</span></span>   

<span data-ttu-id="b5533-505">默认情况下，DevTools 显示 "**概述" 窗格**。</span><span class="sxs-lookup"><span data-stu-id="b5533-505">By default, DevTools shows the **Overview pane**.</span></span>  
<span data-ttu-id="b5533-506">取消选中 "**显示概述**" 复选框以将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="b5533-506">Deselect the **Show Overview** checkbox to hide it.</span></span>  

> ##### <span data-ttu-id="b5533-507">图37</span><span class="sxs-lookup"><span data-stu-id="b5533-507">Figure 37</span></span>  
> <span data-ttu-id="b5533-508">"显示概述" 复选框</span><span class="sxs-lookup"><span data-stu-id="b5533-508">The Show Overview checkbox</span></span>  
> <span data-ttu-id="b5533-509">![显示概述复选框][ImageHideOverviewCheckbox]</span><span class="sxs-lookup"><span data-stu-id="b5533-509">![The Show Overview checkbox][ImageHideOverviewCheckbox]</span></span>  

<!-->   -->  

  

<!-- image links -->  

[ImageCaptureScreenshotsIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-screenshots-icon.msft.png  
[ImageClearIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-requests-icon.msft.png  
[ImageFilterIcon]: /microsoft-edge/devtools-guide-chromium/media/filter-icon.msft.png  
[ImageHideIcon]: /microsoft-edge/devtools-guide-chromium/media/hide-overview-icon.msft.png  
[ImageLargeResourceRowsIcon]: /microsoft-edge/devtools-guide-chromium/media/large-resource-rows-button-icon.msft.png  
[ImageRecordOnIcon]: /microsoft-edge/devtools-guide-chromium/media/record-on-icon.msft.png  

[ImageNetworkPanel]: /microsoft-edge/devtools-guide-chromium/media/network-network-panel.msft.png "图1：网络面板"  
[ImageClearButton]: /microsoft-edge/devtools-guide-chromium/media/network-network-clear-button.msft.png "图2： "清除" 按钮"  
[ImagePreserveLogCheckBox]: /microsoft-edge/devtools-guide-chromium/media/network-network-preserve-log.msft.png "图3： "保留日志" 复选框"  
[ImageScreenshotHover]: /microsoft-edge/devtools-guide-chromium/media/network-network-screenshot-hover.msft.png "图4：将鼠标悬停在屏幕截图上"  
<!--[ImageReplayXHR]: /microsoft-edge/devtools-guide-chromium/media/network-replay-xhr.msft.png "Old Figure 5: Selecting Replay XHR"  -->  
<span data-ttu-id="b5533-514">[ImageDisableCacheCheckBox]：/microsoft-edge/devtools-guide-chromium/media/network-network-disable-cache-checkbox.msft.png "图5：" 禁用缓存 "复选框</span><span class="sxs-lookup"><span data-stu-id="b5533-514">[ImageDisableCacheCheckBox]: /microsoft-edge/devtools-guide-chromium/media/network-network-disable-cache-checkbox.msft.png "Figure 5: The Disable Cache checkbox"</span></span>  
<span data-ttu-id="b5533-515">[ImageClearBrowserCache]：/microsoft-edge/devtools-guide-chromium/media/network-network-clear-browser-cache.msft.png "图6：选择" 清除浏览器缓存 "</span><span class="sxs-lookup"><span data-stu-id="b5533-515">[ImageClearBrowserCache]: /microsoft-edge/devtools-guide-chromium/media/network-network-clear-browser-cache.msft.png "Figure 6: Selecting Clear Browser Cache"</span></span>  
<span data-ttu-id="b5533-516">[ImageOfflineDropdown]：/microsoft-edge/devtools-guide-chromium/media/network-network-offline-dropdown.msft.png "图7：脱机下拉菜单"</span><span class="sxs-lookup"><span data-stu-id="b5533-516">[ImageOfflineDropdown]: /microsoft-edge/devtools-guide-chromium/media/network-network-offline-dropdown.msft.png "Figure 7: The Offline dropdown menu"</span></span>  
<span data-ttu-id="b5533-517">[ImageNetworkThrottlingMenu]：/microsoft-edge/devtools-guide-chromium/media/network-network-throttling-menu.msft.png "图8：网络限制" 菜单 "</span><span class="sxs-lookup"><span data-stu-id="b5533-517">[ImageNetworkThrottlingMenu]: /microsoft-edge/devtools-guide-chromium/media/network-network-throttling-menu.msft.png "Figure 8: The Network Throttling menu"</span></span>  
<span data-ttu-id="b5533-518">[ImageClearBrowserCookies]：/microsoft-edge/devtools-guide-chromium/media/network-network-clear-browser-cookies.msft.png "图9：选择" 清除浏览器 Cookie "</span><span class="sxs-lookup"><span data-stu-id="b5533-518">[ImageClearBrowserCookies]: /microsoft-edge/devtools-guide-chromium/media/network-network-clear-browser-cookies.msft.png "Figure 9: Selecting Clear Browser Cookies"</span></span>  
<span data-ttu-id="b5533-519">[ImageFilterTextBox]：/microsoft-edge/devtools-guide-chromium/media/network-network-filters-textbox.msft.png "图10：筛选文本框"</span><span class="sxs-lookup"><span data-stu-id="b5533-519">[ImageFilterTextBox]: /microsoft-edge/devtools-guide-chromium/media/network-network-filters-textbox.msft.png "Figure 10: The Filters text box"</span></span>  
<span data-ttu-id="b5533-520">[ImageMultiTypeFilter]：/microsoft-edge/devtools-guide-chromium/media/network-network-type-filters.msft.png "图11：使用类型筛选器显示 JS、CSS 和文档资源"</span><span class="sxs-lookup"><span data-stu-id="b5533-520">[ImageMultiTypeFilter]: /microsoft-edge/devtools-guide-chromium/media/network-network-type-filters.msft.png "Figure 11: Using the Type filters to display JS, CSS, and Document resources"</span></span>  
<span data-ttu-id="b5533-521">[ImageOverviewFilter]：/microsoft-edge/devtools-guide-chromium/media/network-network-overview-filter.msft.png "图12：筛选出300ms 周围处于非活动状态的所有请求"</span><span class="sxs-lookup"><span data-stu-id="b5533-521">[ImageOverviewFilter]: /microsoft-edge/devtools-guide-chromium/media/network-network-overview-filter.msft.png "Figure 12: Filtering out any requests that were inactive around 300ms"</span></span>  
<span data-ttu-id="b5533-522">[ImageHideDataURLsCheckBox]：/microsoft-edge/devtools-guide-chromium/media/network-network-hide-data-urls.msft.png "图13：隐藏数据 Url" 复选框</span><span class="sxs-lookup"><span data-stu-id="b5533-522">[ImageHideDataURLsCheckBox]: /microsoft-edge/devtools-guide-chromium/media/network-network-hide-data-urls.msft.png "Figure 13: The Hide Data URLs checkbox"</span></span>  
<span data-ttu-id="b5533-523">[ImageWaterfallTotalDuration]：/microsoft-edge/devtools-guide-chromium/media/network-network-waterfall-total-duration.msft.png "图14：按总工期对瀑布图进行排序"</span><span class="sxs-lookup"><span data-stu-id="b5533-523">[ImageWaterfallTotalDuration]: /microsoft-edge/devtools-guide-chromium/media/network-network-waterfall-total-duration.msft.png "Figure 14: Sorting the Waterfall by total duration"</span></span>  
<span data-ttu-id="b5533-524">[ImageRequestsTable]：/microsoft-edge/devtools-guide-chromium/media/network-network-requests-table.msft.png "图15：请求表"</span><span class="sxs-lookup"><span data-stu-id="b5533-524">[ImageRequestsTable]: /microsoft-edge/devtools-guide-chromium/media/network-network-requests-table.msft.png "Figure 15: The Requests table"</span></span>  
<span data-ttu-id="b5533-525">[ImageRequestsTableAddColumn]：/microsoft-edge/devtools-guide-chromium/media/network-network-requests-add-column.msft.png "图16：将列添加到请求表"</span><span class="sxs-lookup"><span data-stu-id="b5533-525">[ImageRequestsTableAddColumn]: /microsoft-edge/devtools-guide-chromium/media/network-network-requests-add-column.msft.png "Figure 16: Adding a column to the Requests table"</span></span>  
<span data-ttu-id="b5533-526">[ImageRequestsTableCustomColumn]：/microsoft-edge/devtools-guide-chromium/media/network-network-requests-add-custom.msft.png "图17：将自定义列添加到请求表"</span><span class="sxs-lookup"><span data-stu-id="b5533-526">[ImageRequestsTableCustomColumn]: /microsoft-edge/devtools-guide-chromium/media/network-network-requests-add-custom.msft.png "Figure 17: Adding a custom column to the Requests table"</span></span>  
<span data-ttu-id="b5533-527">[ImageRequestsTableWaterfallColumn]：/microsoft-edge/devtools-guide-chromium/media/network-network-requests-waterfall.msft.png "图18：请求窗格的瀑布栏"</span><span class="sxs-lookup"><span data-stu-id="b5533-527">[ImageRequestsTableWaterfallColumn]: /microsoft-edge/devtools-guide-chromium/media/network-network-requests-waterfall.msft.png "Figure 18: The Waterfall column of the Requests pane"</span></span>  
<span data-ttu-id="b5533-528">[ImagePreview]：/microsoft-edge/devtools-guide-chromium/media/network-network-resources-preview.msft.png "图19： ' 预览 ' 选项卡"</span><span class="sxs-lookup"><span data-stu-id="b5533-528">[ImagePreview]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-preview.msft.png "Figure 19: The Preview tab"</span></span>  
<!--[ImageFrames]: /microsoft-edge/devtools-guide-chromium/media/network-frames.msft.png "Old Figure 20: The Frames tab"  -->  
<span data-ttu-id="b5533-529">[ImageResponse]：/microsoft-edge/devtools-guide-chromium/media/network-network-resources-response.msft.png "图20：响应" 选项卡 "</span><span class="sxs-lookup"><span data-stu-id="b5533-529">[ImageResponse]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-response.msft.png "Figure 20: The Response tab"</span></span>  
<span data-ttu-id="b5533-530">[ImageHeaders]：/microsoft-edge/devtools-guide-chromium/media/network-resources-headers.msft.png "图21：标题" 选项卡 "</span><span class="sxs-lookup"><span data-stu-id="b5533-530">[ImageHeaders]: /microsoft-edge/devtools-guide-chromium/media/network-resources-headers.msft.png "Figure 21: The Headers tab"</span></span>  
<span data-ttu-id="b5533-531">[ImageQueryStringParameters]：/microsoft-edge/devtools-guide-chromium/media/network-network-resources-headers-query-string-parameters.msft.png "图22：查询字符串参数" 部分 "</span><span class="sxs-lookup"><span data-stu-id="b5533-531">[ImageQueryStringParameters]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-headers-query-string-parameters.msft.png "Figure 22: The Query String Parameters section"</span></span>  
<span data-ttu-id="b5533-532">[ImageCookies]：/microsoft-edge/devtools-guide-chromium/media/network-network-resources-cookies.msft.png "图23：" Cookie "选项卡"</span><span class="sxs-lookup"><span data-stu-id="b5533-532">[ImageCookies]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-cookies.msft.png "Figure 23: The Cookies tab"</span></span>  
<span data-ttu-id="b5533-533">[ImageTiming]：/microsoft-edge/devtools-guide-chromium/media/network-network-resources-timing.msft.png "图24：计时" 选项卡 "</span><span class="sxs-lookup"><span data-stu-id="b5533-533">[ImageTiming]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-timing.msft.png "Figure 24: The Timing tab"</span></span>  
<span data-ttu-id="b5533-534">[ImageWaterfallHover]：/microsoft-edge/devtools-guide-chromium/media/network-network-resources-waterfall-hover.msft.png "图25：预览请求的计时细目"</span><span class="sxs-lookup"><span data-stu-id="b5533-534">[ImageWaterfallHover]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-waterfall-hover.msft.png "Figure 25: Previewing the timing breakdown of a request"</span></span>  
<span data-ttu-id="b5533-535">[ImageRequestInitiatorsDependencies]：/microsoft-edge/devtools-guide-chromium/media/network-network-resources-initiators-dependencies.msft.png "图26：查看请求的发起人和相关性"</span><span class="sxs-lookup"><span data-stu-id="b5533-535">[ImageRequestInitiatorsDependencies]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-initiators-dependencies.msft.png "Figure 26: Viewing the initiators and dependencies of a request"</span></span>  
<span data-ttu-id="b5533-536">[ImageNetworkPanelDOMContentLoadedLoadEvents]：/microsoft-edge/devtools-guide-chromium/media/network-network-requests-load-events.msft.png "图27： DOMContentLoaded 的位置和" 网络 "面板上的加载事件"</span><span class="sxs-lookup"><span data-stu-id="b5533-536">[ImageNetworkPanelDOMContentLoadedLoadEvents]: /microsoft-edge/devtools-guide-chromium/media/network-network-requests-load-events.msft.png "Figure 27: The locations of the DOMContentLoaded and load events on the Network panel"</span></span>  
<span data-ttu-id="b5533-537">[ImageTotalRequests]：/microsoft-edge/devtools-guide-chromium/media/network-network-total-requests.msft.png "图28：打开 DevTools 以来的请求总数"</span><span class="sxs-lookup"><span data-stu-id="b5533-537">[ImageTotalRequests]: /microsoft-edge/devtools-guide-chromium/media/network-network-total-requests.msft.png "Figure 28: The total number of requests since DevTools was opened"</span></span>  
<span data-ttu-id="b5533-538">[ImageTotalSize]：/microsoft-edge/devtools-guide-chromium/media/network-network-total-download-size.msft.png "图29：请求的总下载大小"</span><span class="sxs-lookup"><span data-stu-id="b5533-538">[ImageTotalSize]: /microsoft-edge/devtools-guide-chromium/media/network-network-total-download-size.msft.png "Figure 29: The total download size of requests"</span></span>  
<span data-ttu-id="b5533-539">[ImageInitiatorStack]：/microsoft-edge/devtools-guide-chromium/media/network-network-requests-initiator-stack.msft.png "图30：导致资源请求的堆栈跟踪"</span><span class="sxs-lookup"><span data-stu-id="b5533-539">[ImageInitiatorStack]: /microsoft-edge/devtools-guide-chromium/media/network-network-requests-initiator-stack.msft.png "Figure 30: The stack trace leading up to a resource request"</span></span>  
<span data-ttu-id="b5533-540">[ImageUncompressedResources]：/microsoft-edge/devtools-guide-chromium/media/network-network-requests-uncompressed-compare.msft.png "图31：未压缩资源的示例"</span><span class="sxs-lookup"><span data-stu-id="b5533-540">[ImageUncompressedResources]: /microsoft-edge/devtools-guide-chromium/media/network-network-requests-uncompressed-compare.msft.png "Figure 31: An example of uncompressed resources"</span></span>  
<span data-ttu-id="b5533-541">[ImageSaveAsHAR]：/microsoft-edge/devtools-guide-chromium/media/network-network-requests-save-har-content.msft.png "图32：选择" 另存为 HAR，含内容 "</span><span class="sxs-lookup"><span data-stu-id="b5533-541">[ImageSaveAsHAR]: /microsoft-edge/devtools-guide-chromium/media/network-network-requests-save-har-content.msft.png "Figure 32: Selecting Save as HAR with Content"</span></span>  
<span data-ttu-id="b5533-542">[ImageCopyResponse]：/microsoft-edge/devtools-guide-chromium/media/network-network-requests-copy-response.msft.png "图33：选择复制响应"</span><span class="sxs-lookup"><span data-stu-id="b5533-542">[ImageCopyResponse]: /microsoft-edge/devtools-guide-chromium/media/network-network-requests-copy-response.msft.png "Figure 33: Selecting Copy Response"</span></span>  
<span data-ttu-id="b5533-543">[ImageHideFiltersButton]：/microsoft-edge/devtools-guide-chromium/media/network-network-resources-hide-filters-button.msft.png "图34：" 隐藏筛选器 "按钮</span><span class="sxs-lookup"><span data-stu-id="b5533-543">[ImageHideFiltersButton]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-hide-filters-button.msft.png "Figure 34: The Hide Filters button"</span></span>  
<span data-ttu-id="b5533-544">[ImageLargeRequestRows]：/microsoft-edge/devtools-guide-chromium/media/network-network-requests-large-request-rows.msft.png "图35：请求窗格中的大型请求行的示例"</span><span class="sxs-lookup"><span data-stu-id="b5533-544">[ImageLargeRequestRows]: /microsoft-edge/devtools-guide-chromium/media/network-network-requests-large-request-rows.msft.png "Figure 35: An example of large request rows in the Requests pane"</span></span>  
<span data-ttu-id="b5533-545">[ImageLargeRequestRowsCheckbox]：/microsoft-edge/devtools-guide-chromium/media/network-network-requests-use-large-request-rows-on.msft.png "图36：大型请求行" 复选框 "</span><span class="sxs-lookup"><span data-stu-id="b5533-545">[ImageLargeRequestRowsCheckbox]: /microsoft-edge/devtools-guide-chromium/media/network-network-requests-use-large-request-rows-on.msft.png "Figure 36: The Large Request Rows checkbox"</span></span>  
<span data-ttu-id="b5533-546">[ImageHideOverviewCheckbox]：/microsoft-edge/devtools-guide-chromium/media/network-network-requests-show-overview-off.msft.png "图37：隐藏概述复选框"</span><span class="sxs-lookup"><span data-stu-id="b5533-546">[ImageHideOverviewCheckbox]: /microsoft-edge/devtools-guide-chromium/media/network-network-requests-show-overview-off.msft.png "Figure 37: The Hide Overview checkbox"</span></span>  

<!-- links -->  

[DevtoolsProgressiveWebApps]: /microsoft-edge/devtools-guide-chromium/network/progressive-web-apps "调试渐进式 Web 应用"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "数据 Url |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "代理服务器-维基百科"  

> [!NOTE]
> <span data-ttu-id="b5533-550">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="b5533-550">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b5533-551">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/reference)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="b5533-551">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="b5533-553">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="b5533-553">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
