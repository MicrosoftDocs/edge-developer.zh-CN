---
description: 代码段是一些小型脚本，您可以在 Microsoft Edge DevTools 的源工具中创作和运行。  你可以从任何网页访问和运行资源。  运行代码段时，代码段从当前打开的网页的上下文中运行。
title: 使用 Microsoft Edge DevTools 在任何页面上运行 JavaScript 代码段
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 89b028177016a9194a67bbbe44d08572e5755f95
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230955"
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

# <span data-ttu-id="1d84f-106">使用 Microsoft Edge DevTools 在任何网页上运行 JavaScript 代码段</span><span class="sxs-lookup"><span data-stu-id="1d84f-106">Run snippets of JavaScript on any webpage with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="1d84f-107">如果在控制台中重复运行相同的代码，请考虑[][DevtoolsConsoleIndex]将代码保存为代码段。</span><span class="sxs-lookup"><span data-stu-id="1d84f-107">If you are running the same code in the [Console][DevtoolsConsoleIndex] repeatedly, consider saving the code as a Snippet instead.</span></span>  <span data-ttu-id="1d84f-108">代码段是你在源工具中 [创作的][DevToolsSourcesTool] 脚本。</span><span class="sxs-lookup"><span data-stu-id="1d84f-108">Snippets are scripts that you author in the [Sources][DevToolsSourcesTool] tool.</span></span>  <span data-ttu-id="1d84f-109">代码段有权访问网页的 JavaScript 上下文，并且您可以在任何网页上运行代码段。</span><span class="sxs-lookup"><span data-stu-id="1d84f-109">Snippets have access to the JavaScript context of the webpage, and you may run snippets on any webpage.</span></span>  <span data-ttu-id="1d84f-110">大多数网页的安全设置阻止在代码段中加载其他脚本。</span><span class="sxs-lookup"><span data-stu-id="1d84f-110">The security settings of most webpages block from loading other scripts in Snippets.</span></span>  <span data-ttu-id="1d84f-111">因此，必须将所有代码都包括在一个文件中。</span><span class="sxs-lookup"><span data-stu-id="1d84f-111">For that reason, you must include all your code in one file.</span></span>  

<span data-ttu-id="1d84f-112">代码段是 [bookmarklet][WikiBookmarklet] 的替代方法，区别在于代码段仅在 DevTools 中运行，且不限于 URL 的允许长度。</span><span class="sxs-lookup"><span data-stu-id="1d84f-112">Snippets are an alternative to [bookmarklets][WikiBookmarklet] with the difference that Snippets only run in DevTools and are not limited to the allowed length of a URL.</span></span>  

<span data-ttu-id="1d84f-113">使用代码段是更改第三方网页中的一些内容很好的方法。</span><span class="sxs-lookup"><span data-stu-id="1d84f-113">Using Snippets is an excellent way to change a few things in a third-party webpage.</span></span>  <span data-ttu-id="1d84f-114">代码段中的代码更改将添加到当前网页，并在同一上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="1d84f-114">Code changes in Snippets are added to the current webpage and run in the same context.</span></span>  <span data-ttu-id="1d84f-115">有关更改网页的现有代码的信息，请导航到["替代"。][DevtoolsJavascriptOverrides]</span><span class="sxs-lookup"><span data-stu-id="1d84f-115">For more information about changing the existing code of a webpage, navigate to [Overrides][DevtoolsJavascriptOverrides].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1d84f-116">例如，下图显示了左侧的 DevTools 主页，右侧显示了一些代码段源代码。</span><span class="sxs-lookup"><span data-stu-id="1d84f-116">For example, in the following figure shows the DevTools homepage on the left and some Snippet source code on the right.</span></span>  
      
      :::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="运行代码段之前" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
         <span data-ttu-id="1d84f-118">运行代码段之前的网页</span><span class="sxs-lookup"><span data-stu-id="1d84f-118">The webpage before running the Snippet</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="1d84f-119">运行代码段之前，网页中的代码段源代码。</span><span class="sxs-lookup"><span data-stu-id="1d84f-119">The Snippet source code from the webpage before running the Snippet.</span></span>  
      
      ```javascript
      console.log('Hello, Snippets!');
      document.body.innerHTML = '';
      var p = document.createElement('p');
      p.textContent = 'Hello, Snippets!';
      document.body.appendChild(p);
      ```
   :::column-end:::
