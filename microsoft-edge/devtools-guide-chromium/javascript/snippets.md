---
title: 在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: aa9f7e96c7e379c1fe537ffba730e08990e0c20a
ms.sourcegitcommit: ecdc4287fa25a18cb4ddcaf43fcce3b396c3314c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/17/2020
ms.locfileid: "10581815"
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





# <span data-ttu-id="8791f-103">在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段</span><span class="sxs-lookup"><span data-stu-id="8791f-103">Run Snippets Of JavaScript On Any Page With Microsoft Edge DevTools</span></span>   



<span data-ttu-id="8791f-104">如果你发现自己在[控制台][DevtoolsConsoleIndex]中重复运行相同的代码，请考虑改为将代码另存为代码段。</span><span class="sxs-lookup"><span data-stu-id="8791f-104">If you find yourself running the same code in the [Console][DevtoolsConsoleIndex] repeatedly, consider saving the code as a Snippet instead.</span></span>  <span data-ttu-id="8791f-105">代码段是您在 " [**源**" 面板][DevToolsSourcesPanel]中创作的脚本。</span><span class="sxs-lookup"><span data-stu-id="8791f-105">Snippets are scripts that you author in the [**Sources** panel][DevToolsSourcesPanel].</span></span>  <span data-ttu-id="8791f-106">他们有权访问页面的 JavaScript 上下文，您可以在任何页面上运行这些上下文。</span><span class="sxs-lookup"><span data-stu-id="8791f-106">They have access to the JavaScript context of the page, and you can run them on any page.</span></span>  <span data-ttu-id="8791f-107">代码段是[bookmarklets][WikiBookmarklet]的替代方法。</span><span class="sxs-lookup"><span data-stu-id="8791f-107">Snippets are an alternative to [bookmarklets][WikiBookmarklet].</span></span>  
<span data-ttu-id="8791f-108">Firefox DevTools 的功能类似于名为 "[便笺簿][MDNScratchpad]" 的 "片段"。</span><span class="sxs-lookup"><span data-stu-id="8791f-108">Firefox DevTools has a feature similar to Snippets called [Scratchpad][MDNScratchpad].</span></span>  

