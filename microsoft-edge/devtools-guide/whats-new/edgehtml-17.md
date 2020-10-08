---
description: 2018年4月更新 (EdgeHTML 17) 中添加到 Microsoft Edge DevTools 的功能
title: DevTools EdgeHTML 17
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、edgehtml 17
ms.custom: seodec18
ms.openlocfilehash: cc110071422f858acf840c1eaf100696a6e3cf03
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563434"
---
# DevTools 2018 年4月更新 (EdgeHTML 17) 

DevTools 的 EdgeHTML 17 版以两种方式提供：作为传统的浏览器 (`F12`) Microsoft Edge 的工具，并从 Microsoft Store 中预览为独立的 [Windows 10 应用](#microsoft-edge-devtools-app-preview) ！

这些工具已经过大量主要功能的更新，包括对 [远程调试](../../devtools-guide.md#remote-debugging) (的基本支持，通过我们的新的 [DevTools 协议](#devtools-protocol)) 、 [PWA 调试功能](#pwa-debugging)、 [IndexedDB 缓存管理](#indexeddb-inspection)、 [垂直停靠](#docking-to-the-right-in-microsoft-edge) 等！ 我们还继续在性能和可靠性方面作为日常投资的一部分，开始上次发布的整体 [重构工作](./edgehtml-16.md) 。

下面是 [Windows 10 2018 年4月更新](/windows/uwp/whats-new/windows-10-build-17134) ([EdgeHTML 17](https://aka.ms/devguide_edgehtml_17)) 中提供的最新 Microsoft Edge DevTools 功能。

## Microsoft Edge DevTools 应用预览

![Microsoft Edge DevTools 应用](../../devtools-protocol/media/microsoft-edge-devtools.png) 

[**Microsoft Edge DevTools**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)现在可用作 microsoft Store 中的独立 Windows 10 应用的预览版。 应用商店版本提供了一个*选择器*面板（用于连接以打开本地和远程页面目标）以及一个选项卡式布局（便于在 DevTools 实例之间进行切换）。 此外，DevTools 应用的独占功能是在 (应用中调试 web 内容的功能，例如 Office、Cortana、EdgeHTML [web 视图](../../webview.md)和 [Windows 安装的 PWAs](../../progressive-web-apps-edgehtml/windows-features.md)) 的加载项。

此外，还可 `F12` 从浏览 (器中 () 边缘 DevTools，但不) 选择器面板。

将 DevTools 与浏览器相分离可提供以下 UX 和体系结构优势：

- DevTools 在单独的应用容器沙盒中从 Microsoft Edge 运行，从而提供更高的可靠性。
- 该应用提供了在活动的 DevTools 实例选项 (卡之间轻松切换的功能，而无需在打开的 Microsoft Edge 选项卡之间切换) 
- 我们能够检测 *EdgeHTML* 浏览器引擎，并通过 [跨浏览器 api](https://github.com/WICG/devtools-protocol/)将其打开到更大的 devtools 生态系统。
- 我们可以独立于 Windows (和 EdgeHTML) 发布周期装运 DevTools 更新。

有关[使用 DevTools 应用进行本地和远程调试](../../devtools-guide.md)的详细信息，请参阅*DevTools 指南*。

## DevTools 协议

开发人员工具可以使用 [**Microsoft Edge DevTools 协议**](../../devtools-protocol/index.md) 来检查和调试 Microsoft edge 浏览器。 它提供了一组方法和事件，这些方法和事件组织到 EdgeHTML 引擎规范的不同 [域](../../devtools-protocol/0.1/domains/index.md) 中。

 工具客户可以通过与由 Microsoft Edge 或[Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal)托管的*DevTools 服务器*交换的 JSON web 套接字消息来调用这些方法并监视这些事件。 
 
 Microsoft Edge DevTools 使用此协议，从 Microsoft Store 提供的[独立 DevTools 客户端](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)开始对运行 microsoft Edge 的主机进行[远程调试](../../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview)。 当前，此预览支持仅限于对另一个桌面设备或 VM 上的另一边缘的 JS 调试。 随着时间的推移，我们将为任何 Windows 10 设备上的任何 EdgeHTML 实例添加对完整 DevTools 集的支持。  
 
  (Visual Studio 15.7 Preview 1 或更高版本中的最新 [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) 预览版) 使用 DevTools 协议从任何 ASP.NET 或 .net Core 项目的 VISUAL Studio IDE 中启用 Microsoft Edge (JavaScript 代码) 。

## IndexedDB 检查

[**调试器**](../debugger.md)的新增版本此版本是[IndexedDB 管理器](../storage.md#indexeddb-manager)，支持检查和刷新对象存储和删除单个键值条目。 将来的版本中预计还会有更多的功能。

## PWA 调试

支持调试渐进式 Web 应用 (PWAs) 现在在默认情况下处于启用状态，为 [**服务工作人员**](../service-workers.md)、 [**缓存 API**](../storage.md#cache-manager)和 [**IndexedDB**](../storage.md#indexeddb-manager) 管理提供工具选项卡。

此外，" [网络" 面板工具栏](../network.md#toolbar) 上有一个 "新建" 按钮， **跳过所有网络请求的服务工作人员**，以将您的注册服务工作人员切换为网络代理：

!["网络" 工具栏按钮：绕过所有网络请求的服务工作人员](../media/network_toolbar_bypass_sw.png)

你可以将[PWA 调试为已安装的 Windows 10 应用](../../progressive-web-apps-edgehtml/windows-features.md)，方法是从[DevTools 应用](../../devtools-guide.md#microsoft-store-app)的选择器中的浏览器选项卡/PWA/Web 视图) 选择[**本地**](../../progressive-web-apps-edgehtml/windows-features.md#debug-your-pwa-edgehtml-as-a-windows-app) (目标列表。  

## 在 Microsoft Edge 中停靠到右侧

现在，除了停靠在浏览器窗口的底部，还可以将 DevTools 停靠在你正在从 Microsoft Edge 中调试的页面右侧。 用于 `Ctrl+Shift+D` 在 **停靠**位置、 **停靠右侧**和取消 **停靠** 位置之间循环，或 DevTools 的右上角中的图标：

![DevTools (处于未插接状态) 停靠选项](../media/docking_buttons.png) 
