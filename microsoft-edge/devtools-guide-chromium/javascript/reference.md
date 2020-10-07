---
description: Discover new debugging workflows in this comprehensive reference of Microsoft Edge DevTools debugging features.
title: JavaScript Debugging Reference
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: f11dfb52e97dcec20d1e6c4f3adeee7010857a33
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993420"
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

# <span data-ttu-id="cf910-104">JavaScript febugging reference</span><span class="sxs-lookup"><span data-stu-id="cf910-104">JavaScript febugging reference</span></span>  

<span data-ttu-id="cf910-105">Discover new debugging workflows with the following comprehensive reference of Microsoft Edge DevTools debugging features.</span><span class="sxs-lookup"><span data-stu-id="cf910-105">Discover new debugging workflows with the following comprehensive reference of Microsoft Edge DevTools debugging features.</span></span>  

<span data-ttu-id="cf910-106">See [Get Started With Debugging JavaScript In Microsoft Edge DevTools][DevToolsJavascriptGetStarted] to learn the basics of debugging.</span><span class="sxs-lookup"><span data-stu-id="cf910-106">See [Get Started With Debugging JavaScript In Microsoft Edge DevTools][DevToolsJavascriptGetStarted] to learn the basics of debugging.</span></span>  

## <span data-ttu-id="cf910-107">Pause code with breakpoints</span><span class="sxs-lookup"><span data-stu-id="cf910-107">Pause code with breakpoints</span></span>  

<span data-ttu-id="cf910-108">Set a breakpoint so that you are able to pause your code in the middle of the runtime.</span><span class="sxs-lookup"><span data-stu-id="cf910-108">Set a breakpoint so that you are able to pause your code in the middle of the runtime.</span></span>  

<span data-ttu-id="cf910-109">See [Pause Your Code With Breakpoints][DevToolsJavascriptBreakpoints] to learn how to set breakpoints.</span><span class="sxs-lookup"><span data-stu-id="cf910-109">See [Pause Your Code With Breakpoints][DevToolsJavascriptBreakpoints] to learn how to set breakpoints.</span></span>  

## <span data-ttu-id="cf910-110">Step through code</span><span class="sxs-lookup"><span data-stu-id="cf910-110">Step through code</span></span>  

<span data-ttu-id="cf910-111">Once your code is paused, step through it, one line at a time, investigating control flow and property values along the way.</span><span class="sxs-lookup"><span data-stu-id="cf910-111">Once your code is paused, step through it, one line at a time, investigating control flow and property values along the way.</span></span>  

### <span data-ttu-id="cf910-112">Step over line of code</span><span class="sxs-lookup"><span data-stu-id="cf910-112">Step over line of code</span></span>  

<span data-ttu-id="cf910-113">When paused on a line of code containing a function that is not relevant to the problem you are debugging, click the **Step over** \(![Step over][ImageStepOverIcon]\) button to run the function without stepping into it.</span><span class="sxs-lookup"><span data-stu-id="cf910-113">When paused on a line of code containing a function that is not relevant to the problem you are debugging, click the **Step over** \(![Step over][ImageStepOverIcon]\) button to run the function without stepping into it.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png" alt-text="Select Step over" lightbox="../media/javascript-source-page-debugger-step-over-next-function-call.msft.png":::
   <span data-ttu-id="cf910-115">Select **Step over**</span><span class="sxs-lookup"><span data-stu-id="cf910-115">Select **Step over**</span></span>  
:::image-end:::  

