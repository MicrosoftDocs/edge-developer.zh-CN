---
description: 获取对象的属性。
title: JsGetProperty 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetProperty
helpviewer_keywords:
- JsGetProperty function
ms.assetid: 606bc14f-e849-4f88-a148-6660e923c07b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: ea0e5a3bad9363800d2b4a3a18ab932ecc384486
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564247"
---
# <span data-ttu-id="de10f-103">JsGetProperty 函数</span><span class="sxs-lookup"><span data-stu-id="de10f-103">JsGetProperty Function</span></span>
<span data-ttu-id="de10f-104">获取对象的属性。</span><span class="sxs-lookup"><span data-stu-id="de10f-104">Gets an object's property.</span></span>  
  
## <span data-ttu-id="de10f-105">语法</span><span class="sxs-lookup"><span data-stu-id="de10f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="de10f-106">参数</span><span class="sxs-lookup"><span data-stu-id="de10f-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="de10f-107">包含属性的对象。</span><span class="sxs-lookup"><span data-stu-id="de10f-107">The object that contains the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="de10f-108">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="de10f-108">The ID of the property.</span></span>  
  
 `value`  
 <span data-ttu-id="de10f-109">属性的值。</span><span class="sxs-lookup"><span data-stu-id="de10f-109">The value of the property.</span></span>  
  
## <span data-ttu-id="de10f-110">返回值</span><span class="sxs-lookup"><span data-stu-id="de10f-110">Return Value</span></span>  
 <span data-ttu-id="de10f-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="de10f-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="de10f-112">备注</span><span class="sxs-lookup"><span data-stu-id="de10f-112">Remarks</span></span>  
 <span data-ttu-id="de10f-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="de10f-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="de10f-114">要求</span><span class="sxs-lookup"><span data-stu-id="de10f-114">Requirements</span></span>  
 <span data-ttu-id="de10f-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="de10f-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="de10f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de10f-116">See Also</span></span>  
 [<span data-ttu-id="de10f-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="de10f-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)