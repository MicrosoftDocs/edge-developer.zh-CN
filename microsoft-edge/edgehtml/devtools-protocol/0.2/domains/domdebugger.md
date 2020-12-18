---
description: DOMDebugger 域的引用。 DOM 调试允许设置特定 DOM 操作和事件的断点。 JavaScript 执行将在这些操作上停止，就像有常规断点集一样。
title: DOMDebugger 域 - DevTools 协议版本 0.2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d97a9a8f2d0e49166f5f081e8bb0c0d5d3cdd93f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232084"
---
# DOMDebugger

DOM 调试允许设置特定 DOM 操作和事件的断点。 JavaScript 执行将在这些操作上停止，就像有常规断点集一样。

| | |
|-|-|
| [**方法**](#methods) | [setInstrumentationBreakpoint](#setinstrumentationbreakpoint)， [removeInstrumentationBreakpoint](#removeinstrumentationbreakpoint) |
## 方法

### setInstrumentationBreakpoint
<span><b>实验。 </b></span>设置特定本机事件的断点。

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
            <td>eventName</td>
            <td><code class="flyout">string</code></td>
            <td>要停止的检测名称。 有效值："scriptFirstStatement"。</td>
        </tr>
    </tbody>
</table>
</p>

---

### removeInstrumentationBreakpoint
<span><b>实验。 </b></span>删除特定本机事件的断点。

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
            <td>eventName</td>
            <td><code class="flyout">string</code></td>
            <td>要停止的检测名称。 有效值："scriptFirstStatement"。</td>
        </tr>
    </tbody>
</table>
</p>

---
