---
description: 代码段是你可以在 Microsoft Edge DevTools 的 "源" 工具中创作和运行的小型脚本。  您可以从任何网页访问和运行资源。  运行代码段时，它从当前打开的网页的上下文中运行。
title: 在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 3542243f7fa886865ced47d47991cd9b11001e2e
ms.sourcegitcommit: 9dcaf598f3930bcfab9f93ff63463beb98274de0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "11145118"
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

# 在具有 Microsoft Edge DevTools 的任何网页上运行 JavaScript 片段  

如果你在 [控制台][DevtoolsConsoleIndex] 中重复运行相同的代码，请考虑改为将代码另存为代码段。  代码段是您在 " [源][DevToolsSourcesTool] " 工具中创作的脚本。  代码段有权访问网页的 JavaScript 上下文，你可能会在任何网页上运行代码段。  大多数网页的安全设置阻止了在代码段中加载其他脚本。  因此，你必须将所有代码包含在一个文件中。  

代码段是 [bookmarklets][WikiBookmarklet] 的一种替代方法，它的不同之处仅在 DevTools 中运行，并且不仅限于允许的 URL 长度。  

使用代码段是在第三方网页中更改一些操作的绝佳方式。  代码段中的代码更改将添加到当前网页并在同一上下文中运行。  有关更改网页的现有代码的详细信息，请导航到 " [替代][DevtoolsJavascriptOverrides]"。  

:::row:::
   :::column span="":::
      例如，下图显示左侧的 DevTools 主页和右侧的一些代码段源代码。  
      
      :::image type="complex" source="../media/javascript-sources-snippets-split-screen.msft.png" alt-text="运行代码段之前" lightbox="../media/javascript-sources-snippets-split-screen.msft.png":::
         运行代码段之前的网页  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      在运行代码段之前网页中的代码段源代码。  
      
      ```javascript
      console.log('Hello, Snippets!');
      document.body.innerHTML = '';
      var p = document.createElement('p');
      p.textContent = 'Hello, Snippets!';
      document.body.appendChild(p);
      ```
   :::column-end:::
:::row-end:::  

下图显示了运行代码段后的网页。  **控制台抽屉**将弹出 `Hello, Snippets!` ，显示代码片段所记录的消息，并且网页的内容将完全更改。  

:::image type="complex" source="../media/javascript-sources-snippets-split-screen-after.msft.png" alt-text="运行代码段之前" lightbox="../media/javascript-sources-snippets-split-screen-after.msft.png":::
   运行代码段后的网页  
:::image-end:::  

## 打开 "代码段" 窗格  

" **代码段** " 窗格将列出你的代码段。  若要编辑代码段，需要从 " **代码段** " 窗格中将其打开。  

:::image type="complex" source="../media/javascript-sources-snippets-pane.msft.png" alt-text="运行代码段之前" lightbox="../media/javascript-sources-snippets-pane.msft.png":::
   " **代码段** " 窗格  
:::image-end:::  

### 使用鼠标打开 "代码段" 窗格  

1.  选择 " **源** " 选项卡以打开 " **源** " 工具。  默认情况下， **页面** 窗格通常打开。  
    
    :::image type="complex" source="../media/javascript-sources-page-pane.msft.png" alt-text="运行代码段之前" lightbox="../media/javascript-sources-page-pane.msft.png":::
       在左侧打开 "**页面**" 窗格的 "**源**" 工具  
    :::image-end:::  
    
1.  选择 " **代码段** " 选项卡以打开 " **代码段** " 窗格。  你可能需要选择 " **更多选项卡** \ (![ 更多选项卡 ][ImageMoreTabsIcon] \ ) " 以访问 " **代码段** " 选项。  
    
### 通过 "命令" 菜单打开 "代码段" 窗格  

