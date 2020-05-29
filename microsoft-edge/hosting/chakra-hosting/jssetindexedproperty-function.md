---
description: 设置对象的指定索引处的值。
title: JsSetIndexedProperty 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetIndexedProperty
helpviewer_keywords:
- JsSetIndexedProperty function
ms.assetid: ccbc5bf4-d99b-485c-ab25-d2bd1ed2142e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 893849c42d9cbf0de160846d3397fcd5d7c77b7b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564174"
---
# <span data-ttu-id="ad58b-103">JsSetIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="ad58b-103">JsSetIndexedProperty Function</span></span>
<span data-ttu-id="ad58b-104">设置对象的指定索引处的值。</span><span class="sxs-lookup"><span data-stu-id="ad58b-104">Set the value at the specified index of an object.</span></span>  
  
## <span data-ttu-id="ad58b-105">语法</span><span class="sxs-lookup"><span data-stu-id="ad58b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _In_ JsValueRef value  
);  
```  
  
#### <span data-ttu-id="ad58b-106">参数</span><span class="sxs-lookup"><span data-stu-id="ad58b-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="ad58b-107">要操作的对象。</span><span class="sxs-lookup"><span data-stu-id="ad58b-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="ad58b-108">要设置的索引。</span><span class="sxs-lookup"><span data-stu-id="ad58b-108">The index to set.</span></span>  
  
 `value`  
 <span data-ttu-id="ad58b-109">要设置的值。</span><span class="sxs-lookup"><span data-stu-id="ad58b-109">The value to set.</span></span>  
  
## <span data-ttu-id="ad58b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="ad58b-110">Return Value</span></span>  
 <span data-ttu-id="ad58b-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="ad58b-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ad58b-112">备注</span><span class="sxs-lookup"><span data-stu-id="ad58b-112">Remarks</span></span>  
 <span data-ttu-id="ad58b-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="ad58b-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ad58b-114">要求</span><span class="sxs-lookup"><span data-stu-id="ad58b-114">Requirements</span></span>  
 <span data-ttu-id="ad58b-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="ad58b-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ad58b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad58b-116">See Also</span></span>  
 [<span data-ttu-id="ad58b-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="ad58b-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)