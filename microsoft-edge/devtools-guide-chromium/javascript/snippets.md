---
description: 代码片段是在 Microsoft Edge DevTools 的源工具中创作和运行的小型脚本。  可以通过任何网页访问和运行资源。  当你运行代码片段时，它是通过当前打开网页的上下文运行。
title: 使用 Microsoft Edge DevTools 在任何网页上运行 JavaScript 代码片段
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools
ms.openlocfilehash: 00c612a1573c7446711a2dc9d22985c83140eecd
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519427"
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

# <a name="run-snippets-of-javascript-on-any-webpage-with-microsoft-edge-devtools"></a><span data-ttu-id="ebd89-106">使用 Microsoft Edge DevTools 在任何网页上运行 JavaScript 代码片段</span><span class="sxs-lookup"><span data-stu-id="ebd89-106">Run snippets of JavaScript on any webpage with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="ebd89-107">如果在[控制台][DevtoolsConsoleIndex]中重复运行相同的代码，请考虑换成将代码另存为代码片段。</span><span class="sxs-lookup"><span data-stu-id="ebd89-107">If you are running the same code in the [Console][DevtoolsConsoleIndex] repeatedly, consider saving the code as a Snippet instead.</span></span>  <span data-ttu-id="ebd89-108">代码片段是在[源][DevToolsSourcesTool]工具中创作的脚本。</span><span class="sxs-lookup"><span data-stu-id="ebd89-108">Snippets are scripts that you author in the [Sources][DevToolsSourcesTool] tool.</span></span>  <span data-ttu-id="ebd89-109">代码片段有权访问网页的 JavaScript 上下文，并且可以在任何网页上运行代码片段。</span><span class="sxs-lookup"><span data-stu-id="ebd89-109">Snippets have access to the JavaScript context of the webpage, and you may run snippets on any webpage.</span></span>  <span data-ttu-id="ebd89-110">大多数网页的安全设置会阻止在代码片段中加载其他脚本。</span><span class="sxs-lookup"><span data-stu-id="ebd89-110">The security settings of most webpages block from loading other scripts in Snippets.</span></span>  <span data-ttu-id="ebd89-111">因此，必须将所有代码都包括在一个文件中。</span><span class="sxs-lookup"><span data-stu-id="ebd89-111">For that reason, you must include all your code in one file.</span></span>  

<span data-ttu-id="ebd89-112">代码片段可以替代[小书签][WikiBookmarklet]，区别在于代码片段仅在 DevTools 中运行，并且不受 URL 允许长度的限制。</span><span class="sxs-lookup"><span data-stu-id="ebd89-112">Snippets are an alternative to [bookmarklets][WikiBookmarklet] with the difference that Snippets only run in DevTools and are not limited to the allowed length of a URL.</span></span>  

<span data-ttu-id="ebd89-113">使用代码片段在第三方网页进行少许内容更改的绝佳方法。</span><span class="sxs-lookup"><span data-stu-id="ebd89-113">Using Snippets is an excellent way to change a few things in a third-party webpage.</span></span>  <span data-ttu-id="ebd89-114">将代码片段中的代码更改添加到当前网页，并在同一上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="ebd89-114">Code changes in Snippets are added to the current webpage and run in the same context.</span></span>  <span data-ttu-id="ebd89-115">有关更改网页现有代码的更多信息，请导航到[替代][DevtoolsJavascriptOverrides]。</span><span class="sxs-lookup"><span data-stu-id="ebd89-115">For more information about changing the existing code of a webpage, navigate to [Overrides][DevtoolsJavascriptOverrides].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="ebd89-116">例如，下图所示左侧为 DevTools 主页，右侧为一些代码片段源代码。</span><span class="sxs-lookup"><span data-stu-id="ebd89-116">For example, in the following figure shows the DevTools homepage on the left and some Snippet source code on the right.</span></span>  
      
      :::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="运行代码片段之前" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
         <span data-ttu-id="ebd89-118">运行代码片段之前的网页</span><span class="sxs-lookup"><span data-stu-id="ebd89-118">The webpage before running the Snippet</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="ebd89-119">运行代码片段之前网页的代码片段源代码。</span><span class="sxs-lookup"><span data-stu-id="ebd89-119">The Snippet source code from the webpage before running the Snippet.</span></span>  
      
      ```javascript
      console.log('Hello, Snippets!');
      document.body.innerHTML = '';
      var p = document.createElement('p');
      p.textContent = 'Hello, Snippets!';
      document.body.appendChild(p);
      ```
   :::column-end:::
:::row-end:::  

