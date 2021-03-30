---
description: 时间线事件模式显示录制时触发的所有事件。  使用时间线事件引用了解有关每个时间线事件类型更多信息。
title: 时间线事件引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
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

# <a name="timeline-event-reference"></a><span data-ttu-id="4f6cf-105">时间线事件引用</span><span class="sxs-lookup"><span data-stu-id="4f6cf-105">Timeline Event reference</span></span>  

<span data-ttu-id="4f6cf-106">时间线事件模式显示录制时触发的所有事件。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-106">The timeline events mode displays all events triggered while making a recording.</span></span>  <span data-ttu-id="4f6cf-107">使用时间线事件引用了解有关每个时间线事件类型更多信息。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-107">Use the timeline event reference to learn more about each timeline event type.</span></span>  

## <a name="common-timeline-event-properties"></a><span data-ttu-id="4f6cf-108">常见时间线事件属性</span><span class="sxs-lookup"><span data-stu-id="4f6cf-108">Common timeline event properties</span></span>  

<span data-ttu-id="4f6cf-109">某些详细信息存在于所有类型的事件中，而有些仅适用于特定事件类型。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-109">Certain details are present in events of all types, while some only apply to certain event types.</span></span>  <span data-ttu-id="4f6cf-110">本节列出了不同事件类型通用的属性。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-110">This section lists properties common to different event types.</span></span>  <span data-ttu-id="4f6cf-111">特定于特定事件类型的属性在后续事件类型的引用中列出。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-111">Properties specific to certain event types are listed in the references for those event types that follow.</span></span>  

| <span data-ttu-id="4f6cf-112">属性</span><span class="sxs-lookup"><span data-stu-id="4f6cf-112">Property</span></span> | <span data-ttu-id="4f6cf-113">何时显示</span><span class="sxs-lookup"><span data-stu-id="4f6cf-113">When is it shown</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="4f6cf-114">聚合时间</span><span class="sxs-lookup"><span data-stu-id="4f6cf-114">Aggregated time</span></span> | <span data-ttu-id="4f6cf-115">对于具有 **嵌套事件的事件**，每类事件所花时间。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-115">For events with **nested events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="4f6cf-116">调用堆栈</span><span class="sxs-lookup"><span data-stu-id="4f6cf-116">Call Stack</span></span> | <span data-ttu-id="4f6cf-117">对于具有 **子事件的事件**，每类事件所花时间。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-117">For events with **child events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="4f6cf-118">CPU 时间</span><span class="sxs-lookup"><span data-stu-id="4f6cf-118">CPU time</span></span> | <span data-ttu-id="4f6cf-119">记录的事件占用的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-119">How much CPU time the recorded event took.</span></span> |  
| <span data-ttu-id="4f6cf-120">详细信息</span><span class="sxs-lookup"><span data-stu-id="4f6cf-120">Details</span></span> | <span data-ttu-id="4f6cf-121">有关事件的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-121">Other details about the event.</span></span> |  
| <span data-ttu-id="4f6cf-122">Duration \(at time-stamp\) </span><span class="sxs-lookup"><span data-stu-id="4f6cf-122">Duration \(at time-stamp\)</span></span> | <span data-ttu-id="4f6cf-123">事件及其所有子项完成所用时间;时间戳是事件发生的时间，相对于录制开始的时间。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-123">How long it took the event with all of its children to complete; timestamp is the time at which the event occurred, relative to when the recording started.</span></span> |  
| <span data-ttu-id="4f6cf-124">自用时间</span><span class="sxs-lookup"><span data-stu-id="4f6cf-124">Self time</span></span> | <span data-ttu-id="4f6cf-125">事件在没有其任何子项的情况下所用时间。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-125">How long the event took without any of its children.</span></span> |  
| <span data-ttu-id="4f6cf-126">已使用的堆大小</span><span class="sxs-lookup"><span data-stu-id="4f6cf-126">Used Heap Size</span></span> | <span data-ttu-id="4f6cf-127">记录事件时应用程序使用的内存量，以及自上次采样以来使用的堆大小的增量 \(+/-\) 变化量。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-127">Amount of memory being used by the application when the event was recorded, and the delta \(+/-\) change in used heap size since the last sampling.</span></span> |  

<!--todo: add nested and child events (timelinetool) section when available -->  

## <a name="loading-events"></a><span data-ttu-id="4f6cf-128">加载事件</span><span class="sxs-lookup"><span data-stu-id="4f6cf-128">Loading events</span></span>  

