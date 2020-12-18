---
description: 设置对象指定索引的值。
title: JsSetIndexedProperty 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetIndexedProperty
helpviewer_keywords:
- JsSetIndexedProperty function
ms.assetid: ccbc5bf4-d99b-485c-ab25-d2bd1ed2142e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1fa961750fa5db262e1512d8d26572280d5e726c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232179"
---
# <span data-ttu-id="2cb9a-103">JsSetIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="2cb9a-103">JsSetIndexedProperty Function</span></span>

<span data-ttu-id="2cb9a-104">设置对象指定索引的值。</span><span class="sxs-lookup"><span data-stu-id="2cb9a-104">Set the value at the specified index of an object.</span></span>  
  
## <span data-ttu-id="2cb9a-105">语法</span><span class="sxs-lookup"><span data-stu-id="2cb9a-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _In_ JsValueRef value  
);  
```  
  
#### <span data-ttu-id="2cb9a-106">参数</span><span class="sxs-lookup"><span data-stu-id="2cb9a-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="2cb9a-107">要操作的对象。</span><span class="sxs-lookup"><span data-stu-id="2cb9a-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="2cb9a-108">要设置的索引。</span><span class="sxs-lookup"><span data-stu-id="2cb9a-108">The index to set.</span></span>  
  
 `value`  
 <span data-ttu-id="2cb9a-109">要设置的值。</span><span class="sxs-lookup"><span data-stu-id="2cb9a-109">The value to set.</span></span>  
  
## <span data-ttu-id="2cb9a-110">返回值</span><span class="sxs-lookup"><span data-stu-id="2cb9a-110">Return Value</span></span>  
 <span data-ttu-id="2cb9a-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="2cb9a-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="2cb9a-112">备注</span><span class="sxs-lookup"><span data-stu-id="2cb9a-112">Remarks</span></span>  
 <span data-ttu-id="2cb9a-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="2cb9a-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="2cb9a-114">要求</span><span class="sxs-lookup"><span data-stu-id="2cb9a-114">Requirements</span></span>  
 <span data-ttu-id="2cb9a-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="2cb9a-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2cb9a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cb9a-116">See Also</span></span>  
 [<span data-ttu-id="2cb9a-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="2cb9a-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
