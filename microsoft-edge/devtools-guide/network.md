---
description: 使用 "网络" 面板监视和分析页面资源请求
title: DevTools-网络
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools，网络，加载时间，http，https，浏览器缓存，HAR
ms.custom: seodec18
ms.openlocfilehash: 0b190f5163f9b7a9f9920877a94577177053e4f6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563463"
---
# <span data-ttu-id="bd06a-104">Network</span><span class="sxs-lookup"><span data-stu-id="bd06a-104">Network</span></span>

<span data-ttu-id="bd06a-105">使用 " **网络** " 面板监控、检查和分析通过线路发送的请求和响应。</span><span class="sxs-lookup"><span data-stu-id="bd06a-105">Use the **Network** panel to monitor, inspect and profile the requests and responses sent over the wire.</span></span> <span data-ttu-id="bd06a-106">有了它，您可以：</span><span class="sxs-lookup"><span data-stu-id="bd06a-106">With it, you can:</span></span>

 - <span data-ttu-id="bd06a-107">浏览该页发出的[所有资源请求的记录](#network-summary)</span><span class="sxs-lookup"><span data-stu-id="bd06a-107">[Browse a record of all the resource requests](#network-summary) made by the page</span></span>
 - <span data-ttu-id="bd06a-108">为新用户和返回的用户[测量您的网站的加载时间](#summary-bar)</span><span class="sxs-lookup"><span data-stu-id="bd06a-108">[Measure the load time of your site](#summary-bar) for new and returning users</span></span> 
 - <span data-ttu-id="bd06a-109">检查页面和网络之间交换[的标题、邮件正文、参数和 cookie](#request-details)</span><span class="sxs-lookup"><span data-stu-id="bd06a-109">[Inspect the headers, message bodies, parameters, and cookies](#request-details) exchanged between your page and the network</span></span>
 - <span data-ttu-id="bd06a-110">在你的网站的加载时间内[识别导致瓶颈的网络事件](#timings)</span><span class="sxs-lookup"><span data-stu-id="bd06a-110">[Identify the network events causing bottlenecks](#timings) in the load time of your site</span></span>

![Microsoft Edge DevTools 网络面板](./media/network.png)

## <span data-ttu-id="bd06a-112">网络摘要</span><span class="sxs-lookup"><span data-stu-id="bd06a-112">Network summary</span></span>

<span data-ttu-id="bd06a-113">打开 DevTools 时，默认情况下，网络分析处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="bd06a-113">When you open  DevTools, network profiling is turned on by default.</span></span> <span data-ttu-id="bd06a-114">即使在与 *网络*不同的 DevTools 面板中工作时，你的活动浏览器选项卡中的所有网络流量都将记录在 "网络摘要" 列表中。</span><span class="sxs-lookup"><span data-stu-id="bd06a-114">All the network traffic from your active browser tab is recorded in the network summary list, even while you are working in a different  DevTools panel than *Network*.</span></span>

![正在进行的网络分析指示器](./media/network_profile_indicator.png)

### <span data-ttu-id="bd06a-116">工具栏</span><span class="sxs-lookup"><span data-stu-id="bd06a-116">Toolbar</span></span>

<span data-ttu-id="bd06a-117">工具栏提供用于分析和筛选页面的网络活动的控件。</span><span class="sxs-lookup"><span data-stu-id="bd06a-117">The toolbar provides controls for profiling and filtering the network activity of your page.</span></span> 

![网络探查器工具栏](./media/network_toolbar.png)

1. <span data-ttu-id="bd06a-119">**启动/停止分析会话**：默认情况下，网络分析处于打开状态，网络流量将记录在 [**网络探查器**](#network-request-list) 列表中。</span><span class="sxs-lookup"><span data-stu-id="bd06a-119">**Start / Stop profiling session**: By default, network profiling is turned on, and network traffic will be logged in the [**Network profiler**](#network-request-list) list.</span></span> <span data-ttu-id="bd06a-120">你可以通过 " **停止** () " 按钮关闭网络捕获 `Ctrl+E` 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-120">You can turn off network capture with the **Stop** (`Ctrl+E`) button.</span></span>

2. <span data-ttu-id="bd06a-121">**导出为 HAR**：您可以将当前的网络分析会话保存 (`Ctrl+S`) 作为 JSON 格式的 [HTTP 存档 (HAR) ](https://dvcs.w3.org/hg/webperf/raw-file/tip/specs/HAR/Overview.html) 文件。</span><span class="sxs-lookup"><span data-stu-id="bd06a-121">**Export as HAR**: You can save the current network profiling session (`Ctrl+S`) as a JSON-formatted [HTTP Archive (HAR)](https://dvcs.w3.org/hg/webperf/raw-file/tip/specs/HAR/Overview.html) file.</span></span> 

3. <span data-ttu-id="bd06a-122">**内容类型筛选**器：按特定内容请求筛选网络请求列表 (*文档、样式表、图像、脚本、媒体、字体、XHR、其他*) 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-122">**Content type filter**: Filter the network request list by specific content requests (*Documents, Style sheets, Images, Scripts, Media, Fonts, XHR, Other*).</span></span> <span data-ttu-id="bd06a-123">默认情况下，显示所有内容类型。</span><span class="sxs-lookup"><span data-stu-id="bd06a-123">By default all content types are shown.</span></span>

4. <span data-ttu-id="bd06a-124">**查找**：筛选 (`Ctrl+F`) 包含指定搜索字符串) 资源路径 (资源名称的网络请求列表。</span><span class="sxs-lookup"><span data-stu-id="bd06a-124">**Find**: Filter (`Ctrl+F`) the network request list by entry names (resource paths) containing a specified search string.</span></span>

5. <span data-ttu-id="bd06a-125">**始终从服务器刷新**：按下此按钮将强制从网络加载页面资源，而不是浏览器缓存。</span><span class="sxs-lookup"><span data-stu-id="bd06a-125">**Always refresh from server**: Depressing this button will force page resources to load from the network rather than the browser cache.</span></span> <span data-ttu-id="bd06a-126">您可以通过按一次即可从网络刷新页面 `Ctrl+F5` 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-126">You can refresh the page from  network a single time by pressing `Ctrl+F5`.</span></span>

6. <span data-ttu-id="bd06a-127">**跳过所有网络请求的服务工作人员**：将已注册的服务工作人员禁用为网络代理。</span><span class="sxs-lookup"><span data-stu-id="bd06a-127">**Bypass Service Worker for all network requests**: Disable your registered service workers as network proxies.</span></span> 

7. <span data-ttu-id="bd06a-128">清除按钮</span><span class="sxs-lookup"><span data-stu-id="bd06a-128">Clear buttons</span></span>

   - <span data-ttu-id="bd06a-129">**清除缓存**：删除浏览器缓存中存储的所有资源 (并模拟加载页面) 的首次体验。</span><span class="sxs-lookup"><span data-stu-id="bd06a-129">**Clear cache**: Removes all resources stored in the browser cache (and emulates a first-time experience loading the page).</span></span>
   - <span data-ttu-id="bd06a-130">**清除 cookie**：删除给定域 (的所有 cookie，并模拟网站) 的首次体验。</span><span class="sxs-lookup"><span data-stu-id="bd06a-130">**Clear cookies**: Removes all cookies for the given domain (and emulates a first-time experience of the site).</span></span>
   - <span data-ttu-id="bd06a-131">**清除导航上的条目**：在页面导航时清除录制的流量。</span><span class="sxs-lookup"><span data-stu-id="bd06a-131">**Clear entries on navigate**: Recorded traffic is cleared upon page navigation.</span></span> <span data-ttu-id="bd06a-132">默认情况下，此项处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="bd06a-132">This is turned on by default.</span></span>
   - <span data-ttu-id="bd06a-133">**清除会话**：从 " **网络摘要** " 列表中清除所有网络请求条目。</span><span class="sxs-lookup"><span data-stu-id="bd06a-133">**Clear session**: Clears all network request entries from the **Network summary** list.</span></span>

### <span data-ttu-id="bd06a-134">网络请求列表</span><span class="sxs-lookup"><span data-stu-id="bd06a-134">Network request list</span></span>

<span data-ttu-id="bd06a-135">所有网络流量都将记录到列表中 (直到在导航、手动清除或 DevTools 关闭) 之前将其清除。</span><span class="sxs-lookup"><span data-stu-id="bd06a-135">All network traffic is recorded to a list (until cleared upon navigation, manually cleared, or  DevTools are closed).</span></span> <span data-ttu-id="bd06a-136">单击任何条目都将打开 [该请求的更详细视图](#request-details)。</span><span class="sxs-lookup"><span data-stu-id="bd06a-136">Clicking on any entry will open a more [detailed view of the request](#request-details).</span></span>

![网络请求列表](./media/network_request_list.png)

<span data-ttu-id="bd06a-138">网络请求列表包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="bd06a-138">The network request list includes the following info:</span></span> 

<span data-ttu-id="bd06a-139">列</span><span class="sxs-lookup"><span data-stu-id="bd06a-139">Column</span></span> | <span data-ttu-id="bd06a-140">描述</span><span class="sxs-lookup"><span data-stu-id="bd06a-140">Description</span></span> 
:------------ | :------------- 
**<span data-ttu-id="bd06a-141">名称</span><span class="sxs-lookup"><span data-stu-id="bd06a-141">Name</span></span>** | <span data-ttu-id="bd06a-142">请求的名称和 URL 路径</span><span class="sxs-lookup"><span data-stu-id="bd06a-142">Name and URL path of the request</span></span>
**<span data-ttu-id="bd06a-143">协议</span><span class="sxs-lookup"><span data-stu-id="bd06a-143">Protocol</span></span>** |  <span data-ttu-id="bd06a-144">请求的协议类型 (如 *HTTPS、HTTP/2*) </span><span class="sxs-lookup"><span data-stu-id="bd06a-144">Type of protocol for the request (such as *HTTPS, HTTP/2*)</span></span>
**<span data-ttu-id="bd06a-145">方法</span><span class="sxs-lookup"><span data-stu-id="bd06a-145">Method</span></span>** |    <span data-ttu-id="bd06a-146">用于请求的[HTTP 方法](https://developer.mozilla.org/docs/Web/HTTP/Methods)</span><span class="sxs-lookup"><span data-stu-id="bd06a-146">[HTTP method](https://developer.mozilla.org/docs/Web/HTTP/Methods) used for the request</span></span>
**<span data-ttu-id="bd06a-147">结果</span><span class="sxs-lookup"><span data-stu-id="bd06a-147">Result</span></span>** |    <span data-ttu-id="bd06a-148">[HTTP 响应状态](https://developer.mozilla.org/docs/Web/HTTP/Status)  代码</span><span class="sxs-lookup"><span data-stu-id="bd06a-148">[HTTP response status](https://developer.mozilla.org/docs/Web/HTTP/Status)  code</span></span>
**<span data-ttu-id="bd06a-149">内容类型</span><span class="sxs-lookup"><span data-stu-id="bd06a-149">Content type</span></span>** |  <span data-ttu-id="bd06a-150"> ([MIME 类型](https://en.wikipedia.org/wiki/Media_type)) 请求的媒体类型</span><span class="sxs-lookup"><span data-stu-id="bd06a-150">Type of media requested ([MIME type](https://en.wikipedia.org/wiki/Media_type))</span></span>
**<span data-ttu-id="bd06a-151">已接收</span><span class="sxs-lookup"><span data-stu-id="bd06a-151">Received</span></span>** | <span data-ttu-id="bd06a-152">服务器发送的响应的大小 (不会为缓存的响应进行计算) </span><span class="sxs-lookup"><span data-stu-id="bd06a-152">Size of the response as delivered by the server (not calculated for cached responses)</span></span>
**<span data-ttu-id="bd06a-153">时间</span><span class="sxs-lookup"><span data-stu-id="bd06a-153">Time</span></span>** |  <span data-ttu-id="bd06a-154">加载服务器响应的时间 (未针对缓存的响应进行计算) </span><span class="sxs-lookup"><span data-stu-id="bd06a-154">Time to load the server response (not calculated for cached responses)</span></span>
**<span data-ttu-id="bd06a-155">启动</span><span class="sxs-lookup"><span data-stu-id="bd06a-155">Initiator</span></span>** | <span data-ttu-id="bd06a-156">负责启动请求的子系统 (*，如分析程序、重定向、脚本、其他*) </span><span class="sxs-lookup"><span data-stu-id="bd06a-156">Subsystem responsible for initiating the request (such as *Parser, Redirect, Script, Other*)</span></span>
**<span data-ttu-id="bd06a-157">时间线</span><span class="sxs-lookup"><span data-stu-id="bd06a-157">Timeline</span></span>** | <span data-ttu-id="bd06a-158">请求的网络事件的可视化日程表 (例如已 *停止、解析 (DNS) 、连接 (TCP) 、SSL、发送、等待 (TTFB) 、下载*) 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-158">Visual timeline for the network events of the request (such as *Stalled, Resolving(DNS), Connecting(TCP), SSL, Sending, Waiting(TTFB), Downloading*).</span></span> <span data-ttu-id="bd06a-159">将鼠标悬停在图表上可提供网络 [网络计时](#timings)) 的粒度明细。</span><span class="sxs-lookup"><span data-stu-id="bd06a-159">Hovering over the chart provides the more granular breakdown of network [network timings](#timings)).</span></span>

### <span data-ttu-id="bd06a-160">摘要栏</span><span class="sxs-lookup"><span data-stu-id="bd06a-160">Summary bar</span></span>

<span data-ttu-id="bd06a-161">**网络**面板底部的栏汇总了网络性能分析会话期间 HTTP 网络错误、请求、传输和加载时间的总数 (也就是说，由于 DevTools 已打开并记录网络流量) 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-161">The bar at the bottom of **Network** panel summarizes the total number of HTTP network errors, requests, data transfered, and load times during the network profiling session (i.e., since  DevTools were opened and recording network traffic).</span></span>

![网络摘要栏](./media/network_summary_bar.png)

<span data-ttu-id="bd06a-163">**经过的时间** 表示分析会话开始与最后一个资源从网络下载之间的时间之间的时间。</span><span class="sxs-lookup"><span data-stu-id="bd06a-163">**Elapsed time** means the time between the start of the profiling session and when the last resource was downloaded from the network.</span></span> <span data-ttu-id="bd06a-164">从浏览器缓存中获取的资源不会计入此数字的时间。</span><span class="sxs-lookup"><span data-stu-id="bd06a-164">Resources fetched from the browser cache do not accrue time to this number.</span></span> 

<span data-ttu-id="bd06a-165">**DOM 加载时间** 表示分析会话开始与触发 [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded) 事件之间的时间，以指示页面文档的结构已加载并分析 (，但不一定任何样式表、图像或 subframes) 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-165">**DOM load time** means the time between the start of the profiling session and when the [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded) event was fired to indicate that the structure of the page document has been loaded and parsed (though not necessarily any stylesheets, images or subframes).</span></span>

<span data-ttu-id="bd06a-166">"**页面加载时间**" 指的是分析会话开始与触发[加载](https://developer.mozilla.org/docs/Web/Events/load)事件之间的时间，以指示页面文档 (并且已完全加载其所有资源) 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-166">**Page load time** time means the time between the start of the profiling session and when the [load](https://developer.mozilla.org/docs/Web/Events/load) event was fired to indicate that the page document (and all its resources) has been fully loaded.</span></span>

## <span data-ttu-id="bd06a-167">请求详细信息</span><span class="sxs-lookup"><span data-stu-id="bd06a-167">Request details</span></span>

<span data-ttu-id="bd06a-168">单击 " [**网络摘要**](#network-summary) " 列表中的任何条目将在 " [**请求详细信息**](#request-details) " 窗格中打开以下每个选项卡中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bd06a-168">Clicking on any entry in the [**Network summary**](#network-summary) list will open the [**Request details**](#request-details) pane with further information in each of the following tabs.</span></span>

![网络请求详细信息窗格](./media/network_request_details.png)

### <span data-ttu-id="bd06a-170">标题</span><span class="sxs-lookup"><span data-stu-id="bd06a-170">Headers</span></span>
<span data-ttu-id="bd06a-171">显示发送到服务器或从服务器接收的 [HTTP 标头](https://developer.mozilla.org/docs/Web/HTTP/Headers) 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-171">Displays the [HTTP headers](https://developer.mozilla.org/docs/Web/HTTP/Headers) sent to and received from the server.</span></span> <span data-ttu-id="bd06a-172">右键单击任意标题条目可将其复制 (`Ctrl+C`) 剪贴板。</span><span class="sxs-lookup"><span data-stu-id="bd06a-172">Right-click on any header entry to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="bd06a-173">你还可以通过按住 `Shift` 键或选择 "所有 (") 来选择多个条目 `Ctrl+A` 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-173">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

### <span data-ttu-id="bd06a-174">正文</span><span class="sxs-lookup"><span data-stu-id="bd06a-174">Body</span></span>
<span data-ttu-id="bd06a-175">如果可用) 请求和响应负载，则显示正文数据 (。</span><span class="sxs-lookup"><span data-stu-id="bd06a-175">Displays the body data (if available) of the request and response payloads.</span></span>

<span data-ttu-id="bd06a-176">图像内容与尺寸和大小数据一起显示。</span><span class="sxs-lookup"><span data-stu-id="bd06a-176">Image content is displayed with dimensions and size data.</span></span>

<span data-ttu-id="bd06a-177">文本内容显示在 (只读) 编辑器中，其中包含使用 **整齐打印** 和/或换 **行** 设置 minified 内容格式的选项，以便更轻松地提高可读性。</span><span class="sxs-lookup"><span data-stu-id="bd06a-177">Text content appears in a (read-only) editor with options to format minified content with **Pretty print** and/or **Word wrap** for easier readability.</span></span>

!["请求详细信息" 窗格的 "正文" 选项卡](./media/network_details_body.png)

### <span data-ttu-id="bd06a-179">参数</span><span class="sxs-lookup"><span data-stu-id="bd06a-179">Parameters</span></span>
<span data-ttu-id="bd06a-180">显示获取请求的查询字符串参数。</span><span class="sxs-lookup"><span data-stu-id="bd06a-180">Displays query string parameters for GET requests.</span></span> <span data-ttu-id="bd06a-181">在标头中发送 POST 请求的参数时，GET 请求将其包含在 URL 中。</span><span class="sxs-lookup"><span data-stu-id="bd06a-181">While the parameters of POST requests are sent in the headers, GET requests include them in the URL.</span></span> <span data-ttu-id="bd06a-182">我们将在此处分解，以便更容易阅读。</span><span class="sxs-lookup"><span data-stu-id="bd06a-182">They're broken out here for easier reading.</span></span>

<span data-ttu-id="bd06a-183">右键单击任意行以将其复制 (`Ctrl+C`) 剪贴板。</span><span class="sxs-lookup"><span data-stu-id="bd06a-183">Right-click on any row to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="bd06a-184">你还可以通过按住 `Shift` 键或选择 "所有 (") 来选择多个条目 `Ctrl+A` 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-184">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

### <span data-ttu-id="bd06a-185">Cookie</span><span class="sxs-lookup"><span data-stu-id="bd06a-185">Cookies</span></span>
<span data-ttu-id="bd06a-186">显示作为键/值对发送或接收的 cookie。</span><span class="sxs-lookup"><span data-stu-id="bd06a-186">Displays cookies that are sent or received as key/value pairs.</span></span>

<span data-ttu-id="bd06a-187">右键单击任意行以将其复制 (`Ctrl+C`) 剪贴板。</span><span class="sxs-lookup"><span data-stu-id="bd06a-187">Right-click on any row to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="bd06a-188">你还可以通过按住 `Shift` 键或选择 "所有 (") 来选择多个条目 `Ctrl+A` 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-188">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

<span data-ttu-id="bd06a-189">你可以从 [工具栏](#network-summary) 中清除所存储的域的 cookie (" **清除 cookie** " 按钮) 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-189">You can clear the stored cookies for the given domain from the [Toolbar](#network-summary) (**Clear cookies** button).</span></span> 

### <span data-ttu-id="bd06a-190">计时</span><span class="sxs-lookup"><span data-stu-id="bd06a-190">Timings</span></span>

<span data-ttu-id="bd06a-191">" **计时** " 选项卡提供加载所选资源所涉及的网络事件的时间线。</span><span class="sxs-lookup"><span data-stu-id="bd06a-191">The **Timings** tab provides a timeline of network events involved in the loading of the selected resource.</span></span> <span data-ttu-id="bd06a-192">这类似于在 "[网络请求" 列表](#network-request-list)的 "*时间线*" 列中找到的信息，但还包括针对通过线路发送的请求所导致的事件，例如在请求队列中等待的时间 (*停止*) 、DNS 解析以及建立 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="bd06a-192">This is similar to the information found in the *Timeline* column of the [Network request list](#network-request-list), but also includes the events leading up to the request being sent over the wire, such as time spent waiting (*Stalled*) in the request queue, DNS resolution, and establishing the TCP connection.</span></span> 

![请求详细信息窗格的 "计时" 选项卡](./media/network_details_timings.png)

<span data-ttu-id="bd06a-194">将注明对其他资源的重定向，然后单击该链接即可将焦点设置到 "网络 [请求详细信息](#request details) " 窗格中的该资源。</span><span class="sxs-lookup"><span data-stu-id="bd06a-194">Redirections to/from other resources are noted, and clicking on the link will set focus to that resource in the network [request details](#request details) pane.</span></span>

<span data-ttu-id="bd06a-195">从缓存中加载的资源不受网络延迟的影响，因此不会显示网络 *计时* 图表。</span><span class="sxs-lookup"><span data-stu-id="bd06a-195">Resouces loaded from the cache are not affected by network latency, so no network *Timings* chart will display.</span></span>

![从缓存加载的重定向资源](./media/network_details_timings_cache_redirect.png)

<span data-ttu-id="bd06a-197">下面是你可能会看到的给定资源的不同网络事件，按时间顺序排列：</span><span class="sxs-lookup"><span data-stu-id="bd06a-197">Here are the different network events you might see for a given resource, in chronological order:</span></span>

#### <span data-ttu-id="bd06a-198">停止</span><span class="sxs-lookup"><span data-stu-id="bd06a-198">Stalled</span></span>

<span data-ttu-id="bd06a-199">等待请求队列中的可用网络连接所用的时间。</span><span class="sxs-lookup"><span data-stu-id="bd06a-199">Time spent waiting for an available network connection in the request queue.</span></span> <span data-ttu-id="bd06a-200">对于 HTTP 1.0/1.1，Microsoft Edge 允许最多6个 (6) 每个主机名的同时 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="bd06a-200">For HTTP 1.0/1.1, Microsoft Edge allows a maximum of six (6) simultaneous TCP connections per hostname.</span></span> 

#### <span data-ttu-id="bd06a-201">解析 (DNS) </span><span class="sxs-lookup"><span data-stu-id="bd06a-201">Resolving (DNS)</span></span>

<span data-ttu-id="bd06a-202">在 DNS ([域名系统](https://en.wikipedia.org/wiki/Domain_Name_System)) 中查找资源的主机名的 IP 地址所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="bd06a-202">Time spent looking up the IP address for the hostname of the resource in the DNS ([Domain Name System](https://en.wikipedia.org/wiki/Domain_Name_System)).</span></span>

#### <span data-ttu-id="bd06a-203">连接 (TCP) </span><span class="sxs-lookup"><span data-stu-id="bd06a-203">Connecting (TCP)</span></span>

<span data-ttu-id="bd06a-204">建立 TCP ([传输控制协议](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)) 连接所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="bd06a-204">Time spent establishing the TCP ([Transmission Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)) connection.</span></span>

#### <span data-ttu-id="bd06a-205">SSL</span><span class="sxs-lookup"><span data-stu-id="bd06a-205">SSL</span></span>

<span data-ttu-id="bd06a-206">与主机的[代理服务器](https://en.wikipedia.org/wiki/Proxy_server)协商 SSL ([安全套接字层](https://en.wikipedia.org/wiki/Transport_Layer_Security)) 连接所用的时间。</span><span class="sxs-lookup"><span data-stu-id="bd06a-206">Time spent negotiating a SSL ([Secure Sockets Layer](https://en.wikipedia.org/wiki/Transport_Layer_Security))  connection with the [proxy server](https://en.wikipedia.org/wiki/Proxy_server) for the host.</span></span>

#### <span data-ttu-id="bd06a-207">给</span><span class="sxs-lookup"><span data-stu-id="bd06a-207">Sending</span></span>

<span data-ttu-id="bd06a-208">发送资源请求所用的时间。</span><span class="sxs-lookup"><span data-stu-id="bd06a-208">Time spent sending the resource request.</span></span>

#### <span data-ttu-id="bd06a-209">正在等待 (TTFB) </span><span class="sxs-lookup"><span data-stu-id="bd06a-209">Waiting (TTFB)</span></span>

<span data-ttu-id="bd06a-210">等待主机服务器响应的第一个字节所用的时间 ( "到首字节的时间" 或 " *TTFB*) "。</span><span class="sxs-lookup"><span data-stu-id="bd06a-210">Time spent waiting for the first byte of the response from the host server ("time to first byte", or *TTFB*).</span></span>

#### <span data-ttu-id="bd06a-211">下载</span><span class="sxs-lookup"><span data-stu-id="bd06a-211">Downloading</span></span>

<span data-ttu-id="bd06a-212">从服务器读取响应所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="bd06a-212">Time spent reading the response from the server.</span></span>

## <span data-ttu-id="bd06a-213">快捷方式</span><span class="sxs-lookup"><span data-stu-id="bd06a-213">Shortcuts</span></span>

| <span data-ttu-id="bd06a-214">操作</span><span class="sxs-lookup"><span data-stu-id="bd06a-214">Action</span></span>                         | <span data-ttu-id="bd06a-215">快捷方式</span><span class="sxs-lookup"><span data-stu-id="bd06a-215">Shortcut</span></span>     |
|:-------------------------------|:-------------|
| <span data-ttu-id="bd06a-216">开始/停止分析会话</span><span class="sxs-lookup"><span data-stu-id="bd06a-216">Start / Stop profiling session</span></span> | `Ctrl` + `E` |
| <span data-ttu-id="bd06a-217">导出为 HAR</span><span class="sxs-lookup"><span data-stu-id="bd06a-217">Export as HAR</span></span>                  | `Ctrl` + `S` |
| <span data-ttu-id="bd06a-218">查找</span><span class="sxs-lookup"><span data-stu-id="bd06a-218">Find</span></span>                           | `Ctrl` + `F` |
| <span data-ttu-id="bd06a-219">复制</span><span class="sxs-lookup"><span data-stu-id="bd06a-219">Copy</span></span>                           | `Ctrl` + `C` |

## <span data-ttu-id="bd06a-220">已知问题</span><span class="sxs-lookup"><span data-stu-id="bd06a-220">Known Issues</span></span>

### <span data-ttu-id="bd06a-221">网络收集代理无法启动。</span><span class="sxs-lookup"><span data-stu-id="bd06a-221">The network collection agent failed to start.</span></span>

<span data-ttu-id="bd06a-222">如果您看到此错误消息： **网络收集代理无法** 在网络工具中启动，请按照以下步骤进行解决。</span><span class="sxs-lookup"><span data-stu-id="bd06a-222">If you see this error message: **The network collection agent failed to start** in the Network tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="bd06a-223">按 `Windows Key`  +  `R` 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-223">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="bd06a-224">在 "运行" 对话框中，输入 **services.msc**。</span><span class="sxs-lookup"><span data-stu-id="bd06a-224">In the Run dialog, enter **services.msc**.</span></span>
![已知问题-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="bd06a-226">找到 **Microsoft (R) 诊断中心标准收集器服务** ，然后右键单击它。</span><span class="sxs-lookup"><span data-stu-id="bd06a-226">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![已知问题-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="bd06a-228">重新启动 **Microsoft (R) 诊断中心标准收集器服务**。</span><span class="sxs-lookup"><span data-stu-id="bd06a-228">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![已知问题-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="bd06a-230">关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到您的页面，然后按 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-230">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="bd06a-231">现在，你应该可以在 **网络** 和你的网页的网络请求旁边看到一个播放标记。</span><span class="sxs-lookup"><span data-stu-id="bd06a-231">You should now see a Play badge next to **Network** and the network requests for your webpage.</span></span>
![已知问题-4](./media/known_issues_4-network.PNG)

<span data-ttu-id="bd06a-233">仍遇到问题？</span><span class="sxs-lookup"><span data-stu-id="bd06a-233">Still running into problems?</span></span> <span data-ttu-id="bd06a-234">请使用 " **发送反馈** " 图标向我们发送您的反馈！</span><span class="sxs-lookup"><span data-stu-id="bd06a-234">Please send us your feedback using the **Send feedback** icon!</span></span> 

![已知问题-5](./media/known_issues_5.PNG)

### <span data-ttu-id="bd06a-236">网络收集代理无法停止。</span><span class="sxs-lookup"><span data-stu-id="bd06a-236">The network collection agent failed to stop.</span></span>

<span data-ttu-id="bd06a-237">如果您看到此错误消息： **网络收集代理无法** 在网络工具中停止，请按照以下步骤进行解决。</span><span class="sxs-lookup"><span data-stu-id="bd06a-237">If you see this error message: **The network collection agent failed to stop** in the Network tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="bd06a-238">按 `Windows Key`  +  `R` 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-238">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="bd06a-239">在 "运行" 对话框中，输入 **services.msc**。</span><span class="sxs-lookup"><span data-stu-id="bd06a-239">In the Run dialog, enter **services.msc**.</span></span>
![已知问题-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="bd06a-241">找到 **Microsoft (R) 诊断中心标准收集器服务** ，然后右键单击它。</span><span class="sxs-lookup"><span data-stu-id="bd06a-241">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![已知问题-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="bd06a-243">重新启动 **Microsoft (R) 诊断中心标准收集器服务**。</span><span class="sxs-lookup"><span data-stu-id="bd06a-243">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![已知问题-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="bd06a-245">关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到您的页面，然后按 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="bd06a-245">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="bd06a-246">现在，你应该可以在 **网络** 和你的网页的网络请求旁边看到一个播放标记。</span><span class="sxs-lookup"><span data-stu-id="bd06a-246">You should now see a Play badge next to **Network** and the network requests for your webpage.</span></span>
![已知问题-4](./media/known_issues_4-network.PNG)

<span data-ttu-id="bd06a-248">仍遇到问题？</span><span class="sxs-lookup"><span data-stu-id="bd06a-248">Still running into problems?</span></span> <span data-ttu-id="bd06a-249">请使用 " **发送反馈** " 图标向我们发送您的反馈！</span><span class="sxs-lookup"><span data-stu-id="bd06a-249">Please send us your feedback using the **Send feedback** icon!</span></span> 

![已知问题-5](./media/known_issues_5.PNG)
