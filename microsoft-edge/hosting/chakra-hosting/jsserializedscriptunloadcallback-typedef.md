---
description: 在运行时使用与脚本执行相关的所有资源完成时调用。 此时，调用方应释放源（如果已加载）、字节代码和上下文。
title: JsSerializedScriptUnloadCallback typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9555b3fd8c14c9629d17c13592e3c78a78be150e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564187"
---
# <span data-ttu-id="ab666-104">JsSerializedScriptUnloadCallback typedef</span><span class="sxs-lookup"><span data-stu-id="ab666-104">JsSerializedScriptUnloadCallback typedef</span></span>
<span data-ttu-id="ab666-105">在运行时使用与脚本执行相关的所有资源完成时调用。</span><span class="sxs-lookup"><span data-stu-id="ab666-105">Called by the runtime when it is finished with all resources related to the script execution.</span></span> <span data-ttu-id="ab666-106">此时，调用方应释放源（如果已加载）、字节代码和上下文。</span><span class="sxs-lookup"><span data-stu-id="ab666-106">The caller should free the source if loaded, the byte code, and the context at this time.</span></span>  
  
## <span data-ttu-id="ab666-107">语法</span><span class="sxs-lookup"><span data-stu-id="ab666-107">Syntax</span></span>  
  
```cpp  
 typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(  
  _In_ JsSourceContext sourceContext  
);  
```  
  
#### <span data-ttu-id="ab666-108">参数</span><span class="sxs-lookup"><span data-stu-id="ab666-108">Parameters</span></span>  
 `sourceContext`  
 <span data-ttu-id="ab666-109">传递给或的 `JsParseSerializedScriptWithCallback` 上下文 `JsRunSerializedScriptWithCallback` 。</span><span class="sxs-lookup"><span data-stu-id="ab666-109">The context passed to `JsParseSerializedScriptWithCallback` or `JsRunSerializedScriptWithCallback`.</span></span>  
  
## <span data-ttu-id="ab666-110">备注</span><span class="sxs-lookup"><span data-stu-id="ab666-110">Remarks</span></span>  
  
> [!WARNING]
## <span data-ttu-id="ab666-111">要求</span><span class="sxs-lookup"><span data-stu-id="ab666-111">Requirements</span></span>  
 <span data-ttu-id="ab666-112">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="ab666-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ab666-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab666-113">See Also</span></span>  
 [<span data-ttu-id="ab666-114">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="ab666-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)