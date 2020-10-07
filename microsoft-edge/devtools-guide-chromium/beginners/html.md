---
description: Get Started with HTML and the DOM
title: 'DevTools for beginners: Get started with HTML and the DOM'
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web developement, f12 tools, devtools
ms.openlocfilehash: 182885cb97dbd1672d33b257569b0d841466985b
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993280"
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

# <span data-ttu-id="5e3c1-104">DevTools for beginners: Get started with HTML and the DOM</span><span class="sxs-lookup"><span data-stu-id="5e3c1-104">DevTools for beginners: Get started with HTML and the DOM</span></span>   

<span data-ttu-id="5e3c1-105">This is the first in a series of tutorials that teach you the basics of web development.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-105">This is the first in a series of tutorials that teach you the basics of web development.</span></span>  <span data-ttu-id="5e3c1-106">You will also learn about a set of web developer tools called Microsoft Edge DevTools that can increase your productivity.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-106">You will also learn about a set of web developer tools called Microsoft Edge DevTools that can increase your productivity.</span></span>  

<span data-ttu-id="5e3c1-107">In this particular tutorial, you learn about HTML and the DOM.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-107">In this particular tutorial, you learn about HTML and the DOM.</span></span>  <span data-ttu-id="5e3c1-108">HTML is one of the core technologies of web development.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-108">HTML is one of the core technologies of web development.</span></span>  <span data-ttu-id="5e3c1-109">It is the language that controls the structure and content of webpages.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-109">It is the language that controls the structure and content of webpages.</span></span>  <span data-ttu-id="5e3c1-110">The DOM is also related to the structure and content of webpages, but you'll learn more about that later.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-110">The DOM is also related to the structure and content of webpages, but you'll learn more about that later.</span></span>  

## <span data-ttu-id="5e3c1-111">Goals</span><span class="sxs-lookup"><span data-stu-id="5e3c1-111">Goals</span></span>   

<span data-ttu-id="5e3c1-112">You are going to learn web development by actually building your own website.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-112">You are going to learn web development by actually building your own website.</span></span>  <span data-ttu-id="5e3c1-113">By the time you complete all of the tutorials in the *DevTools for Beginners* series, your finished site will look like in the following figure.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-113">By the time you complete all of the tutorials in the *DevTools for Beginners* series, your finished site will look like in the following figure.</span></span>  

:::image type="complex" source="../media/beginners-html-finished.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-finished.msft.png":::
   <span data-ttu-id="5e3c1-115">The finished site</span><span class="sxs-lookup"><span data-stu-id="5e3c1-115">The finished site</span></span>  
:::image-end:::  

<span data-ttu-id="5e3c1-116">By the end of this tutorial, you will understand:</span><span class="sxs-lookup"><span data-stu-id="5e3c1-116">By the end of this tutorial, you will understand:</span></span>  

*   <span data-ttu-id="5e3c1-117">How HTML and the DOM create the content that you see on webpages.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-117">How HTML and the DOM create the content that you see on webpages.</span></span>  
*   <span data-ttu-id="5e3c1-118">How Microsoft Edge DevTools can help you experiment with HTML and DOM changes.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-118">How Microsoft Edge DevTools can help you experiment with HTML and DOM changes.</span></span>  
*   <span data-ttu-id="5e3c1-119">The difference between HTML and the DOM.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-119">The difference between HTML and the DOM.</span></span>  

<span data-ttu-id="5e3c1-120">You'll also have a real website!</span><span class="sxs-lookup"><span data-stu-id="5e3c1-120">You'll also have a real website!</span></span>  <span data-ttu-id="5e3c1-121">You can use this site to host your resume or blog.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-121">You can use this site to host your resume or blog.</span></span>  

## <span data-ttu-id="5e3c1-122">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="5e3c1-122">Prerequisites</span></span>   

<span data-ttu-id="5e3c1-123">Before attempting this tutorial, complete the following prerequisites:</span><span class="sxs-lookup"><span data-stu-id="5e3c1-123">Before attempting this tutorial, complete the following prerequisites:</span></span>  