<span data-ttu-id="4f6cf-129">本节列出了属于"正在加载"类别的事件及其属性。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-129">This section lists events that belong to Loading category and their properties.</span></span>  

| <span data-ttu-id="4f6cf-130">事件</span><span class="sxs-lookup"><span data-stu-id="4f6cf-130">Event</span></span> | <span data-ttu-id="4f6cf-131">说明</span><span class="sxs-lookup"><span data-stu-id="4f6cf-131">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="4f6cf-132">分析 HTML</span><span class="sxs-lookup"><span data-stu-id="4f6cf-132">Parse HTML</span></span> |  <span data-ttu-id="4f6cf-133">Microsoft Edge 运行 HTML 分析算法。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-133">Microsoft Edge ran the HTML parsing algorithm.</span></span> |  
| <span data-ttu-id="4f6cf-134">完成加载</span><span class="sxs-lookup"><span data-stu-id="4f6cf-134">Finish Loading</span></span> |  <span data-ttu-id="4f6cf-135">网络请求已完成。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-135">A network request completed.</span></span> |  
| <span data-ttu-id="4f6cf-136">接收数据</span><span class="sxs-lookup"><span data-stu-id="4f6cf-136">Receive Data</span></span> |  <span data-ttu-id="4f6cf-137">已接收请求的数据。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-137">Data for a request was received.</span></span>  <span data-ttu-id="4f6cf-138">有一个或多个接收数据事件。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-138">There are one or more Receive Data events.</span></span> |  
| <span data-ttu-id="4f6cf-139">接收响应</span><span class="sxs-lookup"><span data-stu-id="4f6cf-139">Receive Response</span></span> |  <span data-ttu-id="4f6cf-140">来自请求的初始 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-140">The initial HTTP response from a request.</span></span> |  
| <span data-ttu-id="4f6cf-141">发送请求</span><span class="sxs-lookup"><span data-stu-id="4f6cf-141">Send Request</span></span> |  <span data-ttu-id="4f6cf-142">已发送网络请求。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-142">A network request has been sent.</span></span> |  

### <a name="loading-event-properties"></a><span data-ttu-id="4f6cf-143">加载事件属性</span><span class="sxs-lookup"><span data-stu-id="4f6cf-143">Loading event properties</span></span>  

| <span data-ttu-id="4f6cf-144">属性</span><span class="sxs-lookup"><span data-stu-id="4f6cf-144">Property</span></span> | <span data-ttu-id="4f6cf-145">说明</span><span class="sxs-lookup"><span data-stu-id="4f6cf-145">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="4f6cf-146">资源</span><span class="sxs-lookup"><span data-stu-id="4f6cf-146">Resource</span></span> | <span data-ttu-id="4f6cf-147">所请求资源的 URL。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-147">The URL of the requested resource.</span></span> |  
| <span data-ttu-id="4f6cf-148">预览</span><span class="sxs-lookup"><span data-stu-id="4f6cf-148">Preview</span></span> | <span data-ttu-id="4f6cf-149">仅预览请求的资源 \(\) 。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-149">Preview of the requested resource \(images only\).</span></span> |  
| <span data-ttu-id="4f6cf-150">Request 方法</span><span class="sxs-lookup"><span data-stu-id="4f6cf-150">Request Method</span></span> | <span data-ttu-id="4f6cf-151">用于请求 \(`GET` 或 `POST` ，例如\) 。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-151">HTTP method used for the request \(`GET` or `POST`, for example\).</span></span> |  
| <span data-ttu-id="4f6cf-152">状态代码</span><span class="sxs-lookup"><span data-stu-id="4f6cf-152">Status Code</span></span> | <span data-ttu-id="4f6cf-153">HTTP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-153">HTTP response code.</span></span> |  
| <span data-ttu-id="4f6cf-154">MIME 类型</span><span class="sxs-lookup"><span data-stu-id="4f6cf-154">MIME Type</span></span> | <span data-ttu-id="4f6cf-155">所请求资源的 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-155">MIME type of the requested resource.</span></span> |  
| <span data-ttu-id="4f6cf-156">编码数据长度</span><span class="sxs-lookup"><span data-stu-id="4f6cf-156">Encoded Data Length</span></span> | <span data-ttu-id="4f6cf-157">请求的资源长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-157">Length of requested resource in bytes.</span></span> |  