:::row-end:::  

<span data-ttu-id="1d84f-120">在下图中，网页在运行代码段后显示。</span><span class="sxs-lookup"><span data-stu-id="1d84f-120">In the following figure, the webpage appears after running the Snippet.</span></span>  <span data-ttu-id="1d84f-121">控制台 **箱** 弹出以显示代码段记录的消息，网页 `Hello, Snippets!` 内容完全更改。</span><span class="sxs-lookup"><span data-stu-id="1d84f-121">The **Console Drawer** pops up to display the `Hello, Snippets!` message that the Snippet logs, and the content of the webpage changes completely.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="运行代码段后的网页" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   <span data-ttu-id="1d84f-123">运行代码段后的网页</span><span class="sxs-lookup"><span data-stu-id="1d84f-123">The webpage after running the Snippet</span></span>  
:::image-end:::  

## <span data-ttu-id="1d84f-124">打开代码段窗格</span><span class="sxs-lookup"><span data-stu-id="1d84f-124">Open the Snippets pane</span></span>  

<span data-ttu-id="1d84f-125">代码 **段** 窗格列出了代码段。</span><span class="sxs-lookup"><span data-stu-id="1d84f-125">The **Snippets** pane lists your Snippets.</span></span>  <span data-ttu-id="1d84f-126">当您要编辑代码段时，您需要从代码段窗格中 **打开** 它。</span><span class="sxs-lookup"><span data-stu-id="1d84f-126">When you want to edit a Snippet, you need to open it from the **Snippets** pane.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text="代码段窗格" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   <span data-ttu-id="1d84f-128">代码 **段** 窗格</span><span class="sxs-lookup"><span data-stu-id="1d84f-128">The **Snippets** pane</span></span>  
:::image-end:::  

### <span data-ttu-id="1d84f-129">使用鼠标打开代码段窗格</span><span class="sxs-lookup"><span data-stu-id="1d84f-129">Open the Snippets pane with a mouse</span></span>  

1.  <span data-ttu-id="1d84f-130">选择" **源"** 选项卡以打开 **"源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="1d84f-130">Choose the **Sources** tab to open the **Sources** tool.</span></span>  <span data-ttu-id="1d84f-131">默认情况下 **，"** 页面"窗格通常打开。</span><span class="sxs-lookup"><span data-stu-id="1d84f-131">The **Page** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="左侧打开"页面"窗格的"源"工具" lightbox="../media/javascript-sources-page-pane.msft.png":::
       <span data-ttu-id="1d84f-133">左侧 **打开** "页面" **窗格** 的"源"工具</span><span class="sxs-lookup"><span data-stu-id="1d84f-133">The **Sources** tool with the **Page** pane open on the left</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1d84f-134">选择 **"代码段"** 选项卡以打开 **"代码段"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="1d84f-134">Choose the **Snippets** tab to open the **Snippets** pane.</span></span>  <span data-ttu-id="1d84f-135">你可能需要选择"更多**选项卡**"\ ("选项卡 ![ ][ImageMoreTabsIcon] ") "代码段"选项。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1d84f-135">You may need to choose **More Tabs** \(![More Tabs][ImageMoreTabsIcon]\) to access the **Snippets** option.</span></span>  
    
### <span data-ttu-id="1d84f-136">使用命令菜单打开代码段窗格</span><span class="sxs-lookup"><span data-stu-id="1d84f-136">Open the Snippets pane with the Command Menu</span></span>  

