---
description: 使用控制台命令行与正在运行的页面交互
title: DevTools-Console-命令行
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、控制台命令行
ms.custom: seodec18
ms.openlocfilehash: c661736e5ea264f60279c89cfa0f9c55361d2288
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564322"
---
# 控制台命令行

使用 Console 命令行查看和更改页面上的值，并在使用 Visual Studio [*IntelliSense*](/visualstudio/ide/javascript-intellisense) 自动代码完成时即时执行调试代码。 

只需在命令行提示符处输入任何有效的 JavaScript，然后按 `Enter` 执行即可。 对于多行输入，用 `Shift+Enter` 来添加换行符。 使用 `Up` 和 `Down` 箭头键浏览你在当前 DevTools 会话期间输入的上一个控制台命令。 除了标准 JavaScript 和 [控制台 API](./console-api.md)，控制台还支持以下命令：

 - [选择 DOM 对象](#dom-selectors)
 - [检查对象属性](#object-inspection)
 - [查找给定对象上的所有事件侦听器](#event-listeners)

在命令行中输入的脚本在当前所选窗口的 [全局范围](/scripting/javascript/advanced/variable-scope-javascript) 内执行，除非页面在断点处暂停。 在暂停页面时输入的控制台命令将在调用堆栈内当前函数的 [本地范围](/scripting/javascript/advanced/variable-scope-javascript) 内执行。

控制台的 " **目标** 执行上下文" 下拉列表位于 "控制台输出" 区域的正上方。 默认选择是 **_top**的顶级文档。 文档或运行扩展中的任何 iframe 也将显示为选项，使你可以在这些范围内交替运行命令。

## DOM 选择器
这些控制台选择器提供简单的 shorthands 来快速访问 DOM 中的对象：

### $ (*CSS 选择器字符串*) 
返回文档中与指定的 [CSS 选择器](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  相匹配的第一个元素 (或逗号分隔的选择器组) string。 [QuerySelector ( # B1](https://developer.mozilla.org/docs/Web/API/Document/querySelector)的速记。

示例：打开控制台并键入， `$('#main')` 以返回 `id='main'` 此页面上的 div 对象。

!["$" 选择器示例用法](../media/console_cmd_$.png)

### $ $ (*CSS 选择器字符串*) 
返回文档中与指定的 [CSS 选择器](https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Selectors)  相匹配的元素数组 (或逗号分隔的选择器组) string。 [QuerySelectorAll ( # B1](https://developer.mozilla.org/docs/Web/API/Document/querySelectorAll)的速记。

示例：打开控制台并键入， `$$('.container')` 以返回此页面上的所有 div 对象 `class='container'` 。

![使用 "$ $" 选择器的示例](../media/console_cmd_$$.png)

### $0、$1、$2,.。。
返回在 " [**元素**](../elements.md) " 面板中选择的最后一个元素，其中 `$0` 表示当前选定 `$1` 的项目，是选定项目之前的项目。

示例：打开 DevTools 到 " **元素** " 选项卡，按 `CTRL + B` 激活 " **选择元素** " 工具，然后通过鼠标单击此页面上的某些区域。 现在打开控制台，然后键入 `$0` 以返回刚刚单击的元素。

!["$0" 选择器示例用法](../media/console_cmd_$0.png)

### $x (*XPath 表达式*) 
返回由指定 [XPath](https://developer.mozilla.org/docs/Introduction_to_using_XPath_in_JavaScript) 表达式匹配的元素数组。 

示例：打开控制台并键入， `$x('//script[@defer]')` 返回 `<script>` 此页面上包含属性的所有元素 `defer` 。

![使用 "$x" 选择器的示例](../media/console_cmd_$x.png)

## 对象检查

这些命令提供了检查对象属性的快速方法。 指定的对象必须在全局命名空间中定义或在调试器的当前范围内定义。

### dir (*对象*) 
返回指定对象的属性的树视图列表。

示例：打开控制台并键入， `dir(document)` 以查看代表此页面的 document 对象的对象属性。

!["Dir" 方法的使用示例](../media/console_cmd_dir.png)

###  (*对象*) 的键
返回附加到指定对象的属性名称数组。

示例：打开控制台并键入， `keys(window)` 返回在全局窗口对象上定义的所有属性。

!["Keys" 方法的用法示例](../media/console_cmd_keys.png)

###  (*对象*) 的值
返回附加到指定对象的属性值数组。

示例：打开控制台并键入 `values(window)` ，返回在全局窗口对象上定义的所有属性 (键的值) 。

!["Values" 方法的使用示例](../media/console_cmd_values.png)

## 事件侦听器

此命令允许你检查注册到给定对象的事件侦听器。 指定的对象必须在全局命名空间中定义或在调试器的当前范围内定义。

### getEventListeners (*对象*) 
返回一个对象，其中包含给定对象上每个已注册事件类型的键。 每个键的值是一个事件侦听器数组及其相关信息。 

示例：打开 "控制台" 和 "键入" `getEventListeners(document)` 以查看此页面上的 "文档" 对象上注册的所有事件侦听器。

![使用 "getEventListeners" 方法的示例](../media/console_cmd_getEventListeners.png)
