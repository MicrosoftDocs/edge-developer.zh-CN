---
description: 来自包含导航原因和位置的 focus 事件的已调度对象
title: FocusNavigationEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 88f0a4ef8834c6e851f81ee10bf4202a0429f969
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752162"
---
# <span data-ttu-id="d2ca1-104">FocusNavigationEvent 对象</span><span class="sxs-lookup"><span data-stu-id="d2ca1-104">FocusNavigationEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="d2ca1-105">[**NavigateFocus**](../webview.md#navigatefocus) / [**DepartingFocus**](../webview.md#departingfocus)中包含[**NavigationReason**](#navigationreason)和 location 的已调度对象。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-105">The dispatched object from [**NavigateFocus**](../webview.md#navigatefocus)/[**DepartingFocus**](../webview.md#departingfocus) containing the [**NavigationReason**](#navigationreason) and location.</span></span>  

## <span data-ttu-id="d2ca1-106">方法</span><span class="sxs-lookup"><span data-stu-id="d2ca1-106">Methods</span></span>  

### <span data-ttu-id="d2ca1-107">requestFocus</span><span class="sxs-lookup"><span data-stu-id="d2ca1-107">requestFocus</span></span>  

<span data-ttu-id="d2ca1-108">调用以将焦点从应用移动到 web 视图。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-108">Called to move focus from the app to the webview.</span></span>  

### <span data-ttu-id="d2ca1-109">参数</span><span class="sxs-lookup"><span data-stu-id="d2ca1-109">Parameters</span></span>  

<span data-ttu-id="d2ca1-110">此方法没有参数。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-110">This method does not have parameters.</span></span>  

### <span data-ttu-id="d2ca1-111">返回值</span><span class="sxs-lookup"><span data-stu-id="d2ca1-111">Return value</span></span>  

<span data-ttu-id="d2ca1-112">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-112">This method does not return a value.</span></span>  

## <span data-ttu-id="d2ca1-113">属性</span><span class="sxs-lookup"><span data-stu-id="d2ca1-113">Properties</span></span>  

### <span data-ttu-id="d2ca1-114">navigationReason</span><span class="sxs-lookup"><span data-stu-id="d2ca1-114">navigationReason</span></span>  

<span data-ttu-id="d2ca1-115">枚举类型**NavigationReason**，"左"、"上"、"右" 或 "向下"。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-115">Enumerated type **NavigationReason**, either "left", "up", "right", or "down".</span></span>  

<span data-ttu-id="d2ca1-116">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-116">This property is read-only.</span></span>  

```javascript
var navigationReason = FocusNavigationEvent.navigationReason;
```  

#### <span data-ttu-id="d2ca1-117">属性值</span><span class="sxs-lookup"><span data-stu-id="d2ca1-117">Property value</span></span>  

<span data-ttu-id="d2ca1-118">类型： **NavigationReason**</span><span class="sxs-lookup"><span data-stu-id="d2ca1-118">Type: **NavigationReason**</span></span>  

### <span data-ttu-id="d2ca1-119">originHeight</span><span class="sxs-lookup"><span data-stu-id="d2ca1-119">originHeight</span></span>  

<span data-ttu-id="d2ca1-120">要获得焦点的元素的原始高度位置。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-120">The origin height location of the element to be given focus.</span></span>  

<span data-ttu-id="d2ca1-121">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-121">This property is read-only.</span></span>  

```javascript
var originWoriginHeightidth = FocusNavigationEvent.originHeight;
```  

#### <span data-ttu-id="d2ca1-122">属性值</span><span class="sxs-lookup"><span data-stu-id="d2ca1-122">Property value</span></span>  

<span data-ttu-id="d2ca1-123">类型： **float**</span><span class="sxs-lookup"><span data-stu-id="d2ca1-123">Type: **float**</span></span>  

### <span data-ttu-id="d2ca1-124">originLeft</span><span class="sxs-lookup"><span data-stu-id="d2ca1-124">originLeft</span></span>  

<span data-ttu-id="d2ca1-125">要获得焦点的元素的原点左侧位置。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-125">The origin left location of the element to be given focus.</span></span>  

<span data-ttu-id="d2ca1-126">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-126">This property is read-only.</span></span>  

```javascript
var originLeft = FocusNavigationEvent.originLeft;
```  

#### <span data-ttu-id="d2ca1-127">属性值</span><span class="sxs-lookup"><span data-stu-id="d2ca1-127">Property value</span></span>  

<span data-ttu-id="d2ca1-128">类型： **float**</span><span class="sxs-lookup"><span data-stu-id="d2ca1-128">Type: **float**</span></span>  

### <span data-ttu-id="d2ca1-129">originTop</span><span class="sxs-lookup"><span data-stu-id="d2ca1-129">originTop</span></span>  

<span data-ttu-id="d2ca1-130">要获得焦点的元素的原点顶部位置。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-130">The origin top location of the element to be given focus.</span></span>  

<span data-ttu-id="d2ca1-131">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-131">This property is read-only.</span></span>  

```javascript
var originTop = FocusNavigationEvent.originTop;
```  

#### <span data-ttu-id="d2ca1-132">属性值</span><span class="sxs-lookup"><span data-stu-id="d2ca1-132">Property value</span></span>  

<span data-ttu-id="d2ca1-133">类型： **float**</span><span class="sxs-lookup"><span data-stu-id="d2ca1-133">Type: **float**</span></span>  

### <span data-ttu-id="d2ca1-134">originWidth</span><span class="sxs-lookup"><span data-stu-id="d2ca1-134">originWidth</span></span>  

<span data-ttu-id="d2ca1-135">要获得焦点的元素的原始宽度位置。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-135">The origin width location of the element to be given focus.</span></span>  

<span data-ttu-id="d2ca1-136">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="d2ca1-136">This property is read-only.</span></span>  

```javascript
var originWidth = FocusNavigationEvent.originWidth;
```  

#### <span data-ttu-id="d2ca1-137">属性值</span><span class="sxs-lookup"><span data-stu-id="d2ca1-137">Property value</span></span>  

<span data-ttu-id="d2ca1-138">类型： **float**</span><span class="sxs-lookup"><span data-stu-id="d2ca1-138">Type: **float**</span></span>  