<span data-ttu-id="ebd89-120">下图所示为运行代码片段后出现的网页。</span><span class="sxs-lookup"><span data-stu-id="ebd89-120">In the following figure, the webpage appears after running the Snippet.</span></span>  <span data-ttu-id="ebd89-121">将弹出**控制台抽屉式选项卡**显示代码片段记录的 `Hello, Snippets!` 消息，并且网页的内容全部更改。</span><span class="sxs-lookup"><span data-stu-id="ebd89-121">The **Console Drawer** pops up to display the `Hello, Snippets!` message that the Snippet logs, and the content of the webpage changes completely.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="运行代码片段后的网页" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   <span data-ttu-id="ebd89-123">运行代码片段后的网页</span><span class="sxs-lookup"><span data-stu-id="ebd89-123">The webpage after running the Snippet</span></span>  
:::image-end:::  

## <a name="open-the-snippets-tab"></a><span data-ttu-id="ebd89-124">打开"代码段"选项卡</span><span class="sxs-lookup"><span data-stu-id="ebd89-124">Open the Snippets tab</span></span>  

<span data-ttu-id="ebd89-125">左侧**导航**器窗格中的"代码\*\*\*\* 段"选项卡列出了您的代码段。</span><span class="sxs-lookup"><span data-stu-id="ebd89-125">The **Snippets** tab, in the **Navigator** pane on the left, lists your Snippets.</span></span>  <span data-ttu-id="ebd89-126">当您要编辑代码段时，您需要从"代码段"选项卡 **中打开** 它。</span><span class="sxs-lookup"><span data-stu-id="ebd89-126">When you want to edit a Snippet, you need to open it from the **Snippets** tab.</span></span>  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text="代码段选项卡" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   <span data-ttu-id="ebd89-128">" **代码段"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="ebd89-128">The **Snippets** tab</span></span>  
:::image-end:::  

### <a name="open-the-snippets-tab-with-a-mouse"></a><span data-ttu-id="ebd89-129">用鼠标打开"代码段"选项卡</span><span class="sxs-lookup"><span data-stu-id="ebd89-129">Open the Snippets tab with a mouse</span></span>  

1.  <span data-ttu-id="ebd89-130">选择" **源"** 选项卡。 将显示 **"源** "工具。</span><span class="sxs-lookup"><span data-stu-id="ebd89-130">Choose the **Sources** tab.  The **Sources** tool appears.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="在左侧打开页面选项卡的源工具" lightbox="../media/javascript-sources-page-pane.msft.png":::
       <span data-ttu-id="ebd89-132">在 **左侧** 打开" **页面"** 选项卡的"源"工具</span><span class="sxs-lookup"><span data-stu-id="ebd89-132">The **Sources** tool with the **Page** tab open on the left</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ebd89-133">在左侧 **导航器** (窗格中，) 代码 **段"** 选项卡。 若要访问 **代码段** 选项，你可能需要选择更多 **选项卡** \ (![ 更多选项卡 ](../media/more-tabs-icon.msft.png) \) 。</span><span class="sxs-lookup"><span data-stu-id="ebd89-133">In the **Navigator** pane (on the left), choose the **Snippets** tab.  To access the **Snippets** option, you may need to choose **More tabs** \(![More tabs](../media/more-tabs-icon.msft.png)\).</span></span>  
    
### <a name="open-the-snippets-tab-with-the-command-menu"></a><span data-ttu-id="ebd89-134">使用命令菜单打开"代码段"选项卡</span><span class="sxs-lookup"><span data-stu-id="ebd89-134">Open the Snippets tab with the Command Menu</span></span>  

