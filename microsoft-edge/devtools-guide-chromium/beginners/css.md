---
description: Get Started with CSS
title: 'DevTools for beginners: Get started with CSS'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web developement, f12 tools, devtools
ms.openlocfilehash: fe87b4f840c6d9dde3cdf6455700161ea8d8d31e
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993301"
---
<!-- Copyright Katherine Jackson 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <span data-ttu-id="f5887-104">DevTools for beginners: Get started with CSS</span><span class="sxs-lookup"><span data-stu-id="f5887-104">DevTools for beginners: Get started with CSS</span></span>  

<span data-ttu-id="f5887-105">In this tutorial, you learn how to use CSS to style a web page.</span><span class="sxs-lookup"><span data-stu-id="f5887-105">In this tutorial, you learn how to use CSS to style a web page.</span></span>  <span data-ttu-id="f5887-106">You also learn how to use Microsoft Edge DevTools to experiment with CSS changes.</span><span class="sxs-lookup"><span data-stu-id="f5887-106">You also learn how to use Microsoft Edge DevTools to experiment with CSS changes.</span></span>  

<span data-ttu-id="f5887-107">The following article is the second tutorial in a series of tutorials that teaches you the basics of web development and Microsoft Edge DevTools.</span><span class="sxs-lookup"><span data-stu-id="f5887-107">The following article is the second tutorial in a series of tutorials that teaches you the basics of web development and Microsoft Edge DevTools.</span></span>  <span data-ttu-id="f5887-108">You gain hands-on experience by actually building your own website.</span><span class="sxs-lookup"><span data-stu-id="f5887-108">You gain hands-on experience by actually building your own website.</span></span>  <span data-ttu-id="f5887-109">You do not have to complete the first tutorial before following the second.</span><span class="sxs-lookup"><span data-stu-id="f5887-109">You do not have to complete the first tutorial before following the second.</span></span>  <span data-ttu-id="f5887-110">[Set up your code](#set-up-your-code) shows you how to get set up.</span><span class="sxs-lookup"><span data-stu-id="f5887-110">[Set up your code](#set-up-your-code) shows you how to get set up.</span></span>  

> [!NOTE]
> <span data-ttu-id="f5887-111">This tutorial is designed for absolute beginners and focuses on both the **fundamentals of web development** and the basics of using DevTools to experiment with CSS.</span><span class="sxs-lookup"><span data-stu-id="f5887-111">This tutorial is designed for absolute beginners and focuses on both the **fundamentals of web development** and the basics of using DevTools to experiment with CSS.</span></span>  <span data-ttu-id="f5887-112">If you want a tutorial that only focuses on DevTools, see [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span><span class="sxs-lookup"><span data-stu-id="f5887-112">If you want a tutorial that only focuses on DevTools, see [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

<span data-ttu-id="f5887-113">At the beginning of the tutorial, your site should look like the following figure.</span><span class="sxs-lookup"><span data-stu-id="f5887-113">At the beginning of the tutorial, your site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro1.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-intro1.msft.png":::
   <span data-ttu-id="f5887-115">What your site currently looks like</span><span class="sxs-lookup"><span data-stu-id="f5887-115">What your site currently looks like</span></span>  
:::image-end:::  

<span data-ttu-id="f5887-116">After you complete the tutorial, you site should look like the following figure.</span><span class="sxs-lookup"><span data-stu-id="f5887-116">After you complete the tutorial, you site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro2.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-intro2.msft.png":::
   <span data-ttu-id="f5887-118">What your site should look like at the end of the tutorial</span><span class="sxs-lookup"><span data-stu-id="f5887-118">What your site should look like at the end of the tutorial</span></span>  
:::image-end:::  

## <span data-ttu-id="f5887-119">Goals</span><span class="sxs-lookup"><span data-stu-id="f5887-119">Goals</span></span>  

<span data-ttu-id="f5887-120">Follow this tutorial to better understand the following concepts and tasks.</span><span class="sxs-lookup"><span data-stu-id="f5887-120">Follow this tutorial to better understand the following concepts and tasks.</span></span>  

*   <span data-ttu-id="f5887-121">How to use CSS to style a web page.</span><span class="sxs-lookup"><span data-stu-id="f5887-121">How to use CSS to style a web page.</span></span>  
*   <span data-ttu-id="f5887-122">How to use Microsoft Edge DevTools to experiment with CSS.</span><span class="sxs-lookup"><span data-stu-id="f5887-122">How to use Microsoft Edge DevTools to experiment with CSS.</span></span>  
*   <span data-ttu-id="f5887-123">The difference between CSS and CSS frameworks.</span><span class="sxs-lookup"><span data-stu-id="f5887-123">The difference between CSS and CSS frameworks.</span></span>  

<span data-ttu-id="f5887-124">You are building a real website.</span><span class="sxs-lookup"><span data-stu-id="f5887-124">You are building a real website.</span></span>  

## <span data-ttu-id="f5887-125">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="f5887-125">Prerequisites</span></span>  

<span data-ttu-id="f5887-126">Before attempting this tutorial, complete the following prerequisites.</span><span class="sxs-lookup"><span data-stu-id="f5887-126">Before attempting this tutorial, complete the following prerequisites.</span></span>  

*   <span data-ttu-id="f5887-127">Complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] or make sure that you have an understanding of HTML and the DOM similar to what is taught in that tutorial.</span><span class="sxs-lookup"><span data-stu-id="f5887-127">Complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] or make sure that you have an understanding of HTML and the DOM similar to what is taught in that tutorial.</span></span>  
*   <span data-ttu-id="f5887-128">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span><span class="sxs-lookup"><span data-stu-id="f5887-128">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="f5887-129">The following tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="f5887-129">The following tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <span data-ttu-id="f5887-130">Set up your code</span><span class="sxs-lookup"><span data-stu-id="f5887-130">Set up your code</span></span>  

<span data-ttu-id="f5887-131">To create your site, you must first complete the following actions to set up your code.</span><span class="sxs-lookup"><span data-stu-id="f5887-131">To create your site, you must first complete the following actions to set up your code.</span></span>  

> [!NOTE]
> <span data-ttu-id="f5887-132">If you have already completed the first tutorial in the series, skip to the next section.</span><span class="sxs-lookup"><span data-stu-id="f5887-132">If you have already completed the first tutorial in the series, skip to the next section.</span></span>  <span data-ttu-id="f5887-133">Continue using your code from the last tutorial, [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span><span class="sxs-lookup"><span data-stu-id="f5887-133">Continue using your code from the last tutorial, [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  

1.  <span data-ttu-id="f5887-134">Open the [source code][GlitchCookedAmphibianIndex].</span><span class="sxs-lookup"><span data-stu-id="f5887-134">Open the [source code][GlitchCookedAmphibianIndex].</span></span>  <span data-ttu-id="f5887-135">The in-focus tab of your browser is referenced as the **editing tab**.</span><span class="sxs-lookup"><span data-stu-id="f5887-135">The in-focus tab of your browser is referenced as the **editing tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup1.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-setup1.msft.png":::
       <span data-ttu-id="f5887-137">The **editing** tab</span><span class="sxs-lookup"><span data-stu-id="f5887-137">The **editing** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-138">Choose **cooked-amphibian**.</span><span class="sxs-lookup"><span data-stu-id="f5887-138">Choose **cooked-amphibian**.</span></span>  <span data-ttu-id="f5887-139">A menu pops up.</span><span class="sxs-lookup"><span data-stu-id="f5887-139">A menu pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup2.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-setup2.msft.png":::
       <span data-ttu-id="f5887-141">The Project Options menu</span><span class="sxs-lookup"><span data-stu-id="f5887-141">The Project Options menu</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="f5887-142">Choose **Remix Project**.</span><span class="sxs-lookup"><span data-stu-id="f5887-142">Choose **Remix Project**.</span></span>  <span data-ttu-id="f5887-143">Glitch creates a copy of the project that you are able to edit.</span><span class="sxs-lookup"><span data-stu-id="f5887-143">Glitch creates a copy of the project that you are able to edit.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="f5887-144">Glitch generates a random name for the new project.</span><span class="sxs-lookup"><span data-stu-id="f5887-144">Glitch generates a random name for the new project.</span></span>  
    
1.  <span data-ttu-id="f5887-145">Choose **Show** and select **In a New Window**.</span><span class="sxs-lookup"><span data-stu-id="f5887-145">Choose **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="f5887-146">Another tab opens with a live view of your site.</span><span class="sxs-lookup"><span data-stu-id="f5887-146">Another tab opens with a live view of your site.</span></span>  <span data-ttu-id="f5887-147">The in-focus tab of your browser is referenced as the **live tab**.</span><span class="sxs-lookup"><span data-stu-id="f5887-147">The in-focus tab of your browser is referenced as the **live tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup3.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-setup3.msft.png":::
       <span data-ttu-id="f5887-149">The **live tab**</span><span class="sxs-lookup"><span data-stu-id="f5887-149">The **live tab**</span></span>  
    :::image-end:::  

## <span data-ttu-id="f5887-150">Understand CSS</span><span class="sxs-lookup"><span data-stu-id="f5887-150">Understand CSS</span></span>  

<span data-ttu-id="f5887-151">**CSS** is a computer language that determines the layout and styling of web pages.</span><span class="sxs-lookup"><span data-stu-id="f5887-151">**CSS** is a computer language that determines the layout and styling of web pages.</span></span>  <span data-ttu-id="f5887-152">The following figure is a paragraph with a border.</span><span class="sxs-lookup"><span data-stu-id="f5887-152">The following figure is a paragraph with a border.</span></span>  

:::image type="complex" source="../media/beginners-css-red_paragraph.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-red_paragraph.msft.png":::
   <span data-ttu-id="f5887-154">The text has been styled with CSS</span><span class="sxs-lookup"><span data-stu-id="f5887-154">The text has been styled with CSS</span></span>  
:::image-end:::  

<span data-ttu-id="f5887-155">The following code snippet is the HTML and CSS code used to create the paragraph in the previous figure.</span><span class="sxs-lookup"><span data-stu-id="f5887-155">The following code snippet is the HTML and CSS code used to create the paragraph in the previous figure.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` <span data-ttu-id="f5887-156">probably looks new to you.</span><span class="sxs-lookup"><span data-stu-id="f5887-156">probably looks new to you.</span></span>  <span data-ttu-id="f5887-157">The rest should look familiar.</span><span class="sxs-lookup"><span data-stu-id="f5887-157">The rest should look familiar.</span></span>  <span data-ttu-id="f5887-158">If not, complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] before attempting the following sections.</span><span class="sxs-lookup"><span data-stu-id="f5887-158">If not, complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] before attempting the following sections.</span></span>  

## <span data-ttu-id="f5887-159">Add inline styles</span><span class="sxs-lookup"><span data-stu-id="f5887-159">Add inline styles</span></span>  

<span data-ttu-id="f5887-160">Complete the following actions to use **inline styles** to apply styles to a single element.</span><span class="sxs-lookup"><span data-stu-id="f5887-160">Complete the following actions to use **inline styles** to apply styles to a single element.</span></span>  

1.  <span data-ttu-id="f5887-161">Go back to the editing tab and open `index.html`.</span><span class="sxs-lookup"><span data-stu-id="f5887-161">Go back to the editing tab and open `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline1.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-inline1.msft.png":::
       <span data-ttu-id="f5887-163">Open `index.html` in the editing tab</span><span class="sxs-lookup"><span data-stu-id="f5887-163">Open `index.html` in the editing tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-164">Add `style="background-color: aliceblue;"` to your `<nav>`.</span><span class="sxs-lookup"><span data-stu-id="f5887-164">Add `style="background-color: aliceblue;"` to your `<nav>`.</span></span>  <span data-ttu-id="f5887-165">In the code block below, the fourth line of code is the one you need to change.</span><span class="sxs-lookup"><span data-stu-id="f5887-165">In the code block below, the fourth line of code is the one you need to change.</span></span>  <span data-ttu-id="f5887-166">The rest is just there, so you are able to ensure that you are putting the new code in the right place.</span><span class="sxs-lookup"><span data-stu-id="f5887-166">The rest is just there, so you are able to ensure that you are putting the new code in the right place.</span></span>  
    
    ```html
    <header>
        <p>Welcome to my site!</p>
    </header>
    <nav style="background-color: aliceblue;">
        <ul>
            <li><a href="/">Home</a></li>
            ...
        ...
    ...
    ```  
    
1.  <span data-ttu-id="f5887-167">Go to the **live tab** to see the changes!</span><span class="sxs-lookup"><span data-stu-id="f5887-167">Go to the **live tab** to see the changes!</span></span>  <span data-ttu-id="f5887-168">The background of the `<nav>` section is now blue.</span><span class="sxs-lookup"><span data-stu-id="f5887-168">The background of the `<nav>` section is now blue.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline2.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-inline2.msft.png":::
       <span data-ttu-id="f5887-170">The background color behind the **Home** and **Contact** links is now blue</span><span class="sxs-lookup"><span data-stu-id="f5887-170">The background color behind the **Home** and **Contact** links is now blue</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f5887-171">Re-use styles on a single page with internal stylesheets</span><span class="sxs-lookup"><span data-stu-id="f5887-171">Re-use styles on a single page with internal stylesheets</span></span>  

<span data-ttu-id="f5887-172">In a previous code snippet, an inline style applied a style to a single `<p>` tag.</span><span class="sxs-lookup"><span data-stu-id="f5887-172">In a previous code snippet, an inline style applied a style to a single `<p>` tag.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

<span data-ttu-id="f5887-173">What if you wanted all of the `<p>` elements on your webpage to be styled the same way?</span><span class="sxs-lookup"><span data-stu-id="f5887-173">What if you wanted all of the `<p>` elements on your webpage to be styled the same way?</span></span>  <span data-ttu-id="f5887-174">You would have to copy and paste the code into every single `<p>` tag on your site.</span><span class="sxs-lookup"><span data-stu-id="f5887-174">You would have to copy and paste the code into every single `<p>` tag on your site.</span></span>  <span data-ttu-id="f5887-175">That is a lot of time and effort.</span><span class="sxs-lookup"><span data-stu-id="f5887-175">That is a lot of time and effort.</span></span>  <span data-ttu-id="f5887-176">And, if you needed to make an edit, you would have to change every tag again.</span><span class="sxs-lookup"><span data-stu-id="f5887-176">And, if you needed to make an edit, you would have to change every tag again.</span></span>  <span data-ttu-id="f5887-177">Complete the following actions to use an **Internal stylesheet** to write your CSS once so that it applies to multiple elements.</span><span class="sxs-lookup"><span data-stu-id="f5887-177">Complete the following actions to use an **Internal stylesheet** to write your CSS once so that it applies to multiple elements.</span></span>  

1.  <span data-ttu-id="f5887-178">In the live tab, choose **Contact** to go to the contact page.</span><span class="sxs-lookup"><span data-stu-id="f5887-178">In the live tab, choose **Contact** to go to the contact page.</span></span>  <span data-ttu-id="f5887-179">Notice the font of **Home** and **Contact**.</span><span class="sxs-lookup"><span data-stu-id="f5887-179">Notice the font of **Home** and **Contact**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal1.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-internal1.msft.png":::
       <span data-ttu-id="f5887-181">The Contact page</span><span class="sxs-lookup"><span data-stu-id="f5887-181">The Contact page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-182">In the **editor tab**, go to `contact.html`.</span><span class="sxs-lookup"><span data-stu-id="f5887-182">In the **editor tab**, go to `contact.html`.</span></span>  
1.  <span data-ttu-id="f5887-183">Add the following code to `contact.html`.</span><span class="sxs-lookup"><span data-stu-id="f5887-183">Add the following code to `contact.html`.</span></span>  <span data-ttu-id="f5887-184">Remember, the lines starting with `<style>` and ending with `</style>` are what you need to add.</span><span class="sxs-lookup"><span data-stu-id="f5887-184">Remember, the lines starting with `<style>` and ending with `</style>` are what you need to add.</span></span>  <span data-ttu-id="f5887-185">The other code is just there so you know where to put the new code.</span><span class="sxs-lookup"><span data-stu-id="f5887-185">The other code is just there so you know where to put the new code.</span></span>  
    
    ```html
    ...
        <head>
            ...
            <meta name="viewport" content="width=device-width, initial-scale=1">
            <style>
                li a {
                  font-family: 'Courier New', Courier, Serif;
                }
            </style>
            ...
        </head>
        ...
    ...
    ```  
    
1.  <span data-ttu-id="f5887-186">Go back to the **live tab**.</span><span class="sxs-lookup"><span data-stu-id="f5887-186">Go back to the **live tab**.</span></span>  
1.  <span data-ttu-id="f5887-187">Choose **Contact** to go back to the contact page.</span><span class="sxs-lookup"><span data-stu-id="f5887-187">Choose **Contact** to go back to the contact page.</span></span>  <span data-ttu-id="f5887-188">The font of **Home** and **Contact** has changed.</span><span class="sxs-lookup"><span data-stu-id="f5887-188">The font of **Home** and **Contact** has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal2.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-internal2.msft.png":::
       <span data-ttu-id="f5887-190">The font of the **Home** and **Contact** links has changed</span><span class="sxs-lookup"><span data-stu-id="f5887-190">The font of the **Home** and **Contact** links has changed</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="f5887-191">Understand internal stylesheets</span><span class="sxs-lookup"><span data-stu-id="f5887-191">Understand internal stylesheets</span></span>  

<span data-ttu-id="f5887-192">Internal stylesheets apply styles using **selectors**.</span><span class="sxs-lookup"><span data-stu-id="f5887-192">Internal stylesheets apply styles using **selectors**.</span></span>  <span data-ttu-id="f5887-193">Selectors are patterns that may apply to one or more HTML elements.</span><span class="sxs-lookup"><span data-stu-id="f5887-193">Selectors are patterns that may apply to one or more HTML elements.</span></span>  <span data-ttu-id="f5887-194">The previous code snippet added the following style.</span><span class="sxs-lookup"><span data-stu-id="f5887-194">The previous code snippet added the following style.</span></span>  

```html
<style>
    li a {
      font-family: 'Courier New', Courier, Serif;
    }
</style>
```  

`li a` <span data-ttu-id="f5887-195">is a selector that translates to "any `<li>` element that contains an `<a>` element".</span><span class="sxs-lookup"><span data-stu-id="f5887-195">is a selector that translates to "any `<li>` element that contains an `<a>` element".</span></span>  <span data-ttu-id="f5887-196">The browser changes the font of the **Home** and **Contact** links because each of the tag groups match the pattern.</span><span class="sxs-lookup"><span data-stu-id="f5887-196">The browser changes the font of the **Home** and **Contact** links because each of the tag groups match the pattern.</span></span>  

```html
<li><a href="/">Home</a></li>
<li><a href="/contact.html">Contact</a></li>
```  

`font-family: 'Courier New', Courier, serif` <span data-ttu-id="f5887-197">is a **declaration**.</span><span class="sxs-lookup"><span data-stu-id="f5887-197">is a **declaration**.</span></span>  <span data-ttu-id="f5887-198">A declaration is made of following two parts.</span><span class="sxs-lookup"><span data-stu-id="f5887-198">A declaration is made of following two parts.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="f5887-199">property</span><span class="sxs-lookup"><span data-stu-id="f5887-199">property</span></span>**  
   :::column-end:::
   :::column span="1":::
      `font-family`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="f5887-200">The property describes a general way that you are able to change the style of the element.</span><span class="sxs-lookup"><span data-stu-id="f5887-200">The property describes a general way that you are able to change the style of the element.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="f5887-201">value</span><span class="sxs-lookup"><span data-stu-id="f5887-201">value</span></span>**  
   :::column-end:::
   :::column span="1":::
      `'Courier New', Courier, serif`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="f5887-202">The value describes exactly how the style of the element should change.</span><span class="sxs-lookup"><span data-stu-id="f5887-202">The value describes exactly how the style of the element should change.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="f5887-203">For example, `font-family: 'Courier New', Courier, serif` gives the browser the following instruction:  "Set the font of elements that match the pattern `li a` to `'Courier New'`.</span><span class="sxs-lookup"><span data-stu-id="f5887-203">For example, `font-family: 'Courier New', Courier, serif` gives the browser the following instruction:  "Set the font of elements that match the pattern `li a` to `'Courier New'`.</span></span>  <span data-ttu-id="f5887-204">If that font is not available, use `Courier`.</span><span class="sxs-lookup"><span data-stu-id="f5887-204">If that font is not available, use `Courier`.</span></span>  <span data-ttu-id="f5887-205">If that is not available, use `serif`."</span><span class="sxs-lookup"><span data-stu-id="f5887-205">If that is not available, use `serif`."</span></span>  

### <span data-ttu-id="f5887-206">Add multiple selectors to a ruleset</span><span class="sxs-lookup"><span data-stu-id="f5887-206">Add multiple selectors to a ruleset</span></span>  

<span data-ttu-id="f5887-207">A block of CSS code like what you see below is called a **ruleset**.</span><span class="sxs-lookup"><span data-stu-id="f5887-207">A block of CSS code like what you see below is called a **ruleset**.</span></span>  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

<span data-ttu-id="f5887-208">Complete the following actions to use commas to add multiple selectors to a ruleset.</span><span class="sxs-lookup"><span data-stu-id="f5887-208">Complete the following actions to use commas to add multiple selectors to a ruleset.</span></span>  

1.  <span data-ttu-id="f5887-209">In the **editor tab**, open `contact.html`.</span><span class="sxs-lookup"><span data-stu-id="f5887-209">In the **editor tab**, open `contact.html`.</span></span>  
1.  <span data-ttu-id="f5887-210">After `li a` type `, h1`.</span><span class="sxs-lookup"><span data-stu-id="f5887-210">After `li a` type `, h1`.</span></span>  
    
    ```html
    <style>
        li a, h1 {
          font-family: 'Courier New', Courier, Serif;
        }
    </style>
    ```  
    
    <span data-ttu-id="f5887-211">The previous code snippet tells the browser to style `<h1>` elements the same way that it styles elements that match the pattern `li a`.</span><span class="sxs-lookup"><span data-stu-id="f5887-211">The previous code snippet tells the browser to style `<h1>` elements the same way that it styles elements that match the pattern `li a`.</span></span>  
    
1.  <span data-ttu-id="f5887-212">Go to the **live tab**.</span><span class="sxs-lookup"><span data-stu-id="f5887-212">Go to the **live tab**.</span></span>  
1.  <span data-ttu-id="f5887-213">Choose the **Contact** link to go back to the contact page.</span><span class="sxs-lookup"><span data-stu-id="f5887-213">Choose the **Contact** link to go back to the contact page.</span></span>  <span data-ttu-id="f5887-214">Now, **Contact Me!**</span><span class="sxs-lookup"><span data-stu-id="f5887-214">Now, **Contact Me!**</span></span> <span data-ttu-id="f5887-215">has the same font as the navigation links.</span><span class="sxs-lookup"><span data-stu-id="f5887-215">has the same font as the navigation links.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-multiple1.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-multiple1.msft.png":::
       <span data-ttu-id="f5887-218">The text **Contact Me!**</span><span class="sxs-lookup"><span data-stu-id="f5887-218">The text **Contact Me!**</span></span> <span data-ttu-id="f5887-219">now has the same font as the **Home** and **Contact** links</span><span class="sxs-lookup"><span data-stu-id="f5887-219">now has the same font as the **Home** and **Contact** links</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f5887-220">Experiment with DevTools</span><span class="sxs-lookup"><span data-stu-id="f5887-220">Experiment with DevTools</span></span>  

<span data-ttu-id="f5887-221">As you continue your journey to become an expert in web development, you may find that CSS is tricky.</span><span class="sxs-lookup"><span data-stu-id="f5887-221">As you continue your journey to become an expert in web development, you may find that CSS is tricky.</span></span>  <span data-ttu-id="f5887-222">You may write some CSS and expect it to display one way, but the browser does something completely different.</span><span class="sxs-lookup"><span data-stu-id="f5887-222">You may write some CSS and expect it to display one way, but the browser does something completely different.</span></span>  <span data-ttu-id="f5887-223">Microsoft Edge DevTools makes it easy to experiment with changes and immediately see how the changes affect the page.</span><span class="sxs-lookup"><span data-stu-id="f5887-223">Microsoft Edge DevTools makes it easy to experiment with changes and immediately see how the changes affect the page.</span></span>  

### <span data-ttu-id="f5887-224">Add a declaration to an existing rulest in DevTools</span><span class="sxs-lookup"><span data-stu-id="f5887-224">Add a declaration to an existing rulest in DevTools</span></span>  

<span data-ttu-id="f5887-225">Complete the following actions to iterate on the style of an existing element, add a declaration to an existing ruleset.</span><span class="sxs-lookup"><span data-stu-id="f5887-225">Complete the following actions to iterate on the style of an existing element, add a declaration to an existing ruleset.</span></span>  

1.  <span data-ttu-id="f5887-226">Hover on the **Home** link, open the contextual menu \(right-click\), and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="f5887-226">Hover on the **Home** link, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add1.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-add1.msft.png":::
       <span data-ttu-id="f5887-228">Inspect the Home link</span><span class="sxs-lookup"><span data-stu-id="f5887-228">Inspect the Home link</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="f5887-229">DevTools opens up alongside your page.</span><span class="sxs-lookup"><span data-stu-id="f5887-229">DevTools opens up alongside your page.</span></span>  <span data-ttu-id="f5887-230">The code that represents the Home link, `<a href="/">Home</a>` is highlighted blue in the DOM Tree.</span><span class="sxs-lookup"><span data-stu-id="f5887-230">The code that represents the Home link, `<a href="/">Home</a>` is highlighted blue in the DOM Tree.</span></span>  <span data-ttu-id="f5887-231">The code snippet and preview should be familiar from [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span><span class="sxs-lookup"><span data-stu-id="f5887-231">The code snippet and preview should be familiar from [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  
    
    :::row:::
       :::column span="":::
          <span data-ttu-id="f5887-232">In the following figure, the `font-family: 'Courier New', Courier, serif` declaration that you previously added to `contact.html` is seen in the **Styles** tab below the DOM Tree.</span><span class="sxs-lookup"><span data-stu-id="f5887-232">In the following figure, the `font-family: 'Courier New', Courier, serif` declaration that you previously added to `contact.html` is seen in the **Styles** tab below the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add2.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-add2.msft.png":::
             <span data-ttu-id="f5887-234">The **Styles** tab is below the DOM Tree</span><span class="sxs-lookup"><span data-stu-id="f5887-234">The **Styles** tab is below the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="f5887-235">If your DevTools window is wide, the Styles tab is to the right of the DOM Tree.</span><span class="sxs-lookup"><span data-stu-id="f5887-235">If your DevTools window is wide, the Styles tab is to the right of the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add3.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-add3.msft.png":::
             <span data-ttu-id="f5887-237">The **Styles** tab is to the right of the DOM Tree</span><span class="sxs-lookup"><span data-stu-id="f5887-237">The **Styles** tab is to the right of the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="f5887-238">Choose the empty line below `font-family: 'Courier New', Courier, Serif` to add a new declaration.</span><span class="sxs-lookup"><span data-stu-id="f5887-238">Choose the empty line below `font-family: 'Courier New', Courier, Serif` to add a new declaration.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add4.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-add4.msft.png":::
       <span data-ttu-id="f5887-240">Add a new declaration</span><span class="sxs-lookup"><span data-stu-id="f5887-240">Add a new declaration</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-241">Type `color` and select `Enter`.</span><span class="sxs-lookup"><span data-stu-id="f5887-241">Type `color` and select `Enter`.</span></span>  <span data-ttu-id="f5887-242">The autocomplete UI suggests options as you type.</span><span class="sxs-lookup"><span data-stu-id="f5887-242">The autocomplete UI suggests options as you type.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add5.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-add5.msft.png":::
       <span data-ttu-id="f5887-244">Type</span><span class="sxs-lookup"><span data-stu-id="f5887-244">Type</span></span> `color`  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-245">Type `magenta` and select `Enter`.</span><span class="sxs-lookup"><span data-stu-id="f5887-245">Type `magenta` and select `Enter`.</span></span>  <span data-ttu-id="f5887-246">All of the text on the contact page is now magenta.</span><span class="sxs-lookup"><span data-stu-id="f5887-246">All of the text on the contact page is now magenta.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add6.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-add6.msft.png":::
       <span data-ttu-id="f5887-248">Type</span><span class="sxs-lookup"><span data-stu-id="f5887-248">Type</span></span> `magenta`  
    :::image-end:::  
    
### <span data-ttu-id="f5887-249">Edit a declaration in DevTools</span><span class="sxs-lookup"><span data-stu-id="f5887-249">Edit a declaration in DevTools</span></span>  

<span data-ttu-id="f5887-250">Complete the following actions to edit existing declarations in DevTools.</span><span class="sxs-lookup"><span data-stu-id="f5887-250">Complete the following actions to edit existing declarations in DevTools.</span></span>  

1.  <span data-ttu-id="f5887-251">Choose the magenta square next to `magenta`.</span><span class="sxs-lookup"><span data-stu-id="f5887-251">Choose the magenta square next to `magenta`.</span></span>  <span data-ttu-id="f5887-252">A color picker pops up.</span><span class="sxs-lookup"><span data-stu-id="f5887-252">A color picker pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit1.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-edit1.msft.png":::
       <span data-ttu-id="f5887-254">The Color Picker</span><span class="sxs-lookup"><span data-stu-id="f5887-254">The Color Picker</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-255">Use the color picker to change the font text to a color that you like.</span><span class="sxs-lookup"><span data-stu-id="f5887-255">Use the color picker to change the font text to a color that you like.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit2.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-edit2.msft.png":::
       <span data-ttu-id="f5887-257">Change the font color to purple with the Color Picker</span><span class="sxs-lookup"><span data-stu-id="f5887-257">Change the font color to purple with the Color Picker</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="f5887-258">Add a new ruleset in DevTools</span><span class="sxs-lookup"><span data-stu-id="f5887-258">Add a new ruleset in DevTools</span></span>  

<span data-ttu-id="f5887-259">Complete the following actions to add new rulesets in DevTools.</span><span class="sxs-lookup"><span data-stu-id="f5887-259">Complete the following actions to add new rulesets in DevTools.</span></span>  

1.  <span data-ttu-id="f5887-260">Choose **New Style Rule** \(![New Style Rule][ImageNewStyleRuleIcon]\) which is next to **.cls**.</span><span class="sxs-lookup"><span data-stu-id="f5887-260">Choose **New Style Rule** \(![New Style Rule][ImageNewStyleRuleIcon]\) which is next to **.cls**.</span></span>  <span data-ttu-id="f5887-261">An empty ruleset appears with `a` as the selector.</span><span class="sxs-lookup"><span data-stu-id="f5887-261">An empty ruleset appears with `a` as the selector.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule1.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-rule1.msft.png":::
       <span data-ttu-id="f5887-263">Add a new rule</span><span class="sxs-lookup"><span data-stu-id="f5887-263">Add a new rule</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-264">Replace `a` with `a:hover`.</span><span class="sxs-lookup"><span data-stu-id="f5887-264">Replace `a` with `a:hover`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule2.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-rule2.msft.png":::
       <span data-ttu-id="f5887-266">Replace `a` with</span><span class="sxs-lookup"><span data-stu-id="f5887-266">Replace `a` with</span></span> `a:hover`  
    :::image-end:::  
    
    `:hover` <span data-ttu-id="f5887-267">is a **pseudo-class**.</span><span class="sxs-lookup"><span data-stu-id="f5887-267">is a **pseudo-class**.</span></span>  <span data-ttu-id="f5887-268">Use pseudo-classes for style elements that may enter special states.</span><span class="sxs-lookup"><span data-stu-id="f5887-268">Use pseudo-classes for style elements that may enter special states.</span></span>  <span data-ttu-id="f5887-269">For example, the `a:hover` style only takes effect when you are hovering over an `<a>` element.</span><span class="sxs-lookup"><span data-stu-id="f5887-269">For example, the `a:hover` style only takes effect when you are hovering over an `<a>` element.</span></span>  
    
1.  <span data-ttu-id="f5887-270">Choose between the brackets to add a new declaration.</span><span class="sxs-lookup"><span data-stu-id="f5887-270">Choose between the brackets to add a new declaration.</span></span>  
1.  <span data-ttu-id="f5887-271">Type `background-color` for the declaration name and select `Enter`.</span><span class="sxs-lookup"><span data-stu-id="f5887-271">Type `background-color` for the declaration name and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule3.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-rule3.msft.png":::
       <span data-ttu-id="f5887-273">Type</span><span class="sxs-lookup"><span data-stu-id="f5887-273">Type</span></span> `background-color`  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-274">Type `green` for the declaration value and select `Enter`.</span><span class="sxs-lookup"><span data-stu-id="f5887-274">Type `green` for the declaration value and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule4.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-rule4.msft.png":::
       <span data-ttu-id="f5887-276">Type</span><span class="sxs-lookup"><span data-stu-id="f5887-276">Type</span></span> `green`  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-277">Hover your mouse over the **Home** link.</span><span class="sxs-lookup"><span data-stu-id="f5887-277">Hover your mouse over the **Home** link.</span></span>  <span data-ttu-id="f5887-278">The background of the link turns green.</span><span class="sxs-lookup"><span data-stu-id="f5887-278">The background of the link turns green.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule5.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-rule5.msft.png":::
       <span data-ttu-id="f5887-280">Hover over the Home link to reveal its green background</span><span class="sxs-lookup"><span data-stu-id="f5887-280">Hover over the Home link to reveal its green background</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f5887-281">Re-use styles across pages with external stylesheets</span><span class="sxs-lookup"><span data-stu-id="f5887-281">Re-use styles across pages with external stylesheets</span></span>  

<span data-ttu-id="f5887-282">In a previous step, you added the following code snippet as an internal stylesheet to `contact.html`.</span><span class="sxs-lookup"><span data-stu-id="f5887-282">In a previous step, you added the following code snippet as an internal stylesheet to `contact.html`.</span></span>  

```html
...
    ...
        ...
        <style>
            li a, h1 {
              font-family: 'Courier New', Courier, Serif;
            }
        </style>
        ...
    ...
...
```  

<span data-ttu-id="f5887-283">What if you wanted to style `index.html` the same way?</span><span class="sxs-lookup"><span data-stu-id="f5887-283">What if you wanted to style `index.html` the same way?</span></span>  <span data-ttu-id="f5887-284">What if you had a large number of pages to which you wanted to apply your styles?</span><span class="sxs-lookup"><span data-stu-id="f5887-284">What if you had a large number of pages to which you wanted to apply your styles?</span></span>  <span data-ttu-id="f5887-285">You would have to copy and paste the internal stylesheet into every single web page on your site.</span><span class="sxs-lookup"><span data-stu-id="f5887-285">You would have to copy and paste the internal stylesheet into every single web page on your site.</span></span>  <span data-ttu-id="f5887-286">Complete the following actions to add an **External stylesheet** to allow you to write your CSS once and apply it to multiple pages.</span><span class="sxs-lookup"><span data-stu-id="f5887-286">Complete the following actions to add an **External stylesheet** to allow you to write your CSS once and apply it to multiple pages.</span></span>  

1.  <span data-ttu-id="f5887-287">First, reload the live tab to remove the changes that you made in DevTools.</span><span class="sxs-lookup"><span data-stu-id="f5887-287">First, reload the live tab to remove the changes that you made in DevTools.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external1.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-external1.msft.png":::
        <span data-ttu-id="f5887-289">After you refresh the page, the changes that were made in DevTools are gone</span><span class="sxs-lookup"><span data-stu-id="f5887-289">After you refresh the page, the changes that were made in DevTools are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-290">Go back to the **editor tab** and open `contact.html`.</span><span class="sxs-lookup"><span data-stu-id="f5887-290">Go back to the **editor tab** and open `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external2.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-external2.msft.png":::
       <span data-ttu-id="f5887-292">contact.html</span><span class="sxs-lookup"><span data-stu-id="f5887-292">contact.html</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-293">Delete everything between `<style>` and `</style>`, including `<style>` and `</style>`.</span><span class="sxs-lookup"><span data-stu-id="f5887-293">Delete everything between `<style>` and `</style>`, including `<style>` and `</style>`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external3.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-external3.msft.png":::
       <span data-ttu-id="f5887-295">The style tag has been removed</span><span class="sxs-lookup"><span data-stu-id="f5887-295">The style tag has been removed</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-296">Go to `index.html` and remove `style="background-color: aliceblue;"` from the `<nav>` tag.</span><span class="sxs-lookup"><span data-stu-id="f5887-296">Go to `index.html` and remove `style="background-color: aliceblue;"` from the `<nav>` tag.</span></span>  <span data-ttu-id="f5887-297">You have now removed all of the CSS that you previously added to your site.</span><span class="sxs-lookup"><span data-stu-id="f5887-297">You have now removed all of the CSS that you previously added to your site.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external4.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-external4.msft.png":::
       <span data-ttu-id="f5887-299">The inline style has been removed from the nav element</span><span class="sxs-lookup"><span data-stu-id="f5887-299">The inline style has been removed from the nav element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-300">Choose **New File**.</span><span class="sxs-lookup"><span data-stu-id="f5887-300">Choose **New File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external5.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-external5.msft.png":::
       <span data-ttu-id="f5887-302">The new file dialog</span><span class="sxs-lookup"><span data-stu-id="f5887-302">The new file dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-303">Replace `cool-file.js` with `style.css` and choose **Add File**.</span><span class="sxs-lookup"><span data-stu-id="f5887-303">Replace `cool-file.js` with `style.css` and choose **Add File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external6.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-external6.msft.png":::
       <span data-ttu-id="f5887-305">Type</span><span class="sxs-lookup"><span data-stu-id="f5887-305">Type</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-306">Add the following code snippet to your `style.css` file.</span><span class="sxs-lookup"><span data-stu-id="f5887-306">Add the following code snippet to your `style.css` file.</span></span>  
    
    ```css
    li a, h1 {
      font-family: 'Courier New', Courier, Serif;
    }
    a:hover {
      background-color: green;
    }
    nav {
      background-color: aliceblue;
    }
    ```  
    
    :::image type="complex" source="../media/beginners-css-external7.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-external7.msft.png":::
       <span data-ttu-id="f5887-308">Add code to</span><span class="sxs-lookup"><span data-stu-id="f5887-308">Add code to</span></span> `style.css`  
    :::image-end:::  
    
    <span data-ttu-id="f5887-309">Ensure that you have created an external stylesheet.</span><span class="sxs-lookup"><span data-stu-id="f5887-309">Ensure that you have created an external stylesheet.</span></span> <span data-ttu-id="f5887-310">Your HTML is not aware that it exists.</span><span class="sxs-lookup"><span data-stu-id="f5887-310">Your HTML is not aware that it exists.</span></span>  
    
1.  <span data-ttu-id="f5887-311">Open `index.html`.</span><span class="sxs-lookup"><span data-stu-id="f5887-311">Open `index.html`.</span></span>  
1.  <span data-ttu-id="f5887-312">Add `<link rel="stylesheet" href="style.css">` to your HTML.</span><span class="sxs-lookup"><span data-stu-id="f5887-312">Add `<link rel="stylesheet" href="style.css">` to your HTML.</span></span>  
    
    ```html
    <head>
        ...
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="style.css">
    </head>
    ```  
    
    :::image type="complex" source="../media/beginners-css-external8.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-external8.msft.png":::
       <span data-ttu-id="f5887-314">Link to</span><span class="sxs-lookup"><span data-stu-id="f5887-314">Link to</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-315">Open the `contact.html` file and add the link there.</span><span class="sxs-lookup"><span data-stu-id="f5887-315">Open the `contact.html` file and add the link there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external9.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-external9.msft.png":::
       <span data-ttu-id="f5887-317">Link to `style.css` in</span><span class="sxs-lookup"><span data-stu-id="f5887-317">Link to `style.css` in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-318">Go to the **live tab**.  The home page now has the same font from the last section and a blue navigation section.</span><span class="sxs-lookup"><span data-stu-id="f5887-318">Go to the **live tab**.  The home page now has the same font from the last section and a blue navigation section.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external10.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-external10.msft.png":::
       <span data-ttu-id="f5887-320">The home page</span><span class="sxs-lookup"><span data-stu-id="f5887-320">The home page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-321">Choose the **Contact** link to go to the contact page.</span><span class="sxs-lookup"><span data-stu-id="f5887-321">Choose the **Contact** link to go to the contact page.</span></span>  <span data-ttu-id="f5887-322">The contact page has the same formatting as the home page.</span><span class="sxs-lookup"><span data-stu-id="f5887-322">The contact page has the same formatting as the home page.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external11.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-external11.msft.png":::
       <span data-ttu-id="f5887-324">The contact page</span><span class="sxs-lookup"><span data-stu-id="f5887-324">The contact page</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f5887-325">Use a CSS framework</span><span class="sxs-lookup"><span data-stu-id="f5887-325">Use a CSS framework</span></span>  

<span data-ttu-id="f5887-326">**CSS frameworks** are collections of styles built by other developers that make it easier to create attractive web sites.</span><span class="sxs-lookup"><span data-stu-id="f5887-326">**CSS frameworks** are collections of styles built by other developers that make it easier to create attractive web sites.</span></span>  <span data-ttu-id="f5887-327">Instead of defining styles yourself, a framework provides you a collection of styles that you are able to use on your page elements.</span><span class="sxs-lookup"><span data-stu-id="f5887-327">Instead of defining styles yourself, a framework provides you a collection of styles that you are able to use on your page elements.</span></span>  

1.  <span data-ttu-id="f5887-328">Copy the following code:</span><span class="sxs-lookup"><span data-stu-id="f5887-328">Copy the following code:</span></span>  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  <span data-ttu-id="f5887-329">Go to the editing tab and paste the code into `contact.html`.</span><span class="sxs-lookup"><span data-stu-id="f5887-329">Go to the editing tab and paste the code into `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework1.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-framework1.msft.png":::
       <span data-ttu-id="f5887-331">Link to the framework in</span><span class="sxs-lookup"><span data-stu-id="f5887-331">Link to the framework in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-332">Open the `index.html` file and add the code there.</span><span class="sxs-lookup"><span data-stu-id="f5887-332">Open the `index.html` file and add the code there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework2.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-framework2.msft.png":::
       <span data-ttu-id="f5887-334">Link to the framework in</span><span class="sxs-lookup"><span data-stu-id="f5887-334">Link to the framework in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-335">Go back to the live tab to view your changes.</span><span class="sxs-lookup"><span data-stu-id="f5887-335">Go back to the live tab to view your changes.</span></span>  <span data-ttu-id="f5887-336">While the background color of the `<nav>` element and the font of the `<li>` and `<a>` elements are the same, the font of the other elements has changed.</span><span class="sxs-lookup"><span data-stu-id="f5887-336">While the background color of the `<nav>` element and the font of the `<li>` and `<a>` elements are the same, the font of the other elements has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework3.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-framework3.msft.png":::
       <span data-ttu-id="f5887-338">Some of the font on the home page changed because of the framework</span><span class="sxs-lookup"><span data-stu-id="f5887-338">Some of the font on the home page changed because of the framework</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="f5887-339">Use a class</span><span class="sxs-lookup"><span data-stu-id="f5887-339">Use a class</span></span>  

<span data-ttu-id="f5887-340">In the last section, you added Bootstrap to your web pages, which changed the fonts of some of the elements on your site.</span><span class="sxs-lookup"><span data-stu-id="f5887-340">In the last section, you added Bootstrap to your web pages, which changed the fonts of some of the elements on your site.</span></span>  <span data-ttu-id="f5887-341">CSS frameworks help you make major changes to your page with very little code.</span><span class="sxs-lookup"><span data-stu-id="f5887-341">CSS frameworks help you make major changes to your page with very little code.</span></span>  <span data-ttu-id="f5887-342">Complete the following actions to change your header.</span><span class="sxs-lookup"><span data-stu-id="f5887-342">Complete the following actions to change your header.</span></span>  

1.  <span data-ttu-id="f5887-343">Copy the following code snippet.</span><span class="sxs-lookup"><span data-stu-id="f5887-343">Copy the following code snippet.</span></span>  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  <span data-ttu-id="f5887-344">Add the previous code snippet to your `<header>` tag in `index.html`.</span><span class="sxs-lookup"><span data-stu-id="f5887-344">Add the previous code snippet to your `<header>` tag in `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron1.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-jumbotron1.msft.png":::
       <span data-ttu-id="f5887-346">Add classes in</span><span class="sxs-lookup"><span data-stu-id="f5887-346">Add classes in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-347">Add the code to your `<header>` tag in `contact.html`.</span><span class="sxs-lookup"><span data-stu-id="f5887-347">Add the code to your `<header>` tag in `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron2.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-jumbotron2.msft.png":::
       <span data-ttu-id="f5887-349">Add classes in</span><span class="sxs-lookup"><span data-stu-id="f5887-349">Add classes in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-350">View your changes in the live tab.  There is a big, grey box around your header.</span><span class="sxs-lookup"><span data-stu-id="f5887-350">View your changes in the live tab.  There is a big, grey box around your header.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron3.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-jumbotron3.msft.png":::
       <span data-ttu-id="f5887-352">The header now has a big, grey box around it</span><span class="sxs-lookup"><span data-stu-id="f5887-352">The header now has a big, grey box around it</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="f5887-353">Understand classes</span><span class="sxs-lookup"><span data-stu-id="f5887-353">Understand classes</span></span>  

<span data-ttu-id="f5887-354">Classes let you assign collections of styles to arbitrary elements.</span><span class="sxs-lookup"><span data-stu-id="f5887-354">Classes let you assign collections of styles to arbitrary elements.</span></span>  <span data-ttu-id="f5887-355">Use the following code snippet to apply several styles to the `<header>` element after you set the `class` attribute to `jumbotron`.</span><span class="sxs-lookup"><span data-stu-id="f5887-355">Use the following code snippet to apply several styles to the `<header>` element after you set the `class` attribute to `jumbotron`.</span></span>  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

<span data-ttu-id="f5887-356">One advantage of a class is that it lets you apply styles to whatever elements you want.</span><span class="sxs-lookup"><span data-stu-id="f5887-356">One advantage of a class is that it lets you apply styles to whatever elements you want.</span></span>  <span data-ttu-id="f5887-357">For example, suppose you want to set the background color of some `<p>` elements to purple, but not all `<p>` elements.</span><span class="sxs-lookup"><span data-stu-id="f5887-357">For example, suppose you want to set the background color of some `<p>` elements to purple, but not all `<p>` elements.</span></span>  <span data-ttu-id="f5887-358">Use the following code snippet to define the style in a class.</span><span class="sxs-lookup"><span data-stu-id="f5887-358">Use the following code snippet to define the style in a class.</span></span>  

```css
.custom-background {
  background-color: purple;
}
```  

<span data-ttu-id="f5887-359">Next, apply the class to only the `<p>` elements that you want to style.</span><span class="sxs-lookup"><span data-stu-id="f5887-359">Next, apply the class to only the `<p>` elements that you want to style.</span></span>  

```html
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
```  

### <span data-ttu-id="f5887-360">Align elements</span><span class="sxs-lookup"><span data-stu-id="f5887-360">Align elements</span></span>  

<span data-ttu-id="f5887-361">Complete the following actions to bootstrap and provide classes for aligning elements.</span><span class="sxs-lookup"><span data-stu-id="f5887-361">Complete the following actions to bootstrap and provide classes for aligning elements.</span></span>  

1.  <span data-ttu-id="f5887-362">Go back to the editor tab and open `index.html`.</span><span class="sxs-lookup"><span data-stu-id="f5887-362">Go back to the editor tab and open `index.html`.</span></span>  
1.  <span data-ttu-id="f5887-363">Add `class="container-fluid"` to your `<body>` tag.</span><span class="sxs-lookup"><span data-stu-id="f5887-363">Add `class="container-fluid"` to your `<body>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align1.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-align1.msft.png":::
       <span data-ttu-id="f5887-365">Add the `container-fluid` class</span><span class="sxs-lookup"><span data-stu-id="f5887-365">Add the `container-fluid` class</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-366">Wrap your `<nav>` and `<main>` elements in `<div class="row">`.</span><span class="sxs-lookup"><span data-stu-id="f5887-366">Wrap your `<nav>` and `<main>` elements in `<div class="row">`.</span></span>  <span data-ttu-id="f5887-367">Make sure to put `</div>` after `</main>` in order to properly close the new tag.</span><span class="sxs-lookup"><span data-stu-id="f5887-367">Make sure to put `</div>` after `</main>` in order to properly close the new tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align2.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-align2.msft.png":::
       <span data-ttu-id="f5887-369">Add a row</span><span class="sxs-lookup"><span data-stu-id="f5887-369">Add a row</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-370">Add `class="col-3"` to your `<nav>` tag and `class="col-9"` to your `<main>` tag.</span><span class="sxs-lookup"><span data-stu-id="f5887-370">Add `class="col-3"` to your `<nav>` tag and `class="col-9"` to your `<main>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align3.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-align3.msft.png":::
       <span data-ttu-id="f5887-372">Add the `col-3` and `col-9` classes</span><span class="sxs-lookup"><span data-stu-id="f5887-372">Add the `col-3` and `col-9` classes</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f5887-373">View your changes in the live tab.</span><span class="sxs-lookup"><span data-stu-id="f5887-373">View your changes in the live tab.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align4.msft.png" alt-text="What your site currently looks like" lightbox="../media/beginners-css-align4.msft.png":::
       <span data-ttu-id="f5887-375">The nav content is now to the left of the main content</span><span class="sxs-lookup"><span data-stu-id="f5887-375">The nav content is now to the left of the main content</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f5887-376">Next steps</span><span class="sxs-lookup"><span data-stu-id="f5887-376">Next steps</span></span>  

<span data-ttu-id="f5887-377">Congratulations, you are done.</span><span class="sxs-lookup"><span data-stu-id="f5887-377">Congratulations, you are done.</span></span>  

*   <span data-ttu-id="f5887-378">The best way to get better at web development is to build more sites.</span><span class="sxs-lookup"><span data-stu-id="f5887-378">The best way to get better at web development is to build more sites.</span></span>  <span data-ttu-id="f5887-379">Do not worry about breaking stuff.</span><span class="sxs-lookup"><span data-stu-id="f5887-379">Do not worry about breaking stuff.</span></span>  <span data-ttu-id="f5887-380">Just have fun and learn as much as possible along the way.</span><span class="sxs-lookup"><span data-stu-id="f5887-380">Just have fun and learn as much as possible along the way.</span></span>  
*   <span data-ttu-id="f5887-381">To learn more about styling web pages, see [Introduction to CSS][MDNCssFirstSteps].</span><span class="sxs-lookup"><span data-stu-id="f5887-381">To learn more about styling web pages, see [Introduction to CSS][MDNCssFirstSteps].</span></span>  
*   <span data-ttu-id="f5887-382">To learn more about how to use DevTools to experiment with the CSS of a page, see [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span><span class="sxs-lookup"><span data-stu-id="f5887-382">To learn more about how to use DevTools to experiment with the CSS of a page, see [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

<!--- image links --->  

[ImageNewStyleRuleIcon]: ../media/new-style-rule-icon.msft.png  

<!--- links  --->  

[DevtoolsBeginnersHtml]: ./html.md "DevTools for Beginners: Get Started with HTML and the DOM | Microsoft Docs"  
[DevtoolsCssIndex]: ../css/index.md "Get Started With Viewing And Changing CSS | Microsoft Docs"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index.html - cooked-amphibian | Glitch"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS first steps | MDN"  

> [!NOTE]
> <span data-ttu-id="f5887-388">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f5887-388">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f5887-389">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/css) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span><span class="sxs-lookup"><span data-stu-id="f5887-389">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/css) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f5887-391">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f5887-391">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
