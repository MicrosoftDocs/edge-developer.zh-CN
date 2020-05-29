---
description: 获取 DataView 使用的基础内存存储。
title: JsGetDataViewStorage 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 7c2180e0-51d5-4cc8-ad21-8bf29ff7c583
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 54f8a91b6dea1e0997ad31d6585ea741fde8ba99
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563127"
---
# <span data-ttu-id="0d408-103">JsGetDataViewStorage 函数</span><span class="sxs-lookup"><span data-stu-id="0d408-103">JsGetDataViewStorage Function</span></span>
<span data-ttu-id="0d408-104">获取由 a 使用的基础内存存储 `DataView` 。</span><span class="sxs-lookup"><span data-stu-id="0d408-104">Obtains the underlying memory storage used by a `DataView`.</span></span>  
  
## <span data-ttu-id="0d408-105">语法</span><span class="sxs-lookup"><span data-stu-id="0d408-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetDataViewStorage(  
   _In_ JsValueRef dataView,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength  
);  
```  
  
#### <span data-ttu-id="0d408-106">参数</span><span class="sxs-lookup"><span data-stu-id="0d408-106">Parameters</span></span>  
 `dataView`  
 <span data-ttu-id="0d408-107">DataView 实例。</span><span class="sxs-lookup"><span data-stu-id="0d408-107">The DataView instance.</span></span>  
  
 `buffer`  
 <span data-ttu-id="0d408-108">DataView 的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="0d408-108">The DataView's buffer.</span></span> <span data-ttu-id="0d408-109">返回的缓冲区的生存期与的生存期相同 `DataView` 。</span><span class="sxs-lookup"><span data-stu-id="0d408-109">The lifetime of the buffer returned is the same as the lifetime of the `DataView`.</span></span> <span data-ttu-id="0d408-110">对于垃圾回收用途，缓冲区指针不会作为对的引用进行计数 `DataView` 。</span><span class="sxs-lookup"><span data-stu-id="0d408-110">The buffer pointer does not count as a reference to the `DataView` for the purpose of garbage collection.</span></span>  
  
 `bufferLength`  
 <span data-ttu-id="0d408-111">缓冲区中的字节数。</span><span class="sxs-lookup"><span data-stu-id="0d408-111">The number of bytes in the buffer.</span></span>  
  
## <span data-ttu-id="0d408-112">返回值</span><span class="sxs-lookup"><span data-stu-id="0d408-112">Return Value</span></span>  
 <span data-ttu-id="0d408-113">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="0d408-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0d408-114">备注</span><span class="sxs-lookup"><span data-stu-id="0d408-114">Remarks</span></span>  
 <span data-ttu-id="0d408-115">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="0d408-115">Requires an active script context.</span></span>  
  
 <span data-ttu-id="0d408-116">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="0d408-116">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="0d408-117">要求</span><span class="sxs-lookup"><span data-stu-id="0d408-117">Requirements</span></span>  
 <span data-ttu-id="0d408-118">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="0d408-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0d408-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d408-119">See Also</span></span>  
 [<span data-ttu-id="0d408-120">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="0d408-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)