---
description: '启用运行时中的脚本执行。 '
title: JsEnableRuntimeExecution 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsEnableRuntimeExecution
helpviewer_keywords:
- JsEnableRuntimeExecution function
ms.assetid: daa2036b-aef6-497d-a8ce-5a006b6ed13f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e87191197f70898b2f69d138026edd4e75cd5114
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232398"
---
# <span data-ttu-id="0d15d-103">JsEnableRuntimeExecution 函数</span><span class="sxs-lookup"><span data-stu-id="0d15d-103">JsEnableRuntimeExecution Function</span></span>

<span data-ttu-id="0d15d-104">启用运行时中的脚本执行。</span><span class="sxs-lookup"><span data-stu-id="0d15d-104">Enables script execution in a runtime.</span></span>  
  
## <span data-ttu-id="0d15d-105">语法</span><span class="sxs-lookup"><span data-stu-id="0d15d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsEnableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="0d15d-106">参数</span><span class="sxs-lookup"><span data-stu-id="0d15d-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="0d15d-107">要启用的运行时。</span><span class="sxs-lookup"><span data-stu-id="0d15d-107">The runtime to be enabled.</span></span>  
  
## <span data-ttu-id="0d15d-108">返回值</span><span class="sxs-lookup"><span data-stu-id="0d15d-108">Return Value</span></span>  
 <span data-ttu-id="0d15d-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="0d15d-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0d15d-110">备注</span><span class="sxs-lookup"><span data-stu-id="0d15d-110">Remarks</span></span>  
 <span data-ttu-id="0d15d-111">在已启用脚本执行的运行时中启用脚本执行是无操作。</span><span class="sxs-lookup"><span data-stu-id="0d15d-111">Enabling script execution in a runtime that already has script execution enabled is a no-op.</span></span>  
  
## <span data-ttu-id="0d15d-112">要求</span><span class="sxs-lookup"><span data-stu-id="0d15d-112">Requirements</span></span>  
 <span data-ttu-id="0d15d-113">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="0d15d-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0d15d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d15d-114">See Also</span></span>  
 [<span data-ttu-id="0d15d-115">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="0d15d-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
