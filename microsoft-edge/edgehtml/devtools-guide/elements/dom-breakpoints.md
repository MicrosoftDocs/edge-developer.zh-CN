---
description: 使用 DOM 断点直观调试页面上的布局故障
title: DevTools - 元素 - DOM 断点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 元素， dom 断点， dom 检测
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cb60fa0497c98c152ca2c5adf28e9dee5d7c9f98
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232298"
---
# <span data-ttu-id="648e1-104">DOM 断点</span><span class="sxs-lookup"><span data-stu-id="648e1-104">DOM breakpoints</span></span>

<span data-ttu-id="648e1-105">管理此窗格中的 DOM 分解断点，包括禁用、删除和重新绑定它们。</span><span class="sxs-lookup"><span data-stu-id="648e1-105">Manage your DOM mutation breakpoints from this pane, including disabling, deleting and rebinding them.</span></span>

<span data-ttu-id="648e1-106">只要选定元素节点发生更改，就可以使用 DOM 破坏断点来中断调试程序。</span><span class="sxs-lookup"><span data-stu-id="648e1-106">You can use DOM mutation breakpoints to break into the debugger whenever a selected element node changes.</span></span> <span data-ttu-id="648e1-107">这有助于跟踪导致 UI 出现视觉故障的代码，而无需在 *EdgeHTML* 中可触发此类更改的 450 多个 DOM API 上设置单独的断点。</span><span class="sxs-lookup"><span data-stu-id="648e1-107">This is helpful for tracking down the code responsible for causing visual glitches with your UI without having to set individual breakpoints on each of the 450+ DOM APIs in *EdgeHTML* that can trigger such changes.</span></span> 

<span data-ttu-id="648e1-108">若要设置 DOM 断点，请右键单击"元素" 面板*HTML 树视图中*的任何元素以打开上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="648e1-108">To set a DOM breakpoint, right-click on any element in the **Elements** panel *HTML tree view* to open the context menu.</span></span>

![DOM 断点上下文菜单](../media/elements_dom_breakpoints_contextmenu.png)

<span data-ttu-id="648e1-110">可以设置以下任何断点：</span><span class="sxs-lookup"><span data-stu-id="648e1-110">You can set any of the following breakpoints:</span></span>

 - <span data-ttu-id="648e1-111">**在已删除的节点上**中断：从 DOM 树文档中删除所选元素时， (调试) 。</span><span class="sxs-lookup"><span data-stu-id="648e1-111">**Break on Node removed**: Break into the debugger when the selected element is removed from the document (DOM tree).</span></span>

 - <span data-ttu-id="648e1-112">**修改了子**树上的中断：当所选元素的任何后代发生更改时， (、删除或修改其子树时中断) 。</span><span class="sxs-lookup"><span data-stu-id="648e1-112">**Break on Subtree modified**: Break into the debugger when any of the descendants of the selected element are changed (added, removed, or their subtrees are modified).</span></span> <span data-ttu-id="648e1-113">当属性被修改时，这不会中断 (查看下一个选项) 。</span><span class="sxs-lookup"><span data-stu-id="648e1-113">This will not break when attributes are modified (see the next option for that).</span></span>

 - <span data-ttu-id="648e1-114">**修改属性时中断**：在值中添加、删除或更改选定元素的属性时，中断调试程序。</span><span class="sxs-lookup"><span data-stu-id="648e1-114">**Break on Attribute modified**: Break into the debugger when an attribute of the selected element is added, removed or changed in value.</span></span>

<span data-ttu-id="648e1-115">**然后，DOM**断点窗格将列出所选元素 (，具体操作是生成一个选择器，该选择器描述其在 DOM) 中的位置，以及已设置删除 (*节点*、修改了子树、修改了属性的断点) 。</span><span class="sxs-lookup"><span data-stu-id="648e1-115">The **DOM breakpoints** pane will then list the selected element (by generating a selector describing its location in the DOM) and the types of breakpoints you have set (*Node removed, Subtree modified, Attribute modified*).</span></span> <span data-ttu-id="648e1-116">在此处，您还可以使用 (按钮 从 rt-click 上下文 菜单) 或一次重新绑定、禁用或删除断点 (断点) 。 </span><span class="sxs-lookup"><span data-stu-id="648e1-116">From here, you can also *rebind*, *disable*, or *delete* your breakpoints, individually (from the rt-click context menu) or all at once (using the buttons).</span></span>

![DOM 断点窗格](../media/elements_dom_breakpoints.png)

## <span data-ttu-id="648e1-118">断点持久性</span><span class="sxs-lookup"><span data-stu-id="648e1-118">Breakpoint persistence</span></span>

