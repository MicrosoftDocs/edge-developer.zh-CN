---
title: 网络分析参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: c9d205fb2cc478e9c3f20458f461f004035e85e8
ms.sourcegitcommit: a34858dd3260967ba9699842fa839c7a94775fe4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2020
ms.locfileid: "10710397"
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

# <span data-ttu-id="7b576-103">网络分析参考</span><span class="sxs-lookup"><span data-stu-id="7b576-103">Network Analysis Reference</span></span>  

<span data-ttu-id="7b576-104">了解在 Microsoft Edge DevTools 网络分析功能的这一全面参考中，分析页面加载方式的新方法。</span><span class="sxs-lookup"><span data-stu-id="7b576-104">Discover new ways to analyze how your page loads in this comprehensive reference of Microsoft Edge DevTools network analysis features.</span></span>  

<!--
> [!NOTE]
> This reference is based on Microsoft Edge 58.  If you use another version of Microsoft Edge, the UI, and features of DevTools may be different.  Check `edge://help` to see what version of Microsoft Edge you are running.  
-->

## <span data-ttu-id="7b576-105">记录网络请求</span><span class="sxs-lookup"><span data-stu-id="7b576-105">Record network requests</span></span>  

<span data-ttu-id="7b576-106">默认情况下，DevTools 将在网络面板中记录所有网络请求，只要 DevTools 已打开。</span><span class="sxs-lookup"><span data-stu-id="7b576-106">By default, DevTools records all network requests in the Network panel, so long as DevTools is open.</span></span>  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="网络面板" lightbox="../media/network-network-panel.msft.png":::
   <span data-ttu-id="7b576-108">图1：**网络**面板</span><span class="sxs-lookup"><span data-stu-id="7b576-108">Figure 1:  The **Network** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-109">停止记录网络请求</span><span class="sxs-lookup"><span data-stu-id="7b576-109">Stop recording network requests</span></span>  

<span data-ttu-id="7b576-110">若要停止录制请求，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7b576-110">To stop recording requests, complete the following steps.</span></span>  

1.  <span data-ttu-id="7b576-111">选择 "**停止录制网络日志**" ![ 停止 ][ImageRecordOnIcon] 在**网络**面板上记录网络日志。</span><span class="sxs-lookup"><span data-stu-id="7b576-111">Select **Stop recording network log** ![Stop recording network log][ImageRecordOnIcon] on the **Network** panel.</span></span>  <span data-ttu-id="7b576-112">它将变为灰色，指示 DevTools 不再录制请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-112">It turns grey to indicate that DevTools is no longer recording requests.</span></span>  
1.  <span data-ttu-id="7b576-113">`Control` + `E` 在 "网络" 面板处于聚焦状态时，按 \ （Windows \）或 `Command` + `E` \ （macOS \）。 **Network**</span><span class="sxs-lookup"><span data-stu-id="7b576-113">Press `Control`+`E` \(Windows\) or `Command`+`E` \(macOS\) while the **Network** panel is in focus.</span></span>  

### <span data-ttu-id="7b576-114">清除请求</span><span class="sxs-lookup"><span data-stu-id="7b576-114">Clear requests</span></span>  

<span data-ttu-id="7b576-115">**Clear** ![ ][ImageClearIcon] 在 "网络" 面板上选择 "清除清除"，清除 "请求" 表中的所有请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-115">Select **Clear** ![Clear][ImageClearIcon] on the Network panel to clear all requests from the Requests table.</span></span>  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text=""清除" 按钮" lightbox="../media/network-network-clear-button.msft.png":::
   <span data-ttu-id="7b576-117">图2： "**清除**" 按钮</span><span class="sxs-lookup"><span data-stu-id="7b576-117">Figure 2:  The **Clear** button</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-118">跨页面加载保存请求</span><span class="sxs-lookup"><span data-stu-id="7b576-118">Save requests across page loads</span></span>  

<span data-ttu-id="7b576-119">若要在每个页面加载期间保存请求，请选中 "网络" 面板上的 "**保留日志**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="7b576-119">To save requests across page loads, check the **Preserve log** checkbox on the Network panel.</span></span>  <span data-ttu-id="7b576-120">DevTools 将保存所有请求，直到你禁用**保留日志**。</span><span class="sxs-lookup"><span data-stu-id="7b576-120">DevTools saves all requests until you disable **Preserve log**.</span></span>  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text=""保留日志" 复选框" lightbox="../media/network-network-preserve-log.msft.png":::
   <span data-ttu-id="7b576-122">图3： "**保留日志**" 复选框</span><span class="sxs-lookup"><span data-stu-id="7b576-122">Figure 3:  The **Preserve Log** checkbox</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-123">在页面加载期间捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="7b576-123">Capture screenshots during page load</span></span>  

<span data-ttu-id="7b576-124">捕获屏幕截图，分析用户在等待页面加载时看到的内容。</span><span class="sxs-lookup"><span data-stu-id="7b576-124">Capture screenshots to analyze what users see as they wait for your page to load.</span></span>  

<span data-ttu-id="7b576-125">若要启用屏幕截图，请选择 "**网络设置**"，然后选择**网络**面板上的 "**捕获屏幕截图**" 复选框</span><span class="sxs-lookup"><span data-stu-id="7b576-125">To enable screenshots, select **Network settings** and select **Capture screenshots** checkbox on the **Network** panel.</span></span>  

<span data-ttu-id="7b576-126">在 "**网络**" 面板处于焦点时刷新页面以捕获屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="7b576-126">Refresh the page while the **Network** panel is in focus to capture screenshots.</span></span>  

<span data-ttu-id="7b576-127">捕获屏幕截图后，可通过以下方式与之交互。</span><span class="sxs-lookup"><span data-stu-id="7b576-127">After capturing a screenshot, you interact with it in the following ways.</span></span>  

*   <span data-ttu-id="7b576-128">将鼠标悬停在屏幕截图上以查看捕获该屏幕截图的位置。</span><span class="sxs-lookup"><span data-stu-id="7b576-128">Hover over a screenshot to view the point at which that screenshot was captured.</span></span>  <span data-ttu-id="7b576-129">"**概述**" 窗格上将显示一个黄色线条。</span><span class="sxs-lookup"><span data-stu-id="7b576-129">A yellow line appears on the **Overview** pane.</span></span>  
*   <span data-ttu-id="7b576-130">选择屏幕的缩略图，以筛选出捕获屏幕截图后发生的任何请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-130">Select the thumbnail of a screen to filter out any requests that occurred after the screenshot was captured.</span></span>  
*   <span data-ttu-id="7b576-131">双击缩略图以放大缩略图。</span><span class="sxs-lookup"><span data-stu-id="7b576-131">Double-click a thumbnail to zoom into it.</span></span>  

:::image type="complex" source="../media/network-network-screenshot-hover.msft.png" alt-text="将鼠标悬停在屏幕截图上" lightbox="../media/network-network-screenshot-hover.msft.png":::
   <span data-ttu-id="7b576-133">图4：将鼠标悬停在屏幕截图上</span><span class="sxs-lookup"><span data-stu-id="7b576-133">Figure 4:  Hovering over a screenshot</span></span>  
:::image-end:::  

<!--  ### Replay XHR request  -->

<!--  To replay an XHR request, hover on the request in the Requests table, open the contextual menu \(right-click\), and select **Replay XHR**.  -->

<!--  
:::image type="complex" source="../media/network-replay-xhr.msft.png" alt-text="Selecting Replay XHR" lightbox="../media/network-replay-xhr.msft.png":::
   Old Figure 5:  Selecting Replay XHR  
:::image-end:::  
-->  

## <span data-ttu-id="7b576-134">更改加载行为</span><span class="sxs-lookup"><span data-stu-id="7b576-134">Change loading behavior</span></span>  

### <span data-ttu-id="7b576-135">通过禁用浏览器缓存来模拟首次访问者</span><span class="sxs-lookup"><span data-stu-id="7b576-135">Emulate a first-time visitor by disabling the browser cache</span></span>  

<span data-ttu-id="7b576-136">若要模拟首次用户体验你的网站的情况，请选中 "**禁用缓存**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="7b576-136">To emulate how a first-time user experiences your site, check the **Disable cache** checkbox.</span></span>  <span data-ttu-id="7b576-137">DevTools 禁用浏览器缓存。</span><span class="sxs-lookup"><span data-stu-id="7b576-137">DevTools disables the browser cache.</span></span>  <span data-ttu-id="7b576-138">这将更准确地模拟第一次用户的体验，因为在重复访问时从浏览器缓存提供请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-138">This more accurately emulates a first-time user's experience, because requests are served from the browser cache on repeat visits.</span></span>  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text=""禁用缓存" 复选框" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   <span data-ttu-id="7b576-140">图5： "**禁用缓存**" 复选框</span><span class="sxs-lookup"><span data-stu-id="7b576-140">Figure 5:  The **Disable Cache** checkbox</span></span>  
:::image-end:::  

#### <span data-ttu-id="7b576-141">从网络条件抽屉中禁用浏览器缓存</span><span class="sxs-lookup"><span data-stu-id="7b576-141">Disable the browser cache from the Network Conditions drawer</span></span>  

<span data-ttu-id="7b576-142">如果想要在其他 DevTools 面板中工作时禁用缓存，请使用网络条件抽屉。</span><span class="sxs-lookup"><span data-stu-id="7b576-142">If you want to disable the cache while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="7b576-143">打开**网络条件**抽屉。</span><span class="sxs-lookup"><span data-stu-id="7b576-143">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="7b576-144">选中或取消选中 "**禁用缓存**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="7b576-144">Check or uncheck the **Disable cache** checkbox.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="7b576-145">手动清除浏览器缓存</span><span class="sxs-lookup"><span data-stu-id="7b576-145">Manually clear the browser cache</span></span>  