<span data-ttu-id="cf910-116">For example, suppose you are debugging the following code snippet.</span><span class="sxs-lookup"><span data-stu-id="cf910-116">For example, suppose you are debugging the following code snippet.</span></span>  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name); // D
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name; // C
}
```  

<span data-ttu-id="cf910-117">You are paused on `A`.</span><span class="sxs-lookup"><span data-stu-id="cf910-117">You are paused on `A`.</span></span>  <span data-ttu-id="cf910-118">By pressing **Step over**, DevTools runs all the code in the function that you are stepping over, which is `B` and `C`.</span><span class="sxs-lookup"><span data-stu-id="cf910-118">By pressing **Step over**, DevTools runs all the code in the function that you are stepping over, which is `B` and `C`.</span></span>  <span data-ttu-id="cf910-119">DevTools then pauses on `D`.</span><span class="sxs-lookup"><span data-stu-id="cf910-119">DevTools then pauses on `D`.</span></span>  

### <span data-ttu-id="cf910-120">Step into line of code</span><span class="sxs-lookup"><span data-stu-id="cf910-120">Step into line of code</span></span>  

<span data-ttu-id="cf910-121">When paused on a line of code containing a function call that is related to the problem you are debugging, click the **Step into** \(![Step into][ImageStepIntoIcon]\) button to investigate that function further.</span><span class="sxs-lookup"><span data-stu-id="cf910-121">When paused on a line of code containing a function call that is related to the problem you are debugging, click the **Step into** \(![Step into][ImageStepIntoIcon]\) button to investigate that function further.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png" alt-text="Select Step over" lightbox="../media/javascript-source-page-debugger-step-into-next-function-call.msft.png":::
   <span data-ttu-id="cf910-123">Select **Step into**</span><span class="sxs-lookup"><span data-stu-id="cf910-123">Select **Step into**</span></span>  
:::image-end:::  

<span data-ttu-id="cf910-124">For example, suppose you are debugging the following code snippet.</span><span class="sxs-lookup"><span data-stu-id="cf910-124">For example, suppose you are debugging the following code snippet.</span></span>  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName(); // A
    updateName(name);
}
function getName() {
    var name = app.first + ' ' + app.last; // B
    return name;
}
```  

<span data-ttu-id="cf910-125">You are paused on `A`.</span><span class="sxs-lookup"><span data-stu-id="cf910-125">You are paused on `A`.</span></span>  <span data-ttu-id="cf910-126">By pressing **Step into**, DevTools runs this line of code, then pauses on `B`.</span><span class="sxs-lookup"><span data-stu-id="cf910-126">By pressing **Step into**, DevTools runs this line of code, then pauses on `B`.</span></span>  

### <span data-ttu-id="cf910-127">Step out of line of code</span><span class="sxs-lookup"><span data-stu-id="cf910-127">Step out of line of code</span></span>  

<span data-ttu-id="cf910-128">When paused inside of a function that is not related to the problem you are debugging, click the **Step out** \(![Step out][ImageStepOutIcon]\) button to run the rest of the code of the function.</span><span class="sxs-lookup"><span data-stu-id="cf910-128">When paused inside of a function that is not related to the problem you are debugging, click the **Step out** \(![Step out][ImageStepOutIcon]\) button to run the rest of the code of the function.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png" alt-text="Select Step over" lightbox="../media/javascript-source-page-debugger-step-out-of-current-function.msft.png":::
   <span data-ttu-id="cf910-130">Select **Step out**</span><span class="sxs-lookup"><span data-stu-id="cf910-130">Select **Step out**</span></span>  
:::image-end:::  

<span data-ttu-id="cf910-131">For example, suppose you are debugging the following code snippet.</span><span class="sxs-lookup"><span data-stu-id="cf910-131">For example, suppose you are debugging the following code snippet.</span></span>  

```javascript
function updateHeader() {
    var day = new Date().getDay();
    var name = getName();
    updateName(name); // C
}
function getName() {
    var name = app.first + ' ' + app.last; // A
    return name; // B
}
```  

<span data-ttu-id="cf910-132">You are paused on `A`.</span><span class="sxs-lookup"><span data-stu-id="cf910-132">You are paused on `A`.</span></span>  <span data-ttu-id="cf910-133">By pressing **Step out**, DevTools runs the rest of the code in `getName()`, which is just `B` in this example, and then pauses on `C`.</span><span class="sxs-lookup"><span data-stu-id="cf910-133">By pressing **Step out**, DevTools runs the rest of the code in `getName()`, which is just `B` in this example, and then pauses on `C`.</span></span>  

### <span data-ttu-id="cf910-134">Run all code up to a specific line</span><span class="sxs-lookup"><span data-stu-id="cf910-134">Run all code up to a specific line</span></span>  

<span data-ttu-id="cf910-135">When debugging a long function, there may be a lot of code that is not related to the problem you are debugging.</span><span class="sxs-lookup"><span data-stu-id="cf910-135">When debugging a long function, there may be a lot of code that is not related to the problem you are debugging.</span></span>  

