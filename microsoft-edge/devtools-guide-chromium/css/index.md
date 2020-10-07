---
description: Learn how to use Microsoft Edge DevTools to view and change the CSS of a page.
title: Get Started With Viewing And Changing CSS
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: f055606ff6140652341627097e7fe7b270dc929c
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993063"
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

# <span data-ttu-id="ab290-104">Get Started With Viewing And Changing CSS</span><span class="sxs-lookup"><span data-stu-id="ab290-104">Get Started With Viewing And Changing CSS</span></span>  

<span data-ttu-id="ab290-105">Complete these interactive tutorials to learn the basics of viewing and changing the CSS for a page using Microsoft Edge DevTools.</span><span class="sxs-lookup"><span data-stu-id="ab290-105">Complete these interactive tutorials to learn the basics of viewing and changing the CSS for a page using Microsoft Edge DevTools.</span></span>  

## <span data-ttu-id="ab290-106">Open CSS Examples</span><span class="sxs-lookup"><span data-stu-id="ab290-106">Open CSS Examples</span></span>  

1.  <span data-ttu-id="ab290-107">Hold `Control` \(Windows\) or `Command` \(macOS\) and select **CSS Examples** to open in a new window.</span><span class="sxs-lookup"><span data-stu-id="ab290-107">Hold `Control` \(Windows\) or `Command` \(macOS\) and select **CSS Examples** to open in a new window.</span></span>  
    
    [<span data-ttu-id="ab290-108">CSS Examples</span><span class="sxs-lookup"><span data-stu-id="ab290-108">CSS Examples</span></span>][GlitchDevToolsCssExamples]  
    
    > [!NOTE]
    > <span data-ttu-id="ab290-109">If you want to [dock your DevTools window][DevToolsCustomizePlacement] to the right of your viewport \(displayed in the following figure\), select **Customize and control DevTools** `...`.</span><span class="sxs-lookup"><span data-stu-id="ab290-109">If you want to [dock your DevTools window][DevToolsCustomizePlacement] to the right of your viewport \(displayed in the following figure\), select **Customize and control DevTools** `...`.</span></span>  <span data-ttu-id="ab290-110">On the **Customize and control DevTools** drop-down menu, in the **Dock side** section, select **Dock to right**.</span><span class="sxs-lookup"><span data-stu-id="ab290-110">On the **Customize and control DevTools** drop-down menu, in the **Dock side** section, select **Dock to right**.</span></span>  
    
## <span data-ttu-id="ab290-111">View the CSS for an element</span><span class="sxs-lookup"><span data-stu-id="ab290-111">View the CSS for an element</span></span>  

