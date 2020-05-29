---
title: 日程表事件参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: e5f0807204877ce034fd52ea4535795ea80ba394
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611718"
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





# <span data-ttu-id="25174-103">日程表事件参考</span><span class="sxs-lookup"><span data-stu-id="25174-103">Timeline Event Reference</span></span>   




<span data-ttu-id="25174-104">"日程表事件" 模式显示录制时触发的所有事件。</span><span class="sxs-lookup"><span data-stu-id="25174-104">The timeline events mode displays all events triggered while making a recording.</span></span>  <span data-ttu-id="25174-105">使用日程表事件参考了解有关每个日程表事件类型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="25174-105">Use the timeline event reference to learn more about each timeline event type.</span></span>  

## <span data-ttu-id="25174-106">常用日程表事件属性</span><span class="sxs-lookup"><span data-stu-id="25174-106">Common timeline event properties</span></span>  

<span data-ttu-id="25174-107">某些详细信息存在于所有类型的事件中，而有些仅适用于某些事件类型。</span><span class="sxs-lookup"><span data-stu-id="25174-107">Certain details are present in events of all types, while some only apply to certain event types.</span></span>  <span data-ttu-id="25174-108">本部分列出了不同事件类型的常见属性。</span><span class="sxs-lookup"><span data-stu-id="25174-108">This section lists properties common to different event types.</span></span>  <span data-ttu-id="25174-109">以下事件类型的参考中列出了特定于某些事件类型的属性。</span><span class="sxs-lookup"><span data-stu-id="25174-109">Properties specific to certain event types are listed in the references for those event types that follow.</span></span>  

| <span data-ttu-id="25174-110">属性</span><span class="sxs-lookup"><span data-stu-id="25174-110">Property</span></span> | <span data-ttu-id="25174-111">何时显示</span><span class="sxs-lookup"><span data-stu-id="25174-111">When is it shown</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="25174-112">总时间</span><span class="sxs-lookup"><span data-stu-id="25174-112">Aggregated time</span></span> | <span data-ttu-id="25174-113">对于包含**嵌套事件**的事件，每个事件类别所花的时间。</span><span class="sxs-lookup"><span data-stu-id="25174-113">For events with **nested events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="25174-114">调用堆栈</span><span class="sxs-lookup"><span data-stu-id="25174-114">Call Stack</span></span> | <span data-ttu-id="25174-115">对于包含**子事件**的事件，每个事件类别所花的时间。</span><span class="sxs-lookup"><span data-stu-id="25174-115">For events with **child events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="25174-116">CPU 时间</span><span class="sxs-lookup"><span data-stu-id="25174-116">CPU time</span></span> | <span data-ttu-id="25174-117">录制事件花费的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="25174-117">How much CPU time the recorded event took.</span></span> |  
| <span data-ttu-id="25174-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="25174-118">Details</span></span> | <span data-ttu-id="25174-119">有关事件的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="25174-119">Other details about the event.</span></span> |  
| <span data-ttu-id="25174-120">工期 \ （at 时间戳 \）</span><span class="sxs-lookup"><span data-stu-id="25174-120">Duration \(at time-stamp\)</span></span> | <span data-ttu-id="25174-121">事件与所有子元素的完全相同的时间时间戳是事件发生的时间，相对于录制开始的时间。</span><span class="sxs-lookup"><span data-stu-id="25174-121">How long it took the event with all of its children to complete; timestamp is the time at which the event occurred, relative to when the recording started.</span></span> |  
| <span data-ttu-id="25174-122">自我时间</span><span class="sxs-lookup"><span data-stu-id="25174-122">Self time</span></span> | <span data-ttu-id="25174-123">事件在没有任何子级的情况下花费的时间。</span><span class="sxs-lookup"><span data-stu-id="25174-123">How long the event took without any of its children.</span></span> |  
| <span data-ttu-id="25174-124">使用的堆大小</span><span class="sxs-lookup"><span data-stu-id="25174-124">Used Heap Size</span></span> | <span data-ttu-id="25174-125">在记录事件时应用程序正在使用的内存量，以及自上次取样以来所使用的堆大小的增量 \ （+/）更改。</span><span class="sxs-lookup"><span data-stu-id="25174-125">Amount of memory being used by the application when the event was recorded, and the delta \(+/-\) change in used heap size since the last sampling.</span></span> |  

