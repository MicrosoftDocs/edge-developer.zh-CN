---
description: "\"日程表事件\" 模式显示录制时触发的所有事件。  使用日程表事件参考了解有关每个日程表事件类型的详细信息。"
title: 时间线事件参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 624035636e2231cf1f3cd1e2ba0fdda7e2e4fa00
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992846"
---
<!-- Copyright Meggin Kearney and Flavio Copes

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->





# <span data-ttu-id="85ae0-105">时间线事件参考</span><span class="sxs-lookup"><span data-stu-id="85ae0-105">Timeline Event Reference</span></span>   




<span data-ttu-id="85ae0-106">"日程表事件" 模式显示录制时触发的所有事件。</span><span class="sxs-lookup"><span data-stu-id="85ae0-106">The timeline events mode displays all events triggered while making a recording.</span></span>  <span data-ttu-id="85ae0-107">使用日程表事件参考了解有关每个日程表事件类型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="85ae0-107">Use the timeline event reference to learn more about each timeline event type.</span></span>  

## <span data-ttu-id="85ae0-108">常用日程表事件属性</span><span class="sxs-lookup"><span data-stu-id="85ae0-108">Common timeline event properties</span></span>  

<span data-ttu-id="85ae0-109">某些详细信息存在于所有类型的事件中，而有些仅适用于某些事件类型。</span><span class="sxs-lookup"><span data-stu-id="85ae0-109">Certain details are present in events of all types, while some only apply to certain event types.</span></span>  <span data-ttu-id="85ae0-110">本部分列出了不同事件类型的常见属性。</span><span class="sxs-lookup"><span data-stu-id="85ae0-110">This section lists properties common to different event types.</span></span>  <span data-ttu-id="85ae0-111">以下事件类型的参考中列出了特定于某些事件类型的属性。</span><span class="sxs-lookup"><span data-stu-id="85ae0-111">Properties specific to certain event types are listed in the references for those event types that follow.</span></span>  

| <span data-ttu-id="85ae0-112">属性</span><span class="sxs-lookup"><span data-stu-id="85ae0-112">Property</span></span> | <span data-ttu-id="85ae0-113">何时显示</span><span class="sxs-lookup"><span data-stu-id="85ae0-113">When is it shown</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="85ae0-114">总时间</span><span class="sxs-lookup"><span data-stu-id="85ae0-114">Aggregated time</span></span> | <span data-ttu-id="85ae0-115">对于包含 **嵌套事件**的事件，每个事件类别所花的时间。</span><span class="sxs-lookup"><span data-stu-id="85ae0-115">For events with **nested events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="85ae0-116">调用堆栈</span><span class="sxs-lookup"><span data-stu-id="85ae0-116">Call Stack</span></span> | <span data-ttu-id="85ae0-117">对于包含 **子事件**的事件，每个事件类别所花的时间。</span><span class="sxs-lookup"><span data-stu-id="85ae0-117">For events with **child events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="85ae0-118">CPU 时间</span><span class="sxs-lookup"><span data-stu-id="85ae0-118">CPU time</span></span> | <span data-ttu-id="85ae0-119">录制事件花费的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="85ae0-119">How much CPU time the recorded event took.</span></span> |  
| <span data-ttu-id="85ae0-120">详细信息</span><span class="sxs-lookup"><span data-stu-id="85ae0-120">Details</span></span> | <span data-ttu-id="85ae0-121">有关事件的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="85ae0-121">Other details about the event.</span></span> |  
| <span data-ttu-id="85ae0-122">Duration \ (时间戳 \ ) </span><span class="sxs-lookup"><span data-stu-id="85ae0-122">Duration \(at time-stamp\)</span></span> | <span data-ttu-id="85ae0-123">事件与所有子元素的完全相同的时间时间戳是事件发生的时间，相对于录制开始的时间。</span><span class="sxs-lookup"><span data-stu-id="85ae0-123">How long it took the event with all of its children to complete; timestamp is the time at which the event occurred, relative to when the recording started.</span></span> |  
| <span data-ttu-id="85ae0-124">自我时间</span><span class="sxs-lookup"><span data-stu-id="85ae0-124">Self time</span></span> | <span data-ttu-id="85ae0-125">事件在没有任何子级的情况下花费的时间。</span><span class="sxs-lookup"><span data-stu-id="85ae0-125">How long the event took without any of its children.</span></span> |  
| <span data-ttu-id="85ae0-126">使用的堆大小</span><span class="sxs-lookup"><span data-stu-id="85ae0-126">Used Heap Size</span></span> | <span data-ttu-id="85ae0-127">在记录事件时应用程序使用的内存量，增量 \ (+/\ ) 在上次取样后使用的堆大小发生变化。</span><span class="sxs-lookup"><span data-stu-id="85ae0-127">Amount of memory being used by the application when the event was recorded, and the delta \(+/-\) change in used heap size since the last sampling.</span></span> |  

