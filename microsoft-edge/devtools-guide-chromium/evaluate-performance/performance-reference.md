---
description: The timeline events mode displays all events triggered while making a recording.  Use the timeline event reference to learn more about each timeline event type.
title: Timeline Event Reference
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
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





# <span data-ttu-id="33068-105">Timeline Event Reference</span><span class="sxs-lookup"><span data-stu-id="33068-105">Timeline Event Reference</span></span>   




<span data-ttu-id="33068-106">The timeline events mode displays all events triggered while making a recording.</span><span class="sxs-lookup"><span data-stu-id="33068-106">The timeline events mode displays all events triggered while making a recording.</span></span>  <span data-ttu-id="33068-107">Use the timeline event reference to learn more about each timeline event type.</span><span class="sxs-lookup"><span data-stu-id="33068-107">Use the timeline event reference to learn more about each timeline event type.</span></span>  

## <span data-ttu-id="33068-108">Common timeline event properties</span><span class="sxs-lookup"><span data-stu-id="33068-108">Common timeline event properties</span></span>  

<span data-ttu-id="33068-109">Certain details are present in events of all types, while some only apply to certain event types.</span><span class="sxs-lookup"><span data-stu-id="33068-109">Certain details are present in events of all types, while some only apply to certain event types.</span></span>  <span data-ttu-id="33068-110">This section lists properties common to different event types.</span><span class="sxs-lookup"><span data-stu-id="33068-110">This section lists properties common to different event types.</span></span>  <span data-ttu-id="33068-111">Properties specific to certain event types are listed in the references for those event types that follow.</span><span class="sxs-lookup"><span data-stu-id="33068-111">Properties specific to certain event types are listed in the references for those event types that follow.</span></span>  

| <span data-ttu-id="33068-112">Property</span><span class="sxs-lookup"><span data-stu-id="33068-112">Property</span></span> | <span data-ttu-id="33068-113">When is it shown</span><span class="sxs-lookup"><span data-stu-id="33068-113">When is it shown</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="33068-114">Aggregated time</span><span class="sxs-lookup"><span data-stu-id="33068-114">Aggregated time</span></span> | <span data-ttu-id="33068-115">For events with **nested events**, the time taken by each category of events.</span><span class="sxs-lookup"><span data-stu-id="33068-115">For events with **nested events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="33068-116">Call Stack</span><span class="sxs-lookup"><span data-stu-id="33068-116">Call Stack</span></span> | <span data-ttu-id="33068-117">For events with **child events**, the time taken by each category of events.</span><span class="sxs-lookup"><span data-stu-id="33068-117">For events with **child events**, the time taken by each category of events.</span></span> |  
| <span data-ttu-id="33068-118">CPU time</span><span class="sxs-lookup"><span data-stu-id="33068-118">CPU time</span></span> | <span data-ttu-id="33068-119">How much CPU time the recorded event took.</span><span class="sxs-lookup"><span data-stu-id="33068-119">How much CPU time the recorded event took.</span></span> |  
| <span data-ttu-id="33068-120">Details</span><span class="sxs-lookup"><span data-stu-id="33068-120">Details</span></span> | <span data-ttu-id="33068-121">Other details about the event.</span><span class="sxs-lookup"><span data-stu-id="33068-121">Other details about the event.</span></span> |  
| <span data-ttu-id="33068-122">Duration \(at time-stamp\)</span><span class="sxs-lookup"><span data-stu-id="33068-122">Duration \(at time-stamp\)</span></span> | <span data-ttu-id="33068-123">How long it took the event with all of its children to complete; timestamp is the time at which the event occurred, relative to when the recording started.</span><span class="sxs-lookup"><span data-stu-id="33068-123">How long it took the event with all of its children to complete; timestamp is the time at which the event occurred, relative to when the recording started.</span></span> |  
| <span data-ttu-id="33068-124">Self time</span><span class="sxs-lookup"><span data-stu-id="33068-124">Self time</span></span> | <span data-ttu-id="33068-125">How long the event took without any of its children.</span><span class="sxs-lookup"><span data-stu-id="33068-125">How long the event took without any of its children.</span></span> |  
| <span data-ttu-id="33068-126">Used Heap Size</span><span class="sxs-lookup"><span data-stu-id="33068-126">Used Heap Size</span></span> | <span data-ttu-id="33068-127">Amount of memory being used by the application when the event was recorded, and the delta \(+/-\) change in used heap size since the last sampling.</span><span class="sxs-lookup"><span data-stu-id="33068-127">Amount of memory being used by the application when the event was recorded, and the delta \(+/-\) change in used heap size since the last sampling.</span></span> |  

