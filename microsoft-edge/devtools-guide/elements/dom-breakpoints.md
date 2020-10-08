---
description: 使用 DOM 断点直观地调试页面上的布局故障
title: DevTools-DOM 断点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、元素、dom 断点、dom 转变
ms.custom: seodec18
ms.openlocfilehash: 4e9eab4727cf1c3ef74b69495dd972838985e589
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564280"
---
# <span data-ttu-id="ffe14-104">DOM 断点</span><span class="sxs-lookup"><span data-stu-id="ffe14-104">DOM breakpoints</span></span>

<span data-ttu-id="ffe14-105">从此窗格管理 DOM 转变断点，包括禁用、删除和重新绑定。</span><span class="sxs-lookup"><span data-stu-id="ffe14-105">Manage your DOM mutation breakpoints from this pane, including disabling, deleting and rebinding them.</span></span>

<span data-ttu-id="ffe14-106">当所选元素节点发生更改时，可以使用 DOM 转变断点中断调试器。</span><span class="sxs-lookup"><span data-stu-id="ffe14-106">You can use DOM mutation breakpoints to break into the debugger whenever a selected element node changes.</span></span> <span data-ttu-id="ffe14-107">这有助于跟踪负责在你的 UI 中导致视觉故障的代码，而无需在 *EdgeHTML* 中的每个 450 + DOM api 上设置单个断点，从而触发此类更改。</span><span class="sxs-lookup"><span data-stu-id="ffe14-107">This is helpful for tracking down the code responsible for causing visual glitches with your UI without having to set individual breakpoints on each of the 450+ DOM APIs in *EdgeHTML* that can trigger such changes.</span></span> 

<span data-ttu-id="ffe14-108">若要设置 DOM 断点，请右键单击 " **元素** " 面板中的任意元素 *HTML 树视图* 以打开上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="ffe14-108">To set a DOM breakpoint, right-click on any element in the **Elements** panel *HTML tree view* to open the context menu.</span></span>

![DOM 断点上下文菜单](../media/elements_dom_breakpoints_contextmenu.png)

<span data-ttu-id="ffe14-110">你可以设置以下任意断点：</span><span class="sxs-lookup"><span data-stu-id="ffe14-110">You can set any of the following breakpoints:</span></span>

 - <span data-ttu-id="ffe14-111">**删除节点上的中断**：在从文档 (DOM 树) 中删除所选元素时，中断到调试器。</span><span class="sxs-lookup"><span data-stu-id="ffe14-111">**Break on Node removed**: Break into the debugger when the selected element is removed from the document (DOM tree).</span></span>

 - <span data-ttu-id="ffe14-112">**已修改的子树中断**：当所选元素的任何子代更改 (添加、删除或其子树被修改) 时，请中断调试程序。</span><span class="sxs-lookup"><span data-stu-id="ffe14-112">**Break on Subtree modified**: Break into the debugger when any of the descendants of the selected element are changed (added, removed, or their subtrees are modified).</span></span> <span data-ttu-id="ffe14-113">修改属性时不会中断 (请参阅该) 的 "下一步" 选项。</span><span class="sxs-lookup"><span data-stu-id="ffe14-113">This will not break when attributes are modified (see the next option for that).</span></span>

 - <span data-ttu-id="ffe14-114">**已修改的属性中断**：在值中添加、删除或更改所选元素的属性时，请中断调试程序。</span><span class="sxs-lookup"><span data-stu-id="ffe14-114">**Break on Attribute modified**: Break into the debugger when an attribute of the selected element is added, removed or changed in value.</span></span>

