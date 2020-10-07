---
description: A guide on navigating Microsoft Edge DevTools using assistive technology like screen readers.
title: Navigate Microsoft Edge DevTools with assistive technology
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 9a9accd043d05d1c55b1e79ce580f7b45711118f
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993189"
---
<!-- Copyright Rob Dodson 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <span data-ttu-id="63b0c-104">Navigate Microsoft Edge DevTools with assistive technology</span><span class="sxs-lookup"><span data-stu-id="63b0c-104">Navigate Microsoft Edge DevTools with assistive technology</span></span>  

<span data-ttu-id="63b0c-105">The following article aims to help users who primarily rely on assistive technology like screen readers access and use [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain].</span><span class="sxs-lookup"><span data-stu-id="63b0c-105">The following article aims to help users who primarily rely on assistive technology like screen readers access and use [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain].</span></span>  <span data-ttu-id="63b0c-106">[Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain] is a suite of web developer tools built into the Microsoft Edge browser.</span><span class="sxs-lookup"><span data-stu-id="63b0c-106">[Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain] is a suite of web developer tools built into the Microsoft Edge browser.</span></span>  <span data-ttu-id="63b0c-107">If you are looking for DevTools features related to improving the accessibility of a web page,  see [Accessibility Reference][DevtoolsAccessibilityReference].</span><span class="sxs-lookup"><span data-stu-id="63b0c-107">If you are looking for DevTools features related to improving the accessibility of a web page,  see [Accessibility Reference][DevtoolsAccessibilityReference].</span></span>  

<span data-ttu-id="63b0c-108">The accessibility of DevTools is a work-in-progress.</span><span class="sxs-lookup"><span data-stu-id="63b0c-108">The accessibility of DevTools is a work-in-progress.</span></span>  <span data-ttu-id="63b0c-109">Some panels and tabs work better with assistive technology than others.</span><span class="sxs-lookup"><span data-stu-id="63b0c-109">Some panels and tabs work better with assistive technology than others.</span></span>  <span data-ttu-id="63b0c-110">This guide walks you through the panels which are the most accessible and highlights specific issues you may encounter along the way.</span><span class="sxs-lookup"><span data-stu-id="63b0c-110">This guide walks you through the panels which are the most accessible and highlights specific issues you may encounter along the way.</span></span>  

## <span data-ttu-id="63b0c-111">Overview</span><span class="sxs-lookup"><span data-stu-id="63b0c-111">Overview</span></span>  

<span data-ttu-id="63b0c-112">Before starting, it helps to have a mental model of how the DevTools UI is structured.</span><span class="sxs-lookup"><span data-stu-id="63b0c-112">Before starting, it helps to have a mental model of how the DevTools UI is structured.</span></span>  <span data-ttu-id="63b0c-113">DevTools is divided into a series of panels which are organized into an [ARIA tablist][W3CWaiAriaTablist].</span><span class="sxs-lookup"><span data-stu-id="63b0c-113">DevTools is divided into a series of panels which are organized into an [ARIA tablist][W3CWaiAriaTablist].</span></span>  

<span data-ttu-id="63b0c-114">For example:</span><span class="sxs-lookup"><span data-stu-id="63b0c-114">For example:</span></span>  

*   <span data-ttu-id="63b0c-115">The **Elements** panel lets you [view and change DOM nodes][DevtoolsDomIndexNavigateDomTreeKeyboard] or [CSS][DevtoolsCssIndex].</span><span class="sxs-lookup"><span data-stu-id="63b0c-115">The **Elements** panel lets you [view and change DOM nodes][DevtoolsDomIndexNavigateDomTreeKeyboard] or [CSS][DevtoolsCssIndex].</span></span>  
*   <span data-ttu-id="63b0c-116">The [Console panel][DevtoolsConsoleIndex] lets you read JavaScript logs and live edit objects.</span><span class="sxs-lookup"><span data-stu-id="63b0c-116">The [Console panel][DevtoolsConsoleIndex] lets you read JavaScript logs and live edit objects.</span></span>  

<span data-ttu-id="63b0c-117">Within the content area of each panel, there are a number of different tools, often referred to as tabs or panes in the documentation.</span><span class="sxs-lookup"><span data-stu-id="63b0c-117">Within the content area of each panel, there are a number of different tools, often referred to as tabs or panes in the documentation.</span></span>  
<span data-ttu-id="63b0c-118">For instance, the **Elements** panel contains additional tabs to inspect event listeners, the accessibility tree, and much more.</span><span class="sxs-lookup"><span data-stu-id="63b0c-118">For instance, the **Elements** panel contains additional tabs to inspect event listeners, the accessibility tree, and much more.</span></span>  <span data-ttu-id="63b0c-119">The distinction between tabs and panes is somewhat arbitrary.</span><span class="sxs-lookup"><span data-stu-id="63b0c-119">The distinction between tabs and panes is somewhat arbitrary.</span></span>  <span data-ttu-id="63b0c-120">The only reason you may see one term or the other is to maintain consistency with the rest of the official DevTools documentation.</span><span class="sxs-lookup"><span data-stu-id="63b0c-120">The only reason you may see one term or the other is to maintain consistency with the rest of the official DevTools documentation.</span></span>  

## <span data-ttu-id="63b0c-121">Keyboard shortcuts</span><span class="sxs-lookup"><span data-stu-id="63b0c-121">Keyboard shortcuts</span></span>  

<span data-ttu-id="63b0c-122">The [DevTools Keyboard Shortcuts reference][DevtoolsShortcuts] is a helpful cheatsheet.</span><span class="sxs-lookup"><span data-stu-id="63b0c-122">The [DevTools Keyboard Shortcuts reference][DevtoolsShortcuts] is a helpful cheatsheet.</span></span>  <span data-ttu-id="63b0c-123">Be sure to bookmark it and refer back to it as you explore the different panels.</span><span class="sxs-lookup"><span data-stu-id="63b0c-123">Be sure to bookmark it and refer back to it as you explore the different panels.</span></span>  

## <span data-ttu-id="63b0c-124">Open DevTools</span><span class="sxs-lookup"><span data-stu-id="63b0c-124">Open DevTools</span></span>  

