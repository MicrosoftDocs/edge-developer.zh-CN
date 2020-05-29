---
title: "\"源\" 面板概述"
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: c61d1bda030ce729b0b217b95a9143508d1f51f8
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601906"
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
   limitations under the License. -->






# "源" 面板概述 



使用 Microsoft Edge DevTools "**源**" 面板执行以下操作：

*   [查看文件](#view-files)。  
*   [编辑 CSS 和 JavaScript](#edit-css-and-javascript)。  
*   [创建和保存 JavaScript 的**代码段**](#create-save-and-run-snippets)，你可以在任何页上运行它们。  **代码段**类似于 bookmarklets。  
*   [调试 JavaScript](#debug-javascript)。  
*   [设置工作区](#set-up-a-workspace)，以便在 DevTools 中所做的更改将保存到文件系统上的代码。  

## 查看文件 

使用**页面**窗格查看页面已加载的所有资源。

> ##### 图 1  
> **页面**窗格  
> ![图1：页面窗格][ImageSourcesPagePane]  

如何组织**页面**窗格：  
*   顶级（如 `top` [**图 1**](#figure-1)所示）表示[HTML 框架][W3CHtml4Frames]。  `top`在您访问的每个页面上查找。 `top` 代表主文档框架。  
*   第二级（如 `docs.microsoft.com` [**图 1**](#figure-1)所示）表示[原点][HtmlstandardOrigin]。  
*   第三级、第四级等，表示从该来源加载的目录和资源。  例如，在[**图 1**](#figure-1)中，资源的完整路径 `devtools-guide-chromium` 是 `docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium`  

单击**页面**窗格中的文件以查看 "**编辑器**" 窗格中的内容。  您可以查看任何类型的文件。 对于图像，你将看到图像的预览。  

> ##### 图 2  
> `a4d10f71.index-docs.js`在 "**编辑器**" 窗格中查看内容  
> ![图 2. 在 "编辑器" 窗格中查看 a4d10f71 的内容][ImageSourcesEditorPane]  

## 编辑 CSS 和 JavaScript 

使用 "**编辑器**" 窗格编辑 CSS 和 JavaScript。  DevTools 更新页面以运行新代码。 例如，如果通过添加下面的样式规则来编辑 CSS 文件：

```css
.metadata.page-metadata {
    color: red;
}
```

您应看到更改立即生效。

> ##### 图 3  
> 在 "**编辑器**" 窗格中编辑 CSS 以将副标题的文本颜色更改为红色  
> ![图 3. 在 "编辑器" 窗格中编辑 CSS 以将副标题的文本颜色更改为红色][ImageEditCSS]  

CSS 更改会立即生效，无需保存。 若要使 JavaScript 更改生效，请按 `Control` + `S` \ （Windows \）或 `Command` + `S` \ （macOS \）。 DevTools 不会重新运行脚本，因此只有你在函数中执行的 JavaScript 更改才会生效。  例如，在[**图 4**](#figure-4)中，注意如何 `console.log('A')` 运行，而不是运行 `console.log('B')` 。 如果 DevTools 在进行更改后重新运行整个脚本，则文本 `A` 将被记录到**控制台**。  

> ##### 图 4  
> 在 "**编辑器**" 窗格中编辑 JavaScript  
> ![图 4. 在 "编辑器" 窗格中编辑 JavaScript][ImageEditJS]  

DevTools 会在你重新加载页面时清除你的 CSS 和 JavaScript 更改。 请参阅[设置工作区](#set-up-a-workspace)以了解如何将更改保存到文件系统。  

## 创建、保存和运行代码段 

代码段是可以在任何页上运行的脚本。 假设你在**控制台**中重复键入以下代码，以便将 jquery 库插入到页面中，以便你可以从该**控制台**运行 jquery 命令：  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

相反，你可以将此代码保存在一个代码**段**中，并在每次需要时通过几次按钮单击运行它。  DevTools 将**代码段**保存到文件系统。  

> ##### 图 5  
> 将 jQuery 库插入到页面中的**代码段**  
> ![图 5. 将 jQuery 库插入到页面中的代码段][ImageSnippet]  

要运行**代码段**，请执行以下操作：

*   通过 "**代码段**" 窗格打开文件，然后单击 "**运行** ![ 运行" 按钮 ][ImageRunIcon] 。  
*   打开 "**[命令" 菜单][DevtoolsGuideChromiumCommandMenuIndex]**，删除 " `>` 字符"，键入 `!` **代码段**的名称，然后按 `Enter` 。  

请参阅[从任意页面运行代码片段][DevtoolsGuideChromiumJavascriptSnippets]以了解详细信息。


## 调试 JavaScript 

请 `console.log()` 考虑改用 Microsoft Edge DevTools 调试工具，而不是使用来推断 JavaScript 出现错误的位置。 一般做法是设置一个断点，该断点是代码中有意停止的位置，然后逐句通过代码的运行时，一次一行。 逐句通过代码时，你可以查看和更改所有当前定义的属性和变量的值，并在**控制台**中运行 JavaScript 等。

有关在 DevTools 中调试的基础知识，请参阅[开始使用调试 JavaScript][DevtoolsGuideChromiumJavascriptIndex] 。

> ##### 图 6  
> 调试 JavaScript  
> ![图 6. 调试 JavaScript][ImageDebugging]  

## 设置工作区 

默认情况下，当您在 "**源**" 面板中编辑文件时，当您重新加载页面时，这些更改将会丢失。  **工作区**使你能够将在 DevTools 中所做的更改保存到你的文件系统中。  实质上，这使你可以将 DevTools 用作代码编辑器。

请参阅[编辑包含工作区的文件][DevtoolsGuideChromiumWorkspacesIndex]以开始使用。

 



<!-- image links -->  

[ImageRunIcon]: /microsoft-edge/devtools-guide-chromium/media/run-snippet-icon.msft.png  

[ImageSourcesPagePane]: /microsoft-edge/devtools-guide-chromium/media/sources-page-pane.msft.png "图1：页面窗格"  
[ImageSourcesEditorPane]: /microsoft-edge/devtools-guide-chromium/media/sources-editor-pane.msft.png "图2：在 "编辑器" 窗格中查看 a4d10f71 的内容"  
[ImageEditCSS]: /microsoft-edge/devtools-guide-chromium/media/edit-css.msft.png "图3：在 "编辑器" 窗格中编辑 CSS 以将副标题的文本颜色更改为红色"  
[ImageEditJS]: /microsoft-edge/devtools-guide-chromium/media/edit-js.msft.png "图4：在 "编辑器" 窗格中编辑 JavaScript"  
[ImageSnippet]: /microsoft-edge/devtools-guide-chromium/media/snippet.msft.png "图5：将 jQuery 库插入到页面中的代码段"  
[ImageDebugging]: /microsoft-edge/devtools-guide-chromium/media/debugging.msft.png "图6：调试 JavaScript"  

<!-- links -->  

[DevtoolsGuideChromiumCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令"  
[DevtoolsGuideChromiumJavascriptIndex]: /microsoft-edge/devtools-guide-chromium/javascript/index "在 Microsoft Edge DevTools 中开始使用调试 JavaScript"  
[DevtoolsGuideChromiumJavascriptSnippets]: /microsoft-edge/devtools-guide-chromium/javascript/snippets "在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段"  
[DevtoolsGuideChromiumWorkspacesIndex]: /microsoft-edge/devtools-guide-chromium/workspaces/index "编辑具有工作区的文件"  

[HtmlstandardOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "原创-HTML 标准"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "框架 |W3C"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/sources)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
