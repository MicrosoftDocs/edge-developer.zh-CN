---
description: 使用"网络"面板监视和配置文件页资源请求
title: DevTools - 网络
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 网络， 加载时间， http， https， 浏览器缓存， HAR
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 261226c7210d978f11290816c81355bb0142dee9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232492"
---
# <span data-ttu-id="f7d36-104">Network</span><span class="sxs-lookup"><span data-stu-id="f7d36-104">Network</span></span>

<span data-ttu-id="f7d36-105">使用 **网络** 面板监视、检查和配置文件通过线路发送的请求和响应。</span><span class="sxs-lookup"><span data-stu-id="f7d36-105">Use the **Network** panel to monitor, inspect and profile the requests and responses sent over the wire.</span></span> <span data-ttu-id="f7d36-106">通过它，你可以：</span><span class="sxs-lookup"><span data-stu-id="f7d36-106">With it, you can:</span></span>

 - <span data-ttu-id="f7d36-107">[浏览页面提出的所有](#network-summary) 资源请求的记录</span><span class="sxs-lookup"><span data-stu-id="f7d36-107">[Browse a record of all the resource requests](#network-summary) made by the page</span></span>
 - <span data-ttu-id="f7d36-108">[测量新用户和](#summary-bar) 返回用户的网站的加载时间</span><span class="sxs-lookup"><span data-stu-id="f7d36-108">[Measure the load time of your site](#summary-bar) for new and returning users</span></span> 
 - <span data-ttu-id="f7d36-109">[检查页面和网络之间](#request-details) 交换的标头、邮件正文、参数和 Cookie</span><span class="sxs-lookup"><span data-stu-id="f7d36-109">[Inspect the headers, message bodies, parameters, and cookies](#request-details) exchanged between your page and the network</span></span>
 - <span data-ttu-id="f7d36-110">[确定在站点的加载时间](#timings) 导致瓶颈的网络事件</span><span class="sxs-lookup"><span data-stu-id="f7d36-110">[Identify the network events causing bottlenecks](#timings) in the load time of your site</span></span>

![Microsoft Edge DevTools 网络面板](./media/network.png)

## <span data-ttu-id="f7d36-112">网络摘要</span><span class="sxs-lookup"><span data-stu-id="f7d36-112">Network summary</span></span>

<span data-ttu-id="f7d36-113">打开 DevTools 时，网络分析默认打开。</span><span class="sxs-lookup"><span data-stu-id="f7d36-113">When you open  DevTools, network profiling is turned on by default.</span></span> <span data-ttu-id="f7d36-114">来自活动浏览器选项卡的所有网络流量都记录在网络摘要列表中，即使你在不同的 DevTools 面板中工作，而不是 *网络*。</span><span class="sxs-lookup"><span data-stu-id="f7d36-114">All the network traffic from your active browser tab is recorded in the network summary list, even while you are working in a different  DevTools panel than *Network*.</span></span>

![进行中的网络分析指示器](./media/network_profile_indicator.png)

### <span data-ttu-id="f7d36-116">工具栏</span><span class="sxs-lookup"><span data-stu-id="f7d36-116">Toolbar</span></span>

<span data-ttu-id="f7d36-117">工具栏提供用于分析和筛选页面的网络活动的控件。</span><span class="sxs-lookup"><span data-stu-id="f7d36-117">The toolbar provides controls for profiling and filtering the network activity of your page.</span></span> 

![网络探查器工具栏](./media/network_toolbar.png)

1. <span data-ttu-id="f7d36-119">**开始/停止分析会话**：默认情况下，网络分析已打开，网络流量将记录在 [**网络分析器**](#network-request-list) 列表中。</span><span class="sxs-lookup"><span data-stu-id="f7d36-119">**Start / Stop profiling session**: By default, network profiling is turned on, and network traffic will be logged in the [**Network profiler**](#network-request-list) list.</span></span> <span data-ttu-id="f7d36-120">你可以关闭网络捕获，并按" 停止 `Ctrl+E` () 按钮。</span><span class="sxs-lookup"><span data-stu-id="f7d36-120">You can turn off network capture with the **Stop** (`Ctrl+E`) button.</span></span>

2. <span data-ttu-id="f7d36-121">**导出为 HAR：** 可以将当前网络分析会话 () 为 JSON 格式的 HTTP 存档 (`Ctrl+S` HAR [) ](https://dvcs.w3.org/hg/webperf/raw-file/tip/specs/HAR/Overview.html) 文件。</span><span class="sxs-lookup"><span data-stu-id="f7d36-121">**Export as HAR**: You can save the current network profiling session (`Ctrl+S`) as a JSON-formatted [HTTP Archive (HAR)](https://dvcs.w3.org/hg/webperf/raw-file/tip/specs/HAR/Overview.html) file.</span></span> 

3. <span data-ttu-id="f7d36-122">**内容类型筛选器**：按特定内容请求筛选网络请求列表 (文档、样式表、图像、脚本、 *媒体、字体、XHR、其他*) 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-122">**Content type filter**: Filter the network request list by specific content requests (*Documents, Style sheets, Images, Scripts, Media, Fonts, XHR, Other*).</span></span> <span data-ttu-id="f7d36-123">默认情况下，将显示所有内容类型。</span><span class="sxs-lookup"><span data-stu-id="f7d36-123">By default all content types are shown.</span></span>

4. <span data-ttu-id="f7d36-124">**Find**： Filter () list `Ctrl+F` by entry names (resource paths) containing a specified search string.</span><span class="sxs-lookup"><span data-stu-id="f7d36-124">**Find**: Filter (`Ctrl+F`) the network request list by entry names (resource paths) containing a specified search string.</span></span>

5. <span data-ttu-id="f7d36-125">**始终从服务器刷新**：按下此按钮将强制从网络而不是浏览器缓存加载页面资源。</span><span class="sxs-lookup"><span data-stu-id="f7d36-125">**Always refresh from server**: Depressing this button will force page resources to load from the network rather than the browser cache.</span></span> <span data-ttu-id="f7d36-126">可以通过按从网络刷新页面一次 `Ctrl+F5` 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-126">You can refresh the page from  network a single time by pressing `Ctrl+F5`.</span></span>

6. <span data-ttu-id="f7d36-127">**针对所有网络请求绕过**服务工作线程：禁用注册的服务工作者作为网络代理。</span><span class="sxs-lookup"><span data-stu-id="f7d36-127">**Bypass Service Worker for all network requests**: Disable your registered service workers as network proxies.</span></span> 

7. <span data-ttu-id="f7d36-128">清除按钮</span><span class="sxs-lookup"><span data-stu-id="f7d36-128">Clear buttons</span></span>

   - <span data-ttu-id="f7d36-129">**清除缓存**：删除浏览器缓存中存储的所有 (并模拟在浏览器中加载页面的首次) 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-129">**Clear cache**: Removes all resources stored in the browser cache (and emulates a first-time experience loading the page).</span></span>
   - <span data-ttu-id="f7d36-130">**清除 Cookie：** 删除给定域的所有 cookie (并模拟网站集的首次) 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-130">**Clear cookies**: Removes all cookies for the given domain (and emulates a first-time experience of the site).</span></span>
   - <span data-ttu-id="f7d36-131">**导航时清除条目**：在页面导航时清除记录的流量。</span><span class="sxs-lookup"><span data-stu-id="f7d36-131">**Clear entries on navigate**: Recorded traffic is cleared upon page navigation.</span></span> <span data-ttu-id="f7d36-132">默认情况下，此选项为打开状态。</span><span class="sxs-lookup"><span data-stu-id="f7d36-132">This is turned on by default.</span></span>
   - <span data-ttu-id="f7d36-133">**清除会话**：清除网络摘要列表中的所有 **网络请求** 条目。</span><span class="sxs-lookup"><span data-stu-id="f7d36-133">**Clear session**: Clears all network request entries from the **Network summary** list.</span></span>

### <span data-ttu-id="f7d36-134">网络请求列表</span><span class="sxs-lookup"><span data-stu-id="f7d36-134">Network request list</span></span>

<span data-ttu-id="f7d36-135">所有网络流量将记录到列表中 (，直到导航、手动清除或开发人员工具关闭) 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-135">All network traffic is recorded to a list (until cleared upon navigation, manually cleared, or  DevTools are closed).</span></span> <span data-ttu-id="f7d36-136">单击任何条目将打开请求 [的更详细的视图](#request-details)。</span><span class="sxs-lookup"><span data-stu-id="f7d36-136">Clicking on any entry will open a more [detailed view of the request](#request-details).</span></span>

![网络请求列表](./media/network_request_list.png)

<span data-ttu-id="f7d36-138">网络请求列表包括以下信息：</span><span class="sxs-lookup"><span data-stu-id="f7d36-138">The network request list includes the following info:</span></span> 

<span data-ttu-id="f7d36-139">列</span><span class="sxs-lookup"><span data-stu-id="f7d36-139">Column</span></span> | <span data-ttu-id="f7d36-140">说明</span><span class="sxs-lookup"><span data-stu-id="f7d36-140">Description</span></span> 
:------------ | :------------- 
**<span data-ttu-id="f7d36-141">名称</span><span class="sxs-lookup"><span data-stu-id="f7d36-141">Name</span></span>** | <span data-ttu-id="f7d36-142">请求的名称和 URL 路径</span><span class="sxs-lookup"><span data-stu-id="f7d36-142">Name and URL path of the request</span></span>
**<span data-ttu-id="f7d36-143">协议</span><span class="sxs-lookup"><span data-stu-id="f7d36-143">Protocol</span></span>** |  <span data-ttu-id="f7d36-144">请求服务器的协议类型 (*如 HTTPS、HTTP/2*) </span><span class="sxs-lookup"><span data-stu-id="f7d36-144">Type of protocol for the request (such as *HTTPS, HTTP/2*)</span></span>
**<span data-ttu-id="f7d36-145">方法</span><span class="sxs-lookup"><span data-stu-id="f7d36-145">Method</span></span>** |    <span data-ttu-id="f7d36-146">[用于请求](https://developer.mozilla.org/docs/Web/HTTP/Methods) 的 HTTP 方法</span><span class="sxs-lookup"><span data-stu-id="f7d36-146">[HTTP method](https://developer.mozilla.org/docs/Web/HTTP/Methods) used for the request</span></span>
**<span data-ttu-id="f7d36-147">结果</span><span class="sxs-lookup"><span data-stu-id="f7d36-147">Result</span></span>** |    <span data-ttu-id="f7d36-148">[HTTP 响应状态](https://developer.mozilla.org/docs/Web/HTTP/Status)  代码</span><span class="sxs-lookup"><span data-stu-id="f7d36-148">[HTTP response status](https://developer.mozilla.org/docs/Web/HTTP/Status)  code</span></span>
**<span data-ttu-id="f7d36-149">内容类型</span><span class="sxs-lookup"><span data-stu-id="f7d36-149">Content type</span></span>** |  <span data-ttu-id="f7d36-150">MIME 类型 ([请求的媒体](https://en.wikipedia.org/wiki/Media_type)) </span><span class="sxs-lookup"><span data-stu-id="f7d36-150">Type of media requested ([MIME type](https://en.wikipedia.org/wiki/Media_type))</span></span>
**<span data-ttu-id="f7d36-151">已接收</span><span class="sxs-lookup"><span data-stu-id="f7d36-151">Received</span></span>** | <span data-ttu-id="f7d36-152">未针对缓存响应 (服务器传递的响应大小) </span><span class="sxs-lookup"><span data-stu-id="f7d36-152">Size of the response as delivered by the server (not calculated for cached responses)</span></span>
**<span data-ttu-id="f7d36-153">时间</span><span class="sxs-lookup"><span data-stu-id="f7d36-153">Time</span></span>** |  <span data-ttu-id="f7d36-154">未为缓存的响应 (加载服务器响应) </span><span class="sxs-lookup"><span data-stu-id="f7d36-154">Time to load the server response (not calculated for cached responses)</span></span>
**<span data-ttu-id="f7d36-155">发起人</span><span class="sxs-lookup"><span data-stu-id="f7d36-155">Initiator</span></span>** | <span data-ttu-id="f7d36-156">负责启动请求请求的子系统 (分析器、重定向、 *脚本、其他*) </span><span class="sxs-lookup"><span data-stu-id="f7d36-156">Subsystem responsible for initiating the request (such as *Parser, Redirect, Script, Other*)</span></span>
**<span data-ttu-id="f7d36-157">时间线</span><span class="sxs-lookup"><span data-stu-id="f7d36-157">Timeline</span></span>** | <span data-ttu-id="f7d36-158">请求 (的网络事件的可视时间线，例如停止、解析 (*DNS) 、连接 (TCP) 、SSL、发送、等待 (TTFB) 、* 下载) 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-158">Visual timeline for the network events of the request (such as *Stalled, Resolving(DNS), Connecting(TCP), SSL, Sending, Waiting(TTFB), Downloading*).</span></span> <span data-ttu-id="f7d36-159">将鼠标悬停在图表上可更精细地细分网络[](#timings)) 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-159">Hovering over the chart provides the more granular breakdown of network [network timings](#timings)).</span></span>

### <span data-ttu-id="f7d36-160">摘要栏</span><span class="sxs-lookup"><span data-stu-id="f7d36-160">Summary bar</span></span>

<span data-ttu-id="f7d36-161">网络面板底部的栏汇总了 网络分析会话期间 HTTP 网络错误、请求、传输的数据和加载时间的总次数 (即，自 DevTools 打开并记录网络流量) 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-161">The bar at the bottom of **Network** panel summarizes the total number of HTTP network errors, requests, data transfered, and load times during the network profiling session (i.e., since  DevTools were opened and recording network traffic).</span></span>

![网络摘要栏](./media/network_summary_bar.png)

<span data-ttu-id="f7d36-163">**已用** 时间是指从分析会话开始到从网络下载最后一个资源之间的时间。</span><span class="sxs-lookup"><span data-stu-id="f7d36-163">**Elapsed time** means the time between the start of the profiling session and when the last resource was downloaded from the network.</span></span> <span data-ttu-id="f7d36-164">从浏览器缓存获取的资源不会为此数字累算时间。</span><span class="sxs-lookup"><span data-stu-id="f7d36-164">Resources fetched from the browser cache do not accrue time to this number.</span></span> 

<span data-ttu-id="f7d36-165">**DOM** 加载时间是指从分析会话开始到 [触发 DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded) 事件以指示页面文档的结构已加载和分析 (但不必是任何样式表、图像或子框架) 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-165">**DOM load time** means the time between the start of the profiling session and when the [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded) event was fired to indicate that the structure of the page document has been loaded and parsed (though not necessarily any stylesheets, images or subframes).</span></span>

<span data-ttu-id="f7d36-166"> 页面加载时间是指从分析会话开始到触发加载事件以指示页面文档已完全[](https://developer.mozilla.org/docs/Web/Events/load)加载 (及其所有资源) 的时间。</span><span class="sxs-lookup"><span data-stu-id="f7d36-166">**Page load time** time means the time between the start of the profiling session and when the [load](https://developer.mozilla.org/docs/Web/Events/load) event was fired to indicate that the page document (and all its resources) has been fully loaded.</span></span>

## <span data-ttu-id="f7d36-167">请求详细信息</span><span class="sxs-lookup"><span data-stu-id="f7d36-167">Request details</span></span>

<span data-ttu-id="f7d36-168">单击"网络摘要"列表中的[**任何**](#network-summary)条目将打开"请求详细信息[](#request-details)"窗格，并包含以下每个选项卡中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f7d36-168">Clicking on any entry in the [**Network summary**](#network-summary) list will open the [**Request details**](#request-details) pane with further information in each of the following tabs.</span></span>

![网络请求详细信息窗格](./media/network_request_details.png)

### <span data-ttu-id="f7d36-170">标题</span><span class="sxs-lookup"><span data-stu-id="f7d36-170">Headers</span></span>
<span data-ttu-id="f7d36-171">显示 [发送到服务器](https://developer.mozilla.org/docs/Web/HTTP/Headers) 和从服务器接收的 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="f7d36-171">Displays the [HTTP headers](https://developer.mozilla.org/docs/Web/HTTP/Headers) sent to and received from the server.</span></span> <span data-ttu-id="f7d36-172">右键单击任何标题项，将其 `Ctrl+C` () 剪贴板。</span><span class="sxs-lookup"><span data-stu-id="f7d36-172">Right-click on any header entry to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="f7d36-173">也可以按住该键或选择所有项目，以多选 `Shift` `Ctrl+A` () 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-173">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

### <span data-ttu-id="f7d36-174">正文</span><span class="sxs-lookup"><span data-stu-id="f7d36-174">Body</span></span>
<span data-ttu-id="f7d36-175">显示正文数据 (（如果) 有效负载）。</span><span class="sxs-lookup"><span data-stu-id="f7d36-175">Displays the body data (if available) of the request and response payloads.</span></span>

<span data-ttu-id="f7d36-176">图像内容随尺寸和大小数据一起显示。</span><span class="sxs-lookup"><span data-stu-id="f7d36-176">Image content is displayed with dimensions and size data.</span></span>

<span data-ttu-id="f7d36-177">文本内容显示在只读 (编辑器中，) 选项来设置缩小内容 **的格式，并** 打印和/或 **Word** 自动换行，以便于可读性。</span><span class="sxs-lookup"><span data-stu-id="f7d36-177">Text content appears in a (read-only) editor with options to format minified content with **Pretty print** and/or **Word wrap** for easier readability.</span></span>

![请求详细信息窗格的"正文"选项卡](./media/network_details_body.png)

### <span data-ttu-id="f7d36-179">参数</span><span class="sxs-lookup"><span data-stu-id="f7d36-179">Parameters</span></span>
<span data-ttu-id="f7d36-180">显示 GET 请求的查询字符串参数。</span><span class="sxs-lookup"><span data-stu-id="f7d36-180">Displays query string parameters for GET requests.</span></span> <span data-ttu-id="f7d36-181">当 POST 请求的参数在标头中发送时，GET 请求会将它们包括在 URL 中。</span><span class="sxs-lookup"><span data-stu-id="f7d36-181">While the parameters of POST requests are sent in the headers, GET requests include them in the URL.</span></span> <span data-ttu-id="f7d36-182">它们在此处进行细分以便于阅读。</span><span class="sxs-lookup"><span data-stu-id="f7d36-182">They're broken out here for easier reading.</span></span>

<span data-ttu-id="f7d36-183">右键单击任何行以将其 `Ctrl+C` () 剪贴板。</span><span class="sxs-lookup"><span data-stu-id="f7d36-183">Right-click on any row to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="f7d36-184">也可以按住该键或选择所有项目，以多选 `Shift` `Ctrl+A` () 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-184">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

### <span data-ttu-id="f7d36-185">Cookie</span><span class="sxs-lookup"><span data-stu-id="f7d36-185">Cookies</span></span>
<span data-ttu-id="f7d36-186">显示为键/值对发送或接收的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="f7d36-186">Displays cookies that are sent or received as key/value pairs.</span></span>

<span data-ttu-id="f7d36-187">右键单击任何行以将其 `Ctrl+C` () 剪贴板。</span><span class="sxs-lookup"><span data-stu-id="f7d36-187">Right-click on any row to copy it (`Ctrl+C`) to the clipboard.</span></span> <span data-ttu-id="f7d36-188">也可以按住该键或选择所有项目，以多选 `Shift` `Ctrl+A` () 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-188">You can also multi-select entries by holding down the `Shift` key or select all (`Ctrl+A`).</span></span>

<span data-ttu-id="f7d36-189">You can clear the stored cookie for the given domain from the [Toolbar](#network-summary) (**Clear cookies** button) .</span><span class="sxs-lookup"><span data-stu-id="f7d36-189">You can clear the stored cookies for the given domain from the [Toolbar](#network-summary) (**Clear cookies** button).</span></span> 

### <span data-ttu-id="f7d36-190">计时</span><span class="sxs-lookup"><span data-stu-id="f7d36-190">Timings</span></span>

<span data-ttu-id="f7d36-191">The **Timings** tab provides a timeline of network events involved in the loading of the selected resource.</span><span class="sxs-lookup"><span data-stu-id="f7d36-191">The **Timings** tab provides a timeline of network events involved in the loading of the selected resource.</span></span> <span data-ttu-id="f7d36-192">这类似于在网络请求列表的"日程表\**"列中找到的信息[](#network-request-list)，还包括导致通过线路发送请求的事件，例如等待请求队列中的 (*Stalled\*) 、DNS 解析和建立 TCP 连接所花的时间。</span><span class="sxs-lookup"><span data-stu-id="f7d36-192">This is similar to the information found in the *Timeline* column of the [Network request list](#network-request-list), but also includes the events leading up to the request being sent over the wire, such as time spent waiting (*Stalled*) in the request queue, DNS resolution, and establishing the TCP connection.</span></span> 

![请求详细信息窗格的"计时"选项卡](./media/network_details_timings.png)

<span data-ttu-id="f7d36-194">将指出重定向到其他资源/从其他资源重定向到其他资源，单击链接将在网络请求详细信息窗格中将焦点设置为 [该](#request details) 资源。</span><span class="sxs-lookup"><span data-stu-id="f7d36-194">Redirections to/from other resources are noted, and clicking on the link will set focus to that resource in the network [request details](#request details) pane.</span></span>

<span data-ttu-id="f7d36-195">从缓存加载的资源不受网络延迟的影响，因此不会显示 *任何网络计时* 图表。</span><span class="sxs-lookup"><span data-stu-id="f7d36-195">Resouces loaded from the cache are not affected by network latency, so no network *Timings* chart will display.</span></span>

![从缓存加载的重定向资源](./media/network_details_timings_cache_redirect.png)

<span data-ttu-id="f7d36-197">以下是你可能为给定资源看到的不同网络事件，按时间顺序排序：</span><span class="sxs-lookup"><span data-stu-id="f7d36-197">Here are the different network events you might see for a given resource, in chronological order:</span></span>

#### <span data-ttu-id="f7d36-198">已停止</span><span class="sxs-lookup"><span data-stu-id="f7d36-198">Stalled</span></span>

<span data-ttu-id="f7d36-199">等待请求队列中的可用网络连接所花的时间。</span><span class="sxs-lookup"><span data-stu-id="f7d36-199">Time spent waiting for an available network connection in the request queue.</span></span> <span data-ttu-id="f7d36-200">对于 HTTP 1.0/1.1，Microsoft Edge 允许每个主机名 (6) TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="f7d36-200">For HTTP 1.0/1.1, Microsoft Edge allows a maximum of six (6) simultaneous TCP connections per hostname.</span></span> 

#### <span data-ttu-id="f7d36-201">解析 (DNS) </span><span class="sxs-lookup"><span data-stu-id="f7d36-201">Resolving (DNS)</span></span>

<span data-ttu-id="f7d36-202">在 DNS 或域名系统服务中查找资源的主机名 ([IP](https://en.wikipedia.org/wiki/Domain_Name_System)) 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-202">Time spent looking up the IP address for the hostname of the resource in the DNS ([Domain Name System](https://en.wikipedia.org/wiki/Domain_Name_System)).</span></span>

#### <span data-ttu-id="f7d36-203">连接 (TCP) </span><span class="sxs-lookup"><span data-stu-id="f7d36-203">Connecting (TCP)</span></span>

<span data-ttu-id="f7d36-204">建立 TCP 传输控制协议 ([连接](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)) 的时间。</span><span class="sxs-lookup"><span data-stu-id="f7d36-204">Time spent establishing the TCP ([Transmission Control Protocol](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)) connection.</span></span>

#### <span data-ttu-id="f7d36-205">SSL</span><span class="sxs-lookup"><span data-stu-id="f7d36-205">SSL</span></span>

<span data-ttu-id="f7d36-206">与主机的代理服务器 ([安全套接字层) ](https://en.wikipedia.org/wiki/Transport_Layer_Security) SSL [协议所](https://en.wikipedia.org/wiki/Proxy_server) 花的时间。</span><span class="sxs-lookup"><span data-stu-id="f7d36-206">Time spent negotiating a SSL ([Secure Sockets Layer](https://en.wikipedia.org/wiki/Transport_Layer_Security))  connection with the [proxy server](https://en.wikipedia.org/wiki/Proxy_server) for the host.</span></span>

#### <span data-ttu-id="f7d36-207">发送</span><span class="sxs-lookup"><span data-stu-id="f7d36-207">Sending</span></span>

<span data-ttu-id="f7d36-208">发送资源请求所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="f7d36-208">Time spent sending the resource request.</span></span>

#### <span data-ttu-id="f7d36-209">等待 (TTFB) </span><span class="sxs-lookup"><span data-stu-id="f7d36-209">Waiting (TTFB)</span></span>

<span data-ttu-id="f7d36-210">等待主机服务器响应的第一个字节 ("第一个字节的时间"或 *TTFB*) 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-210">Time spent waiting for the first byte of the response from the host server ("time to first byte", or *TTFB*).</span></span>

#### <span data-ttu-id="f7d36-211">下载</span><span class="sxs-lookup"><span data-stu-id="f7d36-211">Downloading</span></span>

<span data-ttu-id="f7d36-212">从服务器读取响应所花的时间。</span><span class="sxs-lookup"><span data-stu-id="f7d36-212">Time spent reading the response from the server.</span></span>

## <span data-ttu-id="f7d36-213">快捷方式</span><span class="sxs-lookup"><span data-stu-id="f7d36-213">Shortcuts</span></span>

| <span data-ttu-id="f7d36-214">操作</span><span class="sxs-lookup"><span data-stu-id="f7d36-214">Action</span></span>                         | <span data-ttu-id="f7d36-215">快捷方式</span><span class="sxs-lookup"><span data-stu-id="f7d36-215">Shortcut</span></span>     |
|:-------------------------------|:-------------|
| <span data-ttu-id="f7d36-216">启动/停止分析会话</span><span class="sxs-lookup"><span data-stu-id="f7d36-216">Start / Stop profiling session</span></span> | `Ctrl` + `E` |
| <span data-ttu-id="f7d36-217">导出为 HAR</span><span class="sxs-lookup"><span data-stu-id="f7d36-217">Export as HAR</span></span>                  | `Ctrl` + `S` |
| <span data-ttu-id="f7d36-218">查找</span><span class="sxs-lookup"><span data-stu-id="f7d36-218">Find</span></span>                           | `Ctrl` + `F` |
| <span data-ttu-id="f7d36-219">复制</span><span class="sxs-lookup"><span data-stu-id="f7d36-219">Copy</span></span>                           | `Ctrl` + `C` |

## <span data-ttu-id="f7d36-220">已知问题</span><span class="sxs-lookup"><span data-stu-id="f7d36-220">Known Issues</span></span>

### <span data-ttu-id="f7d36-221">网络集合代理启动失败。</span><span class="sxs-lookup"><span data-stu-id="f7d36-221">The network collection agent failed to start.</span></span>

<span data-ttu-id="f7d36-222">如果看到以下错误消息： **网络收集** 代理在网络工具中启动失败，请按照以下步骤获取解决方法。</span><span class="sxs-lookup"><span data-stu-id="f7d36-222">If you see this error message: **The network collection agent failed to start** in the Network tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="f7d36-223">按 `Windows Key`  +  `R` 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-223">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="f7d36-224">在"运行"对话框中，输入**services.msc。**</span><span class="sxs-lookup"><span data-stu-id="f7d36-224">In the Run dialog, enter **services.msc**.</span></span>
![known-issues-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="f7d36-226">找到 **Microsoft (R) 诊断中心标准收集器服务** 并右键单击它。</span><span class="sxs-lookup"><span data-stu-id="f7d36-226">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![known-issues-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="f7d36-228">重新启动 **Microsoft (R) 诊断中心标准收集器服务**。</span><span class="sxs-lookup"><span data-stu-id="f7d36-228">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![known-issues-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="f7d36-230">关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到页面，然后按 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-230">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="f7d36-231">现在，应该会看到"网络"旁边的" 播放"锁屏提醒和网页的网络请求。</span><span class="sxs-lookup"><span data-stu-id="f7d36-231">You should now see a Play badge next to **Network** and the network requests for your webpage.</span></span>
![known-issues-4](./media/known_issues_4-network.PNG)

<span data-ttu-id="f7d36-233">是否仍遇到问题？</span><span class="sxs-lookup"><span data-stu-id="f7d36-233">Still running into problems?</span></span> <span data-ttu-id="f7d36-234">请使用"发送反馈"图标 **向我们发送反馈** ！</span><span class="sxs-lookup"><span data-stu-id="f7d36-234">Please send us your feedback using the **Send feedback** icon!</span></span> 

![known-issues-5](./media/known_issues_5.PNG)

### <span data-ttu-id="f7d36-236">网络集合代理停止失败。</span><span class="sxs-lookup"><span data-stu-id="f7d36-236">The network collection agent failed to stop.</span></span>

<span data-ttu-id="f7d36-237">如果看到以下错误消息： **网络收集代理** 在网络工具中停止失败，请按照以下步骤获取解决方法。</span><span class="sxs-lookup"><span data-stu-id="f7d36-237">If you see this error message: **The network collection agent failed to stop** in the Network tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="f7d36-238">按 `Windows Key`  +  `R` 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-238">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="f7d36-239">在"运行"对话框中，输入**services.msc。**</span><span class="sxs-lookup"><span data-stu-id="f7d36-239">In the Run dialog, enter **services.msc**.</span></span>
![known-issues-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="f7d36-241">找到 **Microsoft (R) 诊断中心标准收集器服务** 并右键单击它。</span><span class="sxs-lookup"><span data-stu-id="f7d36-241">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![known-issues-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="f7d36-243">重新启动 **Microsoft (R) 诊断中心标准收集器服务**。</span><span class="sxs-lookup"><span data-stu-id="f7d36-243">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![known-issues-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="f7d36-245">关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到页面，然后按 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="f7d36-245">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="f7d36-246">现在，应该会看到"网络"旁边的" 播放"锁屏提醒和网页的网络请求。</span><span class="sxs-lookup"><span data-stu-id="f7d36-246">You should now see a Play badge next to **Network** and the network requests for your webpage.</span></span>
![known-issues-4](./media/known_issues_4-network.PNG)

<span data-ttu-id="f7d36-248">是否仍遇到问题？</span><span class="sxs-lookup"><span data-stu-id="f7d36-248">Still running into problems?</span></span> <span data-ttu-id="f7d36-249">请使用"发送反馈"图标 **向我们发送反馈** ！</span><span class="sxs-lookup"><span data-stu-id="f7d36-249">Please send us your feedback using the **Send feedback** icon!</span></span> 

![known-issues-5](./media/known_issues_5.PNG)
