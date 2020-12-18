---
description: Microsoft Edge DevTools 协议版本 0.2 中受支持域的引用列表。
title: 'DevTools 协议域 - DevTools 协议版本 0.2 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 03688ff2a1757205cc1c83d23a13d205e38011c7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232460"
---
# <span data-ttu-id="11fc5-103">DevTools 协议域 - DevTools 协议版本 0.2 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="11fc5-103">DevTools Protocol Domains - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

## [<span data-ttu-id="11fc5-104">CSS</span><span class="sxs-lookup"><span data-stu-id="11fc5-104">CSS</span></span>](css.md)  

<span data-ttu-id="11fc5-105">此域公开 CSS 读/写操作。</span><span class="sxs-lookup"><span data-stu-id="11fc5-105">This domain exposes CSS read/write operations.</span></span> <span data-ttu-id="11fc5-106">样式表 (规则的所有 CSS 对象) 在相关对象的后续操作中使用的 `id` 关联。</span><span class="sxs-lookup"><span data-stu-id="11fc5-106">All CSS objects (stylesheets, rules, and styles) have an associated `id` used in subsequent operations on the related object.</span></span> <span data-ttu-id="11fc5-107">每个对象类型都有一个特定的结构，并且这些结构在不同类型的对象之间 `id` 不可互换。</span><span class="sxs-lookup"><span data-stu-id="11fc5-107">Each object type has a specific `id` structure, and those are not interchangeable between objects of different kinds.</span></span> <span data-ttu-id="11fc5-108">CSS 对象可以使用接受 DOM 节点 id `get*ForNode()` 的 (加载) 。</span><span class="sxs-lookup"><span data-stu-id="11fc5-108">CSS objects can be loaded using the `get*ForNode()` calls (which accept a DOM node id).</span></span> <span data-ttu-id="11fc5-109">客户端还可以通过事件跟踪样式表，然后使用这些方法加载所需的 `styleSheetAdded` / `styleSheetRemoved` 样式表 `getStyleSheet[Text]()` 内容。</span><span class="sxs-lookup"><span data-stu-id="11fc5-109">A client can also keep track of stylesheets via the `styleSheetAdded`/`styleSheetRemoved` events and subsequently load the required stylesheet contents using the `getStyleSheet[Text]()` methods.</span></span>
## [<span data-ttu-id="11fc5-110">DOM</span><span class="sxs-lookup"><span data-stu-id="11fc5-110">DOM</span></span>](dom.md)
<span data-ttu-id="11fc5-111">此域公开 DOM 读/写操作。</span><span class="sxs-lookup"><span data-stu-id="11fc5-111">This domain exposes DOM read/write operations.</span></span> <span data-ttu-id="11fc5-112">每个 DOM 节点都用其镜像对象表示，该对象具有一个 `id` 。</span><span class="sxs-lookup"><span data-stu-id="11fc5-112">Each DOM Node is represented with its mirror object that has an `id`.</span></span> <span data-ttu-id="11fc5-113">这可用于获取有关节点的其他信息、将节点解析 `id` 为 JavaScript 对象包装器等。客户端仅接收客户端已知的节点的 DOM 事件很重要。</span><span class="sxs-lookup"><span data-stu-id="11fc5-113">This `id` can be used to get additional information on the Node, resolve it into the JavaScript object wrapper, etc. It is important that client receives DOM events only for the nodes that are known to the client.</span></span> <span data-ttu-id="11fc5-114">后端跟踪发送到客户端的节点，从不发送同一节点两次。</span><span class="sxs-lookup"><span data-stu-id="11fc5-114">Backend keeps track of the nodes that were sent to the client and never sends the same node twice.</span></span> <span data-ttu-id="11fc5-115">客户端负责收集有关发送到客户端的节点的信息。</span><span class="sxs-lookup"><span data-stu-id="11fc5-115">It is client's responsibility to collect information about the nodes that were sent to the client.</span></span><p><span data-ttu-id="11fc5-116">请注意， `iframe` 所有者元素将返回相应的文档元素作为其子节点。</span><span class="sxs-lookup"><span data-stu-id="11fc5-116">Note that `iframe` owner elements will return corresponding document elements as their child nodes.</span></span></p>
## [<span data-ttu-id="11fc5-117">DOMDebugger</span><span class="sxs-lookup"><span data-stu-id="11fc5-117">DOMDebugger</span></span>](domdebugger.md)
<span data-ttu-id="11fc5-118">DOM 调试允许设置特定 DOM 操作和事件的断点。</span><span class="sxs-lookup"><span data-stu-id="11fc5-118">DOM debugging allows setting breakpoints on particular DOM operations and events.</span></span> <span data-ttu-id="11fc5-119">JavaScript 执行将在这些操作上停止，就像有常规断点集一样。</span><span class="sxs-lookup"><span data-stu-id="11fc5-119">JavaScript execution will stop on these operations as if there was a regular breakpoint set.</span></span>
## [<span data-ttu-id="11fc5-120">调试程序</span><span class="sxs-lookup"><span data-stu-id="11fc5-120">Debugger</span></span>](debugger.md)
<span data-ttu-id="11fc5-121">调试器域公开 JavaScript 调试功能。</span><span class="sxs-lookup"><span data-stu-id="11fc5-121">Debugger domain exposes JavaScript debugging capabilities.</span></span> <span data-ttu-id="11fc5-122">它允许设置和删除断点、逐步执行、探索堆栈跟踪等。</span><span class="sxs-lookup"><span data-stu-id="11fc5-122">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>
## [<span data-ttu-id="11fc5-123">覆盖</span><span class="sxs-lookup"><span data-stu-id="11fc5-123">Overlay</span></span>](overlay.md)
<span data-ttu-id="11fc5-124">覆盖域公开视觉修饰和节点选择交互</span><span class="sxs-lookup"><span data-stu-id="11fc5-124">Overlay domain exposes visual adornments and node selection interaction</span></span>
## [<span data-ttu-id="11fc5-125">页面</span><span class="sxs-lookup"><span data-stu-id="11fc5-125">Page</span></span>](page.md)
<span data-ttu-id="11fc5-126">与检查的页面相关的操作和事件属于页面域。</span><span class="sxs-lookup"><span data-stu-id="11fc5-126">Actions and events related to the inspected page belong to the page domain.</span></span>
## [<span data-ttu-id="11fc5-127">运行时</span><span class="sxs-lookup"><span data-stu-id="11fc5-127">Runtime</span></span>](runtime.md)
<span data-ttu-id="11fc5-128">运行时域通过远程评估和镜像对象公开 JavaScript 运行时。</span><span class="sxs-lookup"><span data-stu-id="11fc5-128">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="11fc5-129">评估结果作为镜像对象返回，该对象公开对象类型、字符串表示形式和唯一标识符，可用于进一步的对象引用。</span><span class="sxs-lookup"><span data-stu-id="11fc5-129">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="11fc5-130">原始对象将保留于内存中，除非显式释放它们。</span><span class="sxs-lookup"><span data-stu-id="11fc5-130">Original objects are maintained in memory unless they are either explicitly released.</span></span>
## [<span data-ttu-id="11fc5-131">架构</span><span class="sxs-lookup"><span data-stu-id="11fc5-131">Schema</span></span>](schema.md)
<span data-ttu-id="11fc5-132">提供有关协议架构的信息。</span><span class="sxs-lookup"><span data-stu-id="11fc5-132">Provides information about the protocol schema.</span></span>