<span data-ttu-id="7b576-146">若要随时手动清除浏览器缓存，请在 "请求" 表中的任意位置打开上下文菜单 \ （右键单击 \），然后选择 "**清除浏览器缓存**"。</span><span class="sxs-lookup"><span data-stu-id="7b576-146">To manually clear the browser cache at any time, open the contextual menu \(right-click\) anywhere in the Requests table and select **Clear Browser Cache**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="选择 "清除浏览器缓存"" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   <span data-ttu-id="7b576-148">图6：选择 "**清除浏览器缓存**"</span><span class="sxs-lookup"><span data-stu-id="7b576-148">Figure 6:  Selecting **Clear Browser Cache**</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-149">模拟脱机</span><span class="sxs-lookup"><span data-stu-id="7b576-149">Emulate offline</span></span>  

<span data-ttu-id="7b576-150">新的 web 应用类（名为 "[渐进式 Web 应用][DevtoolsProgressiveWebApps]"）使用**服务工作人员**帮助脱机工作。</span><span class="sxs-lookup"><span data-stu-id="7b576-150">A new class of web apps, named [Progressive Web Apps][DevtoolsProgressiveWebApps], functions offline with the help of **service workers**.</span></span>  <span data-ttu-id="7b576-151">你可能会发现，在你构建此类型的应用时，快速模拟没有数据连接的设备非常有用。</span><span class="sxs-lookup"><span data-stu-id="7b576-151">You may find it useful to quickly simulate a device that has no data connection when you are building this type of app.</span></span>  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

<span data-ttu-id="7b576-152">选择 "**联机**" 下拉菜单，在 "**预置**" 下搜索，然后选择 "**脱机**" 以模拟完全脱机的网络体验。</span><span class="sxs-lookup"><span data-stu-id="7b576-152">Select the **Online** dropdown menu, search under **Presets**, and select **Offline** to simulate a completely offline network experience.</span></span>  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text=""脱机" 下拉菜单" lightbox="../media/network-network-offline-dropdown.msft.png":::
   <span data-ttu-id="7b576-154">图7：**脱机**下拉菜单</span><span class="sxs-lookup"><span data-stu-id="7b576-154">Figure 7:  The **Offline** dropdown menu</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-155">模拟慢速网络连接</span><span class="sxs-lookup"><span data-stu-id="7b576-155">Emulate slow network connections</span></span>  

<span data-ttu-id="7b576-156">从 "**联机**" 下拉菜单中模拟慢速3G、快速3g 和其他连接速度。</span><span class="sxs-lookup"><span data-stu-id="7b576-156">Emulate Slow 3G, Fast 3G, and other connection speeds from the **Online** dropdown menu.</span></span>  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text="限制下拉菜单" lightbox="../media/network-network-throttling-menu.msft.png":::
   <span data-ttu-id="7b576-158">图8：**限制**下拉菜单</span><span class="sxs-lookup"><span data-stu-id="7b576-158">Figure 8:  The **Throttling** dropdown menu</span></span>  
:::image-end:::  

<span data-ttu-id="7b576-159">您可以从各种预设（如低速3G 或快速3G）中进行选择。</span><span class="sxs-lookup"><span data-stu-id="7b576-159">You may select from a variety of presets, such as Slow 3G or Fast 3G.</span></span>  <span data-ttu-id="7b576-160">您也可以通过打开 "限制" 菜单并选择 "**自定义**添加" 来添加自己的自定义预设  >  **Add**。</span><span class="sxs-lookup"><span data-stu-id="7b576-160">You may also add your own custom presets by opening the Throttling menu and selecting **Custom** > **Add**.</span></span>  

<span data-ttu-id="7b576-161">DevTools 将在 "**网络**" 选项卡旁显示一个警告图标，提醒你已启用限制。</span><span class="sxs-lookup"><span data-stu-id="7b576-161">DevTools displays a warning icon next to the **Network** tab to remind you that throttling is enabled.</span></span>  

#### <span data-ttu-id="7b576-162">从网络条件抽屉中模拟慢速网络连接</span><span class="sxs-lookup"><span data-stu-id="7b576-162">Emulate slow network connections from the Network Conditions drawer</span></span>  

<span data-ttu-id="7b576-163">如果您希望在其他 DevTools 面板中工作时限制网络连接，请使用网络条件抽屉。</span><span class="sxs-lookup"><span data-stu-id="7b576-163">If you want to throttle the network connection while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="7b576-164">打开**网络条件**抽屉。</span><span class="sxs-lookup"><span data-stu-id="7b576-164">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="7b576-165">从 "**限制**" 菜单中选择所需的连接速度。</span><span class="sxs-lookup"><span data-stu-id="7b576-165">Select your desired connection speed from the **Throttling** menu.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="7b576-166">手动清除浏览器 cookie</span><span class="sxs-lookup"><span data-stu-id="7b576-166">Manually clear browser cookies</span></span>  

<span data-ttu-id="7b576-167">若要随时手动清除浏览器 cookie，请在 "请求" 表中的任意位置打开上下文菜单 \ （右键单击 \），然后选择 "**清除浏览器 cookie**"。</span><span class="sxs-lookup"><span data-stu-id="7b576-167">To manually clear browser cookies at any time, open the contextual menu \(right-click\) anywhere in the Requests table and select **Clear Browser Cookies**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="选择 "清除浏览器 Cookie"" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   <span data-ttu-id="7b576-169">图9：选择 "**清除浏览器 cookie** "</span><span class="sxs-lookup"><span data-stu-id="7b576-169">Figure 9:  Selecting **Clear Browser Cookies**</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-170">替代用户代理</span><span class="sxs-lookup"><span data-stu-id="7b576-170">Override the user agent</span></span>  

<span data-ttu-id="7b576-171">要手动替代用户代理，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b576-171">To manually override the user agent:</span></span>  

1.  <span data-ttu-id="7b576-172">打开**网络条件**抽屉。</span><span class="sxs-lookup"><span data-stu-id="7b576-172">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="7b576-173">取消选中 "**自动**"。</span><span class="sxs-lookup"><span data-stu-id="7b576-173">Uncheck **Select automatically**.</span></span>  
1.  <span data-ttu-id="7b576-174">从菜单中选择用户代理选项，或在文本框中输入自定义选项。</span><span class="sxs-lookup"><span data-stu-id="7b576-174">Choose a user agent option from the menu, or enter a custom one in the text box.</span></span>  

<!--todo: add network condition section when available -->  

## <span data-ttu-id="7b576-175">筛选请求</span><span class="sxs-lookup"><span data-stu-id="7b576-175">Filter requests</span></span>  

### <span data-ttu-id="7b576-176">按属性筛选请求</span><span class="sxs-lookup"><span data-stu-id="7b576-176">Filter requests by properties</span></span>  

<span data-ttu-id="7b576-177">使用 "**筛选**" 文本框筛选按属性（如请求的域或大小）的请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-177">Use the **Filter** text box to filter requests by properties, such as the domain or size of the request.</span></span>  

