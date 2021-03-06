---
description: DevTools 协议版本 0.1 (EdgeHTML) 页面域参考。 与检查的页面相关的操作和事件属于页面域。
title: '页面域 - DevTools 协议版本 0.1 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b04b0685a6b465d40e999a2a48d370573a3058d8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399146"
---
# <a name="page-domain---devtools-protocol-version-01-edgehtml"></a><span data-ttu-id="ce721-104">页面域 - DevTools 协议版本 0.1 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="ce721-104">Page Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="ce721-105">与检查的页面相关的操作和事件属于页面域。</span><span class="sxs-lookup"><span data-stu-id="ce721-105">Actions and events related to the inspected page belong to the page domain.</span></span>  

| <span data-ttu-id="ce721-106">分类</span><span class="sxs-lookup"><span data-stu-id="ce721-106">Classification</span></span> | <span data-ttu-id="ce721-107">成员</span><span class="sxs-lookup"><span data-stu-id="ce721-107">Members</span></span> |  
|:--- |:--- |  
| [**<span data-ttu-id="ce721-108">方法</span><span class="sxs-lookup"><span data-stu-id="ce721-108">Methods</span></span>**](#methods) | <span data-ttu-id="ce721-109">[启用](#enable)， [禁用](#disable)， [导航](#navigate)</span><span class="sxs-lookup"><span data-stu-id="ce721-109">[enable](#enable), [disable](#disable), [navigate](#navigate)</span></span> |  
| [**<span data-ttu-id="ce721-110">类型</span><span class="sxs-lookup"><span data-stu-id="ce721-110">Types</span></span>**](#types) | [<span data-ttu-id="ce721-111">FrameId</span><span class="sxs-lookup"><span data-stu-id="ce721-111">FrameId</span></span>](#frameid) |  

## <a name="methods"></a><span data-ttu-id="ce721-112">方法</span><span class="sxs-lookup"><span data-stu-id="ce721-112">Methods</span></span>  

### <a name="enable"></a><span data-ttu-id="ce721-113">“启用”</span><span class="sxs-lookup"><span data-stu-id="ce721-113">enable</span></span>  

<span data-ttu-id="ce721-114">启用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="ce721-114">Enables page domain notifications.</span></span>  

&nbsp;  

---  

### <a name="disable"></a><span data-ttu-id="ce721-115">“禁用”</span><span class="sxs-lookup"><span data-stu-id="ce721-115">disable</span></span>  

<span data-ttu-id="ce721-116">禁用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="ce721-116">Disables page domain notifications.</span></span>  

&nbsp;  

---  

### <a name="navigate"></a><span data-ttu-id="ce721-117">导航</span><span class="sxs-lookup"><span data-stu-id="ce721-117">navigate</span></span>  

<span data-ttu-id="ce721-118">将当前页面导航到给定 URL。</span><span class="sxs-lookup"><span data-stu-id="ce721-118">Navigates current page to the given URL.</span></span>  

| <span data-ttu-id="ce721-119">参数</span><span class="sxs-lookup"><span data-stu-id="ce721-119">Parameters</span></span> | <span data-ttu-id="ce721-120">类型</span><span class="sxs-lookup"><span data-stu-id="ce721-120">Type</span></span> | <span data-ttu-id="ce721-121">详细信息</span><span class="sxs-lookup"><span data-stu-id="ce721-121">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="ce721-122">url</span><span class="sxs-lookup"><span data-stu-id="ce721-122">url</span></span> | `string` | <span data-ttu-id="ce721-123">要导航到页面的 URL。</span><span class="sxs-lookup"><span data-stu-id="ce721-123">URL to navigate the page to.</span></span> |  

| <span data-ttu-id="ce721-124">返回</span><span class="sxs-lookup"><span data-stu-id="ce721-124">Returns</span></span> | <span data-ttu-id="ce721-125">类型</span><span class="sxs-lookup"><span data-stu-id="ce721-125">Type</span></span> | <span data-ttu-id="ce721-126">详细信息</span><span class="sxs-lookup"><span data-stu-id="ce721-126">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="ce721-127">frameId</span><span class="sxs-lookup"><span data-stu-id="ce721-127">frameId</span></span> | [<span data-ttu-id="ce721-128">FrameId</span><span class="sxs-lookup"><span data-stu-id="ce721-128">FrameId</span></span>](#frameid) | <span data-ttu-id="ce721-129">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="ce721-129">**Experimental**.</span></span>  <span data-ttu-id="ce721-130">将导航的帧 ID。</span><span class="sxs-lookup"><span data-stu-id="ce721-130">Frame ID that will be navigated.</span></span> |  

---  

## <a name="types"></a><span data-ttu-id="ce721-131">类型</span><span class="sxs-lookup"><span data-stu-id="ce721-131">Types</span></span>  

### <a name="frameid-string"></a><span data-ttu-id="ce721-132">FrameId 字符串</span><span class="sxs-lookup"><span data-stu-id="ce721-132">FrameId string</span></span>  

<a name="frameid"></a>  

<span data-ttu-id="ce721-133">唯一的帧标识符。</span><span class="sxs-lookup"><span data-stu-id="ce721-133">Unique frame identifier.</span></span>  

&nbsp;  

---  
