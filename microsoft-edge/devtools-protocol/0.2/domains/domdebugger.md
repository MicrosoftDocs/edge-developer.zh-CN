---
description: DOMDebugger 域的参考。 DOM 调试允许在特定的 DOM 操作和事件上设置断点。 由于设置了常规断点，JavaScript 执行将在这些操作上停止。
title: DOMDebugger Domain-DevTools 协议版本0。2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 437a88ff93bda36d85a8f5632c1a02aa205d049b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563399"
---
# <span data-ttu-id="f28af-105">DOMDebugger</span><span class="sxs-lookup"><span data-stu-id="f28af-105">DOMDebugger</span></span>
<span data-ttu-id="f28af-106">DOM 调试允许在特定的 DOM 操作和事件上设置断点。</span><span class="sxs-lookup"><span data-stu-id="f28af-106">DOM debugging allows setting breakpoints on particular DOM operations and events.</span></span> <span data-ttu-id="f28af-107">由于设置了常规断点，JavaScript 执行将在这些操作上停止。</span><span class="sxs-lookup"><span data-stu-id="f28af-107">JavaScript execution will stop on these operations as if there was a regular breakpoint set.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="f28af-108">方法</span><span class="sxs-lookup"><span data-stu-id="f28af-108">Methods</span></span>**](#methods) | <span data-ttu-id="f28af-109">[setInstrumentationBreakpoint](#setinstrumentationbreakpoint)、 [removeInstrumentationBreakpoint](#removeinstrumentationbreakpoint)</span><span class="sxs-lookup"><span data-stu-id="f28af-109">[setInstrumentationBreakpoint](#setinstrumentationbreakpoint), [removeInstrumentationBreakpoint](#removeinstrumentationbreakpoint)</span></span> |
## <span data-ttu-id="f28af-110">方法</span><span class="sxs-lookup"><span data-stu-id="f28af-110">Methods</span></span>

### <span data-ttu-id="f28af-111">setInstrumentationBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f28af-111">setInstrumentationBreakpoint</span></span>
<span><b><span data-ttu-id="f28af-112">实验.</span><span class="sxs-lookup"><span data-stu-id="f28af-112">Experimental.</span></span> </b></span><span data-ttu-id="f28af-113">在特定本机事件上设置断点。</span><span class="sxs-lookup"><span data-stu-id="f28af-113">Sets a breakpoint on a particular native event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f28af-114">参数</span><span class="sxs-lookup"><span data-stu-id="f28af-114">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f28af-115">名称</span><span class="sxs-lookup"><span data-stu-id="f28af-115">eventName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f28af-116">要在其上停止的检测名称。</span><span class="sxs-lookup"><span data-stu-id="f28af-116">Instrumentation name to stop on.</span></span> <span data-ttu-id="f28af-117">有效值： "scriptFirstStatement"。</span><span class="sxs-lookup"><span data-stu-id="f28af-117">Valid values: 'scriptFirstStatement'.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="f28af-118">removeInstrumentationBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f28af-118">removeInstrumentationBreakpoint</span></span>
<span><b><span data-ttu-id="f28af-119">实验.</span><span class="sxs-lookup"><span data-stu-id="f28af-119">Experimental.</span></span> </b></span><span data-ttu-id="f28af-120">删除特定本机事件上的断点。</span><span class="sxs-lookup"><span data-stu-id="f28af-120">Removes a breakpoint on a particular native event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="f28af-121">参数</span><span class="sxs-lookup"><span data-stu-id="f28af-121">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="f28af-122">名称</span><span class="sxs-lookup"><span data-stu-id="f28af-122">eventName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="f28af-123">要在其上停止的检测名称。</span><span class="sxs-lookup"><span data-stu-id="f28af-123">Instrumentation name to stop on.</span></span> <span data-ttu-id="f28af-124">有效值： "scriptFirstStatement"。</span><span class="sxs-lookup"><span data-stu-id="f28af-124">Valid values: 'scriptFirstStatement'.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