<span data-ttu-id="cf910-136">You may choose to step through all the lines, but that is tedious.</span><span class="sxs-lookup"><span data-stu-id="cf910-136">You may choose to step through all the lines, but that is tedious.</span></span>  <span data-ttu-id="cf910-137">You may choose to set a line-of-code breakpoint on the line in which you are interested and then click the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button, but there is a faster way.</span><span class="sxs-lookup"><span data-stu-id="cf910-137">You may choose to set a line-of-code breakpoint on the line in which you are interested and then click the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button, but there is a faster way.</span></span>  

<span data-ttu-id="cf910-138">Right-click the line of code in which you are interested, and select **Continue to here**.</span><span class="sxs-lookup"><span data-stu-id="cf910-138">Right-click the line of code in which you are interested, and select **Continue to here**.</span></span>  <span data-ttu-id="cf910-139">DevTools runs all of the code up to that point, and then pauses on that line.</span><span class="sxs-lookup"><span data-stu-id="cf910-139">DevTools runs all of the code up to that point, and then pauses on that line.</span></span>  

:::image type="complex" source="../media/javascript-source-page-continue-to-here.msft.png" alt-text="Select Step over" lightbox="../media/javascript-source-page-continue-to-here.msft.png":::
   <span data-ttu-id="cf910-141">Select **Continue to here**</span><span class="sxs-lookup"><span data-stu-id="cf910-141">Select **Continue to here**</span></span>  
:::image-end:::  

### <span data-ttu-id="cf910-142">Restart the top function of the call stack</span><span class="sxs-lookup"><span data-stu-id="cf910-142">Restart the top function of the call stack</span></span>  

<span data-ttu-id="cf910-143">While paused on a line of code, right-click anywhere in the **Call Stack** pane and select **Restart Frame** to pause on the first line of the top function in your call stack.</span><span class="sxs-lookup"><span data-stu-id="cf910-143">While paused on a line of code, right-click anywhere in the **Call Stack** pane and select **Restart Frame** to pause on the first line of the top function in your call stack.</span></span>  <span data-ttu-id="cf910-144">The top function is the last function that was run.</span><span class="sxs-lookup"><span data-stu-id="cf910-144">The top function is the last function that was run.</span></span>  

<span data-ttu-id="cf910-145">The following code snippet is an example for you to step-through.</span><span class="sxs-lookup"><span data-stu-id="cf910-145">The following code snippet is an example for you to step-through.</span></span>  

```javascript
function factorial(n) {
    var product = 0; // B
    for (var i = 1; i <= n; i++) {
      product += i;
    }
    return product; // A
}
```  

<span data-ttu-id="cf910-146">You are paused on `A`.</span><span class="sxs-lookup"><span data-stu-id="cf910-146">You are paused on `A`.</span></span>  <span data-ttu-id="cf910-147">After clicking **Restart Frame**, you should be paused on `B`, without ever setting a breakpoint or pressing **Resume script execution**.</span><span class="sxs-lookup"><span data-stu-id="cf910-147">After clicking **Restart Frame**, you should be paused on `B`, without ever setting a breakpoint or pressing **Resume script execution**.</span></span>  

:::image type="complex" source="../media/javascript-source-page-debugger-restart-frame.msft.png" alt-text="Select Step over" lightbox="../media/javascript-source-page-debugger-restart-frame.msft.png":::
   <span data-ttu-id="cf910-149">Select **Restart Frame**</span><span class="sxs-lookup"><span data-stu-id="cf910-149">Select **Restart Frame**</span></span>  
:::image-end:::  

### <span data-ttu-id="cf910-150">Resume script runtime</span><span class="sxs-lookup"><span data-stu-id="cf910-150">Resume script runtime</span></span>  

<span data-ttu-id="cf910-151">To continue the runtime after a pause of your script, click the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button.</span><span class="sxs-lookup"><span data-stu-id="cf910-151">To continue the runtime after a pause of your script, click the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button.</span></span>  <span data-ttu-id="cf910-152">DevTools runs the script up until the next breakpoint, if any.</span><span class="sxs-lookup"><span data-stu-id="cf910-152">DevTools runs the script up until the next breakpoint, if any.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png" alt-text="Select Step over" lightbox="../media/javascript-sources-get-started-js-resume-script-runtime.msft.png":::
   <span data-ttu-id="cf910-154">Select **Resume script execution**</span><span class="sxs-lookup"><span data-stu-id="cf910-154">Select **Resume script execution**</span></span>  
:::image-end:::  

