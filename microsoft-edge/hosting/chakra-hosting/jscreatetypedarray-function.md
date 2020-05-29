---
description: 创建 JavaScript 类型数组对象。
title: JsCreateTypedArray 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 937a2a91-6f5f-4aaa-a018-d3089702bf36
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 57c5d15d76bf8b3ff29d10f7500fe41b3e959f68
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563147"
---
# <span data-ttu-id="2d996-103">JsCreateTypedArray 函数</span><span class="sxs-lookup"><span data-stu-id="2d996-103">JsCreateTypedArray Function</span></span>
<span data-ttu-id="2d996-104">创建 JavaScript 类型数组对象。</span><span class="sxs-lookup"><span data-stu-id="2d996-104">Creates a JavaScript typed array object.</span></span>  
  
## <span data-ttu-id="2d996-105">语法</span><span class="sxs-lookup"><span data-stu-id="2d996-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateTypedArray(  
   _In_ JsTypedArrayType arrayType,  
   _In_ JsValueRef baseArray,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int elementLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="2d996-106">参数</span><span class="sxs-lookup"><span data-stu-id="2d996-106">Parameters</span></span>  
 `arrayType`  
 <span data-ttu-id="2d996-107">要创建的数组的类型。</span><span class="sxs-lookup"><span data-stu-id="2d996-107">The type of the array to create.</span></span>  
  
 `baseArray`  
 <span data-ttu-id="2d996-108">新数组的基础数组。</span><span class="sxs-lookup"><span data-stu-id="2d996-108">The base array of the new array.</span></span> <span data-ttu-id="2d996-109">`JS_INVALID_REFERENCE`如果没有基本数组，则使用。</span><span class="sxs-lookup"><span data-stu-id="2d996-109">Use `JS_INVALID_REFERENCE` if no base array.</span></span>  
  
 `byteOffset`  
 <span data-ttu-id="2d996-110">从 `baseArray` （）的开头 `ArrayBuffer` 到要引用的结果输入数组的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="2d996-110">The offset in bytes from the start of `baseArray` (`ArrayBuffer`) for result typed array to reference.</span></span> <span data-ttu-id="2d996-111">仅当是对象时才适用 `baseArray` `ArrayBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="2d996-111">Only applicable when `baseArray` is an `ArrayBuffer` object.</span></span> <span data-ttu-id="2d996-112">否则必须为0。</span><span class="sxs-lookup"><span data-stu-id="2d996-112">Must be 0 otherwise.</span></span>  
  
 `elementLength`  
 <span data-ttu-id="2d996-113">数组中的元素数。</span><span class="sxs-lookup"><span data-stu-id="2d996-113">The number of elements in the array.</span></span> <span data-ttu-id="2d996-114">仅当创建新的类型化数组而 `baseArray` 不 `baseArray` 使用（is `JS_INVALID_REFERENCE` ）或 `baseArray` 对象时 `ArrayBuffer` 才适用。</span><span class="sxs-lookup"><span data-stu-id="2d996-114">Only applicable when creating a new typed array without `baseArray` (`baseArray` is `JS_INVALID_REFERENCE`) or when `baseArray` is an `ArrayBuffer` object.</span></span> <span data-ttu-id="2d996-115">否则必须为0。</span><span class="sxs-lookup"><span data-stu-id="2d996-115">Must be 0 otherwise.</span></span>  
  
 `result`  
 <span data-ttu-id="2d996-116">新的类型化数组对象。</span><span class="sxs-lookup"><span data-stu-id="2d996-116">The new typed array object.</span></span>  
  
## <span data-ttu-id="2d996-117">返回值</span><span class="sxs-lookup"><span data-stu-id="2d996-117">Return Value</span></span>  
 <span data-ttu-id="2d996-118">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="2d996-118">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="2d996-119">备注</span><span class="sxs-lookup"><span data-stu-id="2d996-119">Remarks</span></span>  
 <span data-ttu-id="2d996-120">`baseArray`可以是 `ArrayBuffer` 、其他类型的数组或 JavaScript `Array` 。</span><span class="sxs-lookup"><span data-stu-id="2d996-120">The `baseArray` can be an `ArrayBuffer`, another typed array, or a JavaScript `Array`.</span></span> <span data-ttu-id="2d996-121">如果返回的类型化数组是，则将使用该数组 `baseArray` `ArrayBuffer` ，或者以其他方式创建并使用基础源数组的副本。</span><span class="sxs-lookup"><span data-stu-id="2d996-121">The returned typed array will use the `baseArray` if it is an `ArrayBuffer`, or otherwise create and use a copy of the underlying source array.</span></span>  
  
 <span data-ttu-id="2d996-122">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="2d996-122">Requires an active script context.</span></span>  
  
 <span data-ttu-id="2d996-123">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="2d996-123">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="2d996-124">要求</span><span class="sxs-lookup"><span data-stu-id="2d996-124">Requirements</span></span>  
 <span data-ttu-id="2d996-125">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="2d996-125">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2d996-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d996-126">See Also</span></span>  
 [<span data-ttu-id="2d996-127">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="2d996-127">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)