---
description: 使用 Microsoft Edge DevTools 协议检查和调试 Microsoft Edge （EdgeHTML）浏览器。
title: Microsoft Edge DevTools 协议
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/11/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 8bef24c98dae284f2111f6a16fca4a6f27c89dc4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563391"
---
# Microsoft Edge （EdgeHTML） DevTools 协议

> [!NOTE]
> Microsoft Edge （EdgeHTML） DevTools 协议仅适用于[2018 年4月更新](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)和更高版本的 Windows 10。

开发人员工具可以使用**Microsoft edge （EdgeHTML） DevTools 协议**检查和调试 Microsoft Edge （EdgeHTML）浏览器。 它提供了一组方法和事件，这些方法和事件组织到 EdgeHTML 引擎规范的不同[域](0.2/domains/index.md)中。

 工具客户可以通过与由 Microsoft Edge （EdgeHTML）或 Windows Device Portal 托管的*DevTools 服务器*交换的 JSON web 套接字消息来调用这些方法并监视这些事件。 Microsoft Edge （EdgeHTML） DevTools 使用此协议，从[Microsoft Store](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)提供的独立 DevTools 客户端开始[远程调试](0.2/clients.md#microsoft-edge-devtools-preview)运行 microsoft Edge （EdgeHTML）的主机。

Microsoft Edge （EdgeHTML） DevTools 协议设计为与 Chrome DevTools 协议密切对齐（请参阅[W3C WICG For DevTools 协议](https://github.com/WICG/devtools-protocol/)），尽管此版本中有已知的互操作性差距。

## 使用协议

下面介绍了如何将自定义工具客户端附加到 Microsoft Edge 中的 DevTools 服务器（EdgeHTML）。 如果您使用的是 Microsoft Edge DevTools 作为客户，请参阅[远程调试](0.2/clients.md#microsoft-edge-devtools-preview)说明。

1. 在远程调试端口打开的情况下启动 Microsoft Edge （EdgeHTML），指定要打开的 URL。 例如：

    ```
    MicrosoftEdge.exe --devtools-server-port 9222 https://www.bing.com
    ```

    如果 Edge 已启动，则 URL 参数是可选的。 浏览器地址栏旁边将显示一个按钮，指示**开发人员工具服务器**已启动：

    ![开发人员工具服务器](media/developer-tools-server.png) 

2. 使用此[HTTP 终结点](0.2/http.md)获取可附加的页面目标的列表：

    ```
    http://localhost:9222/json/list
    ```

3. 连接到所需页面的列出， `webSocketDebuggerUrl` 通过 devtools 套接字服务器发出更多[协议命令](0.2/domains/index.md)并接收事件消息。

## 状态和反馈

除了[版本 0.1](0.1/index.md)中引入的核心脚本调试功能之外，DevTools 协议的[版本 0.2](0.2/index.md)还提供了新域用于样式和布局（只读）调试和控制台 api。 在 Microsoft Edge DevTools UI 中，这将转换为[**元素**](../devtools-guide/elements.md)、[**控制台**](../devtools-guide/console.md)和[**调试器**](../devtools-guide/debugger.md)面板中可用的功能。

感谢你试用 Edge DevTools 协议！ 我们乐意在以下网址听到您的反馈意见：

 - [**Microsoft Edge 开发人员 UserVoice**](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer?category_id=84475)： DevTools 功能创意和请求

 - [**EdgeHTML 问题跟踪**](https://developer.microsoft.com/microsoft-edge/platform/issues/)器：协议、DevTools 和 EdgeHTML 平台错误和问题

 - [**Microsoft Edge DevTools 反馈中心**](feedback-hub:?referrer=microsoftEdge&tabID=2&newFeedback=true&ContextId=344)：通过 "反馈中心" 应用的协议和 DevTools 问题和建议

## 常见问题解答

#### 多个客户端是否可以连接到同一 DevTools 服务器？
否，客户端在调试时不会同时进行。 最后一个要连接的客户端将启动以前的客户端。 将来，当支持其他工具时，这些工具可能支持同时进行的客户端连接。

#### 是否必须将9222用作 DevTools 服务器端口？
否。 你可以指定任何端口，但确保选择一个尚未使用的端口。 约定使用端口9222进行远程调试。

#### 如何将自定义工具客户端连接到运行 DevTools 服务器的 Microsoft Edge （EdgeHTML）？
有关附加到在本地计算机上运行的 Microsoft Edge （EdgeHTML）的协议说明，请参阅[*使用上述协议*](#using-the-protocol)说明。 如果你希望支持远程调试，你将需要设计用户工作流，以便在客户端上安装主机的 SSL 证书，例如安装对话框是[Microsoft Edge DevTools Preview](./0.2/clients.md#microsoft-edge-devtools-preview)使用。

#### 如果我是使用 Edge DevTools 进行远程调试，是否需要使用 *--DevTools 服务器端口*命令行开关启动主浏览器进程？ 
否。 如果你正在[使用 Microsoft Edge DevTools Preview 设置远程调试](./0.2/clients.md#microsoft-edge-devtools-preview)，则 `--devtools-server-port` 命令行开关不是开始边缘所必需的。 在这种情况下，Windows *Device Portal*将代表浏览器托管 DevTools 服务器。

#### 是否可以使用 Edge DevTools 协议远程调试 WWAHost 或 web 视图过程？
Edge DevTools 协议当前仅支持浏览器选项卡。 不支持 WWAHost 和 web 视图进程。