<!--todo: add nested and child events (timelinetool) section when available -->  

## <span data-ttu-id="33068-128">Loading events</span><span class="sxs-lookup"><span data-stu-id="33068-128">Loading events</span></span>  

<span data-ttu-id="33068-129">This section lists events that belong to Loading category and their properties.</span><span class="sxs-lookup"><span data-stu-id="33068-129">This section lists events that belong to Loading category and their properties.</span></span>  

| <span data-ttu-id="33068-130">Event</span><span class="sxs-lookup"><span data-stu-id="33068-130">Event</span></span> | <span data-ttu-id="33068-131">Description</span><span class="sxs-lookup"><span data-stu-id="33068-131">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="33068-132">Parse HTML</span><span class="sxs-lookup"><span data-stu-id="33068-132">Parse HTML</span></span> |  <span data-ttu-id="33068-133">Microsoft Edge ran the HTML parsing algorithm.</span><span class="sxs-lookup"><span data-stu-id="33068-133">Microsoft Edge ran the HTML parsing algorithm.</span></span> |  
| <span data-ttu-id="33068-134">Finish Loading</span><span class="sxs-lookup"><span data-stu-id="33068-134">Finish Loading</span></span> |  <span data-ttu-id="33068-135">A network request completed.</span><span class="sxs-lookup"><span data-stu-id="33068-135">A network request completed.</span></span> |  
| <span data-ttu-id="33068-136">Receive Data</span><span class="sxs-lookup"><span data-stu-id="33068-136">Receive Data</span></span> |  <span data-ttu-id="33068-137">Data for a request was received.</span><span class="sxs-lookup"><span data-stu-id="33068-137">Data for a request was received.</span></span>  <span data-ttu-id="33068-138">There are one or more Receive Data events.</span><span class="sxs-lookup"><span data-stu-id="33068-138">There are one or more Receive Data events.</span></span> |  
| <span data-ttu-id="33068-139">Receive Response</span><span class="sxs-lookup"><span data-stu-id="33068-139">Receive Response</span></span> |  <span data-ttu-id="33068-140">The initial HTTP response from a request.</span><span class="sxs-lookup"><span data-stu-id="33068-140">The initial HTTP response from a request.</span></span> |  
| <span data-ttu-id="33068-141">Send Request</span><span class="sxs-lookup"><span data-stu-id="33068-141">Send Request</span></span> |  <span data-ttu-id="33068-142">A network request has been sent.</span><span class="sxs-lookup"><span data-stu-id="33068-142">A network request has been sent.</span></span> |  

### <span data-ttu-id="33068-143">Loading event properties</span><span class="sxs-lookup"><span data-stu-id="33068-143">Loading event properties</span></span>  

