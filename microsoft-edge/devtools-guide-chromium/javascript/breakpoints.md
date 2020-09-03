---
description: 了解你可以在 Microsoft Edge DevTools 中暂停代码的所有方式。
title: 如何在 Microsoft Edge DevTools 中暂停带有断点的代码
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 95aba99c2cfe87f26704faa20964ace5d2abdf51
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992805"
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







# 如何在 Microsoft Edge DevTools 中暂停带有断点的代码   



使用断点暂停你的 JavaScript 代码。  本指南介绍 DevTools 中可用的每种类型的断点以及何时使用以及如何设置每种类型。  有关调试过程的动手教程，请参阅 [Microsoft Edge DevTools 中的调试 JavaScript 入门][DevtoolsJavascriptIndex]。  

## 有关何时使用每个断点类型的概述   

最著名的断点类型是代码行。  但是，设置代码行的断点可能效率较低，尤其是当你不知道确切的查找位置时，或者如果你使用的是大型代码库。  通过了解如何以及何时使用其他类型的断点，你可以在调试时节省时间。  

| 断点类型 | 如果要暂停，请使用此操作 .。。  |  
|:--- |:--- |  
| [代码行](#line-of-code-breakpoints) | 在确切的代码区域中。  |  
| [条件代码行](#conditional-line-of-code-breakpoints) | 在确切的代码区域中，但仅在某些其他条件为 true 时。  |  
| [DOM](#dom-change-breakpoints) | 更改或删除特定的 DOM 节点或子级的代码。  |  
| [XHR](#xhrfetch-breakpoints) | 当 XHR URL 包含字符串模式时。  |  
| [事件侦听器](#event-listener-breakpoints) | 在事件（如）之后运行的代码上 `click` 运行。  |  
| [异常](#exception-breakpoints) | 在引发已捕获或未捕获异常的代码行上。  |  
| [函数](#function-breakpoints) | 每当运行特定的命令、函数或方法时。  |  

## 代码行断点   

当你知道需要调查的确切代码区域时，请使用代码行断点。  在运行此行代码之前，DevTools 始终暂停。  

在 DevTools 中设置代码行断点：  

1.  单击 " **源** " 选项卡。  
1.  打开包含要中断的代码行的文件。  
1.  转到代码行。  
1.  代码行左侧是 "行号" 列。  单击它。  "行号" 列旁边将显示一个红色图标。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoint-30.msft.png" alt-text="代码行断点" lightbox="../media/javascript-sources-page-js-breakpoint-30.msft.png":::
       代码行断点  
    :::image-end:::  
    
### 代码中的代码行断点   

`debugger`从代码中运行该方法以在该行上暂停。  这等效于 [代码行断点](#line-of-code-breakpoints)，只不过断点是在代码中设置的，而不是在 DevTools UI 中设置的。  

```javascript
console.log('a');
console.log('b');
debugger;
console.log('c');
```  

### 条件代码行断点   

当你知道需要调查的确切代码区域时，请使用条件代码行断点，但只希望在其他某些条件为 true 时暂停。  

设置条件代码行断点：  

1.  单击 " **源** " 选项卡。  
1.  打开包含要中断的代码行的文件。  
1.  转到代码行。  
1.  代码行左侧是 "行号" 列。  右键单击行号。  
1.  选择 " **添加条件断点**"。  将在代码行下方显示一个对话框。  
1.  在对话框中输入条件。  
1.  按 `Enter` 激活断点。  "行号" 列旁边的图标。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-conditional-breakpoint.msft.png" alt-text="条件代码行断点" lightbox="../media/javascript-sources-page-js-conditional-breakpoint.msft.png":::
       条件代码行断点  
    :::image-end:::  
    
### 管理代码行断点   

使用 " **断点** " 窗格从单个位置禁用或删除代码行断点。  

:::image type="complex" source="../media/javascript-sources-page-js-breakpoints-16-33.msft.png" alt-text=""断点" 面板" lightbox="../media/javascript-sources-page-js-breakpoints-16-33.msft.png":::
   " **断点** " 面板  
:::image-end:::  

*   选中某个条目旁边的复选框以禁用该断点。  
*   右键单击某个条目以删除该断点。  
*   右键单击 " **断点** " 窗格中的任意位置可停用所有断点、禁用所有断点或删除所有断点。  禁用所有断点相当于取消选中每一个断点。  停用所有断点指示 DevTools 忽略所有代码行断点，但同时保持已启用状态，以便每个断点在重新激活时保持相同的状态。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png" alt-text=""断点" 窗格中已停用的断点" lightbox="../media/javascript-sources-page-js-breakpoints-deactivate-breakpoints.msft.png":::
       " **断点** " 窗格中已停用的断点  
    :::image-end:::  
    
## DOM 更改断点   

如果要在更改了 DOM 节点或子级的代码上暂停，请使用 DOM 更改断点。  

设置 DOM 更改断点：  

1.  单击 " **元素** " 选项卡。  
1.  转到要在其上设置断点的元素。  
1.  右键单击该元素。  
1.  将鼠标悬停 **在 "中断"**，然后选择 " **子树修改**"、" **属性修改**" 或 " **节点删除**"。  
    
    :::image type="complex" source="../media/javascript-elements-break-on-subtree-modifications.msft.png" alt-text="用于创建 DOM 更改断点的上下文菜单" lightbox="../media/javascript-elements-break-on-subtree-modifications.msft.png":::
       用于创建 DOM 更改断点的上下文菜单  
    :::image-end:::  
    
### DOM 的类型更改断点   

*   **子树修改**。  当删除或添加当前选定节点的子节点时，或者子元素的内容发生更改时触发。  不会在子节点属性更改或对当前选定节点的任何更改上触发。  
*   **属性修改**：当在当前选定的节点上添加或删除属性时，或者当属性值发生更改时触发。  
*   **节点删除**：在删除当前选定的节点时触发。  
    
## XHR/Fetch 断点   

如果你希望在 XHR 的请求 URL 包含指定的字符串时中断，请使用 XHR 断点。  DevTools 将在 XHR 运行该方法的代码行上暂停 `send()` 。  

> [!NOTE]
> 此功能还适用于 [获取 API][MDNFetchApi] 请求。  

这样做很有用的一个示例是，当你看到你的页面请求不正确的 URL 时，你希望快速找到导致错误请求的 AJAX 或提取源代码。  

设置 XHR 断点：  

1.  单击 " **源** " 选项卡。  
1.  展开 " **XHR 断点** " 窗格。  
1.  单击 " **添加断点**"。  
1.  输入要在其上中断的字符串。  当此字符串出现在 XHR 请求 URL 中的任何位置时，DevTools 暂停。  
1.  按 `Enter` 以确认。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png" alt-text="创建 XHR 断点" lightbox="../media/javascript-sources-page-js-xhr-fetch-breakpoints-org.msft.png":::
       创建 XHR 断点  
    :::image-end:::  
    
## 事件侦听器断点 

如果要在激发事件后运行的事件侦听器代码上暂停，请使用事件侦听器断点。  你可以选择特定事件，例如事件的类别，如 `click` 所有鼠标事件。  

1.  单击 " **源** " 选项卡。  
1.  展开 " **事件侦听器断点** " 窗格。  DevTools 显示事件类别的列表，例如 **动画**。  
1.  选中其中一个类别，以便在触发来自该类别的任何事件时暂停，或者展开类别并检查特定事件。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png" alt-text="创建事件侦听器断点" lightbox="../media/javascript-sources-page-js-event-listener-breakpoints-device-deviceorientation.msft.png":::
       创建事件侦听器断点  
    :::image-end:::  
    
## 异常断点   

当你希望在引发已捕获或未捕获异常的代码行上暂停时，请使用异常断点。  

1.  单击 " **源** " 选项卡。  
1.  单击 " **异常时暂停"** (![ "异常时暂停" ][ImagePauseOnExceptionsIcon] \ ) 。  启用时图标变为蓝色。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-pause-on-exceptions.msft.png" alt-text=""在例外时暂停" 按钮" lightbox="../media/javascript-sources-page-js-pause-on-exceptions.msft.png":::
       " **在例外时暂停"** 按钮  
    :::image-end:::  
    
1.  **可选**。  如果你还希望在捕获异常时（除了未捕获的异常）上暂停，请选中 " **捕获异常时暂停** " 复选框。  
    
    :::image type="complex" source="../media/javascript-sources-page-js-paused-on-exception.msft.png" alt-text="已暂停未捕获的异常" lightbox="../media/javascript-sources-page-js-paused-on-exception.msft.png":::
       已暂停未捕获的异常  
    :::image-end:::  
    
## 函数断点   

`debug(method)`如果要在运行特定函数时暂停，请运行该方法，其中 `method` 是要调试的命令、函数或方法。  你可以在 `debug()` 代码中插入 (，如 `console.log()` 语句) 或从 DevTools 控制台运行该方法。  `debug()` 等效于在函数的第一行上设置 [代码行断点](#line-of-code-breakpoints) 。  

```javascript
function sum(a, b) {
    let result = a + b; // DevTools pauses on this line.
    return result;
}
debug(sum); // Pass the function object, not a string.
sum();
```  

### 请确保目标函数在范围内   

`ReferenceError`如果要调试的函数不在作用域内，DevTools 会引发 a。  

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

如果从 DevTools 控制台运行该方法，确保目标函数在范围内非常复杂 `debug()` 。  下面是一个策略：  

1.  在函数在范围中的某个位置设置 [代码行断点](#line-of-code-breakpoints) 。
1.  触发断点。  
1.  `debug()`在 DevTools 控制台中运行该方法，同时代码在代码行断点处仍处于暂停状态。  
    
<!---  
 


-->  

<!-- image links -->  

[ImagePauseOnExceptionsIcon]: ../media/pause-on-exceptions-icon.msft.png  

<!-- links -->  

[DevtoolsJavascriptIndex]: index.md "开始使用 Microsoft Edge DevTools 中的 JavaScript 调试 |Microsoft 文档"  

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