*   <span data-ttu-id="5e3c1-124">If you are unfamiliar with HTML, read [Getting Started with HTML][MDNGettingStartedHtml].</span><span class="sxs-lookup"><span data-stu-id="5e3c1-124">If you are unfamiliar with HTML, read [Getting Started with HTML][MDNGettingStartedHtml].</span></span>  
*   <span data-ttu-id="5e3c1-125">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-125">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="5e3c1-126">This tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-126">This tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <span data-ttu-id="5e3c1-127">Set up your code</span><span class="sxs-lookup"><span data-stu-id="5e3c1-127">Set up your code</span></span>   

<span data-ttu-id="5e3c1-128">You are going to build your site in an online code editor called Glitch.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-128">You are going to build your site in an online code editor called Glitch.</span></span>  

1.  <span data-ttu-id="5e3c1-129">Open the [source code][GlitchAlluringShockIndex].</span><span class="sxs-lookup"><span data-stu-id="5e3c1-129">Open the [source code][GlitchAlluringShockIndex].</span></span>  <span data-ttu-id="5e3c1-130">This tab will be called the **editor tab** throughout this tutorial.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-130">This tab will be called the **editor tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup1.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-setup1.msft.png":::
       <span data-ttu-id="5e3c1-132">The editor tab</span><span class="sxs-lookup"><span data-stu-id="5e3c1-132">The editor tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5e3c1-133">Click **alluring-shock**.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-133">Click **alluring-shock**.</span></span>  <span data-ttu-id="5e3c1-134">The Project Options menu opens in the top-left corner.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-134">The Project Options menu opens in the top-left corner.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup2.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-setup2.msft.png":::
       <span data-ttu-id="5e3c1-136">The Project Options menu</span><span class="sxs-lookup"><span data-stu-id="5e3c1-136">The Project Options menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5e3c1-137">Click **Remix Project**.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-137">Click **Remix Project**.</span></span>  <span data-ttu-id="5e3c1-138">Glitch creates a copy of the project that you can edit and randomly generates a new name for the project.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-138">Glitch creates a copy of the project that you can edit and randomly generates a new name for the project.</span></span>  <span data-ttu-id="5e3c1-139">The content is the same as before.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-139">The content is the same as before.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup3.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-setup3.msft.png":::
       <span data-ttu-id="5e3c1-141">The remixed project</span><span class="sxs-lookup"><span data-stu-id="5e3c1-141">The remixed project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5e3c1-142">If you plan on completing the next tutorial in this series, click **Sign In** and sign in to Glitch with your GitHub or Facebook account.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-142">If you plan on completing the next tutorial in this series, click **Sign In** and sign in to Glitch with your GitHub or Facebook account.</span></span>  <span data-ttu-id="5e3c1-143">If you don't sign in you will lose the ability to edit this project once you close the editing tab.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-143">If you don't sign in you will lose the ability to edit this project once you close the editing tab.</span></span>  
1.  <span data-ttu-id="5e3c1-144">Click **Show** and select **In a New Window**.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-144">Click **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="5e3c1-145">A new tab opens, showing you the live page.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-145">A new tab opens, showing you the live page.</span></span>  <span data-ttu-id="5e3c1-146">This tab will be called the **live tab** throughout this tutorial.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-146">This tab will be called the **live tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup4.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-setup4.msft.png":::
       <span data-ttu-id="5e3c1-148">The live tab</span><span class="sxs-lookup"><span data-stu-id="5e3c1-148">The live tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="5e3c1-149">Add content</span><span class="sxs-lookup"><span data-stu-id="5e3c1-149">Add content</span></span>   

<span data-ttu-id="5e3c1-150">Your site is pretty empty.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-150">Your site is pretty empty.</span></span>  <span data-ttu-id="5e3c1-151">Follow the steps below to add some content to it!</span><span class="sxs-lookup"><span data-stu-id="5e3c1-151">Follow the steps below to add some content to it!</span></span>  