<span data-ttu-id="8791f-109">例如，[**图 1**](#figure-1)显示左侧的 DevTools 主页和右侧的一些代码段源代码。</span><span class="sxs-lookup"><span data-stu-id="8791f-109">For example, [**Figure 1**](#figure-1) shows the DevTools homepage on the left and some Snippet source code on the right.</span></span>  

> ##### <span data-ttu-id="8791f-110">图 1</span><span class="sxs-lookup"><span data-stu-id="8791f-110">Figure 1</span></span>  
> <span data-ttu-id="8791f-111">运行代码段之前页面的外观</span><span class="sxs-lookup"><span data-stu-id="8791f-111">How the page looks before running the Snippet</span></span>  
> ![运行代码段之前页面的外观][ImageSnippetSplitScreen]  

<span data-ttu-id="8791f-113">[**图 1**](#figure-1)中的代码段源代码：</span><span class="sxs-lookup"><span data-stu-id="8791f-113">The Snippet source code from [**Figure 1**](#figure-1):</span></span>  

```javascript
console.log('Hello, Snippets!');
document.body.innerHTML = '';
var p = document.createElement('p');
p.textContent = 'Hello, Snippets!';
document.body.appendChild(p);
```  

<span data-ttu-id="8791f-114">[**图 2**](#figure-2)显示了运行代码段后页面的外观。</span><span class="sxs-lookup"><span data-stu-id="8791f-114">[**Figure 2**](#figure-2) shows how the page looks after running the Snippet.</span></span>  <span data-ttu-id="8791f-115">**控制台抽屉**将弹出 `Hello, Snippets!` ，显示代码片段记录的消息，并且该页面的内容将完全更改。</span><span class="sxs-lookup"><span data-stu-id="8791f-115">The **Console Drawer** pops up to display the `Hello, Snippets!` message that the Snippet logs, and the content of the page changes completely.</span></span>  

> ##### <span data-ttu-id="8791f-116">图 2</span><span class="sxs-lookup"><span data-stu-id="8791f-116">Figure 2</span></span>  
> <span data-ttu-id="8791f-117">运行代码段后页面的外观</span><span class="sxs-lookup"><span data-stu-id="8791f-117">How the page looks after running the Snippet</span></span>  
> ![运行代码段后页面的外观][ImageSnippetSplitScreenAfter]  

## <span data-ttu-id="8791f-119">打开 "代码段" 窗格</span><span class="sxs-lookup"><span data-stu-id="8791f-119">Open the Snippets pane</span></span>   

<span data-ttu-id="8791f-120">"**代码段**" 窗格将列出你的代码段。</span><span class="sxs-lookup"><span data-stu-id="8791f-120">The **Snippets** pane lists your Snippets.</span></span>  <span data-ttu-id="8791f-121">若要编辑代码段，需要从 "**代码段**" 窗格中将其打开。</span><span class="sxs-lookup"><span data-stu-id="8791f-121">When you want to edit a Snippet, you need to open it from the **Snippets** pane.</span></span>  

> ##### <span data-ttu-id="8791f-122">图 3</span><span class="sxs-lookup"><span data-stu-id="8791f-122">Figure 3</span></span>  
> <span data-ttu-id="8791f-123">"**代码段**" 窗格</span><span class="sxs-lookup"><span data-stu-id="8791f-123">The **Snippets** pane</span></span>  
> !["代码段" 窗格][ImageSnippetsPane]  

### <span data-ttu-id="8791f-125">使用鼠标打开 "代码段" 窗格</span><span class="sxs-lookup"><span data-stu-id="8791f-125">Open the Snippets pane with a mouse</span></span>   

1.  <span data-ttu-id="8791f-126">单击 "**源**" 选项卡以打开 "**源**" 面板。</span><span class="sxs-lookup"><span data-stu-id="8791f-126">Click the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="8791f-127">默认情况下，**页面**窗格通常打开。</span><span class="sxs-lookup"><span data-stu-id="8791f-127">The **Page** pane usually opens by default.</span></span>  

    > ##### <span data-ttu-id="8791f-128">图 4</span><span class="sxs-lookup"><span data-stu-id="8791f-128">Figure 4</span></span>  
    > <span data-ttu-id="8791f-129">在左侧打开**页面**窗格的 "**源**" 面板</span><span class="sxs-lookup"><span data-stu-id="8791f-129">The **Sources** panel with the **Page** pane open on the left</span></span>  
    > ![在左侧打开页面窗格的 "源" 面板][ImageSourcesPageEmpty]  

1.  <span data-ttu-id="8791f-131">单击 "**代码段**" 选项卡以打开 "**代码段**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="8791f-131">Click the **Snippets** tab to open the **Snippets** pane.</span></span>  <span data-ttu-id="8791f-132">你可能需要单击 "**更多选项**卡" 选项 ![ 卡才能 ][ImageMoreTabsIcon] 访问 "**代码段**" 选项。</span><span class="sxs-lookup"><span data-stu-id="8791f-132">You might need to click **More Tabs** ![More Tabs][ImageMoreTabsIcon] in order to access the **Snippets** option.</span></span>  

### <span data-ttu-id="8791f-133">通过 "命令" 菜单打开 "代码段" 窗格</span><span class="sxs-lookup"><span data-stu-id="8791f-133">Open the Snippets pane with the Command Menu</span></span>   

1.  <span data-ttu-id="8791f-134">将光标聚焦在 DevTools 内的某个位置。</span><span class="sxs-lookup"><span data-stu-id="8791f-134">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="8791f-135">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单。</span><span class="sxs-lookup"><span data-stu-id="8791f-135">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="8791f-136">开始键入 `Snippets` ，选择 "**显示代码段**"，然后按 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="8791f-136">Start typing `Snippets`, select **Show Snippets**, and then press `Enter` to run the command.</span></span>  

    > ##### <span data-ttu-id="8791f-137">图 5</span><span class="sxs-lookup"><span data-stu-id="8791f-137">Figure 5</span></span>  
    > <span data-ttu-id="8791f-138">"**显示代码段**" 命令</span><span class="sxs-lookup"><span data-stu-id="8791f-138">The **Show Snippets** command</span></span>  
    > !["显示代码段" 命令][ImageShowSnippetsSearch]  

## <span data-ttu-id="8791f-140">创建代码段</span><span class="sxs-lookup"><span data-stu-id="8791f-140">Create Snippets</span></span>   

### <span data-ttu-id="8791f-141">通过 "源" 面板创建代码段</span><span class="sxs-lookup"><span data-stu-id="8791f-141">Create a Snippet through the Sources panel</span></span>   

1.  <span data-ttu-id="8791f-142">[打开 "**代码段**" 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="8791f-142">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="8791f-143">单击 "**新建代码段**"。</span><span class="sxs-lookup"><span data-stu-id="8791f-143">Click **New snippet**.</span></span>  
1.  <span data-ttu-id="8791f-144">输入代码段的名称，然后按 " `Enter` 保存"。</span><span class="sxs-lookup"><span data-stu-id="8791f-144">Enter a name for your Snippet then press `Enter` to save.</span></span>  

    > ##### <span data-ttu-id="8791f-145">图 6</span><span class="sxs-lookup"><span data-stu-id="8791f-145">Figure 6</span></span>  
    > <span data-ttu-id="8791f-146">命名代码段</span><span class="sxs-lookup"><span data-stu-id="8791f-146">Naming a Snippet</span></span>  
    > ![命名代码段][ImageSnippetName]  

### <span data-ttu-id="8791f-148">通过 "命令" 菜单创建代码段</span><span class="sxs-lookup"><span data-stu-id="8791f-148">Create a Snippet through the Command Menu</span></span>   

1.  <span data-ttu-id="8791f-149">将光标聚焦在 DevTools 内的某个位置。</span><span class="sxs-lookup"><span data-stu-id="8791f-149">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="8791f-150">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单。</span><span class="sxs-lookup"><span data-stu-id="8791f-150">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="8791f-151">开始键入 `Snippet` ，选择 "**创建新代码段**"，然后按 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="8791f-151">Start typing `Snippet`, select **Create new snippet**, then press `Enter` to run the command.</span></span>  

    > ##### <span data-ttu-id="8791f-152">图 7</span><span class="sxs-lookup"><span data-stu-id="8791f-152">Figure 7</span></span>  
    > <span data-ttu-id="8791f-153">用于创建新代码段的命令</span><span class="sxs-lookup"><span data-stu-id="8791f-153">The command for creating a new Snippet</span></span>  
    > ![用于创建新代码段的命令][ImageCreateSnippetSearch]  

<span data-ttu-id="8791f-155">如果想要为新的代码段提供自定义名称，请参阅[重命名代码段](#rename-snippets)。</span><span class="sxs-lookup"><span data-stu-id="8791f-155">See [Rename Snippets](#rename-snippets) if you'd like to give your new Snippet a custom name.</span></span>  

## <span data-ttu-id="8791f-156">编辑代码段</span><span class="sxs-lookup"><span data-stu-id="8791f-156">Edit Snippets</span></span>   

1.  <span data-ttu-id="8791f-157">[打开 "**代码段**" 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="8791f-157">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="8791f-158">在 "代码**段**" 窗格中，单击要编辑的代码段的名称，以便在**代码编辑器**中将其打开。</span><span class="sxs-lookup"><span data-stu-id="8791f-158">In the **Snippets** pane click the name of the Snippet that you want to edit in order to open it in the **Code Editor**.</span></span>  

    > ##### <span data-ttu-id="8791f-159">图 8</span><span class="sxs-lookup"><span data-stu-id="8791f-159">Figure 8</span></span>  
    > <span data-ttu-id="8791f-160">代码编辑器</span><span class="sxs-lookup"><span data-stu-id="8791f-160">The Code Editor</span></span>  
    > ![代码编辑器][ImageSnippetEditor]  

1.  <span data-ttu-id="8791f-162">使用**代码编辑器**将 JavaScript 添加到代码段。</span><span class="sxs-lookup"><span data-stu-id="8791f-162">Use the **Code Editor** to add JavaScript to your Snippet.</span></span>  
1.  <span data-ttu-id="8791f-163">当代码段名称旁边显示星号时，表示你有未保存的代码。</span><span class="sxs-lookup"><span data-stu-id="8791f-163">When an asterisk appears next to the name of your Snippet it means you have unsaved code.</span></span> <span data-ttu-id="8791f-164">按 `Control` + `S` \ （Windows \）或 `Command` + `S` \ （macOS \）保存。</span><span class="sxs-lookup"><span data-stu-id="8791f-164">Press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save.</span></span>  

    > ##### <span data-ttu-id="8791f-165">图 9</span><span class="sxs-lookup"><span data-stu-id="8791f-165">Figure 9</span></span>  
    > <span data-ttu-id="8791f-166">代码段名称旁边的星号，指示未保存的代码</span><span class="sxs-lookup"><span data-stu-id="8791f-166">An asterisk next to the Snippet name, which indicates unsaved code</span></span>  
    > ![代码段名称旁边的星号，指示未保存的代码][ImageUnsavedSnippet]  

## <span data-ttu-id="8791f-168">运行代码段</span><span class="sxs-lookup"><span data-stu-id="8791f-168">Run Snippets</span></span>   

### <span data-ttu-id="8791f-169">从 "源" 面板运行代码段</span><span class="sxs-lookup"><span data-stu-id="8791f-169">Run a Snippet from the Sources panel</span></span>   

1.  <span data-ttu-id="8791f-170">[打开 "**代码段**" 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="8791f-170">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="8791f-171">单击要运行的代码段的名称。</span><span class="sxs-lookup"><span data-stu-id="8791f-171">Click the name of the Snippet that you want to run.</span></span>  <span data-ttu-id="8791f-172">代码段将在**代码编辑器**中打开。</span><span class="sxs-lookup"><span data-stu-id="8791f-172">The Snippet opens in the **Code Editor**.</span></span>  
1.  <span data-ttu-id="8791f-173">单击 "**运行片段** ![ 运行代码段 ][ImageRunSnippetIcon] "，或按 `Control` + `Enter` \ （Windows \）或 `Command` + `Enter` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="8791f-173">Click **Run Snippet** ![Run Snippet][ImageRunSnippetIcon], or press `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\).</span></span>  

### <span data-ttu-id="8791f-174">使用 "命令" 菜单运行代码段</span><span class="sxs-lookup"><span data-stu-id="8791f-174">Run a Snippet with the Command Menu</span></span>   

1.  <span data-ttu-id="8791f-175">将光标聚焦在 DevTools 内的某个位置。</span><span class="sxs-lookup"><span data-stu-id="8791f-175">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="8791f-176">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单。</span><span class="sxs-lookup"><span data-stu-id="8791f-176">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="8791f-177">删除 `>` 字符，然后键入一个字符，然后键入 `!` 要运行的代码段的名称。</span><span class="sxs-lookup"><span data-stu-id="8791f-177">Delete the `>` character and type the `!` character followed by the name of the Snippet that you want to run.</span></span>  

    > ##### <span data-ttu-id="8791f-178">图 10</span><span class="sxs-lookup"><span data-stu-id="8791f-178">Figure 10</span></span>  
    > <span data-ttu-id="8791f-179">从 "命令" 菜单运行代码段</span><span class="sxs-lookup"><span data-stu-id="8791f-179">Running a Snippet from the Command Menu</span></span>  
    > ![从 "命令" 菜单运行代码段][ImageRunSnippetCommand]  

1.  <span data-ttu-id="8791f-181">按 `Enter` 运行代码段。</span><span class="sxs-lookup"><span data-stu-id="8791f-181">Press `Enter` to run the Snippet.</span></span>  

## <span data-ttu-id="8791f-182">重命名代码段</span><span class="sxs-lookup"><span data-stu-id="8791f-182">Rename Snippets</span></span>   

1.  <span data-ttu-id="8791f-183">[打开 "**代码段**" 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="8791f-183">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="8791f-184">右键单击代码段名称，然后选择 "**重命名**"。</span><span class="sxs-lookup"><span data-stu-id="8791f-184">Right-click the Snippet name and select **Rename**.</span></span>  

## <span data-ttu-id="8791f-185">删除代码段</span><span class="sxs-lookup"><span data-stu-id="8791f-185">Delete Snippets</span></span>   

1.  <span data-ttu-id="8791f-186">[打开 "**代码段**" 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="8791f-186">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="8791f-187">右键单击代码段名称，然后选择 "**删除**"。</span><span class="sxs-lookup"><span data-stu-id="8791f-187">Right-click the Snippet name and select **Remove**.</span></span>  

 



<!-- image links -->  

[ImageMoreTabsIcon]: /microsoft-edge/devtools-guide-chromium/media/more-tabs-icon.msft.png  
[ImageRunSnippetIcon]: /microsoft-edge/devtools-guide-chromium/media/run-snippet-icon.msft.png  

[ImageSnippetSplitScreen]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-split-screen.msft.png "图1：运行代码段之前页面的外观"  
[ImageSnippetSplitScreenAfter]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-split-screen-after.msft.png "图2：运行代码段后页面的外观"  
[ImageSnippetsPane]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-pane.msft.png "图3： "代码段" 窗格"  
[ImageSourcesPageEmpty]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-page-pane.msft.png "图4：在左侧打开页面窗格的 "源" 面板"  
[ImageShowSnippetsSearch]: /microsoft-edge/devtools-guide-chromium/media/javascript-search-show-snippets.msft.png "图5： "显示代码段" 命令"  
[ImageSnippetName]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-naming.msft.png "图6：命名代码段"  
[ImageCreateSnippetSearch]: /microsoft-edge/devtools-guide-chromium/media/javascript-search-create-new-snippet.msft.png "图7：用于创建新代码段的命令"  
[ImageSnippetEditor]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-editor-saved.msft.png "图8：代码编辑器"  
[ImageUnsavedSnippet]: /microsoft-edge/devtools-guide-chromium/media/javascript-sources-snippets-editor-unsaved.msft.png "图9：代码段名称旁边的星号，指示未保存的代码"  
[ImageRunSnippetCommand]: /microsoft-edge/devtools-guide-chromium/media/javascript-search-run-command.msft.png "图10：从命令菜单运行代码段"  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "控制台概述"  
[DevToolsSourcesPanel]: ../sources.md ""源" 面板概述"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "便笺 |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet-维基百科"  

> [!NOTE]
> <span data-ttu-id="8791f-202">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="8791f-202">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8791f-203">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="8791f-203">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="8791f-205">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="8791f-205">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
