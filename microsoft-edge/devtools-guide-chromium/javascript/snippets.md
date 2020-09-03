---
description: 代码段是可以在 Microsoft Edge DevTools 的 "源" 面板中创作和运行的小型脚本。  您可以从任何页面访问和运行它们。  运行代码段时，它从当前打开的页面的上下文中运行。
title: 在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 5f6284179aacb471116a2d732507b010c37ef235
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993385"
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





# <span data-ttu-id="46f5c-106">在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段</span><span class="sxs-lookup"><span data-stu-id="46f5c-106">Run snippets of JavaScript on any page with Microsoft Edge DevTools</span></span>   



<span data-ttu-id="46f5c-107">如果你发现自己在 [控制台][DevtoolsConsoleIndex] 中重复运行相同的代码，请考虑改为将代码另存为代码段。</span><span class="sxs-lookup"><span data-stu-id="46f5c-107">If you find yourself running the same code in the [Console][DevtoolsConsoleIndex] repeatedly, consider saving the code as a Snippet instead.</span></span>  <span data-ttu-id="46f5c-108">代码段是您在 " [源][DevToolsSourcesPanel] " 面板中创作的脚本。</span><span class="sxs-lookup"><span data-stu-id="46f5c-108">Snippets are scripts that you author in the [Sources][DevToolsSourcesPanel] panel.</span></span>  <span data-ttu-id="46f5c-109">他们有权访问页面的 JavaScript 上下文，您可以在任何页面上运行这些上下文。</span><span class="sxs-lookup"><span data-stu-id="46f5c-109">They have access to the JavaScript context of the page, and you can run them on any page.</span></span>  <span data-ttu-id="46f5c-110">代码段是 [bookmarklets][WikiBookmarklet]的替代方法。</span><span class="sxs-lookup"><span data-stu-id="46f5c-110">Snippets are an alternative to [bookmarklets][WikiBookmarklet].</span></span>  
<span data-ttu-id="46f5c-111">Firefox DevTools 的功能类似于名为 " [便笺簿][MDNScratchpad]" 的 "片段"。</span><span class="sxs-lookup"><span data-stu-id="46f5c-111">Firefox DevTools has a feature similar to Snippets called [Scratchpad][MDNScratchpad].</span></span>  

<span data-ttu-id="46f5c-112">例如，下图显示左侧的 DevTools 主页和右侧的一些代码段源代码。</span><span class="sxs-lookup"><span data-stu-id="46f5c-112">For example, in the following figure shows the DevTools homepage on the left and some Snippet source code on the right.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="运行代码段之前页面的外观" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
   <span data-ttu-id="46f5c-114">运行代码段之前页面的外观</span><span class="sxs-lookup"><span data-stu-id="46f5c-114">How the page looks before running the Snippet</span></span>  
:::image-end:::  

<span data-ttu-id="46f5c-115">上图中的代码段源代码。</span><span class="sxs-lookup"><span data-stu-id="46f5c-115">The Snippet source code from the previous figure.</span></span>  

```javascript
console.log('Hello, Snippets!');
document.body.innerHTML = '';
var p = document.createElement('p');
p.textContent = 'Hello, Snippets!';
document.body.appendChild(p);
```  

<span data-ttu-id="46f5c-116">下图显示了运行代码段后的页面。</span><span class="sxs-lookup"><span data-stu-id="46f5c-116">In the following figure, the page appears after running the Snippet.</span></span>  <span data-ttu-id="46f5c-117">**控制台抽屉**将弹出 `Hello, Snippets!` ，显示代码片段记录的消息，并且该页面的内容将完全更改。</span><span class="sxs-lookup"><span data-stu-id="46f5c-117">The **Console Drawer** pops up to display the `Hello, Snippets!` message that the Snippet logs, and the content of the page changes completely.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="运行代码段后页面的外观" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   <span data-ttu-id="46f5c-119">运行代码段后页面的外观</span><span class="sxs-lookup"><span data-stu-id="46f5c-119">How the page looks after running the Snippet</span></span>  
:::image-end:::  

## <span data-ttu-id="46f5c-120">打开 "代码段" 窗格</span><span class="sxs-lookup"><span data-stu-id="46f5c-120">Open the Snippets pane</span></span>   

<span data-ttu-id="46f5c-121">" **代码段** " 窗格将列出你的代码段。</span><span class="sxs-lookup"><span data-stu-id="46f5c-121">The **Snippets** pane lists your Snippets.</span></span>  <span data-ttu-id="46f5c-122">若要编辑代码段，需要从 " **代码段** " 窗格中将其打开。</span><span class="sxs-lookup"><span data-stu-id="46f5c-122">When you want to edit a Snippet, you need to open it from the **Snippets** pane.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text=""代码段" 窗格" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   <span data-ttu-id="46f5c-124">" **代码段** " 窗格</span><span class="sxs-lookup"><span data-stu-id="46f5c-124">The **Snippets** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="46f5c-125">使用鼠标打开 "代码段" 窗格</span><span class="sxs-lookup"><span data-stu-id="46f5c-125">Open the Snippets pane with a mouse</span></span>   

