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
# DOM
此域公开了 DOM 读/写操作。 每个 DOM 节点都由其镜像对象表示，其镜像对象具有 `id` 。 这 `id` 可用于获取有关节点的其他信息、将其解析为 JavaScript 对象包装等。客户只能接收客户端已知节点的 DOM 事件，这一点非常重要。 后端将跟踪已发送到客户端的节点，并且不会两次发送相同的节点。 客户负责收集有关已发送到客户端的节点的信息。<p>请注意， `iframe` 所有者元素将返回对应的文档元素作为其子节点。</p>

| | |
|-|-|
| [**方法**](#methods) | [enable](#enable)、 [disable](#disable)、 [getDocument](#getdocument)、 [highlightNode](#highlightnode)、 [hideHighlight](#hidehighlight)、 [requestChildNodes](#requestchildnodes)、 [getAttributes](#getattributes)、 [getOuterHTML](#getouterhtml)、 [pushNodesByBackendIdsToFrontend](#pushnodesbybackendidstofrontend)、 [querySelector](#queryselector)、 [querySelectorAll、](#queryselectorall)requestNode、 [resolveNode](#resolvenode)、setInspectedNode、 [、](#requestnode)、 [、](#setinspectednode) |
| [**事件**](#events) | [setChildNodes](#setchildnodes)、 [attributeModified](#attributemodified)、 [attributeRemoved](#attributeremoved)、 [characterDataModified](#characterdatamodified)、 [childNodeInserted](#childnodeinserted)、 [childNodeRemoved](#childnoderemoved)、 [documentUpdated](#documentupdated) |
| [**类型**](#types) | [RGBA](#rgba)、 [HighlightConfig](#highlightconfig)、 [NodeId](#nodeid)[节点](#node)、 [BackendNodeId](#backendnodeid)、 [PseudoType](#pseudotype) |
| [**依赖关系**](#dependencies) | [运行时](runtime.md) |
## 方法

### “启用”
为给定页面启用 DOM 代理。

</p>

---

### “禁用”
为给定页面禁用 DOM 代理。 禁用 DOM 将使以前任何有效的 nodeIds 无效。

</p>

---

### getDocument
返回调用方的根 DOM 节点（也可以选择子树）。 通话 `getDocument` 将使以前任何有效的 nodeIds 失效

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>色阶</td>
            <td><code class="flyout">integer</code></td>
            <td>应检索子级的最大深度，默认值为2。 对整个子树使用-1。</td>
        </tr>
        <tr>
            <td>pierce</td>
            <td><code class="flyout">boolean</code></td>
            <td>在返回子树时是否应遍历 iframe （默认为 false）。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>根目录</td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>生成的节点。</td>
        </tr>
    </tbody>
</table>
</p>

---

### highlightNode
具有给定 id 或对象包装的 Higlights DOM 节点。 必须指定 backendNodeId 或 objectId。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a <br/> <i>可选</i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>要突出显示的节点的标识符。</td>
        </tr>
        <tr>
            <td>backendNodeId <br/> <i>可选</i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td>要突出显示的后端节点的标识符。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>可选</i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td>要突出显示的节点的 JavaScript 对象 id。</td>
        </tr>
        <tr>
            <td>higlightConfig</td>
            <td><a href="#highlightconfig"><code class="flyout">HighlightConfig</code></a></td>
            <td>突出显示外观的描述符。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>根目录</td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>生成的节点。</td>
        </tr>
    </tbody>
</table>
</p>

---

### hideHighlight
隐藏任何当前 DOM 节点突出显示。

</p>

---

### requestChildNodes
请求以事件形式将具有给定 id 的节点的子级返回到 ghe 调用方 `setChildNodes` 。 `setChildNodes` 将针对每个尚未返回其子级的节点（从请求的节点向下到指定的深度）引发。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>要从中获取子级的节点的 Id。</td>
        </tr>
        <tr>
            <td>色阶</td>
            <td><code class="flyout">integer</code></td>
            <td>应检索子级的最大深度，默认值为1。 对整个子树使用-1。</td>
        </tr>
        <tr>
            <td>pierce</td>
            <td><code class="flyout">boolean</code></td>
            <td>在返回子树时是否应遍历 iframe （默认为 false）。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getAttributes
返回指定节点的属性。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>要为其检索 attibutes 的节点的 Id。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>attributes</td>
            <td><code class="flyout">string[]</code></td>
            <td>节点属性名称和值的交错数组。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getOuterHTML
返回节点的 HTML 标记。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a <br/> <i>可选</i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>节点的标识符。</td>
        </tr>
        <tr>
            <td>backendNodeId <br/> <i>可选</i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td>后端节点的标识符。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>可选</i></td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td>节点包装器的 JavaScript 对象 id。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>outerHTML</td>
            <td><code class="flyout">string</code></td>
            <td>外部 HTML 标记。</td>
        </tr>
    </tbody>
</table>
</p>

---

### pushNodesByBackendIdsToFrontend
查找节点 Id 并解析指定后端节点 Id 的所有父级

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>backendNodeIds</td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId[]</code></a></td>
            <td>要解析的节点的后端节点 Id</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>nodeIds</td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td>已解析节点的节点 Id</td>
        </tr>
    </tbody>
</table>
</p>

---

### querySelector
`querySelector`在给定节点上执行。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>要查询的节点的 Id。</td>
        </tr>
        <tr>
            <td>选取</td>
            <td><code class="flyout">string</code></td>
            <td>选择器字符串。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>查询选择器结果。</td>
        </tr>
    </tbody>
</table>
</p>

---

### querySelectorAll
`querySelectorAll`在给定节点上执行。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>要查询的节点的 Id。</td>
        </tr>
        <tr>
            <td>选取</td>
            <td><code class="flyout">string</code></td>
            <td>选择器字符串。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>nodeIds</td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td>查询选择器结果。</td>
        </tr>
    </tbody>
</table>
</p>

---

### requestNode
请求将具有给定远程对象 Id 的节点发送给调用方。 从节点到根的路径组成的所有节点也作为一系列通知发送到客户端 `setChildNodes` 。 如果客户端之前尚未请求包含所请求的节点的文档，则返回0。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>objectId</td>
            <td><a href="runtime.md#remoteobjectid"><code class="flyout">Runtime.RemoteObjectId</code></a></td>
            <td>要转换为节点的 JavaScript 对象 Id。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>给定对象的节点 Id。</td>
        </tr>
    </tbody>
</table>
</p>

---

### resolveNode
解析给定的 BackendNodeId 或的 JavaScript 节点对象。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a <br/> <i>可选</i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>要解析的节点的 Id。</td>
        </tr>
        <tr>
            <td>backendNodeId <br/> <i>可选</i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td>要解析的节点的后端节点 Id。</td>
        </tr>
        <tr>
            <td>objectGroup</td>
            <td><code class="flyout">string</code></td>
            <td>可用于释放多个对象的符号组名称。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>object</td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>给定节点的 JavaScript 对象包装程序。</td>
        </tr>
    </tbody>
</table>
</p>

---

### setInspectedNode
<span><b>实验. </b></span>使控制台能够通过 $0-$ 4 引用具有给定 id 的以前检查过的节点。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>可通过命令行 API 中的 $0-$ 4 访问的 DOM 节点 id。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 事件

### setChildNodes
当后端希望提供缺少 DOM 结构的客户端时引发。 这会在大多数请求 nodeIds 的调用时发生

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>parentId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>与子节点 poplate 的父节点。</td>
        </tr>
        <tr>
            <td>顶点</td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td>子节点数组。</td>
        </tr>
    </tbody>
</table>
</p>

---

### attributeModified
在 `Element` 修改属性时激发。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>已更改的节点的 Id。</td>
        </tr>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>属性名称。</td>
        </tr>
        <tr>
            <td>值</td>
            <td><code class="flyout">string</code></td>
            <td>属性值。</td>
        </tr>
    </tbody>
</table>
</p>

---

### attributeRemoved
在 `Element` 删除其属性时激发。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>已更改的节点的 Id。</td>
        </tr>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>属性名称。</td>
        </tr>
    </tbody>
</table>
</p>

---

### characterDataModified
镜像 `DOMCharacterDataModified` 事件。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>已更改的节点的 Id。</td>
        </tr>
        <tr>
            <td>charcterData</td>
            <td><code class="flyout">string</code></td>
            <td>新文本值。</td>
        </tr>
    </tbody>
</table>
</p>

---

### childNodeInserted
镜像 `DOMNodeInserted` 事件。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>parentNodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>已更改的节点的 Id。</td>
        </tr>
        <tr>
            <td>previousNodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>插入的节点上一个同级的 Id。</td>
        </tr>
        <tr>
            <td>结点</td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>已插入节点数据。</td>
        </tr>
    </tbody>
</table>
</p>

---

### childNodeRemoved
镜像 `DOMNodeRemoved` 事件。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>parentNodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>已更改的节点的 Id。</td>
        </tr>
        <tr>
            <td>a</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>已删除的节点的 Id。</td>
        </tr>
    </tbody>
</table>
</p>

---

### documentUpdated
已 `Document` 完全更新时激发。 节点 id 已不再有效。

</p>

---

## 类型

### <a name="rgba"></a> RGBA `object`

保存 RGBA 颜色的结构。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>研发</td>
            <td><code class="flyout">integer</code></td>
            <td>红色分量，位于 [0-255] 范围内。</td>
        </tr>
        <tr>
            <td>7</td>
            <td><code class="flyout">integer</code></td>
            <td>绿色分量，位于 [0-255] 范围内。</td>
        </tr>
        <tr>
            <td>a</td>
            <td><code class="flyout">integer</code></td>
            <td>蓝色分量，位于 [0-255] 范围内。</td>
        </tr>
        <tr>
            <td>a <br/> <i>可选</i></td>
            <td><code class="flyout">number</code></td>
            <td>Alpha 分量，位于 [0-1] 范围内。 默认值为 1。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="highlightconfig"></a> HighlightConfig `object`

用于突出显示页面元素的配置数据。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>contentColor <br/> <i>可选</i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td>"内容" 框突出显示 "填充颜色"。 默认值为透明。</td>
        </tr>
        <tr>
            <td>paddingColor <br/> <i>可选</i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td>填充突出显示填充颜色。 默认值为透明。</td>
        </tr>
        <tr>
            <td>颜色 <br/> <i>可选</i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td>边框突出显示填充颜色。 默认值为透明。</td>
        </tr>
        <tr>
            <td>marginColor <br/> <i>可选</i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td>边距突出显示填充颜色。 默认值为透明。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="nodeid"></a> A `integer`

唯一的 DOM 节点标识符

</p>

---

### <a name="node"></a> 结点 `object`

表示实际 DOM 节点的 Mirror 对象。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>用于引用此节点的节点标识符。 后端将为具有客户端已知的节点名的节点引发 DOM 事件。</td>
        </tr>
        <tr>
            <td>parentId <br/> <i>可选</i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>父节点的节点标识符（如果有）。</td>
        </tr>
        <tr>
            <td>backendNodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>节点的后端节点标识符。 BackendNodeIds 引用可供客户端识别的节点，但不推送有关此节点的 DOM 事件。</td>
        </tr>
        <tr>
            <td>nodeType</td>
            <td><code class="flyout">integer</code></td>
            <td>`Node`的 nodeType。</td>
        </tr>
        <tr>
            <td>nodeName</td>
            <td><code class="flyout">string</code></td>
            <td>`Node`的 nodeName。</td>
        </tr>
        <tr>
            <td>localName</td>
            <td><code class="flyout">string</code></td>
            <td>`Node`的 localName</td>
        </tr>
        <tr>
            <td>nodeValue</td>
            <td><code class="flyout">string</code></td>
            <td>`Node`的 nodeValue</td>
        </tr>
        <tr>
            <td>childNodeCount <br/> <i>可选</i></td>
            <td><code class="flyout">integer</code></td>
            <td>节点的子计数 `Container` 。</td>
        </tr>
        <tr>
            <td>儿童 <br/> <i>可选</i></td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td>当请求子节点时，此节点的子节点。</td>
        </tr>
        <tr>
            <td>attributes <br/> <i>可选</i></td>
            <td><code class="flyout">string[]</code></td>
            <td>`Element`平面数组 "[name1，value1，name2，value2]" 形式的节点属性</td>
        </tr>
        <tr>
            <td>documentURL <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>节点指向的文档 URL `Document` 。</td>
        </tr>
        <tr>
            <td>baseURL <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>`Document`节点用于完成 URL 完成的文档 URL。</td>
        </tr>
        <tr>
            <td>publicId <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` 节点的 publicId。</td>
        </tr>
        <tr>
            <td>systemId <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` 节点的 systemId。</td>
        </tr>
        <tr>
            <td>internalSubset <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>`DocumentType` 节点的 internalSubset。</td>
        </tr>
        <tr>
            <td>xmlVersion <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>`Document` XML 文档情况下节点的 xml 版本。</td>
        </tr>
        <tr>
            <td>name <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` 节点名称。</td>
        </tr>
        <tr>
            <td>值 <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` 节点值。</td>
        </tr>
        <tr>
            <td>frameId <br/> <i>可选</i></td>
            <td><a href="page.md#frameid"><code class="flyout">Page.FrameId</code></a></td>
            <td>帧所有者元素的帧 ID。</td>
        </tr>
        <tr>
            <td>contentDocument <br/> <i>可选</i></td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>框架所有者元素的内容文档。</td>
        </tr>
        <tr>
            <td>isSVG <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>如果节点为 SVG，则为 True。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="backendnodeid"></a> BackendNodeId `integer`

唯一的 DOM 节点标识符，用于引用可能尚未推送到前端的节点。

</p>

---

### <a name="pseudotype"></a> PseudoType `string`

伪元素类型。

##### 允许值
第一行、首字母、之前、之后、所选内容
</p>

---

## 依赖关系

[运行时](runtime.md)