1.  <span data-ttu-id="ebd89-135">在 DevTools 中选择任何内容，以便 DevTools 具有焦点。</span><span class="sxs-lookup"><span data-stu-id="ebd89-135">Select anything in DevTools, so that DevTools has focus.</span></span>  
1.  <span data-ttu-id="ebd89-136">选择 `Control`+`Shift`+`P` \(Windows, Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="ebd89-136">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="ebd89-137">键入 `Snippets`，选择**显示代码片段**，然后选择 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="ebd89-137">Type `Snippets`, choose **Show Snippets**, and then select `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text="显示代码片段命令" lightbox="../media/javascript-search-show-snippets.msft.png":::
       <span data-ttu-id="ebd89-139">**显示代码片段**命令</span><span class="sxs-lookup"><span data-stu-id="ebd89-139">The **Show Snippets** command</span></span>  
    :::image-end:::  
    
## <a name="create-snippets"></a><span data-ttu-id="ebd89-140">创建代码片段</span><span class="sxs-lookup"><span data-stu-id="ebd89-140">Create Snippets</span></span>  

### <a name="create-a-snippet-through-the-sources-tool"></a><span data-ttu-id="ebd89-141">通过"源"工具创建代码段</span><span class="sxs-lookup"><span data-stu-id="ebd89-141">Create a Snippet through the Sources tool</span></span>  

1.  <span data-ttu-id="ebd89-142">[打开"代码段"选项卡](#open-the-snippets-tab)。</span><span class="sxs-lookup"><span data-stu-id="ebd89-142">[Open the Snippets tab](#open-the-snippets-tab).</span></span>  
1.  <span data-ttu-id="ebd89-143">选择“**新建代码片段**”。</span><span class="sxs-lookup"><span data-stu-id="ebd89-143">Choose **New snippet**.</span></span>  
1.  <span data-ttu-id="ebd89-144">输入代码段的名称，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="ebd89-144">Enter a name for your Snippet, and then select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="为代码片段命名" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       <span data-ttu-id="ebd89-146">为代码片段命名</span><span class="sxs-lookup"><span data-stu-id="ebd89-146">Name a Snippet</span></span>  
    :::image-end:::  
    
### <a name="create-a-snippet-through-the-command-menu"></a><span data-ttu-id="ebd89-147">通过命令菜单创建代码片段</span><span class="sxs-lookup"><span data-stu-id="ebd89-147">Create a Snippet through the Command Menu</span></span>  

1.  <span data-ttu-id="ebd89-148">将光标停在 DevTools 中的任一位置。</span><span class="sxs-lookup"><span data-stu-id="ebd89-148">Focus your cursor somewhere in DevTools.</span></span>  
1.  <span data-ttu-id="ebd89-149">选择 `Control`+`Shift`+`P` \(Windows, Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="ebd89-149">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="ebd89-150">键入 `Snippet`，选 **新建代码片段**，然后选择 `Enter` 运行命令。</span><span class="sxs-lookup"><span data-stu-id="ebd89-150">Type `Snippet`, choose **Create new snippet**, then select `Enter` to run the command.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="用于新建代码片段的命令" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       <span data-ttu-id="ebd89-152">用于新建代码片段的命令</span><span class="sxs-lookup"><span data-stu-id="ebd89-152">The command for creating a new Snippet</span></span>  
    :::image-end:::  
    
<span data-ttu-id="ebd89-153">若要使用自定义名称重命名新代码片段，请导航到[重命名代码片段](#rename-snippets)。</span><span class="sxs-lookup"><span data-stu-id="ebd89-153">To rename your new Snippet with a custom name, navigate to [Rename Snippets](#rename-snippets).</span></span>  

## <a name="edit-snippets"></a><span data-ttu-id="ebd89-154">编辑代码片段</span><span class="sxs-lookup"><span data-stu-id="ebd89-154">Edit Snippets</span></span>  

1.  <span data-ttu-id="ebd89-155">[打开"代码段"选项卡](#open-the-snippets-tab)。</span><span class="sxs-lookup"><span data-stu-id="ebd89-155">[Open the Snippets tab](#open-the-snippets-tab).</span></span>  
1.  <span data-ttu-id="ebd89-156">在 **"代码段** "选项卡中，选择要编辑的代码段的名称。</span><span class="sxs-lookup"><span data-stu-id="ebd89-156">In the **Snippets** tab, choose the name of the Snippet that you want to edit.</span></span>  <span data-ttu-id="ebd89-157">它将在**代码编辑器**中打开。</span><span class="sxs-lookup"><span data-stu-id="ebd89-157">It opens in the **Code Editor**.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="代码编辑器" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       <span data-ttu-id="ebd89-159">代码**编辑器**</span><span class="sxs-lookup"><span data-stu-id="ebd89-159">The **Code Editor**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ebd89-160">使用**代码编辑器**将 JavaScript 添加到代码片段。</span><span class="sxs-lookup"><span data-stu-id="ebd89-160">Use the **Code Editor** to add JavaScript to your Snippet.</span></span>  
1.  <span data-ttu-id="ebd89-161">当代码片段名称旁边出现星号时，表示有代码未保存。</span><span class="sxs-lookup"><span data-stu-id="ebd89-161">When an asterisk appears next to the name of your Snippet, it means you have unsaved code.</span></span>  <span data-ttu-id="ebd89-162">选择 `Control`+`S` \(Windows, Linux\) 或 `Command`+`S` \(macOS\) 进行保存。</span><span class="sxs-lookup"><span data-stu-id="ebd89-162">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save.</span></span>  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="代码片段名称旁边显示星号表示代码未保存" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       <span data-ttu-id="ebd89-164">代码片段名称旁边显示星号表示代码未保存</span><span class="sxs-lookup"><span data-stu-id="ebd89-164">An asterisk next to the Snippet name indicates unsaved code</span></span>  
    :::image-end:::  
    
## <a name="run-snippets"></a><span data-ttu-id="ebd89-165">运行代码片段</span><span class="sxs-lookup"><span data-stu-id="ebd89-165">Run Snippets</span></span>  

### <a name="run-a-snippet-from-the-sources-tool"></a><span data-ttu-id="ebd89-166">从源工具运行代码段</span><span class="sxs-lookup"><span data-stu-id="ebd89-166">Run a Snippet from the Sources tool</span></span>  

1.  <span data-ttu-id="ebd89-167">[打开"代码段"选项卡](#open-the-snippets-tab)。</span><span class="sxs-lookup"><span data-stu-id="ebd89-167">[Open the Snippets tab](#open-the-snippets-tab).</span></span>  
1.  <span data-ttu-id="ebd89-168">选择要运行的代码片段的名称。</span><span class="sxs-lookup"><span data-stu-id="ebd89-168">Choose the name of the Snippet that you want to run.</span></span>  <span data-ttu-id="ebd89-169">代码片段将在**代码编辑器**中打开。</span><span class="sxs-lookup"><span data-stu-id="ebd89-169">The Snippet opens in the **Code Editor**.</span></span>  
1.  <span data-ttu-id="ebd89-170">Choose **Run snippet** \ (Run Snippet ![ ](../media/run-snippet-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="ebd89-170">Choose **Run snippet** \(![Run Snippet](../media/run-snippet-icon.msft.png)\).</span></span>
    
### <a name="run-a-snippet-with-the-command-menu"></a><span data-ttu-id="ebd89-171">使用命令菜单运行代码片段</span><span class="sxs-lookup"><span data-stu-id="ebd89-171">Run a Snippet with the Command Menu</span></span>  

1.  <span data-ttu-id="ebd89-172">将光标停在 DevTools 中的任一位置。</span><span class="sxs-lookup"><span data-stu-id="ebd89-172">Focus your cursor somewhere in DevTools.</span></span>  
1.  <span data-ttu-id="ebd89-173">选择 `Control`+`Shift`+`P` \(Windows, Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="ebd89-173">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="ebd89-174">删除 `>` 字符并在要运行的代码片段名称后键入 `!` 字符。</span><span class="sxs-lookup"><span data-stu-id="ebd89-174">Delete the `>` character and type the `!` character followed by the name of the Snippet that you want to run.</span></span>  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="使用命令菜单运行代码片段" lightbox="../media/javascript-search-run-command.msft.png":::
       <span data-ttu-id="ebd89-176">使用命令菜单运行**代码片段**</span><span class="sxs-lookup"><span data-stu-id="ebd89-176">Running a Snippet from the **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ebd89-177">选择 `Enter` 运行代码片段。</span><span class="sxs-lookup"><span data-stu-id="ebd89-177">Select `Enter` to run the Snippet.</span></span>  

## <a name="rename-snippets"></a><span data-ttu-id="ebd89-178">重命名代码片段</span><span class="sxs-lookup"><span data-stu-id="ebd89-178">Rename Snippets</span></span>  

1.  <span data-ttu-id="ebd89-179">[打开"代码段"选项卡](#open-the-snippets-tab)。</span><span class="sxs-lookup"><span data-stu-id="ebd89-179">[Open the Snippets tab](#open-the-snippets-tab).</span></span>  
1.  <span data-ttu-id="ebd89-180">将鼠标悬停在代码片段名称上，打开上下文菜单\（右键单击\），然后选择**重命名**。</span><span class="sxs-lookup"><span data-stu-id="ebd89-180">Hover on the Snippet name, open the contextual menu \(right-click\), and choose **Rename**.</span></span>  
    
## <a name="delete-snippets"></a><span data-ttu-id="ebd89-181">删除代码片段</span><span class="sxs-lookup"><span data-stu-id="ebd89-181">Delete Snippets</span></span>  

1.  <span data-ttu-id="ebd89-182">[打开"代码段"选项卡](#open-the-snippets-tab)。</span><span class="sxs-lookup"><span data-stu-id="ebd89-182">[Open the Snippets tab](#open-the-snippets-tab).</span></span>  
1.  <span data-ttu-id="ebd89-183">将鼠标悬停在代码片段名称上，打开上下文菜单\（右键单击\），然后选择**删除**。</span><span class="sxs-lookup"><span data-stu-id="ebd89-183">Hover on the Snippet name, open the contextual menu \(right-click\), and choose **Remove**.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="ebd89-184">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="ebd89-184">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "控制台概述 | Microsoft Docs"  
[DevToolsSourcesTool]: ../sources/index.md "源工具概述 | Microsoft Docs"  
[DevtoolsJavascriptOverrides]: ./overrides.md "替代 | Microsoft Docs"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "Scratchpad | MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "小书签 | Wikipedia"  

> [!NOTE]
> <span data-ttu-id="ebd89-190">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="ebd89-190">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ebd89-191">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="ebd89-191">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="ebd89-193">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="ebd89-193">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
