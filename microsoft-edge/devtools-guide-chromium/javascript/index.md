---
description: Learn how to use Microsoft Edge DevTools to find and fix JavaScript bugs.
title: Get Started with Debugging JavaScript in Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: f8846388f92ba330940b4b6842964d96d9bbce4d
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993392"
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







# <span data-ttu-id="285ee-104">Get started with debugging JavaScript in Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="285ee-104">Get started with debugging JavaScript in Microsoft Edge DevTools</span></span>   



<span data-ttu-id="285ee-105">This tutorial teaches you the basic workflow for debugging any JavaScript issue in DevTools.</span><span class="sxs-lookup"><span data-stu-id="285ee-105">This tutorial teaches you the basic workflow for debugging any JavaScript issue in DevTools.</span></span>  

## <span data-ttu-id="285ee-106">Step 1: Reproduce the bug</span><span class="sxs-lookup"><span data-stu-id="285ee-106">Step 1: Reproduce the bug</span></span>   

<span data-ttu-id="285ee-107">Finding a series of actions that consistently reproduces a bug is always the first step to debugging.</span><span class="sxs-lookup"><span data-stu-id="285ee-107">Finding a series of actions that consistently reproduces a bug is always the first step to debugging.</span></span>  

1.  <span data-ttu-id="285ee-108">Click **Open Demo**.</span><span class="sxs-lookup"><span data-stu-id="285ee-108">Click **Open Demo**.</span></span>  <span data-ttu-id="285ee-109">Hold `Control` \(Windows\) or `Command` \(macOS\) and open the demo in a new tab.</span><span class="sxs-lookup"><span data-stu-id="285ee-109">Hold `Control` \(Windows\) or `Command` \(macOS\) and open the demo in a new tab.</span></span>  
    
    [<span data-ttu-id="285ee-110">Open Demo</span><span class="sxs-lookup"><span data-stu-id="285ee-110">Open Demo</span></span>][OpenDebugJSDemo]  
    
1.  <span data-ttu-id="285ee-111">Enter `5` in the **Number 1** text box.</span><span class="sxs-lookup"><span data-stu-id="285ee-111">Enter `5` in the **Number 1** text box.</span></span>  
1.  <span data-ttu-id="285ee-112">Enter `1` in the **Number 2** text box.</span><span class="sxs-lookup"><span data-stu-id="285ee-112">Enter `1` in the **Number 2** text box.</span></span>  
1.  <span data-ttu-id="285ee-113">Click **Add Number 1 and Number 2**.</span><span class="sxs-lookup"><span data-stu-id="285ee-113">Click **Add Number 1 and Number 2**.</span></span>  <span data-ttu-id="285ee-114">The label below the button says `5 + 1 = 51`.</span><span class="sxs-lookup"><span data-stu-id="285ee-114">The label below the button says `5 + 1 = 51`.</span></span>  <span data-ttu-id="285ee-115">The result should be `6`.</span><span class="sxs-lookup"><span data-stu-id="285ee-115">The result should be `6`.</span></span>  <span data-ttu-id="285ee-116">This is the bug you are going to fix.</span><span class="sxs-lookup"><span data-stu-id="285ee-116">This is the bug you are going to fix.</span></span>  
    
    :::image type="complex" source="../media/javascript-js-demo-bad.msft.png" alt-text="The result of 5 + 1 is 51, but should be 6" lightbox="../media/javascript-js-demo-bad.msft.png":::
       <span data-ttu-id="285ee-118">The result of `5 + 1` is `51`, but should be</span><span class="sxs-lookup"><span data-stu-id="285ee-118">The result of `5 + 1` is `51`, but should be</span></span> `6`  
    :::image-end:::  
    
## <span data-ttu-id="285ee-119">Step 2: Get familiar with the Sources panel UI</span><span class="sxs-lookup"><span data-stu-id="285ee-119">Step 2: Get familiar with the Sources panel UI</span></span>   

<span data-ttu-id="285ee-120">DevTools provides a lot of different tools for different tasks, such as changing CSS, profiling page load performance, and monitoring network requests.</span><span class="sxs-lookup"><span data-stu-id="285ee-120">DevTools provides a lot of different tools for different tasks, such as changing CSS, profiling page load performance, and monitoring network requests.</span></span>  <span data-ttu-id="285ee-121">The **Sources** panel is where you debug JavaScript.</span><span class="sxs-lookup"><span data-stu-id="285ee-121">The **Sources** panel is where you debug JavaScript.</span></span>  

1.  <span data-ttu-id="285ee-122">Open DevTools by pressing `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) .</span><span class="sxs-lookup"><span data-stu-id="285ee-122">Open DevTools by pressing `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) .</span></span>  <span data-ttu-id="285ee-123">This shortcut opens the **Console** panel.</span><span class="sxs-lookup"><span data-stu-id="285ee-123">This shortcut opens the **Console** panel.</span></span>  
    
    :::image type="complex" source="../media/javascript-console-empty.msft.png" alt-text="The result of 5 + 1 is 51, but should be 6" lightbox="../media/javascript-console-empty.msft.png":::
       <span data-ttu-id="285ee-125">The **Console** panel</span><span class="sxs-lookup"><span data-stu-id="285ee-125">The **Console** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="285ee-126">Click the **Sources** tab.</span><span class="sxs-lookup"><span data-stu-id="285ee-126">Click the **Sources** tab.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-sections.msft.png" alt-text="The result of 5 + 1 is 51, but should be 6" lightbox="../media/javascript-sources-sections.msft.png":::
       <span data-ttu-id="285ee-128">The **Sources** panel</span><span class="sxs-lookup"><span data-stu-id="285ee-128">The **Sources** panel</span></span>  
    :::image-end:::  
    
