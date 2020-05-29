---
description: 获取与属性 ID 关联的符号。
title: JsGetSymbolFromPropertyId 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0e822cb4-ba9e-44df-bf3a-fae97c354daa
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6902384772f29f80751660ce2d4a295d2ea620ab
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563104"
---
# <span data-ttu-id="8e118-103">JsGetSymbolFromPropertyId 函数</span><span class="sxs-lookup"><span data-stu-id="8e118-103">JsGetSymbolFromPropertyId Function</span></span>
<span data-ttu-id="8e118-104">获取与属性 ID 关联的符号。</span><span class="sxs-lookup"><span data-stu-id="8e118-104">Gets the symbol associated with the property ID.</span></span>  
  
## <span data-ttu-id="8e118-105">语法</span><span class="sxs-lookup"><span data-stu-id="8e118-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetSymbolFromPropertyId(  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *symbol  
);  
```  
  
#### <span data-ttu-id="8e118-106">参数</span><span class="sxs-lookup"><span data-stu-id="8e118-106">Parameters</span></span>  
 `propertyId`  
 <span data-ttu-id="8e118-107">要获取其符号的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="8e118-107">The property ID to get the symbol of.</span></span>  
  
 `symbol`  
 <span data-ttu-id="8e118-108">与属性 ID 关联的符号。</span><span class="sxs-lookup"><span data-stu-id="8e118-108">The symbol associated with the property ID.</span></span>  
  
## <span data-ttu-id="8e118-109">返回值</span><span class="sxs-lookup"><span data-stu-id="8e118-109">Return Value</span></span>  
 <span data-ttu-id="8e118-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="8e118-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="8e118-111">备注</span><span class="sxs-lookup"><span data-stu-id="8e118-111">Remarks</span></span>  
 <span data-ttu-id="8e118-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="8e118-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="8e118-113">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="8e118-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="8e118-114">要求</span><span class="sxs-lookup"><span data-stu-id="8e118-114">Requirements</span></span>  
 <span data-ttu-id="8e118-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="8e118-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="8e118-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e118-116">See Also</span></span>  
 [<span data-ttu-id="8e118-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="8e118-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)