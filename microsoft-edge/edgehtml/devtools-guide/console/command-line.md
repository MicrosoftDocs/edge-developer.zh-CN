---
description: 使用控制台命令行与正在运行的页面交互
title: DevTools - 控制台 - 命令行
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 控制台命令行
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d7ea2bef9fa0014e4d61745636a06d508565df91
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232276"
---
# 控制台命令行

使用控制台命令行查看和更改页面上的值并同时执行调试代码，同时利用Visual Studio IntelliSense [*代码完成*](/visualstudio/ide/javascript-intellisense) 。 

只需在命令行提示符处输入任何有效的 JavaScript，然后按 `Enter` 以执行。 对于多行输入 `Shift+Enter` ，用于添加换行符。 使用箭头 `Up` `Down` 键导航到当前 DevTools 会话期间输入的上一个控制台命令。 除了标准 JavaScript 和 [控制台 API](./console-api.md)之外，控制台还支持以下命令：

 - [选择 DOM 对象](#dom-selectors)
 - [检查对象属性](#object-inspection)
 - [查找给定对象上的所有事件侦听器](#event-listeners)

在命令行中输入的脚本将执行当前选定[](/scripting/javascript/advanced/variable-scope-javascript)窗口的全局范围，除非页面在断点处暂停。 暂停页面时输入的控制台命令将在调用堆栈中的当前函数[](/scripting/javascript/advanced/variable-scope-javascript)的本地范围内执行。

控制台 **在控制台输出** 区域正上方有一个目标执行上下文下拉列表。 默认选择是顶级文档 **，_top。** 文档或运行扩展的任何 iframe 也将显示为选项，从而允许您在这些范围内交替运行命令。

## DOM 选择器
这些控制台选择器提供了简单的简写，用于快速访问 DOM 中的对象：

### $ (*CSS 选择器字符串) *
返回文档中与指定的 [CSS](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  选择器匹配的第一个元素 (或逗号分隔的选择器组) 字符串。 [document.querySelector (的简写。） ](https://developer.mozilla.org/docs/Web/API/Document/querySelector)

示例：打开控制台并键入 `$('#main')` 以返回此页面上的 div `id='main'` 对象。

!["$"选择器的示例使用](../media/console_cmd_$.png)

### $$ (*CSS 选择器字符串) *
返回文档中与指定的 [CSS](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  选择器匹配的元素数组 (或逗号分隔的选择器组) 字符串。 [document.querySelectorAll () 的简写](https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll)。

示例：打开控制台并键入以返回此 `$$('.container')` 页上包含 `class='container'` 的所有 div 对象。

!["$$"选择器的示例使用](../media/console_cmd_$$.png)

### $0、$1、$2,...
返回"元素"面板中选定的[****](../elements.md)最后一个元素，其中表示当前选定的项，是之前选定的项， `$0` `$1` 等等。

示例：打开"元素"选项卡上的**** DevTools，按以激活 Select 元素工具，然后使用鼠标单击此页上 `CTRL + B` 的某个区域。 **** 现在打开控制台并键入 `$0` 以返回你刚刚单击的元素。

!["$0"选择器的示例使用](../media/console_cmd_$0.png)

### $x (*XPath 表达式) *
返回与指定的 [XPath](https://developer.mozilla.org/docs/Introduction_to_using_XPath_in_JavaScript) 表达式匹配的元素数组。 

示例：打开控制台并键入以返回此页上包含属性 `$x('//script[@defer]')` `<script>` 的所有 `defer` 元素。

!["$x"选择器的示例使用](../media/console_cmd_$x.png)

## 对象检查

这些命令提供了快速检查对象属性的方法。 指定的对象必须在全局命名空间或调试器的当前作用域中定义。

### 目录 (*对象) *
返回指定对象的属性的树视图列表。

示例：打开控制台并键入以查看表示此页面 `dir(document)` 的文档对象的对象属性。

!["dir"方法的示例使用](../media/console_cmd_dir.png)

### 键 (*对象) *
返回附加到指定对象的属性名称的数组。

示例：打开控制台并键入以返回在全局窗口对象上 `keys(window)` 定义的所有属性。

!["keys"方法的示例使用](../media/console_cmd_keys.png)

### 值 (*对象) *
返回附加到指定对象的属性值数组。

示例：打开控制台并键入以返回在全局窗口对象上 (`values(window)` 键) 的所有属性值。

!["values"方法的示例使用](../media/console_cmd_values.png)

## 事件侦听器

此命令允许您检查注册到给定对象的事件侦听器。 指定的对象必须在全局命名空间或调试器的当前作用域中定义。

### getEventListeners (*对象) *
返回一个对象，该对象包含给定对象上每个已注册事件类型的键。 每个键的值是一组事件侦听器及其相关信息。 

示例：打开控制台并键入以查看在此页的文档对象上注册 `getEventListeners(document)` 的所有事件侦听器。

!["getEventListeners"方法的示例使用](../media/console_cmd_getEventListeners.png)
