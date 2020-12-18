---
description: 获取对象上所有符号属性的列表。
title: JsGetOwnPropertySymbols 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 57c431e3-de0b-4ed0-b750-87a86448daff
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d44da140f61a17d4cdc3a959c8fa7d017cbab1cc
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232566"
---
# <span data-ttu-id="0d7c4-103">JsGetOwnPropertySymbols 函数</span><span class="sxs-lookup"><span data-stu-id="0d7c4-103">JsGetOwnPropertySymbols Function</span></span>

<span data-ttu-id="0d7c4-104">获取对象上所有符号属性的列表。</span><span class="sxs-lookup"><span data-stu-id="0d7c4-104">Gets the list of all symbol properties on the object.</span></span>  
  
## <span data-ttu-id="0d7c4-105">语法</span><span class="sxs-lookup"><span data-stu-id="0d7c4-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertySymbols(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *propertySymbols  
);  
```  
  
#### <span data-ttu-id="0d7c4-106">参数</span><span class="sxs-lookup"><span data-stu-id="0d7c4-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="0d7c4-107">要获取其属性符号的对象。</span><span class="sxs-lookup"><span data-stu-id="0d7c4-107">The object from which to get the property symbols.</span></span>  
  
 `propertySymbols`  
 <span data-ttu-id="0d7c4-108">属性符号数组。</span><span class="sxs-lookup"><span data-stu-id="0d7c4-108">An array of property symbols.</span></span>  
  
## <span data-ttu-id="0d7c4-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0d7c4-109">Return Value</span></span>  
 <span data-ttu-id="0d7c4-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="0d7c4-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0d7c4-111">备注</span><span class="sxs-lookup"><span data-stu-id="0d7c4-111">Remarks</span></span>  
 <span data-ttu-id="0d7c4-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="0d7c4-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="0d7c4-113">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="0d7c4-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="0d7c4-114">要求</span><span class="sxs-lookup"><span data-stu-id="0d7c4-114">Requirements</span></span>  
 <span data-ttu-id="0d7c4-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="0d7c4-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0d7c4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d7c4-116">See Also</span></span>  
 [<span data-ttu-id="0d7c4-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="0d7c4-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
