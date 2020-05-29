---
description: '在运行时中启用脚本执行。 '
title: JsEnableRuntimeExecution 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsEnableRuntimeExecution
helpviewer_keywords:
- JsEnableRuntimeExecution function
ms.assetid: daa2036b-aef6-497d-a8ce-5a006b6ed13f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: dd8071fd3c120d1c2029a3c7a3d9c39e68c4cfd2
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564273"
---
# <span data-ttu-id="447be-103">JsEnableRuntimeExecution 函数</span><span class="sxs-lookup"><span data-stu-id="447be-103">JsEnableRuntimeExecution Function</span></span>
<span data-ttu-id="447be-104">在运行时中启用脚本执行。</span><span class="sxs-lookup"><span data-stu-id="447be-104">Enables script execution in a runtime.</span></span>  
  
## <span data-ttu-id="447be-105">语法</span><span class="sxs-lookup"><span data-stu-id="447be-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsEnableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="447be-106">参数</span><span class="sxs-lookup"><span data-stu-id="447be-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="447be-107">要启用的运行时。</span><span class="sxs-lookup"><span data-stu-id="447be-107">The runtime to be enabled.</span></span>  
  
## <span data-ttu-id="447be-108">返回值</span><span class="sxs-lookup"><span data-stu-id="447be-108">Return Value</span></span>  
 <span data-ttu-id="447be-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="447be-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="447be-110">备注</span><span class="sxs-lookup"><span data-stu-id="447be-110">Remarks</span></span>  
 <span data-ttu-id="447be-111">在已启用脚本执行的运行时中启用脚本执行是无操作。</span><span class="sxs-lookup"><span data-stu-id="447be-111">Enabling script execution in a runtime that already has script execution enabled is a no-op.</span></span>  
  
## <span data-ttu-id="447be-112">要求</span><span class="sxs-lookup"><span data-stu-id="447be-112">Requirements</span></span>  
 <span data-ttu-id="447be-113">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="447be-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="447be-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="447be-114">See Also</span></span>  
 [<span data-ttu-id="447be-115">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="447be-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)