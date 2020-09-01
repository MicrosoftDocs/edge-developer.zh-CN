---
title: 在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 3a5ae986e3080a0b6a8b1bf34b0e0efc44c90303
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10981981"
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





# <span data-ttu-id="80f78-103">在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段</span><span class="sxs-lookup"><span data-stu-id="80f78-103">Run snippets of JavaScript on any page with Microsoft Edge DevTools</span></span>   



<span data-ttu-id="80f78-104">如果你发现自己在 [控制台][DevtoolsConsoleIndex] 中重复运行相同的代码，请考虑改为将代码另存为代码段。</span><span class="sxs-lookup"><span data-stu-id="80f78-104">If you find yourself running the same code in the [Console][DevtoolsConsoleIndex] repeatedly, consider saving the code as a Snippet instead.</span></span>  <span data-ttu-id="80f78-105">代码段是您在 " [源][DevToolsSourcesPanel] " 面板中创作的脚本。</span><span class="sxs-lookup"><span data-stu-id="80f78-105">Snippets are scripts that you author in the [Sources][DevToolsSourcesPanel] panel.</span></span>  <span data-ttu-id="80f78-106">他们有权访问页面的 JavaScript 上下文，您可以在任何页面上运行这些上下文。</span><span class="sxs-lookup"><span data-stu-id="80f78-106">They have access to the JavaScript context of the page, and you can run them on any page.</span></span>  <span data-ttu-id="80f78-107">代码段是 [bookmarklets][WikiBookmarklet]的替代方法。</span><span class="sxs-lookup"><span data-stu-id="80f78-107">Snippets are an alternative to [bookmarklets][WikiBookmarklet].</span></span>  
<span data-ttu-id="80f78-108">Firefox DevTools 的功能类似于名为 " [便笺簿][MDNScratchpad]" 的 "片段"。</span><span class="sxs-lookup"><span data-stu-id="80f78-108">Firefox DevTools has a feature similar to Snippets called [Scratchpad][MDNScratchpad].</span></span>  

<span data-ttu-id="80f78-109">例如，下图显示左侧的 DevTools 主页和右侧的一些代码段源代码。</span><span class="sxs-lookup"><span data-stu-id="80f78-109">For example, in the following figure shows the DevTools homepage on the left and some Snippet source code on the right.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="运行代码段之前页面的外观" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
   <span data-ttu-id="80f78-111">运行代码段之前页面的外观</span><span class="sxs-lookup"><span data-stu-id="80f78-111">How the page looks before running the Snippet</span></span>  
:::image-end:::  

<span data-ttu-id="80f78-112">上图中的代码段源代码。</span><span class="sxs-lookup"><span data-stu-id="80f78-112">The Snippet source code from the previous figure.</span></span>  

```javascript
console.log('Hello, Snippets!');
document.body.innerHTML = '';
var p = document.createElement('p');
p.textContent = 'Hello, Snippets!';
document.body.appendChild(p);
```  

<span data-ttu-id="80f78-113">下图显示了运行代码段后的页面。</span><span class="sxs-lookup"><span data-stu-id="80f78-113">In the following figure, the page appears after running the Snippet.</span></span>  <span data-ttu-id="80f78-114">**控制台抽屉**将弹出 `Hello, Snippets!` ，显示代码片段记录的消息，并且该页面的内容将完全更改。</span><span class="sxs-lookup"><span data-stu-id="80f78-114">The **Console Drawer** pops up to display the `Hello, Snippets!` message that the Snippet logs, and the content of the page changes completely.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="运行代码段后页面的外观" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   <span data-ttu-id="80f78-116">运行代码段后页面的外观</span><span class="sxs-lookup"><span data-stu-id="80f78-116">How the page looks after running the Snippet</span></span>  
:::image-end:::  

## <span data-ttu-id="80f78-117">打开 "代码段" 窗格</span><span class="sxs-lookup"><span data-stu-id="80f78-117">Open the Snippets pane</span></span>   

<span data-ttu-id="80f78-118">" **代码段** " 窗格将列出你的代码段。</span><span class="sxs-lookup"><span data-stu-id="80f78-118">The **Snippets** pane lists your Snippets.</span></span>  <span data-ttu-id="80f78-119">若要编辑代码段，需要从 " **代码段** " 窗格中将其打开。</span><span class="sxs-lookup"><span data-stu-id="80f78-119">When you want to edit a Snippet, you need to open it from the **Snippets** pane.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text=""代码段" 窗格" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   <span data-ttu-id="80f78-121">" **代码段** " 窗格</span><span class="sxs-lookup"><span data-stu-id="80f78-121">The **Snippets** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="80f78-122">使用鼠标打开 "代码段" 窗格</span><span class="sxs-lookup"><span data-stu-id="80f78-122">Open the Snippets pane with a mouse</span></span>   

