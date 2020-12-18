---
description: '在 EdgeHTML 16 中添加到 Windows 10 Fall Creators Update (Microsoft Edge DevTools) '
title: EdgeHTML 16 中的 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， edgehtml 16
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2d24b6851e843f491e470b18ccc18d559ed5533d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232102"
---
# EdgeHTML 16 (Windows 10 Fall Creators Update 中的 DevTools) 

在此版本中，我们启动了一项重大 DevTools 重构工作，以提高稳定性和性能，并添加了一组立即开始使用的新功能！ 

以下是 EdgeHTML [16 版本 Windows 10 Fall Creators Update](/windows/uwp/whats-new/windows-10-build-16299) ([附带的 Microsoft Edge](https://aka.ms/devguide_edgehtml_16) DevTools) 。

## 上级事件侦听器 

除了**元素本身**上的事件侦听器之外，"事件"窗格现在还添加了查看在元素面板) 中当前选定元素 (**** 的任何上级上注册的事件侦听器的选项。 此外，你现在可以按 Event 或 *Element* 对事件侦听器显示 *进行分组*。 

![事件侦听器检查窗格](../media/elements_ancestor_events.png)

## DOM 破坏断点

现在，你可以设置 DOM 分解断点，以在选定元素节点发生更改时中断调试器。 从 **"元素** "面板中，rt-click on any element in the DOM tree view and select one or more of the following：

 - 删除节点上的中断
 - 修改了子树上的中断
 - 修改属性时中断

可以从"元素"或"调试器"面板中的**DOM**断点窗格******管理**你的分解断点。

![DOM 断点窗格](../media/elements_dom_breakpoints.png)

## CSS 规则支持

CSS "at" (@) 规则现在在"样式"窗格上的其他 CSS 规则声明中表示****，包括动画规则 (当前限制为只读 `@keyframes`) 、功能查询和查询。 `@supports` `@media`

![从"DevTools 样式"窗格进行 CSS 规则检查](../media/elements_at_rules.png)

## CSS 字体窗格

CSS `@font-face` 规则现在具有其自己的专用******"字体"窗格，该窗格显示从本地或网络 (加载) 以及** 使用它的字符数。 如果从网络加载字体，DevTools 将显示导入该字体的规则及其别名和字体类型。

![CSS 字体信息](../media/elements_fonts.png)

## CSS 伪元素支持

" **样式** "窗格现在将伪元素分组在其自己的标题下，不再显示为已排除的内容。

**之前：**
<br>
![生成的内容之前已排除](../media/gc_before.png)

**之后：**
<br>
![生成的内容不再显示带删除线](../media/gc_after.png)

## 控制台改进

控制台 **面板** 进行了 UX 检查，以改进可用性和更快、更丰富的 Intellisense 体验。

**之前：** 
![上一个控制台](../media/console_old.png)

**之后：** 
![新控制台](../media/console_new.png)

我们还添加了以下改进：

 -  用于 `Shift + Enter` 向命令添加一个附加行，然后使用 `Enter` 执行命令。  (以前有一个切换到 *多行/单行模式* 切换按钮。) 

 - 支持以下新 API：
    - [ **console.table (**_对象) _*__*](../console/console-api.md#organizing-log-output)方法
    - [ **getEventListeners (**_对象) _*__*](../console/command-line.md#event-listeners)命令
    - [**键 (**_对象) _*__*](../console/command-line.md#object-inspection)命令
    - [**值 (**_对象) _*__*](../console/command-line.md#object-inspection)命令
    - [ **$x (** _xpath 表达式) _*__*](../console/command-line.md#dom-selectors)选择器

 - [**现在支持 %c () **](../console/console-api.md#logging-custom-messages)格式参数

## 调试改进

除了一套用于调试 [PWA](#progressive-web-app-debugging)服务工作者和缓存的新功能外，调试器还添加了以下功能：

### 合并共享资源的调试

即使从 CDN 加载的资源（如从 CDN 加载的文件）在整个代码中多次引用，DevTools 现在也会为该文件提供单个调试实例，然后你可以设置常用断点，无论该文件引用在何处，都会命中这些断点。  (之前，每个脚本引用都被视为一个唯一的资源将映射到一组单独的断点。) 

### 实时编辑 JavaScript（ *处于空闲状态时编辑）*

现在可以在调试会话期间编辑 JavaScript 实时。 此功能在实验 (上一个 [) ](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) *Windows 10* 创意者更新 () 版本中的标记后面可用，现在是一项永久性功能。 只需从调试器面板中选择任何**** 脚本文件，进行编辑，然后单击"**** 保存 (或) 代码部分下次运行时 `Ctrl+S` 测试更改。 

![调试器使你能够实时编辑脚本并差异更改](../media/debugger_edit_buttons.png) 

单击 **"比较文档与原始文档"** 按钮以查看您更改的内容的差异。

![调试器中已编辑代码的差异视图](../media/debugger_edit_code.png) 

请注意以下约束：

- 脚本编辑仅适用于外部 *.js*文件 (而未嵌入 `<script>` *.html) *
- 编辑保存在内存中，在重新加载文档时刷新，因此无法运行处理程序中的编辑， `DOMContentLoaded` 例如
- 目前，无法 ("另存为"选项) 从**** DevTools 将编辑保存到磁盘

## 快捷方式

你现在可以将 DevTools 启动到上次查看的面板 () 或直接启动到控制台 () 就像在主要浏览器上一 `Ctrl+Shift+I` `Ctrl+Shift+J` 样。

## 渐进式 Web 应用调试

通过从 (中选择"启用服务工作者"选项并重新启动 Microsoft Edge) ，在 Microsoft Edge 和 DevTools 中测试对渐进式 Web 应用 (PWA) 的实验性**** `about:flags` 支持。 如果网站使用服务工作者和****/或缓存**API，** 将填充每个源的调试器面板中的**** 条目，类似于 Web 存储和 Cookie 检查工作的方式。

单击特定服务工作线程条目将打开服务工作者概述****，您可以在其中管理给定范围的服务工作者注册并强制发送测试推送通知。 还可以停止**启动** / **各个**服务工作者，**然后从**单独的调试器窗口中检查它们：

!["服务工作者概述"窗格](../media/debugger_sw_overview.png)

请注意以下有关服务工作器调试的信息：

 - 调试服务工作者将启动独立于页面工具的 DevTools 的新实例，因为服务工作者可以跨多个选项卡共享。 
 - 由于[服务](../elements.md)工作者[](../emulation.md)在后台运行，并且不直接控制应用的前端，因此服务工作器调试器中缺少元素和模拟面板。
 - 目前，仅从服务工作者的 DevTools 调试实例报告服务工作者的网络流量，而不是从页面本身的中央实例报告。

单击特定缓存条目将打开缓存管理器，您可以在**** 其中检查和选择删除请求和响应 (/值对中的缓存) 。 ** **
