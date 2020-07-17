---
description: Microsoft Edge DevTools 协议版本0.2 支持以下 HTTP 终结点。
title: Microsoft Edge DevTools 协议版本 0.2 HTTP 终结点（EdgeHTML）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: eb5b29e4d8149f511d8a7cbca3da72391a13e449
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882851"
---
# Microsoft Edge DevTools 协议版本 0.2 HTTP 终结点（EdgeHTML）  

> [!NOTE]
> Microsoft Edge DevTools 协议的版本0.2 仅适用于[windows 10 10 月2018更新]()及更高版本的[Windows 预览体验计划预览版](https://insider.windows.com/en-us/getting-started/)。

**DevTools 协议 0.2**支持以下 HTTP 终结点。 有关连接到浏览器内容流程和完整的基于 web 套接字的 devtools 协议 API 的[域](domains/index.md)文档，请参阅[使用该协议](../index.md#using-the-protocol)。

## /json/version
提供有关主机计算机的浏览器以及它支持的 DevTools 协议版本的信息。

**参数**

*无*

**返回对象**

```json
{
    "Browser":"Edge/18.17763",
    "Protocol-Version":"0.2",
    "User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.140 Safari/537.36 Edge/18.17763"
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
    "id":"000001F5-87EE-4D55-0091-C4C08A1F30C8",
    "title":"Microsoft Edge Developer website - Microsoft Edge Development",
    "type":"Page",
    "url":"https://developer.microsoft.com/microsoft-edge/",
    "webSocketDebuggerUrl":"ws://localhost:9222/target/000001F5-87EE-4D55-0091-C4C08A1F30C8"
}, … ]
```

## /json/close

关闭目标进程（例如，在 Microsoft Edge 中关闭页面选项卡。）

**参数**

目标 ID 

**返回对象**

```
String("Target is closing")
```
