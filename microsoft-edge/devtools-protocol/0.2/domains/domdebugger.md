---
description: DOMDebugger 域的参考。 DOM 调试允许在特定的 DOM 操作和事件上设置断点。 由于设置了常规断点，JavaScript 执行将在这些操作上停止。
title: DOMDebugger Domain-DevTools 协议版本0。2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 437a88ff93bda36d85a8f5632c1a02aa205d049b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563399"
---
# DOMDebugger
DOM 调试允许在特定的 DOM 操作和事件上设置断点。 由于设置了常规断点，JavaScript 执行将在这些操作上停止。

| | |
|-|-|
| [**方法**](#methods) | [setInstrumentationBreakpoint](#setinstrumentationbreakpoint)、 [removeInstrumentationBreakpoint](#removeinstrumentationbreakpoint) |
## 方法

### setInstrumentationBreakpoint
<span><b>实验. </b></span>在特定本机事件上设置断点。

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
            <td>名称</td>
            <td><code class="flyout">string</code></td>
            <td>要在其上停止的检测名称。 有效值： "scriptFirstStatement"。</td>
        </tr>
    </tbody>
</table>
</p>

---

### removeInstrumentationBreakpoint
<span><b>实验. </b></span>删除特定本机事件上的断点。

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
            <td>名称</td>
            <td><code class="flyout">string</code></td>
            <td>要在其上停止的检测名称。 有效值： "scriptFirstStatement"。</td>
        </tr>
    </tbody>
</table>
</p>

---
