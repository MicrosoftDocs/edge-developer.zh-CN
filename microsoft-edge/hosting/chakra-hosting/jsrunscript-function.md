---
description: 执行脚本。
title: JsRunScript 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsRunScript
helpviewer_keywords:
- JsRunScript function
ms.assetid: 8d6b8c9a-af3a-4e21-a330-5a6b535423a3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 49a06e4e6ad0c04e124b76f31d38b2e362e03f99
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564203"
---
# <span data-ttu-id="f3403-103">JsRunScript 函数</span><span class="sxs-lookup"><span data-stu-id="f3403-103">JsRunScript Function</span></span>
<span data-ttu-id="f3403-104">执行脚本。</span><span class="sxs-lookup"><span data-stu-id="f3403-104">Executes a script.</span></span>  
  
## <span data-ttu-id="f3403-105">语法</span><span class="sxs-lookup"><span data-stu-id="f3403-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsRunScript(  
   _In_z_ const wchar_t *script,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="f3403-106">参数</span><span class="sxs-lookup"><span data-stu-id="f3403-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="f3403-107">要运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="f3403-107">The script to run.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="f3403-108">标识可由可调试脚本上下文使用的脚本的 cookie。</span><span class="sxs-lookup"><span data-stu-id="f3403-108">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="f3403-109">脚本的来源位置。</span><span class="sxs-lookup"><span data-stu-id="f3403-109">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="f3403-110">脚本的结果（如果有）。</span><span class="sxs-lookup"><span data-stu-id="f3403-110">The result of the script, if any.</span></span> <span data-ttu-id="f3403-111">此参数可以为 null。</span><span class="sxs-lookup"><span data-stu-id="f3403-111">This parameter can be null.</span></span>  
  
## <span data-ttu-id="f3403-112">返回值</span><span class="sxs-lookup"><span data-stu-id="f3403-112">Return Value</span></span>  
 <span data-ttu-id="f3403-113">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="f3403-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="f3403-114">备注</span><span class="sxs-lookup"><span data-stu-id="f3403-114">Remarks</span></span>  
 <span data-ttu-id="f3403-115">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="f3403-115">Requires an active script context.</span></span>  
  
## <span data-ttu-id="f3403-116">要求</span><span class="sxs-lookup"><span data-stu-id="f3403-116">Requirements</span></span>  
 <span data-ttu-id="f3403-117">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="f3403-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f3403-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3403-118">See Also</span></span>  
 [<span data-ttu-id="f3403-119">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="f3403-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)