1.  <span data-ttu-id="5e3c1-152">In the **editor tab**, replace `<!-- You're "About Me" will go here.  -->` with `<h1>About Me</h1>`.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-152">In the **editor tab**, replace `<!-- You're "About Me" will go here.  -->` with `<h1>About Me</h1>`.</span></span>  
    
    :::row:::
       :::column span="":::
          ```html
          ...
              ...
              <body>
                  <p> Your site!</p>
                  <main>
                      <h1>About Me</h1>
                  </main>
                  ...
              ...
          ...
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add1.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-add1.msft.png":::
             <span data-ttu-id="5e3c1-154">The new code is highlighted in the editor tab</span><span class="sxs-lookup"><span data-stu-id="5e3c1-154">The new code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="5e3c1-155">View your changes in the **live tab**.  The text `About Me` is visible on the page.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-155">View your changes in the **live tab**.  The text `About Me` is visible on the page.</span></span>  <span data-ttu-id="5e3c1-156">It's larger than the rest of the text, because the `<h1>` element represents a section heading.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-156">It's larger than the rest of the text, because the `<h1>` element represents a section heading.</span></span>  <span data-ttu-id="5e3c1-157">Your web browser automatically styles headings in larger font sizes.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-157">Your web browser automatically styles headings in larger font sizes.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-add2.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-add2.msft.png":::
       <span data-ttu-id="5e3c1-159">The new heading is visible in the live tab</span><span class="sxs-lookup"><span data-stu-id="5e3c1-159">The new heading is visible in the live tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5e3c1-160">Back in the **editor tab**, insert `<p>I am learning HTML.  Recent accomplishments:</p>` on the line below where you just put `<h1>About Me</h1>`.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-160">Back in the **editor tab**, insert `<p>I am learning HTML.  Recent accomplishments:</p>` on the line below where you just put `<h1>About Me</h1>`.</span></span>  
    
    :::row:::
       :::column span="":::
          ```html
          ...
              ...
              <body>
                  <p> Your site!</p>
                  <main>
                      <h1>About Me</h1>
                      <p>I am learning web development.  Recent accomplishments:</p>
                  </main>
                  ...
              ...
          ...
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add3.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-add3.msft.png":::
             <span data-ttu-id="5e3c1-162">The new code is highlighted in the editor tab</span><span class="sxs-lookup"><span data-stu-id="5e3c1-162">The new code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="5e3c1-163">View your change in the **live tab**.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-163">View your change in the **live tab**.</span></span>  
