---
description: DevTools 协议版本 0.2 (架构域的 EdgeHTML) 参考。 提供有关协议架构的信息。
title: '架构域 - DevTools 协议版本 0.2 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 12/16/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 53038a02844fafc9550a6ac26303620a1a0183f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232078"
---
# <span data-ttu-id="05009-104">架构域 - DevTools 协议版本 0.2 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="05009-104">Schema Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="05009-105">提供有关协议架构的信息。</span><span class="sxs-lookup"><span data-stu-id="05009-105">Provides information about the protocol schema.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="05009-106">方法</span><span class="sxs-lookup"><span data-stu-id="05009-106">Methods</span></span>**](#methods) | [<span data-ttu-id="05009-107">getDomains</span><span class="sxs-lookup"><span data-stu-id="05009-107">getDomains</span></span>](#getdomains) |
| [**<span data-ttu-id="05009-108">类型</span><span class="sxs-lookup"><span data-stu-id="05009-108">Types</span></span>**](#types) | [<span data-ttu-id="05009-109">域</span><span class="sxs-lookup"><span data-stu-id="05009-109">Domain</span></span>](#domain) |
## <span data-ttu-id="05009-110">方法</span><span class="sxs-lookup"><span data-stu-id="05009-110">Methods</span></span>

### <span data-ttu-id="05009-111">getDomains</span><span class="sxs-lookup"><span data-stu-id="05009-111">getDomains</span></span>
<span data-ttu-id="05009-112">返回支持的域。</span><span class="sxs-lookup"><span data-stu-id="05009-112">Returns supported domains.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="05009-113">返回</span><span class="sxs-lookup"><span data-stu-id="05009-113">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="05009-114">域</span><span class="sxs-lookup"><span data-stu-id="05009-114">domains</span></span></td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td><span data-ttu-id="05009-115">受支持的域列表。</span><span class="sxs-lookup"><span data-stu-id="05009-115">List of supported domains.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="05009-116">类型</span><span class="sxs-lookup"><span data-stu-id="05009-116">Types</span></span>

### <a name="domain"></a> <span data-ttu-id="05009-117">域</span><span class="sxs-lookup"><span data-stu-id="05009-117">Domain</span></span> `object`

<span data-ttu-id="05009-118">协议域的说明。</span><span class="sxs-lookup"><span data-stu-id="05009-118">Description of the protocol domain.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="05009-119">属性</span><span class="sxs-lookup"><span data-stu-id="05009-119">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="05009-120">name</span><span class="sxs-lookup"><span data-stu-id="05009-120">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="05009-121">域名。</span><span class="sxs-lookup"><span data-stu-id="05009-121">Domain name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="05009-122">version</span><span class="sxs-lookup"><span data-stu-id="05009-122">version</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="05009-123">域版本。</span><span class="sxs-lookup"><span data-stu-id="05009-123">Domain version.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
