---
description: 在 Microsoft Edge DevTools 的"源"面板中显示和编辑文件、创建代码段、调试 JavaScript 和设置工作区。
title: 源窗格概览
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 7ce7ae32b4bf91419512ec9e387cdf75549552a5
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439603"
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

# <a name="sources-panel-overview"></a>源窗格概览  

使用 Microsoft Edge DevTools **源** 面板执行以下操作。  

*   [显示文件](#display-files)。  
*   [编辑 CSS 和 JavaScript](#edit-css-and-javascript)。  
*   [创建并保存**JavaScript**](#create-save-and-run-snippets)的代码段，您可以在任何网页上运行这些代码段。  **代码段** 类似于 bookmarklet。  
*   [调试 JavaScript](#debug-javascript)。  
*   [设置 Workspace](#set-up-a-workspace)，以便将你在 DevTools 中所做的更改保存到文件系统上的代码中。  
    
## <a name="display-files"></a>显示文件  

使用 **页面面板** ;显示页面加载的所有资源。

:::image type="complex" source="../media/sources-page-pane.msft.png" alt-text=""页面"面板" lightbox="../media/sources-page-pane.msft.png":::
   " **页面"** 面板  
:::image-end:::  

**页面** 窗格的组织方式：  
*   顶层，如上图中的 `top`， 表示 [HTML 框架][W3CHtml4Frames]。  在访问的每一页上查找 `top`。  `top` 表示主文档框架。  
*   二级，如上图中 `docs.microsoft.com` 所示，表示 [起源][HtmlstandardOrigin]。  
*   第三级、第四级等表示从该起源加载的目录和资源。  例如，在上图中，资源 `devtools-guide-chromium` 的完整路径为 `docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium`  
    
在"页面"面板 **中选择** 一个文件，以显示" **编辑器"窗格中** 的内容。  可以显示任何类型的文件。  对于图像，将显示图像的预览。  

:::image type="complex" source="../media/sources-editor-pane.msft.png" alt-text="在编辑器窗格中a4d10f71.index-docs.js内容" lightbox="../media/sources-editor-pane.msft.png":::
   在"编辑器 `a4d10f71.index-docs.js` "面板**中显示 的内容**  
:::image-end:::  

## <a name="edit-css-and-javascript"></a>编辑 CSS 和 JavaScript  

使用 **编辑器** 窗格编辑 CSS 和 JavaScript。  DevTools 更新页面以运行新代码。  例如，如果通过添加以下样式规则编辑 CSS 文件：

```css
.metadata.page-metadata {
    color: red;
}
```

该更改应立即生效。

:::image type="complex" source="../media/edit-css.msft.png" alt-text="编辑编辑器窗格中的 CSS，将字幕的文本颜色更改为红色" lightbox="../media/edit-css.msft.png":::
   编辑 **编辑器** 窗格中的CSS，将字幕的文本颜色更改为红色  
:::image-end:::  

CSS 更改会立即生效，无需保存。  若要使 JavaScript 更改生效，请选择 `Control` + `S`\(Windows、Linux\) 或 `Command` + `S`\(macOS\)。  DevTools 不会重新运行脚本，因此唯一生效的 JavaScript 更改就是你在函数内部所做的更改。  例如，在下图中，请注意 `console.log('A')` 如何没有运行，而 `console.log('B')` 则运行。  如果 DevTools 在更改后重新运行整个脚本，则文本 `A` 将记录到 **控制台**。  

:::image type="complex" source="../media/edit-js.msft.png" alt-text="在编辑器窗格中编辑 JavaScript" lightbox="../media/edit-js.msft.png":::
   在编辑器面板中 **编辑** JavaScript  
:::image-end:::  

在刷新页面时，DevTools 会清除 CSS 和 JavaScript 更改。  导航至 [设置工作区](#set-up-a-workspace)，了解如何将更改保存到文件系统。  

## <a name="create-save-and-run-snippets"></a>创建、保存和运行代码段  

代码段是您可以在任何页面上运行的脚本。  假设您在控制台中重复键入以下代码，以便将**** jQuery 库插入页面，以便你可以从控制台运行 jQuery**命令**。  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

相反，你可以将此代码保存在 **代码段** 中，并随时通过单击几次按钮来运行它。  DevTools 将 **代码段** 保存到文件系统。  

:::image type="complex" source="../media/snippet.msft.png" alt-text="将 jQuery 库插入到页面中的代码段" lightbox="../media/snippet.msft.png":::
   将 jQuery 库插入到页面中的 **代码段**  
:::image-end:::  

若要运行 **代码段**：

*   使用"代码 **段"面板** 打开文件， **然后选择"运行** " (" ![ 运行"按钮 ](../media/run-snippet-icon.msft.png) \) 。  
*   打开 [命令菜单][DevtoolsGuideChromiumCommandMenuIndex]，删除字符， `>` 键入 `!` ，键入代码段 **的名称**，然后选择 `Enter` 。  
    
导航至 [从任何页面运行代码段][DevtoolsGuideChromiumJavascriptSnippets] 以了解更多信息。

## <a name="debug-javascript"></a>调试 JavaScript  

请考虑改为使用 Microsoft Edge DevTools 调试工具，而不是通过`console.log()` 推断 JavaScript 出错的地方。  一般想法是设置断点，这是代码中的一个有意停止位置，然后逐步执行代码的运行时，每次一行。  在逐步执行代码时，可以显示和更改所有当前定义的属性和变量的值，在 **控制台**中运行 JavaScript 等。

导航到 [调试 JavaScript入门][DevtoolsGuideChromiumJavascriptIndex]，了解 DevTools 中调试的基础知识。

:::image type="complex" source="../media/debugging.msft.png" alt-text="调试 JavaScript" lightbox="../media/debugging.msft.png":::
   调试 JavaScript  
:::image-end:::  

## <a name="set-up-a-workspace"></a>设置工作区  

默认情况下，在"源"工具中编辑文件时****，刷新页面时这些更改将丢失。  **工作区** 使您能够将你在 DevTools 中所做的更改保存到文件系统。  实质上，DevTools 能够用作代码编辑器。

导航到 [使用工作区编辑文件][DevtoolsGuideChromiumWorkspacesIndex] 以开始操作。

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumCommandMenuIndex]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行|Microsoft Docs"  
[DevtoolsGuideChromiumJavascriptIndex]: ../javascript/index.md "开始在 Microsoft Edge 开发人员工具中调试 JavaScript |Microsoft Docs"  
[DevtoolsGuideChromiumJavascriptSnippets]: ../javascript/snippets.md "使用 Microsoft Edge DevTools 工具在任意页面上运行 JavaScript |Microsoft Docs"  
[DevtoolsGuideChromiumWorkspacesIndex]: ../workspaces/index.md "使用 Workspaces |Microsoft Docs"  

[HtmlstandardOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "源|HTML Standard"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "框架|W3C"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/sources)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