## <a name="scripting-events"></a><span data-ttu-id="4f6cf-158">脚本事件</span><span class="sxs-lookup"><span data-stu-id="4f6cf-158">Scripting events</span></span>  

<span data-ttu-id="4f6cf-159">本节列出了属于脚本类别及其属性的事件。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-159">This section lists events that belong to the Scripting category and their properties.</span></span>  

| <span data-ttu-id="4f6cf-160">事件</span><span class="sxs-lookup"><span data-stu-id="4f6cf-160">Event</span></span> | <span data-ttu-id="4f6cf-161">说明</span><span class="sxs-lookup"><span data-stu-id="4f6cf-161">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="4f6cf-162">触发动画帧</span><span class="sxs-lookup"><span data-stu-id="4f6cf-162">Animation Frame Fired</span></span> | <span data-ttu-id="4f6cf-163">触发的计划动画帧及其回调处理程序已调用。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-163">A scheduled animation frame fired, and its callback handler invoked.</span></span> |  
| <span data-ttu-id="4f6cf-164">取消动画帧</span><span class="sxs-lookup"><span data-stu-id="4f6cf-164">Cancel Animation Frame</span></span> |  <span data-ttu-id="4f6cf-165">已取消计划的动画帧。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-165">A scheduled animation frame was canceled.</span></span> |  
| <span data-ttu-id="4f6cf-166">GC 事件</span><span class="sxs-lookup"><span data-stu-id="4f6cf-166">GC Event</span></span> |  <span data-ttu-id="4f6cf-167">发生垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-167">Garbage collection occurred.</span></span> |  
| <span data-ttu-id="4f6cf-168">DOMContentLoaded</span><span class="sxs-lookup"><span data-stu-id="4f6cf-168">DOMContentLoaded</span></span> |  <span data-ttu-id="4f6cf-169">[DOMContentLoaded 事件][MDNWindowDOMContentLoadedEvent]由浏览器触发。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-169">The [DOMContentLoaded event][MDNWindowDOMContentLoadedEvent] was fired by the browser.</span></span>  <span data-ttu-id="4f6cf-170">加载和分析页面的所有 DOM 内容时，将触发此事件。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-170">This event is fired when all of the DOM content of the page is loaded and parsed.</span></span> |  
| <span data-ttu-id="4f6cf-171">评估脚本</span><span class="sxs-lookup"><span data-stu-id="4f6cf-171">Evaluate Script</span></span> | <span data-ttu-id="4f6cf-172">已评估脚本。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-172">A script was evaluated.</span></span> |  
| <span data-ttu-id="4f6cf-173">事件</span><span class="sxs-lookup"><span data-stu-id="4f6cf-173">Event</span></span> | <span data-ttu-id="4f6cf-174">JavaScript 事件 \(例如 `mousedown` ，或 `key` \) 。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-174">A JavaScript event \(for example, `mousedown`, or `key`\).</span></span> |  
| <span data-ttu-id="4f6cf-175">函数调用</span><span class="sxs-lookup"><span data-stu-id="4f6cf-175">Function Call</span></span> | <span data-ttu-id="4f6cf-176">仅在浏览器进入 JavaScript 引擎\(时，才出现顶级 JavaScript 函数调用) 。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-176">A top-level JavaScript function call was made \(only appears when browser enters JavaScript engine\).</span></span> |  
| <span data-ttu-id="4f6cf-177">安装计时器</span><span class="sxs-lookup"><span data-stu-id="4f6cf-177">Install Timer</span></span> | <span data-ttu-id="4f6cf-178">计时器是使用[setInterval () ][MDNWindowOrWorkerGlobalScopeSetInterval][或 setTimeout () 。 ][MDNWindowOrWorkerGlobalScopeSetTimeout]</span><span class="sxs-lookup"><span data-stu-id="4f6cf-178">A timer was created with [setInterval()][MDNWindowOrWorkerGlobalScopeSetInterval] or [setTimeout()][MDNWindowOrWorkerGlobalScopeSetTimeout].</span></span> |  
| <span data-ttu-id="4f6cf-179">请求动画帧</span><span class="sxs-lookup"><span data-stu-id="4f6cf-179">Request Animation Frame</span></span> | <span data-ttu-id="4f6cf-180">安排 `requestAnimationFrame()` 新帧的呼叫。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-180">A `requestAnimationFrame()` call scheduled a new frame.</span></span> |  
| <span data-ttu-id="4f6cf-181">删除计时器</span><span class="sxs-lookup"><span data-stu-id="4f6cf-181">Remove Timer</span></span> | <span data-ttu-id="4f6cf-182">已清除以前创建的计时器。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-182">A previously created timer was cleared.</span></span> |  
| <span data-ttu-id="4f6cf-183">时间</span><span class="sxs-lookup"><span data-stu-id="4f6cf-183">Time</span></span> |  <span data-ttu-id="4f6cf-184">一个称为 [console.time () ][ConsoleApiTime]。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-184">A script called [console.time()][ConsoleApiTime].</span></span> |  
| <span data-ttu-id="4f6cf-185">时间结束</span><span class="sxs-lookup"><span data-stu-id="4f6cf-185">Time End</span></span> | <span data-ttu-id="4f6cf-186">一个称为 [console.timeEnd () ][ConsoleApiTimeEnd]。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-186">A script called [console.timeEnd()][ConsoleApiTimeEnd].</span></span> |  
| <span data-ttu-id="4f6cf-187">计时器触发</span><span class="sxs-lookup"><span data-stu-id="4f6cf-187">Timer Fired</span></span> | <span data-ttu-id="4f6cf-188">使用 或 计划触发的 `setInterval()` 计时器 `setTimeout()` 。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-188">A timer fired that was scheduled with `setInterval()` or `setTimeout()`.</span></span> |  
| <span data-ttu-id="4f6cf-189">XHR 就绪状态更改</span><span class="sxs-lookup"><span data-stu-id="4f6cf-189">XHR Ready State Change</span></span> | <span data-ttu-id="4f6cf-190">XMLHTTPRequest 的就绪状态已更改。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-190">The ready state of an XMLHTTPRequest changed.</span></span> |  
| <span data-ttu-id="4f6cf-191">XHR 加载</span><span class="sxs-lookup"><span data-stu-id="4f6cf-191">XHR Load</span></span> | <span data-ttu-id="4f6cf-192">已完成 `XMLHTTPRequest` 加载。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-192">An `XMLHTTPRequest` finished loading.</span></span> |  

