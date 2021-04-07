---
description: 更新到 Microsoft Edge DevTools 协议
title: Microsoft Edge DevTools 协议更新
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/06/2021
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: de7d6c39c09ba321f21b34e6e461ec030f09f6ad
ms.sourcegitcommit: 146072bf606b84e5145a48333abf9c6b892a12d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "11480158"
---
# <a name="microsoft-edge-chromium-devtools-protocol-overview"></a>Microsoft Edge (Chromium) DevTools 协议概述  

随着 Microsoft Edge 的基础 Web 平台向 Chromium 的转移 [，Microsoft Edge (EdgeHTML) DevTools 协议](/archive/microsoft-edge/legacy/developer/devtools-protocol/index) 将不会接收任何进一步的更新。  Microsoft Edge \ (Chromium\) DevTools 协议将匹配 Chrome DevTools 协议的 API。  

可以通过引用 [Chrome DevTools](https://chromedevtools.github.io/devtools-protocol/tot)协议查看器来查找有关这些域和方法的文档。  

> [!NOTE]
> `ms`Microsoft Edge \ (Chromium\) [DevTools 协议不再支持在 Microsoft Edge (EdgeHTML) DevTools](/archive/microsoft-edge/legacy/developer/devtools-protocol/index)协议中作为前缀的任何方法。  

## <a name="using-the-devtools-protocol"></a>使用 DevTools 协议  

下面将了解如何将自定义工具客户端附加到 Microsoft Edge \ (Chromium\) 中的 DevTools 服务器。  

1.  确保关闭 Microsoft Edge \ (Chromium\) 实例。  
1.  使用远程调试 (启动 Microsoft Edge \) Chromium\) 。 
    
    ```shell
    msedge.exe --remote-debugging-port=9222
    ```  
    
1.  （可选）如果需要，可以使用不同的用户配置文件启动单独的 Edge 实例。  
    
    ```shell
    msedge.exe --user-data-dir=<some directory>
    ```  
    
1.  接下来，使用 HTTP `list` 终结点获取可附加页面目标的列表。  
    
    ```http
    http://localhost:9222/json/list
    ```  
    
1.  最后，通过 DevTools Web 套接字服务器连接到所需目标的 并发出命令 `webSocketDebuggerUrl` /订阅事件消息。  

## <a name="devtools-protocol-http-endpoints"></a>DevTools 协议 HTTP 终结点  

Microsoft Edge \ (Chromium\) DevTools 协议支持以下 HTTP 终结点。  

## <a name="jsonversion"></a>/json/version  

提供有关主机的浏览器及其支持的 DevTools 协议的哪个版本的信息。  

**参数**  

**无**  

**Return 对象**  

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

## <a name="jsonprotocol"></a>/json/protocol  

提供序列化为 JSON 的整个协议 API 图面。  

**参数**  

**无**  

**Return 对象**  

表示协议当前版本的可用 API 图面的 JSON 对象。  

## <a name="jsonlist"></a>/json/list  

提供用于调试的页面目标的候选列表。  

**参数**  

**无**  

**Return 对象**  

```json
[{
   "description": "",
   "devtoolsFrontendUrl": "/devtools/inspector.html?ws=localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989",
   "id": "AB07C11A262D1EC8634EB12E2DCA4989",
   "title": "localhost:9222/json/protocol",
   "type": "page",
   "url": "http://localhost:9222/json/list",
   "webSocketDebuggerUrl": "ws://localhost:9222/devtools/page/AB07C11A262D1EC8634EB12E2DCA4989"
}, ...  ]
```  

## <a name="jsonclose"></a>/json/close  

关闭目标进程 \ (例如，在 Microsoft Edge \ (Chromium\) 中，关闭页面选项卡\) 。  

**参数**  

目标 ID  

**Return 对象**  

```
String(“Target is closing”)
```  

## <a name="remote-tools-for-microsoft-edge-beta"></a>Microsoft Edge 适用的远程工具 (Beta)  

现在，你可以从 Microsoft Store 安装[适用于 Microsoft Edge (Beta) ](https://www.microsoft.com/store/apps/9P6CMFV44ZLT)[远程工具](https://www.microsoft.com/store/apps/windows)。  此应用使你能够远程调试在开发 (Windows 10) 上运行的 Microsoft Edge 和 Chromium。  

若要了解如何设置 Windows 10 设备，以及如何从开发计算机连接到该设备，请导航到远程调试 [Windows 10](../devtools-guide-chromium/remote-debugging/windows.md)设备入门。  

适用于 [Microsoft Edge (Beta) ](https://www.microsoft.com/store/apps/9P6CMFV44ZLT) 的远程工具使用与 [DevTools](../devtools-guide-chromium/index.md) 相同的 Microsoft Edge (Chromium) DevTools 协议与在你要调试的 Windows 10 设备上运行的 Microsoft Edge 进行通信。  每次调用协议之前，此应用程序只是预先 () `/msedge/` `pid` 进程 ID。  它支持以下 HTTP 终结点。  

### <a name="msedgejsonlist"></a>/msedge/json/list  

提供所有进程 \ (的候选列表，包括 `msedge.exe` [PBA](../progressive-web-apps-chromium/index.md) 和 Windows 10 设备上 Microsoft Edge\) 的所有实例的所有选项卡进行调试。  

**参数**  

**无**  

**Return 对象**  

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
}, ...  ]
```  

### <a name="msedge"></a>/msedge/  

在功能上等同于 [/msedge/json/list](#msedgejsonlist)。  

### <a name="msedgepidjsonlist"></a>/msedge/[pid]/json/list  

提供与提供的调试匹配的 Microsoft Edge 实例的候选页面 `[pid]` 目标列表。  

**参数**  

**无**  

**Return 对象**  

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
}, ...  ]
```  

### <a name="msedgepidjsonversion"></a>/msedge/[pid]/json/version  

提供有关与提供的 Microsoft Edge 实例以及它支持的 `[pid]` DevTools 协议版本匹配的信息。  

**参数**  

**无**  

**Return 对象**  

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

### <a name="msedgepidjsonprotocol"></a>/msedge/[pid]/json/protocol/  

为与提供的 匹配 Microsoft Edge 实例提供序列化为 JSON 的整个协议 API 图面 `[pid]` 。  

**参数**  

**无**  

**Return 对象**  

JSON 对象，表示 Microsoft Edge 实例使用的协议版本的可用 API `[pid]` 图面。  
