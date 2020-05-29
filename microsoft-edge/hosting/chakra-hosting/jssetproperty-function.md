---
description: 放置对象的属性。
title: JsSetProperty 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetProperty
helpviewer_keywords:
- JsSetProperty function
ms.assetid: 2c36bebf-ec86-425c-8131-2dd75fd30f40
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 2aba03a73f35284f79355a7d93161d9a9518012c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564167"
---
# <span data-ttu-id="40e9a-103">JsSetProperty 函数</span><span class="sxs-lookup"><span data-stu-id="40e9a-103">JsSetProperty Function</span></span>
<span data-ttu-id="40e9a-104">放置对象的属性。</span><span class="sxs-lookup"><span data-stu-id="40e9a-104">Puts an object's property.</span></span>  
  
## <span data-ttu-id="40e9a-105">语法</span><span class="sxs-lookup"><span data-stu-id="40e9a-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ JsValueRef value,  
   _In_ bool useStrictRules  
);  
```  
  
#### <span data-ttu-id="40e9a-106">参数</span><span class="sxs-lookup"><span data-stu-id="40e9a-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="40e9a-107">包含属性的对象。</span><span class="sxs-lookup"><span data-stu-id="40e9a-107">The object that contains the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="40e9a-108">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="40e9a-108">The ID of the property.</span></span>  
  
 `value`  
 <span data-ttu-id="40e9a-109">属性的新值。</span><span class="sxs-lookup"><span data-stu-id="40e9a-109">The new value of the property.</span></span>  
  
 `useStrictRules`  
 <span data-ttu-id="40e9a-110">属性集应遵循严格模式规则。</span><span class="sxs-lookup"><span data-stu-id="40e9a-110">The property set should follow strict mode rules.</span></span>  
  
## <span data-ttu-id="40e9a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="40e9a-111">Return Value</span></span>  
 <span data-ttu-id="40e9a-112">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="40e9a-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="40e9a-113">备注</span><span class="sxs-lookup"><span data-stu-id="40e9a-113">Remarks</span></span>  
 <span data-ttu-id="40e9a-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="40e9a-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="40e9a-115">要求</span><span class="sxs-lookup"><span data-stu-id="40e9a-115">Requirements</span></span>  
 <span data-ttu-id="40e9a-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="40e9a-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="40e9a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40e9a-117">See Also</span></span>  
 [<span data-ttu-id="40e9a-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="40e9a-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)