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

# 使用 Microsoft Edge DevTools 在任何网页上运行 JavaScript 代码段  

如果在控制台中重复运行相同的代码，请考虑[][DevtoolsConsoleIndex]将代码保存为代码段。  代码段是你在源工具中 [创作的][DevToolsSourcesTool] 脚本。  代码段有权访问网页的 JavaScript 上下文，并且您可以在任何网页上运行代码段。  大多数网页的安全设置阻止在代码段中加载其他脚本。  因此，必须将所有代码都包括在一个文件中。  

代码段是 [bookmarklet][WikiBookmarklet] 的替代方法，区别在于代码段仅在 DevTools 中运行，且不限于 URL 的允许长度。  

使用代码段是更改第三方网页中的一些内容很好的方法。  代码段中的代码更改将添加到当前网页，并在同一上下文中运行。  有关更改网页的现有代码的信息，请导航到["替代"。][DevtoolsJavascriptOverrides]  

:::row:::
   :::column span="":::
      例如，下图显示了左侧的 DevTools 主页，右侧显示了一些代码段源代码。  
      
      :::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="运行代码段之前" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
         运行代码段之前的网页  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      运行代码段之前，网页中的代码段源代码。  
      
      ```javascript
      console.log('Hello, Snippets!');
      document.body.innerHTML = '';
      var p = document.createElement('p');
      p.textContent = 'Hello, Snippets!';
      document.body.appendChild(p);
      ```
   :::column-end:::
:::row-end:::  

在下图中，网页在运行代码段后显示。  控制台 **箱** 弹出以显示代码段记录的消息，网页 `Hello, Snippets!` 内容完全更改。  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="运行代码段后的网页" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   运行代码段后的网页  
:::image-end:::  

## 打开代码段窗格  

代码 **段** 窗格列出了代码段。  当您要编辑代码段时，您需要从代码段窗格中 **打开** 它。  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text="代码段窗格" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   代码 **段** 窗格  
:::image-end:::  

### 使用鼠标打开代码段窗格  

1.  选择" **源"** 选项卡以打开 **"源"** 工具。  默认情况下 **，"** 页面"窗格通常打开。  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="左侧打开页面窗格的源工具" lightbox="../media/javascript-sources-page-pane.msft.png":::
       左侧 **打开** "页面" **窗格** 的"源"工具  
    :::image-end:::  
    
1.  选择 **"代码段"** 选项卡以打开 **"代码段"** 窗格。  你可能需要选择"更多**选项卡**"\ ("选项卡 ![ ][ImageMoreTabsIcon] ") "代码段"选项。 ****  
    
### 使用命令菜单打开代码段窗格  

1.  将光标焦点放在 DevTools 中的某一位置。  
1.  选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 打开命令菜单。  
1.  键入 `Snippets` ， **选择"显示**代码段"，然后选择 `Enter` 运行命令。  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text="显示代码段命令" lightbox="../media/javascript-search-show-snippets.msft.png":::
       " **显示代码段"** 命令  
    :::image-end:::  
    
## 创建代码段  

### 通过"源"面板创建代码段  

1.  [打开 **代码段** 窗格](#open-the-snippets-pane)。  
1.  选择 **"新建代码段"。**  
1.  输入代码段的名称，然后选择 `Enter` 保存。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="命名代码段" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       命名代码段  
    :::image-end:::  
    
### 通过命令菜单创建代码段  

1.  将光标焦点放在 DevTools 中的某一位置。  
1.  选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 打开命令菜单。  
1.  键入 `Snippet` ，选择 **"创建新代码段**"，然后选择 `Enter` 运行命令。  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="用于创建新代码段的命令" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       用于创建新代码段的命令  
    :::image-end:::  
    
若要使用自定义名称重命名新代码段，请导航到["重命名代码段"。](#rename-snippets)  

## 编辑代码段  

1.  [打开 **代码段** 窗格](#open-the-snippets-pane)。  
1.  在 **"代码** 段"窗格中，选择要编辑的代码段的名称。  它将在代码 **编辑器中打开**。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="代码编辑器" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       代码 **编辑器**  
    :::image-end:::  
    
1.  使用 **代码编辑器** 将 JavaScript 添加到代码段。  
1.  当代码段名称旁边出现星号时，这意味着您具有未保存的代码。  选择 `Control` + `S` \ (Windows、Linux\) 或 `Command` + `S` \ (macOS\) 保存。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="代码段名称旁边的星号指示未保存的代码" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       代码段名称旁边的星号指示未保存的代码  
    :::image-end:::  
    
## 运行代码段  

### 从"源"面板运行代码段  

1.  [打开 **代码段** 窗格](#open-the-snippets-pane)。  
1.  选择要运行的代码段的名称。  代码段将在代码 **编辑器中打开**。  
1.  Choose **Run Snippet** \ (Run Snippet ![ ][ImageRunSnippetIcon] \) ， or select `Control` + `Enter` \ (Windows， Linux\) or `Command` + `Enter` \ (macOS\) .  
    
### 使用命令菜单运行代码段  

1.  将光标焦点放在 DevTools 中的某一位置。  
1.  选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 打开命令菜单。  
1.  删除 `>` 字符并键入后跟要运行 `!` 的代码段的名称的字符。  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="从命令菜单运行代码段" lightbox="../media/javascript-search-run-command.msft.png":::
       从命令菜单 **运行代码段**  
    :::image-end:::  
    
1.  选择 `Enter` 以运行代码段。  

## 重命名代码段  

1.  [打开 **代码段** 窗格](#open-the-snippets-pane)。  
1.  将鼠标悬停在代码段名称上，打开上下文菜单 \ (右键单击\) ，然后选择"重命名 **"。**  
    
## 删除代码段  

1.  [打开 **代码段** 窗格](#open-the-snippets-pane)。  
1.  将鼠标悬停在代码段名称上，打开上下文菜单 \ (右键单击\) ，然后选择"删除 **"。**  
    
## 联系 Microsoft Edge DevTools 团队  

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