<span data-ttu-id="63b0c-125">To get started, see [Open Microsoft Edge DevTools][DevtoolsOpen].</span><span class="sxs-lookup"><span data-stu-id="63b0c-125">To get started, see [Open Microsoft Edge DevTools][DevtoolsOpen].</span></span>  <span data-ttu-id="63b0c-126">There are a number of ways to open DevTools, either through keyboard shortcuts or menu items.</span><span class="sxs-lookup"><span data-stu-id="63b0c-126">There are a number of ways to open DevTools, either through keyboard shortcuts or menu items.</span></span>  

## <span data-ttu-id="63b0c-127">Navigate between panels</span><span class="sxs-lookup"><span data-stu-id="63b0c-127">Navigate between panels</span></span>  

### <span data-ttu-id="63b0c-128">Navigate by keyboard</span><span class="sxs-lookup"><span data-stu-id="63b0c-128">Navigate by keyboard</span></span>  

*   <span data-ttu-id="63b0c-129">With DevTools open, select `Control`+`]` \(Windows\) or `Command`+`]` \(macOS\) to focus the next panel.</span><span class="sxs-lookup"><span data-stu-id="63b0c-129">With DevTools open, select `Control`+`]` \(Windows\) or `Command`+`]` \(macOS\) to focus the next panel.</span></span>  
*   <span data-ttu-id="63b0c-130">Select `Control`+`[` \(Windows\) or `Command`+`[` \(macOS\) to focus the previous panel.</span><span class="sxs-lookup"><span data-stu-id="63b0c-130">Select `Control`+`[` \(Windows\) or `Command`+`[` \(macOS\) to focus the previous panel.</span></span>  
*   <span data-ttu-id="63b0c-131">It is also possible to use `Shift`+`Tab` to move focus into the [ARIA tablist][W3CWaiAriaTablist] of a panel and use the arrow keys to change panels, though it may be faster to use the previously mentioned shortcuts.</span><span class="sxs-lookup"><span data-stu-id="63b0c-131">It is also possible to use `Shift`+`Tab` to move focus into the [ARIA tablist][W3CWaiAriaTablist] of a panel and use the arrow keys to change panels, though it may be faster to use the previously mentioned shortcuts.</span></span>  

**<span data-ttu-id="63b0c-132">Known issues</span><span class="sxs-lookup"><span data-stu-id="63b0c-132">Known issues</span></span>**  

*   <span data-ttu-id="63b0c-133">Some panels, such as the **Console** and **Performance** panels, may move focus into the panel content area as soon as each panel is activated.</span><span class="sxs-lookup"><span data-stu-id="63b0c-133">Some panels, such as the **Console** and **Performance** panels, may move focus into the panel content area as soon as each panel is activated.</span></span>  <span data-ttu-id="63b0c-134">This may make navigating by arrow keys difficult.</span><span class="sxs-lookup"><span data-stu-id="63b0c-134">This may make navigating by arrow keys difficult.</span></span>  
*   <span data-ttu-id="63b0c-135">The name of the selected panel is announced, but only after it has read the focused content in the panel.</span><span class="sxs-lookup"><span data-stu-id="63b0c-135">The name of the selected panel is announced, but only after it has read the focused content in the panel.</span></span>  <span data-ttu-id="63b0c-136">This may make it very easy to miss.</span><span class="sxs-lookup"><span data-stu-id="63b0c-136">This may make it very easy to miss.</span></span>  

### <span data-ttu-id="63b0c-137">Navigate by Command Menu</span><span class="sxs-lookup"><span data-stu-id="63b0c-137">Navigate by Command Menu</span></span>  

<span data-ttu-id="63b0c-138">To focus a specific panel, use the [Command Menu][DevtoolsCommandMenuIndex]:</span><span class="sxs-lookup"><span data-stu-id="63b0c-138">To focus a specific panel, use the [Command Menu][DevtoolsCommandMenuIndex]:</span></span>  

1.  <span data-ttu-id="63b0c-139">With DevTools open, select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span><span class="sxs-lookup"><span data-stu-id="63b0c-139">With DevTools open, select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    <span data-ttu-id="63b0c-140">The **Command Menu** is a fuzzy search autocomplete combobox.</span><span class="sxs-lookup"><span data-stu-id="63b0c-140">The **Command Menu** is a fuzzy search autocomplete combobox.</span></span>  
1.  <span data-ttu-id="63b0c-141">Type the name of the panel you want to open, then use the `Down Arrow` on the keyboard to navigate to the correct option.</span><span class="sxs-lookup"><span data-stu-id="63b0c-141">Type the name of the panel you want to open, then use the `Down Arrow` on the keyboard to navigate to the correct option.</span></span>  
1.  <span data-ttu-id="63b0c-142">Select `Enter` to run a command.</span><span class="sxs-lookup"><span data-stu-id="63b0c-142">Select `Enter` to run a command.</span></span>  

<span data-ttu-id="63b0c-143">Complete the following actions to open the **Elements** panel.</span><span class="sxs-lookup"><span data-stu-id="63b0c-143">Complete the following actions to open the **Elements** panel.</span></span>  

1.  <span data-ttu-id="63b0c-144">Open the **Command Menu**.</span><span class="sxs-lookup"><span data-stu-id="63b0c-144">Open the **Command Menu**.</span></span>  
1.  <span data-ttu-id="63b0c-145">Type `E` then `L`.</span><span class="sxs-lookup"><span data-stu-id="63b0c-145">Type `E` then `L`.</span></span>  <span data-ttu-id="63b0c-146">The **Panel > Show Elements** option is selected.</span><span class="sxs-lookup"><span data-stu-id="63b0c-146">The **Panel > Show Elements** option is selected.</span></span>  
1.  <span data-ttu-id="63b0c-147">Select `Enter` to run the command that opens the panel.</span><span class="sxs-lookup"><span data-stu-id="63b0c-147">Select `Enter` to run the command that opens the panel.</span></span>  

<span data-ttu-id="63b0c-148">Open a panel this way directs focus to the contents of the panel.</span><span class="sxs-lookup"><span data-stu-id="63b0c-148">Open a panel this way directs focus to the contents of the panel.</span></span>  <span data-ttu-id="63b0c-149">In the case of the **Elements** panel, focus moves into the **DOM Tree**.</span><span class="sxs-lookup"><span data-stu-id="63b0c-149">In the case of the **Elements** panel, focus moves into the **DOM Tree**.</span></span>  

## <span data-ttu-id="63b0c-150">Elements panel</span><span class="sxs-lookup"><span data-stu-id="63b0c-150">Elements panel</span></span>  

