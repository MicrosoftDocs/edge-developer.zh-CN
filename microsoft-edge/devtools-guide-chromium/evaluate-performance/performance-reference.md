---
description: 时间线事件模式显示录制时触发的所有事件。  使用时间线事件引用了解有关每个时间线事件类型更多信息。
title: 时间线事件参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 2a166c9eebc980682fa872e5ee8d213f2058b384
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398663"
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

# <a name="timeline-event-reference"></a><span data-ttu-id="877a8-105">时间线事件参考</span><span class="sxs-lookup"><span data-stu-id="877a8-105">Timeline Event reference</span></span>  

<span data-ttu-id="877a8-106">时间线事件模式显示录制时触发的所有事件。</span><span class="sxs-lookup"><span data-stu-id="877a8-106">The timeline events mode displays all events triggered while making a recording.</span></span>  <span data-ttu-id="877a8-107">使用时间线事件引用了解有关每个时间线事件类型更多信息。</span><span class="sxs-lookup"><span data-stu-id="877a8-107">Use the timeline event reference to learn more about each timeline event type.</span></span>  

## <a name="common-timeline-event-properties"></a><span data-ttu-id="877a8-108">常见时间线事件属性</span><span class="sxs-lookup"><span data-stu-id="877a8-108">Common timeline event properties</span></span>  

<span data-ttu-id="877a8-109">某些详细信息存在于所有类型的事件，而某些仅适用于特定事件类型。</span><span class="sxs-lookup"><span data-stu-id="877a8-109">Certain details are present in events of all types, while some only apply to certain event types.</span></span>  <span data-ttu-id="877a8-110">本节列出了不同事件类型通用的属性。</span><span class="sxs-lookup"><span data-stu-id="877a8-110">This section lists properties common to different event types.</span></span>  <span data-ttu-id="877a8-111">特定于特定事件类型的属性在后续事件类型的引用中列出。</span><span class="sxs-lookup"><span data-stu-id="877a8-111">Properties specific to certain event types are listed in the references for those event types that follow.</span></span>  

| <span data-ttu-id="877a8-112">属性</span><span class="sxs-lookup"><span data-stu-id="877a8-112">Property</span></span> | <span data-ttu-id="877a8-113">何时显示</span><span class="sxs-lookup"><span data-stu-id="877a8-113">When is it shown</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="877a8-114">聚合时间</span><span class="sxs-lookup"><span data-stu-id="877a8-114">Aggregated time</span></span> | <span data-ttu-id="877a8-115">对于具有 **嵌套事件的事件**，每个事件类别所花时间。</span><span class="sxs-lookup"><span data-stu-id="877a8-115">For events with **nested events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="877a8-116">调用堆栈</span><span class="sxs-lookup"><span data-stu-id="877a8-116">Call Stack</span></span> | <span data-ttu-id="877a8-117">对于具有 **子事件的事件**，表示每个事件类别所花时间。</span><span class="sxs-lookup"><span data-stu-id="877a8-117">For events with **child events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="877a8-118">CPU 时间</span><span class="sxs-lookup"><span data-stu-id="877a8-118">CPU time</span></span> | <span data-ttu-id="877a8-119">记录的事件占用的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="877a8-119">How much CPU time the recorded event took.</span></span> |  
| <span data-ttu-id="877a8-120">详细信息</span><span class="sxs-lookup"><span data-stu-id="877a8-120">Details</span></span> | <span data-ttu-id="877a8-121">有关事件的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="877a8-121">Other details about the event.</span></span> |  
| <span data-ttu-id="877a8-122">Duration \ (at time-stamp\) </span><span class="sxs-lookup"><span data-stu-id="877a8-122">Duration \(at time-stamp\)</span></span> | <span data-ttu-id="877a8-123">事件及其所有子项完成所用时间;timestamp 是事件发生的时间，相对于录制的开始时间。</span><span class="sxs-lookup"><span data-stu-id="877a8-123">How long it took the event with all of its children to complete; timestamp is the time at which the event occurred, relative to when the recording started.</span></span> |  
| <span data-ttu-id="877a8-124">自时间</span><span class="sxs-lookup"><span data-stu-id="877a8-124">Self time</span></span> | <span data-ttu-id="877a8-125">事件在没有任何子事件的情况下所发生时间。</span><span class="sxs-lookup"><span data-stu-id="877a8-125">How long the event took without any of its children.</span></span> |  
| <span data-ttu-id="877a8-126">使用的堆大小</span><span class="sxs-lookup"><span data-stu-id="877a8-126">Used Heap Size</span></span> | <span data-ttu-id="877a8-127">记录事件时应用程序使用的内存量，以及自上次采样以来使用的堆大小的增量 \ (+/-\) 更改。</span><span class="sxs-lookup"><span data-stu-id="877a8-127">Amount of memory being used by the application when the event was recorded, and the delta \(+/-\) change in used heap size since the last sampling.</span></span> |  

