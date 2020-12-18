---
description: 运行时在使用与脚本执行相关的所有资源完成时调用它。 如果加载，调用方此时应释放源、字节代码和上下文。
title: JsSerializedScriptUnloadCallback typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5c63f2ff3faf21a19e31f2f6fd1692e21d59fc0b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232709"
---
# <span data-ttu-id="9fd0e-104">JsSerializedScriptUnloadCallback typedef</span><span class="sxs-lookup"><span data-stu-id="9fd0e-104">JsSerializedScriptUnloadCallback typedef</span></span>

<span data-ttu-id="9fd0e-105">运行时在使用与脚本执行相关的所有资源完成时调用它。</span><span class="sxs-lookup"><span data-stu-id="9fd0e-105">Called by the runtime when it is finished with all resources related to the script execution.</span></span> <span data-ttu-id="9fd0e-106">如果加载，调用方此时应释放源、字节代码和上下文。</span><span class="sxs-lookup"><span data-stu-id="9fd0e-106">The caller should free the source if loaded, the byte code, and the context at this time.</span></span>  
  
## <span data-ttu-id="9fd0e-107">语法</span><span class="sxs-lookup"><span data-stu-id="9fd0e-107">Syntax</span></span>  
  
```cpp  
 typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(  
  _In_ JsSourceContext sourceContext  
);  
```  
  
#### <span data-ttu-id="9fd0e-108">参数</span><span class="sxs-lookup"><span data-stu-id="9fd0e-108">Parameters</span></span>  
 `sourceContext`  
 <span data-ttu-id="9fd0e-109">传递给 或 `JsParseSerializedScriptWithCallback` `JsRunSerializedScriptWithCallback` 的上下文。</span><span class="sxs-lookup"><span data-stu-id="9fd0e-109">The context passed to `JsParseSerializedScriptWithCallback` or `JsRunSerializedScriptWithCallback`.</span></span>  
  
## <span data-ttu-id="9fd0e-110">备注</span><span class="sxs-lookup"><span data-stu-id="9fd0e-110">Remarks</span></span>  
  
> [!WARNING]
## <span data-ttu-id="9fd0e-111">要求</span><span class="sxs-lookup"><span data-stu-id="9fd0e-111">Requirements</span></span>  
 <span data-ttu-id="9fd0e-112">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="9fd0e-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9fd0e-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fd0e-113">See Also</span></span>  
 [<span data-ttu-id="9fd0e-114">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="9fd0e-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
