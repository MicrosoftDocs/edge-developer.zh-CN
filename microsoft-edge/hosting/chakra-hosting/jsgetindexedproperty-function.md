---
description: 检索对象的指定索引处的值。
title: JsGetIndexedProperty 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetIndexedProperty
helpviewer_keywords:
- JsGetIndexedProperty function
ms.assetid: f61ea388-0ae6-4a19-b3b5-75ed49a3f32d
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 7bb048b841462e27604ab169c69e4c051209a67d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564252"
---
# <span data-ttu-id="fb982-103">JsGetIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="fb982-103">JsGetIndexedProperty Function</span></span>
<span data-ttu-id="fb982-104">检索对象的指定索引处的值。</span><span class="sxs-lookup"><span data-stu-id="fb982-104">Retrieve the value at the specified index of an object.</span></span>  
  
## <span data-ttu-id="fb982-105">语法</span><span class="sxs-lookup"><span data-stu-id="fb982-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="fb982-106">参数</span><span class="sxs-lookup"><span data-stu-id="fb982-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="fb982-107">要操作的对象。</span><span class="sxs-lookup"><span data-stu-id="fb982-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="fb982-108">要检索的索引。</span><span class="sxs-lookup"><span data-stu-id="fb982-108">The index to retrieve.</span></span>  
  
 `result`  
 <span data-ttu-id="fb982-109">检索的值。</span><span class="sxs-lookup"><span data-stu-id="fb982-109">The retrieved value.</span></span>  
  
## <span data-ttu-id="fb982-110">返回值</span><span class="sxs-lookup"><span data-stu-id="fb982-110">Return Value</span></span>  
 <span data-ttu-id="fb982-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="fb982-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="fb982-112">备注</span><span class="sxs-lookup"><span data-stu-id="fb982-112">Remarks</span></span>  
 <span data-ttu-id="fb982-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="fb982-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="fb982-114">要求</span><span class="sxs-lookup"><span data-stu-id="fb982-114">Requirements</span></span>  
 <span data-ttu-id="fb982-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="fb982-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="fb982-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb982-116">See Also</span></span>  
 [<span data-ttu-id="fb982-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="fb982-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)