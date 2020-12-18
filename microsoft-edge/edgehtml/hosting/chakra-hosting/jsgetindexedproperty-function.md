---
description: 检索对象指定索引的值。
title: JsGetIndexedProperty 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetIndexedProperty
helpviewer_keywords:
- JsGetIndexedProperty function
ms.assetid: f61ea388-0ae6-4a19-b3b5-75ed49a3f32d
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: bd0246464d00884ca71fd8d3564ce775415f6267
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232028"
---
# <span data-ttu-id="fbabb-103">JsGetIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="fbabb-103">JsGetIndexedProperty Function</span></span>

<span data-ttu-id="fbabb-104">检索对象指定索引的值。</span><span class="sxs-lookup"><span data-stu-id="fbabb-104">Retrieve the value at the specified index of an object.</span></span>  
  
## <span data-ttu-id="fbabb-105">语法</span><span class="sxs-lookup"><span data-stu-id="fbabb-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="fbabb-106">参数</span><span class="sxs-lookup"><span data-stu-id="fbabb-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="fbabb-107">要操作的对象。</span><span class="sxs-lookup"><span data-stu-id="fbabb-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="fbabb-108">要检索的索引。</span><span class="sxs-lookup"><span data-stu-id="fbabb-108">The index to retrieve.</span></span>  
  
 `result`  
 <span data-ttu-id="fbabb-109">检索到的值。</span><span class="sxs-lookup"><span data-stu-id="fbabb-109">The retrieved value.</span></span>  
  
## <span data-ttu-id="fbabb-110">返回值</span><span class="sxs-lookup"><span data-stu-id="fbabb-110">Return Value</span></span>  
 <span data-ttu-id="fbabb-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="fbabb-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="fbabb-112">备注</span><span class="sxs-lookup"><span data-stu-id="fbabb-112">Remarks</span></span>  
 <span data-ttu-id="fbabb-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="fbabb-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="fbabb-114">要求</span><span class="sxs-lookup"><span data-stu-id="fbabb-114">Requirements</span></span>  
 <span data-ttu-id="fbabb-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="fbabb-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="fbabb-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbabb-116">See Also</span></span>  
 [<span data-ttu-id="fbabb-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="fbabb-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