1.  <span data-ttu-id="1d84f-137">将光标焦点放在 DevTools 中的某一位置。</span><span class="sxs-lookup"><span data-stu-id="1d84f-137">Focus your cursor somewhere in DevTools.</span></span>  
1.  <span data-ttu-id="1d84f-138">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="1d84f-138">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="1d84f-139">键入 `Snippets` ， **选择"显示**代码段"，然后选择 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="1d84f-139">Type `Snippets`, choose **Show Snippets**, and then select `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text=""显示代码段"命令" lightbox="../media/javascript-search-show-snippets.msft.png":::
       <span data-ttu-id="1d84f-141">" **显示代码段"** 命令</span><span class="sxs-lookup"><span data-stu-id="1d84f-141">The **Show Snippets** command</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="1d84f-142">创建代码段</span><span class="sxs-lookup"><span data-stu-id="1d84f-142">Create Snippets</span></span>  

### <span data-ttu-id="1d84f-143">通过"源"面板创建代码段</span><span class="sxs-lookup"><span data-stu-id="1d84f-143">Create a Snippet through the Sources panel</span></span>  

1.  <span data-ttu-id="1d84f-144">[打开 **代码段** 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="1d84f-144">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="1d84f-145">选择 **"新建代码段"。**</span><span class="sxs-lookup"><span data-stu-id="1d84f-145">Choose **New snippet**.</span></span>  
1.  <span data-ttu-id="1d84f-146">输入代码段的名称，然后选择 `Enter` 保存。</span><span class="sxs-lookup"><span data-stu-id="1d84f-146">Enter a name for your Snippet then select `Enter` to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="命名代码段" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       <span data-ttu-id="1d84f-148">命名代码段</span><span class="sxs-lookup"><span data-stu-id="1d84f-148">Name a Snippet</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="1d84f-149">通过命令菜单创建代码段</span><span class="sxs-lookup"><span data-stu-id="1d84f-149">Create a Snippet through the Command Menu</span></span>  

1.  <span data-ttu-id="1d84f-150">将光标焦点放在 DevTools 中的某一位置。</span><span class="sxs-lookup"><span data-stu-id="1d84f-150">Focus your cursor somewhere in DevTools.</span></span>  
1.  <span data-ttu-id="1d84f-151">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="1d84f-151">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="1d84f-152">键入 `Snippet` ，选择 **"创建新代码段**"，然后选择 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="1d84f-152">Type `Snippet`, choose **Create new snippet**, then select `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="用于创建新代码段的命令" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       <span data-ttu-id="1d84f-154">用于创建新代码段的命令</span><span class="sxs-lookup"><span data-stu-id="1d84f-154">The command for creating a new Snippet</span></span>  
    :::image-end:::  
    
