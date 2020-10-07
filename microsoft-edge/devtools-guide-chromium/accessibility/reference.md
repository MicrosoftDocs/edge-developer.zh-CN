---
description: A comprehensive reference of accessibility features in Microsoft Edge DevTools.
title: Accessibility Reference
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 39b0b8c36cea017b9976ea4e80e92ea93896a671
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993266"
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

# <span data-ttu-id="f4b08-104">Accessibility reference</span><span class="sxs-lookup"><span data-stu-id="f4b08-104">Accessibility reference</span></span>  

<span data-ttu-id="f4b08-105">This page is a comprehensive reference of accessibility features in Microsoft Edge DevTools.</span><span class="sxs-lookup"><span data-stu-id="f4b08-105">This page is a comprehensive reference of accessibility features in Microsoft Edge DevTools.</span></span>  <span data-ttu-id="f4b08-106">It is intended for web developers who:</span><span class="sxs-lookup"><span data-stu-id="f4b08-106">It is intended for web developers who:</span></span>  

*   <span data-ttu-id="f4b08-107">Have a basic understanding of DevTools, such as how to open it.</span><span class="sxs-lookup"><span data-stu-id="f4b08-107">Have a basic understanding of DevTools, such as how to open it.</span></span>  
*   <span data-ttu-id="f4b08-108">Are familiar with [accessibility principles and best practices][MDNAccessibility].</span><span class="sxs-lookup"><span data-stu-id="f4b08-108">Are familiar with [accessibility principles and best practices][MDNAccessibility].</span></span>  
    
<span data-ttu-id="f4b08-109">The purpose of this reference is to help you discover all of the tools available in DevTools that help you examine the accessibility of a page.</span><span class="sxs-lookup"><span data-stu-id="f4b08-109">The purpose of this reference is to help you discover all of the tools available in DevTools that help you examine the accessibility of a page.</span></span>  

<span data-ttu-id="f4b08-110">See [Navigating Microsoft Edge DevTools With Assistive Technology][DevtoolsAccessibilityNavigation] if you are looking for help on navigating DevTools with an assistive technology like a screen reader.</span><span class="sxs-lookup"><span data-stu-id="f4b08-110">See [Navigating Microsoft Edge DevTools With Assistive Technology][DevtoolsAccessibilityNavigation] if you are looking for help on navigating DevTools with an assistive technology like a screen reader.</span></span>  

## <span data-ttu-id="f4b08-111">Overview of accessibility features in Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="f4b08-111">Overview of accessibility features in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="f4b08-112">This section explains how DevTools fits into your overall accessibility toolkit.</span><span class="sxs-lookup"><span data-stu-id="f4b08-112">This section explains how DevTools fits into your overall accessibility toolkit.</span></span>  

<span data-ttu-id="f4b08-113">When determining whether a page is accessible, you need to have 2 general questions in mind:</span><span class="sxs-lookup"><span data-stu-id="f4b08-113">When determining whether a page is accessible, you need to have 2 general questions in mind:</span></span>  

1.  <span data-ttu-id="f4b08-114">Are you able to navigate the page with a keyboard or [screen reader][MDNScreenReader]?</span><span class="sxs-lookup"><span data-stu-id="f4b08-114">Are you able to navigate the page with a keyboard or [screen reader][MDNScreenReader]?</span></span>  
1.  <span data-ttu-id="f4b08-115">Are the elements of the page properly marked up for screen readers?</span><span class="sxs-lookup"><span data-stu-id="f4b08-115">Are the elements of the page properly marked up for screen readers?</span></span>  
    
