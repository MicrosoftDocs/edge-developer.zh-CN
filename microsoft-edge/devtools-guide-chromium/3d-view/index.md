---
description: All about 3D View and how to use it.
title: 3D View
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: ba1125654c46be6ef4da99efc9ba027ba5e40672
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986078"
---
# <span data-ttu-id="b3622-104">3D View</span><span class="sxs-lookup"><span data-stu-id="b3622-104">3D View</span></span>  

<span data-ttu-id="b3622-105">Use the **3D View** to debug your web application by navigating through the [Document Object Model (DOM)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span><span class="sxs-lookup"><span data-stu-id="b3622-105">Use the **3D View** to debug your web application by navigating through the [Document Object Model (DOM)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  <span data-ttu-id="b3622-106">With it you are able to perform the following tasks.</span><span class="sxs-lookup"><span data-stu-id="b3622-106">With it you are able to perform the following tasks.</span></span>  

*   [<span data-ttu-id="b3622-107">Explore the web page translated into a 3D perspective</span><span class="sxs-lookup"><span data-stu-id="b3622-107">Explore the web page translated into a 3D perspective</span></span>](#3d-dom)  
*   [<span data-ttu-id="b3622-108">Debug based on z-index stacking context</span><span class="sxs-lookup"><span data-stu-id="b3622-108">Debug based on z-index stacking context</span></span>](#z-index)  
*   <span data-ttu-id="b3622-109">[Clear some of the clutter on the DOM pane](#changing-your-view) or the [z-index pane](#change-the-scope-of-your-exploration)</span><span class="sxs-lookup"><span data-stu-id="b3622-109">[Clear some of the clutter on the DOM pane](#changing-your-view) or the [z-index pane](#change-the-scope-of-your-exploration)</span></span>  
*   <span data-ttu-id="b3622-110">[Pick the color scheme to best debug your DOM problems](#dom-color-type) or [z-index problems](#z-index-color-type)</span><span class="sxs-lookup"><span data-stu-id="b3622-110">[Pick the color scheme to best debug your DOM problems](#dom-color-type) or [z-index problems](#z-index-color-type)</span></span>  

<span data-ttu-id="b3622-111">If you want to explore an early prototype of 3D View project and run the code yourself, see [3D View Sample][GithubMicrosoftedgeDevtoolssamples3dview].</span><span class="sxs-lookup"><span data-stu-id="b3622-111">If you want to explore an early prototype of 3D View project and run the code yourself, see [3D View Sample][GithubMicrosoftedgeDevtoolssamples3dview].</span></span>   

<span data-ttu-id="b3622-112">On the left side, there are two panes that you are able to use for your debugging experience.</span><span class="sxs-lookup"><span data-stu-id="b3622-112">On the left side, there are two panes that you are able to use for your debugging experience.</span></span>  

1.  <span data-ttu-id="b3622-113">The [Z-index](#z-index) pane.</span><span class="sxs-lookup"><span data-stu-id="b3622-113">The [Z-index](#z-index) pane.</span></span>  <span data-ttu-id="b3622-114">Navigate through the different elements in the web application with the z-index context in mind.</span><span class="sxs-lookup"><span data-stu-id="b3622-114">Navigate through the different elements in the web application with the z-index context in mind.</span></span>  <span data-ttu-id="b3622-115">The **Z-index** pane is the default pane.</span><span class="sxs-lookup"><span data-stu-id="b3622-115">The **Z-index** pane is the default pane.</span></span>  
1.  <span data-ttu-id="b3622-116">The [3D DOM](#3d-dom) pane.</span><span class="sxs-lookup"><span data-stu-id="b3622-116">The [3D DOM](#3d-dom) pane.</span></span>  <span data-ttu-id="b3622-117">Explore the DOM as a whole with all the elements at your fingertips.</span><span class="sxs-lookup"><span data-stu-id="b3622-117">Explore the DOM as a whole with all the elements at your fingertips.</span></span>  <span data-ttu-id="b3622-118">To access the pane, select on the **DOM** pane next to the **Z-index** pane.</span><span class="sxs-lookup"><span data-stu-id="b3622-118">To access the pane, select on the **DOM** pane next to the **Z-index** pane.</span></span>  
    
<span data-ttu-id="b3622-119">On the right side, the canvas displays your selections from the [Z-index](#z-index) or [3D DOM](#3d-dom).</span><span class="sxs-lookup"><span data-stu-id="b3622-119">On the right side, the canvas displays your selections from the [Z-index](#z-index) or [3D DOM](#3d-dom).</span></span>  

## <span data-ttu-id="b3622-120">Navigating the canvas</span><span class="sxs-lookup"><span data-stu-id="b3622-120">Navigating the canvas</span></span>  

:::image type="complex" source="../media/canvas.png" alt-text="Canvas of 3D View" lightbox="../media/canvas.png":::
   <span data-ttu-id="b3622-122">Canvas of 3D View</span><span class="sxs-lookup"><span data-stu-id="b3622-122">Canvas of 3D View</span></span>  
:::image-end:::  

### <span data-ttu-id="b3622-123">Keyboard shortcuts</span><span class="sxs-lookup"><span data-stu-id="b3622-123">Keyboard shortcuts</span></span>  

*   <span data-ttu-id="b3622-124">Rotate the DOM:  To rotate horizontally, press the `left-arrow` and `right-arrow` keys.</span><span class="sxs-lookup"><span data-stu-id="b3622-124">Rotate the DOM:  To rotate horizontally, press the `left-arrow` and `right-arrow` keys.</span></span>  <span data-ttu-id="b3622-125">To rotate vertically, press the `up-arrow` and `down-arrow` keys.</span><span class="sxs-lookup"><span data-stu-id="b3622-125">To rotate vertically, press the `up-arrow` and `down-arrow` keys.</span></span>  
*   <span data-ttu-id="b3622-126">Navigate the DOM:  To move through the adjacent elements, select an element and press the `up-arrow` and `down-arrow` keys.</span><span class="sxs-lookup"><span data-stu-id="b3622-126">Navigate the DOM:  To move through the adjacent elements, select an element and press the `up-arrow` and `down-arrow` keys.</span></span>  

### <span data-ttu-id="b3622-127">Mouse controls</span><span class="sxs-lookup"><span data-stu-id="b3622-127">Mouse controls</span></span>  

*   <span data-ttu-id="b3622-128">Rotate the DOM:  Select and drag around the canvas space.</span><span class="sxs-lookup"><span data-stu-id="b3622-128">Rotate the DOM:  Select and drag around the canvas space.</span></span>  
*   <span data-ttu-id="b3622-129">Pan around the DOM:  Open the contextual menu \(right-click\) and drag in the direction you want the DOM to move.</span><span class="sxs-lookup"><span data-stu-id="b3622-129">Pan around the DOM:  Open the contextual menu \(right-click\) and drag in the direction you want the DOM to move.</span></span>  
*   <span data-ttu-id="b3622-130">Zoom:  Drag two fingers across the touchpad or use the scroll wheel on your mouse.</span><span class="sxs-lookup"><span data-stu-id="b3622-130">Zoom:  Drag two fingers across the touchpad or use the scroll wheel on your mouse.</span></span>  

### <span data-ttu-id="b3622-131">On-screen controls</span><span class="sxs-lookup"><span data-stu-id="b3622-131">On-screen controls</span></span>  

:::image type="complex" source="../media/controls-small.png" alt-text="Canvas of 3D View" lightbox="../media/controls-small.png":::
   <span data-ttu-id="b3622-133">On-screen controls</span><span class="sxs-lookup"><span data-stu-id="b3622-133">On-screen controls</span></span>  
:::image-end:::  

*   <span data-ttu-id="b3622-134">Reset the canvas view to the original view:  Select the **Reset camera** button, or select the **Reset elements in view and re-center camera** \(sideways refresh icon\) button.</span><span class="sxs-lookup"><span data-stu-id="b3622-134">Reset the canvas view to the original view:  Select the **Reset camera** button, or select the **Reset elements in view and re-center camera** \(sideways refresh icon\) button.</span></span>  
*   <span data-ttu-id="b3622-135">Refresh the canvas \(for example, if the browser changed or you switched to a device emulator view\):  Select the **Retake snapshot** button or select the **Take new snapshot** button \(refresh icon\).</span><span class="sxs-lookup"><span data-stu-id="b3622-135">Refresh the canvas \(for example, if the browser changed or you switched to a device emulator view\):  Select the **Retake snapshot** button or select the **Take new snapshot** button \(refresh icon\).</span></span>  

## <span data-ttu-id="b3622-136">Z-index</span><span class="sxs-lookup"><span data-stu-id="b3622-136">Z-index</span></span>  

:::image type="complex" source="../media/z-index-view-box.png" alt-text="Canvas of 3D View" lightbox="../media/z-index-view-box.png":::
   <span data-ttu-id="b3622-138">Z-index view</span><span class="sxs-lookup"><span data-stu-id="b3622-138">Z-index view</span></span>  
:::image-end:::  

<span data-ttu-id="b3622-139">While the **Z-index** pane has shared features with the **3D DOM** pane, the panes still have elements that are unique to the pane.</span><span class="sxs-lookup"><span data-stu-id="b3622-139">While the **Z-index** pane has shared features with the **3D DOM** pane, the panes still have elements that are unique to the pane.</span></span>  

### <span data-ttu-id="b3622-140">Highlight elements with stacking context</span><span class="sxs-lookup"><span data-stu-id="b3622-140">Highlight elements with stacking context</span></span>  

<span data-ttu-id="b3622-141">The **Highlight elements with stacking context** setting allows you to turn on \(and off\) the z-index tags for the elements on the canvas.</span><span class="sxs-lookup"><span data-stu-id="b3622-141">The **Highlight elements with stacking context** setting allows you to turn on \(and off\) the z-index tags for the elements on the canvas.</span></span>  <span data-ttu-id="b3622-142">The checkbox is selected by default.</span><span class="sxs-lookup"><span data-stu-id="b3622-142">The checkbox is selected by default.</span></span>  

### <span data-ttu-id="b3622-143">Change the scope of your exploration</span><span class="sxs-lookup"><span data-stu-id="b3622-143">Change the scope of your exploration</span></span>  

<span data-ttu-id="b3622-144">The **Show all elements** button is the quickest way to display all the elements of the DOM after changing the settings below.</span><span class="sxs-lookup"><span data-stu-id="b3622-144">The **Show all elements** button is the quickest way to display all the elements of the DOM after changing the settings below.</span></span>  

<span data-ttu-id="b3622-145">The **Show only elements with stacking context** button removes elements without stacking context and flattens the DOM for easier navigation.</span><span class="sxs-lookup"><span data-stu-id="b3622-145">The **Show only elements with stacking context** button removes elements without stacking context and flattens the DOM for easier navigation.</span></span>  

<span data-ttu-id="b3622-146">The **Isolate selected element** button is essentially three buttons in one.</span><span class="sxs-lookup"><span data-stu-id="b3622-146">The **Isolate selected element** button is essentially three buttons in one.</span></span>  <span data-ttu-id="b3622-147">There are two checkboxes below the **Isolate selected element** button:  The **Show all parents** checkbox and **Keep only parents with new stacking context** checkbox.</span><span class="sxs-lookup"><span data-stu-id="b3622-147">There are two checkboxes below the **Isolate selected element** button:  The **Show all parents** checkbox and **Keep only parents with new stacking context** checkbox.</span></span>  

<span data-ttu-id="b3622-148">The **Show all parents** checkbox is selected by default.</span><span class="sxs-lookup"><span data-stu-id="b3622-148">The **Show all parents** checkbox is selected by default.</span></span>  <span data-ttu-id="b3622-149">If you select an element on the canvas pane and select **Isolate selected element** button, the canvas only displays the element and any parents.</span><span class="sxs-lookup"><span data-stu-id="b3622-149">If you select an element on the canvas pane and select **Isolate selected element** button, the canvas only displays the element and any parents.</span></span>  

<span data-ttu-id="b3622-150">If you select the **Keep only parents with new stacking context** checkbox, and select **Isolate selected element** button, the canvas only displays the element and the parents that have a new stacking context.</span><span class="sxs-lookup"><span data-stu-id="b3622-150">If you select the **Keep only parents with new stacking context** checkbox, and select **Isolate selected element** button, the canvas only displays the element and the parents that have a new stacking context.</span></span>  

<span data-ttu-id="b3622-151">If you deselect both of the checkboxes and select **Isolate selected element** button, the canvas only displays the element you chose in the first place.</span><span class="sxs-lookup"><span data-stu-id="b3622-151">If you deselect both of the checkboxes and select **Isolate selected element** button, the canvas only displays the element you chose in the first place.</span></span>  

<span data-ttu-id="b3622-152">At the very bottom of the **3D DOM** panel, locate the **Hide elements with the same paint order as their parent** checkbox.</span><span class="sxs-lookup"><span data-stu-id="b3622-152">At the very bottom of the **3D DOM** panel, locate the **Hide elements with the same paint order as their parent** checkbox.</span></span>  <span data-ttu-id="b3622-153">Selecting and deselecting the checkbox refreshes the elements based on your selection.</span><span class="sxs-lookup"><span data-stu-id="b3622-153">Selecting and deselecting the checkbox refreshes the elements based on your selection.</span></span>  <span data-ttu-id="b3622-154">If selected, elements that share paint order are flattened to the parent.</span><span class="sxs-lookup"><span data-stu-id="b3622-154">If selected, elements that share paint order are flattened to the parent.</span></span>  

<span data-ttu-id="b3622-155">The options are meant to clear up some of the clutter that more complex web pages create in your canvas.</span><span class="sxs-lookup"><span data-stu-id="b3622-155">The options are meant to clear up some of the clutter that more complex web pages create in your canvas.</span></span>  

### <span data-ttu-id="b3622-156">Z-index color type</span><span class="sxs-lookup"><span data-stu-id="b3622-156">Z-index color type</span></span>  

<span data-ttu-id="b3622-157">The are the different visualizations you may use for the DOM in your canvas.</span><span class="sxs-lookup"><span data-stu-id="b3622-157">The are the different visualizations you may use for the DOM in your canvas.</span></span>  <span data-ttu-id="b3622-158">Whether you use it for fun or because the visualizations help you visualize the DOM better, The DevTools has three different colorways as well as a **background color** setting.</span><span class="sxs-lookup"><span data-stu-id="b3622-158">Whether you use it for fun or because the visualizations help you visualize the DOM better, The DevTools has three different colorways as well as a **background color** setting.</span></span>  <span data-ttu-id="b3622-159">The radio buttons allow you to toggle through the options and pick the color type most appropriate for your project \(or that you like the most\).</span><span class="sxs-lookup"><span data-stu-id="b3622-159">The radio buttons allow you to toggle through the options and pick the color type most appropriate for your project \(or that you like the most\).</span></span>  

## <span data-ttu-id="b3622-160">3D DOM</span><span class="sxs-lookup"><span data-stu-id="b3622-160">3D DOM</span></span>  

:::image type="complex" source="../media/dom-purple-box.png" alt-text="Canvas of 3D View" lightbox="../media/dom-purple-box.png":::
   <span data-ttu-id="b3622-162">DOM view</span><span class="sxs-lookup"><span data-stu-id="b3622-162">DOM view</span></span>  
:::image-end:::  

<span data-ttu-id="b3622-163">If you want to take more of a general debugging view, rather than the z-index experience, the **3D DOM** gives an overall look of the DOM.</span><span class="sxs-lookup"><span data-stu-id="b3622-163">If you want to take more of a general debugging view, rather than the z-index experience, the **3D DOM** gives an overall look of the DOM.</span></span>  <span data-ttu-id="b3622-164">Since the z-index context is removed, the DOM is stacked more closely and cleanly.</span><span class="sxs-lookup"><span data-stu-id="b3622-164">Since the z-index context is removed, the DOM is stacked more closely and cleanly.</span></span>  <span data-ttu-id="b3622-165">The **3D DOM** pane has similar functionality, but there are a few nuances.</span><span class="sxs-lookup"><span data-stu-id="b3622-165">The **3D DOM** pane has similar functionality, but there are a few nuances.</span></span>  

### <span data-ttu-id="b3622-166">Changing your view</span><span class="sxs-lookup"><span data-stu-id="b3622-166">Changing your view</span></span>  

<span data-ttu-id="b3622-167">On the **3D DOM** pane, the **Isolate selected element** button has **Include children** and **Include parents** checkboxes.</span><span class="sxs-lookup"><span data-stu-id="b3622-167">On the **3D DOM** pane, the **Isolate selected element** button has **Include children** and **Include parents** checkboxes.</span></span>  <span data-ttu-id="b3622-168">By default both checkboxes are selected, which means that selecting the **Isolate selected element** button after selecting an element on the canvas should display the element chosen, the parents of the element, and the children of the element.</span><span class="sxs-lookup"><span data-stu-id="b3622-168">By default both checkboxes are selected, which means that selecting the **Isolate selected element** button after selecting an element on the canvas should display the element chosen, the parents of the element, and the children of the element.</span></span>  <span data-ttu-id="b3622-169">Deselecting the **Include children** checkbox and selecting the **Isolate selected element** button again should display the selected element and the parents of the element.</span><span class="sxs-lookup"><span data-stu-id="b3622-169">Deselecting the **Include children** checkbox and selecting the **Isolate selected element** button again should display the selected element and the parents of the element.</span></span>  <span data-ttu-id="b3622-170">If you select the **Include children** checkbox and deselect the **Include parents** checkbox before selecting **Isolate selected element** button, the canvas then displays the element and any children.</span><span class="sxs-lookup"><span data-stu-id="b3622-170">If you select the **Include children** checkbox and deselect the **Include parents** checkbox before selecting **Isolate selected element** button, the canvas then displays the element and any children.</span></span>  <span data-ttu-id="b3622-171">If you deselect both checkboxes and select **Isolate selected element** button, the canvas only displays the element you previously selected.</span><span class="sxs-lookup"><span data-stu-id="b3622-171">If you deselect both checkboxes and select **Isolate selected element** button, the canvas only displays the element you previously selected.</span></span>  

<span data-ttu-id="b3622-172">A slider on the control pane titled **Nesting level for page** with a number next to it.</span><span class="sxs-lookup"><span data-stu-id="b3622-172">A slider on the control pane titled **Nesting level for page** with a number next to it.</span></span>  <span data-ttu-id="b3622-173">The number indicates the number of layers for the document.</span><span class="sxs-lookup"><span data-stu-id="b3622-173">The number indicates the number of layers for the document.</span></span>  <span data-ttu-id="b3622-174">Dragging the slider to the left causes the outermost layers to peel away until you are left with a nesting level set to 1, which displays only the furthest back element in the DOM.</span><span class="sxs-lookup"><span data-stu-id="b3622-174">Dragging the slider to the left causes the outermost layers to peel away until you are left with a nesting level set to 1, which displays only the furthest back element in the DOM.</span></span>  <span data-ttu-id="b3622-175">Dragging the slider allows you to remove some of the clutter if you are trying to get a closer look at what is happening in the lower levels.</span><span class="sxs-lookup"><span data-stu-id="b3622-175">Dragging the slider allows you to remove some of the clutter if you are trying to get a closer look at what is happening in the lower levels.</span></span>  

### <span data-ttu-id="b3622-176">DOM color type</span><span class="sxs-lookup"><span data-stu-id="b3622-176">DOM color type</span></span>  

<span data-ttu-id="b3622-177">In addition to the **Heatmap - Purple to White**, **Heatmap - Blue to Yellow**, **Heatmap - Rainbow**, and **Use background color** radio buttons, there is **Use screen texture**.</span><span class="sxs-lookup"><span data-stu-id="b3622-177">In addition to the **Heatmap - Purple to White**, **Heatmap - Blue to Yellow**, **Heatmap - Rainbow**, and **Use background color** radio buttons, there is **Use screen texture**.</span></span>  <span data-ttu-id="b3622-178">The screen texture adds context to your debugging experience by displaying the content from the web page directly onto the elements.</span><span class="sxs-lookup"><span data-stu-id="b3622-178">The screen texture adds context to your debugging experience by displaying the content from the web page directly onto the elements.</span></span>  <span data-ttu-id="b3622-179">On the **3D DOM** pane, the  **color type** setting is still a work in progress, since some websites have a harder time rendering screen texture in the 3D View.</span><span class="sxs-lookup"><span data-stu-id="b3622-179">On the **3D DOM** pane, the  **color type** setting is still a work in progress, since some websites have a harder time rendering screen texture in the 3D View.</span></span>  

## <span data-ttu-id="b3622-180">Getting in touch with the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="b3622-180">Getting in touch with the Microsoft Edge DevTools team</span></span>

<span data-ttu-id="b3622-181">The Microsoft Edge Devtools team is working on the UI and adding more functionality to the 3D View based on asks from users like you.</span><span class="sxs-lookup"><span data-stu-id="b3622-181">The Microsoft Edge Devtools team is working on the UI and adding more functionality to the 3D View based on asks from users like you.</span></span>  <span data-ttu-id="b3622-182">Please send your feedback to help improve the Microsoft Edge DevTools.</span><span class="sxs-lookup"><span data-stu-id="b3622-182">Please send your feedback to help improve the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="b3622-183">Simply select the feedback icon in the DevTools or press `Alt`+`Shift`+`I` \(Windows\) or press `Option`+`Shift`+`I` \(macOS\) and enter any feedback or feature requests you have for the DevTools.</span><span class="sxs-lookup"><span data-stu-id="b3622-183">Simply select the feedback icon in the DevTools or press `Alt`+`Shift`+`I` \(Windows\) or press `Option`+`Shift`+`I` \(macOS\) and enter any feedback or feature requests you have for the DevTools.</span></span>  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamples3dview]: https://github.com/MicrosoftEdge/DevToolsSamples/tree/master/3DView "Microsoft Edge DevTools 3D View - MicrosoftEdge/DevToolsSamples | GitHub"  

[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "Document Object Model (DOM) | MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index | MDN"  