<span data-ttu-id="285ee-129">The **Sources** panel UI has 3 parts.</span><span class="sxs-lookup"><span data-stu-id="285ee-129">The **Sources** panel UI has 3 parts.</span></span>  

:::image type="complex" source="../media/javascript-sources-sections-annotated.msft.png" alt-text="The result of 5 + 1 is 51, but should be 6" lightbox="../media/javascript-sources-sections-annotated.msft.png":::
   <span data-ttu-id="285ee-131">The 3 parts of the **Sources** panel UI</span><span class="sxs-lookup"><span data-stu-id="285ee-131">The 3 parts of the **Sources** panel UI</span></span>  
:::image-end:::  

1.  <span data-ttu-id="285ee-132">The **File Navigator** pane \(Section 1 in the previous figure\).</span><span class="sxs-lookup"><span data-stu-id="285ee-132">The **File Navigator** pane \(Section 1 in the previous figure\).</span></span>  <span data-ttu-id="285ee-133">Every file that the page requests is listed here.</span><span class="sxs-lookup"><span data-stu-id="285ee-133">Every file that the page requests is listed here.</span></span>  
1.  <span data-ttu-id="285ee-134">The **Code Editor** pane \(Section 2 in the previous figure\).</span><span class="sxs-lookup"><span data-stu-id="285ee-134">The **Code Editor** pane \(Section 2 in the previous figure\).</span></span>  <span data-ttu-id="285ee-135">After selecting a file in the **File Navigator** pane, the contents of that file are displayed here.</span><span class="sxs-lookup"><span data-stu-id="285ee-135">After selecting a file in the **File Navigator** pane, the contents of that file are displayed here.</span></span>  
1.  <span data-ttu-id="285ee-136">The **JavaScript Debugging** pane \(Section 3 in the previous figure\).</span><span class="sxs-lookup"><span data-stu-id="285ee-136">The **JavaScript Debugging** pane \(Section 3 in the previous figure\).</span></span>  <span data-ttu-id="285ee-137">Various tools for inspecting the JavaScript for the page.</span><span class="sxs-lookup"><span data-stu-id="285ee-137">Various tools for inspecting the JavaScript for the page.</span></span>  <span data-ttu-id="285ee-138">If your DevTools window is wide, this pane is displayed to the right of the **Code Editor** pane.</span><span class="sxs-lookup"><span data-stu-id="285ee-138">If your DevTools window is wide, this pane is displayed to the right of the **Code Editor** pane.</span></span>  
    
## <span data-ttu-id="285ee-139">Step 3: Pause the code with a breakpoint</span><span class="sxs-lookup"><span data-stu-id="285ee-139">Step 3: Pause the code with a breakpoint</span></span>   

<span data-ttu-id="285ee-140">A common method for debugging a problem like this is to insert a lot of `console.log()` statements into the code, in order to inspect values as the script runs.</span><span class="sxs-lookup"><span data-stu-id="285ee-140">A common method for debugging a problem like this is to insert a lot of `console.log()` statements into the code, in order to inspect values as the script runs.</span></span>  <span data-ttu-id="285ee-141">For example:</span><span class="sxs-lookup"><span data-stu-id="285ee-141">For example:</span></span>  

```javascript
function updateLabel() {
    var addend1 = getNumber1();
    console.log('addend1:', addend1);
    var addend2 = getNumber2();
    console.log('addend2:', addend2);
    var sum = addend1 + addend2;
    console.log('sum:', sum);
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
}
```  

<span data-ttu-id="285ee-142">The `console.log()` method may get the job done, but **breakpoints** are able to get it done faster.</span><span class="sxs-lookup"><span data-stu-id="285ee-142">The `console.log()` method may get the job done, but **breakpoints** are able to get it done faster.</span></span>  <span data-ttu-id="285ee-143">A breakpoint lets you pause your code in the middle of the runtime, and examine all values at that moment in time.</span><span class="sxs-lookup"><span data-stu-id="285ee-143">A breakpoint lets you pause your code in the middle of the runtime, and examine all values at that moment in time.</span></span>  <span data-ttu-id="285ee-144">Breakpoints have a few advantages over the `console.log()` method:</span><span class="sxs-lookup"><span data-stu-id="285ee-144">Breakpoints have a few advantages over the `console.log()` method:</span></span>  