| <span data-ttu-id="33068-144">Property</span><span class="sxs-lookup"><span data-stu-id="33068-144">Property</span></span> | <span data-ttu-id="33068-145">Description</span><span class="sxs-lookup"><span data-stu-id="33068-145">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="33068-146">Resource</span><span class="sxs-lookup"><span data-stu-id="33068-146">Resource</span></span> | <span data-ttu-id="33068-147">The URL of the requested resource.</span><span class="sxs-lookup"><span data-stu-id="33068-147">The URL of the requested resource.</span></span> |  
| <span data-ttu-id="33068-148">Preview</span><span class="sxs-lookup"><span data-stu-id="33068-148">Preview</span></span> | <span data-ttu-id="33068-149">Preview of the requested resource \(images only\).</span><span class="sxs-lookup"><span data-stu-id="33068-149">Preview of the requested resource \(images only\).</span></span> |  
| <span data-ttu-id="33068-150">Request Method</span><span class="sxs-lookup"><span data-stu-id="33068-150">Request Method</span></span> | <span data-ttu-id="33068-151">HTTP method used for the request \(`GET` or `POST`, for example\).</span><span class="sxs-lookup"><span data-stu-id="33068-151">HTTP method used for the request \(`GET` or `POST`, for example\).</span></span> |  
| <span data-ttu-id="33068-152">Status Code</span><span class="sxs-lookup"><span data-stu-id="33068-152">Status Code</span></span> | <span data-ttu-id="33068-153">HTTP response code.</span><span class="sxs-lookup"><span data-stu-id="33068-153">HTTP response code.</span></span> |  
| <span data-ttu-id="33068-154">MIME Type</span><span class="sxs-lookup"><span data-stu-id="33068-154">MIME Type</span></span> | <span data-ttu-id="33068-155">MIME type of the requested resource.</span><span class="sxs-lookup"><span data-stu-id="33068-155">MIME type of the requested resource.</span></span> |  
| <span data-ttu-id="33068-156">Encoded Data Length</span><span class="sxs-lookup"><span data-stu-id="33068-156">Encoded Data Length</span></span> | <span data-ttu-id="33068-157">Length of requested resource in bytes.</span><span class="sxs-lookup"><span data-stu-id="33068-157">Length of requested resource in bytes.</span></span> |  

## <span data-ttu-id="33068-158">Scripting events</span><span class="sxs-lookup"><span data-stu-id="33068-158">Scripting events</span></span>  

<span data-ttu-id="33068-159">This section lists events that belong to the Scripting category and their properties.</span><span class="sxs-lookup"><span data-stu-id="33068-159">This section lists events that belong to the Scripting category and their properties.</span></span>  