<!--todo: add nested and child events (timelinetool) section when available -->  

## <span data-ttu-id="25174-126">加载事件</span><span class="sxs-lookup"><span data-stu-id="25174-126">Loading events</span></span>  

<span data-ttu-id="25174-127">此部分列出了属于加载类别及其属性的事件。</span><span class="sxs-lookup"><span data-stu-id="25174-127">This section lists events that belong to Loading category and their properties.</span></span>  

| <span data-ttu-id="25174-128">事件</span><span class="sxs-lookup"><span data-stu-id="25174-128">Event</span></span> | <span data-ttu-id="25174-129">描述</span><span class="sxs-lookup"><span data-stu-id="25174-129">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="25174-130">分析 HTML</span><span class="sxs-lookup"><span data-stu-id="25174-130">Parse HTML</span></span> |  <span data-ttu-id="25174-131">Microsoft Edge 运行了 HTML 分析算法。</span><span class="sxs-lookup"><span data-stu-id="25174-131">Microsoft Edge ran the HTML parsing algorithm.</span></span> |  
| <span data-ttu-id="25174-132">完成加载</span><span class="sxs-lookup"><span data-stu-id="25174-132">Finish Loading</span></span> |  <span data-ttu-id="25174-133">网络请求已完成。</span><span class="sxs-lookup"><span data-stu-id="25174-133">A network request completed.</span></span> |  
| <span data-ttu-id="25174-134">接收数据</span><span class="sxs-lookup"><span data-stu-id="25174-134">Receive Data</span></span> |  <span data-ttu-id="25174-135">已收到请求的数据。</span><span class="sxs-lookup"><span data-stu-id="25174-135">Data for a request was received.</span></span>  <span data-ttu-id="25174-136">有一个或多个接收数据事件。</span><span class="sxs-lookup"><span data-stu-id="25174-136">There are one or more Receive Data events.</span></span> |  
| <span data-ttu-id="25174-137">接收答复</span><span class="sxs-lookup"><span data-stu-id="25174-137">Receive Response</span></span> |  <span data-ttu-id="25174-138">来自请求的初始 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="25174-138">The initial HTTP response from a request.</span></span> |  
| <span data-ttu-id="25174-139">发送请求</span><span class="sxs-lookup"><span data-stu-id="25174-139">Send Request</span></span> |  <span data-ttu-id="25174-140">已发送网络请求。</span><span class="sxs-lookup"><span data-stu-id="25174-140">A network request has been sent.</span></span> |  

### <span data-ttu-id="25174-141">加载事件属性</span><span class="sxs-lookup"><span data-stu-id="25174-141">Loading event properties</span></span>  

