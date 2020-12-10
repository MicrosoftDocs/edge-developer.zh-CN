---
description: Microsoft Edge DevTools 网络面板功能的全面参考。
title: 网络分析参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 4d4dc8ad5102766f3ad3c8322dbf9342a69e9097
ms.sourcegitcommit: 6571bcc0b7f1c4c9d6ead65081374bab87cd4469
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203904"
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

# <span data-ttu-id="bcdc8-104">网络分析参考</span><span class="sxs-lookup"><span data-stu-id="bcdc8-104">Network Analysis reference</span></span>  

<span data-ttu-id="bcdc8-105">了解在 Microsoft Edge DevTools 网络分析功能的这一全面参考中，分析页面加载方式的新方法。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-105">Discover new ways to analyze how your page loads in this comprehensive reference of Microsoft Edge DevTools network analysis features.</span></span>  

## <span data-ttu-id="bcdc8-106">记录网络请求</span><span class="sxs-lookup"><span data-stu-id="bcdc8-106">Record network requests</span></span>  

<span data-ttu-id="bcdc8-107">默认情况下，DevTools 在 **网络** 面板中记录所有网络请求，只要 DevTools 已打开。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-107">By default, DevTools record all network requests in the **Network** panel, so long as DevTools is open.</span></span>  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="网络面板" lightbox="../media/network-network-panel.msft.png":::
   <span data-ttu-id="bcdc8-109">**网络**面板</span><span class="sxs-lookup"><span data-stu-id="bcdc8-109">The **Network** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-110">停止记录网络请求</span><span class="sxs-lookup"><span data-stu-id="bcdc8-110">Stop recording network requests</span></span>  

<span data-ttu-id="bcdc8-111">若要停止录制请求，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-111">To stop recording requests, complete the following steps.</span></span>  

1.  <span data-ttu-id="bcdc8-112">在 " **网络** " 面板上，选择 " **停止录制网络日志** \ (![ 停止记录网络日志 ][ImageRecordOnIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-112">On the **Network** panel, choose **Stop recording network log** \(![Stop recording network log][ImageRecordOnIcon]\).</span></span>  <span data-ttu-id="bcdc8-113">它将变为灰色，指示 DevTools 不再录制请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-113">It turns grey to indicate that DevTools is no longer recording requests.</span></span>  
1.  <span data-ttu-id="bcdc8-114">选择 `Control` + `E` \ (Windows、Linux \ ) 或 `Command` + `E` \ (macOS \ ) ，同时**网络**面板处于焦点。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-114">Select `Control`+`E` \(Windows, Linux\) or `Command`+`E` \(macOS\) while the **Network** panel is in focus.</span></span>  

### <span data-ttu-id="bcdc8-115">清除请求</span><span class="sxs-lookup"><span data-stu-id="bcdc8-115">Clear requests</span></span>  

<span data-ttu-id="bcdc8-116">\*\*\*\* ![ ][ImageClearIcon] 在 "**网络**" 面板上选择 "清除 \ (清除 \ ) "，清除 "请求" 表中的所有请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-116">Choose **Clear** \(![Clear][ImageClearIcon]\) on the **Network** panel to clear all requests from the Requests table.</span></span>  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text=""清除" 按钮" lightbox="../media/network-network-clear-button.msft.png":::
   <span data-ttu-id="bcdc8-118">" **清除** " 按钮</span><span class="sxs-lookup"><span data-stu-id="bcdc8-118">The **Clear** button</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-119">跨页面加载保存请求</span><span class="sxs-lookup"><span data-stu-id="bcdc8-119">Save requests across page loads</span></span>  

<span data-ttu-id="bcdc8-120">若要跨页面加载保存请求，请在 " **网络** " 面板上，打开 " **保留日志** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-120">To save requests across page loads, on the **Network** panel, turn on the **Preserve log** checkbox.</span></span>  <span data-ttu-id="bcdc8-121">DevTools 将保存所有请求，直到你禁用 **保留日志**。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-121">DevTools saves all requests until you disable **Preserve log**.</span></span>  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text=""保留日志" 复选框" lightbox="../media/network-network-preserve-log.msft.png":::
   <span data-ttu-id="bcdc8-123">" **保留日志** " 复选框</span><span class="sxs-lookup"><span data-stu-id="bcdc8-123">The **Preserve Log** checkbox</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-124">在页面加载期间捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="bcdc8-124">Capture screenshots during page load</span></span>  

<span data-ttu-id="bcdc8-125">捕获屏幕截图，分析用户在等待加载页面时显示的内容。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-125">Capture screenshots to analyze what displays for users while waiting for your page to load.</span></span>  

<span data-ttu-id="bcdc8-126">若要启用屏幕截图，请选择 " **网络设置**"，然后在 " **网络** " 面板上，打开 " **捕获屏幕截图** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-126">To enable screenshots, choose **Network settings**, and on the **Network** panel, turn on the **Capture screenshots** checkbox.</span></span>  

<span data-ttu-id="bcdc8-127">在 " **网络** " 面板处于焦点时刷新页面以捕获屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-127">Refresh the page while the **Network** panel is in focus to capture screenshots.</span></span>  

<span data-ttu-id="bcdc8-128">捕获屏幕截图后，可通过以下方式与之交互。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-128">After capturing a screenshot, you interact with it in the following ways.</span></span>  

*   <span data-ttu-id="bcdc8-129">将鼠标悬停在屏幕截图上以显示捕获屏幕截图的位置。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-129">Hover on a screenshot to display the point at which that screenshot was captured.</span></span>  <span data-ttu-id="bcdc8-130">" **概述** " 窗格上将显示一个黄色线条。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-130">A yellow line is displayed on the **Overview** pane.</span></span>  
*   <span data-ttu-id="bcdc8-131">选择屏幕的缩略图，以筛选出捕获屏幕截图后发生的任何请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-131">Choose the thumbnail of a screen to filter out any requests that occurred after the screenshot was captured.</span></span>  
*   <span data-ttu-id="bcdc8-132">双击缩略图以放大缩略图。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-132">Double-click a thumbnail to zoom into it.</span></span>  

:::image type="complex" source="../media/network-network-screenshot-hover.msft.png" alt-text="悬停在屏幕截图上" lightbox="../media/network-network-screenshot-hover.msft.png":::
   <span data-ttu-id="bcdc8-134">悬停在屏幕截图上</span><span class="sxs-lookup"><span data-stu-id="bcdc8-134">Hover on a screenshot</span></span>  
:::image-end:::  

<!--  ### Replay XHR request  -->

<!--  To replay an XHR request, hover on the request in the Requests table, open the contextual menu \(right-click\), and choose **Replay XHR**.  -->

<!--  
:::image type="complex" source="../media/network-replay-xhr.msft.png" alt-text="Choose Replay XHR" lightbox="../media/network-replay-xhr.msft.png":::
   Choose Replay XHR  
:::image-end:::  
-->  

## <span data-ttu-id="bcdc8-135">更改加载行为</span><span class="sxs-lookup"><span data-stu-id="bcdc8-135">Change loading behavior</span></span>  

### <span data-ttu-id="bcdc8-136">通过禁用浏览器缓存来模拟首次访问者</span><span class="sxs-lookup"><span data-stu-id="bcdc8-136">Emulate a first-time visitor by disabling the browser cache</span></span>  

<span data-ttu-id="bcdc8-137">若要模拟首次用户体验你的网站的方式，请打开 " **禁用缓存** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-137">To emulate how a first-time user experiences your site, turn on the **Disable cache** checkbox.</span></span>  <span data-ttu-id="bcdc8-138">DevTools 禁用浏览器缓存。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-138">DevTools disables the browser cache.</span></span>  <span data-ttu-id="bcdc8-139">此功能更准确地模拟了首次使用用户的体验，因为在重复访问时，将从浏览器缓存提供请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-139">This feature more accurately emulates a first-time user's experience, because requests are served from the browser cache on repeat visits.</span></span>  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text=""禁用缓存" 复选框" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   <span data-ttu-id="bcdc8-141">" **禁用缓存** " 复选框</span><span class="sxs-lookup"><span data-stu-id="bcdc8-141">The **Disable Cache** checkbox</span></span>  
:::image-end:::  

#### <span data-ttu-id="bcdc8-142">从网络条件抽屉中禁用浏览器缓存</span><span class="sxs-lookup"><span data-stu-id="bcdc8-142">Disable the browser cache from the Network Conditions drawer</span></span>  