<span data-ttu-id="f4b08-116">In general, DevTools should help you fix errors related to question #2, because these errors are easy to detect in an automated fashion.</span><span class="sxs-lookup"><span data-stu-id="f4b08-116">In general, DevTools should help you fix errors related to question #2, because these errors are easy to detect in an automated fashion.</span></span>  <span data-ttu-id="f4b08-117">Question #1 is just as important, but unfortunately DevTools does not help you there.</span><span class="sxs-lookup"><span data-stu-id="f4b08-117">Question #1 is just as important, but unfortunately DevTools does not help you there.</span></span>  <span data-ttu-id="f4b08-118">The only way to find errors related to question #1 is to try using a page with a keyboard or screen reader yourself.</span><span class="sxs-lookup"><span data-stu-id="f4b08-118">The only way to find errors related to question #1 is to try using a page with a keyboard or screen reader yourself.</span></span>  <!--See [How To Do An Accessibility Review][AccessibilityReview] to learn more.  -->  

<!--[AccessibilityReview]: /web/fundamentals/accessibility/how-to-review  -->  

## <span data-ttu-id="f4b08-119">Audit the accessibility of a page</span><span class="sxs-lookup"><span data-stu-id="f4b08-119">Audit the accessibility of a page</span></span>  

> [!NOTE]
> <span data-ttu-id="f4b08-120">The **Audits** panel provides links to content hosted on third-party websites.</span><span class="sxs-lookup"><span data-stu-id="f4b08-120">The **Audits** panel provides links to content hosted on third-party websites.</span></span>  <span data-ttu-id="f4b08-121">Microsoft is not responsible for and has no control over the content of these sites and any data that may be collected.</span><span class="sxs-lookup"><span data-stu-id="f4b08-121">Microsoft is not responsible for and has no control over the content of these sites and any data that may be collected.</span></span>  

<span data-ttu-id="f4b08-122">In general, use the Audits panel to determine if:</span><span class="sxs-lookup"><span data-stu-id="f4b08-122">In general, use the Audits panel to determine if:</span></span>  

