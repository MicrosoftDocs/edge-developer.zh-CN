---
description: 在运行时使用与脚本执行相关的所有资源完成时调用。 此时，调用方应释放源（如果已加载）、字节代码和上下文。
title: JsSerializedScriptUnloadCallback typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c3da27af18ebc7a1913980a865d926bac6a29d11
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10751938"
---
# <span data-ttu-id="98e2f-104">JsSerializedScriptUnloadCallback typedef</span><span class="sxs-lookup"><span data-stu-id="98e2f-104">JsSerializedScriptUnloadCallback typedef</span></span>
<span data-ttu-id="98e2f-105">在运行时使用与脚本执行相关的所有资源完成时调用。</span><span class="sxs-lookup"><span data-stu-id="98e2f-105">Called by the runtime when it is finished with all resources related to the script execution.</span></span> <span data-ttu-id="98e2f-106">此时，调用方应释放源（如果已加载）、字节代码和上下文。</span><span class="sxs-lookup"><span data-stu-id="98e2f-106">The caller should free the source if loaded, the byte code, and the context at this time.</span></span>  
  
## <span data-ttu-id="98e2f-107">语法</span><span class="sxs-lookup"><span data-stu-id="98e2f-107">Syntax</span></span>  
  
```cpp  
 typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(  
  _In_ JsSourceContext sourceContext  
);  
```  
  
#### <span data-ttu-id="98e2f-108">参数</span><span class="sxs-lookup"><span data-stu-id="98e2f-108">Parameters</span></span>  
 `sourceContext`  
 <span data-ttu-id="98e2f-109">传递给或的 `JsParseSerializedScriptWithCallback` 上下文 `JsRunSerializedScriptWithCallback` 。</span><span class="sxs-lookup"><span data-stu-id="98e2f-109">The context passed to `JsParseSerializedScriptWithCallback` or `JsRunSerializedScriptWithCallback`.</span></span>  
  
## <span data-ttu-id="98e2f-110">备注</span><span class="sxs-lookup"><span data-stu-id="98e2f-110">Remarks</span></span>  
  
> [!WARNING]
## <span data-ttu-id="98e2f-111">要求</span><span class="sxs-lookup"><span data-stu-id="98e2f-111">Requirements</span></span>  
 <span data-ttu-id="98e2f-112">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="98e2f-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="98e2f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98e2f-113">See Also</span></span>  
 [<span data-ttu-id="98e2f-114">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="98e2f-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)