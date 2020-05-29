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
# <span data-ttu-id="29ec1-104">架构</span><span class="sxs-lookup"><span data-stu-id="29ec1-104">Schema</span></span>
<span data-ttu-id="29ec1-105">提供有关协议架构的信息。</span><span class="sxs-lookup"><span data-stu-id="29ec1-105">Provides information about the protocol schema.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="29ec1-106">方法</span><span class="sxs-lookup"><span data-stu-id="29ec1-106">Methods</span></span>**](#methods) | [<span data-ttu-id="29ec1-107">getDomains</span><span class="sxs-lookup"><span data-stu-id="29ec1-107">getDomains</span></span>](#getdomains) |
| [**<span data-ttu-id="29ec1-108">类型</span><span class="sxs-lookup"><span data-stu-id="29ec1-108">Types</span></span>**](#types) | [<span data-ttu-id="29ec1-109">域</span><span class="sxs-lookup"><span data-stu-id="29ec1-109">Domain</span></span>](#domain) |
## <span data-ttu-id="29ec1-110">方法</span><span class="sxs-lookup"><span data-stu-id="29ec1-110">Methods</span></span>

### <span data-ttu-id="29ec1-111">getDomains</span><span class="sxs-lookup"><span data-stu-id="29ec1-111">getDomains</span></span>
<span data-ttu-id="29ec1-112">返回支持的域。</span><span class="sxs-lookup"><span data-stu-id="29ec1-112">Returns supported domains.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="29ec1-113">返回</span><span class="sxs-lookup"><span data-stu-id="29ec1-113">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="29ec1-114">域</span><span class="sxs-lookup"><span data-stu-id="29ec1-114">domains</span></span></td>
            <td><a href="#domain"><code class="flyout">Domain[]</code></a></td>
            <td><span data-ttu-id="29ec1-115">支持的域列表。</span><span class="sxs-lookup"><span data-stu-id="29ec1-115">List of supported domains.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="29ec1-116">类型</span><span class="sxs-lookup"><span data-stu-id="29ec1-116">Types</span></span>

### <a name="domain"></a> <span data-ttu-id="29ec1-117">域</span><span class="sxs-lookup"><span data-stu-id="29ec1-117">Domain</span></span> `object`

<span data-ttu-id="29ec1-118">协议域的说明。</span><span class="sxs-lookup"><span data-stu-id="29ec1-118">Description of the protocol domain.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="29ec1-119">属性</span><span class="sxs-lookup"><span data-stu-id="29ec1-119">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="29ec1-120">name</span><span class="sxs-lookup"><span data-stu-id="29ec1-120">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="29ec1-121">域名。</span><span class="sxs-lookup"><span data-stu-id="29ec1-121">Domain name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="29ec1-122">version</span><span class="sxs-lookup"><span data-stu-id="29ec1-122">version</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="29ec1-123">域版本。</span><span class="sxs-lookup"><span data-stu-id="29ec1-123">Domain version.</span></span></td>
        </tr>
    </tbody>
</table>

---