| <span data-ttu-id="33068-160">Event</span><span class="sxs-lookup"><span data-stu-id="33068-160">Event</span></span> | <span data-ttu-id="33068-161">Description</span><span class="sxs-lookup"><span data-stu-id="33068-161">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="33068-162">Animation Frame Fired</span><span class="sxs-lookup"><span data-stu-id="33068-162">Animation Frame Fired</span></span> | <span data-ttu-id="33068-163">A scheduled animation frame fired, and its callback handler invoked.</span><span class="sxs-lookup"><span data-stu-id="33068-163">A scheduled animation frame fired, and its callback handler invoked.</span></span> |  
| <span data-ttu-id="33068-164">Cancel Animation Frame</span><span class="sxs-lookup"><span data-stu-id="33068-164">Cancel Animation Frame</span></span> |  <span data-ttu-id="33068-165">A scheduled animation frame was canceled.</span><span class="sxs-lookup"><span data-stu-id="33068-165">A scheduled animation frame was canceled.</span></span> |  
| <span data-ttu-id="33068-166">GC Event</span><span class="sxs-lookup"><span data-stu-id="33068-166">GC Event</span></span> |  <span data-ttu-id="33068-167">Garbage collection occurred.</span><span class="sxs-lookup"><span data-stu-id="33068-167">Garbage collection occurred.</span></span> |  
| <span data-ttu-id="33068-168">DOMContentLoaded</span><span class="sxs-lookup"><span data-stu-id="33068-168">DOMContentLoaded</span></span> |  <span data-ttu-id="33068-169">The [DOMContentLoaded event][MDNWindowDOMContentLoadedEvent] was fired by the browser.</span><span class="sxs-lookup"><span data-stu-id="33068-169">The [DOMContentLoaded event][MDNWindowDOMContentLoadedEvent] was fired by the browser.</span></span>  <span data-ttu-id="33068-170">This event is fired when all of the page's DOM content has been loaded and parsed.</span><span class="sxs-lookup"><span data-stu-id="33068-170">This event is fired when all of the page's DOM content has been loaded and parsed.</span></span> |  
| <span data-ttu-id="33068-171">Evaluate Script</span><span class="sxs-lookup"><span data-stu-id="33068-171">Evaluate Script</span></span> | <span data-ttu-id="33068-172">A script was evaluated.</span><span class="sxs-lookup"><span data-stu-id="33068-172">A script was evaluated.</span></span> |  
| <span data-ttu-id="33068-173">Event</span><span class="sxs-lookup"><span data-stu-id="33068-173">Event</span></span> | <span data-ttu-id="33068-174">A JavaScript event \(for example, `mousedown`, or `key`\).</span><span class="sxs-lookup"><span data-stu-id="33068-174">A JavaScript event \(for example, `mousedown`, or `key`\).</span></span> |  
| <span data-ttu-id="33068-175">Function Call</span><span class="sxs-lookup"><span data-stu-id="33068-175">Function Call</span></span> | <span data-ttu-id="33068-176">A top-level JavaScript function call was made \(only appears when browser enters JavaScript engine\).</span><span class="sxs-lookup"><span data-stu-id="33068-176">A top-level JavaScript function call was made \(only appears when browser enters JavaScript engine\).</span></span> |  
| <span data-ttu-id="33068-177">Install Timer</span><span class="sxs-lookup"><span data-stu-id="33068-177">Install Timer</span></span> | <span data-ttu-id="33068-178">A timer was created with [setInterval()][MDNWindowOrWorkerGlobalScopeSetInterval] or [setTimeout()][MDNWindowOrWorkerGlobalScopeSetTimeout].</span><span class="sxs-lookup"><span data-stu-id="33068-178">A timer was created with [setInterval()][MDNWindowOrWorkerGlobalScopeSetInterval] or [setTimeout()][MDNWindowOrWorkerGlobalScopeSetTimeout].</span></span> |  
| <span data-ttu-id="33068-179">Request Animation Frame</span><span class="sxs-lookup"><span data-stu-id="33068-179">Request Animation Frame</span></span> | <span data-ttu-id="33068-180">A `requestAnimationFrame()` call scheduled a new frame.</span><span class="sxs-lookup"><span data-stu-id="33068-180">A `requestAnimationFrame()` call scheduled a new frame.</span></span> |  
| <span data-ttu-id="33068-181">Remove Timer</span><span class="sxs-lookup"><span data-stu-id="33068-181">Remove Timer</span></span> | <span data-ttu-id="33068-182">A previously created timer was cleared.</span><span class="sxs-lookup"><span data-stu-id="33068-182">A previously created timer was cleared.</span></span> |  
| <span data-ttu-id="33068-183">Time</span><span class="sxs-lookup"><span data-stu-id="33068-183">Time</span></span> |  <span data-ttu-id="33068-184">A script called [console.time()][ConsoleApiTime].</span><span class="sxs-lookup"><span data-stu-id="33068-184">A script called [console.time()][ConsoleApiTime].</span></span> |  
| <span data-ttu-id="33068-185">Time End</span><span class="sxs-lookup"><span data-stu-id="33068-185">Time End</span></span> | <span data-ttu-id="33068-186">A script called [console.timeEnd()][ConsoleApiTimeEnd].</span><span class="sxs-lookup"><span data-stu-id="33068-186">A script called [console.timeEnd()][ConsoleApiTimeEnd].</span></span> |  
| <span data-ttu-id="33068-187">Timer Fired</span><span class="sxs-lookup"><span data-stu-id="33068-187">Timer Fired</span></span> | <span data-ttu-id="33068-188">A timer fired that was scheduled with `setInterval()` or `setTimeout()`.</span><span class="sxs-lookup"><span data-stu-id="33068-188">A timer fired that was scheduled with `setInterval()` or `setTimeout()`.</span></span> |  
| <span data-ttu-id="33068-189">XHR Ready State Change</span><span class="sxs-lookup"><span data-stu-id="33068-189">XHR Ready State Change</span></span> | <span data-ttu-id="33068-190">The ready state of an XMLHTTPRequest changed.</span><span class="sxs-lookup"><span data-stu-id="33068-190">The ready state of an XMLHTTPRequest changed.</span></span> |  
| <span data-ttu-id="33068-191">XHR Load</span><span class="sxs-lookup"><span data-stu-id="33068-191">XHR Load</span></span> | <span data-ttu-id="33068-192">An `XMLHTTPRequest` finished loading.</span><span class="sxs-lookup"><span data-stu-id="33068-192">An `XMLHTTPRequest` finished loading.</span></span> |  

