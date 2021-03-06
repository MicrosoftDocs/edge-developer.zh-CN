---
description: 了解在 Microsoft Edge DevTools 中可以暂停代码的所有方法。
title: 如何使用 Microsoft Edge DevTools 中的断点暂停代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 84077503d6c786244fc2ca4d54c349ae9f6d20d8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398593"
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

# <a name="how-to-pause-your-code-with-breakpoints-in-microsoft-edge-devtools"></a>如何使用 Microsoft Edge DevTools 中的断点暂停代码  

使用断点暂停 JavaScript 代码。  本指南介绍 DevTools 中可用的每种类型的断点，以及何时使用以及如何设置每种类型的断点。  有关调试过程的实践教程，请导航到 Microsoft Edge [DevTools][DevtoolsJavascriptIndex]中的 JavaScript 调试入门。  

## <a name="overview-of-when-to-use-each-breakpoint-type"></a>有关何时使用每个断点类型的概述  

最已知的断点类型是代码行。  但是，代码行断点设置效率可能较低，尤其是在您不知道具体查找位置，或者使用大型代码库时。  通过了解如何以及何时使用其他类型的断点，在调试时可以节省时间。  

| 断点类型 | 在你想要暂停时使用此...  |  
|:--- |:--- |  
| [代码行](#line-of-code-breakpoints) | 在代码的准确区域上。  |  
| [条件代码行](#conditional-line-of-code-breakpoints) | 在代码的准确区域上，但仅在某些其他条件为 true 时。  |  
| [DOM](#dom-change-breakpoints) | 在更改或删除特定 DOM 节点或子级的代码上。  |  
| [XHR](#xhrfetch-breakpoints) | 当 XHR URL 包含字符串模式时。  |  
| [事件侦听器](#event-listener-breakpoints) | 在运行事件（如 ）后运行 `click` 的代码上。  |  
| [异常](#exception-breakpoints) | 在引发捕获或不捕获异常的代码行上。  |  
| [函数](#function-breakpoints) | 每当运行特定命令、函数或方法时。  |  

## <a name="line-of-code-breakpoints"></a>代码行断点  

当您知道需要调查的代码的准确区域时，请使用代码行断点。  DevTools 始终在运行此代码行之前暂停。  

若要在 DevTools 中设置代码行断点，  

1.  选择 **"源"** 工具。  
1.  打开包含要中断的代码行的文件。  
1.  转到代码行。  
1.  代码行的左侧是行号列。  选择它。  行号列旁边将显示一个红色图标。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       代码行断点  
    :::image-end:::  
    
### <a name="line-of-code-breakpoints-in-your-code"></a>代码中的代码行断点  

从 `debugger` 代码运行该方法以暂停该行。  这等效于代码 [行](#line-of-code-breakpoints)断点，只是断点是在代码中设置的，而不是在 DevTools UI 中设置的。  

```javascript
console.log('a');
console.log('b');
debugger;
console.log('c');
```  

### <a name="conditional-line-of-code-breakpoints"></a>条件代码行断点  

如果您知道需要调查的代码的确切区域，但希望仅在满足其他某些条件时暂停，请使用条件的代码行断点。  

若要设置条件的代码行断点：：  

1.  选择 **"源"** 工具。  
1.  打开包含要中断的代码行的文件。  
1.  转到代码行。  
1.  代码行的左侧是行号列。  将鼠标悬停在行号上，然后打开上下文菜单 \ (右键单击\) 。  
1.  选择 **"添加条件断点"。**  在代码行下方显示一个对话框。  
1.  在对话框中输入条件。  
1.  选择 `Enter` 以激活断点。  行号列旁边的图标。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-conditional-breakpoint.msft.png" alt-text="条件代码行断点" lightbox="../media/javascript-sources-page-js-conditional-breakpoint.msft.png":::
       条件代码行断点  
    :::image-end:::  
    
### <a name="manage-line-of-code-breakpoints"></a>管理代码行断点  

使用 **断点** 窗格从单个位置禁用或删除代码行断点。  

:::image type="complex" source="../media/javascript-sources-page-js-breakpoints-16-33.msft.png" alt-text="断点面板" lightbox="../media/javascript-sources-page-js-breakpoints-16-33.msft.png":::
   断 **点** 面板  
:::image-end:::  

*   选中某个条目旁边的复选框可禁用该断点。  
*   将鼠标悬停在某个条目上并打开上下文菜单 \ (右键单击\) 删除该断点。  
*   将鼠标悬停在断**** 点窗格中的任意位置，然后打开上下文菜单 \ (右键单击\) 以停用所有断点、禁用所有断点或删除所有断点。  禁用所有断点等效于取消选中每个断点。  停用所有断点将指示 DevTools 忽略所有代码行断点，但还要保持启用状态，以便每个断点在重新激活每个断点时处于与之前相同的状态。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png" alt-text="断点窗格中停用的断点" lightbox="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png":::
       断点窗格中的**已停用断点**  
    :::image-end:::  
    
## <a name="dom-change-breakpoints"></a>DOM 更改断点  

当你想要暂停更改 DOM 节点或子级的代码时，请使用 DOM 更改断点。  

若要设置 DOM 更改断点，  

1.  选择 **"元素"** 工具。  
1.  转到要设置断点的元素。  
1.  将鼠标悬停在元素上并打开上下文菜单 \ (右键单击\) 。  
1.  将鼠标悬 **停在中断上**，然后选择 **子树修改**、 **属性修改**或 **节点删除**。  
    
    :::image type="complex" source="../media/javascript-elements-break-on-subtree-modifications.msft.png" alt-text="用于创建 DOM 更改断点的上下文菜单" lightbox="../media/javascript-elements-break-on-subtree-modifications.msft.png":::
       用于创建 DOM 更改断点的上下文菜单  
    :::image-end:::  
    
### <a name="types-of-dom-change-breakpoints"></a>DOM 更改断点的类型  

*   **子树修改**。  在删除或添加当前选定的节点的子节点，或者更改子节点的内容时触发。  在子节点属性更改或当前选定的节点的任何更改时不触发。  
*   **属性修改**：在当前选定的节点上添加或删除属性时，或当属性值更改时触发。  
*   **节点删除**：删除当前选定的节点时触发。  
    
## <a name="xhrfetch-breakpoints"></a>XHR/Fetch 断点  

当 XHR 的请求 URL 包含指定字符串时，请使用 XHR 断点。  DevTools 暂停 XHR 运行该方法的代码 `send()` 行。  

> [!NOTE]
> 此功能还适用于提取 [API][MDNFetchApi] 请求。  

当网页请求的 URL 不正确，并且您希望快速找到导致错误请求的 AJAX 或 Fetch 源代码时，这非常有用的一个示例。  

若要设置 XHR 断点，  

1.  选择 **"源"** 工具。  
1.  展开 **XHR 断点** 面板。  
1.  选择 **"添加断点"。**  
1.  输入要中断的字符串。  当此字符串存在于 XHR 请求 URL 中的任何位置时，DevTools 将暂停。  
1.  选择 `Enter` 以确认。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png" alt-text="创建 XHR 断点" lightbox="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png":::
       创建 XHR 断点  
    :::image-end:::  
    
## <a name="event-listener-breakpoints"></a>事件侦听器断点  

当你想要暂停在触发事件后运行的事件侦听器代码时，请使用事件侦听器断点。  可以选择特定事件，例如 `click` ，或事件类别，如所有鼠标事件。  

1.  选择 **"源"** 工具。  
1.  展开 **"事件侦听器断点"** 面板。  DevTools 显示事件类别的列表，如 **动画**。  
1.  检查其中一个类别以在触发该类别的任何事件时暂停，或者展开类别并检查特定事件。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png" alt-text="创建事件侦听器断点" lightbox="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png":::
       创建事件侦听器断点  
    :::image-end:::  
    
## <a name="exception-breakpoints"></a>异常断点  

当你想要暂停引发捕获或不捕获异常的代码行时，请使用异常断点。  

1.  选择 **"源"** 工具。  
1.  选择 **"在异常时暂停** ![ " ("在异常上暂停 ][ImagePauseOnExceptionsIcon] ") 。  图标在启用时变为蓝色。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-pause-on-exceptions.msft.png" alt-text=""暂停异常"按钮" lightbox="../media/javascript-sources-page-js-pause-on-exceptions.msft.png":::
       " **暂停异常"** 按钮  
    :::image-end:::  
    
1.  **可选**。  如果除了 **未** 捕获的异常之外，还希望暂停捕获的异常，请选中"暂停捕获的异常"复选框。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-paused-on-exception.msft.png" alt-text="在未捕获的异常上暂停" lightbox="../media/javascript-sources-page-js-paused-on-exception.msft.png":::
       在未捕获的异常上暂停  
    :::image-end:::  
    
## <a name="function-breakpoints"></a>函数断点  

在想要在运行特定函数时暂停时，运行要调试的命令、函数 `debug(method)` `method` 或方法。  你可以像语句 `debug()` (插入代码 `console.log()`) ，也可以从 DevTools 控制台运行该方法。  `debug()` 等效于在函数 [的第](#line-of-code-breakpoints) 一行上设置代码行断点。  

```javascript
function sum(a, b) {
    let result = a + b; // DevTools pauses on this line.
    return result;
}
debug(sum); // Pass the function object, not a string.
sum();
```  

### <a name="make-sure-the-target-function-is-in-scope"></a>确保目标函数在范围内  

如果要调试的函数不在范围内，DevTools `ReferenceError` 将引发一个。  

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

如果从 DevTools 控制台运行方法，确保目标函数在作用域内是一件 `debug()` 很复杂的事情。  下面是一个策略：  

1.  在 [函数位于](#line-of-code-breakpoints) 范围中的某一位置设置代码行断点。
1.  触发断点。  
1.  当代码仍暂停在代码行断点上时，在 `debug()` DevTools 控制台中运行该方法。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImagePauseOnExceptionsIcon]: ../media/pause-on-exceptions-icon.msft.png  

<!-- links -->  

[DevtoolsJavascriptIndex]: index.md "开始在 Microsoft Edge DevTools |Microsoft Docs"  

[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "获取 API |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/breakpoints)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
