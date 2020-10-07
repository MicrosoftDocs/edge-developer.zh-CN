---
description: Learn about all the ways you are able to pause your code in Microsoft Edge DevTools.
title: How To Pause Your Code With Breakpoints In Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 95aba99c2cfe87f26704faa20964ace5d2abdf51
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992805"
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







# <span data-ttu-id="80ef1-104">How to pause your code with breakpoints in Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="80ef1-104">How to pause your code with breakpoints in Microsoft Edge DevTools</span></span>   



<span data-ttu-id="80ef1-105">Use breakpoints to pause your JavaScript code.</span><span class="sxs-lookup"><span data-stu-id="80ef1-105">Use breakpoints to pause your JavaScript code.</span></span>  <span data-ttu-id="80ef1-106">This guide explains each type of breakpoint that is available in DevTools, as well as when to use and how to set each type.</span><span class="sxs-lookup"><span data-stu-id="80ef1-106">This guide explains each type of breakpoint that is available in DevTools, as well as when to use and how to set each type.</span></span>  <span data-ttu-id="80ef1-107">For a hands-on tutorial of the debugging process, see [Get started with debugging JavaScript in Microsoft Edge DevTools][DevtoolsJavascriptIndex].</span><span class="sxs-lookup"><span data-stu-id="80ef1-107">For a hands-on tutorial of the debugging process, see [Get started with debugging JavaScript in Microsoft Edge DevTools][DevtoolsJavascriptIndex].</span></span>  

## <span data-ttu-id="80ef1-108">Overview of when to use each breakpoint type</span><span class="sxs-lookup"><span data-stu-id="80ef1-108">Overview of when to use each breakpoint type</span></span>   

<span data-ttu-id="80ef1-109">The most well-known type of breakpoint is line-of-code.</span><span class="sxs-lookup"><span data-stu-id="80ef1-109">The most well-known type of breakpoint is line-of-code.</span></span>  <span data-ttu-id="80ef1-110">But line-of-code breakpoints may be inefficient to set, especially if you do not know exactly where to look, or if you are working with a large codebase.</span><span class="sxs-lookup"><span data-stu-id="80ef1-110">But line-of-code breakpoints may be inefficient to set, especially if you do not know exactly where to look, or if you are working with a large codebase.</span></span>  <span data-ttu-id="80ef1-111">You may save yourself time when debugging by knowing how and when to use the other types of breakpoints.</span><span class="sxs-lookup"><span data-stu-id="80ef1-111">You may save yourself time when debugging by knowing how and when to use the other types of breakpoints.</span></span>  