1.  <span data-ttu-id="46f5c-126">单击 " **源** " 选项卡以打开 " **源** " 面板。</span><span class="sxs-lookup"><span data-stu-id="46f5c-126">Click the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="46f5c-127">默认情况下， **页面** 窗格通常打开。</span><span class="sxs-lookup"><span data-stu-id="46f5c-127">The **Page** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="在左侧打开页面窗格的 "源" 面板" lightbox="../media/javascript-sources-page-pane.msft.png":::
       <span data-ttu-id="46f5c-129">在左侧打开**页面**窗格的 "**源**" 面板</span><span class="sxs-lookup"><span data-stu-id="46f5c-129">The **Sources** panel with the **Page** pane open on the left</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="46f5c-130">单击 " **代码段** " 选项卡以打开 " **代码段** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="46f5c-130">Click the **Snippets** tab to open the **Snippets** pane.</span></span>  <span data-ttu-id="46f5c-131">您可能需要单击 " **更多选项卡** \ (![ 更多选项卡 ][ImageMoreTabsIcon] \ ) " 才能访问 " **代码段** " 选项。</span><span class="sxs-lookup"><span data-stu-id="46f5c-131">You might need to click **More Tabs** \(![More Tabs][ImageMoreTabsIcon]\) in order to access the **Snippets** option.</span></span>  
    
### <span data-ttu-id="46f5c-132">通过 "命令" 菜单打开 "代码段" 窗格</span><span class="sxs-lookup"><span data-stu-id="46f5c-132">Open the Snippets pane with the Command Menu</span></span>   

