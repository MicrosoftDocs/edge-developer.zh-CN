---
description: 对 DOM 域的引用。 此域公开了 DOM 读/写操作。 每个 DOM 节点都由其镜像对象表示，其镜像对象具有 `id` 。 这 `id` 可用于获取有关节点的其他信息、将其解析为 JavaScript 对象包装等。客户只能接收客户端已知节点的 DOM 事件，这一点非常重要。 后端将跟踪已发送到客户端的节点，并且不会两次发送相同的节点。 客户负责收集有关已发送到客户端的节点的信息。<p>请注意， `iframe` 所有者元素将返回对应的文档元素作为其子节点。</p>
title: DOM 域-DevTools 协议版本0。2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 9ebe5ff709ac2981cb2359b7279c5d4e5d375426
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563405"
---
# <span data-ttu-id="fb239-109">DOM</span><span class="sxs-lookup"><span data-stu-id="fb239-109">DOM</span></span>
<span data-ttu-id="fb239-110">此域公开了 DOM 读/写操作。</span><span class="sxs-lookup"><span data-stu-id="fb239-110">This domain exposes DOM read/write operations.</span></span> <span data-ttu-id="fb239-111">每个 DOM 节点都由其镜像对象表示，其镜像对象具有 `id` 。</span><span class="sxs-lookup"><span data-stu-id="fb239-111">Each DOM Node is represented with its mirror object that has an `id`.</span></span> <span data-ttu-id="fb239-112">这 `id` 可用于获取有关节点的其他信息、将其解析为 JavaScript 对象包装等。客户只能接收客户端已知节点的 DOM 事件，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="fb239-112">This `id` can be used to get additional information on the Node, resolve it into the JavaScript object wrapper, etc. It is important that client receives DOM events only for the nodes that are known to the client.</span></span> <span data-ttu-id="fb239-113">后端将跟踪已发送到客户端的节点，并且不会两次发送相同的节点。</span><span class="sxs-lookup"><span data-stu-id="fb239-113">Backend keeps track of the nodes that were sent to the client and never sends the same node twice.</span></span> <span data-ttu-id="fb239-114">客户负责收集有关已发送到客户端的节点的信息。</span><span class="sxs-lookup"><span data-stu-id="fb239-114">It is client's responsibility to collect information about the nodes that were sent to the client.</span></span><p><span data-ttu-id="fb239-115">请注意， `iframe` 所有者元素将返回对应的文档元素作为其子节点。</span><span class="sxs-lookup"><span data-stu-id="fb239-115">Note that `iframe` owner elements will return corresponding document elements as their child nodes.</span></span></p>

