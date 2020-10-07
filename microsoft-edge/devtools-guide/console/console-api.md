---
description: Use the Console API to programmatically debug and profile your code
title: DevTools - Console - Console API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, console api
ms.custom: seodec18
ms.openlocfilehash: d722934c3694c3c23e367141158ad45f6d03b175
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564328"
---
# <span data-ttu-id="52f66-104">Console API</span><span class="sxs-lookup"><span data-stu-id="52f66-104">Console API</span></span>

<span data-ttu-id="52f66-105">The *Console API* provides command-line and programmatic access to the  DevTools Console through the global `console` object, allowing you to:</span><span class="sxs-lookup"><span data-stu-id="52f66-105">The *Console API* provides command-line and programmatic access to the  DevTools Console through the global `console` object, allowing you to:</span></span>

 - <span data-ttu-id="52f66-106">[Log custom messages](#logging-custom-messages) from you code</span><span class="sxs-lookup"><span data-stu-id="52f66-106">[Log custom messages](#logging-custom-messages) from you code</span></span>
 - <span data-ttu-id="52f66-107">[Inspect objects and elements](#inspecting-objects-and-elements) and log their information</span><span class="sxs-lookup"><span data-stu-id="52f66-107">[Inspect objects and elements](#inspecting-objects-and-elements) and log their information</span></span>
 - <span data-ttu-id="52f66-108">[Test and measure your code](#testing-and-measuring) by setting assertions, timers and counters</span><span class="sxs-lookup"><span data-stu-id="52f66-108">[Test and measure your code](#testing-and-measuring) by setting assertions, timers and counters</span></span>
 - <span data-ttu-id="52f66-109">[Take snapshots of the heap](#taking-heap-snapshots) to assess the memory consumption of your running code and identify memory leaks</span><span class="sxs-lookup"><span data-stu-id="52f66-109">[Take snapshots of the heap](#taking-heap-snapshots) to assess the memory consumption of your running code and identify memory leaks</span></span>
 - <span data-ttu-id="52f66-110">[Trace your callstacks](#tracing-callstacks) to understand where your code is being called from</span><span class="sxs-lookup"><span data-stu-id="52f66-110">[Trace your callstacks](#tracing-callstacks) to understand where your code is being called from</span></span> 
 - <span data-ttu-id="52f66-111">[Organize your log output](#organizing-log-output) to streamline your debugging</span><span class="sxs-lookup"><span data-stu-id="52f66-111">[Organize your log output](#organizing-log-output) to streamline your debugging</span></span>

<span data-ttu-id="52f66-112">The following are the commands and formatting parameters currently supported by Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="52f66-112">The following are the commands and formatting parameters currently supported by Microsoft Edge.</span></span> <span data-ttu-id="52f66-113">They work similarly on major browsers.</span><span class="sxs-lookup"><span data-stu-id="52f66-113">They work similarly on major browsers.</span></span>

## <span data-ttu-id="52f66-114">Logging custom messages</span><span class="sxs-lookup"><span data-stu-id="52f66-114">Logging custom messages</span></span>

<span data-ttu-id="52f66-115">Your code can send several types of custom messages to the console, including:</span><span class="sxs-lookup"><span data-stu-id="52f66-115">Your code can send several types of custom messages to the console, including:</span></span>

<span data-ttu-id="52f66-116">Message type</span><span class="sxs-lookup"><span data-stu-id="52f66-116">Message type</span></span>  | &nbsp;   |
:------------------- | :------ |
<span data-ttu-id="52f66-117">[**error()**](https://developer.mozilla.org/docs/Web/API/Console/error) and [**exception()**](https://developer.mozilla.org/docs/Web/API/Console/error)</span><span class="sxs-lookup"><span data-stu-id="52f66-117">[**error()**](https://developer.mozilla.org/docs/Web/API/Console/error) and [**exception()**](https://developer.mozilla.org/docs/Web/API/Console/error)</span></span>| <span data-ttu-id="52f66-118">Critical errors and failures</span><span class="sxs-lookup"><span data-stu-id="52f66-118">Critical errors and failures</span></span>
[**<span data-ttu-id="52f66-119">warn()</span><span class="sxs-lookup"><span data-stu-id="52f66-119">warn()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/warn) | <span data-ttu-id="52f66-120">Possible errors or unexpected behavior</span><span class="sxs-lookup"><span data-stu-id="52f66-120">Possible errors or unexpected behavior</span></span> 
[**<span data-ttu-id="52f66-121">info()</span><span class="sxs-lookup"><span data-stu-id="52f66-121">info()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/info) | <span data-ttu-id="52f66-122">Useful, but non-critical information</span><span class="sxs-lookup"><span data-stu-id="52f66-122">Useful, but non-critical information</span></span>
<span data-ttu-id="52f66-123">[**log()**](https://developer.mozilla.org/docs/Web/API/Console/log) and [**debug()**](https://developer.mozilla.org/docs/Web/API/Console/log)</span><span class="sxs-lookup"><span data-stu-id="52f66-123">[**log()**](https://developer.mozilla.org/docs/Web/API/Console/log) and [**debug()**](https://developer.mozilla.org/docs/Web/API/Console/log)</span></span> | <span data-ttu-id="52f66-124">General debugging (without generating a system alert icon in the console)</span><span class="sxs-lookup"><span data-stu-id="52f66-124">General debugging (without generating a system alert icon in the console)</span></span>

   
<span data-ttu-id="52f66-125">You can group and filter these along with the other messages generated from Microsoft Edge from the  Console panel.</span><span class="sxs-lookup"><span data-stu-id="52f66-125">You can group and filter these along with the other messages generated from Microsoft Edge from the  Console panel.</span></span> <span data-ttu-id="52f66-126">All custom message methods require a string (message) parameter and optional format substitution parameters.</span><span class="sxs-lookup"><span data-stu-id="52f66-126">All custom message methods require a string (message) parameter and optional format substitution parameters.</span></span> <span data-ttu-id="52f66-127">Microsoft Edge supports the following formatting options:</span><span class="sxs-lookup"><span data-stu-id="52f66-127">Microsoft Edge supports the following formatting options:</span></span>

<span data-ttu-id="52f66-128">Format parameter</span><span class="sxs-lookup"><span data-stu-id="52f66-128">Format parameter</span></span> | &nbsp;
:------------------- | :--- |
**<span data-ttu-id="52f66-129">%b</span><span class="sxs-lookup"><span data-stu-id="52f66-129">%b</span></span>** | <span data-ttu-id="52f66-130">Binary</span><span class="sxs-lookup"><span data-stu-id="52f66-130">Binary</span></span>
**<span data-ttu-id="52f66-131">%c</span><span class="sxs-lookup"><span data-stu-id="52f66-131">%c</span></span>** | <span data-ttu-id="52f66-132">Inline CSS style (see example below)</span><span class="sxs-lookup"><span data-stu-id="52f66-132">Inline CSS style (see example below)</span></span>
<span data-ttu-id="52f66-133">**%d**, **%i**</span><span class="sxs-lookup"><span data-stu-id="52f66-133">**%d**, **%i**</span></span> | <span data-ttu-id="52f66-134">Integer</span><span class="sxs-lookup"><span data-stu-id="52f66-134">Integer</span></span> 
**<span data-ttu-id="52f66-135">%f</span><span class="sxs-lookup"><span data-stu-id="52f66-135">%f</span></span>** | <span data-ttu-id="52f66-136">Float</span><span class="sxs-lookup"><span data-stu-id="52f66-136">Float</span></span>  
**<span data-ttu-id="52f66-137">%s</span><span class="sxs-lookup"><span data-stu-id="52f66-137">%s</span></span>** | <span data-ttu-id="52f66-138">String</span><span class="sxs-lookup"><span data-stu-id="52f66-138">String</span></span> 
**<span data-ttu-id="52f66-139">%x</span><span class="sxs-lookup"><span data-stu-id="52f66-139">%x</span></span>** | <span data-ttu-id="52f66-140">Hexadecimal</span><span class="sxs-lookup"><span data-stu-id="52f66-140">Hexadecimal</span></span> 
**<span data-ttu-id="52f66-141">%e</span><span class="sxs-lookup"><span data-stu-id="52f66-141">%e</span></span>** | <span data-ttu-id="52f66-142">Exponent</span><span class="sxs-lookup"><span data-stu-id="52f66-142">Exponent</span></span> 

<span data-ttu-id="52f66-143">For example, here's how you would include string and integer variables in your log message:</span><span class="sxs-lookup"><span data-stu-id="52f66-143">For example, here's how you would include string and integer variables in your log message:</span></span>

```javascript
var myText = 'pieces';
var myVal = 5;
console.log("The number of %s is %d.", myText, myVal);
```

>`The number of pieces is 5.`

<span data-ttu-id="52f66-144">And here's how you might add a green highlight effect to a log message with inline CSS (`%c`):</span><span class="sxs-lookup"><span data-stu-id="52f66-144">And here's how you might add a green highlight effect to a log message with inline CSS (`%c`):</span></span>

```javascript
console.log("%cHighlight this log message in green", "background-color: #10ff00; text-transform: uppercase;");
```

![Console log with inline styles](../media/console_api_css.png)

## <span data-ttu-id="52f66-146">Inspecting objects and elements</span><span class="sxs-lookup"><span data-stu-id="52f66-146">Inspecting objects and elements</span></span>

<span data-ttu-id="52f66-147">Inspectable objects appear in the console in a collapsed tree view with expandable nodes.</span><span class="sxs-lookup"><span data-stu-id="52f66-147">Inspectable objects appear in the console in a collapsed tree view with expandable nodes.</span></span> <span data-ttu-id="52f66-148">The console detects whether you are sending a DOM node (like a div) or a JavaScript object (like an event) and displays them as the detected type automatically.</span><span class="sxs-lookup"><span data-stu-id="52f66-148">The console detects whether you are sending a DOM node (like a div) or a JavaScript object (like an event) and displays them as the detected type automatically.</span></span>

<span data-ttu-id="52f66-149">You can also force a specific output:</span><span class="sxs-lookup"><span data-stu-id="52f66-149">You can also force a specific output:</span></span>

<span data-ttu-id="52f66-150">Command</span><span class="sxs-lookup"><span data-stu-id="52f66-150">Command</span></span> | &nbsp;
:------------------- | :--- |
[**<span data-ttu-id="52f66-151">dir()</span><span class="sxs-lookup"><span data-stu-id="52f66-151">dir()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/dir) | <span data-ttu-id="52f66-152">Displays as inspectable JavaScript object</span><span class="sxs-lookup"><span data-stu-id="52f66-152">Displays as inspectable JavaScript object</span></span>
[**<span data-ttu-id="52f66-153">dirxml()</span><span class="sxs-lookup"><span data-stu-id="52f66-153">dirxml()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/dirxml) | <span data-ttu-id="52f66-154">Displays as inspectable DOM node</span><span class="sxs-lookup"><span data-stu-id="52f66-154">Displays as inspectable DOM node</span></span>

<span data-ttu-id="52f66-155">For example, try opening the console and compare the following outputs for the `<div id='main'>` element on this page:</span><span class="sxs-lookup"><span data-stu-id="52f66-155">For example, try opening the console and compare the following outputs for the `<div id='main'>` element on this page:</span></span>

```javascript
console.dir(document.querySelector('#main'));
console.dirxml(document.querySelector('#main'));
```

![Comparison of 'dir' versus 'dirxml' output](../media/console_api_dir.png)

### <span data-ttu-id="52f66-157">Selecting an element in the **Elements** panel</span><span class="sxs-lookup"><span data-stu-id="52f66-157">Selecting an element in the **Elements** panel</span></span>

<span data-ttu-id="52f66-158">You can select an element within the HTML tree context of the page directly from the console for immediate layout and style debugging.</span><span class="sxs-lookup"><span data-stu-id="52f66-158">You can select an element within the HTML tree context of the page directly from the console for immediate layout and style debugging.</span></span>

<span data-ttu-id="52f66-159">Command</span><span class="sxs-lookup"><span data-stu-id="52f66-159">Command</span></span> | &nbsp;
:------------------- | :--- |
**<span data-ttu-id="52f66-160">select()</span><span class="sxs-lookup"><span data-stu-id="52f66-160">select()</span></span>** | <span data-ttu-id="52f66-161">Switches to the **Elements** panel and sets focus to the specified element.</span><span class="sxs-lookup"><span data-stu-id="52f66-161">Switches to the **Elements** panel and sets focus to the specified element.</span></span>

<span data-ttu-id="52f66-162">For example, if you open the console on this page and type:</span><span class="sxs-lookup"><span data-stu-id="52f66-162">For example, if you open the console on this page and type:</span></span>

```javascript
console.select(document.querySelector("body"));
```

<span data-ttu-id="52f66-163">The DevTools will switch to the **Elements** panel (if its not already the current) and set focus in the [*HTML tree view*](../elements.md#html-tree-view) to the specified element.</span><span class="sxs-lookup"><span data-stu-id="52f66-163">The DevTools will switch to the **Elements** panel (if its not already the current) and set focus in the [*HTML tree view*](../elements.md#html-tree-view) to the specified element.</span></span>

![Example of the 'select' method](../media/console_api_select.png)

## <span data-ttu-id="52f66-165">Testing and measuring</span><span class="sxs-lookup"><span data-stu-id="52f66-165">Testing and measuring</span></span>

### <span data-ttu-id="52f66-166">Testing your code</span><span class="sxs-lookup"><span data-stu-id="52f66-166">Testing your code</span></span>

<span data-ttu-id="52f66-167">Add Console API test assertions to your code for unit testing and debugging your code as it runs in the browser.</span><span class="sxs-lookup"><span data-stu-id="52f66-167">Add Console API test assertions to your code for unit testing and debugging your code as it runs in the browser.</span></span>

<span data-ttu-id="52f66-168">Command</span><span class="sxs-lookup"><span data-stu-id="52f66-168">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="52f66-169">assert()</span><span class="sxs-lookup"><span data-stu-id="52f66-169">assert()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/assert) | <span data-ttu-id="52f66-170">Logs a console error message if the provided expression evaluates to *false*.</span><span class="sxs-lookup"><span data-stu-id="52f66-170">Logs a console error message if the provided expression evaluates to *false*.</span></span>

<span data-ttu-id="52f66-171">In addition to the logical expression you supply as the testable assertion, you can add an optional message and formatting parameters as you would use with other [custom console messages](#logging-custom-messages).</span><span class="sxs-lookup"><span data-stu-id="52f66-171">In addition to the logical expression you supply as the testable assertion, you can add an optional message and formatting parameters as you would use with other [custom console messages](#logging-custom-messages).</span></span> <span data-ttu-id="52f66-172">For example:</span><span class="sxs-lookup"><span data-stu-id="52f66-172">For example:</span></span>

```javascript
var x = 26.8;
console.assert(x < 25, 'The value of x is %f (it is NOT less than %i)', x, 25);
```

![Example of the 'assert' method](../media/console_api_assert.png)

### <span data-ttu-id="52f66-174">Counting executions in your code</span><span class="sxs-lookup"><span data-stu-id="52f66-174">Counting executions in your code</span></span>

<span data-ttu-id="52f66-175">You can set counters in your code to keep track of how many times the surrounding code gets executed.</span><span class="sxs-lookup"><span data-stu-id="52f66-175">You can set counters in your code to keep track of how many times the surrounding code gets executed.</span></span> <span data-ttu-id="52f66-176">Setting counters can help ensure your code is running as expected and assist you in diagnosing performance bottlenecks.</span><span class="sxs-lookup"><span data-stu-id="52f66-176">Setting counters can help ensure your code is running as expected and assist you in diagnosing performance bottlenecks.</span></span>

<span data-ttu-id="52f66-177">Command</span><span class="sxs-lookup"><span data-stu-id="52f66-177">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="52f66-178">count()</span><span class="sxs-lookup"><span data-stu-id="52f66-178">count()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/count) | <span data-ttu-id="52f66-179">Increments and logs the number of times *count()* for the given label has been executed.</span><span class="sxs-lookup"><span data-stu-id="52f66-179">Increments and logs the number of times *count()* for the given label has been executed.</span></span>
[**<span data-ttu-id="52f66-180">countReset()</span><span class="sxs-lookup"><span data-stu-id="52f66-180">countReset()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/countReset) | <span data-ttu-id="52f66-181">Resets the count to zero for the given counter label.</span><span class="sxs-lookup"><span data-stu-id="52f66-181">Resets the count to zero for the given counter label.</span></span>

<span data-ttu-id="52f66-182">For example, executing the following lines in console:</span><span class="sxs-lookup"><span data-stu-id="52f66-182">For example, executing the following lines in console:</span></span>

```javascript
console.count('My Counter');
console.count('My Counter');
console.countReset('My Counter');
console.count('My Counter');
```

 <span data-ttu-id="52f66-183">.</span><span class="sxs-lookup"><span data-stu-id="52f66-183">.</span></span> <span data-ttu-id="52f66-184">.</span><span class="sxs-lookup"><span data-stu-id="52f66-184">.</span></span> <span data-ttu-id="52f66-185">.</span><span class="sxs-lookup"><span data-stu-id="52f66-185">.</span></span> <span data-ttu-id="52f66-186">will result in:</span><span class="sxs-lookup"><span data-stu-id="52f66-186">will result in:</span></span>
> <span data-ttu-id="52f66-187">My Counter: 1</span><span class="sxs-lookup"><span data-stu-id="52f66-187">My Counter: 1</span></span>

### <span data-ttu-id="52f66-188">Timing your code</span><span class="sxs-lookup"><span data-stu-id="52f66-188">Timing your code</span></span>

<span data-ttu-id="52f66-189">Instrument your code with labeled timers to measure how long it takes to complete a given operation.</span><span class="sxs-lookup"><span data-stu-id="52f66-189">Instrument your code with labeled timers to measure how long it takes to complete a given operation.</span></span>

<span data-ttu-id="52f66-190">Command</span><span class="sxs-lookup"><span data-stu-id="52f66-190">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="52f66-191">time()</span><span class="sxs-lookup"><span data-stu-id="52f66-191">time()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/time) | <span data-ttu-id="52f66-192">Starts a timer with the given label.</span><span class="sxs-lookup"><span data-stu-id="52f66-192">Starts a timer with the given label.</span></span>
[**<span data-ttu-id="52f66-193">timeEnd()</span><span class="sxs-lookup"><span data-stu-id="52f66-193">timeEnd()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/timeEnd) | <span data-ttu-id="52f66-194">Ends the timer with the given label and reports the time elapsed (in milliseconds).</span><span class="sxs-lookup"><span data-stu-id="52f66-194">Ends the timer with the given label and reports the time elapsed (in milliseconds).</span></span>
[**<span data-ttu-id="52f66-195">timeStamp()</span><span class="sxs-lookup"><span data-stu-id="52f66-195">timeStamp()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/timeStamp) | <span data-ttu-id="52f66-196">Reports the current system time (in milliseconds).</span><span class="sxs-lookup"><span data-stu-id="52f66-196">Reports the current system time (in milliseconds).</span></span>

<span data-ttu-id="52f66-197">For example, try executing the following lines in console:</span><span class="sxs-lookup"><span data-stu-id="52f66-197">For example, try executing the following lines in console:</span></span>

```javascript
console.time('My Timer');
console.timeEnd('My Timer');
```

### <span data-ttu-id="52f66-198">Taking heap snapshots</span><span class="sxs-lookup"><span data-stu-id="52f66-198">Taking heap snapshots</span></span>

<span data-ttu-id="52f66-199">Take snapshots of the heap to assess the memory consumption of your running code and identify memory leaks.</span><span class="sxs-lookup"><span data-stu-id="52f66-199">Take snapshots of the heap to assess the memory consumption of your running code and identify memory leaks.</span></span>

<span data-ttu-id="52f66-200">Command</span><span class="sxs-lookup"><span data-stu-id="52f66-200">Command</span></span> | &nbsp;
:------------ | :-------------
**<span data-ttu-id="52f66-201">takeHeapSnapshot()</span><span class="sxs-lookup"><span data-stu-id="52f66-201">takeHeapSnapshot()</span></span>** | <span data-ttu-id="52f66-202">Captures details about the current JavaScript heap and its allocated objects.</span><span class="sxs-lookup"><span data-stu-id="52f66-202">Captures details about the current JavaScript heap and its allocated objects.</span></span>

<span data-ttu-id="52f66-203">The  DevTools [memory profiler](../memory.md#toolbar) must be running in order to take heap snapshots.</span><span class="sxs-lookup"><span data-stu-id="52f66-203">The  DevTools [memory profiler](../memory.md#toolbar) must be running in order to take heap snapshots.</span></span> <span data-ttu-id="52f66-204">Each snapshot will appear as a tile in the [*Snapshot summary*](../memory.md#snapshot-summary) of the [**Memory**](../memory.md) panel for further inspection.</span><span class="sxs-lookup"><span data-stu-id="52f66-204">Each snapshot will appear as a tile in the [*Snapshot summary*](../memory.md#snapshot-summary) of the [**Memory**](../memory.md) panel for further inspection.</span></span>

## <span data-ttu-id="52f66-205">Tracing callstacks</span><span class="sxs-lookup"><span data-stu-id="52f66-205">Tracing callstacks</span></span>

<span data-ttu-id="52f66-206">Understanding where your code is being called from, what code is running, and how long that execution takes can be useful in analyzing slowness or unexpected behavior.</span><span class="sxs-lookup"><span data-stu-id="52f66-206">Understanding where your code is being called from, what code is running, and how long that execution takes can be useful in analyzing slowness or unexpected behavior.</span></span> <span data-ttu-id="52f66-207">A stack trace shows you the execution path your code took to reach it, from the trace request upward through the path.</span><span class="sxs-lookup"><span data-stu-id="52f66-207">A stack trace shows you the execution path your code took to reach it, from the trace request upward through the path.</span></span> 

<span data-ttu-id="52f66-208">Command</span><span class="sxs-lookup"><span data-stu-id="52f66-208">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="52f66-209">trace()</span><span class="sxs-lookup"><span data-stu-id="52f66-209">trace()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/trace) | <span data-ttu-id="52f66-210">Outputs a trace of the current script execution callstack.</span><span class="sxs-lookup"><span data-stu-id="52f66-210">Outputs a trace of the current script execution callstack.</span></span>

<span data-ttu-id="52f66-211">For example, running the following code in the console:</span><span class="sxs-lookup"><span data-stu-id="52f66-211">For example, running the following code in the console:</span></span>

```javascript
function a(){
  c();
}
function b(){
  c();
}
function c(){
  console.trace()
}
function d(){
  b();
}

a();
d();
```

<span data-ttu-id="52f66-212">.</span><span class="sxs-lookup"><span data-stu-id="52f66-212">.</span></span> <span data-ttu-id="52f66-213">.</span><span class="sxs-lookup"><span data-stu-id="52f66-213">.</span></span> <span data-ttu-id="52f66-214">.</span><span class="sxs-lookup"><span data-stu-id="52f66-214">.</span></span> <span data-ttu-id="52f66-215">will output the following stack traces:</span><span class="sxs-lookup"><span data-stu-id="52f66-215">will output the following stack traces:</span></span>
> <span data-ttu-id="52f66-216">console.trace() at c (eval code:8:3) at a (eval code:2:3) at eval code (eval code:14:1)</span><span class="sxs-lookup"><span data-stu-id="52f66-216">console.trace() at c (eval code:8:3) at a (eval code:2:3) at eval code (eval code:14:1)</span></span>
> 
> <span data-ttu-id="52f66-217">console.trace() at c (eval code:8:3) at b (eval code:5:3) at d (eval code:11:3) at eval code (eval code:15:1)</span><span class="sxs-lookup"><span data-stu-id="52f66-217">console.trace() at c (eval code:8:3) at b (eval code:5:3) at d (eval code:11:3) at eval code (eval code:15:1)</span></span>

## <span data-ttu-id="52f66-218">Organizing log output</span><span class="sxs-lookup"><span data-stu-id="52f66-218">Organizing log output</span></span>

<span data-ttu-id="52f66-219">To simply clear all previous console output, use *console.clear()* (or `CTRL + L`).</span><span class="sxs-lookup"><span data-stu-id="52f66-219">To simply clear all previous console output, use *console.clear()* (or `CTRL + L`).</span></span> <span data-ttu-id="52f66-220">This does not clear the backstack of your console command history (you can still traverse it with the up and down arrow keys).</span><span class="sxs-lookup"><span data-stu-id="52f66-220">This does not clear the backstack of your console command history (you can still traverse it with the up and down arrow keys).</span></span>

<span data-ttu-id="52f66-221">Command</span><span class="sxs-lookup"><span data-stu-id="52f66-221">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="52f66-222">clear()</span><span class="sxs-lookup"><span data-stu-id="52f66-222">clear()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/clear) | <span data-ttu-id="52f66-223">Clears all previous console output.</span><span class="sxs-lookup"><span data-stu-id="52f66-223">Clears all previous console output.</span></span>

<span data-ttu-id="52f66-224">If your code outputs a lot of console messages, you can visually organize them into nested blocks with the following commands:</span><span class="sxs-lookup"><span data-stu-id="52f66-224">If your code outputs a lot of console messages, you can visually organize them into nested blocks with the following commands:</span></span>

 <span data-ttu-id="52f66-225">Command</span><span class="sxs-lookup"><span data-stu-id="52f66-225">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="52f66-226">group()</span><span class="sxs-lookup"><span data-stu-id="52f66-226">group()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/group) | <span data-ttu-id="52f66-227">Starts a new level of nesting for console output with the specified (optional) label.</span><span class="sxs-lookup"><span data-stu-id="52f66-227">Starts a new level of nesting for console output with the specified (optional) label.</span></span>
[**<span data-ttu-id="52f66-228">groupCollapsed()</span><span class="sxs-lookup"><span data-stu-id="52f66-228">groupCollapsed()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/groupCollapsed) | <span data-ttu-id="52f66-229">Starts a new level of nesting for console output with the specified (optional) label, however the grouping control is collapsed by default and must be expanded (by clicking on the arrow control) to display the child output.</span><span class="sxs-lookup"><span data-stu-id="52f66-229">Starts a new level of nesting for console output with the specified (optional) label, however the grouping control is collapsed by default and must be expanded (by clicking on the arrow control) to display the child output.</span></span>
[**<span data-ttu-id="52f66-230">groupEnd()</span><span class="sxs-lookup"><span data-stu-id="52f66-230">groupEnd()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/groupEnd) | <span data-ttu-id="52f66-231">Ends the nesting group for the specified label.</span><span class="sxs-lookup"><span data-stu-id="52f66-231">Ends the nesting group for the specified label.</span></span>

<span data-ttu-id="52f66-232">For example, try entering the following commands in the console:</span><span class="sxs-lookup"><span data-stu-id="52f66-232">For example, try entering the following commands in the console:</span></span>

```javascript
console.groupCollapsed('Group 1');
console.log('In Group 1');
console.groupCollapsed('Group 1.1');
console.log('In Group 1.1');
console.groupEnd('Group 1.1');
console.groupEnd('Group 1');
console.log('No longer in a group');
```

<span data-ttu-id="52f66-233">.</span><span class="sxs-lookup"><span data-stu-id="52f66-233">.</span></span> <span data-ttu-id="52f66-234">.</span><span class="sxs-lookup"><span data-stu-id="52f66-234">.</span></span> <span data-ttu-id="52f66-235">.</span><span class="sxs-lookup"><span data-stu-id="52f66-235">.</span></span> <span data-ttu-id="52f66-236">and then expand the *Group 1* and *Group 1.1* controls to see how the log comments are nested:</span><span class="sxs-lookup"><span data-stu-id="52f66-236">and then expand the *Group 1* and *Group 1.1* controls to see how the log comments are nested:</span></span>

![Grouping messages in the console](../media/console_api_group.png)

<span data-ttu-id="52f66-238">Sometimes its easier to visualize a JavaScript object or array in tabular form, rather than a flat list.</span><span class="sxs-lookup"><span data-stu-id="52f66-238">Sometimes its easier to visualize a JavaScript object or array in tabular form, rather than a flat list.</span></span> <span data-ttu-id="52f66-239">For that, you can use the *console.table()* command:</span><span class="sxs-lookup"><span data-stu-id="52f66-239">For that, you can use the *console.table()* command:</span></span>

<span data-ttu-id="52f66-240">Command</span><span class="sxs-lookup"><span data-stu-id="52f66-240">Command</span></span> | &nbsp;
:------------ | :-------------
[**<span data-ttu-id="52f66-241">table()</span><span class="sxs-lookup"><span data-stu-id="52f66-241">table()</span></span>**](https://developer.mozilla.org/docs/Web/API/Console/table) | <span data-ttu-id="52f66-242">Outputs the supplied array or object to the console in tabular form.</span><span class="sxs-lookup"><span data-stu-id="52f66-242">Outputs the supplied array or object to the console in tabular form.</span></span>

<span data-ttu-id="52f66-243">For example, the following object array:</span><span class="sxs-lookup"><span data-stu-id="52f66-243">For example, the following object array:</span></span>

```javascript
var orders = [{'Size':'XL', 'Quantity':1},{'Size':'M', 'Quantity':3}, {'Size':'L', 'Quantity':2}];
console.table(orders);
```

<span data-ttu-id="52f66-244">.</span><span class="sxs-lookup"><span data-stu-id="52f66-244">.</span></span> <span data-ttu-id="52f66-245">.</span><span class="sxs-lookup"><span data-stu-id="52f66-245">.</span></span> <span data-ttu-id="52f66-246">.</span><span class="sxs-lookup"><span data-stu-id="52f66-246">.</span></span> <span data-ttu-id="52f66-247">will render as this table in the console:</span><span class="sxs-lookup"><span data-stu-id="52f66-247">will render as this table in the console:</span></span>

![Display an object array as a table in the console](../media/console_api_table.png)
