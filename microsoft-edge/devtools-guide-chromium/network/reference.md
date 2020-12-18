---
description: Microsoft Edge DevTools 网络面板功能的综合参考。
title: 网络分析参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: c600197ffa0e415fe42aecc704a523d1b23f8260
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230752"
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

# <span data-ttu-id="efd2f-104">网络分析参考</span><span class="sxs-lookup"><span data-stu-id="efd2f-104">Network Analysis reference</span></span>  

<span data-ttu-id="efd2f-105">在此 Microsoft Edge DevTools 网络分析功能的全面参考中，发现分析页面加载方式的新增方法。</span><span class="sxs-lookup"><span data-stu-id="efd2f-105">Discover new ways to analyze how your page loads in this comprehensive reference of Microsoft Edge DevTools network analysis features.</span></span>  

## <span data-ttu-id="efd2f-106">记录网络请求</span><span class="sxs-lookup"><span data-stu-id="efd2f-106">Record network requests</span></span>  

<span data-ttu-id="efd2f-107">默认情况下，DevTools 在网络面板中记录所有网络\*\*\*\* 请求，只要 DevTools 打开。</span><span class="sxs-lookup"><span data-stu-id="efd2f-107">By default, DevTools record all network requests in the **Network** panel, so long as DevTools is open.</span></span>  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="网络面板" lightbox="../media/network-network-panel.msft.png":::
   <span data-ttu-id="efd2f-109">网络**面板**</span><span class="sxs-lookup"><span data-stu-id="efd2f-109">The **Network** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-110">停止记录网络请求</span><span class="sxs-lookup"><span data-stu-id="efd2f-110">Stop recording network requests</span></span>  

<span data-ttu-id="efd2f-111">若要停止录制请求，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="efd2f-111">To stop recording requests, complete the following steps.</span></span>  

1.  <span data-ttu-id="efd2f-112">在" **网络** "面板上，选择"停止 **录制网络** 日志\ (![ 停止录制网络日志 ][ImageRecordOnIcon] \) 。</span><span class="sxs-lookup"><span data-stu-id="efd2f-112">On the **Network** panel, choose **Stop recording network log** \(![Stop recording network log][ImageRecordOnIcon]\).</span></span>  <span data-ttu-id="efd2f-113">它将变为灰色，以指示 DevTools 不再录制请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-113">It turns grey to indicate that DevTools is no longer recording requests.</span></span>  
1.  <span data-ttu-id="efd2f-114">在网络 (焦点时，选择 `Control` + `E` \ (Windows、Linux\) 或 `Command` + `E` \ (macOS\) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="efd2f-114">Select `Control`+`E` \(Windows, Linux\) or `Command`+`E` \(macOS\) while the **Network** panel is in focus.</span></span>  

### <span data-ttu-id="efd2f-115">清除请求</span><span class="sxs-lookup"><span data-stu-id="efd2f-115">Clear requests</span></span>  

<span data-ttu-id="efd2f-116">在 **"网络** (选择"清除) "以清除"请求" ![ ][ImageClearIcon] 表中的所有请求。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="efd2f-116">Choose **Clear** \(![Clear][ImageClearIcon]\) on the **Network** panel to clear all requests from the Requests table.</span></span>  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text=""清除"按钮" lightbox="../media/network-network-clear-button.msft.png":::
   <span data-ttu-id="efd2f-118">" **清除"** 按钮</span><span class="sxs-lookup"><span data-stu-id="efd2f-118">The **Clear** button</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-119">跨页面加载保存请求</span><span class="sxs-lookup"><span data-stu-id="efd2f-119">Save requests across page loads</span></span>  

<span data-ttu-id="efd2f-120">若要跨页面加载保存请求，在"网络\*\*\*\*"面板上，打开"保留**日志"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="efd2f-120">To save requests across page loads, on the **Network** panel, turn on the **Preserve log** checkbox.</span></span>  <span data-ttu-id="efd2f-121">DevTools 保存所有请求，直到禁用 **保留日志**。</span><span class="sxs-lookup"><span data-stu-id="efd2f-121">DevTools saves all requests until you disable **Preserve log**.</span></span>  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text=""保留日志"复选框" lightbox="../media/network-network-preserve-log.msft.png":::
   <span data-ttu-id="efd2f-123">" **保留日志"** 复选框</span><span class="sxs-lookup"><span data-stu-id="efd2f-123">The **Preserve Log** checkbox</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-124">在页面加载期间捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="efd2f-124">Capture screenshots during page load</span></span>  

<span data-ttu-id="efd2f-125">捕获屏幕截图，以分析在等待页面加载时为用户显示的内容。</span><span class="sxs-lookup"><span data-stu-id="efd2f-125">Capture screenshots to analyze what displays for users while waiting for your page to load.</span></span>  

<span data-ttu-id="efd2f-126">若要启用屏幕截图，请选择 **"网络设置**"，在"\*\*\*\* 网络"面板上，打开"捕获屏幕截图 **"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="efd2f-126">To enable screenshots, choose **Network settings**, and on the **Network** panel, turn on the **Capture screenshots** checkbox.</span></span>  

<span data-ttu-id="efd2f-127">在网络面板聚焦时\*\*\*\* 刷新页面以捕获屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="efd2f-127">Refresh the page while the **Network** panel is in focus to capture screenshots.</span></span>  

<span data-ttu-id="efd2f-128">捕获屏幕截图后，可以按照以下方式与其交互。</span><span class="sxs-lookup"><span data-stu-id="efd2f-128">After capturing a screenshot, you interact with it in the following ways.</span></span>  

*   <span data-ttu-id="efd2f-129">将鼠标悬停在屏幕截图上可显示捕获该屏幕截图的点。</span><span class="sxs-lookup"><span data-stu-id="efd2f-129">Hover on a screenshot to display the point at which that screenshot was captured.</span></span>  <span data-ttu-id="efd2f-130">在"概述"窗格中显示一条 **黄色** 线条。</span><span class="sxs-lookup"><span data-stu-id="efd2f-130">A yellow line is displayed on the **Overview** pane.</span></span>  
*   <span data-ttu-id="efd2f-131">选择屏幕的缩略图以筛选出捕获屏幕截图后发生的任何请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-131">Choose the thumbnail of a screen to filter out any requests that occurred after the screenshot was captured.</span></span>  
*   <span data-ttu-id="efd2f-132">双击缩略图可放大它。</span><span class="sxs-lookup"><span data-stu-id="efd2f-132">Double-click a thumbnail to zoom into it.</span></span>  

:::image type="complex" source="../media/network-network-screenshot-hover.msft.png" alt-text="将鼠标悬停在屏幕截图上" lightbox="../media/network-network-screenshot-hover.msft.png":::
   <span data-ttu-id="efd2f-134">将鼠标悬停在屏幕截图上</span><span class="sxs-lookup"><span data-stu-id="efd2f-134">Hover on a screenshot</span></span>  
:::image-end:::  

<!--  ### Replay XHR request  -->

<!--  To replay an XHR request, hover on the request in the Requests table, open the contextual menu \(right-click\), and choose **Replay XHR**.  -->

<!--  
:::image type="complex" source="../media/network-replay-xhr.msft.png" alt-text="Choose Replay XHR" lightbox="../media/network-replay-xhr.msft.png":::
   Choose Replay XHR  
:::image-end:::  
-->  

## <span data-ttu-id="efd2f-135">更改加载行为</span><span class="sxs-lookup"><span data-stu-id="efd2f-135">Change loading behavior</span></span>  

### <span data-ttu-id="efd2f-136">通过禁用浏览器缓存模拟第一次访问者</span><span class="sxs-lookup"><span data-stu-id="efd2f-136">Emulate a first-time visitor by disabling the browser cache</span></span>  

<span data-ttu-id="efd2f-137">若要模拟首次用户访问网站时的体验，请打开"禁用 **缓存"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="efd2f-137">To emulate how a first-time user experiences your site, turn on the **Disable cache** checkbox.</span></span>  <span data-ttu-id="efd2f-138">DevTools 禁用浏览器缓存。</span><span class="sxs-lookup"><span data-stu-id="efd2f-138">DevTools disables the browser cache.</span></span>  <span data-ttu-id="efd2f-139">此功能可以更准确地模拟第一次用户体验，因为请求在重复访问时从浏览器缓存提供。</span><span class="sxs-lookup"><span data-stu-id="efd2f-139">This feature more accurately emulates a first-time user's experience, because requests are served from the browser cache on repeat visits.</span></span>  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text=""禁用缓存"复选框" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   <span data-ttu-id="efd2f-141">" **禁用缓存"** 复选框</span><span class="sxs-lookup"><span data-stu-id="efd2f-141">The **Disable Cache** checkbox</span></span>  
:::image-end:::  

#### <span data-ttu-id="efd2f-142">从"网络条件"箱禁用浏览器缓存</span><span class="sxs-lookup"><span data-stu-id="efd2f-142">Disable the browser cache from the Network Conditions drawer</span></span>  

<span data-ttu-id="efd2f-143">如果要在其他 DevTools 面板中操作时禁用缓存，请使用"网络条件"箱。</span><span class="sxs-lookup"><span data-stu-id="efd2f-143">If you want to disable the cache while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="efd2f-144">打开 **"网络条件"** 箱。</span><span class="sxs-lookup"><span data-stu-id="efd2f-144">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="efd2f-145">打开\ (或关闭\) **禁用缓存复选框** 。</span><span class="sxs-lookup"><span data-stu-id="efd2f-145">Turn on \(or off\) the **Disable cache** checkbox.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="efd2f-146">手动清除浏览器缓存</span><span class="sxs-lookup"><span data-stu-id="efd2f-146">Manually clear the browser cache</span></span>  

