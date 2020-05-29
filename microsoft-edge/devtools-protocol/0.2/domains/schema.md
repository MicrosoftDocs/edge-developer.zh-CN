---
description: 对架构域的引用。 提供有关协议架构的信息。
title: 架构域-DevTools 协议版本0。2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: df86e6669956c14b7c905514fc44376f71eaa993
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563393"
---
# <span data-ttu-id="63bfd-104">架构</span><span class="sxs-lookup"><span data-stu-id="63bfd-104">Schema</span></span>
<span data-ttu-id="63bfd-105">提供有关协议架构的信息。</span><span class="sxs-lookup"><span data-stu-id="63bfd-105">Provides information about the protocol schema.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="63bfd-106">方法</span><span class="sxs-lookup"><span data-stu-id="63bfd-106">Methods</span></span>**](#methods) | [<span data-ttu-id="63bfd-107">getDomains</span><span class="sxs-lookup"><span data-stu-id="63bfd-107">getDomains</span></span>](#getdomains) |
| [**<span data-ttu-id="63bfd-108">类型</span><span class="sxs-lookup"><span data-stu-id="63bfd-108">Types</span></span>**](#types) | [<span data-ttu-id="63bfd-109">域</span><span class="sxs-lookup"><span data-stu-id="63bfd-109">Domain</span></span>](#domain) |
## <span data-ttu-id="63bfd-110">方法</span><span class="sxs-lookup"><span data-stu-id="63bfd-110">Methods</span></span>

### <span data-ttu-id="63bfd-111">getDomains</span><span class="sxs-lookup"><span data-stu-id="63bfd-111">getDomains</span></span>
<span data-ttu-id="63bfd-112">返回支持的域。</span><span class="sxs-lookup"><span data-stu-id="63bfd-112">Returns supported domains.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="63bfd-113">返回</span><span class="sxs-lookup"><span data-stu-id="63bfd-113">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="63bfd-114">域</span><span class="sxs-lookup"><span data-stu-id="63bfd-114">domains</span></span></td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td><span data-ttu-id="63bfd-115">支持的域列表。</span><span class="sxs-lookup"><span data-stu-id="63bfd-115">List of supported domains.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="63bfd-116">类型</span><span class="sxs-lookup"><span data-stu-id="63bfd-116">Types</span></span>

### <a name="domain"></a> <span data-ttu-id="63bfd-117">域</span><span class="sxs-lookup"><span data-stu-id="63bfd-117">Domain</span></span> `object`

<span data-ttu-id="63bfd-118">协议域的说明。</span><span class="sxs-lookup"><span data-stu-id="63bfd-118">Description of the protocol domain.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="63bfd-119">属性</span><span class="sxs-lookup"><span data-stu-id="63bfd-119">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="63bfd-120">name</span><span class="sxs-lookup"><span data-stu-id="63bfd-120">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="63bfd-121">域名。</span><span class="sxs-lookup"><span data-stu-id="63bfd-121">Domain name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="63bfd-122">version</span><span class="sxs-lookup"><span data-stu-id="63bfd-122">version</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="63bfd-123">域版本。</span><span class="sxs-lookup"><span data-stu-id="63bfd-123">Domain version.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