1.  <span data-ttu-id="5e3c1-164">Back in the **editor tab**, add a list of your accomplishments:</span><span class="sxs-lookup"><span data-stu-id="5e3c1-164">Back in the **editor tab**, add a list of your accomplishments:</span></span>  
    
    :::row:::
       :::column span="":::
          ```html
          ...
              ...
                  ...
                  <p>I am learning web development.  Recent accomplishments:</p>
                  <ul>
                      <li>Learned how to set up my code in Glitch.</li>
                      <li>Added content to my HTML.</li>
                      <li>TODO: Learn how to use Microsoft Edge DevTools to experiment with content changes.</li>
                      <li>TODO: Learn the difference between HTML and the DOM.</li>
                  </ul>
                  ...
              ...
          ...
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add4.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-add4.msft.png":::
             <span data-ttu-id="5e3c1-166">The new code is highlighted in the editor tab</span><span class="sxs-lookup"><span data-stu-id="5e3c1-166">The new code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="5e3c1-167">Again, go back to the **live tab** to make sure that the new content is displaying correctly.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-167">Again, go back to the **live tab** to make sure that the new content is displaying correctly.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-add5.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-add5.msft.png":::
       <span data-ttu-id="5e3c1-169">The new list is visible in the live tab</span><span class="sxs-lookup"><span data-stu-id="5e3c1-169">The new list is visible in the live tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="5e3c1-170">Experiment with content changes in Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="5e3c1-170">Experiment with content changes in Microsoft Edge DevTools</span></span>   

<span data-ttu-id="5e3c1-171">If you were developing a big page with a lot of HTML, you can imagine that it might be somewhat tedious to go back-and-forth between the editor tab and the live tab hundreds of times in order to see your changes, especially if you weren't sure what exactly to put on the page.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-171">If you were developing a big page with a lot of HTML, you can imagine that it might be somewhat tedious to go back-and-forth between the editor tab and the live tab hundreds of times in order to see your changes, especially if you weren't sure what exactly to put on the page.</span></span>  <span data-ttu-id="5e3c1-172">Microsoft Edge DevTools can help you experiment with content changes without ever leaving the live tab.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-172">Microsoft Edge DevTools can help you experiment with content changes without ever leaving the live tab.</span></span>  

### <span data-ttu-id="5e3c1-173">Learn the difference between HTML and the DOM</span><span class="sxs-lookup"><span data-stu-id="5e3c1-173">Learn the difference between HTML and the DOM</span></span>   

<span data-ttu-id="5e3c1-174">Before you start editing your content from Microsoft Edge DevTools, it's helpful to understand the difference between HTML and the DOM.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-174">Before you start editing your content from Microsoft Edge DevTools, it's helpful to understand the difference between HTML and the DOM.</span></span>  <span data-ttu-id="5e3c1-175">The best way to learn is by example:</span><span class="sxs-lookup"><span data-stu-id="5e3c1-175">The best way to learn is by example:</span></span>  

1.  <span data-ttu-id="5e3c1-176">Go to the **live tab**.  At the bottom of your page you see the text `A new element!?!`.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-176">Go to the **live tab**.  At the bottom of your page you see the text `A new element!?!`.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom1.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-dom1.msft.png":::
       <span data-ttu-id="5e3c1-179">At the bottom of the page the text A new element!?!</span><span class="sxs-lookup"><span data-stu-id="5e3c1-179">At the bottom of the page the text A new element!?!</span></span> <span data-ttu-id="5e3c1-180">can be seen</span><span class="sxs-lookup"><span data-stu-id="5e3c1-180">can be seen</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5e3c1-181">Go back to the **editor tab** and try to find this text in `index.html`.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-181">Go back to the **editor tab** and try to find this text in `index.html`.</span></span>  <span data-ttu-id="5e3c1-182">It's not there!</span><span class="sxs-lookup"><span data-stu-id="5e3c1-182">It's not there!</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom2.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-dom2.msft.png":::
       <span data-ttu-id="5e3c1-185">The mystery text `A new element!?!` is nowhere to be found in</span><span class="sxs-lookup"><span data-stu-id="5e3c1-185">The mystery text `A new element!?!` is nowhere to be found in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="5e3c1-186">Go back to the **live tab**, right-click `A new element!?!`, and select **Inspect**.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-186">Go back to the **live tab**, right-click `A new element!?!`, and select **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom3.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-dom3.msft.png":::
       <span data-ttu-id="5e3c1-188">Inspecting some text</span><span class="sxs-lookup"><span data-stu-id="5e3c1-188">Inspecting some text</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="5e3c1-189">DevTools opens up alongside your page.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-189">DevTools opens up alongside your page.</span></span>  `<div>A new element!?!</div>` <span data-ttu-id="5e3c1-190">is highlighted blue.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-190">is highlighted blue.</span></span>  <span data-ttu-id="5e3c1-191">Although this structure in DevTools looks like your HTML, it is actually the **DOM Tree**.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-191">Although this structure in DevTools looks like your HTML, it is actually the **DOM Tree**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom4.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-dom4.msft.png":::
       <span data-ttu-id="5e3c1-193">DevTools is open alongside the page</span><span class="sxs-lookup"><span data-stu-id="5e3c1-193">DevTools is open alongside the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="5e3c1-194">When your page loads, the browser takes your HTML to create the *initial* content of the page.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-194">When your page loads, the browser takes your HTML to create the *initial* content of the page.</span></span>  <span data-ttu-id="5e3c1-195">The DOM represents the *current* content of the page, which can change over time.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-195">The DOM represents the *current* content of the page, which can change over time.</span></span>  <span data-ttu-id="5e3c1-196">The mysterious `<div>A new element!?!</div>` content is added to your page because of the `<script src="new.js"></script>` tag at the bottom of your HTML.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-196">The mysterious `<div>A new element!?!</div>` content is added to your page because of the `<script src="new.js"></script>` tag at the bottom of your HTML.</span></span>  <span data-ttu-id="5e3c1-197">This tag causes some JavaScript code to run.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-197">This tag causes some JavaScript code to run.</span></span>  <span data-ttu-id="5e3c1-198">You'll learn more about JavaScript in a later tutorial, but for now think of it as a programming language that can change the content of your page.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-198">You'll learn more about JavaScript in a later tutorial, but for now think of it as a programming language that can change the content of your page.</span></span>  <span data-ttu-id="5e3c1-199">In this particular case, JavaScript code adds `<div>A new element!?!</div>` to your page.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-199">In this particular case, JavaScript code adds `<div>A new element!?!</div>` to your page.</span></span>  <span data-ttu-id="5e3c1-200">That is why this mystery text is visible on your live page, but not in your HTML.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-200">That is why this mystery text is visible on your live page, but not in your HTML.</span></span>  

### <span data-ttu-id="5e3c1-201">Edit the DOM</span><span class="sxs-lookup"><span data-stu-id="5e3c1-201">Edit the DOM</span></span>   

<span data-ttu-id="5e3c1-202">If you want to quickly experiment with content changes without ever leaving the live tab, try DevTools.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-202">If you want to quickly experiment with content changes without ever leaving the live tab, try DevTools.</span></span>  

1.  <span data-ttu-id="5e3c1-203">In DevTools, right-click `Your site!` and select **Edit as HTML**.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-203">In DevTools, right-click `Your site!` and select **Edit as HTML**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-edit1.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-edit1.msft.png":::
       <span data-ttu-id="5e3c1-205">Editing the node as HTML</span><span class="sxs-lookup"><span data-stu-id="5e3c1-205">Editing the node as HTML</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5e3c1-206">Replace `<p>Your site!</p>` with the code below.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-206">Replace `<p>Your site!</p>` with the code below.</span></span>  
    
    :::row:::
       :::column span="":::
          ```html
          ...
              ...
                  ...
                  <header>
                      <p><b>Welcome to my site!</b></p>
                      <button>Download my resume</button>
                  </header>
                  ...
              ...
          ...
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-edit2.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-edit2.msft.png":::
             <span data-ttu-id="5e3c1-208">Editing the node as HTML</span><span class="sxs-lookup"><span data-stu-id="5e3c1-208">Editing the node as HTML</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="5e3c1-209">Press `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to save your changes, or click outside of the box.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-209">Press `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to save your changes, or click outside of the box.</span></span>  <span data-ttu-id="5e3c1-210">Your changes automatically show up in the live view of your page.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-210">Your changes automatically show up in the live view of your page.</span></span>  <span data-ttu-id="5e3c1-211">The text `Your site!` has been replaced with the new content.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-211">The text `Your site!` has been replaced with the new content.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-edit3.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-edit3.msft.png":::
       <span data-ttu-id="5e3c1-213">The new content shows up immediately on the page</span><span class="sxs-lookup"><span data-stu-id="5e3c1-213">The new content shows up immediately on the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="5e3c1-214">This workflow is only good for experimenting with content changes.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-214">This workflow is only good for experimenting with content changes.</span></span>  <span data-ttu-id="5e3c1-215">If you reload the page or close the tab, your changes will be gone forever.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-215">If you reload the page or close the tab, your changes will be gone forever.</span></span>  <span data-ttu-id="5e3c1-216">If you're using this workflow and you want to save your changes, you need to manually copy those changes over to your HTML.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-216">If you're using this workflow and you want to save your changes, you need to manually copy those changes over to your HTML.</span></span>  <span data-ttu-id="5e3c1-217">The next couple of sections show you some more ways that you can change content from the DOM Tree.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-217">The next couple of sections show you some more ways that you can change content from the DOM Tree.</span></span>  

