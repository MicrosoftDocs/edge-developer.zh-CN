---
description: 创建 JavaScript `ArrayBuffer` 对象。
title: JsCreateArrayBuffer 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: c9e74184-7dd9-41a7-a1fe-9575e1701392
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3bee44d77f78bd35705211c598db78ab09000c71
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232197"
---
# <span data-ttu-id="0a9d2-103">JsCreateArrayBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="0a9d2-103">JsCreateArrayBuffer Function</span></span>

<span data-ttu-id="0a9d2-104">创建 JavaScript `ArrayBuffer` 对象。</span><span class="sxs-lookup"><span data-stu-id="0a9d2-104">Creates a JavaScript `ArrayBuffer` object.</span></span>  
  
## <span data-ttu-id="0a9d2-105">语法</span><span class="sxs-lookup"><span data-stu-id="0a9d2-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateArrayBuffer(  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="0a9d2-106">参数</span><span class="sxs-lookup"><span data-stu-id="0a9d2-106">Parameters</span></span>  
 `byteLength`  
 <span data-ttu-id="0a9d2-107">ArrayBuffer 中的字节数。</span><span class="sxs-lookup"><span data-stu-id="0a9d2-107">The number of bytes in the ArrayBuffer.</span></span>  
  
 `result`  
 <span data-ttu-id="0a9d2-108">新的 ArrayBuffer 对象。</span><span class="sxs-lookup"><span data-stu-id="0a9d2-108">The new ArrayBuffer object.</span></span>  
  
## <span data-ttu-id="0a9d2-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0a9d2-109">Return Value</span></span>  
 <span data-ttu-id="0a9d2-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="0a9d2-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0a9d2-111">备注</span><span class="sxs-lookup"><span data-stu-id="0a9d2-111">Remarks</span></span>  
 <span data-ttu-id="0a9d2-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="0a9d2-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="0a9d2-113">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="0a9d2-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="0a9d2-114">要求</span><span class="sxs-lookup"><span data-stu-id="0a9d2-114">Requirements</span></span>  
 <span data-ttu-id="0a9d2-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="0a9d2-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0a9d2-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a9d2-116">See Also</span></span>  
 [<span data-ttu-id="0a9d2-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="0a9d2-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
