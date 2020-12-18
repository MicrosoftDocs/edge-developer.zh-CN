---
description: 在 Microsoft Edge DevTools 的"源"面板中显示和编辑文件、创建代码段、调试 JavaScript 和设置工作区。
title: 源窗格概览
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: b90f927670146c004a335256ace28203219442eb
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232168"
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

# <span data-ttu-id="96594-104">源窗格概览</span><span class="sxs-lookup"><span data-stu-id="96594-104">Sources panel overview</span></span>  

<span data-ttu-id="96594-105">使用 Microsoft Edge DevTools **源** 面板执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="96594-105">Use the Microsoft Edge DevTools **Sources** panel to perform the following actions.</span></span>  

*   <span data-ttu-id="96594-106">[显示文件](#display-files)。</span><span class="sxs-lookup"><span data-stu-id="96594-106">[Display files](#display-files).</span></span>  
*   <span data-ttu-id="96594-107">[编辑 CSS 和 JavaScript](#edit-css-and-javascript)。</span><span class="sxs-lookup"><span data-stu-id="96594-107">[Edit CSS and JavaScript](#edit-css-and-javascript).</span></span>  
*   <span data-ttu-id="96594-108">[创建和保存**JavaScript**](#create-save-and-run-snippets)的代码段，您可以在任何网页上运行这些代码段。</span><span class="sxs-lookup"><span data-stu-id="96594-108">[Create and save **Snippets** of JavaScript](#create-save-and-run-snippets), which you may run on any webpage.</span></span>  <span data-ttu-id="96594-109">**代码段** 类似于 bookmarklet。</span><span class="sxs-lookup"><span data-stu-id="96594-109">**Snippets** are similar to bookmarklets.</span></span>  
*   <span data-ttu-id="96594-110">[调试 JavaScript](#debug-javascript)。</span><span class="sxs-lookup"><span data-stu-id="96594-110">[Debug JavaScript](#debug-javascript).</span></span>  
*   <span data-ttu-id="96594-111">[设置 Workspace](#set-up-a-workspace)，以便将你在 DevTools 中所做的更改保存到文件系统上的代码中。</span><span class="sxs-lookup"><span data-stu-id="96594-111">[Set up a Workspace](#set-up-a-workspace), so that changes you make in DevTools get saved to the code on your file system.</span></span>  
    
## <span data-ttu-id="96594-112">显示文件</span><span class="sxs-lookup"><span data-stu-id="96594-112">Display files</span></span>  

<span data-ttu-id="96594-113">使用 **"页面** "窗格显示页面加载的所有资源。</span><span class="sxs-lookup"><span data-stu-id="96594-113">Use the **Page** pane to display all of the resources that the page has loaded.</span></span>

:::image type="complex" source="../media/sources-page-pane.msft.png" alt-text="“页面”窗格" lightbox="../media/sources-page-pane.msft.png":::
   <span data-ttu-id="96594-115">**页面** 窗格</span><span class="sxs-lookup"><span data-stu-id="96594-115">The **Page** pane</span></span>  
:::image-end:::  

<span data-ttu-id="96594-116">**页面** 窗格的组织方式：</span><span class="sxs-lookup"><span data-stu-id="96594-116">How the **Page** pane is organized:</span></span>  
*   <span data-ttu-id="96594-117">顶层，如上图中的 `top`， 表示 [HTML 框架][W3CHtml4Frames]。</span><span class="sxs-lookup"><span data-stu-id="96594-117">The top-level, such as `top` in the previous figure, represents an [HTML frame][W3CHtml4Frames].</span></span>  <span data-ttu-id="96594-118">在访问的每一页上查找 `top`。</span><span class="sxs-lookup"><span data-stu-id="96594-118">Find `top` on every page that you visit.</span></span>  `top` <span data-ttu-id="96594-119">表示主文档框架。</span><span class="sxs-lookup"><span data-stu-id="96594-119">represents the main document frame.</span></span>  
*   <span data-ttu-id="96594-120">二级，如上图中 `docs.microsoft.com` 所示，表示 [起源][HtmlstandardOrigin]。</span><span class="sxs-lookup"><span data-stu-id="96594-120">The second-level, such as `docs.microsoft.com` in the previous figure, represents an [origin][HtmlstandardOrigin].</span></span>  
*   <span data-ttu-id="96594-121">第三级、第四级等表示从该起源加载的目录和资源。</span><span class="sxs-lookup"><span data-stu-id="96594-121">The third-level, fourth-level, and so on, represent directories and resources that were loaded from that origin.</span></span>  <span data-ttu-id="96594-122">例如，在上图中，资源 `devtools-guide-chromium` 的完整路径为</span><span class="sxs-lookup"><span data-stu-id="96594-122">For example, in the previous figure the full path to the resource `devtools-guide-chromium` is</span></span> `docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium`  
    
<span data-ttu-id="96594-123">在"页面"窗格中 **选择** 一个文件，以显示 **编辑器窗格中的内容** 。</span><span class="sxs-lookup"><span data-stu-id="96594-123">Choose a file in the **Page** pane to display the contents in the **Editor** pane.</span></span>  <span data-ttu-id="96594-124">可以显示任何类型的文件。</span><span class="sxs-lookup"><span data-stu-id="96594-124">You may display any type of file.</span></span>  <span data-ttu-id="96594-125">对于图像，将显示图像的预览。</span><span class="sxs-lookup"><span data-stu-id="96594-125">For images, a preview of the image is displayed.</span></span>  

:::image type="complex" source="../media/sources-editor-pane.msft.png" alt-text="在编辑器窗格中a4d10f71.index-docs.js内容" lightbox="../media/sources-editor-pane.msft.png":::
   <span data-ttu-id="96594-127">在编辑器窗格中 `a4d10f71.index-docs.js` **显示内容**</span><span class="sxs-lookup"><span data-stu-id="96594-127">Display the contents of `a4d10f71.index-docs.js` in the **Editor** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="96594-128">编辑 CSS 和 JavaScript</span><span class="sxs-lookup"><span data-stu-id="96594-128">Edit CSS and JavaScript</span></span>  

<span data-ttu-id="96594-129">使用 **编辑器** 窗格编辑 CSS 和 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="96594-129">Use the **Editor** pane to edit CSS and JavaScript.</span></span>  <span data-ttu-id="96594-130">DevTools 更新页面以运行新代码。</span><span class="sxs-lookup"><span data-stu-id="96594-130">DevTools updates the page to run your new code.</span></span>  <span data-ttu-id="96594-131">例如，如果通过添加以下样式规则编辑 CSS 文件：</span><span class="sxs-lookup"><span data-stu-id="96594-131">For example, if you edit a CSS file by adding the style rule below:</span></span>

```css
.metadata.page-metadata {
    color: red;
}
```

<span data-ttu-id="96594-132">该更改应立即生效。</span><span class="sxs-lookup"><span data-stu-id="96594-132">That change should take effect immediately.</span></span>

:::image type="complex" source="../media/edit-css.msft.png" alt-text="编辑编辑器窗格中的 CSS，将字幕的文本颜色更改为红色" lightbox="../media/edit-css.msft.png":::
   <span data-ttu-id="96594-134">编辑 **编辑器** 窗格中的CSS，将字幕的文本颜色更改为红色</span><span class="sxs-lookup"><span data-stu-id="96594-134">Edit CSS in the **Editor** pane to change the text color of the subtitle to red</span></span>  
:::image-end:::  

<span data-ttu-id="96594-135">CSS 更改会立即生效，无需保存。</span><span class="sxs-lookup"><span data-stu-id="96594-135">CSS changes take effect immediately, no save needed.</span></span>  <span data-ttu-id="96594-136">若要使 JavaScript 更改生效，请选择 `Control` + `S`\(Windows、Linux\) 或 `Command` + `S`\(macOS\)。</span><span class="sxs-lookup"><span data-stu-id="96594-136">For JavaScript changes to take effect, select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\).</span></span>  <span data-ttu-id="96594-137">DevTools 不会重新运行脚本，因此唯一生效的 JavaScript 更改就是你在函数内部所做的更改。</span><span class="sxs-lookup"><span data-stu-id="96594-137">DevTools does not re-run a script, so the only JavaScript changes that take effect are those that you make inside of functions.</span></span>  <span data-ttu-id="96594-138">例如，在下图中，请注意 `console.log('A')` 如何没有运行，而 `console.log('B')` 则运行。</span><span class="sxs-lookup"><span data-stu-id="96594-138">For example, in the following figure, notice how `console.log('A')` does not run, whereas `console.log('B')` does.</span></span>  <span data-ttu-id="96594-139">If DevTools 在更改后重新运行整个脚本，则文本 `A` 已经记录到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="96594-139">If DevTools re-runs the entire script after making the change, then the text `A` would have been logged to the **Console**.</span></span>  

:::image type="complex" source="../media/edit-js.msft.png" alt-text="在编辑器窗格中编辑 JavaScript" lightbox="../media/edit-js.msft.png":::
   <span data-ttu-id="96594-141">在 **编辑器** 窗格中编辑 JavaScript</span><span class="sxs-lookup"><span data-stu-id="96594-141">Editing JavaScript in the **Editor** pane</span></span>  
:::image-end:::  

<span data-ttu-id="96594-142">在重新加载页面时，DevTools 会清除 CSS 和 JavaScript 更改。</span><span class="sxs-lookup"><span data-stu-id="96594-142">DevTools erases your CSS and JavaScript changes when you reload the page.</span></span>  <span data-ttu-id="96594-143">导航至 [设置工作区](#set-up-a-workspace)，了解如何将更改保存到文件系统。</span><span class="sxs-lookup"><span data-stu-id="96594-143">Navigate to [Set up a Workspace](#set-up-a-workspace) to learn how to save the changes to your file system.</span></span>  

## <span data-ttu-id="96594-144">创建、保存和运行代码段</span><span class="sxs-lookup"><span data-stu-id="96594-144">Create, save, and run Snippets</span></span>  

<span data-ttu-id="96594-145">代码段是您可以在任何页面上运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="96594-145">Snippets are scripts which you may run on any page.</span></span>  <span data-ttu-id="96594-146">假设你在控制台中重复键入以下代码，以便将\*\*\*\* jQuery 库插入页面，以便你可以从控制台运行 jQuery**命令**。</span><span class="sxs-lookup"><span data-stu-id="96594-146">Imagine that you repeatedly type out the following code in the **Console**, in order to insert the jQuery library into a page, so that you may run jQuery commands from the **Console**.</span></span>  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

<span data-ttu-id="96594-147">相反，你可以将此代码保存在 **代码段** 中，并随时通过单击几次按钮来运行它。</span><span class="sxs-lookup"><span data-stu-id="96594-147">Instead, you may save this code in a **Snippet** and run it with a couple of button clicks, any time you need it.</span></span>  <span data-ttu-id="96594-148">DevTools 将 **代码段** 保存到文件系统。</span><span class="sxs-lookup"><span data-stu-id="96594-148">DevTools saves the **Snippet** to your file system.</span></span>  

:::image type="complex" source="../media/snippet.msft.png" alt-text="将 jQuery 库插入到页面中的代码段" lightbox="../media/snippet.msft.png":::
   <span data-ttu-id="96594-150">将 jQuery 库插入到页面中的 **代码段**</span><span class="sxs-lookup"><span data-stu-id="96594-150">A **Snippet** that inserts the jQuery library into a page</span></span>  
:::image-end:::  

<span data-ttu-id="96594-151">若要运行 **代码段**：</span><span class="sxs-lookup"><span data-stu-id="96594-151">To run a **Snippet**:</span></span>

*   <span data-ttu-id="96594-152">使用 **代码段** 窗格打开文件， 然后选择 **运行**\（![运行按钮][ImageRunIcon]\）。</span><span class="sxs-lookup"><span data-stu-id="96594-152">Open the file using the **Snippets** pane, and choose **Run** \(![The Run button][ImageRunIcon]\).</span></span>  
*   <span data-ttu-id="96594-153">打开 [命令菜单][DevtoolsGuideChromiumCommandMenuIndex]，删除 `>` 字符，键入 `!` ，键入代码段 **的名称**，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="96594-153">Open the [Command Menu][DevtoolsGuideChromiumCommandMenuIndex], delete the `>` character, type `!`, type the name of your **Snippet**, and then select `Enter`.</span></span>  
    
<span data-ttu-id="96594-154">导航至 [从任何页面运行代码段][DevtoolsGuideChromiumJavascriptSnippets] 以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="96594-154">Navigate to [Run Snippets Of Code From Any Page][DevtoolsGuideChromiumJavascriptSnippets] to learn more.</span></span>

## <span data-ttu-id="96594-155">调试 JavaScript</span><span class="sxs-lookup"><span data-stu-id="96594-155">Debug JavaScript</span></span>  

<span data-ttu-id="96594-156">请考虑改为使用 Microsoft Edge DevTools 调试工具，而不是通过`console.log()` 推断 JavaScript 出错的地方。</span><span class="sxs-lookup"><span data-stu-id="96594-156">Rather than using `console.log()` to infer where your JavaScript is going wrong, consider using the Microsoft Edge DevTools debugging tools, instead.</span></span>  <span data-ttu-id="96594-157">一般想法是设置断点，这是代码中的一个有意停止位置，然后逐步执行代码的运行时，每次一行。</span><span class="sxs-lookup"><span data-stu-id="96594-157">The general idea is to set a breakpoint, which is an intentional stopping place in your code, and then step through the runtime of your code, one line at a time.</span></span>  <span data-ttu-id="96594-158">在逐步执行代码时，可以显示和更改所有当前定义的属性和变量的值，在控制台中运行 JavaScript 等。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="96594-158">As you step through the code, you may display and change the values of all currently-defined properties and variables, run JavaScript in the **Console**, and more.</span></span>

<span data-ttu-id="96594-159">导航到 [调试 JavaScript入门][DevtoolsGuideChromiumJavascriptIndex]，了解 DevTools 中调试的基础知识。</span><span class="sxs-lookup"><span data-stu-id="96594-159">Navigate to [Get Started With Debugging JavaScript][DevtoolsGuideChromiumJavascriptIndex] to learn the basics of debugging in DevTools.</span></span>

:::image type="complex" source="../media/debugging.msft.png" alt-text="调试 JavaScript" lightbox="../media/debugging.msft.png":::
   <span data-ttu-id="96594-161">调试 JavaScript</span><span class="sxs-lookup"><span data-stu-id="96594-161">Debug JavaScript</span></span>  
:::image-end:::  

## <span data-ttu-id="96594-162">设置工作区</span><span class="sxs-lookup"><span data-stu-id="96594-162">Set up a Workspace</span></span>  

<span data-ttu-id="96594-163">默认情况下，当您在源工具中编辑文件时，\*\*\*\* 这些更改在重新加载页面时将丢失。</span><span class="sxs-lookup"><span data-stu-id="96594-163">By default, when you edit a file in the **Sources** tool, those changes are lost when you reload the page.</span></span>  <span data-ttu-id="96594-164">**工作区** 使您能够将你在 DevTools 中所做的更改保存到文件系统。</span><span class="sxs-lookup"><span data-stu-id="96594-164">**Workspaces** enable you to save the changes that you make in DevTools to your file system.</span></span>  <span data-ttu-id="96594-165">实质上，DevTools 能够用作代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="96594-165">Essentially, DevTools is able to be used as your code editor.</span></span>

<span data-ttu-id="96594-166">导航到 [使用工作区编辑文件][DevtoolsGuideChromiumWorkspacesIndex] 以开始操作。</span><span class="sxs-lookup"><span data-stu-id="96594-166">Navigate to [Edit Files With Workspaces][DevtoolsGuideChromiumWorkspacesIndex] to get started.</span></span>

## <span data-ttu-id="96594-167">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="96594-167">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageRunIcon]: ../media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsGuideChromiumCommandMenuIndex]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft Docs"  
[DevtoolsGuideChromiumJavascriptIndex]: ../javascript/index.md "开始在 Microsoft Edge DevTools 中调试 JavaScript |Microsoft Docs"  
[DevtoolsGuideChromiumJavascriptSnippets]: ../javascript/snippets.md "使用 Microsoft Edge DevTools 在任何页面上运行 JavaScript 代码段 |Microsoft Docs"  
[DevtoolsGuideChromiumWorkspacesIndex]: ../workspaces/index.md "使用 Workspaces 编辑文件 |Microsoft Docs"  

[HtmlstandardOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "Origin |HTML Standard"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "框架|W3C"  

> [!NOTE]
> <span data-ttu-id="96594-174">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="96594-174">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="96594-175">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/sources)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="96594-175">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/sources) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="96594-177">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="96594-177">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