#### <span data-ttu-id="cf910-155">Force script runtime</span><span class="sxs-lookup"><span data-stu-id="cf910-155">Force script runtime</span></span>  

<span data-ttu-id="cf910-156">To ignore all breakpoints and force your script to resume running, click and hold the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button and then select the **Force script execution** \(![Force script execution][ImageForceScriptExecutionIcon]\) button.</span><span class="sxs-lookup"><span data-stu-id="cf910-156">To ignore all breakpoints and force your script to resume running, click and hold the **Resume Script Execution** \(![Resume Script Execution][ImageResumeScriptExecutionIcon]\) button and then select the **Force script execution** \(![Force script execution][ImageForceScriptExecutionIcon]\) button.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-force-script-runtime.msft.png" alt-text="Select Step over" lightbox="../media/javascript-sources-get-started-js-force-script-runtime.msft.png":::
   <span data-ttu-id="cf910-158">Select **Force script execution**</span><span class="sxs-lookup"><span data-stu-id="cf910-158">Select **Force script execution**</span></span>  
:::image-end:::  

### <span data-ttu-id="cf910-159">Change thread context</span><span class="sxs-lookup"><span data-stu-id="cf910-159">Change thread context</span></span>  

<span data-ttu-id="cf910-160">When working with web workers or service workers, click on a context listed in the **Threads** pane to switch to that context.</span><span class="sxs-lookup"><span data-stu-id="cf910-160">When working with web workers or service workers, click on a context listed in the **Threads** pane to switch to that context.</span></span>  <span data-ttu-id="cf910-161">The blue arrow icon represents which context is currently selected.</span><span class="sxs-lookup"><span data-stu-id="cf910-161">The blue arrow icon represents which context is currently selected.</span></span>  

:::image type="complex" source="../media/javascript-sources-main-min-js-threads.msft.png" alt-text="Select Step over" lightbox="../media/javascript-sources-main-min-js-threads.msft.png":::
   <span data-ttu-id="cf910-163">The **Threads** pane</span><span class="sxs-lookup"><span data-stu-id="cf910-163">The **Threads** pane</span></span>  
:::image-end:::  

<span data-ttu-id="cf910-164">For example, suppose that you are paused on a breakpoint in both your main script and your service worker script.</span><span class="sxs-lookup"><span data-stu-id="cf910-164">For example, suppose that you are paused on a breakpoint in both your main script and your service worker script.</span></span>  <span data-ttu-id="cf910-165">You want to view the local and global properties for the service worker context, but the **Sources** panel is showing the main script context.</span><span class="sxs-lookup"><span data-stu-id="cf910-165">You want to view the local and global properties for the service worker context, but the **Sources** panel is showing the main script context.</span></span>  <span data-ttu-id="cf910-166">By clicking on the service worker entry in the **Threads** pane, you should be able to switch to that context.</span><span class="sxs-lookup"><span data-stu-id="cf910-166">By clicking on the service worker entry in the **Threads** pane, you should be able to switch to that context.</span></span>  

## <span data-ttu-id="cf910-167">View and edit local, closure, and global properties</span><span class="sxs-lookup"><span data-stu-id="cf910-167">View and edit local, closure, and global properties</span></span>  

<span data-ttu-id="cf910-168">While paused on a line of code, use the **Scope** pane to view and edit the values of properties and variables in the local, closure, and global scopes.</span><span class="sxs-lookup"><span data-stu-id="cf910-168">While paused on a line of code, use the **Scope** pane to view and edit the values of properties and variables in the local, closure, and global scopes.</span></span>  

*   <span data-ttu-id="cf910-169">Double-click a property value to change it.</span><span class="sxs-lookup"><span data-stu-id="cf910-169">Double-click a property value to change it.</span></span>  
*   <span data-ttu-id="cf910-170">Non-enumerable properties are greyed out.</span><span class="sxs-lookup"><span data-stu-id="cf910-170">Non-enumerable properties are greyed out.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-scope.msft.png" alt-text="Select Step over" lightbox="../media/javascript-sources-get-started-js-scope.msft.png":::
   <span data-ttu-id="cf910-172">The **Scope** pane</span><span class="sxs-lookup"><span data-stu-id="cf910-172">The **Scope** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="cf910-173">View the current call stack</span><span class="sxs-lookup"><span data-stu-id="cf910-173">View the current call stack</span></span>  