*   <span data-ttu-id="285ee-145">With `console.log()`, you need to manually open the source code, find the relevant code, insert the `console.log()` statements, and then reload the page in order to see the messages in the Console.</span><span class="sxs-lookup"><span data-stu-id="285ee-145">With `console.log()`, you need to manually open the source code, find the relevant code, insert the `console.log()` statements, and then reload the page in order to see the messages in the Console.</span></span>  <span data-ttu-id="285ee-146">With breakpoints, you may pause on the relevant code without even knowing how the code is structured.</span><span class="sxs-lookup"><span data-stu-id="285ee-146">With breakpoints, you may pause on the relevant code without even knowing how the code is structured.</span></span>  
*   <span data-ttu-id="285ee-147">In your `console.log()` statements you need to explicitly specify each value that you want to inspect.</span><span class="sxs-lookup"><span data-stu-id="285ee-147">In your `console.log()` statements you need to explicitly specify each value that you want to inspect.</span></span>  <span data-ttu-id="285ee-148">With breakpoints, DevTools shows you the values of all variables at that moment in time.</span><span class="sxs-lookup"><span data-stu-id="285ee-148">With breakpoints, DevTools shows you the values of all variables at that moment in time.</span></span>  <span data-ttu-id="285ee-149">Sometimes there are variables affecting your code that you are not even aware of.</span><span class="sxs-lookup"><span data-stu-id="285ee-149">Sometimes there are variables affecting your code that you are not even aware of.</span></span>  

<span data-ttu-id="285ee-150">In short, breakpoints may help you find and fix bugs faster than the `console.log()` method.</span><span class="sxs-lookup"><span data-stu-id="285ee-150">In short, breakpoints may help you find and fix bugs faster than the `console.log()` method.</span></span>  

<span data-ttu-id="285ee-151">If you take a step back and think about how the app works, you are able to make an educated guess that the incorrect sum (`5 + 1 = 51`) gets computed in the `click` event listener that is associated to the **Add Number 1 and Number 2** button.</span><span class="sxs-lookup"><span data-stu-id="285ee-151">If you take a step back and think about how the app works, you are able to make an educated guess that the incorrect sum (`5 + 1 = 51`) gets computed in the `click` event listener that is associated to the **Add Number 1 and Number 2** button.</span></span>  <span data-ttu-id="285ee-152">Therefore, you probably want to pause the code around the time that the `click` listener runs.</span><span class="sxs-lookup"><span data-stu-id="285ee-152">Therefore, you probably want to pause the code around the time that the `click` listener runs.</span></span>  <span data-ttu-id="285ee-153">**Event Listener Breakpoints** let you do exactly that:</span><span class="sxs-lookup"><span data-stu-id="285ee-153">**Event Listener Breakpoints** let you do exactly that:</span></span>  

1.  <span data-ttu-id="285ee-154">In the **JavaScript Debugging** pane, click **Event Listener Breakpoints** to expand the section.</span><span class="sxs-lookup"><span data-stu-id="285ee-154">In the **JavaScript Debugging** pane, click **Event Listener Breakpoints** to expand the section.</span></span>  <span data-ttu-id="285ee-155">DevTools reveals a list of expandable event categories, such as **Animation** and **Clipboard**.</span><span class="sxs-lookup"><span data-stu-id="285ee-155">DevTools reveals a list of expandable event categories, such as **Animation** and **Clipboard**.</span></span>  
1.  <span data-ttu-id="285ee-156">Next to the **Mouse** event category, click **Expand** \(![Expand icon][ImageExpandIcon]\).</span><span class="sxs-lookup"><span data-stu-id="285ee-156">Next to the **Mouse** event category, click **Expand** \(![Expand icon][ImageExpandIcon]\).</span></span>  <span data-ttu-id="285ee-157">DevTools reveals a list of mouse events, such as **click** and **mousedown**.</span><span class="sxs-lookup"><span data-stu-id="285ee-157">DevTools reveals a list of mouse events, such as **click** and **mousedown**.</span></span>  <span data-ttu-id="285ee-158">Each event has a checkbox next to it.</span><span class="sxs-lookup"><span data-stu-id="285ee-158">Each event has a checkbox next to it.</span></span>  
1.  <span data-ttu-id="285ee-159">Check the **click** checkbox.</span><span class="sxs-lookup"><span data-stu-id="285ee-159">Check the **click** checkbox.</span></span>  <span data-ttu-id="285ee-160">DevTools is now set up to automatically pause when *any* `click` event listener runs.</span><span class="sxs-lookup"><span data-stu-id="285ee-160">DevTools is now set up to automatically pause when *any* `click` event listener runs.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png" alt-text="The result of 5 + 1 is 51, but should be 6" lightbox="../media/javascript-sources-event-listener-breakpoint-mouse-click.msft.png":::
       <span data-ttu-id="285ee-162">The **click** checkbox is enabled</span><span class="sxs-lookup"><span data-stu-id="285ee-162">The **click** checkbox is enabled</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="285ee-163">Back on the demo, click **Add Number 1 and Number 2** again.</span><span class="sxs-lookup"><span data-stu-id="285ee-163">Back on the demo, click **Add Number 1 and Number 2** again.</span></span>  <span data-ttu-id="285ee-164">DevTools pauses the demo and highlights a line of code in the **Sources** panel.</span><span class="sxs-lookup"><span data-stu-id="285ee-164">DevTools pauses the demo and highlights a line of code in the **Sources** panel.</span></span>  <span data-ttu-id="285ee-165">DevTools should pause on line 16 in `get-started.js`.</span><span class="sxs-lookup"><span data-stu-id="285ee-165">DevTools should pause on line 16 in `get-started.js`.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    <span data-ttu-id="285ee-166">If you pause on a different line of code, press **Resume Script Execution** \(![Resume Script Execution][ImageResumeIcon]\) until you pause on the correct line.</span><span class="sxs-lookup"><span data-stu-id="285ee-166">If you pause on a different line of code, press **Resume Script Execution** \(![Resume Script Execution][ImageResumeIcon]\) until you pause on the correct line.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="285ee-167">If you paused on a different line, you have a browser extension that registers a `click` event listener on every page that you visit.</span><span class="sxs-lookup"><span data-stu-id="285ee-167">If you paused on a different line, you have a browser extension that registers a `click` event listener on every page that you visit.</span></span>  <span data-ttu-id="285ee-168">You were paused in the `click` listener of the extension.</span><span class="sxs-lookup"><span data-stu-id="285ee-168">You were paused in the `click` listener of the extension.</span></span>  <span data-ttu-id="285ee-169">If you use InPrivate Mode to **browse in private**, which disables all extensions, you may see that you pause on the desired line of code every time.</span><span class="sxs-lookup"><span data-stu-id="285ee-169">If you use InPrivate Mode to **browse in private**, which disables all extensions, you may see that you pause on the desired line of code every time.</span></span>  