<span data-ttu-id="efd2f-147">若要随时手动清除浏览器缓存，请打开上下文菜单 \ (右键单击\) 请求表中的任意位置，然后选择 **"清除浏览器缓存"。**</span><span class="sxs-lookup"><span data-stu-id="efd2f-147">To manually clear the browser cache at any time, open the contextual menu \(right-click\) anywhere in the Requests table and choose **Clear Browser Cache**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="选择"清除浏览器缓存"" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   <span data-ttu-id="efd2f-149">选择 **"清除浏览器缓存"**</span><span class="sxs-lookup"><span data-stu-id="efd2f-149">Choose **Clear Browser Cache**</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-150">脱机模拟</span><span class="sxs-lookup"><span data-stu-id="efd2f-150">Emulate offline</span></span>  

<span data-ttu-id="efd2f-151">名为"渐进 Web 应用"[][DevtoolsProgressiveWebApps]的新 Web 应用类在服务工作者的帮助下脱机**工作**。</span><span class="sxs-lookup"><span data-stu-id="efd2f-151">A new class of web apps, named [Progressive Web Apps][DevtoolsProgressiveWebApps], functions offline with the help of **service workers**.</span></span>  <span data-ttu-id="efd2f-152">你可能会发现，在生成此类应用时，快速模拟没有数据连接的设备会很有用。</span><span class="sxs-lookup"><span data-stu-id="efd2f-152">You may find it useful to quickly simulate a device that has no data connection when you are building this type of app.</span></span>  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

<span data-ttu-id="efd2f-153">选择 **"联机**"下拉菜单，在 **"预设**"下搜索，然后选择\*\*\*\*"脱机"以模拟脱机网络体验。</span><span class="sxs-lookup"><span data-stu-id="efd2f-153">Choose the **Online** dropdown menu, search under **Presets**, and choose **Offline** to simulate an offline network experience.</span></span>  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text=""脱机"下拉菜单" lightbox="../media/network-network-offline-dropdown.msft.png":::
   <span data-ttu-id="efd2f-155">" **脱机** "下拉菜单</span><span class="sxs-lookup"><span data-stu-id="efd2f-155">The **Offline** dropdown menu</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-156">模拟慢速网络连接</span><span class="sxs-lookup"><span data-stu-id="efd2f-156">Emulate slow network connections</span></span>  

<span data-ttu-id="efd2f-157">从"联机"下拉菜单中模拟慢速 3G、快速 3G 和其他连接速度。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="efd2f-157">Emulate Slow 3G, Fast 3G, and other connection speeds from the **Online** dropdown menu.</span></span>  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text=""限制"下拉菜单" lightbox="../media/network-network-throttling-menu.msft.png":::
   <span data-ttu-id="efd2f-159">" **限制"** 下拉菜单</span><span class="sxs-lookup"><span data-stu-id="efd2f-159">The **Throttling** dropdown menu</span></span>  
:::image-end:::  

<span data-ttu-id="efd2f-160">你可以选择不同的预设，如慢速 3G 或快速 3G。</span><span class="sxs-lookup"><span data-stu-id="efd2f-160">You may choose from different presets, such as Slow 3G or Fast 3G.</span></span>  <span data-ttu-id="efd2f-161">若要添加自己的自定义预设，请打开限制菜单，然后选择"**自定义**  >  **添加"。**</span><span class="sxs-lookup"><span data-stu-id="efd2f-161">To add your own custom presets, open the Throttling menu, and choose **Custom** > **Add**.</span></span>  

<span data-ttu-id="efd2f-162">DevTools 在"网络"选项卡旁边\*\*\*\* 显示一个警告图标，提醒你已启用限制。</span><span class="sxs-lookup"><span data-stu-id="efd2f-162">DevTools displays a warning icon next to the **Network** tab to remind you that throttling is enabled.</span></span>  

#### <span data-ttu-id="efd2f-163">模拟来自"网络条件"箱的慢速网络连接</span><span class="sxs-lookup"><span data-stu-id="efd2f-163">Emulate slow network connections from the Network Conditions drawer</span></span>  

<span data-ttu-id="efd2f-164">如果要在其他 DevTools 面板中工作时限制网络连接，请使用"网络条件"箱。</span><span class="sxs-lookup"><span data-stu-id="efd2f-164">If you want to throttle the network connection while working in other DevTools panels, use the Network Conditions drawer.</span></span>  

1.  <span data-ttu-id="efd2f-165">打开 **"网络条件"** 箱。</span><span class="sxs-lookup"><span data-stu-id="efd2f-165">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="efd2f-166">从限制菜单中 **选择连接** 速度。</span><span class="sxs-lookup"><span data-stu-id="efd2f-166">Choose your connection speed from the **Throttling** menu.</span></span>  

<!--todo: add network condition section when available -->  

### <span data-ttu-id="efd2f-167">手动清除浏览器 Cookie</span><span class="sxs-lookup"><span data-stu-id="efd2f-167">Manually clear browser cookies</span></span>  

<span data-ttu-id="efd2f-168">若要随时手动清除浏览器 Cookie，请将鼠标悬停在"请求"表中的任意位置，打开上下文菜单 \ (右键单击\) ，然后选择"清除浏览器**Cookie"。**</span><span class="sxs-lookup"><span data-stu-id="efd2f-168">To manually clear browser cookies at any time, hover anywhere in the Requests table, open the contextual menu \(right-click\), and choose **Clear Browser Cookies**.</span></span>  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="选择"清除浏览器 Cookie"" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   <span data-ttu-id="efd2f-170">选择 **"清除浏览器 Cookie"**</span><span class="sxs-lookup"><span data-stu-id="efd2f-170">Choose **Clear Browser Cookies**</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-171">覆盖用户代理</span><span class="sxs-lookup"><span data-stu-id="efd2f-171">Override the user agent</span></span>  

<span data-ttu-id="efd2f-172">若要手动覆盖用户代理，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="efd2f-172">To manually override the user agent, use the following steps.</span></span>  

1.  <span data-ttu-id="efd2f-173">打开 **"网络条件"** 箱。</span><span class="sxs-lookup"><span data-stu-id="efd2f-173">Open the **Network Conditions** drawer.</span></span>  
1.  <span data-ttu-id="efd2f-174">关闭"自动 **选择"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="efd2f-174">Turn off the **Select automatically** checkbox.</span></span>  
1.  <span data-ttu-id="efd2f-175">从菜单中选择用户代理选项，或在文本框中输入自定义选项。</span><span class="sxs-lookup"><span data-stu-id="efd2f-175">Choose a user agent option from the menu, or enter a custom one in the text box.</span></span>  

<!--todo: add network condition section when available -->  

## <span data-ttu-id="efd2f-176">筛选请求</span><span class="sxs-lookup"><span data-stu-id="efd2f-176">Filter requests</span></span>  

### <span data-ttu-id="efd2f-177">按属性筛选请求</span><span class="sxs-lookup"><span data-stu-id="efd2f-177">Filter requests by properties</span></span>  

<span data-ttu-id="efd2f-178">使用 **"** 筛选器"文本框按属性（如请求的域或大小）筛选请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-178">Use the **Filter** text box to filter requests by properties, such as the domain or size of the request.</span></span>  

