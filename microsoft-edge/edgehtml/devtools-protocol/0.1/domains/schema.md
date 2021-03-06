---
description: DevTools 协议版本 0.1 (EdgeHTML) 架构域参考。 提供有关协议架构的信息。
title: '架构域 - DevTools 协议版本 0.1 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e89f4269b4984ee49e83a23fcab9679485c49040
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398859"
---
# <a name="schema-domain---devtools-protocol-version-01-edgehtml"></a><span data-ttu-id="17d65-104">架构域 - DevTools 协议版本 0.1 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="17d65-104">Schema Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="17d65-105">提供有关协议架构的信息。</span><span class="sxs-lookup"><span data-stu-id="17d65-105">Provides information about the protocol schema.</span></span>  

| <span data-ttu-id="17d65-106">分类</span><span class="sxs-lookup"><span data-stu-id="17d65-106">Classification</span></span> | <span data-ttu-id="17d65-107">成员</span><span class="sxs-lookup"><span data-stu-id="17d65-107">Members</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="17d65-108">方法</span><span class="sxs-lookup"><span data-stu-id="17d65-108">Methods</span></span>](#methods) | [<span data-ttu-id="17d65-109">getDomains</span><span class="sxs-lookup"><span data-stu-id="17d65-109">getDomains</span></span>](#getdomains) |  
| [<span data-ttu-id="17d65-110">类型</span><span class="sxs-lookup"><span data-stu-id="17d65-110">Types</span></span>](#types) | [<span data-ttu-id="17d65-111">域</span><span class="sxs-lookup"><span data-stu-id="17d65-111">Domain</span></span>](#domain) |  

## <a name="methods"></a><span data-ttu-id="17d65-112">方法</span><span class="sxs-lookup"><span data-stu-id="17d65-112">Methods</span></span>  

### <a name="getdomains"></a><span data-ttu-id="17d65-113">getDomains</span><span class="sxs-lookup"><span data-stu-id="17d65-113">getDomains</span></span>  

<span data-ttu-id="17d65-114">返回支持的域。</span><span class="sxs-lookup"><span data-stu-id="17d65-114">Returns supported domains.</span></span>  

| <span data-ttu-id="17d65-115">返回</span><span class="sxs-lookup"><span data-stu-id="17d65-115">Returns</span></span> | <span data-ttu-id="17d65-116">类型</span><span class="sxs-lookup"><span data-stu-id="17d65-116">Type</span></span> | <span data-ttu-id="17d65-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="17d65-117">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="17d65-118">域</span><span class="sxs-lookup"><span data-stu-id="17d65-118">domains</span></span> | [<span data-ttu-id="17d65-119">域[]</span><span class="sxs-lookup"><span data-stu-id="17d65-119">Domain[]</span></span>](#domain) | <span data-ttu-id="17d65-120">受支持的域列表。</span><span class="sxs-lookup"><span data-stu-id="17d65-120">List of supported domains.</span></span> |  

---  

## <a name="types"></a><span data-ttu-id="17d65-121">类型</span><span class="sxs-lookup"><span data-stu-id="17d65-121">Types</span></span>  

### <a name="domain-object"></a><span data-ttu-id="17d65-122">Domain 对象</span><span class="sxs-lookup"><span data-stu-id="17d65-122">Domain object</span></span>  

<a name="domain"></a>  

<span data-ttu-id="17d65-123">协议域的说明。</span><span class="sxs-lookup"><span data-stu-id="17d65-123">Description of the protocol domain.</span></span>  

| <span data-ttu-id="17d65-124">属性</span><span class="sxs-lookup"><span data-stu-id="17d65-124">Properties</span></span> | <span data-ttu-id="17d65-125">类型</span><span class="sxs-lookup"><span data-stu-id="17d65-125">Type</span></span> | <span data-ttu-id="17d65-126">详细信息</span><span class="sxs-lookup"><span data-stu-id="17d65-126">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="17d65-127">name</span><span class="sxs-lookup"><span data-stu-id="17d65-127">name</span></span> | `string` | <span data-ttu-id="17d65-128">域名。</span><span class="sxs-lookup"><span data-stu-id="17d65-128">Domain name.</span></span> |  
| <span data-ttu-id="17d65-129">version</span><span class="sxs-lookup"><span data-stu-id="17d65-129">version</span></span> | `string` | <span data-ttu-id="17d65-130">域版本。</span><span class="sxs-lookup"><span data-stu-id="17d65-130">Domain version.</span></span> |  

---  
