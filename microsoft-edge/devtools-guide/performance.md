---
description: Use the Performance panel to analyze the responsivenes of your page during user interaction
title: DevTools - Performance
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, performance, profile, frame rate, fps, CPU utilization, JavaScript execution
ms.custom: seodec18
ms.openlocfilehash: aecf3cf49592dbf1f24231e76f14ddc2ca1228c3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563475"
---
# <span data-ttu-id="ff08e-104">Performance</span><span class="sxs-lookup"><span data-stu-id="ff08e-104">Performance</span></span>

<span data-ttu-id="ff08e-105">The **Performance** panel offers tools for profiling and analyzing the responsiveness of your UI during the course of user interaction.</span><span class="sxs-lookup"><span data-stu-id="ff08e-105">The **Performance** panel offers tools for profiling and analyzing the responsiveness of your UI during the course of user interaction.</span></span> <span data-ttu-id="ff08e-106">With it, you can:</span><span class="sxs-lookup"><span data-stu-id="ff08e-106">With it, you can:</span></span>

 - <span data-ttu-id="ff08e-107">[Measure execution times](#recording-a-profile) of the various components of your page</span><span class="sxs-lookup"><span data-stu-id="ff08e-107">[Measure execution times](#recording-a-profile) of the various components of your page</span></span> 
 - <span data-ttu-id="ff08e-108">[Drill down to where you're spending the most CPU cycles](#timeline-ruler) to run your page and the resulting visual effect for your users</span><span class="sxs-lookup"><span data-stu-id="ff08e-108">[Drill down to where you're spending the most CPU cycles](#timeline-ruler) to run your page and the resulting visual effect for your users</span></span>
 - <span data-ttu-id="ff08e-109">[Get a step-by-step breakdown of the processes](#timeline-details) consuming page execution time</span><span class="sxs-lookup"><span data-stu-id="ff08e-109">[Get a step-by-step breakdown of the processes](#timeline-details) consuming page execution time</span></span> 
 - <span data-ttu-id="ff08e-110">[Walk your JavaScript call stacks](#javascript-call-stacks) to identify costly operations, such as those requiring layout recalculations</span><span class="sxs-lookup"><span data-stu-id="ff08e-110">[Walk your JavaScript call stacks](#javascript-call-stacks) to identify costly operations, such as those requiring layout recalculations</span></span> 

![DevTools Performance panel](./media/performance.png)

## <span data-ttu-id="ff08e-112">Recording a profile</span><span class="sxs-lookup"><span data-stu-id="ff08e-112">Recording a profile</span></span>

<span data-ttu-id="ff08e-113">The first step to analyzing the performance of your page is to capture a profile as you perform a particular user scenario, such as the repro steps of a performance bug you're trying to fix, or a typical use case you want to optimize for a better user experience.</span><span class="sxs-lookup"><span data-stu-id="ff08e-113">The first step to analyzing the performance of your page is to capture a profile as you perform a particular user scenario, such as the repro steps of a performance bug you're trying to fix, or a typical use case you want to optimize for a better user experience.</span></span> 

### <span data-ttu-id="ff08e-114">Toolbar</span><span class="sxs-lookup"><span data-stu-id="ff08e-114">Toolbar</span></span>

<span data-ttu-id="ff08e-115">Use the **Start** / **Stop** buttons on the toolbar (or `Ctrl+E`) to initiate and conclude your performance trace.</span><span class="sxs-lookup"><span data-stu-id="ff08e-115">Use the **Start** / **Stop** buttons on the toolbar (or `Ctrl+E`) to initiate and conclude your performance trace.</span></span> <span data-ttu-id="ff08e-116">A green indicator will apear on the **Performance** tab to indicate a recording is in progress.</span><span class="sxs-lookup"><span data-stu-id="ff08e-116">A green indicator will apear on the **Performance** tab to indicate a recording is in progress.</span></span> 

![Performance panel toolbar](./media/performance_toolbar.png)

<span data-ttu-id="ff08e-118">A performance report will generate upon stopping the profile.</span><span class="sxs-lookup"><span data-stu-id="ff08e-118">A performance report will generate upon stopping the profile.</span></span> <span data-ttu-id="ff08e-119">You can choose to save it to disk (`Ctrl+S`) and reload (`Ctrl+O`) in  DevTools at a later time.</span><span class="sxs-lookup"><span data-stu-id="ff08e-119">You can choose to save it to disk (`Ctrl+S`) and reload (`Ctrl+O`) in  DevTools at a later time.</span></span>  <span data-ttu-id="ff08e-120">DevTools diagnostic sessions are saved with the *.diagsession* extension.</span><span class="sxs-lookup"><span data-stu-id="ff08e-120">DevTools diagnostic sessions are saved with the *.diagsession* extension.</span></span>

<span data-ttu-id="ff08e-121">Here are some things to keep in mind when recording a profile:</span><span class="sxs-lookup"><span data-stu-id="ff08e-121">Here are some things to keep in mind when recording a profile:</span></span>

- <span data-ttu-id="ff08e-122">Perform the fewest actions you need to capture the scenario you're trying to analyze.</span><span class="sxs-lookup"><span data-stu-id="ff08e-122">Perform the fewest actions you need to capture the scenario you're trying to analyze.</span></span> <span data-ttu-id="ff08e-123">Extraneous actions with the page will produce extra data and clutter your results.</span><span class="sxs-lookup"><span data-stu-id="ff08e-123">Extraneous actions with the page will produce extra data and clutter your results.</span></span>

- <span data-ttu-id="ff08e-124">The profiler will automatically mark major app lifecycle events in the report, such as page navigation, [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded), and page [load](https://developer.mozilla.org/docs/Web/Events/load).</span><span class="sxs-lookup"><span data-stu-id="ff08e-124">The profiler will automatically mark major app lifecycle events in the report, such as page navigation, [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded), and page [load](https://developer.mozilla.org/docs/Web/Events/load).</span></span> <span data-ttu-id="ff08e-125">You can add custom markers by calling the [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the console.</span><span class="sxs-lookup"><span data-stu-id="ff08e-125">You can add custom markers by calling the [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the console.</span></span> 

- <span data-ttu-id="ff08e-126">If initial page load times are important to your analysis, make sure to clear your browser cache (from the [Network](./network.md) panel) to ensure all page resources are loading from the network.</span><span class="sxs-lookup"><span data-stu-id="ff08e-126">If initial page load times are important to your analysis, make sure to clear your browser cache (from the [Network](./network.md) panel) to ensure all page resources are loading from the network.</span></span>

- <span data-ttu-id="ff08e-127">Sometimes it helps to record multiple sessions and/or sample the same scenario across different machines to better understand the performance issue in the wild.</span><span class="sxs-lookup"><span data-stu-id="ff08e-127">Sometimes it helps to record multiple sessions and/or sample the same scenario across different machines to better understand the performance issue in the wild.</span></span>

## <span data-ttu-id="ff08e-128">Timeline ruler</span><span class="sxs-lookup"><span data-stu-id="ff08e-128">Timeline ruler</span></span>

<span data-ttu-id="ff08e-129">The timeline works as a sliding ruler.</span><span class="sxs-lookup"><span data-stu-id="ff08e-129">The timeline works as a sliding ruler.</span></span> <span data-ttu-id="ff08e-130">Use it to limit the scope of the report to the particular timeframe (or span of events) of interest.</span><span class="sxs-lookup"><span data-stu-id="ff08e-130">Use it to limit the scope of the report to the particular timeframe (or span of events) of interest.</span></span> <span data-ttu-id="ff08e-131">Drag the black **slide controls** to limit the time range you wish to investigate and filter out extraneous profiling data from the [Timeline](#timeline-details) and [JavaScript call stacks](#javascript-call-stacks) reports in the lower *Details pane*.</span><span class="sxs-lookup"><span data-stu-id="ff08e-131">Drag the black **slide controls** to limit the time range you wish to investigate and filter out extraneous profiling data from the [Timeline](#timeline-details) and [JavaScript call stacks](#javascript-call-stacks) reports in the lower *Details pane*.</span></span> 

<span data-ttu-id="ff08e-132">You will see two types of markers on the ruler:</span><span class="sxs-lookup"><span data-stu-id="ff08e-132">You will see two types of markers on the ruler:</span></span>

 - <span data-ttu-id="ff08e-133">**App lifecycle marks** on the timeline (such as page navigation, [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded), and page [load](https://developer.mozilla.org/docs/Web/Events/load)) are automatically logged as you record a profile.</span><span class="sxs-lookup"><span data-stu-id="ff08e-133">**App lifecycle marks** on the timeline (such as page navigation, [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded), and page [load](https://developer.mozilla.org/docs/Web/Events/load)) are automatically logged as you record a profile.</span></span>

 - <span data-ttu-id="ff08e-134">**User marks** are custom markers you can choose to add  with calls to the [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the  DevTools [**Console**](./console.md).</span><span class="sxs-lookup"><span data-stu-id="ff08e-134">**User marks** are custom markers you can choose to add  with calls to the [Performance.mark()](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the  DevTools [**Console**](./console.md).</span></span> <span data-ttu-id="ff08e-135">You can group *start* and *end* marks together as a single, named measure with the [Performance.measure()](https://developer.mozilla.org/docs/Web/API/Performance/measure) method.</span><span class="sxs-lookup"><span data-stu-id="ff08e-135">You can group *start* and *end* marks together as a single, named measure with the [Performance.measure()](https://developer.mozilla.org/docs/Web/API/Performance/measure) method.</span></span> 

<span data-ttu-id="ff08e-136">Once you have selected a time range, you can further **Zoom in** from the toolbar, or **Reset zoom** and **Clear selection** to return to the full view of the performance trace (with no time range selected).</span><span class="sxs-lookup"><span data-stu-id="ff08e-136">Once you have selected a time range, you can further **Zoom in** from the toolbar, or **Reset zoom** and **Clear selection** to return to the full view of the performance trace (with no time range selected).</span></span> <span data-ttu-id="ff08e-137">These controls are also available from the right-click context menu.</span><span class="sxs-lookup"><span data-stu-id="ff08e-137">These controls are also available from the right-click context menu.</span></span>

![Performance panel timeline](./media/performance_timeline.png)

### <span data-ttu-id="ff08e-139">CPU utilization</span><span class="sxs-lookup"><span data-stu-id="ff08e-139">CPU utilization</span></span>

<span data-ttu-id="ff08e-140">The **CPU utilization %** timeline graph describes the processing resources consumed by the various browser subsystems required to run the page, broken out by category:</span><span class="sxs-lookup"><span data-stu-id="ff08e-140">The **CPU utilization %** timeline graph describes the processing resources consumed by the various browser subsystems required to run the page, broken out by category:</span></span>

#### <span data-ttu-id="ff08e-141">Loading</span><span class="sxs-lookup"><span data-stu-id="ff08e-141">Loading</span></span>
<span data-ttu-id="ff08e-142">Indicates time spent retrieving app resources and parsing HTML and CSS.</span><span class="sxs-lookup"><span data-stu-id="ff08e-142">Indicates time spent retrieving app resources and parsing HTML and CSS.</span></span> <span data-ttu-id="ff08e-143">This can include network requests.</span><span class="sxs-lookup"><span data-stu-id="ff08e-143">This can include network requests.</span></span> <span data-ttu-id="ff08e-144">The following associated events are logged in the [Timeline](#timeline-details):</span><span class="sxs-lookup"><span data-stu-id="ff08e-144">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="ff08e-145">Event</span><span class="sxs-lookup"><span data-stu-id="ff08e-145">Event</span></span> | <span data-ttu-id="ff08e-146">Description</span><span class="sxs-lookup"><span data-stu-id="ff08e-146">Description</span></span>
:------------ | :-------------
<span data-ttu-id="ff08e-147">CssParsing</span><span class="sxs-lookup"><span data-stu-id="ff08e-147">CssParsing</span></span>  | <span data-ttu-id="ff08e-148">New CSS content was encountered that needed to be parsed.</span><span class="sxs-lookup"><span data-stu-id="ff08e-148">New CSS content was encountered that needed to be parsed.</span></span>
<span data-ttu-id="ff08e-149">HtmlParsing</span><span class="sxs-lookup"><span data-stu-id="ff08e-149">HtmlParsing</span></span> | <span data-ttu-id="ff08e-150">New HTML content was encountered that needed to be parsed into nodes and inserted into the DOM.</span><span class="sxs-lookup"><span data-stu-id="ff08e-150">New HTML content was encountered that needed to be parsed into nodes and inserted into the DOM.</span></span>
<span data-ttu-id="ff08e-151">HttpRequest</span><span class="sxs-lookup"><span data-stu-id="ff08e-151">HttpRequest</span></span> | <span data-ttu-id="ff08e-152">A remote resource was encountered in the DOM or an XMLHttpRequest was created that required an HTTP request to be made.</span><span class="sxs-lookup"><span data-stu-id="ff08e-152">A remote resource was encountered in the DOM or an XMLHttpRequest was created that required an HTTP request to be made.</span></span>
<span data-ttu-id="ff08e-153">HtmlSpeculativeDownloading</span><span class="sxs-lookup"><span data-stu-id="ff08e-153">HtmlSpeculativeDownloading</span></span> | <span data-ttu-id="ff08e-154">The page's HTML content was being searched for required resources so that the HTTP requests for them could be scheduled as quickly as possible.</span><span class="sxs-lookup"><span data-stu-id="ff08e-154">The page's HTML content was being searched for required resources so that the HTTP requests for them could be scheduled as quickly as possible.</span></span>


#### <span data-ttu-id="ff08e-155">Scripting</span><span class="sxs-lookup"><span data-stu-id="ff08e-155">Scripting</span></span>
<span data-ttu-id="ff08e-156">Indicates time spent parsing and executing JavaScript.</span><span class="sxs-lookup"><span data-stu-id="ff08e-156">Indicates time spent parsing and executing JavaScript.</span></span> <span data-ttu-id="ff08e-157">This includes DOM events, timers, script evaluation, and animation frame callbacks.</span><span class="sxs-lookup"><span data-stu-id="ff08e-157">This includes DOM events, timers, script evaluation, and animation frame callbacks.</span></span> <span data-ttu-id="ff08e-158">The following associated events are logged in the [Timeline](#timeline-details):</span><span class="sxs-lookup"><span data-stu-id="ff08e-158">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="ff08e-159">Event</span><span class="sxs-lookup"><span data-stu-id="ff08e-159">Event</span></span> | <span data-ttu-id="ff08e-160">Description</span><span class="sxs-lookup"><span data-stu-id="ff08e-160">Description</span></span>
:------------ | :-------------
<span data-ttu-id="ff08e-161">DomEvent</span><span class="sxs-lookup"><span data-stu-id="ff08e-161">DomEvent</span></span> | <span data-ttu-id="ff08e-162">An event was fired on a DOM object.</span><span class="sxs-lookup"><span data-stu-id="ff08e-162">An event was fired on a DOM object.</span></span>
<span data-ttu-id="ff08e-163">EvaluatingScript</span><span class="sxs-lookup"><span data-stu-id="ff08e-163">EvaluatingScript</span></span> | <span data-ttu-id="ff08e-164">A new `<script>` element was encountered in the DOM and needed to be parsed and executed.</span><span class="sxs-lookup"><span data-stu-id="ff08e-164">A new `<script>` element was encountered in the DOM and needed to be parsed and executed.</span></span>
<span data-ttu-id="ff08e-165">EventHandler</span><span class="sxs-lookup"><span data-stu-id="ff08e-165">EventHandler</span></span> | <span data-ttu-id="ff08e-166">A registered event listener was triggered in response to a DOM event being fired.</span><span class="sxs-lookup"><span data-stu-id="ff08e-166">A registered event listener was triggered in response to a DOM event being fired.</span></span>
<span data-ttu-id="ff08e-167">Frame</span><span class="sxs-lookup"><span data-stu-id="ff08e-167">Frame</span></span> | <span data-ttu-id="ff08e-168">While a new frame was being prepared a registered callback was triggered so that it could contribute visual changes.</span><span class="sxs-lookup"><span data-stu-id="ff08e-168">While a new frame was being prepared a registered callback was triggered so that it could contribute visual changes.</span></span>
<span data-ttu-id="ff08e-169">Measure</span><span class="sxs-lookup"><span data-stu-id="ff08e-169">Measure</span></span> | <span data-ttu-id="ff08e-170">An app-specific scenario was measured using the `performance.measure()` method.</span><span class="sxs-lookup"><span data-stu-id="ff08e-170">An app-specific scenario was measured using the `performance.measure()` method.</span></span>
<span data-ttu-id="ff08e-171">MediaQueryListener</span><span class="sxs-lookup"><span data-stu-id="ff08e-171">MediaQueryListener</span></span> | <span data-ttu-id="ff08e-172">A registered media query was invalidated which resulted in the execution of its associated listener(s).</span><span class="sxs-lookup"><span data-stu-id="ff08e-172">A registered media query was invalidated which resulted in the execution of its associated listener(s).</span></span>
<span data-ttu-id="ff08e-173">MutationObserver</span><span class="sxs-lookup"><span data-stu-id="ff08e-173">MutationObserver</span></span> | <span data-ttu-id="ff08e-174">One or more observed DOM elements were modified which resulted in the execution of a MutationObserver's associated callback.</span><span class="sxs-lookup"><span data-stu-id="ff08e-174">One or more observed DOM elements were modified which resulted in the execution of a MutationObserver's associated callback.</span></span>
<span data-ttu-id="ff08e-175">TimerFired</span><span class="sxs-lookup"><span data-stu-id="ff08e-175">TimerFired</span></span> | <span data-ttu-id="ff08e-176">A scheduled timer elapsed which resulted in the execution of its associated callback.</span><span class="sxs-lookup"><span data-stu-id="ff08e-176">A scheduled timer elapsed which resulted in the execution of its associated callback.</span></span>
<span data-ttu-id="ff08e-177">WindowsRuntimeAsyncCallback</span><span class="sxs-lookup"><span data-stu-id="ff08e-177">WindowsRuntimeAsyncCallback</span></span> | <span data-ttu-id="ff08e-178">An async operation was completed by a Windows Runtime object which triggered a `Promise` callback.</span><span class="sxs-lookup"><span data-stu-id="ff08e-178">An async operation was completed by a Windows Runtime object which triggered a `Promise` callback.</span></span>
<span data-ttu-id="ff08e-179">WindowsRuntimeEvent</span><span class="sxs-lookup"><span data-stu-id="ff08e-179">WindowsRuntimeEvent</span></span> | <span data-ttu-id="ff08e-180">An event was fired on a Windows Runtime object which triggered a registered listener.</span><span class="sxs-lookup"><span data-stu-id="ff08e-180">An event was fired on a Windows Runtime object which triggered a registered listener.</span></span>

#### <span data-ttu-id="ff08e-181">GC</span><span class="sxs-lookup"><span data-stu-id="ff08e-181">GC</span></span>
<span data-ttu-id="ff08e-182">Indicates time spent collecting memory for objects that are no longer in use.</span><span class="sxs-lookup"><span data-stu-id="ff08e-182">Indicates time spent collecting memory for objects that are no longer in use.</span></span> <span data-ttu-id="ff08e-183">The following associated events are logged in the [Timeline](#timeline-details):</span><span class="sxs-lookup"><span data-stu-id="ff08e-183">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="ff08e-184">Event</span><span class="sxs-lookup"><span data-stu-id="ff08e-184">Event</span></span> | <span data-ttu-id="ff08e-185">Description</span><span class="sxs-lookup"><span data-stu-id="ff08e-185">Description</span></span>
:------------ | :-------------
<span data-ttu-id="ff08e-186">GarbageCollection</span><span class="sxs-lookup"><span data-stu-id="ff08e-186">GarbageCollection</span></span> | <span data-ttu-id="ff08e-187">The JavaScript runtime audited the app's current memory usage in order to determine which objects aren't being referenced anymore and could therefore be collected.</span><span class="sxs-lookup"><span data-stu-id="ff08e-187">The JavaScript runtime audited the app's current memory usage in order to determine which objects aren't being referenced anymore and could therefore be collected.</span></span>

#### <span data-ttu-id="ff08e-188">Styling</span><span class="sxs-lookup"><span data-stu-id="ff08e-188">Styling</span></span>
<span data-ttu-id="ff08e-189">Indicates time spent calculating element presentation and layout.</span><span class="sxs-lookup"><span data-stu-id="ff08e-189">Indicates time spent calculating element presentation and layout.</span></span> <span data-ttu-id="ff08e-190">The following associated events are logged in the [Timeline](#timeline-details):</span><span class="sxs-lookup"><span data-stu-id="ff08e-190">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="ff08e-191">Event</span><span class="sxs-lookup"><span data-stu-id="ff08e-191">Event</span></span> | <span data-ttu-id="ff08e-192">Description</span><span class="sxs-lookup"><span data-stu-id="ff08e-192">Description</span></span>
:------------ | :-------------
<span data-ttu-id="ff08e-193">AlignedBeat</span><span class="sxs-lookup"><span data-stu-id="ff08e-193">AlignedBeat</span></span> | <span data-ttu-id="ff08e-194">Pending visual changes that were made to the DOM were processed so that the app's display could be updated.</span><span class="sxs-lookup"><span data-stu-id="ff08e-194">Pending visual changes that were made to the DOM were processed so that the app's display could be updated.</span></span>
<span data-ttu-id="ff08e-195">CssCalculation</span><span class="sxs-lookup"><span data-stu-id="ff08e-195">CssCalculation</span></span> | <span data-ttu-id="ff08e-196">Changes were made to the DOM or new CSS content was added, requiring the style properties of all affected elements to be recalculated.</span><span class="sxs-lookup"><span data-stu-id="ff08e-196">Changes were made to the DOM or new CSS content was added, requiring the style properties of all affected elements to be recalculated.</span></span>
<span data-ttu-id="ff08e-197">Layout</span><span class="sxs-lookup"><span data-stu-id="ff08e-197">Layout</span></span> | <span data-ttu-id="ff08e-198">Changes were made to the DOM that required the size and/or position of all affected elements to be computed.</span><span class="sxs-lookup"><span data-stu-id="ff08e-198">Changes were made to the DOM that required the size and/or position of all affected elements to be computed.</span></span>

#### <span data-ttu-id="ff08e-199">Rendering</span><span class="sxs-lookup"><span data-stu-id="ff08e-199">Rendering</span></span>
<span data-ttu-id="ff08e-200">Indicates time spent in painting the screen.</span><span class="sxs-lookup"><span data-stu-id="ff08e-200">Indicates time spent in painting the screen.</span></span> <span data-ttu-id="ff08e-201">The following associated events are logged in the [Timeline](#timeline-details):</span><span class="sxs-lookup"><span data-stu-id="ff08e-201">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="ff08e-202">Event</span><span class="sxs-lookup"><span data-stu-id="ff08e-202">Event</span></span> | <span data-ttu-id="ff08e-203">Description</span><span class="sxs-lookup"><span data-stu-id="ff08e-203">Description</span></span>
:------------ | :-------------
<span data-ttu-id="ff08e-204">Paint</span><span class="sxs-lookup"><span data-stu-id="ff08e-204">Paint</span></span> | <span data-ttu-id="ff08e-205">Visual changes were made to the DOM that required all affected portions of the page to be redrawn.</span><span class="sxs-lookup"><span data-stu-id="ff08e-205">Visual changes were made to the DOM that required all affected portions of the page to be redrawn.</span></span>
<span data-ttu-id="ff08e-206">RenderLayer</span><span class="sxs-lookup"><span data-stu-id="ff08e-206">RenderLayer</span></span> | <span data-ttu-id="ff08e-207">Visual changes were made to an independently rendered fragment of the DOM (called a layer) which required its respective portion of the page to be redrawn.</span><span class="sxs-lookup"><span data-stu-id="ff08e-207">Visual changes were made to an independently rendered fragment of the DOM (called a layer) which required its respective portion of the page to be redrawn.</span></span>

#### <span data-ttu-id="ff08e-208">Image decoding</span><span class="sxs-lookup"><span data-stu-id="ff08e-208">Image decoding</span></span>
<span data-ttu-id="ff08e-209">Indicates time spent decompressing and decoding images.</span><span class="sxs-lookup"><span data-stu-id="ff08e-209">Indicates time spent decompressing and decoding images.</span></span> <span data-ttu-id="ff08e-210">The following associated events are logged in the [Timeline](#timeline-details):</span><span class="sxs-lookup"><span data-stu-id="ff08e-210">The following associated events are logged in the [Timeline](#timeline-details):</span></span>

<span data-ttu-id="ff08e-211">Event</span><span class="sxs-lookup"><span data-stu-id="ff08e-211">Event</span></span> | <span data-ttu-id="ff08e-212">Description</span><span class="sxs-lookup"><span data-stu-id="ff08e-212">Description</span></span>
:------------ | :-------------
<span data-ttu-id="ff08e-213">ImageDecoded</span><span class="sxs-lookup"><span data-stu-id="ff08e-213">ImageDecoded</span></span> | <span data-ttu-id="ff08e-214">An image was included into the DOM and needed be to decompressed from its original format into a bitmap.</span><span class="sxs-lookup"><span data-stu-id="ff08e-214">An image was included into the DOM and needed be to decompressed from its original format into a bitmap.</span></span>

### <span data-ttu-id="ff08e-215">Visual throughput</span><span class="sxs-lookup"><span data-stu-id="ff08e-215">Visual throughput</span></span>

<span data-ttu-id="ff08e-216">The **Visual throughput (FPS)** graph shows the estimated *frames per second* (FPS) during the course of the profiling scenario, where 60 FPS is the ideal display rate.</span><span class="sxs-lookup"><span data-stu-id="ff08e-216">The **Visual throughput (FPS)** graph shows the estimated *frames per second* (FPS) during the course of the profiling scenario, where 60 FPS is the ideal display rate.</span></span> <span data-ttu-id="ff08e-217">Dips in the frame rate indicate performance bottlenecks and a frame rate of zero means that frames are getting dropped entirely.</span><span class="sxs-lookup"><span data-stu-id="ff08e-217">Dips in the frame rate indicate performance bottlenecks and a frame rate of zero means that frames are getting dropped entirely.</span></span>

## <span data-ttu-id="ff08e-218">Timeline details</span><span class="sxs-lookup"><span data-stu-id="ff08e-218">Timeline details</span></span>

<span data-ttu-id="ff08e-219">Use the lowermost details pane to get the full breakdown of what happened on the page.</span><span class="sxs-lookup"><span data-stu-id="ff08e-219">Use the lowermost details pane to get the full breakdown of what happened on the page.</span></span> <span data-ttu-id="ff08e-220">The **Timeline details** tab provides a breakdown of events that occurred within the various browser subsystems.</span><span class="sxs-lookup"><span data-stu-id="ff08e-220">The **Timeline details** tab provides a breakdown of events that occurred within the various browser subsystems.</span></span>

![Performance timeline details pane](./media/performance_details_timeline.png)

1. **<span data-ttu-id="ff08e-222">Event list sort control</span><span class="sxs-lookup"><span data-stu-id="ff08e-222">Event list sort control</span></span>**

    <span data-ttu-id="ff08e-223">Use the **Sort by** dropdown control to toggle the [Event list](#event-list) order between *Start time* or *Duration (inclusive*).</span><span class="sxs-lookup"><span data-stu-id="ff08e-223">Use the **Sort by** dropdown control to toggle the [Event list](#event-list) order between *Start time* or *Duration (inclusive*).</span></span> <span data-ttu-id="ff08e-224">This also changes the view of the [Selected timeline details](#selected-timeline-details).</span><span class="sxs-lookup"><span data-stu-id="ff08e-224">This also changes the view of the [Selected timeline details](#selected-timeline-details).</span></span>

2. **<span data-ttu-id="ff08e-225">Group events by frame</span><span class="sxs-lookup"><span data-stu-id="ff08e-225">Group events by frame</span></span>**

    <span data-ttu-id="ff08e-226">Use the **Group top level events by frames** toggle to group top-level events (*HTML parsing, Layout, DOM event,* etc.) into their corresponding unit of work (or "frame") during periods of time where animations/visual updates were occurring.</span><span class="sxs-lookup"><span data-stu-id="ff08e-226">Use the **Group top level events by frames** toggle to group top-level events (*HTML parsing, Layout, DOM event,* etc.) into their corresponding unit of work (or "frame") during periods of time where animations/visual updates were occurring.</span></span> <span data-ttu-id="ff08e-227">The frames are treated like other events, so they can be sorted/filtered and provide an *Inclusive time* summary when clicked in the [Event list](#event-list).</span><span class="sxs-lookup"><span data-stu-id="ff08e-227">The frames are treated like other events, so they can be sorted/filtered and provide an *Inclusive time* summary when clicked in the [Event list](#event-list).</span></span>

3. **<span data-ttu-id="ff08e-228">Event list filter controls</span><span class="sxs-lookup"><span data-stu-id="ff08e-228">Event list filter controls</span></span>**

    <span data-ttu-id="ff08e-229">Use the **Filter events** menu to configure the types of events shown in the [timeline details](#timeline-details).</span><span class="sxs-lookup"><span data-stu-id="ff08e-229">Use the **Filter events** menu to configure the types of events shown in the [timeline details](#timeline-details).</span></span> 

    ![Control to filter performance events](./media/performance_filter_events.png) 

    <span data-ttu-id="ff08e-231">The following filters are available:</span><span class="sxs-lookup"><span data-stu-id="ff08e-231">The following filters are available:</span></span>

   - <span data-ttu-id="ff08e-232">**Image decoding**: Show events which occurred on a background thread (e.g. Image decoding, GC).</span><span class="sxs-lookup"><span data-stu-id="ff08e-232">**Image decoding**: Show events which occurred on a background thread (e.g. Image decoding, GC).</span></span> 
   - <span data-ttu-id="ff08e-233">**Network traffic**: Show HTTP requests which were network-bound.</span><span class="sxs-lookup"><span data-stu-id="ff08e-233">**Network traffic**: Show HTTP requests which were network-bound.</span></span>
   - <span data-ttu-id="ff08e-234">**UI activity**: Show events which occurred on the UI thread and/or render thread (e.g. DOM event handlers, Layout).</span><span class="sxs-lookup"><span data-stu-id="ff08e-234">**UI activity**: Show events which occurred on the UI thread and/or render thread (e.g. DOM event handlers, Layout).</span></span>
   - <span data-ttu-id="ff08e-235">**User measures**: Show custom events which indicate calls to the performance.measure() method.</span><span class="sxs-lookup"><span data-stu-id="ff08e-235">**User measures**: Show custom events which indicate calls to the performance.measure() method.</span></span>

     <span data-ttu-id="ff08e-236">You can further filter top-level events by their inclusive duration.</span><span class="sxs-lookup"><span data-stu-id="ff08e-236">You can further filter top-level events by their inclusive duration.</span></span>

### <span data-ttu-id="ff08e-237">Event list</span><span class="sxs-lookup"><span data-stu-id="ff08e-237">Event list</span></span>

<span data-ttu-id="ff08e-238">The *Event list* gives you a chronological list of [browser subsystem events](#cpu-utilization) that occurred during the selected span of time.</span><span class="sxs-lookup"><span data-stu-id="ff08e-238">The *Event list* gives you a chronological list of [browser subsystem events](#cpu-utilization) that occurred during the selected span of time.</span></span> 

<span data-ttu-id="ff08e-239">Click on any entry to populate the **Selected event details** chart for that item.</span><span class="sxs-lookup"><span data-stu-id="ff08e-239">Click on any entry to populate the **Selected event details** chart for that item.</span></span> <span data-ttu-id="ff08e-240">Entries with nested events / functions will show their **inclusive** (time spent executing the function *and* any other functions it called) and **exclusive** (time spent only within the body of the calling function itself) times displayed in the chart.</span><span class="sxs-lookup"><span data-stu-id="ff08e-240">Entries with nested events / functions will show their **inclusive** (time spent executing the function *and* any other functions it called) and **exclusive** (time spent only within the body of the calling function itself) times displayed in the chart.</span></span>

<span data-ttu-id="ff08e-241">Right-click on any entry to open the context menu to filter the timeline to only that event and view the source code responsible for the event in the [**Debugger**](./debugger.md) (or [**Elements**](./elements.md) panel, if applicable).</span><span class="sxs-lookup"><span data-stu-id="ff08e-241">Right-click on any entry to open the context menu to filter the timeline to only that event and view the source code responsible for the event in the [**Debugger**](./debugger.md) (or [**Elements**](./elements.md) panel, if applicable).</span></span>

### <span data-ttu-id="ff08e-242">Selected timeline details</span><span class="sxs-lookup"><span data-stu-id="ff08e-242">Selected timeline details</span></span>

<span data-ttu-id="ff08e-243">The *Selected timeline details* provides a detailed bar graph of inclusive/exclusive event times during the selected time span.</span><span class="sxs-lookup"><span data-stu-id="ff08e-243">The *Selected timeline details* provides a detailed bar graph of inclusive/exclusive event times during the selected time span.</span></span> <span data-ttu-id="ff08e-244">When you sort by *Duration (inclusive)* using the **Event list sort control**, the longest running events will visually stand out in this chart.</span><span class="sxs-lookup"><span data-stu-id="ff08e-244">When you sort by *Duration (inclusive)* using the **Event list sort control**, the longest running events will visually stand out in this chart.</span></span> 

### <span data-ttu-id="ff08e-245">Selected event details</span><span class="sxs-lookup"><span data-stu-id="ff08e-245">Selected event details</span></span>

<span data-ttu-id="ff08e-246">This report provides further information about the selected event, including *Start time*, the executing thread type (for example, *Download*, *UI*, *Render*), and other contextual details specific to the specific event type.</span><span class="sxs-lookup"><span data-stu-id="ff08e-246">This report provides further information about the selected event, including *Start time*, the executing thread type (for example, *Download*, *UI*, *Render*), and other contextual details specific to the specific event type.</span></span> <span data-ttu-id="ff08e-247">For example, *Event listener* types provide debugger links to the *Callback function* and *Scheduling call stack*.</span><span class="sxs-lookup"><span data-stu-id="ff08e-247">For example, *Event listener* types provide debugger links to the *Callback function* and *Scheduling call stack*.</span></span>

## <span data-ttu-id="ff08e-248">JavaScript call stacks</span><span class="sxs-lookup"><span data-stu-id="ff08e-248">JavaScript call stacks</span></span>

![Performance timings for JavaScript call stacks](./media/performance_details_javascript.png)

<span data-ttu-id="ff08e-250">The **JavaScript call stacks** tab provides CPU usage information and timings for the script functions that ran during the selected time range:</span><span class="sxs-lookup"><span data-stu-id="ff08e-250">The **JavaScript call stacks** tab provides CPU usage information and timings for the script functions that ran during the selected time range:</span></span>

 <span data-ttu-id="ff08e-251">Column</span><span class="sxs-lookup"><span data-stu-id="ff08e-251">Column</span></span> | <span data-ttu-id="ff08e-252">Description</span><span class="sxs-lookup"><span data-stu-id="ff08e-252">Description</span></span>
:------------ | :-------------
<span data-ttu-id="ff08e-253">Function name</span><span class="sxs-lookup"><span data-stu-id="ff08e-253">Function name</span></span> | <span data-ttu-id="ff08e-254">Name of browser or user-defined function.</span><span class="sxs-lookup"><span data-stu-id="ff08e-254">Name of browser or user-defined function.</span></span>
<span data-ttu-id="ff08e-255">Inclusive CPU (%)</span><span class="sxs-lookup"><span data-stu-id="ff08e-255">Inclusive CPU (%)</span></span> | <span data-ttu-id="ff08e-256">Percentage of selected CPU activity in this function and in functions called by this function.</span><span class="sxs-lookup"><span data-stu-id="ff08e-256">Percentage of selected CPU activity in this function and in functions called by this function.</span></span>
<span data-ttu-id="ff08e-257">Exclusive CPU (%)</span><span class="sxs-lookup"><span data-stu-id="ff08e-257">Exclusive CPU (%)</span></span> | <span data-ttu-id="ff08e-258">Percentage of selected CPU activity in this function, excluding activity in functions called by this function.</span><span class="sxs-lookup"><span data-stu-id="ff08e-258">Percentage of selected CPU activity in this function, excluding activity in functions called by this function.</span></span>
<span data-ttu-id="ff08e-259">Inclusive CPU (ms)</span><span class="sxs-lookup"><span data-stu-id="ff08e-259">Inclusive CPU (ms)</span></span> | <span data-ttu-id="ff08e-260">CPU time spent executing code in this function and in functions called by this function.</span><span class="sxs-lookup"><span data-stu-id="ff08e-260">CPU time spent executing code in this function and in functions called by this function.</span></span>
<span data-ttu-id="ff08e-261">Exclusive CPU (ms)</span><span class="sxs-lookup"><span data-stu-id="ff08e-261">Exclusive CPU (ms)</span></span> | <span data-ttu-id="ff08e-262">CPU time spent executing code in this function, excluding time in functions called by this function.</span><span class="sxs-lookup"><span data-stu-id="ff08e-262">CPU time spent executing code in this function, excluding time in functions called by this function.</span></span>
<span data-ttu-id="ff08e-263">URL</span><span class="sxs-lookup"><span data-stu-id="ff08e-263">URL</span></span> | <span data-ttu-id="ff08e-264">URL(s) where stack frame occurred.</span><span class="sxs-lookup"><span data-stu-id="ff08e-264">URL(s) where stack frame occurred.</span></span> <span data-ttu-id="ff08e-265">Function calls originating from the browser (standards-based web APIs) are labeled as *[DOM]*.</span><span class="sxs-lookup"><span data-stu-id="ff08e-265">Function calls originating from the browser (standards-based web APIs) are labeled as *[DOM]*.</span></span>

## <span data-ttu-id="ff08e-266">Shortcuts</span><span class="sxs-lookup"><span data-stu-id="ff08e-266">Shortcuts</span></span>

| <span data-ttu-id="ff08e-267">Action</span><span class="sxs-lookup"><span data-stu-id="ff08e-267">Action</span></span>                         | <span data-ttu-id="ff08e-268">Shortcut</span><span class="sxs-lookup"><span data-stu-id="ff08e-268">Shortcut</span></span>     |
|:-------------------------------|:-------------|
| <span data-ttu-id="ff08e-269">Start / Stop profiling session</span><span class="sxs-lookup"><span data-stu-id="ff08e-269">Start / Stop profiling session</span></span> | `Ctrl` + `E` |
| <span data-ttu-id="ff08e-270">Import profiling session</span><span class="sxs-lookup"><span data-stu-id="ff08e-270">Import profiling session</span></span>       | `Ctrl` + `O` |
| <span data-ttu-id="ff08e-271">Export profiling session</span><span class="sxs-lookup"><span data-stu-id="ff08e-271">Export profiling session</span></span>       | `Ctrl` + `S` |

## <span data-ttu-id="ff08e-272">Known Issues</span><span class="sxs-lookup"><span data-stu-id="ff08e-272">Known Issues</span></span>

### <span data-ttu-id="ff08e-273">An error occurred while starting the profiling session</span><span class="sxs-lookup"><span data-stu-id="ff08e-273">An error occurred while starting the profiling session</span></span>

<span data-ttu-id="ff08e-274">If you see this error message: **An error occurred while starting the profiling session** in the Performance tool, follow these steps for a workaround.</span><span class="sxs-lookup"><span data-stu-id="ff08e-274">If you see this error message: **An error occurred while starting the profiling session** in the Performance tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="ff08e-275">Press `Windows Key` + `R`.</span><span class="sxs-lookup"><span data-stu-id="ff08e-275">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="ff08e-276">In the Run dialog, enter **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="ff08e-276">In the Run dialog, enter **services.msc**.</span></span>
![known-issues-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="ff08e-278">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span><span class="sxs-lookup"><span data-stu-id="ff08e-278">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![known-issues-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="ff08e-280">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span><span class="sxs-lookup"><span data-stu-id="ff08e-280">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![known-issues-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="ff08e-282">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span><span class="sxs-lookup"><span data-stu-id="ff08e-282">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="ff08e-283">You should now be able to begin profiling.</span><span class="sxs-lookup"><span data-stu-id="ff08e-283">You should now be able to begin profiling.</span></span>
![known-issues-4](./media/known_issues_4-performance.PNG)

<span data-ttu-id="ff08e-285">Still running into problems?</span><span class="sxs-lookup"><span data-stu-id="ff08e-285">Still running into problems?</span></span> <span data-ttu-id="ff08e-286">Please send us your feedback using the **Send feedback** icon!</span><span class="sxs-lookup"><span data-stu-id="ff08e-286">Please send us your feedback using the **Send feedback** icon!</span></span> 

![known-issues-5](./media/known_issues_5.PNG)

### <span data-ttu-id="ff08e-288">An error occurred while stopping the profiling session.</span><span class="sxs-lookup"><span data-stu-id="ff08e-288">An error occurred while stopping the profiling session.</span></span>

<span data-ttu-id="ff08e-289">If you see this error message: **An error occurred while stopping the profiling session** in the Performance tool, follow these steps for a workaround.</span><span class="sxs-lookup"><span data-stu-id="ff08e-289">If you see this error message: **An error occurred while stopping the profiling session** in the Performance tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="ff08e-290">Press `Windows Key` + `R`.</span><span class="sxs-lookup"><span data-stu-id="ff08e-290">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="ff08e-291">In the Run dialog, enter **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="ff08e-291">In the Run dialog, enter **services.msc**.</span></span>
![known-issues-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="ff08e-293">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span><span class="sxs-lookup"><span data-stu-id="ff08e-293">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![known-issues-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="ff08e-295">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span><span class="sxs-lookup"><span data-stu-id="ff08e-295">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![known-issues-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="ff08e-297">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span><span class="sxs-lookup"><span data-stu-id="ff08e-297">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="ff08e-298">You should now be able to begin profiling.</span><span class="sxs-lookup"><span data-stu-id="ff08e-298">You should now be able to begin profiling.</span></span>
![known-issues-4](./media/known_issues_4-performance.PNG)

<span data-ttu-id="ff08e-300">Still running into problems?</span><span class="sxs-lookup"><span data-stu-id="ff08e-300">Still running into problems?</span></span> <span data-ttu-id="ff08e-301">Please send us your feedback using the **Send feedback** icon!</span><span class="sxs-lookup"><span data-stu-id="ff08e-301">Please send us your feedback using the **Send feedback** icon!</span></span> 

![known-issues-5](./media/known_issues_5.PNG)
