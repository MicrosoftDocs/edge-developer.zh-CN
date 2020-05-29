---
description: 分析脚本并返回表示脚本的函数。
title: JsParseScript 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsParseScript
helpviewer_keywords:
- JsParseScript function
ms.assetid: e9d0e363-7cbe-43eb-9dc0-1f47e586c9ab
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: dd224ef0e800f05e6e07580f545bc4af218b3498
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564217"
---
# <span data-ttu-id="7212c-103">JsParseScript 函数</span><span class="sxs-lookup"><span data-stu-id="7212c-103">JsParseScript Function</span></span>
<span data-ttu-id="7212c-104">分析脚本并返回表示脚本的函数。</span><span class="sxs-lookup"><span data-stu-id="7212c-104">Parses a script and returns a function representing the script.</span></span>  
  
## <span data-ttu-id="7212c-105">语法</span><span class="sxs-lookup"><span data-stu-id="7212c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsParseScript(  
   _In_z_ const wchar_t *script,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="7212c-106">参数</span><span class="sxs-lookup"><span data-stu-id="7212c-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="7212c-107">要分析的脚本。</span><span class="sxs-lookup"><span data-stu-id="7212c-107">The script to parse.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="7212c-108">标识可由可调试脚本上下文使用的脚本的 cookie。</span><span class="sxs-lookup"><span data-stu-id="7212c-108">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="7212c-109">脚本的来源位置。</span><span class="sxs-lookup"><span data-stu-id="7212c-109">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="7212c-110">表示脚本代码的函数。</span><span class="sxs-lookup"><span data-stu-id="7212c-110">A function representing the script code.</span></span>  
  
## <span data-ttu-id="7212c-111">返回值</span><span class="sxs-lookup"><span data-stu-id="7212c-111">Return Value</span></span>  
 <span data-ttu-id="7212c-112">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="7212c-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7212c-113">备注</span><span class="sxs-lookup"><span data-stu-id="7212c-113">Remarks</span></span>  
 <span data-ttu-id="7212c-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="7212c-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="7212c-115">要求</span><span class="sxs-lookup"><span data-stu-id="7212c-115">Requirements</span></span>  
 <span data-ttu-id="7212c-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="7212c-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7212c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7212c-117">See Also</span></span>  
 [<span data-ttu-id="7212c-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="7212c-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)