<span data-ttu-id="648e1-119">断点存储在 (范围设置为在开发人员工具设置) 中设置的页面的 URL。</span><span class="sxs-lookup"><span data-stu-id="648e1-119">Breakpoints are stored (and scoped to the URL of the page they're set within) as part of your DevTools settings.</span></span> <span data-ttu-id="648e1-120">重新加载页面或关闭并重新打开工具时，DevTools 将尝试将断点重新绑定到其关联元素。</span><span class="sxs-lookup"><span data-stu-id="648e1-120">When the page is reloaded or the tools are closed and reopened, DevTools will attempt to rebind your breakpoints to their associated elements.</span></span>

<span data-ttu-id="648e1-121">无法自动重新绑定的断点在断点圆圈上用警告图标指示。</span><span class="sxs-lookup"><span data-stu-id="648e1-121">Breakpoints that couldn't be automatically rebinded are indicated with a warning icon on the breakpoint circle.</span></span> <span data-ttu-id="648e1-122">对于这些元素，你可以等待在 DOM ( (中出现相应元素后，使用重新绑定断点按钮和/或上下文菜单选项) 手动重新绑定元素) ，或者完全删除断点。 </span><span class="sxs-lookup"><span data-stu-id="648e1-122">For these, you can wait to rebind the element manually (using the **Rebind breakpoint** button and/or context menu option) once a corresponding element appears in the DOM (and the breakpoint icon no longer shows the warning indicator), or **Delete** the breakpoint altogether.</span></span>

![未绑定断点指示器](../media/elements_dom_breakpoint_unbound.png)

<span data-ttu-id="648e1-124">除了此 *DOM 断* 点窗格，您还可以从调试器中管理 [DOM](../debugger.md#dom-breakpoints) **断点**。</span><span class="sxs-lookup"><span data-stu-id="648e1-124">In addition to this *DOM breakpoints* pane, you can also manage your [DOM breakpoints](../debugger.md#dom-breakpoints) from within the **Debugger**.</span></span>

## <span data-ttu-id="648e1-125">当前限制</span><span class="sxs-lookup"><span data-stu-id="648e1-125">Current limitations</span></span>

<span data-ttu-id="648e1-126">请注意边缘开发人员工具中 DOM 断点调试的以下限制：</span><span class="sxs-lookup"><span data-stu-id="648e1-126">Please be aware of the following limitations of DOM breakpoint debugging in Edge DevTools:</span></span>

- <span data-ttu-id="648e1-127">Edge DevTools 当前不支持重新绑定内部[ `<iframe>` 断点](https://developer.mozilla.org/docs/Web/HTML/Element/iframe)。</span><span class="sxs-lookup"><span data-stu-id="648e1-127">Edge DevTools don't currently support rebinding breakpoints inside of [`<iframe>`s](https://developer.mozilla.org/docs/Web/HTML/Element/iframe).</span></span> <span data-ttu-id="648e1-128">如果在 iframe 中设置断点并关闭 Edge DevTools 或刷新页面，断点将丢失。</span><span class="sxs-lookup"><span data-stu-id="648e1-128">If you set a breakpoint in an iframe and close Edge DevTools or refresh the page, the breakpoint will be lost.</span></span>

- <span data-ttu-id="648e1-129">如果脚本在 DOM 完成之前遇到同步执行的断点，将无法在调试程序暂停时设置 [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) DOM 断点。</span><span class="sxs-lookup"><span data-stu-id="648e1-129">If your script encounters a synchronously-executed breakpoint before the DOM [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) is completed, you won't be able to set a DOM breakpoint while the debugger is paused.</span></span> <span data-ttu-id="648e1-130">通常可以通过设置或脚本属性 [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) 来 [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) 补救这种情况。</span><span class="sxs-lookup"><span data-stu-id="648e1-130">You can typically remedy this situation by setting the [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) or [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) script attributes.</span></span>

- <span data-ttu-id="648e1-131">对于同步脚本，在调用事件时触发断点的 [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) 自动重新绑定。</span><span class="sxs-lookup"><span data-stu-id="648e1-131">For synchronous scripts, we trigger automatic rebinding of breakpoints when the [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) event is called.</span></span> <span data-ttu-id="648e1-132">在这种情况下，我们可能会错过绑定断点，这些断点将在 DOM 的初始脚本驱动构建过程中触发。</span><span class="sxs-lookup"><span data-stu-id="648e1-132">In this case, we may miss binding breakpoints that would trigger during initial script-driven build-up of the DOM.</span></span> <span data-ttu-id="648e1-133">对于异步脚本，我们在执行第一个脚本之前触发重新绑定尝试，以便断点可以按需要重新绑定和触发。</span><span class="sxs-lookup"><span data-stu-id="648e1-133">For asynchronous scripts, we trigger a rebind attempt before the first script executes, so your breakpoints may rebind and trigger as desired.</span></span>
