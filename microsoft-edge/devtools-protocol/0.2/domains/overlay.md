---
description: 覆盖域的参考。 覆盖域公开视觉装饰和节点选择交互
title: 覆盖域 DevTools 协议版本0。2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: a7657e2abc99e45894f19f6557f12f78f8ee9c75
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563398"
---
# Overlay
覆盖域公开视觉装饰和节点选择交互

| | |
|-|-|
| [**方法**](#methods) | [enable](#enable)、 [disable](#disable)、 [setInspectMode](#setinspectmode) |
| [**事件**](#events) | [inspectNodeRequested](#inspectnoderequested)、 [nodeHighlightRequested](#nodehighlightrequested) |
| [**依赖关系**](#dependencies) | [DOM](dom.md) |
## 方法

### “启用”
启用 <code>nodeHighlightRequested</code> 和事件报告 <code>inspectElementRequested</code>

</p>

---

### “禁用”
禁用覆盖域事件的报告

</p>

---

### setInspectMode
设置客户端的元素选择模式

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
            <td>mode</td>
            <td><code class="flyout">string</code></td>
            <td>检查模式。  有效值为 "searchForNode" 和 "none"。</td>
        </tr>
        <tr>
            <td>highlightConfig <br/> <i>可选</i></td>
            <td><a href="dom.md#highlightconfig"><code class="flyout">DOM.HighlightConfig</code></a></td>
            <td>检查时要使用的突出显示配置</td>
        </tr>
    </tbody>
</table>
</p>

---

## 事件

### inspectNodeRequested
通知客户端用户已要求检查特定节点

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
            <td>backendNodeId</td>
            <td><a href="dom.md#backendnodeid"><code class="flyout">DOM.BackendNodeId</code></a></td>
            <td>请求的节点的后端节点 ID</td>
        </tr>
    </tbody>
</table>
</p>

---

### nodeHighlightRequested
指示用户已悬停在节点上，并且可能检查节点

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
            <td><a href="dom.md#nodeid"><code class="flyout">DOM.NodeId</code></a></td>
            <td>要考虑的节点的节点 ID</td>
        </tr>
    </tbody>
</table>
</p>

---

## 依赖关系

[DOM](dom.md)