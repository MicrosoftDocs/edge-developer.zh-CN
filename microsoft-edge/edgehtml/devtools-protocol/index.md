---
description: 使用 Microsoft Edge DevTools 协议检查和调试 Microsoft Edge (EdgeHTML) 浏览器。
title: Microsoft Edge DevTools 协议
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2ba81e51d3f9abd2aa2011993532566885ce553f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232456"
---
# Microsoft Edge (EdgeHTML) DevTools 协议

> [!NOTE]
> Microsoft Edge (EdgeHTML) DevTools 协议仅适用于 [Windows 10 2018](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 年 4 月更新和更高版本。

开发人员工具可以使用 **Microsoft Edge (EdgeHTML) DevTools** 协议检查和调试 Microsoft Edge (EdgeHTML) 浏览器。 它提供了一组组织到 EdgeHTML 引擎检测的不同 [域中](0.2/domains/index.md) 的方法和事件。

 工具客户端可以调用这些方法，并通过与由 Microsoft Edge (EdgeHTML) 或 Windows Device Portal 托管的 *DevTools Server* 交换的 JSON Web 套接字消息来监视这些事件。 Microsoft Edge (EdgeHTML) DevTools 使用此协议启用从[](0.2/clients.md#microsoft-edge-devtools-preview)Microsoft Store 提供的独立 DevTools 客户端远程调试运行 Microsoft Edge (EdgeHTML) 的[主机](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)。

Microsoft Edge (EdgeHTML) DevTools 协议旨在与 Chrome DevTools 协议 (请参阅 [适用于 DevTools 协议的 W3C WICG](https://github.com/WICG/devtools-protocol/)) ，尽管此版本存在已知的互操作性差异。

## 使用协议

下面将了解如何将自定义工具客户端附加到 Microsoft Edge 中的 DevTools Server (EdgeHTML) 。 如果使用 [Microsoft](0.2/clients.md#microsoft-edge-devtools-preview) Edge DevTools 作为客户端，请参阅远程调试说明。

1. 启动 Microsoft Edge (EdgeHTML) 远程调试端口处于打开状态，并指定要打开的 URL。 例如：

    ```shell
    MicrosoftEdge.exe --devtools-server-port 9222 https://www.bing.com
    ```

    如果边缘已启动，URL 参数是可选的。 浏览器地址栏旁边将显示一个按钮，以指示 **开发人员工具服务器** 已启动：

    ![开发人员工具服务器](media/developer-tools-server.png) 

2. 使用此 [HTTP 终结点](0.2/http.md) 获取可附加页面目标的列表：

    ```http
    http://localhost:9222/json/list
    ```

3. 连接到所需页面的列表，以 `webSocketDebuggerUrl` 发出进一步 [的协议命令](0.2/domains/index.md) 并通过 devtools 套接字服务器接收事件消息。

## 状态和反馈

除[版本 0.1](0.2/index.md)中引入的核心脚本调试功能外，DevTools 协议版本[0.2](0.1/index.md)还提供了样式和布局的新域 (只读) 调试和控制台 API。 在 Microsoft Edge DevTools UI 中，这转换为元素、[****](../devtools-guide/elements.md)控制台和[****](../devtools-guide/console.md)调试器面板[**中提供**](../devtools-guide/debugger.md)的功能。

感谢尝试 Edge DevTools 协议！ 我们喜欢在：

 - [**Microsoft Edge 开发人员 UserVoice：DevTools**](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer?category_id=84475)功能想法和请求

 - [**EdgeHTML 问题跟踪程序**](https://developer.microsoft.com/microsoft-edge/platform/issues/)：协议、DevTools 和 EdgeHTML 平台 Bug 和问题

 - [**Microsoft Edge DevTools 反馈中心**](feedback-hub:?referrer=microsoftEdge&tabID=2&newFeedback=true&ContextId=344)：通过反馈中心应用的协议和 DevTools 问题和建议

## 常见问题

#### 多个客户端能否连接到同一个 DevTools 服务器？
否，在客户端调试时不能同时进行。 最后一个要连接的客户端将启动上一个客户端。 在将来支持其他工具时，这些工具可能支持同时进行客户端连接。

#### 我是否必须使用 9222 作为 DevTools 服务器端口？
否。 您可以指定任何端口，但请务必选取尚未使用的端口。 用于远程调试的端口 9222 按惯例使用。

#### 如何将我的自定义工具客户端连接到运行 DevTools (EdgeHTML) Microsoft Edge？
请参阅 [*使用上述协议*](#using-the-protocol) 说明连接到本地计算机上 (运行的 EdgeHTML) Microsoft Edge。 如果你希望支持远程调试，则需要设计一个用户工作流，以在客户端上安装主机的 SSL 证书，例如，在 [Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview) 使用安装对话框时。

#### 如果我使用 Edge DevTools 进行远程调试，是否需要使用 *--devtools-server-port* cmd 线路交换机启动主机浏览器进程？ 
否。 如果使用 Microsoft Edge [DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview)设置远程调试，则启动 Edge 时不需要 `--devtools-server-port` 命令行开关。 在这种情况下，Windows *Device Portal* 代表浏览器托管 DevTools Server。

#### 我能否使用边缘开发人员工具协议远程调试WWAHost.exe或 Webview 进程？
边缘 DevTools 协议当前仅支持浏览器选项卡。 WWAHost.exe webview 进程不受支持。
