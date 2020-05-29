---
description: 对页面域的引用。 与已检查页面相关的操作和事件属于页面域。
title: Page Domain-DevTools 协议版本0。2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 688cc1fcfce0b81c5eed0c858a4a60b4754c49a4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563400"
---
# 页面
与已检查页面相关的操作和事件属于页面域。

| | |
|-|-|
| [**方法**](#methods) | [启用](#enable)、[禁用](#disable)、[导航](#navigate)、 [getFrameTree](#getframetree) |
| [**事件**](#events) | [frameAttached](#frameattached)、 [frameDetached](#framedetached)、 [frameNavigated](#framenavigated)、 [loadEventFired](#loadeventfired)、 [domContentEventFired](#domcontenteventfired) |
| [**类型**](#types) | [FrameId](#frameid)、 [Frame](#frame)、 [FrameTree](#frametree) |
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
将当前页导航到给定的 URL。

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
            <td>要将页面导航到的 URL。</td>
        </tr>
        <tr>
            <td>frameId <br/> <i>可选</i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>要导航的帧 id。 如果未指定，将导航页首页。</td>
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
            <td>将导航的帧 id。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getFrameTree
返回当前的帧树结构。

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
            <td>显示帧树结构。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 事件

### frameAttached
当 frame 已附加到其父项时激发。

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
            <td>已附加的帧的 Id。</td>
        </tr>
        <tr>
            <td>parentFrameId</td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>父框架标识符。</td>
        </tr>
        <tr>
            <td>牌 <br/> <i>可选</i></td>
            <td><a href="runtime.md#stacktrace"><code class="flyout">Runtime.StackTrace</code></a></td>
            <td>JavaScript 堆栈跟踪（附加了 frame），仅在从脚本启动的帧时进行设置。</td>
        </tr>
    </tbody>
</table>
</p>

---

### frameDetached
当 frame 已从其父项分离时激发。

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
            <td>已分离的帧的 Id。</td>
        </tr>
    </tbody>
</table>
</p>

---

### frameNavigated
在帧导航完成后激发。

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
            <td>帧</td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td>Frame 对象。</td>
        </tr>
    </tbody>
</table>
</p>

---

### loadEventFired
对应于 window onload 事件。

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
            <td>icmp</td>
            <td><code class="flyout">number</code></td>
            <td>自 epoch 以来的毫秒数。</td>
        </tr>
    </tbody>
</table>
</p>

---

### domContentEventFired
对应于 onDOMContentLoaded 事件。

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
            <td>icmp</td>
            <td><code class="flyout">number</code></td>
            <td>自 epoch 以来的毫秒数。</td>
        </tr>
    </tbody>
</table>
</p>

---

## 类型

### <a name="frameid"></a> FrameId `string`

唯一的帧标识符。

</p>

---

### <a name="frame"></a> 帧 `object`

有关页面上的框架的信息。

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
            <td>Frame 唯一标识符。</td>
        </tr>
        <tr>
            <td>parentId <br/> <i>可选</i></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td>父框架唯一标识符。</td>
        </tr>
        <tr>
            <td>name <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>在标记中指定的帧的名称。</td>
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
            <td>由浏览器确定的框架文档的 mimeType。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="frametree"></a> FrameTree `object`

有关帧层次结构的信息。

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
            <td>帧</td>
            <td><a href="#frame"><code class="flyout">Frame</code></a></td>
            <td>此树项目的帧信息。</td>
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