| <span data-ttu-id="80ef1-112">Breakpoint Type</span><span class="sxs-lookup"><span data-stu-id="80ef1-112">Breakpoint Type</span></span> | <span data-ttu-id="80ef1-113">Use This When You Want To Pause...</span><span class="sxs-lookup"><span data-stu-id="80ef1-113">Use This When You Want To Pause...</span></span>  |  
|:--- |:--- |  
| [<span data-ttu-id="80ef1-114">Line-of-code</span><span class="sxs-lookup"><span data-stu-id="80ef1-114">Line-of-code</span></span>](#line-of-code-breakpoints) | <span data-ttu-id="80ef1-115">On an exact region of code.</span><span class="sxs-lookup"><span data-stu-id="80ef1-115">On an exact region of code.</span></span>  |  
| [<span data-ttu-id="80ef1-116">Conditional line-of-code</span><span class="sxs-lookup"><span data-stu-id="80ef1-116">Conditional line-of-code</span></span>](#conditional-line-of-code-breakpoints) | <span data-ttu-id="80ef1-117">On an exact region of code, but only when some other condition is true.</span><span class="sxs-lookup"><span data-stu-id="80ef1-117">On an exact region of code, but only when some other condition is true.</span></span>  |  
| [<span data-ttu-id="80ef1-118">DOM</span><span class="sxs-lookup"><span data-stu-id="80ef1-118">DOM</span></span>](#dom-change-breakpoints) | <span data-ttu-id="80ef1-119">On the code that changes or removes a specific DOM node, or the children.</span><span class="sxs-lookup"><span data-stu-id="80ef1-119">On the code that changes or removes a specific DOM node, or the children.</span></span>  |  
| [<span data-ttu-id="80ef1-120">XHR</span><span class="sxs-lookup"><span data-stu-id="80ef1-120">XHR</span></span>](#xhrfetch-breakpoints) | <span data-ttu-id="80ef1-121">When an XHR URL contains a string pattern.</span><span class="sxs-lookup"><span data-stu-id="80ef1-121">When an XHR URL contains a string pattern.</span></span>  |  
| [<span data-ttu-id="80ef1-122">Event listener</span><span class="sxs-lookup"><span data-stu-id="80ef1-122">Event listener</span></span>](#event-listener-breakpoints) | <span data-ttu-id="80ef1-123">On the code that runs after an event, such as `click`, runs.</span><span class="sxs-lookup"><span data-stu-id="80ef1-123">On the code that runs after an event, such as `click`, runs.</span></span>  |  
| [<span data-ttu-id="80ef1-124">Exception</span><span class="sxs-lookup"><span data-stu-id="80ef1-124">Exception</span></span>](#exception-breakpoints) | <span data-ttu-id="80ef1-125">On the line of code that is throwing a caught or uncaught exception.</span><span class="sxs-lookup"><span data-stu-id="80ef1-125">On the line of code that is throwing a caught or uncaught exception.</span></span>  |  
| [<span data-ttu-id="80ef1-126">Function</span><span class="sxs-lookup"><span data-stu-id="80ef1-126">Function</span></span>](#function-breakpoints) | <span data-ttu-id="80ef1-127">Whenever a specific command, function, or method is run.</span><span class="sxs-lookup"><span data-stu-id="80ef1-127">Whenever a specific command, function, or method is run.</span></span>  |  

## <span data-ttu-id="80ef1-128">Line-of-code breakpoints</span><span class="sxs-lookup"><span data-stu-id="80ef1-128">Line-of-code breakpoints</span></span>   

<span data-ttu-id="80ef1-129">Use a line-of-code breakpoint when you know the exact region of code that you need to investigate.</span><span class="sxs-lookup"><span data-stu-id="80ef1-129">Use a line-of-code breakpoint when you know the exact region of code that you need to investigate.</span></span>  <span data-ttu-id="80ef1-130">DevTools always pauses before this line of code is run.</span><span class="sxs-lookup"><span data-stu-id="80ef1-130">DevTools always pauses before this line of code is run.</span></span>  

<span data-ttu-id="80ef1-131">To set a line-of-code breakpoint in DevTools:</span><span class="sxs-lookup"><span data-stu-id="80ef1-131">To set a line-of-code breakpoint in DevTools:</span></span>  

1.  <span data-ttu-id="80ef1-132">Click the **Sources** tab.</span><span class="sxs-lookup"><span data-stu-id="80ef1-132">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="80ef1-133">Open the file containing the line of code on which you want to break.</span><span class="sxs-lookup"><span data-stu-id="80ef1-133">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="80ef1-134">Go the line of code.</span><span class="sxs-lookup"><span data-stu-id="80ef1-134">Go the line of code.</span></span>  
1.  <span data-ttu-id="80ef1-135">To the left of the line of code is the line number column.</span><span class="sxs-lookup"><span data-stu-id="80ef1-135">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="80ef1-136">Click on it.</span><span class="sxs-lookup"><span data-stu-id="80ef1-136">Click on it.</span></span>  <span data-ttu-id="80ef1-137">A red icon appears next to the line number column.</span><span class="sxs-lookup"><span data-stu-id="80ef1-137">A red icon appears next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="A line-of-code breakpoint" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       <span data-ttu-id="80ef1-139">A line-of-code breakpoint</span><span class="sxs-lookup"><span data-stu-id="80ef1-139">A line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="80ef1-140">Line-of-code breakpoints in your code</span><span class="sxs-lookup"><span data-stu-id="80ef1-140">Line-of-code breakpoints in your code</span></span>   

<span data-ttu-id="80ef1-141">Run the `debugger` method from your code to pause on that line.</span><span class="sxs-lookup"><span data-stu-id="80ef1-141">Run the `debugger` method from your code to pause on that line.</span></span>  <span data-ttu-id="80ef1-142">This is equivalent to a [line-of-code breakpoint](#line-of-code-breakpoints), except that the breakpoint is set in your code, not in the DevTools UI.</span><span class="sxs-lookup"><span data-stu-id="80ef1-142">This is equivalent to a [line-of-code breakpoint](#line-of-code-breakpoints), except that the breakpoint is set in your code, not in the DevTools UI.</span></span>  

```javascript
console.log('a');
console.log('b');
debugger;
console.log('c');
```  

### <span data-ttu-id="80ef1-143">Conditional line-of-code breakpoints</span><span class="sxs-lookup"><span data-stu-id="80ef1-143">Conditional line-of-code breakpoints</span></span>   

<span data-ttu-id="80ef1-144">Use a conditional line-of-code breakpoint when you know the exact region of code that you need to investigate, but you want to pause only when some other condition is true.</span><span class="sxs-lookup"><span data-stu-id="80ef1-144">Use a conditional line-of-code breakpoint when you know the exact region of code that you need to investigate, but you want to pause only when some other condition is true.</span></span>  

<span data-ttu-id="80ef1-145">To set a conditional line-of-code breakpoint:</span><span class="sxs-lookup"><span data-stu-id="80ef1-145">To set a conditional line-of-code breakpoint:</span></span>  

1.  <span data-ttu-id="80ef1-146">Click the **Sources** tab.</span><span class="sxs-lookup"><span data-stu-id="80ef1-146">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="80ef1-147">Open the file containing the line of code on which you want to break.</span><span class="sxs-lookup"><span data-stu-id="80ef1-147">Open the file containing the line of code on which you want to break.</span></span>  
1.  <span data-ttu-id="80ef1-148">Go the line of code.</span><span class="sxs-lookup"><span data-stu-id="80ef1-148">Go the line of code.</span></span>  
1.  <span data-ttu-id="80ef1-149">To the left of the line of code is the line number column.</span><span class="sxs-lookup"><span data-stu-id="80ef1-149">To the left of the line of code is the line number column.</span></span>  <span data-ttu-id="80ef1-150">Right-click the line number.</span><span class="sxs-lookup"><span data-stu-id="80ef1-150">Right-click the line number.</span></span>  
1.  <span data-ttu-id="80ef1-151">Select **Add conditional breakpoint**.</span><span class="sxs-lookup"><span data-stu-id="80ef1-151">Select **Add conditional breakpoint**.</span></span>  <span data-ttu-id="80ef1-152">A dialog displays underneath the line of code.</span><span class="sxs-lookup"><span data-stu-id="80ef1-152">A dialog displays underneath the line of code.</span></span>  
1.  <span data-ttu-id="80ef1-153">Enter your condition in the dialog.</span><span class="sxs-lookup"><span data-stu-id="80ef1-153">Enter your condition in the dialog.</span></span>  
1.  <span data-ttu-id="80ef1-154">Press `Enter` to activate the breakpoint.</span><span class="sxs-lookup"><span data-stu-id="80ef1-154">Press `Enter` to activate the breakpoint.</span></span>  <span data-ttu-id="80ef1-155">An icon next to the line number column.</span><span class="sxs-lookup"><span data-stu-id="80ef1-155">An icon next to the line number column.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-conditional-breakpoint.msft.png" alt-text="A line-of-code breakpoint" lightbox="../media/javascript-sources-page-js-conditional-breakpoint.msft.png":::
       <span data-ttu-id="80ef1-157">A conditional line-of-code breakpoint</span><span class="sxs-lookup"><span data-stu-id="80ef1-157">A conditional line-of-code breakpoint</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="80ef1-158">Manage line-of-code breakpoints</span><span class="sxs-lookup"><span data-stu-id="80ef1-158">Manage line-of-code breakpoints</span></span>   

<span data-ttu-id="80ef1-159">Use the **Breakpoints** pane to disable or remove line-of-code breakpoints from a single location.</span><span class="sxs-lookup"><span data-stu-id="80ef1-159">Use the **Breakpoints** pane to disable or remove line-of-code breakpoints from a single location.</span></span>  

:::image type="complex" source="../media/javascript-sources-page-js-breakpoints-16-33.msft.png" alt-text="A line-of-code breakpoint" lightbox="../media/javascript-sources-page-js-breakpoints-16-33.msft.png":::
   <span data-ttu-id="80ef1-161">The **Breakpoints** panel</span><span class="sxs-lookup"><span data-stu-id="80ef1-161">The **Breakpoints** panel</span></span>  
:::image-end:::  

*   <span data-ttu-id="80ef1-162">Check the checkbox next to an entry to disable that breakpoint.</span><span class="sxs-lookup"><span data-stu-id="80ef1-162">Check the checkbox next to an entry to disable that breakpoint.</span></span>  
*   <span data-ttu-id="80ef1-163">Right-click an entry to remove that breakpoint.</span><span class="sxs-lookup"><span data-stu-id="80ef1-163">Right-click an entry to remove that breakpoint.</span></span>  
*   <span data-ttu-id="80ef1-164">Right-click anywhere in the **Breakpoints** pane to deactivate all breakpoints, disable all breakpoints, or remove all breakpoints.</span><span class="sxs-lookup"><span data-stu-id="80ef1-164">Right-click anywhere in the **Breakpoints** pane to deactivate all breakpoints, disable all breakpoints, or remove all breakpoints.</span></span>  <span data-ttu-id="80ef1-165">Disabling all breakpoints is equivalent to unchecking each one.</span><span class="sxs-lookup"><span data-stu-id="80ef1-165">Disabling all breakpoints is equivalent to unchecking each one.</span></span>  <span data-ttu-id="80ef1-166">Deactivating all breakpoints instructs DevTools to ignore all line-of-code breakpoints, but to also maintain the enabled state so that each are in the same state as before when you reactivate each one.</span><span class="sxs-lookup"><span data-stu-id="80ef1-166">Deactivating all breakpoints instructs DevTools to ignore all line-of-code breakpoints, but to also maintain the enabled state so that each are in the same state as before when you reactivate each one.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png" alt-text="A line-of-code breakpoint" lightbox="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png":::
       <span data-ttu-id="80ef1-168">Deactivated breakpoints in the **Breakpoints** pane</span><span class="sxs-lookup"><span data-stu-id="80ef1-168">Deactivated breakpoints in the **Breakpoints** pane</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="80ef1-169">DOM change breakpoints</span><span class="sxs-lookup"><span data-stu-id="80ef1-169">DOM change breakpoints</span></span>   

<span data-ttu-id="80ef1-170">Use a DOM change breakpoint when you want to pause on the code that changes a DOM node or the children.</span><span class="sxs-lookup"><span data-stu-id="80ef1-170">Use a DOM change breakpoint when you want to pause on the code that changes a DOM node or the children.</span></span>  

<span data-ttu-id="80ef1-171">To set a DOM change breakpoint:</span><span class="sxs-lookup"><span data-stu-id="80ef1-171">To set a DOM change breakpoint:</span></span>  

1.  <span data-ttu-id="80ef1-172">Click the **Elements** tab.</span><span class="sxs-lookup"><span data-stu-id="80ef1-172">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="80ef1-173">Go the element on which you want to set the breakpoint.</span><span class="sxs-lookup"><span data-stu-id="80ef1-173">Go the element on which you want to set the breakpoint.</span></span>  
1.  <span data-ttu-id="80ef1-174">Right-click the element.</span><span class="sxs-lookup"><span data-stu-id="80ef1-174">Right-click the element.</span></span>  
1.  <span data-ttu-id="80ef1-175">Hover over **Break on**, then select **Subtree modifications**, **Attribute modifications**, or **Node removal**.</span><span class="sxs-lookup"><span data-stu-id="80ef1-175">Hover over **Break on**, then select **Subtree modifications**, **Attribute modifications**, or **Node removal**.</span></span>  
    
    :::image type="complex" source="../media/javascript-elements-break-on-subtree-modifications.msft.png" alt-text="A line-of-code breakpoint" lightbox="../media/javascript-elements-break-on-subtree-modifications.msft.png":::
       <span data-ttu-id="80ef1-177">The context menu for creating a DOM change breakpoint</span><span class="sxs-lookup"><span data-stu-id="80ef1-177">The context menu for creating a DOM change breakpoint</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="80ef1-178">Types of DOM change breakpoints</span><span class="sxs-lookup"><span data-stu-id="80ef1-178">Types of DOM change breakpoints</span></span>   

*   <span data-ttu-id="80ef1-179">**Subtree modifications**.</span><span class="sxs-lookup"><span data-stu-id="80ef1-179">**Subtree modifications**.</span></span>  <span data-ttu-id="80ef1-180">Triggered when a child of the currently-selected node is removed or added, or the contents of a child are changed.</span><span class="sxs-lookup"><span data-stu-id="80ef1-180">Triggered when a child of the currently-selected node is removed or added, or the contents of a child are changed.</span></span>  <span data-ttu-id="80ef1-181">Not triggered on child node attribute changes, or on any changes to the currently-selected node.</span><span class="sxs-lookup"><span data-stu-id="80ef1-181">Not triggered on child node attribute changes, or on any changes to the currently-selected node.</span></span>  
*   <span data-ttu-id="80ef1-182">**Attributes modifications**: Triggered when an attribute is added or removed on the currently-selected node, or when an attribute value changes.</span><span class="sxs-lookup"><span data-stu-id="80ef1-182">**Attributes modifications**: Triggered when an attribute is added or removed on the currently-selected node, or when an attribute value changes.</span></span>  
*   <span data-ttu-id="80ef1-183">**Node Removal**: Triggered when the currently-selected node is removed.</span><span class="sxs-lookup"><span data-stu-id="80ef1-183">**Node Removal**: Triggered when the currently-selected node is removed.</span></span>  
    
## <span data-ttu-id="80ef1-184">XHR/Fetch breakpoints</span><span class="sxs-lookup"><span data-stu-id="80ef1-184">XHR/Fetch breakpoints</span></span>   

<span data-ttu-id="80ef1-185">Use an XHR breakpoint when you want to break when the request URL of an XHR contains a specified string.</span><span class="sxs-lookup"><span data-stu-id="80ef1-185">Use an XHR breakpoint when you want to break when the request URL of an XHR contains a specified string.</span></span>  <span data-ttu-id="80ef1-186">DevTools pauses on the line of code where the XHR runs the `send()` method.</span><span class="sxs-lookup"><span data-stu-id="80ef1-186">DevTools pauses on the line of code where the XHR runs the `send()` method.</span></span>  

> [!NOTE]
> <span data-ttu-id="80ef1-187">This feature also works with [Fetch API][MDNFetchApi] requests.</span><span class="sxs-lookup"><span data-stu-id="80ef1-187">This feature also works with [Fetch API][MDNFetchApi] requests.</span></span>  

<span data-ttu-id="80ef1-188">One example of when this is helpful is when you see that your page is requesting an incorrect URL, and you want to quickly find the AJAX or Fetch source code that is causing the incorrect request.</span><span class="sxs-lookup"><span data-stu-id="80ef1-188">One example of when this is helpful is when you see that your page is requesting an incorrect URL, and you want to quickly find the AJAX or Fetch source code that is causing the incorrect request.</span></span>  

<span data-ttu-id="80ef1-189">To set an XHR breakpoint:</span><span class="sxs-lookup"><span data-stu-id="80ef1-189">To set an XHR breakpoint:</span></span>  

1.  <span data-ttu-id="80ef1-190">Click the **Sources** tab.</span><span class="sxs-lookup"><span data-stu-id="80ef1-190">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="80ef1-191">Expand the **XHR Breakpoints** pane.</span><span class="sxs-lookup"><span data-stu-id="80ef1-191">Expand the **XHR Breakpoints** pane.</span></span>  
1.  <span data-ttu-id="80ef1-192">Click **Add breakpoint**.</span><span class="sxs-lookup"><span data-stu-id="80ef1-192">Click **Add breakpoint**.</span></span>  
1.  <span data-ttu-id="80ef1-193">Enter the string which you want to break on.</span><span class="sxs-lookup"><span data-stu-id="80ef1-193">Enter the string which you want to break on.</span></span>  <span data-ttu-id="80ef1-194">DevTools pauses when this string is present anywhere in an XHR request URL.</span><span class="sxs-lookup"><span data-stu-id="80ef1-194">DevTools pauses when this string is present anywhere in an XHR request URL.</span></span>  
1.  <span data-ttu-id="80ef1-195">Press `Enter` to confirm.</span><span class="sxs-lookup"><span data-stu-id="80ef1-195">Press `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png" alt-text="A line-of-code breakpoint" lightbox="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png":::
       <span data-ttu-id="80ef1-197">Create an XHR breakpoint</span><span class="sxs-lookup"><span data-stu-id="80ef1-197">Create an XHR breakpoint</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="80ef1-198">Event listener breakpoints</span><span class="sxs-lookup"><span data-stu-id="80ef1-198">Event listener breakpoints</span></span> 

<span data-ttu-id="80ef1-199">Use event listener breakpoints when you want to pause on the event listener code that runs after an event is fired.</span><span class="sxs-lookup"><span data-stu-id="80ef1-199">Use event listener breakpoints when you want to pause on the event listener code that runs after an event is fired.</span></span>  <span data-ttu-id="80ef1-200">You are able to select specific events, such as `click`, or categories of events, such as all mouse events.</span><span class="sxs-lookup"><span data-stu-id="80ef1-200">You are able to select specific events, such as `click`, or categories of events, such as all mouse events.</span></span>  

1.  <span data-ttu-id="80ef1-201">Click the **Sources** tab.</span><span class="sxs-lookup"><span data-stu-id="80ef1-201">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="80ef1-202">Expand the **Event Listener Breakpoints** pane.</span><span class="sxs-lookup"><span data-stu-id="80ef1-202">Expand the **Event Listener Breakpoints** pane.</span></span>  <span data-ttu-id="80ef1-203">DevTools shows a list of event categories, such as **Animation**.</span><span class="sxs-lookup"><span data-stu-id="80ef1-203">DevTools shows a list of event categories, such as **Animation**.</span></span>  
1.  <span data-ttu-id="80ef1-204">Check one of these categories to pause whenever any event from that category is fired, or expand the category and check a specific event.</span><span class="sxs-lookup"><span data-stu-id="80ef1-204">Check one of these categories to pause whenever any event from that category is fired, or expand the category and check a specific event.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png" alt-text="A line-of-code breakpoint" lightbox="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png":::
       <span data-ttu-id="80ef1-206">Create an event listener breakpoint</span><span class="sxs-lookup"><span data-stu-id="80ef1-206">Create an event listener breakpoint</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="80ef1-207">Exception breakpoints</span><span class="sxs-lookup"><span data-stu-id="80ef1-207">Exception breakpoints</span></span>   

<span data-ttu-id="80ef1-208">Use exception breakpoints when you want to pause on the line of code that is throwing a caught or uncaught exception.</span><span class="sxs-lookup"><span data-stu-id="80ef1-208">Use exception breakpoints when you want to pause on the line of code that is throwing a caught or uncaught exception.</span></span>  

1.  <span data-ttu-id="80ef1-209">Click the **Sources** tab.</span><span class="sxs-lookup"><span data-stu-id="80ef1-209">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="80ef1-210">Click **Pause on exceptions** \(![Pause on exceptions][ImagePauseOnExceptionsIcon]\).</span><span class="sxs-lookup"><span data-stu-id="80ef1-210">Click **Pause on exceptions** \(![Pause on exceptions][ImagePauseOnExceptionsIcon]\).</span></span>  <span data-ttu-id="80ef1-211">The icon turns blue when enabled.</span><span class="sxs-lookup"><span data-stu-id="80ef1-211">The icon turns blue when enabled.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-pause-on-exceptions.msft.png" alt-text="A line-of-code breakpoint" lightbox="../media/javascript-sources-page-js-pause-on-exceptions.msft.png":::
       <span data-ttu-id="80ef1-213">The **Pause on exceptions** button</span><span class="sxs-lookup"><span data-stu-id="80ef1-213">The **Pause on exceptions** button</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="80ef1-214">**Optional**.</span><span class="sxs-lookup"><span data-stu-id="80ef1-214">**Optional**.</span></span>  <span data-ttu-id="80ef1-215">Check the **Pause On Caught Exceptions** checkbox if you also want to pause on caught exceptions, in addition to uncaught ones.</span><span class="sxs-lookup"><span data-stu-id="80ef1-215">Check the **Pause On Caught Exceptions** checkbox if you also want to pause on caught exceptions, in addition to uncaught ones.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-js-paused-on-exception.msft.png" alt-text="A line-of-code breakpoint" lightbox="../media/javascript-sources-page-js-paused-on-exception.msft.png":::
       <span data-ttu-id="80ef1-217">Paused on an uncaught exception</span><span class="sxs-lookup"><span data-stu-id="80ef1-217">Paused on an uncaught exception</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="80ef1-218">Function breakpoints</span><span class="sxs-lookup"><span data-stu-id="80ef1-218">Function breakpoints</span></span>   

<span data-ttu-id="80ef1-219">Run the `debug(method)` method, where `method` is the command, function, or method you want to debug, when you want to pause whenever a specific function is run.</span><span class="sxs-lookup"><span data-stu-id="80ef1-219">Run the `debug(method)` method, where `method` is the command, function, or method you want to debug, when you want to pause whenever a specific function is run.</span></span>  <span data-ttu-id="80ef1-220">You may insert `debug()` into your code (like a `console.log()` statement) or run the method from the DevTools Console.</span><span class="sxs-lookup"><span data-stu-id="80ef1-220">You may insert `debug()` into your code (like a `console.log()` statement) or run the method from the DevTools Console.</span></span>  `debug()` <span data-ttu-id="80ef1-221">is equivalent to setting a [line-of-code breakpoint](#line-of-code-breakpoints) on the first line of the function.</span><span class="sxs-lookup"><span data-stu-id="80ef1-221">is equivalent to setting a [line-of-code breakpoint](#line-of-code-breakpoints) on the first line of the function.</span></span>  

```javascript
function sum(a, b) {
    let result = a + b; // DevTools pauses on this line.
    return result;
}
debug(sum); // Pass the function object, not a string.
sum();
```  

### <span data-ttu-id="80ef1-222">Make sure the target function is in scope</span><span class="sxs-lookup"><span data-stu-id="80ef1-222">Make sure the target function is in scope</span></span>   

<span data-ttu-id="80ef1-223">DevTools throws a `ReferenceError` if the function you want to debug is not in scope.</span><span class="sxs-lookup"><span data-stu-id="80ef1-223">DevTools throws a `ReferenceError` if the function you want to debug is not in scope.</span></span>  

```javascript
(function () {
    function hey() {
        console.log('hey');
    }
    function yo() {
        console.log('yo');
    }
    debug(yo); // This works.
    yo();
})();
debug(hey); // This does not work.  hey() is out of scope.
```  

<span data-ttu-id="80ef1-224">Ensuring the target function is in scope is tricky if you are running the `debug()` method from the DevTools Console.</span><span class="sxs-lookup"><span data-stu-id="80ef1-224">Ensuring the target function is in scope is tricky if you are running the `debug()` method from the DevTools Console.</span></span>  <span data-ttu-id="80ef1-225">Here is one strategy:</span><span class="sxs-lookup"><span data-stu-id="80ef1-225">Here is one strategy:</span></span>  

1.  <span data-ttu-id="80ef1-226">Set a [line-of-code breakpoint](#line-of-code-breakpoints) somewhere where the function is in scope.</span><span class="sxs-lookup"><span data-stu-id="80ef1-226">Set a [line-of-code breakpoint](#line-of-code-breakpoints) somewhere where the function is in scope.</span></span>
1.  <span data-ttu-id="80ef1-227">Trigger the breakpoint.</span><span class="sxs-lookup"><span data-stu-id="80ef1-227">Trigger the breakpoint.</span></span>  
1.  <span data-ttu-id="80ef1-228">Run the `debug()` method in the DevTools Console while the code is still paused on your line-of-code breakpoint.</span><span class="sxs-lookup"><span data-stu-id="80ef1-228">Run the `debug()` method in the DevTools Console while the code is still paused on your line-of-code breakpoint.</span></span>  
    
<!---  
 


-->  

<!-- image links -->  

[ImagePauseOnExceptionsIcon]: ../media/pause-on-exceptions-icon.msft.png  

<!-- links -->  

[DevtoolsJavascriptIndex]: index.md "Get started with debugging JavaScript in Microsoft Edge DevTools | Microsoft Docs"  

[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "Fetch API | MDN"  

> [!NOTE]
> <span data-ttu-id="80ef1-231">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="80ef1-231">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="80ef1-232">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="80ef1-232">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="80ef1-234">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="80ef1-234">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