## <span data-ttu-id="5e3c1-218">Reorder nodes</span><span class="sxs-lookup"><span data-stu-id="5e3c1-218">Reorder nodes</span></span>   

<span data-ttu-id="5e3c1-219">You can also change the order of DOM nodes.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-219">You can also change the order of DOM nodes.</span></span>  <span data-ttu-id="5e3c1-220">For example, on your web page the navigation menu is near the bottom.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-220">For example, on your web page the navigation menu is near the bottom.</span></span>  <span data-ttu-id="5e3c1-221">To move it to the top:</span><span class="sxs-lookup"><span data-stu-id="5e3c1-221">To move it to the top:</span></span>  

1.  <span data-ttu-id="5e3c1-222">Find the `<nav>` node in the **DOM Tree** of DevTools.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-222">Find the `<nav>` node in the **DOM Tree** of DevTools.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-reorder1.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-reorder1.msft.png":::
       <span data-ttu-id="5e3c1-224">The nav node is highlighted blue in DevTools</span><span class="sxs-lookup"><span data-stu-id="5e3c1-224">The nav node is highlighted blue in DevTools</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5e3c1-225">Drag the `<nav>` node to the top, so that it's the first child below the `<body>` node.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-225">Drag the `<nav>` node to the top, so that it's the first child below the `<body>` node.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-reorder2.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-reorder2.msft.png":::
             <span data-ttu-id="5e3c1-227">Dragging the nav node to the top</span><span class="sxs-lookup"><span data-stu-id="5e3c1-227">Dragging the nav node to the top</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="5e3c1-228">The `<nav>` node is now displaying at the top of your page.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-228">The `<nav>` node is now displaying at the top of your page.</span></span>  
          
          :::image type="complex" source="../media/beginners-html-reorder3.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-reorder3.msft.png":::
             <span data-ttu-id="5e3c1-230">The nav node is at the top of the page</span><span class="sxs-lookup"><span data-stu-id="5e3c1-230">The nav node is at the top of the page</span></span>  
          :::image-end:::  
       :::column-end:::
   :::row-end:::  
    
