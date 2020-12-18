---
description: 使用"性能"面板在用户交互期间分析页面的响应性
title: DevTools - 性能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， 开发工具， 性能， 配置文件， 帧速率， fps， CPU 使用率， JavaScript 执行
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 561cfe62f7db492ce3914b4daba8ccf8c0a62a8a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232143"
---
# 性能

性能 **面板** 提供用于分析和分析 UI 在用户交互过程中的响应性的工具。 通过它，你可以：

 - [测量页面](#recording-a-profile) 各个组件的执行时间 
 - [向下钻取](#timeline-ruler) 到运行页面的 CPU 周期最多的地方，以及为用户提供的结果视觉效果
 - [获取使用页面执行时间的进程](#timeline-details) 的分步细分 
 - [演练 JavaScript 调用堆栈](#javascript-call-stacks) ，以确定代价高昂的操作，例如需要布局重新计算的操作 

![DevTools 性能面板](./media/performance.png)

## 录制配置文件

分析页面性能的第一步是，当你执行特定用户方案时捕获配置文件，例如尝试修复的性能 bug 的重新说明步骤，或者你想要优化以提供更好的用户体验的典型用例。 

### 工具栏

使用**工具栏上的**"开始停止  /  ****" (或) 启动和结束 `Ctrl+E` 性能跟踪。 在"性能"选项卡上，绿色指示器**** 将闪烁以指示正在录制。 

![性能面板工具栏](./media/performance_toolbar.png)

在停止配置文件时将生成性能报告。 你可以选择将其保存到磁盘 `Ctrl+S` () ， () `Ctrl+O` 在 DevTools 中重新加载它。  DevTools 诊断会话与 *.diagsession 扩展一起* 保存。

录制配置文件时，请注意以下一些情况：

- 执行捕获尝试分析的方案所需的最最短操作。 与页面不相随的操作会产生额外的数据，并且会使结果变得混乱。

- 探查器将自动标记报告中的主要应用生命周期事件，如页面导航 [、DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded)和页面 [加载](https://developer.mozilla.org/docs/Web/Events/load)。 可以通过从代码或控制台内调用 [Performance.mark () ](https://developer.mozilla.org/docs/Web/API/Performance/mark) 方法来添加自定义标记。 

- 如果初始页面加载时间对分析非常重要，请确保从网络面板 (清除浏览器缓存) 以确保从网络加载所有[](./network.md)页面资源。

- 有时，这有助于记录多个会话和/或跨不同计算机对同一方案进行采样，以更好地了解通配符中的性能问题。

## 日程表标尺

时间线用作滑动标尺。 使用它将报告范围限制为特定时间范围， (关注的事件范围) 时间范围。 拖动黑色**幻灯片**控件以限制希望调查和筛选出日程表和[JavaScript](#javascript-call-stacks)调用堆栈报告中的外在分析数据的范围[](#timeline-details)，具体操作在"详细信息"窗格*下。* 

你将在标尺上看到两种类型的标记：

 - **时间线上的应用** 生命周期标记 (如页面导航 [、DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded)和页面 [加载) 记录](https://developer.mozilla.org/docs/Web/Events/load) 配置文件时自动记录。

 - **用户标记** 是自定义标记，你可以选择从代码或 DevTools 控制台内调用 [Performance.mark () ](https://developer.mozilla.org/docs/Web/API/Performance/mark) 方法进行 [**添加**](./console.md)。 可以使用[Performance.measure () ](https://developer.mozilla.org/docs/Web/API/Performance/measure)方法将开始标记和结束标记分组为一个命名度量值。 ** ** 

选择一个时间范围后，可以从工具栏进一步放大，或者重置缩放和**** 清除选择以**** 返回到性能跟踪视图的完整视图 (未选择任何) 。 **** 这些控件也可从右键单击上下文菜单中获得。

![性能面板时间线](./media/performance_timeline.png)

### CPU 使用率

CPU **使用率百分比** 时间线图按类别描述运行页面所需的各种浏览器子系统使用的处理资源：

#### 正在加载
指示检索应用程序资源和分析 HTML 和 CSS 所花费的时间。 这可能包括网络请求。 以下关联事件记录在 [时间线中](#timeline-details)：

事件 | 描述
:------------ | :-------------
CssParsing  | 遇到需要分析的新 CSS 内容。
HtmlParsing | 遇到需要解析为节点并插入到 DOM 的新 HTML 内容。
HttpRequest | 在 DOM 中遇到远程资源，或创建了需要进行 HTTP 请求的 XMLHttpRequest。
HtmlSpeculativeDownloading | 正在搜索页面的 HTML 内容以查找所需资源，以便尽快计划其 HTTP 请求。


#### 脚本
指示分析和执行 JavaScript 所花费的时间。 这包括 DOM 事件、计时器、脚本评估和动画帧回调。 以下关联事件记录在 [时间线中](#timeline-details)：

事件 | 描述
:------------ | :-------------
DomEvent | 在 DOM 对象上触发了事件。
EvaluatingScript | 在 `<script>` DOM 中遇到新元素，需要进行分析和执行。
EventHandler | 已触发注册的事件侦听器以响应正在触发的 DOM 事件。
帧 | 准备新帧时，触发了已注册的回调，以便它可以参与视觉更改。
测量 | 使用该方法测量了特定于应用 `performance.measure()` 的方案。
MediaQueryListener | 注册的媒体查询失效，导致在其关联的侦听器查询 () 。
MutationObserver | 修改了一个或多个观察到的 DOM 元素，这导致执行一个与一个一体机关联的回调。
TimerFired | 计划的计时器已过，导致执行其关联的回调。
WindowsRuntimeAsyncCallback | 异步操作由触发回调的 Windows 运行时对象 `Promise` 完成。
WindowsRuntimeEvent | 在触发注册侦听器的 Windows 运行时对象上触发了事件。

#### GC
指示收集不再使用的对象的内存所花费的时间。 以下关联事件记录在 [时间线中](#timeline-details)：

事件 | 描述
:------------ | :-------------
GarbageCollection | JavaScript 运行时审核应用的当前内存使用情况，以确定不再引用的对象，因此可以收集这些对象。

#### 样式设置
指示计算元素演示文稿和布局所花费的时间。 以下关联事件记录在 [时间线中](#timeline-details)：

事件 | 描述
:------------ | :-------------
AlignedBeat | 已处理对 DOM 进行挂起的视觉更改，以便可以更新应用的显示。
CssCalculation | 对 DOM 进行了更改或添加了新的 CSS 内容，要求重新计算所有受影响的元素的样式属性。
布局 | 对 DOM 进行了更改，要求计算所有受影响的元素的大小和/或位置。

#### 呈现
指示绘制屏幕所花费的时间。 以下关联事件记录在 [时间线中](#timeline-details)：

事件 | 描述
:------------ | :-------------
画图 | 对 DOM 进行了可视更改，要求重新绘制页面的所有受影响的部分。
RenderLayer | 对 DOM 文件的独立呈现片段进行了视觉更改 (称为层) 需要重新绘制页面各自的部分。

#### 图像解码
指示解压缩和解码图像所花费的时间。 以下关联事件记录在 [时间线中](#timeline-details)：

事件 | 描述
:------------ | :-------------
ImageDecoded | 图像包含在 DOM 中，需要将图像的原始格式解压缩为位图。

### 可视吞吐量

**"FPS (FPS**) 图显示分析方案（其中 60 FPS 是理想显示速率）期间估计每秒*帧数* (FPS) 。 帧速率下降表示性能瓶颈，帧速率为零意味着帧完全被丢弃。

## 时间线详细信息

使用最下层的详细信息窗格获取页面上所发生事件的完整细目。 " **日程表详细信息** "选项卡提供了各种浏览器子系统内所发生事件的细分。

![性能时间线详细信息窗格](./media/performance_details_timeline.png)

1. **事件列表排序控件**

    使用"**按下拉列表排序**"控件在开始时间或[](#event-list)持续时间之间切换事件** 列表顺序 (*包括) 。* 这还会更改所选日程表 [详细信息的视图](#selected-timeline-details)。

2. **按帧分组事件**

    使用按**** 帧切换的组顶级事件，将顶级事件 (HTML 分析、布局 *、DOM*事件等 ) 分组到其相应的工作单元 (或"frame") 中（动画/视觉更新发生期间）。 帧被视为与其他事件一样，因此可以排序/筛选它们，并提供在事件列表中单击时包含**[时间摘要](#event-list)。

3. **事件列表筛选器控件**

    使用 **"筛选器事件"** 菜单配置时间线详细信息中显示的 [事件类型](#timeline-details)。 

    ![用于筛选性能事件的控件](./media/performance_filter_events.png) 

    以下筛选器可用：

   - **图像解码**：显示在后台线程上 (的事件，例如图像解码、GC) 。 
   - **网络流量**：显示已网络绑定的 HTTP 请求。
   - **UI 活动**：显示 UI 线程和/或呈现线程上 (的事件，例如 DOM 事件处理程序、布局) 。
   - **用户度量**：显示指示对 performance.measure () 方法的调用的自定义事件。

     可以进一步按包含持续时间筛选顶级事件。

### 事件列表

事件*列表*按时间顺序列出所选时间跨度内发生的[](#cpu-utilization)浏览器子系统事件。 

单击任何条目以填充 **该项目的 Selected** 事件详细信息图表。 具有嵌套事件/函数的条目将显示其执行函数所花费的包含的** (** 时间及其调用**) 的其他任何函数，以及仅在调用函数本身的正文中花费**的独占** (时间（) 次）。

右键单击任何项以打开上下文菜单以仅筛选时间线到该事件，并查看调试器 (或元素面板中负责事件的源代码[****](./debugger.md)（如果适用) ）。 [****](./elements.md)

### 选定的日程表详细信息

" *选定的时间线详细信息* "提供了选定时间跨度内包含非独占/独占事件时间的详细条形图。 当使用事件 (*排序 *) 按持续时间排序 **时**，运行时间最长的事件将在图中直观地突出。 

### 选定的事件详细信息

此报告提供有关所选事件的详细信息，包括开始时间、执行** 线程类型 (例如，下载 *、UI、**呈现*) 以及** 特定于特定事件类型的其他上下文详细信息。 例如， *事件侦听器* 类型提供指向回调函数和计划调用 *堆栈* 的 *调试程序链接*。

## JavaScript 调用堆栈

![JavaScript 调用堆栈的性能计时](./media/performance_details_javascript.png)

JavaScript **调用堆栈** 选项卡为在选定时间范围内运行脚本函数提供 CPU 使用率信息和计时：

 列 | 描述
:------------ | :-------------
函数名称 | 浏览器或用户定义函数的名称。
非独占 CPU (%)  | 此函数和此函数调用的函数中所选 CPU 活动的百分比。
独占 CPU (%)  | 此函数中所选 CPU 活动的百分比，不包括此函数调用的函数中的活动。
非独占 CPU (毫秒)  | 在此函数和此函数调用的函数中执行代码所花费的 CPU 时间。
独占 CPU (ms ms)  | 在此函数中执行代码所花费的 CPU 时间，不包括此函数调用的函数中的时间。
URL | URL () 发生堆栈帧的位置。 基于标准的 Web API (来自浏览器的函数调用) *标记为 [DOM]*。

## 快捷方式

| 操作                         | 快捷方式     |
|:-------------------------------|:-------------|
| 启动/停止分析会话 | `Ctrl` + `E` |
| 导入分析会话       | `Ctrl` + `O` |
| 导出分析会话       | `Ctrl` + `S` |

## 已知问题

### 启动分析会话时出错

如果看到以下错误消息：在"**** 性能"工具中启动分析会话时出错，请按照以下步骤操作以寻找解决方法。

1. 按 `Windows Key`  +  `R` 。

2. 在"运行"对话框中，输入**services.msc。**
![known-issues-1](./media/known_issues_1.PNG)

3. 找到 **Microsoft (R) 诊断中心标准收集器服务** 并右键单击它。
![known-issues-2](./media/known_issues_2.PNG)

4. 重新启动 **Microsoft (R) 诊断中心标准收集器服务**。
![known-issues-3](./media/known_issues_3.PNG)

5. 关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到页面，然后按 `F12` 。

6. 现在，你应该能够开始分析。
![known-issues-4](./media/known_issues_4-performance.PNG)

是否仍遇到问题？ 请使用"发送反馈"图标 **向我们发送反馈** ！ 

![known-issues-5](./media/known_issues_5.PNG)

### 停止分析会话时出错。

如果看到以下错误消息：在停止**** 性能工具中的分析会话时出错，请按照以下步骤操作以寻找解决方法。

1. 按 `Windows Key`  +  `R` 。

2. 在"运行"对话框中，输入**services.msc。**
![known-issues-1](./media/known_issues_1.PNG)

3. 找到 **Microsoft (R) 诊断中心标准收集器服务** 并右键单击它。
![known-issues-2](./media/known_issues_2.PNG)

4. 重新启动 **Microsoft (R) 诊断中心标准收集器服务**。
![known-issues-3](./media/known_issues_3.PNG)

5. 关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到页面，然后按 `F12` 。

6. 现在，你应该能够开始分析。
![known-issues-4](./media/known_issues_4-performance.PNG)

是否仍遇到问题？ 请使用"发送反馈"图标 **向我们发送反馈** ！ 

![known-issues-5](./media/known_issues_5.PNG)