<span data-ttu-id="cf910-174">While paused on a line of code, use the **Call Stack** pane to view the call stack that got you to this point.</span><span class="sxs-lookup"><span data-stu-id="cf910-174">While paused on a line of code, use the **Call Stack** pane to view the call stack that got you to this point.</span></span>  

<!--If you are working with async code, check the **Async** checkbox to enable async call stacks.  -->  

<span data-ttu-id="cf910-175">Click on an entry to jump to the line of code where that function was called.</span><span class="sxs-lookup"><span data-stu-id="cf910-175">Click on an entry to jump to the line of code where that function was called.</span></span>  <span data-ttu-id="cf910-176">The blue arrow icon represents which function DevTools is currently highlighting.</span><span class="sxs-lookup"><span data-stu-id="cf910-176">The blue arrow icon represents which function DevTools is currently highlighting.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png" alt-text="Select Step over" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty.msft.png":::
   <span data-ttu-id="cf910-178">The **Call Stack** pane</span><span class="sxs-lookup"><span data-stu-id="cf910-178">The **Call Stack** pane</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="cf910-179">When not paused on a line of code, the **Call Stack** pane is empty.</span><span class="sxs-lookup"><span data-stu-id="cf910-179">When not paused on a line of code, the **Call Stack** pane is empty.</span></span>  

### <span data-ttu-id="cf910-180">Copy stack trace</span><span class="sxs-lookup"><span data-stu-id="cf910-180">Copy stack trace</span></span>  

<!--
This should be moved to an "Export debug data" H2 section when there is enough content for that, but there is not right now, so it is here.
-->

<span data-ttu-id="cf910-181">Right-click anywhere in the **Call Stack** pane and select **Copy stack trace** to copy the current call stack to the clipboard.</span><span class="sxs-lookup"><span data-stu-id="cf910-181">Right-click anywhere in the **Call Stack** pane and select **Copy stack trace** to copy the current call stack to the clipboard.</span></span>  

:::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png" alt-text="Select Step over" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-copy-stack-trace.msft.png":::
   <span data-ttu-id="cf910-183">Select **Copy Stack Trace**</span><span class="sxs-lookup"><span data-stu-id="cf910-183">Select **Copy Stack Trace**</span></span>  
:::image-end:::  

<span data-ttu-id="cf910-184">The following code snippet is an example of the output.</span><span class="sxs-lookup"><span data-stu-id="cf910-184">The following code snippet is an example of the output.</span></span>  

```javascript
getNumber1 (get-started.js:35)
inputsAreEmpty (get-started.js:22)
onClick (get-started.js:15)
```  

## <span data-ttu-id="cf910-185">Ignore a script or pattern of scripts</span><span class="sxs-lookup"><span data-stu-id="cf910-185">Ignore a script or pattern of scripts</span></span>  

<span data-ttu-id="cf910-186">Mark a script as Library code when you want to ignore that script while debugging.</span><span class="sxs-lookup"><span data-stu-id="cf910-186">Mark a script as Library code when you want to ignore that script while debugging.</span></span>  <span data-ttu-id="cf910-187">When marked as Library code, a script is obscured in the **Call Stack** pane, and you never step into the functions of the script when you step through your code.</span><span class="sxs-lookup"><span data-stu-id="cf910-187">When marked as Library code, a script is obscured in the **Call Stack** pane, and you never step into the functions of the script when you step through your code.</span></span>  

<span data-ttu-id="cf910-188">The following code snippet is an example for you to step-through.</span><span class="sxs-lookup"><span data-stu-id="cf910-188">The following code snippet is an example for you to step-through.</span></span>  

```javascript
function animate() {
    prepare();
    lib.doFancyStuff(); // A
    render();
}
```  

`A` <span data-ttu-id="cf910-189">is a third-party library that you trust.</span><span class="sxs-lookup"><span data-stu-id="cf910-189">is a third-party library that you trust.</span></span>  <span data-ttu-id="cf910-190">If you are confident that the problem you are debugging is not related to the third-party library, then it makes sense to mark the script as **Library code**.</span><span class="sxs-lookup"><span data-stu-id="cf910-190">If you are confident that the problem you are debugging is not related to the third-party library, then it makes sense to mark the script as **Library code**.</span></span>  

