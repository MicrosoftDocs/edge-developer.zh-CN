---
description: 将 `VARIANT` 作为 JavaScript 值的投影初始化传入的。
title: JsValueToVariant 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsValueToVariant
helpviewer_keywords:
- JsValueToVariant function
ms.assetid: 070244be-a69d-4b78-971b-69c0579c03cf
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d8748fddcc149cf09fbd46ad3ad489cd66200b71
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563061"
---
# <span data-ttu-id="4ccad-103">JsValueToVariant 函数</span><span class="sxs-lookup"><span data-stu-id="4ccad-103">JsValueToVariant Function</span></span>
<span data-ttu-id="4ccad-104">将 `VARIANT` 作为 JavaScript 值的投影初始化传入的。</span><span class="sxs-lookup"><span data-stu-id="4ccad-104">Initializes the passed in `VARIANT` as a projection of a JavaScript value.</span></span>  
  
## <span data-ttu-id="4ccad-105">语法</span><span class="sxs-lookup"><span data-stu-id="4ccad-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsValueToVariant(  
   _In_ JsValueRef object,  
   _Out_ VARIANT *variant  
);  
```  
  
#### <span data-ttu-id="4ccad-106">参数</span><span class="sxs-lookup"><span data-stu-id="4ccad-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="4ccad-107">项目的 JavaScript 值 `VARIANT` 。</span><span class="sxs-lookup"><span data-stu-id="4ccad-107">A JavaScript value to project as a `VARIANT`.</span></span>  
  
 `variant`  
 <span data-ttu-id="4ccad-108">指向 `VARIANT` 将初始化为投影的结构的指针。</span><span class="sxs-lookup"><span data-stu-id="4ccad-108">A pointer to a `VARIANT` struct that will be initialized as a projection.</span></span>  
  
## <span data-ttu-id="4ccad-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4ccad-109">Return Value</span></span>  
  
## <span data-ttu-id="4ccad-110">备注</span><span class="sxs-lookup"><span data-stu-id="4ccad-110">Remarks</span></span>  
 <span data-ttu-id="4ccad-111">`VARIANT`COM 自动化客户端可以使用投影来调入计划的 JavaScript 对象。</span><span class="sxs-lookup"><span data-stu-id="4ccad-111">The projection `VARIANT` can be used by COM automation clients to call into the projected JavaScript object.</span></span>  
  
 <span data-ttu-id="4ccad-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="4ccad-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="4ccad-113">要求</span><span class="sxs-lookup"><span data-stu-id="4ccad-113">Requirements</span></span>  
 <span data-ttu-id="4ccad-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="4ccad-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4ccad-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ccad-115">See Also</span></span>  
 [<span data-ttu-id="4ccad-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="4ccad-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)