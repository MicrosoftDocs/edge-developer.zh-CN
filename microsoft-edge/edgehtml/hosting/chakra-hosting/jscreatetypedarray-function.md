---
description: 创建 JavaScript 类型数组对象。
title: JsCreateTypedArray 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 937a2a91-6f5f-4aaa-a018-d3089702bf36
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 62f62296d81dafe6515f69a990e33ff5c00730e1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232552"
---
# <span data-ttu-id="d830c-103">JsCreateTypedArray 函数</span><span class="sxs-lookup"><span data-stu-id="d830c-103">JsCreateTypedArray Function</span></span>

<span data-ttu-id="d830c-104">创建 JavaScript 类型数组对象。</span><span class="sxs-lookup"><span data-stu-id="d830c-104">Creates a JavaScript typed array object.</span></span>  
  
## <span data-ttu-id="d830c-105">语法</span><span class="sxs-lookup"><span data-stu-id="d830c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateTypedArray(  
   _In_ JsTypedArrayType arrayType,  
   _In_ JsValueRef baseArray,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int elementLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="d830c-106">参数</span><span class="sxs-lookup"><span data-stu-id="d830c-106">Parameters</span></span>  
 `arrayType`  
 <span data-ttu-id="d830c-107">要创建的数组的类型。</span><span class="sxs-lookup"><span data-stu-id="d830c-107">The type of the array to create.</span></span>  
  
 `baseArray`  
 <span data-ttu-id="d830c-108">新数组的基准数组。</span><span class="sxs-lookup"><span data-stu-id="d830c-108">The base array of the new array.</span></span> <span data-ttu-id="d830c-109">如果没有 `JS_INVALID_REFERENCE` 基本数组，请使用。</span><span class="sxs-lookup"><span data-stu-id="d830c-109">Use `JS_INVALID_REFERENCE` if no base array.</span></span>  
  
 `byteOffset`  
 <span data-ttu-id="d830c-110">结果类型数组从 () `baseArray` `ArrayBuffer` 的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d830c-110">The offset in bytes from the start of `baseArray` (`ArrayBuffer`) for result typed array to reference.</span></span> <span data-ttu-id="d830c-111">仅在对象 `baseArray` 适用 `ArrayBuffer` 时适用。</span><span class="sxs-lookup"><span data-stu-id="d830c-111">Only applicable when `baseArray` is an `ArrayBuffer` object.</span></span> <span data-ttu-id="d830c-112">否则必须为 0。</span><span class="sxs-lookup"><span data-stu-id="d830c-112">Must be 0 otherwise.</span></span>  
  
 `elementLength`  
 <span data-ttu-id="d830c-113">数组中的元素数。</span><span class="sxs-lookup"><span data-stu-id="d830c-113">The number of elements in the array.</span></span> <span data-ttu-id="d830c-114">仅在创建一个新的类型数组（ () `baseArray` `baseArray` `JS_INVALID_REFERENCE` 或对象 `baseArray` `ArrayBuffer` 时适用。</span><span class="sxs-lookup"><span data-stu-id="d830c-114">Only applicable when creating a new typed array without `baseArray` (`baseArray` is `JS_INVALID_REFERENCE`) or when `baseArray` is an `ArrayBuffer` object.</span></span> <span data-ttu-id="d830c-115">否则必须为 0。</span><span class="sxs-lookup"><span data-stu-id="d830c-115">Must be 0 otherwise.</span></span>  
  
 `result`  
 <span data-ttu-id="d830c-116">新的类型数组对象。</span><span class="sxs-lookup"><span data-stu-id="d830c-116">The new typed array object.</span></span>  
  
## <span data-ttu-id="d830c-117">返回值</span><span class="sxs-lookup"><span data-stu-id="d830c-117">Return Value</span></span>  
 <span data-ttu-id="d830c-118">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="d830c-118">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d830c-119">备注</span><span class="sxs-lookup"><span data-stu-id="d830c-119">Remarks</span></span>  
 <span data-ttu-id="d830c-120">可以是 `baseArray` 一个 `ArrayBuffer` 、另一个键入的数组或一个 JavaScript `Array` 。</span><span class="sxs-lookup"><span data-stu-id="d830c-120">The `baseArray` can be an `ArrayBuffer`, another typed array, or a JavaScript `Array`.</span></span> <span data-ttu-id="d830c-121">返回的键入的数组将使用 if 它是一个 ，或以其他方式创建和使用基础源数组 `baseArray` `ArrayBuffer` 的副本。</span><span class="sxs-lookup"><span data-stu-id="d830c-121">The returned typed array will use the `baseArray` if it is an `ArrayBuffer`, or otherwise create and use a copy of the underlying source array.</span></span>  
  
 <span data-ttu-id="d830c-122">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="d830c-122">Requires an active script context.</span></span>  
  
 <span data-ttu-id="d830c-123">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="d830c-123">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="d830c-124">要求</span><span class="sxs-lookup"><span data-stu-id="d830c-124">Requirements</span></span>  
 <span data-ttu-id="d830c-125">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="d830c-125">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d830c-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d830c-126">See Also</span></span>  
 [<span data-ttu-id="d830c-127">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="d830c-127">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