### <span data-ttu-id="cf910-191">Mark a script as Library code from the Editor pane</span><span class="sxs-lookup"><span data-stu-id="cf910-191">Mark a script as Library code from the Editor pane</span></span>  

<span data-ttu-id="cf910-192">Complete the following actions to mark a script as **Library code** from the **Editor** pane.</span><span class="sxs-lookup"><span data-stu-id="cf910-192">Complete the following actions to mark a script as **Library code** from the **Editor** pane.</span></span>  

1.  <span data-ttu-id="cf910-193">Open the file.</span><span class="sxs-lookup"><span data-stu-id="cf910-193">Open the file.</span></span>  
1.  <span data-ttu-id="cf910-194">Right-click anywhere.</span><span class="sxs-lookup"><span data-stu-id="cf910-194">Right-click anywhere.</span></span>  
1.  <span data-ttu-id="cf910-195">Select **Mark as Library code**.</span><span class="sxs-lookup"><span data-stu-id="cf910-195">Select **Mark as Library code**.</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png" alt-text="Select Step over" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-editor-mark-as-library-code.msft.png":::
       <span data-ttu-id="cf910-197">Mark a script as **Library code** from the **Editor** pane</span><span class="sxs-lookup"><span data-stu-id="cf910-197">Mark a script as **Library code** from the **Editor** pane</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="cf910-198">Mark a script as Library code from the Call Stack pane</span><span class="sxs-lookup"><span data-stu-id="cf910-198">Mark a script as Library code from the Call Stack pane</span></span>  

<span data-ttu-id="cf910-199">Compelte the folliwng actions to mark a script as **Library code** from the **Call Stack** pane.</span><span class="sxs-lookup"><span data-stu-id="cf910-199">Compelte the folliwng actions to mark a script as **Library code** from the **Call Stack** pane.</span></span>  

1.  <span data-ttu-id="cf910-200">Right-click on a function from the script.</span><span class="sxs-lookup"><span data-stu-id="cf910-200">Right-click on a function from the script.</span></span>  
1.  <span data-ttu-id="cf910-201">Select **Mark as Library code**.</span><span class="sxs-lookup"><span data-stu-id="cf910-201">Select **Mark as Library code**.</span></span>  
    
    :::image type="complex" source="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png" alt-text="Select Step over" lightbox="../media/javascript-glitch-debug-js-sources-get-started-inputs-are-empty-call-stack-mark-as-library-code.msft.png":::
       <span data-ttu-id="cf910-203">Mark a script as **Library code** from the **Call Stack** pane</span><span class="sxs-lookup"><span data-stu-id="cf910-203">Mark a script as **Library code** from the **Call Stack** pane</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="cf910-204">Mark a script as Library code from Settings</span><span class="sxs-lookup"><span data-stu-id="cf910-204">Mark a script as Library code from Settings</span></span>  

<span data-ttu-id="cf910-205">Complete the following actions to mark a single script or pattern of scripts from **Settings**.</span><span class="sxs-lookup"><span data-stu-id="cf910-205">Complete the following actions to mark a single script or pattern of scripts from **Settings**.</span></span>  

1.  <span data-ttu-id="cf910-206">Open [Settings][DevToolsCustomize].</span><span class="sxs-lookup"><span data-stu-id="cf910-206">Open [Settings][DevToolsCustomize].</span></span>  
1.  <span data-ttu-id="cf910-207">Go to the **Library code** tab.</span><span class="sxs-lookup"><span data-stu-id="cf910-207">Go to the **Library code** tab.</span></span>  
1.  <span data-ttu-id="cf910-208">Click **Add pattern**.</span><span class="sxs-lookup"><span data-stu-id="cf910-208">Click **Add pattern**.</span></span>  
1.  <span data-ttu-id="cf910-209">Enter the script name or a regex pattern of script names to mark as **Library code**.</span><span class="sxs-lookup"><span data-stu-id="cf910-209">Enter the script name or a regex pattern of script names to mark as **Library code**.</span></span>  
1.  <span data-ttu-id="cf910-210">Click **Add**.</span><span class="sxs-lookup"><span data-stu-id="cf910-210">Click **Add**.</span></span>  
    
    :::image type="complex" source="../media/javascript-framework-library-code.msft.png" alt-text="Select Step over" lightbox="../media/javascript-framework-library-code.msft.png":::
       <span data-ttu-id="cf910-212">Mark a script as **Library code** from **Settings**</span><span class="sxs-lookup"><span data-stu-id="cf910-212">Mark a script as **Library code** from **Settings**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="cf910-213">Run snippets of debug code from any page</span><span class="sxs-lookup"><span data-stu-id="cf910-213">Run snippets of debug code from any page</span></span>   