1.  <span data-ttu-id="80f78-123">单击 " **源** " 选项卡以打开 " **源** " 面板。</span><span class="sxs-lookup"><span data-stu-id="80f78-123">Click the **Sources** tab to open the **Sources** panel.</span></span>  <span data-ttu-id="80f78-124">默认情况下， **页面** 窗格通常打开。</span><span class="sxs-lookup"><span data-stu-id="80f78-124">The **Page** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="在左侧打开页面窗格的 "源" 面板" lightbox="../media/javascript-sources-page-pane.msft.png":::
       <span data-ttu-id="80f78-126">在左侧打开**页面**窗格的 "**源**" 面板</span><span class="sxs-lookup"><span data-stu-id="80f78-126">The **Sources** panel with the **Page** pane open on the left</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="80f78-127">单击 " **代码段** " 选项卡以打开 " **代码段** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="80f78-127">Click the **Snippets** tab to open the **Snippets** pane.</span></span>  <span data-ttu-id="80f78-128">您可能需要单击 " **更多选项卡** \ (![ 更多选项卡 ][ImageMoreTabsIcon] \ ) " 才能访问 " **代码段** " 选项。</span><span class="sxs-lookup"><span data-stu-id="80f78-128">You might need to click **More Tabs** \(![More Tabs][ImageMoreTabsIcon]\) in order to access the **Snippets** option.</span></span>  
    
### <span data-ttu-id="80f78-129">通过 "命令" 菜单打开 "代码段" 窗格</span><span class="sxs-lookup"><span data-stu-id="80f78-129">Open the Snippets pane with the Command Menu</span></span>   

