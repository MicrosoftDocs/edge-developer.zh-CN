---
description: Use DOM breakpoints to visually debug layout glitches on your page
title: DevTools - Elements - DOM breakpoints
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, elements, dom breakpoints, dom mutation
ms.custom: seodec18
ms.openlocfilehash: 4e9eab4727cf1c3ef74b69495dd972838985e589
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564280"
---
# <span data-ttu-id="c793e-104">DOM breakpoints</span><span class="sxs-lookup"><span data-stu-id="c793e-104">DOM breakpoints</span></span>

<span data-ttu-id="c793e-105">Manage your DOM mutation breakpoints from this pane, including disabling, deleting and rebinding them.</span><span class="sxs-lookup"><span data-stu-id="c793e-105">Manage your DOM mutation breakpoints from this pane, including disabling, deleting and rebinding them.</span></span>

<span data-ttu-id="c793e-106">You can use DOM mutation breakpoints to break into the debugger whenever a selected element node changes.</span><span class="sxs-lookup"><span data-stu-id="c793e-106">You can use DOM mutation breakpoints to break into the debugger whenever a selected element node changes.</span></span> <span data-ttu-id="c793e-107">This is helpful for tracking down the code responsible for causing visual glitches with your UI without having to set individual breakpoints on each of the 450+ DOM APIs in *EdgeHTML* that can trigger such changes.</span><span class="sxs-lookup"><span data-stu-id="c793e-107">This is helpful for tracking down the code responsible for causing visual glitches with your UI without having to set individual breakpoints on each of the 450+ DOM APIs in *EdgeHTML* that can trigger such changes.</span></span> 

<span data-ttu-id="c793e-108">To set a DOM breakpoint, right-click on any element in the **Elements** panel *HTML tree view* to open the context menu.</span><span class="sxs-lookup"><span data-stu-id="c793e-108">To set a DOM breakpoint, right-click on any element in the **Elements** panel *HTML tree view* to open the context menu.</span></span>

![DOM Breakpoints context menu](../media/elements_dom_breakpoints_contextmenu.png)

<span data-ttu-id="c793e-110">You can set any of the following breakpoints:</span><span class="sxs-lookup"><span data-stu-id="c793e-110">You can set any of the following breakpoints:</span></span>

 - <span data-ttu-id="c793e-111">**Break on Node removed**: Break into the debugger when the selected element is removed from the document (DOM tree).</span><span class="sxs-lookup"><span data-stu-id="c793e-111">**Break on Node removed**: Break into the debugger when the selected element is removed from the document (DOM tree).</span></span>

 - <span data-ttu-id="c793e-112">**Break on Subtree modified**: Break into the debugger when any of the descendants of the selected element are changed (added, removed, or their subtrees are modified).</span><span class="sxs-lookup"><span data-stu-id="c793e-112">**Break on Subtree modified**: Break into the debugger when any of the descendants of the selected element are changed (added, removed, or their subtrees are modified).</span></span> <span data-ttu-id="c793e-113">This will not break when attributes are modified (see the next option for that).</span><span class="sxs-lookup"><span data-stu-id="c793e-113">This will not break when attributes are modified (see the next option for that).</span></span>

 - <span data-ttu-id="c793e-114">**Break on Attribute modified**: Break into the debugger when an attribute of the selected element is added, removed or changed in value.</span><span class="sxs-lookup"><span data-stu-id="c793e-114">**Break on Attribute modified**: Break into the debugger when an attribute of the selected element is added, removed or changed in value.</span></span>

<span data-ttu-id="c793e-115">The **DOM breakpoints** pane will then list the selected element (by generating a selector describing its location in the DOM) and the types of breakpoints you have set (*Node removed, Subtree modified, Attribute modified*).</span><span class="sxs-lookup"><span data-stu-id="c793e-115">The **DOM breakpoints** pane will then list the selected element (by generating a selector describing its location in the DOM) and the types of breakpoints you have set (*Node removed, Subtree modified, Attribute modified*).</span></span> <span data-ttu-id="c793e-116">From here, you can also *rebind*, *disable*, or *delete* your breakpoints, individually (from the rt-click context menu) or all at once (using the buttons).</span><span class="sxs-lookup"><span data-stu-id="c793e-116">From here, you can also *rebind*, *disable*, or *delete* your breakpoints, individually (from the rt-click context menu) or all at once (using the buttons).</span></span>

![DOM breakpoints pane](../media/elements_dom_breakpoints.png)

## <span data-ttu-id="c793e-118">Breakpoint persistence</span><span class="sxs-lookup"><span data-stu-id="c793e-118">Breakpoint persistence</span></span>

