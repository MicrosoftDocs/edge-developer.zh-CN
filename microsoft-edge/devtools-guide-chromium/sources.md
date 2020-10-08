---
description: 在 Microsoft Edge DevTools 的 "源" 面板中查看和编辑文件、创建代码段、调试 JavaScript 和设置工作区。
title: 源窗格概览
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
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







# <span data-ttu-id="05fe6-104">"源" 面板概述</span><span class="sxs-lookup"><span data-stu-id="05fe6-104">Sources panel overview</span></span> 



<span data-ttu-id="05fe6-105">使用 Microsoft Edge DevTools " **源** " 面板执行 folowing 操作。</span><span class="sxs-lookup"><span data-stu-id="05fe6-105">Use the Microsoft Edge DevTools **Sources** panel to perform the folowing actions.</span></span>  

*   <span data-ttu-id="05fe6-106">[查看文件](#view-files)。</span><span class="sxs-lookup"><span data-stu-id="05fe6-106">[View files](#view-files).</span></span>  
*   <span data-ttu-id="05fe6-107">[编辑 CSS 和 JavaScript](#edit-css-and-javascript)。</span><span class="sxs-lookup"><span data-stu-id="05fe6-107">[Edit CSS and JavaScript](#edit-css-and-javascript).</span></span>  
*   <span data-ttu-id="05fe6-108">[创建和保存 JavaScript 的**代码段**](#create-save-and-run-snippets)，你可以在任何页上运行它们。</span><span class="sxs-lookup"><span data-stu-id="05fe6-108">[Create and save **Snippets** of JavaScript](#create-save-and-run-snippets), which you may run on any page.</span></span>  <span data-ttu-id="05fe6-109">**代码段** 类似于 bookmarklets。</span><span class="sxs-lookup"><span data-stu-id="05fe6-109">**Snippets** are similar to bookmarklets.</span></span>  
*   <span data-ttu-id="05fe6-110">[调试 JavaScript](#debug-javascript)。</span><span class="sxs-lookup"><span data-stu-id="05fe6-110">[Debug JavaScript](#debug-javascript).</span></span>  
*   <span data-ttu-id="05fe6-111">[设置工作区](#set-up-a-workspace)，以便在 DevTools 中所做的更改将保存到文件系统上的代码。</span><span class="sxs-lookup"><span data-stu-id="05fe6-111">[Set up a Workspace](#set-up-a-workspace), so that changes you make in DevTools get saved to the code on your file system.</span></span>  
    
## <span data-ttu-id="05fe6-112">查看文件</span><span class="sxs-lookup"><span data-stu-id="05fe6-112">View files</span></span> 

<span data-ttu-id="05fe6-113">使用 **页面** 窗格查看页面已加载的所有资源。</span><span class="sxs-lookup"><span data-stu-id="05fe6-113">Use the **Page** pane to view all of the resources that the page has loaded.</span></span>

:::image type="complex" source="./media/sources-page-pane.msft.png" alt-text="页面窗格" lightbox="./media/sources-page-pane.msft.png":::
   <span data-ttu-id="05fe6-115">**页面**窗格</span><span class="sxs-lookup"><span data-stu-id="05fe6-115">The **Page** pane</span></span>  
:::image-end:::  

<span data-ttu-id="05fe6-116">如何组织 **页面** 窗格：</span><span class="sxs-lookup"><span data-stu-id="05fe6-116">How the **Page** pane is organized:</span></span>  
*   <span data-ttu-id="05fe6-117">顶级（如 `top` 前面的图所示）表示 [HTML 框架][W3CHtml4Frames]。</span><span class="sxs-lookup"><span data-stu-id="05fe6-117">The top-level, such as `top` in the previous figure, represents an [HTML frame][W3CHtml4Frames].</span></span>  <span data-ttu-id="05fe6-118">`top`在您访问的每个页面上查找。</span><span class="sxs-lookup"><span data-stu-id="05fe6-118">Find `top` on every page that you visit.</span></span>  `top` <span data-ttu-id="05fe6-119">代表主文档框架。</span><span class="sxs-lookup"><span data-stu-id="05fe6-119">represents the main document frame.</span></span>  
*   <span data-ttu-id="05fe6-120">第二级别（如 `docs.microsoft.com` 前面的图所示）表示 [原点][HtmlstandardOrigin]。</span><span class="sxs-lookup"><span data-stu-id="05fe6-120">The second-level, such as `docs.microsoft.com` in the previous figure, represents an [origin][HtmlstandardOrigin].</span></span>  
*   <span data-ttu-id="05fe6-121">第三级、第四级等，表示从该来源加载的目录和资源。</span><span class="sxs-lookup"><span data-stu-id="05fe6-121">The third-level, fourth-level, and so on, represent directories and resources that were loaded from that origin.</span></span>  <span data-ttu-id="05fe6-122">例如，在上图中，指向资源的完整路径 `devtools-guide-chromium` 是</span><span class="sxs-lookup"><span data-stu-id="05fe6-122">For example, in the previous figure the full path to the resource `devtools-guide-chromium` is</span></span> `docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium`  
    
<span data-ttu-id="05fe6-123">单击 **页面** 窗格中的文件以查看 " **编辑器** " 窗格中的内容。</span><span class="sxs-lookup"><span data-stu-id="05fe6-123">Click a file in the **Page** pane to view the contents in the **Editor** pane.</span></span>  <span data-ttu-id="05fe6-124">您可以查看任何类型的文件。</span><span class="sxs-lookup"><span data-stu-id="05fe6-124">You may view any type of file.</span></span>  <span data-ttu-id="05fe6-125">对于图像，你将看到图像的预览。</span><span class="sxs-lookup"><span data-stu-id="05fe6-125">For images, you see a preview of the image.</span></span>  

:::image type="complex" source="./media/sources-editor-pane.msft.png" alt-text="页面窗格" lightbox="./media/sources-editor-pane.msft.png":::
   <span data-ttu-id="05fe6-127">`a4d10f71.index-docs.js`在 "**编辑器**" 窗格中查看内容</span><span class="sxs-lookup"><span data-stu-id="05fe6-127">View the contents of `a4d10f71.index-docs.js` in the **Editor** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="05fe6-128">编辑 CSS 和 JavaScript</span><span class="sxs-lookup"><span data-stu-id="05fe6-128">Edit CSS and JavaScript</span></span> 

<span data-ttu-id="05fe6-129">使用 " **编辑器** " 窗格编辑 CSS 和 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="05fe6-129">Use the **Editor** pane to edit CSS and JavaScript.</span></span>  <span data-ttu-id="05fe6-130">DevTools 更新页面以运行新代码。</span><span class="sxs-lookup"><span data-stu-id="05fe6-130">DevTools updates the page to run your new code.</span></span>  <span data-ttu-id="05fe6-131">例如，如果通过添加下面的样式规则来编辑 CSS 文件：</span><span class="sxs-lookup"><span data-stu-id="05fe6-131">For example, if you edit a CSS file by adding the style rule below:</span></span>

```css
.metadata.page-metadata {
    color: red;
}
```

<span data-ttu-id="05fe6-132">您应看到更改立即生效。</span><span class="sxs-lookup"><span data-stu-id="05fe6-132">You should see that change take effect immediately.</span></span>

:::image type="complex" source="./media/edit-css.msft.png" alt-text="页面窗格" lightbox="./media/edit-css.msft.png":::
   <span data-ttu-id="05fe6-134">在 " **编辑器** " 窗格中编辑 CSS 以将副标题的文本颜色更改为红色</span><span class="sxs-lookup"><span data-stu-id="05fe6-134">Edit CSS in the **Editor** pane to change the text color of the subtitle to red</span></span>  
:::image-end:::  

<span data-ttu-id="05fe6-135">CSS 更改会立即生效，无需保存。</span><span class="sxs-lookup"><span data-stu-id="05fe6-135">CSS changes take effect immediately, no save needed.</span></span>  <span data-ttu-id="05fe6-136">若要使 JavaScript 更改生效，请按 `Control` + `S` \ (Windows \ ) 或 `Command` + `S` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="05fe6-136">For JavaScript changes to take effect, press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\).</span></span>  <span data-ttu-id="05fe6-137">DevTools 不会重新运行脚本，因此只有你在函数中执行的 JavaScript 更改才会生效。</span><span class="sxs-lookup"><span data-stu-id="05fe6-137">DevTools does not re-run a script, so the only JavaScript changes that take effect are those that you make inside of functions.</span></span>  <span data-ttu-id="05fe6-138">例如，在下图中，注意如何 `console.log('A')` 运行，而不是运行 `console.log('B')` 。</span><span class="sxs-lookup"><span data-stu-id="05fe6-138">For example, in the following figure, notice how `console.log('A')` does not run, whereas `console.log('B')` does.</span></span>  <span data-ttu-id="05fe6-139">如果 DevTools 在进行更改后重新运行整个脚本，则文本 `A` 将被记录到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="05fe6-139">If DevTools re-runs the entire script after making the change, then the text `A` would have been logged to the **Console**.</span></span>  

:::image type="complex" source="./media/edit-js.msft.png" alt-text="页面窗格" lightbox="./media/edit-js.msft.png":::
   <span data-ttu-id="05fe6-141">在 " **编辑器** " 窗格中编辑 JavaScript</span><span class="sxs-lookup"><span data-stu-id="05fe6-141">Editing JavaScript in the **Editor** pane</span></span>  
:::image-end:::  

<span data-ttu-id="05fe6-142">DevTools 会在你重新加载页面时清除你的 CSS 和 JavaScript 更改。</span><span class="sxs-lookup"><span data-stu-id="05fe6-142">DevTools erases your CSS and JavaScript changes when you reload the page.</span></span>  <span data-ttu-id="05fe6-143">请参阅 [设置工作区](#set-up-a-workspace) 以了解如何将更改保存到文件系统。</span><span class="sxs-lookup"><span data-stu-id="05fe6-143">See [Set up a Workspace](#set-up-a-workspace) to learn how to save the changes to your file system.</span></span>  

## <span data-ttu-id="05fe6-144">创建、保存和运行代码段</span><span class="sxs-lookup"><span data-stu-id="05fe6-144">Create, save, and run Snippets</span></span> 

<span data-ttu-id="05fe6-145">代码段是可以在任何页上运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="05fe6-145">Snippets are scripts which you may run on any page.</span></span>  <span data-ttu-id="05fe6-146">假设你在 **控制台**中重复键入以下代码，以便将 jquery 库插入到页面中，以便你可以从该 **控制台**运行 jquery 命令：</span><span class="sxs-lookup"><span data-stu-id="05fe6-146">Imagine that you repeatedly type out the following code in the **Console**, in order to insert the jQuery library into a page, so that you may run jQuery commands from the **Console**:</span></span>  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

<span data-ttu-id="05fe6-147">相反，你可以将此代码保存在一个代码 **段** 中，并在每次需要时通过几次按钮单击运行它。</span><span class="sxs-lookup"><span data-stu-id="05fe6-147">Instead, you may save this code in a **Snippet** and run it with a couple of button clicks, any time you need it.</span></span>  <span data-ttu-id="05fe6-148">DevTools 将 **代码段** 保存到文件系统。</span><span class="sxs-lookup"><span data-stu-id="05fe6-148">DevTools saves the **Snippet** to your file system.</span></span>  

:::image type="complex" source="./media/snippet.msft.png" alt-text="页面窗格" lightbox="./media/snippet.msft.png":::
   <span data-ttu-id="05fe6-150">将 jQuery 库插入到页面中的**代码段**</span><span class="sxs-lookup"><span data-stu-id="05fe6-150">A **Snippet** that inserts the jQuery library into a page</span></span>  
:::image-end:::  

<span data-ttu-id="05fe6-151">要运行 **代码段**，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="05fe6-151">To run a **Snippet**:</span></span>

*   <span data-ttu-id="05fe6-152">使用 " **代码段** " 窗格打开文件，然后单击 " **运行** ![ " ("运行" 按钮 ][ImageRunIcon] \ ) 。</span><span class="sxs-lookup"><span data-stu-id="05fe6-152">Open the file using the **Snippets** pane, and click **Run** \(![The Run button][ImageRunIcon]\).</span></span>  
*   <span data-ttu-id="05fe6-153">打开 " **[命令" 菜单][DevtoolsGuideChromiumCommandMenuIndex]**，删除 " `>` 字符"，键入 `!` **代码段**的名称，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="05fe6-153">Open the **[Command Menu][DevtoolsGuideChromiumCommandMenuIndex]**, delete the `>` character, type `!`, type the name of your **Snippet**, then press `Enter`.</span></span>  
    
<span data-ttu-id="05fe6-154">请参阅 [从任意页面运行代码片段][DevtoolsGuideChromiumJavascriptSnippets] 以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="05fe6-154">See [Run Snippets Of Code From Any Page][DevtoolsGuideChromiumJavascriptSnippets] to learn more.</span></span>

## <span data-ttu-id="05fe6-155">调试 JavaScript</span><span class="sxs-lookup"><span data-stu-id="05fe6-155">Debug JavaScript</span></span> 

<span data-ttu-id="05fe6-156">请 `console.log()` 考虑改用 Microsoft Edge DevTools 调试工具，而不是使用来推断 JavaScript 出现错误的位置。</span><span class="sxs-lookup"><span data-stu-id="05fe6-156">Rather than using `console.log()` to infer where your JavaScript is going wrong, consider using the Microsoft Edge DevTools debugging tools, instead.</span></span>  <span data-ttu-id="05fe6-157">一般做法是设置一个断点，该断点是代码中有意停止的位置，然后逐句通过代码的运行时，一次一行。</span><span class="sxs-lookup"><span data-stu-id="05fe6-157">The general idea is to set a breakpoint, which is an intentional stopping place in your code, and then step through the runtime of your code, one line at a time.</span></span>  <span data-ttu-id="05fe6-158">逐句通过代码时，你可以查看和更改所有当前定义的属性和变量的值，并在 **控制台**中运行 JavaScript 等。</span><span class="sxs-lookup"><span data-stu-id="05fe6-158">As you step through the code, you may view and change the values of all currently-defined properties and variables, run JavaScript in the **Console**, and more.</span></span>

<span data-ttu-id="05fe6-159">有关在 DevTools 中调试的基础知识，请参阅 [开始使用调试 JavaScript][DevtoolsGuideChromiumJavascriptIndex] 。</span><span class="sxs-lookup"><span data-stu-id="05fe6-159">See [Get Started With Debugging JavaScript][DevtoolsGuideChromiumJavascriptIndex] to learn the basics of debugging in DevTools.</span></span>

:::image type="complex" source="./media/debugging.msft.png" alt-text="页面窗格" lightbox="./media/debugging.msft.png":::
   <span data-ttu-id="05fe6-161">调试 JavaScript</span><span class="sxs-lookup"><span data-stu-id="05fe6-161">Debug JavaScript</span></span>  
:::image-end:::  

## <span data-ttu-id="05fe6-162">设置工作区</span><span class="sxs-lookup"><span data-stu-id="05fe6-162">Set up a Workspace</span></span> 

<span data-ttu-id="05fe6-163">默认情况下，当您在 " **源** " 面板中编辑文件时，当您重新加载页面时，这些更改将会丢失。</span><span class="sxs-lookup"><span data-stu-id="05fe6-163">By default, when you edit a file in the **Sources** panel, those changes are lost when you reload the page.</span></span>  <span data-ttu-id="05fe6-164">**工作区** 使你能够将在 DevTools 中所做的更改保存到你的文件系统中。</span><span class="sxs-lookup"><span data-stu-id="05fe6-164">**Workspaces** enable you to save the changes that you make in DevTools to your file system.</span></span>  <span data-ttu-id="05fe6-165">实质上，DevTools 可以用作你的代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="05fe6-165">Essentially, DevTools is able to be used as your code editor.</span></span>

<span data-ttu-id="05fe6-166">请参阅 [编辑包含工作区的文件][DevtoolsGuideChromiumWorkspacesIndex] 以开始使用。</span><span class="sxs-lookup"><span data-stu-id="05fe6-166">See [Edit Files With Workspaces][DevtoolsGuideChromiumWorkspacesIndex] to get started.</span></span>

<!--  
 


-->  

<!-- image links -->  

[ImageRunIcon]: ./media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsGuideChromiumCommandMenuIndex]: ./command-menu/index.md "使用 Microsoft Edge 开发人员工具命令菜单运行命令"  
[DevtoolsGuideChromiumJavascriptIndex]: ./javascript/index.md "在 Microsoft Edge DevTools 中开始使用调试 JavaScript"  
[DevtoolsGuideChromiumJavascriptSnippets]: ./javascript/snippets.md "在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段"  
[DevtoolsGuideChromiumWorkspacesIndex]: ./workspaces/index.md "编辑具有工作区的文件"  

[HtmlstandardOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "原创-HTML 标准"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "框架 |W3C"  

> [!NOTE]
> <span data-ttu-id="05fe6-173">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="05fe6-173">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="05fe6-174">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/sources)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="05fe6-174">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/sources) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="05fe6-176">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="05fe6-176">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
