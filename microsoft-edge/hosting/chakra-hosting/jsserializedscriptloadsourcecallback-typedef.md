---
description: 由运行时调用以加载序列化脚本的源代码。 调用方必须保持脚本缓冲区 `JsSerializedScriptUnloadCallback` 有效，直到
title: JsSerializedScriptLoadSourceCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 9406c488-76ac-49e5-b305-39751f3412ea
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 571314145cc19513f04174a9a1c93822a5795b29
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752197"
---
# <span data-ttu-id="db86f-104">JsSerializedScriptLoadSourceCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="db86f-104">JsSerializedScriptLoadSourceCallback Typedef</span></span>
<span data-ttu-id="db86f-105">由运行时调用以加载序列化脚本的源代码。</span><span class="sxs-lookup"><span data-stu-id="db86f-105">Called by the runtime to load the source code of the serialized script.</span></span> <span data-ttu-id="db86f-106">调用方必须保持脚本缓冲区 `JsSerializedScriptUnloadCallback` 有效，直到</span><span class="sxs-lookup"><span data-stu-id="db86f-106">The caller must keep the script buffer valid until the `JsSerializedScriptUnloadCallback`.</span></span>  
  
## <span data-ttu-id="db86f-107">语法</span><span class="sxs-lookup"><span data-stu-id="db86f-107">Syntax</span></span>  
  
```cpp  
typedef bool (CALLBACK * JsSerializedScriptLoadSourceCallback)(  
  _In_ JsSourceContextsourceContext,  
  _Outptr_result_z_ const wchar_t** scriptBuffer  
);  
```  
  
#### <span data-ttu-id="db86f-108">参数</span><span class="sxs-lookup"><span data-stu-id="db86f-108">Parameters</span></span>  
 `sourceContext`  
 <span data-ttu-id="db86f-109">传递给或的 `JsParseSerializedScriptWithCallback` 上下文 `JsRunSerializedScriptWithCallback` 。</span><span class="sxs-lookup"><span data-stu-id="db86f-109">The context passed to `JsParseSerializedScriptWithCallback` or `JsRunSerializedScriptWithCallback`.</span></span>  
  
 `scriptBuffer`  
 <span data-ttu-id="db86f-110">脚本返回。</span><span class="sxs-lookup"><span data-stu-id="db86f-110">The script returned.</span></span>  
  
## <span data-ttu-id="db86f-111">备注</span><span class="sxs-lookup"><span data-stu-id="db86f-111">Remarks</span></span>  
  
> [!WARNING]
## <span data-ttu-id="db86f-112">要求</span><span class="sxs-lookup"><span data-stu-id="db86f-112">Requirements</span></span>  
 <span data-ttu-id="db86f-113">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="db86f-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="db86f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db86f-114">See Also</span></span>  
 [<span data-ttu-id="db86f-115">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="db86f-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)