---
description: DevTools 协议版本 0.1 (EdgeHTML) 页面域参考。 与检查的页面相关的操作和事件属于页面域。
title: '页面域 - DevTools 协议版本 0.1 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 55575e54b9125d7ff544c23c81da4b15d3b56fb1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232473"
---
# <span data-ttu-id="54c1d-104">页面域 - DevTools 协议版本 0.1 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="54c1d-104">Page Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="54c1d-105">与检查的页面相关的操作和事件属于页面域。</span><span class="sxs-lookup"><span data-stu-id="54c1d-105">Actions and events related to the inspected page belong to the page domain.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="54c1d-106">方法</span><span class="sxs-lookup"><span data-stu-id="54c1d-106">Methods</span></span>**](#methods) | <span data-ttu-id="54c1d-107">[启用](#enable)， [禁用](#disable)， [导航](#navigate)</span><span class="sxs-lookup"><span data-stu-id="54c1d-107">[enable](#enable), [disable](#disable), [navigate](#navigate)</span></span> |
| [**<span data-ttu-id="54c1d-108">类型</span><span class="sxs-lookup"><span data-stu-id="54c1d-108">Types</span></span>**](#types) | [<span data-ttu-id="54c1d-109">FrameId</span><span class="sxs-lookup"><span data-stu-id="54c1d-109">FrameId</span></span>](#frameid) |
## <span data-ttu-id="54c1d-110">方法</span><span class="sxs-lookup"><span data-stu-id="54c1d-110">Methods</span></span>

### <span data-ttu-id="54c1d-111">“启用”</span><span class="sxs-lookup"><span data-stu-id="54c1d-111">enable</span></span>
<span data-ttu-id="54c1d-112">启用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="54c1d-112">Enables page domain notifications.</span></span>


---

### <span data-ttu-id="54c1d-113">“禁用”</span><span class="sxs-lookup"><span data-stu-id="54c1d-113">disable</span></span>
<span data-ttu-id="54c1d-114">禁用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="54c1d-114">Disables page domain notifications.</span></span>


---

### <span data-ttu-id="54c1d-115">导航</span><span class="sxs-lookup"><span data-stu-id="54c1d-115">navigate</span></span>
<span data-ttu-id="54c1d-116">将当前页面导航到给定 URL。</span><span class="sxs-lookup"><span data-stu-id="54c1d-116">Navigates current page to the given URL.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="54c1d-117">参数</span><span class="sxs-lookup"><span data-stu-id="54c1d-117">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="54c1d-118">url</span><span class="sxs-lookup"><span data-stu-id="54c1d-118">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="54c1d-119">导航到页面的 URL。</span><span class="sxs-lookup"><span data-stu-id="54c1d-119">URL to navigate the page to.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="54c1d-120">返回</span><span class="sxs-lookup"><span data-stu-id="54c1d-120">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="54c1d-121">frameId</span><span class="sxs-lookup"><span data-stu-id="54c1d-121">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span><b><span data-ttu-id="54c1d-122">实验。</span><span class="sxs-lookup"><span data-stu-id="54c1d-122">Experimental.</span></span> </b></span><span data-ttu-id="54c1d-123">将导航的框架 ID。</span><span class="sxs-lookup"><span data-stu-id="54c1d-123">Frame id that will be navigated.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="54c1d-124">类型</span><span class="sxs-lookup"><span data-stu-id="54c1d-124">Types</span></span>

### <a name="frameid"></a> <span data-ttu-id="54c1d-125">FrameId</span><span class="sxs-lookup"><span data-stu-id="54c1d-125">FrameId</span></span> `string`

<span data-ttu-id="54c1d-126">唯一帧标识符。</span><span class="sxs-lookup"><span data-stu-id="54c1d-126">Unique frame identifier.</span></span>


---