1.  将光标聚焦在 DevTools 中的某个位置。  
1.  选择 `Control` + `Shift` + `P` \ (Windows、Linux \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "命令" 菜单。  
1.  键入 `Snippets` ，选择 " **显示代码段**"，然后选择 `Enter` 运行命令。  
    
    :::image type="complex" source="../media/javascript-search-show-snippets.msft.png" alt-text="运行代码段之前" lightbox="../media/javascript-search-show-snippets.msft.png":::
       " **显示代码段** " 命令  
    :::image-end:::  
    
## 创建代码段  

### 通过 "源" 面板创建代码段  

1.  [打开 " **代码段** " 窗格](#open-the-snippets-pane)。  
1.  选择 " **新建代码片断**"。  
1.  输入代码段的名称，然后选择 " `Enter` 保存"。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-naming.msft.png" alt-text="运行代码段之前" lightbox="../media/javascript-sources-snippets-naming.msft.png":::
       为代码段命名  
    :::image-end:::  
    
### 通过 "命令" 菜单创建代码段  

1.  将光标聚焦在 DevTools 中的某个位置。  
1.  选择 `Control` + `Shift` + `P` \ (Windows、Linux \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "命令" 菜单。  
1.  键入 `Snippet` ，选择 " **创建新代码段**"，然后选择 `Enter` 运行该命令。  
    
    :::image type="complex" source="../media/javascript-search-create-new-snippet.msft.png" alt-text="运行代码段之前" lightbox="../media/javascript-search-create-new-snippet.msft.png":::
       用于创建新代码段的命令  
    :::image-end:::  
    
若要使用自定义名称重命名新的代码段，请导航到 " [重命名代码段](#rename-snippets)"。  

## 编辑代码段  

1.  [打开 " **代码段** " 窗格](#open-the-snippets-pane)。  
1.  在 " **代码段** " 窗格中，选择要编辑的代码段的名称。  它将在 **代码编辑器**中打开。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-saved.msft.png" alt-text="运行代码段之前" lightbox="../media/javascript-sources-snippets-editor-saved.msft.png":::
       **代码编辑器**  
    :::image-end:::  
    
1.  使用 **代码编辑器** 将 JavaScript 添加到代码段。  
1.  如果代码段名称旁边显示星号，则表示你有未保存的代码。  选择 `Control` + `S` \ (Windows、Linux \ ) 或 `Command` + `S` \ (macOS \ ) 保存。  
    
    :::image type="complex" source="../media/javascript-sources-snippets-editor-unsaved.msft.png" alt-text="运行代码段之前" lightbox="../media/javascript-sources-snippets-editor-unsaved.msft.png":::
       代码段名称旁边的星号表示未保存的代码  
    :::image-end:::  
    
## 运行代码段  

### 从 "源" 面板运行代码段  

1.  [打开 " **代码段** " 窗格](#open-the-snippets-pane)。  
1.  选择要运行的代码段的名称。  代码段将在 **代码编辑器**中打开。  
1.  选择 "**运行片段**\ (![ 运行代码段 ][ImageRunSnippetIcon] \ ) "，或选择 `Control` + `Enter` \ (Windows、Linux \ ) 或 `Command` + `Enter` \ (macOS \ ) 。  
    
### 使用 "命令" 菜单运行代码段  

1.  将光标聚焦在 DevTools 中的某个位置。  
1.  选择 `Control` + `Shift` + `P` \ (Windows、Linux \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "命令" 菜单。  
1.  删除 `>` 字符，然后键入一个字符，然后键入 `!` 要运行的代码段的名称。  
    
    :::image type="complex" source="../media/javascript-search-run-command.msft.png" alt-text="运行代码段之前" lightbox="../media/javascript-search-run-command.msft.png":::
       从 "**命令" 菜单**运行代码段  
    :::image-end:::  
    
1.  选择 `Enter` 以运行代码段。  

## 重命名代码段  

1.  [打开 " **代码段** " 窗格](#open-the-snippets-pane)。  
1.  将鼠标悬停在代码段名称上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **重命名**"。  
    
## 删除代码段  

1.  [打开 " **代码段** " 窗格](#open-the-snippets-pane)。  
1.  将鼠标悬停在代码段名称上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **删除**"。  
    
## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageMoreTabsIcon]: ../media/more-tabs-icon.msft.png  
[ImageRunSnippetIcon]: ../media/run-snippet-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "控制台概述 |Microsoft 文档"  
[DevToolsSourcesTool]: ../sources.md "源工具概述 |Microsoft 文档"  
[DevtoolsJavascriptOverrides]: ./overrides.md "替代 |Microsoft 文档"  

[MDNScratchpad]: https://developer.mozilla.org/docs/Tools/Scratchpad "便笺 |MDN"  
[WikiBookmarklet]: https://en.wikipedia.org/wiki/Bookmarklet "Bookmarklet |科"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
