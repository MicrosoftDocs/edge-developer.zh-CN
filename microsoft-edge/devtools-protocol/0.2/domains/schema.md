---
description: 对架构域的引用。 提供有关协议架构的信息。
title: 架构域-DevTools 协议版本0.2 （EdgeHTML）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: d0fbe9cde742d255797a2460b940732ffa5b8f27
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882875"
---
# <span data-ttu-id="178da-104">架构域-DevTools 协议版本0.2 （EdgeHTML）</span><span class="sxs-lookup"><span data-stu-id="178da-104">Schema Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="178da-105">提供有关协议架构的信息。</span><span class="sxs-lookup"><span data-stu-id="178da-105">Provides information about the protocol schema.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="178da-106">方法</span><span class="sxs-lookup"><span data-stu-id="178da-106">Methods</span></span>**](#methods) | [<span data-ttu-id="178da-107">getDomains</span><span class="sxs-lookup"><span data-stu-id="178da-107">getDomains</span></span>](#getdomains) |
| [**<span data-ttu-id="178da-108">类型</span><span class="sxs-lookup"><span data-stu-id="178da-108">Types</span></span>**](#types) | [<span data-ttu-id="178da-109">域</span><span class="sxs-lookup"><span data-stu-id="178da-109">Domain</span></span>](#domain) |
## <span data-ttu-id="178da-110">方法</span><span class="sxs-lookup"><span data-stu-id="178da-110">Methods</span></span>

### <span data-ttu-id="178da-111">getDomains</span><span class="sxs-lookup"><span data-stu-id="178da-111">getDomains</span></span>
<span data-ttu-id="178da-112">返回支持的域。</span><span class="sxs-lookup"><span data-stu-id="178da-112">Returns supported domains.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="178da-113">返回</span><span class="sxs-lookup"><span data-stu-id="178da-113">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="178da-114">域</span><span class="sxs-lookup"><span data-stu-id="178da-114">domains</span></span></td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td><span data-ttu-id="178da-115">支持的域列表。</span><span class="sxs-lookup"><span data-stu-id="178da-115">List of supported domains.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="178da-116">类型</span><span class="sxs-lookup"><span data-stu-id="178da-116">Types</span></span>

### <a name="domain"></a> <span data-ttu-id="178da-117">域</span><span class="sxs-lookup"><span data-stu-id="178da-117">Domain</span></span> `object`

<span data-ttu-id="178da-118">协议域的说明。</span><span class="sxs-lookup"><span data-stu-id="178da-118">Description of the protocol domain.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="178da-119">属性</span><span class="sxs-lookup"><span data-stu-id="178da-119">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="178da-120">name</span><span class="sxs-lookup"><span data-stu-id="178da-120">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="178da-121">域名。</span><span class="sxs-lookup"><span data-stu-id="178da-121">Domain name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="178da-122">version</span><span class="sxs-lookup"><span data-stu-id="178da-122">version</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="178da-123">域版本。</span><span class="sxs-lookup"><span data-stu-id="178da-123">Domain version.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