<span data-ttu-id="c793e-119">Breakpoints are stored (and scoped to the URL of the page they're set within) as part of your DevTools settings.</span><span class="sxs-lookup"><span data-stu-id="c793e-119">Breakpoints are stored (and scoped to the URL of the page they're set within) as part of your DevTools settings.</span></span> <span data-ttu-id="c793e-120">When the page is reloaded or the tools are closed and reopened, DevTools will attempt to rebind your breakpoints to their associated elements.</span><span class="sxs-lookup"><span data-stu-id="c793e-120">When the page is reloaded or the tools are closed and reopened, DevTools will attempt to rebind your breakpoints to their associated elements.</span></span>

<span data-ttu-id="c793e-121">Breakpoints that couldn't be automatically rebinded are indicated with a warning icon on the breakpoint circle.</span><span class="sxs-lookup"><span data-stu-id="c793e-121">Breakpoints that couldn't be automatically rebinded are indicated with a warning icon on the breakpoint circle.</span></span> <span data-ttu-id="c793e-122">For these, you can wait to rebind the element manually (using the **Rebind breakpoint** button and/or context menu option) once a corresponding element appears in the DOM (and the breakpoint icon no longer shows the warning indicator), or **Delete** the breakpoint altogether.</span><span class="sxs-lookup"><span data-stu-id="c793e-122">For these, you can wait to rebind the element manually (using the **Rebind breakpoint** button and/or context menu option) once a corresponding element appears in the DOM (and the breakpoint icon no longer shows the warning indicator), or **Delete** the breakpoint altogether.</span></span>

![Unbound breakpoint indicator](../media/elements_dom_breakpoint_unbound.png)

<span data-ttu-id="c793e-124">In addition to this *DOM breakpoints* pane, you can also manage your [DOM breakpoints](../debugger.md#dom-breakpoints) from within the **Debugger**.</span><span class="sxs-lookup"><span data-stu-id="c793e-124">In addition to this *DOM breakpoints* pane, you can also manage your [DOM breakpoints](../debugger.md#dom-breakpoints) from within the **Debugger**.</span></span>

## <span data-ttu-id="c793e-125">Current limitations</span><span class="sxs-lookup"><span data-stu-id="c793e-125">Current limitations</span></span>

<span data-ttu-id="c793e-126">Please be aware of the following limitations of DOM breakpoint debugging in Edge DevTools:</span><span class="sxs-lookup"><span data-stu-id="c793e-126">Please be aware of the following limitations of DOM breakpoint debugging in Edge DevTools:</span></span>

- <span data-ttu-id="c793e-127">Edge DevTools don't currently support rebinding breakpoints inside of [`<iframe>`s](https://developer.mozilla.org/docs/Web/HTML/Element/iframe).</span><span class="sxs-lookup"><span data-stu-id="c793e-127">Edge DevTools don't currently support rebinding breakpoints inside of [`<iframe>`s](https://developer.mozilla.org/docs/Web/HTML/Element/iframe).</span></span> <span data-ttu-id="c793e-128">If you set a breakpoint in an iframe and close Edge DevTools or refresh the page, the breakpoint will be lost.</span><span class="sxs-lookup"><span data-stu-id="c793e-128">If you set a breakpoint in an iframe and close Edge DevTools or refresh the page, the breakpoint will be lost.</span></span>

- <span data-ttu-id="c793e-129">If your script encounters a synchronously-executed breakpoint before the DOM [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) is completed, you won't be able to set a DOM breakpoint while the debugger is paused.</span><span class="sxs-lookup"><span data-stu-id="c793e-129">If your script encounters a synchronously-executed breakpoint before the DOM [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) is completed, you won't be able to set a DOM breakpoint while the debugger is paused.</span></span> <span data-ttu-id="c793e-130">You can typically remedy this situation by setting the [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) or [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) script attributes.</span><span class="sxs-lookup"><span data-stu-id="c793e-130">You can typically remedy this situation by setting the [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) or [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) script attributes.</span></span>

- <span data-ttu-id="c793e-131">For synchronous scripts, we trigger automatic rebinding of breakpoints when the [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) event is called.</span><span class="sxs-lookup"><span data-stu-id="c793e-131">For synchronous scripts, we trigger automatic rebinding of breakpoints when the [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) event is called.</span></span> <span data-ttu-id="c793e-132">In this case, we may miss binding breakpoints that would trigger during initial script-driven build-up of the DOM.</span><span class="sxs-lookup"><span data-stu-id="c793e-132">In this case, we may miss binding breakpoints that would trigger during initial script-driven build-up of the DOM.</span></span> <span data-ttu-id="c793e-133">For asynchronous scripts, we trigger a rebind attempt before the first script executes, so your breakpoints may rebind and trigger as desired.</span><span class="sxs-lookup"><span data-stu-id="c793e-133">For asynchronous scripts, we trigger a rebind attempt before the first script executes, so your breakpoints may rebind and trigger as desired.</span></span>
