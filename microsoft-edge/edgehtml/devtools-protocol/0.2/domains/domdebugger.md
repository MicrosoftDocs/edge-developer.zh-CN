---
description: DOMDebugger 域的引用。 DOM 调试允许设置特定 DOM 操作和事件的断点。 JavaScript 执行将在这些操作上停止，就像有常规断点集一样。
title: DOMDebugger 域 - DevTools 协议版本 0.2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d97a9a8f2d0e49166f5f081e8bb0c0d5d3cdd93f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232084"
---
# <span data-ttu-id="ba91b-105">DOMDebugger</span><span class="sxs-lookup"><span data-stu-id="ba91b-105">DOMDebugger</span></span>

<span data-ttu-id="ba91b-106">DOM 调试允许设置特定 DOM 操作和事件的断点。</span><span class="sxs-lookup"><span data-stu-id="ba91b-106">DOM debugging allows setting breakpoints on particular DOM operations and events.</span></span> <span data-ttu-id="ba91b-107">JavaScript 执行将在这些操作上停止，就像有常规断点集一样。</span><span class="sxs-lookup"><span data-stu-id="ba91b-107">JavaScript execution will stop on these operations as if there was a regular breakpoint set.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="ba91b-108">方法</span><span class="sxs-lookup"><span data-stu-id="ba91b-108">Methods</span></span>**](#methods) | <span data-ttu-id="ba91b-109">[setInstrumentationBreakpoint](#setinstrumentationbreakpoint)， [removeInstrumentationBreakpoint](#removeinstrumentationbreakpoint)</span><span class="sxs-lookup"><span data-stu-id="ba91b-109">[setInstrumentationBreakpoint](#setinstrumentationbreakpoint), [removeInstrumentationBreakpoint](#removeinstrumentationbreakpoint)</span></span> |
## <span data-ttu-id="ba91b-110">方法</span><span class="sxs-lookup"><span data-stu-id="ba91b-110">Methods</span></span>

### <span data-ttu-id="ba91b-111">setInstrumentationBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ba91b-111">setInstrumentationBreakpoint</span></span>
<span><b><span data-ttu-id="ba91b-112">实验。</span><span class="sxs-lookup"><span data-stu-id="ba91b-112">Experimental.</span></span> </b></span><span data-ttu-id="ba91b-113">设置特定本机事件的断点。</span><span class="sxs-lookup"><span data-stu-id="ba91b-113">Sets a breakpoint on a particular native event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ba91b-114">参数</span><span class="sxs-lookup"><span data-stu-id="ba91b-114">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ba91b-115">eventName</span><span class="sxs-lookup"><span data-stu-id="ba91b-115">eventName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ba91b-116">要停止的检测名称。</span><span class="sxs-lookup"><span data-stu-id="ba91b-116">Instrumentation name to stop on.</span></span> <span data-ttu-id="ba91b-117">有效值："scriptFirstStatement"。</span><span class="sxs-lookup"><span data-stu-id="ba91b-117">Valid values: 'scriptFirstStatement'.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="ba91b-118">removeInstrumentationBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ba91b-118">removeInstrumentationBreakpoint</span></span>
<span><b><span data-ttu-id="ba91b-119">实验。</span><span class="sxs-lookup"><span data-stu-id="ba91b-119">Experimental.</span></span> </b></span><span data-ttu-id="ba91b-120">删除特定本机事件的断点。</span><span class="sxs-lookup"><span data-stu-id="ba91b-120">Removes a breakpoint on a particular native event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ba91b-121">参数</span><span class="sxs-lookup"><span data-stu-id="ba91b-121">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ba91b-122">eventName</span><span class="sxs-lookup"><span data-stu-id="ba91b-122">eventName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ba91b-123">要停止的检测名称。</span><span class="sxs-lookup"><span data-stu-id="ba91b-123">Instrumentation name to stop on.</span></span> <span data-ttu-id="ba91b-124">有效值："scriptFirstStatement"。</span><span class="sxs-lookup"><span data-stu-id="ba91b-124">Valid values: 'scriptFirstStatement'.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
