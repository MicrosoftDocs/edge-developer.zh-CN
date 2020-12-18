---
description: 分析脚本并返回表示该脚本的函数。
title: JsParseScript 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsParseScript
helpviewer_keywords:
- JsParseScript function
ms.assetid: e9d0e363-7cbe-43eb-9dc0-1f47e586c9ab
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 656d9a992868a3cb892808775f160092b8eaf069
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232533"
---
# <span data-ttu-id="1fe8d-103">JsParseScript 函数</span><span class="sxs-lookup"><span data-stu-id="1fe8d-103">JsParseScript Function</span></span>

<span data-ttu-id="1fe8d-104">分析脚本并返回表示该脚本的函数。</span><span class="sxs-lookup"><span data-stu-id="1fe8d-104">Parses a script and returns a function representing the script.</span></span>  
  
## <span data-ttu-id="1fe8d-105">语法</span><span class="sxs-lookup"><span data-stu-id="1fe8d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsParseScript(  
   _In_z_ const wchar_t *script,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="1fe8d-106">参数</span><span class="sxs-lookup"><span data-stu-id="1fe8d-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="1fe8d-107">要分析的脚本。</span><span class="sxs-lookup"><span data-stu-id="1fe8d-107">The script to parse.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="1fe8d-108">用于标识可调试脚本上下文使用的脚本的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="1fe8d-108">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="1fe8d-109">脚本来自的位置。</span><span class="sxs-lookup"><span data-stu-id="1fe8d-109">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="1fe8d-110">一个代表脚本代码的函数。</span><span class="sxs-lookup"><span data-stu-id="1fe8d-110">A function representing the script code.</span></span>  
  
## <span data-ttu-id="1fe8d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="1fe8d-111">Return Value</span></span>  
 <span data-ttu-id="1fe8d-112">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="1fe8d-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="1fe8d-113">备注</span><span class="sxs-lookup"><span data-stu-id="1fe8d-113">Remarks</span></span>  
 <span data-ttu-id="1fe8d-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="1fe8d-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="1fe8d-115">要求</span><span class="sxs-lookup"><span data-stu-id="1fe8d-115">Requirements</span></span>  
 <span data-ttu-id="1fe8d-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="1fe8d-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1fe8d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fe8d-117">See Also</span></span>  
 [<span data-ttu-id="1fe8d-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="1fe8d-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
