---
description: 对架构域的引用。 提供有关协议架构的信息。
title: 架构域-DevTools 协议版本0。1
author: pelavall
ms.author: pelavall
ms.date: 12/15/2017
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 83d7019d18ccce1c81b67aafdcafe1a8566694ea
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563418"
---
# 架构
提供有关协议架构的信息。

| | |
|-|-|
| [**方法**](#methods) | [getDomains](#getdomains) |
| [**类型**](#types) | [域](#domain) |
## 方法

### getDomains
返回支持的域。

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
            <td>域</td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td>支持的域列表。</td>
        </tr>
    </tbody>
</table>

---

## 类型

### <a name="domain"></a> 域 `object`

协议域的说明。

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
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>域名。</td>
        </tr>
        <tr>
            <td>version</td>
            <td><code class="flyout">string</code></td>
            <td>域版本。</td>
        </tr>
    </tbody>
</table>

---
