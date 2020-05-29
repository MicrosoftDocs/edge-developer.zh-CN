---
description: 来自包含导航原因和位置的 focus 事件的已调度对象
title: FocusNavigationEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: b988bcd7ff252b9972bef9a31339a34b4b58d9ee
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563043"
---
# <span data-ttu-id="2c5aa-104">FocusNavigationEvent 对象</span><span class="sxs-lookup"><span data-stu-id="2c5aa-104">FocusNavigationEvent object</span></span>

<span data-ttu-id="2c5aa-105">[**NavigateFocus**](../webview.md#navigatefocus) / [**DepartingFocus**](../webview.md#departingfocus)中包含[**NavigationReason**](#navigationreason)和 location 的已调度对象。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-105">The dispatched object from [**NavigateFocus**](../webview.md#navigatefocus)/[**DepartingFocus**](../webview.md#departingfocus) containing the [**NavigationReason**](#navigationreason) and location.</span></span> 

## <span data-ttu-id="2c5aa-106">方法</span><span class="sxs-lookup"><span data-stu-id="2c5aa-106">Methods</span></span>

### <span data-ttu-id="2c5aa-107">requestFocus</span><span class="sxs-lookup"><span data-stu-id="2c5aa-107">requestFocus</span></span>

<span data-ttu-id="2c5aa-108">调用以将焦点从应用移动到 web 视图。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-108">Called to move focus from the app to the webview.</span></span>

### <span data-ttu-id="2c5aa-109">参数</span><span class="sxs-lookup"><span data-stu-id="2c5aa-109">Parameters</span></span>

<span data-ttu-id="2c5aa-110">此方法没有参数。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-110">This method does not have parameters.</span></span>

### <span data-ttu-id="2c5aa-111">返回值</span><span class="sxs-lookup"><span data-stu-id="2c5aa-111">Return value</span></span>

<span data-ttu-id="2c5aa-112">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-112">This method does not return a value.</span></span>

## <span data-ttu-id="2c5aa-113">属性</span><span class="sxs-lookup"><span data-stu-id="2c5aa-113">Properties</span></span>
    
### <span data-ttu-id="2c5aa-114">navigationReason</span><span class="sxs-lookup"><span data-stu-id="2c5aa-114">navigationReason</span></span>

<span data-ttu-id="2c5aa-115">枚举类型**NavigationReason**，"左"、"上"、"右" 或 "向下"。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-115">Enumerated type **NavigationReason**, either "left", "up", "right", or "down".</span></span> 

<span data-ttu-id="2c5aa-116">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-116">This property is read-only.</span></span>

```js
var navigationReason = FocusNavigationEvent.navigationReason;
```

#### <span data-ttu-id="2c5aa-117">属性值</span><span class="sxs-lookup"><span data-stu-id="2c5aa-117">Property value</span></span>
<span data-ttu-id="2c5aa-118">类型： **NavigationReason**</span><span class="sxs-lookup"><span data-stu-id="2c5aa-118">Type: **NavigationReason**</span></span>

### <span data-ttu-id="2c5aa-119">originHeight</span><span class="sxs-lookup"><span data-stu-id="2c5aa-119">originHeight</span></span>

<span data-ttu-id="2c5aa-120">要获得焦点的元素的原始高度位置。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-120">The origin height location of the element to be given focus.</span></span>

<span data-ttu-id="2c5aa-121">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-121">This property is read-only.</span></span>

```js
var originWoriginHeightidth = FocusNavigationEvent.originHeight;
```

#### <span data-ttu-id="2c5aa-122">属性值</span><span class="sxs-lookup"><span data-stu-id="2c5aa-122">Property value</span></span>
<span data-ttu-id="2c5aa-123">类型： **float**</span><span class="sxs-lookup"><span data-stu-id="2c5aa-123">Type: **float**</span></span>

### <span data-ttu-id="2c5aa-124">originLeft</span><span class="sxs-lookup"><span data-stu-id="2c5aa-124">originLeft</span></span>

<span data-ttu-id="2c5aa-125">要获得焦点的元素的原点左侧位置。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-125">The origin left location of the element to be given focus.</span></span>

<span data-ttu-id="2c5aa-126">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-126">This property is read-only.</span></span>

```js
var originLeft = FocusNavigationEvent.originLeft;
```

#### <span data-ttu-id="2c5aa-127">属性值</span><span class="sxs-lookup"><span data-stu-id="2c5aa-127">Property value</span></span>
<span data-ttu-id="2c5aa-128">类型： **float**</span><span class="sxs-lookup"><span data-stu-id="2c5aa-128">Type: **float**</span></span>

### <span data-ttu-id="2c5aa-129">originTop</span><span class="sxs-lookup"><span data-stu-id="2c5aa-129">originTop</span></span>

<span data-ttu-id="2c5aa-130">要获得焦点的元素的原点顶部位置。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-130">The origin top location of the element to be given focus.</span></span>

<span data-ttu-id="2c5aa-131">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-131">This property is read-only.</span></span>

```js
var originTop = FocusNavigationEvent.originTop;
```

#### <span data-ttu-id="2c5aa-132">属性值</span><span class="sxs-lookup"><span data-stu-id="2c5aa-132">Property value</span></span>
<span data-ttu-id="2c5aa-133">类型： **float**</span><span class="sxs-lookup"><span data-stu-id="2c5aa-133">Type: **float**</span></span>

### <span data-ttu-id="2c5aa-134">originWidth</span><span class="sxs-lookup"><span data-stu-id="2c5aa-134">originWidth</span></span>

<span data-ttu-id="2c5aa-135">要获得焦点的元素的原始宽度位置。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-135">The origin width location of the element to be given focus.</span></span>

<span data-ttu-id="2c5aa-136">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="2c5aa-136">This property is read-only.</span></span>

```js
var originWidth = FocusNavigationEvent.originWidth;
```

#### <span data-ttu-id="2c5aa-137">属性值</span><span class="sxs-lookup"><span data-stu-id="2c5aa-137">Property value</span></span>
<span data-ttu-id="2c5aa-138">类型： **float**</span><span class="sxs-lookup"><span data-stu-id="2c5aa-138">Type: **float**</span></span>

