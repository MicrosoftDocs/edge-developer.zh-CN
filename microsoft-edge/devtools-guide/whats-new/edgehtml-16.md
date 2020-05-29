---
description: 在 Windows 10 秋季创意者更新（EdgeHTML 16）中添加到 Microsoft Edge DevTools 的功能
title: EdgeHTML 16 中的 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、edgehtml 16
ms.custom: seodec18
ms.openlocfilehash: 78ede81e022cc8f0f623ecd33fd2303314ec9cb0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563438"
---
# Windows 10 秋季创意者更新中的 DevTools （EdgeHTML 16）

在此版本中，我们为改进的可靠性和性能开始了重大 DevTools 重构工作，同时还添加了一组可开始使用今天的新功能！ 

下面是[Windows 10 秋季创意者更新](/windows/uwp/whats-new/windows-10-build-16299)（[EdgeHTML 16](https://aka.ms/devguide_edgehtml_16)）随附的 Microsoft Edge DevTools 功能。

## 上级事件侦听器 

"**事件**" 窗格现在添加用于查看在当前选定元素（在 "**元素**" 面板中）的任何上级上注册的事件侦听器的选项以及元素本身的任何上级。 此外，你现在可以按*事件*或*元素*对事件侦听器显示进行分组。 

![事件侦听器检查窗格](../media/elements_ancestor_events.png)

## DOM 转变断点

现在，你可以将 DOM 转变断点设置为在所选元素节点发生更改时中断调试程序。 从 "**元素**" 面板中，rt-单击 DOM 树视图中的任意元素，然后选择以下一个或多个操作：

 - 删除节点上的中断
 - 已修改子树的中断
 - 属性被修改时中断

你可以从 "**元素**" 或 "**调试器**" 面板中的 " **DOM 断点**" 窗格管理变化断点。

![DOM 断点窗格](../media/elements_dom_breakpoints.png)

## CSS at 规则支持

CSS "at" （@）规则现在表示在 "**样式**" 窗格上的其他 CSS 规则声明中，包括动画 `@keyframes` 规则（当前限于只读）、 `@supports` 功能查询和 `@media` 查询。

![来自 DevTools 样式窗格的 CSS at 规则检查](../media/elements_at_rules.png)

## CSS 字体窗格

CSS `@font-face` 规则现在有自己的专用 "**字体**" 窗格，显示从何处加载字体（*本地*或*网络*）以及使用该字体的字符数。 如果从网络加载字体，DevTools 将显示导入该字体及其别名和字体类型的规则。

![CSS 字体信息](../media/elements_fonts.png)

## CSS 伪元素支持

"**样式**" 窗格现在将伪元素分组在其自己的标题下，不再显示其内容，如带删除线。

**之前：**
<br>
![以前已删除生成的内容](../media/gc_before.png)

**之后：**
<br>
![带有删除线的生成内容不再显示](../media/gc_after.png)

## 增强了控制台

**控制台**面板为提高可用性和更快、更丰富的智能感知体验获得了 UX

**之前：** 
![以前的控制台](../media/console_old.png)

**在：** 
![新的控制台](../media/console_new.png)

我们还添加了以下改进：

 -  用于 `Shift + Enter` 在执行命令前将另一行添加到命令 `Enter` 。 （以前有一个*切换到多行/单行模式*切换按钮。）

 - 以下新 Api 受支持：
    - [**console. table （***object***）**](../console/console-api.md#organizing-log-output)方法
    - [**getEventListeners （***object***）**](../console/command-line.md#event-listeners)命令
    - [**键（***对象***）**](../console/command-line.md#object-inspection)命令
    - [**values （***object***）**](../console/command-line.md#object-inspection)命令
    - [**$x （***xpath 表达式***）**](../console/command-line.md#dom-selectors)选择器

 - [**% C （）**](../console/console-api.md#logging-custom-messages)格式参数现在受支持

## 调试改进

除了用于调试[PWA 服务工作人员和缓存](#progressive-web-app-debugging)的一组新功能之外，调试器还添加了这些功能：

### 共享资源的合并调试

即使在你的代码中多次引用某个资源（如从 CDN 加载的文件），DevTools 现在也会为该文件提供单个调试实例，你可以在该文件中设置将命中的常用断点，而不管该文件的引用位置。 （之前的每个脚本引用均被视为唯一资源将映射到单独的一组断点。）

### 实时编辑 JavaScript 和 *"空闲时编辑"*

现在，你可以在调试会话期间编辑 JavaScript live。 此功能在[上](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97)一个（*Windows 10 创意者更新*）版本中 experimentally 可用（在标志后面），现在是永久性的功能。 只需从 "**调试器**" 面板中选择任意脚本文件，然后单击 "**保存**" （或 `Ctrl+S` ）以在下次运行该代码段时测试所做的更改。 

![调试器使你能够实时编辑脚本并比较更改](../media/debugger_edit_buttons.png) 

单击 "**将文档与原始文档比较**" 按钮以查看更改内容的差异。

![调试器中编辑代码的比较视图](../media/debugger_edit_code.png) 

请注意以下限制：

- 脚本编辑仅适用于外部 *.js*文件（而不是嵌入 `<script>` 在 *.html*中）
- 编辑保存在内存中，并在重新加载文档时进行刷新，因此你无法在处理程序内运行编辑 `DOMContentLoaded` ，例如
- 目前没有办法（如 "**另存为**" 选项）将您的编辑内容从 DevTools 保存到磁盘。

## 指向

现在，你可以在最后一次查看的面板（）上启动 DevTools， `Ctrl+Shift+I` 也可以直接在控制台（）中启动它， `Ctrl+Shift+J` 就像在其他主流浏览器上一样。

## 渐进 Web 应用调试

通过从（和重启 Microsoft Edge）中选择 "**启用服务工作线程**" 选项，在 Microsoft Edge 和 DevTools 中测试累进 Web Apps （PWAs）的实验性支持 `about:flags` 。 如果网站使用**服务工作者**和/或**缓存**API，将在**调试器**面板中为每个源填充条目，类似于 web 存储和 cookie 检查的工作方式。

单击特定的服务工作人员条目将打开 "**服务工作人员" 概览**，您可以在其中管理给定范围的服务工作人员注册并强制实施测试推送通知。 您还可以**停止** / **启动**单个服务工作人员并从单独的调试器窗口**检查**它们：

![服务工作人员概述窗格](../media/debugger_sw_overview.png)

请注意以下有关服务工作者调试的信息：

 - 调试服务工作人员将启动与页面工具分开的 DevTools 的新实例，因为服务工作人员可以在多个选项卡之间共享。 
 - 如果服务工作者在后台运行，并且不直接控制应用的前端，则服务工作器调试器中不存在[元素](../elements.md)和[仿真](../emulation.md)面板。
 - 当前，服务工作者的网络流量仅从该工作人员的 DevTools 调试实例，而不是从页面本身的中央实例中报告。

单击特定的缓存条目将打开**缓存**管理器，您可以在其中检查和删除缓存条目（*请求*和*响应*键/值对）。