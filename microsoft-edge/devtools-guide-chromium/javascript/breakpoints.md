---
description: 了解在 Microsoft Edge 开发工具中暂停代码的所有方法。
title: 如何在 Microsoft Edge 开发工具中使用断点暂停代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: dd865f346046cb6706e71fdb3cc869950b2b4352
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519357"
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

# <a name="how-to-pause-your-code-with-breakpoints-in-microsoft-edge-devtools"></a>如何在 Microsoft Edge 开发工具中使用断点暂停代码  

使用断点暂停 JavaScript 代码。  本文介绍了 DevTools 中提供的每种断点类型，以及何时使用以及如何设置每种类型。

有关使用现有网页的介绍性教程，请导航到 [开始在 Microsoft Edge DevTools][DevtoolsJavascriptIndex]中调试 JavaScript。

## <a name="overview-of-when-to-use-each-breakpoint-type"></a>何时使用各断点类型的概述  

最著名的断点类型是代码行。  但代码行断点设置效率可能较低，尤其是在不知道具体查找位置，或者正使用大型代码库时。  通过了解如何以及何时使用其他类型的断点，可在调试时节省自己的时间。  

| 断点类型 | 使用此类型，如果希望暂停... |  
|:--- |:--- |  
| [代码行](#line-of-code-breakpoints) | 在代码的准确区域上。  |  
| [条件代码行](#conditional-line-of-code-breakpoints) | 在代码的准确区域上，但仅在某些其他条件为 true 时。  |  
| [DOM](#dom-change-breakpoints) | 在更改或删除特定 DOM 节点或子节点的代码上。  |  
| [XHR](#xhrfetch-breakpoints) | XHR URL 包含字符串模式时。  |  
| [事件侦听器](#event-listener-breakpoints) | 在发生事件后运行的代码上，例如 `click`，运行。  |  
| [异常](#exception-breakpoints) | 在引发已捕获或未捕获异常的代码行上。  |  
| [函数](#function-breakpoints) | 每当运行特定的命令、函数或方法时。  |  

## <a name="line-of-code-breakpoints"></a>代码行断点  

知道需要调查的确切代码区域时，使用代码行断点。  开发工具始终在运行此代码行之前暂停。  

在开发工具中设置代码行断点：  

1.  选择“**源**”工具。  
1.  打开包含要中断的代码行的文件。  
1.  转到代码行。  
1.  代码行的左侧是行号列。  选择。  行号列旁边出现红色图标。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       代码行断点  
    :::image-end:::  
    
### <a name="line-of-code-breakpoints-in-your-code"></a>代码中的代码行断点  

从代码运行 `debugger` 方法，以暂停在此行。  这与[代码行断点](#line-of-code-breakpoints)等效，只是断点在代码中设置，而不是在开发工具 UI 中设置的。  

```javascript
console.log('a');
console.log('b');
debugger;
console.log('c');
```  

### <a name="conditional-line-of-code-breakpoints"></a>条件代码行断点  

如果知道需要调查的确切代码区域时，但仅在某些其他条件为 true 时才想暂停，请使用条件代码行断点。  

设置条件代码行断点：  

1.  选择“**源**”工具。  
1.  打开包含要中断的代码行的文件。  
1.  转到代码行。  
1.  代码行的左侧是行号列。  将鼠标悬停在行号上，打开上下文菜单 \(右键单击\)。  
1.  选择“**添加条件断点**”。  代码行下方将显示一个对话框。  
1.  在对话框中输入条件。  
1.  选择 `Enter` 以激活断点。  行号列旁边的图标。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-conditional-breakpoint.msft.png" alt-text="条件代码行断点" lightbox="../media/javascript-sources-page-js-conditional-breakpoint.msft.png":::
       条件代码行断点  
    :::image-end:::  
    
### <a name="manage-line-of-code-breakpoints"></a>管理代码行断点  

使用“**断点**”窗格可禁用或删除单个位置中的代码行断点。  

:::image type="complex" source="../media/javascript-sources-page-js-breakpoints-16-33.msft.png" alt-text="断点窗格" lightbox="../media/javascript-sources-page-js-breakpoints-16-33.msft.png":::
   **断点**窗格  
:::image-end:::  

*   选中条目旁边的复选框以禁用该断点。  
*   将鼠标悬停在某个项上并打开上下文菜单 \(右键单击\) 删除该断点。  
*   将鼠标悬停在“**断点**”窗格中的任意位置，然后打开上下文菜单 \(右键单击\) 以停用所有断点、禁用所有断点或删除所有断点。  禁用所有断点等效于取消选中每个断点。  取消激活所有断点将指示开发工具忽略所有代码行断点，但也要保持启用状态，以使每个断点都与重新激活每个断点时的状态相同。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png" alt-text="“断点”窗格中的已停用断点" lightbox="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png":::
       “**断点**”窗格中的已停用断点  
    :::image-end:::  
    
## <a name="dom-change-breakpoints"></a>DOM 更改断点  

想要暂停更改 DOM 节点或子级的代码时，请使用 DOM 更改断点。  

设置 DOM 更改断点类型：  

1.  选择“**元素**”工具。  
1.  转到要设置断点的元素。  
1.  将鼠标悬停在元素上并打开上下文菜单 \(右键单击\)。  
1.  将鼠标悬停在“**中断**”上，然后选择“**子树修改**”，“**属性修改**”或“**节点删除**”。  
    
    :::image type="complex" source="../media/javascript-elements-break-on-subtree-modifications.msft.png" alt-text="用于创建 DOM 更改断点的上下文菜单" lightbox="../media/javascript-elements-break-on-subtree-modifications.msft.png":::
       用于创建 DOM 更改断点的上下文菜单  
    :::image-end:::  
    
### <a name="types-of-dom-change-breakpoints"></a>DOM 更改断点类型  

*   **子树修改**。  删除或添加当前选定的节点的子节点，或者更改子节点的内容时触发。  子节点属性更改时，或对当前选定的节点进行任何更改时不触发。  
*   **属性修改**：在当前选定的节点上添加或删除属性时触发，或当属性值更改时触发。  
*   **节点删除**：删除当前选定的节点时触发。  
    
## <a name="xhrfetch-breakpoints"></a>XHR/Fetch 断点  

当 XHR 的请求 URL 包含指定字符串时，若要中断，请使用 XHR 断点。  开发工具将在 XHR 运行 `send()` 方法的代码行上暂停。  

> [!NOTE]
> 此功能还适用于 [Fetch API][MDNFetchApi] 请求。  

例如，当网页请求 URL 不正确，并且希望快速找到导致错误请求的 AJAX 或 Fetch 源代码时，这非常有用。  

设置 XHR 断点：  

1.  选择“**源**”工具。  
1.  展开“**XHR 断点**”窗格。  
1.  选择“**添加断点**”。  
1.  输入要中断的字符串。  当此字符串存在于 XHR 请求 URL 中的任何位置时，开发工具将暂停。  
1.  选择 `Enter` 以确认。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png" alt-text="创建 XHR 断点" lightbox="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png":::
       创建 XHR 断点  
    :::image-end:::  
    
## <a name="event-listener-breakpoints"></a>事件侦听器断点  

如果想在事件触发后运行的事件侦听器代码上暂停时，请使用事件侦听器断点。  可以选择特定事件，如 `click`，或事件类别，如所有鼠标事件。  

1.  选择“**源**”工具。  
1.  展开“**事件侦听器断点**”窗格。  开发工具显示事件类别的列表，如 **动画**。  
1.  检查这些类别之一可在触发该类别的任何事件时暂停，或展开该类别并检查特定事件。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png" alt-text="创建事件侦听器断点" lightbox="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png":::
       创建事件侦听器断点  
    :::image-end:::  
    
## <a name="exception-breakpoints"></a>异常断  

想要暂停引发已捕获或未捕获异常的代码行时，请使用异常断点。  

1.  选择“**源**”工具。  
1.  选择“**因异常暂停**” \(![ 因异常暂停 ](../media/pause-on-exceptions-icon.msft.png) \)。  图标在启用时变为蓝色。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-pause-on-exceptions.msft.png" alt-text="“因异常暂停”按钮" lightbox="../media/javascript-sources-page-js-pause-on-exceptions.msft.png":::
       “**因异常暂停**”按钮  
    :::image-end:::  
    
1.  **可选**。  如果还想捕获异常时暂停，请选中“**捕获异常时暂停**”复选框。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-paused-on-exception.msft.png" alt-text="因未捕获异常暂停" lightbox="../media/javascript-sources-page-js-paused-on-exception.msft.png":::
       因未捕获异常暂停  
    :::image-end:::  
    
## <a name="function-breakpoints"></a>函数断点  

如果要在运行特定功能时暂停，请运行 `debug(method)` 方法，其中 `method` 是要调试的命令、函数或方法。  可以在代码中插入 `debug()`（如`console.log()`语句）或从开发工具控制台运行方法。  `debug()` 等效于在函数第一行上“[代码行断点](#line-of-code-breakpoints)”设置。  

```javascript
function sum(a, b) {
    let result = a + b; // DevTools pauses on this line.
    return result;
}
debug(sum); // Pass the function object, not a string.
sum();
```  

### <a name="make-sure-the-target-function-is-in-scope"></a>确保目标函数在作用域内  

如果要调试的函数不在作用域内，开发工具将引发 `ReferenceError`。  

```javascript
(function () {
    function hey() {
        console.log('hey');
    }
    function yo() {
        console.log('yo');
    }
    debug(yo); // This works.
    yo();
})();
debug(hey); // This does not work.  hey() is out of scope.
```  

如果要从开发工具控制台运行 `debug()` 方法，确保目标函数位于作用域内则比较困难。  下面是一个策略：  

1.  在函数作用域内的某个位置设置[代码行断点](#line-of-code-breakpoints)。
1.  触发断点。  
1.  代码仍在代码行断点处暂停时，在开发工具控制台中运行 `debug()` 方法。  
    
## <a name="related-articles"></a>相关文章

*   [使用调试器功能][DevtoolsJavascriptReference] - 使用"源"工具 **中的调试器** UI。
*   [在 Microsoft Edge DevTools][DevtoolsJavascriptIndex] 中调试 JavaScript 入门 - 使用现有网页的介绍性教程。
*   [源工具概述][DevtoolsSourcesIndex]- 调试器是源工具**** 的一部分，其中包括 JavaScript 编辑器。

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsJavascriptReference]: ./reference.md "使用调试器功能|Microsoft Docs"  

[DevtoolsJavascriptIndex]: index.md "在 Microsoft Edge 开发工具中调试 JavaScript 入门 | Microsoft Docs"  

[DevtoolsSourcesIndex]: ../sources/index.md "源工具概述 | Microsoft Docs"  

[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "Fetch API | MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
