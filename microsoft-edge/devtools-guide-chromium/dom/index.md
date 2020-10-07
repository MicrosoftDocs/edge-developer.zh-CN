---
description: How to view nodes, search for nodes, edit nodes, reference nodes in the Console, break on node changes, and more.
title: Get Started With Viewing And Changing The DOM
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 555e627b70f0cc5e50c0676cf90067c2709a9ae3
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992951"
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





# <span data-ttu-id="510e3-104">Get started with viewing and changing the DOM</span><span class="sxs-lookup"><span data-stu-id="510e3-104">Get started with viewing and changing the DOM</span></span>   



<span data-ttu-id="510e3-105">Complete these interactive tutorials to learn the basics of viewing and changing the DOM of a page using Microsoft Edge DevTools.</span><span class="sxs-lookup"><span data-stu-id="510e3-105">Complete these interactive tutorials to learn the basics of viewing and changing the DOM of a page using Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="510e3-106">This tutorial assumes that you know the difference between the DOM and HTML.</span><span class="sxs-lookup"><span data-stu-id="510e3-106">This tutorial assumes that you know the difference between the DOM and HTML.</span></span>  <span data-ttu-id="510e3-107">See [Appendix: HTML versus the DOM](#appendix-html-versus-the-dom) for an explanation.</span><span class="sxs-lookup"><span data-stu-id="510e3-107">See [Appendix: HTML versus the DOM](#appendix-html-versus-the-dom) for an explanation.</span></span>  

## <span data-ttu-id="510e3-108">Open DOM examples</span><span class="sxs-lookup"><span data-stu-id="510e3-108">Open DOM examples</span></span>  

1.  <span data-ttu-id="510e3-109">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **DOM Examples** to open in a new tab.</span><span class="sxs-lookup"><span data-stu-id="510e3-109">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **DOM Examples** to open in a new tab.</span></span>  
    
    [<span data-ttu-id="510e3-110">DOM Examples</span><span class="sxs-lookup"><span data-stu-id="510e3-110">DOM Examples</span></span>][GlitchDomExamples]  
    
## <span data-ttu-id="510e3-111">View DOM nodes</span><span class="sxs-lookup"><span data-stu-id="510e3-111">View DOM nodes</span></span>   

<span data-ttu-id="510e3-112">The DOM Tree of the Elements panel is where you do all DOM-related activities in DevTools.</span><span class="sxs-lookup"><span data-stu-id="510e3-112">The DOM Tree of the Elements panel is where you do all DOM-related activities in DevTools.</span></span>  

### <span data-ttu-id="510e3-113">Inspect a node</span><span class="sxs-lookup"><span data-stu-id="510e3-113">Inspect a node</span></span>   

<span data-ttu-id="510e3-114">When you are interested in a particular DOM node, **Inspect** is a fast way to open DevTools and investigate that node.</span><span class="sxs-lookup"><span data-stu-id="510e3-114">When you are interested in a particular DOM node, **Inspect** is a fast way to open DevTools and investigate that node.</span></span>  

1.  <span data-ttu-id="510e3-115">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-115">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-116">Under **Inspect a Node**, right-click **Michelangelo** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-116">Under **Inspect a Node**, right-click **Michelangelo** and select **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png" alt-text="Inspect a node" lightbox="../media/dom-glitch-dom-examples-michelangelo-inspect.msft.png":::
       <span data-ttu-id="510e3-118">Inspect a node</span><span class="sxs-lookup"><span data-stu-id="510e3-118">Inspect a node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="510e3-119">The **Elements** panel of DevTools opens.</span><span class="sxs-lookup"><span data-stu-id="510e3-119">The **Elements** panel of DevTools opens.</span></span>  `<li>Michelangelo</li>` <span data-ttu-id="510e3-120">is highlighted in the **DOM Tree**.</span><span class="sxs-lookup"><span data-stu-id="510e3-120">is highlighted in the **DOM Tree**.</span></span>  
        
        :::image type="complex" source="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png" alt-text="Inspect a node" lightbox="../media/dom-glitch-dom-examples-michelangelo-elements-highlighted.msft.png":::
           <span data-ttu-id="510e3-122">Highlight the `Michelangelo` node</span><span class="sxs-lookup"><span data-stu-id="510e3-122">Highlight the `Michelangelo` node</span></span>  
        :::image-end:::  
        
        1.  <span data-ttu-id="510e3-123">Click the **Inspect** \(![Inspect][ImageInspectIcon]\) icon in the top-left corner of DevTools.</span><span class="sxs-lookup"><span data-stu-id="510e3-123">Click the **Inspect** \(![Inspect][ImageInspectIcon]\) icon in the top-left corner of DevTools.</span></span>  
            
            :::image type="complex" source="../media/dom-elements-highlighted-select-element-page-inspect.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-select-element-page-inspect.msft.png":::
               <span data-ttu-id="510e3-125">The **Inspect** icon</span><span class="sxs-lookup"><span data-stu-id="510e3-125">The **Inspect** icon</span></span>  
            :::image-end:::  
            
1.  <span data-ttu-id="510e3-126">Under **Inspect a Node**, click the **Tokyo** text.</span><span class="sxs-lookup"><span data-stu-id="510e3-126">Under **Inspect a Node**, click the **Tokyo** text.</span></span>  <span data-ttu-id="510e3-127">Now, `<li>Tokyo</li>` is highlighted in the DOM Tree.</span><span class="sxs-lookup"><span data-stu-id="510e3-127">Now, `<li>Tokyo</li>` is highlighted in the DOM Tree.</span></span>  

<span data-ttu-id="510e3-128">Inspecting a node is also the first step towards viewing and changing the styles of a node.</span><span class="sxs-lookup"><span data-stu-id="510e3-128">Inspecting a node is also the first step towards viewing and changing the styles of a node.</span></span>  <span data-ttu-id="510e3-129">See [Get Started With Viewing And Changing CSS][DevToolsCssGetStarted].</span><span class="sxs-lookup"><span data-stu-id="510e3-129">See [Get Started With Viewing And Changing CSS][DevToolsCssGetStarted].</span></span>  

### <span data-ttu-id="510e3-130">Navigate the DOM Tree with a keyboard</span><span class="sxs-lookup"><span data-stu-id="510e3-130">Navigate the DOM Tree with a keyboard</span></span>   

<span data-ttu-id="510e3-131">Once you have selected a node in the DOM Tree, you may navigate the DOM Tree with your keyboard.</span><span class="sxs-lookup"><span data-stu-id="510e3-131">Once you have selected a node in the DOM Tree, you may navigate the DOM Tree with your keyboard.</span></span>  

1.  <span data-ttu-id="510e3-132">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-132">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-133">Under **Navigate the DOM Tree with a Keyboard**, right-click **Ringo** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-133">Under **Navigate the DOM Tree with a Keyboard**, right-click **Ringo** and select **Inspect**.</span></span>  `<li>Ringo</li>` <span data-ttu-id="510e3-134">is selected in the DOM Tree.</span><span class="sxs-lookup"><span data-stu-id="510e3-134">is selected in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ringo.msft.png":::
       <span data-ttu-id="510e3-136">Inspect the `Ringo` node</span><span class="sxs-lookup"><span data-stu-id="510e3-136">Inspect the `Ringo` node</span></span>  
    :::image-end:::  
    
    1.  <span data-ttu-id="510e3-137">Press the `Up` arrow key 2 times.</span><span class="sxs-lookup"><span data-stu-id="510e3-137">Press the `Up` arrow key 2 times.</span></span>  `<ul>` <span data-ttu-id="510e3-138">is selected.</span><span class="sxs-lookup"><span data-stu-id="510e3-138">is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-navigate-dom-tree-keyboard-ul.msft.png":::
           <span data-ttu-id="510e3-140">Inspect the `ul` node</span><span class="sxs-lookup"><span data-stu-id="510e3-140">Inspect the `ul` node</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="510e3-141">Press the `Left` arrow key.</span><span class="sxs-lookup"><span data-stu-id="510e3-141">Press the `Left` arrow key.</span></span>  <span data-ttu-id="510e3-142">The `<ul>` list collapses.</span><span class="sxs-lookup"><span data-stu-id="510e3-142">The `<ul>` list collapses.</span></span>  
    1.  <span data-ttu-id="510e3-143">Press the `Left` arrow key again.</span><span class="sxs-lookup"><span data-stu-id="510e3-143">Press the `Left` arrow key again.</span></span>  <span data-ttu-id="510e3-144">The parent of the `<ul>` node is selected.</span><span class="sxs-lookup"><span data-stu-id="510e3-144">The parent of the `<ul>` node is selected.</span></span>  <span data-ttu-id="510e3-145">In this case it is the `<div>` with the ID `navigate-the-dom-tree-with-a-keyboard-1`.</span><span class="sxs-lookup"><span data-stu-id="510e3-145">In this case it is the `<div>` with the ID `navigate-the-dom-tree-with-a-keyboard-1`.</span></span>  
    1.  <span data-ttu-id="510e3-146">Press the `Down` arrow key 2 times so that you have re-selected the `<ul>` list that you just collapsed.</span><span class="sxs-lookup"><span data-stu-id="510e3-146">Press the `Down` arrow key 2 times so that you have re-selected the `<ul>` list that you just collapsed.</span></span>  <span data-ttu-id="510e3-147">It should look like this:</span><span class="sxs-lookup"><span data-stu-id="510e3-147">It should look like this:</span></span> `<ul>... </ul>`  
    1.  <span data-ttu-id="510e3-148">Press the `Right` arrow key.</span><span class="sxs-lookup"><span data-stu-id="510e3-148">Press the `Right` arrow key.</span></span>  <span data-ttu-id="510e3-149">The list expands.</span><span class="sxs-lookup"><span data-stu-id="510e3-149">The list expands.</span></span>  

### <span data-ttu-id="510e3-150">Scroll into view</span><span class="sxs-lookup"><span data-stu-id="510e3-150">Scroll into view</span></span>   

<span data-ttu-id="510e3-151">When viewing the DOM Tree, you may find yourself interested in a DOM node that is not currently in the viewport.</span><span class="sxs-lookup"><span data-stu-id="510e3-151">When viewing the DOM Tree, you may find yourself interested in a DOM node that is not currently in the viewport.</span></span>  <span data-ttu-id="510e3-152">For example, suppose that you scrolled to the bottom of the page, and you are interested in the `<h1>` node at the top of the page.</span><span class="sxs-lookup"><span data-stu-id="510e3-152">For example, suppose that you scrolled to the bottom of the page, and you are interested in the `<h1>` node at the top of the page.</span></span>  <span data-ttu-id="510e3-153">**Scroll into view** lets you quickly reposition the viewport so that you are able to see the node.</span><span class="sxs-lookup"><span data-stu-id="510e3-153">**Scroll into view** lets you quickly reposition the viewport so that you are able to see the node.</span></span>  

1.  <span data-ttu-id="510e3-154">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-154">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-155">Under **Scroll into View**, right-click **Magritte** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-155">Under **Scroll into View**, right-click **Magritte** and select **Inspect**.</span></span>  
1.  <span data-ttu-id="510e3-156">Scroll to the bottom of the DOM Examples page.</span><span class="sxs-lookup"><span data-stu-id="510e3-156">Scroll to the bottom of the DOM Examples page.</span></span>  
1.  <span data-ttu-id="510e3-157">The `<li>Magritte</li>` node should still be selected in your DOM Tree.</span><span class="sxs-lookup"><span data-stu-id="510e3-157">The `<li>Magritte</li>` node should still be selected in your DOM Tree.</span></span>  <span data-ttu-id="510e3-158">If not, go back to [Scroll into view](#scroll-into-view) and start over.</span><span class="sxs-lookup"><span data-stu-id="510e3-158">If not, go back to [Scroll into view](#scroll-into-view) and start over.</span></span>  
1.  <span data-ttu-id="510e3-159">Right-click the `<li>Magritte</li>` node and select **Scroll into view**.</span><span class="sxs-lookup"><span data-stu-id="510e3-159">Right-click the `<li>Magritte</li>` node and select **Scroll into view**.</span></span>  <span data-ttu-id="510e3-160">Your viewport scrolls back up so that you may see the **Magritte** node.</span><span class="sxs-lookup"><span data-stu-id="510e3-160">Your viewport scrolls back up so that you may see the **Magritte** node.</span></span>  <span data-ttu-id="510e3-161">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.</span><span class="sxs-lookup"><span data-stu-id="510e3-161">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.</span></span>
    
    :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
       **<span data-ttu-id="510e3-163">Scroll into view</span><span class="sxs-lookup"><span data-stu-id="510e3-163">Scroll into view</span></span>**  
    :::image-end:::  

### <span data-ttu-id="510e3-164">Search for nodes</span><span class="sxs-lookup"><span data-stu-id="510e3-164">Search for nodes</span></span>   

<span data-ttu-id="510e3-165">You may search the DOM Tree by string, CSS selector, or XPath selector.</span><span class="sxs-lookup"><span data-stu-id="510e3-165">You may search the DOM Tree by string, CSS selector, or XPath selector.</span></span>  

1.  <span data-ttu-id="510e3-166">Focus your cursor on the **Elements** panel.</span><span class="sxs-lookup"><span data-stu-id="510e3-166">Focus your cursor on the **Elements** panel.</span></span>  
1.  <span data-ttu-id="510e3-167">Press `Control`+`F` \(Windows\) or `Command`+`F` \(macOS\).</span><span class="sxs-lookup"><span data-stu-id="510e3-167">Press `Control`+`F` \(Windows\) or `Command`+`F` \(macOS\).</span></span>  <span data-ttu-id="510e3-168">The Search bar opens at the bottom of the DOM Tree.</span><span class="sxs-lookup"><span data-stu-id="510e3-168">The Search bar opens at the bottom of the DOM Tree.</span></span>  
1.  <span data-ttu-id="510e3-169">Type `The Moon is a Harsh Mistress`.</span><span class="sxs-lookup"><span data-stu-id="510e3-169">Type `The Moon is a Harsh Mistress`.</span></span>  <span data-ttu-id="510e3-170">The last sentence is highlighted in the DOM Tree.</span><span class="sxs-lookup"><span data-stu-id="510e3-170">The last sentence is highlighted in the DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-search-nodes-highlight.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-search-nodes-highlight.msft.png":::
       <span data-ttu-id="510e3-172">Highlight the query in the Search bar</span><span class="sxs-lookup"><span data-stu-id="510e3-172">Highlight the query in the Search bar</span></span>  
    :::image-end:::  
    
<span data-ttu-id="510e3-173">As mentioned above, the Search bar also supports CSS and XPath selectors.</span><span class="sxs-lookup"><span data-stu-id="510e3-173">As mentioned above, the Search bar also supports CSS and XPath selectors.</span></span>  

## <span data-ttu-id="510e3-174">Edit the DOM</span><span class="sxs-lookup"><span data-stu-id="510e3-174">Edit the DOM</span></span>   

<span data-ttu-id="510e3-175">You may edit the DOM on the fly and see how those changes affect the page.</span><span class="sxs-lookup"><span data-stu-id="510e3-175">You may edit the DOM on the fly and see how those changes affect the page.</span></span>  

### <span data-ttu-id="510e3-176">Edit content</span><span class="sxs-lookup"><span data-stu-id="510e3-176">Edit content</span></span>   

<span data-ttu-id="510e3-177">To edit the content of a node, double-click the content in the DOM Tree.</span><span class="sxs-lookup"><span data-stu-id="510e3-177">To edit the content of a node, double-click the content in the DOM Tree.</span></span>  

1.  <span data-ttu-id="510e3-178">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-178">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-179">Under **Edit Content**, right-click **Michelle** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-179">Under **Edit Content**, right-click **Michelle** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="510e3-180">In the DOM Tree, double-click `Michelle`.</span><span class="sxs-lookup"><span data-stu-id="510e3-180">In the DOM Tree, double-click `Michelle`.</span></span>  <span data-ttu-id="510e3-181">In other words, double-click the text between `<li>` and `</li>`.</span><span class="sxs-lookup"><span data-stu-id="510e3-181">In other words, double-click the text between `<li>` and `</li>`.</span></span>  <span data-ttu-id="510e3-182">The text is highlighted to indicate that it is selected.</span><span class="sxs-lookup"><span data-stu-id="510e3-182">The text is highlighted to indicate that it is selected.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-content.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-edit-content.msft.png":::
           <span data-ttu-id="510e3-184">Edit the text</span><span class="sxs-lookup"><span data-stu-id="510e3-184">Edit the text</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="510e3-185">Delete `Michelle`, type `Leela`, then press `Enter` to confirm the change.</span><span class="sxs-lookup"><span data-stu-id="510e3-185">Delete `Michelle`, type `Leela`, then press `Enter` to confirm the change.</span></span>  <span data-ttu-id="510e3-186">The text in the DOM changes from **Michelle** to **Leela**.</span><span class="sxs-lookup"><span data-stu-id="510e3-186">The text in the DOM changes from **Michelle** to **Leela**.</span></span>  

### <span data-ttu-id="510e3-187">Edit attributes</span><span class="sxs-lookup"><span data-stu-id="510e3-187">Edit attributes</span></span>   

<span data-ttu-id="510e3-188">To edit attributes, double-click the attribute name or value.</span><span class="sxs-lookup"><span data-stu-id="510e3-188">To edit attributes, double-click the attribute name or value.</span></span>  <span data-ttu-id="510e3-189">Follow the instructions to learn how to add attributes to a node.</span><span class="sxs-lookup"><span data-stu-id="510e3-189">Follow the instructions to learn how to add attributes to a node.</span></span>  

1.  <span data-ttu-id="510e3-190">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-190">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-191">Under **Edit Attributes**, right-click **Howard** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-191">Under **Edit Attributes**, right-click **Howard** and select **Inspect**.</span></span>  
1.  <span data-ttu-id="510e3-192">Double-click `<li>`.</span><span class="sxs-lookup"><span data-stu-id="510e3-192">Double-click `<li>`.</span></span>  <span data-ttu-id="510e3-193">The text is highlighted to indicate that the node is selected.</span><span class="sxs-lookup"><span data-stu-id="510e3-193">The text is highlighted to indicate that the node is selected.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-edit-attributes-highlighted.msft.png":::
       <span data-ttu-id="510e3-195">Edit the node</span><span class="sxs-lookup"><span data-stu-id="510e3-195">Edit the node</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="510e3-196">Press the `Right` arrow key, add a space, type `style="background-color:gold"`, and then press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="510e3-196">Press the `Right` arrow key, add a space, type `style="background-color:gold"`, and then press `Enter`.</span></span>  <span data-ttu-id="510e3-197">The background color of the node changes to gold.</span><span class="sxs-lookup"><span data-stu-id="510e3-197">The background color of the node changes to gold.</span></span>  
    
    :::image type="complex" source="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-edit-attributes-inline-css.msft.png":::
       <span data-ttu-id="510e3-199">Add a `style` attribute to the node</span><span class="sxs-lookup"><span data-stu-id="510e3-199">Add a `style` attribute to the node</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="510e3-200">Edit node type</span><span class="sxs-lookup"><span data-stu-id="510e3-200">Edit node type</span></span>   

<span data-ttu-id="510e3-201">To edit the type of a node, double-click the type and then type in the new type.</span><span class="sxs-lookup"><span data-stu-id="510e3-201">To edit the type of a node, double-click the type and then type in the new type.</span></span>  

1.  <span data-ttu-id="510e3-202">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-202">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-203">Under **Edit Node Type**, right-click **Hank** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-203">Under **Edit Node Type**, right-click **Hank** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="510e3-204">Double-click `<li>`.</span><span class="sxs-lookup"><span data-stu-id="510e3-204">Double-click `<li>`.</span></span>  <span data-ttu-id="510e3-205">The text `li` is highlighted.</span><span class="sxs-lookup"><span data-stu-id="510e3-205">The text `li` is highlighted.</span></span>  
    1.  <span data-ttu-id="510e3-206">Delete `li`, type `button`, then press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="510e3-206">Delete `li`, type `button`, then press `Enter`.</span></span>  <span data-ttu-id="510e3-207">The `<li>` node changes to a `<button>` node.</span><span class="sxs-lookup"><span data-stu-id="510e3-207">The `<li>` node changes to a `<button>` node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-edit-node-type-button.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-edit-node-type-button.msft.png":::
           <span data-ttu-id="510e3-209">Change the node type to</span><span class="sxs-lookup"><span data-stu-id="510e3-209">Change the node type to</span></span> `button`  
        :::image-end:::  
        
### <span data-ttu-id="510e3-210">Reorder DOM nodes</span><span class="sxs-lookup"><span data-stu-id="510e3-210">Reorder DOM nodes</span></span>   

<span data-ttu-id="510e3-211">Drag nodes to reorder them.</span><span class="sxs-lookup"><span data-stu-id="510e3-211">Drag nodes to reorder them.</span></span>  

1.  <span data-ttu-id="510e3-212">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-212">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-213">Under **Reorder DOM Nodes**, right-click **Elvis Presley** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-213">Under **Reorder DOM Nodes**, right-click **Elvis Presley** and select **Inspect**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="510e3-214">It is the last item in the list.</span><span class="sxs-lookup"><span data-stu-id="510e3-214">It is the last item in the list.</span></span>  
    
    1.  <span data-ttu-id="510e3-215">In the DOM Tree, drag `<li>Elvis Presley</li>` to the top of the list.</span><span class="sxs-lookup"><span data-stu-id="510e3-215">In the DOM Tree, drag `<li>Elvis Presley</li>` to the top of the list.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-reorder-dom-nodes.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-reorder-dom-nodes.msft.png":::
           <span data-ttu-id="510e3-217">Drag the node to the top of the list</span><span class="sxs-lookup"><span data-stu-id="510e3-217">Drag the node to the top of the list</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="510e3-218">Force state</span><span class="sxs-lookup"><span data-stu-id="510e3-218">Force state</span></span>   

<span data-ttu-id="510e3-219">You are able to force nodes to remain in states including `:active`, `:hover`, `:focus`, `:visited`, and `:focus-within`.</span><span class="sxs-lookup"><span data-stu-id="510e3-219">You are able to force nodes to remain in states including `:active`, `:hover`, `:focus`, `:visited`, and `:focus-within`.</span></span>  

1.  <span data-ttu-id="510e3-220">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-220">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-221">Under **Force state**, hover over **The Lord of the Flies**.</span><span class="sxs-lookup"><span data-stu-id="510e3-221">Under **Force state**, hover over **The Lord of the Flies**.</span></span>  <span data-ttu-id="510e3-222">The background color becomes orange.</span><span class="sxs-lookup"><span data-stu-id="510e3-222">The background color becomes orange.</span></span>  
    1.  <span data-ttu-id="510e3-223">Right-click **The Lord of the Flies** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-223">Right-click **The Lord of the Flies** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="510e3-224">Right-click `<li class="demo--hover">The Lord of the Flies</li>` and select **Force State** > **:hover**.</span><span class="sxs-lookup"><span data-stu-id="510e3-224">Right-click `<li class="demo--hover">The Lord of the Flies</li>` and select **Force State** > **:hover**.</span></span>  <span data-ttu-id="510e3-225">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span><span class="sxs-lookup"><span data-stu-id="510e3-225">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span></span>  <span data-ttu-id="510e3-226">The background color remains orange even though you are not actually hovering over the node.</span><span class="sxs-lookup"><span data-stu-id="510e3-226">The background color remains orange even though you are not actually hovering over the node.</span></span>  

### <span data-ttu-id="510e3-227">Hide a node</span><span class="sxs-lookup"><span data-stu-id="510e3-227">Hide a node</span></span>   

<span data-ttu-id="510e3-228">Press `H` to hide a node.</span><span class="sxs-lookup"><span data-stu-id="510e3-228">Press `H` to hide a node.</span></span>  

1.  <span data-ttu-id="510e3-229">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-229">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-230">Under **Hide a node**, right-click **The Stars My Destination** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-230">Under **Hide a node**, right-click **The Stars My Destination** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="510e3-231">Press the `H` key.</span><span class="sxs-lookup"><span data-stu-id="510e3-231">Press the `H` key.</span></span>  <span data-ttu-id="510e3-232">The node is hidden.</span><span class="sxs-lookup"><span data-stu-id="510e3-232">The node is hidden.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-hide-a-node.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-hide-a-node.msft.png":::
           <span data-ttu-id="510e3-234">What the node looks like in the DOM Tree after it is hidden</span><span class="sxs-lookup"><span data-stu-id="510e3-234">What the node looks like in the DOM Tree after it is hidden</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="510e3-235">Press the `H` key again.</span><span class="sxs-lookup"><span data-stu-id="510e3-235">Press the `H` key again.</span></span>  <span data-ttu-id="510e3-236">The node is shown again.</span><span class="sxs-lookup"><span data-stu-id="510e3-236">The node is shown again.</span></span>  

### <span data-ttu-id="510e3-237">Delete a node</span><span class="sxs-lookup"><span data-stu-id="510e3-237">Delete a node</span></span>   

<span data-ttu-id="510e3-238">Press `Delete` to delete a node.</span><span class="sxs-lookup"><span data-stu-id="510e3-238">Press `Delete` to delete a node.</span></span>  

1.  <span data-ttu-id="510e3-239">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-239">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-240">Under **Delete a Node**, right-click **Foundation** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-240">Under **Delete a Node**, right-click **Foundation** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="510e3-241">Press the `Delete` key.</span><span class="sxs-lookup"><span data-stu-id="510e3-241">Press the `Delete` key.</span></span>  <span data-ttu-id="510e3-242">The node is deleted.</span><span class="sxs-lookup"><span data-stu-id="510e3-242">The node is deleted.</span></span>  
    1.  <span data-ttu-id="510e3-243">Press `Control`+`Z` \(Windows\) or `Command`+`Z` \(macOS\).</span><span class="sxs-lookup"><span data-stu-id="510e3-243">Press `Control`+`Z` \(Windows\) or `Command`+`Z` \(macOS\).</span></span>  <span data-ttu-id="510e3-244">The last action is undone and the node reappears.</span><span class="sxs-lookup"><span data-stu-id="510e3-244">The last action is undone and the node reappears.</span></span>  

## <span data-ttu-id="510e3-245">Access nodes in the Console</span><span class="sxs-lookup"><span data-stu-id="510e3-245">Access nodes in the Console</span></span>   

<span data-ttu-id="510e3-246">DevTools provides a few shortcuts for accessing DOM nodes from the Console, or getting JavaScript references to each one.</span><span class="sxs-lookup"><span data-stu-id="510e3-246">DevTools provides a few shortcuts for accessing DOM nodes from the Console, or getting JavaScript references to each one.</span></span>  

### <span data-ttu-id="510e3-247">Reference the currently-selected node with $0</span><span class="sxs-lookup"><span data-stu-id="510e3-247">Reference the currently-selected node with $0</span></span>   

<span data-ttu-id="510e3-248">When you inspect a node, the `== $0` text next to the node means that you may reference this node in the Console with the variable `$0`.</span><span class="sxs-lookup"><span data-stu-id="510e3-248">When you inspect a node, the `== $0` text next to the node means that you may reference this node in the Console with the variable `$0`.</span></span>  

1.  <span data-ttu-id="510e3-249">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-249">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-250">Under **Reference the currently-selected node with $0**, right-click **The Left Hand of Darkness** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-250">Under **Reference the currently-selected node with $0**, right-click **The Left Hand of Darkness** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="510e3-251">Press the `Escape` key to open the Console Drawer.</span><span class="sxs-lookup"><span data-stu-id="510e3-251">Press the `Escape` key to open the Console Drawer.</span></span>  
    1.  <span data-ttu-id="510e3-252">Type `$0` and press the `Enter` key.</span><span class="sxs-lookup"><span data-stu-id="510e3-252">Type `$0` and press the `Enter` key.</span></span>  <span data-ttu-id="510e3-253">The result of the expression shows that `$0` evaluates to `<li>The Left Hand of Darkness</li>`.</span><span class="sxs-lookup"><span data-stu-id="510e3-253">The result of the expression shows that `$0` evaluates to `<li>The Left Hand of Darkness</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-1.msft.png":::
            <span data-ttu-id="510e3-255">The result of the first `$0` expression in the **Console**</span><span class="sxs-lookup"><span data-stu-id="510e3-255">The result of the first `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="510e3-256">Hover over the result.</span><span class="sxs-lookup"><span data-stu-id="510e3-256">Hover over the result.</span></span>  <span data-ttu-id="510e3-257">The node is highlighted in the viewport.</span><span class="sxs-lookup"><span data-stu-id="510e3-257">The node is highlighted in the viewport.</span></span>  
    1.  <span data-ttu-id="510e3-258">Click `<li>Dune</li>` in the DOM Tree, type `$0` in the Console again, and then press `Enter` again.</span><span class="sxs-lookup"><span data-stu-id="510e3-258">Click `<li>Dune</li>` in the DOM Tree, type `$0` in the Console again, and then press `Enter` again.</span></span>  <span data-ttu-id="510e3-259">Now, `$0` evaluates to `<li>Dune</li>`.</span><span class="sxs-lookup"><span data-stu-id="510e3-259">Now, `$0` evaluates to `<li>Dune</li>`.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-reference-currently-selected-node-console-2.msft.png":::
           <span data-ttu-id="510e3-261">The result of the second `$0` expression in the **Console**</span><span class="sxs-lookup"><span data-stu-id="510e3-261">The result of the second `$0` expression in the **Console**</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="510e3-262">Store as global variable</span><span class="sxs-lookup"><span data-stu-id="510e3-262">Store as global variable</span></span>   

<span data-ttu-id="510e3-263">If you need to refer back to a node many times, store it as a global variable.</span><span class="sxs-lookup"><span data-stu-id="510e3-263">If you need to refer back to a node many times, store it as a global variable.</span></span>  

1.  <span data-ttu-id="510e3-264">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-264">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-265">Under **Store as global variable**, right-click **The Big Sleep** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-265">Under **Store as global variable**, right-click **The Big Sleep** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="510e3-266">Right-click `<li>The Big Sleep</li>` in the DOM Tree and select **Store as global variable**.</span><span class="sxs-lookup"><span data-stu-id="510e3-266">Right-click `<li>The Big Sleep</li>` in the DOM Tree and select **Store as global variable**.</span></span>  <span data-ttu-id="510e3-267">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span><span class="sxs-lookup"><span data-stu-id="510e3-267">See [Appendix: Missing options](#appendix-missing-options) if you do not see this option.</span></span>  
    1.  <span data-ttu-id="510e3-268">Type `temp1` in the Console and then press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="510e3-268">Type `temp1` in the Console and then press `Enter`.</span></span>  <span data-ttu-id="510e3-269">The result of the expression shows that the variable evaluates to the node.</span><span class="sxs-lookup"><span data-stu-id="510e3-269">The result of the expression shows that the variable evaluates to the node.</span></span>  
        
        :::image type="complex" source="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-store-global-variable-console-temp1.msft.png":::
           <span data-ttu-id="510e3-271">The result of the `temp1` expression</span><span class="sxs-lookup"><span data-stu-id="510e3-271">The result of the `temp1` expression</span></span>  
        :::image-end:::  
        
### <span data-ttu-id="510e3-272">Copy JS path</span><span class="sxs-lookup"><span data-stu-id="510e3-272">Copy JS path</span></span>   

<span data-ttu-id="510e3-273">Copy the JavaScript path to a node when you need to reference it in an automated test.</span><span class="sxs-lookup"><span data-stu-id="510e3-273">Copy the JavaScript path to a node when you need to reference it in an automated test.</span></span>  

1.  <span data-ttu-id="510e3-274">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-274">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-275">Under **Copy JS path**, right-click **The Brothers Karamazov** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-275">Under **Copy JS path**, right-click **The Brothers Karamazov** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="510e3-276">Right-click `<li>The Brothers Karamazov</li>` in the DOM Tree and select **Copy** > **Copy JS Path**.</span><span class="sxs-lookup"><span data-stu-id="510e3-276">Right-click `<li>The Brothers Karamazov</li>` in the DOM Tree and select **Copy** > **Copy JS Path**.</span></span>  <span data-ttu-id="510e3-277">A `document.querySelector()` expression that resolves to the node has been copied to your clipboard.</span><span class="sxs-lookup"><span data-stu-id="510e3-277">A `document.querySelector()` expression that resolves to the node has been copied to your clipboard.</span></span>  
    1.  <span data-ttu-id="510e3-278">Press `Control`+`V` \(Windows\) or `Command`+`V` \(macOS\) to paste the expression into the Console.</span><span class="sxs-lookup"><span data-stu-id="510e3-278">Press `Control`+`V` \(Windows\) or `Command`+`V` \(macOS\) to paste the expression into the Console.</span></span>  
    1.  <span data-ttu-id="510e3-279">Press `Enter` to evaluate the expression.</span><span class="sxs-lookup"><span data-stu-id="510e3-279">Press `Enter` to evaluate the expression.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-copy-js-path-console-query-selector.msft.png":::
           <span data-ttu-id="510e3-281">The result of the **Copy JS Path** expression</span><span class="sxs-lookup"><span data-stu-id="510e3-281">The result of the **Copy JS Path** expression</span></span>  
        :::image-end:::  
        
## <span data-ttu-id="510e3-282">Break on DOM changes</span><span class="sxs-lookup"><span data-stu-id="510e3-282">Break on DOM changes</span></span>   

<span data-ttu-id="510e3-283">DevTools enables you to pause the JavaScript of a page when the JavaScript modifies the DOM.</span><span class="sxs-lookup"><span data-stu-id="510e3-283">DevTools enables you to pause the JavaScript of a page when the JavaScript modifies the DOM.</span></span>  

### <span data-ttu-id="510e3-284">Break on attribute modifications</span><span class="sxs-lookup"><span data-stu-id="510e3-284">Break on attribute modifications</span></span>   

<span data-ttu-id="510e3-285">Use attribute modification breakpoints when you want to pause the JavaScript that causes any attribute of a node to change.</span><span class="sxs-lookup"><span data-stu-id="510e3-285">Use attribute modification breakpoints when you want to pause the JavaScript that causes any attribute of a node to change.</span></span>  

1.  <span data-ttu-id="510e3-286">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-286">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-287">Under **Break on attribute modifications**, right-click **Sauerkraut** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-287">Under **Break on attribute modifications**, right-click **Sauerkraut** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="510e3-288">In the DOM Tree, right-click `<li id="target">Sauerkraut</li>` and select **Break On** > **Attribute Modifications**.</span><span class="sxs-lookup"><span data-stu-id="510e3-288">In the DOM Tree, right-click `<li id="target">Sauerkraut</li>` and select **Break On** > **Attribute Modifications**.</span></span>  <span data-ttu-id="510e3-289">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span><span class="sxs-lookup"><span data-stu-id="510e3-289">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>
        
        :::image type="complex" source="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-break-attribute-modifications-break-on-attribute-modifications.msft.png":::
           **<span data-ttu-id="510e3-291">Break on attribute modifications</span><span class="sxs-lookup"><span data-stu-id="510e3-291">Break on attribute modifications</span></span>**  
        :::image-end:::  
        
    1.  <span data-ttu-id="510e3-292">In the next step you are going to be instructed to click a button that pauses the code of the page.</span><span class="sxs-lookup"><span data-stu-id="510e3-292">In the next step you are going to be instructed to click a button that pauses the code of the page.</span></span>  <span data-ttu-id="510e3-293">After the page is paused you are no longer able to scroll the page.</span><span class="sxs-lookup"><span data-stu-id="510e3-293">After the page is paused you are no longer able to scroll the page.</span></span>  <span data-ttu-id="510e3-294">You must click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\) in order to make the page scrollable again.</span><span class="sxs-lookup"><span data-stu-id="510e3-294">You must click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\) in order to make the page scrollable again.</span></span>
        
        :::image type="complex" source="../media/dom-break-attribute-modifications-sources-paused-on.msft.png" alt-text="Inspect a node" lightbox="../media/dom-break-attribute-modifications-sources-paused-on.msft.png":::
           <span data-ttu-id="510e3-296">Where to resume script running</span><span class="sxs-lookup"><span data-stu-id="510e3-296">Where to resume script running</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="510e3-297">Click the **Set Background** button above.</span><span class="sxs-lookup"><span data-stu-id="510e3-297">Click the **Set Background** button above.</span></span>  <span data-ttu-id="510e3-298">This sets the `style` attribute of the node to `background-color:thistle`.</span><span class="sxs-lookup"><span data-stu-id="510e3-298">This sets the `style` attribute of the node to `background-color:thistle`.</span></span>  <span data-ttu-id="510e3-299">DevTools pauses the page and highlights the code that caused the attribute to change.</span><span class="sxs-lookup"><span data-stu-id="510e3-299">DevTools pauses the page and highlights the code that caused the attribute to change.</span></span>  
    1.  <span data-ttu-id="510e3-300">Click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\), as mentioned earlier.</span><span class="sxs-lookup"><span data-stu-id="510e3-300">Click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\), as mentioned earlier.</span></span>  
    
