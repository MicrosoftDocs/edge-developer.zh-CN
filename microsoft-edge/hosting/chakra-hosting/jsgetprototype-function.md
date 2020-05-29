---
description: 返回对象的原型。
title: JsGetPrototype 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetPrototype
helpviewer_keywords:
- JsGetPrototype function
ms.assetid: 05d743fc-103e-4a92-86f2-a063f39a2a6f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 12708634fea9e8f9fd1205514845b1cb9760ee9e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563115"
---
# <span data-ttu-id="77b94-103">JsGetPrototype 函数</span><span class="sxs-lookup"><span data-stu-id="77b94-103">JsGetPrototype Function</span></span>
<span data-ttu-id="77b94-104">返回对象的原型。</span><span class="sxs-lookup"><span data-stu-id="77b94-104">Returns the prototype of an object.</span></span>  
  
## <span data-ttu-id="77b94-105">语法</span><span class="sxs-lookup"><span data-stu-id="77b94-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPrototype(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *prototypeObject  
);  
```  
  
#### <span data-ttu-id="77b94-106">参数</span><span class="sxs-lookup"><span data-stu-id="77b94-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="77b94-107">要返回其原型的对象。</span><span class="sxs-lookup"><span data-stu-id="77b94-107">The object whose prototype is to be returned.</span></span>  
  
 `prototypeObject`  
 <span data-ttu-id="77b94-108">对象的原型。</span><span class="sxs-lookup"><span data-stu-id="77b94-108">The object's prototype.</span></span>  
  
## <span data-ttu-id="77b94-109">返回值</span><span class="sxs-lookup"><span data-stu-id="77b94-109">Return Value</span></span>  
 <span data-ttu-id="77b94-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="77b94-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="77b94-111">备注</span><span class="sxs-lookup"><span data-stu-id="77b94-111">Remarks</span></span>  
 <span data-ttu-id="77b94-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="77b94-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="77b94-113">要求</span><span class="sxs-lookup"><span data-stu-id="77b94-113">Requirements</span></span>  
 <span data-ttu-id="77b94-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="77b94-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="77b94-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77b94-115">See Also</span></span>  
 [<span data-ttu-id="77b94-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="77b94-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)