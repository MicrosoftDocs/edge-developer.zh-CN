---
description: 使对象不可扩展。
title: JsPreventExtension 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsPreventExtension
helpviewer_keywords:
- JsPreventExtension function
ms.assetid: 8da07e20-d076-4ae4-9fb0-3f3c141518c2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1904756a932bd581e05ec474004af7107da3f64b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232528"
---
# <span data-ttu-id="505b5-103">JsPreventExtension 函数</span><span class="sxs-lookup"><span data-stu-id="505b5-103">JsPreventExtension Function</span></span>

<span data-ttu-id="505b5-104">使对象不可扩展。</span><span class="sxs-lookup"><span data-stu-id="505b5-104">Makes an object non-extensible.</span></span>  
  
## <span data-ttu-id="505b5-105">语法</span><span class="sxs-lookup"><span data-stu-id="505b5-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsPreventExtension(  
   _In_ JsValueRef object  
);  
```  
  
#### <span data-ttu-id="505b5-106">参数</span><span class="sxs-lookup"><span data-stu-id="505b5-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="505b5-107">使不可扩展的对象。</span><span class="sxs-lookup"><span data-stu-id="505b5-107">The object to make non-extensible.</span></span>  
  
## <span data-ttu-id="505b5-108">返回值</span><span class="sxs-lookup"><span data-stu-id="505b5-108">Return Value</span></span>  
 <span data-ttu-id="505b5-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="505b5-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="505b5-110">备注</span><span class="sxs-lookup"><span data-stu-id="505b5-110">Remarks</span></span>  
 <span data-ttu-id="505b5-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="505b5-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="505b5-112">要求</span><span class="sxs-lookup"><span data-stu-id="505b5-112">Requirements</span></span>  
 <span data-ttu-id="505b5-113">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="505b5-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="505b5-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="505b5-114">See Also</span></span>  
 [<span data-ttu-id="505b5-115">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="505b5-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
