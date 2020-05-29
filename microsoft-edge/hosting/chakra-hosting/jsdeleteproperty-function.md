---
description: 删除对象的属性。
title: JsDeleteProperty 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDeleteProperty
helpviewer_keywords:
- JsDeleteProperty function
ms.assetid: 0f6ac6a7-3576-42f5-98d0-1c06542c8149
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c5539238324d59126b45f19fa9a6f8facc0f2ee3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563140"
---
# <span data-ttu-id="0a7a9-103">JsDeleteProperty 函数</span><span class="sxs-lookup"><span data-stu-id="0a7a9-103">JsDeleteProperty Function</span></span>
<span data-ttu-id="0a7a9-104">删除对象的属性。</span><span class="sxs-lookup"><span data-stu-id="0a7a9-104">Deletes an object's property.</span></span>  
  
## <span data-ttu-id="0a7a9-105">语法</span><span class="sxs-lookup"><span data-stu-id="0a7a9-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDeleteProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ bool useStrictRules,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="0a7a9-106">参数</span><span class="sxs-lookup"><span data-stu-id="0a7a9-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="0a7a9-107">包含属性的对象。</span><span class="sxs-lookup"><span data-stu-id="0a7a9-107">The object that contains the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="0a7a9-108">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="0a7a9-108">The ID of the property.</span></span>  
  
 `useStrictRules`  
 <span data-ttu-id="0a7a9-109">属性集应遵循严格模式规则。</span><span class="sxs-lookup"><span data-stu-id="0a7a9-109">The property set should follow strict mode rules.</span></span>  
  
 `result`  
 <span data-ttu-id="0a7a9-110">是否已删除该属性。</span><span class="sxs-lookup"><span data-stu-id="0a7a9-110">Whether the property was deleted.</span></span>  
  
## <span data-ttu-id="0a7a9-111">返回值</span><span class="sxs-lookup"><span data-stu-id="0a7a9-111">Return Value</span></span>  
 <span data-ttu-id="0a7a9-112">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="0a7a9-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0a7a9-113">备注</span><span class="sxs-lookup"><span data-stu-id="0a7a9-113">Remarks</span></span>  
 <span data-ttu-id="0a7a9-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="0a7a9-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="0a7a9-115">要求</span><span class="sxs-lookup"><span data-stu-id="0a7a9-115">Requirements</span></span>  
 <span data-ttu-id="0a7a9-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="0a7a9-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0a7a9-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a7a9-117">See Also</span></span>  
 [<span data-ttu-id="0a7a9-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="0a7a9-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)