### <span data-ttu-id="63b0c-151">Inspect an element on the page</span><span class="sxs-lookup"><span data-stu-id="63b0c-151">Inspect an element on the page</span></span>  

1.  <span data-ttu-id="63b0c-152">Navigate to the element you want to inspect using the cursor in the screen reader.</span><span class="sxs-lookup"><span data-stu-id="63b0c-152">Navigate to the element you want to inspect using the cursor in the screen reader.</span></span>  
1.  <span data-ttu-id="63b0c-153">Simulate a right-click using a mouse on the element to open the context menu.</span><span class="sxs-lookup"><span data-stu-id="63b0c-153">Simulate a right-click using a mouse on the element to open the context menu.</span></span>  
1.  <span data-ttu-id="63b0c-154">Choose the **Inspect** option.</span><span class="sxs-lookup"><span data-stu-id="63b0c-154">Choose the **Inspect** option.</span></span>  <span data-ttu-id="63b0c-155">This [opens the Elements panel and focuses the element in the DOM Tree][DevtoolsDomIndexViewDomNodes].</span><span class="sxs-lookup"><span data-stu-id="63b0c-155">This [opens the Elements panel and focuses the element in the DOM Tree][DevtoolsDomIndexViewDomNodes].</span></span>  

<span data-ttu-id="63b0c-156">The **DOM Tree** is laid out as an [ARIA tree][W3CWaiAriaTree].</span><span class="sxs-lookup"><span data-stu-id="63b0c-156">The **DOM Tree** is laid out as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="63b0c-157">For an example, see [Navigate the **DOM Tree** with a keyboard][DevtoolsDomIndexNavigateDomTreeKeyboard].</span><span class="sxs-lookup"><span data-stu-id="63b0c-157">For an example, see [Navigate the **DOM Tree** with a keyboard][DevtoolsDomIndexNavigateDomTreeKeyboard].</span></span>  

### <span data-ttu-id="63b0c-158">Copy the code for an element in the DOM Tree</span><span class="sxs-lookup"><span data-stu-id="63b0c-158">Copy the code for an element in the DOM Tree</span></span>  

1.  <span data-ttu-id="63b0c-159">With focus on a node in the **DOM Tree**, hover on the node and open the contextual menu \(right-click\).</span><span class="sxs-lookup"><span data-stu-id="63b0c-159">With focus on a node in the **DOM Tree**, hover on the node and open the contextual menu \(right-click\).</span></span>  
1.  <span data-ttu-id="63b0c-160">Expand the **Copy** option.</span><span class="sxs-lookup"><span data-stu-id="63b0c-160">Expand the **Copy** option.</span></span>  
1.  <span data-ttu-id="63b0c-161">Select **Copy outerHTML**.</span><span class="sxs-lookup"><span data-stu-id="63b0c-161">Select **Copy outerHTML**.</span></span>  

**<span data-ttu-id="63b0c-162">Known issues</span><span class="sxs-lookup"><span data-stu-id="63b0c-162">Known issues</span></span>**  

*   <span data-ttu-id="63b0c-163">**Copy outerHTML** often does not select the current node but instead selects the parent node.</span><span class="sxs-lookup"><span data-stu-id="63b0c-163">**Copy outerHTML** often does not select the current node but instead selects the parent node.</span></span>  <span data-ttu-id="63b0c-164">However, the contents of the element should still be in the copied outerHTML.</span><span class="sxs-lookup"><span data-stu-id="63b0c-164">However, the contents of the element should still be in the copied outerHTML.</span></span>  

### <span data-ttu-id="63b0c-165">Modify the attributes of an element in the DOM Tree</span><span class="sxs-lookup"><span data-stu-id="63b0c-165">Modify the attributes of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="63b0c-166">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span><span class="sxs-lookup"><span data-stu-id="63b0c-166">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="63b0c-167">Select `Tab` to move between attribute values.</span><span class="sxs-lookup"><span data-stu-id="63b0c-167">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="63b0c-168">When you hear "space" you are inside of an empty text input and are able to type a new attribute value.</span><span class="sxs-lookup"><span data-stu-id="63b0c-168">When you hear "space" you are inside of an empty text input and are able to type a new attribute value.</span></span>  
*   <span data-ttu-id="63b0c-169">Select `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to accept the change and hear the entire contents of the element.</span><span class="sxs-lookup"><span data-stu-id="63b0c-169">Select `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to accept the change and hear the entire contents of the element.</span></span>  

**<span data-ttu-id="63b0c-170">Known issues</span><span class="sxs-lookup"><span data-stu-id="63b0c-170">Known issues</span></span>**  

*   <span data-ttu-id="63b0c-171">When you type into the text input you get no feedback.</span><span class="sxs-lookup"><span data-stu-id="63b0c-171">When you type into the text input you get no feedback.</span></span>  <span data-ttu-id="63b0c-172">If you make a typo and use the arrow keys to explore your input you also get no feedback.</span><span class="sxs-lookup"><span data-stu-id="63b0c-172">If you make a typo and use the arrow keys to explore your input you also get no feedback.</span></span>  <span data-ttu-id="63b0c-173">The easiest way to check your work is to accept the change, then listen for the entire element to be announced.</span><span class="sxs-lookup"><span data-stu-id="63b0c-173">The easiest way to check your work is to accept the change, then listen for the entire element to be announced.</span></span>  

### <span data-ttu-id="63b0c-174">Edit the HTML of an element in the DOM Tree</span><span class="sxs-lookup"><span data-stu-id="63b0c-174">Edit the HTML of an element in the DOM Tree</span></span>  

*   <span data-ttu-id="63b0c-175">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span><span class="sxs-lookup"><span data-stu-id="63b0c-175">With focus on a node in the **DOM Tree**, select `Enter` to make it editable.</span></span>  
*   <span data-ttu-id="63b0c-176">Select `Tab` to move between attribute values.</span><span class="sxs-lookup"><span data-stu-id="63b0c-176">Select `Tab` to move between attribute values.</span></span>  <span data-ttu-id="63b0c-177">When you hear the name of the element, for instance, `h2`, you are inside of a text input and may change the type of the element.</span><span class="sxs-lookup"><span data-stu-id="63b0c-177">When you hear the name of the element, for instance, `h2`, you are inside of a text input and may change the type of the element.</span></span>  
*   <span data-ttu-id="63b0c-178">Select `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to accept the change.</span><span class="sxs-lookup"><span data-stu-id="63b0c-178">Select `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to accept the change.</span></span>  

