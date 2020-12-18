---
description: 使用"内存"面板
title: DevTools - 内存
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 内存， 堆， GC， 垃圾回收， 保留大小， 管理程序
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5ad284f8072cc296743299ec9c4fb2037f8fd883
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232124"
---
# 内存

使用 **内存** 面板测量系统资源的使用，并比较代码执行的不同状态中的堆快照。 通过它，你可以：

- [实时绘制页面的内存消耗并](#memory-usage-timeline) 获取堆的快照
- [确定代码中的潜在](#snapshot-summary) 内存问题，例如未附加到 DOM 的保留对象
- [按实例、](#snapshot-details) 实例对象类型大小和引用查看内存使用率数据，以帮助隔离问题
- [应用快照数据筛选器](#filters) 以减少不可操作信息的干扰
- [确定特定对象的内存](#object-references) 成本和使该对象保持活动状态的引用
- [在调查的不同阶段](#snapshot-comparison) 对堆进行差异，以跟踪内存泄漏和其他问题的来源

![Microsoft Edge DevTools 内存面板](./media/memory.png)


## 工具栏

1. **启动/停止分析会话 (Ctrl+E) ： **打开探查器后，你可以跟踪内存使用情况并获取堆的快照。
2. **将分析会话 (Ctrl+O) ： **加载保存的 DevTools 内存诊断会话。
3. **将分析会话 (Ctrl+S) ： **将当前诊断会话保存到磁盘。
4. **使用 Ctrl (Shift+T) **获取堆快照：记录给定时间点的当前内存分配。


## 内存使用时间线

内存问题可能是性能问题的主要原因，从而导致页面逐渐变得无响应和滞后。

分析页面的内存使用情况的第一步是启动分析会话，以在对导致[](#toolbar)内存不足或可疑内存泄漏的步骤进行重新说明时，获取堆的快照之前/之后。

启动内存探查器时，你将看到一个进程内存图，它允许你观察整个专用工作集 (页面占用的内存量) 一段时间。 内存图显示选项卡的进程内存（包括专用字节、本机内存和 JavaScript 堆）实时视图。 

![内存使用时间线](./media/memory_timeline.png)

 此图指示页面的内存趋势，该趋势使你能够判断何时适合拍摄堆 [快照供以后](#toolbar) 比较，例如当你看到意外的内存保留期时。

### Performance.mark () 

你可以向时间线 **添加自定义用户** 标记，以帮助识别分析会话过程中的关键事件，方法是从代码或 [`Performance.mark()`](https://developer.mozilla.org/docs/Web/API/Performance/mark) DevTools 控制台内调用 [**该方法**](./console.md)。

### Console.takeheapSnapshot () 

有时，你需要在非常具体的点获取快照，例如紧接 DOM 发生大规模更改之前。 在这些情况下，可以通过编程方式获取快照 [`Console.takeHeapSnapshot()`](./console/console-api.md#taking-heap-snapshots) 。

## 快照摘要

[拍摄快照](#toolbar) 将生成一个摘要磁贴，该磁贴指示拍摄快照时 JavaScript 堆的大小，以及分配的对象数和页面的屏幕截图。 在需要分析的用户方案中运行时，你随时都可以继续获取快照。 快照生成其他磁贴，其中每个磁贴都指示 JavaScript 内存与上一个快照的区别。

![堆快照](./media/memory_snapshot.png)

单击摘要磁贴中的值将切换到显示快照数据详细信息 [的窗格](#snapshot-details)。 潜在的 [内存问题用](#snapshot-details) 蓝色信息图标 ("i") 图标。

## 快照详细信息

"快照" *窗格中* 的数据显示页面创建的对象以及你可能使用 JavaScript 框架分配的任何内存。

![快照详细信息表](./media/memory_details.png)

这三个选项卡表示数据的不同视图：

#### 类型

显示堆栈上对象的实例计数和总大小，对象类型。 默认情况下，这些实例按实例计数排序。

选择上半部分"类型"窗格中** 的对象时，下[](#object-references)窗格中的"对象引用"表将列出指向该对象的所有对象。

#### 根

显示子引用的分层视图，以描述对象如何作为全局对象的根，从而防止它们被垃圾回收。

默认情况下，子节点按保留大小列进行排序，最顶端为最大。

#### Dominators

显示堆栈上具有对其他对象的独占引用的对象的列表。 管理程序按保留大小进行排序，以指示使用最可能最轻松释放的内存的对象。

下面是如何解释"类型"、"根"** 和"管理程序"*视图中的列*：

列 | 描述
:------------ | :-------------
标识符 ()  | 最能够标识对象的名称。 例如，对于 HTML 元素，快照详细信息会显示 ID 属性值（如果使用）。
类型 | 对象类型 (例如 *，HTMLDivElement*) 。
大小 | 对象大小，不包括任何引用对象的大小。
保留大小 | 对象大小加上没有其他父对象的所有子对象的大小。 出于实用目的，这是对象保留的内存量，因此，如果删除对象，将回收指定内存量。
Count | 对象实例的数量。 此值仅在"类型"视图中显示。

选择上窗格中的对象时，下窗格中** 的"对象引用"表将[](#object-references)列出指向该对象的所有对象。

### 筛选器

可以使用以下内容进一步调整表中的数据：

![内置和对象 ID 的筛选器](./media/memory_filter.png)

1. **标识符筛选器**：通过搜索特定对象标识符筛选出数据
2. **按管理**程序分组：只有具有对其他对象的** 独占引用的对象显示在对象的顶级视图中 (这是 *"Dominators"* 选项卡视图中的默认) 。
3. **内置 /ID 筛选器**：默认情况下 [，JavaScript](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects) 内置对象包含在列表中。 如果有多个需要区分的匿名对象，则列出对象 ID 会很有用。

" *类型"* 视图、"根视图"和"管理 *程序* "视图各有其自己的筛选器，因此切换到其他视图时不会保留该筛选器。

### 对象引用

在[**"类型**](#types)"[**和"管理程序**](#dominators)"视图中，下窗格包含一**** 个显示共享引用的对象引用列表。 在上窗格中选择一个对象时，此列表将显示指向该对象的所有对象，即使选定对象保持活动状态的对象。

循环引用使用星号 (*) 和信息性工具提示显示，并且不能展开。 否则，它们会阻止您向上移动引用树并标识保留内存的对象。

若要快速标识等效对象，请选中 [*"显示对象标识*](#filters) "筛选器选项，以显示"标识符"列 (对象名称 *) 对象标识 * 。 具有相同的 ID 的对象是共享引用。

### 快照比较

单击快照 [摘要磁贴上的快照比较](#snapshot-details) 选项卡或比较 [链接](#snapshot-summary)  将显示两个快照之间的信息差异。 在比较窗格中，"Dominators"视图、"** 类型"视图和"[**](#snapshot-details)根"视图提供与单个快照相同的快照详细信息，并包含以下附加值： **

列 | 描述
:------------ | :-------------
大小差。 | 当前快照中对象的大小与上一快照中对象的大小之间的差，不包括任何引用对象的大小。
保留大小差异。 | 当前快照中对象的保留大小与上一快照中对象的保留大小之间的差。 保留的大小包括对象大小以及其所有没有其他父项的子对象的大小。 出于实用目的，保留的大小是对象保留的内存量，因此，如果删除对象，将回收指定内存量。

可以使用 **"范围"** 下拉列表筛选快照之间的差异信息：

![快照比较的作用域筛选器](./media/memory_comparison_scope_filter.png)

- <strong>从 Snapshot # 中保留的对象：显示添加到堆和从堆栈中删除的对象（从基线快照到上一个快照） <number></strong> 之间的差。 例如，如果快照摘要在对象计数中显示 <em> +205 / -195，则此筛选器将显示已添加但不删除的十 </em> 个对象。

- <strong>在 Snapshot # 和 # 之间添加的对象：显示从上一个快照 <number> <number></strong> 添加到堆的所有对象。

- <strong>Snapshot # 中的所有对象：显示堆上 (对象，也就是说，未筛选的 <number></strong> <em> </em> 视图) 。

默认情况下 *，"显示不匹配* 的引用"筛选器应用于比较视图以指示与当前范围筛选器不匹配的对象引用。 你可以从下拉菜单中关闭它：

![快照比较的不匹配引用筛选器](./media/memory_comparison_matching_filter.png)


## 快捷方式

 操作 | 快捷方式
:------------ | :-------------
启动/停止分析会话  | `Ctrl` + `E`
导入分析会话 | `Ctrl` + `O`
导出分析会话 | `Ctrl` + `S`
获取堆快照 | `Ctrl` + `Shift` + `T`

## 已知问题

### 启动分析会话时出错

如果看到以下错误消息：在"**** 内存"工具中启动分析会话时出错，请按照以下步骤操作以寻找解决方法。

1. 按 `Windows Key`  +  `R` 。

2. 在"运行"对话框中，输入**services.msc。**
![known-issues-1](./media/known_issues_1.PNG)

3. 找到 **Microsoft (R) 诊断中心标准收集器服务** 并右键单击它。
![known-issues-2](./media/known_issues_2.PNG)

4. 重新启动 **Microsoft (R) 诊断中心标准收集器服务**。
![known-issues-3](./media/known_issues_3.PNG)

5. 关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到页面，然后按 `F12` 。

6. 现在，你应该能够开始分析。 
![known-issues-4](./media/known_issues_4-memory.PNG)

是否仍遇到问题？ 请使用"发送反馈"图标 **向我们发送反馈** ！ 

![known-issues-5](./media/known_issues_5.PNG)
