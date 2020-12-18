---
description: 获取 ArrayBuffer 使用的基础内存存储。
title: JsGetArrayBufferStorage 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 712ae298-36a9-47ef-b089-e51835c056bc
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 64b031a81506e68322759eff49da7467cac6f219
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232325"
---
# <span data-ttu-id="624c7-103">JsGetArrayBufferStorage 函数</span><span class="sxs-lookup"><span data-stu-id="624c7-103">JsGetArrayBufferStorage Function</span></span>

<span data-ttu-id="624c7-104">获取由 . `ArrayBuffer`</span><span class="sxs-lookup"><span data-stu-id="624c7-104">Obtains the underlying memory storage used by an `ArrayBuffer`.</span></span>  
  
## <span data-ttu-id="624c7-105">语法</span><span class="sxs-lookup"><span data-stu-id="624c7-105">Syntax</span></span>  
  
```cpp  
JsErrorCode STDAPI_ JsGetArrayBufferStorage(  
   _In_ JsValueRef arrayBuffer,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength  
);  
```  
  
#### <span data-ttu-id="624c7-106">参数</span><span class="sxs-lookup"><span data-stu-id="624c7-106">Parameters</span></span>  
 `arrayBuffer`  
 <span data-ttu-id="624c7-107">ArrayBuffer 实例。</span><span class="sxs-lookup"><span data-stu-id="624c7-107">The ArrayBuffer instance.</span></span>  
  
 `buffer`  
 <span data-ttu-id="624c7-108">ArrayBuffer 的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="624c7-108">The ArrayBuffer's buffer.</span></span> <span data-ttu-id="624c7-109">返回的缓冲区的生存期与 `ArrayBuffer`</span><span class="sxs-lookup"><span data-stu-id="624c7-109">The lifetime of the buffer returned is the same as the lifetime of the `ArrayBuffer`.</span></span> <span data-ttu-id="624c7-110">出于垃圾回收目的，缓冲区指针 `ArrayBuffer` 不计数为对它的引用。</span><span class="sxs-lookup"><span data-stu-id="624c7-110">The buffer pointer does not count as a reference to the `ArrayBuffer` for the purpose of garbage collection.</span></span>  
  
 `bufferLength`  
 <span data-ttu-id="624c7-111">缓冲区中的字节数。</span><span class="sxs-lookup"><span data-stu-id="624c7-111">The number of bytes in the buffer.</span></span>  
  
## <span data-ttu-id="624c7-112">返回值</span><span class="sxs-lookup"><span data-stu-id="624c7-112">Return Value</span></span>  
 <span data-ttu-id="624c7-113">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="624c7-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="624c7-114">备注</span><span class="sxs-lookup"><span data-stu-id="624c7-114">Remarks</span></span>  
 <span data-ttu-id="624c7-115">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="624c7-115">Requires an active script context.</span></span>  
  
 <span data-ttu-id="624c7-116">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="624c7-116">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="624c7-117">要求</span><span class="sxs-lookup"><span data-stu-id="624c7-117">Requirements</span></span>  
 <span data-ttu-id="624c7-118">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="624c7-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="624c7-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="624c7-119">See Also</span></span>  
 [<span data-ttu-id="624c7-120">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="624c7-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
