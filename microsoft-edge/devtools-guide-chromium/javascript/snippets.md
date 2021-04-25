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

# <a name="run-snippets-of-javascript-on-any-webpage-with-microsoft-edge-devtools"></a>使用 Microsoft Edge DevTools 在任何网页上运行 JavaScript 代码片段  

如果在[控制台][DevtoolsConsoleIndex]中重复运行相同的代码，请考虑换成将代码另存为代码片段。  代码片段是在[源][DevToolsSourcesTool]工具中创作的脚本。  代码片段有权访问网页的 JavaScript 上下文，并且可以在任何网页上运行代码片段。  大多数网页的安全设置会阻止在代码片段中加载其他脚本。  因此，必须将所有代码都包括在一个文件中。  

代码片段可以替代[小书签][WikiBookmarklet]，区别在于代码片段仅在 DevTools 中运行，并且不受 URL 允许长度的限制。  

使用代码片段在第三方网页进行少许内容更改的绝佳方法。  将代码片段中的代码更改添加到当前网页，并在同一上下文中运行。  有关更改网页现有代码的更多信息，请导航到[替代][DevtoolsJavascriptOverrides]。  

:::row:::
   :::column span="":::
      例如，下图所示左侧为 DevTools 主页，右侧为一些代码片段源代码。  
      
      :::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="运行代码片段之前" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
         运行代码片段之前的网页  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      运行代码片段之前网页的代码片段源代码。  
      
      ```javascript
      console.log('Hello, Snippets!');
      document.body.innerHTML = '';
      var p = document.createElement('p');
      p.textContent = 'Hello, Snippets!';
      document.body.appendChild(p);
      ```
   :::column-end:::
:::row-end:::  

下图所示为运行代码片段后出现的网页。  将弹出**控制台抽屉式选项卡**显示代码片段记录的 `Hello, Snippets!` 消息，并且网页的内容全部更改。  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="运行代码片段后的网页" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   运行代码片段后的网页  
:::image-end:::  

## <a name="open-the-snippets-tab"></a>打开"代码段"选项卡  

左侧**导航**器窗格中的"代码**** 段"选项卡列出了您的代码段。  当您要编辑代码段时，您需要从"代码段"选项卡 **中打开** 它。  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text=""代码段"选项卡" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   " **代码段"** 选项卡  
:::image-end:::  

### <a name="open-the-snippets-tab-with-a-mouse"></a>用鼠标打开"代码段"选项卡  

1.  选择" **源"** 选项卡。 将显示 **"源** "工具。  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="在左侧打开"页面"选项卡的"源"工具" lightbox="../media/javascript-sources-page-pane.msft.png":::
       在 **左侧** 打开" **页面"** 选项卡的"源"工具  
    :::image-end:::  
    
1.  在左侧 **导航器** (窗格中，) 代码 **段"** 选项卡。 若要访问 **代码段** 选项，你可能需要选择更多 **选项卡** \ (![ 更多选项卡 ](../media/more-tabs-icon.msft.png) \) 。  
    
### <a name="open-the-snippets-tab-with-the-command-menu"></a>使用命令菜单打开"代码段"选项卡  

1.  在 DevTools 中选择任何内容，以便 DevTools 具有焦点。  
1.  选择 `Control`+`Shift`+`P` \(Windows, Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。  
1.  键入 `Snippets`，选择**显示代码片段**，然后选择 `Enter` 运行命令。  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text="显示代码片段命令" lightbox="../media/javascript-search-show-snippets.msft.png":::
       **显示代码片段**命令  
    :::image-end:::  
    
## <a name="create-snippets"></a>创建代码片段  

### <a name="create-a-snippet-through-the-sources-tool"></a>通过"源"工具创建代码段  

1.  [打开"代码段"选项卡](#open-the-snippets-tab)。  
1.  选择“**新建代码片段**”。  
1.  输入代码段的名称，然后选择 `Enter` 。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="为代码片段命名" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       为代码片段命名  
    :::image-end:::  
    
### <a name="create-a-snippet-through-the-command-menu"></a>通过命令菜单创建代码片段  

1.  将光标停在 DevTools 中的任一位置。  
1.  选择 `Control`+`Shift`+`P` \(Windows, Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。  
1.  键入 `Snippet`，选 **新建代码片段**，然后选择 `Enter` 运行命令。  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="用于新建代码片段的命令" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       用于新建代码片段的命令  
    :::image-end:::  
    
若要使用自定义名称重命名新代码片段，请导航到[重命名代码片段](#rename-snippets)。  

## <a name="edit-snippets"></a>编辑代码片段  

1.  [打开"代码段"选项卡](#open-the-snippets-tab)。  
1.  在 **"代码段** "选项卡中，选择要编辑的代码段的名称。  它将在**代码编辑器**中打开。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="代码编辑器" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       代码**编辑器**  
    :::image-end:::  
    
1.  使用**代码编辑器**将 JavaScript 添加到代码片段。  
1.  当代码片段名称旁边出现星号时，表示有代码未保存。  选择 `Control`+`S` \(Windows, Linux\) 或 `Command`+`S` \(macOS\) 进行保存。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="代码片段名称旁边显示星号表示代码未保存" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       代码片段名称旁边显示星号表示代码未保存  
    :::image-end:::  
    
## <a name="run-snippets"></a>运行代码片段  

### <a name="run-a-snippet-from-the-sources-tool"></a>从源工具运行代码段  

1.  [打开"代码段"选项卡](#open-the-snippets-tab)。  
1.  选择要运行的代码片段的名称。  代码片段将在**代码编辑器**中打开。  
1.  Choose **Run snippet** \ (Run Snippet ![ ](../media/run-snippet-icon.msft.png) \) .
    
### <a name="run-a-snippet-with-the-command-menu"></a>使用命令菜单运行代码片段  

1.  将光标停在 DevTools 中的任一位置。  
1.  选择 `Control`+`Shift`+`P` \(Windows, Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。  
1.  删除 `>` 字符并在要运行的代码片段名称后键入 `!` 字符。  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="使用命令菜单运行代码片段" lightbox="../media/javascript-search-run-command.msft.png":::
       使用命令菜单运行**代码片段**  
    :::image-end:::  
    
1.  选择 `Enter` 运行代码片段。  

## <a name="rename-snippets"></a>重命名代码片段  

1.  [打开"代码段"选项卡](#open-the-snippets-tab)。  
1.  将鼠标悬停在代码片段名称上，打开上下文菜单\（右键单击\），然后选择**重命名**。  
    
## <a name="delete-snippets"></a>删除代码片段  

1.  [打开"代码段"选项卡](#open-the-snippets-tab)。  
1.  将鼠标悬停在代码片段名称上，打开上下文菜单\（右键单击\），然后选择**删除**。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "控制台概述 | Microsoft Docs"  
[DevToolsSourcesTool]: ../sources/index.md "源工具概述 | Microsoft Docs"  
[DevtoolsJavascriptOverrides]: ./overrides.md "替代 | Microsoft Docs"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "Scratchpad | MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "小书签 | Wikipedia"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
