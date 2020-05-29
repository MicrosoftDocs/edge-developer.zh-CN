---
description: 从属性描述符定义新对象的自己的属性。
title: JsDefineProperty 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDefineProperty
helpviewer_keywords:
- JsDefineProperty function
ms.assetid: b2cf48d6-eb40-457c-aa8b-b16a50dc5d6a
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b3c9641b4d00540670b44d1718a6aa2aca3b02de
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563142"
---
# <span data-ttu-id="29821-103">JsDefineProperty 函数</span><span class="sxs-lookup"><span data-stu-id="29821-103">JsDefineProperty Function</span></span>
<span data-ttu-id="29821-104">从属性描述符定义新对象的自己的属性。</span><span class="sxs-lookup"><span data-stu-id="29821-104">Defines a new object's own property from a property descriptor.</span></span>  
  
## <span data-ttu-id="29821-105">语法</span><span class="sxs-lookup"><span data-stu-id="29821-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDefineProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ JsValueRef propertyDescriptor,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="29821-106">参数</span><span class="sxs-lookup"><span data-stu-id="29821-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="29821-107">具有属性的对象。</span><span class="sxs-lookup"><span data-stu-id="29821-107">The object that has the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="29821-108">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="29821-108">The ID of the property.</span></span>  
  
 `propertyDescriptor`  
 <span data-ttu-id="29821-109">属性描述符。</span><span class="sxs-lookup"><span data-stu-id="29821-109">The property descriptor.</span></span>  
  
 `result`  
 <span data-ttu-id="29821-110">是否已定义属性。</span><span class="sxs-lookup"><span data-stu-id="29821-110">Whether the property was defined.</span></span>  
  
## <span data-ttu-id="29821-111">返回值</span><span class="sxs-lookup"><span data-stu-id="29821-111">Return Value</span></span>  
 <span data-ttu-id="29821-112">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="29821-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="29821-113">备注</span><span class="sxs-lookup"><span data-stu-id="29821-113">Remarks</span></span>  
 <span data-ttu-id="29821-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="29821-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="29821-115">要求</span><span class="sxs-lookup"><span data-stu-id="29821-115">Requirements</span></span>  
 <span data-ttu-id="29821-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="29821-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="29821-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29821-117">See Also</span></span>  
 [<span data-ttu-id="29821-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="29821-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)