| <span data-ttu-id="25174-142">属性</span><span class="sxs-lookup"><span data-stu-id="25174-142">Property</span></span> | <span data-ttu-id="25174-143">描述</span><span class="sxs-lookup"><span data-stu-id="25174-143">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="25174-144">资源</span><span class="sxs-lookup"><span data-stu-id="25174-144">Resource</span></span> | <span data-ttu-id="25174-145">所请求的资源的 URL。</span><span class="sxs-lookup"><span data-stu-id="25174-145">The URL of the requested resource.</span></span> |  
| <span data-ttu-id="25174-146">预览</span><span class="sxs-lookup"><span data-stu-id="25174-146">Preview</span></span> | <span data-ttu-id="25174-147">所请求资源的预览 \ （仅图像 \）。</span><span class="sxs-lookup"><span data-stu-id="25174-147">Preview of the requested resource \(images only\).</span></span> |  
| <span data-ttu-id="25174-148">请求方法</span><span class="sxs-lookup"><span data-stu-id="25174-148">Request Method</span></span> | <span data-ttu-id="25174-149">用于请求的 HTTP 方法 \ （ `GET` 或 `POST` ，例如 \）。</span><span class="sxs-lookup"><span data-stu-id="25174-149">HTTP method used for the request \(`GET` or `POST`, for example\).</span></span> |  
| <span data-ttu-id="25174-150">状态代码</span><span class="sxs-lookup"><span data-stu-id="25174-150">Status Code</span></span> | <span data-ttu-id="25174-151">HTTP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="25174-151">HTTP response code.</span></span> |  
| <span data-ttu-id="25174-152">MIME 类型</span><span class="sxs-lookup"><span data-stu-id="25174-152">MIME Type</span></span> | <span data-ttu-id="25174-153">所请求资源的 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="25174-153">MIME type of the requested resource.</span></span> |  
| <span data-ttu-id="25174-154">编码数据长度</span><span class="sxs-lookup"><span data-stu-id="25174-154">Encoded Data Length</span></span> | <span data-ttu-id="25174-155">请求的资源的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="25174-155">Length of requested resource in bytes.</span></span> |  

## <span data-ttu-id="25174-156">脚本事件</span><span class="sxs-lookup"><span data-stu-id="25174-156">Scripting events</span></span>  

<span data-ttu-id="25174-157">此部分列出了属于脚本类别及其属性的事件。</span><span class="sxs-lookup"><span data-stu-id="25174-157">This section lists events that belong to the Scripting category and their properties.</span></span>  