### <a name="scripting-event-properties"></a><span data-ttu-id="4f6cf-193">脚本事件属性</span><span class="sxs-lookup"><span data-stu-id="4f6cf-193">Scripting event properties</span></span>  

| <span data-ttu-id="4f6cf-194">属性</span><span class="sxs-lookup"><span data-stu-id="4f6cf-194">Property</span></span> | <span data-ttu-id="4f6cf-195">说明</span><span class="sxs-lookup"><span data-stu-id="4f6cf-195">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="4f6cf-196">计时器 ID</span><span class="sxs-lookup"><span data-stu-id="4f6cf-196">Timer ID</span></span> | <span data-ttu-id="4f6cf-197">计时器 ID。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-197">The timer ID.</span></span> |  
| <span data-ttu-id="4f6cf-198">超时</span><span class="sxs-lookup"><span data-stu-id="4f6cf-198">Timeout</span></span> | <span data-ttu-id="4f6cf-199">计时器指定的超时。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-199">The timeout specified by the timer.</span></span> |  
| <span data-ttu-id="4f6cf-200">重复</span><span class="sxs-lookup"><span data-stu-id="4f6cf-200">Repeats</span></span> | <span data-ttu-id="4f6cf-201">指定计时器是否重复的布尔值。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-201">Boolean that specifies if the timer repeats.</span></span> |  
| <span data-ttu-id="4f6cf-202">函数调用</span><span class="sxs-lookup"><span data-stu-id="4f6cf-202">Function Call</span></span> | <span data-ttu-id="4f6cf-203">已调用的函数。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-203">A function that was invoked.</span></span> |  

## <a name="rendering-events"></a><span data-ttu-id="4f6cf-204">呈现事件</span><span class="sxs-lookup"><span data-stu-id="4f6cf-204">Rendering events</span></span>  

<span data-ttu-id="4f6cf-205">本节列出了属于"呈现"类别及其属性的事件。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-205">This section lists events that belong to Rendering category and their properties.</span></span>  

