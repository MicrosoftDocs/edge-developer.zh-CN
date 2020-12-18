---
description: 使用控制台 API 以编程方式调试和配置文件代码
title: DevTools - 控制台 - 控制台 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 控制台 api
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 46a74b80b504358ff7dbea40970528c8e2b228cf
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232152"
---
# 主机 API

控制台 *API* 通过全局对象提供对 DevTools 控制台的命令行和编程访问， `console` 从而允许您：

 - [记录代码中的](#logging-custom-messages) 自定义消息
 - [检查对象和元素并](#inspecting-objects-and-elements) 记录其信息
 - [通过设置断言、](#testing-and-measuring) 计时器和计数器测试和测量代码
 - [获取堆的快照](#taking-heap-snapshots) ，以评估运行代码的内存消耗并确定内存泄漏
 - [跟踪调用堆栈](#tracing-callstacks) ，了解从何处调用代码 
 - [组织日志输出](#organizing-log-output) 以简化调试

以下是 Microsoft Edge 当前支持的命令和格式参数。 它们在主要浏览器上类似地工作。

## 记录自定义消息

代码可以将多种类型的自定义消息发送到控制台，包括：

消息类型  | &nbsp;   |
:------------------- | :------ |
[**error () **](https://developer.mozilla.org/docs/Web/API/Console/error) and [ **exception () **](https://developer.mozilla.org/docs/Web/API/Console/error)| 严重错误和故障
[**warn () **](https://developer.mozilla.org/docs/Web/API/Console/warn) | 可能的错误或意外行为 
[**info () **](https://developer.mozilla.org/docs/Web/API/Console/info) | 有用但非关键的信息
[**log () **](https://developer.mozilla.org/docs/Web/API/Console/log) and [ **debug () **](https://developer.mozilla.org/docs/Web/API/Console/log) | 常规调试 (控制台中生成系统警报图标) 

   
你可以对这些信息进行分组和筛选，以及从控制台面板中从 Microsoft Edge 生成的其他消息。 所有自定义邮件方法都需要一个字符串 (消息) 可选格式替换参数。 Microsoft Edge 支持以下格式选项：

Format 参数 | &nbsp;
:------------------- | :--- |
**%b** | 二进制文件
**%c** | 内联 CSS 样式 (请参阅下面的示例) 
**%d** **、%i** | 整型 
**%f** | Float  
**%s** | 字符串 
**%x** | 十六进制 
**%e** | Exponent 

例如，下面显示了如何在日志消息中包括字符串和整数变量：

```javascript
var myText = 'pieces';
var myVal = 5;
console.log("The number of %s is %d.", myText, myVal);
```

>`The number of pieces is 5.`

下面介绍如何将绿色突出显示效果添加到具有内联 CSS `%c` () ：

```javascript
console.log("%cHighlight this log message in green", "background-color: #10ff00; text-transform: uppercase;");
```

![具有内联样式的控制台日志](../media/console_api_css.png)

## 检查对象和元素

可检查对象显示在具有可展开节点的折叠树视图中的控制台中。 控制台检测是发送 DOM 节点 (div) 还是 JavaScript 对象 (如事件) ，并自动将其显示为检测到的类型。

还可以强制特定输出：

命令 | &nbsp;
:------------------- | :--- |
[**dir () **](https://developer.mozilla.org/docs/Web/API/Console/dir) | 显示为可检查的 JavaScript 对象
[**dirxml () **](https://developer.mozilla.org/docs/Web/API/Console/dirxml) | 显示为可检查 DOM 节点

例如，尝试打开控制台并比较此页面上 `<div id='main'>` 元素的以下输出：

```javascript
console.dir(document.querySelector('#main'));
console.dirxml(document.querySelector('#main'));
```

!["dir"与"dirxml"输出的比较](../media/console_api_dir.png)

### 选择"元素" **面板中的** 元素

可以直接从控制台中选择页面的 HTML 树上下文中的元素，以便立即进行布局和样式调试。

命令 | &nbsp;
:------------------- | :--- |
**选择 () ** | 切换到元素 **面板** ，将焦点设置到指定的元素。

例如，如果在此页面上打开控制台并键入：

```javascript
console.select(document.querySelector("body"));
```

如果 DevTools 尚未 (，它将切换到"元素"面板) 将[*HTML*](../elements.md#html-tree-view)树视图中的焦点设置为指定的元素。 ****

!["select"方法的示例](../media/console_api_select.png)

## 测试和衡量

### 测试代码

将控制台 API 测试断言添加到代码中，以便当代码在浏览器中运行时进行单元测试和调试。

命令 | &nbsp;
:------------ | :-------------
[**assert () **](https://developer.mozilla.org/docs/Web/API/Console/assert) | 如果提供的表达式计算结果为 *false，* 则记录控制台错误消息。

除了作为可测试断言提供的逻辑表达式之外，还可以添加可选消息和格式参数，就像用于其他自定义控制台 [消息一样](#logging-custom-messages)。 例如：

```javascript
var x = 26.8;
console.assert(x < 25, 'The value of x is %f (it is NOT less than %i)', x, 25);
```

!["assert"方法的示例](../media/console_api_assert.png)

### 计算代码中的执行次数

可以在代码中设置计数器，以跟踪周围代码的执行次数。 设置计数器有助于确保代码如期运行，并帮助您诊断性能瓶颈。

命令 | &nbsp;
:------------ | :-------------
[**count () **](https://developer.mozilla.org/docs/Web/API/Console/count) | 为给定标签增加并记录 ( *次数 * 。
[**countReset () **](https://developer.mozilla.org/docs/Web/API/Console/countReset) | 将给定计数器标签的计数重置为零。

例如，在控制台中执行以下行：

```javascript
console.count('My Counter');
console.count('My Counter');
console.countReset('My Counter');
console.count('My Counter');
```

 . . . 将导致：
> 我的计数器：1

### 对代码进行计时

使用标记的计时器检测代码，以测量完成给定操作所花的时间。

命令 | &nbsp;
:------------ | :-------------
[**time () **](https://developer.mozilla.org/docs/Web/API/Console/time) | 使用给定标签启动计时器。
[**timeEnd () **](https://developer.mozilla.org/docs/Web/API/Console/timeEnd) | 使用给定标签结束计时器，并报告已用时间 (毫秒) 。
[**timeStamp () **](https://developer.mozilla.org/docs/Web/API/Console/timeStamp) | 报告当前系统的时间 (毫秒) 。

例如，请尝试在控制台中执行以下行：

```javascript
console.time('My Timer');
console.timeEnd('My Timer');
```

### 获取堆快照

获取堆的快照，以评估运行代码的内存消耗并确定内存泄漏。

命令 | &nbsp;
:------------ | :-------------
**takeHeapSnapshot () ** | 捕获有关当前 JavaScript 堆及其已分配对象的详细信息。

必须运行 DevTools [](../memory.md#toolbar)内存探查器才能获取堆快照。 每个快照将在"内存"面板的 [*"快照"摘要*](../memory.md#snapshot-summary) 中显示为 [**磁贴，以**](../memory.md) 进一步检查。

## 跟踪调用代码

了解代码的调用位置、正在运行的代码以及执行所花的时间在分析速度慢或意外行为时可能很有用。 堆栈跟踪显示代码从跟踪请求向上到达路径时所经过的执行路径。 

命令 | &nbsp;
:------------ | :-------------
[**trace () **](https://developer.mozilla.org/docs/Web/API/Console/trace) | 输出当前脚本执行调用堆栈的跟踪。

例如，在控制台中运行以下代码：

```javascript
function a(){
  c();
}
function b(){
  c();
}
function c(){
  console.trace()
}
function d(){
  b();
}

a();
d();
```

. . . 将输出以下堆栈跟踪：
>  (eval code：8：3) at a (eval code：2：3) at eval code (eval code：14：1) 的 console. ( trace () 
> 
> console.trace () at c (eval code：8：3) at b (eval code：5：3) at d (eval code：11：3) at eval code (eval code：15：1) 

## 组织日志输出

若要清除所有以前的控制台输出，请使用 *console.clear () * (或 `CTRL + L`) 。 这不会清除控制台命令历史记录的后退 (你仍可以使用向上和向下箭头键遍历它) 。

命令 | &nbsp;
:------------ | :-------------
[**clear () **](https://developer.mozilla.org/docs/Web/API/Console/clear) | 清除所有以前的控制台输出。

如果代码输出大量控制台消息，可以使用以下命令直观地将它们组织到嵌套块中：

 命令 | &nbsp;
:------------ | :-------------
[**group () **](https://developer.mozilla.org/docs/Web/API/Console/group) | 使用指定的可选 (开始控制台输出的新嵌套) 级别。
[**groupCollapsed () **](https://developer.mozilla.org/docs/Web/API/Console/groupCollapsed) | 为具有指定 (可选) 标签的控制台输出启动新的嵌套级别，但分组控件默认为折叠，并且必须通过单击箭头控件) 来展开 (以显示子输出。
[**groupEnd () **](https://developer.mozilla.org/docs/Web/API/Console/groupEnd) | 结束指定标签的嵌套组。

例如，尝试在控制台中输入以下命令：

```javascript
console.groupCollapsed('Group 1');
console.log('In Group 1');
console.groupCollapsed('Group 1.1');
console.log('In Group 1.1');
console.groupEnd('Group 1.1');
console.groupEnd('Group 1');
console.log('No longer in a group');
```

. . . 然后展开组 *1* 和 *组 1.1* 控件以查看日志注释的嵌套方式：

![对控制台中的邮件进行分组](../media/console_api_group.png)

有时，以表格形式可视化 JavaScript 对象或数组简单列表。 为此，可以使用 *console.table () * 命令：

命令 | &nbsp;
:------------ | :-------------
[**table () **](https://developer.mozilla.org/docs/Web/API/Console/table) | 以表格形式将提供的数组或对象输出到控制台。

例如，以下对象数组：

```javascript
var orders = [{'Size':'XL', 'Quantity':1},{'Size':'M', 'Quantity':3}, {'Size':'L', 'Quantity':2}];
console.table(orders);
```

. . . 将在控制台中呈现为此表：

![在控制台中将对象数组显示为表](../media/console_api_table.png)