<span data-ttu-id="bcdc8-143">如果想要在其他 DevTools 面板中工作时禁用缓存，请使用网络条件抽屉。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-143">If you want to disable the cache while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="bcdc8-144">打开 **网络条件** 抽屉。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-144">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="bcdc8-145">打开 " **禁用缓存** " 复选框，打开 \ (或关闭 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-145">Turn on \(or off\) the **Disable cache** checkbox.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="bcdc8-146">手动清除浏览器缓存</span><span class="sxs-lookup"><span data-stu-id="bcdc8-146">Manually clear the browser cache</span></span>  

<span data-ttu-id="bcdc8-147">若要随时手动清除浏览器缓存，请打开上下文菜单 \ (右键单击 "请求" 表中的任意位置的 "\ ) "，然后选择 " **清除浏览器缓存**"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-147">To manually clear the browser cache at any time, open the contextual menu \(right-click\) anywhere in the Requests table and choose **Clear Browser Cache**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="选择 "清除浏览器缓存"" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   <span data-ttu-id="bcdc8-149">选择 "**清除浏览器缓存**"</span><span class="sxs-lookup"><span data-stu-id="bcdc8-149">Choose **Clear Browser Cache**</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-150">模拟脱机</span><span class="sxs-lookup"><span data-stu-id="bcdc8-150">Emulate offline</span></span>  

<span data-ttu-id="bcdc8-151">新的 web 应用类（名为 " [渐进式 Web 应用][DevtoolsProgressiveWebApps]"）使用 **服务工作人员**帮助脱机工作。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-151">A new class of web apps, named [Progressive Web Apps][DevtoolsProgressiveWebApps], functions offline with the help of **service workers**.</span></span>  <span data-ttu-id="bcdc8-152">你可能会发现，在你构建此类型的应用时，快速模拟没有数据连接的设备非常有用。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-152">You may find it useful to quickly simulate a device that has no data connection when you are building this type of app.</span></span>  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

<span data-ttu-id="bcdc8-153">选择 " **联机** " 下拉菜单，在 " **预置**" 下搜索，然后选择 " **脱机** " 以模拟脱机网络体验。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-153">Choose the **Online** dropdown menu, search under **Presets**, and choose **Offline** to simulate an offline network experience.</span></span>  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text=""脱机" 下拉菜单" lightbox="../media/network-network-offline-dropdown.msft.png":::
   <span data-ttu-id="bcdc8-155">" **脱机** " 下拉菜单</span><span class="sxs-lookup"><span data-stu-id="bcdc8-155">The **Offline** dropdown menu</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-156">模拟慢速网络连接</span><span class="sxs-lookup"><span data-stu-id="bcdc8-156">Emulate slow network connections</span></span>  

<span data-ttu-id="bcdc8-157">从 " **联机** " 下拉菜单中模拟慢速3G、快速3g 和其他连接速度。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-157">Emulate Slow 3G, Fast 3G, and other connection speeds from the **Online** dropdown menu.</span></span>  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text="限制下拉菜单" lightbox="../media/network-network-throttling-menu.msft.png":::
   <span data-ttu-id="bcdc8-159">**限制**下拉菜单</span><span class="sxs-lookup"><span data-stu-id="bcdc8-159">The **Throttling** dropdown menu</span></span>  
:::image-end:::  

<span data-ttu-id="bcdc8-160">您可以选择不同的预设，例如，"低速 3G" 或 "快速 3G"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-160">You may choose from different presets, such as Slow 3G or Fast 3G.</span></span>  <span data-ttu-id="bcdc8-161">若要添加您自己的自定义预设，请打开 "限制" 菜单，然后选择 "**自定义**  >  **添加**"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-161">To add your own custom presets, open the Throttling menu, and choose **Custom** > **Add**.</span></span>  

<span data-ttu-id="bcdc8-162">DevTools 将在 " **网络** " 选项卡旁显示一个警告图标，提醒你已启用限制。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-162">DevTools displays a warning icon next to the **Network** tab to remind you that throttling is enabled.</span></span>  

#### <span data-ttu-id="bcdc8-163">从网络条件抽屉中模拟慢速网络连接</span><span class="sxs-lookup"><span data-stu-id="bcdc8-163">Emulate slow network connections from the Network Conditions drawer</span></span>  

<span data-ttu-id="bcdc8-164">如果您希望在其他 DevTools 面板中工作时限制网络连接，请使用网络条件抽屉。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-164">If you want to throttle the network connection while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="bcdc8-165">打开 **网络条件** 抽屉。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-165">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="bcdc8-166">从 " **限制** " 菜单中选择连接速度。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-166">Choose your connection speed from the **Throttling** menu.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="bcdc8-167">手动清除浏览器 cookie</span><span class="sxs-lookup"><span data-stu-id="bcdc8-167">Manually clear browser cookies</span></span>  

<span data-ttu-id="bcdc8-168">若要随时手动清除浏览器 cookie，请将鼠标悬停在 "请求" 表中的任意位置，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **清除浏览器 cookie**"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-168">To manually clear browser cookies at any time, hover anywhere in the Requests table, open the contextual menu \(right-click\), and choose **Clear Browser Cookies**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="选择 "清除浏览器 Cookie"" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   <span data-ttu-id="bcdc8-170">选择 "**清除浏览器 cookie** "</span><span class="sxs-lookup"><span data-stu-id="bcdc8-170">Choose **Clear Browser Cookies**</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-171">替代用户代理</span><span class="sxs-lookup"><span data-stu-id="bcdc8-171">Override the user agent</span></span>  

<span data-ttu-id="bcdc8-172">若要手动替代用户代理，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-172">To manually override the user agent, use the following steps.</span></span>  

1.  <span data-ttu-id="bcdc8-173">打开 **网络条件** 抽屉。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-173">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="bcdc8-174">关闭 " **自动选择** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-174">Turn off the **Select automatically** checkbox.</span></span>  
1.  <span data-ttu-id="bcdc8-175">从菜单中选择用户代理选项，或在文本框中输入自定义选项。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-175">Choose a user agent option from the menu, or enter a custom one in the text box.</span></span>  

<!--todo: add network condition section when available -->  

## <span data-ttu-id="bcdc8-176">筛选请求</span><span class="sxs-lookup"><span data-stu-id="bcdc8-176">Filter requests</span></span>  

### <span data-ttu-id="bcdc8-177">按属性筛选请求</span><span class="sxs-lookup"><span data-stu-id="bcdc8-177">Filter requests by properties</span></span>  

<span data-ttu-id="bcdc8-178">使用 " **筛选** " 文本框筛选按属性（如请求的域或大小）的请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-178">Use the **Filter** text box to filter requests by properties, such as the domain or size of the request.</span></span>  

<span data-ttu-id="bcdc8-179">如果未显示文本框，则 " **筛选器** " 窗格可能处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-179">If the text box is not displayed, the **Filters** pane is probably hidden.</span></span>  
<span data-ttu-id="bcdc8-180">有关详细信息，请导航到 ["隐藏筛选器" 窗格](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-180">For more information, navigate to [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text=""筛选器" 文本框" lightbox="../media/network-network-filters-textbox.msft.png":::
   <span data-ttu-id="bcdc8-182">" **筛选器** " 文本框</span><span class="sxs-lookup"><span data-stu-id="bcdc8-182">The **Filter** text box</span></span>  
:::image-end:::  

<span data-ttu-id="bcdc8-183">你可以通过使用空格分隔每个属性来同时使用多个属性。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-183">You may use multiple properties simultaneously by separating each property with a space.</span></span>  <span data-ttu-id="bcdc8-184">例如， `mime-type:image/png larger-than:1K` 显示大于 1 kb 的所有 PNGs。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-184">For example, `mime-type:image/png larger-than:1K` displays all PNGs that are larger than 1 kilobyte.</span></span>  <span data-ttu-id="bcdc8-185">多属性筛选器等效于 `AND` 操作。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-185">The multi-property filters are equivalent to `AND` operations.</span></span>  `OR` <span data-ttu-id="bcdc8-186">当前不支持操作。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-186">operations are currently not supported.</span></span>  

<span data-ttu-id="bcdc8-187">受支持的属性的完整列表。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-187">The complete list of supported properties.</span></span>  

| <span data-ttu-id="bcdc8-188">属性</span><span class="sxs-lookup"><span data-stu-id="bcdc8-188">Property</span></span> | <span data-ttu-id="bcdc8-189">详细信息</span><span class="sxs-lookup"><span data-stu-id="bcdc8-189">Details</span></span> |  
|:--- | :--- |  
| `domain` | <span data-ttu-id="bcdc8-190">仅显示指定域中的资源。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-190">Only display resources from the specified domain.</span></span>  <span data-ttu-id="bcdc8-191">您可以使用通配符 \ (`*` \ ) 包含多个域。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-191">You may use a wildcard character \(`*`\) to include multiple domains.</span></span>  <span data-ttu-id="bcdc8-192">例如， `*.com` 显示所有以结尾的域名的资源 `.com` 。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-192">For example, `*.com` displays resources from all domain names ending in `.com`.</span></span>  <span data-ttu-id="bcdc8-193">DevTools 将填充 "自动完成" 下拉菜单，其中包含找到的所有域。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-193">DevTools populate the autocomplete dropdown menu with all of the domains that are found.</span></span> |  
| `has-response-header` | <span data-ttu-id="bcdc8-194">显示包含指定的 HTTP 响应标头的资源。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-194">Displays the resources that contain the specified HTTP response header.</span></span>  <span data-ttu-id="bcdc8-195">DevTools 将通过找到的所有响应标题填充 "自动完成" 下拉列表。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-195">DevTools populate the autocomplete dropdown with all of the response headers that are found.</span></span> |  
| `is` | <span data-ttu-id="bcdc8-196">用于 `is:running` 查找 `WebSocket` 资源。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-196">Use `is:running` to find `WebSocket` resources.</span></span> |  
| `larger-than` | <span data-ttu-id="bcdc8-197">显示大于指定大小（以字节为单位）的资源。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-197">Displays resources that are larger than the specified size, in bytes.</span></span>  <span data-ttu-id="bcdc8-198">设置值 `1000` 等效于将值设置为 `1k` 。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-198">Setting a value of `1000` is equivalent to setting a value of `1k`.</span></span> |  
| `method` | <span data-ttu-id="bcdc8-199">显示通过指定的 HTTP 方法类型检索的资源。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-199">Displays resources that were retrieved over a specified HTTP method type.</span></span>  <span data-ttu-id="bcdc8-200">DevTools 将通过找到的所有 HTTP 方法填充下拉列表。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-200">DevTools populate the dropdown with all of the HTTP methods  that are found.</span></span> |  
| `mime-type` | <span data-ttu-id="bcdc8-201">显示指定 MIME 类型的资源。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-201">Displays resources of a specified MIME type.</span></span>  <span data-ttu-id="bcdc8-202">DevTools 将通过找到的所有 MIME 类型填充下拉列表。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-202">DevTools populate the dropdown with all MIME types  that are found.</span></span> |  
| `mixed-content` | <span data-ttu-id="bcdc8-203">显示所有混合内容资源 \ (`mixed-content:all` \ ) 或仅显示当前显示的 \ (`mixed-content:displayed` \ ) 的资源。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-203">Show all mixed content resources \(`mixed-content:all`\) or just the ones that are currently displayed \(`mixed-content:displayed`\).</span></span> |  
| `scheme` | <span data-ttu-id="bcdc8-204">显示通过未受保护的 HTTP \ (`scheme:http` \ ) 或受保护的 HTTPS \ (`scheme:https` \ ) 检索的资源。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-204">Displays resources retrieved over unprotected HTTP \(`scheme:http`\) or protected HTTPS \(`scheme:https`\).</span></span> |  
| `set-cookie-domain` | <span data-ttu-id="bcdc8-205">显示具有 `Set-Cookie` 与指定值匹配的属性的标题的资源 `Domain` 。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-205">Displays resources that have a `Set-Cookie` header with a `Domain` attribute that matches the specified value.</span></span>  <span data-ttu-id="bcdc8-206">DevTools 将通过找到的所有 cookie 域填充自动完成功能。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-206">DevTools populate the autocomplete with all of the cookie domains that are found.</span></span> |  
| `set-cookie-name` | <span data-ttu-id="bcdc8-207">显示具有 `Set-Cookie` 与指定值匹配的名称的标题的资源。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-207">Displays resources that have a `Set-Cookie` header with a name that matches the specified value.</span></span>  <span data-ttu-id="bcdc8-208">DevTools 将通过找到的所有 cookie 名称填充记忆式键入。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-208">DevTools populate the autocomplete with all of the cookie names that are found.</span></span> |  
| `set-cookie-value` | <span data-ttu-id="bcdc8-209">显示具有 `Set-Cookie` 与指定值匹配的值的标题的资源。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-209">Displays resources that have a `Set-Cookie` header with a value that matches the specified value.</span></span>  <span data-ttu-id="bcdc8-210">DevTools 将通过找到的所有 cookie 值填充记忆式键入。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-210">DevTools populate the autocomplete with all of the cookie values that are found.</span></span> |  
| `status-code` | <span data-ttu-id="bcdc8-211">显示与特定 HTTP 状态代码匹配的资源。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-211">Displays resources that match the specific HTTP status code.</span></span>  <span data-ttu-id="bcdc8-212">DevTools 将填充 "自动完成" 下拉菜单，其中包含找到的所有状态代码。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-212">DevTools populates the autocomplete dropdown menu with all of the status codes that are found.</span></span> |  

### <span data-ttu-id="bcdc8-213">按类型筛选请求</span><span class="sxs-lookup"><span data-stu-id="bcdc8-213">Filter requests by type</span></span>  

<span data-ttu-id="bcdc8-214">若要按请求类型筛选请求，请选择 " **网络** " 面板上的以下按钮之一。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-214">To filter requests by request type, choose the one of the following buttons on the **Network** panel.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-215">XHR</span><span class="sxs-lookup"><span data-stu-id="bcdc8-215">XHR</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-216">JS</span><span class="sxs-lookup"><span data-stu-id="bcdc8-216">JS</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-217">CSS</span><span class="sxs-lookup"><span data-stu-id="bcdc8-217">CSS</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-218">Img</span><span class="sxs-lookup"><span data-stu-id="bcdc8-218">Img</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-219">Media</span><span class="sxs-lookup"><span data-stu-id="bcdc8-219">Media</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-220">字体</span><span class="sxs-lookup"><span data-stu-id="bcdc8-220">Font</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-221">首</span><span class="sxs-lookup"><span data-stu-id="bcdc8-221">Doc</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-222">WS-TRUST</span><span class="sxs-lookup"><span data-stu-id="bcdc8-222">WS</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-223">WebSocket.</span><span class="sxs-lookup"><span data-stu-id="bcdc8-223">WebSocket.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-224">部件</span><span class="sxs-lookup"><span data-stu-id="bcdc8-224">Manifest</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-225">Other</span><span class="sxs-lookup"><span data-stu-id="bcdc8-225">Other</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-226">未列出任何其他类型。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-226">Any other type not listed.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="bcdc8-227">如果未显示按钮，则 " **筛选器** " 窗格可能处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-227">If the buttons do not display, the **Filters** pane may be hidden.</span></span>  
<span data-ttu-id="bcdc8-228">有关详细信息，请导航到 ["隐藏筛选器" 窗格](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-228">For more information, navigate to [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

<span data-ttu-id="bcdc8-229">若要同时启用多个类型筛选器，请按住 `Control` (Windows、Linux \ ) 或 `Command` \ (macOS \ ) 然后选择。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-229">To enable multiple type filters simultaneously, hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and then choose.</span></span>  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="使用类型筛选器显示 JS、CSS 和文档资源" lightbox="../media/network-network-type-filters.msft.png":::
   <span data-ttu-id="bcdc8-231">使用类型筛选器显示 JS、CSS 和文档资源</span><span class="sxs-lookup"><span data-stu-id="bcdc8-231">Use the Type filters to display JS, CSS, and Document resources</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-232">按时间筛选请求</span><span class="sxs-lookup"><span data-stu-id="bcdc8-232">Filter requests by time</span></span>  

<span data-ttu-id="bcdc8-233">在 " **概述** " 窗格中选择并向左或向右拖动，以仅显示在该时间范围内处于活动状态的请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-233">Choose and drag left or right on the **Overview** pane to only display requests that were active during that time frame.</span></span>  <span data-ttu-id="bcdc8-234">筛选器是包含的。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-234">The filter is inclusive.</span></span>  <span data-ttu-id="bcdc8-235">显示在突出显示的时间内处于活动状态的任何请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-235">Any request that was active during the highlighted time is shown.</span></span>  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="筛选出 300 ms 周围处于非活动状态的所有请求" lightbox="../media/network-network-overview-filter.msft.png":::
   <span data-ttu-id="bcdc8-237">筛选出 300 ms 周围处于非活动状态的所有请求</span><span class="sxs-lookup"><span data-stu-id="bcdc8-237">Filter out any requests that were inactive around 300 ms</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-238">隐藏数据 Url</span><span class="sxs-lookup"><span data-stu-id="bcdc8-238">Hide data URLs</span></span>  

<span data-ttu-id="bcdc8-239">[数据 url][MDNHTTPDataURIs] 是嵌入到其他文档中的小文件。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-239">[Data URLs][MDNHTTPDataURIs] are small files embedded into other documents.</span></span>  <span data-ttu-id="bcdc8-240">"请求" 表中显示的以数据 URL 开头的任何请求 `data:` 。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-240">Any request that displays in the Requests table that starts with `data:` is a data URL.</span></span>  

<span data-ttu-id="bcdc8-241">若要隐藏请求，请关闭 " **隐藏数据 url** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-241">To hide the requests, turn off the **Hide data URLs** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text=""隐藏数据 Url" 复选框" lightbox="../media/network-network-hide-data-urls.msft.png":::
   <span data-ttu-id="bcdc8-243">" **隐藏数据 url** " 复选框</span><span class="sxs-lookup"><span data-stu-id="bcdc8-243">The **Hide Data URLs** checkbox</span></span>  
:::image-end:::  

## <span data-ttu-id="bcdc8-244">排序请求</span><span class="sxs-lookup"><span data-stu-id="bcdc8-244">Sort requests</span></span>  

<span data-ttu-id="bcdc8-245">默认情况下，请求表中的请求按初始时间排序，但你可以使用其他条件对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-245">By default, the requests in the Requests table are sorted by initiation time, but you may sort the table using other criteria.</span></span>  

### <span data-ttu-id="bcdc8-246">按列排序</span><span class="sxs-lookup"><span data-stu-id="bcdc8-246">Sort by column</span></span>  

<span data-ttu-id="bcdc8-247">选择请求中的任何列的标题，对该列的请求进行排序。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-247">Choose the header of any column in the Requests to sort requests by that column.</span></span>  

### <span data-ttu-id="bcdc8-248">按活动阶段排序</span><span class="sxs-lookup"><span data-stu-id="bcdc8-248">Sort by activity phase</span></span>  

<span data-ttu-id="bcdc8-249">若要更改瀑布对请求的排序方式，请将鼠标悬停在 "请求" 表的标题上，打开上下文菜单 \ (右键单击 "\ ) "，将鼠标悬停在 **瀑布**图上，然后选择下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-249">To change how the Waterfall sorts requests, hover on the header of the Requests table, open the contextual menu \(right-click\), hover on **Waterfall**, and choose one of the following options.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-250">开始时间</span><span class="sxs-lookup"><span data-stu-id="bcdc8-250">Start Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-251">启动的第一个请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-251">The first request that was initiated is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-252">响应时间</span><span class="sxs-lookup"><span data-stu-id="bcdc8-252">Response Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-253">开始下载的第一个请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-253">The first request that started downloading is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-254">结束时间</span><span class="sxs-lookup"><span data-stu-id="bcdc8-254">End Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-255">第一个已完成的请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-255">The first request that finished is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-256">总工期</span><span class="sxs-lookup"><span data-stu-id="bcdc8-256">Total Duration</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-257">具有最短连接设置和请求或响应的请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-257">The request with the shortest connection settings and request or response is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-258">滞后</span><span class="sxs-lookup"><span data-stu-id="bcdc8-258">Latency</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-259">等待响应时间最短的请求位于最前面。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-259">The request that waited the shortest time for a response is at the top.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="bcdc8-260">这些说明假定每个各自的选项均按最短到最长的排序。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-260">These descriptions assume that each respective option is ranked from shortest to longest.</span></span>  <span data-ttu-id="bcdc8-261">选择 **瀑布** 栏的标题以反转顺序。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-261">Choose the header of the **Waterfall** column to reverse the order.</span></span>  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="按总工期对瀑布图进行排序" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   <span data-ttu-id="bcdc8-263">按总持续时间对瀑布图进行排序 \ (每个条形图的较亮部分是等待的时间，较暗的部分是下载字节所花费的时间 \ ) </span><span class="sxs-lookup"><span data-stu-id="bcdc8-263">Sort the Waterfall by total duration  \(The lighter portion of each bar is time spent waiting and the darker portion is time spent downloading bytes\)</span></span>  
:::image-end:::  

## <span data-ttu-id="bcdc8-264">分析请求</span><span class="sxs-lookup"><span data-stu-id="bcdc8-264">Analyze requests</span></span>  

<span data-ttu-id="bcdc8-265">只要 DevTools 打开，它就会在 " **网络** " 面板中记录所有请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-265">So long as DevTools are open, it logs all requests in the **Network** panel.</span></span>  
<span data-ttu-id="bcdc8-266">使用 "网络" 面板分析请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-266">Use the Network panel to analyze requests.</span></span>  

### <span data-ttu-id="bcdc8-267">显示请求日志</span><span class="sxs-lookup"><span data-stu-id="bcdc8-267">Display a log of requests</span></span>  

<span data-ttu-id="bcdc8-268">使用 "请求" 表，显示在 DevTools 打开时发出的所有请求的日志。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-268">Use the Requests table to display a log of all requests made while DevTools have been open.</span></span>  <span data-ttu-id="bcdc8-269">若要显示有关每个项目的详细信息，请选择或悬停请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-269">To reveals more information about each item, choose or hover on requests.</span></span>  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="请求表" lightbox="../media/network-network-requests-table.msft.png":::
   <span data-ttu-id="bcdc8-271">请求表</span><span class="sxs-lookup"><span data-stu-id="bcdc8-271">The Requests table</span></span>  
:::image-end:::  

<span data-ttu-id="bcdc8-272">"请求" 表默认情况下显示以下列。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-272">The Requests table displays the following columns by default.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-273">名称</span><span class="sxs-lookup"><span data-stu-id="bcdc8-273">Name</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-274">资源的文件名或标识符。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-274">The filename of, or an identifier for, the resource.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-275">状态</span><span class="sxs-lookup"><span data-stu-id="bcdc8-275">Status</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-276">HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-276">The HTTP status code.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-277">类型</span><span class="sxs-lookup"><span data-stu-id="bcdc8-277">Type</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-278">所请求的资源的 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-278">The MIME type of the requested resource.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-279">启动</span><span class="sxs-lookup"><span data-stu-id="bcdc8-279">Initiator</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-280">以下对象或进程启动请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-280">The following objects or processes initiate requests.</span></span>  
      
      *   <span data-ttu-id="bcdc8-281">**分析**  程序 Microsoft Edge 的 HTML 分析程序。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-281">**Parser**  The HTML parser for Microsoft Edge.</span></span>  
      *   <span data-ttu-id="bcdc8-282">**重定向**  HTTP 重定向。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-282">**Redirect**  An HTTP redirect.</span></span>  
      *   <span data-ttu-id="bcdc8-283">**脚本**  JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-283">**Script**  A JavaScript function.</span></span>  
      *   <span data-ttu-id="bcdc8-284">**其他**  某些其他进程或操作，例如，使用链接导航到页面或在地址栏中输入 URL。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-284">**Other**  Some other process or action, such as navigating to a page using a link or entering a URL in the address bar.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-285">大小</span><span class="sxs-lookup"><span data-stu-id="bcdc8-285">Size</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-286">由服务器发送的响应标题和响应正文的合并大小。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-286">The combined size of the response headers plus the response body, as delivered by the server.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-287">时间</span><span class="sxs-lookup"><span data-stu-id="bcdc8-287">Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-288">从请求开始到响应中最后一个字节的接收的总持续时间。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-288">The total duration, from the start of the request to the receipt of the final byte in the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="bcdc8-289">瀑布</span><span class="sxs-lookup"><span data-stu-id="bcdc8-289">Waterfall</span></span>](#display-the-timing-relationship-of-requests)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-290">每个请求的活动的可视化细目。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-290">A visual breakdown of the activity for each request.</span></span>  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="bcdc8-291">添加或删除列</span><span class="sxs-lookup"><span data-stu-id="bcdc8-291">Add or remove columns</span></span>  

<span data-ttu-id="bcdc8-292">将鼠标悬停在 "请求" 表的标题上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择一个选项以隐藏或显示它。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-292">Hover on the header of the Requests table, open the contextual menu \(right-click\), and choose an option to hide or show it.</span></span>  <span data-ttu-id="bcdc8-293">当前显示的选项在每个项目旁边都有复选标记。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-293">Currently displayed options have checkmarks next to each item.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="向请求表添加列" lightbox="../media/network-network-requests-add-column.msft.png":::
   <span data-ttu-id="bcdc8-295">向请求表添加列</span><span class="sxs-lookup"><span data-stu-id="bcdc8-295">Add a column to the Requests table</span></span>  
:::image-end:::  

#### <span data-ttu-id="bcdc8-296">添加自定义列</span><span class="sxs-lookup"><span data-stu-id="bcdc8-296">Add custom columns</span></span>  

<span data-ttu-id="bcdc8-297">若要向 "请求" 表添加自定义列，请将鼠标悬停在 "请求" 表的标题上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 "**响应标题**  >  **管理标题列**"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-297">To add a custom column to the Requests table, hover on the header of the Requests table, open the contextual menu \(right-click\), and choose **Response Headers** > **Manage Header Columns**.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="向请求表添加自定义列" lightbox="../media/network-network-requests-add-custom.msft.png":::
   <span data-ttu-id="bcdc8-299">向请求表添加自定义列</span><span class="sxs-lookup"><span data-stu-id="bcdc8-299">Add a custom column to the Requests table</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-300">显示请求的计时关系</span><span class="sxs-lookup"><span data-stu-id="bcdc8-300">Display the timing relationship of requests</span></span>  

<span data-ttu-id="bcdc8-301">使用瀑布图显示请求的计时关系。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-301">Use the Waterfall to display the timing relationships of requests.</span></span>  
<span data-ttu-id="bcdc8-302">瀑布图的默认组织使用请求的开始时间。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-302">The default organization of the Waterfall uses the start time of the requests.</span></span>  
<span data-ttu-id="bcdc8-303">因此，比右侧更远的请求更早地开始向左的请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-303">So, requests that are farther to the left started earlier than the requests that are farther to the right.</span></span>  

<span data-ttu-id="bcdc8-304">若要查看可对瀑布图排序的不同方式，请导航到 " [按活动排序" 阶段](#sort-by-activity-phase)。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-304">To review the different ways that you may sort the Waterfall, navigate to [Sort by activity phase](#sort-by-activity-phase).</span></span>  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text=""请求" 窗格的瀑布栏" lightbox="../media/network-network-requests-waterfall.msft.png":::
   <span data-ttu-id="bcdc8-306">" **请求** " 窗格的瀑布栏</span><span class="sxs-lookup"><span data-stu-id="bcdc8-306">The Waterfall column of the **Requests** pane</span></span>  
:::image-end:::  

<!-- ### Analyze the frames of a WebSocket Connection  -->

<!--To review the frames of a WebSocket connection, use the following steps.  

1.  Choose the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Choose the **Frames** tab.  The table shows the last 100 frames.  

To refresh the table, re-choose the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
:::image type="complex" source="../media/network-frames.msft.png" alt-text="The Frames tab" lightbox="../media/network-frames.msft.png":::
   The **Frames** tab  
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

### <span data-ttu-id="bcdc8-307">显示响应正文的预览</span><span class="sxs-lookup"><span data-stu-id="bcdc8-307">Display a preview of a response body</span></span>  

<span data-ttu-id="bcdc8-308">若要显示响应正文的预览，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-308">To display a preview of a response body, use the following steps.</span></span>  

1.  <span data-ttu-id="bcdc8-309">在 "请求" 表的 " **名称** " 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-309">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="bcdc8-310">选择 " **预览** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-310">Choose the **Preview** tab.</span></span>  

<span data-ttu-id="bcdc8-311">"预览" 选项卡主要用于显示图像。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-311">The Preview tab is mostly useful to display images.</span></span>  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text=""预览" 选项卡" lightbox="../media/network-network-resources-preview.msft.png":::
   <span data-ttu-id="bcdc8-313">" **预览** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="bcdc8-313">The **Preview** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-314">显示响应正文</span><span class="sxs-lookup"><span data-stu-id="bcdc8-314">Display a response body</span></span>  

<span data-ttu-id="bcdc8-315">若要将响应正文显示给请求，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-315">To display the response body to a request, use the following steps.</span></span>  

1.  <span data-ttu-id="bcdc8-316">在 "请求" 表的 " **名称** " 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-316">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="bcdc8-317">选择 " **响应** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-317">Choose the **Response** tab.</span></span>  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text=""响应" 选项卡" lightbox="../media/network-network-resources-response.msft.png":::
   <span data-ttu-id="bcdc8-319">" **响应** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="bcdc8-319">The **Response** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-320">显示 HTTP 头</span><span class="sxs-lookup"><span data-stu-id="bcdc8-320">Display HTTP headers</span></span>  

<span data-ttu-id="bcdc8-321">若要显示有关请求的 HTTP 标头数据，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-321">To display HTTP header data about a request, use the following steps.</span></span>  

1.  <span data-ttu-id="bcdc8-322">在 "请求" 表的 " **名称** " 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-322">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="bcdc8-323">选择 " **页眉** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-323">Choose the **Headers** tab.</span></span>  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text=""页眉" 选项卡" lightbox="../media/network-resources-headers.msft.png":::
   <span data-ttu-id="bcdc8-325">" **页眉** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="bcdc8-325">The **Headers** tab</span></span>  
:::image-end:::  

#### <span data-ttu-id="bcdc8-326">显示 HTTP 域名源</span><span class="sxs-lookup"><span data-stu-id="bcdc8-326">Display HTTP header source</span></span>  

<span data-ttu-id="bcdc8-327">默认情况下，"页眉" 选项卡按字母顺序显示标题名称。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-327">By default, the Headers tab shows header names alphabetically.</span></span>  <span data-ttu-id="bcdc8-328">若要在接收的订单中的 HTTP 标头名称，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-328">To dsiplay the HTTP header names in the order received, use the following steps.</span></span>  

1.  <span data-ttu-id="bcdc8-329">打开您感兴趣的请求的 " **标题** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-329">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="bcdc8-330">有关详细信息，请导航到 " [显示 HTTP 标头](#display-http-headers)"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-330">For more information, navigate to [Display HTTP headers](#display-http-headers).</span></span>  
1.  <span data-ttu-id="bcdc8-331">选择 " **查看源**"，然后选择 " **请求标头** " 或 " **响应标题** " 部分。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-331">Choose **view source**, next to the **Request Header** or **Response Header** section.</span></span>  

### <span data-ttu-id="bcdc8-332">显示查询字符串参数</span><span class="sxs-lookup"><span data-stu-id="bcdc8-332">Display query string parameters</span></span>  

<span data-ttu-id="bcdc8-333">若要以人类可读的格式显示 URL 的查询字符串参数，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-333">To display the query string parameters of a URL in a human-readable format, use the following steps.</span></span>  

1.  <span data-ttu-id="bcdc8-334">打开您感兴趣的请求的 " **标题** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-334">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="bcdc8-335">有关详细信息，请导航到 " [显示 HTTP 标头](#display-http-headers)"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-335">For more information, navigate to [Display HTTP headers](#display-http-headers).</span></span>  
1.  <span data-ttu-id="bcdc8-336">转到 " **查询字符串参数** " 部分。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-336">Go to the **Query String Parameters** section.</span></span>  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text=""查询字符串参数" 部分" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   <span data-ttu-id="bcdc8-338">" **查询字符串参数** " 部分</span><span class="sxs-lookup"><span data-stu-id="bcdc8-338">The **Query String Parameters** section</span></span>  
:::image-end:::  

#### <span data-ttu-id="bcdc8-339">显示查询字符串参数源</span><span class="sxs-lookup"><span data-stu-id="bcdc8-339">Display query string parameters source</span></span>  

<span data-ttu-id="bcdc8-340">若要显示请求的查询字符串参数源，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-340">To display the query string parameter source of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="bcdc8-341">转到 "查询字符串参数" 部分。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-341">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="bcdc8-342">有关详细信息，请导航到 " [显示查询字符串参数](#display-query-string-parameters)"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-342">For more information, navigate to [Display query string parameters](#display-query-string-parameters).</span></span>  
1.  <span data-ttu-id="bcdc8-343">选择 " **查看源**"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-343">Choose **view source**.</span></span>  

#### <span data-ttu-id="bcdc8-344">显示 URL 编码的查询字符串参数</span><span class="sxs-lookup"><span data-stu-id="bcdc8-344">Display URL-encoded query string parameters</span></span>  

<span data-ttu-id="bcdc8-345">若要以可读格式显示查询字符串参数，但保留编码，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-345">To display query string parameters in a human-readable format, but with encodings preserved, use the following steps.</span></span>  

1.  <span data-ttu-id="bcdc8-346">转到 "查询字符串参数" 部分。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-346">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="bcdc8-347">有关详细信息，请导航到 " [显示查询字符串参数](#display-query-string-parameters)"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-347">For more information, navigate to [Display query string parameters](#display-query-string-parameters).</span></span>  
1.  <span data-ttu-id="bcdc8-348">选择 " **查看 URL 编码**"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-348">Choose **view URL encoded**.</span></span>  

### <span data-ttu-id="bcdc8-349">显示 cookie</span><span class="sxs-lookup"><span data-stu-id="bcdc8-349">Display cookies</span></span>  

<span data-ttu-id="bcdc8-350">若要显示在请求的 HTTP 头中发送的 cookie，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-350">To display the cookies sent in the HTTP header of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="bcdc8-351">在 "请求" 表的 " **名称** " 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-351">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="bcdc8-352">选择 " **cookie** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-352">Choose the **Cookies** tab.</span></span>  

<!--For more information about each of the columns, navigate to [Fields][ManageDataCookiesFields].  -->  

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->  
<!--TODO: add link when section is available -->  

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text=""Cookie" 选项卡" lightbox="../media/network-network-resources-cookies.msft.png":::
   <span data-ttu-id="bcdc8-354">"Cookie" 选项卡</span><span class="sxs-lookup"><span data-stu-id="bcdc8-354">The Cookies tab</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-355">显示请求的计时细目</span><span class="sxs-lookup"><span data-stu-id="bcdc8-355">Display the timing breakdown of a request</span></span>  

<span data-ttu-id="bcdc8-356">若要显示请求的计时细目，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-356">To display the timing breakdown of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="bcdc8-357">在 "请求" 表的 " **名称** " 列下，选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-357">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="bcdc8-358">选择 " **计时** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-358">Choose the **Timing** tab.</span></span>  

<span data-ttu-id="bcdc8-359">若要以更快的方式访问数据，请导航到 " [预览计时分析](#preview-a-timing-breakdown)"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-359">For a faster way to access the data, navigate to [Preview a timing breakdown](#preview-a-timing-breakdown).</span></span>  

<span data-ttu-id="bcdc8-360">有关 " **计时** " 选项卡中可能显示的每个阶段的详细信息，请导航到 " [计时分解" 阶段](#timing-breakdown-phases-explained)。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-360">For more information about each of the phases that may be displayed in the **Timing** tab, navigate to [Timing breakdown phases explained](#timing-breakdown-phases-explained).</span></span>  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text=""计时" 选项卡" lightbox="../media/network-network-resources-timing.msft.png":::
   <span data-ttu-id="bcdc8-362">" **计时** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="bcdc8-362">The **Timing** tab</span></span>  
:::image-end:::  

<span data-ttu-id="bcdc8-363">有关每个阶段的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-363">More information about each of the phases.</span></span>  

<span data-ttu-id="bcdc8-364">有关访问显示的详细信息，请导航到 " [显示计时细目](#display-the-timing-breakdown-of-a-request)"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-364">For more information about accessing the display, navigate to [Display timing breakdown](#display-the-timing-breakdown-of-a-request).</span></span>  

#### <span data-ttu-id="bcdc8-365">预览计时细目</span><span class="sxs-lookup"><span data-stu-id="bcdc8-365">Preview a timing breakdown</span></span>  

<span data-ttu-id="bcdc8-366">若要显示请求的计时分解的预览，请在 "请求" 表的 " **瀑布** 图" 列中，将鼠标悬停在请求的条目上。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-366">To display a preview of the timing breakdown of a request, in the **Waterfall** column of the Requests table, hover on the entry for the request.</span></span>  

<span data-ttu-id="bcdc8-367">有关如何在没有悬停的情况下访问数据的详细信息，请导航到 " [显示请求的计时细目"](#display-the-timing-breakdown-of-a-request)。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-367">For more information about how to access the data without hovering, navigate to [Display the timing breakdown of a request](#display-the-timing-breakdown-of-a-request).</span></span>  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text="> 预览请求的计时细目" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   <span data-ttu-id="bcdc8-369">预览请求的计时细目</span><span class="sxs-lookup"><span data-stu-id="bcdc8-369">Preview the timing breakdown of a request</span></span>  
:::image-end:::  

#### <span data-ttu-id="bcdc8-370">已解释的计时分解阶段</span><span class="sxs-lookup"><span data-stu-id="bcdc8-370">Timing breakdown phases explained</span></span>  

<span data-ttu-id="bcdc8-371">有关可能在 " **计时** " 选项卡中显示的每个阶段的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-371">More information about each of the phases that may display in the **Timing** tab.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-372">入</span><span class="sxs-lookup"><span data-stu-id="bcdc8-372">Queueing</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-373">当以下任何条件为 true 时，浏览器将请求排队。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-373">The browser queues requests when any of the following are true.</span></span>  
      
      *   <span data-ttu-id="bcdc8-374">存在更高优先级的请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-374">Higher priority requests exist.</span></span>  
      *   <span data-ttu-id="bcdc8-375">对于相同的原点，6个 TCP 连接是开放的，这是限制。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-375">Six TCP connections are open for the same origin, which is the limit.</span></span>  <span data-ttu-id="bcdc8-376">仅适用于 HTTP/1.0 和 HTTP/1.1。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-376">Applies to HTTP/1.0 and HTTP/1.1 only.</span></span>  
      *   <span data-ttu-id="bcdc8-377">浏览器在磁盘缓存中短暂分配空间。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-377">The browser is briefly allocating space in the disk cache.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-378">停止</span><span class="sxs-lookup"><span data-stu-id="bcdc8-378">Stalled</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-379">由于 " **排队**" 中所述的任何原因，请求停止。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-379">The request is stalled for any of the reasons described in **Queueing**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-380">DNS 查找</span><span class="sxs-lookup"><span data-stu-id="bcdc8-380">DNS Lookup</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-381">浏览器正在解析请求的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-381">The browser is resolving the IP address for the request.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-382">初始连接</span><span class="sxs-lookup"><span data-stu-id="bcdc8-382">Initial connection</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-383">浏览器建立一个连接，包括 TCP 握手、TCP 重试以及协商安全套接字层。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-383">The browser establishes a connection including TCP handshakes, TCP retries, and negotiates a Secure Socket Layer.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-384">代理协商</span><span class="sxs-lookup"><span data-stu-id="bcdc8-384">Proxy negotiation</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-385">浏览器正使用 [代理服务器][WikiProxyServer]协商请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-385">The browser is negotiating the request with a [proxy server][WikiProxyServer].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-386">请求已发送</span><span class="sxs-lookup"><span data-stu-id="bcdc8-386">Request sent</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-387">正在发送请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-387">The request is being sent.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-388">ServiceWorker 准备</span><span class="sxs-lookup"><span data-stu-id="bcdc8-388">ServiceWorker Preparation</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-389">浏览器正在启动服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-389">The browser is starting the service worker.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-390">请求 ServiceWorker</span><span class="sxs-lookup"><span data-stu-id="bcdc8-390">Request to ServiceWorker</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-391">请求将发送给服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-391">The request is being sent to the service worker.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-392">正在等待 \ (TTFB \ ) </span><span class="sxs-lookup"><span data-stu-id="bcdc8-392">Waiting \(TTFB\)</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-393">浏览器正在等待响应的第一个字节。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-393">The browser is waiting for the first byte of a response.</span></span>  <span data-ttu-id="bcdc8-394">TTFB 代表第一个字节的时间。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-394">TTFB stands for Time To First Byte.</span></span>  <span data-ttu-id="bcdc8-395">此定时包括延迟的一次往返行程，以及服务器准备响应的时间。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-395">This timing includes one round trip of latency and the time the server took to prepare the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-396">内容下载</span><span class="sxs-lookup"><span data-stu-id="bcdc8-396">Content Download</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-397">浏览器正在接收响应。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-397">The browser is receiving the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-398">接收推送</span><span class="sxs-lookup"><span data-stu-id="bcdc8-398">Receiving Push</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-399">浏览器正在通过 HTTP/2 服务器推送接收此响应的数据。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-399">The browser is receiving data for this response via HTTP/2 Server Push.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="bcdc8-400">正在读取推送</span><span class="sxs-lookup"><span data-stu-id="bcdc8-400">Reading Push</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="bcdc8-401">浏览器正在读取以前收到的本地数据。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-401">The browser is reading the local data previously received.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="bcdc8-402">显示启动器和相关性</span><span class="sxs-lookup"><span data-stu-id="bcdc8-402">Display initiators and dependencies</span></span>  

<span data-ttu-id="bcdc8-403">若要显示请求的发起程序和依赖关系，请 `Shift` 在请求表中保留并悬停请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-403">To display the initiators and dependencies of a request, hold `Shift`and hover on the request in the Requests table.</span></span>  <span data-ttu-id="bcdc8-404">DevTools 颜色：启动器显示为绿色，相关性显示为红色。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-404">DevTools colors: initiators are shown in green and dependencies are shown in red.</span></span>  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="显示请求的发起人和相关性" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   <span data-ttu-id="bcdc8-406">显示请求的发起人和相关性</span><span class="sxs-lookup"><span data-stu-id="bcdc8-406">Display the initiators and dependencies of a request</span></span>  
:::image-end:::  

<span data-ttu-id="bcdc8-407">当按时间顺序对请求表进行排序时，如果将鼠标悬停在一行上，它前面的一行将显示绿色请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-407">When the Requests table is ordered chronologically, if you hover on a line, the line preceding it displays a green request.</span></span>  <span data-ttu-id="bcdc8-408">绿色请求是依赖方的发起者。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-408">The green request is the initiator of the dependency.</span></span>  <span data-ttu-id="bcdc8-409">如果行上显示了另一个绿色请求，则该请求就是发起方的发起方。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-409">If another green request is displayed on the line before that, that higher request is the initiator of the initiator.</span></span>  <span data-ttu-id="bcdc8-410">以此类推。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-410">And so on.</span></span>  

### <span data-ttu-id="bcdc8-411">显示加载事件</span><span class="sxs-lookup"><span data-stu-id="bcdc8-411">Display load events</span></span>  

<span data-ttu-id="bcdc8-412">DevTools 显示 `DOMContentLoaded` `load` **网络** 面板上多个位置的和事件的计时。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-412">DevTools displays the timing of the `DOMContentLoaded` and `load` events in multiple places on the **Network** panel.</span></span>  <span data-ttu-id="bcdc8-413">`DOMContentLoaded`事件颜色为蓝色， `load` 事件为红色。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-413">The `DOMContentLoaded` event is colored blue, and the `load` event is red.</span></span>  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="DOMContentLoaded 和加载事件在网络面板上的位置" lightbox="../media/network-network-requests-load-events.msft.png":::
   <span data-ttu-id="bcdc8-415">" `DOMContentLoaded` `load` **网络** " 面板上的 "和" 事件的位置</span><span class="sxs-lookup"><span data-stu-id="bcdc8-415">The locations of the `DOMContentLoaded` and `load` events on the **Network** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-416">显示请求总数</span><span class="sxs-lookup"><span data-stu-id="bcdc8-416">Display the total number of requests</span></span>  

<span data-ttu-id="bcdc8-417">请求总数将列在 " **摘要** " 窗格中的 " **网络** " 面板底部。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-417">The total number of requests is listed in the **Summary** pane, at the bottom of the **Network** panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="bcdc8-418">此号码仅跟踪自 DevTools 打开以来已记录的请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-418">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="bcdc8-419">如果在 DevTools 打开之前发生了其他请求，则不会对这些请求进行计数。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-419">If other requests occurred before DevTools was opened, those requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="自 DevTools 打开以来的请求总数" lightbox="../media/network-network-total-requests.msft.png":::
   <span data-ttu-id="bcdc8-421">自 DevTools 打开以来的请求总数</span><span class="sxs-lookup"><span data-stu-id="bcdc8-421">The total number of requests since DevTools were opened</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-422">显示下载总大小</span><span class="sxs-lookup"><span data-stu-id="bcdc8-422">Display the total download size</span></span>  

<span data-ttu-id="bcdc8-423">请求的总下载大小列在 " **摘要** " 窗格中的 " **网络** " 面板底部。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-423">The total download size of requests is listed in the **Summary** pane, at the bottom of the **Network** panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="bcdc8-424">此号码仅跟踪自 DevTools 打开以来已记录的请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-424">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="bcdc8-425">如果在 DevTools 打开之前发生了其他请求，则不会对以前的请求进行计数。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-425">If other requests occurred before DevTools was opened, the previous requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="请求的总下载大小" lightbox="../media/network-network-total-download-size.msft.png":::
   <span data-ttu-id="bcdc8-427">请求的总下载大小</span><span class="sxs-lookup"><span data-stu-id="bcdc8-427">The total download size of requests</span></span>  
:::image-end:::  

<span data-ttu-id="bcdc8-428">若要验证浏览器 uncompresses 每个项目后资源的大小，请导航到 ["显示资源的未压缩大小"](#display-the-uncompressed-size-of-a-resource)。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-428">To verify how large resources are after the browser uncompresses each item, navigate to [display the uncompressed size of a resource](#display-the-uncompressed-size-of-a-resource).</span></span>  

### <span data-ttu-id="bcdc8-429">显示导致请求的堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="bcdc8-429">Display the stack trace that caused a request</span></span>  

<span data-ttu-id="bcdc8-430">在 JavaScript 语句请求资源后，将鼠标悬停在 " **发起方** " 列上，以显示对请求的最后一个堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-430">After a JavaScript statement requests a resource, hover on the **Initiator** column to display the stack trace leading up to the request.</span></span>  

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
   <span data-ttu-id="bcdc8-432">堆栈跟踪导致资源请求</span><span class="sxs-lookup"><span data-stu-id="bcdc8-432">The stack trace leading up to a resource request</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-433">显示资源的未压缩大小</span><span class="sxs-lookup"><span data-stu-id="bcdc8-433">Display the uncompressed size of a resource</span></span>  

<span data-ttu-id="bcdc8-434">打开 " **使用大请求行** " 复选框，然后查看 " **大小** " 列的最小值。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-434">Turn on the **Use large request rows** checkbox and then review the bottom value of the **Size** column.</span></span>  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="未压缩资源的示例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   <span data-ttu-id="bcdc8-436">已解压缩资源的示例 (`jquery-3.3.1.min.js` 通过网络发送的文件的压缩大小是 `29.9 KB` ，而未压缩的大小为 `84.9 KB` \ ) </span><span class="sxs-lookup"><span data-stu-id="bcdc8-436">An example of uncompressed resources  \(The compressed size of the `jquery-3.3.1.min.js` file that was sent over the network was `29.9 KB`, whereas the uncompressed size was `84.9 KB`\)</span></span>  
:::image-end:::  

## <span data-ttu-id="bcdc8-437">导出请求数据</span><span class="sxs-lookup"><span data-stu-id="bcdc8-437">Export requests data</span></span>  

### <span data-ttu-id="bcdc8-438">将所有网络请求保存到 HAR 文件</span><span class="sxs-lookup"><span data-stu-id="bcdc8-438">Save all network requests to a HAR file</span></span>  

<span data-ttu-id="bcdc8-439">若要将所有网络请求保存到 HAR 文件，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-439">To save all network requests to a HAR file, complete the following steps.</span></span>  

1.  <span data-ttu-id="bcdc8-440">将鼠标悬停在请求表中的任何请求并打开上下文菜单 \ (右键单击 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-440">Hover on any request in the Requests table and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="bcdc8-441">选择 " **另存为 HAR 和内容**"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-441">Choose **Save as HAR with Content**.</span></span>  <span data-ttu-id="bcdc8-442">DevTools 将打开 DevTools 后出现的所有请求保存到 HAR 文件。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-442">DevTools saves all requests that have occurred since you opened DevTools to the HAR file.</span></span>  <span data-ttu-id="bcdc8-443">您无法筛选请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-443">You are not able to filter requests.</span></span>  <span data-ttu-id="bcdc8-444">您也无法保存单个请求。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-444">You are also not able to save a single request.</span></span>  

<span data-ttu-id="bcdc8-445">保存 HAR 文件后，可将其导入 DevTools 进行分析。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-445">Once you save a HAR file, you may import it back into DevTools for analysis.</span></span>  <span data-ttu-id="bcdc8-446">只需将 HAR 文件拖放到 "请求" 表中。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-446">Just drag-and-drop the HAR file into the Requests table.</span></span>  
<!--For more information, navigate to also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="选择 "另存为 HAR 和内容"" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   <span data-ttu-id="bcdc8-448">选择 "**另存为 HAR 和内容**"</span><span class="sxs-lookup"><span data-stu-id="bcdc8-448">Choose **Save as HAR with Content**</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-449">将一个或多个请求复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="bcdc8-449">Copy one or more requests to the clipboard</span></span>  

<span data-ttu-id="bcdc8-450">在 "请求" 表的 " **名称** " 列下，将鼠标悬停在请求上，打开上下文菜单 \ (右键单击 "\ ) "，悬停在 " **复制**"，然后选择下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-450">Under the **Name** column of the Requests table, hover on a request, open the contextual menu \(right-click\), hover on **Copy**, and choose one of the following options.</span></span>  

| <span data-ttu-id="bcdc8-451">名称</span><span class="sxs-lookup"><span data-stu-id="bcdc8-451">Name</span></span> | <span data-ttu-id="bcdc8-452">详细信息</span><span class="sxs-lookup"><span data-stu-id="bcdc8-452">Details</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="bcdc8-453">复制链接地址</span><span class="sxs-lookup"><span data-stu-id="bcdc8-453">Copy Link Address</span></span>** | <span data-ttu-id="bcdc8-454">将请求的 URL 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-454">Copy the URL of the request to the clipboard.</span></span> |  
| **<span data-ttu-id="bcdc8-455">复制答复</span><span class="sxs-lookup"><span data-stu-id="bcdc8-455">Copy Response</span></span>** | <span data-ttu-id="bcdc8-456">将响应正文复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-456">Copy the response body to the clipboard.</span></span> |  
| **<span data-ttu-id="bcdc8-457">复制为提取</span><span class="sxs-lookup"><span data-stu-id="bcdc8-457">Copy as Fetch</span></span>** | &nbsp; |  
| **<span data-ttu-id="bcdc8-458">复制为卷曲</span><span class="sxs-lookup"><span data-stu-id="bcdc8-458">Copy as cURL</span></span>** | <span data-ttu-id="bcdc8-459">将请求复制为卷曲命令。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-459">Copy the request as a cURL command.</span></span> |  
| **<span data-ttu-id="bcdc8-460">全部复制为提取</span><span class="sxs-lookup"><span data-stu-id="bcdc8-460">Copy All as Fetch</span></span>** | &nbsp; |  
| **<span data-ttu-id="bcdc8-461">复制全部为卷曲</span><span class="sxs-lookup"><span data-stu-id="bcdc8-461">Copy All as cURL</span></span>** | <span data-ttu-id="bcdc8-462">将所有请求复制为一个卷曲命令链。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-462">Copy all requests as a chain of cURL commands.</span></span> |  
| **<span data-ttu-id="bcdc8-463">全部复制到 HAR</span><span class="sxs-lookup"><span data-stu-id="bcdc8-463">Copy All as HAR</span></span>** | <span data-ttu-id="bcdc8-464">将所有请求复制到 HAR 数据。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-464">Copy all requests as HAR data.</span></span> |  

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

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="选择 "复制答复"" lightbox="../media/network-network-requests-copy-response.msft.png":::
   <span data-ttu-id="bcdc8-466">选择 "**复制答复**"</span><span class="sxs-lookup"><span data-stu-id="bcdc8-466">Choose **Copy Response**</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-467">将带格式的响应 JSON 复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="bcdc8-467">Copy formatted response JSON to the clipboard</span></span>  

<span data-ttu-id="bcdc8-468">选择一个网络请求并导航到 " **页眉** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-468">Choose a network request and navigate to the **Headers** pane.</span></span>  <span data-ttu-id="bcdc8-469">若要复制响应的 JSON 值，请导航到 " **请求负载**"，将鼠标悬停在 JSON 响应内容上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **复制值**"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-469">To copy the JSON value of a response, navigate to **Request payload**, hover on the JSON response content, open the contextual menu \(right-click\), and choose **Copy Value**.</span></span>  

:::row:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-copy-property-value.msft.png" alt-text="在上下文菜单中复制值" lightbox="../media/network-header-copy-property-value.msft.png":::
          <span data-ttu-id="bcdc8-471">在上下文菜单中**复制值**</span><span class="sxs-lookup"><span data-stu-id="bcdc8-471">**Copy Value** in contextual menu</span></span>  
        :::image-end:::  
   :::column-end:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-paste-property-value.msft.png" alt-text="带格式的响应 JSON 的 Visual Studio 代码" lightbox="../media/network-header-paste-property-value.msft.png":::
          <span data-ttu-id="bcdc8-473">在 Visual Studio 代码中粘贴带格式的响应 JSON</span><span class="sxs-lookup"><span data-stu-id="bcdc8-473">Pasting formatted response JSON in Visual Studio Code</span></span>  
        :::image-end:::  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="bcdc8-474">将网络请求中的属性值复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="bcdc8-474">Copy property values from network requests to your clipboard</span></span>  

<span data-ttu-id="bcdc8-475">若要将网络请求中的属性值复制到剪贴板，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-475">To copy property values from network requests to your clipboard, complete the following actions.</span></span>  

1.  <span data-ttu-id="bcdc8-476">打开 " **页眉** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-476">Open the **Headers** pane.</span></span>  
1.  <span data-ttu-id="bcdc8-477">打开以下页眉部分之一。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-477">Open one of the following header sections.</span></span>  
    *   <span data-ttu-id="bcdc8-478">请求负载 \ (JSON \ ) </span><span class="sxs-lookup"><span data-stu-id="bcdc8-478">Request payload \(JSON\)</span></span>  
    *   <span data-ttu-id="bcdc8-479">表单数据</span><span class="sxs-lookup"><span data-stu-id="bcdc8-479">Form Data</span></span>  
    *   <span data-ttu-id="bcdc8-480">查询字符串参数</span><span class="sxs-lookup"><span data-stu-id="bcdc8-480">Query String Parameters</span></span>  
    *   <span data-ttu-id="bcdc8-481">请求标头</span><span class="sxs-lookup"><span data-stu-id="bcdc8-481">Request Headers</span></span>  
    *   <span data-ttu-id="bcdc8-482">响应标题</span><span class="sxs-lookup"><span data-stu-id="bcdc8-482">Response Headers</span></span>  
1.  <span data-ttu-id="bcdc8-483">打开上下文菜单 \ (右键单击 \ ) > " **复制值**"。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-483">Open the contextual menu \(right-click\) > **Copy value**.</span></span>  <span data-ttu-id="bcdc8-484">现在，你可以将该值粘贴到任何编辑器中以进行查看。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-484">You can now paste the value into any editor to review it.</span></span>  
    
## <span data-ttu-id="bcdc8-485">更改网络面板的布局</span><span class="sxs-lookup"><span data-stu-id="bcdc8-485">Change the layout of the Network panel</span></span>  

<span data-ttu-id="bcdc8-486">你可以展开或折叠 " **网络** 面板" UI 的各个部分以重点介绍重要信息。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-486">You may expand or collapse sections of the **Network** panel UI to focus important information.</span></span>  

### <span data-ttu-id="bcdc8-487">隐藏 "筛选器" 窗格</span><span class="sxs-lookup"><span data-stu-id="bcdc8-487">Hide the Filters pane</span></span>  

<span data-ttu-id="bcdc8-488">默认情况下，DevTools 显示 " **筛选器** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-488">By default, DevTools show the **Filters** pane.</span></span>  
<span data-ttu-id="bcdc8-489">选择 " **筛选** \ (![ 筛选 ][ImageFilterIcon] \ ) " 将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-489">Choose **Filter** \(![Filter][ImageFilterIcon]\) to hide it.</span></span>  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text=""隐藏筛选器" 按钮" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   <span data-ttu-id="bcdc8-491">"隐藏筛选器" 按钮</span><span class="sxs-lookup"><span data-stu-id="bcdc8-491">The Hide Filters button</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-492">使用大型请求行</span><span class="sxs-lookup"><span data-stu-id="bcdc8-492">Use large request rows</span></span>  

<span data-ttu-id="bcdc8-493">如果需要在网络请求表中有更多的空格，请使用较大的行。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-493">Use large rows when you want more whitespace in your network requests table.</span></span>  <span data-ttu-id="bcdc8-494">在使用较大的行时，某些列还提供了一些更多的信息。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-494">Some columns also provide a little more information when using large rows.</span></span>  <span data-ttu-id="bcdc8-495">例如， **Size** 列的底部值是请求的未压缩大小。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-495">For example, the bottom value of the **Size** column is the uncompressed size of a request.</span></span>  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text="请求窗格中的大型请求行的示例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   <span data-ttu-id="bcdc8-497">**请求**窗格中的大型请求行的示例</span><span class="sxs-lookup"><span data-stu-id="bcdc8-497">An example of large request rows in the **Requests** pane</span></span>  
:::image-end:::  

<span data-ttu-id="bcdc8-498">若要启用较大的行，请打开 " **使用大型请求行** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-498">To enable large rows, turn on the **Use large request rows** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text=""使用大请求行" 复选框" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   <span data-ttu-id="bcdc8-500">" **使用大请求行** " 复选框</span><span class="sxs-lookup"><span data-stu-id="bcdc8-500">The **Use large request rows** checkbox</span></span>  
:::image-end:::  

### <span data-ttu-id="bcdc8-501">隐藏 "概述" 窗格</span><span class="sxs-lookup"><span data-stu-id="bcdc8-501">Hide the Overview pane</span></span>  

<span data-ttu-id="bcdc8-502">默认情况下，DevTools 显示 " **概述** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-502">By default, DevTools displays the **Overview** pane.</span></span>  <span data-ttu-id="bcdc8-503">若要隐藏它，请关闭 " **显示概述** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-503">To hide it, turn off the **Show Overview** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text=""显示概述" 复选框" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   <span data-ttu-id="bcdc8-505">" **显示概述** " 复选框</span><span class="sxs-lookup"><span data-stu-id="bcdc8-505">The **Show Overview** checkbox</span></span>  
:::image-end:::  

## <span data-ttu-id="bcdc8-506">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="bcdc8-506">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCaptureScreenshotsIcon]: ../media/capture-screenshots-icon.msft.png  
[ImageClearIcon]: ../media/clear-requests-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageHideIcon]: ../media/hide-overview-icon.msft.png  
[ImageLargeResourceRowsIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageRecordOnIcon]: ../media/record-on-icon.msft.png  

<!-- links -->  

[DevtoolsProgressiveWebApps]: ../progressive-web-apps.md "调试渐进式 Web 应用 |Microsoft 文档"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions | Microsoft Docs"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "数据 Url |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "代理服务器-维基百科"  

> [!NOTE]
> <span data-ttu-id="bcdc8-510">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-510">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="bcdc8-511">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-511">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="bcdc8-513">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="bcdc8-513">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
