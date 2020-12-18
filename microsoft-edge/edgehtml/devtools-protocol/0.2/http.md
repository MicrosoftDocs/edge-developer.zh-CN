---
description: Microsoft Edge DevTools 协议版本 0.2 支持以下 HTTP 终结点。
title: 'Microsoft Edge DevTools 协议版本 0.2 HTTP 终结点 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a0e100cee6a73d688b9b74a9b38d1dd37722428f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232458"
---
# <span data-ttu-id="fca58-103">Microsoft Edge DevTools 协议版本 0.2 HTTP 终结点 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="fca58-103">Microsoft Edge DevTools Protocol Version 0.2 HTTP Endpoints (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="fca58-104">Microsoft Edge DevTools 协议的版本 0.2 仅适用于 [Windows 10 2018 年 10 月]() 更新和更高版本的 Windows Insider [Preview](https://insider.windows.com/en-us/getting-started/) 版本。</span><span class="sxs-lookup"><span data-stu-id="fca58-104">Version 0.2 of the Microsoft Edge DevTools Protocol works only on the [Windows 10 October 2018 Update]() and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="fca58-105">**DevTools 协议 0.2** 支持以下 HTTP 终结点。</span><span class="sxs-lookup"><span data-stu-id="fca58-105">**DevTools Protocol 0.2** supports the following HTTP endpoints.</span></span> <span data-ttu-id="fca58-106">有关[连接到浏览器](../index.md#using-the-protocol)内容过程和基于完整 Web 套接字的开发工具协议[](domains/index.md)API 的域文档，请参阅使用该协议。</span><span class="sxs-lookup"><span data-stu-id="fca58-106">See [using the protocol](../index.md#using-the-protocol) for more on connecting to a browser content process and the [Domains](domains/index.md) documentation for the full web sockets-based devtools protocol API.</span></span>

## <span data-ttu-id="fca58-107">/json/version</span><span class="sxs-lookup"><span data-stu-id="fca58-107">/json/version</span></span>
<span data-ttu-id="fca58-108">提供有关主机浏览器及其支持的 DevTools 协议版本的信息。</span><span class="sxs-lookup"><span data-stu-id="fca58-108">Provides information on the host machine's browser and which version of the DevTools Protocol it supports.</span></span>

**<span data-ttu-id="fca58-109">参数</span><span class="sxs-lookup"><span data-stu-id="fca58-109">Parameters</span></span>**

*<span data-ttu-id="fca58-110">无</span><span class="sxs-lookup"><span data-stu-id="fca58-110">None</span></span>*

**<span data-ttu-id="fca58-111">Return 对象</span><span class="sxs-lookup"><span data-stu-id="fca58-111">Return object</span></span>**

```json
{
    "Browser":"Edge/18.17763",
    "Protocol-Version":"0.2",
    "User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.140 Safari/537.36 Edge/18.17763"
}
```

## <span data-ttu-id="fca58-112">/json/protocol</span><span class="sxs-lookup"><span data-stu-id="fca58-112">/json/protocol</span></span>

<span data-ttu-id="fca58-113">提供序列化为 JSON 的整个协议 API 图面。</span><span class="sxs-lookup"><span data-stu-id="fca58-113">Provides the entire protocol API surface serialized as JSON.</span></span>

**<span data-ttu-id="fca58-114">参数</span><span class="sxs-lookup"><span data-stu-id="fca58-114">Parameters</span></span>**

*<span data-ttu-id="fca58-115">无</span><span class="sxs-lookup"><span data-stu-id="fca58-115">None</span></span>*

**<span data-ttu-id="fca58-116">Return 对象</span><span class="sxs-lookup"><span data-stu-id="fca58-116">Return object</span></span>**

<span data-ttu-id="fca58-117">JSON 对象，该对象表示协议当前版本的可用 API 图面。</span><span class="sxs-lookup"><span data-stu-id="fca58-117">JSON object which represents the available API surface for current version of the protocol.</span></span>

## <span data-ttu-id="fca58-118">/json/list</span><span class="sxs-lookup"><span data-stu-id="fca58-118">/json/list</span></span>

<span data-ttu-id="fca58-119">提供用于调试的页面目标的候选列表。</span><span class="sxs-lookup"><span data-stu-id="fca58-119">Provides a candidate list of page targets for debugging.</span></span>

**<span data-ttu-id="fca58-120">参数</span><span class="sxs-lookup"><span data-stu-id="fca58-120">Parameters</span></span>**

*<span data-ttu-id="fca58-121">无</span><span class="sxs-lookup"><span data-stu-id="fca58-121">None</span></span>*

**<span data-ttu-id="fca58-122">Return 对象</span><span class="sxs-lookup"><span data-stu-id="fca58-122">Return object</span></span>**

```json
[{
    "id":"000001F5-87EE-4D55-0091-C4C08A1F30C8",
    "title":"Microsoft Edge Developer website - Microsoft Edge Development",
    "type":"Page",
    "url":"https://developer.microsoft.com/microsoft-edge/",
    "webSocketDebuggerUrl":"ws://localhost:9222/target/000001F5-87EE-4D55-0091-C4C08A1F30C8"
}, … ]
```

## <span data-ttu-id="fca58-123">/json/close</span><span class="sxs-lookup"><span data-stu-id="fca58-123">/json/close</span></span>

<span data-ttu-id="fca58-124">关闭目标进程 (例如，在 Microsoft Edge 中关闭页面选项卡。) </span><span class="sxs-lookup"><span data-stu-id="fca58-124">Closes down the target process (e.g., in Microsoft Edge, closes the page tab.)</span></span>

**<span data-ttu-id="fca58-125">参数</span><span class="sxs-lookup"><span data-stu-id="fca58-125">Parameters</span></span>**

<span data-ttu-id="fca58-126">目标 ID</span><span class="sxs-lookup"><span data-stu-id="fca58-126">Target ID</span></span> 

**<span data-ttu-id="fca58-127">Return 对象</span><span class="sxs-lookup"><span data-stu-id="fca58-127">Return object</span></span>**

```
String("Target is closing")
```
