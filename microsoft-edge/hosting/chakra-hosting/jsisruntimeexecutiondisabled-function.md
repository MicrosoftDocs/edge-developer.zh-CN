---
description: 返回一个值，该值指示是否在运行时中禁用脚本执行。
title: JsIsRuntimeExecutionDisabled 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsIsRuntimeExecutionDisabled
helpviewer_keywords:
- JsIsRuntimeExecutionDisabled function
ms.assetid: 77490280-fb84-4614-a1f0-6ac31e3bd607
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6968a31c9acab70589fe58c86cc566e631778c3c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563089"
---
# <span data-ttu-id="30501-103">JsIsRuntimeExecutionDisabled 函数</span><span class="sxs-lookup"><span data-stu-id="30501-103">JsIsRuntimeExecutionDisabled Function</span></span>
<span data-ttu-id="30501-104">返回一个值，该值指示是否在运行时中禁用脚本执行。</span><span class="sxs-lookup"><span data-stu-id="30501-104">Returns a value that indicates whether script execution is disabled in the runtime.</span></span>  
  
## <span data-ttu-id="30501-105">语法</span><span class="sxs-lookup"><span data-stu-id="30501-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIsRuntimeExecutionDisabled(    _In_ JsRuntimeHandle runtime,    _Out_ bool *isDisabled);  
```  
  
#### <span data-ttu-id="30501-106">参数</span><span class="sxs-lookup"><span data-stu-id="30501-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="30501-107">指定运行时检查是否已禁用执行。</span><span class="sxs-lookup"><span data-stu-id="30501-107">Specifies the runtime to check if execution is disabled.</span></span>  
  
 `isDisabled`  
 `true` <span data-ttu-id="30501-108">如果执行被禁用，则 `false` 为。</span><span class="sxs-lookup"><span data-stu-id="30501-108">if execution is disabled, `false` otherwise.</span></span>  
  
## <span data-ttu-id="30501-109">返回值</span><span class="sxs-lookup"><span data-stu-id="30501-109">Return Value</span></span>  
 `JsNoError` <span data-ttu-id="30501-110">如果操作成功，则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="30501-110">if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="30501-111">要求</span><span class="sxs-lookup"><span data-stu-id="30501-111">Requirements</span></span>  
 <span data-ttu-id="30501-112">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="30501-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="30501-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30501-113">See Also</span></span>  
 [<span data-ttu-id="30501-114">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="30501-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)