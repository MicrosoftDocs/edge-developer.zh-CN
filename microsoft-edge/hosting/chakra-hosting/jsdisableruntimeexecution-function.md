---
description: 暂停脚本执行并终止运行时中运行的任何脚本。
title: JsDisableRuntimeExecution 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDisableRuntimeExecution
helpviewer_keywords:
- JsDisableRuntimeExecution function
ms.assetid: 4bd4670a-a9da-4f8c-b3fd-1fd366d915c3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 575947d3038eaa136e9d6ae62507501bc768eabe
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563138"
---
# <span data-ttu-id="094a3-103">JsDisableRuntimeExecution 函数</span><span class="sxs-lookup"><span data-stu-id="094a3-103">JsDisableRuntimeExecution Function</span></span>
<span data-ttu-id="094a3-104">暂停脚本执行并终止运行时中运行的任何脚本。</span><span class="sxs-lookup"><span data-stu-id="094a3-104">Suspends script execution and terminates any running scripts in a runtime.</span></span>  
  
## <span data-ttu-id="094a3-105">语法</span><span class="sxs-lookup"><span data-stu-id="094a3-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDisableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="094a3-106">参数</span><span class="sxs-lookup"><span data-stu-id="094a3-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="094a3-107">要暂停的运行时。</span><span class="sxs-lookup"><span data-stu-id="094a3-107">The runtime to be suspended.</span></span>  
  
## <span data-ttu-id="094a3-108">返回值</span><span class="sxs-lookup"><span data-stu-id="094a3-108">Return Value</span></span>  
 <span data-ttu-id="094a3-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="094a3-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="094a3-110">备注</span><span class="sxs-lookup"><span data-stu-id="094a3-110">Remarks</span></span>  
 <span data-ttu-id="094a3-111">调用挂起的运行时将失败，直到 `JsEnableRuntimeExecution` 调用。</span><span class="sxs-lookup"><span data-stu-id="094a3-111">Calls to a suspended runtime will fail until `JsEnableRuntimeExecution` is called.</span></span>  
  
 <span data-ttu-id="094a3-112">不必在运行时处于活动状态的线程上调用此 API。</span><span class="sxs-lookup"><span data-stu-id="094a3-112">This API does not have to be called on the thread the runtime is active on.</span></span> <span data-ttu-id="094a3-113">尽管运行时将设置为挂起状态，但可能无法立即挂起正在执行的脚本;将尽快终止正在运行的脚本，并显示 uncatchable 异常。</span><span class="sxs-lookup"><span data-stu-id="094a3-113">Although the runtime will be set into a suspended state, an executing script may not be suspended immediately; a running script will be terminated with an uncatchable exception as soon as possible.</span></span>  
  
 <span data-ttu-id="094a3-114">在已暂停的运行时中暂停执行是无中断操作。</span><span class="sxs-lookup"><span data-stu-id="094a3-114">Suspending execution in a runtime that is already suspended is a no-op.</span></span>  
  
## <span data-ttu-id="094a3-115">要求</span><span class="sxs-lookup"><span data-stu-id="094a3-115">Requirements</span></span>  
 <span data-ttu-id="094a3-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="094a3-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="094a3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="094a3-117">See Also</span></span>  
 [<span data-ttu-id="094a3-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="094a3-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)