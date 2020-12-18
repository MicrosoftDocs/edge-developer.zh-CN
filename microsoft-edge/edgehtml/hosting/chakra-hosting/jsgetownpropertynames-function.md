---
description: 获取对象上所有属性的列表。
title: JsGetOwnPropertyNames 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetOwnPropertyNames
helpviewer_keywords:
- JsGetOwnPropertyNames function
ms.assetid: 0c17ea06-b17f-4ea3-ad04-1259a4d1b6de
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4d00788b6ef581b923413e5c71a63bb27398a326
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232005"
---
# <span data-ttu-id="2682a-103">JsGetOwnPropertyNames 函数</span><span class="sxs-lookup"><span data-stu-id="2682a-103">JsGetOwnPropertyNames Function</span></span>

<span data-ttu-id="2682a-104">获取对象上所有属性的列表。</span><span class="sxs-lookup"><span data-stu-id="2682a-104">Gets the list of all properties on the object.</span></span>  
  
## <span data-ttu-id="2682a-105">语法</span><span class="sxs-lookup"><span data-stu-id="2682a-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertyNames(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *propertyNames  
);  
```  
  
#### <span data-ttu-id="2682a-106">参数</span><span class="sxs-lookup"><span data-stu-id="2682a-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="2682a-107">要获取其属性名称的对象。</span><span class="sxs-lookup"><span data-stu-id="2682a-107">The object from which to get the property names.</span></span>  
  
 `propertyNames`  
 <span data-ttu-id="2682a-108">属性名称的数组。</span><span class="sxs-lookup"><span data-stu-id="2682a-108">An array of property names.</span></span>  
  
## <span data-ttu-id="2682a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2682a-109">Return Value</span></span>  
 <span data-ttu-id="2682a-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="2682a-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="2682a-111">备注</span><span class="sxs-lookup"><span data-stu-id="2682a-111">Remarks</span></span>  
 <span data-ttu-id="2682a-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="2682a-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="2682a-113">要求</span><span class="sxs-lookup"><span data-stu-id="2682a-113">Requirements</span></span>  
 <span data-ttu-id="2682a-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="2682a-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2682a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2682a-115">See Also</span></span>  
 [<span data-ttu-id="2682a-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="2682a-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