1.  <span data-ttu-id="80f78-130">将光标聚焦在 DevTools 内的某个位置。</span><span class="sxs-lookup"><span data-stu-id="80f78-130">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="80f78-131">按 `Control`+`Shift`+`P` \(Windows\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="80f78-131">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="80f78-132">开始键入 `Snippets` ，选择 " **显示代码段**"，然后按 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="80f78-132">Start typing `Snippets`, select **Show Snippets**, and then press `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text=""显示代码段" 命令" lightbox="../media/javascript-search-show-snippets.msft.png":::
       <span data-ttu-id="80f78-134">" **显示代码段** " 命令</span><span class="sxs-lookup"><span data-stu-id="80f78-134">The **Show Snippets** command</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="80f78-135">创建代码段</span><span class="sxs-lookup"><span data-stu-id="80f78-135">Create Snippets</span></span>   

### <span data-ttu-id="80f78-136">通过 "源" 面板创建代码段</span><span class="sxs-lookup"><span data-stu-id="80f78-136">Create a Snippet through the Sources panel</span></span>   

1.  <span data-ttu-id="80f78-137">[打开 " **代码段** " 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="80f78-137">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="80f78-138">单击 " **新建代码段**"。</span><span class="sxs-lookup"><span data-stu-id="80f78-138">Click **New snippet**.</span></span>  
1.  <span data-ttu-id="80f78-139">输入代码段的名称，然后按 " `Enter` 保存"。</span><span class="sxs-lookup"><span data-stu-id="80f78-139">Enter a name for your Snippet then press `Enter` to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="为代码段命名" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       <span data-ttu-id="80f78-141">为代码段命名</span><span class="sxs-lookup"><span data-stu-id="80f78-141">Name a Snippet</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="80f78-142">通过 "命令" 菜单创建代码段</span><span class="sxs-lookup"><span data-stu-id="80f78-142">Create a Snippet through the Command Menu</span></span>   

1.  <span data-ttu-id="80f78-143">将光标聚焦在 DevTools 内的某个位置。</span><span class="sxs-lookup"><span data-stu-id="80f78-143">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="80f78-144">按 `Control`+`Shift`+`P` \(Windows\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="80f78-144">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="80f78-145">开始键入 `Snippet` ，选择 " **创建新代码段**"，然后按 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="80f78-145">Start typing `Snippet`, select **Create new snippet**, then press `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="用于创建新代码段的命令" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       <span data-ttu-id="80f78-147">用于创建新代码段的命令</span><span class="sxs-lookup"><span data-stu-id="80f78-147">The command for creating a new Snippet</span></span>  
    :::image-end:::  
    
<span data-ttu-id="80f78-148">如果想要为新的代码段提供自定义名称，请参阅 [重命名代码段](#rename-snippets) 。</span><span class="sxs-lookup"><span data-stu-id="80f78-148">See [Rename Snippets](#rename-snippets) if you'd like to give your new Snippet a custom name.</span></span>  

## <span data-ttu-id="80f78-149">编辑代码段</span><span class="sxs-lookup"><span data-stu-id="80f78-149">Edit Snippets</span></span>   

1.  <span data-ttu-id="80f78-150">[打开 " **代码段** " 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="80f78-150">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="80f78-151">在 "代码 **段** " 窗格中，单击要编辑的代码段的名称，以便在 **代码编辑器**中将其打开。</span><span class="sxs-lookup"><span data-stu-id="80f78-151">In the **Snippets** pane click the name of the Snippet that you want to edit in order to open it in the **Code Editor**.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="代码编辑器" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       <span data-ttu-id="80f78-153">**代码编辑器**</span><span class="sxs-lookup"><span data-stu-id="80f78-153">The **Code Editor**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="80f78-154">使用 **代码编辑器** 将 JavaScript 添加到代码段。</span><span class="sxs-lookup"><span data-stu-id="80f78-154">Use the **Code Editor** to add JavaScript to your Snippet.</span></span>  
1.  <span data-ttu-id="80f78-155">当代码段名称旁边显示星号时，表示你有未保存的代码。</span><span class="sxs-lookup"><span data-stu-id="80f78-155">When an asterisk appears next to the name of your Snippet it means you have unsaved code.</span></span> <span data-ttu-id="80f78-156">按 `Control` + `S` \ (Windows \ ) 或 `Command` + `S` \ (macOS \ ) 保存。</span><span class="sxs-lookup"><span data-stu-id="80f78-156">Press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="代码段名称旁边的星号，指示未保存的代码" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       <span data-ttu-id="80f78-158">代码段名称旁边的星号，指示未保存的代码</span><span class="sxs-lookup"><span data-stu-id="80f78-158">An asterisk next to the Snippet name, which indicates unsaved code</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="80f78-159">运行代码段</span><span class="sxs-lookup"><span data-stu-id="80f78-159">Run Snippets</span></span>   

### <span data-ttu-id="80f78-160">从 "源" 面板运行代码段</span><span class="sxs-lookup"><span data-stu-id="80f78-160">Run a Snippet from the Sources panel</span></span>   

1.  <span data-ttu-id="80f78-161">[打开 " **代码段** " 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="80f78-161">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="80f78-162">单击要运行的代码段的名称。</span><span class="sxs-lookup"><span data-stu-id="80f78-162">Click the name of the Snippet that you want to run.</span></span>  <span data-ttu-id="80f78-163">代码段将在 **代码编辑器**中打开。</span><span class="sxs-lookup"><span data-stu-id="80f78-163">The Snippet opens in the **Code Editor**.</span></span>  
1.  <span data-ttu-id="80f78-164">单击 "**运行片段**\ (![ 运行代码段 ][ImageRunSnippetIcon] \ ) "，或按 `Control` + `Enter` \ (Windows \ ) 或 `Command` + `Enter` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="80f78-164">Click **Run Snippet** \(![Run Snippet][ImageRunSnippetIcon]\), or press `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\).</span></span>  
    
### <span data-ttu-id="80f78-165">使用 "命令" 菜单运行代码段</span><span class="sxs-lookup"><span data-stu-id="80f78-165">Run a Snippet with the Command Menu</span></span>   

1.  <span data-ttu-id="80f78-166">将光标聚焦在 DevTools 内的某个位置。</span><span class="sxs-lookup"><span data-stu-id="80f78-166">Focus your cursor somewhere inside of DevTools.</span></span>  
1.  <span data-ttu-id="80f78-167">按 `Control`+`Shift`+`P` \(Windows\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="80f78-167">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="80f78-168">删除 `>` 字符，然后键入一个字符，然后键入 `!` 要运行的代码段的名称。</span><span class="sxs-lookup"><span data-stu-id="80f78-168">Delete the `>` character and type the `!` character followed by the name of the Snippet that you want to run.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="从 "命令" 菜单运行代码段" lightbox="../media/javascript-search-run-command.msft.png":::
       <span data-ttu-id="80f78-170">从 "**命令" 菜单**运行代码段</span><span class="sxs-lookup"><span data-stu-id="80f78-170">Running a Snippet from the **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="80f78-171">按 `Enter` 运行代码段。</span><span class="sxs-lookup"><span data-stu-id="80f78-171">Press `Enter` to run the Snippet.</span></span>  

## <span data-ttu-id="80f78-172">重命名代码段</span><span class="sxs-lookup"><span data-stu-id="80f78-172">Rename Snippets</span></span>   

1.  <span data-ttu-id="80f78-173">[打开 " **代码段** " 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="80f78-173">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="80f78-174">右键单击代码段名称，然后选择 " **重命名**"。</span><span class="sxs-lookup"><span data-stu-id="80f78-174">Right-click the Snippet name and select **Rename**.</span></span>  
    
## <span data-ttu-id="80f78-175">删除代码段</span><span class="sxs-lookup"><span data-stu-id="80f78-175">Delete Snippets</span></span>   

1.  <span data-ttu-id="80f78-176">[打开 " **代码段** " 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="80f78-176">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="80f78-177">右键单击代码段名称，然后选择 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="80f78-177">Right-click the Snippet name and select **Remove**.</span></span>  
    
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
> <span data-ttu-id="80f78-182">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="80f78-182">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="80f78-183">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="80f78-183">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="80f78-185">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="80f78-185">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
