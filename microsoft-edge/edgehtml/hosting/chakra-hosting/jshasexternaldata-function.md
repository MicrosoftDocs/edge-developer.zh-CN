---
description: 确定对象是否是外部对象。
title: JsHasExternalData 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsHasExternalData
helpviewer_keywords:
- JsHasExternalData function
ms.assetid: a077e3ac-4f6f-4d94-8398-f1b5cc4c18e0
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d73333215a33fc409190a0e33fa616b6350fb2a3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232060"
---
# <span data-ttu-id="77eea-103">JsHasExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="77eea-103">JsHasExternalData Function</span></span>

<span data-ttu-id="77eea-104">确定对象是否是外部对象。</span><span class="sxs-lookup"><span data-stu-id="77eea-104">Determines whether an object is an external object.</span></span>  
  
## <span data-ttu-id="77eea-105">语法</span><span class="sxs-lookup"><span data-stu-id="77eea-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasExternalData(  
   _In_ JsValueRef object,  
   _Out_ bool *value  
);  
```  
  
#### <span data-ttu-id="77eea-106">参数</span><span class="sxs-lookup"><span data-stu-id="77eea-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="77eea-107">对象。</span><span class="sxs-lookup"><span data-stu-id="77eea-107">The object.</span></span>  
  
 `value`  
 <span data-ttu-id="77eea-108">对象是否是外部对象。</span><span class="sxs-lookup"><span data-stu-id="77eea-108">Whether the object is an external object.</span></span>  
  
## <span data-ttu-id="77eea-109">返回值</span><span class="sxs-lookup"><span data-stu-id="77eea-109">Return Value</span></span>  
 <span data-ttu-id="77eea-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="77eea-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="77eea-111">备注</span><span class="sxs-lookup"><span data-stu-id="77eea-111">Remarks</span></span>  
 <span data-ttu-id="77eea-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="77eea-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="77eea-113">要求</span><span class="sxs-lookup"><span data-stu-id="77eea-113">Requirements</span></span>  
 <span data-ttu-id="77eea-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="77eea-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="77eea-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77eea-115">See Also</span></span>  
 [<span data-ttu-id="77eea-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="77eea-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
