---
description: 返回对象的原型。
title: JsGetPrototype 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetPrototype
helpviewer_keywords:
- JsGetPrototype function
ms.assetid: 05d743fc-103e-4a92-86f2-a063f39a2a6f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d64e8b090753e5d0627f0d40ee8745eeadd65227
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232697"
---
# <span data-ttu-id="71462-103">JsGetPrototype 函数</span><span class="sxs-lookup"><span data-stu-id="71462-103">JsGetPrototype Function</span></span>

<span data-ttu-id="71462-104">返回对象的原型。</span><span class="sxs-lookup"><span data-stu-id="71462-104">Returns the prototype of an object.</span></span>  
  
## <span data-ttu-id="71462-105">语法</span><span class="sxs-lookup"><span data-stu-id="71462-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPrototype(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *prototypeObject  
);  
```  
  
#### <span data-ttu-id="71462-106">参数</span><span class="sxs-lookup"><span data-stu-id="71462-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="71462-107">要返回其原型的对象。</span><span class="sxs-lookup"><span data-stu-id="71462-107">The object whose prototype is to be returned.</span></span>  
  
 `prototypeObject`  
 <span data-ttu-id="71462-108">对象的原型。</span><span class="sxs-lookup"><span data-stu-id="71462-108">The object's prototype.</span></span>  
  
## <span data-ttu-id="71462-109">返回值</span><span class="sxs-lookup"><span data-stu-id="71462-109">Return Value</span></span>  
 <span data-ttu-id="71462-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="71462-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="71462-111">备注</span><span class="sxs-lookup"><span data-stu-id="71462-111">Remarks</span></span>  
 <span data-ttu-id="71462-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="71462-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="71462-113">要求</span><span class="sxs-lookup"><span data-stu-id="71462-113">Requirements</span></span>  
 <span data-ttu-id="71462-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="71462-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="71462-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71462-115">See Also</span></span>  
 [<span data-ttu-id="71462-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="71462-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
