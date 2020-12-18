---
description: 设置对象的原型。
title: JsSetPrototype 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 88e1e421-4ae5-4e3b-b377-19256cc80e9f
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 860a7b8d85e043c87d554e09de50d0cb642b273a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232182"
---
# <span data-ttu-id="d664a-103">JsSetPrototype 函数</span><span class="sxs-lookup"><span data-stu-id="d664a-103">JsSetPrototype Function</span></span>

<span data-ttu-id="d664a-104">设置对象的原型。</span><span class="sxs-lookup"><span data-stu-id="d664a-104">Sets the prototype of an object.</span></span>  
  
## <span data-ttu-id="d664a-105">语法</span><span class="sxs-lookup"><span data-stu-id="d664a-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetPrototype(  
   _In_ JsValueRef object,  
   _In_ JsValueRef prototypeObject  
);  
```  
  
#### <span data-ttu-id="d664a-106">参数</span><span class="sxs-lookup"><span data-stu-id="d664a-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="d664a-107">要更改其原型的对象。</span><span class="sxs-lookup"><span data-stu-id="d664a-107">The object whose prototype is to be changed.</span></span>  
  
 `prototypeObject`  
 <span data-ttu-id="d664a-108">对象的新原型。</span><span class="sxs-lookup"><span data-stu-id="d664a-108">The object's new prototype.</span></span>  
  
## <span data-ttu-id="d664a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="d664a-109">Return Value</span></span>  
 <span data-ttu-id="d664a-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="d664a-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d664a-111">备注</span><span class="sxs-lookup"><span data-stu-id="d664a-111">Remarks</span></span>  
 <span data-ttu-id="d664a-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="d664a-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="d664a-113">要求</span><span class="sxs-lookup"><span data-stu-id="d664a-113">Requirements</span></span>  
 <span data-ttu-id="d664a-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="d664a-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d664a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d664a-115">See Also</span></span>  
 [<span data-ttu-id="d664a-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="d664a-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
