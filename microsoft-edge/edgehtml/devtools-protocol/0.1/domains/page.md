---
description: DevTools 协议版本 0.1 (EdgeHTML) 页面域参考。 与检查的页面相关的操作和事件属于页面域。
title: '页面域 - DevTools 协议版本 0.1 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 55575e54b9125d7ff544c23c81da4b15d3b56fb1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232473"
---
# 页面域 - DevTools 协议版本 0.1 (EdgeHTML)   

与检查的页面相关的操作和事件属于页面域。

| | |
|-|-|
| [**方法**](#methods) | [启用](#enable)， [禁用](#disable)， [导航](#navigate) |
| [**类型**](#types) | [FrameId](#frameid) |
## 方法

### “启用”
启用页面域通知。


---

### “禁用”
禁用页面域通知。


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
            <td><span><b>实验。 </b></span>将导航的框架 ID。</td>
        </tr>
    </tbody>
</table>

---

## 类型

### <a name="frameid"></a> FrameId `string`

唯一帧标识符。


---
