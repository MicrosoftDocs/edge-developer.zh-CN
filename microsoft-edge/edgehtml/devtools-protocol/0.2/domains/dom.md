---
description: DOM 域的引用。 此域公开 DOM 读/写操作。 每个 DOM 节点都用其镜像对象表示，该对象具有一个 `id` 。 这可用于获取有关节点的其他信息、将节点解析 `id` 为 JavaScript 对象包装器等。客户端仅接收客户端已知的节点的 DOM 事件很重要。 后端跟踪发送到客户端的节点，从不发送同一节点两次。 客户端负责收集有关发送到客户端的节点的信息。<p>请注意， `iframe` 所有者元素将返回相应的文档元素作为其子节点。</p>
title: DOM 域 - DevTools 协议版本 0.2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7d9861a2395f7b24142a41efea9ac599907dec27
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232462"
---
# <span data-ttu-id="28216-109">DOM</span><span class="sxs-lookup"><span data-stu-id="28216-109">DOM</span></span>

<span data-ttu-id="28216-110">此域公开 DOM 读/写操作。</span><span class="sxs-lookup"><span data-stu-id="28216-110">This domain exposes DOM read/write operations.</span></span> <span data-ttu-id="28216-111">每个 DOM 节点都用其镜像对象表示，该对象具有一个 `id` 。</span><span class="sxs-lookup"><span data-stu-id="28216-111">Each DOM Node is represented with its mirror object that has an `id`.</span></span> <span data-ttu-id="28216-112">这可用于获取有关节点的其他信息、将节点解析 `id` 为 JavaScript 对象包装器等。客户端仅接收客户端已知的节点的 DOM 事件很重要。</span><span class="sxs-lookup"><span data-stu-id="28216-112">This `id` can be used to get additional information on the Node, resolve it into the JavaScript object wrapper, etc. It is important that client receives DOM events only for the nodes that are known to the client.</span></span> <span data-ttu-id="28216-113">后端跟踪发送到客户端的节点，从不发送同一节点两次。</span><span class="sxs-lookup"><span data-stu-id="28216-113">Backend keeps track of the nodes that were sent to the client and never sends the same node twice.</span></span> <span data-ttu-id="28216-114">客户端负责收集有关发送到客户端的节点的信息。</span><span class="sxs-lookup"><span data-stu-id="28216-114">It is client's responsibility to collect information about the nodes that were sent to the client.</span></span><p><span data-ttu-id="28216-115">请注意， `iframe` 所有者元素将返回相应的文档元素作为其子节点。</span><span class="sxs-lookup"><span data-stu-id="28216-115">Note that `iframe` owner elements will return corresponding document elements as their child nodes.</span></span></p>