| <span data-ttu-id="25174-158">事件</span><span class="sxs-lookup"><span data-stu-id="25174-158">Event</span></span> | <span data-ttu-id="25174-159">描述</span><span class="sxs-lookup"><span data-stu-id="25174-159">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="25174-160">激发的动画帧</span><span class="sxs-lookup"><span data-stu-id="25174-160">Animation Frame Fired</span></span> | <span data-ttu-id="25174-161">引发计划动画帧，并调用其回调处理程序。</span><span class="sxs-lookup"><span data-stu-id="25174-161">A scheduled animation frame fired, and its callback handler invoked.</span></span> |  
| <span data-ttu-id="25174-162">取消动画帧</span><span class="sxs-lookup"><span data-stu-id="25174-162">Cancel Animation Frame</span></span> |  <span data-ttu-id="25174-163">已取消计划的动画帧。</span><span class="sxs-lookup"><span data-stu-id="25174-163">A scheduled animation frame was canceled.</span></span> |  
| <span data-ttu-id="25174-164">GC 事件</span><span class="sxs-lookup"><span data-stu-id="25174-164">GC Event</span></span> |  <span data-ttu-id="25174-165">发生垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="25174-165">Garbage collection occurred.</span></span> |  
| <span data-ttu-id="25174-166">DOMContentLoaded</span><span class="sxs-lookup"><span data-stu-id="25174-166">DOMContentLoaded</span></span> |  <span data-ttu-id="25174-167">浏览器激发了[DOMContentLoaded 事件][MDNWindowDOMContentLoadedEvent]。</span><span class="sxs-lookup"><span data-stu-id="25174-167">The [DOMContentLoaded event][MDNWindowDOMContentLoadedEvent] was fired by the browser.</span></span>  <span data-ttu-id="25174-168">当已加载和分析页面的所有 DOM 内容时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="25174-168">This event is fired when all of the page's DOM content has been loaded and parsed.</span></span> |  
| <span data-ttu-id="25174-169">计算脚本</span><span class="sxs-lookup"><span data-stu-id="25174-169">Evaluate Script</span></span> | <span data-ttu-id="25174-170">已评估脚本。</span><span class="sxs-lookup"><span data-stu-id="25174-170">A script was evaluated.</span></span> |  
| <span data-ttu-id="25174-171">事件</span><span class="sxs-lookup"><span data-stu-id="25174-171">Event</span></span> | <span data-ttu-id="25174-172">JavaScript 事件 \ （例如， `mousedown` 或 `key` \）。</span><span class="sxs-lookup"><span data-stu-id="25174-172">A JavaScript event \(for example, `mousedown`, or `key`\).</span></span> |  
| <span data-ttu-id="25174-173">函数调用</span><span class="sxs-lookup"><span data-stu-id="25174-173">Function Call</span></span> | <span data-ttu-id="25174-174">已创建顶级 JavaScript 函数调用 \ （仅当浏览器进入 JavaScript 引擎 \ 时才出现）。</span><span class="sxs-lookup"><span data-stu-id="25174-174">A top-level JavaScript function call was made \(only appears when browser enters JavaScript engine\).</span></span> |  
| <span data-ttu-id="25174-175">安装计时器</span><span class="sxs-lookup"><span data-stu-id="25174-175">Install Timer</span></span> | <span data-ttu-id="25174-176">使用[setInterval （）][MDNWindowOrWorkerGlobalScopeSetInterval]或[setTimeout （）][MDNWindowOrWorkerGlobalScopeSetTimeout]创建了计时器。</span><span class="sxs-lookup"><span data-stu-id="25174-176">A timer was created with [setInterval()][MDNWindowOrWorkerGlobalScopeSetInterval] or [setTimeout()][MDNWindowOrWorkerGlobalScopeSetTimeout].</span></span> |  
| <span data-ttu-id="25174-177">请求动画帧</span><span class="sxs-lookup"><span data-stu-id="25174-177">Request Animation Frame</span></span> | <span data-ttu-id="25174-178">`requestAnimationFrame()`通话安排了一个新帧。</span><span class="sxs-lookup"><span data-stu-id="25174-178">A `requestAnimationFrame()` call scheduled a new frame.</span></span> |  
| <span data-ttu-id="25174-179">删除计时器</span><span class="sxs-lookup"><span data-stu-id="25174-179">Remove Timer</span></span> | <span data-ttu-id="25174-180">以前创建的计时器已清除。</span><span class="sxs-lookup"><span data-stu-id="25174-180">A previously created timer was cleared.</span></span> |  
| <span data-ttu-id="25174-181">时间</span><span class="sxs-lookup"><span data-stu-id="25174-181">Time</span></span> |  <span data-ttu-id="25174-182">名为 console 的脚本[（）][ConsoleApiTime]。</span><span class="sxs-lookup"><span data-stu-id="25174-182">A script called [console.time()][ConsoleApiTime].</span></span> |  
| <span data-ttu-id="25174-183">结束时间</span><span class="sxs-lookup"><span data-stu-id="25174-183">Time End</span></span> | <span data-ttu-id="25174-184">名为[timeEnd （）][ConsoleApiTimeEnd]的脚本。</span><span class="sxs-lookup"><span data-stu-id="25174-184">A script called [console.timeEnd()][ConsoleApiTimeEnd].</span></span> |  
| <span data-ttu-id="25174-185">计时器已激发</span><span class="sxs-lookup"><span data-stu-id="25174-185">Timer Fired</span></span> | <span data-ttu-id="25174-186">通过 or 计划引发的计时器 `setInterval()` `setTimeout()` 。</span><span class="sxs-lookup"><span data-stu-id="25174-186">A timer fired that was scheduled with `setInterval()` or `setTimeout()`.</span></span> |  
| <span data-ttu-id="25174-187">XHR 准备状态更改</span><span class="sxs-lookup"><span data-stu-id="25174-187">XHR Ready State Change</span></span> | <span data-ttu-id="25174-188">XMLHTTPRequest 的准备状态已更改。</span><span class="sxs-lookup"><span data-stu-id="25174-188">The ready state of an XMLHTTPRequest changed.</span></span> |  
| <span data-ttu-id="25174-189">XHR 负载</span><span class="sxs-lookup"><span data-stu-id="25174-189">XHR Load</span></span> | <span data-ttu-id="25174-190">`XMLHTTPRequest`已完成加载。</span><span class="sxs-lookup"><span data-stu-id="25174-190">An `XMLHTTPRequest` finished loading.</span></span> |  

