---
description: 对页面域的引用。 与已检查页面相关的操作和事件属于页面域。
title: Page Domain-DevTools 协议版本0。1
author: pelavall
ms.author: pelavall
ms.date: 12/15/2017
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: a1cd094baef4571240881a86ecccfdb319fef61b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563424"
---
# 页面
与已检查页面相关的操作和事件属于页面域。

| | |
|-|-|
| [**方法**](#methods) | [启用](#enable)、[禁用](#disable)、[导航](#navigate) |
| [**类型**](#types) | [FrameId](#frameid) |
## 方法

### “启用”
启用页面域通知。


---

### “禁用”
禁用页面域通知。


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
            <td><span><b>实验. </b></span>将导航的帧 id。</td>
        </tr>
    </tbody>
</table>

---

## 类型

### <a name="frameid"></a> FrameId `string`

唯一的帧标识符。


---