| | |
|-|-|
| [**<span data-ttu-id="fb239-116">方法</span><span class="sxs-lookup"><span data-stu-id="fb239-116">Methods</span></span>**](#methods) | <span data-ttu-id="fb239-117">[enable](#enable)、 [disable](#disable)、 [getDocument](#getdocument)、 [highlightNode](#highlightnode)、 [hideHighlight](#hidehighlight)、 [requestChildNodes](#requestchildnodes)、 [getAttributes](#getattributes)、 [getOuterHTML](#getouterhtml)、 [pushNodesByBackendIdsToFrontend](#pushnodesbybackendidstofrontend)、 [querySelector](#queryselector)、 [querySelectorAll、](#queryselectorall)requestNode、 [resolveNode](#resolvenode)、setInspectedNode、 [、](#requestnode)、 [、](#setinspectednode)</span><span class="sxs-lookup"><span data-stu-id="fb239-117">[enable](#enable), [disable](#disable), [getDocument](#getdocument), [highlightNode](#highlightnode), [hideHighlight](#hidehighlight), [requestChildNodes](#requestchildnodes), [getAttributes](#getattributes), [getOuterHTML](#getouterhtml), [pushNodesByBackendIdsToFrontend](#pushnodesbybackendidstofrontend), [querySelector](#queryselector), [querySelectorAll](#queryselectorall), [requestNode](#requestnode), [resolveNode](#resolvenode), [setInspectedNode](#setinspectednode)</span></span> |
| [**<span data-ttu-id="fb239-118">事件</span><span class="sxs-lookup"><span data-stu-id="fb239-118">Events</span></span>**](#events) | <span data-ttu-id="fb239-119">[setChildNodes](#setchildnodes)、 [attributeModified](#attributemodified)、 [attributeRemoved](#attributeremoved)、 [characterDataModified](#characterdatamodified)、 [childNodeInserted](#childnodeinserted)、 [childNodeRemoved](#childnoderemoved)、 [documentUpdated](#documentupdated)</span><span class="sxs-lookup"><span data-stu-id="fb239-119">[setChildNodes](#setchildnodes), [attributeModified](#attributemodified), [attributeRemoved](#attributeremoved), [characterDataModified](#characterdatamodified), [childNodeInserted](#childnodeinserted), [childNodeRemoved](#childnoderemoved), [documentUpdated](#documentupdated)</span></span> |
| [**<span data-ttu-id="fb239-120">类型</span><span class="sxs-lookup"><span data-stu-id="fb239-120">Types</span></span>**](#types) | <span data-ttu-id="fb239-121">[RGBA](#rgba)、 [HighlightConfig](#highlightconfig)、 [NodeId](#nodeid)[节点](#node)、 [BackendNodeId](#backendnodeid)、 [PseudoType](#pseudotype)</span><span class="sxs-lookup"><span data-stu-id="fb239-121">[RGBA](#rgba), [HighlightConfig](#highlightconfig), [NodeId](#nodeid), [Node](#node), [BackendNodeId](#backendnodeid), [PseudoType](#pseudotype)</span></span> |
| [**<span data-ttu-id="fb239-122">依赖关系</span><span class="sxs-lookup"><span data-stu-id="fb239-122">Dependencies</span></span>**](#dependencies) | [<span data-ttu-id="fb239-123">运行时</span><span class="sxs-lookup"><span data-stu-id="fb239-123">Runtime</span></span>](runtime.md) |
## <span data-ttu-id="fb239-124">方法</span><span class="sxs-lookup"><span data-stu-id="fb239-124">Methods</span></span>

### <span data-ttu-id="fb239-125">“启用”</span><span class="sxs-lookup"><span data-stu-id="fb239-125">enable</span></span>
<span data-ttu-id="fb239-126">为给定页面启用 DOM 代理。</span><span class="sxs-lookup"><span data-stu-id="fb239-126">Enables DOM agent for the given page.</span></span>

</p>

---

### <span data-ttu-id="fb239-127">“禁用”</span><span class="sxs-lookup"><span data-stu-id="fb239-127">disable</span></span>
<span data-ttu-id="fb239-128">为给定页面禁用 DOM 代理。</span><span class="sxs-lookup"><span data-stu-id="fb239-128">Disables DOM agent for the given page.</span></span> <span data-ttu-id="fb239-129">禁用 DOM 将使以前任何有效的 nodeIds 无效。</span><span class="sxs-lookup"><span data-stu-id="fb239-129">Disabling the DOM will invalidate any previously valid nodeIds.</span></span>

</p>

---

### <span data-ttu-id="fb239-130">getDocument</span><span class="sxs-lookup"><span data-stu-id="fb239-130">getDocument</span></span>
<span data-ttu-id="fb239-131">返回调用方的根 DOM 节点（也可以选择子树）。</span><span class="sxs-lookup"><span data-stu-id="fb239-131">Returns the root DOM node (and optionally the subtree) to the caller.</span></span> <span data-ttu-id="fb239-132">通话 `getDocument` 将使以前任何有效的 nodeIds 失效</span><span class="sxs-lookup"><span data-stu-id="fb239-132">Calling `getDocument` will invalidate any previously valid nodeIds</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-133">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-133">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-134">色阶</span><span class="sxs-lookup"><span data-stu-id="fb239-134">depth</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="fb239-135">应检索子级的最大深度，默认值为2。</span><span class="sxs-lookup"><span data-stu-id="fb239-135">The maximum depth at which children should be retrieved, defaults to 2.</span></span> <span data-ttu-id="fb239-136">对整个子树使用-1。</span><span class="sxs-lookup"><span data-stu-id="fb239-136">Use -1 for entire subtree.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-137">pierce</span><span class="sxs-lookup"><span data-stu-id="fb239-137">pierce</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="fb239-138">在返回子树时是否应遍历 iframe （默认为 false）。</span><span class="sxs-lookup"><span data-stu-id="fb239-138">Whether or not iframes should be traversed when returning the subtree (default is false).</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-139">返回</span><span class="sxs-lookup"><span data-stu-id="fb239-139">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-140">根目录</span><span class="sxs-lookup"><span data-stu-id="fb239-140">root</span></span></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="fb239-141">生成的节点。</span><span class="sxs-lookup"><span data-stu-id="fb239-141">Resulting Node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-142">highlightNode</span><span class="sxs-lookup"><span data-stu-id="fb239-142">highlightNode</span></span>
<span data-ttu-id="fb239-143">具有给定 id 或对象包装的 Higlights DOM 节点。</span><span class="sxs-lookup"><span data-stu-id="fb239-143">Higlights DOM node with given id or object wrapper.</span></span> <span data-ttu-id="fb239-144">必须指定 backendNodeId 或 objectId。</span><span class="sxs-lookup"><span data-stu-id="fb239-144">nodeId, backendNodeId, or objectId must be specified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-145">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-145">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-146">a</span><span class="sxs-lookup"><span data-stu-id="fb239-146">nodeId</span></span> <br/> <i><span data-ttu-id="fb239-147">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-147">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-148">要突出显示的节点的标识符。</span><span class="sxs-lookup"><span data-stu-id="fb239-148">Identifier of the node to highlight.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-149">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="fb239-149">backendNodeId</span></span> <br/> <i><span data-ttu-id="fb239-150">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-150">optional</span></span></i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td><span data-ttu-id="fb239-151">要突出显示的后端节点的标识符。</span><span class="sxs-lookup"><span data-stu-id="fb239-151">Identifier of the backend node to highlight.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-152">objectId</span><span class="sxs-lookup"><span data-stu-id="fb239-152">objectId</span></span> <br/> <i><span data-ttu-id="fb239-153">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-153">optional</span></span></i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td><span data-ttu-id="fb239-154">要突出显示的节点的 JavaScript 对象 id。</span><span class="sxs-lookup"><span data-stu-id="fb239-154">JavaScript object id of the node to be highlighted.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-155">higlightConfig</span><span class="sxs-lookup"><span data-stu-id="fb239-155">higlightConfig</span></span></td>
            <td><a href="#highlightconfig"><code class="flyout">HighlightConfig</code></a></td>
            <td><span data-ttu-id="fb239-156">突出显示外观的描述符。</span><span class="sxs-lookup"><span data-stu-id="fb239-156">Descriptor of the highlight appearance.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-157">返回</span><span class="sxs-lookup"><span data-stu-id="fb239-157">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-158">根目录</span><span class="sxs-lookup"><span data-stu-id="fb239-158">root</span></span></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="fb239-159">生成的节点。</span><span class="sxs-lookup"><span data-stu-id="fb239-159">Resulting Node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-160">hideHighlight</span><span class="sxs-lookup"><span data-stu-id="fb239-160">hideHighlight</span></span>
<span data-ttu-id="fb239-161">隐藏任何当前 DOM 节点突出显示。</span><span class="sxs-lookup"><span data-stu-id="fb239-161">Hides any current DOM node highlight.</span></span>

</p>

---

### <span data-ttu-id="fb239-162">requestChildNodes</span><span class="sxs-lookup"><span data-stu-id="fb239-162">requestChildNodes</span></span>
<span data-ttu-id="fb239-163">请求以事件形式将具有给定 id 的节点的子级返回到 ghe 调用方 `setChildNodes` 。</span><span class="sxs-lookup"><span data-stu-id="fb239-163">Requests that children of the node with given id are returned to ghe caller in the form of `setChildNodes` events.</span></span> `setChildNodes` <span data-ttu-id="fb239-164">将针对每个尚未返回其子级的节点（从请求的节点向下到指定的深度）引发。</span><span class="sxs-lookup"><span data-stu-id="fb239-164">will be fired for each node that has not previously returned it's children, starting from the requested node down to the specified depth.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-165">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-165">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-166">a</span><span class="sxs-lookup"><span data-stu-id="fb239-166">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-167">要从中获取子级的节点的 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-167">Id of the node to get children from.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-168">色阶</span><span class="sxs-lookup"><span data-stu-id="fb239-168">depth</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="fb239-169">应检索子级的最大深度，默认值为1。</span><span class="sxs-lookup"><span data-stu-id="fb239-169">The maximum depth at which children should be retrieved, defaults to 1.</span></span> <span data-ttu-id="fb239-170">对整个子树使用-1。</span><span class="sxs-lookup"><span data-stu-id="fb239-170">Use -1 for entire subtree.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-171">pierce</span><span class="sxs-lookup"><span data-stu-id="fb239-171">pierce</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="fb239-172">在返回子树时是否应遍历 iframe （默认为 false）。</span><span class="sxs-lookup"><span data-stu-id="fb239-172">Whether or not iframes should be traversed when returning the subtree (default is false).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-173">getAttributes</span><span class="sxs-lookup"><span data-stu-id="fb239-173">getAttributes</span></span>
<span data-ttu-id="fb239-174">返回指定节点的属性。</span><span class="sxs-lookup"><span data-stu-id="fb239-174">Returns attributes for the specified node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-175">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-175">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-176">a</span><span class="sxs-lookup"><span data-stu-id="fb239-176">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-177">要为其检索 attibutes 的节点的 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-177">Id of the node to retrieve attibutes for.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-178">返回</span><span class="sxs-lookup"><span data-stu-id="fb239-178">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-179">attributes</span><span class="sxs-lookup"><span data-stu-id="fb239-179">attributes</span></span></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="fb239-180">节点属性名称和值的交错数组。</span><span class="sxs-lookup"><span data-stu-id="fb239-180">An interleaved array of node attribute names and values.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-181">getOuterHTML</span><span class="sxs-lookup"><span data-stu-id="fb239-181">getOuterHTML</span></span>
<span data-ttu-id="fb239-182">返回节点的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="fb239-182">Returns node's HTML markup.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-183">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-183">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-184">a</span><span class="sxs-lookup"><span data-stu-id="fb239-184">nodeId</span></span> <br/> <i><span data-ttu-id="fb239-185">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-185">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-186">节点的标识符。</span><span class="sxs-lookup"><span data-stu-id="fb239-186">Identifier of the node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-187">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="fb239-187">backendNodeId</span></span> <br/> <i><span data-ttu-id="fb239-188">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-188">optional</span></span></i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td><span data-ttu-id="fb239-189">后端节点的标识符。</span><span class="sxs-lookup"><span data-stu-id="fb239-189">Identifier of the backend node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-190">objectId</span><span class="sxs-lookup"><span data-stu-id="fb239-190">objectId</span></span> <br/> <i><span data-ttu-id="fb239-191">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-191">optional</span></span></i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td><span data-ttu-id="fb239-192">节点包装器的 JavaScript 对象 id。</span><span class="sxs-lookup"><span data-stu-id="fb239-192">JavaScript object id of the node wrapper.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-193">返回</span><span class="sxs-lookup"><span data-stu-id="fb239-193">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-194">outerHTML</span><span class="sxs-lookup"><span data-stu-id="fb239-194">outerHTML</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="fb239-195">外部 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="fb239-195">Outer HTML markup.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-196">pushNodesByBackendIdsToFrontend</span><span class="sxs-lookup"><span data-stu-id="fb239-196">pushNodesByBackendIdsToFrontend</span></span>
<span data-ttu-id="fb239-197">查找节点 Id 并解析指定后端节点 Id 的所有父级</span><span class="sxs-lookup"><span data-stu-id="fb239-197">Looks up Node Ids and resolves all parents for the specified Backend Node Ids</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-198">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-198">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-199">backendNodeIds</span><span class="sxs-lookup"><span data-stu-id="fb239-199">backendNodeIds</span></span></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId[]</code></a></td>
            <td><span data-ttu-id="fb239-200">要解析的节点的后端节点 Id</span><span class="sxs-lookup"><span data-stu-id="fb239-200">Backend Node IDs of the nodes to resolve</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-201">返回</span><span class="sxs-lookup"><span data-stu-id="fb239-201">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-202">nodeIds</span><span class="sxs-lookup"><span data-stu-id="fb239-202">nodeIds</span></span></td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td><span data-ttu-id="fb239-203">已解析节点的节点 Id</span><span class="sxs-lookup"><span data-stu-id="fb239-203">Node Ids of the resolved nodes</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-204">querySelector</span><span class="sxs-lookup"><span data-stu-id="fb239-204">querySelector</span></span>
<span data-ttu-id="fb239-205">`querySelector`在给定节点上执行。</span><span class="sxs-lookup"><span data-stu-id="fb239-205">Executes `querySelector` on a given node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-206">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-206">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-207">a</span><span class="sxs-lookup"><span data-stu-id="fb239-207">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-208">要查询的节点的 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-208">Id of the node to query upon.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-209">选取</span><span class="sxs-lookup"><span data-stu-id="fb239-209">selector</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="fb239-210">选择器字符串。</span><span class="sxs-lookup"><span data-stu-id="fb239-210">The selector string.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-211">返回</span><span class="sxs-lookup"><span data-stu-id="fb239-211">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-212">a</span><span class="sxs-lookup"><span data-stu-id="fb239-212">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-213">查询选择器结果。</span><span class="sxs-lookup"><span data-stu-id="fb239-213">Query selector result.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-214">querySelectorAll</span><span class="sxs-lookup"><span data-stu-id="fb239-214">querySelectorAll</span></span>
<span data-ttu-id="fb239-215">`querySelectorAll`在给定节点上执行。</span><span class="sxs-lookup"><span data-stu-id="fb239-215">Executes `querySelectorAll` on a given node.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-216">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-216">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-217">a</span><span class="sxs-lookup"><span data-stu-id="fb239-217">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-218">要查询的节点的 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-218">Id of the node to query upon.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-219">选取</span><span class="sxs-lookup"><span data-stu-id="fb239-219">selector</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="fb239-220">选择器字符串。</span><span class="sxs-lookup"><span data-stu-id="fb239-220">The selector string.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-221">返回</span><span class="sxs-lookup"><span data-stu-id="fb239-221">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-222">nodeIds</span><span class="sxs-lookup"><span data-stu-id="fb239-222">nodeIds</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td><span data-ttu-id="fb239-223">查询选择器结果。</span><span class="sxs-lookup"><span data-stu-id="fb239-223">Query selector results.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-224">requestNode</span><span class="sxs-lookup"><span data-stu-id="fb239-224">requestNode</span></span>
<span data-ttu-id="fb239-225">请求将具有给定远程对象 Id 的节点发送给调用方。</span><span class="sxs-lookup"><span data-stu-id="fb239-225">Requests that the node with given remote object Id is sent to caller.</span></span> <span data-ttu-id="fb239-226">从节点到根的路径组成的所有节点也作为一系列通知发送到客户端 `setChildNodes` 。</span><span class="sxs-lookup"><span data-stu-id="fb239-226">All nodes that form the path from the node to the root are also sent to the client as a series of `setChildNodes` notifications.</span></span> <span data-ttu-id="fb239-227">如果客户端之前尚未请求包含所请求的节点的文档，则返回0。</span><span class="sxs-lookup"><span data-stu-id="fb239-227">returns 0 if the document containing the requested node has not previously been requested by the client.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-228">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-228">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-229">objectId</span><span class="sxs-lookup"><span data-stu-id="fb239-229">objectId</span></span></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td><span data-ttu-id="fb239-230">要转换为节点的 JavaScript 对象 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-230">JavaScript object Id to convert into node.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-231">返回</span><span class="sxs-lookup"><span data-stu-id="fb239-231">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-232">a</span><span class="sxs-lookup"><span data-stu-id="fb239-232">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-233">给定对象的节点 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-233">Node Id for given object.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-234">resolveNode</span><span class="sxs-lookup"><span data-stu-id="fb239-234">resolveNode</span></span>
<span data-ttu-id="fb239-235">解析给定的 BackendNodeId 或的 JavaScript 节点对象。</span><span class="sxs-lookup"><span data-stu-id="fb239-235">Resolves the JavaScript node object for a given NodeId or BackendNodeId.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-236">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-236">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-237">a</span><span class="sxs-lookup"><span data-stu-id="fb239-237">nodeId</span></span> <br/> <i><span data-ttu-id="fb239-238">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-238">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-239">要解析的节点的 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-239">Id of the node to resolve.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-240">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="fb239-240">backendNodeId</span></span> <br/> <i><span data-ttu-id="fb239-241">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-241">optional</span></span></i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td><span data-ttu-id="fb239-242">要解析的节点的后端节点 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-242">Backend Node Id of the node to resolve.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-243">objectGroup</span><span class="sxs-lookup"><span data-stu-id="fb239-243">objectGroup</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="fb239-244">可用于释放多个对象的符号组名称。</span><span class="sxs-lookup"><span data-stu-id="fb239-244">Symbolic group name that can be used to release multiple objects.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-245">返回</span><span class="sxs-lookup"><span data-stu-id="fb239-245">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-246">object</span><span class="sxs-lookup"><span data-stu-id="fb239-246">object</span></span></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><span data-ttu-id="fb239-247">给定节点的 JavaScript 对象包装程序。</span><span class="sxs-lookup"><span data-stu-id="fb239-247">JavaScript object wrapper for given node.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-248">setInspectedNode</span><span class="sxs-lookup"><span data-stu-id="fb239-248">setInspectedNode</span></span>
<span><b><span data-ttu-id="fb239-249">实验.</span><span class="sxs-lookup"><span data-stu-id="fb239-249">Experimental.</span></span> </b></span><span data-ttu-id="fb239-250">使控制台能够通过 $0-$ 4 引用具有给定 id 的以前检查过的节点。</span><span class="sxs-lookup"><span data-stu-id="fb239-250">Enables console to refer to the previous inspected node with given id via $0-$4.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-251">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-251">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-252">a</span><span class="sxs-lookup"><span data-stu-id="fb239-252">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-253">可通过命令行 API 中的 $0-$ 4 访问的 DOM 节点 id。</span><span class="sxs-lookup"><span data-stu-id="fb239-253">DOM node id to be accessible by means of $0-$4 in command line API.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="fb239-254">事件</span><span class="sxs-lookup"><span data-stu-id="fb239-254">Events</span></span>

### <span data-ttu-id="fb239-255">setChildNodes</span><span class="sxs-lookup"><span data-stu-id="fb239-255">setChildNodes</span></span>
<span data-ttu-id="fb239-256">当后端希望提供缺少 DOM 结构的客户端时引发。</span><span class="sxs-lookup"><span data-stu-id="fb239-256">Fired when the backend wishes to provide client with missing DOM structure.</span></span> <span data-ttu-id="fb239-257">这会在大多数请求 nodeIds 的调用时发生</span><span class="sxs-lookup"><span data-stu-id="fb239-257">This happens upon most calls requesting nodeIds</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-258">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-258">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-259">parentId</span><span class="sxs-lookup"><span data-stu-id="fb239-259">parentId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-260">与子节点 poplate 的父节点。</span><span class="sxs-lookup"><span data-stu-id="fb239-260">Parent node to poplate with children.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-261">顶点</span><span class="sxs-lookup"><span data-stu-id="fb239-261">nodes</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td><span data-ttu-id="fb239-262">子节点数组。</span><span class="sxs-lookup"><span data-stu-id="fb239-262">Child nodes array.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-263">attributeModified</span><span class="sxs-lookup"><span data-stu-id="fb239-263">attributeModified</span></span>
<span data-ttu-id="fb239-264">在 `Element` 修改属性时激发。</span><span class="sxs-lookup"><span data-stu-id="fb239-264">Fired when `Element`'s attribute is modified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-265">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-265">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-266">a</span><span class="sxs-lookup"><span data-stu-id="fb239-266">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-267">已更改的节点的 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-267">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-268">name</span><span class="sxs-lookup"><span data-stu-id="fb239-268">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="fb239-269">属性名称。</span><span class="sxs-lookup"><span data-stu-id="fb239-269">Attribute name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-270">值</span><span class="sxs-lookup"><span data-stu-id="fb239-270">value</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="fb239-271">属性值。</span><span class="sxs-lookup"><span data-stu-id="fb239-271">Attribute value.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-272">attributeRemoved</span><span class="sxs-lookup"><span data-stu-id="fb239-272">attributeRemoved</span></span>
<span data-ttu-id="fb239-273">在 `Element` 删除其属性时激发。</span><span class="sxs-lookup"><span data-stu-id="fb239-273">Fired when `Element`'s attribute is removed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-274">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-274">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-275">a</span><span class="sxs-lookup"><span data-stu-id="fb239-275">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-276">已更改的节点的 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-276">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-277">name</span><span class="sxs-lookup"><span data-stu-id="fb239-277">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="fb239-278">属性名称。</span><span class="sxs-lookup"><span data-stu-id="fb239-278">Attribute name.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-279">characterDataModified</span><span class="sxs-lookup"><span data-stu-id="fb239-279">characterDataModified</span></span>
<span data-ttu-id="fb239-280">镜像 `DOMCharacterDataModified` 事件。</span><span class="sxs-lookup"><span data-stu-id="fb239-280">Mirrors `DOMCharacterDataModified` event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-281">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-281">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-282">a</span><span class="sxs-lookup"><span data-stu-id="fb239-282">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-283">已更改的节点的 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-283">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-284">charcterData</span><span class="sxs-lookup"><span data-stu-id="fb239-284">charcterData</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="fb239-285">新文本值。</span><span class="sxs-lookup"><span data-stu-id="fb239-285">New text value.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-286">childNodeInserted</span><span class="sxs-lookup"><span data-stu-id="fb239-286">childNodeInserted</span></span>
<span data-ttu-id="fb239-287">镜像 `DOMNodeInserted` 事件。</span><span class="sxs-lookup"><span data-stu-id="fb239-287">Mirrors `DOMNodeInserted` event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-288">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-288">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-289">parentNodeId</span><span class="sxs-lookup"><span data-stu-id="fb239-289">parentNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-290">已更改的节点的 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-290">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-291">previousNodeId</span><span class="sxs-lookup"><span data-stu-id="fb239-291">previousNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-292">插入的节点上一个同级的 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-292">Id of the inserted node's previous sibling.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-293">结点</span><span class="sxs-lookup"><span data-stu-id="fb239-293">node</span></span></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="fb239-294">已插入节点数据。</span><span class="sxs-lookup"><span data-stu-id="fb239-294">Inserted node data.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-295">childNodeRemoved</span><span class="sxs-lookup"><span data-stu-id="fb239-295">childNodeRemoved</span></span>
<span data-ttu-id="fb239-296">镜像 `DOMNodeRemoved` 事件。</span><span class="sxs-lookup"><span data-stu-id="fb239-296">Mirrors `DOMNodeRemoved` event.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-297">参数</span><span class="sxs-lookup"><span data-stu-id="fb239-297">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-298">parentNodeId</span><span class="sxs-lookup"><span data-stu-id="fb239-298">parentNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-299">已更改的节点的 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-299">Id of the node that has changed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-300">a</span><span class="sxs-lookup"><span data-stu-id="fb239-300">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-301">已删除的节点的 Id。</span><span class="sxs-lookup"><span data-stu-id="fb239-301">Id of the node that has been removed.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="fb239-302">documentUpdated</span><span class="sxs-lookup"><span data-stu-id="fb239-302">documentUpdated</span></span>
<span data-ttu-id="fb239-303">已 `Document` 完全更新时激发。</span><span class="sxs-lookup"><span data-stu-id="fb239-303">Fired when `Document` has been totally updated.</span></span> <span data-ttu-id="fb239-304">节点 id 已不再有效。</span><span class="sxs-lookup"><span data-stu-id="fb239-304">Node ids are no longer valid.</span></span>

</p>

---

## <span data-ttu-id="fb239-305">类型</span><span class="sxs-lookup"><span data-stu-id="fb239-305">Types</span></span>

### <a name="rgba"></a> <span data-ttu-id="fb239-306">RGBA</span><span class="sxs-lookup"><span data-stu-id="fb239-306">RGBA</span></span> `object`

<span data-ttu-id="fb239-307">保存 RGBA 颜色的结构。</span><span class="sxs-lookup"><span data-stu-id="fb239-307">A Structure holding an RGBA color.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-308">属性</span><span class="sxs-lookup"><span data-stu-id="fb239-308">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-309">研发</span><span class="sxs-lookup"><span data-stu-id="fb239-309">r</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="fb239-310">红色分量，位于 [0-255] 范围内。</span><span class="sxs-lookup"><span data-stu-id="fb239-310">The red component, in the [0-255] range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-311">7</span><span class="sxs-lookup"><span data-stu-id="fb239-311">g</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="fb239-312">绿色分量，位于 [0-255] 范围内。</span><span class="sxs-lookup"><span data-stu-id="fb239-312">The green component, in the [0-255] range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-313">a</span><span class="sxs-lookup"><span data-stu-id="fb239-313">b</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="fb239-314">蓝色分量，位于 [0-255] 范围内。</span><span class="sxs-lookup"><span data-stu-id="fb239-314">The blue component, in the [0-255] range.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-315">a</span><span class="sxs-lookup"><span data-stu-id="fb239-315">a</span></span> <br/> <i><span data-ttu-id="fb239-316">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-316">optional</span></span></i></td>
            <td><code class="flyout">number</code></td>
            <td><span data-ttu-id="fb239-317">Alpha 分量，位于 [0-1] 范围内。</span><span class="sxs-lookup"><span data-stu-id="fb239-317">The alpha component, in the [0-1] range.</span></span> <span data-ttu-id="fb239-318">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="fb239-318">Default is 1.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="highlightconfig"></a> <span data-ttu-id="fb239-319">HighlightConfig</span><span class="sxs-lookup"><span data-stu-id="fb239-319">HighlightConfig</span></span> `object`

<span data-ttu-id="fb239-320">用于突出显示页面元素的配置数据。</span><span class="sxs-lookup"><span data-stu-id="fb239-320">Configuration data for highlighting of page elements.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-321">属性</span><span class="sxs-lookup"><span data-stu-id="fb239-321">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-322">contentColor</span><span class="sxs-lookup"><span data-stu-id="fb239-322">contentColor</span></span> <br/> <i><span data-ttu-id="fb239-323">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-323">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="fb239-324">"内容" 框突出显示 "填充颜色"。</span><span class="sxs-lookup"><span data-stu-id="fb239-324">The content box highlight fill color.</span></span> <span data-ttu-id="fb239-325">默认值为透明。</span><span class="sxs-lookup"><span data-stu-id="fb239-325">Default is transparent.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-326">paddingColor</span><span class="sxs-lookup"><span data-stu-id="fb239-326">paddingColor</span></span> <br/> <i><span data-ttu-id="fb239-327">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-327">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="fb239-328">填充突出显示填充颜色。</span><span class="sxs-lookup"><span data-stu-id="fb239-328">The padding highlight fill color.</span></span> <span data-ttu-id="fb239-329">默认值为透明。</span><span class="sxs-lookup"><span data-stu-id="fb239-329">Default is transparent.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-330">颜色</span><span class="sxs-lookup"><span data-stu-id="fb239-330">borderColor</span></span> <br/> <i><span data-ttu-id="fb239-331">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-331">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="fb239-332">边框突出显示填充颜色。</span><span class="sxs-lookup"><span data-stu-id="fb239-332">The border highlight fill color.</span></span> <span data-ttu-id="fb239-333">默认值为透明。</span><span class="sxs-lookup"><span data-stu-id="fb239-333">Default is transparent.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-334">marginColor</span><span class="sxs-lookup"><span data-stu-id="fb239-334">marginColor</span></span> <br/> <i><span data-ttu-id="fb239-335">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-335">optional</span></span></i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td><span data-ttu-id="fb239-336">边距突出显示填充颜色。</span><span class="sxs-lookup"><span data-stu-id="fb239-336">The margin highlight fill color.</span></span> <span data-ttu-id="fb239-337">默认值为透明。</span><span class="sxs-lookup"><span data-stu-id="fb239-337">Default is transparent.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="nodeid"></a> <span data-ttu-id="fb239-338">A</span><span class="sxs-lookup"><span data-stu-id="fb239-338">NodeId</span></span> `integer`

<span data-ttu-id="fb239-339">唯一的 DOM 节点标识符</span><span class="sxs-lookup"><span data-stu-id="fb239-339">Unique DOM node identifier</span></span>

</p>

---

### <a name="node"></a> <span data-ttu-id="fb239-340">结点</span><span class="sxs-lookup"><span data-stu-id="fb239-340">Node</span></span> `object`

<span data-ttu-id="fb239-341">表示实际 DOM 节点的 Mirror 对象。</span><span class="sxs-lookup"><span data-stu-id="fb239-341">Mirror object that represents the actual DOM nodes.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="fb239-342">属性</span><span class="sxs-lookup"><span data-stu-id="fb239-342">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="fb239-343">a</span><span class="sxs-lookup"><span data-stu-id="fb239-343">nodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-344">用于引用此节点的节点标识符。</span><span class="sxs-lookup"><span data-stu-id="fb239-344">Node Identifier used to reference this node.</span></span> <span data-ttu-id="fb239-345">后端将为具有客户端已知的节点名的节点引发 DOM 事件。</span><span class="sxs-lookup"><span data-stu-id="fb239-345">Backend will fire DOM events for nodes that have a nodeId that is known to the client</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-346">parentId</span><span class="sxs-lookup"><span data-stu-id="fb239-346">parentId</span></span> <br/> <i><span data-ttu-id="fb239-347">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-347">optional</span></span></i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-348">父节点的节点标识符（如果有）。</span><span class="sxs-lookup"><span data-stu-id="fb239-348">Node Identifier of the parent Node, if any.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-349">backendNodeId</span><span class="sxs-lookup"><span data-stu-id="fb239-349">backendNodeId</span></span></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td><span data-ttu-id="fb239-350">节点的后端节点标识符。</span><span class="sxs-lookup"><span data-stu-id="fb239-350">Backend Node identifier of the node.</span></span> <span data-ttu-id="fb239-351">BackendNodeIds 引用可供客户端识别的节点，但不推送有关此节点的 DOM 事件。</span><span class="sxs-lookup"><span data-stu-id="fb239-351">BackendNodeIds reference Nodes that can be known to the client, but do not push DOM events about this node.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-352">nodeType</span><span class="sxs-lookup"><span data-stu-id="fb239-352">nodeType</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td>`Node`<span data-ttu-id="fb239-353">的 nodeType。</span><span class="sxs-lookup"><span data-stu-id="fb239-353">'s nodeType.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-354">nodeName</span><span class="sxs-lookup"><span data-stu-id="fb239-354">nodeName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td>`Node`<span data-ttu-id="fb239-355">的 nodeName。</span><span class="sxs-lookup"><span data-stu-id="fb239-355">'s nodeName.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-356">localName</span><span class="sxs-lookup"><span data-stu-id="fb239-356">localName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td>`Node`<span data-ttu-id="fb239-357">的 localName</span><span class="sxs-lookup"><span data-stu-id="fb239-357">'s localName</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-358">nodeValue</span><span class="sxs-lookup"><span data-stu-id="fb239-358">nodeValue</span></span></td>
            <td><code class="flyout">string</code></td>
            <td>`Node`<span data-ttu-id="fb239-359">的 nodeValue</span><span class="sxs-lookup"><span data-stu-id="fb239-359">'s nodeValue</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-360">childNodeCount</span><span class="sxs-lookup"><span data-stu-id="fb239-360">childNodeCount</span></span> <br/> <i><span data-ttu-id="fb239-361">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-361">optional</span></span></i></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="fb239-362">节点的子计数 `Container` 。</span><span class="sxs-lookup"><span data-stu-id="fb239-362">Child count for `Container` nodes.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-363">儿童</span><span class="sxs-lookup"><span data-stu-id="fb239-363">children</span></span> <br/> <i><span data-ttu-id="fb239-364">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-364">optional</span></span></i></td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td><span data-ttu-id="fb239-365">当请求子节点时，此节点的子节点。</span><span class="sxs-lookup"><span data-stu-id="fb239-365">Child nodes of this node when requested with children.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-366">attributes</span><span class="sxs-lookup"><span data-stu-id="fb239-366">attributes</span></span> <br/> <i><span data-ttu-id="fb239-367">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-367">optional</span></span></i></td>
            <td><code class="flyout">string[]</code></td>
            <td><span data-ttu-id="fb239-368">`Element`平面数组 "[name1，value1，name2，value2]" 形式的节点属性</span><span class="sxs-lookup"><span data-stu-id="fb239-368">Attributes of `Element` nodes in the form of a flat array \`[name1, value1, name2, value2]</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-369">documentURL</span><span class="sxs-lookup"><span data-stu-id="fb239-369">documentURL</span></span> <br/> <i><span data-ttu-id="fb239-370">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-370">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="fb239-371">节点指向的文档 URL `Document` 。</span><span class="sxs-lookup"><span data-stu-id="fb239-371">Document URL that `Document` nodes point to.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-372">baseURL</span><span class="sxs-lookup"><span data-stu-id="fb239-372">baseURL</span></span> <br/> <i><span data-ttu-id="fb239-373">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-373">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="fb239-374">`Document`节点用于完成 URL 完成的文档 URL。</span><span class="sxs-lookup"><span data-stu-id="fb239-374">Document URL that `Document` nodes use for URL completion.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-375">publicId</span><span class="sxs-lookup"><span data-stu-id="fb239-375">publicId</span></span> <br/> <i><span data-ttu-id="fb239-376">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-376">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` <span data-ttu-id="fb239-377">节点的 publicId。</span><span class="sxs-lookup"><span data-stu-id="fb239-377">Node's publicId.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-378">systemId</span><span class="sxs-lookup"><span data-stu-id="fb239-378">systemId</span></span> <br/> <i><span data-ttu-id="fb239-379">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-379">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` <span data-ttu-id="fb239-380">节点的 systemId。</span><span class="sxs-lookup"><span data-stu-id="fb239-380">Node's systemId.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-381">internalSubset</span><span class="sxs-lookup"><span data-stu-id="fb239-381">internalSubset</span></span> <br/> <i><span data-ttu-id="fb239-382">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-382">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` <span data-ttu-id="fb239-383">节点的 internalSubset。</span><span class="sxs-lookup"><span data-stu-id="fb239-383">Node's internalSubset.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-384">xmlVersion</span><span class="sxs-lookup"><span data-stu-id="fb239-384">xmlVersion</span></span> <br/> <i><span data-ttu-id="fb239-385">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-385">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`Document` <span data-ttu-id="fb239-386">XML 文档情况下节点的 xml 版本。</span><span class="sxs-lookup"><span data-stu-id="fb239-386">Node's xml version in the case of XML documents.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-387">name</span><span class="sxs-lookup"><span data-stu-id="fb239-387">name</span></span> <br/> <i><span data-ttu-id="fb239-388">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-388">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` <span data-ttu-id="fb239-389">节点名称。</span><span class="sxs-lookup"><span data-stu-id="fb239-389">Node's name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-390">值</span><span class="sxs-lookup"><span data-stu-id="fb239-390">value</span></span> <br/> <i><span data-ttu-id="fb239-391">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-391">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` <span data-ttu-id="fb239-392">节点值。</span><span class="sxs-lookup"><span data-stu-id="fb239-392">Node's value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-393">frameId</span><span class="sxs-lookup"><span data-stu-id="fb239-393">frameId</span></span> <br/> <i><span data-ttu-id="fb239-394">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-394">optional</span></span></i></td>
            <td><a href="page.md#frameid"><code class="flyout">Page.FrameId</code></a></td>
            <td><span data-ttu-id="fb239-395">帧所有者元素的帧 ID。</span><span class="sxs-lookup"><span data-stu-id="fb239-395">Frame ID for frame owner elements.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-396">contentDocument</span><span class="sxs-lookup"><span data-stu-id="fb239-396">contentDocument</span></span> <br/> <i><span data-ttu-id="fb239-397">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-397">optional</span></span></i></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td><span data-ttu-id="fb239-398">框架所有者元素的内容文档。</span><span class="sxs-lookup"><span data-stu-id="fb239-398">Content document for frame owner elements.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="fb239-399">isSVG</span><span class="sxs-lookup"><span data-stu-id="fb239-399">isSVG</span></span> <br/> <i><span data-ttu-id="fb239-400">可选</span><span class="sxs-lookup"><span data-stu-id="fb239-400">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="fb239-401">如果节点为 SVG，则为 True。</span><span class="sxs-lookup"><span data-stu-id="fb239-401">True if the node is SVG.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="backendnodeid"></a> <span data-ttu-id="fb239-402">BackendNodeId</span><span class="sxs-lookup"><span data-stu-id="fb239-402">BackendNodeId</span></span> `integer`

<span data-ttu-id="fb239-403">唯一的 DOM 节点标识符，用于引用可能尚未推送到前端的节点。</span><span class="sxs-lookup"><span data-stu-id="fb239-403">Unique DOM node identifier used to reference a node that may not have been pushed to the front-end.</span></span>

</p>

---

### <a name="pseudotype"></a> <span data-ttu-id="fb239-404">PseudoType</span><span class="sxs-lookup"><span data-stu-id="fb239-404">PseudoType</span></span> `string`

<span data-ttu-id="fb239-405">伪元素类型。</span><span class="sxs-lookup"><span data-stu-id="fb239-405">Pseudo element type.</span></span>

##### <span data-ttu-id="fb239-406">允许值</span><span class="sxs-lookup"><span data-stu-id="fb239-406">Allowed Values</span></span>
<span data-ttu-id="fb239-407">第一行、首字母、之前、之后、所选内容</span><span class="sxs-lookup"><span data-stu-id="fb239-407">first-line, first-letter, before, after, selection</span></span>
</p>

---

## <span data-ttu-id="fb239-408">依赖关系</span><span class="sxs-lookup"><span data-stu-id="fb239-408">Dependencies</span></span>

[<span data-ttu-id="fb239-409">运行时</span><span class="sxs-lookup"><span data-stu-id="fb239-409">Runtime</span></span>](runtime.md)