### <span data-ttu-id="25174-191">脚本事件属性</span><span class="sxs-lookup"><span data-stu-id="25174-191">Scripting event properties</span></span>  

| <span data-ttu-id="25174-192">属性</span><span class="sxs-lookup"><span data-stu-id="25174-192">Property</span></span> | <span data-ttu-id="25174-193">描述</span><span class="sxs-lookup"><span data-stu-id="25174-193">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="25174-194">计时器 ID</span><span class="sxs-lookup"><span data-stu-id="25174-194">Timer ID</span></span> | <span data-ttu-id="25174-195">计时器 ID。</span><span class="sxs-lookup"><span data-stu-id="25174-195">The timer ID.</span></span> |  
| <span data-ttu-id="25174-196">超时</span><span class="sxs-lookup"><span data-stu-id="25174-196">Timeout</span></span> | <span data-ttu-id="25174-197">计时器指定的超时值。</span><span class="sxs-lookup"><span data-stu-id="25174-197">The timeout specified by the timer.</span></span> |  
| <span data-ttu-id="25174-198">播放</span><span class="sxs-lookup"><span data-stu-id="25174-198">Repeats</span></span> | <span data-ttu-id="25174-199">指定计时器是否重复的布尔值。</span><span class="sxs-lookup"><span data-stu-id="25174-199">Boolean that specifies if the timer repeats.</span></span> |  
| <span data-ttu-id="25174-200">函数调用</span><span class="sxs-lookup"><span data-stu-id="25174-200">Function Call</span></span> | <span data-ttu-id="25174-201">已调用的函数。</span><span class="sxs-lookup"><span data-stu-id="25174-201">A function that was invoked.</span></span> |  

## <span data-ttu-id="25174-202">呈现事件</span><span class="sxs-lookup"><span data-stu-id="25174-202">Rendering events</span></span>  

<span data-ttu-id="25174-203">此部分列出了属于呈现类别及其属性的事件。</span><span class="sxs-lookup"><span data-stu-id="25174-203">This section lists events that belong to Rendering category and their properties.</span></span>  

| <span data-ttu-id="25174-204">事件</span><span class="sxs-lookup"><span data-stu-id="25174-204">Event</span></span> | <span data-ttu-id="25174-205">描述</span><span class="sxs-lookup"><span data-stu-id="25174-205">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="25174-206">使布局无效</span><span class="sxs-lookup"><span data-stu-id="25174-206">Invalidate layout</span></span> | <span data-ttu-id="25174-207">DOM 更改使页面布局失效。</span><span class="sxs-lookup"><span data-stu-id="25174-207">The page layout was invalidated by a DOM change.</span></span> |  
| <span data-ttu-id="25174-208">布局</span><span class="sxs-lookup"><span data-stu-id="25174-208">Layout</span></span> | <span data-ttu-id="25174-209">已完成页面布局。</span><span class="sxs-lookup"><span data-stu-id="25174-209">A page layout was completed.</span></span> |  
| <span data-ttu-id="25174-210">重新计算样式</span><span class="sxs-lookup"><span data-stu-id="25174-210">Recalculate style</span></span> | <span data-ttu-id="25174-211">Microsoft Edge 重新计算的元素样式。</span><span class="sxs-lookup"><span data-stu-id="25174-211">Microsoft Edge recalculated element styles.</span></span> |  
| <span data-ttu-id="25174-212">滚动</span><span class="sxs-lookup"><span data-stu-id="25174-212">Scroll</span></span> | <span data-ttu-id="25174-213">已滚动嵌套视图的内容。</span><span class="sxs-lookup"><span data-stu-id="25174-213">The content of nested view was scrolled.</span></span> |  