### <span data-ttu-id="5e3c1-231">Delete a node</span><span class="sxs-lookup"><span data-stu-id="5e3c1-231">Delete a node</span></span>   

<span data-ttu-id="5e3c1-232">You can also remove nodes from the DOM Tree.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-232">You can also remove nodes from the DOM Tree.</span></span>  

1.  <span data-ttu-id="5e3c1-233">In the **DOM Tree**, click `<div>A new element!?!</div>`.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-233">In the **DOM Tree**, click `<div>A new element!?!</div>`.</span></span>  <span data-ttu-id="5e3c1-234">DevTools highlights the node blue.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-234">DevTools highlights the node blue.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-delete1.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-delete1.msft.png":::
       <span data-ttu-id="5e3c1-236">Selecting the node to be deleted</span><span class="sxs-lookup"><span data-stu-id="5e3c1-236">Selecting the node to be deleted</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5e3c1-237">Press the `Delete` key on your keyboard.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-237">Press the `Delete` key on your keyboard.</span></span>  <span data-ttu-id="5e3c1-238">The `<div>A new element!?!</div>` node is removed from your DOM Tree.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-238">The `<div>A new element!?!</div>` node is removed from your DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-delete2.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-delete2.msft.png":::
       <span data-ttu-id="5e3c1-240">The node has been deleted</span><span class="sxs-lookup"><span data-stu-id="5e3c1-240">The node has been deleted</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="5e3c1-241">Copy your changes</span><span class="sxs-lookup"><span data-stu-id="5e3c1-241">Copy your changes</span></span>   

<span data-ttu-id="5e3c1-242">You're almost done.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-242">You're almost done.</span></span>  <span data-ttu-id="5e3c1-243">You've made a few changes to your page in DevTools, but they're not yet saved to your source code.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-243">You've made a few changes to your page in DevTools, but they're not yet saved to your source code.</span></span>  