### <span data-ttu-id="510e3-301">Break on node removal</span><span class="sxs-lookup"><span data-stu-id="510e3-301">Break on node removal</span></span>   

<span data-ttu-id="510e3-302">If you want to pause when a particular node is removed, use node removal breakpoints.</span><span class="sxs-lookup"><span data-stu-id="510e3-302">If you want to pause when a particular node is removed, use node removal breakpoints.</span></span>  

1.  <span data-ttu-id="510e3-303">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-303">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-304">Under **Break on Node Removal**, right-click **Neuromancer** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-304">Under **Break on Node Removal**, right-click **Neuromancer** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="510e3-305">In the DOM Tree, right-click `<li id="target">Neuromancer</li>` and select **Break On** > **Node Removal**.</span><span class="sxs-lookup"><span data-stu-id="510e3-305">In the DOM Tree, right-click `<li id="target">Neuromancer</li>` and select **Break On** > **Node Removal**.</span></span>  <span data-ttu-id="510e3-306">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span><span class="sxs-lookup"><span data-stu-id="510e3-306">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>  
    1.  <span data-ttu-id="510e3-307">Click the **Delete** button above.</span><span class="sxs-lookup"><span data-stu-id="510e3-307">Click the **Delete** button above.</span></span>  <span data-ttu-id="510e3-308">DevTools pauses the page and highlights the code that caused the node to be removed.</span><span class="sxs-lookup"><span data-stu-id="510e3-308">DevTools pauses the page and highlights the code that caused the node to be removed.</span></span>  
    1.  <span data-ttu-id="510e3-309">Click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span><span class="sxs-lookup"><span data-stu-id="510e3-309">Click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
