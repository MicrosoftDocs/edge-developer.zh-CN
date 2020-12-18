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
# DOM

此域公开 DOM 读/写操作。 每个 DOM 节点都用其镜像对象表示，该对象具有一个 `id` 。 这可用于获取有关节点的其他信息、将节点解析 `id` 为 JavaScript 对象包装器等。客户端仅接收客户端已知的节点的 DOM 事件很重要。 后端跟踪发送到客户端的节点，从不发送同一节点两次。 客户端负责收集有关发送到客户端的节点的信息。<p>请注意， `iframe` 所有者元素将返回相应的文档元素作为其子节点。</p>

| | |
|-|-|
| [**方法**](#methods) | [enable](#enable)， [disable](#disable)， [getDocument](#getdocument)， [highlightNode](#highlightnode)， [hideHighlight](#hidehighlight)， [requestChildNodes](#requestchildnodes)， [getAttributes，](#getattributes) [getOuterHTML](#getouterhtml)， [pushNodesByBackendIdsToFrontend](#pushnodesbybackendidstofrontend)， [querySelector](#queryselector)， [querySelectorAll](#queryselectorall)， [requestNode ， resolveNode](#requestnode)， [setInspectedNode](#setinspectednode) [](#resolvenode) |
| [**事件**](#events) | [setChildNodes](#setchildnodes)， [attributeModified](#attributemodified)， [attributeRemoved](#attributeremoved)， [characterDataModified](#characterdatamodified)， [childNodeInserted](#childnodeinserted)， [childNodeRemoved](#childnoderemoved)， [documentUpdated](#documentupdated) |
| [**类型**](#types) | [RGBA](#rgba)， [HighlightConfig](#highlightconfig)， [NodeId](#nodeid)， [Node](#node)， [BackendNodeId](#backendnodeid)， [PseudoType](#pseudotype) |
| [**依赖关系**](#dependencies) | [运行时](runtime.md) |
## 方法

### “启用”
为给定页面启用 DOM 代理。

</p>

---

### “禁用”
禁用给定页面的 DOM 代理。 禁用 DOM 将使任何以前有效的 nodeId 失效。

</p>

---

### getDocument
返回根 DOM 节点 (（可选）将子树) 调用方。 调用 `getDocument` 将使任何以前有效的 nodeId 无效

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
            <td>depth</td>
            <td><code class="flyout">integer</code></td>
            <td>应检索子级的最大深度（默认为 2）。 将 -1 用于整个子树。</td>
        </tr>
        <tr>
            <td>一些</td>
            <td><code class="flyout">boolean</code></td>
            <td>返回子树时是否应该遍历 iframe，默认值 (为 false) 。</td>
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
            <td>root</td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>生成的节点。</td>
        </tr>
    </tbody>
</table>
</p>

---

### highlightNode
具有给定 ID 或对象包装的 Higlights DOM 节点。 必须指定 nodeId、backendNodeId 或 objectId。

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
            <td>nodeId <br/> <i>可选</i></td>
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
            <td>要突出显示的节点的 JavaScript 对象 ID。</td>
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
            <td>root</td>
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
请求将具有给定 ID 的节点的子级以事件形式返回给呼叫 `setChildNodes` 者。 `setChildNodes` 将针对之前未返回其子级的每个节点（从请求的节点向下到指定深度）触发。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>要获取其子节点的 ID。</td>
        </tr>
        <tr>
            <td>depth</td>
            <td><code class="flyout">integer</code></td>
            <td>应检索子级的最大深度，默认为 1。 将 -1 用于整个子树。</td>
        </tr>
        <tr>
            <td>一些</td>
            <td><code class="flyout">boolean</code></td>
            <td>返回子树时是否应该遍历 iframe，默认值 (为 false) 。</td>
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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>要检索其属性的节点的 ID。</td>
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
            <td>nodeId <br/> <i>可选</i></td>
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
            <td>节点包装的 JavaScript 对象 ID。</td>
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
查找节点 ID 并解析指定后端节点 ID 的所有父节点

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
            <td>要解析的节点的后端节点 ID</td>
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
            <td>已解析节点的节点 ID</td>
        </tr>
    </tbody>
</table>
</p>

---

### querySelector
在 `querySelector` 给定节点上执行。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>要查询的节点的 ID。</td>
        </tr>
        <tr>
            <td>选择器</td>
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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>查询选择器结果。</td>
        </tr>
    </tbody>
</table>
</p>

---

### querySelectorAll
在 `querySelectorAll` 给定节点上执行。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>要查询的节点的 ID。</td>
        </tr>
        <tr>
            <td>选择器</td>
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
请求将具有给定远程对象 ID 的节点发送给调用方。 构成从节点到根的路径的所有节点也会作为一系列通知发送到 `setChildNodes` 客户端。 如果包含请求的节点的文档之前尚未由客户端请求，则返回 0。

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
            <td>要转换为节点的 JavaScript 对象 ID。</td>
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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>给定对象的节点 ID。</td>
        </tr>
    </tbody>
</table>
</p>

---

### resolveNode
解析给定 NodeId 或 BackendNodeId 的 JavaScript 节点对象。

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
            <td>nodeId <br/> <i>可选</i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>要解析的节点的 ID。</td>
        </tr>
        <tr>
            <td>backendNodeId <br/> <i>可选</i></td>
            <td><a href="#backendnodeid"><code class="flyout">BackendNodeId</code></a></td>
            <td>要解析的节点的后端节点 ID。</td>
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
            <td>给定节点的 JavaScript 对象包装。</td>
        </tr>
    </tbody>
</table>
</p>

---

### setInspectedNode
<span><b>实验。 </b></span>允许控制台通过 $0-$4 引用具有给定 ID 的上一个已检查节点。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>可通过命令行 API 中的 $0-$4 访问 DOM 节点 ID。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 事件

### setChildNodes
当后端希望向客户端提供缺少 DOM 结构时触发。 大多数请求 nodeIds 的调用时发生此情况

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
            <td>要弹出带子元素的父节点。</td>
        </tr>
        <tr>
            <td>节点</td>
            <td><a href="#nodeid"><code class="flyout">NodeId[]</code></a></td>
            <td>子节点数组。</td>
        </tr>
    </tbody>
</table>
</p>

---

### attributeModified
修改 `Element` 's 属性时触发。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>已更改的节点的 ID。</td>
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
删除 `Element` 's 属性时触发。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>已更改的节点的 ID。</td>
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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>已更改的节点的 ID。</td>
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
            <td>已更改的节点的 ID。</td>
        </tr>
        <tr>
            <td>previousNodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>插入的节点的上一同级节点的 ID。</td>
        </tr>
        <tr>
            <td>node</td>
            <td><a href="#node"><code class="flyout">Node</code></a></td>
            <td>插入的节点数据。</td>
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
            <td>已更改的节点的 ID。</td>
        </tr>
        <tr>
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>已删除的节点的 ID。</td>
        </tr>
    </tbody>
</table>
</p>

---

### documentUpdated
在 `Document` 完全更新时触发。 节点 ID 不再有效。

</p>

---

## 类型

### <a name="rgba"></a> RGBA `object`

一种保持 RGBA 颜色的结构。

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
            <td>r</td>
            <td><code class="flyout">integer</code></td>
            <td>红色分量，在 [0-255] 范围内。</td>
        </tr>
        <tr>
            <td>g</td>
            <td><code class="flyout">integer</code></td>
            <td>绿色分量，在 [0-255] 范围内。</td>
        </tr>
        <tr>
            <td>b</td>
            <td><code class="flyout">integer</code></td>
            <td>[0-255] 范围中的蓝色分量。</td>
        </tr>
        <tr>
            <td>a <br/> <i>可选</i></td>
            <td><code class="flyout">number</code></td>
            <td>alpha 分量，在 [0-1] 范围内。 默认值为 1。</td>
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
            <td>内容框突出显示填充颜色。 默认值为透明。</td>
        </tr>
        <tr>
            <td>paddingColor <br/> <i>可选</i></td>
            <td><a href="#rgba"><code class="flyout">RGBA</code></a></td>
            <td>填充突出显示填充颜色。 默认值为透明。</td>
        </tr>
        <tr>
            <td>borderColor <br/> <i>可选</i></td>
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

### <a name="nodeid"></a> NodeId `integer`

唯一 DOM 节点标识符

</p>

---

### <a name="node"></a> 节点 `object`

表示实际 DOM 节点的镜像对象。

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
            <td>nodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>用于引用此节点的节点标识符。 后端将为具有客户端已知的 nodeId 的节点启动 DOM 事件</td>
        </tr>
        <tr>
            <td>parentId <br/> <i>可选</i></td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>父节点的节点标识符（如果有）。</td>
        </tr>
        <tr>
            <td>backendNodeId</td>
            <td><a href="#nodeid"><code class="flyout">NodeId</code></a></td>
            <td>节点的后端节点标识符。 BackendNodeIds 引用客户端已知的节点，但不推送有关此节点的 DOM 事件。</td>
        </tr>
        <tr>
            <td>nodeType</td>
            <td><code class="flyout">integer</code></td>
            <td>`Node`'s nodeType。</td>
        </tr>
        <tr>
            <td>nodeName</td>
            <td><code class="flyout">string</code></td>
            <td>`Node`'s nodeName.</td>
        </tr>
        <tr>
            <td>localName</td>
            <td><code class="flyout">string</code></td>
            <td>`Node`'s localName</td>
        </tr>
        <tr>
            <td>nodeValue</td>
            <td><code class="flyout">string</code></td>
            <td>`Node`'s nodeValue</td>
        </tr>
        <tr>
            <td>childNodeCount <br/> <i>可选</i></td>
            <td><code class="flyout">integer</code></td>
            <td>节点的子 `Container` 计数。</td>
        </tr>
        <tr>
            <td>儿童 <br/> <i>可选</i></td>
            <td><a href="#node"><code class="flyout">Node[]</code></a></td>
            <td>具有子级时请求此节点的子节点。</td>
        </tr>
        <tr>
            <td>attributes <br/> <i>可选</i></td>
            <td><code class="flyout">string[]</code></td>
            <td>平面数组 `Element` "[name1， value1， name2， value2] 形式的节点属性</td>
        </tr>
        <tr>
            <td>documentURL <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>节点指向 `Document` 的文档 URL。</td>
        </tr>
        <tr>
            <td>baseURL <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>节点用于 `Document` URL 完成的文档 URL。</td>
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
            <td>`Document` 对于 XML 文档，节点的 xml 版本。</td>
        </tr>
        <tr>
            <td>name <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` 节点的名称。</td>
        </tr>
        <tr>
            <td>值 <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>`Attr` 节点的值。</td>
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
            <td>如果节点为 SVG，则其为 True。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="backendnodeid"></a> BackendNodeId `integer`

用于引用可能尚未推送到前端的节点的唯一 DOM 节点标识符。

</p>

---

### <a name="pseudotype"></a> PseudoType `string`

伪元素类型。

##### 允许的值
第一行、第一个字母、之前、之后、所选内容
</p>

---

## 依赖关系

[运行时](runtime.md)