<span data-ttu-id="cf910-214">If you find yourself running the same debug code in the Console over and over, consider Snippets.</span><span class="sxs-lookup"><span data-stu-id="cf910-214">If you find yourself running the same debug code in the Console over and over, consider Snippets.</span></span>  <span data-ttu-id="cf910-215">Snippets are runtime scripts that you author, store, and run within DevTools.</span><span class="sxs-lookup"><span data-stu-id="cf910-215">Snippets are runtime scripts that you author, store, and run within DevTools.</span></span>  

<span data-ttu-id="cf910-216">See [Run Snippets of Code From Any Page][DevToolsJavascriptSnippets] to learn more.</span><span class="sxs-lookup"><span data-stu-id="cf910-216">See [Run Snippets of Code From Any Page][DevToolsJavascriptSnippets] to learn more.</span></span>  

## <span data-ttu-id="cf910-217">Watch the values of custom JavaScript expressions</span><span class="sxs-lookup"><span data-stu-id="cf910-217">Watch the values of custom JavaScript expressions</span></span>  

<span data-ttu-id="cf910-218">Use the **Watch** pane to watch the values of custom expressions.</span><span class="sxs-lookup"><span data-stu-id="cf910-218">Use the **Watch** pane to watch the values of custom expressions.</span></span>  <span data-ttu-id="cf910-219">You may watch any valid JavaScript expression.</span><span class="sxs-lookup"><span data-stu-id="cf910-219">You may watch any valid JavaScript expression.</span></span>  

:::image type="complex" source="../media/javascript-sources-get-started-js-watch.msft.png" alt-text="Select Step over" lightbox="../media/javascript-sources-get-started-js-watch.msft.png":::
   <span data-ttu-id="cf910-221">The **Watch** pane</span><span class="sxs-lookup"><span data-stu-id="cf910-221">The **Watch** pane</span></span>  
:::image-end:::  

*   <span data-ttu-id="cf910-222">Click the **Add Expression** \(![Add Expression][ImageAddExpressionIcon]\) button to create a new watch expression.</span><span class="sxs-lookup"><span data-stu-id="cf910-222">Click the **Add Expression** \(![Add Expression][ImageAddExpressionIcon]\) button to create a new watch expression.</span></span>  
*   <span data-ttu-id="cf910-223">Click the **Refresh** \(![Refresh][ImageRefreshIcon]\) button to refresh the values of all existing expressions.</span><span class="sxs-lookup"><span data-stu-id="cf910-223">Click the **Refresh** \(![Refresh][ImageRefreshIcon]\) button to refresh the values of all existing expressions.</span></span>  <span data-ttu-id="cf910-224">Values automatically refresh while stepping through code.</span><span class="sxs-lookup"><span data-stu-id="cf910-224">Values automatically refresh while stepping through code.</span></span>  
*   <span data-ttu-id="cf910-225">Hover over an expression and click the **Delete Expression** \(![Delete Expression][ImageDeleteExpressionIcon]\) button to delete it.</span><span class="sxs-lookup"><span data-stu-id="cf910-225">Hover over an expression and click the **Delete Expression** \(![Delete Expression][ImageDeleteExpressionIcon]\) button to delete it.</span></span>  

## <span data-ttu-id="cf910-226">Make a minified file readable</span><span class="sxs-lookup"><span data-stu-id="cf910-226">Make a minified file readable</span></span>  

<span data-ttu-id="cf910-227">Click the **Format** \(![Format][ImageFormatIcon]\) button to make a minified file human-readable.</span><span class="sxs-lookup"><span data-stu-id="cf910-227">Click the **Format** \(![Format][ImageFormatIcon]\) button to make a minified file human-readable.</span></span>  

:::image type="complex" source="../media/javascript-sources-html-non-minified.msft.png" alt-text="Select Step over" lightbox="../media/javascript-sources-html-non-minified.msft.png":::
   <span data-ttu-id="cf910-229">The **Format** button</span><span class="sxs-lookup"><span data-stu-id="cf910-229">The **Format** button</span></span>  