<!--todo: add nested and child events (timelinetool) section when available -->  

## <a name="loading-events"></a><span data-ttu-id="877a8-128">加载事件</span><span class="sxs-lookup"><span data-stu-id="877a8-128">Loading events</span></span>  

<span data-ttu-id="877a8-129">此部分列出了属于 Loading 类别的事件及其属性。</span><span class="sxs-lookup"><span data-stu-id="877a8-129">This section lists events that belong to Loading category and their properties.</span></span>  

| <span data-ttu-id="877a8-130">事件</span><span class="sxs-lookup"><span data-stu-id="877a8-130">Event</span></span> | <span data-ttu-id="877a8-131">说明</span><span class="sxs-lookup"><span data-stu-id="877a8-131">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="877a8-132">分析 HTML</span><span class="sxs-lookup"><span data-stu-id="877a8-132">Parse HTML</span></span> |  <span data-ttu-id="877a8-133">Microsoft Edge HTML 分析算法。</span><span class="sxs-lookup"><span data-stu-id="877a8-133">Microsoft Edge ran the HTML parsing algorithm.</span></span> |  
| <span data-ttu-id="877a8-134">完成加载</span><span class="sxs-lookup"><span data-stu-id="877a8-134">Finish Loading</span></span> |  <span data-ttu-id="877a8-135">网络请求已完成。</span><span class="sxs-lookup"><span data-stu-id="877a8-135">A network request completed.</span></span> |  
| <span data-ttu-id="877a8-136">接收数据</span><span class="sxs-lookup"><span data-stu-id="877a8-136">Receive Data</span></span> |  <span data-ttu-id="877a8-137">已接收请求的数据。</span><span class="sxs-lookup"><span data-stu-id="877a8-137">Data for a request was received.</span></span>  <span data-ttu-id="877a8-138">有一个或多个接收数据事件。</span><span class="sxs-lookup"><span data-stu-id="877a8-138">There are one or more Receive Data events.</span></span> |  
| <span data-ttu-id="877a8-139">接收响应</span><span class="sxs-lookup"><span data-stu-id="877a8-139">Receive Response</span></span> |  <span data-ttu-id="877a8-140">来自请求的初始 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="877a8-140">The initial HTTP response from a request.</span></span> |  
| <span data-ttu-id="877a8-141">发送请求</span><span class="sxs-lookup"><span data-stu-id="877a8-141">Send Request</span></span> |  <span data-ttu-id="877a8-142">已发送网络请求。</span><span class="sxs-lookup"><span data-stu-id="877a8-142">A network request has been sent.</span></span> |  

### <a name="loading-event-properties"></a><span data-ttu-id="877a8-143">加载事件属性</span><span class="sxs-lookup"><span data-stu-id="877a8-143">Loading event properties</span></span>  

