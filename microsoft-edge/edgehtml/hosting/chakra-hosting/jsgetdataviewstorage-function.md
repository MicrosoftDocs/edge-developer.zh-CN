---
description: 获取 DataView 使用的基础内存存储。
title: JsGetDataViewStorage 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 7c2180e0-51d5-4cc8-ad21-8bf29ff7c583
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 55f357e4a94b1edbc417ebb14ab99db11083dff4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232446"
---
# <span data-ttu-id="03609-103">JsGetDataViewStorage 函数</span><span class="sxs-lookup"><span data-stu-id="03609-103">JsGetDataViewStorage Function</span></span>

<span data-ttu-id="03609-104">获取 .使用的基础内存存储 `DataView` 。</span><span class="sxs-lookup"><span data-stu-id="03609-104">Obtains the underlying memory storage used by a `DataView`.</span></span>  
  
## <span data-ttu-id="03609-105">语法</span><span class="sxs-lookup"><span data-stu-id="03609-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetDataViewStorage(  
   _In_ JsValueRef dataView,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength  
);  
```  
  
#### <span data-ttu-id="03609-106">参数</span><span class="sxs-lookup"><span data-stu-id="03609-106">Parameters</span></span>  
 `dataView`  
 <span data-ttu-id="03609-107">DataView 实例。</span><span class="sxs-lookup"><span data-stu-id="03609-107">The DataView instance.</span></span>  
  
 `buffer`  
 <span data-ttu-id="03609-108">DataView 的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="03609-108">The DataView's buffer.</span></span> <span data-ttu-id="03609-109">返回的缓冲区的生存期与 `DataView`</span><span class="sxs-lookup"><span data-stu-id="03609-109">The lifetime of the buffer returned is the same as the lifetime of the `DataView`.</span></span> <span data-ttu-id="03609-110">出于垃圾回收目的，缓冲区指针 `DataView` 不计数为对它的引用。</span><span class="sxs-lookup"><span data-stu-id="03609-110">The buffer pointer does not count as a reference to the `DataView` for the purpose of garbage collection.</span></span>  
  
 `bufferLength`  
 <span data-ttu-id="03609-111">缓冲区中的字节数。</span><span class="sxs-lookup"><span data-stu-id="03609-111">The number of bytes in the buffer.</span></span>  
  
## <span data-ttu-id="03609-112">返回值</span><span class="sxs-lookup"><span data-stu-id="03609-112">Return Value</span></span>  
 <span data-ttu-id="03609-113">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="03609-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="03609-114">备注</span><span class="sxs-lookup"><span data-stu-id="03609-114">Remarks</span></span>  
 <span data-ttu-id="03609-115">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="03609-115">Requires an active script context.</span></span>  
  
 <span data-ttu-id="03609-116">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="03609-116">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="03609-117">要求</span><span class="sxs-lookup"><span data-stu-id="03609-117">Requirements</span></span>  
 <span data-ttu-id="03609-118">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="03609-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="03609-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03609-119">See Also</span></span>  
 [<span data-ttu-id="03609-120">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="03609-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