<span data-ttu-id="63b0c-179">For example, when you type `h3` and select `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\), the start and end tags of the `h3` element change.</span><span class="sxs-lookup"><span data-stu-id="63b0c-179">For example, when you type `h3` and select `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\), the start and end tags of the `h3` element change.</span></span>  

## <span data-ttu-id="63b0c-180">Elements panel tabs</span><span class="sxs-lookup"><span data-stu-id="63b0c-180">Elements panel tabs</span></span>  

<span data-ttu-id="63b0c-181">The **Elements** panel contains additional tabs for inspecting things like the CSS applied to an element or the relevant place in the accessibility tree.</span><span class="sxs-lookup"><span data-stu-id="63b0c-181">The **Elements** panel contains additional tabs for inspecting things like the CSS applied to an element or the relevant place in the accessibility tree.</span></span>  

*   <span data-ttu-id="63b0c-182">With focus on a node in the **DOM Tree**, select `Tab` until you hear that the **Styles** pane is selected.</span><span class="sxs-lookup"><span data-stu-id="63b0c-182">With focus on a node in the **DOM Tree**, select `Tab` until you hear that the **Styles** pane is selected.</span></span>  
*   <span data-ttu-id="63b0c-183">Use the `Right Arrow` to explore other available tabs.</span><span class="sxs-lookup"><span data-stu-id="63b0c-183">Use the `Right Arrow` to explore other available tabs.</span></span>  

<span data-ttu-id="63b0c-184">The **DOM Tree** turns elements with `href` attributes into focusable links, so you may need to select `Tab` more than once to reach the **Styles** pane.</span><span class="sxs-lookup"><span data-stu-id="63b0c-184">The **DOM Tree** turns elements with `href` attributes into focusable links, so you may need to select `Tab` more than once to reach the **Styles** pane.</span></span>  

**<span data-ttu-id="63b0c-185">Known issues</span><span class="sxs-lookup"><span data-stu-id="63b0c-185">Known issues</span></span>**  

<span data-ttu-id="63b0c-186">The **DOM Breakpoints** and **Properties** tabs are not keyboard accessible.</span><span class="sxs-lookup"><span data-stu-id="63b0c-186">The **DOM Breakpoints** and **Properties** tabs are not keyboard accessible.</span></span>  

### <span data-ttu-id="63b0c-187">Styles pane</span><span class="sxs-lookup"><span data-stu-id="63b0c-187">Styles pane</span></span>  

<span data-ttu-id="63b0c-188">In the **Styles** pane find controls for filtering styles, toggling element states \(such as [:active][MDNActive] and [:focus][MDNFocus]\), toggling classes, and adding new classes.</span><span class="sxs-lookup"><span data-stu-id="63b0c-188">In the **Styles** pane find controls for filtering styles, toggling element states \(such as [:active][MDNActive] and [:focus][MDNFocus]\), toggling classes, and adding new classes.</span></span>  <span data-ttu-id="63b0c-189">There is also a powerful style inspection tool to explore and modify styles currently applied to the element that is in focus in the **DOM Tree**.</span><span class="sxs-lookup"><span data-stu-id="63b0c-189">There is also a powerful style inspection tool to explore and modify styles currently applied to the element that is in focus in the **DOM Tree**.</span></span>  

