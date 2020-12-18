---
description: DevTools 协议版本 0.2 (EdgeHTML) 页面域参考。 与检查的页面相关的操作和事件属于页面域。
title: '页面域 - DevTools 协议版本 0.2 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2f1849a2e2aa2f53cef9dff5d03ac991d368a6f3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232083"
---
# 页面域 - DevTools 协议版本 0.2 (EdgeHTML)   

与检查的页面相关的操作和事件属于页面域。

| | |
|-|-|
| [**方法**](#methods) | [启用](#enable)， [禁用](#disable)， [导航](#navigate)， [getFrameTree](#getframetree) |
| [**事件**](#events) | [frameAttached](#frameattached)， [frameDetached](#framedetached)， [frameNavigated](#framenavigated)， [loadEventFired](#loadeventfired)， [domContentEventFired](#domcontenteventfired) |
| [**类型**](#types) | [FrameId](#frameid)， [Frame](#frame)， [FrameTree](#frametree) |
## 方法

### “启用”
启用页面域通知。

</p>

---

### “禁用”
禁用页面域通知。

</p>

---

### 导航
将当前页面导航到给定 URL。

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
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>导航到页面的 URL。</td>
        </tr>
        <tr>
            <td>frameId <br/> <i>可选</i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>要导航的框架 ID。 如果未指定，将导航到顶部页面。</td>
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
            <td>frameId</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>将导航的框架 ID。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getFrameTree
返回当前框架树结构。

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
            <td>frameTree</td>
            <td><a href="#frametree"><code class="flyout">FrameTree</code></a></td>
            <td>显示框架树结构。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 事件

### frameAttached
当框架已连接到其父级时触发。

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
            <td>frameId</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>已附加的帧的 ID。</td>
        </tr>
        <tr>
            <td>parentFrameId</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>父框架标识符。</td>
        </tr>
        <tr>
            <td>stack <br/> <i>可选</i></td>
            <td><a href="runtime.md#stacktrace"><code class="flyout">Runtime.StackTrace</code></a></td>
            <td>框架的附加时间 JavaScript 堆栈跟踪，仅在框架从脚本启动时设置。</td>
        </tr>
    </tbody>
</table>
</p>

---

### frameDetached
当框架与父级分离时触发。

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
            <td>frameId</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>已分离的帧的 ID。</td>
        </tr>
    </tbody>
</table>
</p>

---

### frameNavigated
帧导航完成后触发。

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
            <td>frame</td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td>Frame 对象。</td>
        </tr>
    </tbody>
</table>
</p>

---

### loadEventFired
对应于 window.onload 事件。

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
            <td>timestamp</td>
            <td><code class="flyout">number</code></td>
            <td>自纪元以来的毫秒数。</td>
        </tr>
    </tbody>
</table>
</p>

---

### domContentEventFired
对应于 document.onDOMContentLoaded 事件。

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
            <td>timestamp</td>
            <td><code class="flyout">number</code></td>
            <td>自纪元以来的毫秒数。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 类型

### <a name="frameid"></a> FrameId `string`

唯一帧标识符。

</p>

---

### <a name="frame"></a> 帧 `object`

有关页面上框架的信息。

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
            <td>id</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>帧唯一标识符。</td>
        </tr>
        <tr>
            <td>parentId <br/> <i>可选</i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>父框架唯一标识符。</td>
        </tr>
        <tr>
            <td>name <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>标记中指定的框架名称。</td>
        </tr>
        <tr>
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>框架文档的 URL。</td>
        </tr>
        <tr>
            <td>securityOrigin</td>
            <td><code class="flyout">string</code></td>
            <td>框架文档的安全来源。</td>
        </tr>
        <tr>
            <td>mimeType</td>
            <td><code class="flyout">string</code></td>
            <td>框架文档的 mimeType，由浏览器确定。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="frametree"></a> FrameTree `object`

有关 Frame 层次结构的信息。

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
            <td>frame</td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td>此树项的框架信息。</td>
        </tr>
        <tr>
            <td>childFrames <br/> <i>可选</i></td>
            <td><a href="#frametree"><code class="flyout">FrameTree[]</code></a></td>
            <td>子框架。</td>
        </tr>
    </tbody>
</table>
</p>

---