| | |
|-|-|
| [**<span data-ttu-id="28216-116">方法</span><span class="sxs-lookup"><span data-stu-id="28216-116">Methods</span></span>**](#methods) | <span data-ttu-id="28216-117">[enable](#enable)， [disable](#disable)， [getDocument](#getdocument)， [highlightNode](#highlightnode)， [hideHighlight](#hidehighlight)， [requestChildNodes](#requestchildnodes)， [getAttributes，](#getattributes) [getOuterHTML](#getouterhtml)， [pushNodesByBackendIdsToFrontend](#pushnodesbybackendidstofrontend)， [querySelector](#queryselector)， [querySelectorAll](#queryselectorall)， [requestNode ， resolveNode](#requestnode)， [setInspectedNode](#setinspectednode) [](#resolvenode)</span><span class="sxs-lookup"><span data-stu-id="28216-117">[enable](#enable), [disable](#disable), [getDocument](#getdocument), [highlightNode](#highlightnode), [hideHighlight](#hidehighlight), [requestChildNodes](#requestchildnodes), [getAttributes](#getattributes), [getOuterHTML](#getouterhtml), [pushNodesByBackendIdsToFrontend](#pushnodesbybackendidstofrontend), [querySelector](#queryselector), [querySelectorAll](#queryselectorall), [requestNode](#requestnode), [resolveNode](#resolvenode), [setInspectedNode](#setinspectednode)</span></span> |
| [**<span data-ttu-id="28216-118">事件</span><span class="sxs-lookup"><span data-stu-id="28216-118">Events</span></span>**](#events) | <span data-ttu-id="28216-119">[setChildNodes](#setchildnodes)， [attributeModified](#attributemodified)， [attributeRemoved](#attributeremoved)， [characterDataModified](#characterdatamodified)， [childNodeInserted](#childnodeinserted)， [childNodeRemoved](#childnoderemoved)， [documentUpdated](#documentupdated)</span><span class="sxs-lookup"><span data-stu-id="28216-119">[setChildNodes](#setchildnodes), [attributeModified](#attributemodified), [attributeRemoved](#attributeremoved), [characterDataModified](#characterdatamodified), [childNodeInserted](#childnodeinserted), [childNodeRemoved](#childnoderemoved), [documentUpdated](#documentupdated)</span></span> |
| [**<span data-ttu-id="28216-120">类型</span><span class="sxs-lookup"><span data-stu-id="28216-120">Types</span></span>**](#types) | <span data-ttu-id="28216-121">[RGBA](#rgba)， [HighlightConfig](#highlightconfig)， [NodeId](#nodeid)， [Node](#node)， [BackendNodeId](#backendnodeid)， [PseudoType](#pseudotype)</span><span class="sxs-lookup"><span data-stu-id="28216-121">[RGBA](#rgba), [HighlightConfig](#highlightconfig), [NodeId](#nodeid), [Node](#node), [BackendNodeId](#backendnodeid), [PseudoType](#pseudotype)</span></span> |
| [**<span data-ttu-id="28216-122">依赖关系</span><span class="sxs-lookup"><span data-stu-id="28216-122">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="28216-123">运行时</span><span class="sxs-lookup"><span data-stu-id="28216-123">Runtime</span></span>](runtime.md) |
## <span data-ttu-id="28216-124">方法</span><span class="sxs-lookup"><span data-stu-id="28216-124">Methods</span></span>

### <span data-ttu-id="28216-125">“启用”</span><span class="sxs-lookup"><span data-stu-id="28216-125">enable</span></span>
<span data-ttu-id="28216-126">为给定页面启用 DOM 代理。</span><span class="sxs-lookup"><span data-stu-id="28216-126">Enables DOM agent for the given page.</span></span>

</p>

---

### <span data-ttu-id="28216-127">“禁用”</span><span class="sxs-lookup"><span data-stu-id="28216-127">disable</span></span>
<span data-ttu-id="28216-128">禁用给定页面的 DOM 代理。</span><span class="sxs-lookup"><span data-stu-id="28216-128">Disables DOM agent for the given page.</span></span> <span data-ttu-id="28216-129">禁用 DOM 将使任何以前有效的 nodeId 失效。</span><span class="sxs-lookup"><span data-stu-id="28216-129">Disabling the DOM will invalidate any previously valid nodeIds.</span></span>

</p>

---

### <span data-ttu-id="28216-130">getDocument</span><span class="sxs-lookup"><span data-stu-id="28216-130">getDocument</span></span>
<span data-ttu-id="28216-131">返回根 DOM 节点 (（可选）将子树) 调用方。</span><span class="sxs-lookup"><span data-stu-id="28216-131">Returns the root DOM node (and optionally the subtree) to the caller.</span></span> <span data-ttu-id="28216-132">调用 `getDocument` 将使任何以前有效的 nodeId 无效</span><span class="sxs-lookup"><span data-stu-id="28216-132">Calling `getDocument` will invalidate any previously valid nodeIds</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-133">参数</span><span class="sxs-lookup"><span data-stu-id="28216-133">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-134">depth</span><span class="sxs-lookup"><span data-stu-id="28216-134">depth</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="28216-135">应检索子级的最大深度（默认为 2）。</span><span class="sxs-lookup"><span data-stu-id="28216-135">The maximum depth at which children should be retrieved, defaults to 2.</span></span> <span data-ttu-id="28216-136">将 -1 用于整个子树。</span><span class="sxs-lookup"><span data-stu-id="28216-136">Use -1 for entire subtree.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-137">一些</span><span class="sxs-lookup"><span data-stu-id="28216-137">pierce</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="28216-138">返回子树时是否应该遍历 iframe，默认值 (为 false) 。</span><span class="sxs-lookup"><span data-stu-id="28216-138">Whether or not iframes should be traversed when returning the subtree (default is false).</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-139">返回</span><span class="sxs-lookup"><span data-stu-id="28216-139">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-140">root</span><span class="sxs-lookup"><span data-stu-id="28216-140">root</span></span></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="28216-141">生成的节点。</span><span class="sxs-lookup"><span data-stu-id="28216-141">Resulting Node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-142">highlightNode</span><span class="sxs-lookup"><span data-stu-id="28216-142">highlightNode</span></span>
<span data-ttu-id="28216-143">具有给定 ID 或对象包装的 Higlights DOM 节点。</span><span class="sxs-lookup"><span data-stu-id="28216-143">Higlights DOM node with given id or object wrapper.</span></span> <span data-ttu-id="28216-144">必须指定 nodeId、backendNodeId 或 objectId。</span><span class="sxs-lookup"><span data-stu-id="28216-144">nodeId, backendNodeId, or objectId must be specified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-145">参数</span><span class="sxs-lookup"><span data-stu-id="28216-145">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-146">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-146">nodeId</span></span> <br/> <i><span data-ttu-id="28216-147">可选</span><span class="sxs-lookup"><span data-stu-id="28216-147">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-148">要突出显示的节点的标识符。</span><span class="sxs-lookup"><span data-stu-id="28216-148">Identifier of the node to highlight.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-149">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="28216-149">backendNodeId</span></span> <br/> <i><span data-ttu-id="28216-150">可选</span><span class="sxs-lookup"><span data-stu-id="28216-150">optional</span></span></i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td><span data-ttu-id="28216-151">要突出显示的后端节点的标识符。</span><span class="sxs-lookup"><span data-stu-id="28216-151">Identifier of the backend node to highlight.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-152">objectId</span><span class="sxs-lookup"><span data-stu-id="28216-152">objectId</span></span> <br/> <i><span data-ttu-id="28216-153">可选</span><span class="sxs-lookup"><span data-stu-id="28216-153">optional</span></span></i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td><span data-ttu-id="28216-154">要突出显示的节点的 JavaScript 对象 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-154">JavaScript object id of the node to be highlighted.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-155">higlightConfig</span><span class="sxs-lookup"><span data-stu-id="28216-155">higlightConfig</span></span></td>
            <td><a href="#highlightconfig"><code class="flyout">HighlightConfig</code></a></td>
            <td><span data-ttu-id="28216-156">突出显示外观的描述符。</span><span class="sxs-lookup"><span data-stu-id="28216-156">Descriptor of the highlight appearance.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-157">返回</span><span class="sxs-lookup"><span data-stu-id="28216-157">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-158">root</span><span class="sxs-lookup"><span data-stu-id="28216-158">root</span></span></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="28216-159">生成的节点。</span><span class="sxs-lookup"><span data-stu-id="28216-159">Resulting Node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-160">hideHighlight</span><span class="sxs-lookup"><span data-stu-id="28216-160">hideHighlight</span></span>
<span data-ttu-id="28216-161">隐藏任何当前 DOM 节点突出显示。</span><span class="sxs-lookup"><span data-stu-id="28216-161">Hides any current DOM node highlight.</span></span>

</p>

---

### <span data-ttu-id="28216-162">requestChildNodes</span><span class="sxs-lookup"><span data-stu-id="28216-162">requestChildNodes</span></span>
<span data-ttu-id="28216-163">请求将具有给定 ID 的节点的子级以事件形式返回给呼叫 `setChildNodes` 者。</span><span class="sxs-lookup"><span data-stu-id="28216-163">Requests that children of the node with given id are returned to ghe caller in the form of `setChildNodes` events.</span></span> `setChildNodes` <span data-ttu-id="28216-164">将针对之前未返回其子级的每个节点（从请求的节点向下到指定深度）触发。</span><span class="sxs-lookup"><span data-stu-id="28216-164">will be fired for each node that has not previously returned it's children, starting from the requested node down to the specified depth.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-165">参数</span><span class="sxs-lookup"><span data-stu-id="28216-165">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-166">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-166">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-167">要获取其子节点的 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-167">Id of the node to get children from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-168">depth</span><span class="sxs-lookup"><span data-stu-id="28216-168">depth</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="28216-169">应检索子级的最大深度，默认为 1。</span><span class="sxs-lookup"><span data-stu-id="28216-169">The maximum depth at which children should be retrieved, defaults to 1.</span></span> <span data-ttu-id="28216-170">将 -1 用于整个子树。</span><span class="sxs-lookup"><span data-stu-id="28216-170">Use -1 for entire subtree.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-171">一些</span><span class="sxs-lookup"><span data-stu-id="28216-171">pierce</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="28216-172">返回子树时是否应该遍历 iframe，默认值 (为 false) 。</span><span class="sxs-lookup"><span data-stu-id="28216-172">Whether or not iframes should be traversed when returning the subtree (default is false).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-173">getAttributes</span><span class="sxs-lookup"><span data-stu-id="28216-173">getAttributes</span></span>
<span data-ttu-id="28216-174">返回指定节点的属性。</span><span class="sxs-lookup"><span data-stu-id="28216-174">Returns attributes for the specified node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-175">参数</span><span class="sxs-lookup"><span data-stu-id="28216-175">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-176">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-176">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-177">要检索其属性的节点的 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-177">Id of the node to retrieve attibutes for.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-178">返回</span><span class="sxs-lookup"><span data-stu-id="28216-178">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-179">attributes</span><span class="sxs-lookup"><span data-stu-id="28216-179">attributes</span></span></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="28216-180">节点属性名称和值的交错数组。</span><span class="sxs-lookup"><span data-stu-id="28216-180">An interleaved array of node attribute names and values.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-181">getOuterHTML</span><span class="sxs-lookup"><span data-stu-id="28216-181">getOuterHTML</span></span>
<span data-ttu-id="28216-182">返回节点的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="28216-182">Returns node's HTML markup.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-183">参数</span><span class="sxs-lookup"><span data-stu-id="28216-183">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-184">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-184">nodeId</span></span> <br/> <i><span data-ttu-id="28216-185">可选</span><span class="sxs-lookup"><span data-stu-id="28216-185">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-186">节点的标识符。</span><span class="sxs-lookup"><span data-stu-id="28216-186">Identifier of the node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-187">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="28216-187">backendNodeId</span></span> <br/> <i><span data-ttu-id="28216-188">可选</span><span class="sxs-lookup"><span data-stu-id="28216-188">optional</span></span></i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td><span data-ttu-id="28216-189">后端节点的标识符。</span><span class="sxs-lookup"><span data-stu-id="28216-189">Identifier of the backend node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-190">objectId</span><span class="sxs-lookup"><span data-stu-id="28216-190">objectId</span></span> <br/> <i><span data-ttu-id="28216-191">可选</span><span class="sxs-lookup"><span data-stu-id="28216-191">optional</span></span></i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td><span data-ttu-id="28216-192">节点包装的 JavaScript 对象 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-192">JavaScript object id of the node wrapper.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-193">返回</span><span class="sxs-lookup"><span data-stu-id="28216-193">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-194">outerHTML</span><span class="sxs-lookup"><span data-stu-id="28216-194">outerHTML</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="28216-195">外部 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="28216-195">Outer HTML markup.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-196">pushNodesByBackendIdsToFrontend</span><span class="sxs-lookup"><span data-stu-id="28216-196">pushNodesByBackendIdsToFrontend</span></span>
<span data-ttu-id="28216-197">查找节点 ID 并解析指定后端节点 ID 的所有父节点</span><span class="sxs-lookup"><span data-stu-id="28216-197">Looks up Node Ids and resolves all parents for the specified Backend Node Ids</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-198">参数</span><span class="sxs-lookup"><span data-stu-id="28216-198">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-199">backendNodeIds</span><span class="sxs-lookup"><span data-stu-id="28216-199">backendNodeIds</span></span></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId[]</code></a></td>
            <td><span data-ttu-id="28216-200">要解析的节点的后端节点 ID</span><span class="sxs-lookup"><span data-stu-id="28216-200">Backend Node IDs of the nodes to resolve</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-201">返回</span><span class="sxs-lookup"><span data-stu-id="28216-201">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-202">nodeIds</span><span class="sxs-lookup"><span data-stu-id="28216-202">nodeIds</span></span></td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td><span data-ttu-id="28216-203">已解析节点的节点 ID</span><span class="sxs-lookup"><span data-stu-id="28216-203">Node Ids of the resolved nodes</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-204">querySelector</span><span class="sxs-lookup"><span data-stu-id="28216-204">querySelector</span></span>
<span data-ttu-id="28216-205">在 `querySelector` 给定节点上执行。</span><span class="sxs-lookup"><span data-stu-id="28216-205">Executes `querySelector` on a given node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-206">参数</span><span class="sxs-lookup"><span data-stu-id="28216-206">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-207">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-207">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-208">要查询的节点的 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-208">Id of the node to query upon.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-209">选择器</span><span class="sxs-lookup"><span data-stu-id="28216-209">selector</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="28216-210">选择器字符串。</span><span class="sxs-lookup"><span data-stu-id="28216-210">The selector string.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-211">返回</span><span class="sxs-lookup"><span data-stu-id="28216-211">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-212">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-212">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-213">查询选择器结果。</span><span class="sxs-lookup"><span data-stu-id="28216-213">Query selector result.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-214">querySelectorAll</span><span class="sxs-lookup"><span data-stu-id="28216-214">querySelectorAll</span></span>
<span data-ttu-id="28216-215">在 `querySelectorAll` 给定节点上执行。</span><span class="sxs-lookup"><span data-stu-id="28216-215">Executes `querySelectorAll` on a given node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-216">参数</span><span class="sxs-lookup"><span data-stu-id="28216-216">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-217">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-217">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-218">要查询的节点的 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-218">Id of the node to query upon.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-219">选择器</span><span class="sxs-lookup"><span data-stu-id="28216-219">selector</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="28216-220">选择器字符串。</span><span class="sxs-lookup"><span data-stu-id="28216-220">The selector string.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-221">返回</span><span class="sxs-lookup"><span data-stu-id="28216-221">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-222">nodeIds</span><span class="sxs-lookup"><span data-stu-id="28216-222">nodeIds</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td><span data-ttu-id="28216-223">查询选择器结果。</span><span class="sxs-lookup"><span data-stu-id="28216-223">Query selector results.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-224">requestNode</span><span class="sxs-lookup"><span data-stu-id="28216-224">requestNode</span></span>
<span data-ttu-id="28216-225">请求将具有给定远程对象 ID 的节点发送给调用方。</span><span class="sxs-lookup"><span data-stu-id="28216-225">Requests that the node with given remote object Id is sent to caller.</span></span> <span data-ttu-id="28216-226">构成从节点到根的路径的所有节点也会作为一系列通知发送到 `setChildNodes` 客户端。</span><span class="sxs-lookup"><span data-stu-id="28216-226">All nodes that form the path from the node to the root are also sent to the client as a series of `setChildNodes` notifications.</span></span> <span data-ttu-id="28216-227">如果包含请求的节点的文档之前尚未由客户端请求，则返回 0。</span><span class="sxs-lookup"><span data-stu-id="28216-227">returns 0 if the document containing the requested node has not previously been requested by the client.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-228">参数</span><span class="sxs-lookup"><span data-stu-id="28216-228">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-229">objectId</span><span class="sxs-lookup"><span data-stu-id="28216-229">objectId</span></span></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td><span data-ttu-id="28216-230">要转换为节点的 JavaScript 对象 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-230">JavaScript object Id to convert into node.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-231">返回</span><span class="sxs-lookup"><span data-stu-id="28216-231">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-232">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-232">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-233">给定对象的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-233">Node Id for given object.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-234">resolveNode</span><span class="sxs-lookup"><span data-stu-id="28216-234">resolveNode</span></span>
<span data-ttu-id="28216-235">解析给定 NodeId 或 BackendNodeId 的 JavaScript 节点对象。</span><span class="sxs-lookup"><span data-stu-id="28216-235">Resolves the JavaScript node object for a given NodeId or BackendNodeId.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-236">参数</span><span class="sxs-lookup"><span data-stu-id="28216-236">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-237">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-237">nodeId</span></span> <br/> <i><span data-ttu-id="28216-238">可选</span><span class="sxs-lookup"><span data-stu-id="28216-238">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-239">要解析的节点的 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-239">Id of the node to resolve.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-240">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="28216-240">backendNodeId</span></span> <br/> <i><span data-ttu-id="28216-241">可选</span><span class="sxs-lookup"><span data-stu-id="28216-241">optional</span></span></i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td><span data-ttu-id="28216-242">要解析的节点的后端节点 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-242">Backend Node Id of the node to resolve.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-243">objectGroup</span><span class="sxs-lookup"><span data-stu-id="28216-243">objectGroup</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="28216-244">可用于释放多个对象的符号组名称。</span><span class="sxs-lookup"><span data-stu-id="28216-244">Symbolic group name that can be used to release multiple objects.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-245">返回</span><span class="sxs-lookup"><span data-stu-id="28216-245">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-246">object</span><span class="sxs-lookup"><span data-stu-id="28216-246">object</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="28216-247">给定节点的 JavaScript 对象包装。</span><span class="sxs-lookup"><span data-stu-id="28216-247">JavaScript object wrapper for given node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-248">setInspectedNode</span><span class="sxs-lookup"><span data-stu-id="28216-248">setInspectedNode</span></span>
<span><b><span data-ttu-id="28216-249">实验。</span><span class="sxs-lookup"><span data-stu-id="28216-249">Experimental.</span></span> </b></span><span data-ttu-id="28216-250">允许控制台通过 $0-$4 引用具有给定 ID 的上一个已检查节点。</span><span class="sxs-lookup"><span data-stu-id="28216-250">Enables console to refer to the previous inspected node with given id via $0-$4.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-251">参数</span><span class="sxs-lookup"><span data-stu-id="28216-251">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-252">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-252">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-253">可通过命令行 API 中的 $0-$4 访问 DOM 节点 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-253">DOM node id to be accessible by means of $0-$4 in command line API.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="28216-254">事件</span><span class="sxs-lookup"><span data-stu-id="28216-254">Events</span></span>

### <span data-ttu-id="28216-255">setChildNodes</span><span class="sxs-lookup"><span data-stu-id="28216-255">setChildNodes</span></span>
<span data-ttu-id="28216-256">当后端希望向客户端提供缺少 DOM 结构时触发。</span><span class="sxs-lookup"><span data-stu-id="28216-256">Fired when the backend wishes to provide client with missing DOM structure.</span></span> <span data-ttu-id="28216-257">大多数请求 nodeIds 的调用时发生此情况</span><span class="sxs-lookup"><span data-stu-id="28216-257">This happens upon most calls requesting nodeIds</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-258">参数</span><span class="sxs-lookup"><span data-stu-id="28216-258">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-259">parentId</span><span class="sxs-lookup"><span data-stu-id="28216-259">parentId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-260">要弹出带子元素的父节点。</span><span class="sxs-lookup"><span data-stu-id="28216-260">Parent node to poplate with children.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-261">节点</span><span class="sxs-lookup"><span data-stu-id="28216-261">nodes</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td><span data-ttu-id="28216-262">子节点数组。</span><span class="sxs-lookup"><span data-stu-id="28216-262">Child nodes array.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-263">attributeModified</span><span class="sxs-lookup"><span data-stu-id="28216-263">attributeModified</span></span>
<span data-ttu-id="28216-264">修改 `Element` 's 属性时触发。</span><span class="sxs-lookup"><span data-stu-id="28216-264">Fired when `Element`'s attribute is modified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-265">参数</span><span class="sxs-lookup"><span data-stu-id="28216-265">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-266">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-266">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-267">已更改的节点的 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-267">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-268">name</span><span class="sxs-lookup"><span data-stu-id="28216-268">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="28216-269">属性名称。</span><span class="sxs-lookup"><span data-stu-id="28216-269">Attribute name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-270">值</span><span class="sxs-lookup"><span data-stu-id="28216-270">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="28216-271">属性值。</span><span class="sxs-lookup"><span data-stu-id="28216-271">Attribute value.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-272">attributeRemoved</span><span class="sxs-lookup"><span data-stu-id="28216-272">attributeRemoved</span></span>
<span data-ttu-id="28216-273">删除 `Element` 's 属性时触发。</span><span class="sxs-lookup"><span data-stu-id="28216-273">Fired when `Element`'s attribute is removed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-274">参数</span><span class="sxs-lookup"><span data-stu-id="28216-274">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-275">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-275">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-276">已更改的节点的 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-276">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-277">name</span><span class="sxs-lookup"><span data-stu-id="28216-277">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="28216-278">属性名称。</span><span class="sxs-lookup"><span data-stu-id="28216-278">Attribute name.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-279">characterDataModified</span><span class="sxs-lookup"><span data-stu-id="28216-279">characterDataModified</span></span>
<span data-ttu-id="28216-280">镜像 `DOMCharacterDataModified` 事件。</span><span class="sxs-lookup"><span data-stu-id="28216-280">Mirrors `DOMCharacterDataModified` event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-281">参数</span><span class="sxs-lookup"><span data-stu-id="28216-281">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-282">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-282">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-283">已更改的节点的 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-283">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-284">charcterData</span><span class="sxs-lookup"><span data-stu-id="28216-284">charcterData</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="28216-285">新文本值。</span><span class="sxs-lookup"><span data-stu-id="28216-285">New text value.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-286">childNodeInserted</span><span class="sxs-lookup"><span data-stu-id="28216-286">childNodeInserted</span></span>
<span data-ttu-id="28216-287">镜像 `DOMNodeInserted` 事件。</span><span class="sxs-lookup"><span data-stu-id="28216-287">Mirrors `DOMNodeInserted` event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-288">参数</span><span class="sxs-lookup"><span data-stu-id="28216-288">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-289">parentNodeId</span><span class="sxs-lookup"><span data-stu-id="28216-289">parentNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-290">已更改的节点的 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-290">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-291">previousNodeId</span><span class="sxs-lookup"><span data-stu-id="28216-291">previousNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-292">插入的节点的上一同级节点的 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-292">Id of the inserted node's previous sibling.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-293">node</span><span class="sxs-lookup"><span data-stu-id="28216-293">node</span></span></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="28216-294">插入的节点数据。</span><span class="sxs-lookup"><span data-stu-id="28216-294">Inserted node data.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-295">childNodeRemoved</span><span class="sxs-lookup"><span data-stu-id="28216-295">childNodeRemoved</span></span>
<span data-ttu-id="28216-296">镜像 `DOMNodeRemoved` 事件。</span><span class="sxs-lookup"><span data-stu-id="28216-296">Mirrors `DOMNodeRemoved` event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-297">参数</span><span class="sxs-lookup"><span data-stu-id="28216-297">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-298">parentNodeId</span><span class="sxs-lookup"><span data-stu-id="28216-298">parentNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-299">已更改的节点的 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-299">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-300">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-300">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-301">已删除的节点的 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-301">Id of the node that has been removed.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="28216-302">documentUpdated</span><span class="sxs-lookup"><span data-stu-id="28216-302">documentUpdated</span></span>
<span data-ttu-id="28216-303">在 `Document` 完全更新时触发。</span><span class="sxs-lookup"><span data-stu-id="28216-303">Fired when `Document` has been totally updated.</span></span> <span data-ttu-id="28216-304">节点 ID 不再有效。</span><span class="sxs-lookup"><span data-stu-id="28216-304">Node ids are no longer valid.</span></span>

</p>

---

## <span data-ttu-id="28216-305">类型</span><span class="sxs-lookup"><span data-stu-id="28216-305">Types</span></span>

### <a name="rgba"></a> <span data-ttu-id="28216-306">RGBA</span><span class="sxs-lookup"><span data-stu-id="28216-306">RGBA</span></span> `object`

<span data-ttu-id="28216-307">一种保持 RGBA 颜色的结构。</span><span class="sxs-lookup"><span data-stu-id="28216-307">A Structure holding an RGBA color.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-308">属性</span><span class="sxs-lookup"><span data-stu-id="28216-308">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-309">r</span><span class="sxs-lookup"><span data-stu-id="28216-309">r</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="28216-310">红色分量，在 [0-255] 范围内。</span><span class="sxs-lookup"><span data-stu-id="28216-310">The red component, in the [0-255] range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-311">g</span><span class="sxs-lookup"><span data-stu-id="28216-311">g</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="28216-312">绿色分量，在 [0-255] 范围内。</span><span class="sxs-lookup"><span data-stu-id="28216-312">The green component, in the [0-255] range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-313">b</span><span class="sxs-lookup"><span data-stu-id="28216-313">b</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="28216-314">[0-255] 范围中的蓝色分量。</span><span class="sxs-lookup"><span data-stu-id="28216-314">The blue component, in the [0-255] range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-315">a</span><span class="sxs-lookup"><span data-stu-id="28216-315">a</span></span> <br/> <i><span data-ttu-id="28216-316">可选</span><span class="sxs-lookup"><span data-stu-id="28216-316">optional</span></span></i></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="28216-317">alpha 分量，在 [0-1] 范围内。</span><span class="sxs-lookup"><span data-stu-id="28216-317">The alpha component, in the [0-1] range.</span></span> <span data-ttu-id="28216-318">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="28216-318">Default is 1.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="highlightconfig"></a> <span data-ttu-id="28216-319">HighlightConfig</span><span class="sxs-lookup"><span data-stu-id="28216-319">HighlightConfig</span></span> `object`

<span data-ttu-id="28216-320">用于突出显示页面元素的配置数据。</span><span class="sxs-lookup"><span data-stu-id="28216-320">Configuration data for highlighting of page elements.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-321">属性</span><span class="sxs-lookup"><span data-stu-id="28216-321">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-322">contentColor</span><span class="sxs-lookup"><span data-stu-id="28216-322">contentColor</span></span> <br/> <i><span data-ttu-id="28216-323">可选</span><span class="sxs-lookup"><span data-stu-id="28216-323">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="28216-324">内容框突出显示填充颜色。</span><span class="sxs-lookup"><span data-stu-id="28216-324">The content box highlight fill color.</span></span> <span data-ttu-id="28216-325">默认值为透明。</span><span class="sxs-lookup"><span data-stu-id="28216-325">Default is transparent.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-326">paddingColor</span><span class="sxs-lookup"><span data-stu-id="28216-326">paddingColor</span></span> <br/> <i><span data-ttu-id="28216-327">可选</span><span class="sxs-lookup"><span data-stu-id="28216-327">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="28216-328">填充突出显示填充颜色。</span><span class="sxs-lookup"><span data-stu-id="28216-328">The padding highlight fill color.</span></span> <span data-ttu-id="28216-329">默认值为透明。</span><span class="sxs-lookup"><span data-stu-id="28216-329">Default is transparent.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-330">borderColor</span><span class="sxs-lookup"><span data-stu-id="28216-330">borderColor</span></span> <br/> <i><span data-ttu-id="28216-331">可选</span><span class="sxs-lookup"><span data-stu-id="28216-331">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="28216-332">边框突出显示填充颜色。</span><span class="sxs-lookup"><span data-stu-id="28216-332">The border highlight fill color.</span></span> <span data-ttu-id="28216-333">默认值为透明。</span><span class="sxs-lookup"><span data-stu-id="28216-333">Default is transparent.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-334">marginColor</span><span class="sxs-lookup"><span data-stu-id="28216-334">marginColor</span></span> <br/> <i><span data-ttu-id="28216-335">可选</span><span class="sxs-lookup"><span data-stu-id="28216-335">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="28216-336">边距突出显示填充颜色。</span><span class="sxs-lookup"><span data-stu-id="28216-336">The margin highlight fill color.</span></span> <span data-ttu-id="28216-337">默认值为透明。</span><span class="sxs-lookup"><span data-stu-id="28216-337">Default is transparent.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="nodeid"></a> <span data-ttu-id="28216-338">NodeId</span><span class="sxs-lookup"><span data-stu-id="28216-338">NodeId</span></span> `integer`

<span data-ttu-id="28216-339">唯一 DOM 节点标识符</span><span class="sxs-lookup"><span data-stu-id="28216-339">Unique DOM node identifier</span></span>

</p>

---

### <a name="node"></a> <span data-ttu-id="28216-340">节点</span><span class="sxs-lookup"><span data-stu-id="28216-340">Node</span></span> `object`

<span data-ttu-id="28216-341">表示实际 DOM 节点的镜像对象。</span><span class="sxs-lookup"><span data-stu-id="28216-341">Mirror object that represents the actual DOM nodes.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="28216-342">属性</span><span class="sxs-lookup"><span data-stu-id="28216-342">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="28216-343">nodeId</span><span class="sxs-lookup"><span data-stu-id="28216-343">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-344">用于引用此节点的节点标识符。</span><span class="sxs-lookup"><span data-stu-id="28216-344">Node Identifier used to reference this node.</span></span> <span data-ttu-id="28216-345">后端将为具有客户端已知的 nodeId 的节点启动 DOM 事件</span><span class="sxs-lookup"><span data-stu-id="28216-345">Backend will fire DOM events for nodes that have a nodeId that is known to the client</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-346">parentId</span><span class="sxs-lookup"><span data-stu-id="28216-346">parentId</span></span> <br/> <i><span data-ttu-id="28216-347">可选</span><span class="sxs-lookup"><span data-stu-id="28216-347">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-348">父节点的节点标识符（如果有）。</span><span class="sxs-lookup"><span data-stu-id="28216-348">Node Identifier of the parent Node, if any.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-349">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="28216-349">backendNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="28216-350">节点的后端节点标识符。</span><span class="sxs-lookup"><span data-stu-id="28216-350">Backend Node identifier of the node.</span></span> <span data-ttu-id="28216-351">BackendNodeIds 引用客户端已知的节点，但不推送有关此节点的 DOM 事件。</span><span class="sxs-lookup"><span data-stu-id="28216-351">BackendNodeIds reference Nodes that can be known to the client, but do not push DOM events about this node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-352">nodeType</span><span class="sxs-lookup"><span data-stu-id="28216-352">nodeType</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td>`Node`<span data-ttu-id="28216-353">'s nodeType。</span><span class="sxs-lookup"><span data-stu-id="28216-353">'s nodeType.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-354">nodeName</span><span class="sxs-lookup"><span data-stu-id="28216-354">nodeName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td>`Node`<span data-ttu-id="28216-355">'s nodeName.</span><span class="sxs-lookup"><span data-stu-id="28216-355">'s nodeName.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-356">localName</span><span class="sxs-lookup"><span data-stu-id="28216-356">localName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td>`Node`<span data-ttu-id="28216-357">'s localName</span><span class="sxs-lookup"><span data-stu-id="28216-357">'s localName</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-358">nodeValue</span><span class="sxs-lookup"><span data-stu-id="28216-358">nodeValue</span></span></td>
            <td><code class="flyout">string</code></td>
            <td>`Node`<span data-ttu-id="28216-359">'s nodeValue</span><span class="sxs-lookup"><span data-stu-id="28216-359">'s nodeValue</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-360">childNodeCount</span><span class="sxs-lookup"><span data-stu-id="28216-360">childNodeCount</span></span> <br/> <i><span data-ttu-id="28216-361">可选</span><span class="sxs-lookup"><span data-stu-id="28216-361">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="28216-362">节点的子 `Container` 计数。</span><span class="sxs-lookup"><span data-stu-id="28216-362">Child count for `Container` nodes.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-363">儿童</span><span class="sxs-lookup"><span data-stu-id="28216-363">children</span></span> <br/> <i><span data-ttu-id="28216-364">可选</span><span class="sxs-lookup"><span data-stu-id="28216-364">optional</span></span></i></td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td><span data-ttu-id="28216-365">具有子级时请求此节点的子节点。</span><span class="sxs-lookup"><span data-stu-id="28216-365">Child nodes of this node when requested with children.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-366">attributes</span><span class="sxs-lookup"><span data-stu-id="28216-366">attributes</span></span> <br/> <i><span data-ttu-id="28216-367">可选</span><span class="sxs-lookup"><span data-stu-id="28216-367">optional</span></span></i></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="28216-368">平面数组 `Element` "[name1， value1， name2， value2] 形式的节点属性</span><span class="sxs-lookup"><span data-stu-id="28216-368">Attributes of `Element` nodes in the form of a flat array \`[name1, value1, name2, value2]</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-369">documentURL</span><span class="sxs-lookup"><span data-stu-id="28216-369">documentURL</span></span> <br/> <i><span data-ttu-id="28216-370">可选</span><span class="sxs-lookup"><span data-stu-id="28216-370">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="28216-371">节点指向 `Document` 的文档 URL。</span><span class="sxs-lookup"><span data-stu-id="28216-371">Document URL that `Document` nodes point to.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-372">baseURL</span><span class="sxs-lookup"><span data-stu-id="28216-372">baseURL</span></span> <br/> <i><span data-ttu-id="28216-373">可选</span><span class="sxs-lookup"><span data-stu-id="28216-373">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="28216-374">节点用于 `Document` URL 完成的文档 URL。</span><span class="sxs-lookup"><span data-stu-id="28216-374">Document URL that `Document` nodes use for URL completion.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-375">publicId</span><span class="sxs-lookup"><span data-stu-id="28216-375">publicId</span></span> <br/> <i><span data-ttu-id="28216-376">可选</span><span class="sxs-lookup"><span data-stu-id="28216-376">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` <span data-ttu-id="28216-377">节点的 publicId。</span><span class="sxs-lookup"><span data-stu-id="28216-377">Node's publicId.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-378">systemId</span><span class="sxs-lookup"><span data-stu-id="28216-378">systemId</span></span> <br/> <i><span data-ttu-id="28216-379">可选</span><span class="sxs-lookup"><span data-stu-id="28216-379">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` <span data-ttu-id="28216-380">节点的 systemId。</span><span class="sxs-lookup"><span data-stu-id="28216-380">Node's systemId.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-381">internalSubset</span><span class="sxs-lookup"><span data-stu-id="28216-381">internalSubset</span></span> <br/> <i><span data-ttu-id="28216-382">可选</span><span class="sxs-lookup"><span data-stu-id="28216-382">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` <span data-ttu-id="28216-383">节点的 internalSubset。</span><span class="sxs-lookup"><span data-stu-id="28216-383">Node's internalSubset.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-384">xmlVersion</span><span class="sxs-lookup"><span data-stu-id="28216-384">xmlVersion</span></span> <br/> <i><span data-ttu-id="28216-385">可选</span><span class="sxs-lookup"><span data-stu-id="28216-385">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`Document` <span data-ttu-id="28216-386">对于 XML 文档，节点的 xml 版本。</span><span class="sxs-lookup"><span data-stu-id="28216-386">Node's xml version in the case of XML documents.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-387">name</span><span class="sxs-lookup"><span data-stu-id="28216-387">name</span></span> <br/> <i><span data-ttu-id="28216-388">可选</span><span class="sxs-lookup"><span data-stu-id="28216-388">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` <span data-ttu-id="28216-389">节点的名称。</span><span class="sxs-lookup"><span data-stu-id="28216-389">Node's name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-390">值</span><span class="sxs-lookup"><span data-stu-id="28216-390">value</span></span> <br/> <i><span data-ttu-id="28216-391">可选</span><span class="sxs-lookup"><span data-stu-id="28216-391">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` <span data-ttu-id="28216-392">节点的值。</span><span class="sxs-lookup"><span data-stu-id="28216-392">Node's value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-393">frameId</span><span class="sxs-lookup"><span data-stu-id="28216-393">frameId</span></span> <br/> <i><span data-ttu-id="28216-394">可选</span><span class="sxs-lookup"><span data-stu-id="28216-394">optional</span></span></i></td>
            <td><a href="page.md#frameid"><code class="flyout">Page.FrameId</code></a></td>
            <td><span data-ttu-id="28216-395">帧所有者元素的帧 ID。</span><span class="sxs-lookup"><span data-stu-id="28216-395">Frame ID for frame owner elements.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-396">contentDocument</span><span class="sxs-lookup"><span data-stu-id="28216-396">contentDocument</span></span> <br/> <i><span data-ttu-id="28216-397">可选</span><span class="sxs-lookup"><span data-stu-id="28216-397">optional</span></span></i></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="28216-398">框架所有者元素的内容文档。</span><span class="sxs-lookup"><span data-stu-id="28216-398">Content document for frame owner elements.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="28216-399">isSVG</span><span class="sxs-lookup"><span data-stu-id="28216-399">isSVG</span></span> <br/> <i><span data-ttu-id="28216-400">可选</span><span class="sxs-lookup"><span data-stu-id="28216-400">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="28216-401">如果节点为 SVG，则其为 True。</span><span class="sxs-lookup"><span data-stu-id="28216-401">True if the node is SVG.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="backendnodeid"></a> <span data-ttu-id="28216-402">BackendNodeId</span><span class="sxs-lookup"><span data-stu-id="28216-402">BackendNodeId</span></span> `integer`

<span data-ttu-id="28216-403">用于引用可能尚未推送到前端的节点的唯一 DOM 节点标识符。</span><span class="sxs-lookup"><span data-stu-id="28216-403">Unique DOM node identifier used to reference a node that may not have been pushed to the front-end.</span></span>

</p>

---

### <a name="pseudotype"></a> <span data-ttu-id="28216-404">PseudoType</span><span class="sxs-lookup"><span data-stu-id="28216-404">PseudoType</span></span> `string`

<span data-ttu-id="28216-405">伪元素类型。</span><span class="sxs-lookup"><span data-stu-id="28216-405">Pseudo element type.</span></span>

##### <span data-ttu-id="28216-406">允许的值</span><span class="sxs-lookup"><span data-stu-id="28216-406">Allowed Values</span></span>
<span data-ttu-id="28216-407">第一行、第一个字母、之前、之后、所选内容</span><span class="sxs-lookup"><span data-stu-id="28216-407">first-line, first-letter, before, after, selection</span></span>
</p>

---

## <span data-ttu-id="28216-408">依赖关系</span><span class="sxs-lookup"><span data-stu-id="28216-408">Dependencies</span></span>

[<span data-ttu-id="28216-409">运行时</span><span class="sxs-lookup"><span data-stu-id="28216-409">Runtime</span></span>](runtime.md)
