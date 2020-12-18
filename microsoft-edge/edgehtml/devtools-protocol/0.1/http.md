---
description: Microsoft Edge DevTools 协议版本 0.1 支持以下 HTTP 终结点。
title: 'DevTools 协议版本 0.1 HTTP 终结点 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5fe50122728304de137efdfb25ebed7274c55cee
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232094"
---
# DevTools 协议版本 0.1 HTTP 终结点 (EdgeHTML)   

> [!NOTE]
> Microsoft Edge DevTools 协议仅适用于 [Windows 10 2018 年 4](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) 月更新和 [更高版本的 Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) 版本。

**DevTools 协议 0.1** 支持以下 HTTP 终结点。 有关[连接到浏览器](../index.md#using-the-protocol)内容过程和基于完整 Web 套接字的开发工具协议[](domains/index.md)API 的域文档，请参阅使用该协议。

## /json/version
提供有关主机浏览器及其支持的 DevTools 协议版本的信息。

**参数**

*无*

**Return 对象**

```json
{
    "Browser":"Edge/17.17627",
    "Protocol-Version":"0.1",
    "User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.140 Safari/537.36 Edge/17.17627"
}
```

## /json/protocol

提供序列化为 JSON 的整个协议 API 图面。

**参数**

*无*

**Return 对象**

JSON 对象，该对象表示协议当前版本的可用 API 图面。

## /json/list

提供用于调试的页面目标的候选列表。

**参数**

*无*

**Return 对象**

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

关闭目标进程 (例如，在 Microsoft Edge 中关闭页面选项卡。) 

**参数**

目标 ID 

**Return 对象**

```
String("Target is closing")
```
