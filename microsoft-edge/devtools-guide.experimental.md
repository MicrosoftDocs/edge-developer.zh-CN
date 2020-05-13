---
description: 了解 Microsoft Edge 开发人员工具
title: Microsoft Edge 开发人员工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: edgehtml
keywords: microsoft edge、web 开发、f12 工具、devtools
experimental: false
experiment_id: 51fe4b97-3e55-41
ms.openlocfilehash: 47b7a3f4f523170f4dfb6f3ef674cecfdc0e157c
ms.sourcegitcommit: 24430258f363b7dd85f7067afd4565bf102b4a1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "10645327"
---
# Microsoft Edge 开发人员工具  

> [!NOTE]
> Microsoft Edge DevTools 帮助 web 开发人员构建和测试网站。  如果意外打开了 DevTools，只需按下 `F12` 即可关闭。  

Microsoft Edge DevTools 是通过[开放源代码](https://github.com/Microsoft/ChakraCore)（针对新式前端工作流进行了优化）[生成的，](https://www.typescriptlang.org/)现在可在 Microsoft Store 中作为[独立的 Windows 10 应用](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)使用。

有关最新功能的详细信息，请查看[*最新的 Windows 10 更新（EdgeHTML 17） DevTools*](./devtools-guide/whats-new.md)。

## 核心工具

![Microsoft Edge 开发工具](./devtools-guide/media/devtools.png)

Microsoft Edge DevTools 包括：

 - "[**元素**](./devtools-guide/elements.md)" 面板，用于编辑 HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 转变断点
 - 用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点以及在所选窗口或框架的上下文中运行 JavaScript 的[**控制台**](./devtools-guide/console.md)
 - 用于逐句通过代码、设置监视和断点、实时编辑代码以及检查 web 存储和 cookie 缓存的[**调试器**](./devtools-guide/debugger.md)
 - 用于监视和检查来自网络和浏览器缓存的请求和响应的[**网络**](./devtools-guide/network.md)面板 
 - 用于分析你的网站所需的时间和系统资源的[**性能**](./devtools-guide/performance.md)面板
 - 用于测量内存资源使用情况并比较不同代码执行状态的堆快照的[**内存**](./devtools-guide/memory.md)面板
 - 用于使用不同浏览器配置文件、屏幕分辨率和 GPS 位置坐标测试网站的[**仿真**](./devtools-guide/emulation.md)面板

请继续发送您的[反馈和功能请求](#feedback)！

> [!TIP]
> **[从任何浏览器免费测试 Microsoft edge](https://developer.microsoft.com/microsoft-edge/tools/remote/)**：我们与[BrowserStack](https://www.browserstack.com/test-on-microsoft-edge-browser#live-cloud)合作，在 microsoft edge 上提供免费实时和自动测试。

## Microsoft Store 应用

**Microsoft Edge DevTools** [现在可](./devtools-guide/whats-new.md)用作 microsoft Store 中的独立[Windows 10 应用](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)，除了浏览器（ `F12` ）工具体验。 使用应用商店版本时，将出现一个*选择器*面板，用于附加到打开本地和远程页面目标以及选项卡式布局，以便在 DevTools 实例之间轻松切换。

### 本地调试

若要在本地调试页面，只需启动*Microsoft Edge DevTools*应用。 选择器的**本地**面板将显示所有活动的 EdgeHTML 内容进程，包括打开的边缘浏览器选项卡、运行[PWAs](./progressive-web-apps-edgehtml/index.md) （*WWAHost*进程）和[web 视图](./webview.md)控件。 单击所需的目标以附加并打开 DevTools 的新选项卡实例。

![DevTools app 本地面板](./devtools-guide/media/chooser_local.png)

### 远程调试

*Microsoft Edge DevTools*应用通过我们新发布的[**DevTools 协议**](./devtools-protocol/index.md)引入了对远程计算机上的页面调试的基本支持。 通过此版本，可在[**调试程序**](./devtools-guide/debugger.md)面板中远程访问核心 funtionality，减去缓存检查（对于 Web 存储、服务工作人员、缓存 API 和 IndexedDB）。 远程调试仅限于*Microsoft Edge*运行*桌面*主机，并且支持其他 EdgeHTML 主机和在未来版本中推出的 Windows 10 设备。

若要开始使用，请查看[DevTools 协议](./devtools-protocol/index.md)文档的[*Microsoft Edge DevTools*](./devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview)部分。

![DevTools 应用程序远程面板](./devtools-guide/media/chooser_remote.png)

## 反馈

请向我们发送您的反馈，以便我们可以继续为您改进 Microsoft Edge DevTools！ 只需打开 "工具" （ `F12` ），然后单击 "[**发送反馈**](#microsoft-edge-developer-tools)" 按钮。

您还可以向[UserVoice 论坛](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer/category/84475-f12-developer-tools)添加和投赞成票刀具请求，并成为[Windows 预览体验成员](https://insider.windows.com/)，以预览[即将进入 DevTools 的最新功能](./devtools-guide/whats-new.md)。 使用 Windows**反馈中心**应用发布、投赞成票、跟踪和获取有关常规 Windows 建议和问题的支持。

## 常规快捷方式

这些快捷方式控制主 DevTools 窗口和/或跨所有工具工作。

操作 | 快捷方式
:------------ | :-------------
显示/隐藏 DevTools （打开到上次查看的面板） | F12，Ctrl + Shift + I
切换停靠（取消停靠/底部/右侧） | Ctrl + Shift + D 
在调试器中显示不可编辑的 HTML 源代码 | Ctrl + U
在任何其他工具的底部显示/隐藏控制台  | Ctrl +**`**
切换到元素（DOM 资源管理器） | Ctrl + 1
切换到控制台 |  Ctrl + 2
切换到调试器 | Ctrl + 3
切换到网络 | Ctrl + 4
切换到性能 | Ctrl + 5
切换到内存 | Ctrl + 6
切换到仿真 | Ctrl + 7
帮助文档 | F1
下一个工具 | Ctrl + F6
上一个工具 | Ctrl + Shift + F6
上一个工具（来自历史记录） | Ctrl + Shift + [
下一个工具（来自历史记录） | Ctrl + Shift +]
下一个 Subframe    | F6
以前的 Subframe | Shift + F6
搜索框中的下一个匹配项 | F3
搜索框中的上一个匹配项 | Shift+F3
在搜索框中查找 | Ctrl+F
向底部的控制台提供焦点 | Alt + Shift + I
固定/取消固定工具（切换坞站） | Ctrl+P  
启动 DevTools 到 Console | Ctrl + Shift + J
刷新页面。 **注意：** 如果你在断点处进行调试和暂停，这将首先继续执行。 | Ctrl + Shift + F5 或 Ctrl + R
