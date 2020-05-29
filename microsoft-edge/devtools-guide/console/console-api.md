---
description: 使用控制台 API 以编程方式调试和分析你的代码
title: DevTools-控制台 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、控制台 api
ms.custom: seodec18
ms.openlocfilehash: d722934c3694c3c23e367141158ad45f6d03b175
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564328"
---
# 控制台 API

*控制台 API*通过全局对象提供对 DevTools 控制台的命令行和编程访问 `console` ，使你可以：

 - 记录来自你的代码的[自定义消息](#logging-custom-messages)
 - [检查对象和元素](#inspecting-objects-and-elements)并记录其信息
 - 通过设置断言、计时器和计数器来[测试和测量代码](#testing-and-measuring)
 - [获取堆的快照](#taking-heap-snapshots)以评估运行代码的内存占用并确定内存泄漏
 - [跟踪你的 callstacks](#tracing-callstacks)以了解你的代码的调用位置 
 - [整理日志输出](#organizing-log-output)以简化调试

以下是 Microsoft Edge 当前支持的命令和格式设置参数。 它们在主要浏览器上的工作方式类似。

## 记录自定义消息

你的代码可以向控制台发送多种类型的自定义消息，包括：

消息类型  | &nbsp;   |
:------------------- | :------ |
[**错误（）**](https://developer.mozilla.org/docs/Web/API/Console/error)和[**异常（）**](https://developer.mozilla.org/docs/Web/API/Console/error)| 关键错误和故障
[**警告（）**](https://developer.mozilla.org/docs/Web/API/Console/warn) | 可能的错误或意外行为 
[**info （）**](https://developer.mozilla.org/docs/Web/API/Console/info) | 有用但不重要的信息
[**log （）**](https://developer.mozilla.org/docs/Web/API/Console/log)和[ **debug （）**](https://developer.mozilla.org/docs/Web/API/Console/log) | 常规调试（不在控制台中生成系统警报图标）

   
您可以将这些邮件与从 "控制台" 面板中的 Microsoft Edge 生成的其他邮件组合在一起并进行筛选。 所有自定义邮件方法都需要字符串（message）参数和可选的格式替换参数。 Microsoft Edge 支持下列格式设置选项：

格式参数 | &nbsp;
:------------------- | :--- |
**% b** | 二进制文件
**% c** | 内联 CSS 样式（请参阅下面的示例）
**% d**， **% i** | 整型 
**% f** | Float  
**% s** | 字符串 
**% x** | 十六进制数 
**% e** | 加 

例如，下面介绍了如何在日志消息中包含字符串和整数变量：

```javascript
var myText = 'pieces';
var myVal = 5;
console.log("The number of %s is %d.", myText, myVal);
```

>`The number of pieces is 5.`

下面介绍了如何使用内联 CSS （）向日志消息添加绿色突出显示效果 `%c` ：

```javascript
console.log("%cHighlight this log message in green", "background-color: #10ff00; text-transform: uppercase;");
```

![带有内联样式的控制台日志](../media/console_api_css.png)

## 检查对象和元素

Inspectable 对象在具有可展开节点的折叠树视图中显示在控制台中。 控制台检测你是要发送的是 DOM 节点（如 div）还是 JavaScript 对象（如事件），并自动将其显示为检测到的类型。

您还可以强制执行特定输出：

命令 | &nbsp;
:------------------- | :--- |
[**dir （）**](https://developer.mozilla.org/docs/Web/API/Console/dir) | 显示为 inspectable JavaScript 对象
[**dirxml()**](https://developer.mozilla.org/docs/Web/API/Console/dirxml) | 显示为 inspectable DOM 节点

例如，尝试打开控制台并比较 `<div id='main'>` 此页面上的元素的以下输出：

```javascript
console.dir(document.querySelector('#main'));
console.dirxml(document.querySelector('#main'));
```

!["Dir" 与 "dirxml" 输出的比较](../media/console_api_dir.png)

### 在 "**元素**" 面板中选择一个元素

你可以直接从控制台选择页面的 HTML 树上下文中的元素，以便立即进行布局和样式调试。

命令 | &nbsp;
:------------------- | :--- |
**select （）** | 切换到 "**元素**" 面板，并将焦点设置到指定的元素。

例如，如果您在此页面上打开控制台，请键入：

```javascript
console.select(document.querySelector("body"));
```

DevTools 将切换到 "元素" 面板（如果它尚不是当前**元素**），并将焦点放在[*HTML 树视图*](../elements.md#html-tree-view)中的指定元素。

!["Select" 方法的示例](../media/console_api_select.png)

## 测试和测量

### 测试代码

将控制台 API 测试声明添加到你的代码中，以便在浏览器中运行单元测试和调试代码。

命令 | &nbsp;
:------------ | :-------------
[**assert （）**](https://developer.mozilla.org/docs/Web/API/Console/assert) | 如果所提供的表达式的计算结果为*false*，则记录一个控制台错误消息。

除了作为可测试断言提供的逻辑表达式外，你还可以添加可选消息和格式参数，就像使用其他[自定义控制台消息](#logging-custom-messages)一样。 例如：

```javascript
var x = 26.8;
console.assert(x < 25, 'The value of x is %f (it is NOT less than %i)', x, 25);
```

!["Assert" 方法的示例](../media/console_api_assert.png)

### 统计代码中的执行次数

你可以在你的代码中设置计数器以跟踪已执行前后代码的次数。 设置计数器有助于确保你的代码按预期运行，并帮助你诊断性能瓶颈。

命令 | &nbsp;
:------------ | :-------------
[**count （）**](https://developer.mozilla.org/docs/Web/API/Console/count) | 增量和记录已执行给定标签的次数*计数（）* 。
[**countReset()**](https://developer.mozilla.org/docs/Web/API/Console/countReset) | 将给定计数器标签的计数重置为零。

例如，在控制台中执行以下行：

```javascript
console.count('My Counter');
console.count('My Counter');
console.countReset('My Counter');
console.count('My Counter');
```

 . . . 将导致：
> 我的计数器：1

### 对代码计时

使用带有标签的计时器检测代码，以测量完成给定操作所需的时间。

命令 | &nbsp;
:------------ | :-------------
[**时间（）**](https://developer.mozilla.org/docs/Web/API/Console/time) | 启动具有给定标签的计时器。
[**timeEnd()**](https://developer.mozilla.org/docs/Web/API/Console/timeEnd) | 结束带有给定标签的计时器，并报告已用时间（以毫秒为单位）。
[**timeStamp （）**](https://developer.mozilla.org/docs/Web/API/Console/timeStamp) | 报告当前系统时间（以毫秒为单位）。

例如，请尝试在控制台中执行以下行：

```javascript
console.time('My Timer');
console.timeEnd('My Timer');
```

### 获取堆快照

获取堆的快照，以评估运行代码的内存占用并确定内存泄漏。

命令 | &nbsp;
:------------ | :-------------
**takeHeapSnapshot()** | 捕获有关当前 JavaScript 堆及其分配的对象的详细信息。

DevTools[内存探查器](../memory.md#toolbar)必须运行才能获取堆快照。 每个快照将在 "[**内存**](../memory.md)" 面板的 "[*快照摘要*](../memory.md#snapshot-summary)" 中显示为一个磁贴，以便进一步检查。

## 跟踪 callstacks

了解代码的调用位置、正在运行的代码，以及执行时间在分析 slowness 或意外行为时可能会很有用。 堆栈跟踪显示你的代码为到达它所需的执行路径，从跟踪请求向上遍历路径。 

命令 | &nbsp;
:------------ | :-------------
[**trace （）**](https://developer.mozilla.org/docs/Web/API/Console/trace) | 输出当前脚本执行调用堆栈的跟踪。

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
> 位于 c （eval 代码：8：3）（eval 代码：2：3）（eval 代码：14：1）处的 console、trace （）
> 
> 在 c （eval 代码：8：3）处的 c （eval 代码：5：3）在 eval （eval 代码：11：3）的 eval 代码（eval 代码：15：1）处的 trace （）

## 组织日志输出

若只需清除以前的所有控制台输出，请使用*console。 clear （）* （或 `CTRL + L` ）。 这不会清除您的控制台命令历史记录的 backstack （您仍可以用向上和向下箭头键遍历它）。

命令 | &nbsp;
:------------ | :-------------
[**clear （）**](https://developer.mozilla.org/docs/Web/API/Console/clear) | 清除以前的所有控制台输出。

如果你的代码输出了大量的控制台消息，你可以使用以下命令直观地将它们组织到嵌套块中：

 命令 | &nbsp;
:------------ | :-------------
[**group （）**](https://developer.mozilla.org/docs/Web/API/Console/group) | 使用指定的（可选）标签为控制台输出启动新的嵌套级别。
[**groupCollapsed()**](https://developer.mozilla.org/docs/Web/API/Console/groupCollapsed) | 使用指定的（可选）标签启动控制台输出的新嵌套层嵌套，但是分组控件在默认情况下处于折叠状态，并且必须展开（通过单击箭头控件）才能显示子输出。
[**groupEnd()**](https://developer.mozilla.org/docs/Web/API/Console/groupEnd) | 结束指定标签的嵌套组。

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

. . . 然后展开*组 1*和*组 1.1*控件以查看日志注释的嵌套方式：

![对控制台中的邮件进行分组](../media/console_api_group.png)

有时，使用表格形式（而不是简单列表）可视化 JavaScript 对象或数组更容易。 为此，你可以使用*console for table （）* 命令：

命令 | &nbsp;
:------------ | :-------------
[**table （）**](https://developer.mozilla.org/docs/Web/API/Console/table) | 将提供的数组或对象以表格形式输出到控制台。

例如，以下对象数组：

```javascript
var orders = [{'Size':'XL', 'Quantity':1},{'Size':'M', 'Quantity':3}, {'Size':'L', 'Quantity':2}];
console.table(orders);
```

. . . 将在控制台中呈现为此表：

![在控制台中将对象数组显示为表](../media/console_api_table.png)