### <span data-ttu-id="33068-193">Scripting event properties</span><span class="sxs-lookup"><span data-stu-id="33068-193">Scripting event properties</span></span>  

| <span data-ttu-id="33068-194">Property</span><span class="sxs-lookup"><span data-stu-id="33068-194">Property</span></span> | <span data-ttu-id="33068-195">Description</span><span class="sxs-lookup"><span data-stu-id="33068-195">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="33068-196">Timer ID</span><span class="sxs-lookup"><span data-stu-id="33068-196">Timer ID</span></span> | <span data-ttu-id="33068-197">The timer ID.</span><span class="sxs-lookup"><span data-stu-id="33068-197">The timer ID.</span></span> |  
| <span data-ttu-id="33068-198">Timeout</span><span class="sxs-lookup"><span data-stu-id="33068-198">Timeout</span></span> | <span data-ttu-id="33068-199">The timeout specified by the timer.</span><span class="sxs-lookup"><span data-stu-id="33068-199">The timeout specified by the timer.</span></span> |  
| <span data-ttu-id="33068-200">Repeats</span><span class="sxs-lookup"><span data-stu-id="33068-200">Repeats</span></span> | <span data-ttu-id="33068-201">Boolean that specifies if the timer repeats.</span><span class="sxs-lookup"><span data-stu-id="33068-201">Boolean that specifies if the timer repeats.</span></span> |  
| <span data-ttu-id="33068-202">Function Call</span><span class="sxs-lookup"><span data-stu-id="33068-202">Function Call</span></span> | <span data-ttu-id="33068-203">A function that was invoked.</span><span class="sxs-lookup"><span data-stu-id="33068-203">A function that was invoked.</span></span> |  

## <span data-ttu-id="33068-204">Rendering events</span><span class="sxs-lookup"><span data-stu-id="33068-204">Rendering events</span></span>  

<span data-ttu-id="33068-205">This section lists events that belong to Rendering category and their properties.</span><span class="sxs-lookup"><span data-stu-id="33068-205">This section lists events that belong to Rendering category and their properties.</span></span>  

| <span data-ttu-id="33068-206">Event</span><span class="sxs-lookup"><span data-stu-id="33068-206">Event</span></span> | <span data-ttu-id="33068-207">Description</span><span class="sxs-lookup"><span data-stu-id="33068-207">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="33068-208">Invalidate layout</span><span class="sxs-lookup"><span data-stu-id="33068-208">Invalidate layout</span></span> | <span data-ttu-id="33068-209">The page layout was invalidated by a DOM change.</span><span class="sxs-lookup"><span data-stu-id="33068-209">The page layout was invalidated by a DOM change.</span></span> |  
| <span data-ttu-id="33068-210">Layout</span><span class="sxs-lookup"><span data-stu-id="33068-210">Layout</span></span> | <span data-ttu-id="33068-211">A page layout was completed.</span><span class="sxs-lookup"><span data-stu-id="33068-211">A page layout was completed.</span></span> |  
| <span data-ttu-id="33068-212">Recalculate style</span><span class="sxs-lookup"><span data-stu-id="33068-212">Recalculate style</span></span> | <span data-ttu-id="33068-213">Microsoft Edge recalculated element styles.</span><span class="sxs-lookup"><span data-stu-id="33068-213">Microsoft Edge recalculated element styles.</span></span> |  
| <span data-ttu-id="33068-214">Scroll</span><span class="sxs-lookup"><span data-stu-id="33068-214">Scroll</span></span> | <span data-ttu-id="33068-215">The content of nested view was scrolled.</span><span class="sxs-lookup"><span data-stu-id="33068-215">The content of nested view was scrolled.</span></span> |  

