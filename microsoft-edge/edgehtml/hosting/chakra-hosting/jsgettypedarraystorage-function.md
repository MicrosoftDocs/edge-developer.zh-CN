---
description: 获取类型数组使用的基础内存存储。
title: JsGetTypedArrayStorage 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 52e4ac5f-cc71-456d-95de-a48f7327503d
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 442727228433368de14bac528ea416fcc2a95fa8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232062"
---
# <span data-ttu-id="c498d-103">JsGetTypedArrayStorage 函数</span><span class="sxs-lookup"><span data-stu-id="c498d-103">JsGetTypedArrayStorage Function</span></span>

<span data-ttu-id="c498d-104">获取类型数组使用的基础内存存储。</span><span class="sxs-lookup"><span data-stu-id="c498d-104">Obtains the underlying memory storage used by a typed array.</span></span>  
  
## <span data-ttu-id="c498d-105">语法</span><span class="sxs-lookup"><span data-stu-id="c498d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTypedArrayStorage(  
   _In_ JsValueRef typedArray,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength,  
   _Out_opt_ JsTypedArrayType *arrayType,  
   _Out_opt_ int *elementSize  
);  
```  
  
#### <span data-ttu-id="c498d-106">参数</span><span class="sxs-lookup"><span data-stu-id="c498d-106">Parameters</span></span>  
 `typedArray`  
 <span data-ttu-id="c498d-107">键入的数组实例。</span><span class="sxs-lookup"><span data-stu-id="c498d-107">The typed array instance.</span></span>  
  
 `buffer`  
 <span data-ttu-id="c498d-108">数组的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c498d-108">The array's buffer.</span></span> <span data-ttu-id="c498d-109">返回的缓冲区的生存期与数组的生存期相同。</span><span class="sxs-lookup"><span data-stu-id="c498d-109">The lifetime of the buffer returned is the same as the lifetime of the array.</span></span> <span data-ttu-id="c498d-110">出于垃圾回收目的，缓冲区指针不计数为对数组的引用。</span><span class="sxs-lookup"><span data-stu-id="c498d-110">The buffer pointer does not count as a reference to the array for the purpose of garbage collection.</span></span>  
  
 `bufferLength`  
 <span data-ttu-id="c498d-111">缓冲区中的字节数。</span><span class="sxs-lookup"><span data-stu-id="c498d-111">The number of bytes in the buffer.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="c498d-112">数组的类型。</span><span class="sxs-lookup"><span data-stu-id="c498d-112">The type of the array.</span></span>  
  
 `elementSize`  
 <span data-ttu-id="c498d-113">数组元素的大小。</span><span class="sxs-lookup"><span data-stu-id="c498d-113">The size of an element of the array.</span></span>  
  
## <span data-ttu-id="c498d-114">返回值</span><span class="sxs-lookup"><span data-stu-id="c498d-114">Return Value</span></span>  
 <span data-ttu-id="c498d-115">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="c498d-115">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c498d-116">备注</span><span class="sxs-lookup"><span data-stu-id="c498d-116">Remarks</span></span>  
 <span data-ttu-id="c498d-117">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="c498d-117">Requires an active script context.</span></span>  
  
 <span data-ttu-id="c498d-118">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="c498d-118">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="c498d-119">要求</span><span class="sxs-lookup"><span data-stu-id="c498d-119">Requirements</span></span>  
 <span data-ttu-id="c498d-120">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="c498d-120">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c498d-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c498d-121">See Also</span></span>  
 [<span data-ttu-id="c498d-122">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="c498d-122">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
