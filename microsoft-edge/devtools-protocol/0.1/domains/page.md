---
description: 对页面域的引用。 与已检查页面相关的操作和事件属于页面域。
title: Page 域-DevTools 协议版本0.1 （EdgeHTML）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 1602673eae1c04f60046a898dbadeab1b59f9ce5
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882938"
---
# <span data-ttu-id="d943c-104">Page 域-DevTools 协议版本0.1 （EdgeHTML）</span><span class="sxs-lookup"><span data-stu-id="d943c-104">Page Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="d943c-105">与已检查页面相关的操作和事件属于页面域。</span><span class="sxs-lookup"><span data-stu-id="d943c-105">Actions and events related to the inspected page belong to the page domain.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="d943c-106">方法</span><span class="sxs-lookup"><span data-stu-id="d943c-106">Methods</span></span>**](#methods) | <span data-ttu-id="d943c-107">[启用](#enable)、[禁用](#disable)、[导航](#navigate)</span><span class="sxs-lookup"><span data-stu-id="d943c-107">[enable](#enable), [disable](#disable), [navigate](#navigate)</span></span> |
| [**<span data-ttu-id="d943c-108">类型</span><span class="sxs-lookup"><span data-stu-id="d943c-108">Types</span></span>**](#types) | [<span data-ttu-id="d943c-109">FrameId</span><span class="sxs-lookup"><span data-stu-id="d943c-109">FrameId</span></span>](#frameid) |
## <span data-ttu-id="d943c-110">方法</span><span class="sxs-lookup"><span data-stu-id="d943c-110">Methods</span></span>

### <span data-ttu-id="d943c-111">“启用”</span><span class="sxs-lookup"><span data-stu-id="d943c-111">enable</span></span>
<span data-ttu-id="d943c-112">启用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="d943c-112">Enables page domain notifications.</span></span>


---

### <span data-ttu-id="d943c-113">“禁用”</span><span class="sxs-lookup"><span data-stu-id="d943c-113">disable</span></span>
<span data-ttu-id="d943c-114">禁用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="d943c-114">Disables page domain notifications.</span></span>


---

### <span data-ttu-id="d943c-115">导航</span><span class="sxs-lookup"><span data-stu-id="d943c-115">navigate</span></span>
<span data-ttu-id="d943c-116">将当前页导航到给定的 URL。</span><span class="sxs-lookup"><span data-stu-id="d943c-116">Navigates current page to the given URL.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d943c-117">参数</span><span class="sxs-lookup"><span data-stu-id="d943c-117">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d943c-118">url</span><span class="sxs-lookup"><span data-stu-id="d943c-118">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="d943c-119">要将页面导航到的 URL。</span><span class="sxs-lookup"><span data-stu-id="d943c-119">URL to navigate the page to.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="d943c-120">返回</span><span class="sxs-lookup"><span data-stu-id="d943c-120">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="d943c-121">frameId</span><span class="sxs-lookup"><span data-stu-id="d943c-121">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span><b><span data-ttu-id="d943c-122">实验.</span><span class="sxs-lookup"><span data-stu-id="d943c-122">Experimental.</span></span> </b></span><span data-ttu-id="d943c-123">将导航的帧 id。</span><span class="sxs-lookup"><span data-stu-id="d943c-123">Frame id that will be navigated.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="d943c-124">类型</span><span class="sxs-lookup"><span data-stu-id="d943c-124">Types</span></span>

### <a name="frameid"></a> <span data-ttu-id="d943c-125">FrameId</span><span class="sxs-lookup"><span data-stu-id="d943c-125">FrameId</span></span> `string`

<span data-ttu-id="d943c-126">唯一的帧标识符。</span><span class="sxs-lookup"><span data-stu-id="d943c-126">Unique frame identifier.</span></span>


---