| <span data-ttu-id="877a8-144">属性</span><span class="sxs-lookup"><span data-stu-id="877a8-144">Property</span></span> | <span data-ttu-id="877a8-145">说明</span><span class="sxs-lookup"><span data-stu-id="877a8-145">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="877a8-146">资源</span><span class="sxs-lookup"><span data-stu-id="877a8-146">Resource</span></span> | <span data-ttu-id="877a8-147">所请求资源的 URL。</span><span class="sxs-lookup"><span data-stu-id="877a8-147">The URL of the requested resource.</span></span> |  
| <span data-ttu-id="877a8-148">预览</span><span class="sxs-lookup"><span data-stu-id="877a8-148">Preview</span></span> | <span data-ttu-id="877a8-149">仅预览请求的资源 \ (\) 。</span><span class="sxs-lookup"><span data-stu-id="877a8-149">Preview of the requested resource \(images only\).</span></span> |  
| <span data-ttu-id="877a8-150">Request 方法</span><span class="sxs-lookup"><span data-stu-id="877a8-150">Request Method</span></span> | <span data-ttu-id="877a8-151">用于请求 \ (或 的 HTTP 方法，例如 `GET` `POST` \) 。</span><span class="sxs-lookup"><span data-stu-id="877a8-151">HTTP method used for the request \(`GET` or `POST`, for example\).</span></span> |  
| <span data-ttu-id="877a8-152">状态代码</span><span class="sxs-lookup"><span data-stu-id="877a8-152">Status Code</span></span> | <span data-ttu-id="877a8-153">HTTP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="877a8-153">HTTP response code.</span></span> |  
| <span data-ttu-id="877a8-154">MIME 类型</span><span class="sxs-lookup"><span data-stu-id="877a8-154">MIME Type</span></span> | <span data-ttu-id="877a8-155">所请求资源的 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="877a8-155">MIME type of the requested resource.</span></span> |  
| <span data-ttu-id="877a8-156">编码数据长度</span><span class="sxs-lookup"><span data-stu-id="877a8-156">Encoded Data Length</span></span> | <span data-ttu-id="877a8-157">请求的资源的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="877a8-157">Length of requested resource in bytes.</span></span> |  

## <a name="scripting-events"></a><span data-ttu-id="877a8-158">脚本事件</span><span class="sxs-lookup"><span data-stu-id="877a8-158">Scripting events</span></span>  

<span data-ttu-id="877a8-159">本节列出了属于"脚本"类别的事件及其属性。</span><span class="sxs-lookup"><span data-stu-id="877a8-159">This section lists events that belong to the Scripting category and their properties.</span></span>  