<span data-ttu-id="63b0c-190">The key concept to understand about the **Styles** pane is that it only shows styles for the currently-selected node in the **DOM Tree**.</span><span class="sxs-lookup"><span data-stu-id="63b0c-190">The key concept to understand about the **Styles** pane is that it only shows styles for the currently-selected node in the **DOM Tree**.</span></span>  <span data-ttu-id="63b0c-191">For example, suppose you are done inspecting the styles of a `<header>` node, and now you want to look at the styles for a `<footer>` node.</span><span class="sxs-lookup"><span data-stu-id="63b0c-191">For example, suppose you are done inspecting the styles of a `<header>` node, and now you want to look at the styles for a `<footer>` node.</span></span>  <span data-ttu-id="63b0c-192">To do that, you first need to select the `<footer>` node in the **DOM Tree**.</span><span class="sxs-lookup"><span data-stu-id="63b0c-192">To do that, you first need to select the `<footer>` node in the **DOM Tree**.</span></span>  <span data-ttu-id="63b0c-193">You may find it faster to use the [Inspect](#inspect-an-element-on-the-page) workflow to inspect a node that is in the general vicinity of the `footer` node \(such as a link within the footer\), which focuses the **DOM Tree**, and then use your keyboard to navigate to the exact node in which you are interested.</span><span class="sxs-lookup"><span data-stu-id="63b0c-193">You may find it faster to use the [Inspect](#inspect-an-element-on-the-page) workflow to inspect a node that is in the general vicinity of the `footer` node \(such as a link within the footer\), which focuses the **DOM Tree**, and then use your keyboard to navigate to the exact node in which you are interested.</span></span>  

#### <span data-ttu-id="63b0c-194">Navigate the Styles pane</span><span class="sxs-lookup"><span data-stu-id="63b0c-194">Navigate the Styles pane</span></span>  

<span data-ttu-id="63b0c-195">Because all of the style tools connect in one way or another back to the **Styles** pane, it makes sense to become an expert in this tool first.</span><span class="sxs-lookup"><span data-stu-id="63b0c-195">Because all of the style tools connect in one way or another back to the **Styles** pane, it makes sense to become an expert in this tool first.</span></span>  

*   <span data-ttu-id="63b0c-196">With focus on the **Styles** pane, select `Tab` to move focus inside and explore the contents.</span><span class="sxs-lookup"><span data-stu-id="63b0c-196">With focus on the **Styles** pane, select `Tab` to move focus inside and explore the contents.</span></span>  
*   <span data-ttu-id="63b0c-197">Select `Tab` until the first style becomes active.</span><span class="sxs-lookup"><span data-stu-id="63b0c-197">Select `Tab` until the first style becomes active.</span></span>  <span data-ttu-id="63b0c-198">If you are using a screen reader this first style is announced as `element.style {}`.</span><span class="sxs-lookup"><span data-stu-id="63b0c-198">If you are using a screen reader this first style is announced as `element.style {}`.</span></span>  
*   <span data-ttu-id="63b0c-199">Select `Down Arrow` to navigate the list of styles in order of specificity.</span><span class="sxs-lookup"><span data-stu-id="63b0c-199">Select `Down Arrow` to navigate the list of styles in order of specificity.</span></span>  <span data-ttu-id="63b0c-200">A screen reader announces each style starting with the name of the CSS file, the line number on which the style appears, and the name of the style.</span><span class="sxs-lookup"><span data-stu-id="63b0c-200">A screen reader announces each style starting with the name of the CSS file, the line number on which the style appears, and the name of the style.</span></span>  <span data-ttu-id="63b0c-201">For example, `main.css:233 .card__img {}`.</span><span class="sxs-lookup"><span data-stu-id="63b0c-201">For example, `main.css:233 .card__img {}`.</span></span>  
*   <span data-ttu-id="63b0c-202">Select `Enter` to inspect a style in more detail.</span><span class="sxs-lookup"><span data-stu-id="63b0c-202">Select `Enter` to inspect a style in more detail.</span></span>  <span data-ttu-id="63b0c-203">Focus begins on an editable version of the style name.</span><span class="sxs-lookup"><span data-stu-id="63b0c-203">Focus begins on an editable version of the style name.</span></span>  
*   <span data-ttu-id="63b0c-204">Select `Tab` to move between editable versions of each CSS property and the corresponding values.</span><span class="sxs-lookup"><span data-stu-id="63b0c-204">Select `Tab` to move between editable versions of each CSS property and the corresponding values.</span></span>  <span data-ttu-id="63b0c-205">At the end of each style block is a blank editable text field which you may use to add additional CSS properties.</span><span class="sxs-lookup"><span data-stu-id="63b0c-205">At the end of each style block is a blank editable text field which you may use to add additional CSS properties.</span></span>  
*   <span data-ttu-id="63b0c-206">You may continue to select `Tab` to move through the list of styles, or select `Escape` to exit the mode and go back to navigating by arrow keys.</span><span class="sxs-lookup"><span data-stu-id="63b0c-206">You may continue to select `Tab` to move through the list of styles, or select `Escape` to exit the mode and go back to navigating by arrow keys.</span></span>  

<span data-ttu-id="63b0c-207">For additional shortcuts, see [Styles pane keyboard reference][DevtoolsShortcutsStylesPaneKeyboard].</span><span class="sxs-lookup"><span data-stu-id="63b0c-207">For additional shortcuts, see [Styles pane keyboard reference][DevtoolsShortcutsStylesPaneKeyboard].</span></span>  

**<span data-ttu-id="63b0c-208">Known issues</span><span class="sxs-lookup"><span data-stu-id="63b0c-208">Known issues</span></span>**  

*   <span data-ttu-id="63b0c-209">If you use the **Filter** editable text field, you are no longer be able to navigate the list of styles.</span><span class="sxs-lookup"><span data-stu-id="63b0c-209">If you use the **Filter** editable text field, you are no longer be able to navigate the list of styles.</span></span>  

#### <span data-ttu-id="63b0c-210">Toggle element state</span><span class="sxs-lookup"><span data-stu-id="63b0c-210">Toggle element state</span></span>  

<span data-ttu-id="63b0c-211">To toggle the state of an element, such as `:active` or `:focus`:</span><span class="sxs-lookup"><span data-stu-id="63b0c-211">To toggle the state of an element, such as `:active` or `:focus`:</span></span>  

1.  <span data-ttu-id="63b0c-212">Navigate to the **Styles** pane and select `Tab` until the **Toggle Element State** button has focus.</span><span class="sxs-lookup"><span data-stu-id="63b0c-212">Navigate to the **Styles** pane and select `Tab` until the **Toggle Element State** button has focus.</span></span>  
1.  <span data-ttu-id="63b0c-213">Select `Enter` to expand the collection of element states.</span><span class="sxs-lookup"><span data-stu-id="63b0c-213">Select `Enter` to expand the collection of element states.</span></span>  <span data-ttu-id="63b0c-214">The element states are presented as a group of checkboxes.</span><span class="sxs-lookup"><span data-stu-id="63b0c-214">The element states are presented as a group of checkboxes.</span></span>  
1.  <span data-ttu-id="63b0c-215">Select `Tab` until the first state, `:active`, has focus.</span><span class="sxs-lookup"><span data-stu-id="63b0c-215">Select `Tab` until the first state, `:active`, has focus.</span></span>  
1.  <span data-ttu-id="63b0c-216">Select `Space` to enable it.</span><span class="sxs-lookup"><span data-stu-id="63b0c-216">Select `Space` to enable it.</span></span>  <span data-ttu-id="63b0c-217">If the currently-selected element in the DOM Tree has an `:active` style, it is now applied.</span><span class="sxs-lookup"><span data-stu-id="63b0c-217">If the currently-selected element in the DOM Tree has an `:active` style, it is now applied.</span></span>  
1.  <span data-ttu-id="63b0c-218">Hold `Tab` to explore all of the available states.</span><span class="sxs-lookup"><span data-stu-id="63b0c-218">Hold `Tab` to explore all of the available states.</span></span>  

#### <span data-ttu-id="63b0c-219">Add an existing class</span><span class="sxs-lookup"><span data-stu-id="63b0c-219">Add an existing class</span></span>  

<span data-ttu-id="63b0c-220">Adjacent to the **Toggle Element State** button is the **Element Classes** button.</span><span class="sxs-lookup"><span data-stu-id="63b0c-220">Adjacent to the **Toggle Element State** button is the **Element Classes** button.</span></span>  <span data-ttu-id="63b0c-221">To move the focus to it, select `Tab` and select `Enter`.</span><span class="sxs-lookup"><span data-stu-id="63b0c-221">To move the focus to it, select `Tab` and select `Enter`.</span></span>  <span data-ttu-id="63b0c-222">Focus moves into an edit text field labeled **Add New Class**.</span><span class="sxs-lookup"><span data-stu-id="63b0c-222">Focus moves into an edit text field labeled **Add New Class**.</span></span>  

<span data-ttu-id="63b0c-223">The **Element Classes** button is primarily used for adding existing classes to an element.</span><span class="sxs-lookup"><span data-stu-id="63b0c-223">The **Element Classes** button is primarily used for adding existing classes to an element.</span></span>  <span data-ttu-id="63b0c-224">For example, if your stylesheet contained a helper class named `.clearfix` you may select `.` inside of the edit text field to see a suggestion list of classes and use the `Down Arrow` to find the `.clearfix` suggestion.</span><span class="sxs-lookup"><span data-stu-id="63b0c-224">For example, if your stylesheet contained a helper class named `.clearfix` you may select `.` inside of the edit text field to see a suggestion list of classes and use the `Down Arrow` to find the `.clearfix` suggestion.</span></span>  <span data-ttu-id="63b0c-225">Or type the class name out yourself and select `Enter` to apply it.</span><span class="sxs-lookup"><span data-stu-id="63b0c-225">Or type the class name out yourself and select `Enter` to apply it.</span></span>  

#### <span data-ttu-id="63b0c-226">Add a new style rule</span><span class="sxs-lookup"><span data-stu-id="63b0c-226">Add a new style rule</span></span>  

<span data-ttu-id="63b0c-227">Adjacent to the **Element Classes** button is the **New Style Rule** button.</span><span class="sxs-lookup"><span data-stu-id="63b0c-227">Adjacent to the **Element Classes** button is the **New Style Rule** button.</span></span>  <span data-ttu-id="63b0c-228">To move the focus to it, select `Tab` and select `Enter`.</span><span class="sxs-lookup"><span data-stu-id="63b0c-228">To move the focus to it, select `Tab` and select `Enter`.</span></span>  <span data-ttu-id="63b0c-229">Focus moves into an editable text field inside of the style inspector.</span><span class="sxs-lookup"><span data-stu-id="63b0c-229">Focus moves into an editable text field inside of the style inspector.</span></span>  <span data-ttu-id="63b0c-230">The initial text content of the field is the tag name of the element that is selected in the **DOM Tree**.</span><span class="sxs-lookup"><span data-stu-id="63b0c-230">The initial text content of the field is the tag name of the element that is selected in the **DOM Tree**.</span></span>  
<span data-ttu-id="63b0c-231">You may type any class name you want into this field and then select `Tab` to assign CSS properties to it.</span><span class="sxs-lookup"><span data-stu-id="63b0c-231">You may type any class name you want into this field and then select `Tab` to assign CSS properties to it.</span></span>  

### <span data-ttu-id="63b0c-232">Computed tab</span><span class="sxs-lookup"><span data-stu-id="63b0c-232">Computed tab</span></span>  

<span data-ttu-id="63b0c-233">With focus on the **Computed** tab, select `Tab` to move focus inside and explore the contents.</span><span class="sxs-lookup"><span data-stu-id="63b0c-233">With focus on the **Computed** tab, select `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="63b0c-234">Within the **Computed** tab there are controls for exploring which CSS properties are actually applied to an element in order of specificity.</span><span class="sxs-lookup"><span data-stu-id="63b0c-234">Within the **Computed** tab there are controls for exploring which CSS properties are actually applied to an element in order of specificity.</span></span>  

<!--todo: add computed tab section when available  -->  

#### <span data-ttu-id="63b0c-235">Explore all computed styles</span><span class="sxs-lookup"><span data-stu-id="63b0c-235">Explore all computed styles</span></span>  

<span data-ttu-id="63b0c-236">Select `Tab` until you reach the collection of computed styles.</span><span class="sxs-lookup"><span data-stu-id="63b0c-236">Select `Tab` until you reach the collection of computed styles.</span></span>  <span data-ttu-id="63b0c-237">These are presented as an [ARIA tree][W3CWaiAriaTree].</span><span class="sxs-lookup"><span data-stu-id="63b0c-237">These are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="63b0c-238">Expanding a listbox reveals which CSS selectors are applying the computed style.</span><span class="sxs-lookup"><span data-stu-id="63b0c-238">Expanding a listbox reveals which CSS selectors are applying the computed style.</span></span>  <span data-ttu-id="63b0c-239">These selectors are organized by specificity.</span><span class="sxs-lookup"><span data-stu-id="63b0c-239">These selectors are organized by specificity.</span></span>  <span data-ttu-id="63b0c-240">A screen reader announces the computed value, which CSS selector is currently matching, the filename of the stylesheet that contains the selector, and the line number for the selector.</span><span class="sxs-lookup"><span data-stu-id="63b0c-240">A screen reader announces the computed value, which CSS selector is currently matching, the filename of the stylesheet that contains the selector, and the line number for the selector.</span></span>  

**<span data-ttu-id="63b0c-241">Known issues</span><span class="sxs-lookup"><span data-stu-id="63b0c-241">Known issues</span></span>**  

*   <span data-ttu-id="63b0c-242">If you use the **Filter** text field, you are no longer able to inspect styles.</span><span class="sxs-lookup"><span data-stu-id="63b0c-242">If you use the **Filter** text field, you are no longer able to inspect styles.</span></span>  

### <span data-ttu-id="63b0c-243">Event listeners tab</span><span class="sxs-lookup"><span data-stu-id="63b0c-243">Event listeners tab</span></span>  

<span data-ttu-id="63b0c-244">From within the **Elements** panel you may inspect the event listeners applied to an element using the **Event Listeners** tab.  With focus on the **Styles** pane, select the `Right Arrow` to navigate to the **Event Listeners** tab.</span><span class="sxs-lookup"><span data-stu-id="63b0c-244">From within the **Elements** panel you may inspect the event listeners applied to an element using the **Event Listeners** tab.  With focus on the **Styles** pane, select the `Right Arrow` to navigate to the **Event Listeners** tab.</span></span>  

#### <span data-ttu-id="63b0c-245">Explore event listeners</span><span class="sxs-lookup"><span data-stu-id="63b0c-245">Explore event listeners</span></span>  

<span data-ttu-id="63b0c-246">Event listeners are presented as an [ARIA tree][W3CWaiAriaTree].</span><span class="sxs-lookup"><span data-stu-id="63b0c-246">Event listeners are presented as an [ARIA tree][W3CWaiAriaTree].</span></span>  <span data-ttu-id="63b0c-247">You may use the arrow keys to navigate them.</span><span class="sxs-lookup"><span data-stu-id="63b0c-247">You may use the arrow keys to navigate them.</span></span>  <span data-ttu-id="63b0c-248">A screen reader announces the name of the DOM object that the event listener is attached to, as well as the file name where the event listener is defined and the line number.</span><span class="sxs-lookup"><span data-stu-id="63b0c-248">A screen reader announces the name of the DOM object that the event listener is attached to, as well as the file name where the event listener is defined and the line number.</span></span>  

### <span data-ttu-id="63b0c-249">Accessibility pane</span><span class="sxs-lookup"><span data-stu-id="63b0c-249">Accessibility pane</span></span>  

<span data-ttu-id="63b0c-250">With focus on the **Accessibility** pane, select `Tab` to move focus inside and explore the contents.</span><span class="sxs-lookup"><span data-stu-id="63b0c-250">With focus on the **Accessibility** pane, select `Tab` to move focus inside and explore the contents.</span></span>  <span data-ttu-id="63b0c-251">On the [Accessibility pane][DevtoolsAccessibilityReference] there are controls for exploring the accessibility tree, the ARIA attributes applied to an element, and the computed accessibility properties.</span><span class="sxs-lookup"><span data-stu-id="63b0c-251">On the [Accessibility pane][DevtoolsAccessibilityReference] there are controls for exploring the accessibility tree, the ARIA attributes applied to an element, and the computed accessibility properties.</span></span>  

#### <span data-ttu-id="63b0c-252">Accessibility Tree</span><span class="sxs-lookup"><span data-stu-id="63b0c-252">Accessibility Tree</span></span>  

<span data-ttu-id="63b0c-253">The **Accessibility Tree** is presented as an [ARIA tree][W3CWaiAriaTree] where each `treeitem` corresponds to an element in the DOM.</span><span class="sxs-lookup"><span data-stu-id="63b0c-253">The **Accessibility Tree** is presented as an [ARIA tree][W3CWaiAriaTree] where each `treeitem` corresponds to an element in the DOM.</span></span>  <span data-ttu-id="63b0c-254">The tree announces the computed role for the selected node.</span><span class="sxs-lookup"><span data-stu-id="63b0c-254">The tree announces the computed role for the selected node.</span></span>  <span data-ttu-id="63b0c-255">Generic elements like `div` and `span` are announced as "GenericContainer" in the tree.</span><span class="sxs-lookup"><span data-stu-id="63b0c-255">Generic elements like `div` and `span` are announced as "GenericContainer" in the tree.</span></span>  <span data-ttu-id="63b0c-256">Use the arrow keys to traverse the tree and explore parent-child relationships.</span><span class="sxs-lookup"><span data-stu-id="63b0c-256">Use the arrow keys to traverse the tree and explore parent-child relationships.</span></span>  

**<span data-ttu-id="63b0c-257">Known issues</span><span class="sxs-lookup"><span data-stu-id="63b0c-257">Known issues</span></span>**  

*   <span data-ttu-id="63b0c-258">The type of [ARIA tree][W3CWaiAriaTree] used by the **Accessibility** pane may not be properly exposed in Microsoft Edge for macOS screen readers like VoiceOver.</span><span class="sxs-lookup"><span data-stu-id="63b0c-258">The type of [ARIA tree][W3CWaiAriaTree] used by the **Accessibility** pane may not be properly exposed in Microsoft Edge for macOS screen readers like VoiceOver.</span></span>  <span data-ttu-id="63b0c-259">Subscribe to [Chromium issue #868480][ChromiumIssues868480] to be informed about progress on this issue.</span><span class="sxs-lookup"><span data-stu-id="63b0c-259">Subscribe to [Chromium issue #868480][ChromiumIssues868480] to be informed about progress on this issue.</span></span>  
*   <span data-ttu-id="63b0c-260">Each of the **ARIA Attributes** and **Computed Properties** sections are marked up as an [ARIA tree][W3CWaiAriaTree], but each does not currently have focus management and is not keyboard operable.</span><span class="sxs-lookup"><span data-stu-id="63b0c-260">Each of the **ARIA Attributes** and **Computed Properties** sections are marked up as an [ARIA tree][W3CWaiAriaTree], but each does not currently have focus management and is not keyboard operable.</span></span>  

## <span data-ttu-id="63b0c-261">Audits panel</span><span class="sxs-lookup"><span data-stu-id="63b0c-261">Audits panel</span></span>  

<span data-ttu-id="63b0c-262">The **Audits** panel you should run a series of tests against a site to check for common issues related to performance, accessibility, SEO, and a number of other categories.</span><span class="sxs-lookup"><span data-stu-id="63b0c-262">The **Audits** panel you should run a series of tests against a site to check for common issues related to performance, accessibility, SEO, and a number of other categories.</span></span>  

### <span data-ttu-id="63b0c-263">Configure and run an audit</span><span class="sxs-lookup"><span data-stu-id="63b0c-263">Configure and run an audit</span></span>  

1.  <span data-ttu-id="63b0c-264">When the **Audits** panel is first opened, focus is placed on the **Run Audit** button at the end of the form.</span><span class="sxs-lookup"><span data-stu-id="63b0c-264">When the **Audits** panel is first opened, focus is placed on the **Run Audit** button at the end of the form.</span></span>  <span data-ttu-id="63b0c-265">By default the form is configured to run audits for every category using mobile emulation on a simulated 3G connection.</span><span class="sxs-lookup"><span data-stu-id="63b0c-265">By default the form is configured to run audits for every category using mobile emulation on a simulated 3G connection.</span></span>  
1.  <span data-ttu-id="63b0c-266">Use `Shift`+`Tab` or navigate back in Browse mode to change the audit settings.</span><span class="sxs-lookup"><span data-stu-id="63b0c-266">Use `Shift`+`Tab` or navigate back in Browse mode to change the audit settings.</span></span>  
1.  <span data-ttu-id="63b0c-267">When you are ready to run the audit, navigate back to the **Run Audit** button and select `Enter`.</span><span class="sxs-lookup"><span data-stu-id="63b0c-267">When you are ready to run the audit, navigate back to the **Run Audit** button and select `Enter`.</span></span>  
1.  <span data-ttu-id="63b0c-268">Focus moves into a modal window with a **Cancel** button which allows you to exit the audit.</span><span class="sxs-lookup"><span data-stu-id="63b0c-268">Focus moves into a modal window with a **Cancel** button which allows you to exit the audit.</span></span>  <span data-ttu-id="63b0c-269">You may hear a series of earcons as the audit runs and refreshes the page multiple times.</span><span class="sxs-lookup"><span data-stu-id="63b0c-269">You may hear a series of earcons as the audit runs and refreshes the page multiple times.</span></span>  

**<span data-ttu-id="63b0c-270">Known issues</span><span class="sxs-lookup"><span data-stu-id="63b0c-270">Known issues</span></span>**  

*   <span data-ttu-id="63b0c-271">The different sections of the configuration form are not currently marked up with a `fieldset` element.</span><span class="sxs-lookup"><span data-stu-id="63b0c-271">The different sections of the configuration form are not currently marked up with a `fieldset` element.</span></span>  <span data-ttu-id="63b0c-272">It may be easier to navigate them in Browse mode to figure out which controls are associated with each section.</span><span class="sxs-lookup"><span data-stu-id="63b0c-272">It may be easier to navigate them in Browse mode to figure out which controls are associated with each section.</span></span>  
*   <span data-ttu-id="63b0c-273">There is no earcon or live region announcement when the audit is finished running.</span><span class="sxs-lookup"><span data-stu-id="63b0c-273">There is no earcon or live region announcement when the audit is finished running.</span></span>  <span data-ttu-id="63b0c-274">Generally it takes about 30 seconds, after which you should be able to navigate to the results.</span><span class="sxs-lookup"><span data-stu-id="63b0c-274">Generally it takes about 30 seconds, after which you should be able to navigate to the results.</span></span>  <span data-ttu-id="63b0c-275">Using Browse mode may be the easiest way to reach the results.</span><span class="sxs-lookup"><span data-stu-id="63b0c-275">Using Browse mode may be the easiest way to reach the results.</span></span>  

### <span data-ttu-id="63b0c-276">Navigate the audit report</span><span class="sxs-lookup"><span data-stu-id="63b0c-276">Navigate the audit report</span></span>  

<span data-ttu-id="63b0c-277">The audit report is organized into sections that correspond with each of the audit categories.</span><span class="sxs-lookup"><span data-stu-id="63b0c-277">The audit report is organized into sections that correspond with each of the audit categories.</span></span>  <span data-ttu-id="63b0c-278">The report opens with a list of scores for each category.</span><span class="sxs-lookup"><span data-stu-id="63b0c-278">The report opens with a list of scores for each category.</span></span>  <span data-ttu-id="63b0c-279">These scores are also links which are able to be used to skip to the relevant sections.</span><span class="sxs-lookup"><span data-stu-id="63b0c-279">These scores are also links which are able to be used to skip to the relevant sections.</span></span>  <span data-ttu-id="63b0c-280">Within each section are expandable `details` elements, which contain information relating to passed or failed audits.</span><span class="sxs-lookup"><span data-stu-id="63b0c-280">Within each section are expandable `details` elements, which contain information relating to passed or failed audits.</span></span>  <span data-ttu-id="63b0c-281">By default, only failing audits are shown.</span><span class="sxs-lookup"><span data-stu-id="63b0c-281">By default, only failing audits are shown.</span></span>  <span data-ttu-id="63b0c-282">Each section ends with a final `details` element which contains all of the passed audits.</span><span class="sxs-lookup"><span data-stu-id="63b0c-282">Each section ends with a final `details` element which contains all of the passed audits.</span></span>  

<span data-ttu-id="63b0c-283">To run a new audit, use `Shift`+`Tab` to exit the report and look for the **Perform An Audit** button.</span><span class="sxs-lookup"><span data-stu-id="63b0c-283">To run a new audit, use `Shift`+`Tab` to exit the report and look for the **Perform An Audit** button.</span></span>  

## <span data-ttu-id="63b0c-284">Getting in touch with the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="63b0c-284">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsAccessibilityReference]: ./reference.md "Accessibility reference | Microsoft Docs"  
[DevtoolsAccessibilityReferencePane]: reference.md#the-accessibility-pane "The Accessibility pane - Accessibility Reference | Microsoft Docs"  
[MicrosoftEdgeDevtoolsMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) Developer Tools | Microsoft Docs"  
[DevtoolsCommandMenuIndex]: ../command-menu/index.md "Run Commands With The Microsoft Edge DevTools Command Menu | Microsoft Docs"  
[DevtoolsConsoleIndex]: ../console/index.md "Console Overview | Microsoft Docs"  
[DevtoolsCssIndex]: ../css/index.md "Get Started With Viewing And Changing CSS | Microsoft Docs"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element | Microsoft Docs"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get started with viewing and changing the DOM | Microsoft Docs"  -->  
[DevtoolsDomIndexViewDomNodes]: ../dom/index.md#view-dom-nodes "View DOM nodes - Get started with viewing and changing the DOM | Microsoft Docs"  
[DevtoolsDomIndexNavigateDomTreeKeyboard]: ../dom/index.md#navigate-the-dom-tree-with-a-keyboard "Navigate the DOM Tree with a keyboard - Get started with viewing and changing the DOM | Microsoft Docs"  
[DevtoolsOpen]: ../open.md "Open Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsShortcuts]: ../shortcuts.md "Microsoft Edge DevTools Keyboard Shortcuts | Microsoft Docs"  
[DevtoolsShortcutsStylesPaneKeyboard]: ../shortcuts.md#styles-pane-keyboard-shortcuts "Styles pane keyboard shortcuts - Microsoft Edge DevTools Keyboard Shortcuts | Microsoft Docs"  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "Issue 868480 - Expose ARIA trees as tables in Mac accessibility"  

[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "New Issue - MicrosoftDocs/edge-developer | GitHub"  

[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active ":active | MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus ":focus | MDN"  

[MonorailChromiumIssues]: https://crbug.com "Issues - chromium - Monorail"  

[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "tablist (role) - Accessible Rich Internet Applications (WAI-ARIA) 1.1 | W3C"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "tree (role) - Accessible Rich Internet Applications (WAI-ARIA) 1.1 | W3C"  

> [!NOTE]
> <span data-ttu-id="63b0c-303">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="63b0c-303">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="63b0c-304">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) and is authored by [Rob Dodson][RobDodson] \(Contributor, Google WebFundamentals\).</span><span class="sxs-lookup"><span data-stu-id="63b0c-304">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) and is authored by [Rob Dodson][RobDodson] \(Contributor, Google WebFundamentals\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="63b0c-306">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="63b0c-306">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[RobDodson]: https://developers.google.com/web/resources/contributors/robdodson  
