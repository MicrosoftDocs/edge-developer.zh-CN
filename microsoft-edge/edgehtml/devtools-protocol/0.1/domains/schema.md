---
description: DevTools 协议版本 0.1 (架构域的 EdgeHTML) 参考。 提供有关协议架构的信息。
title: '架构域 - DevTools 协议版本 0.1 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7b4ec71b7799ae099c673bd81fa5b15a8ddd5d27
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232466"
---
# 架构域 - DevTools 协议版本 0.1 (EdgeHTML)   

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
            <td>受支持的域列表。</td>
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
