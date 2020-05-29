---
description: Microsoft Edge DevTools 协议版本0.1 支持以下 HTTP 终结点。
title: DevTools 协议版本 0.1 HTTP 终结点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 5b1cf0d347fec5bfe20b2574afcd635ee569c92d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563416"
---
# <span data-ttu-id="6235f-103">DevTools 协议 HTTP 终结点</span><span class="sxs-lookup"><span data-stu-id="6235f-103">DevTools Protocol HTTP Endpoints</span></span>

> [!NOTE]
> <span data-ttu-id="6235f-104">Microsoft Edge DevTools 协议仅适用于[windows 10 2018 年4月更新](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97)及更高版本的[Windows 预览体验计划预览](https://insider.windows.com/en-us/getting-started/)版本。</span><span class="sxs-lookup"><span data-stu-id="6235f-104">The Microsoft Edge DevTools Protocol works only on [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/30/how-to-get-the-windows-10-april-2018-update/#5VXkQMU41CJzZPER.97) and later [Windows Insider Preview](https://insider.windows.com/en-us/getting-started/) builds.</span></span>

<span data-ttu-id="6235f-105">**DevTools 协议 0.1**支持以下 HTTP 终结点。</span><span class="sxs-lookup"><span data-stu-id="6235f-105">**DevTools Protocol 0.1** supports the following HTTP endpoints.</span></span> <span data-ttu-id="6235f-106">有关连接到浏览器内容流程和完整的基于 web 套接字的 devtools 协议 API 的[域](domains/index.md)文档，请参阅[使用该协议](../index.md#using-the-protocol)。</span><span class="sxs-lookup"><span data-stu-id="6235f-106">See [using the protocol](../index.md#using-the-protocol) for more on connecting to a browser content process and the [Domains](domains/index.md) documentation for the full web sockets-based devtools protocol API.</span></span>

## <span data-ttu-id="6235f-107">/json/version</span><span class="sxs-lookup"><span data-stu-id="6235f-107">/json/version</span></span>
<span data-ttu-id="6235f-108">提供有关主机计算机的浏览器以及它支持的 DevTools 协议版本的信息。</span><span class="sxs-lookup"><span data-stu-id="6235f-108">Provides information on the host machine's browser and which version of the DevTools Protocol it supports.</span></span>

**<span data-ttu-id="6235f-109">参数</span><span class="sxs-lookup"><span data-stu-id="6235f-109">Parameters</span></span>**

*<span data-ttu-id="6235f-110">无</span><span class="sxs-lookup"><span data-stu-id="6235f-110">None</span></span>*

**<span data-ttu-id="6235f-111">返回对象</span><span class="sxs-lookup"><span data-stu-id="6235f-111">Return object</span></span>**

```json
{
    "Browser":"Edge/17.17627",
    "Protocol-Version":"0.1",
    "User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.140 Safari/537.36 Edge/17.17627"
}
```

## <span data-ttu-id="6235f-112">/json/protocol</span><span class="sxs-lookup"><span data-stu-id="6235f-112">/json/protocol</span></span>

<span data-ttu-id="6235f-113">提供序列化为 JSON 的整个协议 API 图面。</span><span class="sxs-lookup"><span data-stu-id="6235f-113">Provides the entire protocol API surface serialized as JSON.</span></span>

**<span data-ttu-id="6235f-114">参数</span><span class="sxs-lookup"><span data-stu-id="6235f-114">Parameters</span></span>**

*<span data-ttu-id="6235f-115">无</span><span class="sxs-lookup"><span data-stu-id="6235f-115">None</span></span>*

**<span data-ttu-id="6235f-116">返回对象</span><span class="sxs-lookup"><span data-stu-id="6235f-116">Return object</span></span>**

<span data-ttu-id="6235f-117">JSON 对象，表示当前版本的协议的可用 API 图面。</span><span class="sxs-lookup"><span data-stu-id="6235f-117">JSON object which represents the available API surface for current version of the protocol.</span></span>

## <span data-ttu-id="6235f-118">/json/list</span><span class="sxs-lookup"><span data-stu-id="6235f-118">/json/list</span></span>

<span data-ttu-id="6235f-119">提供用于调试的页面目标的候选列表。</span><span class="sxs-lookup"><span data-stu-id="6235f-119">Provides a candidate list of page targets for debugging.</span></span>

**<span data-ttu-id="6235f-120">参数</span><span class="sxs-lookup"><span data-stu-id="6235f-120">Parameters</span></span>**

*<span data-ttu-id="6235f-121">无</span><span class="sxs-lookup"><span data-stu-id="6235f-121">None</span></span>*

**<span data-ttu-id="6235f-122">返回对象</span><span class="sxs-lookup"><span data-stu-id="6235f-122">Return object</span></span>**

```json
[{
    "id":"000001F5-87EE-4D55-0091-C4C08A1F30C8",
    "title":"Microsoft Edge Developer website - Microsoft Edge Development",
    "type":"Page",
    "url":"https://developer.microsoft.com/microsoft-edge/",
    "webSocketDebuggerUrl":"ws://localhost:9222/target/000001F5-87EE-4D55-0091-C4C08A1F30C8"
}, … ]
```

## <span data-ttu-id="6235f-123">/json/close</span><span class="sxs-lookup"><span data-stu-id="6235f-123">/json/close</span></span>

<span data-ttu-id="6235f-124">关闭目标进程（例如，在 Microsoft Edge 中关闭页面选项卡。）</span><span class="sxs-lookup"><span data-stu-id="6235f-124">Closes down the target process (e.g., in Microsoft Edge, closes the page tab.)</span></span>

**<span data-ttu-id="6235f-125">参数</span><span class="sxs-lookup"><span data-stu-id="6235f-125">Parameters</span></span>**

<span data-ttu-id="6235f-126">目标 ID</span><span class="sxs-lookup"><span data-stu-id="6235f-126">Target ID</span></span> 

**<span data-ttu-id="6235f-127">返回对象</span><span class="sxs-lookup"><span data-stu-id="6235f-127">Return object</span></span>**

```
String("Target is closing")
```
