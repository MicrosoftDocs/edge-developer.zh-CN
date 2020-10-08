---
description: 了解 Microsoft Edge 开发人员工具
title: Microsoft Edge 开发人员工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: edgehtml
keywords: microsoft edge, web 开发, f12 工具, devtools
experimental: false
experiment_id: 51fe4b97-3e55-41
ms.openlocfilehash: 3aee2ab67c6e703a0a31b58b5bf985a23fcbb481
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10986218"
---
# Microsoft Edge 开发人员工具  

> [!NOTE]
> Microsoft Edge DevTools 帮助 web 开发人员构建和测试网站。  如果意外打开了 DevTools，只需按下 `F12` 即可关闭。  

Microsoft Edge DevTools 是通过[开放源代码](https://github.com/Microsoft/ChakraCore)（针对新式前端工作流进行了优化）[生成的，](https://www.typescriptlang.org/)现在可在 Microsoft Store 中作为[独立的 Windows 10 应用](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)使用。

有关最新功能的详细信息，请参阅 [*Windows 10 (EdgeHTML 17) 的最新更新 DevTools *](./devtools-guide/whats-new.md)。

## 核心工具

![Microsoft Edge 开发工具](./devtools-guide/media/devtools.png)

Microsoft Edge DevTools 包括：

 - " [**元素**](./devtools-guide/elements.md) " 面板，用于编辑 HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 转变断点
 - 用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点以及在所选窗口或框架的上下文中运行 JavaScript 的[**控制台**](./devtools-guide/console.md)
 - 用于逐句通过代码、设置监视和断点、实时编辑代码以及检查 web 存储和 cookie 缓存的[**调试器**](./devtools-guide/debugger.md)
 - 用于监视和检查来自网络和浏览器缓存的请求和响应的 [**网络**](./devtools-guide/network.md) 面板 
 - 用于分析你的网站所需的时间和系统资源的 [**性能**](./devtools-guide/performance.md) 面板
 - 用于测量内存资源使用情况并比较不同代码执行状态的堆快照的 [**内存**](./devtools-guide/memory.md) 面板
 - 用于使用不同浏览器配置文件、屏幕分辨率和 GPS 位置坐标测试网站的 [**仿真**](./devtools-guide/emulation.md) 面板

请继续发送您的 [反馈和功能请求](#getting-in-touch-with-the-microsoft-edge-devtools-team)。

> [!TIP]
> **[从任何浏览器免费测试 Microsoft edge](https://developer.microsoft.com/microsoft-edge/tools/remote/)**：我们与 [BrowserStack](https://www.browserstack.com/test-on-microsoft-edge-browser#live-cloud) 合作，在 microsoft edge 上提供免费实时和自动测试。

## Microsoft Store 应用

**Microsoft Edge DevTools** [现在可](./devtools-guide/whats-new.md)用作 microsoft Store 中的独立[Windows 10 应用](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)，除了浏览器中 (`F12`) 工具体验。 应用商店版本提供了一个*选择器*面板（用于连接以打开本地和远程页面目标）以及一个选项卡式布局（便于在 DevTools 实例之间进行切换）。

### 本地调试

若要在本地调试页面，只需启动 *Microsoft Edge DevTools* 应用。 选择器的 **本地** 面板将显示所有活动的 EdgeHTML 内容进程，包括打开的边缘浏览器选项卡、运行 [PWAs](./progressive-web-apps-edgehtml/index.md) (*WWAHost.exe* 进程) 和 [web 视图](./webview.md) 控件。 单击所需的目标以附加并打开 DevTools 的新选项卡实例。

![DevTools 应用的“本地”面板](./devtools-guide/media/chooser_local.png)

### 远程调试

*Microsoft Edge DevTools*应用通过我们新发布的[**DevTools 协议**](./devtools-protocol/index.md)引入了对远程计算机上的页面调试的基本支持。 通过此版本，可在 [**调试程序**](./devtools-guide/debugger.md) 面板中远程访问核心 funtionality，减去 Web 存储、服务工作人员、缓存 API 和 IndexedDB) 的缓存检查 (。 远程调试仅限于 *Microsoft Edge* 运行 *桌面* 主机，并且支持其他 EdgeHTML 主机和在未来版本中推出的 Windows 10 设备。

若要开始，请查看“[DevTools 协议](./devtools-protocol/index.md)”文档的“[*Microsoft Edge DevTools*](./devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview)”部分。

![DevTools 应用“远程”面板](./devtools-guide/media/chooser_remote.png)

## 常规快捷方式

这些快捷方式控制主 DevTools 窗口和/或跨所有工具工作。

操作 | 快捷方式
:------------ | :-------------
显示/隐藏 DevTools (打开上一次查看的面板)  | F12，Ctrl + Shift + I
切换停靠 (脱开/下/右)  | Ctrl + Shift + D 
在调试程序中显示不可编辑的 HTML 源代码 | Ctrl + U
在任何其他工具底部显示/隐藏“控制台”  | Ctrl +**`**
切换到 DOM 资源管理器 (的元素)  | Ctrl + 1
切换到“控制台” |  Ctrl + 2
切换到“调试程序” | Ctrl + 3
切换到“网络” | Ctrl + 4
切换到“性能” | Ctrl + 5
切换到“内存” | Ctrl + 6
切换到“枚举” | Ctrl + 7
帮助文档 | F1
下一个工具 | Ctrl + F6
上一个工具 | Ctrl + Shift + F6
以前的工具 (历史记录)  | Ctrl + Shift + [
"下一工具" ("历史记录")  | Ctrl + Shift +]
下一个子框架    | F6
上一个子框架 | Shift + F6
搜索框中的下一个匹配项 | F3
搜索框中的上一个匹配项 | Shift+F3
在搜索框中查找 | Ctrl+F
将焦点放在底部的控制台上 | Alt + Shift + I
停靠/取消停靠工具 (切换停靠)  | Ctrl+P  
启动 DevTools 到“控制台” | Ctrl + Shift + J
刷新页面。 **注意：** 如果你在断点处进行调试和暂停，这将首先继续执行。 | Ctrl + Shift + F5 或 Ctrl + R

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](./devtools-guide-chromium/includes/contact-devtools-team-note.md)]  