### <span data-ttu-id="25174-214">呈现事件属性</span><span class="sxs-lookup"><span data-stu-id="25174-214">Rendering event properties</span></span>  

| <span data-ttu-id="25174-215">属性</span><span class="sxs-lookup"><span data-stu-id="25174-215">Property</span></span> | <span data-ttu-id="25174-216">描述</span><span class="sxs-lookup"><span data-stu-id="25174-216">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="25174-217">布局无效</span><span class="sxs-lookup"><span data-stu-id="25174-217">Layout invalidated</span></span> | <span data-ttu-id="25174-218">对于布局记录，导致布局失效的代码的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="25174-218">For Layout records, the stack trace of the code that caused the layout to be invalidated.</span></span> |  
| <span data-ttu-id="25174-219">需要布局的节点</span><span class="sxs-lookup"><span data-stu-id="25174-219">Nodes that need layout</span></span> | <span data-ttu-id="25174-220">对于布局记录，在 relayout 开始之前标记为需要布局的节点数。</span><span class="sxs-lookup"><span data-stu-id="25174-220">For Layout records, the number of nodes that were marked as needing layout before the relayout started.</span></span>  <span data-ttu-id="25174-221">这些节点通常是由开发人员代码无效的节点，还包括指向 relayout 根的路径。</span><span class="sxs-lookup"><span data-stu-id="25174-221">These are normally those nodes that were invalidated by developer code, plus a path upward to relayout root.</span></span> |  
| <span data-ttu-id="25174-222">布局树大小</span><span class="sxs-lookup"><span data-stu-id="25174-222">Layout tree size</span></span> | <span data-ttu-id="25174-223">对于布局记录，relayout 根节点下的总节点数 \ （Microsoft Edge 启动 relayout \ 的节点）。</span><span class="sxs-lookup"><span data-stu-id="25174-223">For Layout records, the total number of nodes under the relayout root \(the node that Microsoft Edge starts the relayout\).</span></span> |  
| <span data-ttu-id="25174-224">布局范围</span><span class="sxs-lookup"><span data-stu-id="25174-224">Layout scope</span></span> | <span data-ttu-id="25174-225">可能的值为 `Partial` \ （重新布局边界是 DOM 的一部分）或 `Whole document` 。</span><span class="sxs-lookup"><span data-stu-id="25174-225">Possible values are `Partial` \(the re-layout boundary is a portion of the DOM\) or `Whole document`.</span></span> |  
| <span data-ttu-id="25174-226">受影响的元素</span><span class="sxs-lookup"><span data-stu-id="25174-226">Elements affected</span></span> | <span data-ttu-id="25174-227">对于重新计算样式记录，受样式重新计算影响的元素数。</span><span class="sxs-lookup"><span data-stu-id="25174-227">For Recalculate style records, the number of elements affected by a style recalculation.</span></span> |  
| <span data-ttu-id="25174-228">样式无效</span><span class="sxs-lookup"><span data-stu-id="25174-228">Styles invalidated</span></span> | <span data-ttu-id="25174-229">对于 "重新计算" 样式记录，提供导致样式无效的代码的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="25174-229">For Recalculate style records, provides the stack trace of the code that caused the style invalidation.</span></span> |  

## <span data-ttu-id="25174-230">绘制事件</span><span class="sxs-lookup"><span data-stu-id="25174-230">Painting events</span></span>  

<span data-ttu-id="25174-231">此部分列出了属于 Painting 类别及其属性的事件。</span><span class="sxs-lookup"><span data-stu-id="25174-231">This section lists events that belong to Painting category and their properties.</span></span>  

