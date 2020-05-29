---
description: 更新到 Microsoft Edge DevTools 协议
title: Microsoft Edge DevTools 协议更新
author: zoherghadyali
ms.author: zoghadya
ms.date: 03/11/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: f1936a83f948dd17cc76139b7fd67fc73cd692d0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563433"
---
# Microsoft Edge （Chromium） DevTools 协议

通过 Microsoft Edge 的基础 web 平台中的 shift 至 Chromium， [Microsoft edge （EdgeHTML） DevTools 协议](./devtools-protocol/index.md)将不会收到任何进一步的更新。 Microsoft Edge （Chromium） DevTools 协议将匹配 Chrome DevTools 协议的 Api。 

你可以通过参阅[Chrome DevTools 协议查看器](https://chromedevtools.github.io/devtools-protocol/tot/)找到有关这些域和方法的文档。

> [!NOTE]
> Microsoft edge （ `ms` Chromium） DevTools 协议不再支持[microsoft Edge （EdgeHTML） DevTools 协议](./devtools-protocol/index.md)中带前缀的任何方法。

## 使用 DevTools 协议

下面介绍了如何将自定义工具客户端附加到 Microsoft Edge 中的 DevTools 服务器（Chromium）。

1. 确保 Microsoft Edge （Chromium）的所有实例均已关闭。

2. 通过远程调试端口启动 Microsoft Edge （Chromium）：

    ```
    msedge.exe --remote-debugging-port=9222
    ```

3. 或者，如果需要，可以使用不同的用户配置文件启动另一个边缘实例：

    ```
    msedge.exe --user-data-dir=<some directory>
    ```

4. 接下来，使用 HTTP `list` 终结点获取可附加的页面目标的列表：

    ```
    http://localhost:9222/json/list
    ```

5. 最后，连接到 `webSocketDebuggerUrl` 所需的目标并发出命令/通过 DevTools web 套接字服务器订阅事件消息。

## DevTools 协议 HTTP 终结点

Microsoft Edge （Chromium） DevTools 协议支持以下 HTTP 终结点。

## /json/version
提供有关主机计算机的浏览器以及它支持的 DevTools 协议版本的信息。

**参数**

*无*

**返回对象**

```json
{
   "Browser": "Edg/75.0.115.0",
   "Protocol-Version": "1.3",
   "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3739.0 Safari/537.36 Edg/75.0.115.0",
   "V8-Version": "7.5.98",
   "WebKit-Version": "537.36 (@68a98f73c7d0f766fb5a013ea7f8dbb41089bc1b)",
   "webSocketDebuggerUrl": "ws://localhost:9222/devtools/browser/a9d0e8cf-476a-4a89-bba9-0fc27ce691cd"
}
```

## /json/protocol

提供序列化为 JSON 的整个协议 API 图面。

**参数**

*无*

**返回对象**

JSON 对象，表示当前版本的协议的可用 API 图面。

## /json/list

提供用于调试的页面目标的候选列表。

**参数**

*无*

**返回对象**

```json
[{
   "description": "",
   "devtoolsFrontendUrl": "/devtools/inspector.html?ws=localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989",
   "id": "AB07C11A262D1EC8634EB12E2DCA4989",
   "title": "localhost:9222/json/protocol",
   "type": "page",
   "url": "http://localhost:9222/json/list",
   "webSocketDebuggerUrl": "ws://localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989"
}, … ]
```

## /json/close

关闭目标进程（例如，在 Microsoft Edge 中（Chromium），关闭页面选项卡。）

**参数**

目标 ID 

**返回对象**

```
String(“Target is closing”)
```

## Microsoft Edge 远程工具（Beta 版）

现在，你可以从[Microsoft Store](https://www.microsoft.com/store/apps/windows)安装[Microsoft Edge 远程工具（Beta）](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) 。 此应用使你能够从你的开发计算机远程调试运行在 Windows 10 设备上的 Microsoft Edge （Chromium）。

若要了解如何设置 Windows 10 设备并从开发计算机连接到该设备，请查看[本教程](./devtools-guide-chromium/remote-debugging/windows.md)。

[适用于 Microsoft edge 的远程工具（Beta）](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)将相同的 microsoft Edge （Chromium） DevTools 协议用作[DevTools](./devtools-guide-chromium.md) ，以与运行在你想要调试的 Windows 10 设备上的 microsoft edge 通信。 `/msedge/`在每次调用该协议之前，此应用只需预先操作和进程 ID （ `pid` ）。 它支持以下 HTTP 终结点。

### /msedge/json/list

`msedge.exe`在 Windows 10 设备上提供用于调试的所有进程（包括[PWAs](./progressive-web-apps-chromium/index.md)和所有 Microsoft Edge 实例中的所有选项卡）的候选列表。

**参数**

*无*

**返回对象**

```json
[{
   "description": "",
    "devtoolsFrontendUrl": "http://172.17.75.195:80/msedge/7264/devtools/inspector.html?ws=172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB",
    "faviconUrl": "https://docs.microsoft.com/favicon.ico",
    "id": "ED4FFDB4529723A0FAFCBDB9B45851BB",
    "title": "Get Started with Remote Debugging Windows 10 Devices - Microsoft Edge Development | Microsoft Docs",
    "type": "page",
    "url": "https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/remote-debugging/windows",
    "webSocketDebuggerUrl": "ws://172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB",
    "browserProcessId": 7264
}, … ]
```

### /msedge/

在功能上等效于[/msedge/json/list](#msedgejsonlist)。 

### /msedge/[pid]/json/list

为 Microsoft Edge 实例提供与提供的用于调试匹配的目标的候选列表 `[pid]` 。

**参数**

*无*

**返回对象**

```json
[{
    "description": "",
    "devtoolsFrontendUrl": "http://172.17.75.195:80/msedge/7264/devtools/inspector.html?ws=172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB",
    "faviconUrl": "https://docs.microsoft.com/favicon.ico",
    "id": "ED4FFDB4529723A0FAFCBDB9B45851BB",
    "title": "Get Started with Remote Debugging Windows 10 Devices - Microsoft Edge Development | Microsoft Docs",
    "type": "page",
    "url": "https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide-chromium/remote-debugging/windows",
    "webSocketDebuggerUrl": "ws://172.17.75.195:80/msedge/7264/devtools/page/ED4FFDB4529723A0FAFCBDB9B45851BB"
}, … ]
```

### /msedge/[pid]/json/version

提供与所提供的 `[pid]` 和其支持的 DevTools 协议版本相匹配的 Microsoft Edge 实例的相关信息。

**参数**

*无*

**返回对象**

```json
{
    "Browser": "Edg/82.0.452.0",
    "Protocol-Version": "1.3",
    "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/82.0.4080.0 Safari/537.36 Edg/82.0.452.0",
    "V8-Version": "8.2.263",
    "WebKit-Version": "537.36 (@fe0232051787ca94ac8edfc0084c3488b7d9bdb2)",
    "webSocketDebuggerUrl": "172.17.75.195:80/msedge/7264/devtools/browser/7a67c8c4-138b-48e3-bfe0-cb7af34d559a"
}
```

### /msedge/[pid]/json/protocol/

为与所提供的 Microsoft Edge 实例匹配的 Microsoft Edge 实例提供完整的协议 API 图面序列化为 JSON `[pid]` 。

**参数**

*无*

**返回对象**

JSON 对象，表示与所提供的 Microsoft Edge 实例匹配的 Microsoft Edge 实例所使用的协议版本的可用 API 图面 `[pid]` 。