<span data-ttu-id="1d84f-155">若要使用自定义名称重命名新代码段，请导航到["重命名代码段"。](#rename-snippets)</span><span class="sxs-lookup"><span data-stu-id="1d84f-155">To rename your new Snippet with a custom name, navigate to [Rename Snippets](#rename-snippets).</span></span>  

## <span data-ttu-id="1d84f-156">编辑代码段</span><span class="sxs-lookup"><span data-stu-id="1d84f-156">Edit Snippets</span></span>  

1.  <span data-ttu-id="1d84f-157">[打开 **代码段** 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="1d84f-157">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="1d84f-158">在 **"代码** 段"窗格中，选择要编辑的代码段的名称。</span><span class="sxs-lookup"><span data-stu-id="1d84f-158">In the **Snippets** pane, choose the name of the Snippet that you want to edit.</span></span>  <span data-ttu-id="1d84f-159">它将在代码 **编辑器中打开**。</span><span class="sxs-lookup"><span data-stu-id="1d84f-159">It opens in the **Code Editor**.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="代码编辑器" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       <span data-ttu-id="1d84f-161">代码 **编辑器**</span><span class="sxs-lookup"><span data-stu-id="1d84f-161">The **Code Editor**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1d84f-162">使用 **代码编辑器** 将 JavaScript 添加到代码段。</span><span class="sxs-lookup"><span data-stu-id="1d84f-162">Use the **Code Editor** to add JavaScript to your Snippet.</span></span>  
1.  <span data-ttu-id="1d84f-163">当代码段名称旁边出现星号时，这意味着您具有未保存的代码。</span><span class="sxs-lookup"><span data-stu-id="1d84f-163">When an asterisk appears next to the name of your Snippet, it means you have unsaved code.</span></span>  <span data-ttu-id="1d84f-164">选择 `Control` + `S` \ (Windows、Linux\) 或 `Command` + `S` \ (macOS\) 保存。</span><span class="sxs-lookup"><span data-stu-id="1d84f-164">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="代码段名称旁边的星号指示未保存的代码" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       <span data-ttu-id="1d84f-166">代码段名称旁边的星号指示未保存的代码</span><span class="sxs-lookup"><span data-stu-id="1d84f-166">An asterisk next to the Snippet name indicates unsaved code</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="1d84f-167">运行代码段</span><span class="sxs-lookup"><span data-stu-id="1d84f-167">Run Snippets</span></span>  

### <span data-ttu-id="1d84f-168">从"源"面板运行代码段</span><span class="sxs-lookup"><span data-stu-id="1d84f-168">Run a Snippet from the Sources panel</span></span>  

1.  <span data-ttu-id="1d84f-169">[打开 **代码段** 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="1d84f-169">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="1d84f-170">选择要运行的代码段的名称。</span><span class="sxs-lookup"><span data-stu-id="1d84f-170">Choose the name of the Snippet that you want to run.</span></span>  <span data-ttu-id="1d84f-171">代码段将在代码 **编辑器中打开**。</span><span class="sxs-lookup"><span data-stu-id="1d84f-171">The Snippet opens in the **Code Editor**.</span></span>  
1.  <span data-ttu-id="1d84f-172">Choose **Run Snippet** \ (Run Snippet ![ ][ImageRunSnippetIcon] \) ， or select `Control` + `Enter` \ (Windows， Linux\) or `Command` + `Enter` \ (macOS\) .</span><span class="sxs-lookup"><span data-stu-id="1d84f-172">Choose **Run Snippet** \(![Run Snippet][ImageRunSnippetIcon]\), or select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\).</span></span>  
    
### <span data-ttu-id="1d84f-173">使用命令菜单运行代码段</span><span class="sxs-lookup"><span data-stu-id="1d84f-173">Run a Snippet with the Command Menu</span></span>  

1.  <span data-ttu-id="1d84f-174">将光标焦点放在 DevTools 中的某一位置。</span><span class="sxs-lookup"><span data-stu-id="1d84f-174">Focus your cursor somewhere in DevTools.</span></span>  
1.  <span data-ttu-id="1d84f-175">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="1d84f-175">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="1d84f-176">删除 `>` 字符并键入后跟要运行 `!` 的代码段的名称的字符。</span><span class="sxs-lookup"><span data-stu-id="1d84f-176">Delete the `>` character and type the `!` character followed by the name of the Snippet that you want to run.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="从命令菜单运行代码段" lightbox="../media/javascript-search-run-command.msft.png":::
       <span data-ttu-id="1d84f-178">从命令菜单 **运行代码段**</span><span class="sxs-lookup"><span data-stu-id="1d84f-178">Running a Snippet from the **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1d84f-179">选择 `Enter` 以运行代码段。</span><span class="sxs-lookup"><span data-stu-id="1d84f-179">Select `Enter` to run the Snippet.</span></span>  

## <span data-ttu-id="1d84f-180">重命名代码段</span><span class="sxs-lookup"><span data-stu-id="1d84f-180">Rename Snippets</span></span>  

1.  <span data-ttu-id="1d84f-181">[打开 **代码段** 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="1d84f-181">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="1d84f-182">将鼠标悬停在代码段名称上，打开上下文菜单 \ (右键单击\) ，然后选择"重命名 **"。**</span><span class="sxs-lookup"><span data-stu-id="1d84f-182">Hover on the Snippet name, open the contextual menu \(right-click\), and choose **Rename**.</span></span>  
    
## <span data-ttu-id="1d84f-183">删除代码段</span><span class="sxs-lookup"><span data-stu-id="1d84f-183">Delete Snippets</span></span>  

1.  <span data-ttu-id="1d84f-184">[打开 **代码段** 窗格](#open-the-snippets-pane)。</span><span class="sxs-lookup"><span data-stu-id="1d84f-184">[Open the **Snippets** pane](#open-the-snippets-pane).</span></span>  
1.  <span data-ttu-id="1d84f-185">将鼠标悬停在代码段名称上，打开上下文菜单 \ (右键单击\) ，然后选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="1d84f-185">Hover on the Snippet name, open the contextual menu \(right-click\), and choose **Remove**.</span></span>  
    
## <span data-ttu-id="1d84f-186">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="1d84f-186">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  
[ImageRunSnippetIcon]: ../media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "控制台概述 |Microsoft Docs"  
[DevToolsSourcesTool]: ../sources/index.md "源工具概述 |Microsoft Docs"  
[DevtoolsJavascriptOverrides]: ./overrides.md "替代 |Microsoft Docs"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "Scratchpad |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet |Wikipedia"  

> [!NOTE]
> <span data-ttu-id="1d84f-192">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="1d84f-192">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1d84f-193">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="1d84f-193">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="1d84f-195">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="1d84f-195">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
