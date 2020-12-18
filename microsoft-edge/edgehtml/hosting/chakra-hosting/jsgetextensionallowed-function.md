---
description: 返回一个值，该值指示对象是否可扩展。
title: JsGetExtensionAllowed 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetExtensionAllowed
helpviewer_keywords:
- JsGetExtensionAllowed function
ms.assetid: 839054a1-d643-47d9-89db-6a015bba0d91
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7bc9e3265b48a27d0da4bc4646b2b5e3b1765b86
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232445"
---
# <span data-ttu-id="9d147-103">JsGetExtensionAllowed 函数</span><span class="sxs-lookup"><span data-stu-id="9d147-103">JsGetExtensionAllowed Function</span></span>

<span data-ttu-id="9d147-104">返回一个值，该值指示对象是否可扩展。</span><span class="sxs-lookup"><span data-stu-id="9d147-104">Returns a value that indicates whether an object is extensible or not.</span></span>  
  
## <span data-ttu-id="9d147-105">语法</span><span class="sxs-lookup"><span data-stu-id="9d147-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetExtensionAllowed(  
   _In_ JsValueRef object,  
   _Out_ bool *value  
);  
```  
  
#### <span data-ttu-id="9d147-106">参数</span><span class="sxs-lookup"><span data-stu-id="9d147-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="9d147-107">要测试的对象。</span><span class="sxs-lookup"><span data-stu-id="9d147-107">The object to test.</span></span>  
  
 `value`  
 <span data-ttu-id="9d147-108">对象是否可扩展。</span><span class="sxs-lookup"><span data-stu-id="9d147-108">Whether the object is extensible or not.</span></span>  
  
## <span data-ttu-id="9d147-109">返回值</span><span class="sxs-lookup"><span data-stu-id="9d147-109">Return Value</span></span>  
 <span data-ttu-id="9d147-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="9d147-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9d147-111">备注</span><span class="sxs-lookup"><span data-stu-id="9d147-111">Remarks</span></span>  
 <span data-ttu-id="9d147-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="9d147-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="9d147-113">要求</span><span class="sxs-lookup"><span data-stu-id="9d147-113">Requirements</span></span>  
 <span data-ttu-id="9d147-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="9d147-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9d147-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d147-115">See Also</span></span>  
 [<span data-ttu-id="9d147-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="9d147-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