<span data-ttu-id="ffe14-115">然后，" **dom 断点** " 窗格将通过生成一个选择器来列出所选元素 (，该选择器描述其在 DOM) 中的位置以及已设置的断点类型 (*节点已被删除、子树已修改、属性已* 修改) 。</span><span class="sxs-lookup"><span data-stu-id="ffe14-115">The **DOM breakpoints** pane will then list the selected element (by generating a selector describing its location in the DOM) and the types of breakpoints you have set (*Node removed, Subtree modified, Attribute modified*).</span></span> <span data-ttu-id="ffe14-116">在此处，你还可以重新 *绑定*、 *禁用*或 *删除* 你的断点，从 rt 单击上下文菜单中单独 () 或同时使用 "按钮) " (。</span><span class="sxs-lookup"><span data-stu-id="ffe14-116">From here, you can also *rebind*, *disable*, or *delete* your breakpoints, individually (from the rt-click context menu) or all at once (using the buttons).</span></span>

![DOM 断点窗格](../media/elements_dom_breakpoints.png)

## <span data-ttu-id="ffe14-118">断点持久性</span><span class="sxs-lookup"><span data-stu-id="ffe14-118">Breakpoint persistence</span></span>

<span data-ttu-id="ffe14-119">断点存储 (和范围内，其在) 中设置为 DevTools 设置的一部分的页面的 URL。</span><span class="sxs-lookup"><span data-stu-id="ffe14-119">Breakpoints are stored (and scoped to the URL of the page they're set within) as part of your DevTools settings.</span></span> <span data-ttu-id="ffe14-120">重新加载页面或关闭并重新打开工具后，DevTools 将尝试将断点重新绑定到其关联的元素。</span><span class="sxs-lookup"><span data-stu-id="ffe14-120">When the page is reloaded or the tools are closed and reopened, DevTools will attempt to rebind your breakpoints to their associated elements.</span></span>

<span data-ttu-id="ffe14-121">无法自动 rebinded 的断点以断点圆圈上的警告图标表示。</span><span class="sxs-lookup"><span data-stu-id="ffe14-121">Breakpoints that couldn't be automatically rebinded are indicated with a warning icon on the breakpoint circle.</span></span> <span data-ttu-id="ffe14-122">对于这些内容，你可以等待手动重新绑定该元素 (使用 "重新 **绑定断点** " 按钮和/或上下文菜单选项) 只要相应元素出现在 (DOM 中，断点图标将不再显示警告指示器) ，或者完全 **删除** 断点。</span><span class="sxs-lookup"><span data-stu-id="ffe14-122">For these, you can wait to rebind the element manually (using the **Rebind breakpoint** button and/or context menu option) once a corresponding element appears in the DOM (and the breakpoint icon no longer shows the warning indicator), or **Delete** the breakpoint altogether.</span></span>

![未绑定断点指示器](../media/elements_dom_breakpoint_unbound.png)

<span data-ttu-id="ffe14-124">除了此*DOM 断点*窗格外，你还可以在**调试器**中管理你的[DOM 断点](../debugger.md#dom-breakpoints)。</span><span class="sxs-lookup"><span data-stu-id="ffe14-124">In addition to this *DOM breakpoints* pane, you can also manage your [DOM breakpoints](../debugger.md#dom-breakpoints) from within the **Debugger**.</span></span>

## <span data-ttu-id="ffe14-125">当前限制</span><span class="sxs-lookup"><span data-stu-id="ffe14-125">Current limitations</span></span>

<span data-ttu-id="ffe14-126">请注意在 Edge DevTools 中 DOM 断点调试的以下限制：</span><span class="sxs-lookup"><span data-stu-id="ffe14-126">Please be aware of the following limitations of DOM breakpoint debugging in Edge DevTools:</span></span>

- <span data-ttu-id="ffe14-127">Edge DevTools 目前不支持[ `<iframe>` s](https://developer.mozilla.org/docs/Web/HTML/Element/iframe)中的重新绑定断点。</span><span class="sxs-lookup"><span data-stu-id="ffe14-127">Edge DevTools don't currently support rebinding breakpoints inside of [`<iframe>`s](https://developer.mozilla.org/docs/Web/HTML/Element/iframe).</span></span> <span data-ttu-id="ffe14-128">如果在 iframe 中设置断点并关闭边缘 DevTools 或刷新页面，则断点将丢失。</span><span class="sxs-lookup"><span data-stu-id="ffe14-128">If you set a breakpoint in an iframe and close Edge DevTools or refresh the page, the breakpoint will be lost.</span></span>

- <span data-ttu-id="ffe14-129">如果你的脚本在 DOM 完成之前遇到同步执行的断点 [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) ，则你将无法在调试器暂停时设置 DOM 断点。</span><span class="sxs-lookup"><span data-stu-id="ffe14-129">If your script encounters a synchronously-executed breakpoint before the DOM [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) is completed, you won't be able to set a DOM breakpoint while the debugger is paused.</span></span> <span data-ttu-id="ffe14-130">你通常可以通过设置 [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) 或脚本属性来解决此情况 [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) 。</span><span class="sxs-lookup"><span data-stu-id="ffe14-130">You can typically remedy this situation by setting the [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) or [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) script attributes.</span></span>

- <span data-ttu-id="ffe14-131">对于同步脚本，我们会在调用事件时触发断点的自动重新绑定 [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) 。</span><span class="sxs-lookup"><span data-stu-id="ffe14-131">For synchronous scripts, we trigger automatic rebinding of breakpoints when the [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) event is called.</span></span> <span data-ttu-id="ffe14-132">在这种情况下，我们可能会错过在 DOM 的初始脚本驱动内部版本期间将触发的绑定断点。</span><span class="sxs-lookup"><span data-stu-id="ffe14-132">In this case, we may miss binding breakpoints that would trigger during initial script-driven build-up of the DOM.</span></span> <span data-ttu-id="ffe14-133">对于异步脚本，我们会在执行第一个脚本之前触发重新绑定尝试，因此你的断点可能会根据需要重新绑定和触发。</span><span class="sxs-lookup"><span data-stu-id="ffe14-133">For asynchronous scripts, we trigger a rebind attempt before the first script executes, so your breakpoints may rebind and trigger as desired.</span></span>
