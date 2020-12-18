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
# <span data-ttu-id="c53d4-104">架构域 - DevTools 协议版本 0.1 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="c53d4-104">Schema Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="c53d4-105">提供有关协议架构的信息。</span><span class="sxs-lookup"><span data-stu-id="c53d4-105">Provides information about the protocol schema.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="c53d4-106">方法</span><span class="sxs-lookup"><span data-stu-id="c53d4-106">Methods</span></span>**](#methods) | [<span data-ttu-id="c53d4-107">getDomains</span><span class="sxs-lookup"><span data-stu-id="c53d4-107">getDomains</span></span>](#getdomains) |
| [**<span data-ttu-id="c53d4-108">类型</span><span class="sxs-lookup"><span data-stu-id="c53d4-108">Types</span></span>**](#types) | [<span data-ttu-id="c53d4-109">域</span><span class="sxs-lookup"><span data-stu-id="c53d4-109">Domain</span></span>](#domain) |
## <span data-ttu-id="c53d4-110">方法</span><span class="sxs-lookup"><span data-stu-id="c53d4-110">Methods</span></span>

### <span data-ttu-id="c53d4-111">getDomains</span><span class="sxs-lookup"><span data-stu-id="c53d4-111">getDomains</span></span>
<span data-ttu-id="c53d4-112">返回支持的域。</span><span class="sxs-lookup"><span data-stu-id="c53d4-112">Returns supported domains.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c53d4-113">返回</span><span class="sxs-lookup"><span data-stu-id="c53d4-113">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c53d4-114">域</span><span class="sxs-lookup"><span data-stu-id="c53d4-114">domains</span></span></td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td><span data-ttu-id="c53d4-115">受支持的域列表。</span><span class="sxs-lookup"><span data-stu-id="c53d4-115">List of supported domains.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="c53d4-116">类型</span><span class="sxs-lookup"><span data-stu-id="c53d4-116">Types</span></span>

### <a name="domain"></a> <span data-ttu-id="c53d4-117">域</span><span class="sxs-lookup"><span data-stu-id="c53d4-117">Domain</span></span> `object`

<span data-ttu-id="c53d4-118">协议域的说明。</span><span class="sxs-lookup"><span data-stu-id="c53d4-118">Description of the protocol domain.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="c53d4-119">属性</span><span class="sxs-lookup"><span data-stu-id="c53d4-119">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="c53d4-120">name</span><span class="sxs-lookup"><span data-stu-id="c53d4-120">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c53d4-121">域名。</span><span class="sxs-lookup"><span data-stu-id="c53d4-121">Domain name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="c53d4-122">version</span><span class="sxs-lookup"><span data-stu-id="c53d4-122">version</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="c53d4-123">域版本。</span><span class="sxs-lookup"><span data-stu-id="c53d4-123">Domain version.</span></span></td>
        </tr>
    </tbody>
</table>

---
