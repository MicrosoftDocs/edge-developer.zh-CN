---
description: '在 EdgeHTML 17 中添加到 Windows 10 2018 年 4 月更新 (Microsoft Edge DevTools) '
title: EdgeHTML 17 中的 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， edgehtml 17
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 937525f349a1db650b795db1efb983f1359fcaa5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232478"
---
# EdgeHTML 17 (Windows 10 2018 年 4 月更新中的 DevTools) 

DevTools 的 EdgeHTML 17 版本以两种方式提供：作为 Microsoft Edge 的传统浏览器内 () 工具，以及从 Microsoft Store 预览为独立 `F12` [Windows 10](#microsoft-edge-devtools-app-preview) 应用！

这些工具已使用许多主要功能进行了更新，包括[](#docking-to-the-right-in-microsoft-edge)通过我们新的[DevTools](#devtools-protocol)协议 (、PWA 调试功能[](../index.md#remote-debugging)[、IndexedDB](#indexeddb-inspection)缓存管理[](#pwa-debugging)、垂直停靠等对远程调试)  (的基本支持！ 作为对性能和可靠性的持续[](./edgehtml-16.md)投资一部分，我们还继续进行上一版本开始的整体重构工作。

以下是[EdgeHTML 17](https://aka.ms/devguide_edgehtml_17)更新版中的 Windows [10 2018](/windows/uwp/whats-new/windows-10-build-17134)年 4 月更新中 (Microsoft Edge DevTools) 。

## Microsoft Edge DevTools 应用预览

![Microsoft Edge DevTools 应用](../../devtools-protocol/media/microsoft-edge-devtools.png) 

Microsoft [Edge DevTools](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj) 现在可从 Microsoft Store 作为独立 Windows 10 应用进行预览。 应用商店版本提供了一个*选择器*面板（用于连接以打开本地和远程页面目标）以及一个选项卡式布局（便于在 DevTools 实例之间进行切换）。 此外，DevTools 应用还能够调试应用 \ (中的 Web 内容，如 Office、Cortana、EdgeHTML [Webview](../../hosting/webview/index.md)和 Windows 安装的 [PWA](../../progressive-web-apps/windows-features.md)\) 。

Edge DevTools 在 () 选择器面板 (中仍 `F12`) 。

将 DevTools 与浏览器分离可提供以下 UX 和体系结构优势：

- DevTools 从 Microsoft Edge 在单独的应用容器沙盒中运行，为两者提供更好的可靠性。
- 该应用提供在活动 DevTools 实例选项卡 (轻松切换，而无需在打开的 Microsoft Edge 选项卡) 
- 我们能够通过跨浏览器 API 检测 *EdgeHTML* 浏览器引擎，并打开它到更大的开发工具 [生态系统](https://github.com/WICG/devtools-protocol/)。
- 我们可以独立于 Windows 应用版和 EdgeHTML (发布周期) DevTools 更新。

查看 *DevTools 指南，* 详细了解使用 [DevTools](../index.md)应用进行本地和远程调试。

## DevTools 协议

开发人员工具可以使用 [**Microsoft Edge DevTools 协议**](../../devtools-protocol/index.md) 来检查和调试 Microsoft Edge 浏览器。 它提供了一组组织到 EdgeHTML 引擎检测的不同 [域中](../../devtools-protocol/0.1/domains/index.md) 的方法和事件。

 工具客户端可以调用这些方法，并通过与 Microsoft Edge 或 Windows Device Portal 托管的 *DevTools 服务器* 交换的 JSON Web 套接字消息来 [监视这些事件](/windows/mixed-reality/using-the-windows-device-portal)。 
 
 Microsoft Edge DevTools 使用此协议[](../../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview)启用从 Microsoft Store 提供的独立[DevTools](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)客户端远程调试运行 Microsoft Edge 的主机。 目前，此预览支持仅限于在另一台桌面设备或 VM 上对另一个边缘进行 JS 调试。 随着时间的推移，我们将针对任何 Windows 10 设备上的任何 EdgeHTML 实例添加对整套 DevTools 的支持。  
 
 最新的 [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) 版本 (Visual Studio 15.7 Preview 1 或更高版本) 使用 DevTools 协议启用从任何 ASP.NET 或 .NET Core 项目的 Visual Studio IDE 中启动和调试 Microsoft Edge (JavaScript 代码) 。

## IndexedDB 检查

此版本的 [**调试**](../debugger.md) 器新增了 [IndexedDB 管理器](../storage.md#indexeddb-manager) ，支持检查和刷新对象存储和删除单个键值条目。 预计未来版本中会有更多的功能。

## PWA 调试

现在默认启用对调试渐进 Web 应用 (PWA) ，为服务工作者、缓存[**API**](../storage.md#cache-manager)和[****](../service-workers.md)[**IndexedDB**](../storage.md#indexeddb-manager)管理提供工具选项卡。

此外，[网络](../network.md#toolbar)面板工具栏有一个新按钮"绕过**** 所有网络请求的服务工作线程"，以作为网络代理打开/关闭注册的服务工作者：

![网络工具栏按钮：绕过所有网络请求的服务工作线程](../media/network_toolbar_bypass_sw.png)

可以通过从独立[DevTools](../index.md#microsoft-store-app)应用选择器中的本地目标 (浏览器选项卡/PWA/webview) 列表中选择[PWA，将 PWA](../../progressive-web-apps/windows-features.md)调试为已安装的 Windows 10 应用。 [****](../../progressive-web-apps/windows-features.md#debug-your-pwa-edgehtml-as-a-windows-app)  

## 固定到 Microsoft Edge 中的右侧

除了停靠在底部和从浏览器窗口取消停靠 DevTools 之外，你现在还可以将 DevTools 停靠在从 Microsoft Edge 中调试的页面的右侧。 用于 `Ctrl+Shift+D` 在扩展坞 **底部**、 **扩展坞右侧**和 **Undock** 位置之间循环，或在 DevTools 右上角的图标之间循环：

![DevTools (未停靠状态) 扩展选项](../media/docking_buttons.png) 
