---
title: "\"源\" 面板概述"
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: c61d1bda030ce729b0b217b95a9143508d1f51f8
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601906"
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
   limitations under the License. -->






# <span data-ttu-id="839e0-103">"源" 面板概述</span><span class="sxs-lookup"><span data-stu-id="839e0-103">Sources Panel Overview</span></span> 



<span data-ttu-id="839e0-104">使用 Microsoft Edge DevTools "**源**" 面板执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="839e0-104">Use the Microsoft Edge DevTools **Sources** panel to:</span></span>

*   <span data-ttu-id="839e0-105">[查看文件](#view-files)。</span><span class="sxs-lookup"><span data-stu-id="839e0-105">[View files](#view-files).</span></span>  
*   <span data-ttu-id="839e0-106">[编辑 CSS 和 JavaScript](#edit-css-and-javascript)。</span><span class="sxs-lookup"><span data-stu-id="839e0-106">[Edit CSS and JavaScript](#edit-css-and-javascript).</span></span>  
*   <span data-ttu-id="839e0-107">[创建和保存 JavaScript 的**代码段**](#create-save-and-run-snippets)，你可以在任何页上运行它们。</span><span class="sxs-lookup"><span data-stu-id="839e0-107">[Create and save **Snippets** of JavaScript](#create-save-and-run-snippets), which you may run on any page.</span></span>  <span data-ttu-id="839e0-108">**代码段**类似于 bookmarklets。</span><span class="sxs-lookup"><span data-stu-id="839e0-108">**Snippets** are similar to bookmarklets.</span></span>  
*   <span data-ttu-id="839e0-109">[调试 JavaScript](#debug-javascript)。</span><span class="sxs-lookup"><span data-stu-id="839e0-109">[Debug JavaScript](#debug-javascript).</span></span>  
*   <span data-ttu-id="839e0-110">[设置工作区](#set-up-a-workspace)，以便在 DevTools 中所做的更改将保存到文件系统上的代码。</span><span class="sxs-lookup"><span data-stu-id="839e0-110">[Set up a Workspace](#set-up-a-workspace), so that changes you make in DevTools get saved to the code on your file system.</span></span>  

## <span data-ttu-id="839e0-111">查看文件</span><span class="sxs-lookup"><span data-stu-id="839e0-111">View files</span></span> 

<span data-ttu-id="839e0-112">使用**页面**窗格查看页面已加载的所有资源。</span><span class="sxs-lookup"><span data-stu-id="839e0-112">Use the **Page** pane to view all of the resources that the page has loaded.</span></span>

> ##### <span data-ttu-id="839e0-113">图 1</span><span class="sxs-lookup"><span data-stu-id="839e0-113">Figure 1</span></span>  
> <span data-ttu-id="839e0-114">**页面**窗格</span><span class="sxs-lookup"><span data-stu-id="839e0-114">The **Page** pane</span></span>  
> ![图1：页面窗格][ImageSourcesPagePane]  

<span data-ttu-id="839e0-116">如何组织**页面**窗格：</span><span class="sxs-lookup"><span data-stu-id="839e0-116">How the **Page** pane is organized:</span></span>  
*   <span data-ttu-id="839e0-117">顶级（如 `top` [**图 1**](#figure-1)所示）表示[HTML 框架][W3CHtml4Frames]。</span><span class="sxs-lookup"><span data-stu-id="839e0-117">The top-level, such as `top` in [**Figure 1**](#figure-1), represents an [HTML frame][W3CHtml4Frames].</span></span>  <span data-ttu-id="839e0-118">`top`在您访问的每个页面上查找。</span><span class="sxs-lookup"><span data-stu-id="839e0-118">Find `top` on every page that you visit.</span></span> `top` <span data-ttu-id="839e0-119">代表主文档框架。</span><span class="sxs-lookup"><span data-stu-id="839e0-119">represents the main document frame.</span></span>  
*   <span data-ttu-id="839e0-120">第二级（如 `docs.microsoft.com` [**图 1**](#figure-1)所示）表示[原点][HtmlstandardOrigin]。</span><span class="sxs-lookup"><span data-stu-id="839e0-120">The second-level, such as `docs.microsoft.com` in [**Figure 1**](#figure-1), represents an [origin][HtmlstandardOrigin].</span></span>  
*   <span data-ttu-id="839e0-121">第三级、第四级等，表示从该来源加载的目录和资源。</span><span class="sxs-lookup"><span data-stu-id="839e0-121">The third-level, fourth-level, and so on, represent directories and resources that were loaded from that origin.</span></span>  <span data-ttu-id="839e0-122">例如，在[**图 1**](#figure-1)中，资源的完整路径 `devtools-guide-chromium` 是</span><span class="sxs-lookup"><span data-stu-id="839e0-122">For example, in [**Figure 1**](#figure-1) the full path to the resource `devtools-guide-chromium` is</span></span> `docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium`  

<span data-ttu-id="839e0-123">单击**页面**窗格中的文件以查看 "**编辑器**" 窗格中的内容。</span><span class="sxs-lookup"><span data-stu-id="839e0-123">Click a file in the **Page** pane to view the contents in the **Editor** pane.</span></span>  <span data-ttu-id="839e0-124">您可以查看任何类型的文件。</span><span class="sxs-lookup"><span data-stu-id="839e0-124">You may view any type of file.</span></span> <span data-ttu-id="839e0-125">对于图像，你将看到图像的预览。</span><span class="sxs-lookup"><span data-stu-id="839e0-125">For images, you see a preview of the image.</span></span>  

> ##### <span data-ttu-id="839e0-126">图 2</span><span class="sxs-lookup"><span data-stu-id="839e0-126">Figure 2</span></span>  
> <span data-ttu-id="839e0-127">`a4d10f71.index-docs.js`在 "**编辑器**" 窗格中查看内容</span><span class="sxs-lookup"><span data-stu-id="839e0-127">Viewing the contents of `a4d10f71.index-docs.js` in the **Editor** pane</span></span>  
> ![图 2.][ImageSourcesEditorPane]  

## <span data-ttu-id="839e0-130">编辑 CSS 和 JavaScript</span><span class="sxs-lookup"><span data-stu-id="839e0-130">Edit CSS and JavaScript</span></span> 

<span data-ttu-id="839e0-131">使用 "**编辑器**" 窗格编辑 CSS 和 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="839e0-131">Use the **Editor** pane to edit CSS and JavaScript.</span></span>  <span data-ttu-id="839e0-132">DevTools 更新页面以运行新代码。</span><span class="sxs-lookup"><span data-stu-id="839e0-132">DevTools updates the page to run your new code.</span></span> <span data-ttu-id="839e0-133">例如，如果通过添加下面的样式规则来编辑 CSS 文件：</span><span class="sxs-lookup"><span data-stu-id="839e0-133">For example, if you edit a CSS file by adding the style rule below:</span></span>

```css
.metadata.page-metadata {
    color: red;
}
```

<span data-ttu-id="839e0-134">您应看到更改立即生效。</span><span class="sxs-lookup"><span data-stu-id="839e0-134">You should see that change take effect immediately.</span></span>

> ##### <span data-ttu-id="839e0-135">图 3</span><span class="sxs-lookup"><span data-stu-id="839e0-135">Figure 3</span></span>  
> <span data-ttu-id="839e0-136">在 "**编辑器**" 窗格中编辑 CSS 以将副标题的文本颜色更改为红色</span><span class="sxs-lookup"><span data-stu-id="839e0-136">Editing CSS in the **Editor** pane to change the text color of the subtitle to red</span></span>  
> ![图 3.][ImageEditCSS]  

<span data-ttu-id="839e0-139">CSS 更改会立即生效，无需保存。</span><span class="sxs-lookup"><span data-stu-id="839e0-139">CSS changes take effect immediately, no save needed.</span></span> <span data-ttu-id="839e0-140">若要使 JavaScript 更改生效，请按 `Control` + `S` \ （Windows \）或 `Command` + `S` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="839e0-140">For JavaScript changes to take effect, press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\).</span></span> <span data-ttu-id="839e0-141">DevTools 不会重新运行脚本，因此只有你在函数中执行的 JavaScript 更改才会生效。</span><span class="sxs-lookup"><span data-stu-id="839e0-141">DevTools does not re-run a script, so the only JavaScript changes that take effect are those that you make inside of functions.</span></span>  <span data-ttu-id="839e0-142">例如，在[**图 4**](#figure-4)中，注意如何 `console.log('A')` 运行，而不是运行 `console.log('B')` 。</span><span class="sxs-lookup"><span data-stu-id="839e0-142">For example, in [**Figure 4**](#figure-4) note how `console.log('A')` does not run, whereas `console.log('B')` does.</span></span> <span data-ttu-id="839e0-143">如果 DevTools 在进行更改后重新运行整个脚本，则文本 `A` 将被记录到**控制台**。</span><span class="sxs-lookup"><span data-stu-id="839e0-143">If DevTools re-ran the entire script after making the change, then the text `A` would have been logged to the **Console**.</span></span>  

> ##### <span data-ttu-id="839e0-144">图 4</span><span class="sxs-lookup"><span data-stu-id="839e0-144">Figure 4</span></span>  
> <span data-ttu-id="839e0-145">在 "**编辑器**" 窗格中编辑 JavaScript</span><span class="sxs-lookup"><span data-stu-id="839e0-145">Editing JavaScript in the **Editor** pane</span></span>  
> ![图 4.][ImageEditJS]  

<span data-ttu-id="839e0-148">DevTools 会在你重新加载页面时清除你的 CSS 和 JavaScript 更改。</span><span class="sxs-lookup"><span data-stu-id="839e0-148">DevTools erases your CSS and JavaScript changes when you reload the page.</span></span> <span data-ttu-id="839e0-149">请参阅[设置工作区](#set-up-a-workspace)以了解如何将更改保存到文件系统。</span><span class="sxs-lookup"><span data-stu-id="839e0-149">See [Set up a Workspace](#set-up-a-workspace) to learn how to save the changes to your file system.</span></span>  

## <span data-ttu-id="839e0-150">创建、保存和运行代码段</span><span class="sxs-lookup"><span data-stu-id="839e0-150">Create, save, and run Snippets</span></span> 

<span data-ttu-id="839e0-151">代码段是可以在任何页上运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="839e0-151">Snippets are scripts which you may run on any page.</span></span> <span data-ttu-id="839e0-152">假设你在**控制台**中重复键入以下代码，以便将 jquery 库插入到页面中，以便你可以从该**控制台**运行 jquery 命令：</span><span class="sxs-lookup"><span data-stu-id="839e0-152">Imagine that you repeatedly type out the following code in the **Console**, in order to insert the jQuery library into a page, so that you may run jQuery commands from the **Console**:</span></span>  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

<span data-ttu-id="839e0-153">相反，你可以将此代码保存在一个代码**段**中，并在每次需要时通过几次按钮单击运行它。</span><span class="sxs-lookup"><span data-stu-id="839e0-153">Instead, you may save this code in a **Snippet** and run it with a couple of button clicks, any time you need it.</span></span>  <span data-ttu-id="839e0-154">DevTools 将**代码段**保存到文件系统。</span><span class="sxs-lookup"><span data-stu-id="839e0-154">DevTools saves the **Snippet** to your file system.</span></span>  

> ##### <span data-ttu-id="839e0-155">图 5</span><span class="sxs-lookup"><span data-stu-id="839e0-155">Figure 5</span></span>  
> <span data-ttu-id="839e0-156">将 jQuery 库插入到页面中的**代码段**</span><span class="sxs-lookup"><span data-stu-id="839e0-156">A **Snippet** that inserts the jQuery library into a page</span></span>  
> ![图 5.][ImageSnippet]  

<span data-ttu-id="839e0-159">要运行**代码段**，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="839e0-159">To run a **Snippet**:</span></span>

*   <span data-ttu-id="839e0-160">通过 "**代码段**" 窗格打开文件，然后单击 "**运行** ![ 运行" 按钮 ][ImageRunIcon] 。</span><span class="sxs-lookup"><span data-stu-id="839e0-160">Open the file via the **Snippets** pane, and click **Run** ![The Run button][ImageRunIcon].</span></span>  
*   <span data-ttu-id="839e0-161">打开 "**[命令" 菜单][DevtoolsGuideChromiumCommandMenuIndex]**，删除 " `>` 字符"，键入 `!` **代码段**的名称，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="839e0-161">Open the **[Command Menu][DevtoolsGuideChromiumCommandMenuIndex]**, delete the `>` character, type `!`, type the name of your **Snippet**, then press `Enter`.</span></span>  

<span data-ttu-id="839e0-162">请参阅[从任意页面运行代码片段][DevtoolsGuideChromiumJavascriptSnippets]以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="839e0-162">See [Run Snippets Of Code From Any Page][DevtoolsGuideChromiumJavascriptSnippets] to learn more.</span></span>


## <span data-ttu-id="839e0-163">调试 JavaScript</span><span class="sxs-lookup"><span data-stu-id="839e0-163">Debug JavaScript</span></span> 

<span data-ttu-id="839e0-164">请 `console.log()` 考虑改用 Microsoft Edge DevTools 调试工具，而不是使用来推断 JavaScript 出现错误的位置。</span><span class="sxs-lookup"><span data-stu-id="839e0-164">Rather than using `console.log()` to infer where your JavaScript is going wrong, consider using the Microsoft Edge DevTools debugging tools, instead.</span></span> <span data-ttu-id="839e0-165">一般做法是设置一个断点，该断点是代码中有意停止的位置，然后逐句通过代码的运行时，一次一行。</span><span class="sxs-lookup"><span data-stu-id="839e0-165">The general idea is to set a breakpoint, which is an intentional stopping place in your code, and then step through the runtime of your code, one line at a time.</span></span> <span data-ttu-id="839e0-166">逐句通过代码时，你可以查看和更改所有当前定义的属性和变量的值，并在**控制台**中运行 JavaScript 等。</span><span class="sxs-lookup"><span data-stu-id="839e0-166">As you step through the code, you may view and change the values of all currently-defined properties and variables, run JavaScript in the **Console**, and more.</span></span>

<span data-ttu-id="839e0-167">有关在 DevTools 中调试的基础知识，请参阅[开始使用调试 JavaScript][DevtoolsGuideChromiumJavascriptIndex] 。</span><span class="sxs-lookup"><span data-stu-id="839e0-167">See [Get Started With Debugging JavaScript][DevtoolsGuideChromiumJavascriptIndex] to learn the basics of debugging in DevTools.</span></span>

> ##### <span data-ttu-id="839e0-168">图 6</span><span class="sxs-lookup"><span data-stu-id="839e0-168">Figure 6</span></span>  
> <span data-ttu-id="839e0-169">调试 JavaScript</span><span class="sxs-lookup"><span data-stu-id="839e0-169">Debugging JavaScript</span></span>  
> ![图 6.][ImageDebugging]  

## <span data-ttu-id="839e0-172">设置工作区</span><span class="sxs-lookup"><span data-stu-id="839e0-172">Set up a Workspace</span></span> 

<span data-ttu-id="839e0-173">默认情况下，当您在 "**源**" 面板中编辑文件时，当您重新加载页面时，这些更改将会丢失。</span><span class="sxs-lookup"><span data-stu-id="839e0-173">By default, when you edit a file in the **Sources** panel, those changes are lost when you reload the page.</span></span>  <span data-ttu-id="839e0-174">**工作区**使你能够将在 DevTools 中所做的更改保存到你的文件系统中。</span><span class="sxs-lookup"><span data-stu-id="839e0-174">**Workspaces** enable you to save the changes that you make in DevTools to your file system.</span></span>  <span data-ttu-id="839e0-175">实质上，这使你可以将 DevTools 用作代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="839e0-175">Essentially, this lets you use DevTools as your code editor.</span></span>

<span data-ttu-id="839e0-176">请参阅[编辑包含工作区的文件][DevtoolsGuideChromiumWorkspacesIndex]以开始使用。</span><span class="sxs-lookup"><span data-stu-id="839e0-176">See [Edit Files With Workspaces][DevtoolsGuideChromiumWorkspacesIndex] to get started.</span></span>

 



<!-- image links -->  

[ImageRunIcon]: /microsoft-edge/devtools-guide-chromium/media/run-snippet-icon.msft.png  

[ImageSourcesPagePane]: /microsoft-edge/devtools-guide-chromium/media/sources-page-pane.msft.png "图1：页面窗格"  
[ImageSourcesEditorPane]: /microsoft-edge/devtools-guide-chromium/media/sources-editor-pane.msft.png "图2：在 "编辑器" 窗格中查看 a4d10f71 的内容"  
[ImageEditCSS]: /microsoft-edge/devtools-guide-chromium/media/edit-css.msft.png "图3：在 "编辑器" 窗格中编辑 CSS 以将副标题的文本颜色更改为红色"  
[ImageEditJS]: /microsoft-edge/devtools-guide-chromium/media/edit-js.msft.png "图4：在 "编辑器" 窗格中编辑 JavaScript"  
[ImageSnippet]: /microsoft-edge/devtools-guide-chromium/media/snippet.msft.png "图5：将 jQuery 库插入到页面中的代码段"  
[ImageDebugging]: /microsoft-edge/devtools-guide-chromium/media/debugging.msft.png "图6：调试 JavaScript"  

<!-- links -->  

[DevtoolsGuideChromiumCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令"  
[DevtoolsGuideChromiumJavascriptIndex]: /microsoft-edge/devtools-guide-chromium/javascript/index "在 Microsoft Edge DevTools 中开始使用调试 JavaScript"  
[DevtoolsGuideChromiumJavascriptSnippets]: /microsoft-edge/devtools-guide-chromium/javascript/snippets "在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段"  
[DevtoolsGuideChromiumWorkspacesIndex]: /microsoft-edge/devtools-guide-chromium/workspaces/index "编辑具有工作区的文件"  

[HtmlstandardOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "原创-HTML 标准"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "框架 |W3C"  

> [!NOTE]
> <span data-ttu-id="839e0-189">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="839e0-189">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="839e0-190">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/sources)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="839e0-190">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/sources) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="839e0-192">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="839e0-192">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
