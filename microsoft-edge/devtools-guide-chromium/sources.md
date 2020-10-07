---
description: View and edit files, create Snippets, debug JavaScript, and set up Workspaces in the Sources panel of Microsoft Edge DevTools.
title: Sources Panel Overview
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 029693ba27665a556446f4349c1517c53ff39b02
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993539"
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







# <span data-ttu-id="02626-104">Sources panel overview</span><span class="sxs-lookup"><span data-stu-id="02626-104">Sources panel overview</span></span> 



<span data-ttu-id="02626-105">Use the Microsoft Edge DevTools **Sources** panel to perform the folowing actions.</span><span class="sxs-lookup"><span data-stu-id="02626-105">Use the Microsoft Edge DevTools **Sources** panel to perform the folowing actions.</span></span>  

*   <span data-ttu-id="02626-106">[View files](#view-files).</span><span class="sxs-lookup"><span data-stu-id="02626-106">[View files](#view-files).</span></span>  
*   <span data-ttu-id="02626-107">[Edit CSS and JavaScript](#edit-css-and-javascript).</span><span class="sxs-lookup"><span data-stu-id="02626-107">[Edit CSS and JavaScript](#edit-css-and-javascript).</span></span>  
*   <span data-ttu-id="02626-108">[Create and save **Snippets** of JavaScript](#create-save-and-run-snippets), which you may run on any page.</span><span class="sxs-lookup"><span data-stu-id="02626-108">[Create and save **Snippets** of JavaScript](#create-save-and-run-snippets), which you may run on any page.</span></span>  <span data-ttu-id="02626-109">**Snippets** are similar to bookmarklets.</span><span class="sxs-lookup"><span data-stu-id="02626-109">**Snippets** are similar to bookmarklets.</span></span>  
*   <span data-ttu-id="02626-110">[Debug JavaScript](#debug-javascript).</span><span class="sxs-lookup"><span data-stu-id="02626-110">[Debug JavaScript](#debug-javascript).</span></span>  
*   <span data-ttu-id="02626-111">[Set up a Workspace](#set-up-a-workspace), so that changes you make in DevTools get saved to the code on your file system.</span><span class="sxs-lookup"><span data-stu-id="02626-111">[Set up a Workspace](#set-up-a-workspace), so that changes you make in DevTools get saved to the code on your file system.</span></span>  
    
## <span data-ttu-id="02626-112">View files</span><span class="sxs-lookup"><span data-stu-id="02626-112">View files</span></span> 

<span data-ttu-id="02626-113">Use the **Page** pane to view all of the resources that the page has loaded.</span><span class="sxs-lookup"><span data-stu-id="02626-113">Use the **Page** pane to view all of the resources that the page has loaded.</span></span>

:::image type="complex" source="./media/sources-page-pane.msft.png" alt-text="The Page pane" lightbox="./media/sources-page-pane.msft.png":::
   <span data-ttu-id="02626-115">The **Page** pane</span><span class="sxs-lookup"><span data-stu-id="02626-115">The **Page** pane</span></span>  
:::image-end:::  

<span data-ttu-id="02626-116">How the **Page** pane is organized:</span><span class="sxs-lookup"><span data-stu-id="02626-116">How the **Page** pane is organized:</span></span>  
*   <span data-ttu-id="02626-117">The top-level, such as `top` in the previous figure, represents an [HTML frame][W3CHtml4Frames].</span><span class="sxs-lookup"><span data-stu-id="02626-117">The top-level, such as `top` in the previous figure, represents an [HTML frame][W3CHtml4Frames].</span></span>  <span data-ttu-id="02626-118">Find `top` on every page that you visit.</span><span class="sxs-lookup"><span data-stu-id="02626-118">Find `top` on every page that you visit.</span></span>  `top` <span data-ttu-id="02626-119">represents the main document frame.</span><span class="sxs-lookup"><span data-stu-id="02626-119">represents the main document frame.</span></span>  
*   <span data-ttu-id="02626-120">The second-level, such as `docs.microsoft.com` in the previous figure, represents an [origin][HtmlstandardOrigin].</span><span class="sxs-lookup"><span data-stu-id="02626-120">The second-level, such as `docs.microsoft.com` in the previous figure, represents an [origin][HtmlstandardOrigin].</span></span>  
*   <span data-ttu-id="02626-121">The third-level, fourth-level, and so on, represent directories and resources that were loaded from that origin.</span><span class="sxs-lookup"><span data-stu-id="02626-121">The third-level, fourth-level, and so on, represent directories and resources that were loaded from that origin.</span></span>  <span data-ttu-id="02626-122">For example, in the previous figure the full path to the resource `devtools-guide-chromium` is</span><span class="sxs-lookup"><span data-stu-id="02626-122">For example, in the previous figure the full path to the resource `devtools-guide-chromium` is</span></span> `docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium`  
    
<span data-ttu-id="02626-123">Click a file in the **Page** pane to view the contents in the **Editor** pane.</span><span class="sxs-lookup"><span data-stu-id="02626-123">Click a file in the **Page** pane to view the contents in the **Editor** pane.</span></span>  <span data-ttu-id="02626-124">You may view any type of file.</span><span class="sxs-lookup"><span data-stu-id="02626-124">You may view any type of file.</span></span>  <span data-ttu-id="02626-125">For images, you see a preview of the image.</span><span class="sxs-lookup"><span data-stu-id="02626-125">For images, you see a preview of the image.</span></span>  

:::image type="complex" source="./media/sources-editor-pane.msft.png" alt-text="The Page pane" lightbox="./media/sources-editor-pane.msft.png":::
   <span data-ttu-id="02626-127">View the contents of `a4d10f71.index-docs.js` in the **Editor** pane</span><span class="sxs-lookup"><span data-stu-id="02626-127">View the contents of `a4d10f71.index-docs.js` in the **Editor** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="02626-128">Edit CSS and JavaScript</span><span class="sxs-lookup"><span data-stu-id="02626-128">Edit CSS and JavaScript</span></span> 

<span data-ttu-id="02626-129">Use the **Editor** pane to edit CSS and JavaScript.</span><span class="sxs-lookup"><span data-stu-id="02626-129">Use the **Editor** pane to edit CSS and JavaScript.</span></span>  <span data-ttu-id="02626-130">DevTools updates the page to run your new code.</span><span class="sxs-lookup"><span data-stu-id="02626-130">DevTools updates the page to run your new code.</span></span>  <span data-ttu-id="02626-131">For example, if you edit a CSS file by adding the style rule below:</span><span class="sxs-lookup"><span data-stu-id="02626-131">For example, if you edit a CSS file by adding the style rule below:</span></span>

```css
.metadata.page-metadata {
    color: red;
}
```

<span data-ttu-id="02626-132">You should see that change take effect immediately.</span><span class="sxs-lookup"><span data-stu-id="02626-132">You should see that change take effect immediately.</span></span>

:::image type="complex" source="./media/edit-css.msft.png" alt-text="The Page pane" lightbox="./media/edit-css.msft.png":::
   <span data-ttu-id="02626-134">Edit CSS in the **Editor** pane to change the text color of the subtitle to red</span><span class="sxs-lookup"><span data-stu-id="02626-134">Edit CSS in the **Editor** pane to change the text color of the subtitle to red</span></span>  
:::image-end:::  

<span data-ttu-id="02626-135">CSS changes take effect immediately, no save needed.</span><span class="sxs-lookup"><span data-stu-id="02626-135">CSS changes take effect immediately, no save needed.</span></span>  <span data-ttu-id="02626-136">For JavaScript changes to take effect, press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\).</span><span class="sxs-lookup"><span data-stu-id="02626-136">For JavaScript changes to take effect, press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\).</span></span>  <span data-ttu-id="02626-137">DevTools does not re-run a script, so the only JavaScript changes that take effect are those that you make inside of functions.</span><span class="sxs-lookup"><span data-stu-id="02626-137">DevTools does not re-run a script, so the only JavaScript changes that take effect are those that you make inside of functions.</span></span>  <span data-ttu-id="02626-138">For example, in the following figure, notice how `console.log('A')` does not run, whereas `console.log('B')` does.</span><span class="sxs-lookup"><span data-stu-id="02626-138">For example, in the following figure, notice how `console.log('A')` does not run, whereas `console.log('B')` does.</span></span>  <span data-ttu-id="02626-139">If DevTools re-runs the entire script after making the change, then the text `A` would have been logged to the **Console**.</span><span class="sxs-lookup"><span data-stu-id="02626-139">If DevTools re-runs the entire script after making the change, then the text `A` would have been logged to the **Console**.</span></span>  

:::image type="complex" source="./media/edit-js.msft.png" alt-text="The Page pane" lightbox="./media/edit-js.msft.png":::
   <span data-ttu-id="02626-141">Editing JavaScript in the **Editor** pane</span><span class="sxs-lookup"><span data-stu-id="02626-141">Editing JavaScript in the **Editor** pane</span></span>  
:::image-end:::  

<span data-ttu-id="02626-142">DevTools erases your CSS and JavaScript changes when you reload the page.</span><span class="sxs-lookup"><span data-stu-id="02626-142">DevTools erases your CSS and JavaScript changes when you reload the page.</span></span>  <span data-ttu-id="02626-143">See [Set up a Workspace](#set-up-a-workspace) to learn how to save the changes to your file system.</span><span class="sxs-lookup"><span data-stu-id="02626-143">See [Set up a Workspace](#set-up-a-workspace) to learn how to save the changes to your file system.</span></span>  

## <span data-ttu-id="02626-144">Create, save, and run Snippets</span><span class="sxs-lookup"><span data-stu-id="02626-144">Create, save, and run Snippets</span></span> 

<span data-ttu-id="02626-145">Snippets are scripts which you may run on any page.</span><span class="sxs-lookup"><span data-stu-id="02626-145">Snippets are scripts which you may run on any page.</span></span>  <span data-ttu-id="02626-146">Imagine that you repeatedly type out the following code in the **Console**, in order to insert the jQuery library into a page, so that you may run jQuery commands from the **Console**:</span><span class="sxs-lookup"><span data-stu-id="02626-146">Imagine that you repeatedly type out the following code in the **Console**, in order to insert the jQuery library into a page, so that you may run jQuery commands from the **Console**:</span></span>  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

<span data-ttu-id="02626-147">Instead, you may save this code in a **Snippet** and run it with a couple of button clicks, any time you need it.</span><span class="sxs-lookup"><span data-stu-id="02626-147">Instead, you may save this code in a **Snippet** and run it with a couple of button clicks, any time you need it.</span></span>  <span data-ttu-id="02626-148">DevTools saves the **Snippet** to your file system.</span><span class="sxs-lookup"><span data-stu-id="02626-148">DevTools saves the **Snippet** to your file system.</span></span>  

:::image type="complex" source="./media/snippet.msft.png" alt-text="The Page pane" lightbox="./media/snippet.msft.png":::
   <span data-ttu-id="02626-150">A **Snippet** that inserts the jQuery library into a page</span><span class="sxs-lookup"><span data-stu-id="02626-150">A **Snippet** that inserts the jQuery library into a page</span></span>  
:::image-end:::  

<span data-ttu-id="02626-151">To run a **Snippet**:</span><span class="sxs-lookup"><span data-stu-id="02626-151">To run a **Snippet**:</span></span>

*   <span data-ttu-id="02626-152">Open the file using the **Snippets** pane, and click **Run** \(![The Run button][ImageRunIcon]\).</span><span class="sxs-lookup"><span data-stu-id="02626-152">Open the file using the **Snippets** pane, and click **Run** \(![The Run button][ImageRunIcon]\).</span></span>  
*   <span data-ttu-id="02626-153">Open the **[Command Menu][DevtoolsGuideChromiumCommandMenuIndex]**, delete the `>` character, type `!`, type the name of your **Snippet**, then press `Enter`.</span><span class="sxs-lookup"><span data-stu-id="02626-153">Open the **[Command Menu][DevtoolsGuideChromiumCommandMenuIndex]**, delete the `>` character, type `!`, type the name of your **Snippet**, then press `Enter`.</span></span>  
    
<span data-ttu-id="02626-154">See [Run Snippets Of Code From Any Page][DevtoolsGuideChromiumJavascriptSnippets] to learn more.</span><span class="sxs-lookup"><span data-stu-id="02626-154">See [Run Snippets Of Code From Any Page][DevtoolsGuideChromiumJavascriptSnippets] to learn more.</span></span>

## <span data-ttu-id="02626-155">Debug JavaScript</span><span class="sxs-lookup"><span data-stu-id="02626-155">Debug JavaScript</span></span> 

<span data-ttu-id="02626-156">Rather than using `console.log()` to infer where your JavaScript is going wrong, consider using the Microsoft Edge DevTools debugging tools, instead.</span><span class="sxs-lookup"><span data-stu-id="02626-156">Rather than using `console.log()` to infer where your JavaScript is going wrong, consider using the Microsoft Edge DevTools debugging tools, instead.</span></span>  <span data-ttu-id="02626-157">The general idea is to set a breakpoint, which is an intentional stopping place in your code, and then step through the runtime of your code, one line at a time.</span><span class="sxs-lookup"><span data-stu-id="02626-157">The general idea is to set a breakpoint, which is an intentional stopping place in your code, and then step through the runtime of your code, one line at a time.</span></span>  <span data-ttu-id="02626-158">As you step through the code, you may view and change the values of all currently-defined properties and variables, run JavaScript in the **Console**, and more.</span><span class="sxs-lookup"><span data-stu-id="02626-158">As you step through the code, you may view and change the values of all currently-defined properties and variables, run JavaScript in the **Console**, and more.</span></span>

<span data-ttu-id="02626-159">See [Get Started With Debugging JavaScript][DevtoolsGuideChromiumJavascriptIndex] to learn the basics of debugging in DevTools.</span><span class="sxs-lookup"><span data-stu-id="02626-159">See [Get Started With Debugging JavaScript][DevtoolsGuideChromiumJavascriptIndex] to learn the basics of debugging in DevTools.</span></span>

:::image type="complex" source="./media/debugging.msft.png" alt-text="The Page pane" lightbox="./media/debugging.msft.png":::
   <span data-ttu-id="02626-161">Debug JavaScript</span><span class="sxs-lookup"><span data-stu-id="02626-161">Debug JavaScript</span></span>  
:::image-end:::  

## <span data-ttu-id="02626-162">Set up a Workspace</span><span class="sxs-lookup"><span data-stu-id="02626-162">Set up a Workspace</span></span> 

<span data-ttu-id="02626-163">By default, when you edit a file in the **Sources** panel, those changes are lost when you reload the page.</span><span class="sxs-lookup"><span data-stu-id="02626-163">By default, when you edit a file in the **Sources** panel, those changes are lost when you reload the page.</span></span>  <span data-ttu-id="02626-164">**Workspaces** enable you to save the changes that you make in DevTools to your file system.</span><span class="sxs-lookup"><span data-stu-id="02626-164">**Workspaces** enable you to save the changes that you make in DevTools to your file system.</span></span>  <span data-ttu-id="02626-165">Essentially, DevTools is able to be used as your code editor.</span><span class="sxs-lookup"><span data-stu-id="02626-165">Essentially, DevTools is able to be used as your code editor.</span></span>

<span data-ttu-id="02626-166">See [Edit Files With Workspaces][DevtoolsGuideChromiumWorkspacesIndex] to get started.</span><span class="sxs-lookup"><span data-stu-id="02626-166">See [Edit Files With Workspaces][DevtoolsGuideChromiumWorkspacesIndex] to get started.</span></span>

<!--  
 


-->  

<!-- image links -->  

[ImageRunIcon]: ./media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsGuideChromiumCommandMenuIndex]: ./command-menu/index.md "Run Commands With The Microsoft Edge DevTools Command Menu"  
[DevtoolsGuideChromiumJavascriptIndex]: ./javascript/index.md "Get Started with Debugging JavaScript in Microsoft Edge DevTools"  
[DevtoolsGuideChromiumJavascriptSnippets]: ./javascript/snippets.md "Run Snippets Of JavaScript On Any Page With Microsoft Edge DevTools"  
[DevtoolsGuideChromiumWorkspacesIndex]: ./workspaces/index.md "Edit Files With Workspaces"  

[HtmlstandardOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "Origin - HTML Standard"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "Frames | W3C"  

> [!NOTE]
> <span data-ttu-id="02626-173">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="02626-173">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="02626-174">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/sources)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="02626-174">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/sources) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="02626-176">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="02626-176">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