| <span data-ttu-id="4f6cf-206">事件</span><span class="sxs-lookup"><span data-stu-id="4f6cf-206">Event</span></span> | <span data-ttu-id="4f6cf-207">说明</span><span class="sxs-lookup"><span data-stu-id="4f6cf-207">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="4f6cf-208">无效布局</span><span class="sxs-lookup"><span data-stu-id="4f6cf-208">Invalidate layout</span></span> | <span data-ttu-id="4f6cf-209">页面布局因 DOM 更改而失效。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-209">The page layout was invalidated by a DOM change.</span></span> |  
| <span data-ttu-id="4f6cf-210">布局</span><span class="sxs-lookup"><span data-stu-id="4f6cf-210">Layout</span></span> | <span data-ttu-id="4f6cf-211">已完成页面布局。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-211">A page layout was completed.</span></span> |  
| <span data-ttu-id="4f6cf-212">重新计算样式</span><span class="sxs-lookup"><span data-stu-id="4f6cf-212">Recalculate style</span></span> | <span data-ttu-id="4f6cf-213">Microsoft Edge 重新计算的元素样式。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-213">Microsoft Edge recalculated element styles.</span></span> |  
| <span data-ttu-id="4f6cf-214">滚动</span><span class="sxs-lookup"><span data-stu-id="4f6cf-214">Scroll</span></span> | <span data-ttu-id="4f6cf-215">已滚动嵌套视图的内容。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-215">The content of nested view was scrolled.</span></span> |  

### <a name="rendering-event-properties"></a><span data-ttu-id="4f6cf-216">呈现事件属性</span><span class="sxs-lookup"><span data-stu-id="4f6cf-216">Rendering event properties</span></span>  

| <span data-ttu-id="4f6cf-217">属性</span><span class="sxs-lookup"><span data-stu-id="4f6cf-217">Property</span></span> | <span data-ttu-id="4f6cf-218">说明</span><span class="sxs-lookup"><span data-stu-id="4f6cf-218">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="4f6cf-219">布局无效</span><span class="sxs-lookup"><span data-stu-id="4f6cf-219">Layout invalidated</span></span> | <span data-ttu-id="4f6cf-220">对于布局记录，是导致布局失效的代码堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-220">For Layout records, the stack trace of the code that caused the layout to be invalidated.</span></span> |  
| <span data-ttu-id="4f6cf-221">需要布局的节点</span><span class="sxs-lookup"><span data-stu-id="4f6cf-221">Nodes that need layout</span></span> | <span data-ttu-id="4f6cf-222">对于布局记录，是中继启动前标记为需要布局的节点数。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-222">For Layout records, the number of nodes that were marked as needing layout before the relayout started.</span></span>  <span data-ttu-id="4f6cf-223">这些节点通常是开发人员代码失效的节点，以及中继根的向上路径。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-223">These are normally those nodes that were invalidated by developer code, plus a path upward to relayout root.</span></span> |  
| <span data-ttu-id="4f6cf-224">布局树大小</span><span class="sxs-lookup"><span data-stu-id="4f6cf-224">Layout tree size</span></span> | <span data-ttu-id="4f6cf-225">对于布局记录，中继根 \(Microsoft Edge 启动中继的节点下的节点总数) 。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-225">For Layout records, the total number of nodes under the relayout root \(the node that Microsoft Edge starts the relayout\).</span></span> |  
| <span data-ttu-id="4f6cf-226">布局范围</span><span class="sxs-lookup"><span data-stu-id="4f6cf-226">Layout scope</span></span> | <span data-ttu-id="4f6cf-227">可能的值是 \(重新布局边界是 `Partial` DOM\) 或 的一部分 `Whole document` 。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-227">Possible values are `Partial` \(the re-layout boundary is a portion of the DOM\) or `Whole document`.</span></span> |  
| <span data-ttu-id="4f6cf-228">受影响的元素</span><span class="sxs-lookup"><span data-stu-id="4f6cf-228">Elements affected</span></span> | <span data-ttu-id="4f6cf-229">对于"重新计算样式"记录，为受样式重新计算影响的元素数。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-229">For Recalculate style records, the number of elements affected by a style recalculation.</span></span> |  
| <span data-ttu-id="4f6cf-230">样式失效</span><span class="sxs-lookup"><span data-stu-id="4f6cf-230">Styles invalidated</span></span> | <span data-ttu-id="4f6cf-231">对于重新计算样式记录，提供导致样式无效的代码的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-231">For Recalculate style records, provides the stack trace of the code that caused the style invalidation.</span></span> |  

## <a name="painting-events"></a><span data-ttu-id="4f6cf-232">绘制事件</span><span class="sxs-lookup"><span data-stu-id="4f6cf-232">Painting events</span></span>  

