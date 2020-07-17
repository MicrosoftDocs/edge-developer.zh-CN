---
description: 对架构域的引用。 提供有关协议架构的信息。
title: 架构域-DevTools 协议版本0.1 （EdgeHTML）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: a2f679f6f4bf8e82dc7298d96f798507b1338062
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882924"
---
# <span data-ttu-id="b8e87-104">架构域-DevTools 协议版本0.1 （EdgeHTML）</span><span class="sxs-lookup"><span data-stu-id="b8e87-104">Schema Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="b8e87-105">提供有关协议架构的信息。</span><span class="sxs-lookup"><span data-stu-id="b8e87-105">Provides information about the protocol schema.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="b8e87-106">方法</span><span class="sxs-lookup"><span data-stu-id="b8e87-106">Methods</span></span>**](#methods) | [<span data-ttu-id="b8e87-107">getDomains</span><span class="sxs-lookup"><span data-stu-id="b8e87-107">getDomains</span></span>](#getdomains) |
| [**<span data-ttu-id="b8e87-108">类型</span><span class="sxs-lookup"><span data-stu-id="b8e87-108">Types</span></span>**](#types) | [<span data-ttu-id="b8e87-109">域</span><span class="sxs-lookup"><span data-stu-id="b8e87-109">Domain</span></span>](#domain) |
## <span data-ttu-id="b8e87-110">方法</span><span class="sxs-lookup"><span data-stu-id="b8e87-110">Methods</span></span>

### <span data-ttu-id="b8e87-111">getDomains</span><span class="sxs-lookup"><span data-stu-id="b8e87-111">getDomains</span></span>
<span data-ttu-id="b8e87-112">返回支持的域。</span><span class="sxs-lookup"><span data-stu-id="b8e87-112">Returns supported domains.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b8e87-113">返回</span><span class="sxs-lookup"><span data-stu-id="b8e87-113">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b8e87-114">域</span><span class="sxs-lookup"><span data-stu-id="b8e87-114">domains</span></span></td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td><span data-ttu-id="b8e87-115">支持的域列表。</span><span class="sxs-lookup"><span data-stu-id="b8e87-115">List of supported domains.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="b8e87-116">类型</span><span class="sxs-lookup"><span data-stu-id="b8e87-116">Types</span></span>

### <a name="domain"></a> <span data-ttu-id="b8e87-117">域</span><span class="sxs-lookup"><span data-stu-id="b8e87-117">Domain</span></span> `object`

<span data-ttu-id="b8e87-118">协议域的说明。</span><span class="sxs-lookup"><span data-stu-id="b8e87-118">Description of the protocol domain.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="b8e87-119">属性</span><span class="sxs-lookup"><span data-stu-id="b8e87-119">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="b8e87-120">name</span><span class="sxs-lookup"><span data-stu-id="b8e87-120">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b8e87-121">域名。</span><span class="sxs-lookup"><span data-stu-id="b8e87-121">Domain name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="b8e87-122">version</span><span class="sxs-lookup"><span data-stu-id="b8e87-122">version</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="b8e87-123">域版本。</span><span class="sxs-lookup"><span data-stu-id="b8e87-123">Domain version.</span></span></td>
        </tr>
    </tbody>
</table>

---
