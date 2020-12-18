---
description: JsValueRef 的 JavaScript 类型。
title: JsValueType 枚举 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsValueType
helpviewer_keywords:
- JsValueType enumeration
ms.assetid: 6645e723-e554-41fc-b622-ab54ee044b3d
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 840afcde86d4df80490d463921a74c73e42ddfc2
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232348"
---
# <span data-ttu-id="4428b-103">JsValueType 枚举</span><span class="sxs-lookup"><span data-stu-id="4428b-103">JsValueType Enumeration</span></span>

<span data-ttu-id="4428b-104">JsValueRef 的 JavaScript 类型。</span><span class="sxs-lookup"><span data-stu-id="4428b-104">The JavaScript type of a JsValueRef.</span></span>  
  
## <span data-ttu-id="4428b-105">语法</span><span class="sxs-lookup"><span data-stu-id="4428b-105">Syntax</span></span>  
  
```cpp  
enum JsValueType {  
    JsUndefined      = 0,  
    JsNull           = 1,  
    JsNumber         = 2,  
    JsString         = 3,  
    JsBoolean        = 4,  
    JsObject         = 5,  
    JsFunction       = 6,  
    JsError          = 7,  
    JsArray          = 8,  
    JsSymbol         = 9,  
    JsArrayBuffer    = 10,  
    JsTypedArray     = 11,  
    JsDataView       = 12,  
};  
```  
  
## <span data-ttu-id="4428b-106">成员</span><span class="sxs-lookup"><span data-stu-id="4428b-106">Members</span></span>  
  
### <span data-ttu-id="4428b-107">值</span><span class="sxs-lookup"><span data-stu-id="4428b-107">Values</span></span>  
  
|<span data-ttu-id="4428b-108">名称</span><span class="sxs-lookup"><span data-stu-id="4428b-108">Name</span></span>|<span data-ttu-id="4428b-109">描述</span><span class="sxs-lookup"><span data-stu-id="4428b-109">Description</span></span>|  
|----------|-----------------|  
|`JsUndefined`|<span data-ttu-id="4428b-110">值为 `undefined` 值。</span><span class="sxs-lookup"><span data-stu-id="4428b-110">The value is the `undefined` value.</span></span>|  
|`JsNull`|<span data-ttu-id="4428b-111">值为 `null` 值。</span><span class="sxs-lookup"><span data-stu-id="4428b-111">The value is the `null` value.</span></span>|  
|`JsNumber`|<span data-ttu-id="4428b-112">值为 JavaScript 数字值。</span><span class="sxs-lookup"><span data-stu-id="4428b-112">The value is a JavaScript number value.</span></span>|  
|`JsString`|<span data-ttu-id="4428b-113">值为 JavaScript 字符串值。</span><span class="sxs-lookup"><span data-stu-id="4428b-113">The value is a JavaScript string value.</span></span>|  
|`JsBoolean`|<span data-ttu-id="4428b-114">值为 JavaScript 布尔值。</span><span class="sxs-lookup"><span data-stu-id="4428b-114">The value is a JavaScript Boolean value.</span></span>|  
|`JsObject`|<span data-ttu-id="4428b-115">值为 JavaScript 对象值。</span><span class="sxs-lookup"><span data-stu-id="4428b-115">The value is a JavaScript object value.</span></span>|  
|`JsFunction`|<span data-ttu-id="4428b-116">值为 JavaScript 函数对象值。</span><span class="sxs-lookup"><span data-stu-id="4428b-116">The value is a JavaScript function object value.</span></span>|  
|`JsError`|<span data-ttu-id="4428b-117">值为 JavaScript 错误对象值。</span><span class="sxs-lookup"><span data-stu-id="4428b-117">The value is a JavaScript error object value.</span></span>|  
|`JsArray`|<span data-ttu-id="4428b-118">值为 JavaScript 数组对象值。</span><span class="sxs-lookup"><span data-stu-id="4428b-118">The value is a JavaScript array object value.</span></span>|  
|`JsSymbol`|<span data-ttu-id="4428b-119">该值是一个 JavaScript 符号值。</span><span class="sxs-lookup"><span data-stu-id="4428b-119">The value is a JavaScript symbol value.</span></span><br /><br /> <span data-ttu-id="4428b-120">此枚举值仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="4428b-120">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsArrayBuffer`|<span data-ttu-id="4428b-121">值为 JavaScript `ArrayBuffer` 对象值。</span><span class="sxs-lookup"><span data-stu-id="4428b-121">The value is a JavaScript `ArrayBuffer` object value.</span></span><br /><br /> <span data-ttu-id="4428b-122">此枚举值仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="4428b-122">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsTypedArray`|<span data-ttu-id="4428b-123">该值为 JavaScript 类型数组对象值。</span><span class="sxs-lookup"><span data-stu-id="4428b-123">The value is a JavaScript typed array object value.</span></span><br /><br /> <span data-ttu-id="4428b-124">此枚举值仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="4428b-124">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsDataView`|<span data-ttu-id="4428b-125">值为 JavaScript `DataView` 对象值。</span><span class="sxs-lookup"><span data-stu-id="4428b-125">The value is a JavaScript `DataView` object value.</span></span><br /><br /> <span data-ttu-id="4428b-126">此枚举值仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="4428b-126">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
  
## <span data-ttu-id="4428b-127">要求</span><span class="sxs-lookup"><span data-stu-id="4428b-127">Requirements</span></span>  
 <span data-ttu-id="4428b-128">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="4428b-128">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4428b-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4428b-129">See Also</span></span>  
 [<span data-ttu-id="4428b-130">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="4428b-130">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
