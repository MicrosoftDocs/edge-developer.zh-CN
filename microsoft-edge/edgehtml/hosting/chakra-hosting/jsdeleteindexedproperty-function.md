---
description: 删除对象指定索引的值。
title: JsDeleteIndexedProperty 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDeleteIndexedProperty
helpviewer_keywords:
- JsDeleteIndexedProperty function
ms.assetid: cc876839-2ecd-41a8-82d0-c19b3de944e3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1340b0204d3845d4a9bd3f18a58ec125a82d2bc0
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232545"
---
# <span data-ttu-id="76326-103">JsDeleteIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="76326-103">JsDeleteIndexedProperty Function</span></span>

<span data-ttu-id="76326-104">删除对象指定索引的值。</span><span class="sxs-lookup"><span data-stu-id="76326-104">Delete the value at the specified index of an object.</span></span>  
  
## <span data-ttu-id="76326-105">语法</span><span class="sxs-lookup"><span data-stu-id="76326-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDeleteIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index  
);  
```  
  
#### <span data-ttu-id="76326-106">参数</span><span class="sxs-lookup"><span data-stu-id="76326-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="76326-107">要操作的对象。</span><span class="sxs-lookup"><span data-stu-id="76326-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="76326-108">要删除的索引。</span><span class="sxs-lookup"><span data-stu-id="76326-108">The index to delete.</span></span>  
  
## <span data-ttu-id="76326-109">返回值</span><span class="sxs-lookup"><span data-stu-id="76326-109">Return Value</span></span>  
 <span data-ttu-id="76326-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="76326-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="76326-111">备注</span><span class="sxs-lookup"><span data-stu-id="76326-111">Remarks</span></span>  
 <span data-ttu-id="76326-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="76326-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="76326-113">要求</span><span class="sxs-lookup"><span data-stu-id="76326-113">Requirements</span></span>  
 <span data-ttu-id="76326-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="76326-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="76326-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76326-115">See Also</span></span>  
 [<span data-ttu-id="76326-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="76326-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
