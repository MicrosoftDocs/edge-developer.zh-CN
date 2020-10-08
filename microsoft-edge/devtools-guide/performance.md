---
description: 在用户交互期间使用 "性能" 面板分析页面的 responsivenes
title: DevTools-性能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、性能、配置文件、帧速率、fps、CPU 使用率、JavaScript 执行
ms.custom: seodec18
ms.openlocfilehash: aecf3cf49592dbf1f24231e76f14ddc2ca1228c3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563475"
---
# 性能

" **性能** " 面板提供了用于分析和分析用户交互期间的 UI 响应的工具。 有了它，您可以：

 - 测量页面各个组件的[执行时间](#recording-a-profile) 
 - 向[下钻取到你要花费最多 CPU 周期的位置](#timeline-ruler)，以运行你的页面和你的用户的结果视觉效果
 - [获取](#timeline-details) 消耗页面执行时间的进程的分步细分 
 - [遍历 JavaScript 调用堆栈](#javascript-call-stacks) 以标识成本高昂的操作，例如那些需要布局重新计算的操作 

![DevTools 性能面板](./media/performance.png)

## 录制配置文件

分析页面性能的第一步是在执行特定用户方案（如尝试修复的性能 bug 的重现步骤）中捕获配置文件，或者想要为获得更好的用户体验而优化的典型使用情形。 

### 工具栏

使用工具栏上的 "**开始**  /  **停止**" 按钮 (或 `Ctrl+E`) 启动和结束性能跟踪。 绿色指示器将在 " **性能** " 选项卡上显示，指示正在进行录制。 

![性能面板工具栏](./media/performance_toolbar.png)

性能报告将在停止配置文件时生成。 你可以选择将其保存到磁盘 (`Ctrl+S`) ，然后在 `Ctrl+O` DevTools 中重新加载 () 。  DevTools 诊断会话将以 *diagsession* 扩展名保存。

以下是录制配置文件时需要记住的一些事项：

- 执行捕获你要分析的方案所需的最少操作。 页面上的无关操作将产生额外的数据并令您的结果混乱。

- 探查器将自动标记报表中的主要应用生命周期事件，例如页面导航、 [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded)和页面 [加载](https://developer.mozilla.org/docs/Web/Events/load)。 你可以通过调用性能来添加自定义标记。从代码或控制台中 [标记 ( # B1 ](https://developer.mozilla.org/docs/Web/API/Performance/mark) 方法。 

- 如果初始页面加载时间对分析非常重要，请确保从 " [网络](./network.md) " 面板中清除浏览器缓存 () 以确保从网络加载所有页面资源。

- 有时，你可以在不同的计算机上记录多个会话和/或采样相同的方案，从而更好地了解通配符中的性能问题。

## 日程表标尺

时间线作为滑动标尺工作。 使用它将报表的范围限制为特定时间范围 (或) 感兴趣的事件范围。 拖动黑色**幻灯片控件**以限制你想要调查的时间范围，并从下一个*详细信息窗格*中的 "[时间线](#timeline-details)" 和 " [JavaScript 调用堆栈](#javascript-call-stacks)" 报告中筛选无关的分析数据。 

您将在标尺上看到两种类型的标记：

 - 日程表上的**应用生命周期标记** (如页面导航、 [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded)和页面[加载](https://developer.mozilla.org/docs/Web/Events/load)) 将在你录制配置文件时自动记录。

 - **用户标记**是自定义标记，您可以选择添加对性能的调用。从代码或 DevTools[**控制台**](./console.md)中[标记 ( # B1](https://developer.mozilla.org/docs/Web/API/Performance/mark)方法。 你可以将 *开始* 和 *结束* 标记组合为具有性能的单个命名度量值 [。测量 ( # B1 ](https://developer.mozilla.org/docs/Web/API/Performance/measure) 方法。 

选择时间范围后，可以从工具栏进一步 **放大** ，或 **重置缩放** 和 **清除选择** ，以返回到性能跟踪 (的完整视图，) 未选择时间范围。 也可通过右键单击上下文菜单使用这些控件。

![性能面板日程表](./media/performance_timeline.png)

### CPU 使用率

" **CPU 使用率%** 时序表" 图表描述运行页面时所需的各种浏览器子系统所占用的处理资源，按类别划分：

#### 正在加载
指示检索应用资源和分析 HTML 和 CSS 所花费的时间。 这可能包括网络请求。 以下关联事件将记录在 [时间线](#timeline-details)中：

事件 | 描述
:------------ | :-------------
CssParsing  | 遇到需要分析的新 CSS 内容。
HtmlParsing | 遇到需要解析为节点并插入到 DOM 中的新 HTML 内容。
HttpRequest | 在 DOM 中遇到远程资源，或者创建了需要进行 HTTP 请求的 XMLHttpRequest。
HtmlSpeculativeDownloading | 正在搜索所需资源的页面 HTML 内容，以便能够尽快安排这些资源的 HTTP 请求。


#### 运行
指示分析和执行 JavaScript 所花费的时间。 这包括 DOM 事件、计时器、脚本求值和动画帧回调。 以下关联事件将记录在 [时间线](#timeline-details)中：

事件 | 描述
:------------ | :-------------
DomEvent | 在 DOM 对象上触发了事件。
EvaluatingScript | `<script>`在 DOM 中遇到新元素，需要对其进行分析和执行。
EventHandler | 为响应正在触发的 DOM 事件而触发的已注册事件侦听器。
帧 | 当新框架准备就绪时，将触发已注册的回调，以便它可以参与视觉更改。
测量 | 使用方法测量特定于应用的方案 `performance.measure()` 。
MediaQueryListener | 已注册的媒体查询已失效，导致其关联的侦听器 (s) 的执行。
MutationObserver | 已修改一个或多个观测的 DOM 元素，这些元素导致执行 MutationObserver 的关联回调。
TimerFired | 计划的计时器已过，导致执行其关联的回调。
WindowsRuntimeAsyncCallback | 异步操作由触发回调的 Windows 运行时对象完成 `Promise` 。
WindowsRuntimeEvent | 在触发已注册侦听器的 Windows 运行时对象上触发了事件。

#### GC
指示为不再使用的对象收集内存所花费的时间。 以下关联事件将记录在 [时间线](#timeline-details)中：

事件 | 描述
:------------ | :-------------
GarbageCollection | JavaScript 运行时已审核应用的当前内存使用情况，以确定不再引用哪些对象，从而可以回收这些对象。

#### 样式设置
指示计算元素演示文稿和布局所用的时间。 以下关联事件将记录在 [时间线](#timeline-details)中：

事件 | 描述
:------------ | :-------------
AlignedBeat | 已处理对 DOM 所做的挂起的可视更改，以便可以更新应用的显示。
CssCalculation | 已对 DOM 进行了更改，或者添加了新的 CSS 内容，需要重新计算所有受影响的元素的样式属性。
布局 | 对 DOM 进行了更改，需要计算所有受影响的元素的大小和/或位置。

#### 呈现
指示绘制屏幕所用的时间。 以下关联事件将记录在 [时间线](#timeline-details)中：

事件 | 描述
:------------ | :-------------
画图 | 对 DOM 进行了可视更改，需要重新绘制页面的所有受影响的部分。
RenderLayer | 对 DOM 的独立呈现片段进行了可视更改 (称为 "图层") 需要重新绘制的页面的各自部分。

#### 图像解码
指示解压缩和解码图像所用的时间。 以下关联事件将记录在 [时间线](#timeline-details)中：

事件 | 描述
:------------ | :-------------
ImageDecoded | DOM 中已包含一个图像，需要将其从其原始格式解压缩到位图中。

### 视觉吞吐量

** (FPS) graph 的视觉吞吐量**显示分析方案期间*每秒*的估计帧 (FPS) ，其中 60 FPS 是理想的显示速率。 帧速率中的 dip 表示性能瓶颈，帧速率为零意味着完全删除帧。

## 日程表详细信息

使用 "调换详细信息" 窗格全面了解页面上发生的情况。 " **时间线详细信息** " 选项卡提供了在各种浏览器子系统中发生的事件的细目。

![性能日程表详细信息窗格](./media/performance_details_timeline.png)

1. **事件列表排序控件**

    使用 "**排序依据**" 下拉列表控件在 "*开始时间*" 或 "持续时间" 之间切换 "[事件列表](#event-list)" 顺序* (非独占*) 。 这还会更改 [所选日程表详细信息](#selected-timeline-details)的视图。

2. **按帧对事件进行分组**

    使用 " **按框架分组的组事件** " 切换到组的顶级事件 (*HTML 分析、布局、DOM 事件等）* ) 到其相应的工作单元 (或 "frame" ) 发生动画/视觉更新的时间段。 这些帧被视为其他事件，因此可以对它们进行排序/筛选，并在[事件列表](#event-list)中单击时提供*非独占时间*摘要。

3. **事件列表筛选控件**

    使用 " **筛选事件** " 菜单配置 [日程表详细信息](#timeline-details)中显示的事件类型。 

    ![用于筛选性能事件的控件](./media/performance_filter_events.png) 

    以下筛选器可用：

   - **图像解码**：显示在后台线程上发生的事件 (例如图像解码、GC) 。 
   - **网络流量**：显示网络绑定的 HTTP 请求。
   - **Ui 活动**：显示在 UI 线程和/或呈现线程上发生的事件 (例如 DOM 事件处理程序、布局) 。
   - **用户度量值**：显示指示对性能的调用的自定义事件。测量 ( # A1 方法。

     你可以按其非独占持续时间进一步筛选顶级事件。

### 事件列表

*事件列表*提供按时间顺序排列所选时间范围内出现的[浏览器子系统事件](#cpu-utilization)的列表。 

单击任意条目以填充该项目的 **选定事件详细信息** 图表。 具有嵌套事件/函数的条目将显示执行该函数所花费的 **非独占** (时间 *，* 以及它调用的任何其他函数) 和 **独占** (时间仅在调用函数本身的主体内所用) 时间在图表中显示。

右键单击任何条目以打开上下文菜单，以仅将日程表筛选到该事件，并在 [**调试程序**](./debugger.md) (或 " [**元素**](./elements.md) " 面板中查看负责该事件的源代码（如适用) ）。

### 所选日程表详细信息

*所选日程表详细信息*提供所选时间范围内非独占/独占事件时间的详细条形图。 按 *持续时间排序时 (包含) * 使用 " **事件列表" 排序控件**时，最长运行事件将在此图表中直观地突出。 

### 所选事件详细信息

此报表提供有关所选事件的进一步信息，包括 *开始时间*、执行线程类型 (例如， *下载*、 *UI*、 *呈现*) 以及特定于特定事件类型的其他上下文详细信息。 例如， *事件侦听器* 类型提供指向 *回调函数* 和 *调度调用堆栈*的调试器链接。

## JavaScript 调用堆栈

![JavaScript 调用堆栈的性能计时](./media/performance_details_javascript.png)

**JavaScript "调用堆栈**" 选项卡提供在所选时间范围内运行的脚本函数的 CPU 使用信息和计时：

 列 | 描述
:------------ | :-------------
函数名称 | 浏览器或用户定义函数的名称。
非独占 CPU (% )  | 此函数以及此函数调用的函数中所选 CPU 活动的百分比。
独占 CPU (% )  | 此函数中所选 CPU 活动的百分比，不包括此函数调用的函数中的活动。
非独占 CPU (ms)  | 执行此函数中的代码以及此函数调用的函数所用的 CPU 时间。
独占 CPU (ms)  | 执行此函数中的代码所用的 CPU 时间，不包括此函数调用的函数中的时间。
URL |  (s 的 URL) 出现堆栈帧的位置。 源自浏览器 (基于标准的 web Api) 的函数调用标记为 *[DOM]*。

## 快捷方式

| 操作                         | 快捷方式     |
|:-------------------------------|:-------------|
| 开始/停止分析会话 | `Ctrl` + `E` |
| 导入性能分析会话       | `Ctrl` + `O` |
| 导出分析会话       | `Ctrl` + `S` |

## 已知问题

### 启动分析会话时出错

如果你看到此错误消息：在性能工具中 **启动分析会话时出错** ，请按照以下步骤进行解决。

1. 按 `Windows Key`  +  `R` 。

2. 在 "运行" 对话框中，输入 **services.msc**。
![已知问题-1](./media/known_issues_1.PNG)

3. 找到 **Microsoft (R) 诊断中心标准收集器服务** ，然后右键单击它。
![已知问题-2](./media/known_issues_2.PNG)

4. 重新启动 **Microsoft (R) 诊断中心标准收集器服务**。
![已知问题-3](./media/known_issues_3.PNG)

5. 关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到您的页面，然后按 `F12` 。

6. 现在，你应该能够开始分析。
![已知问题-4](./media/known_issues_4-performance.PNG)

仍遇到问题？ 请使用 " **发送反馈** " 图标向我们发送您的反馈！ 

![已知问题-5](./media/known_issues_5.PNG)

### 停止性能分析会话时出错。

如果你看到此错误消息：在性能工具中 **停止分析会话时发生错误** ，请按照以下步骤进行解决。

1. 按 `Windows Key`  +  `R` 。

2. 在 "运行" 对话框中，输入 **services.msc**。
![已知问题-1](./media/known_issues_1.PNG)

3. 找到 **Microsoft (R) 诊断中心标准收集器服务** ，然后右键单击它。
![已知问题-2](./media/known_issues_2.PNG)

4. 重新启动 **Microsoft (R) 诊断中心标准收集器服务**。
![已知问题-3](./media/known_issues_3.PNG)

5. 关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到您的页面，然后按 `F12` 。

6. 现在，你应该能够开始分析。
![已知问题-4](./media/known_issues_4-performance.PNG)

仍遇到问题？ 请使用 " **发送反馈** " 图标向我们发送您的反馈！ 

![已知问题-5](./media/known_issues_5.PNG)