1.  <span data-ttu-id="5e3c1-244">Refresh your **live tab**.  The changes that you made in the DOM Tree disappear.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-244">Refresh your **live tab**.  The changes that you made in the DOM Tree disappear.</span></span>  <span data-ttu-id="5e3c1-245">In particular, the text `Your site!` returns to the top of the page, and the text `A new element!?!` returns to the bottom.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-245">In particular, the text `Your site!` returns to the top of the page, and the text `A new element!?!` returns to the bottom.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-copy1.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-copy1.msft.png":::
       <span data-ttu-id="5e3c1-247">The changes that you've made are gone</span><span class="sxs-lookup"><span data-stu-id="5e3c1-247">The changes that you've made are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="5e3c1-248">Copy the code below.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-248">Copy the code below.</span></span>  
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="utf-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, initial-scale=1">
        </head>
        <body>
            <header>
                <p>Welcome to my site!</p>
            </header>
            <nav>
                <ul>
                    <li><a href="/">Home</a></li>
                    <li><a href="/contact.html">Contact</a></li>
                </ul>
            </nav>
            <main>
                <h1>About Me</h1>
                <p>I am learning web development.  Recent accomplishments:</p>
                <ul>
                    <li>Learned how to set up my code in Glitch.</li>
                    <li>Added content to my HTML.</li>
                    <li>Learned how to use Microsoft Edge DevTools to experiment with content changes.</li>
                    <li>Learned the difference between HTML and the DOM.</li>
                </ul>
            </main>
        </body>
    </html>
    ```  
    
1.  <span data-ttu-id="5e3c1-249">Go back to the **editor tab** and replace the contents of your `index.html` file with the code that you just copied.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-249">Go back to the **editor tab** and replace the contents of your `index.html` file with the code that you just copied.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-copy2.msft.png" alt-text="The finished site" lightbox="../media/beginners-html-copy2.msft.png":::
       <span data-ttu-id="5e3c1-251">How your `index.html` file should look</span><span class="sxs-lookup"><span data-stu-id="5e3c1-251">How your `index.html` file should look</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="5e3c1-252">Next steps</span><span class="sxs-lookup"><span data-stu-id="5e3c1-252">Next steps</span></span>   

*   <span data-ttu-id="5e3c1-253">Complete the next tutorial in this series, [Get Started with CSS][DevToolsBeginnersCss], to learn how to style your page and experiment with style changes in Microsoft Edge DevTools.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-253">Complete the next tutorial in this series, [Get Started with CSS][DevToolsBeginnersCss], to learn how to style your page and experiment with style changes in Microsoft Edge DevTools.</span></span>  
*   <span data-ttu-id="5e3c1-254">Read [Introduction to the DOM][MDNIntroductionDom] to learn more about the DOM.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-254">Read [Introduction to the DOM][MDNIntroductionDom] to learn more about the DOM.</span></span>  
*   <span data-ttu-id="5e3c1-255">Check out a course like [Introduction to Web Development][CourseraIntroductionToWebDevelopment] to get more hands-on web development experience.</span><span class="sxs-lookup"><span data-stu-id="5e3c1-255">Check out a course like [Introduction to Web Development][CourseraIntroductionToWebDevelopment] to get more hands-on web development experience.</span></span>  

<!--- links --->  

[DevToolsBeginnersCss]: ./css.md "DevTools For Beginners: Get Started with CSS | Microsoft Docs"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge Insider"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Introduction to Web Development | Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "index.html - alluring-shock | Glitch"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "Getting started with HTML | MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "Introduction to the DOM | MDN"  

> [!NOTE]
> <span data-ttu-id="5e3c1-262">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="5e3c1-262">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="5e3c1-263">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/html) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span><span class="sxs-lookup"><span data-stu-id="5e3c1-263">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/html) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="5e3c1-265">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="5e3c1-265">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