<!--todo: add nested and child events (timelinetool) section when available -->  

## <span data-ttu-id="85ae0-128">加载事件</span><span class="sxs-lookup"><span data-stu-id="85ae0-128">Loading events</span></span>  

<span data-ttu-id="85ae0-129">此部分列出了属于加载类别及其属性的事件。</span><span class="sxs-lookup"><span data-stu-id="85ae0-129">This section lists events that belong to Loading category and their properties.</span></span>  

| <span data-ttu-id="85ae0-130">事件</span><span class="sxs-lookup"><span data-stu-id="85ae0-130">Event</span></span> | <span data-ttu-id="85ae0-131">描述</span><span class="sxs-lookup"><span data-stu-id="85ae0-131">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="85ae0-132">分析 HTML</span><span class="sxs-lookup"><span data-stu-id="85ae0-132">Parse HTML</span></span> |  <span data-ttu-id="85ae0-133">Microsoft Edge 运行了 HTML 分析算法。</span><span class="sxs-lookup"><span data-stu-id="85ae0-133">Microsoft Edge ran the HTML parsing algorithm.</span></span> |  
| <span data-ttu-id="85ae0-134">完成加载</span><span class="sxs-lookup"><span data-stu-id="85ae0-134">Finish Loading</span></span> |  <span data-ttu-id="85ae0-135">网络请求已完成。</span><span class="sxs-lookup"><span data-stu-id="85ae0-135">A network request completed.</span></span> |  
| <span data-ttu-id="85ae0-136">接收数据</span><span class="sxs-lookup"><span data-stu-id="85ae0-136">Receive Data</span></span> |  <span data-ttu-id="85ae0-137">已收到请求的数据。</span><span class="sxs-lookup"><span data-stu-id="85ae0-137">Data for a request was received.</span></span>  <span data-ttu-id="85ae0-138">有一个或多个接收数据事件。</span><span class="sxs-lookup"><span data-stu-id="85ae0-138">There are one or more Receive Data events.</span></span> |  
| <span data-ttu-id="85ae0-139">接收答复</span><span class="sxs-lookup"><span data-stu-id="85ae0-139">Receive Response</span></span> |  <span data-ttu-id="85ae0-140">来自请求的初始 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="85ae0-140">The initial HTTP response from a request.</span></span> |  
| <span data-ttu-id="85ae0-141">发送请求</span><span class="sxs-lookup"><span data-stu-id="85ae0-141">Send Request</span></span> |  <span data-ttu-id="85ae0-142">已发送网络请求。</span><span class="sxs-lookup"><span data-stu-id="85ae0-142">A network request has been sent.</span></span> |  

### <span data-ttu-id="85ae0-143">加载事件属性</span><span class="sxs-lookup"><span data-stu-id="85ae0-143">Loading event properties</span></span>  

