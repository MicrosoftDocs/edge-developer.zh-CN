---
description: 创建 JavaScript 符号。
title: JsCreateSymbol 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 2fccc5d9-f857-46cd-9aeb-f0a2e7cdee6b
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 6a2f77f477aeebac150635d93cbd0cd043357256
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232415"
---
# <span data-ttu-id="af84d-103">JsCreateSymbol 函数</span><span class="sxs-lookup"><span data-stu-id="af84d-103">JsCreateSymbol Function</span></span>

<span data-ttu-id="af84d-104">创建 JavaScript 符号。</span><span class="sxs-lookup"><span data-stu-id="af84d-104">Creates a JavaScript symbol.</span></span>
  
## <span data-ttu-id="af84d-105">语法</span><span class="sxs-lookup"><span data-stu-id="af84d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateSymbol(  
   _In_ JsValueRef description,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="af84d-106">参数</span><span class="sxs-lookup"><span data-stu-id="af84d-106">Parameters</span></span>  
 `description`  
 <span data-ttu-id="af84d-107">符号的字符串说明。</span><span class="sxs-lookup"><span data-stu-id="af84d-107">The string description of the symbol.</span></span> <span data-ttu-id="af84d-108">可以是 null。</span><span class="sxs-lookup"><span data-stu-id="af84d-108">Can be null.</span></span>  
  
 `result`  
 <span data-ttu-id="af84d-109">新符号。</span><span class="sxs-lookup"><span data-stu-id="af84d-109">The new symbol.</span></span>  
  
## <span data-ttu-id="af84d-110">返回值</span><span class="sxs-lookup"><span data-stu-id="af84d-110">Return Value</span></span>  
 <span data-ttu-id="af84d-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="af84d-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="af84d-112">备注</span><span class="sxs-lookup"><span data-stu-id="af84d-112">Remarks</span></span>  
 <span data-ttu-id="af84d-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="af84d-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="af84d-114">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="af84d-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="af84d-115">要求</span><span class="sxs-lookup"><span data-stu-id="af84d-115">Requirements</span></span>  
 <span data-ttu-id="af84d-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="af84d-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="af84d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af84d-117">See Also</span></span>  
 [<span data-ttu-id="af84d-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="af84d-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