| <span data-ttu-id="877a8-160">事件</span><span class="sxs-lookup"><span data-stu-id="877a8-160">Event</span></span> | <span data-ttu-id="877a8-161">说明</span><span class="sxs-lookup"><span data-stu-id="877a8-161">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="877a8-162">触发的动画帧</span><span class="sxs-lookup"><span data-stu-id="877a8-162">Animation Frame Fired</span></span> | <span data-ttu-id="877a8-163">触发的计划动画帧及其回调处理程序已调用。</span><span class="sxs-lookup"><span data-stu-id="877a8-163">A scheduled animation frame fired, and its callback handler invoked.</span></span> |  
| <span data-ttu-id="877a8-164">取消动画帧</span><span class="sxs-lookup"><span data-stu-id="877a8-164">Cancel Animation Frame</span></span> |  <span data-ttu-id="877a8-165">已取消计划的动画帧。</span><span class="sxs-lookup"><span data-stu-id="877a8-165">A scheduled animation frame was canceled.</span></span> |  
| <span data-ttu-id="877a8-166">GC 事件</span><span class="sxs-lookup"><span data-stu-id="877a8-166">GC Event</span></span> |  <span data-ttu-id="877a8-167">发生垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="877a8-167">Garbage collection occurred.</span></span> |  
| <span data-ttu-id="877a8-168">DOMContentLoaded</span><span class="sxs-lookup"><span data-stu-id="877a8-168">DOMContentLoaded</span></span> |  <span data-ttu-id="877a8-169">[DOMContentLoaded 事件][MDNWindowDOMContentLoadedEvent]由浏览器触发。</span><span class="sxs-lookup"><span data-stu-id="877a8-169">The [DOMContentLoaded event][MDNWindowDOMContentLoadedEvent] was fired by the browser.</span></span>  <span data-ttu-id="877a8-170">加载和分析页面的所有 DOM 内容时，将触发此事件。</span><span class="sxs-lookup"><span data-stu-id="877a8-170">This event is fired when all of the DOM content of the page is loaded and parsed.</span></span> |  
| <span data-ttu-id="877a8-171">评估脚本</span><span class="sxs-lookup"><span data-stu-id="877a8-171">Evaluate Script</span></span> | <span data-ttu-id="877a8-172">已评估脚本。</span><span class="sxs-lookup"><span data-stu-id="877a8-172">A script was evaluated.</span></span> |  
| <span data-ttu-id="877a8-173">事件</span><span class="sxs-lookup"><span data-stu-id="877a8-173">Event</span></span> | <span data-ttu-id="877a8-174">JavaScript 事件 \ (例如 ， `mousedown` 或 `key` \) 。</span><span class="sxs-lookup"><span data-stu-id="877a8-174">A JavaScript event \(for example, `mousedown`, or `key`\).</span></span> |  
| <span data-ttu-id="877a8-175">函数调用</span><span class="sxs-lookup"><span data-stu-id="877a8-175">Function Call</span></span> | <span data-ttu-id="877a8-176">进行了顶级 JavaScript 函数调用 \ (浏览器进入 JavaScript engine\) 。</span><span class="sxs-lookup"><span data-stu-id="877a8-176">A top-level JavaScript function call was made \(only appears when browser enters JavaScript engine\).</span></span> |  
| <span data-ttu-id="877a8-177">安装计时器</span><span class="sxs-lookup"><span data-stu-id="877a8-177">Install Timer</span></span> | <span data-ttu-id="877a8-178">计时器是使用 [setInterval ][MDNWindowOrWorkerGlobalScopeSetInterval] () [setTimeout ][MDNWindowOrWorkerGlobalScopeSetTimeout] () 创建的。</span><span class="sxs-lookup"><span data-stu-id="877a8-178">A timer was created with [setInterval()][MDNWindowOrWorkerGlobalScopeSetInterval] or [setTimeout()][MDNWindowOrWorkerGlobalScopeSetTimeout].</span></span> |  
| <span data-ttu-id="877a8-179">请求动画帧</span><span class="sxs-lookup"><span data-stu-id="877a8-179">Request Animation Frame</span></span> | <span data-ttu-id="877a8-180">安排 `requestAnimationFrame()` 新帧的呼叫。</span><span class="sxs-lookup"><span data-stu-id="877a8-180">A `requestAnimationFrame()` call scheduled a new frame.</span></span> |  
| <span data-ttu-id="877a8-181">删除计时器</span><span class="sxs-lookup"><span data-stu-id="877a8-181">Remove Timer</span></span> | <span data-ttu-id="877a8-182">已清除之前创建的计时器。</span><span class="sxs-lookup"><span data-stu-id="877a8-182">A previously created timer was cleared.</span></span> |  
| <span data-ttu-id="877a8-183">时间</span><span class="sxs-lookup"><span data-stu-id="877a8-183">Time</span></span> |  <span data-ttu-id="877a8-184">一个称为 [console.time () ][ConsoleApiTime]脚本。</span><span class="sxs-lookup"><span data-stu-id="877a8-184">A script called [console.time()][ConsoleApiTime].</span></span> |  
| <span data-ttu-id="877a8-185">时间结束</span><span class="sxs-lookup"><span data-stu-id="877a8-185">Time End</span></span> | <span data-ttu-id="877a8-186">名为 [console.timeEnd ][ConsoleApiTimeEnd]的脚本 () 。</span><span class="sxs-lookup"><span data-stu-id="877a8-186">A script called [console.timeEnd()][ConsoleApiTimeEnd].</span></span> |  
| <span data-ttu-id="877a8-187">计时器触发</span><span class="sxs-lookup"><span data-stu-id="877a8-187">Timer Fired</span></span> | <span data-ttu-id="877a8-188">使用 或 计划触发的 `setInterval()` 计时器 `setTimeout()` 。</span><span class="sxs-lookup"><span data-stu-id="877a8-188">A timer fired that was scheduled with `setInterval()` or `setTimeout()`.</span></span> |  
| <span data-ttu-id="877a8-189">XHR 就绪状态更改</span><span class="sxs-lookup"><span data-stu-id="877a8-189">XHR Ready State Change</span></span> | <span data-ttu-id="877a8-190">XMLHTTPRequest 的就绪状态已更改。</span><span class="sxs-lookup"><span data-stu-id="877a8-190">The ready state of an XMLHTTPRequest changed.</span></span> |  
| <span data-ttu-id="877a8-191">XHR Load</span><span class="sxs-lookup"><span data-stu-id="877a8-191">XHR Load</span></span> | <span data-ttu-id="877a8-192">已完成 `XMLHTTPRequest` 加载。</span><span class="sxs-lookup"><span data-stu-id="877a8-192">An `XMLHTTPRequest` finished loading.</span></span> |  