| <span data-ttu-id="25174-232">事件</span><span class="sxs-lookup"><span data-stu-id="25174-232">Event</span></span> | <span data-ttu-id="25174-233">描述</span><span class="sxs-lookup"><span data-stu-id="25174-233">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="25174-234">复合图层</span><span class="sxs-lookup"><span data-stu-id="25174-234">Composite Layers</span></span> | <span data-ttu-id="25174-235">Microsoft Edge 呈现引擎的合成图像图层。</span><span class="sxs-lookup"><span data-stu-id="25174-235">The composited image layers for the Microsoft Edge rendering engine.</span></span> |  
| <span data-ttu-id="25174-236">图像解码</span><span class="sxs-lookup"><span data-stu-id="25174-236">Image Decode</span></span> | <span data-ttu-id="25174-237">图像资源已解码。</span><span class="sxs-lookup"><span data-stu-id="25174-237">An image resource was decoded.</span></span> |  
| <span data-ttu-id="25174-238">图像调整大小</span><span class="sxs-lookup"><span data-stu-id="25174-238">Image Resize</span></span> | <span data-ttu-id="25174-239">从其本机尺寸调整图像大小。</span><span class="sxs-lookup"><span data-stu-id="25174-239">An image was resized from its native dimensions.</span></span> |  
| <span data-ttu-id="25174-240">画图</span><span class="sxs-lookup"><span data-stu-id="25174-240">Paint</span></span> | <span data-ttu-id="25174-241">复合图层已绘制到显示区域。</span><span class="sxs-lookup"><span data-stu-id="25174-241">Composited layers were painted to a region of the display.</span></span>  <span data-ttu-id="25174-242">将鼠标悬停在 "画图" 记录上将突出显示已更新的显示区域。</span><span class="sxs-lookup"><span data-stu-id="25174-242">Hovering over a Paint record highlights the region of the display that was updated.</span></span> |  

### <span data-ttu-id="25174-243">绘制事件属性</span><span class="sxs-lookup"><span data-stu-id="25174-243">Painting event properties</span></span>  

| <span data-ttu-id="25174-244">属性</span><span class="sxs-lookup"><span data-stu-id="25174-244">Property</span></span> | <span data-ttu-id="25174-245">说明</span><span class="sxs-lookup"><span data-stu-id="25174-245">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="25174-246">位置</span><span class="sxs-lookup"><span data-stu-id="25174-246">Location</span></span> | <span data-ttu-id="25174-247">对于画图事件，绘制矩形的 x 和 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="25174-247">For Paint events, the x and y coordinates of the paint rectangle.</span></span> |  
| <span data-ttu-id="25174-248">三维</span><span class="sxs-lookup"><span data-stu-id="25174-248">Dimensions</span></span> | <span data-ttu-id="25174-249">对于 "画图" 事件，即绘制区域的高度和宽度。</span><span class="sxs-lookup"><span data-stu-id="25174-249">For Paint events, the height and width of the painted region.</span></span> |  

 



<!-- image links -->  

<!-- links -->

[ConsoleApiTime]: /microsoft-edge/devtools-guide-chromium/console/api#time "时间-控制台 API 参考"  
[ConsoleApiTimeEnd]: /microsoft-edge/devtools-guide-chromium/console/api#timeend "timeEnd-控制台 API 参考"  
<!--[EvaluatePerformanceTimelineTool]: timeline-tool "How to Use the Timeline Tool"  -->

[MDNWindowDOMContentLoadedEvent]: https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded "窗口： DOMContentLoaded 事件 |MDN"  
[MDNWindowOrWorkerGlobalScopeSetInterval]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setInterval "WindowOrWorkerGlobalScope setInterval （） |MDN"  
[MDNWindowOrWorkerGlobalScopeSetTimeout]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setTimeout "WindowOrWorkerGlobalScope setTimeout （） |MDN"  

> [!NOTE]
> <span data-ttu-id="25174-255">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="25174-255">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="25174-256">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference)，由[Meggin Kearney][MegginKearney] \ （技术作者 \）和[Flavio Copes][FlavioCopes] \ （完整堆栈开发人员 \）创作。</span><span class="sxs-lookup"><span data-stu-id="25174-256">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Flavio Copes][FlavioCopes] \(Full Stack Developer\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="25174-258">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="25174-258">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[FlavioCopes]: https://developers.google.com/web/resources/contributors/flaviocopes  