### <span data-ttu-id="510e3-310">Break on subtree modifications</span><span class="sxs-lookup"><span data-stu-id="510e3-310">Break on subtree modifications</span></span>   

<span data-ttu-id="510e3-311">After you put a subtree modification breakpoint on a node, DevTools pauses the page when any of the descendants of the node are added or removed.</span><span class="sxs-lookup"><span data-stu-id="510e3-311">After you put a subtree modification breakpoint on a node, DevTools pauses the page when any of the descendants of the node are added or removed.</span></span>  

1.  <span data-ttu-id="510e3-312">[Open DOM Examples](#open-dom-examples).</span><span class="sxs-lookup"><span data-stu-id="510e3-312">[Open DOM Examples](#open-dom-examples).</span></span>  
1.  <span data-ttu-id="510e3-313">Under **Break on Subtree Modifications**, right-click **A Fire Upon The Deep** and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="510e3-313">Under **Break on Subtree Modifications**, right-click **A Fire Upon The Deep** and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="510e3-314">In the DOM Tree, right-click `<ul id="target">`, which is the node above `<li>A Fire Upon the Deep</li>`, and select **Break On** > **Subtree Modifications**.</span><span class="sxs-lookup"><span data-stu-id="510e3-314">In the DOM Tree, right-click `<ul id="target">`, which is the node above `<li>A Fire Upon the Deep</li>`, and select **Break On** > **Subtree Modifications**.</span></span>  <span data-ttu-id="510e3-315">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span><span class="sxs-lookup"><span data-stu-id="510e3-315">See [Appendix: Missing options](#appendix-missing-options) if you are not able to see this option.</span></span>  
    1.  <span data-ttu-id="510e3-316">Click **Add Child**.</span><span class="sxs-lookup"><span data-stu-id="510e3-316">Click **Add Child**.</span></span>  <span data-ttu-id="510e3-317">The code pauses because a `<li>` node was added to the list.</span><span class="sxs-lookup"><span data-stu-id="510e3-317">The code pauses because a `<li>` node was added to the list.</span></span>  
    1.  <span data-ttu-id="510e3-318">Click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span><span class="sxs-lookup"><span data-stu-id="510e3-318">Click **Resume Script** \(![Resume Script][ImageResumeScriptIcon]\).</span></span>  
    
## <span data-ttu-id="510e3-319">Next steps</span><span class="sxs-lookup"><span data-stu-id="510e3-319">Next steps</span></span>   

<span data-ttu-id="510e3-320">That covers most of the DOM-related features in DevTools.</span><span class="sxs-lookup"><span data-stu-id="510e3-320">That covers most of the DOM-related features in DevTools.</span></span>  <span data-ttu-id="510e3-321">You are able to discover the rest of them by right-clicking nodes in the DOM Tree and experimenting with the other options that were not covered in this tutorial.</span><span class="sxs-lookup"><span data-stu-id="510e3-321">You are able to discover the rest of them by right-clicking nodes in the DOM Tree and experimenting with the other options that were not covered in this tutorial.</span></span>  <span data-ttu-id="510e3-322">See also [Elements panel keyboard shortcuts][DevToolsShortcutsElements].</span><span class="sxs-lookup"><span data-stu-id="510e3-322">See also [Elements panel keyboard shortcuts][DevToolsShortcutsElements].</span></span>  

<span data-ttu-id="510e3-323">Check out the [Microsoft Edge DevTools homepage][MicrosoftEdgeDevTools] to discover everything else you are able to do with DevTools.</span><span class="sxs-lookup"><span data-stu-id="510e3-323">Check out the [Microsoft Edge DevTools homepage][MicrosoftEdgeDevTools] to discover everything else you are able to do with DevTools.</span></span>  

<!--See [Community](../index#community) if you want to contact the DevTools team or get help from the DevTools community.  -->  



## <span data-ttu-id="510e3-324">Appendix: HTML versus the DOM</span><span class="sxs-lookup"><span data-stu-id="510e3-324">Appendix: HTML versus the DOM</span></span>   

<span data-ttu-id="510e3-325">The following section quickly explains the difference between HTML and the DOM.</span><span class="sxs-lookup"><span data-stu-id="510e3-325">The following section quickly explains the difference between HTML and the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="510e3-326">When you use a web browser to request a page, the server returns HTML like the following code snippet</span><span class="sxs-lookup"><span data-stu-id="510e3-326">When you use a web browser to request a page, the server returns HTML like the following code snippet</span></span>  

      ```html
      <!doctype html>
      <html>
          <head>
              <title>Hello, world!</title>
          </head>
          <body>
              <h1>Hello, world!</h1>
              <p>This is a hypertext document on the World Wide Web.</p>
              <script src="/script.js" async></script>
          </body>
      </html>
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="510e3-327">The browser parses the HTML and creates a tree of objects like the following list.</span><span class="sxs-lookup"><span data-stu-id="510e3-327">The browser parses the HTML and creates a tree of objects like the following list.</span></span>  
      
      ```dom
      html
          head
              title
          body
              h1
              p
              script
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="510e3-328">This tree of objects, or nodes, representing the content of the page is called the DOM.</span><span class="sxs-lookup"><span data-stu-id="510e3-328">This tree of objects, or nodes, representing the content of the page is called the DOM.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="510e3-329">Right now it looks the same as the HTML, but suppose that the script referenced at the bottom of the HTML runs the following code snippet.</span><span class="sxs-lookup"><span data-stu-id="510e3-329">Right now it looks the same as the HTML, but suppose that the script referenced at the bottom of the HTML runs the following code snippet.</span></span>  
      
      ```javascript
      const h1 = document.querySelector('h1');
      h1.parentElement.removeChild(h1);
      const p = document.createElement('p');
      p.textContent = 'Wildcard!';
      document.body.appendChild(p);
      ```  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="510e3-330">That code removes the `h1` node and adds another `p` node to the DOM.</span><span class="sxs-lookup"><span data-stu-id="510e3-330">That code removes the `h1` node and adds another `p` node to the DOM.</span></span>  <span data-ttu-id="510e3-331">The complete DOM now displays the following list.</span><span class="sxs-lookup"><span data-stu-id="510e3-331">The complete DOM now displays the following list.</span></span>  
      
      ```dom
      html
          head
              title
          body
              p
              script
              p
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="510e3-332">The HTML for the page is now different than the DOM.</span><span class="sxs-lookup"><span data-stu-id="510e3-332">The HTML for the page is now different than the DOM.</span></span>  <span data-ttu-id="510e3-333">In other words, HTML represents initial page content, and the DOM represents current page content.</span><span class="sxs-lookup"><span data-stu-id="510e3-333">In other words, HTML represents initial page content, and the DOM represents current page content.</span></span>  <span data-ttu-id="510e3-334">When JavaScript adds, removes, or edits nodes, the DOM becomes different than the HTML.</span><span class="sxs-lookup"><span data-stu-id="510e3-334">When JavaScript adds, removes, or edits nodes, the DOM becomes different than the HTML.</span></span>  

<span data-ttu-id="510e3-335">See [Introduction to the DOM][MDNIntroductionToDOM] to learn more.</span><span class="sxs-lookup"><span data-stu-id="510e3-335">See [Introduction to the DOM][MDNIntroductionToDOM] to learn more.</span></span>  

<!--
## Appendix: Scroll into view   

This is a continuation of the [Scroll into view](#scroll-into-view) section.  Follow the instructions below to complete the section.  

1.  The `<li>Magritte</li>` node should still be selected in your DOM Tree.  If not, go back to [Scroll into view](#scroll-into-view) and start over.  
1.  Right-click the `<li>Magritte</li>` node and select **Scroll into view**.  Your viewport scrolls back up so that you may see the **Magritte** node.  See [Appendix: Missing options](#appendix-missing-options) if you are not able to see the **Scroll into view** option.
    
    > ##### Figure 19  
    > Scroll into view  
    > :::image type="complex" source="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-scroll-into-view-dropdown.msft.png":::
   Scroll into view  
:::image-end:::  
    -->  

## <span data-ttu-id="510e3-336">Appendix: Missing options</span><span class="sxs-lookup"><span data-stu-id="510e3-336">Appendix: Missing options</span></span>   

<span data-ttu-id="510e3-337">Many of the instructions in this tutorial instruct you to right-click a node in the DOM Tree and then select an option from the context menu that pops up.</span><span class="sxs-lookup"><span data-stu-id="510e3-337">Many of the instructions in this tutorial instruct you to right-click a node in the DOM Tree and then select an option from the context menu that pops up.</span></span>  <span data-ttu-id="510e3-338">If you do not see the specified option in the context menu, try right-clicking away from the node text.</span><span class="sxs-lookup"><span data-stu-id="510e3-338">If you do not see the specified option in the context menu, try right-clicking away from the node text.</span></span>  

:::image type="complex" source="../media/dom-elements-highlighted-right-click-right-side.msft.png" alt-text="Inspect a node" lightbox="../media/dom-elements-highlighted-right-click-right-side.msft.png":::
   <span data-ttu-id="510e3-340">Where to click if you are not seeing all the options</span><span class="sxs-lookup"><span data-stu-id="510e3-340">Where to click if you are not seeing all the options</span></span>  
:::image-end:::  

<!-- image links -->  

[ImageInspectIcon]: ../media/inspect-icon.msft.png  
[ImageResumeScriptIcon]: ../media/resume-script-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge \(Chromium\) Developer Tools | Microsoft Docs"  
[DevToolsCssGetStarted]: ../css/index.md "Get Started With Viewing And Changing CSS | Microsoft Docs"  
[DevToolsShortcutsElements]: ../shortcuts.md#elements-panel-keyboard-shortcuts "Elements panel keyboard shortcuts - Microsoft Edge DevTools Keyboard Shortcuts | Microsoft Docs"  

[GlitchDomExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/dom "Microsoft Edge (Chromium) DevTools DOM Example | Glitch"

[MDNIntroductionToDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "Introduction to the DOM | MDN"  

> [!NOTE]
> <span data-ttu-id="510e3-346">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="510e3-346">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="510e3-347">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/dom/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="510e3-347">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/dom/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="510e3-349">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="510e3-349">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
