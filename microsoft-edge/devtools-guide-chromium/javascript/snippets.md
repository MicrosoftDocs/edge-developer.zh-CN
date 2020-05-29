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





# 在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段   



如果你发现自己在[控制台][DevtoolsConsoleIndex]中重复运行相同的代码，请考虑改为将代码另存为代码段。  代码段是您在 " [**源**" 面板][DevToolsSourcesPanel]中创作的脚本。  他们有权访问页面的 JavaScript 上下文，您可以在任何页面上运行这些上下文。  代码段是[bookmarklets][WikiBookmarklet]的替代方法。  
Firefox DevTools 的功能类似于名为 "[便笺簿][MDNScratchpad]" 的 "片段"。  

例如，[**图 1**](#figure-1)显示左侧的 DevTools 主页和右侧的一些代码段源代码。  

> ##### 图 1  
> 运行代码段之前页面的外观  
> ![运行代码段之前页面的外观][ImageSnippetSplitScreen]  

[**图 1**](#figure-1)中的代码段源代码：  

```javascript
console.log('Hello, Snippets!');
document.body.innerHTML = '';
var p = document.createElement('p');
p.textContent = 'Hello, Snippets!';
document.body.appendChild(p);
```  

[**图 2**](#figure-2)显示了运行代码段后页面的外观。  **控制台抽屉**将弹出 `Hello, Snippets!` ，显示代码片段记录的消息，并且该页面的内容将完全更改。  

> ##### 图 2  
> 运行代码段后页面的外观  
> ![运行代码段后页面的外观][ImageSnippetSplitScreenAfter]  

## 打开 "代码段" 窗格   

"**代码段**" 窗格将列出你的代码段。  若要编辑代码段，需要从 "**代码段**" 窗格中将其打开。  

> ##### 图 3  
> "**代码段**" 窗格  
> !["代码段" 窗格][ImageSnippetsPane]  

### 使用鼠标打开 "代码段" 窗格   

1.  单击 "**源**" 选项卡以打开 "**源**" 面板。  默认情况下，**页面**窗格通常打开。  

    > ##### 图 4  
    > 在左侧打开**页面**窗格的 "**源**" 面板  
    > ![在左侧打开页面窗格的 "源" 面板][ImageSourcesPageEmpty]  

1.  单击 "**代码段**" 选项卡以打开 "**代码段**" 窗格。  你可能需要单击 "**更多选项**卡" 选项 ![ 卡才能 ][ImageMoreTabsIcon] 访问 "**代码段**" 选项。  

### 通过 "命令" 菜单打开 "代码段" 窗格   

1.  将光标聚焦在 DevTools 内的某个位置。  
1.  按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单。  
1.  开始键入 `Snippets` ，选择 "**显示代码段**"，然后按 `Enter` 运行命令。  

    > ##### 图 5  
    > "**显示代码段**" 命令  
    > !["显示代码段" 命令][ImageShowSnippetsSearch]  

## 创建代码段   

### 通过 "源" 面板创建代码段   

1.  [打开 "**代码段**" 窗格](#open-the-snippets-pane)。  
1.  单击 "**新建代码段**"。  
1.  输入代码段的名称，然后按 " `Enter` 保存"。  

    > ##### 图 6  
    > 命名代码段  
    > ![命名代码段][ImageSnippetName]  

### 通过 "命令" 菜单创建代码段   

1.  将光标聚焦在 DevTools 内的某个位置。  
1.  按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单。  
1.  开始键入 `Snippet` ，选择 "**创建新代码段**"，然后按 `Enter` 运行命令。  

    > ##### 图 7  
    > 用于创建新代码段的命令  
    > ![用于创建新代码段的命令][ImageCreateSnippetSearch]  

如果想要为新的代码段提供自定义名称，请参阅[重命名代码段](#rename-snippets)。  

## 编辑代码段   

1.  [打开 "**代码段**" 窗格](#open-the-snippets-pane)。  
1.  在 "代码**段**" 窗格中，单击要编辑的代码段的名称，以便在**代码编辑器**中将其打开。  

    > ##### 图 8  
    > 代码编辑器  
    > ![代码编辑器][ImageSnippetEditor]  

1.  使用**代码编辑器**将 JavaScript 添加到代码段。  
1.  当代码段名称旁边显示星号时，表示你有未保存的代码。 按 `Control` + `S` \ （Windows \）或 `Command` + `S` \ （macOS \）保存。  

    > ##### 图 9  
    > 代码段名称旁边的星号，指示未保存的代码  
    > ![代码段名称旁边的星号，指示未保存的代码][ImageUnsavedSnippet]  

## 运行代码段   

### 从 "源" 面板运行代码段   

1.  [打开 "**代码段**" 窗格](#open-the-snippets-pane)。  
1.  单击要运行的代码段的名称。  代码段将在**代码编辑器**中打开。  
1.  单击 "**运行片段** ![ 运行代码段 ][ImageRunSnippetIcon] "，或按 `Control` + `Enter` \ （Windows \）或 `Command` + `Enter` \ （macOS \）。  

### 使用 "命令" 菜单运行代码段   

1.  将光标聚焦在 DevTools 内的某个位置。  
1.  按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单。  
1.  删除 `>` 字符，然后键入一个字符，然后键入 `!` 要运行的代码段的名称。  

    > ##### 图 10  
    > 从 "命令" 菜单运行代码段  
    > ![从 "命令" 菜单运行代码段][ImageRunSnippetCommand]  

1.  按 `Enter` 运行代码段。  

## 重命名代码段   

1.  [打开 "**代码段**" 窗格](#open-the-snippets-pane)。  
1.  右键单击代码段名称，然后选择 "**重命名**"。  

## 删除代码段   

1.  [打开 "**代码段**" 窗格](#open-the-snippets-pane)。  
1.  右键单击代码段名称，然后选择 "**删除**"。  

 



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
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/snippets)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