:::image-end:::  

## <span data-ttu-id="cf910-230">Edit a script</span><span class="sxs-lookup"><span data-stu-id="cf910-230">Edit a script</span></span>   

<span data-ttu-id="cf910-231">When fixing a bug, you often want to test out some changes to your JavaScript code.</span><span class="sxs-lookup"><span data-stu-id="cf910-231">When fixing a bug, you often want to test out some changes to your JavaScript code.</span></span>  <span data-ttu-id="cf910-232">You do not need to make the changes in an external editor or IDE and then reload the page.</span><span class="sxs-lookup"><span data-stu-id="cf910-232">You do not need to make the changes in an external editor or IDE and then reload the page.</span></span>  <span data-ttu-id="cf910-233">You may edit your script in DevTools.</span><span class="sxs-lookup"><span data-stu-id="cf910-233">You may edit your script in DevTools.</span></span>  

<span data-ttu-id="cf910-234">Complete the following actions to edit a script.</span><span class="sxs-lookup"><span data-stu-id="cf910-234">Complete the following actions to edit a script.</span></span>  

1.  <span data-ttu-id="cf910-235">Open the file in the **Editor** pane of the **Sources** panel.</span><span class="sxs-lookup"><span data-stu-id="cf910-235">Open the file in the **Editor** pane of the **Sources** panel.</span></span>  
1.  <span data-ttu-id="cf910-236">Make your changes in the **Editor** pane.</span><span class="sxs-lookup"><span data-stu-id="cf910-236">Make your changes in the **Editor** pane.</span></span>  
1.  <span data-ttu-id="cf910-237">Press `Ctrl`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save.</span><span class="sxs-lookup"><span data-stu-id="cf910-237">Press `Ctrl`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save.</span></span>  <span data-ttu-id="cf910-238">DevTools patches the entire JS file into the JavaScript engine of Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="cf910-238">DevTools patches the entire JS file into the JavaScript engine of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-html-minified.msft.png" alt-text="Select Step over" lightbox="../media/javascript-sources-html-minified.msft.png":::
       <span data-ttu-id="cf910-240">The **Editor** pane</span><span class="sxs-lookup"><span data-stu-id="cf910-240">The **Editor** pane</span></span>  
    :::image-end:::  
     
## <span data-ttu-id="cf910-241">Disable JavaScript</span><span class="sxs-lookup"><span data-stu-id="cf910-241">Disable JavaScript</span></span>   

<span data-ttu-id="cf910-242">See [Disable JavaScript with Microsoft Edge DevTools][DevToolsJavascriptDisable].</span><span class="sxs-lookup"><span data-stu-id="cf910-242">See [Disable JavaScript with Microsoft Edge DevTools][DevToolsJavascriptDisable].</span></span>  

## <span data-ttu-id="cf910-243">Getting in touch with the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="cf910-243">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageStepOverIcon]: ../media/step-over-icon.msft.png  
[ImageStepIntoIcon]: ../media/step-into-icon.msft.png  
[ImageStepOutIcon]: ../media/step-out-icon.msft.png  
[ImageResumeScriptExecutionIcon]: ../media/resume-script-run-icon.msft.png  
[ImageForceScriptExecutionIcon]: ../media/force-script-run-icon.msft.png  
[ImageAddExpressionIcon]: ../media/add-expression-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageDeleteExpressionIcon]: ../media/delete-expression-icon.msft.png  
[ImageFormatIcon]: ../media/format-icon.msft.png  

<!-- links -->  

[DevToolsJavascriptBreakpoints]: ./breakpoints.md "How to pause your code with breakpoints in Microsoft Edge DevTools | Microsoft Docs"  
[DevToolsJavascriptDisable]: ./disable.md "Disable JavaScript with Microsoft Edge DevTools | Microsoft Docs"  
[DevToolsJavascriptGetStarted]: ./index.md "Get started with debugging JavaScript in Microsoft Edge DevTools | Microsoft Docs"  
[DevToolsJavascriptSnippets]: ./snippets.md "Run snippets of JavaScript on any page with Microsoft Edge DevTools | Microsoft Docs"  
[DevToolsCustomize]: ../customize/index.md "Customize Microsoft Edge DevTools | Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="cf910-249">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="cf910-249">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="cf910-250">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="cf910-250">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="cf910-252">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="cf910-252">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