<!--todo: add inprivate section when available -->  

<span data-ttu-id="285ee-170">**Event Listener Breakpoints** are just one of many types of breakpoints available in DevTools.</span><span class="sxs-lookup"><span data-stu-id="285ee-170">**Event Listener Breakpoints** are just one of many types of breakpoints available in DevTools.</span></span>  <span data-ttu-id="285ee-171">It is worth memorizing all the different types, because each type ultimately helps you debug different scenarios as quickly as possible.</span><span class="sxs-lookup"><span data-stu-id="285ee-171">It is worth memorizing all the different types, because each type ultimately helps you debug different scenarios as quickly as possible.</span></span>  <!--See [Pause Your Code With Breakpoints][JSBreakpoints] to learn when and how to use each type.  -->  

## <span data-ttu-id="285ee-172">Step 4: Step through the code</span><span class="sxs-lookup"><span data-stu-id="285ee-172">Step 4: Step through the code</span></span>   

<span data-ttu-id="285ee-173">One common cause of bugs is when a script runs in the wrong order.</span><span class="sxs-lookup"><span data-stu-id="285ee-173">One common cause of bugs is when a script runs in the wrong order.</span></span>  <span data-ttu-id="285ee-174">Stepping through your code enables you to walk through the runtime of your code, one line at a time, and figure out exactly where it is running in a different order than you expected.</span><span class="sxs-lookup"><span data-stu-id="285ee-174">Stepping through your code enables you to walk through the runtime of your code, one line at a time, and figure out exactly where it is running in a different order than you expected.</span></span>  <span data-ttu-id="285ee-175">Try it now:</span><span class="sxs-lookup"><span data-stu-id="285ee-175">Try it now:</span></span>  