1.  <span data-ttu-id="ab290-112">[Open CSS Examples](#open-css-examples).</span><span class="sxs-lookup"><span data-stu-id="ab290-112">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="ab290-113">Hover on the `Inspect Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="ab290-113">Hover on the `Inspect Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="ab290-114">In DevTools, on the **Elements** panel, in the **DOM Tree** tab, the `Inspect Me!` element is highlighted.</span><span class="sxs-lookup"><span data-stu-id="ab290-114">In DevTools, on the **Elements** panel, in the **DOM Tree** tab, the `Inspect Me!` element is highlighted.</span></span>  
        
        :::image type="complex" source="../media/css-elements-inspect-me.msft.png" alt-text="The inspected element is highlighted in the DOM Tree" lightbox="../media/css-elements-inspect-me.msft.png":::
           <span data-ttu-id="ab290-116">Figure 1:  The inspected element is highlighted in the **DOM Tree**</span><span class="sxs-lookup"><span data-stu-id="ab290-116">Figure 1:  The inspected element is highlighted in the **DOM Tree**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="ab290-117">In the `Inspect Me!` element, find the value of the `data-message` attribute and copy it.</span><span class="sxs-lookup"><span data-stu-id="ab290-117">In the `Inspect Me!` element, find the value of the `data-message` attribute and copy it.</span></span>  
1.  <span data-ttu-id="ab290-118">On the page, in the **Value of `data-message`:** textbox, enter the value.</span><span class="sxs-lookup"><span data-stu-id="ab290-118">On the page, in the **Value of `data-message`:** textbox, enter the value.</span></span>  
1.  <span data-ttu-id="ab290-119">Hover on the `Inspect Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="ab290-119">Hover on the `Inspect Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="ab290-120">In DevTools, on the **Elements** panel, select the **Styles** tab.</span><span class="sxs-lookup"><span data-stu-id="ab290-120">In DevTools, on the **Elements** panel, select the **Styles** tab.</span></span>  
    1.  <span data-ttu-id="ab290-121">In the **Styles** tab, the `Inspect Me!` element is highlighted.</span><span class="sxs-lookup"><span data-stu-id="ab290-121">In the **Styles** tab, the `Inspect Me!` element is highlighted.</span></span>  
    1.  <span data-ttu-id="ab290-122">In the `Inspect Me!` element, find the `aloha` class rule.</span><span class="sxs-lookup"><span data-stu-id="ab290-122">In the `Inspect Me!` element, find the `aloha` class rule.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="ab290-123">You see this rule because it is being applied to the `Inspect Me!` element.</span><span class="sxs-lookup"><span data-stu-id="ab290-123">You see this rule because it is being applied to the `Inspect Me!` element.</span></span>  
        
    1.  <span data-ttu-id="ab290-124">In the `aloha` class, find the value for the `padding` style and copy it.</span><span class="sxs-lookup"><span data-stu-id="ab290-124">In the `aloha` class, find the value for the `padding` style and copy it.</span></span>  
        
        :::image type="complex" source="../media/css-elements-inspect-me-styles.msft.png" alt-text="The inspected element is highlighted in the DOM Tree" lightbox="../media/css-elements-inspect-me-styles.msft.png":::
           <span data-ttu-id="ab290-126">Figure 2:  CSS classes being applied to the selected element, such as `aloha`, are displayed in the **Styles** tab</span><span class="sxs-lookup"><span data-stu-id="ab290-126">Figure 2:  CSS classes being applied to the selected element, such as `aloha`, are displayed in the **Styles** tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="ab290-127">On the page, in the **Value of `padding`:** textbox, enter the value.</span><span class="sxs-lookup"><span data-stu-id="ab290-127">On the page, in the **Value of `padding`:** textbox, enter the value.</span></span>  

## <span data-ttu-id="ab290-128">Add a CSS declaration to an element</span><span class="sxs-lookup"><span data-stu-id="ab290-128">Add a CSS declaration to an element</span></span>  

<span data-ttu-id="ab290-129">Use the **Styles** tab when you want to change or add CSS declarations to an element.</span><span class="sxs-lookup"><span data-stu-id="ab290-129">Use the **Styles** tab when you want to change or add CSS declarations to an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="ab290-130">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span><span class="sxs-lookup"><span data-stu-id="ab290-130">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="ab290-131">[Open CSS Examples](#open-css-examples).</span><span class="sxs-lookup"><span data-stu-id="ab290-131">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="ab290-132">Hover on the `Add A Background Color To Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="ab290-132">Hover on the `Add A Background Color To Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
1.  <span data-ttu-id="ab290-133">Select `element.style` near the top of the **Styles** tab.</span><span class="sxs-lookup"><span data-stu-id="ab290-133">Select `element.style` near the top of the **Styles** tab.</span></span>  
1.  <span data-ttu-id="ab290-134">Type `background-color` and press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="ab290-134">Type `background-color` and press `Enter`.</span></span>  
1.  <span data-ttu-id="ab290-135">Type `honeydew` and press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="ab290-135">Type `honeydew` and press `Enter`.</span></span>  <span data-ttu-id="ab290-136">In the **DOM Tree** you should see that an inline style declaration was applied to the element.</span><span class="sxs-lookup"><span data-stu-id="ab290-136">In the **DOM Tree** you should see that an inline style declaration was applied to the element.</span></span>  
    
    :::image type="complex" source="../media/css-elements-add-background-color-to-me-styles-p.msft.png" alt-text="The inspected element is highlighted in the DOM Tree" lightbox="../media/css-elements-add-background-color-to-me-styles-p.msft.png":::
       <span data-ttu-id="ab290-138">Figure 3:  The `background-color:honeydew` declaration has been applied to the element using the `element.style` section of the **Styles** tab</span><span class="sxs-lookup"><span data-stu-id="ab290-138">Figure 3:  The `background-color:honeydew` declaration has been applied to the element using the `element.style` section of the **Styles** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="ab290-139">Add a CSS class to an element</span><span class="sxs-lookup"><span data-stu-id="ab290-139">Add a CSS class to an element</span></span>  

<span data-ttu-id="ab290-140">Use the **Styles** tab to see how an element looks when a CSS class is applied to or removed from an element.</span><span class="sxs-lookup"><span data-stu-id="ab290-140">Use the **Styles** tab to see how an element looks when a CSS class is applied to or removed from an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="ab290-141">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span><span class="sxs-lookup"><span data-stu-id="ab290-141">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="ab290-142">[Open CSS Examples](#open-css-examples).</span><span class="sxs-lookup"><span data-stu-id="ab290-142">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="ab290-143">Hover on the `Add A Class To Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="ab290-143">Hover on the `Add A Class To Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
1.  <span data-ttu-id="ab290-144">Select **.cls**.</span><span class="sxs-lookup"><span data-stu-id="ab290-144">Select **.cls**.</span></span>  <span data-ttu-id="ab290-145">DevTools reveals a text box where you may add classes to the selected element.</span><span class="sxs-lookup"><span data-stu-id="ab290-145">DevTools reveals a text box where you may add classes to the selected element.</span></span>  
1.  <span data-ttu-id="ab290-146">Type `color_me` in the **Add new class** text box and then press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="ab290-146">Type `color_me` in the **Add new class** text box and then press `Enter`.</span></span>  <span data-ttu-id="ab290-147">A checkbox appears below the **Add new class** text box, where you may toggle the class on and off.</span><span class="sxs-lookup"><span data-stu-id="ab290-147">A checkbox appears below the **Add new class** text box, where you may toggle the class on and off.</span></span>  <span data-ttu-id="ab290-148">If the `Add A Class To Me!` element has any other classes applied to it, you are also able to toggle each from here.</span><span class="sxs-lookup"><span data-stu-id="ab290-148">If the `Add A Class To Me!` element has any other classes applied to it, you are also able to toggle each from here.</span></span>  
    
    :::image type="complex" source="../media/css-elements-add-a-class-to-me-styles-cls.msft.png" alt-text="The inspected element is highlighted in the DOM Tree" lightbox="../media/css-elements-add-a-class-to-me-styles-cls.msft.png":::
       <span data-ttu-id="ab290-150">Figure 4:  The `color_me` class has been applied to the element using the **.cls** section of the **Styles** tab</span><span class="sxs-lookup"><span data-stu-id="ab290-150">Figure 4:  The `color_me` class has been applied to the element using the **.cls** section of the **Styles** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="ab290-151">Add a pseudostate to a class</span><span class="sxs-lookup"><span data-stu-id="ab290-151">Add a pseudostate to a class</span></span>  

<span data-ttu-id="ab290-152">Use the **Styles** tab to permanently apply a CSS pseudostate to an element.</span><span class="sxs-lookup"><span data-stu-id="ab290-152">Use the **Styles** tab to permanently apply a CSS pseudostate to an element.</span></span>  <span data-ttu-id="ab290-153">DevTools supports `:active`, `:focus`, `:hover`, and `:visited`.</span><span class="sxs-lookup"><span data-stu-id="ab290-153">DevTools supports `:active`, `:focus`, `:hover`, and `:visited`.</span></span>  

> [!NOTE]
> <span data-ttu-id="ab290-154">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span><span class="sxs-lookup"><span data-stu-id="ab290-154">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="ab290-155">[Open CSS Examples](#open-css-examples).</span><span class="sxs-lookup"><span data-stu-id="ab290-155">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="ab290-156">Hover over the `Hover Over Me!` text.</span><span class="sxs-lookup"><span data-stu-id="ab290-156">Hover over the `Hover Over Me!` text.</span></span>  <span data-ttu-id="ab290-157">The background color changes.</span><span class="sxs-lookup"><span data-stu-id="ab290-157">The background color changes.</span></span>  
1.  <span data-ttu-id="ab290-158">Hover on the `Hover Over Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="ab290-158">Hover on the `Hover Over Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
1.  <span data-ttu-id="ab290-159">In the **Styles** tab, select **:hov**.</span><span class="sxs-lookup"><span data-stu-id="ab290-159">In the **Styles** tab, select **:hov**.</span></span>  
1.  <span data-ttu-id="ab290-160">Check the **:hover** checkbox.</span><span class="sxs-lookup"><span data-stu-id="ab290-160">Check the **:hover** checkbox.</span></span>  <span data-ttu-id="ab290-161">The background color changes like before, even though you are not actually hovering over the element.</span><span class="sxs-lookup"><span data-stu-id="ab290-161">The background color changes like before, even though you are not actually hovering over the element.</span></span>  
    
    :::image type="complex" source="../media/css-elements-hover-over-me-styles-hov-hover.msft.png" alt-text="The inspected element is highlighted in the DOM Tree" lightbox="../media/css-elements-hover-over-me-styles-hov-hover.msft.png":::
       <span data-ttu-id="ab290-163">Figure 5:  Toggling the `:hover` pseudostate on an element</span><span class="sxs-lookup"><span data-stu-id="ab290-163">Figure 5:  Toggling the `:hover` pseudostate on an element</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="ab290-164">Change the dimensions of an element</span><span class="sxs-lookup"><span data-stu-id="ab290-164">Change the dimensions of an element</span></span>  

<span data-ttu-id="ab290-165">Use the **Box Model** interactive diagram in the **Styles** tab to change the width, height, padding, margin, or border length of an element.</span><span class="sxs-lookup"><span data-stu-id="ab290-165">Use the **Box Model** interactive diagram in the **Styles** tab to change the width, height, padding, margin, or border length of an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="ab290-166">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span><span class="sxs-lookup"><span data-stu-id="ab290-166">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="ab290-167">[Open CSS Examples](#open-css-examples).</span><span class="sxs-lookup"><span data-stu-id="ab290-167">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="ab290-168">Hover on the `Change My Margin!` text, open the contextual menu \(right-click\), and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="ab290-168">Hover on the `Change My Margin!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
1.  <span data-ttu-id="ab290-169">In the **Box Model** diagram in the **Styles** tab, hover over **padding**.</span><span class="sxs-lookup"><span data-stu-id="ab290-169">In the **Box Model** diagram in the **Styles** tab, hover over **padding**.</span></span>  <span data-ttu-id="ab290-170">The padding of an element is highlighted in the viewport.</span><span class="sxs-lookup"><span data-stu-id="ab290-170">The padding of an element is highlighted in the viewport.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="ab290-171">Depending on the size of your DevTools window, you may need to scroll to the bottom of the **Styles** tab to see the **Box Model**.</span><span class="sxs-lookup"><span data-stu-id="ab290-171">Depending on the size of your DevTools window, you may need to scroll to the bottom of the **Styles** tab to see the **Box Model**.</span></span>  

1.  <span data-ttu-id="ab290-172">Double-click the left margin in the **Box Model**, which currently has a value of `-` meaning that the element does not have a left-margin.</span><span class="sxs-lookup"><span data-stu-id="ab290-172">Double-click the left margin in the **Box Model**, which currently has a value of `-` meaning that the element does not have a left-margin.</span></span>  
1.  <span data-ttu-id="ab290-173">Type `100px` and press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="ab290-173">Type `100px` and press `Enter`.</span></span>  <span data-ttu-id="ab290-174">The **Box Model** defaults to pixels, but it also accepts other values, such as `25%`, or `10vw`.</span><span class="sxs-lookup"><span data-stu-id="ab290-174">The **Box Model** defaults to pixels, but it also accepts other values, such as `25%`, or `10vw`.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-padding.msft.png" alt-text="The inspected element is highlighted in the DOM Tree" lightbox="../media/css-elements-change-my-margin-styles-padding.msft.png":::
             <span data-ttu-id="ab290-176">Figure 6:  Hovering over the padding of the element</span><span class="sxs-lookup"><span data-stu-id="ab290-176">Figure 6:  Hovering over the padding of the element</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-margin-edit.msft.png" alt-text="The inspected element is highlighted in the DOM Tree" lightbox="../media/css-elements-change-my-margin-styles-margin-edit.msft.png":::
             <span data-ttu-id="ab290-178">Figure 7:  Changing the left-margin of the element</span><span class="sxs-lookup"><span data-stu-id="ab290-178">Figure 7:  Changing the left-margin of the element</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <span data-ttu-id="ab290-179">Debugging Media Queries</span><span class="sxs-lookup"><span data-stu-id="ab290-179">Debugging Media Queries</span></span>  

<span data-ttu-id="ab290-180">[Media Queries][MDNUsingMediaGueries] are a way to make your web product react to changes in the configuration settings for each user.</span><span class="sxs-lookup"><span data-stu-id="ab290-180">[Media Queries][MDNUsingMediaGueries] are a way to make your web product react to changes in the configuration settings for each user.</span></span>  <span data-ttu-id="ab290-181">The most significant use case is to provide your product a different CSS layout depending on the dimensions of the viewport.</span><span class="sxs-lookup"><span data-stu-id="ab290-181">The most significant use case is to provide your product a different CSS layout depending on the dimensions of the viewport.</span></span>  <span data-ttu-id="ab290-182">Using separate layouts allows for a one-column layout for mobile devices and multi-column layouts when there is more screen estate available.</span><span class="sxs-lookup"><span data-stu-id="ab290-182">Using separate layouts allows for a one-column layout for mobile devices and multi-column layouts when there is more screen estate available.</span></span>  

<span data-ttu-id="ab290-183">If you want to debug or test the Media Queries you defined in your CSS, use the following steps.</span><span class="sxs-lookup"><span data-stu-id="ab290-183">If you want to debug or test the Media Queries you defined in your CSS, use the following steps.</span></span>  

1.  <span data-ttu-id="ab290-184">Open the developer tools and select the **Toggle device toolbar** icon second on the top-left, or press `Ctrl`+`Shift`+`M` \(`Cmd`+`Shift`+`M` on macOS\).</span><span class="sxs-lookup"><span data-stu-id="ab290-184">Open the developer tools and select the **Toggle device toolbar** icon second on the top-left, or press `Ctrl`+`Shift`+`M` \(`Cmd`+`Shift`+`M` on macOS\).</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-open-device-toolbar.msft.png" alt-text="The inspected element is highlighted in the DOM Tree" lightbox="../media/css-elements-media-queries-open-device-toolbar.msft.png":::
       <span data-ttu-id="ab290-186">Figure 8:  Opening the device toolbar</span><span class="sxs-lookup"><span data-stu-id="ab290-186">Figure 8:  Opening the device toolbar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ab290-187">With the device toolbar open, select the `...` menu on the top-right and select **View Media Queries**.</span><span class="sxs-lookup"><span data-stu-id="ab290-187">With the device toolbar open, select the `...` menu on the top-right and select **View Media Queries**.</span></span>  <span data-ttu-id="ab290-188">You should see colored bars above the display of the page that represent the different media queries.</span><span class="sxs-lookup"><span data-stu-id="ab290-188">You should see colored bars above the display of the page that represent the different media queries.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-showing-mq.msft.png" alt-text="The inspected element is highlighted in the DOM Tree" lightbox="../media/css-elements-media-queries-showing-mq.msft.png":::
       <span data-ttu-id="ab290-190">Figure 9:  Showing Media Queries in Device Toolbar</span><span class="sxs-lookup"><span data-stu-id="ab290-190">Figure 9:  Showing Media Queries in Device Toolbar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ab290-191">Hover over the boundaries in the bars to see the values of the different media queries.</span><span class="sxs-lookup"><span data-stu-id="ab290-191">Hover over the boundaries in the bars to see the values of the different media queries.</span></span> <span data-ttu-id="ab290-192">Select each to resize the web page to match.</span><span class="sxs-lookup"><span data-stu-id="ab290-192">Select each to resize the web page to match.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-select-bar.msft.png" alt-text="The inspected element is highlighted in the DOM Tree" lightbox="../media/css-elements-media-queries-select-bar.msft.png":::
       <span data-ttu-id="ab290-194">Figure 10:  Selecting Media Query from preview bar</span><span class="sxs-lookup"><span data-stu-id="ab290-194">Figure 10:  Selecting Media Query from preview bar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ab290-195">To debug media queries and open the CSS file in the `Sources` editor; hover on any of the bar segments, open the contextual menu \(right-click\), and select `reveal in source code`.</span><span class="sxs-lookup"><span data-stu-id="ab290-195">To debug media queries and open the CSS file in the `Sources` editor; hover on any of the bar segments, open the contextual menu \(right-click\), and select `reveal in source code`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-reveal-in-sources.msft.png" alt-text="The inspected element is highlighted in the DOM Tree" lightbox="../media/css-elements-media-queries-reveal-in-sources.msft.png":::
       <span data-ttu-id="ab290-197">Figure 11:  Revealing Media Queries in Sources Editor</span><span class="sxs-lookup"><span data-stu-id="ab290-197">Figure 11:  Revealing Media Queries in Sources Editor</span></span>  
    :::image-end:::  
    
<!-- links -->  

[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Change Microsoft Edge DevTools Placement (Undock, Dock To Bottom, Dock To Left)"  

[GlitchDevToolsCssExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/css/examples/ecma.html "CSS Examples - Microsoft Edge (Chromium) DevTools | Glitch"  

[MDNUsingMediaGueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "Using media queries | MDN"  

> [!NOTE]
> <span data-ttu-id="ab290-201">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="ab290-201">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ab290-202">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="ab290-202">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="ab290-204">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="ab290-204">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
