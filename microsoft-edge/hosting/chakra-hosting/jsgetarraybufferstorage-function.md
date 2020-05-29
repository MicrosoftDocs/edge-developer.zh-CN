---
description: 获取 ArrayBuffer 使用的基础内存存储。
title: JsGetArrayBufferStorage 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 712ae298-36a9-47ef-b089-e51835c056bc
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1e8d265f3e81015ba9f5d0547b6b1c7246c23ce5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564263"
---
# <span data-ttu-id="e618a-103">JsGetArrayBufferStorage 函数</span><span class="sxs-lookup"><span data-stu-id="e618a-103">JsGetArrayBufferStorage Function</span></span>
<span data-ttu-id="e618a-104">获取由使用的基础内存存储 `ArrayBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="e618a-104">Obtains the underlying memory storage used by an `ArrayBuffer`.</span></span>  
  
## <span data-ttu-id="e618a-105">语法</span><span class="sxs-lookup"><span data-stu-id="e618a-105">Syntax</span></span>  
  
```cpp  
JsErrorCode STDAPI_ JsGetArrayBufferStorage(  
   _In_ JsValueRef arrayBuffer,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength  
);  
```  
  
#### <span data-ttu-id="e618a-106">参数</span><span class="sxs-lookup"><span data-stu-id="e618a-106">Parameters</span></span>  
 `arrayBuffer`  
 <span data-ttu-id="e618a-107">ArrayBuffer 实例。</span><span class="sxs-lookup"><span data-stu-id="e618a-107">The ArrayBuffer instance.</span></span>  
  
 `buffer`  
 <span data-ttu-id="e618a-108">ArrayBuffer 的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e618a-108">The ArrayBuffer's buffer.</span></span> <span data-ttu-id="e618a-109">返回的缓冲区的生存期与的生存期相同 `ArrayBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="e618a-109">The lifetime of the buffer returned is the same as the lifetime of the `ArrayBuffer`.</span></span> <span data-ttu-id="e618a-110">对于垃圾回收用途，缓冲区指针不会作为对的引用进行计数 `ArrayBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="e618a-110">The buffer pointer does not count as a reference to the `ArrayBuffer` for the purpose of garbage collection.</span></span>  
  
 `bufferLength`  
 <span data-ttu-id="e618a-111">缓冲区中的字节数。</span><span class="sxs-lookup"><span data-stu-id="e618a-111">The number of bytes in the buffer.</span></span>  
  
## <span data-ttu-id="e618a-112">返回值</span><span class="sxs-lookup"><span data-stu-id="e618a-112">Return Value</span></span>  
 <span data-ttu-id="e618a-113">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="e618a-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e618a-114">备注</span><span class="sxs-lookup"><span data-stu-id="e618a-114">Remarks</span></span>  
 <span data-ttu-id="e618a-115">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="e618a-115">Requires an active script context.</span></span>  
  
 <span data-ttu-id="e618a-116">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="e618a-116">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="e618a-117">要求</span><span class="sxs-lookup"><span data-stu-id="e618a-117">Requirements</span></span>  
 <span data-ttu-id="e618a-118">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="e618a-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e618a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e618a-119">See Also</span></span>  
 [<span data-ttu-id="e618a-120">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="e618a-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)