<span data-ttu-id="efd2f-179">如果未显示文本框，"筛选器 **"窗格可能** 处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="efd2f-179">If the text box is not displayed, the **Filters** pane is probably hidden.</span></span>  
<span data-ttu-id="efd2f-180">有关详细信息，请导航到" [隐藏筛选器"窗格](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="efd2f-180">For more information, navigate to [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text=""筛选器"文本框" lightbox="../media/network-network-filters-textbox.msft.png":::
   <span data-ttu-id="efd2f-182">" **筛选器** "文本框</span><span class="sxs-lookup"><span data-stu-id="efd2f-182">The **Filter** text box</span></span>  
:::image-end:::  

<span data-ttu-id="efd2f-183">通过用空格分隔每个属性，可以同时使用多个属性。</span><span class="sxs-lookup"><span data-stu-id="efd2f-183">You may use multiple properties simultaneously by separating each property with a space.</span></span>  <span data-ttu-id="efd2f-184">例如， `mime-type:image/png larger-than:1K` 显示大于 1 KB 的所有 PNG。</span><span class="sxs-lookup"><span data-stu-id="efd2f-184">For example, `mime-type:image/png larger-than:1K` displays all PNGs that are larger than 1 kilobyte.</span></span>  <span data-ttu-id="efd2f-185">多属性筛选器等效于 `AND` 操作。</span><span class="sxs-lookup"><span data-stu-id="efd2f-185">The multi-property filters are equivalent to `AND` operations.</span></span>  `OR` <span data-ttu-id="efd2f-186">操作当前不受支持。</span><span class="sxs-lookup"><span data-stu-id="efd2f-186">operations are currently not supported.</span></span>  

<span data-ttu-id="efd2f-187">受支持的属性的完整列表。</span><span class="sxs-lookup"><span data-stu-id="efd2f-187">The complete list of supported properties.</span></span>  

| <span data-ttu-id="efd2f-188">属性</span><span class="sxs-lookup"><span data-stu-id="efd2f-188">Property</span></span> | <span data-ttu-id="efd2f-189">详细信息</span><span class="sxs-lookup"><span data-stu-id="efd2f-189">Details</span></span> |  
|:--- | :--- |  
| `domain` | <span data-ttu-id="efd2f-190">仅显示来自指定域的资源。</span><span class="sxs-lookup"><span data-stu-id="efd2f-190">Only display resources from the specified domain.</span></span>  <span data-ttu-id="efd2f-191">可以使用通配符 \ (`*` \) 包含多个域。</span><span class="sxs-lookup"><span data-stu-id="efd2f-191">You may use a wildcard character \(`*`\) to include multiple domains.</span></span>  <span data-ttu-id="efd2f-192">例如， `*.com` 显示以 . `.com`</span><span class="sxs-lookup"><span data-stu-id="efd2f-192">For example, `*.com` displays resources from all domain names ending in `.com`.</span></span>  <span data-ttu-id="efd2f-193">DevTools 使用找到的所有域填充自动完成下拉菜单。</span><span class="sxs-lookup"><span data-stu-id="efd2f-193">DevTools populate the autocomplete dropdown menu with all of the domains that are found.</span></span> |  
| `has-response-header` | <span data-ttu-id="efd2f-194">显示包含指定 HTTP 响应标头的资源。</span><span class="sxs-lookup"><span data-stu-id="efd2f-194">Displays the resources that contain the specified HTTP response header.</span></span>  <span data-ttu-id="efd2f-195">DevTools 使用找到的所有响应标头填充自动完成下拉列表。</span><span class="sxs-lookup"><span data-stu-id="efd2f-195">DevTools populate the autocomplete dropdown with all of the response headers that are found.</span></span> |  
| `is` | <span data-ttu-id="efd2f-196">用于 `is:running` 查找 `WebSocket` 资源。</span><span class="sxs-lookup"><span data-stu-id="efd2f-196">Use `is:running` to find `WebSocket` resources.</span></span> |  
| `larger-than` | <span data-ttu-id="efd2f-197">以字节为单位显示大于指定大小的资源。</span><span class="sxs-lookup"><span data-stu-id="efd2f-197">Displays resources that are larger than the specified size, in bytes.</span></span>  <span data-ttu-id="efd2f-198">设置值 `1000` 等效于设置值 `1k` 。</span><span class="sxs-lookup"><span data-stu-id="efd2f-198">Setting a value of `1000` is equivalent to setting a value of `1k`.</span></span> |  
| `method` | <span data-ttu-id="efd2f-199">显示通过指定的 HTTP 方法类型检索的资源。</span><span class="sxs-lookup"><span data-stu-id="efd2f-199">Displays resources that were retrieved over a specified HTTP method type.</span></span>  <span data-ttu-id="efd2f-200">DevTools 使用找到的所有 HTTP 方法填充下拉列表。</span><span class="sxs-lookup"><span data-stu-id="efd2f-200">DevTools populate the dropdown with all of the HTTP methods  that are found.</span></span> |  
| `mime-type` | <span data-ttu-id="efd2f-201">显示指定 MIME 类型的资源。</span><span class="sxs-lookup"><span data-stu-id="efd2f-201">Displays resources of a specified MIME type.</span></span>  <span data-ttu-id="efd2f-202">DevTools 使用找到的所有 MIME 类型填充下拉列表。</span><span class="sxs-lookup"><span data-stu-id="efd2f-202">DevTools populate the dropdown with all MIME types  that are found.</span></span> |  
| `mixed-content` | <span data-ttu-id="efd2f-203">显示所有混合内容资源 \ (\) 或只显示当前显示的 `mixed-content:all` \ (`mixed-content:displayed` \) 。</span><span class="sxs-lookup"><span data-stu-id="efd2f-203">Show all mixed content resources \(`mixed-content:all`\) or just the ones that are currently displayed \(`mixed-content:displayed`\).</span></span> |  
| `scheme` | <span data-ttu-id="efd2f-204">显示通过未受保护的 HTTP \ (`scheme:http` \) 或受保护的 HTTPS \ (`scheme:https` \) 检索的资源。</span><span class="sxs-lookup"><span data-stu-id="efd2f-204">Displays resources retrieved over unprotected HTTP \(`scheme:http`\) or protected HTTPS \(`scheme:https`\).</span></span> |  
| `set-cookie-domain` | <span data-ttu-id="efd2f-205">显示具有与指定值匹配的属性的标头 `Set-Cookie` `Domain` 的资源。</span><span class="sxs-lookup"><span data-stu-id="efd2f-205">Displays resources that have a `Set-Cookie` header with a `Domain` attribute that matches the specified value.</span></span>  <span data-ttu-id="efd2f-206">DevTools 使用找到的所有 Cookie 域填充自动完成。</span><span class="sxs-lookup"><span data-stu-id="efd2f-206">DevTools populate the autocomplete with all of the cookie domains that are found.</span></span> |  
| `set-cookie-name` | <span data-ttu-id="efd2f-207">显示具有与指定 `Set-Cookie` 值匹配的名称的标题的资源。</span><span class="sxs-lookup"><span data-stu-id="efd2f-207">Displays resources that have a `Set-Cookie` header with a name that matches the specified value.</span></span>  <span data-ttu-id="efd2f-208">DevTools 使用找到的所有 Cookie 名称填充自动完成。</span><span class="sxs-lookup"><span data-stu-id="efd2f-208">DevTools populate the autocomplete with all of the cookie names that are found.</span></span> |  
| `set-cookie-value` | <span data-ttu-id="efd2f-209">显示标题具有与指定 `Set-Cookie` 值匹配的值的资源。</span><span class="sxs-lookup"><span data-stu-id="efd2f-209">Displays resources that have a `Set-Cookie` header with a value that matches the specified value.</span></span>  <span data-ttu-id="efd2f-210">DevTools 使用找到的所有 Cookie 值填充自动完成。</span><span class="sxs-lookup"><span data-stu-id="efd2f-210">DevTools populate the autocomplete with all of the cookie values that are found.</span></span> |  
| `status-code` | <span data-ttu-id="efd2f-211">显示与特定 HTTP 状态代码匹配的资源。</span><span class="sxs-lookup"><span data-stu-id="efd2f-211">Displays resources that match the specific HTTP status code.</span></span>  <span data-ttu-id="efd2f-212">DevTools 使用找到的所有状态代码填充自动完成下拉菜单。</span><span class="sxs-lookup"><span data-stu-id="efd2f-212">DevTools populates the autocomplete dropdown menu with all of the status codes that are found.</span></span> |  

### <span data-ttu-id="efd2f-213">按类型筛选请求</span><span class="sxs-lookup"><span data-stu-id="efd2f-213">Filter requests by type</span></span>  

<span data-ttu-id="efd2f-214">若要按请求类型筛选请求，请选择"网络"面板上的以下按钮 **之** 一。</span><span class="sxs-lookup"><span data-stu-id="efd2f-214">To filter requests by request type, choose the one of the following buttons on the **Network** panel.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-215">XHR</span><span class="sxs-lookup"><span data-stu-id="efd2f-215">XHR</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-216">JS</span><span class="sxs-lookup"><span data-stu-id="efd2f-216">JS</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-217">CSS</span><span class="sxs-lookup"><span data-stu-id="efd2f-217">CSS</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-218">Img</span><span class="sxs-lookup"><span data-stu-id="efd2f-218">Img</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-219">Media</span><span class="sxs-lookup"><span data-stu-id="efd2f-219">Media</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-220">字体</span><span class="sxs-lookup"><span data-stu-id="efd2f-220">Font</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-221">Doc</span><span class="sxs-lookup"><span data-stu-id="efd2f-221">Doc</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-222">WS</span><span class="sxs-lookup"><span data-stu-id="efd2f-222">WS</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-223">WebSocket。</span><span class="sxs-lookup"><span data-stu-id="efd2f-223">WebSocket.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-224">清单</span><span class="sxs-lookup"><span data-stu-id="efd2f-224">Manifest</span></span>**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-225">Other</span><span class="sxs-lookup"><span data-stu-id="efd2f-225">Other</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-226">任何其他类型未列出。</span><span class="sxs-lookup"><span data-stu-id="efd2f-226">Any other type not listed.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="efd2f-227">如果未显示按钮，则 **可能会隐藏"筛选器** "窗格。</span><span class="sxs-lookup"><span data-stu-id="efd2f-227">If the buttons do not display, the **Filters** pane may be hidden.</span></span>  
<span data-ttu-id="efd2f-228">有关详细信息，请导航到" [隐藏筛选器"窗格](#hide-the-filters-pane)。</span><span class="sxs-lookup"><span data-stu-id="efd2f-228">For more information, navigate to [Hide the Filters pane](#hide-the-filters-pane).</span></span>  

<span data-ttu-id="efd2f-229">若要同时启用多个类型筛选器，请按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后选择。</span><span class="sxs-lookup"><span data-stu-id="efd2f-229">To enable multiple type filters simultaneously, hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and then choose.</span></span>  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="使用类型筛选器显示 JS、CSS 和文档资源" lightbox="../media/network-network-type-filters.msft.png":::
   <span data-ttu-id="efd2f-231">使用类型筛选器显示 JS、CSS 和文档资源</span><span class="sxs-lookup"><span data-stu-id="efd2f-231">Use the Type filters to display JS, CSS, and Document resources</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-232">按时间筛选请求</span><span class="sxs-lookup"><span data-stu-id="efd2f-232">Filter requests by time</span></span>  

<span data-ttu-id="efd2f-233">选择并向左或向右拖动"概述\*\*\*\*"窗格，以仅显示该时间帧内处于活动状态的请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-233">Choose and drag left or right on the **Overview** pane to only display requests that were active during that time frame.</span></span>  <span data-ttu-id="efd2f-234">筛选器包含。</span><span class="sxs-lookup"><span data-stu-id="efd2f-234">The filter is inclusive.</span></span>  <span data-ttu-id="efd2f-235">将显示突出显示时间内处于活动状态的任何请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-235">Any request that was active during the highlighted time is shown.</span></span>  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="筛选出在 300 毫秒左右处于非活动状态的任何请求" lightbox="../media/network-network-overview-filter.msft.png":::
   <span data-ttu-id="efd2f-237">筛选出在 300 毫秒左右处于非活动状态的任何请求</span><span class="sxs-lookup"><span data-stu-id="efd2f-237">Filter out any requests that were inactive around 300 ms</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-238">隐藏数据 URL</span><span class="sxs-lookup"><span data-stu-id="efd2f-238">Hide data URLs</span></span>  

<span data-ttu-id="efd2f-239">[数据 URL][MDNHTTPDataURIs] 是嵌入到其他文档中的小文件。</span><span class="sxs-lookup"><span data-stu-id="efd2f-239">[Data URLs][MDNHTTPDataURIs] are small files embedded into other documents.</span></span>  <span data-ttu-id="efd2f-240">在"请求"表中显示的任何以数据 URL 开头 `data:` 的请求都是数据 URL。</span><span class="sxs-lookup"><span data-stu-id="efd2f-240">Any request that displays in the Requests table that starts with `data:` is a data URL.</span></span>  

<span data-ttu-id="efd2f-241">若要隐藏请求，请关闭"隐藏 **数据 URL"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="efd2f-241">To hide the requests, turn off the **Hide data URLs** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text=""隐藏数据 URL"复选框" lightbox="../media/network-network-hide-data-urls.msft.png":::
   <span data-ttu-id="efd2f-243">" **隐藏数据 URL"** 复选框</span><span class="sxs-lookup"><span data-stu-id="efd2f-243">The **Hide Data URLs** checkbox</span></span>  
:::image-end:::  

## <span data-ttu-id="efd2f-244">对请求进行排序</span><span class="sxs-lookup"><span data-stu-id="efd2f-244">Sort requests</span></span>  

<span data-ttu-id="efd2f-245">默认情况下，Requests 表中的请求按启动时间排序，但您可以使用其他条件对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="efd2f-245">By default, the requests in the Requests table are sorted by initiation time, but you may sort the table using other criteria.</span></span>  

### <span data-ttu-id="efd2f-246">按列排序</span><span class="sxs-lookup"><span data-stu-id="efd2f-246">Sort by column</span></span>  

<span data-ttu-id="efd2f-247">选择"请求"中任何列的标题，以按该列对请求进行排序。</span><span class="sxs-lookup"><span data-stu-id="efd2f-247">Choose the header of any column in the Requests to sort requests by that column.</span></span>  

### <span data-ttu-id="efd2f-248">按活动阶段排序</span><span class="sxs-lookup"><span data-stu-id="efd2f-248">Sort by activity phase</span></span>  

<span data-ttu-id="efd2f-249">若要更改瀑布对请求的排序方式，请将鼠标悬停在请求表的标题上，打开上下文菜单 \ (右键单击\) ，将鼠标悬停在瀑布上，然后选择下列\*\*\*\* 选项之一。</span><span class="sxs-lookup"><span data-stu-id="efd2f-249">To change how the Waterfall sorts requests, hover on the header of the Requests table, open the contextual menu \(right-click\), hover on **Waterfall**, and choose one of the following options.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-250">开始时间</span><span class="sxs-lookup"><span data-stu-id="efd2f-250">Start Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-251">启动的第一个请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="efd2f-251">The first request that was initiated is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-252">响应时间</span><span class="sxs-lookup"><span data-stu-id="efd2f-252">Response Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-253">开始下载的第一个请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="efd2f-253">The first request that started downloading is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-254">结束时间</span><span class="sxs-lookup"><span data-stu-id="efd2f-254">End Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-255">完成的第一个请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="efd2f-255">The first request that finished is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-256">总持续时间</span><span class="sxs-lookup"><span data-stu-id="efd2f-256">Total Duration</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-257">具有最短连接设置和请求或响应的请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="efd2f-257">The request with the shortest connection settings and request or response is at the top.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-258">延迟</span><span class="sxs-lookup"><span data-stu-id="efd2f-258">Latency</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-259">等待响应最短时间的请求位于顶部。</span><span class="sxs-lookup"><span data-stu-id="efd2f-259">The request that waited the shortest time for a response is at the top.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="efd2f-260">这些说明假定每个选项的排名从最短到最长。</span><span class="sxs-lookup"><span data-stu-id="efd2f-260">These descriptions assume that each respective option is ranked from shortest to longest.</span></span>  <span data-ttu-id="efd2f-261">选择" **瀑布"列** 的标题以反转顺序。</span><span class="sxs-lookup"><span data-stu-id="efd2f-261">Choose the header of the **Waterfall** column to reverse the order.</span></span>  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="按总持续时间对瀑布进行排序" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   <span data-ttu-id="efd2f-263">按总持续时间 \ (对瀑布进行排序 每个栏的较浅部分是等待的时间，而较暗的部分是下载字节\) </span><span class="sxs-lookup"><span data-stu-id="efd2f-263">Sort the Waterfall by total duration  \(The lighter portion of each bar is time spent waiting and the darker portion is time spent downloading bytes\)</span></span>  
:::image-end:::  

## <span data-ttu-id="efd2f-264">分析请求</span><span class="sxs-lookup"><span data-stu-id="efd2f-264">Analyze requests</span></span>  

<span data-ttu-id="efd2f-265">只要 DevTools 打开，它将记录网络面板中 **的所有** 请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-265">So long as DevTools are open, it logs all requests in the **Network** panel.</span></span>  
<span data-ttu-id="efd2f-266">使用"网络"面板分析请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-266">Use the Network panel to analyze requests.</span></span>  

### <span data-ttu-id="efd2f-267">显示请求日志</span><span class="sxs-lookup"><span data-stu-id="efd2f-267">Display a log of requests</span></span>  

<span data-ttu-id="efd2f-268">使用 Requests 表可显示打开 DevTools 时所提出所有请求的日志。</span><span class="sxs-lookup"><span data-stu-id="efd2f-268">Use the Requests table to display a log of all requests made while DevTools have been open.</span></span>  <span data-ttu-id="efd2f-269">若要显示有关每个项目的详细信息，请选择或将鼠标悬停在请求上。</span><span class="sxs-lookup"><span data-stu-id="efd2f-269">To reveals more information about each item, choose or hover on requests.</span></span>  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="Requests 表" lightbox="../media/network-network-requests-table.msft.png":::
   <span data-ttu-id="efd2f-271">Requests 表</span><span class="sxs-lookup"><span data-stu-id="efd2f-271">The Requests table</span></span>  
:::image-end:::  

<span data-ttu-id="efd2f-272">默认情况下，Requests 表将显示以下列。</span><span class="sxs-lookup"><span data-stu-id="efd2f-272">The Requests table displays the following columns by default.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-273">名称</span><span class="sxs-lookup"><span data-stu-id="efd2f-273">Name</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-274">资源的文件名或标识符。</span><span class="sxs-lookup"><span data-stu-id="efd2f-274">The filename of, or an identifier for, the resource.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-275">状态</span><span class="sxs-lookup"><span data-stu-id="efd2f-275">Status</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-276">HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="efd2f-276">The HTTP status code.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-277">类型</span><span class="sxs-lookup"><span data-stu-id="efd2f-277">Type</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-278">所请求资源的 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="efd2f-278">The MIME type of the requested resource.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-279">发起人</span><span class="sxs-lookup"><span data-stu-id="efd2f-279">Initiator</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-280">以下对象或进程启动请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-280">The following objects or processes initiate requests.</span></span>  
      
      *   <span data-ttu-id="efd2f-281">**分析程序**  Microsoft Edge 的 HTML 分析程序。</span><span class="sxs-lookup"><span data-stu-id="efd2f-281">**Parser**  The HTML parser for Microsoft Edge.</span></span>  
      *   <span data-ttu-id="efd2f-282">**重定向**  HTTP 重定向。</span><span class="sxs-lookup"><span data-stu-id="efd2f-282">**Redirect**  An HTTP redirect.</span></span>  
      *   <span data-ttu-id="efd2f-283">**脚本**  JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="efd2f-283">**Script**  A JavaScript function.</span></span>  
      *   <span data-ttu-id="efd2f-284">**其他**  一些其他过程或操作，例如使用链接导航到页面或在地址栏中输入 URL。</span><span class="sxs-lookup"><span data-stu-id="efd2f-284">**Other**  Some other process or action, such as navigating to a page using a link or entering a URL in the address bar.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-285">大小</span><span class="sxs-lookup"><span data-stu-id="efd2f-285">Size</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-286">服务器提供的响应标头和响应正文的组合大小。</span><span class="sxs-lookup"><span data-stu-id="efd2f-286">The combined size of the response headers plus the response body, as delivered by the server.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-287">时间</span><span class="sxs-lookup"><span data-stu-id="efd2f-287">Time</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-288">从请求开始到响应中最后一个字节的接收的总持续时间。</span><span class="sxs-lookup"><span data-stu-id="efd2f-288">The total duration, from the start of the request to the receipt of the final byte in the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="efd2f-289">瀑布</span><span class="sxs-lookup"><span data-stu-id="efd2f-289">Waterfall</span></span>](#display-the-timing-relationship-of-requests)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-290">每个请求的活动的直观细分。</span><span class="sxs-lookup"><span data-stu-id="efd2f-290">A visual breakdown of the activity for each request.</span></span>  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="efd2f-291">添加或删除列</span><span class="sxs-lookup"><span data-stu-id="efd2f-291">Add or remove columns</span></span>  

<span data-ttu-id="efd2f-292">将鼠标悬停在 Requests 表的标题上，打开上下文菜单 \ (右键单击\) ，然后选择一个选项来隐藏或显示它。</span><span class="sxs-lookup"><span data-stu-id="efd2f-292">Hover on the header of the Requests table, open the contextual menu \(right-click\), and choose an option to hide or show it.</span></span>  <span data-ttu-id="efd2f-293">当前显示的选项在每个项目旁边都有选中标记。</span><span class="sxs-lookup"><span data-stu-id="efd2f-293">Currently displayed options have checkmarks next to each item.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="向"请求"表添加列" lightbox="../media/network-network-requests-add-column.msft.png":::
   <span data-ttu-id="efd2f-295">向"请求"表添加列</span><span class="sxs-lookup"><span data-stu-id="efd2f-295">Add a column to the Requests table</span></span>  
:::image-end:::  

#### <span data-ttu-id="efd2f-296">添加自定义列</span><span class="sxs-lookup"><span data-stu-id="efd2f-296">Add custom columns</span></span>  

<span data-ttu-id="efd2f-297">若要向 Requests 表添加自定义列，请将鼠标悬停在 Requests 表的标题上，打开上下文菜单 \ (右键单击\) ，然后选择"响应标头\*\*\*\* 管理  >  **标头**列"。</span><span class="sxs-lookup"><span data-stu-id="efd2f-297">To add a custom column to the Requests table, hover on the header of the Requests table, open the contextual menu \(right-click\), and choose **Response Headers** > **Manage Header Columns**.</span></span>  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="向"请求"表添加自定义列" lightbox="../media/network-network-requests-add-custom.msft.png":::
   <span data-ttu-id="efd2f-299">向"请求"表添加自定义列</span><span class="sxs-lookup"><span data-stu-id="efd2f-299">Add a custom column to the Requests table</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-300">显示请求的计时关系</span><span class="sxs-lookup"><span data-stu-id="efd2f-300">Display the timing relationship of requests</span></span>  

<span data-ttu-id="efd2f-301">使用瀑布显示请求的计时关系。</span><span class="sxs-lookup"><span data-stu-id="efd2f-301">Use the Waterfall to display the timing relationships of requests.</span></span>  
<span data-ttu-id="efd2f-302">瀑布的默认组织使用请求的开始时间。</span><span class="sxs-lookup"><span data-stu-id="efd2f-302">The default organization of the Waterfall uses the start time of the requests.</span></span>  
<span data-ttu-id="efd2f-303">因此，距离左侧较远的请求在较右边的请求之前启动。</span><span class="sxs-lookup"><span data-stu-id="efd2f-303">So, requests that are farther to the left started earlier than the requests that are farther to the right.</span></span>  

<span data-ttu-id="efd2f-304">若要查看对瀑布进行排序的不同方法，请导航到按 [活动阶段排序](#sort-by-activity-phase)。</span><span class="sxs-lookup"><span data-stu-id="efd2f-304">To review the different ways that you may sort the Waterfall, navigate to [Sort by activity phase](#sort-by-activity-phase).</span></span>  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text="请求窗格的"瀑布"列" lightbox="../media/network-network-requests-waterfall.msft.png":::
   <span data-ttu-id="efd2f-306">请求窗格的"瀑布 **"** 列</span><span class="sxs-lookup"><span data-stu-id="efd2f-306">The Waterfall column of the **Requests** pane</span></span>  
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

### <span data-ttu-id="efd2f-307">显示响应正文的预览</span><span class="sxs-lookup"><span data-stu-id="efd2f-307">Display a preview of a response body</span></span>  

<span data-ttu-id="efd2f-308">若要显示响应正文的预览，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="efd2f-308">To display a preview of a response body, use the following steps.</span></span>  

1.  <span data-ttu-id="efd2f-309">在"请求"表的"名称" **列下** 选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="efd2f-309">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="efd2f-310">选择 **"预览"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="efd2f-310">Choose the **Preview** tab.</span></span>  

<span data-ttu-id="efd2f-311">"预览"选项卡对显示图像非常有用。</span><span class="sxs-lookup"><span data-stu-id="efd2f-311">The Preview tab is mostly useful to display images.</span></span>  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text="“预览”选项卡" lightbox="../media/network-network-resources-preview.msft.png":::
   <span data-ttu-id="efd2f-313">“**预览**”选项卡</span><span class="sxs-lookup"><span data-stu-id="efd2f-313">The **Preview** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-314">显示响应正文</span><span class="sxs-lookup"><span data-stu-id="efd2f-314">Display a response body</span></span>  

<span data-ttu-id="efd2f-315">若要向请求显示响应正文，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="efd2f-315">To display the response body to a request, use the following steps.</span></span>  

1.  <span data-ttu-id="efd2f-316">在"请求"表的"名称" **列下** 选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="efd2f-316">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="efd2f-317">选择" **响应"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="efd2f-317">Choose the **Response** tab.</span></span>  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text="“响应”选项卡" lightbox="../media/network-network-resources-response.msft.png":::
   <span data-ttu-id="efd2f-319">“**响应**” 选项卡</span><span class="sxs-lookup"><span data-stu-id="efd2f-319">The **Response** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-320">显示 HTTP 标头</span><span class="sxs-lookup"><span data-stu-id="efd2f-320">Display HTTP headers</span></span>  

<span data-ttu-id="efd2f-321">若要显示有关请求的 HTTP 标头数据，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="efd2f-321">To display HTTP header data about a request, use the following steps.</span></span>  

1.  <span data-ttu-id="efd2f-322">在"请求"表的"名称" **列下** 选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="efd2f-322">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="efd2f-323">选择 **"标题"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="efd2f-323">Choose the **Headers** tab.</span></span>  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text="“标头”选项卡" lightbox="../media/network-resources-headers.msft.png":::
   <span data-ttu-id="efd2f-325">“**标头**”选项卡</span><span class="sxs-lookup"><span data-stu-id="efd2f-325">The **Headers** tab</span></span>  
:::image-end:::  

#### <span data-ttu-id="efd2f-326">显示 HTTP 标头源</span><span class="sxs-lookup"><span data-stu-id="efd2f-326">Display HTTP header source</span></span>  

<span data-ttu-id="efd2f-327">默认情况下，"标题"选项卡按字母顺序显示标题名称。</span><span class="sxs-lookup"><span data-stu-id="efd2f-327">By default, the Headers tab shows header names alphabetically.</span></span>  <span data-ttu-id="efd2f-328">若要按接收的顺序显示 HTTP 头名称，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="efd2f-328">To dsiplay the HTTP header names in the order received, use the following steps.</span></span>  

1.  <span data-ttu-id="efd2f-329">打开 **您** 感兴趣的请求的"标题"选项卡。</span><span class="sxs-lookup"><span data-stu-id="efd2f-329">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="efd2f-330">有关详细信息，请导航到["显示 HTTP 标头"。](#display-http-headers)</span><span class="sxs-lookup"><span data-stu-id="efd2f-330">For more information, navigate to [Display HTTP headers](#display-http-headers).</span></span>  
1.  <span data-ttu-id="efd2f-331">选择 **"请求**标头"或"响应头 **"部分\*\*\*\*旁边的**视图源。</span><span class="sxs-lookup"><span data-stu-id="efd2f-331">Choose **view source**, next to the **Request Header** or **Response Header** section.</span></span>  

### <span data-ttu-id="efd2f-332">显示查询字符串参数</span><span class="sxs-lookup"><span data-stu-id="efd2f-332">Display query string parameters</span></span>  

<span data-ttu-id="efd2f-333">若要以可读格式显示 URL 的查询字符串参数，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="efd2f-333">To display the query string parameters of a URL in a human-readable format, use the following steps.</span></span>  

1.  <span data-ttu-id="efd2f-334">打开 **您** 感兴趣的请求的"标题"选项卡。</span><span class="sxs-lookup"><span data-stu-id="efd2f-334">Open the **Headers** tab for the request that interests you.</span></span>  <span data-ttu-id="efd2f-335">有关详细信息，请导航到["显示 HTTP 标头"。](#display-http-headers)</span><span class="sxs-lookup"><span data-stu-id="efd2f-335">For more information, navigate to [Display HTTP headers](#display-http-headers).</span></span>  
1.  <span data-ttu-id="efd2f-336">转到" **查询字符串参数"** 部分。</span><span class="sxs-lookup"><span data-stu-id="efd2f-336">Go to the **Query String Parameters** section.</span></span>  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text=""查询字符串参数"部分" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   <span data-ttu-id="efd2f-338">" **查询字符串参数"** 部分</span><span class="sxs-lookup"><span data-stu-id="efd2f-338">The **Query String Parameters** section</span></span>  
:::image-end:::  

#### <span data-ttu-id="efd2f-339">显示查询字符串参数源</span><span class="sxs-lookup"><span data-stu-id="efd2f-339">Display query string parameters source</span></span>  

<span data-ttu-id="efd2f-340">若要显示请求的查询字符串参数源，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="efd2f-340">To display the query string parameter source of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="efd2f-341">转到"查询字符串参数"部分。</span><span class="sxs-lookup"><span data-stu-id="efd2f-341">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="efd2f-342">有关详细信息，请导航到["显示查询字符串参数"。](#display-query-string-parameters)</span><span class="sxs-lookup"><span data-stu-id="efd2f-342">For more information, navigate to [Display query string parameters](#display-query-string-parameters).</span></span>  
1.  <span data-ttu-id="efd2f-343">选择 **视图源**。</span><span class="sxs-lookup"><span data-stu-id="efd2f-343">Choose **view source**.</span></span>  

#### <span data-ttu-id="efd2f-344">显示 URL 编码的查询字符串参数</span><span class="sxs-lookup"><span data-stu-id="efd2f-344">Display URL-encoded query string parameters</span></span>  

<span data-ttu-id="efd2f-345">若要以可读格式显示查询字符串参数，但保留编码，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="efd2f-345">To display query string parameters in a human-readable format, but with encodings preserved, use the following steps.</span></span>  

1.  <span data-ttu-id="efd2f-346">转到"查询字符串参数"部分。</span><span class="sxs-lookup"><span data-stu-id="efd2f-346">Go to the Query String Parameters section.</span></span>  <span data-ttu-id="efd2f-347">有关详细信息，请导航到["显示查询字符串参数"。](#display-query-string-parameters)</span><span class="sxs-lookup"><span data-stu-id="efd2f-347">For more information, navigate to [Display query string parameters](#display-query-string-parameters).</span></span>  
1.  <span data-ttu-id="efd2f-348">选择**编码的视图 URL。**</span><span class="sxs-lookup"><span data-stu-id="efd2f-348">Choose **view URL encoded**.</span></span>  

### <span data-ttu-id="efd2f-349">显示 Cookie</span><span class="sxs-lookup"><span data-stu-id="efd2f-349">Display cookies</span></span>  

<span data-ttu-id="efd2f-350">若要显示请求的 HTTP 标头中发送的 Cookie，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="efd2f-350">To display the cookies sent in the HTTP header of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="efd2f-351">在"请求"表的"名称" **列下** 选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="efd2f-351">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="efd2f-352">选择 **"Cookie"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="efd2f-352">Choose the **Cookies** tab.</span></span>  

<!--For more information about each of the columns, navigate to [Fields][ManageDataCookiesFields].  -->  

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->  
<!--TODO: add link when section is available -->  

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text=""Cookie"选项卡" lightbox="../media/network-network-resources-cookies.msft.png":::
   <span data-ttu-id="efd2f-354">"Cookie"选项卡</span><span class="sxs-lookup"><span data-stu-id="efd2f-354">The Cookies tab</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-355">显示请求的时间细分</span><span class="sxs-lookup"><span data-stu-id="efd2f-355">Display the timing breakdown of a request</span></span>  

<span data-ttu-id="efd2f-356">若要显示请求的时间细分，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="efd2f-356">To display the timing breakdown of a request, use the following steps.</span></span>  

1.  <span data-ttu-id="efd2f-357">在"请求"表的"名称" **列下** 选择请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="efd2f-357">Choose the URL of the request, under the **Name** column of the Requests table.</span></span>  
1.  <span data-ttu-id="efd2f-358">选择 **"计时"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="efd2f-358">Choose the **Timing** tab.</span></span>  

<span data-ttu-id="efd2f-359">若要更快地访问数据，请导航到"[预览计时细分"。](#preview-a-timing-breakdown)</span><span class="sxs-lookup"><span data-stu-id="efd2f-359">For a faster way to access the data, navigate to [Preview a timing breakdown](#preview-a-timing-breakdown).</span></span>  

<span data-ttu-id="efd2f-360">有关"计时"选项卡中可能显示的每个阶段详细信息，请导航到\*\*\*\* 说明的"计时["细分阶段](#timing-breakdown-phases-explained)。</span><span class="sxs-lookup"><span data-stu-id="efd2f-360">For more information about each of the phases that may be displayed in the **Timing** tab, navigate to [Timing breakdown phases explained](#timing-breakdown-phases-explained).</span></span>  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text="“计时”选项卡" lightbox="../media/network-network-resources-timing.msft.png":::
   <span data-ttu-id="efd2f-362">“**计时**”选项卡</span><span class="sxs-lookup"><span data-stu-id="efd2f-362">The **Timing** tab</span></span>  
:::image-end:::  

<span data-ttu-id="efd2f-363">有关每个阶段详细信息。</span><span class="sxs-lookup"><span data-stu-id="efd2f-363">More information about each of the phases.</span></span>  

<span data-ttu-id="efd2f-364">有关访问屏幕详细信息，请导航到"[显示计时细分"。](#display-the-timing-breakdown-of-a-request)</span><span class="sxs-lookup"><span data-stu-id="efd2f-364">For more information about accessing the display, navigate to [Display timing breakdown](#display-the-timing-breakdown-of-a-request).</span></span>  

#### <span data-ttu-id="efd2f-365">预览计时细分</span><span class="sxs-lookup"><span data-stu-id="efd2f-365">Preview a timing breakdown</span></span>  

<span data-ttu-id="efd2f-366">若要显示请求的时间细分预览，在"请求"表的 **"瀑布** "列中，将鼠标悬停在请求的条目上。</span><span class="sxs-lookup"><span data-stu-id="efd2f-366">To display a preview of the timing breakdown of a request, in the **Waterfall** column of the Requests table, hover on the entry for the request.</span></span>  

<span data-ttu-id="efd2f-367">若要详细了解如何在不悬停的情况下访问数据，请导航到"[显示请求的时间细分"。](#display-the-timing-breakdown-of-a-request)</span><span class="sxs-lookup"><span data-stu-id="efd2f-367">For more information about how to access the data without hovering, navigate to [Display the timing breakdown of a request](#display-the-timing-breakdown-of-a-request).</span></span>  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text=">预览请求的时间细分" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   <span data-ttu-id="efd2f-369">预览请求的时间细分</span><span class="sxs-lookup"><span data-stu-id="efd2f-369">Preview the timing breakdown of a request</span></span>  
:::image-end:::  

#### <span data-ttu-id="efd2f-370">说明的时间细分阶段</span><span class="sxs-lookup"><span data-stu-id="efd2f-370">Timing breakdown phases explained</span></span>  

<span data-ttu-id="efd2f-371">有关"计时"选项卡中可能显示 **的每个阶段详细信息** 。</span><span class="sxs-lookup"><span data-stu-id="efd2f-371">More information about each of the phases that may display in the **Timing** tab.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-372">排队</span><span class="sxs-lookup"><span data-stu-id="efd2f-372">Queueing</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-373">当以下任一项为真时，浏览器将队列请求排成队列。</span><span class="sxs-lookup"><span data-stu-id="efd2f-373">The browser queues requests when any of the following are true.</span></span>  
      
      *   <span data-ttu-id="efd2f-374">存在更高优先级的请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-374">Higher priority requests exist.</span></span>  
      *   <span data-ttu-id="efd2f-375">为同一源打开了六个 TCP 连接，这是限制。</span><span class="sxs-lookup"><span data-stu-id="efd2f-375">Six TCP connections are open for the same origin, which is the limit.</span></span>  <span data-ttu-id="efd2f-376">仅适用于 HTTP/1.0 和 HTTP/1.1。</span><span class="sxs-lookup"><span data-stu-id="efd2f-376">Applies to HTTP/1.0 and HTTP/1.1 only.</span></span>  
      *   <span data-ttu-id="efd2f-377">浏览器在磁盘缓存中简要分配空间。</span><span class="sxs-lookup"><span data-stu-id="efd2f-377">The browser is briefly allocating space in the disk cache.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-378">已停止</span><span class="sxs-lookup"><span data-stu-id="efd2f-378">Stalled</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-379">请求因队列中所述的任何原因 **而停止**。</span><span class="sxs-lookup"><span data-stu-id="efd2f-379">The request is stalled for any of the reasons described in **Queueing**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-380">DNS 查找</span><span class="sxs-lookup"><span data-stu-id="efd2f-380">DNS Lookup</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-381">浏览器正在解析请求的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="efd2f-381">The browser is resolving the IP address for the request.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-382">初始连接</span><span class="sxs-lookup"><span data-stu-id="efd2f-382">Initial connection</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-383">浏览器建立包括 TCP 握手、TCP 重试和协商安全套接字层在内的连接。</span><span class="sxs-lookup"><span data-stu-id="efd2f-383">The browser establishes a connection including TCP handshakes, TCP retries, and negotiates a Secure Socket Layer.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-384">代理协商</span><span class="sxs-lookup"><span data-stu-id="efd2f-384">Proxy negotiation</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-385">浏览器正在与代理服务器协商 [请求][WikiProxyServer]。</span><span class="sxs-lookup"><span data-stu-id="efd2f-385">The browser is negotiating the request with a [proxy server][WikiProxyServer].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-386">发送的请求</span><span class="sxs-lookup"><span data-stu-id="efd2f-386">Request sent</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-387">正在发送请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-387">The request is being sent.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-388">ServiceWorker 准备</span><span class="sxs-lookup"><span data-stu-id="efd2f-388">ServiceWorker Preparation</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-389">浏览器正在启动服务工作进程。</span><span class="sxs-lookup"><span data-stu-id="efd2f-389">The browser is starting the service worker.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-390">对 ServiceWorker 的请求</span><span class="sxs-lookup"><span data-stu-id="efd2f-390">Request to ServiceWorker</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-391">请求将发送给服务工作者。</span><span class="sxs-lookup"><span data-stu-id="efd2f-391">The request is being sent to the service worker.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-392">等待 \ (TTFB\) </span><span class="sxs-lookup"><span data-stu-id="efd2f-392">Waiting \(TTFB\)</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-393">浏览器正在等待响应的第一个字节。</span><span class="sxs-lookup"><span data-stu-id="efd2f-393">The browser is waiting for the first byte of a response.</span></span>  <span data-ttu-id="efd2f-394">TTFB 代表第一个字节的时间。</span><span class="sxs-lookup"><span data-stu-id="efd2f-394">TTFB stands for Time To First Byte.</span></span>  <span data-ttu-id="efd2f-395">此时间包括一次延迟往返以及服务器准备响应所花时间。</span><span class="sxs-lookup"><span data-stu-id="efd2f-395">This timing includes one round trip of latency and the time the server took to prepare the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-396">内容下载</span><span class="sxs-lookup"><span data-stu-id="efd2f-396">Content Download</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-397">浏览器正在接收响应。</span><span class="sxs-lookup"><span data-stu-id="efd2f-397">The browser is receiving the response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-398">接收推送</span><span class="sxs-lookup"><span data-stu-id="efd2f-398">Receiving Push</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-399">浏览器通过 HTTP/2 服务器推送接收此响应的数据。</span><span class="sxs-lookup"><span data-stu-id="efd2f-399">The browser is receiving data for this response via HTTP/2 Server Push.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="efd2f-400">读取推送</span><span class="sxs-lookup"><span data-stu-id="efd2f-400">Reading Push</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="efd2f-401">浏览器正在读取之前收到的本地数据。</span><span class="sxs-lookup"><span data-stu-id="efd2f-401">The browser is reading the local data previously received.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="efd2f-402">显示发起方和依赖项</span><span class="sxs-lookup"><span data-stu-id="efd2f-402">Display initiators and dependencies</span></span>  

<span data-ttu-id="efd2f-403">若要显示请求的发起方和依赖项，请将 `Shift` 鼠标悬停在请求表中的请求上。</span><span class="sxs-lookup"><span data-stu-id="efd2f-403">To display the initiators and dependencies of a request, hold `Shift`and hover on the request in the Requests table.</span></span>  <span data-ttu-id="efd2f-404">DevTools 颜色：发起人以绿色显示，依赖关系显示为红色。</span><span class="sxs-lookup"><span data-stu-id="efd2f-404">DevTools colors: initiators are shown in green and dependencies are shown in red.</span></span>  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="显示请求的发起方和依赖项" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   <span data-ttu-id="efd2f-406">显示请求的发起方和依赖项</span><span class="sxs-lookup"><span data-stu-id="efd2f-406">Display the initiators and dependencies of a request</span></span>  
:::image-end:::  

<span data-ttu-id="efd2f-407">当 Requests 表按时间顺序排序时，如果将鼠标悬停在行上，则它前面的行将显示一个绿色请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-407">When the Requests table is ordered chronologically, if you hover on a line, the line preceding it displays a green request.</span></span>  <span data-ttu-id="efd2f-408">绿色请求是依赖项的发起者。</span><span class="sxs-lookup"><span data-stu-id="efd2f-408">The green request is the initiator of the dependency.</span></span>  <span data-ttu-id="efd2f-409">如果前一行上显示另一个绿色请求，则较高的请求是发起者发起人。</span><span class="sxs-lookup"><span data-stu-id="efd2f-409">If another green request is displayed on the line before that, that higher request is the initiator of the initiator.</span></span>  <span data-ttu-id="efd2f-410">以此类推。</span><span class="sxs-lookup"><span data-stu-id="efd2f-410">And so on.</span></span>  

### <span data-ttu-id="efd2f-411">显示加载事件</span><span class="sxs-lookup"><span data-stu-id="efd2f-411">Display load events</span></span>  

<span data-ttu-id="efd2f-412">DevTools 在网络面板上的 `DOMContentLoaded` 多个 `load` 位置显示和事件的计时。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="efd2f-412">DevTools displays the timing of the `DOMContentLoaded` and `load` events in multiple places on the **Network** panel.</span></span>  <span data-ttu-id="efd2f-413">事件 `DOMContentLoaded` 的颜色为蓝色， `load` 事件为红色。</span><span class="sxs-lookup"><span data-stu-id="efd2f-413">The `DOMContentLoaded` event is colored blue, and the `load` event is red.</span></span>  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="DOMContentLoaded 和"网络"面板上的加载事件的位置" lightbox="../media/network-network-requests-load-events.msft.png":::
   <span data-ttu-id="efd2f-415">"网络" `DOMContentLoaded` 面板 `load` 上和事件的位置\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="efd2f-415">The locations of the `DOMContentLoaded` and `load` events on the **Network** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-416">显示请求总数</span><span class="sxs-lookup"><span data-stu-id="efd2f-416">Display the total number of requests</span></span>  

<span data-ttu-id="efd2f-417">"摘要"窗格中的"网络"面板底部\*\*\*\* 列出了请求**总数**。</span><span class="sxs-lookup"><span data-stu-id="efd2f-417">The total number of requests is listed in the **Summary** pane, at the bottom of the **Network** panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="efd2f-418">此数字仅跟踪自 DevTools 打开后记录的请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-418">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="efd2f-419">如果在打开 DevTools 之前发生了其他请求，则这些请求不会计算在内。</span><span class="sxs-lookup"><span data-stu-id="efd2f-419">If other requests occurred before DevTools was opened, those requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="自打开 DevTools 以来的请求总数" lightbox="../media/network-network-total-requests.msft.png":::
   <span data-ttu-id="efd2f-421">自打开 DevTools 以来的请求总数</span><span class="sxs-lookup"><span data-stu-id="efd2f-421">The total number of requests since DevTools were opened</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-422">显示总下载大小</span><span class="sxs-lookup"><span data-stu-id="efd2f-422">Display the total download size</span></span>  

<span data-ttu-id="efd2f-423">请求的总下载大小在网络面板底部的"摘要"\*\*\*\*\*\*窗格中列出。\*\*</span><span class="sxs-lookup"><span data-stu-id="efd2f-423">The total download size of requests is listed in the **Summary** pane, at the bottom of the **Network** panel.</span></span>  

> [!CAUTION]
> <span data-ttu-id="efd2f-424">此数字仅跟踪自 DevTools 打开后记录的请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-424">This number only tracks requests that have been logged since DevTools was opened.</span></span>  <span data-ttu-id="efd2f-425">如果在打开 DevTools 之前发生了其他请求，则以前的请求不会计算在内。</span><span class="sxs-lookup"><span data-stu-id="efd2f-425">If other requests occurred before DevTools was opened, the previous requests are not counted.</span></span>  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="请求的总下载大小" lightbox="../media/network-network-total-download-size.msft.png":::
   <span data-ttu-id="efd2f-427">请求的总下载大小</span><span class="sxs-lookup"><span data-stu-id="efd2f-427">The total download size of requests</span></span>  
:::image-end:::  

<span data-ttu-id="efd2f-428">若要验证浏览器取消压缩每个项目后资源的大小，请导航以显示资源的未压缩 [大小](#display-the-uncompressed-size-of-a-resource)。</span><span class="sxs-lookup"><span data-stu-id="efd2f-428">To verify how large resources are after the browser uncompresses each item, navigate to [display the uncompressed size of a resource](#display-the-uncompressed-size-of-a-resource).</span></span>  

### <span data-ttu-id="efd2f-429">显示导致请求的堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="efd2f-429">Display the stack trace that caused a request</span></span>  

<span data-ttu-id="efd2f-430">JavaScript 语句请求资源后，将鼠标悬停在 **发起** 方列上，以显示导致请求的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="efd2f-430">After a JavaScript statement requests a resource, hover on the **Initiator** column to display the stack trace leading up to the request.</span></span>  

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
   <span data-ttu-id="efd2f-432">导致资源请求的堆栈跟踪</span><span class="sxs-lookup"><span data-stu-id="efd2f-432">The stack trace leading up to a resource request</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-433">显示资源的未压缩大小</span><span class="sxs-lookup"><span data-stu-id="efd2f-433">Display the uncompressed size of a resource</span></span>  

<span data-ttu-id="efd2f-434">打开" **使用大型请求行"** 复选框，然后查看"大小" **列的底部值** 。</span><span class="sxs-lookup"><span data-stu-id="efd2f-434">Turn on the **Use large request rows** checkbox and then review the bottom value of the **Size** column.</span></span>  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="未压缩资源的示例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   <span data-ttu-id="efd2f-436">未压缩资源的示例 \ (通过网络发送的文件的压缩大小为 `jquery-3.3.1.min.js` `29.9 KB` `84.9 KB` \) </span><span class="sxs-lookup"><span data-stu-id="efd2f-436">An example of uncompressed resources  \(The compressed size of the `jquery-3.3.1.min.js` file that was sent over the network was `29.9 KB`, whereas the uncompressed size was `84.9 KB`\)</span></span>  
:::image-end:::  

## <span data-ttu-id="efd2f-437">导出请求数据</span><span class="sxs-lookup"><span data-stu-id="efd2f-437">Export requests data</span></span>  

### <span data-ttu-id="efd2f-438">将所有网络请求保存到 HAR 文件</span><span class="sxs-lookup"><span data-stu-id="efd2f-438">Save all network requests to a HAR file</span></span>  

<span data-ttu-id="efd2f-439">若要将所有网络请求保存到 HAR 文件，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="efd2f-439">To save all network requests to a HAR file, complete the following steps.</span></span>  

1.  <span data-ttu-id="efd2f-440">将鼠标悬停在 Requests 表中的任何请求上，然后打开上下文菜单 \ (右键单击\) 。</span><span class="sxs-lookup"><span data-stu-id="efd2f-440">Hover on any request in the Requests table and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="efd2f-441">选择 **"保存为具有内容的 HAR"。**</span><span class="sxs-lookup"><span data-stu-id="efd2f-441">Choose **Save as HAR with Content**.</span></span>  <span data-ttu-id="efd2f-442">DevTools 将打开 DevTools 后发生的所有请求保存到 HAR 文件中。</span><span class="sxs-lookup"><span data-stu-id="efd2f-442">DevTools saves all requests that have occurred since you opened DevTools to the HAR file.</span></span>  <span data-ttu-id="efd2f-443">无法筛选请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-443">You are not able to filter requests.</span></span>  <span data-ttu-id="efd2f-444">您也无法保存单个请求。</span><span class="sxs-lookup"><span data-stu-id="efd2f-444">You are also not able to save a single request.</span></span>  

<span data-ttu-id="efd2f-445">保存 HAR 文件后，你可以将其导入回 DevTools 进行分析。</span><span class="sxs-lookup"><span data-stu-id="efd2f-445">Once you save a HAR file, you may import it back into DevTools for analysis.</span></span>  <span data-ttu-id="efd2f-446">只需将 HAR 文件拖放到 Requests 表中。</span><span class="sxs-lookup"><span data-stu-id="efd2f-446">Just drag-and-drop the HAR file into the Requests table.</span></span>  
<!--For more information, navigate to also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="选择"将内容另存为 HAR"" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   <span data-ttu-id="efd2f-448">选择 **"将内容另存为 HAR"**</span><span class="sxs-lookup"><span data-stu-id="efd2f-448">Choose **Save as HAR with Content**</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-449">将一个或多个请求复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="efd2f-449">Copy one or more requests to the clipboard</span></span>  

<span data-ttu-id="efd2f-450">在"\*\*\*\* 请求"表的"名称"列下，将鼠标悬停在请求上，打开上下文菜单 \ (右键单击\) ，将鼠标悬\*\*\*\* 停在"复制"上，然后选择下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="efd2f-450">Under the **Name** column of the Requests table, hover on a request, open the contextual menu \(right-click\), hover on **Copy**, and choose one of the following options.</span></span>  

| <span data-ttu-id="efd2f-451">名称</span><span class="sxs-lookup"><span data-stu-id="efd2f-451">Name</span></span> | <span data-ttu-id="efd2f-452">详细信息</span><span class="sxs-lookup"><span data-stu-id="efd2f-452">Details</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="efd2f-453">复制链接地址</span><span class="sxs-lookup"><span data-stu-id="efd2f-453">Copy Link Address</span></span>** | <span data-ttu-id="efd2f-454">将请求的 URL 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="efd2f-454">Copy the URL of the request to the clipboard.</span></span> |  
| **<span data-ttu-id="efd2f-455">复制响应</span><span class="sxs-lookup"><span data-stu-id="efd2f-455">Copy Response</span></span>** | <span data-ttu-id="efd2f-456">将响应正文复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="efd2f-456">Copy the response body to the clipboard.</span></span> |  
| **<span data-ttu-id="efd2f-457">复制为提取</span><span class="sxs-lookup"><span data-stu-id="efd2f-457">Copy as Fetch</span></span>** | &nbsp; |  
| **<span data-ttu-id="efd2f-458">复制为 cURL</span><span class="sxs-lookup"><span data-stu-id="efd2f-458">Copy as cURL</span></span>** | <span data-ttu-id="efd2f-459">将请求复制为 cURL 命令。</span><span class="sxs-lookup"><span data-stu-id="efd2f-459">Copy the request as a cURL command.</span></span> |  
| **<span data-ttu-id="efd2f-460">全部复制为提取</span><span class="sxs-lookup"><span data-stu-id="efd2f-460">Copy All as Fetch</span></span>** | &nbsp; |  
| **<span data-ttu-id="efd2f-461">全部复制为 cURL</span><span class="sxs-lookup"><span data-stu-id="efd2f-461">Copy All as cURL</span></span>** | <span data-ttu-id="efd2f-462">复制所有请求作为 cURL 命令链。</span><span class="sxs-lookup"><span data-stu-id="efd2f-462">Copy all requests as a chain of cURL commands.</span></span> |  
| **<span data-ttu-id="efd2f-463">全部复制为 HAR</span><span class="sxs-lookup"><span data-stu-id="efd2f-463">Copy All as HAR</span></span>** | <span data-ttu-id="efd2f-464">复制所有请求作为 HAR 数据。</span><span class="sxs-lookup"><span data-stu-id="efd2f-464">Copy all requests as HAR data.</span></span> |  

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

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="选择"复制响应"" lightbox="../media/network-network-requests-copy-response.msft.png":::
   <span data-ttu-id="efd2f-466">选择 **"复制响应"**</span><span class="sxs-lookup"><span data-stu-id="efd2f-466">Choose **Copy Response**</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-467">将格式化的响应 JSON 复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="efd2f-467">Copy formatted response JSON to the clipboard</span></span>  

<span data-ttu-id="efd2f-468">选择网络请求并导航到 **"标题"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="efd2f-468">Choose a network request and navigate to the **Headers** pane.</span></span>  <span data-ttu-id="efd2f-469">若要复制响应的 JSON 值，请导航\*\*\*\* 到"请求负载"，将鼠标悬停在 JSON 响应内容上，打开上下文菜单 \ (右键单击\) ，然后选择"复制**值**"。</span><span class="sxs-lookup"><span data-stu-id="efd2f-469">To copy the JSON value of a response, navigate to **Request payload**, hover on the JSON response content, open the contextual menu \(right-click\), and choose **Copy Value**.</span></span>  

:::row:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-copy-property-value.msft.png" alt-text="在上下文菜单中复制值" lightbox="../media/network-header-copy-property-value.msft.png":::
          <span data-ttu-id="efd2f-471">**在上下文菜单中** 复制值</span><span class="sxs-lookup"><span data-stu-id="efd2f-471">**Copy Value** in contextual menu</span></span>  
        :::image-end:::  
   :::column-end:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-paste-property-value.msft.png" alt-text="Visual Studio格式响应 JSON 的代码" lightbox="../media/network-header-paste-property-value.msft.png":::
          <span data-ttu-id="efd2f-473">将格式化的响应 JSON 粘贴到Visual Studio代码</span><span class="sxs-lookup"><span data-stu-id="efd2f-473">Pasting formatted response JSON in Visual Studio Code</span></span>  
        :::image-end:::  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="efd2f-474">将属性值从网络请求复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="efd2f-474">Copy property values from network requests to your clipboard</span></span>  

<span data-ttu-id="efd2f-475">若要将属性值从网络请求复制到剪贴板，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="efd2f-475">To copy property values from network requests to your clipboard, complete the following actions.</span></span>  

1.  <span data-ttu-id="efd2f-476">打开 **"标题"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="efd2f-476">Open the **Headers** pane.</span></span>  
1.  <span data-ttu-id="efd2f-477">打开以下标题部分之一。</span><span class="sxs-lookup"><span data-stu-id="efd2f-477">Open one of the following header sections.</span></span>  
    *   <span data-ttu-id="efd2f-478">请求有效负载 \ (JSON\) </span><span class="sxs-lookup"><span data-stu-id="efd2f-478">Request payload \(JSON\)</span></span>  
    *   <span data-ttu-id="efd2f-479">表单数据</span><span class="sxs-lookup"><span data-stu-id="efd2f-479">Form Data</span></span>  
    *   <span data-ttu-id="efd2f-480">查询字符串参数</span><span class="sxs-lookup"><span data-stu-id="efd2f-480">Query String Parameters</span></span>  
    *   <span data-ttu-id="efd2f-481">请求标头</span><span class="sxs-lookup"><span data-stu-id="efd2f-481">Request Headers</span></span>  
    *   <span data-ttu-id="efd2f-482">响应标头</span><span class="sxs-lookup"><span data-stu-id="efd2f-482">Response Headers</span></span>  
1.  <span data-ttu-id="efd2f-483">打开上下文菜单 \ (右键单击\) > **复制值**。</span><span class="sxs-lookup"><span data-stu-id="efd2f-483">Open the contextual menu \(right-click\) > **Copy value**.</span></span>  <span data-ttu-id="efd2f-484">现在，您可以将该值粘贴到任何编辑器中以查看它。</span><span class="sxs-lookup"><span data-stu-id="efd2f-484">You can now paste the value into any editor to review it.</span></span>  
    
## <span data-ttu-id="efd2f-485">更改网络面板的布局</span><span class="sxs-lookup"><span data-stu-id="efd2f-485">Change the layout of the Network panel</span></span>  

<span data-ttu-id="efd2f-486">可以展开或折叠网络面板 UI **的各个部分** ，以重点关注重要信息。</span><span class="sxs-lookup"><span data-stu-id="efd2f-486">You may expand or collapse sections of the **Network** panel UI to focus important information.</span></span>  

### <span data-ttu-id="efd2f-487">隐藏"筛选器"窗格</span><span class="sxs-lookup"><span data-stu-id="efd2f-487">Hide the Filters pane</span></span>  

<span data-ttu-id="efd2f-488">默认情况下，DevTools 显示" **筛选器"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="efd2f-488">By default, DevTools show the **Filters** pane.</span></span>  
<span data-ttu-id="efd2f-489">Choose **Filter** \ (![ Filter ][ImageFilterIcon] \) to hide it.</span><span class="sxs-lookup"><span data-stu-id="efd2f-489">Choose **Filter** \(![Filter][ImageFilterIcon]\) to hide it.</span></span>  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text=""隐藏筛选器"按钮" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   <span data-ttu-id="efd2f-491">"隐藏筛选器"按钮</span><span class="sxs-lookup"><span data-stu-id="efd2f-491">The Hide Filters button</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-492">使用大型请求行</span><span class="sxs-lookup"><span data-stu-id="efd2f-492">Use large request rows</span></span>  

<span data-ttu-id="efd2f-493">在网络请求表中需要更多空格时，请使用大行。</span><span class="sxs-lookup"><span data-stu-id="efd2f-493">Use large rows when you want more whitespace in your network requests table.</span></span>  <span data-ttu-id="efd2f-494">使用大行时，某些列还会提供一些详细信息。</span><span class="sxs-lookup"><span data-stu-id="efd2f-494">Some columns also provide a little more information when using large rows.</span></span>  <span data-ttu-id="efd2f-495">例如，Size 列 **的底部值为请求** 的未压缩大小。</span><span class="sxs-lookup"><span data-stu-id="efd2f-495">For example, the bottom value of the **Size** column is the uncompressed size of a request.</span></span>  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text=""请求"窗格中大型请求行的示例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   <span data-ttu-id="efd2f-497">"请求"窗格中大型请求 **行** 的示例</span><span class="sxs-lookup"><span data-stu-id="efd2f-497">An example of large request rows in the **Requests** pane</span></span>  
:::image-end:::  

<span data-ttu-id="efd2f-498">若要启用大行，请打开"使用 **大型请求行"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="efd2f-498">To enable large rows, turn on the **Use large request rows** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text=""使用大型请求行"复选框" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   <span data-ttu-id="efd2f-500">" **使用大型请求行"** 复选框</span><span class="sxs-lookup"><span data-stu-id="efd2f-500">The **Use large request rows** checkbox</span></span>  
:::image-end:::  

### <span data-ttu-id="efd2f-501">隐藏"概述"窗格</span><span class="sxs-lookup"><span data-stu-id="efd2f-501">Hide the Overview pane</span></span>  

<span data-ttu-id="efd2f-502">默认情况下，DevTools 显示 **"概述"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="efd2f-502">By default, DevTools displays the **Overview** pane.</span></span>  <span data-ttu-id="efd2f-503">若要隐藏它，请关闭"显示 **概述"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="efd2f-503">To hide it, turn off the **Show Overview** checkbox.</span></span>  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text=""显示概述"复选框" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   <span data-ttu-id="efd2f-505">" **显示概述"** 复选框</span><span class="sxs-lookup"><span data-stu-id="efd2f-505">The **Show Overview** checkbox</span></span>  
:::image-end:::  

## <span data-ttu-id="efd2f-506">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="efd2f-506">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCaptureScreenshotsIcon]: ../media/capture-screenshots-icon.msft.png  
[ImageClearIcon]: ../media/clear-requests-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageHideIcon]: ../media/hide-overview-icon.msft.png  
[ImageLargeResourceRowsIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageRecordOnIcon]: ../media/record-on-icon.msft.png  

<!-- links -->  

[DevtoolsProgressiveWebApps]: ../progressive-web-apps/index.md "调试渐进式 Web 应用 |Microsoft Docs"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions | Microsoft Docs"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "数据 URL |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "代理服务器 - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="efd2f-510">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="efd2f-510">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="efd2f-511">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="efd2f-511">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="efd2f-513">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="efd2f-513">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
