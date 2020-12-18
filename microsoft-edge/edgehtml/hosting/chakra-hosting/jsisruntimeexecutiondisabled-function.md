---
description: 返回一个值，该值指示是否在运行时禁用脚本执行。
title: JsIsRuntimeExecutionDisabled 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsIsRuntimeExecutionDisabled
helpviewer_keywords:
- JsIsRuntimeExecutionDisabled function
ms.assetid: 77490280-fb84-4614-a1f0-6ac31e3bd607
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0ce59c77525abdb2dd6cac71dde1378264395e79
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232022"
---
# <span data-ttu-id="48bfa-103">JsIsRuntimeExecutionDisabled 函数</span><span class="sxs-lookup"><span data-stu-id="48bfa-103">JsIsRuntimeExecutionDisabled Function</span></span>

<span data-ttu-id="48bfa-104">返回一个值，该值指示是否在运行时禁用脚本执行。</span><span class="sxs-lookup"><span data-stu-id="48bfa-104">Returns a value that indicates whether script execution is disabled in the runtime.</span></span>  
  
## <span data-ttu-id="48bfa-105">语法</span><span class="sxs-lookup"><span data-stu-id="48bfa-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIsRuntimeExecutionDisabled(    _In_ JsRuntimeHandle runtime,    _Out_ bool *isDisabled);  
```  
  
#### <span data-ttu-id="48bfa-106">参数</span><span class="sxs-lookup"><span data-stu-id="48bfa-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="48bfa-107">指定要检查执行是否禁用的运行时。</span><span class="sxs-lookup"><span data-stu-id="48bfa-107">Specifies the runtime to check if execution is disabled.</span></span>  
  
 `isDisabled`  
 `true` <span data-ttu-id="48bfa-108">如果禁用执行， `false` 否则。</span><span class="sxs-lookup"><span data-stu-id="48bfa-108">if execution is disabled, `false` otherwise.</span></span>  
  
## <span data-ttu-id="48bfa-109">返回值</span><span class="sxs-lookup"><span data-stu-id="48bfa-109">Return Value</span></span>  
 `JsNoError` <span data-ttu-id="48bfa-110">如果操作成功，则否则失败代码。</span><span class="sxs-lookup"><span data-stu-id="48bfa-110">if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="48bfa-111">要求</span><span class="sxs-lookup"><span data-stu-id="48bfa-111">Requirements</span></span>  
 <span data-ttu-id="48bfa-112">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="48bfa-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="48bfa-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48bfa-113">See Also</span></span>  
 [<span data-ttu-id="48bfa-114">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="48bfa-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