<span data-ttu-id="7b576-178">如果看不到文本框，则 "筛选器" 窗格可能已隐藏。</span><span class="sxs-lookup"><span data-stu-id="7b576-178">If you do not see the text box, the Filters pane is probably hidden.</span></span>  
<span data-ttu-id="7b576-179">请参阅[隐藏筛选器窗格](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="7b576-179">See [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text=""筛选器" 文本框" lightbox="../media/network-network-filters-textbox.msft.png":::
   <span data-ttu-id="7b576-181">图10： "**筛选**" 文本框</span><span class="sxs-lookup"><span data-stu-id="7b576-181">Figure 10:  The **Filter** text box</span></span>  
:::image-end:::  

<span data-ttu-id="7b576-182">你可以通过使用空格分隔每个属性来同时使用多个属性。</span><span class="sxs-lookup"><span data-stu-id="7b576-182">You may use multiple properties simultaneously by separating each property with a space.</span></span>  <span data-ttu-id="7b576-183">例如， `mime-type:image/png larger-than:1K` 显示大于 1 kb 的所有 PNGs。</span><span class="sxs-lookup"><span data-stu-id="7b576-183">For example, `mime-type:image/png larger-than:1K` displays all PNGs that are larger than one kilobyte.</span></span>  <span data-ttu-id="7b576-184">这些多属性筛选器等效于 `AND` 操作。</span><span class="sxs-lookup"><span data-stu-id="7b576-184">These multi-property filters are equivalent to `AND` operations.</span></span>  `OR` <span data-ttu-id="7b576-185">当前不支持操作。</span><span class="sxs-lookup"><span data-stu-id="7b576-185">operations are currently not supported.</span></span>  

<span data-ttu-id="7b576-186">受支持的属性的完整列表。</span><span class="sxs-lookup"><span data-stu-id="7b576-186">The complete list of supported properties.</span></span>  

| <span data-ttu-id="7b576-187">属性</span><span class="sxs-lookup"><span data-stu-id="7b576-187">Property</span></span> | <span data-ttu-id="7b576-188">详细信息</span><span class="sxs-lookup"><span data-stu-id="7b576-188">Details</span></span> |  
|:--- | :--- |  
| `domain` | <span data-ttu-id="7b576-189">仅显示指定域中的资源。</span><span class="sxs-lookup"><span data-stu-id="7b576-189">Only display resources from the specified domain.</span></span>  <span data-ttu-id="7b576-190">您可以使用通配符 \ （ `*` \）包含多个域。</span><span class="sxs-lookup"><span data-stu-id="7b576-190">You may use a wildcard character \(`*`\) to include multiple domains.</span></span>  <span data-ttu-id="7b576-191">例如， `*.com` 显示所有以结尾的域名的资源 `.com` 。</span><span class="sxs-lookup"><span data-stu-id="7b576-191">For example, `*.com` displays resources from all domain names ending in `.com`.</span></span>  <span data-ttu-id="7b576-192">DevTools 将填充 "自动完成" 下拉菜单，其中包含它遇到的所有域。</span><span class="sxs-lookup"><span data-stu-id="7b576-192">DevTools populates the autocomplete dropdown menu with all of the domains it has encountered.</span></span> |  
| `has-response-header` | <span data-ttu-id="7b576-193">显示包含指定的 HTTP 响应标头的资源。</span><span class="sxs-lookup"><span data-stu-id="7b576-193">Show the resources that contain the specified HTTP response header.</span></span>  <span data-ttu-id="7b576-194">DevTools 将填充 "自动完成" 下拉列表，其中包含已遇到的所有响应标题。</span><span class="sxs-lookup"><span data-stu-id="7b576-194">DevTools populates the autocomplete dropdown with all of the response headers that it has encountered.</span></span> |  
| `is` | <span data-ttu-id="7b576-195">用于 `is:running` 查找 `WebSocket` 资源。</span><span class="sxs-lookup"><span data-stu-id="7b576-195">Use `is:running` to find `WebSocket` resources.</span></span> |  
| `larger-than` | <span data-ttu-id="7b576-196">显示大于指定大小的资源（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="7b576-196">Show resources that are larger than the specified size, in bytes.</span></span>  <span data-ttu-id="7b576-197">设置值 `1000` 等效于将值设置为 `1k` 。</span><span class="sxs-lookup"><span data-stu-id="7b576-197">Setting a value of `1000` is equivalent to setting a value of `1k`.</span></span> |  
| `method` | <span data-ttu-id="7b576-198">显示通过指定的 HTTP 方法类型检索的资源。</span><span class="sxs-lookup"><span data-stu-id="7b576-198">Show resources that were retrieved over a specified HTTP method type.</span></span>  <span data-ttu-id="7b576-199">DevTools 将用它遇到的所有 HTTP 方法填充下拉列表。</span><span class="sxs-lookup"><span data-stu-id="7b576-199">DevTools populates the dropdown with all of the HTTP methods it has encountered.</span></span> |  
| `mime-type` | <span data-ttu-id="7b576-200">显示指定 MIME 类型的资源。</span><span class="sxs-lookup"><span data-stu-id="7b576-200">Show resources of a specified MIME type.</span></span>  <span data-ttu-id="7b576-201">DevTools 将用遇到的所有 MIME 类型填充下拉列表。</span><span class="sxs-lookup"><span data-stu-id="7b576-201">DevTools populates the dropdown with all MIME types it has encountered.</span></span> |  
| `mixed-content` | <span data-ttu-id="7b576-202">显示所有混合内容资源 \ （ `mixed-content:all` \）或仅显示当前显示的所有混合内容资源 \ （ `mixed-content:displayed` \）。</span><span class="sxs-lookup"><span data-stu-id="7b576-202">Show all mixed content resources \(`mixed-content:all`\) or just the ones that are currently displayed \(`mixed-content:displayed`\).</span></span> |  
| `scheme` | <span data-ttu-id="7b576-203">显示通过未受保护的 HTTP \ （ `scheme:http` \）或受保护的 HTTPS \ （ `scheme:https` \）检索的资源。</span><span class="sxs-lookup"><span data-stu-id="7b576-203">Show resources retrieved over unprotected HTTP \(`scheme:http`\) or protected HTTPS \(`scheme:https`\).</span></span> |  
| `set-cookie-domain` | <span data-ttu-id="7b576-204">显示具有 `Set-Cookie` 与指定值匹配的属性的标题的资源 `Domain` 。</span><span class="sxs-lookup"><span data-stu-id="7b576-204">Show the resources that have a `Set-Cookie` header with a `Domain` attribute that matches the specified value.</span></span>  <span data-ttu-id="7b576-205">DevTools 将填充所遇到的所有 cookie 域的自动完成功能。</span><span class="sxs-lookup"><span data-stu-id="7b576-205">DevTools populates the autocomplete with all of the cookie domains that it has encountered.</span></span> |  
| `set-cookie-name` | <span data-ttu-id="7b576-206">显示具有 `Set-Cookie` 与指定值匹配的名称的标题的资源。</span><span class="sxs-lookup"><span data-stu-id="7b576-206">Show the resources that have a `Set-Cookie` header with a name that matches the specified value.</span></span>  <span data-ttu-id="7b576-207">DevTools 将用遇到的所有 cookie 名称填充记忆式键入。</span><span class="sxs-lookup"><span data-stu-id="7b576-207">DevTools populates the autocomplete with all of the cookie names that it has encountered.</span></span> |  
| `set-cookie-value` | <span data-ttu-id="7b576-208">显示具有与 `Set-Cookie` 指定值匹配的值的标题的资源。</span><span class="sxs-lookup"><span data-stu-id="7b576-208">Show the resources that have a `Set-Cookie` header with a value that matches the specified value.</span></span>  <span data-ttu-id="7b576-209">DevTools 将用遇到的所有 cookie 值填充记忆式键入。</span><span class="sxs-lookup"><span data-stu-id="7b576-209">DevTools populates the autocomplete with all of the cookie values that it has encountered.</span></span> |  
| `status-code` | <span data-ttu-id="7b576-210">仅显示 HTTP 状态代码与指定代码匹配的资源。</span><span class="sxs-lookup"><span data-stu-id="7b576-210">Show only the resources for which the HTTP status code matches the specified code.</span></span>  <span data-ttu-id="7b576-211">DevTools 将填充 "自动完成" 下拉菜单，其中包含遇到的所有状态代码。</span><span class="sxs-lookup"><span data-stu-id="7b576-211">DevTools populates the autocomplete dropdown menu with all of the status codes it has encountered.</span></span> |  

### <span data-ttu-id="7b576-212">按类型筛选请求</span><span class="sxs-lookup"><span data-stu-id="7b576-212">Filter requests by type</span></span>  

<span data-ttu-id="7b576-213">若要按请求类型筛选请求，请选择 "网络" 面板上的**XHR**、 **JS**、 **CSS**、 **Img**、**媒体**、**字体**、**文档**、 **WS** \ （WebSocket \）、**清单**或**其他**\ （此处未列出的任何其他类型 \）按钮。</span><span class="sxs-lookup"><span data-stu-id="7b576-213">To filter requests by request type, select the **XHR**, **JS**, **CSS**, **Img**, **Media**, **Font**, **Doc**, **WS** \(WebSocket\), **Manifest**, or **Other** \(any other type not listed here\) buttons on the Network panel.</span></span>  

<span data-ttu-id="7b576-214">如果看不到这些按钮，则 "筛选器" 窗格可能处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="7b576-214">If you do not see these buttons, the Filters pane is probably hidden.</span></span>  
<span data-ttu-id="7b576-215">请参阅[隐藏筛选器窗格](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="7b576-215">See [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

<span data-ttu-id="7b576-216">若要同时启用多个类型筛选器，请按住 `Control` \ （Windows \）或 `Command` \ （macOS \），然后选择。</span><span class="sxs-lookup"><span data-stu-id="7b576-216">To enable multiple type filters simultaneously, hold `Control` \(Windows\) or `Command` \(macOS\) and then select.</span></span>  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="使用类型筛选器显示 JS、CSS 和文档资源" lightbox="../media/network-network-type-filters.msft.png":::
   <span data-ttu-id="7b576-218">图11：使用类型筛选器显示 JS、CSS 和文档资源</span><span class="sxs-lookup"><span data-stu-id="7b576-218">Figure 11:  Using the Type filters to display JS, CSS, and Document resources</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-219">按时间筛选请求</span><span class="sxs-lookup"><span data-stu-id="7b576-219">Filter requests by time</span></span>  

<span data-ttu-id="7b576-220">在 "概述" 窗格中选择并向左或向右拖动，以仅显示在该时间范围内处于活动状态的请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-220">Select and drag left or right on the Overview pane to only display requests that were active during that time frame.</span></span>  <span data-ttu-id="7b576-221">筛选器是包含的。</span><span class="sxs-lookup"><span data-stu-id="7b576-221">The filter is inclusive.</span></span>  <span data-ttu-id="7b576-222">显示在突出显示的时间内处于活动状态的任何请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-222">Any request that was active during the highlighted time is shown.</span></span>  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="筛选出在300ms 周围处于非活动状态的任何请求" lightbox="../media/network-network-overview-filter.msft.png":::
   <span data-ttu-id="7b576-224">图12：筛选出在300ms 周围处于非活动状态的任何请求</span><span class="sxs-lookup"><span data-stu-id="7b576-224">Figure 12:  Filtering out any requests that were inactive around 300ms</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-225">隐藏数据 Url</span><span class="sxs-lookup"><span data-stu-id="7b576-225">Hide data URLs</span></span>  

<span data-ttu-id="7b576-226">[数据 url][MDNHTTPDataURIs]是嵌入到其他文档中的小文件。</span><span class="sxs-lookup"><span data-stu-id="7b576-226">[Data URLs][MDNHTTPDataURIs] are small files embedded into other documents.</span></span>  <span data-ttu-id="7b576-227">在 "请求" 表中看到的以数据 URL 开头的任何请求 `data:` 。</span><span class="sxs-lookup"><span data-stu-id="7b576-227">Any request that you see in the Requests table that starts with `data:` is a data URL.</span></span>  

<span data-ttu-id="7b576-228">选中 "**隐藏数据 url** " 复选框以隐藏请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-228">Check the **Hide data URLs** checkbox to hide the requests.</span></span>  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text=""隐藏数据 Url" 复选框" lightbox="../media/network-network-hide-data-urls.msft.png":::
   <span data-ttu-id="7b576-230">图13： "**隐藏数据 Url** " 复选框</span><span class="sxs-lookup"><span data-stu-id="7b576-230">Figure 13:  The **Hide Data URLs** checkbox</span></span>  
:::image-end:::  

## <span data-ttu-id="7b576-231">排序请求</span><span class="sxs-lookup"><span data-stu-id="7b576-231">Sort requests</span></span>  

<span data-ttu-id="7b576-232">默认情况下，请求表中的请求按初始时间排序，但你可以使用其他条件对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="7b576-232">By default, the requests in the Requests table are sorted by initiation time, but you may sort the table using other criteria.</span></span>  

### <span data-ttu-id="7b576-233">按列排序</span><span class="sxs-lookup"><span data-stu-id="7b576-233">Sort by column</span></span>  

<span data-ttu-id="7b576-234">选择请求中的任何列的标题，对该列的请求进行排序。</span><span class="sxs-lookup"><span data-stu-id="7b576-234">Select the header of any column in the Requests to sort requests by that column.</span></span>  

### <span data-ttu-id="7b576-235">按活动阶段排序</span><span class="sxs-lookup"><span data-stu-id="7b576-235">Sort by activity phase</span></span>  

<span data-ttu-id="7b576-236">若要更改瀑布对请求的排序方式，请将鼠标悬停在 "请求" 表的标题上，打开上下文菜单 \ （右键单击 \），将鼠标悬停在**瀑布**上，然后选择下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="7b576-236">To change how the Waterfall sorts requests, hover on the header of the Requests table, open the contextual menu \(right-click\), hover over **Waterfall**, and select one of the following options.</span></span>  

*   <span data-ttu-id="7b576-237">**开始时间**。</span><span class="sxs-lookup"><span data-stu-id="7b576-237">**Start Time**.</span></span>  <span data-ttu-id="7b576-238">启动的第一个请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="7b576-238">The first request that was initiated is at the top.</span></span>  
*   <span data-ttu-id="7b576-239">**响应时间**。</span><span class="sxs-lookup"><span data-stu-id="7b576-239">**Response Time**.</span></span>  <span data-ttu-id="7b576-240">开始下载的第一个请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="7b576-240">The first request that started downloading is at the top.</span></span>  
*   <span data-ttu-id="7b576-241">**结束时间**。</span><span class="sxs-lookup"><span data-stu-id="7b576-241">**End Time**.</span></span>  <span data-ttu-id="7b576-242">第一个已完成的请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="7b576-242">The first request that finished is at the top.</span></span>  
*   <span data-ttu-id="7b576-243">**总工期**。</span><span class="sxs-lookup"><span data-stu-id="7b576-243">**Total Duration**.</span></span>  <span data-ttu-id="7b576-244">具有最短连接设置和请求/响应的请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="7b576-244">The request with the shortest connection setup and request / response is at the top.</span></span>  
*   <span data-ttu-id="7b576-245">**延迟**。</span><span class="sxs-lookup"><span data-stu-id="7b576-245">**Latency**.</span></span>  <span data-ttu-id="7b576-246">等待响应时间最短的请求位于最前面。</span><span class="sxs-lookup"><span data-stu-id="7b576-246">The request that waited the shortest time for a response is at the top.</span></span>  

<span data-ttu-id="7b576-247">这些说明假定每个各自的选项均按最短到最长的排序。</span><span class="sxs-lookup"><span data-stu-id="7b576-247">These descriptions assume that each respective option is ranked from shortest to longest.</span></span>  <span data-ttu-id="7b576-248">选择**瀑布**栏的标题将反转顺序。</span><span class="sxs-lookup"><span data-stu-id="7b576-248">Selecting the header of the **Waterfall** column reverses the order.</span></span>  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="按总工期对瀑布图进行排序" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   <span data-ttu-id="7b576-250">图14：按总工期对瀑布图进行排序 \ （每个条形图的较亮部分是等待的时间，较暗的部分是下载字节所花费的时间）</span><span class="sxs-lookup"><span data-stu-id="7b576-250">Figure 14:  Sorting the Waterfall by total duration  \(The lighter portion of each bar is time spent waiting and the darker portion is time spent downloading bytes\)</span></span>  
:::image-end:::  

## <span data-ttu-id="7b576-251">分析请求</span><span class="sxs-lookup"><span data-stu-id="7b576-251">Analyze requests</span></span>  

<span data-ttu-id="7b576-252">只要 DevTools 打开，它就会在 "网络" 面板中记录所有请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-252">So long as DevTools is open, it logs all requests in the Network panel.</span></span>  
<span data-ttu-id="7b576-253">使用 "网络" 面板分析请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-253">Use the Network panel to analyze requests.</span></span>  

### <span data-ttu-id="7b576-254">查看请求日志</span><span class="sxs-lookup"><span data-stu-id="7b576-254">View a log of requests</span></span>  

<span data-ttu-id="7b576-255">使用 "请求" 表查看在 DevTools 打开时发出的所有请求的日志。</span><span class="sxs-lookup"><span data-stu-id="7b576-255">Use the Requests table to view a log of all requests made while DevTools has been open.</span></span>  <span data-ttu-id="7b576-256">选择或悬停的请求将显示有关每个项目的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7b576-256">Selecting or hovering over requests reveals more information about each item.</span></span>  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="请求表" lightbox="../media/network-network-requests-table.msft.png":::
   <span data-ttu-id="7b576-258">图15：请求表</span><span class="sxs-lookup"><span data-stu-id="7b576-258">Figure 15:  The Requests table</span></span>  
:::image-end:::  

<span data-ttu-id="7b576-259">"请求" 表默认情况下显示以下列。</span><span class="sxs-lookup"><span data-stu-id="7b576-259">The Requests table displays the following columns by default.</span></span>  

*   <span data-ttu-id="7b576-260">**名称**。</span><span class="sxs-lookup"><span data-stu-id="7b576-260">**Name**.</span></span>  <span data-ttu-id="7b576-261">资源的文件名或标识符。</span><span class="sxs-lookup"><span data-stu-id="7b576-261">The filename of, or an identifier for, the resource.</span></span>  
*   <span data-ttu-id="7b576-262">**状态**。</span><span class="sxs-lookup"><span data-stu-id="7b576-262">**Status**.</span></span>  <span data-ttu-id="7b576-263">HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="7b576-263">The HTTP status code.</span></span>  
*   <span data-ttu-id="7b576-264">**类型**。</span><span class="sxs-lookup"><span data-stu-id="7b576-264">**Type**.</span></span>  <span data-ttu-id="7b576-265">所请求的资源的 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="7b576-265">The MIME type of the requested resource.</span></span>  
*   <span data-ttu-id="7b576-266">**启动器**。</span><span class="sxs-lookup"><span data-stu-id="7b576-266">**Initiator**.</span></span>  <span data-ttu-id="7b576-267">以下对象或进程启动请求：</span><span class="sxs-lookup"><span data-stu-id="7b576-267">The following objects or processes initiate requests:</span></span>  
    *   <span data-ttu-id="7b576-268">**分析器**。</span><span class="sxs-lookup"><span data-stu-id="7b576-268">**Parser**.</span></span>  <span data-ttu-id="7b576-269">Microsoft Edge 的 HTML 分析程序。</span><span class="sxs-lookup"><span data-stu-id="7b576-269">The HTML parser for Microsoft Edge.</span></span>  
    *   <span data-ttu-id="7b576-270">**重定向**。</span><span class="sxs-lookup"><span data-stu-id="7b576-270">**Redirect**.</span></span>  <span data-ttu-id="7b576-271">HTTP 重定向。</span><span class="sxs-lookup"><span data-stu-id="7b576-271">An HTTP redirect.</span></span>  
    *   <span data-ttu-id="7b576-272">**脚本**。</span><span class="sxs-lookup"><span data-stu-id="7b576-272">**Script**.</span></span>  <span data-ttu-id="7b576-273">JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="7b576-273">A JavaScript function.</span></span>  
    *   <span data-ttu-id="7b576-274">**其他**。</span><span class="sxs-lookup"><span data-stu-id="7b576-274">**Other**.</span></span>  <span data-ttu-id="7b576-275">某些其他进程或操作，例如通过链接导航到页面或在地址栏中输入 URL。</span><span class="sxs-lookup"><span data-stu-id="7b576-275">Some other process or action, such as navigating to a page via a link or entering a URL in the address bar.</span></span>  
*   <span data-ttu-id="7b576-276">**大小**。</span><span class="sxs-lookup"><span data-stu-id="7b576-276">**Size**.</span></span>  <span data-ttu-id="7b576-277">由服务器发送的响应标题和响应正文的合并大小。</span><span class="sxs-lookup"><span data-stu-id="7b576-277">The combined size of the response headers plus the response body, as delivered by the server.</span></span>  
*   <span data-ttu-id="7b576-278">**时间**。</span><span class="sxs-lookup"><span data-stu-id="7b576-278">**Time**.</span></span>  <span data-ttu-id="7b576-279">从请求开始到响应中最后一个字节的接收的总持续时间。</span><span class="sxs-lookup"><span data-stu-id="7b576-279">The total duration, from the start of the request to the receipt of the final byte in the response.</span></span>  
*   <span data-ttu-id="7b576-280">[**瀑布**](#view-the-timing-of-requests-in-relation-to-one-another)图。</span><span class="sxs-lookup"><span data-stu-id="7b576-280">[**Waterfall**](#view-the-timing-of-requests-in-relation-to-one-another).</span></span>  <span data-ttu-id="7b576-281">每个请求的活动的可视化细目。</span><span class="sxs-lookup"><span data-stu-id="7b576-281">A visual breakdown of the activity for each request.</span></span>  

#### <span data-ttu-id="7b576-282">添加或删除列</span><span class="sxs-lookup"><span data-stu-id="7b576-282">Add or remove columns</span></span>  

<span data-ttu-id="7b576-283">将鼠标悬停在 "请求" 表的标题上，打开上下文菜单 \ （右键单击 \），然后选择一个选项以隐藏或显示它。</span><span class="sxs-lookup"><span data-stu-id="7b576-283">Hover on the header of the Requests table, open the contextual menu \(right-click\), and select an option to hide or show it.</span></span>  <span data-ttu-id="7b576-284">当前显示的选项在每个项目旁边都有复选标记。</span><span class="sxs-lookup"><span data-stu-id="7b576-284">Currently displayed options have checkmarks next to each item.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="将列添加到 "请求" 表" lightbox="../media/network-network-requests-add-column.msft.png":::
   <span data-ttu-id="7b576-286">图16：向请求表添加列</span><span class="sxs-lookup"><span data-stu-id="7b576-286">Figure 16:  Adding a column to the Requests table</span></span>  
:::image-end:::  

#### <span data-ttu-id="7b576-287">添加自定义列</span><span class="sxs-lookup"><span data-stu-id="7b576-287">Add custom columns</span></span>  

<span data-ttu-id="7b576-288">若要向 "请求" 表添加自定义列，请将鼠标悬停在 "请求" 表的标题上，打开上下文菜单 \ （右键单击 \），然后选择 "**响应标题**" "  >  **管理标题列**"。</span><span class="sxs-lookup"><span data-stu-id="7b576-288">To add a custom column to the Requests table, hover on the header of the Requests table, open the contextual menu \(right-click\), and select **Response Headers** > **Manage Header Columns**.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="向请求表添加自定义列" lightbox="../media/network-network-requests-add-custom.msft.png":::
   <span data-ttu-id="7b576-290">图17：向请求表添加自定义列</span><span class="sxs-lookup"><span data-stu-id="7b576-290">Figure 17:  Adding a custom column to the Requests table</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-291">查看请求之间的相对计时</span><span class="sxs-lookup"><span data-stu-id="7b576-291">View the timing of requests in relation to one another</span></span>  

<span data-ttu-id="7b576-292">使用瀑布图查看请求相对于另一个时间的计时。</span><span class="sxs-lookup"><span data-stu-id="7b576-292">Use the Waterfall to view the timing of requests in relation to one another.</span></span>  
<span data-ttu-id="7b576-293">默认情况下，瀑布图按请求的开始时间进行组织。</span><span class="sxs-lookup"><span data-stu-id="7b576-293">By default, the Waterfall is organized by the start time of the requests.</span></span>  
<span data-ttu-id="7b576-294">因此，比右侧更远的时间开始向左的请求更远。</span><span class="sxs-lookup"><span data-stu-id="7b576-294">So, requests that are farther to the left started earlier than those that are farther to the right.</span></span>  

<span data-ttu-id="7b576-295">请参阅 "[按活动排序" 阶段](#sort-by-activity-phase)以查看可对瀑布图进行排序的不同方式。</span><span class="sxs-lookup"><span data-stu-id="7b576-295">See [Sort by activity phase](#sort-by-activity-phase) to see the different ways that you may sort the Waterfall.</span></span>  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text=""请求" 窗格的瀑布栏" lightbox="../media/network-network-requests-waterfall.msft.png":::
   <span data-ttu-id="7b576-297">图18： "**请求**" 窗格的 "瀑布图" 列</span><span class="sxs-lookup"><span data-stu-id="7b576-297">Figure 18:  The Waterfall column of the **Requests** pane</span></span>  
:::image-end:::  

<!-- ### Analyze the frames of a WebSocket Connection  -->

<!--To view the frames of a WebSocket connection:  

1.  Select the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Select the **Frames** tab.  The table shows the last 100 frames.  

To refresh the table, re-select the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
:::image type="complex" source="../media/network-frames.msft.png" alt-text="The Frames tab" lightbox="../media/network-frames.msft.png":::
   Old Figure 20:  The **Frames** tab  
:::image-end:::  
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

### <span data-ttu-id="7b576-298">查看答复正文的预览</span><span class="sxs-lookup"><span data-stu-id="7b576-298">View a preview of a response body</span></span>  

<span data-ttu-id="7b576-299">若要查看响应正文的预览，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b576-299">To view a preview of a response body:</span></span>  

1.  <span data-ttu-id="7b576-300">在 "请求" 表的 "**名称**" 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="7b576-300">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="7b576-301">选择 "**预览**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7b576-301">Select the **Preview** tab.</span></span>  

<span data-ttu-id="7b576-302">此选项卡最适用于查看图像。</span><span class="sxs-lookup"><span data-stu-id="7b576-302">This tab is mostly useful for viewing images.</span></span>  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text=""预览" 选项卡" lightbox="../media/network-network-resources-preview.msft.png":::
   <span data-ttu-id="7b576-304">图19： "**预览**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="7b576-304">Figure 19:  The **Preview** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-305">查看答复正文</span><span class="sxs-lookup"><span data-stu-id="7b576-305">View a response body</span></span>  

<span data-ttu-id="7b576-306">要查看请求的响应正文，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b576-306">To view the response body to a request:</span></span>  

1.  <span data-ttu-id="7b576-307">在 "请求" 表的 "**名称**" 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="7b576-307">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="7b576-308">选择 "**响应**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7b576-308">Select the **Response** tab.</span></span>  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text=""响应" 选项卡" lightbox="../media/network-network-resources-response.msft.png":::
   <span data-ttu-id="7b576-310">图20： "**响应**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="7b576-310">Figure 20:  The **Response** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-311">查看 HTTP 标头</span><span class="sxs-lookup"><span data-stu-id="7b576-311">View HTTP headers</span></span>  

<span data-ttu-id="7b576-312">查看有关请求的 HTTP 头数据：</span><span class="sxs-lookup"><span data-stu-id="7b576-312">To view HTTP header data about a request:</span></span>  

1.  <span data-ttu-id="7b576-313">在 "请求" 表的 "**名称**" 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="7b576-313">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="7b576-314">选择 "**页眉**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7b576-314">Select the **Headers** tab.</span></span>  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text=""页眉" 选项卡" lightbox="../media/network-resources-headers.msft.png":::
   <span data-ttu-id="7b576-316">图21： "**页眉**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="7b576-316">Figure 21:  The **Headers** tab</span></span>  
:::image-end:::  

#### <span data-ttu-id="7b576-317">查看 HTTP 域名源</span><span class="sxs-lookup"><span data-stu-id="7b576-317">View HTTP header source</span></span>  

<span data-ttu-id="7b576-318">默认情况下，"页眉" 选项卡按字母顺序显示标题名称。</span><span class="sxs-lookup"><span data-stu-id="7b576-318">By default, the Headers tab shows header names alphabetically.</span></span>  <span data-ttu-id="7b576-319">若要按接收的顺序查看 HTTP 标头名称，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b576-319">To view the HTTP header names in the order they were received:</span></span>  

1.  <span data-ttu-id="7b576-320">打开您感兴趣的请求的 "**标题**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7b576-320">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="7b576-321">请参阅[查看 HTTP 标头](#view-http-headers)。</span><span class="sxs-lookup"><span data-stu-id="7b576-321">See [View HTTP headers](#view-http-headers).</span></span>  
1.  <span data-ttu-id="7b576-322">选择 "**请求标头**" 或 "**响应标题**" 部分旁边的 "**查看源**"。</span><span class="sxs-lookup"><span data-stu-id="7b576-322">Select **view source**, next to the **Request Header** or **Response Header** section.</span></span>  

### <span data-ttu-id="7b576-323">查看查询字符串参数</span><span class="sxs-lookup"><span data-stu-id="7b576-323">View query string parameters</span></span>  

<span data-ttu-id="7b576-324">若要以可读的格式查看 URL 的查询字符串参数，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b576-324">To view the query string parameters of a URL in a human-readable format:</span></span>  

1.  <span data-ttu-id="7b576-325">打开您感兴趣的请求的 "**标题**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7b576-325">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="7b576-326">请参阅[查看 HTTP 标头](#view-http-headers)。</span><span class="sxs-lookup"><span data-stu-id="7b576-326">See [View HTTP headers](#view-http-headers).</span></span>  
1.  <span data-ttu-id="7b576-327">转到 "**查询字符串参数**" 部分。</span><span class="sxs-lookup"><span data-stu-id="7b576-327">Go to the **Query String Parameters** section.</span></span>  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text=""查询字符串参数" 部分" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   <span data-ttu-id="7b576-329">图22： "**查询字符串参数**" 部分</span><span class="sxs-lookup"><span data-stu-id="7b576-329">Figure 22:  The **Query String Parameters** section</span></span>  
:::image-end:::  

#### <span data-ttu-id="7b576-330">查看查询字符串参数源</span><span class="sxs-lookup"><span data-stu-id="7b576-330">View query string parameters source</span></span>  

<span data-ttu-id="7b576-331">要查看请求的查询字符串参数源，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b576-331">To view the query string parameter source of a request:</span></span>  

1.  <span data-ttu-id="7b576-332">转到 "查询字符串参数" 部分。</span><span class="sxs-lookup"><span data-stu-id="7b576-332">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="7b576-333">请参阅[查看查询字符串参数](#view-query-string-parameters)。</span><span class="sxs-lookup"><span data-stu-id="7b576-333">See [View query string parameters](#view-query-string-parameters).</span></span>  
1.  <span data-ttu-id="7b576-334">选择 "**查看源**"。</span><span class="sxs-lookup"><span data-stu-id="7b576-334">Select **view source**.</span></span>  

#### <span data-ttu-id="7b576-335">查看 URL 编码查询字符串参数</span><span class="sxs-lookup"><span data-stu-id="7b576-335">View URL-encoded query string parameters</span></span>  

<span data-ttu-id="7b576-336">以人类可读格式查看查询字符串参数，但保留编码：</span><span class="sxs-lookup"><span data-stu-id="7b576-336">To view query string parameters in a human-readable format, but with encodings preserved:</span></span>  

1.  <span data-ttu-id="7b576-337">转到 "查询字符串参数" 部分。</span><span class="sxs-lookup"><span data-stu-id="7b576-337">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="7b576-338">请参阅[查看查询字符串参数](#view-query-string-parameters)。</span><span class="sxs-lookup"><span data-stu-id="7b576-338">See [View query string parameters](#view-query-string-parameters).</span></span>  
1.  <span data-ttu-id="7b576-339">选择 "**查看 URL 编码**"。</span><span class="sxs-lookup"><span data-stu-id="7b576-339">Select **view URL encoded**.</span></span>  

### <span data-ttu-id="7b576-340">查看 cookie</span><span class="sxs-lookup"><span data-stu-id="7b576-340">View cookies</span></span>  

<span data-ttu-id="7b576-341">若要查看在请求的 HTTP 头中发送的 cookie，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b576-341">To view the cookies sent in the HTTP header of a request:</span></span>  

1.  <span data-ttu-id="7b576-342">在 "请求" 表的 "**名称**" 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="7b576-342">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="7b576-343">选择 " **cookie** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7b576-343">Select the **Cookies** tab.</span></span>  

<!--See [Fields][ManageDataCookiesFields] for a description of each of the columns.  -->

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->
<!--TODO: add link when section is available -->

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text=""Cookie" 选项卡" lightbox="../media/network-network-resources-cookies.msft.png":::
   <span data-ttu-id="7b576-345">图23： "Cookies" 选项卡</span><span class="sxs-lookup"><span data-stu-id="7b576-345">Figure 23:  The Cookies tab</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-346">查看请求的计时细目</span><span class="sxs-lookup"><span data-stu-id="7b576-346">View the timing breakdown of a request</span></span>  

<span data-ttu-id="7b576-347">要查看请求的计时细目，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7b576-347">To view the timing breakdown of a request:</span></span>  

1.  <span data-ttu-id="7b576-348">在 "请求" 表的 "**名称**" 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="7b576-348">Select the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="7b576-349">选择 "**计时**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7b576-349">Select the **Timing** tab.</span></span>  

<span data-ttu-id="7b576-350">请参阅[预览计时细目](#preview-a-timing-breakdown)以获得更快的访问此数据的方式。</span><span class="sxs-lookup"><span data-stu-id="7b576-350">See [Preview a timing breakdown](#preview-a-timing-breakdown) for a faster way to access this data.</span></span>  

<span data-ttu-id="7b576-351">有关你在 "计时" 选项卡中看到的每个阶段的详细信息，请参阅[介绍的计时分解阶段](#timing-breakdown-phases-explained)。</span><span class="sxs-lookup"><span data-stu-id="7b576-351">See [Timing breakdown phases explained](#timing-breakdown-phases-explained) for more information about each of the phases that you may see in the Timing tab.</span></span>  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text=""计时" 选项卡" lightbox="../media/network-network-resources-timing.msft.png":::
   <span data-ttu-id="7b576-353">图24： "**计时**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="7b576-353">Figure 24:  The **Timing** tab</span></span>  
:::image-end:::  

<span data-ttu-id="7b576-354">有关每个阶段的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7b576-354">More information about each of the phases.</span></span>  

<span data-ttu-id="7b576-355">请参阅[查看计时细目](#view-the-timing-breakdown-of-a-request)以了解另一种访问此视图的方式。</span><span class="sxs-lookup"><span data-stu-id="7b576-355">See [View timing breakdown](#view-the-timing-breakdown-of-a-request) for another way to access this view.</span></span>  

#### <span data-ttu-id="7b576-356">预览计时细目</span><span class="sxs-lookup"><span data-stu-id="7b576-356">Preview a timing breakdown</span></span>  

<span data-ttu-id="7b576-357">若要查看请求的计时分解的预览，请将鼠标悬停在 "请求" 表的 "**瀑布**图" 列中请求的条目上。</span><span class="sxs-lookup"><span data-stu-id="7b576-357">To view a preview of the timing breakdown of a request, hover over the entry for the request in the **Waterfall** column of the Requests table.</span></span>  

<span data-ttu-id="7b576-358">请参阅[查看请求的计时细目](#view-the-timing-breakdown-of-a-request)以了解访问不需要悬停的数据的方式。</span><span class="sxs-lookup"><span data-stu-id="7b576-358">See [View the timing breakdown of a request](#view-the-timing-breakdown-of-a-request) for a way to access this data that does not require hovering.</span></span>  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text="> 预览请求的计时细目" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   <span data-ttu-id="7b576-360">图25：预览请求的计时细目</span><span class="sxs-lookup"><span data-stu-id="7b576-360">Figure 25:  Previewing the timing breakdown of a request</span></span>  
:::image-end:::  

#### <span data-ttu-id="7b576-361">已解释的计时分解阶段</span><span class="sxs-lookup"><span data-stu-id="7b576-361">Timing breakdown phases explained</span></span>  

<span data-ttu-id="7b576-362">有关你可能会在 "**计时**" 选项卡中看到的每个阶段的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7b576-362">More information about each of the phases you may see in the **Timing** tab.</span></span>  

*   <span data-ttu-id="7b576-363">**排队**。</span><span class="sxs-lookup"><span data-stu-id="7b576-363">**Queueing**.</span></span>  <span data-ttu-id="7b576-364">浏览器在以下情况中对请求进行排队：</span><span class="sxs-lookup"><span data-stu-id="7b576-364">The browser queues requests when:</span></span>  
    *   <span data-ttu-id="7b576-365">优先级较高的请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-365">There are higher priority requests.</span></span>  
    *   <span data-ttu-id="7b576-366">已为此来源打开6个 TCP 连接，这是限制。</span><span class="sxs-lookup"><span data-stu-id="7b576-366">There are already six TCP connections open for this origin, which is the limit.</span></span>  <span data-ttu-id="7b576-367">仅适用于 HTTP/1.0 和 HTTP/1.1。</span><span class="sxs-lookup"><span data-stu-id="7b576-367">Applies to HTTP/1.0 and HTTP/1.1 only.</span></span>  
    *   <span data-ttu-id="7b576-368">浏览器在磁盘缓存中短暂分配空间。</span><span class="sxs-lookup"><span data-stu-id="7b576-368">The browser is briefly allocating space in the disk cache.</span></span>  
*   <span data-ttu-id="7b576-369">**停止**。</span><span class="sxs-lookup"><span data-stu-id="7b576-369">**Stalled**.</span></span>  <span data-ttu-id="7b576-370">由于 "**排队**" 中所述的任何原因，请求可能停止。</span><span class="sxs-lookup"><span data-stu-id="7b576-370">The request could be stalled for any of the reasons described in **Queueing**.</span></span>  
*   <span data-ttu-id="7b576-371">**DNS 查找**。</span><span class="sxs-lookup"><span data-stu-id="7b576-371">**DNS Lookup**.</span></span>  <span data-ttu-id="7b576-372">浏览器正在解析请求的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="7b576-372">The browser is resolving the IP address for the request.</span></span>  
*   <span data-ttu-id="7b576-373">**初始连接**。</span><span class="sxs-lookup"><span data-stu-id="7b576-373">**Initial connection**.</span></span>  <span data-ttu-id="7b576-374">浏览器正在建立连接，包括 TCP 握手、TCP 重试和协商 SSL。</span><span class="sxs-lookup"><span data-stu-id="7b576-374">The browser is establishing a connection including TCP handshakes, TCP retries, and negotiating an SSL.</span></span>
*   <span data-ttu-id="7b576-375">**代理协商**。</span><span class="sxs-lookup"><span data-stu-id="7b576-375">**Proxy negotiation**.</span></span>  <span data-ttu-id="7b576-376">浏览器正使用[代理服务器][WikiProxyServer]协商请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-376">The browser is negotiating the request with a [proxy server][WikiProxyServer].</span></span>  
*   <span data-ttu-id="7b576-377">**请求已发送**。</span><span class="sxs-lookup"><span data-stu-id="7b576-377">**Request sent**.</span></span>  <span data-ttu-id="7b576-378">正在发送请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-378">The request is being sent.</span></span>  
*   <span data-ttu-id="7b576-379">**ServiceWorker 准备**。</span><span class="sxs-lookup"><span data-stu-id="7b576-379">**ServiceWorker Preparation**.</span></span>  <span data-ttu-id="7b576-380">浏览器正在启动服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="7b576-380">The browser is starting up the service worker.</span></span>  
*   <span data-ttu-id="7b576-381">**对 ServiceWorker 的请求**。</span><span class="sxs-lookup"><span data-stu-id="7b576-381">**Request to ServiceWorker**.</span></span>  <span data-ttu-id="7b576-382">请求将发送给服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="7b576-382">The request is being sent to the service worker.</span></span>  
*   <span data-ttu-id="7b576-383">**等待 \ （TTFB \）**。</span><span class="sxs-lookup"><span data-stu-id="7b576-383">**Waiting \(TTFB\)**.</span></span>  <span data-ttu-id="7b576-384">浏览器正在等待响应的第一个字节。</span><span class="sxs-lookup"><span data-stu-id="7b576-384">The browser is waiting for the first byte of a response.</span></span>  
  <span data-ttu-id="7b576-385">TTFB 代表第一个字节的时间。</span><span class="sxs-lookup"><span data-stu-id="7b576-385">TTFB stands for Time To First Byte.</span></span>  <span data-ttu-id="7b576-386">此计时包括延迟的1次往返行程以及服务器准备响应的时间。</span><span class="sxs-lookup"><span data-stu-id="7b576-386">This timing includes 1 round trip of latency and the time the server took to prepare the response.</span></span>  
*   <span data-ttu-id="7b576-387">**内容下载**。</span><span class="sxs-lookup"><span data-stu-id="7b576-387">**Content Download**.</span></span>  <span data-ttu-id="7b576-388">浏览器正在接收响应。</span><span class="sxs-lookup"><span data-stu-id="7b576-388">The browser is receiving the response.</span></span>  
*   <span data-ttu-id="7b576-389">**接收推送**。</span><span class="sxs-lookup"><span data-stu-id="7b576-389">**Receiving Push**.</span></span>  <span data-ttu-id="7b576-390">浏览器正在通过 HTTP/2 服务器推送接收此响应的数据。</span><span class="sxs-lookup"><span data-stu-id="7b576-390">The browser is receiving data for this response via HTTP/2 Server Push.</span></span>  
*   <span data-ttu-id="7b576-391">**正在读取推送**。</span><span class="sxs-lookup"><span data-stu-id="7b576-391">**Reading Push**.</span></span>  <span data-ttu-id="7b576-392">浏览器正在读取以前收到的本地数据。</span><span class="sxs-lookup"><span data-stu-id="7b576-392">The browser is reading the local data previously received.</span></span>  

### <span data-ttu-id="7b576-393">查看启动器和相关性</span><span class="sxs-lookup"><span data-stu-id="7b576-393">View initiators and dependencies</span></span>  

<span data-ttu-id="7b576-394">若要查看请求的发起程序和依赖关系，请 `Shift` 在请求表中保留并悬停请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-394">To view the initiators and dependencies of a request, hold `Shift`and hover over the request in the Requests table.</span></span>  <span data-ttu-id="7b576-395">DevTools 颜色：启动器显示为绿色，相关性显示为红色。</span><span class="sxs-lookup"><span data-stu-id="7b576-395">DevTools colors: initiators are shown in green and dependencies are shown in red.</span></span>  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="查看请求的发起人和相关性" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   <span data-ttu-id="7b576-397">图26：查看请求的启动器和相关性</span><span class="sxs-lookup"><span data-stu-id="7b576-397">Figure 26:  Viewing the initiators and dependencies of a request</span></span>  
:::image-end:::  

<span data-ttu-id="7b576-398">当请求表按时间顺序排序时，悬停的第一个绿色请求上方是依赖项的发起程序。</span><span class="sxs-lookup"><span data-stu-id="7b576-398">When the Requests table is ordered chronologically, the first green request above the one you are hovering is the initiator of the dependency.</span></span>  <span data-ttu-id="7b576-399">如果在上面显示了另一个绿色请求，则该请求是发起方的发起方。</span><span class="sxs-lookup"><span data-stu-id="7b576-399">If another green request appears above that, that higher request is the initiator of the initiator.</span></span>  <span data-ttu-id="7b576-400">以此类推。</span><span class="sxs-lookup"><span data-stu-id="7b576-400">And so on.</span></span>  

### <span data-ttu-id="7b576-401">查看加载事件</span><span class="sxs-lookup"><span data-stu-id="7b576-401">View load events</span></span>  

<span data-ttu-id="7b576-402">DevTools 显示 `DOMContentLoaded` `load` 网络面板上多个位置的和事件的计时。</span><span class="sxs-lookup"><span data-stu-id="7b576-402">DevTools displays the timing of the `DOMContentLoaded` and `load` events in multiple places on the Network panel.</span></span>  <span data-ttu-id="7b576-403">`DOMContentLoaded`事件颜色为蓝色， `load` 事件为红色。</span><span class="sxs-lookup"><span data-stu-id="7b576-403">The `DOMContentLoaded` event is colored blue, and the `load` event is red.</span></span>  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="DOMContentLoaded 和加载事件在网络面板上的位置" lightbox="../media/network-network-requests-load-events.msft.png":::
   <span data-ttu-id="7b576-405">图27： " `DOMContentLoaded` `load` 网络" 面板上的和事件的位置</span><span class="sxs-lookup"><span data-stu-id="7b576-405">Figure 27:  The locations of the `DOMContentLoaded` and `load` events on the Network panel</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-406">查看请求总数</span><span class="sxs-lookup"><span data-stu-id="7b576-406">View the total number of requests</span></span>  

<span data-ttu-id="7b576-407">请求总数将列在 "摘要" 窗格中的 "网络" 面板底部。</span><span class="sxs-lookup"><span data-stu-id="7b576-407">The total number of requests is listed in the Summary pane, at the bottom of the Network panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="7b576-408">此号码仅跟踪自 DevTools 打开以来已记录的请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-408">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="7b576-409">如果在 DevTools 打开之前发生了其他请求，则不会对这些请求进行计数。</span><span class="sxs-lookup"><span data-stu-id="7b576-409">If other requests occurred before DevTools was opened, those requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="自 DevTools 打开以来的请求总数" lightbox="../media/network-network-total-requests.msft.png":::
   <span data-ttu-id="7b576-411">图28：自 DevTools 打开以来的请求总数</span><span class="sxs-lookup"><span data-stu-id="7b576-411">Figure 28:  The total number of requests since DevTools was opened</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-412">查看总下载大小</span><span class="sxs-lookup"><span data-stu-id="7b576-412">View the total download size</span></span>  

<span data-ttu-id="7b576-413">请求的总下载大小列在 "摘要" 窗格中的 "网络" 面板底部。</span><span class="sxs-lookup"><span data-stu-id="7b576-413">The total download size of requests is listed in the Summary pane, at the bottom of the Network panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="7b576-414">此号码仅跟踪自 DevTools 打开以来已记录的请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-414">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="7b576-415">如果在 DevTools 打开之前发生了其他请求，则不会对以前的请求进行计数。</span><span class="sxs-lookup"><span data-stu-id="7b576-415">If other requests occurred before DevTools was opened, the previous requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="请求的总下载大小" lightbox="../media/network-network-total-download-size.msft.png":::
   <span data-ttu-id="7b576-417">图29：请求的总下载大小</span><span class="sxs-lookup"><span data-stu-id="7b576-417">Figure 29:  The total download size of requests</span></span>  
:::image-end:::  

<span data-ttu-id="7b576-418">请参阅[查看资源的未压缩大小](#view-the-uncompressed-size-of-a-resource)，以查看浏览器 uncompresses 每个项目后的大资源。</span><span class="sxs-lookup"><span data-stu-id="7b576-418">See [View the uncompressed size of a resource](#view-the-uncompressed-size-of-a-resource) to see how large resources are after the browser uncompresses each item.</span></span>  

### <span data-ttu-id="7b576-419">查看导致请求的堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="7b576-419">View the stack trace that caused a request</span></span>  

<span data-ttu-id="7b576-420">在 JavaScript 语句请求资源后，将鼠标悬停在**发起程序**列上以查看该请求的最后一个堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="7b576-420">After a JavaScript statement requests a resource, hover over the **Initiator** column to view the stack trace leading up to the request.</span></span>  

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

:::image type="complex" source="../media/network-network-requests-initiator-stack.msft.png" alt-text="堆栈跟踪导致资源请求" lightbox="../media/network-network-requests-initiator-stack.msft.png":::
   <span data-ttu-id="7b576-422">图30：导致资源请求的堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="7b576-422">Figure 30:  The stack trace leading up to a resource request</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-423">查看资源的未压缩大小</span><span class="sxs-lookup"><span data-stu-id="7b576-423">View the uncompressed size of a resource</span></span>  

<span data-ttu-id="7b576-424">选中 "**使用大型请求行**" 复选框，然后查看 "**大小**" 列的底部值。</span><span class="sxs-lookup"><span data-stu-id="7b576-424">Select the **Use large request rows** checkbox and then look at the bottom value of the **Size** column.</span></span>  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="未压缩资源的示例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   <span data-ttu-id="7b576-426">图31：解压缩的资源的示例 \ （ `jquery-3.3.1.min.js` 通过网络发送的文件的压缩大小是 `29.9 KB` ，未压缩的大小为 `84.9 KB` \）</span><span class="sxs-lookup"><span data-stu-id="7b576-426">Figure 31:  An example of uncompressed resources  \(The compressed size of the `jquery-3.3.1.min.js` file that was sent over the network was `29.9 KB`, whereas the uncompressed size was `84.9 KB`\)</span></span>  
:::image-end:::  

## <span data-ttu-id="7b576-427">导出请求数据</span><span class="sxs-lookup"><span data-stu-id="7b576-427">Export requests data</span></span>  

### <span data-ttu-id="7b576-428">将所有网络请求保存到 HAR 文件</span><span class="sxs-lookup"><span data-stu-id="7b576-428">Save all network requests to a HAR file</span></span>  

<span data-ttu-id="7b576-429">若要将所有网络请求保存到 HAR 文件，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7b576-429">To save all network requests to a HAR file, complete the following steps.</span></span>  

1.  <span data-ttu-id="7b576-430">将鼠标悬停在 "请求" 表中的任何请求上，然后打开上下文菜单 \ （右键单击 \）。</span><span class="sxs-lookup"><span data-stu-id="7b576-430">Hover on any request in the Requests table and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="7b576-431">选择 "**另存为 HAR 和内容**"。</span><span class="sxs-lookup"><span data-stu-id="7b576-431">Select **Save as HAR with Content**.</span></span>  <span data-ttu-id="7b576-432">DevTools 将打开 DevTools 后出现的所有请求保存到 HAR 文件。</span><span class="sxs-lookup"><span data-stu-id="7b576-432">DevTools saves all requests that have occurred since you opened DevTools to the HAR file.</span></span>  <span data-ttu-id="7b576-433">无法筛选请求，或仅保存单个请求。</span><span class="sxs-lookup"><span data-stu-id="7b576-433">There is no way to filter requests, or to save just a single request.</span></span>  

<span data-ttu-id="7b576-434">保存 HAR 文件后，可将其导入 DevTools 进行分析。</span><span class="sxs-lookup"><span data-stu-id="7b576-434">Once you save a HAR file, you may import it back into DevTools for analysis.</span></span>  <span data-ttu-id="7b576-435">只需将 HAR 文件拖放到 "请求" 表中。</span><span class="sxs-lookup"><span data-stu-id="7b576-435">Just drag-and-drop the HAR file into the Requests table.</span></span>  
<!--See also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="选择 "另存为 HAR 和内容"" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   <span data-ttu-id="7b576-437">图32：选择 "**另存为 HAR 和内容**"</span><span class="sxs-lookup"><span data-stu-id="7b576-437">Figure 32:  Selecting **Save as HAR with Content**</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-438">将一个或多个请求复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="7b576-438">Copy one or more requests to the clipboard</span></span>  

<span data-ttu-id="7b576-439">在 "请求" 表的 "**名称**" 列下，将鼠标悬停在请求上，打开上下文菜单 \ （右键单击 \），将鼠标悬停在 "**复制**" 上，然后选择下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="7b576-439">Under the **Name** column of the Requests table, hover on a request, open the contextual menu \(right-click\), hover over **Copy**, and select one of the following options.</span></span>  

*   <span data-ttu-id="7b576-440">**复制链接地址**。</span><span class="sxs-lookup"><span data-stu-id="7b576-440">**Copy Link Address**.</span></span>  <span data-ttu-id="7b576-441">将请求的 URL 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="7b576-441">Copy the URL of the request to the clipboard.</span></span>  
*   <span data-ttu-id="7b576-442">**复制响应**。</span><span class="sxs-lookup"><span data-stu-id="7b576-442">**Copy Response**.</span></span>  <span data-ttu-id="7b576-443">将响应正文复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="7b576-443">Copy the response body to the clipboard.</span></span>  
*   <span data-ttu-id="7b576-444">**复制为提取**。</span><span class="sxs-lookup"><span data-stu-id="7b576-444">**Copy as Fetch**.</span></span>  
*   <span data-ttu-id="7b576-445">**复制为卷曲**。</span><span class="sxs-lookup"><span data-stu-id="7b576-445">**Copy as cURL**.</span></span>  <span data-ttu-id="7b576-446">将请求复制为卷曲命令。</span><span class="sxs-lookup"><span data-stu-id="7b576-446">Copy the request as a cURL command.</span></span>  
*   <span data-ttu-id="7b576-447">**全部复制为 "提取**"。</span><span class="sxs-lookup"><span data-stu-id="7b576-447">**Copy All as Fetch**.</span></span>  
*   <span data-ttu-id="7b576-448">**全部复制为卷曲**。</span><span class="sxs-lookup"><span data-stu-id="7b576-448">**Copy All as cURL**.</span></span>  <span data-ttu-id="7b576-449">将所有请求复制为一个卷曲命令链。</span><span class="sxs-lookup"><span data-stu-id="7b576-449">Copy all requests as a chain of cURL commands.</span></span>  
*   <span data-ttu-id="7b576-450">**全部复制为 HAR**。</span><span class="sxs-lookup"><span data-stu-id="7b576-450">**Copy All as HAR**.</span></span>  <span data-ttu-id="7b576-451">将所有请求复制到 HAR 数据。</span><span class="sxs-lookup"><span data-stu-id="7b576-451">Copy all requests as HAR data.</span></span>  

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="选择 "复制响应"" lightbox="../media/network-network-requests-copy-response.msft.png":::
   <span data-ttu-id="7b576-453">图33：选择 "**复制响应**"</span><span class="sxs-lookup"><span data-stu-id="7b576-453">Figure 33:  Selecting **Copy Response**</span></span>  
:::image-end:::  

## <span data-ttu-id="7b576-454">更改网络面板的布局</span><span class="sxs-lookup"><span data-stu-id="7b576-454">Change the layout of the Network panel</span></span>  

<span data-ttu-id="7b576-455">你可以展开或折叠 "网络面板" UI 的各个部分以重点介绍重要信息。</span><span class="sxs-lookup"><span data-stu-id="7b576-455">You may expand or collapse sections of the Network panel UI to focus important information.</span></span>  

### <span data-ttu-id="7b576-456">隐藏 "筛选器" 窗格</span><span class="sxs-lookup"><span data-stu-id="7b576-456">Hide the Filters pane</span></span>  

<span data-ttu-id="7b576-457">默认情况下，DevTools 显示 "**筛选器" 窗格**。</span><span class="sxs-lookup"><span data-stu-id="7b576-457">By default, DevTools shows the **Filters pane**.</span></span>  
<span data-ttu-id="7b576-458">选择 "**筛选** ![ 筛选" ][ImageFilterIcon] 以将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="7b576-458">Select **Filter** ![Filter][ImageFilterIcon] to hide it.</span></span>  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text=""隐藏筛选器" 按钮" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   <span data-ttu-id="7b576-460">图34： "隐藏筛选器" 按钮</span><span class="sxs-lookup"><span data-stu-id="7b576-460">Figure 34:  The Hide Filters button</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-461">使用大型请求行</span><span class="sxs-lookup"><span data-stu-id="7b576-461">Use large request rows</span></span>  

<span data-ttu-id="7b576-462">如果需要在网络请求表中有更多的空格，请使用较大的行。</span><span class="sxs-lookup"><span data-stu-id="7b576-462">Use large rows when you want more whitespace in your network requests table.</span></span>  <span data-ttu-id="7b576-463">在使用较大的行时，某些列还提供了一些更多的信息。</span><span class="sxs-lookup"><span data-stu-id="7b576-463">Some columns also provide a little more information when using large rows.</span></span>  <span data-ttu-id="7b576-464">例如， **Size**列的底部值是请求的未压缩大小。</span><span class="sxs-lookup"><span data-stu-id="7b576-464">For example, the bottom value of the **Size** column is the uncompressed size of a request.</span></span>  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text="请求窗格中的大型请求行的示例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   <span data-ttu-id="7b576-466">图35： "**请求**" 窗格中的大型请求行的示例</span><span class="sxs-lookup"><span data-stu-id="7b576-466">Figure 35:  An example of large request rows in the **Requests** pane</span></span>  
:::image-end:::  

<span data-ttu-id="7b576-467">选中 "**使用大请求行**" 复选框以启用大行。</span><span class="sxs-lookup"><span data-stu-id="7b576-467">Select the **Use large request rows** checkbox to enable large rows.</span></span>  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text=""使用大请求行" 复选框" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   <span data-ttu-id="7b576-469">图36： "**使用大型请求行**" 复选框</span><span class="sxs-lookup"><span data-stu-id="7b576-469">Figure 36:  The **Use large request rows** checkbox</span></span>  
:::image-end:::  

### <span data-ttu-id="7b576-470">隐藏 "概述" 窗格</span><span class="sxs-lookup"><span data-stu-id="7b576-470">Hide the Overview pane</span></span>  

<span data-ttu-id="7b576-471">默认情况下，DevTools 显示 "**概述" 窗格**。</span><span class="sxs-lookup"><span data-stu-id="7b576-471">By default, DevTools shows the **Overview pane**.</span></span>  <span data-ttu-id="7b576-472">取消选中 "**显示概述**" 复选框以将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="7b576-472">Deselect the **Show Overview** checkbox to hide it.</span></span>  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text=""显示概述" 复选框" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   <span data-ttu-id="7b576-474">图37： "**显示概述**" 复选框</span><span class="sxs-lookup"><span data-stu-id="7b576-474">Figure 37:  The **Show Overview** checkbox</span></span>  
:::image-end:::  

<!-- image links -->  

[ImageCaptureScreenshotsIcon]: ../media/capture-screenshots-icon.msft.png  
[ImageClearIcon]: ../media/clear-requests-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageHideIcon]: ../media/hide-overview-icon.msft.png  
[ImageLargeResourceRowsIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageRecordOnIcon]: ../media/record-on-icon.msft.png  

<!-- links -->  

[DevtoolsProgressiveWebApps]: /microsoft-edge/devtools-guide-chromium/network/progressive-web-apps "调试渐进式 Web 应用"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "数据 Url |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "代理服务器-维基百科"  

> [!NOTE]
> <span data-ttu-id="7b576-478">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="7b576-478">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7b576-479">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/reference)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="7b576-479">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="7b576-481">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="7b576-481">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