### <a name="scripting-event-properties"></a><span data-ttu-id="877a8-193">脚本事件属性</span><span class="sxs-lookup"><span data-stu-id="877a8-193">Scripting event properties</span></span>  

| <span data-ttu-id="877a8-194">属性</span><span class="sxs-lookup"><span data-stu-id="877a8-194">Property</span></span> | <span data-ttu-id="877a8-195">说明</span><span class="sxs-lookup"><span data-stu-id="877a8-195">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="877a8-196">计时器 ID</span><span class="sxs-lookup"><span data-stu-id="877a8-196">Timer ID</span></span> | <span data-ttu-id="877a8-197">计时器 ID。</span><span class="sxs-lookup"><span data-stu-id="877a8-197">The timer ID.</span></span> |  
| <span data-ttu-id="877a8-198">超时</span><span class="sxs-lookup"><span data-stu-id="877a8-198">Timeout</span></span> | <span data-ttu-id="877a8-199">计时器指定的超时。</span><span class="sxs-lookup"><span data-stu-id="877a8-199">The timeout specified by the timer.</span></span> |  
| <span data-ttu-id="877a8-200">重复</span><span class="sxs-lookup"><span data-stu-id="877a8-200">Repeats</span></span> | <span data-ttu-id="877a8-201">指定计时器是否重复的布尔值。</span><span class="sxs-lookup"><span data-stu-id="877a8-201">Boolean that specifies if the timer repeats.</span></span> |  
| <span data-ttu-id="877a8-202">函数调用</span><span class="sxs-lookup"><span data-stu-id="877a8-202">Function Call</span></span> | <span data-ttu-id="877a8-203">已调用的函数。</span><span class="sxs-lookup"><span data-stu-id="877a8-203">A function that was invoked.</span></span> |  

## <a name="rendering-events"></a><span data-ttu-id="877a8-204">呈现事件</span><span class="sxs-lookup"><span data-stu-id="877a8-204">Rendering events</span></span>  

<span data-ttu-id="877a8-205">此部分列出了属于"呈现"类别及其属性的事件。</span><span class="sxs-lookup"><span data-stu-id="877a8-205">This section lists events that belong to Rendering category and their properties.</span></span>  

| <span data-ttu-id="877a8-206">事件</span><span class="sxs-lookup"><span data-stu-id="877a8-206">Event</span></span> | <span data-ttu-id="877a8-207">说明</span><span class="sxs-lookup"><span data-stu-id="877a8-207">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="877a8-208">无效布局</span><span class="sxs-lookup"><span data-stu-id="877a8-208">Invalidate layout</span></span> | <span data-ttu-id="877a8-209">页面布局因 DOM 更改而无效。</span><span class="sxs-lookup"><span data-stu-id="877a8-209">The page layout was invalidated by a DOM change.</span></span> |  
| <span data-ttu-id="877a8-210">布局</span><span class="sxs-lookup"><span data-stu-id="877a8-210">Layout</span></span> | <span data-ttu-id="877a8-211">已完成页面布局。</span><span class="sxs-lookup"><span data-stu-id="877a8-211">A page layout was completed.</span></span> |  
| <span data-ttu-id="877a8-212">重新计算样式</span><span class="sxs-lookup"><span data-stu-id="877a8-212">Recalculate style</span></span> | <span data-ttu-id="877a8-213">Microsoft Edge重新计算的元素样式。</span><span class="sxs-lookup"><span data-stu-id="877a8-213">Microsoft Edge recalculated element styles.</span></span> |  
| <span data-ttu-id="877a8-214">滚动</span><span class="sxs-lookup"><span data-stu-id="877a8-214">Scroll</span></span> | <span data-ttu-id="877a8-215">已滚动嵌套视图的内容。</span><span class="sxs-lookup"><span data-stu-id="877a8-215">The content of nested view was scrolled.</span></span> |  