1.  <span data-ttu-id="46f5c-133">将光标聚焦在 DevTools 内的某个位置。</span><span class="sxs-lookup"><span data-stu-id="46f5c-133">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="46f5c-134">按 `Control`+`Shift`+`P` \(Windows\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="46f5c-134">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="46f5c-135">开始键入 `Snippets` ，选择 " **显示代码段**"，然后按 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="46f5c-135">Start typing `Snippets`, select **Show Snippets**, and then press `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text=""显示代码段" 命令" lightbox="../media/javascript-search-show-snippets.msft.png":::
       <span data-ttu-id="46f5c-137">" **显示代码段** " 命令</span><span class="sxs-lookup"><span data-stu-id="46f5c-137">The **Show Snippets** command</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="46f5c-138">创建代码段</span><span class="sxs-lookup"><span data-stu-id="46f5c-138">Create Snippets</span></span>   

### <span data-ttu-id="46f5c-139">通过 "源" 面板创建代码段</span><span class="sxs-lookup"><span data-stu-id="46f5c-139">Create a Snippet through the Sources panel</span></span>   

1.  <span data-ttu-id="46f5c-140">[打开 " **代码段** " 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="46f5c-140">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="46f5c-141">单击 " **新建代码段**"。</span><span class="sxs-lookup"><span data-stu-id="46f5c-141">Click **New snippet**.</span></span>  
1.  <span data-ttu-id="46f5c-142">输入代码段的名称，然后按 " `Enter` 保存"。</span><span class="sxs-lookup"><span data-stu-id="46f5c-142">Enter a name for your Snippet then press `Enter` to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="为代码段命名" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       <span data-ttu-id="46f5c-144">为代码段命名</span><span class="sxs-lookup"><span data-stu-id="46f5c-144">Name a Snippet</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="46f5c-145">通过 "命令" 菜单创建代码段</span><span class="sxs-lookup"><span data-stu-id="46f5c-145">Create a Snippet through the Command Menu</span></span>   

1.  <span data-ttu-id="46f5c-146">将光标聚焦在 DevTools 内的某个位置。</span><span class="sxs-lookup"><span data-stu-id="46f5c-146">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="46f5c-147">按 `Control`+`Shift`+`P` \(Windows\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="46f5c-147">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="46f5c-148">开始键入 `Snippet` ，选择 " **创建新代码段**"，然后按 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="46f5c-148">Start typing `Snippet`, select **Create new snippet**, then press `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="用于创建新代码段的命令" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       <span data-ttu-id="46f5c-150">用于创建新代码段的命令</span><span class="sxs-lookup"><span data-stu-id="46f5c-150">The command for creating a new Snippet</span></span>  
    :::image-end:::  
    
<span data-ttu-id="46f5c-151">如果想要为新的代码段提供自定义名称，请参阅 [重命名代码段](#rename-snippets) 。</span><span class="sxs-lookup"><span data-stu-id="46f5c-151">See [Rename Snippets](#rename-snippets) if you'd like to give your new Snippet a custom name.</span></span>  

## <span data-ttu-id="46f5c-152">编辑代码段</span><span class="sxs-lookup"><span data-stu-id="46f5c-152">Edit Snippets</span></span>   

1.  <span data-ttu-id="46f5c-153">[打开 " **代码段** " 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="46f5c-153">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="46f5c-154">在 "代码 **段** " 窗格中，单击要编辑的代码段的名称，以便在 **代码编辑器**中将其打开。</span><span class="sxs-lookup"><span data-stu-id="46f5c-154">In the **Snippets** pane click the name of the Snippet that you want to edit in order to open it in the **Code Editor**.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="代码编辑器" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       <span data-ttu-id="46f5c-156">**代码编辑器**</span><span class="sxs-lookup"><span data-stu-id="46f5c-156">The **Code Editor**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="46f5c-157">使用 **代码编辑器** 将 JavaScript 添加到代码段。</span><span class="sxs-lookup"><span data-stu-id="46f5c-157">Use the **Code Editor** to add JavaScript to your Snippet.</span></span>  
1.  <span data-ttu-id="46f5c-158">当代码段名称旁边显示星号时，表示你有未保存的代码。</span><span class="sxs-lookup"><span data-stu-id="46f5c-158">When an asterisk appears next to the name of your Snippet it means you have unsaved code.</span></span> <span data-ttu-id="46f5c-159">按 `Control` + `S` \ (Windows \ ) 或 `Command` + `S` \ (macOS \ ) 保存。</span><span class="sxs-lookup"><span data-stu-id="46f5c-159">Press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="代码段名称旁边的星号，指示未保存的代码" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       <span data-ttu-id="46f5c-161">代码段名称旁边的星号，指示未保存的代码</span><span class="sxs-lookup"><span data-stu-id="46f5c-161">An asterisk next to the Snippet name, which indicates unsaved code</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="46f5c-162">运行代码段</span><span class="sxs-lookup"><span data-stu-id="46f5c-162">Run Snippets</span></span>   

### <span data-ttu-id="46f5c-163">从 "源" 面板运行代码段</span><span class="sxs-lookup"><span data-stu-id="46f5c-163">Run a Snippet from the Sources panel</span></span>   

1.  <span data-ttu-id="46f5c-164">[打开 " **代码段** " 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="46f5c-164">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="46f5c-165">单击要运行的代码段的名称。</span><span class="sxs-lookup"><span data-stu-id="46f5c-165">Click the name of the Snippet that you want to run.</span></span>  <span data-ttu-id="46f5c-166">代码段将在 **代码编辑器**中打开。</span><span class="sxs-lookup"><span data-stu-id="46f5c-166">The Snippet opens in the **Code Editor**.</span></span>  
1.  <span data-ttu-id="46f5c-167">单击 "**运行片段**\ (![ 运行代码段 ][ImageRunSnippetIcon] \ ) "，或按 `Control` + `Enter` \ (Windows \ ) 或 `Command` + `Enter` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="46f5c-167">Click **Run Snippet** \(![Run Snippet][ImageRunSnippetIcon]\), or press `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\).</span></span>  
    
### <span data-ttu-id="46f5c-168">使用 "命令" 菜单运行代码段</span><span class="sxs-lookup"><span data-stu-id="46f5c-168">Run a Snippet with the Command Menu</span></span>   

1.  <span data-ttu-id="46f5c-169">将光标聚焦在 DevTools 内的某个位置。</span><span class="sxs-lookup"><span data-stu-id="46f5c-169">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="46f5c-170">按 `Control`+`Shift`+`P` \(Windows\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="46f5c-170">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="46f5c-171">删除 `>` 字符，然后键入一个字符，然后键入 `!` 要运行的代码段的名称。</span><span class="sxs-lookup"><span data-stu-id="46f5c-171">Delete the `>` character and type the `!` character followed by the name of the Snippet that you want to run.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="从 "命令" 菜单运行代码段" lightbox="../media/javascript-search-run-command.msft.png":::
       <span data-ttu-id="46f5c-173">从 "**命令" 菜单**运行代码段</span><span class="sxs-lookup"><span data-stu-id="46f5c-173">Running a Snippet from the **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="46f5c-174">按 `Enter` 运行代码段。</span><span class="sxs-lookup"><span data-stu-id="46f5c-174">Press `Enter` to run the Snippet.</span></span>  

## <span data-ttu-id="46f5c-175">重命名代码段</span><span class="sxs-lookup"><span data-stu-id="46f5c-175">Rename Snippets</span></span>   

1.  <span data-ttu-id="46f5c-176">[打开 " **代码段** " 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="46f5c-176">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="46f5c-177">右键单击代码段名称，然后选择 " **重命名**"。</span><span class="sxs-lookup"><span data-stu-id="46f5c-177">Right-click the Snippet name and select **Rename**.</span></span>  
    
## <span data-ttu-id="46f5c-178">删除代码段</span><span class="sxs-lookup"><span data-stu-id="46f5c-178">Delete Snippets</span></span>   

1.  <span data-ttu-id="46f5c-179">[打开 " **代码段** " 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="46f5c-179">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="46f5c-180">右键单击代码段名称，然后选择 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="46f5c-180">Right-click the Snippet name and select **Remove**.</span></span>  
    
<!--  
 


-->  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  
[ImageRunSnippetIcon]: ../media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "控制台概述 |Microsoft 文档"  
[DevToolsSourcesPanel]: ../sources.md ""源" 面板概述 |Microsoft 文档"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "便笺 |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet-维基百科"  

> [!NOTE]
> <span data-ttu-id="46f5c-185">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="46f5c-185">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="46f5c-186">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="46f5c-186">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="46f5c-188">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="46f5c-188">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