*   <span data-ttu-id="f4b08-123">A page is properly marked up for screen readers.</span><span class="sxs-lookup"><span data-stu-id="f4b08-123">A page is properly marked up for screen readers.</span></span>  
*   <span data-ttu-id="f4b08-124">The text elements on a page have sufficient contrast ratios.</span><span class="sxs-lookup"><span data-stu-id="f4b08-124">The text elements on a page have sufficient contrast ratios.</span></span>  <span data-ttu-id="f4b08-125">See [View the contrast ratio of a text element in the Color Picker](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker).</span><span class="sxs-lookup"><span data-stu-id="f4b08-125">See [View the contrast ratio of a text element in the Color Picker](#view-the-contrast-ratio-of-a-text-element-in-the-color-picker).</span></span>  

<span data-ttu-id="f4b08-126">To audit a page:</span><span class="sxs-lookup"><span data-stu-id="f4b08-126">To audit a page:</span></span>  

1.  <span data-ttu-id="f4b08-127">Go to the URL that you want to audit.</span><span class="sxs-lookup"><span data-stu-id="f4b08-127">Go to the URL that you want to audit.</span></span>  
1.  <span data-ttu-id="f4b08-128">In DevTools, click the **Audits** tab.  DevTools shows you various configuration options.</span><span class="sxs-lookup"><span data-stu-id="f4b08-128">In DevTools, click the **Audits** tab.  DevTools shows you various configuration options.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-pane.msft.png" alt-text="Configure audits" lightbox="../media/accessibility-audits-pane.msft.png":::
       <span data-ttu-id="f4b08-130">Configure audits</span><span class="sxs-lookup"><span data-stu-id="f4b08-130">Configure audits</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="f4b08-131">The screenshots in this section were taken with version 79 of Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="f4b08-131">The screenshots in this section were taken with version 79 of Microsoft Edge.</span></span>  <span data-ttu-id="f4b08-132">You may check what version you are running at `edge://version`.</span><span class="sxs-lookup"><span data-stu-id="f4b08-132">You may check what version you are running at `edge://version`.</span></span>  <span data-ttu-id="f4b08-133">The **Audits** panel UI looks different in earlier versions of Microsoft Edge, but the general workflow is the same.</span><span class="sxs-lookup"><span data-stu-id="f4b08-133">The **Audits** panel UI looks different in earlier versions of Microsoft Edge, but the general workflow is the same.</span></span>  
    
1.  <span data-ttu-id="f4b08-134">For **Device**, select **Mobile** if you want to simulate a mobile device.</span><span class="sxs-lookup"><span data-stu-id="f4b08-134">For **Device**, select **Mobile** if you want to simulate a mobile device.</span></span>  <span data-ttu-id="f4b08-135">This option changes your user agent string and resizes the viewport.</span><span class="sxs-lookup"><span data-stu-id="f4b08-135">This option changes your user agent string and resizes the viewport.</span></span>  <span data-ttu-id="f4b08-136">If the mobile version of the page displays differently than the desktop version, this option could have a significant effect on the results of your audit.</span><span class="sxs-lookup"><span data-stu-id="f4b08-136">If the mobile version of the page displays differently than the desktop version, this option could have a significant effect on the results of your audit.</span></span>  
1.  <span data-ttu-id="f4b08-137">In the **Audits** section, make sure that **Accessibility** is enabled.</span><span class="sxs-lookup"><span data-stu-id="f4b08-137">In the **Audits** section, make sure that **Accessibility** is enabled.</span></span>  <span data-ttu-id="f4b08-138">Disable the other categories if you want to exclude them from your report.</span><span class="sxs-lookup"><span data-stu-id="f4b08-138">Disable the other categories if you want to exclude them from your report.</span></span>  <span data-ttu-id="f4b08-139">Leave them enabled if you want to discover other ways to improve the quality of your page.</span><span class="sxs-lookup"><span data-stu-id="f4b08-139">Leave them enabled if you want to discover other ways to improve the quality of your page.</span></span>  
1.  <span data-ttu-id="f4b08-140">The **Throttling** section lets you throttle the network and CPU, which is useful when analyzing load performance.</span><span class="sxs-lookup"><span data-stu-id="f4b08-140">The **Throttling** section lets you throttle the network and CPU, which is useful when analyzing load performance.</span></span>  <span data-ttu-id="f4b08-141">This option should be irrelevant to your accessibility score, so you may use whatever you prefer.</span><span class="sxs-lookup"><span data-stu-id="f4b08-141">This option should be irrelevant to your accessibility score, so you may use whatever you prefer.</span></span>  
1.  <span data-ttu-id="f4b08-142">The **Clear Storage** checkbox lets you clear all storage before loading the page, or preserve storage between page loads.</span><span class="sxs-lookup"><span data-stu-id="f4b08-142">The **Clear Storage** checkbox lets you clear all storage before loading the page, or preserve storage between page loads.</span></span>  <span data-ttu-id="f4b08-143">This option is also probably irrelevant to your accessibility score, so you may use whatever you prefer.</span><span class="sxs-lookup"><span data-stu-id="f4b08-143">This option is also probably irrelevant to your accessibility score, so you may use whatever you prefer.</span></span>  
1.  <span data-ttu-id="f4b08-144">Click **Run Audits**.</span><span class="sxs-lookup"><span data-stu-id="f4b08-144">Click **Run Audits**.</span></span> <span data-ttu-id="f4b08-145">After 10 to 30 seconds, DevTools provides a report.</span><span class="sxs-lookup"><span data-stu-id="f4b08-145">After 10 to 30 seconds, DevTools provides a report.</span></span>  <span data-ttu-id="f4b08-146">Your report gives you various tips on how to improve the accessibility of the page.</span><span class="sxs-lookup"><span data-stu-id="f4b08-146">Your report gives you various tips on how to improve the accessibility of the page.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result.msft.png" alt-text="Configure audits" lightbox="../media/accessibility-audits-run-audits-result.msft.png":::
       <span data-ttu-id="f4b08-148">A report</span><span class="sxs-lookup"><span data-stu-id="f4b08-148">A report</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f4b08-149">Click an audit to learn more about it.</span><span class="sxs-lookup"><span data-stu-id="f4b08-149">Click an audit to learn more about it.</span></span>  
    
    :::image type="complex" source="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png" alt-text="Configure audits" lightbox="../media/accessibility-audits-run-audits-result-issues-expanded.msft.png":::
       <span data-ttu-id="f4b08-151">More information about an audit</span><span class="sxs-lookup"><span data-stu-id="f4b08-151">More information about an audit</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f4b08-152">Click **Learn More** to view the documentation of that audit.</span><span class="sxs-lookup"><span data-stu-id="f4b08-152">Click **Learn More** to view the documentation of that audit.</span></span>  
    
    :::image type="complex" source="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png" alt-text="Configure audits" lightbox="../media/accessibility-web-dev-accessibility-audits-learn-more.msft.png":::
       <span data-ttu-id="f4b08-154">View the documentation of an audit</span><span class="sxs-lookup"><span data-stu-id="f4b08-154">View the documentation of an audit</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="f4b08-155">See also: aXe extension</span><span class="sxs-lookup"><span data-stu-id="f4b08-155">See also: aXe extension</span></span>  

<span data-ttu-id="f4b08-156">You may prefer to use the [aXe extension][ChromeWebStoreAxe] rather than the **Audits** panel.</span><span class="sxs-lookup"><span data-stu-id="f4b08-156">You may prefer to use the [aXe extension][ChromeWebStoreAxe] rather than the **Audits** panel.</span></span>  
<span data-ttu-id="f4b08-157">The aXe extension generally provides the same information, since it is the underlying engine that powers the Audits panel.</span><span class="sxs-lookup"><span data-stu-id="f4b08-157">The aXe extension generally provides the same information, since it is the underlying engine that powers the Audits panel.</span></span>  <span data-ttu-id="f4b08-158">The aXe extension has a different UI and describes audits slightly differently.</span><span class="sxs-lookup"><span data-stu-id="f4b08-158">The aXe extension has a different UI and describes audits slightly differently.</span></span>  
<span data-ttu-id="f4b08-159">One advantage that the aXe extension has over the **Audits** panel is that it enables you to inspect and highlight failing nodes.</span><span class="sxs-lookup"><span data-stu-id="f4b08-159">One advantage that the aXe extension has over the **Audits** panel is that it enables you to inspect and highlight failing nodes.</span></span>  

:::image type="complex" source="../media/accessibility-devtools-extension-axe-panel.msft.png" alt-text="Configure audits" lightbox="../media/accessibility-devtools-extension-axe-panel.msft.png":::
   <span data-ttu-id="f4b08-161">The aXe extension</span><span class="sxs-lookup"><span data-stu-id="f4b08-161">The aXe extension</span></span>  
:::image-end:::  

## <span data-ttu-id="f4b08-162">The Accessibility pane</span><span class="sxs-lookup"><span data-stu-id="f4b08-162">The Accessibility pane</span></span>  

<span data-ttu-id="f4b08-163">The **Accessibility** pane is where you view the accessibility tree, ARIA attributes, and computed accessibility properties of DOM nodes.</span><span class="sxs-lookup"><span data-stu-id="f4b08-163">The **Accessibility** pane is where you view the accessibility tree, ARIA attributes, and computed accessibility properties of DOM nodes.</span></span>  

<span data-ttu-id="f4b08-164">To open the **Accessibility** pane:</span><span class="sxs-lookup"><span data-stu-id="f4b08-164">To open the **Accessibility** pane:</span></span>  

1.  <span data-ttu-id="f4b08-165">Click the **Elements** tab.</span><span class="sxs-lookup"><span data-stu-id="f4b08-165">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="f4b08-166">In the **DOM Tree**, select the element which you want to inspect.</span><span class="sxs-lookup"><span data-stu-id="f4b08-166">In the **DOM Tree**, select the element which you want to inspect.</span></span>  
1.  <span data-ttu-id="f4b08-167">Click the **Accessibility** tab.  This tab may be hidden behind the **More Tabs** \(![More Tabs][ImageMoreTabsIcon]\) button.</span><span class="sxs-lookup"><span data-stu-id="f4b08-167">Click the **Accessibility** tab.  This tab may be hidden behind the **More Tabs** \(![More Tabs][ImageMoreTabsIcon]\) button.</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility.msft.png" alt-text="Configure audits" lightbox="../media/accessibility-elements-accessibility.msft.png":::
   <span data-ttu-id="f4b08-169">Inspect the `h1` element of the DevTools homepage in the **Accessibility** pane</span><span class="sxs-lookup"><span data-stu-id="f4b08-169">Inspect the `h1` element of the DevTools homepage in the **Accessibility** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="f4b08-170">View the position of an element in the accessibility tree</span><span class="sxs-lookup"><span data-stu-id="f4b08-170">View the position of an element in the accessibility tree</span></span>  

<span data-ttu-id="f4b08-171">The [accessibility tree][MDNAccessibilityTree] is a subset of the DOM tree.</span><span class="sxs-lookup"><span data-stu-id="f4b08-171">The [accessibility tree][MDNAccessibilityTree] is a subset of the DOM tree.</span></span>  <span data-ttu-id="f4b08-172">It only contains elements from the DOM tree that are relevant and useful for displaying the contents of a page in a screen reader.</span><span class="sxs-lookup"><span data-stu-id="f4b08-172">It only contains elements from the DOM tree that are relevant and useful for displaying the contents of a page in a screen reader.</span></span>  

<span data-ttu-id="f4b08-173">Inspect the position of an element in the accessibility tree from the [Accessibility pane](#the-accessibility-pane).</span><span class="sxs-lookup"><span data-stu-id="f4b08-173">Inspect the position of an element in the accessibility tree from the [Accessibility pane](#the-accessibility-pane).</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-tree.msft.png" alt-text="Configure audits" lightbox="../media/accessibility-elements-accessibility-tree.msft.png":::
   <span data-ttu-id="f4b08-175">The **Accessibility Tree** section</span><span class="sxs-lookup"><span data-stu-id="f4b08-175">The **Accessibility Tree** section</span></span>  
:::image-end:::  

### <span data-ttu-id="f4b08-176">View the ARIA attributes of an element</span><span class="sxs-lookup"><span data-stu-id="f4b08-176">View the ARIA attributes of an element</span></span>  

<span data-ttu-id="f4b08-177">ARIA attributes ensure that screen readers have all of the information that they need in order to properly represent the contents of a page.</span><span class="sxs-lookup"><span data-stu-id="f4b08-177">ARIA attributes ensure that screen readers have all of the information that they need in order to properly represent the contents of a page.</span></span>  

<span data-ttu-id="f4b08-178">View the ARIA attributes of an element in the [Accessibility pane](#the-accessibility-pane).</span><span class="sxs-lookup"><span data-stu-id="f4b08-178">View the ARIA attributes of an element in the [Accessibility pane](#the-accessibility-pane).</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-aria-attributes.msft.png" alt-text="Configure audits" lightbox="../media/accessibility-elements-accessibility-aria-attributes.msft.png":::
   <span data-ttu-id="f4b08-180">The **ARIA Attributes** section</span><span class="sxs-lookup"><span data-stu-id="f4b08-180">The **ARIA Attributes** section</span></span>  
:::image-end:::  

### <span data-ttu-id="f4b08-181">View the computed accessibility properties of an element</span><span class="sxs-lookup"><span data-stu-id="f4b08-181">View the computed accessibility properties of an element</span></span>  

> [!NOTE]
> <span data-ttu-id="f4b08-182">If you are looking for computed CSS properties, see the [Computed tab][DevtoolsCssReferenceViewActuallyAppliedElements].</span><span class="sxs-lookup"><span data-stu-id="f4b08-182">If you are looking for computed CSS properties, see the [Computed tab][DevtoolsCssReferenceViewActuallyAppliedElements].</span></span>  

<span data-ttu-id="f4b08-183">Some accessibility properties are dynamically calculated by the browser.</span><span class="sxs-lookup"><span data-stu-id="f4b08-183">Some accessibility properties are dynamically calculated by the browser.</span></span>  <span data-ttu-id="f4b08-184">These properties are displayed in the **Computed Properties** section of the **Accessibility** pane.</span><span class="sxs-lookup"><span data-stu-id="f4b08-184">These properties are displayed in the **Computed Properties** section of the **Accessibility** pane.</span></span>  

<span data-ttu-id="f4b08-185">View the computed accessibility properties of an element in the [Accessibility pane](#the-accessibility-pane).</span><span class="sxs-lookup"><span data-stu-id="f4b08-185">View the computed accessibility properties of an element in the [Accessibility pane](#the-accessibility-pane).</span></span>  

:::image type="complex" source="../media/accessibility-elements-accessibility-computed-properties.msft.png" alt-text="Configure audits" lightbox="../media/accessibility-elements-accessibility-computed-properties.msft.png":::
   <span data-ttu-id="f4b08-187">The **Computed Properties** section of the **Accessibility** pane</span><span class="sxs-lookup"><span data-stu-id="f4b08-187">The **Computed Properties** section of the **Accessibility** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="f4b08-188">View the contrast ratio of a text element in the Color Picker</span><span class="sxs-lookup"><span data-stu-id="f4b08-188">View the contrast ratio of a text element in the Color Picker</span></span>  

<span data-ttu-id="f4b08-189">Some people with low vision do not see areas as very bright or very dark.</span><span class="sxs-lookup"><span data-stu-id="f4b08-189">Some people with low vision do not see areas as very bright or very dark.</span></span>  <span data-ttu-id="f4b08-190">Everything tends to appear at about the same brightness, which makes it hard to distinguish outlines and edges.</span><span class="sxs-lookup"><span data-stu-id="f4b08-190">Everything tends to appear at about the same brightness, which makes it hard to distinguish outlines and edges.</span></span>  

<span data-ttu-id="f4b08-191">Contrast ratio measures the difference in brightness between the foreground and background of text.</span><span class="sxs-lookup"><span data-stu-id="f4b08-191">Contrast ratio measures the difference in brightness between the foreground and background of text.</span></span>  <span data-ttu-id="f4b08-192">If your text has a low contrast ratio, then these low vision users may literally experience your site as a blank screen.</span><span class="sxs-lookup"><span data-stu-id="f4b08-192">If your text has a low contrast ratio, then these low vision users may literally experience your site as a blank screen.</span></span>  

<span data-ttu-id="f4b08-193">The Color Picker helps you verify that your text meets recommended contrast ratio levels:</span><span class="sxs-lookup"><span data-stu-id="f4b08-193">The Color Picker helps you verify that your text meets recommended contrast ratio levels:</span></span>  

1.  <span data-ttu-id="f4b08-194">Click the **Elements** tab.</span><span class="sxs-lookup"><span data-stu-id="f4b08-194">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="f4b08-195">In the **DOM Tree**, select the text element that you want to inspect.</span><span class="sxs-lookup"><span data-stu-id="f4b08-195">In the **DOM Tree**, select the text element that you want to inspect.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-paragraph-highlight.msft.png" alt-text="Configure audits" lightbox="../media/accessibility-elements-paragraph-highlight.msft.png":::
       <span data-ttu-id="f4b08-197">Inspect a paragraph in the **DOM Tree**</span><span class="sxs-lookup"><span data-stu-id="f4b08-197">Inspect a paragraph in the **DOM Tree**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f4b08-198">In the **Styles** pane, click the color square next to the `color` value of the element.</span><span class="sxs-lookup"><span data-stu-id="f4b08-198">In the **Styles** pane, click the color square next to the `color` value of the element.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png" alt-text="Configure audits" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color.msft.png":::
       <span data-ttu-id="f4b08-200">The `color` property of the element</span><span class="sxs-lookup"><span data-stu-id="f4b08-200">The `color` property of the element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f4b08-201">Check the **Contrast Ratio** section of the Color Picker.</span><span class="sxs-lookup"><span data-stu-id="f4b08-201">Check the **Contrast Ratio** section of the Color Picker.</span></span>  <span data-ttu-id="f4b08-202">One checkmark means that the element meets the [minimum recommendation][W3CContrastMinimum].</span><span class="sxs-lookup"><span data-stu-id="f4b08-202">One checkmark means that the element meets the [minimum recommendation][W3CContrastMinimum].</span></span>  <span data-ttu-id="f4b08-203">Two checkmarks means that it meets the [enhanced recommendation][W3CContrastEnhanced].</span><span class="sxs-lookup"><span data-stu-id="f4b08-203">Two checkmarks means that it meets the [enhanced recommendation][W3CContrastEnhanced].</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png" alt-text="Configure audits" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker.msft.png":::
       <span data-ttu-id="f4b08-205">The **Contrast Ratio** section of the Color Picker shows 2 checkmarks and a value of</span><span class="sxs-lookup"><span data-stu-id="f4b08-205">The **Contrast Ratio** section of the Color Picker shows 2 checkmarks and a value of</span></span> `13.97`  
    :::image-end:::  
    
1.  <span data-ttu-id="f4b08-206">Click the **Contrast Ratio** section to see more information.</span><span class="sxs-lookup"><span data-stu-id="f4b08-206">Click the **Contrast Ratio** section to see more information.</span></span>  <span data-ttu-id="f4b08-207">A line appears in the visual picker at the top of the Color Picker.</span><span class="sxs-lookup"><span data-stu-id="f4b08-207">A line appears in the visual picker at the top of the Color Picker.</span></span>  <span data-ttu-id="f4b08-208">If the current color meets recommendations, then anything on the same side of the line also meets recommendations.</span><span class="sxs-lookup"><span data-stu-id="f4b08-208">If the current color meets recommendations, then anything on the same side of the line also meets recommendations.</span></span>  <span data-ttu-id="f4b08-209">If the current color does not meet recommendations, then anything on the same side also does not meet recommendations.</span><span class="sxs-lookup"><span data-stu-id="f4b08-209">If the current color does not meet recommendations, then anything on the same side also does not meet recommendations.</span></span>  
    
    :::image type="complex" source="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png" alt-text="Configure audits" lightbox="../media/accessibility-elements-styles-paragraph-highlight-color-picker-contrast-ratio-details.msft.png":::
       <span data-ttu-id="f4b08-211">The **Contrast Ratio** Line in the visual picker</span><span class="sxs-lookup"><span data-stu-id="f4b08-211">The **Contrast Ratio** Line in the visual picker</span></span>  
    :::image-end:::  
    
<!--## Feedback   -->  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  

<!-- links -->  

[DevtoolsAccessibilityNavigation]: ./navigation.md "Navigate Microsoft Edge DevTools With Assistive Technology | Microsoft Docs"  
[DevtoolsCssReferenceViewActuallyAppliedElements]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "View only the CSS that is actually applied to an element - CSS Reference | Microsoft Docs"  

[ChromeWebStoreAxe]: https://chrome.google.com/webstore/detail/axe/lhdoppojpmngadmnindnejefpokejbdd?hl=en-US "axe - Web Accessibility Testing - Chrome Web Store"  

[MDNAccessibilityTree]: https://developer.mozilla.org/docs/Glossary/AOM "Accessibility tree (AOM) | MDN"  
[MDNAccessibility]: https://developer.mozilla.org/docs/Web/Accessibility "Accessibility | MDN"  
[MDNScreenReader]: https://developer.mozilla.org/docs/Glossary/Screen_reader "Screen reader | MDN"  

[W3CContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-enhanced "Contrast (Enhanced) Level AAA | W3C"  
[W3CContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum "Contrast (Minimum) Level AA | W3C"  

> [!NOTE]
> <span data-ttu-id="f4b08-220">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f4b08-220">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f4b08-221">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="f4b08-221">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f4b08-223">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f4b08-223">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