### <a name="rendering-event-properties"></a><span data-ttu-id="877a8-216">呈现事件属性</span><span class="sxs-lookup"><span data-stu-id="877a8-216">Rendering event properties</span></span>  

| <span data-ttu-id="877a8-217">属性</span><span class="sxs-lookup"><span data-stu-id="877a8-217">Property</span></span> | <span data-ttu-id="877a8-218">说明</span><span class="sxs-lookup"><span data-stu-id="877a8-218">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="877a8-219">布局无效</span><span class="sxs-lookup"><span data-stu-id="877a8-219">Layout invalidated</span></span> | <span data-ttu-id="877a8-220">对于布局记录，是导致布局失效的代码堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="877a8-220">For Layout records, the stack trace of the code that caused the layout to be invalidated.</span></span> |  
| <span data-ttu-id="877a8-221">需要布局的节点</span><span class="sxs-lookup"><span data-stu-id="877a8-221">Nodes that need layout</span></span> | <span data-ttu-id="877a8-222">对于布局记录，表示在启动中继之前标记为需要布局的节点数。</span><span class="sxs-lookup"><span data-stu-id="877a8-222">For Layout records, the number of nodes that were marked as needing layout before the relayout started.</span></span>  <span data-ttu-id="877a8-223">这些节点通常是开发人员代码无效的节点，以及中继根的向上路径。</span><span class="sxs-lookup"><span data-stu-id="877a8-223">These are normally those nodes that were invalidated by developer code, plus a path upward to relayout root.</span></span> |  
| <span data-ttu-id="877a8-224">布局树大小</span><span class="sxs-lookup"><span data-stu-id="877a8-224">Layout tree size</span></span> | <span data-ttu-id="877a8-225">对于布局记录，中继根 \ (节点下的节点总数Microsoft Edge relayout\) 。</span><span class="sxs-lookup"><span data-stu-id="877a8-225">For Layout records, the total number of nodes under the relayout root \(the node that Microsoft Edge starts the relayout\).</span></span> |  
| <span data-ttu-id="877a8-226">布局范围</span><span class="sxs-lookup"><span data-stu-id="877a8-226">Layout scope</span></span> | <span data-ttu-id="877a8-227">可能的值为 `Partial` \ (重布局边界是 DOM\) 或 的一部分 `Whole document` 。</span><span class="sxs-lookup"><span data-stu-id="877a8-227">Possible values are `Partial` \(the re-layout boundary is a portion of the DOM\) or `Whole document`.</span></span> |  
| <span data-ttu-id="877a8-228">受影响的元素</span><span class="sxs-lookup"><span data-stu-id="877a8-228">Elements affected</span></span> | <span data-ttu-id="877a8-229">对于"重新计算样式记录"，为受样式重新计算影响的元素数。</span><span class="sxs-lookup"><span data-stu-id="877a8-229">For Recalculate style records, the number of elements affected by a style recalculation.</span></span> |  
| <span data-ttu-id="877a8-230">样式无效</span><span class="sxs-lookup"><span data-stu-id="877a8-230">Styles invalidated</span></span> | <span data-ttu-id="877a8-231">对于"重新计算样式"记录，提供导致样式无效的代码的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="877a8-231">For Recalculate style records, provides the stack trace of the code that caused the style invalidation.</span></span> |  

## <a name="painting-events"></a><span data-ttu-id="877a8-232">Painting 事件</span><span class="sxs-lookup"><span data-stu-id="877a8-232">Painting events</span></span>  

<span data-ttu-id="877a8-233">此部分列出了属于 Painting 类别的事件及其属性。</span><span class="sxs-lookup"><span data-stu-id="877a8-233">This section lists events that belong to Painting category and their properties.</span></span>  

