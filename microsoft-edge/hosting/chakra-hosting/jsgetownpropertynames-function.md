---
description: 获取对象上的所有属性的列表。
title: JsGetOwnPropertyNames 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetOwnPropertyNames
helpviewer_keywords:
- JsGetOwnPropertyNames function
ms.assetid: 0c17ea06-b17f-4ea3-ad04-1259a4d1b6de
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5355caab864724d72fdb2c7abb3dc70e39662b55
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564249"
---
# <span data-ttu-id="6a37c-103">JsGetOwnPropertyNames 函数</span><span class="sxs-lookup"><span data-stu-id="6a37c-103">JsGetOwnPropertyNames Function</span></span>
<span data-ttu-id="6a37c-104">获取对象上的所有属性的列表。</span><span class="sxs-lookup"><span data-stu-id="6a37c-104">Gets the list of all properties on the object.</span></span>  
  
## <span data-ttu-id="6a37c-105">语法</span><span class="sxs-lookup"><span data-stu-id="6a37c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertyNames(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *propertyNames  
);  
```  
  
#### <span data-ttu-id="6a37c-106">参数</span><span class="sxs-lookup"><span data-stu-id="6a37c-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="6a37c-107">要从中获取属性名称的对象。</span><span class="sxs-lookup"><span data-stu-id="6a37c-107">The object from which to get the property names.</span></span>  
  
 `propertyNames`  
 <span data-ttu-id="6a37c-108">属性名称数组。</span><span class="sxs-lookup"><span data-stu-id="6a37c-108">An array of property names.</span></span>  
  
## <span data-ttu-id="6a37c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="6a37c-109">Return Value</span></span>  
 <span data-ttu-id="6a37c-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="6a37c-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6a37c-111">备注</span><span class="sxs-lookup"><span data-stu-id="6a37c-111">Remarks</span></span>  
 <span data-ttu-id="6a37c-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="6a37c-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="6a37c-113">要求</span><span class="sxs-lookup"><span data-stu-id="6a37c-113">Requirements</span></span>  
 <span data-ttu-id="6a37c-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="6a37c-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6a37c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a37c-115">See Also</span></span>  
 [<span data-ttu-id="6a37c-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="6a37c-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)