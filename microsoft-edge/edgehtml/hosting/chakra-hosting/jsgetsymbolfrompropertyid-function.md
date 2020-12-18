---
description: 获取与属性 ID 关联的符号。
title: JsGetSymbolFromPropertyId 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 0e822cb4-ba9e-44df-bf3a-fae97c354daa
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 472253aea228ca0374c42d99710a7a7ab528184c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232767"
---
# <span data-ttu-id="6cc0b-103">JsGetSymbolFromPropertyId 函数</span><span class="sxs-lookup"><span data-stu-id="6cc0b-103">JsGetSymbolFromPropertyId Function</span></span>

<span data-ttu-id="6cc0b-104">获取与属性 ID 关联的符号。</span><span class="sxs-lookup"><span data-stu-id="6cc0b-104">Gets the symbol associated with the property ID.</span></span>  
  
## <span data-ttu-id="6cc0b-105">语法</span><span class="sxs-lookup"><span data-stu-id="6cc0b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetSymbolFromPropertyId(  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *symbol  
);  
```  
  
#### <span data-ttu-id="6cc0b-106">参数</span><span class="sxs-lookup"><span data-stu-id="6cc0b-106">Parameters</span></span>  
 `propertyId`  
 <span data-ttu-id="6cc0b-107">要获取其符号的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="6cc0b-107">The property ID to get the symbol of.</span></span>  
  
 `symbol`  
 <span data-ttu-id="6cc0b-108">与属性 ID 关联的符号。</span><span class="sxs-lookup"><span data-stu-id="6cc0b-108">The symbol associated with the property ID.</span></span>  
  
## <span data-ttu-id="6cc0b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="6cc0b-109">Return Value</span></span>  
 <span data-ttu-id="6cc0b-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="6cc0b-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6cc0b-111">备注</span><span class="sxs-lookup"><span data-stu-id="6cc0b-111">Remarks</span></span>  
 <span data-ttu-id="6cc0b-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="6cc0b-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="6cc0b-113">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="6cc0b-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="6cc0b-114">要求</span><span class="sxs-lookup"><span data-stu-id="6cc0b-114">Requirements</span></span>  
 <span data-ttu-id="6cc0b-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="6cc0b-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6cc0b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cc0b-116">See Also</span></span>  
 [<span data-ttu-id="6cc0b-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="6cc0b-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