### <span data-ttu-id="33068-216">Rendering event properties</span><span class="sxs-lookup"><span data-stu-id="33068-216">Rendering event properties</span></span>  

| <span data-ttu-id="33068-217">Property</span><span class="sxs-lookup"><span data-stu-id="33068-217">Property</span></span> | <span data-ttu-id="33068-218">Description</span><span class="sxs-lookup"><span data-stu-id="33068-218">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="33068-219">Layout invalidated</span><span class="sxs-lookup"><span data-stu-id="33068-219">Layout invalidated</span></span> | <span data-ttu-id="33068-220">For Layout records, the stack trace of the code that caused the layout to be invalidated.</span><span class="sxs-lookup"><span data-stu-id="33068-220">For Layout records, the stack trace of the code that caused the layout to be invalidated.</span></span> |  
| <span data-ttu-id="33068-221">Nodes that need layout</span><span class="sxs-lookup"><span data-stu-id="33068-221">Nodes that need layout</span></span> | <span data-ttu-id="33068-222">For Layout records, the number of nodes that were marked as needing layout before the relayout started.</span><span class="sxs-lookup"><span data-stu-id="33068-222">For Layout records, the number of nodes that were marked as needing layout before the relayout started.</span></span>  <span data-ttu-id="33068-223">These are normally those nodes that were invalidated by developer code, plus a path upward to relayout root.</span><span class="sxs-lookup"><span data-stu-id="33068-223">These are normally those nodes that were invalidated by developer code, plus a path upward to relayout root.</span></span> |  
| <span data-ttu-id="33068-224">Layout tree size</span><span class="sxs-lookup"><span data-stu-id="33068-224">Layout tree size</span></span> | <span data-ttu-id="33068-225">For Layout records, the total number of nodes under the relayout root \(the node that Microsoft Edge starts the relayout\).</span><span class="sxs-lookup"><span data-stu-id="33068-225">For Layout records, the total number of nodes under the relayout root \(the node that Microsoft Edge starts the relayout\).</span></span> |  
| <span data-ttu-id="33068-226">Layout scope</span><span class="sxs-lookup"><span data-stu-id="33068-226">Layout scope</span></span> | <span data-ttu-id="33068-227">Possible values are `Partial` \(the re-layout boundary is a portion of the DOM\) or `Whole document`.</span><span class="sxs-lookup"><span data-stu-id="33068-227">Possible values are `Partial` \(the re-layout boundary is a portion of the DOM\) or `Whole document`.</span></span> |  
| <span data-ttu-id="33068-228">Elements affected</span><span class="sxs-lookup"><span data-stu-id="33068-228">Elements affected</span></span> | <span data-ttu-id="33068-229">For Recalculate style records, the number of elements affected by a style recalculation.</span><span class="sxs-lookup"><span data-stu-id="33068-229">For Recalculate style records, the number of elements affected by a style recalculation.</span></span> |  
| <span data-ttu-id="33068-230">Styles invalidated</span><span class="sxs-lookup"><span data-stu-id="33068-230">Styles invalidated</span></span> | <span data-ttu-id="33068-231">For Recalculate style records, provides the stack trace of the code that caused the style invalidation.</span><span class="sxs-lookup"><span data-stu-id="33068-231">For Recalculate style records, provides the stack trace of the code that caused the style invalidation.</span></span> |  

## <span data-ttu-id="33068-232">Painting events</span><span class="sxs-lookup"><span data-stu-id="33068-232">Painting events</span></span>  

<span data-ttu-id="33068-233">This section lists events that belong to Painting category and their properties.</span><span class="sxs-lookup"><span data-stu-id="33068-233">This section lists events that belong to Painting category and their properties.</span></span>  