| <span data-ttu-id="85ae0-144">属性</span><span class="sxs-lookup"><span data-stu-id="85ae0-144">Property</span></span> | <span data-ttu-id="85ae0-145">描述</span><span class="sxs-lookup"><span data-stu-id="85ae0-145">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="85ae0-146">资源</span><span class="sxs-lookup"><span data-stu-id="85ae0-146">Resource</span></span> | <span data-ttu-id="85ae0-147">所请求的资源的 URL。</span><span class="sxs-lookup"><span data-stu-id="85ae0-147">The URL of the requested resource.</span></span> |  
| <span data-ttu-id="85ae0-148">预览</span><span class="sxs-lookup"><span data-stu-id="85ae0-148">Preview</span></span> | <span data-ttu-id="85ae0-149">仅预览所请求的资源 \ (图像 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="85ae0-149">Preview of the requested resource \(images only\).</span></span> |  
| <span data-ttu-id="85ae0-150">请求方法</span><span class="sxs-lookup"><span data-stu-id="85ae0-150">Request Method</span></span> | <span data-ttu-id="85ae0-151">用于请求 \ (的 HTTP 方法 `GET` `POST` ，例如 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="85ae0-151">HTTP method used for the request \(`GET` or `POST`, for example\).</span></span> |  
| <span data-ttu-id="85ae0-152">状态代码</span><span class="sxs-lookup"><span data-stu-id="85ae0-152">Status Code</span></span> | <span data-ttu-id="85ae0-153">HTTP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="85ae0-153">HTTP response code.</span></span> |  
| <span data-ttu-id="85ae0-154">MIME 类型</span><span class="sxs-lookup"><span data-stu-id="85ae0-154">MIME Type</span></span> | <span data-ttu-id="85ae0-155">所请求资源的 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="85ae0-155">MIME type of the requested resource.</span></span> |  
| <span data-ttu-id="85ae0-156">编码数据长度</span><span class="sxs-lookup"><span data-stu-id="85ae0-156">Encoded Data Length</span></span> | <span data-ttu-id="85ae0-157">请求的资源的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="85ae0-157">Length of requested resource in bytes.</span></span> |  

## <span data-ttu-id="85ae0-158">脚本事件</span><span class="sxs-lookup"><span data-stu-id="85ae0-158">Scripting events</span></span>  

<span data-ttu-id="85ae0-159">此部分列出了属于脚本类别及其属性的事件。</span><span class="sxs-lookup"><span data-stu-id="85ae0-159">This section lists events that belong to the Scripting category and their properties.</span></span>  

| <span data-ttu-id="85ae0-160">事件</span><span class="sxs-lookup"><span data-stu-id="85ae0-160">Event</span></span> | <span data-ttu-id="85ae0-161">描述</span><span class="sxs-lookup"><span data-stu-id="85ae0-161">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="85ae0-162">激发的动画帧</span><span class="sxs-lookup"><span data-stu-id="85ae0-162">Animation Frame Fired</span></span> | <span data-ttu-id="85ae0-163">引发计划动画帧，并调用其回调处理程序。</span><span class="sxs-lookup"><span data-stu-id="85ae0-163">A scheduled animation frame fired, and its callback handler invoked.</span></span> |  
| <span data-ttu-id="85ae0-164">取消动画帧</span><span class="sxs-lookup"><span data-stu-id="85ae0-164">Cancel Animation Frame</span></span> |  <span data-ttu-id="85ae0-165">已取消计划的动画帧。</span><span class="sxs-lookup"><span data-stu-id="85ae0-165">A scheduled animation frame was canceled.</span></span> |  
| <span data-ttu-id="85ae0-166">GC 事件</span><span class="sxs-lookup"><span data-stu-id="85ae0-166">GC Event</span></span> |  <span data-ttu-id="85ae0-167">发生垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="85ae0-167">Garbage collection occurred.</span></span> |  
| <span data-ttu-id="85ae0-168">DOMContentLoaded</span><span class="sxs-lookup"><span data-stu-id="85ae0-168">DOMContentLoaded</span></span> |  <span data-ttu-id="85ae0-169">浏览器激发了 [DOMContentLoaded 事件][MDNWindowDOMContentLoadedEvent] 。</span><span class="sxs-lookup"><span data-stu-id="85ae0-169">The [DOMContentLoaded event][MDNWindowDOMContentLoadedEvent] was fired by the browser.</span></span>  <span data-ttu-id="85ae0-170">当已加载和分析页面的所有 DOM 内容时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="85ae0-170">This event is fired when all of the page's DOM content has been loaded and parsed.</span></span> |  
| <span data-ttu-id="85ae0-171">计算脚本</span><span class="sxs-lookup"><span data-stu-id="85ae0-171">Evaluate Script</span></span> | <span data-ttu-id="85ae0-172">已评估脚本。</span><span class="sxs-lookup"><span data-stu-id="85ae0-172">A script was evaluated.</span></span> |  
| <span data-ttu-id="85ae0-173">事件</span><span class="sxs-lookup"><span data-stu-id="85ae0-173">Event</span></span> | <span data-ttu-id="85ae0-174">JavaScript 事件 \ (例如、 `mousedown` 或 `key` \ ) 。</span><span class="sxs-lookup"><span data-stu-id="85ae0-174">A JavaScript event \(for example, `mousedown`, or `key`\).</span></span> |  
| <span data-ttu-id="85ae0-175">函数调用</span><span class="sxs-lookup"><span data-stu-id="85ae0-175">Function Call</span></span> | <span data-ttu-id="85ae0-176">执行了顶级 JavaScript 函数调用 \ (仅当浏览器输入 JavaScript 引擎 \ ) 时才出现。</span><span class="sxs-lookup"><span data-stu-id="85ae0-176">A top-level JavaScript function call was made \(only appears when browser enters JavaScript engine\).</span></span> |  
| <span data-ttu-id="85ae0-177">安装计时器</span><span class="sxs-lookup"><span data-stu-id="85ae0-177">Install Timer</span></span> | <span data-ttu-id="85ae0-178">已使用 SetInterval 创建了计时器， [ ( # B1 ][MDNWindowOrWorkerGlobalScopeSetInterval] 或 [SetTimeout ( # B3 ][MDNWindowOrWorkerGlobalScopeSetTimeout]。</span><span class="sxs-lookup"><span data-stu-id="85ae0-178">A timer was created with [setInterval()][MDNWindowOrWorkerGlobalScopeSetInterval] or [setTimeout()][MDNWindowOrWorkerGlobalScopeSetTimeout].</span></span> |  
| <span data-ttu-id="85ae0-179">请求动画帧</span><span class="sxs-lookup"><span data-stu-id="85ae0-179">Request Animation Frame</span></span> | <span data-ttu-id="85ae0-180">`requestAnimationFrame()`通话安排了一个新帧。</span><span class="sxs-lookup"><span data-stu-id="85ae0-180">A `requestAnimationFrame()` call scheduled a new frame.</span></span> |  
| <span data-ttu-id="85ae0-181">删除计时器</span><span class="sxs-lookup"><span data-stu-id="85ae0-181">Remove Timer</span></span> | <span data-ttu-id="85ae0-182">以前创建的计时器已清除。</span><span class="sxs-lookup"><span data-stu-id="85ae0-182">A previously created timer was cleared.</span></span> |  
| <span data-ttu-id="85ae0-183">时间</span><span class="sxs-lookup"><span data-stu-id="85ae0-183">Time</span></span> |  <span data-ttu-id="85ae0-184">名为 console 的脚本 [。时间 ( # B1 ][ConsoleApiTime]。</span><span class="sxs-lookup"><span data-stu-id="85ae0-184">A script called [console.time()][ConsoleApiTime].</span></span> |  
| <span data-ttu-id="85ae0-185">结束时间</span><span class="sxs-lookup"><span data-stu-id="85ae0-185">Time End</span></span> | <span data-ttu-id="85ae0-186">名为 [timeEnd ( # B1 ][ConsoleApiTimeEnd]的脚本。</span><span class="sxs-lookup"><span data-stu-id="85ae0-186">A script called [console.timeEnd()][ConsoleApiTimeEnd].</span></span> |  
| <span data-ttu-id="85ae0-187">计时器已激发</span><span class="sxs-lookup"><span data-stu-id="85ae0-187">Timer Fired</span></span> | <span data-ttu-id="85ae0-188">通过 or 计划引发的计时器 `setInterval()` `setTimeout()` 。</span><span class="sxs-lookup"><span data-stu-id="85ae0-188">A timer fired that was scheduled with `setInterval()` or `setTimeout()`.</span></span> |  
| <span data-ttu-id="85ae0-189">XHR 准备状态更改</span><span class="sxs-lookup"><span data-stu-id="85ae0-189">XHR Ready State Change</span></span> | <span data-ttu-id="85ae0-190">XMLHTTPRequest 的准备状态已更改。</span><span class="sxs-lookup"><span data-stu-id="85ae0-190">The ready state of an XMLHTTPRequest changed.</span></span> |  
| <span data-ttu-id="85ae0-191">XHR 负载</span><span class="sxs-lookup"><span data-stu-id="85ae0-191">XHR Load</span></span> | <span data-ttu-id="85ae0-192">`XMLHTTPRequest`已完成加载。</span><span class="sxs-lookup"><span data-stu-id="85ae0-192">An `XMLHTTPRequest` finished loading.</span></span> |  

### <span data-ttu-id="85ae0-193">脚本事件属性</span><span class="sxs-lookup"><span data-stu-id="85ae0-193">Scripting event properties</span></span>  

| <span data-ttu-id="85ae0-194">属性</span><span class="sxs-lookup"><span data-stu-id="85ae0-194">Property</span></span> | <span data-ttu-id="85ae0-195">描述</span><span class="sxs-lookup"><span data-stu-id="85ae0-195">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="85ae0-196">计时器 ID</span><span class="sxs-lookup"><span data-stu-id="85ae0-196">Timer ID</span></span> | <span data-ttu-id="85ae0-197">计时器 ID。</span><span class="sxs-lookup"><span data-stu-id="85ae0-197">The timer ID.</span></span> |  
| <span data-ttu-id="85ae0-198">超时</span><span class="sxs-lookup"><span data-stu-id="85ae0-198">Timeout</span></span> | <span data-ttu-id="85ae0-199">计时器指定的超时值。</span><span class="sxs-lookup"><span data-stu-id="85ae0-199">The timeout specified by the timer.</span></span> |  
| <span data-ttu-id="85ae0-200">播放</span><span class="sxs-lookup"><span data-stu-id="85ae0-200">Repeats</span></span> | <span data-ttu-id="85ae0-201">指定计时器是否重复的布尔值。</span><span class="sxs-lookup"><span data-stu-id="85ae0-201">Boolean that specifies if the timer repeats.</span></span> |  
| <span data-ttu-id="85ae0-202">函数调用</span><span class="sxs-lookup"><span data-stu-id="85ae0-202">Function Call</span></span> | <span data-ttu-id="85ae0-203">已调用的函数。</span><span class="sxs-lookup"><span data-stu-id="85ae0-203">A function that was invoked.</span></span> |  

## <span data-ttu-id="85ae0-204">呈现事件</span><span class="sxs-lookup"><span data-stu-id="85ae0-204">Rendering events</span></span>  

<span data-ttu-id="85ae0-205">此部分列出了属于呈现类别及其属性的事件。</span><span class="sxs-lookup"><span data-stu-id="85ae0-205">This section lists events that belong to Rendering category and their properties.</span></span>  

| <span data-ttu-id="85ae0-206">事件</span><span class="sxs-lookup"><span data-stu-id="85ae0-206">Event</span></span> | <span data-ttu-id="85ae0-207">描述</span><span class="sxs-lookup"><span data-stu-id="85ae0-207">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="85ae0-208">使布局无效</span><span class="sxs-lookup"><span data-stu-id="85ae0-208">Invalidate layout</span></span> | <span data-ttu-id="85ae0-209">DOM 更改使页面布局失效。</span><span class="sxs-lookup"><span data-stu-id="85ae0-209">The page layout was invalidated by a DOM change.</span></span> |  
| <span data-ttu-id="85ae0-210">布局</span><span class="sxs-lookup"><span data-stu-id="85ae0-210">Layout</span></span> | <span data-ttu-id="85ae0-211">已完成页面布局。</span><span class="sxs-lookup"><span data-stu-id="85ae0-211">A page layout was completed.</span></span> |  
| <span data-ttu-id="85ae0-212">重新计算样式</span><span class="sxs-lookup"><span data-stu-id="85ae0-212">Recalculate style</span></span> | <span data-ttu-id="85ae0-213">Microsoft Edge 重新计算的元素样式。</span><span class="sxs-lookup"><span data-stu-id="85ae0-213">Microsoft Edge recalculated element styles.</span></span> |  
| <span data-ttu-id="85ae0-214">滚动</span><span class="sxs-lookup"><span data-stu-id="85ae0-214">Scroll</span></span> | <span data-ttu-id="85ae0-215">已滚动嵌套视图的内容。</span><span class="sxs-lookup"><span data-stu-id="85ae0-215">The content of nested view was scrolled.</span></span> |  

### <span data-ttu-id="85ae0-216">呈现事件属性</span><span class="sxs-lookup"><span data-stu-id="85ae0-216">Rendering event properties</span></span>  

| <span data-ttu-id="85ae0-217">属性</span><span class="sxs-lookup"><span data-stu-id="85ae0-217">Property</span></span> | <span data-ttu-id="85ae0-218">描述</span><span class="sxs-lookup"><span data-stu-id="85ae0-218">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="85ae0-219">布局无效</span><span class="sxs-lookup"><span data-stu-id="85ae0-219">Layout invalidated</span></span> | <span data-ttu-id="85ae0-220">对于布局记录，导致布局失效的代码的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="85ae0-220">For Layout records, the stack trace of the code that caused the layout to be invalidated.</span></span> |  
| <span data-ttu-id="85ae0-221">需要布局的节点</span><span class="sxs-lookup"><span data-stu-id="85ae0-221">Nodes that need layout</span></span> | <span data-ttu-id="85ae0-222">对于布局记录，在 relayout 开始之前标记为需要布局的节点数。</span><span class="sxs-lookup"><span data-stu-id="85ae0-222">For Layout records, the number of nodes that were marked as needing layout before the relayout started.</span></span>  <span data-ttu-id="85ae0-223">这些节点通常是由开发人员代码无效的节点，还包括指向 relayout 根的路径。</span><span class="sxs-lookup"><span data-stu-id="85ae0-223">These are normally those nodes that were invalidated by developer code, plus a path upward to relayout root.</span></span> |  
| <span data-ttu-id="85ae0-224">布局树大小</span><span class="sxs-lookup"><span data-stu-id="85ae0-224">Layout tree size</span></span> | <span data-ttu-id="85ae0-225">对于布局记录，relayout 根节点下的节点总数 (Microsoft Edge 启动 relayout \ ) 的节点。</span><span class="sxs-lookup"><span data-stu-id="85ae0-225">For Layout records, the total number of nodes under the relayout root \(the node that Microsoft Edge starts the relayout\).</span></span> |  
| <span data-ttu-id="85ae0-226">布局范围</span><span class="sxs-lookup"><span data-stu-id="85ae0-226">Layout scope</span></span> | <span data-ttu-id="85ae0-227">可能的值为 `Partial` \ (重新布局边界是 DOM \ ) 的一部分 `Whole document` 。</span><span class="sxs-lookup"><span data-stu-id="85ae0-227">Possible values are `Partial` \(the re-layout boundary is a portion of the DOM\) or `Whole document`.</span></span> |  
| <span data-ttu-id="85ae0-228">受影响的元素</span><span class="sxs-lookup"><span data-stu-id="85ae0-228">Elements affected</span></span> | <span data-ttu-id="85ae0-229">对于重新计算样式记录，受样式重新计算影响的元素数。</span><span class="sxs-lookup"><span data-stu-id="85ae0-229">For Recalculate style records, the number of elements affected by a style recalculation.</span></span> |  
| <span data-ttu-id="85ae0-230">样式无效</span><span class="sxs-lookup"><span data-stu-id="85ae0-230">Styles invalidated</span></span> | <span data-ttu-id="85ae0-231">对于 "重新计算" 样式记录，提供导致样式无效的代码的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="85ae0-231">For Recalculate style records, provides the stack trace of the code that caused the style invalidation.</span></span> |  

## <span data-ttu-id="85ae0-232">绘制事件</span><span class="sxs-lookup"><span data-stu-id="85ae0-232">Painting events</span></span>  

<span data-ttu-id="85ae0-233">此部分列出了属于 Painting 类别及其属性的事件。</span><span class="sxs-lookup"><span data-stu-id="85ae0-233">This section lists events that belong to Painting category and their properties.</span></span>  

| <span data-ttu-id="85ae0-234">事件</span><span class="sxs-lookup"><span data-stu-id="85ae0-234">Event</span></span> | <span data-ttu-id="85ae0-235">描述</span><span class="sxs-lookup"><span data-stu-id="85ae0-235">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="85ae0-236">复合图层</span><span class="sxs-lookup"><span data-stu-id="85ae0-236">Composite Layers</span></span> | <span data-ttu-id="85ae0-237">Microsoft Edge 呈现引擎的合成图像图层。</span><span class="sxs-lookup"><span data-stu-id="85ae0-237">The composited image layers for the Microsoft Edge rendering engine.</span></span> |  
| <span data-ttu-id="85ae0-238">图像解码</span><span class="sxs-lookup"><span data-stu-id="85ae0-238">Image Decode</span></span> | <span data-ttu-id="85ae0-239">图像资源已解码。</span><span class="sxs-lookup"><span data-stu-id="85ae0-239">An image resource was decoded.</span></span> |  
| <span data-ttu-id="85ae0-240">图像调整大小</span><span class="sxs-lookup"><span data-stu-id="85ae0-240">Image Resize</span></span> | <span data-ttu-id="85ae0-241">从其本机尺寸调整图像大小。</span><span class="sxs-lookup"><span data-stu-id="85ae0-241">An image was resized from its native dimensions.</span></span> |  
| <span data-ttu-id="85ae0-242">画图</span><span class="sxs-lookup"><span data-stu-id="85ae0-242">Paint</span></span> | <span data-ttu-id="85ae0-243">复合图层已绘制到显示区域。</span><span class="sxs-lookup"><span data-stu-id="85ae0-243">Composited layers were painted to a region of the display.</span></span>  <span data-ttu-id="85ae0-244">将鼠标悬停在 "画图" 记录上将突出显示已更新的显示区域。</span><span class="sxs-lookup"><span data-stu-id="85ae0-244">Hovering over a Paint record highlights the region of the display that was updated.</span></span> |  

### <span data-ttu-id="85ae0-245">绘制事件属性</span><span class="sxs-lookup"><span data-stu-id="85ae0-245">Painting event properties</span></span>  

| <span data-ttu-id="85ae0-246">属性</span><span class="sxs-lookup"><span data-stu-id="85ae0-246">Property</span></span> | <span data-ttu-id="85ae0-247">说明</span><span class="sxs-lookup"><span data-stu-id="85ae0-247">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="85ae0-248">位置</span><span class="sxs-lookup"><span data-stu-id="85ae0-248">Location</span></span> | <span data-ttu-id="85ae0-249">对于画图事件，绘制矩形的 x 和 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="85ae0-249">For Paint events, the x and y coordinates of the paint rectangle.</span></span> |  
| <span data-ttu-id="85ae0-250">三维</span><span class="sxs-lookup"><span data-stu-id="85ae0-250">Dimensions</span></span> | <span data-ttu-id="85ae0-251">对于 "画图" 事件，即绘制区域的高度和宽度。</span><span class="sxs-lookup"><span data-stu-id="85ae0-251">For Paint events, the height and width of the painted region.</span></span> |  

 



<!-- image links -->  

<!-- links -->

[ConsoleApiTime]: /microsoft-edge/devtools-guide-chromium/console/api#time "时间-控制台 API 参考"  
[ConsoleApiTimeEnd]: /microsoft-edge/devtools-guide-chromium/console/api#timeend "timeEnd-控制台 API 参考"  
<!--[EvaluatePerformanceTimelineTool]: timeline-tool "How to Use the Timeline Tool"  -->

[MDNWindowDOMContentLoadedEvent]: https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded "窗口： DOMContentLoaded 事件 |MDN"  
[MDNWindowOrWorkerGlobalScopeSetInterval]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setInterval "WindowOrWorkerGlobalScope setInterval ( # A1 |MDN"  
[MDNWindowOrWorkerGlobalScopeSetTimeout]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setTimeout "WindowOrWorkerGlobalScope setTimeout ( # A1 |MDN"  

> [!NOTE]
> <span data-ttu-id="85ae0-257">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="85ae0-257">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="85ae0-258">原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) 找到，并由 [Meggin Kearney][MegginKearney] (技术作者 \ ) 和 [Flavio Copes][FlavioCopes] (完全堆栈开发人员 \ ) 创作。</span><span class="sxs-lookup"><span data-stu-id="85ae0-258">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Flavio Copes][FlavioCopes] \(Full Stack Developer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="85ae0-260">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="85ae0-260">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[FlavioCopes]: https://developers.google.com/web/resources/contributors/flaviocopes  
