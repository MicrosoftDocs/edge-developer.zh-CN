---
description: 覆盖域的引用。 覆盖域公开视觉修饰和节点选择交互
title: 覆盖域 - DevTools 协议版本 0.2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: dcf5feff9983aa2e9e61ac0569938988812165f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232082"
---
# <span data-ttu-id="45831-104">覆盖</span><span class="sxs-lookup"><span data-stu-id="45831-104">Overlay</span></span>

<span data-ttu-id="45831-105">覆盖域公开视觉修饰和节点选择交互</span><span class="sxs-lookup"><span data-stu-id="45831-105">Overlay domain exposes visual adornments and node selection interaction</span></span>

| | |
|-|-|
| [**<span data-ttu-id="45831-106">方法</span><span class="sxs-lookup"><span data-stu-id="45831-106">Methods</span></span>**](#methods) | <span data-ttu-id="45831-107">[enable](#enable)， [disable](#disable)， [setInspectMode](#setinspectmode)</span><span class="sxs-lookup"><span data-stu-id="45831-107">[enable](#enable), [disable](#disable), [setInspectMode](#setinspectmode)</span></span> |
| [**<span data-ttu-id="45831-108">事件</span><span class="sxs-lookup"><span data-stu-id="45831-108">Events</span></span>**](#events) | <span data-ttu-id="45831-109">[inspectNodeRequested](#inspectnoderequested)， [nodeHighlightRequested](#nodehighlightrequested)</span><span class="sxs-lookup"><span data-stu-id="45831-109">[inspectNodeRequested](#inspectnoderequested), [nodeHighlightRequested](#nodehighlightrequested)</span></span> |
| [**<span data-ttu-id="45831-110">依赖关系</span><span class="sxs-lookup"><span data-stu-id="45831-110">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="45831-111">DOM</span><span class="sxs-lookup"><span data-stu-id="45831-111">DOM</span></span>](dom.md) |
## <span data-ttu-id="45831-112">方法</span><span class="sxs-lookup"><span data-stu-id="45831-112">Methods</span></span>

### <span data-ttu-id="45831-113">“启用”</span><span class="sxs-lookup"><span data-stu-id="45831-113">enable</span></span>
<span data-ttu-id="45831-114">启用报告和 <code>nodeHighlightRequested</code> <code>inspectElementRequested</code> 事件</span><span class="sxs-lookup"><span data-stu-id="45831-114">Enables reporting of <code>nodeHighlightRequested</code> and <code>inspectElementRequested</code> events</span></span>

</p>

---

### <span data-ttu-id="45831-115">“禁用”</span><span class="sxs-lookup"><span data-stu-id="45831-115">disable</span></span>
<span data-ttu-id="45831-116">禁用覆盖域事件报告</span><span class="sxs-lookup"><span data-stu-id="45831-116">Disables reporting of Overlay domain events</span></span>

</p>

---

### <span data-ttu-id="45831-117">setInspectMode</span><span class="sxs-lookup"><span data-stu-id="45831-117">setInspectMode</span></span>
<span data-ttu-id="45831-118">设置客户端的元素选择模式</span><span class="sxs-lookup"><span data-stu-id="45831-118">Sets the element selection mode for the client</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="45831-119">参数</span><span class="sxs-lookup"><span data-stu-id="45831-119">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="45831-120">mode</span><span class="sxs-lookup"><span data-stu-id="45831-120">mode</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="45831-121">检查模式。</span><span class="sxs-lookup"><span data-stu-id="45831-121">The inspection mode.</span></span>  <span data-ttu-id="45831-122">有效值为"searchForNode"和"none"。</span><span class="sxs-lookup"><span data-stu-id="45831-122">Valid values are 'searchForNode' and 'none'.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="45831-123">highlightConfig</span><span class="sxs-lookup"><span data-stu-id="45831-123">highlightConfig</span></span> <br/> <i><span data-ttu-id="45831-124">可选</span><span class="sxs-lookup"><span data-stu-id="45831-124">optional</span></span></i></td>
            <td><a href="dom.md#highlightconfig"><code class="flyout">DOM.HighlightConfig</code></a></td>
            <td><span data-ttu-id="45831-125">检查时要使用的突出显示配置</span><span class="sxs-lookup"><span data-stu-id="45831-125">The highlight configuration to use while inspecting</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="45831-126">事件</span><span class="sxs-lookup"><span data-stu-id="45831-126">Events</span></span>

### <span data-ttu-id="45831-127">inspectNodeRequested</span><span class="sxs-lookup"><span data-stu-id="45831-127">inspectNodeRequested</span></span>
<span data-ttu-id="45831-128">通知客户端用户已要求检查特定节点</span><span class="sxs-lookup"><span data-stu-id="45831-128">Notifies the client that the user has asked to inspect a particular node</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="45831-129">参数</span><span class="sxs-lookup"><span data-stu-id="45831-129">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="45831-130">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="45831-130">backendNodeId</span></span></td>
            <td><a href="dom.md#backendnodeid"><code class="flyout">DOM.BackendNodeId</code></a></td>
            <td><span data-ttu-id="45831-131">请求的节点的后端节点 ID</span><span class="sxs-lookup"><span data-stu-id="45831-131">The backend node ID of node requested</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="45831-132">nodeHighlightRequested</span><span class="sxs-lookup"><span data-stu-id="45831-132">nodeHighlightRequested</span></span>
<span data-ttu-id="45831-133">指示用户已悬停在节点上，并可能检查节点</span><span class="sxs-lookup"><span data-stu-id="45831-133">Indicates that the user has hovered over the node and may inspect the node</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="45831-134">参数</span><span class="sxs-lookup"><span data-stu-id="45831-134">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="45831-135">nodeId</span><span class="sxs-lookup"><span data-stu-id="45831-135">nodeId</span></span></td>
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td><span data-ttu-id="45831-136">考虑的节点的节点 ID</span><span class="sxs-lookup"><span data-stu-id="45831-136">The node ID of the node being considered</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="45831-137">依赖关系</span><span class="sxs-lookup"><span data-stu-id="45831-137">Dependencies</span></span>

[<span data-ttu-id="45831-138">DOM</span><span class="sxs-lookup"><span data-stu-id="45831-138">DOM</span></span>](dom.md)
