---
description: 获取类型化数组使用的基础内存存储。
title: JsGetTypedArrayStorage 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 52e4ac5f-cc71-456d-95de-a48f7327503d
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f03414d64fa819ac464217c8362d02e866d45296
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564243"
---
# <span data-ttu-id="4a909-103">JsGetTypedArrayStorage 函数</span><span class="sxs-lookup"><span data-stu-id="4a909-103">JsGetTypedArrayStorage Function</span></span>
<span data-ttu-id="4a909-104">获取类型化数组使用的基础内存存储。</span><span class="sxs-lookup"><span data-stu-id="4a909-104">Obtains the underlying memory storage used by a typed array.</span></span>  
  
## <span data-ttu-id="4a909-105">语法</span><span class="sxs-lookup"><span data-stu-id="4a909-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTypedArrayStorage(  
   _In_ JsValueRef typedArray,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength,  
   _Out_opt_ JsTypedArrayType *arrayType,  
   _Out_opt_ int *elementSize  
);  
```  
  
#### <span data-ttu-id="4a909-106">参数</span><span class="sxs-lookup"><span data-stu-id="4a909-106">Parameters</span></span>  
 `typedArray`  
 <span data-ttu-id="4a909-107">类型化数组实例。</span><span class="sxs-lookup"><span data-stu-id="4a909-107">The typed array instance.</span></span>  
  
 `buffer`  
 <span data-ttu-id="4a909-108">数组的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="4a909-108">The array's buffer.</span></span> <span data-ttu-id="4a909-109">返回的缓冲区的生存期与数组的生存期相同。</span><span class="sxs-lookup"><span data-stu-id="4a909-109">The lifetime of the buffer returned is the same as the lifetime of the array.</span></span> <span data-ttu-id="4a909-110">由于垃圾回收的目的，缓冲区指针不会作为数组的引用计数。</span><span class="sxs-lookup"><span data-stu-id="4a909-110">The buffer pointer does not count as a reference to the array for the purpose of garbage collection.</span></span>  
  
 `bufferLength`  
 <span data-ttu-id="4a909-111">缓冲区中的字节数。</span><span class="sxs-lookup"><span data-stu-id="4a909-111">The number of bytes in the buffer.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="4a909-112">数组的类型。</span><span class="sxs-lookup"><span data-stu-id="4a909-112">The type of the array.</span></span>  
  
 `elementSize`  
 <span data-ttu-id="4a909-113">数组元素的大小。</span><span class="sxs-lookup"><span data-stu-id="4a909-113">The size of an element of the array.</span></span>  
  
## <span data-ttu-id="4a909-114">返回值</span><span class="sxs-lookup"><span data-stu-id="4a909-114">Return Value</span></span>  
 <span data-ttu-id="4a909-115">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="4a909-115">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="4a909-116">备注</span><span class="sxs-lookup"><span data-stu-id="4a909-116">Remarks</span></span>  
 <span data-ttu-id="4a909-117">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="4a909-117">Requires an active script context.</span></span>  
  
 <span data-ttu-id="4a909-118">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="4a909-118">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="4a909-119">要求</span><span class="sxs-lookup"><span data-stu-id="4a909-119">Requirements</span></span>  
 <span data-ttu-id="4a909-120">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="4a909-120">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4a909-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a909-121">See Also</span></span>  
 [<span data-ttu-id="4a909-122">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="4a909-122">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)