1.  <span data-ttu-id="285ee-176">Click **Step over next function call** \(![Step over next function call][ImageOverIcon]\).</span><span class="sxs-lookup"><span data-stu-id="285ee-176">Click **Step over next function call** \(![Step over next function call][ImageOverIcon]\).</span></span>  <span data-ttu-id="285ee-177">DevTools runs the following code without stepping into it.</span><span class="sxs-lookup"><span data-stu-id="285ee-177">DevTools runs the following code without stepping into it.</span></span>  
    
    ```javascript
    if (inputsAreEmpty()) {
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="285ee-178">DevTools skips a few lines of code.</span><span class="sxs-lookup"><span data-stu-id="285ee-178">DevTools skips a few lines of code.</span></span>  <span data-ttu-id="285ee-179">This is because `inputsAreEmpty()` evaluates as false, so the block of code for the `if` statement does not run.</span><span class="sxs-lookup"><span data-stu-id="285ee-179">This is because `inputsAreEmpty()` evaluates as false, so the block of code for the `if` statement does not run.</span></span>  
    
1.  <span data-ttu-id="285ee-180">On the **Sources** panel of DevTools, click **Step into next function call** \(![Step into next function call][ImageIntoIcon]\) to step through the runtime of the `updateLabel()` function, one line at a time.</span><span class="sxs-lookup"><span data-stu-id="285ee-180">On the **Sources** panel of DevTools, click **Step into next function call** \(![Step into next function call][ImageIntoIcon]\) to step through the runtime of the `updateLabel()` function, one line at a time.</span></span>  
    
<span data-ttu-id="285ee-181">That is the basic idea of stepping through code.</span><span class="sxs-lookup"><span data-stu-id="285ee-181">That is the basic idea of stepping through code.</span></span>  <span data-ttu-id="285ee-182">If you look at the code in `get-started.js`, you see that the bug is probably somewhere in the `updateLabel()` function.</span><span class="sxs-lookup"><span data-stu-id="285ee-182">If you look at the code in `get-started.js`, you see that the bug is probably somewhere in the `updateLabel()` function.</span></span>  <span data-ttu-id="285ee-183">Rather than stepping through every line of code, you may use another type of breakpoint to pause the code closer to the probable location of the bug.</span><span class="sxs-lookup"><span data-stu-id="285ee-183">Rather than stepping through every line of code, you may use another type of breakpoint to pause the code closer to the probable location of the bug.</span></span>  

## <span data-ttu-id="285ee-184">Step 5: Set a line-of-code breakpoint</span><span class="sxs-lookup"><span data-stu-id="285ee-184">Step 5: Set a line-of-code breakpoint</span></span>   

<span data-ttu-id="285ee-185">Line-of-code breakpoints are the most common type of breakpoint.</span><span class="sxs-lookup"><span data-stu-id="285ee-185">Line-of-code breakpoints are the most common type of breakpoint.</span></span>  <span data-ttu-id="285ee-186">When you get the specific line of code that you want to pause on, use a line-of-code breakpoint:</span><span class="sxs-lookup"><span data-stu-id="285ee-186">When you get the specific line of code that you want to pause on, use a line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="285ee-187">Look at the last line of code in `updateLabel()`:</span><span class="sxs-lookup"><span data-stu-id="285ee-187">Look at the last line of code in `updateLabel()`:</span></span>  
    
    ```javascript
    label.textContent = addend1 + ' + ' + addend2 + ' = ' + sum;
    ```  
    
1.  <span data-ttu-id="285ee-188">To the left of the code you see the line number of this particular line of code, which is **33**.</span><span class="sxs-lookup"><span data-stu-id="285ee-188">To the left of the code you see the line number of this particular line of code, which is **33**.</span></span>  <span data-ttu-id="285ee-189">Click on **33**.</span><span class="sxs-lookup"><span data-stu-id="285ee-189">Click on **33**.</span></span>  <span data-ttu-id="285ee-190">DevTools puts a red icon to the left of **33**.</span><span class="sxs-lookup"><span data-stu-id="285ee-190">DevTools puts a red icon to the left of **33**.</span></span>  <span data-ttu-id="285ee-191">This means that there is a line-of-code breakpoint on this line.</span><span class="sxs-lookup"><span data-stu-id="285ee-191">This means that there is a line-of-code breakpoint on this line.</span></span>  <span data-ttu-id="285ee-192">DevTools now always pauses before this line of code is run.</span><span class="sxs-lookup"><span data-stu-id="285ee-192">DevTools now always pauses before this line of code is run.</span></span>  
1.  <span data-ttu-id="285ee-193">Click **Resume script execution** \(![Resume script execution][ImageResumeIcon]\).</span><span class="sxs-lookup"><span data-stu-id="285ee-193">Click **Resume script execution** \(![Resume script execution][ImageResumeIcon]\).</span></span>  <span data-ttu-id="285ee-194">The script continues running until it reaches line 33.</span><span class="sxs-lookup"><span data-stu-id="285ee-194">The script continues running until it reaches line 33.</span></span>  <span data-ttu-id="285ee-195">On lines 30, 31, and 32, DevTools prints out the values of `addend1`, `addend2`, and `sum` to the right of the semi-colon on each line.</span><span class="sxs-lookup"><span data-stu-id="285ee-195">On lines 30, 31, and 32, DevTools prints out the values of `addend1`, `addend2`, and `sum` to the right of the semi-colon on each line.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused.msft.png" alt-text="The result of 5 + 1 is 51, but should be 6" lightbox="../media/javascript-sources-breakpoint-paused.msft.png":::
       <span data-ttu-id="285ee-197">DevTools pauses on the line-of-code breakpoint on line 32</span><span class="sxs-lookup"><span data-stu-id="285ee-197">DevTools pauses on the line-of-code breakpoint on line 32</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="285ee-198">Step 6: Check variable values</span><span class="sxs-lookup"><span data-stu-id="285ee-198">Step 6: Check variable values</span></span>   

<span data-ttu-id="285ee-199">The values of `addend1`, `addend2`, and `sum` look suspicious.</span><span class="sxs-lookup"><span data-stu-id="285ee-199">The values of `addend1`, `addend2`, and `sum` look suspicious.</span></span>  <span data-ttu-id="285ee-200">They are wrapped in quotes, which means that they are strings.</span><span class="sxs-lookup"><span data-stu-id="285ee-200">They are wrapped in quotes, which means that they are strings.</span></span>  <span data-ttu-id="285ee-201">This is a good hypothesis for the explaining the cause of the bug.</span><span class="sxs-lookup"><span data-stu-id="285ee-201">This is a good hypothesis for the explaining the cause of the bug.</span></span>  <span data-ttu-id="285ee-202">Now it is time to gather more information.</span><span class="sxs-lookup"><span data-stu-id="285ee-202">Now it is time to gather more information.</span></span>  <span data-ttu-id="285ee-203">DevTools provides a lot of tools for examining variable values.</span><span class="sxs-lookup"><span data-stu-id="285ee-203">DevTools provides a lot of tools for examining variable values.</span></span>  

### <span data-ttu-id="285ee-204">Method 1: The Scope pane</span><span class="sxs-lookup"><span data-stu-id="285ee-204">Method 1: The Scope pane</span></span>   

<span data-ttu-id="285ee-205">When you pause on a line of code, the **Scope** pane shows you what local and global variables are currently defined, along with the value of each variable.</span><span class="sxs-lookup"><span data-stu-id="285ee-205">When you pause on a line of code, the **Scope** pane shows you what local and global variables are currently defined, along with the value of each variable.</span></span>  <span data-ttu-id="285ee-206">It also shows closure variables, when applicable.</span><span class="sxs-lookup"><span data-stu-id="285ee-206">It also shows closure variables, when applicable.</span></span>  <span data-ttu-id="285ee-207">Double-click a variable value to edit it.</span><span class="sxs-lookup"><span data-stu-id="285ee-207">Double-click a variable value to edit it.</span></span>  <span data-ttu-id="285ee-208">When you are not paused on a line of code, the **Scope** pane is empty.</span><span class="sxs-lookup"><span data-stu-id="285ee-208">When you are not paused on a line of code, the **Scope** pane is empty.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-scope.msft.png" alt-text="The result of 5 + 1 is 51, but should be 6" lightbox="../media/javascript-sources-breakpoint-paused-scope.msft.png":::
   <span data-ttu-id="285ee-210">The **Scope** pane</span><span class="sxs-lookup"><span data-stu-id="285ee-210">The **Scope** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="285ee-211">Method 2: Watch Expressions</span><span class="sxs-lookup"><span data-stu-id="285ee-211">Method 2: Watch Expressions</span></span>   

<span data-ttu-id="285ee-212">The **Watch Expressions** tab lets you monitor the values of variables over time.</span><span class="sxs-lookup"><span data-stu-id="285ee-212">The **Watch Expressions** tab lets you monitor the values of variables over time.</span></span>  <span data-ttu-id="285ee-213">As the name implies, Watch Expressions are not just limited to variables.</span><span class="sxs-lookup"><span data-stu-id="285ee-213">As the name implies, Watch Expressions are not just limited to variables.</span></span>  <span data-ttu-id="285ee-214">You are able to store any valid JavaScript expression in a Watch Expression.</span><span class="sxs-lookup"><span data-stu-id="285ee-214">You are able to store any valid JavaScript expression in a Watch Expression.</span></span>  <span data-ttu-id="285ee-215">Try it now:</span><span class="sxs-lookup"><span data-stu-id="285ee-215">Try it now:</span></span>  

1.  <span data-ttu-id="285ee-216">Click the **Watch** tab.</span><span class="sxs-lookup"><span data-stu-id="285ee-216">Click the **Watch** tab.</span></span>  
1.  <span data-ttu-id="285ee-217">Click **Add Expression** \(![Add Expression][ImageAddIcon]\).</span><span class="sxs-lookup"><span data-stu-id="285ee-217">Click **Add Expression** \(![Add Expression][ImageAddIcon]\).</span></span>  
1.  <span data-ttu-id="285ee-218">Type `typeof sum`.</span><span class="sxs-lookup"><span data-stu-id="285ee-218">Type `typeof sum`.</span></span>  
1.  <span data-ttu-id="285ee-219">Press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="285ee-219">Press `Enter`.</span></span>  <span data-ttu-id="285ee-220">DevTools shows `typeof sum: "string"`.</span><span class="sxs-lookup"><span data-stu-id="285ee-220">DevTools shows `typeof sum: "string"`.</span></span>  <span data-ttu-id="285ee-221">The value to the right of the colon is the result of your Watch Expression.</span><span class="sxs-lookup"><span data-stu-id="285ee-221">The value to the right of the colon is the result of your Watch Expression.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="285ee-222">In the Watch Expression pane \(bottom-right\) in in the following figure, the `typeof sum` Watch Expression is displayed.</span><span class="sxs-lookup"><span data-stu-id="285ee-222">In the Watch Expression pane \(bottom-right\) in in the following figure, the `typeof sum` Watch Expression is displayed.</span></span>  <span data-ttu-id="285ee-223">If your DevTools window is large, the Watch Expression pane is on the right above the **Event Listener Breakpoints** pane.</span><span class="sxs-lookup"><span data-stu-id="285ee-223">If your DevTools window is large, the Watch Expression pane is on the right above the **Event Listener Breakpoints** pane.</span></span>  

:::image type="complex" source="../media/javascript-sources-breakpoint-paused-watch.msft.png" alt-text="The result of 5 + 1 is 51, but should be 6" lightbox="../media/javascript-sources-breakpoint-paused-watch.msft.png":::
   <span data-ttu-id="285ee-225">The **Watch Expression** pane</span><span class="sxs-lookup"><span data-stu-id="285ee-225">The **Watch Expression** pane</span></span>  
:::image-end:::  

<span data-ttu-id="285ee-226">As suspected, `sum` is being evaluated as a string, when it should be a number.</span><span class="sxs-lookup"><span data-stu-id="285ee-226">As suspected, `sum` is being evaluated as a string, when it should be a number.</span></span>  <span data-ttu-id="285ee-227">You have now confirmed that this is the cause of the bug.</span><span class="sxs-lookup"><span data-stu-id="285ee-227">You have now confirmed that this is the cause of the bug.</span></span>  

### <span data-ttu-id="285ee-228">Method 3: The Console</span><span class="sxs-lookup"><span data-stu-id="285ee-228">Method 3: The Console</span></span>   

<span data-ttu-id="285ee-229">In addition to viewing `console.log()` messages, you may also use the Console to evaluate arbitrary JavaScript statements.</span><span class="sxs-lookup"><span data-stu-id="285ee-229">In addition to viewing `console.log()` messages, you may also use the Console to evaluate arbitrary JavaScript statements.</span></span>  <span data-ttu-id="285ee-230">In terms of debugging, you may use the Console to test out potential fixes for bugs.</span><span class="sxs-lookup"><span data-stu-id="285ee-230">In terms of debugging, you may use the Console to test out potential fixes for bugs.</span></span>  <span data-ttu-id="285ee-231">Try it now:</span><span class="sxs-lookup"><span data-stu-id="285ee-231">Try it now:</span></span>  

1.  <span data-ttu-id="285ee-232">If you do not have the Console drawer open, press `Escape` to open it.</span><span class="sxs-lookup"><span data-stu-id="285ee-232">If you do not have the Console drawer open, press `Escape` to open it.</span></span>  <span data-ttu-id="285ee-233">It opens at the bottom of your DevTools window.</span><span class="sxs-lookup"><span data-stu-id="285ee-233">It opens at the bottom of your DevTools window.</span></span>  
1.  <span data-ttu-id="285ee-234">In the Console, type `parseInt(addend1) + parseInt(addend2)`.</span><span class="sxs-lookup"><span data-stu-id="285ee-234">In the Console, type `parseInt(addend1) + parseInt(addend2)`.</span></span>  <span data-ttu-id="285ee-235">This statement works because you are paused on a line of code where `addend1` and `addend2` are in scope.</span><span class="sxs-lookup"><span data-stu-id="285ee-235">This statement works because you are paused on a line of code where `addend1` and `addend2` are in scope.</span></span>  
1.  <span data-ttu-id="285ee-236">Press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="285ee-236">Press `Enter`.</span></span>  <span data-ttu-id="285ee-237">DevTools evaluates the statement and prints out `6`, which is the result you expect the demo to produce.</span><span class="sxs-lookup"><span data-stu-id="285ee-237">DevTools evaluates the statement and prints out `6`, which is the result you expect the demo to produce.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-breakpoint-paused-console.msft.png" alt-text="The result of 5 + 1 is 51, but should be 6" lightbox="../media/javascript-sources-breakpoint-paused-console.msft.png":::
       <span data-ttu-id="285ee-239">The **Console** drawer, after evaluating</span><span class="sxs-lookup"><span data-stu-id="285ee-239">The **Console** drawer, after evaluating</span></span> `parseInt(addend1) + parseInt(addend2)`  
    :::image-end:::  
    
## <span data-ttu-id="285ee-240">Step 7: Apply a fix</span><span class="sxs-lookup"><span data-stu-id="285ee-240">Step 7: Apply a fix</span></span>   

<span data-ttu-id="285ee-241">If you find a fix for the bug, try out your fix by editing the code and re-running the demo.</span><span class="sxs-lookup"><span data-stu-id="285ee-241">If you find a fix for the bug, try out your fix by editing the code and re-running the demo.</span></span>  <span data-ttu-id="285ee-242">You do not need to leave DevTools to apply the fix.</span><span class="sxs-lookup"><span data-stu-id="285ee-242">You do not need to leave DevTools to apply the fix.</span></span>  <span data-ttu-id="285ee-243">You are able to edit JavaScript code directly within the DevTools UI.</span><span class="sxs-lookup"><span data-stu-id="285ee-243">You are able to edit JavaScript code directly within the DevTools UI.</span></span>  <span data-ttu-id="285ee-244">Try it now:</span><span class="sxs-lookup"><span data-stu-id="285ee-244">Try it now:</span></span>  

1.  <span data-ttu-id="285ee-245">Click **Resume script execution** \(![Resume script execution][ImageResumeIcon]\).</span><span class="sxs-lookup"><span data-stu-id="285ee-245">Click **Resume script execution** \(![Resume script execution][ImageResumeIcon]\).</span></span>  
1.  <span data-ttu-id="285ee-246">In the **Code Editor**, replace line 32, `var sum = addend1 + addend2`, with `var sum = parseInt(addend1) + parseInt(addend2)`.</span><span class="sxs-lookup"><span data-stu-id="285ee-246">In the **Code Editor**, replace line 32, `var sum = addend1 + addend2`, with `var sum = parseInt(addend1) + parseInt(addend2)`.</span></span>  
1.  <span data-ttu-id="285ee-247">Press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save your change.</span><span class="sxs-lookup"><span data-stu-id="285ee-247">Press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save your change.</span></span>  
1.  <span data-ttu-id="285ee-248">Click **Deactivate breakpoints** \(![Deactivate breakpoints][ImageDeactivateIcon]\).</span><span class="sxs-lookup"><span data-stu-id="285ee-248">Click **Deactivate breakpoints** \(![Deactivate breakpoints][ImageDeactivateIcon]\).</span></span>  <span data-ttu-id="285ee-249">It changes blue to indicate that it is active.</span><span class="sxs-lookup"><span data-stu-id="285ee-249">It changes blue to indicate that it is active.</span></span>  <span data-ttu-id="285ee-250">While this is set, DevTools ignores any breakpoints you set.</span><span class="sxs-lookup"><span data-stu-id="285ee-250">While this is set, DevTools ignores any breakpoints you set.</span></span>  
1.  <span data-ttu-id="285ee-251">Try out the demo with different values.</span><span class="sxs-lookup"><span data-stu-id="285ee-251">Try out the demo with different values.</span></span>  <span data-ttu-id="285ee-252">The demo now calculates correctly.</span><span class="sxs-lookup"><span data-stu-id="285ee-252">The demo now calculates correctly.</span></span>  
    
> [!CAUTION]
> <span data-ttu-id="285ee-253">This workflow only applies a fix to the code that is running in your browser.</span><span class="sxs-lookup"><span data-stu-id="285ee-253">This workflow only applies a fix to the code that is running in your browser.</span></span>  <span data-ttu-id="285ee-254">It does not fix the code for all users that visit your page.</span><span class="sxs-lookup"><span data-stu-id="285ee-254">It does not fix the code for all users that visit your page.</span></span>  <span data-ttu-id="285ee-255">To do that, you need to fix the code that is on your servers.</span><span class="sxs-lookup"><span data-stu-id="285ee-255">To do that, you need to fix the code that is on your servers.</span></span>  

## <span data-ttu-id="285ee-256">Next steps</span><span class="sxs-lookup"><span data-stu-id="285ee-256">Next steps</span></span>   

<span data-ttu-id="285ee-257">Congratulations!</span><span class="sxs-lookup"><span data-stu-id="285ee-257">Congratulations!</span></span>  <span data-ttu-id="285ee-258">You now know how to make the most of Microsoft Edge DevTools when debugging JavaScript.</span><span class="sxs-lookup"><span data-stu-id="285ee-258">You now know how to make the most of Microsoft Edge DevTools when debugging JavaScript.</span></span>  <span data-ttu-id="285ee-259">The tools and methods you learned in this tutorial may save you countless hours.</span><span class="sxs-lookup"><span data-stu-id="285ee-259">The tools and methods you learned in this tutorial may save you countless hours.</span></span>  

<span data-ttu-id="285ee-260">This tutorial only showed you two ways to set breakpoints.</span><span class="sxs-lookup"><span data-stu-id="285ee-260">This tutorial only showed you two ways to set breakpoints.</span></span>  <span data-ttu-id="285ee-261">DevTools offers many other ways including the following settings.</span><span class="sxs-lookup"><span data-stu-id="285ee-261">DevTools offers many other ways including the following settings.</span></span>  

*   <span data-ttu-id="285ee-262">Conditional breakpoints that are only triggered when the condition that you provide is true.</span><span class="sxs-lookup"><span data-stu-id="285ee-262">Conditional breakpoints that are only triggered when the condition that you provide is true.</span></span>  
*   <span data-ttu-id="285ee-263">Breakpoints on caught or uncaught exceptions.</span><span class="sxs-lookup"><span data-stu-id="285ee-263">Breakpoints on caught or uncaught exceptions.</span></span>  
*   <span data-ttu-id="285ee-264">XHR breakpoints that are triggered when the requested URL matches a substring that you provide.</span><span class="sxs-lookup"><span data-stu-id="285ee-264">XHR breakpoints that are triggered when the requested URL matches a substring that you provide.</span></span>  
    
<span data-ttu-id="285ee-265">For more information about when and how to use each type, go to [Pause Your Code With Breakpoints][DevtoolsJavscriptBreakpoints].</span><span class="sxs-lookup"><span data-stu-id="285ee-265">For more information about when and how to use each type, go to [Pause Your Code With Breakpoints][DevtoolsJavscriptBreakpoints].</span></span>  

<span data-ttu-id="285ee-266">There are a couple of code stepping controls that were not explained in this tutorial.</span><span class="sxs-lookup"><span data-stu-id="285ee-266">There are a couple of code stepping controls that were not explained in this tutorial.</span></span>  <span data-ttu-id="285ee-267">For more information, go to [Step over line of code][DevtoolsJavascriptReferenceStepThroughCode].</span><span class="sxs-lookup"><span data-stu-id="285ee-267">For more information, go to [Step over line of code][DevtoolsJavascriptReferenceStepThroughCode].</span></span>  

<!--  
 


-->  

<!-- image links -->  

[ImageAddIcon]: ../media/add-expression-icon.msft.png  
[ImageDeactivateIcon]: ../media/deactivate-breakpoints-button-icon.msft.png  
[ImageExpandIcon]: ../media/expand-icon.msft.png  
[ImageIntoIcon]: ../media/step-into-icon.msft.png  
[ImageOverIcon]: ../media/step-over-icon.msft.png  
[ImageResumeIcon]: ../media/resume-script-run-icon.msft.png  

<!-- links -->  

[DevtoolsJavscriptBreakpoints]: ./breakpoints.md "How to pause your code with breakpoints in Microsoft Edge DevTools | Microsoft Docs"
[DevtoolsJavascriptReferenceStepThroughCode]: ./reference.md#step-through-code "Step through code - JavaScript debugging reference | Microsoft Docs"

<!--[inPrivate]: https://support.alphabet.com/alphabet-browser/answer/95464  -->  

[OpenDebugJSDemo]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "Open Demo | Glitch"  

> [!NOTE]
> <span data-ttu-id="285ee-271">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="285ee-271">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="285ee-272">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="285ee-272">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="285ee-274">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="285ee-274">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