| <span data-ttu-id="33068-234">Event</span><span class="sxs-lookup"><span data-stu-id="33068-234">Event</span></span> | <span data-ttu-id="33068-235">Description</span><span class="sxs-lookup"><span data-stu-id="33068-235">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="33068-236">Composite Layers</span><span class="sxs-lookup"><span data-stu-id="33068-236">Composite Layers</span></span> | <span data-ttu-id="33068-237">The composited image layers for the Microsoft Edge rendering engine.</span><span class="sxs-lookup"><span data-stu-id="33068-237">The composited image layers for the Microsoft Edge rendering engine.</span></span> |  
| <span data-ttu-id="33068-238">Image Decode</span><span class="sxs-lookup"><span data-stu-id="33068-238">Image Decode</span></span> | <span data-ttu-id="33068-239">An image resource was decoded.</span><span class="sxs-lookup"><span data-stu-id="33068-239">An image resource was decoded.</span></span> |  
| <span data-ttu-id="33068-240">Image Resize</span><span class="sxs-lookup"><span data-stu-id="33068-240">Image Resize</span></span> | <span data-ttu-id="33068-241">An image was resized from its native dimensions.</span><span class="sxs-lookup"><span data-stu-id="33068-241">An image was resized from its native dimensions.</span></span> |  
| <span data-ttu-id="33068-242">Paint</span><span class="sxs-lookup"><span data-stu-id="33068-242">Paint</span></span> | <span data-ttu-id="33068-243">Composited layers were painted to a region of the display.</span><span class="sxs-lookup"><span data-stu-id="33068-243">Composited layers were painted to a region of the display.</span></span>  <span data-ttu-id="33068-244">Hovering over a Paint record highlights the region of the display that was updated.</span><span class="sxs-lookup"><span data-stu-id="33068-244">Hovering over a Paint record highlights the region of the display that was updated.</span></span> |  

### <span data-ttu-id="33068-245">Painting event properties</span><span class="sxs-lookup"><span data-stu-id="33068-245">Painting event properties</span></span>  

| <span data-ttu-id="33068-246">Property</span><span class="sxs-lookup"><span data-stu-id="33068-246">Property</span></span> | <span data-ttu-id="33068-247">说明</span><span class="sxs-lookup"><span data-stu-id="33068-247">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="33068-248">Location</span><span class="sxs-lookup"><span data-stu-id="33068-248">Location</span></span> | <span data-ttu-id="33068-249">For Paint events, the x and y coordinates of the paint rectangle.</span><span class="sxs-lookup"><span data-stu-id="33068-249">For Paint events, the x and y coordinates of the paint rectangle.</span></span> |  
| <span data-ttu-id="33068-250">Dimensions</span><span class="sxs-lookup"><span data-stu-id="33068-250">Dimensions</span></span> | <span data-ttu-id="33068-251">For Paint events, the height and width of the painted region.</span><span class="sxs-lookup"><span data-stu-id="33068-251">For Paint events, the height and width of the painted region.</span></span> |  

 



<!-- image links -->  

<!-- links -->

[ConsoleApiTime]: /microsoft-edge/devtools-guide-chromium/console/api#time "time - Console API Reference"  
[ConsoleApiTimeEnd]: /microsoft-edge/devtools-guide-chromium/console/api#timeend "timeEnd - Console API Reference"  
<!--[EvaluatePerformanceTimelineTool]: timeline-tool "How to Use the Timeline Tool"  -->

[MDNWindowDOMContentLoadedEvent]: https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded "Window: DOMContentLoaded event | MDN"  
[MDNWindowOrWorkerGlobalScopeSetInterval]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setInterval "WindowOrWorkerGlobalScope.setInterval() | MDN"  
[MDNWindowOrWorkerGlobalScopeSetTimeout]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setTimeout "WindowOrWorkerGlobalScope.setTimeout() | MDN"  

> [!NOTE]
> <span data-ttu-id="33068-257">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="33068-257">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="33068-258">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Flavio Copes][FlavioCopes] \(Full Stack Developer\).</span><span class="sxs-lookup"><span data-stu-id="33068-258">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) and is authored by [Meggin Kearney][MegginKearney] \(Tech Writer\) and [Flavio Copes][FlavioCopes] \(Full Stack Developer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="33068-260">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="33068-260">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[FlavioCopes]: https://developers.google.com/web/resources/contributors/flaviocopes  