| <span data-ttu-id="877a8-234">事件</span><span class="sxs-lookup"><span data-stu-id="877a8-234">Event</span></span> | <span data-ttu-id="877a8-235">说明</span><span class="sxs-lookup"><span data-stu-id="877a8-235">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="877a8-236">复合层</span><span class="sxs-lookup"><span data-stu-id="877a8-236">Composite Layers</span></span> | <span data-ttu-id="877a8-237">用于呈现引擎的复合Microsoft Edge层。</span><span class="sxs-lookup"><span data-stu-id="877a8-237">The composited image layers for the Microsoft Edge rendering engine.</span></span> |  
| <span data-ttu-id="877a8-238">图像解码</span><span class="sxs-lookup"><span data-stu-id="877a8-238">Image Decode</span></span> | <span data-ttu-id="877a8-239">已解码图像资源。</span><span class="sxs-lookup"><span data-stu-id="877a8-239">An image resource was decoded.</span></span> |  
| <span data-ttu-id="877a8-240">图像调整大小</span><span class="sxs-lookup"><span data-stu-id="877a8-240">Image Resize</span></span> | <span data-ttu-id="877a8-241">从图像本机尺寸调整了图像的大小。</span><span class="sxs-lookup"><span data-stu-id="877a8-241">An image was resized from its native dimensions.</span></span> |  
| <span data-ttu-id="877a8-242">画图</span><span class="sxs-lookup"><span data-stu-id="877a8-242">Paint</span></span> | <span data-ttu-id="877a8-243">复合层绘制到屏幕的一个区域。</span><span class="sxs-lookup"><span data-stu-id="877a8-243">Composited layers were painted to a region of the display.</span></span>  <span data-ttu-id="877a8-244">将鼠标悬停在画图可突出显示已更新的屏幕区域。</span><span class="sxs-lookup"><span data-stu-id="877a8-244">Hovering over a Paint record highlights the region of the display that was updated.</span></span> |  

### <a name="painting-event-properties"></a><span data-ttu-id="877a8-245">Painting 事件属性</span><span class="sxs-lookup"><span data-stu-id="877a8-245">Painting event properties</span></span>  

| <span data-ttu-id="877a8-246">属性</span><span class="sxs-lookup"><span data-stu-id="877a8-246">Property</span></span> | <span data-ttu-id="877a8-247">说明</span><span class="sxs-lookup"><span data-stu-id="877a8-247">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="877a8-248">位置</span><span class="sxs-lookup"><span data-stu-id="877a8-248">Location</span></span> | <span data-ttu-id="877a8-249">对于画图，绘制矩形的 x 和 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="877a8-249">For Paint events, the x and y coordinates of the paint rectangle.</span></span> |  
| <span data-ttu-id="877a8-250">维度</span><span class="sxs-lookup"><span data-stu-id="877a8-250">Dimensions</span></span> | <span data-ttu-id="877a8-251">对于画图，为绘制区域的高度和宽度。</span><span class="sxs-lookup"><span data-stu-id="877a8-251">For Paint events, the height and width of the painted region.</span></span> |  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="877a8-252">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="877a8-252">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->

[ConsoleApiTime]: /microsoft-edge/devtools-guide-chromium/console/api#time "time - 控制台 API 参考"  
[ConsoleApiTimeEnd]: /microsoft-edge/devtools-guide-chromium/console/api#timeend "timeEnd - 控制台 API 参考"  
<!--[EvaluatePerformanceTimelineTool]: timeline-tool "How to Use the Timeline Tool"  -->

[MDNWindowDOMContentLoadedEvent]: https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded "窗口：DOMContentLoaded 事件|MDN"  
[MDNWindowOrWorkerGlobalScopeSetInterval]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setInterval "WindowOrWorkerGlobalScope.setInterval () |MDN"  
[MDNWindowOrWorkerGlobalScopeSetTimeout]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setTimeout "WindowOrWorkerGlobalScope.setTimeout () |MDN"  

> [!NOTE]
> <span data-ttu-id="877a8-258">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="877a8-258">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="877a8-259">原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference)由[Meggin Kearney][MegginKearney] \ (Tech Writer\) and [Flavio Copes][FlavioCopes] \ (Full Stack Developer\) 创作。</span><span class="sxs-lookup"><span data-stu-id="877a8-259">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Flavio Copes][FlavioCopes] \(Full Stack Developer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="877a8-261">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="877a8-261">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[FlavioCopes]: https://developers.google.com/web/resources/contributors/flaviocopes  