<span data-ttu-id="4f6cf-233">本节列出了属于"绘图"类别及其属性的事件。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-233">This section lists events that belong to Painting category and their properties.</span></span>  

| <span data-ttu-id="4f6cf-234">事件</span><span class="sxs-lookup"><span data-stu-id="4f6cf-234">Event</span></span> | <span data-ttu-id="4f6cf-235">说明</span><span class="sxs-lookup"><span data-stu-id="4f6cf-235">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="4f6cf-236">复合层</span><span class="sxs-lookup"><span data-stu-id="4f6cf-236">Composite Layers</span></span> | <span data-ttu-id="4f6cf-237">Microsoft Edge 呈现引擎的复合图像层。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-237">The composited image layers for the Microsoft Edge rendering engine.</span></span> |  
| <span data-ttu-id="4f6cf-238">图像解码</span><span class="sxs-lookup"><span data-stu-id="4f6cf-238">Image Decode</span></span> | <span data-ttu-id="4f6cf-239">已解码图像资源。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-239">An image resource was decoded.</span></span> |  
| <span data-ttu-id="4f6cf-240">图像调整大小</span><span class="sxs-lookup"><span data-stu-id="4f6cf-240">Image Resize</span></span> | <span data-ttu-id="4f6cf-241">图像已调整其本机尺寸的大小。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-241">An image was resized from its native dimensions.</span></span> |  
| <span data-ttu-id="4f6cf-242">画图</span><span class="sxs-lookup"><span data-stu-id="4f6cf-242">Paint</span></span> | <span data-ttu-id="4f6cf-243">复合层已绘制到屏幕的一个区域。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-243">Composited layers were painted to a region of the display.</span></span>  <span data-ttu-id="4f6cf-244">将鼠标悬停在"画图"记录上会突出显示已更新的屏幕区域。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-244">Hovering over a Paint record highlights the region of the display that was updated.</span></span> |  

### <a name="painting-event-properties"></a><span data-ttu-id="4f6cf-245">绘制事件属性</span><span class="sxs-lookup"><span data-stu-id="4f6cf-245">Painting event properties</span></span>  

| <span data-ttu-id="4f6cf-246">属性</span><span class="sxs-lookup"><span data-stu-id="4f6cf-246">Property</span></span> | <span data-ttu-id="4f6cf-247">说明</span><span class="sxs-lookup"><span data-stu-id="4f6cf-247">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="4f6cf-248">位置</span><span class="sxs-lookup"><span data-stu-id="4f6cf-248">Location</span></span> | <span data-ttu-id="4f6cf-249">对于 Paint 事件，绘制矩形的 x 和 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-249">For Paint events, the x and y coordinates of the paint rectangle.</span></span> |  
| <span data-ttu-id="4f6cf-250">维度</span><span class="sxs-lookup"><span data-stu-id="4f6cf-250">Dimensions</span></span> | <span data-ttu-id="4f6cf-251">对于 Paint 事件，绘制区域的高度和宽度。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-251">For Paint events, the height and width of the painted region.</span></span> |  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="4f6cf-252">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="4f6cf-252">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->

[ConsoleApiTime]: /microsoft-edge/devtools-guide-chromium/console/api#time "time - 控制台 API 参考"  
[ConsoleApiTimeEnd]: /microsoft-edge/devtools-guide-chromium/console/api#timeend "timeEnd - 控制台 API 参考"  
<!--[EvaluatePerformanceTimelineTool]: timeline-tool "How to Use the Timeline Tool"  -->

[MDNWindowDOMContentLoadedEvent]: https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded "窗口：DOMContentLoaded 事件|MDN"  
[MDNWindowOrWorkerGlobalScopeSetInterval]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setInterval "WindowOrWorkerGlobalScope.setInterval () |MDN"  
[MDNWindowOrWorkerGlobalScopeSetTimeout]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setTimeout "WindowOrWorkerGlobalScope.setTimeout () |MDN"  

> [!NOTE]
> <span data-ttu-id="4f6cf-258">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-258">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4f6cf-259">原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference)由[Meggin Kearney][MegginKearney] \(Tech Writer\) 和[Flavio 管理][FlavioCopes]程序 \(Full Stack Developer\) 创作。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-259">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Flavio Copes][FlavioCopes] \(Full Stack Developer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="4f6cf-261">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="4f6cf-261">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[FlavioCopes]: https://developers.google.com/web/resources/contributors/flaviocopes  
