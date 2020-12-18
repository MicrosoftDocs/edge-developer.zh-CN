---
description: 执行脚本。
title: JsRunScript 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsRunScript
helpviewer_keywords:
- JsRunScript function
ms.assetid: 8d6b8c9a-af3a-4e21-a330-5a6b535423a3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d61771991e1d22a9d71a928d785390b814a992a8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232696"
---
# <span data-ttu-id="44c12-103">JsRunScript 函数</span><span class="sxs-lookup"><span data-stu-id="44c12-103">JsRunScript Function</span></span>

<span data-ttu-id="44c12-104">执行脚本。</span><span class="sxs-lookup"><span data-stu-id="44c12-104">Executes a script.</span></span>  
  
## <span data-ttu-id="44c12-105">语法</span><span class="sxs-lookup"><span data-stu-id="44c12-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsRunScript(  
   _In_z_ const wchar_t *script,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="44c12-106">参数</span><span class="sxs-lookup"><span data-stu-id="44c12-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="44c12-107">要运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="44c12-107">The script to run.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="44c12-108">用于标识可调试脚本上下文使用的脚本的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="44c12-108">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="44c12-109">脚本来自的位置。</span><span class="sxs-lookup"><span data-stu-id="44c12-109">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="44c12-110">脚本的结果（如果有）。</span><span class="sxs-lookup"><span data-stu-id="44c12-110">The result of the script, if any.</span></span> <span data-ttu-id="44c12-111">此参数可以是 null。</span><span class="sxs-lookup"><span data-stu-id="44c12-111">This parameter can be null.</span></span>  
  
## <span data-ttu-id="44c12-112">返回值</span><span class="sxs-lookup"><span data-stu-id="44c12-112">Return Value</span></span>  
 <span data-ttu-id="44c12-113">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="44c12-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="44c12-114">备注</span><span class="sxs-lookup"><span data-stu-id="44c12-114">Remarks</span></span>  
 <span data-ttu-id="44c12-115">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="44c12-115">Requires an active script context.</span></span>  
  
## <span data-ttu-id="44c12-116">要求</span><span class="sxs-lookup"><span data-stu-id="44c12-116">Requirements</span></span>  
 <span data-ttu-id="44c12-117">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="44c12-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="44c12-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44c12-118">See Also</span></span>  
 [<span data-ttu-id="44c12-119">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="44c12-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
