---
description: 由运行时调用以加载序列化脚本的源代码。 调用方必须保持脚本缓冲区 `JsSerializedScriptUnloadCallback` 有效，直到
title: JsSerializedScriptLoadSourceCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9406c488-76ac-49e5-b305-39751f3412ea
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: bc1264bdc77da10cadb44a570ae37e7f3cd9ce6b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564188"
---
# <span data-ttu-id="daf15-104">JsSerializedScriptLoadSourceCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="daf15-104">JsSerializedScriptLoadSourceCallback Typedef</span></span>
<span data-ttu-id="daf15-105">由运行时调用以加载序列化脚本的源代码。</span><span class="sxs-lookup"><span data-stu-id="daf15-105">Called by the runtime to load the source code of the serialized script.</span></span> <span data-ttu-id="daf15-106">调用方必须保持脚本缓冲区 `JsSerializedScriptUnloadCallback` 有效，直到</span><span class="sxs-lookup"><span data-stu-id="daf15-106">The caller must keep the script buffer valid until the `JsSerializedScriptUnloadCallback`.</span></span>  
  
## <span data-ttu-id="daf15-107">语法</span><span class="sxs-lookup"><span data-stu-id="daf15-107">Syntax</span></span>  
  
```cpp  
typedef bool (CALLBACK * JsSerializedScriptLoadSourceCallback)(  
  _In_ JsSourceContextsourceContext,  
  _Outptr_result_z_ const wchar_t** scriptBuffer  
);  
```  
  
#### <span data-ttu-id="daf15-108">参数</span><span class="sxs-lookup"><span data-stu-id="daf15-108">Parameters</span></span>  
 `sourceContext`  
 <span data-ttu-id="daf15-109">传递给或的 `JsParseSerializedScriptWithCallback` 上下文 `JsRunSerializedScriptWithCallback` 。</span><span class="sxs-lookup"><span data-stu-id="daf15-109">The context passed to `JsParseSerializedScriptWithCallback` or `JsRunSerializedScriptWithCallback`.</span></span>  
  
 `scriptBuffer`  
 <span data-ttu-id="daf15-110">脚本返回。</span><span class="sxs-lookup"><span data-stu-id="daf15-110">The script returned.</span></span>  
  
## <span data-ttu-id="daf15-111">备注</span><span class="sxs-lookup"><span data-stu-id="daf15-111">Remarks</span></span>  
  
> [!WARNING]
## <span data-ttu-id="daf15-112">要求</span><span class="sxs-lookup"><span data-stu-id="daf15-112">Requirements</span></span>  
 <span data-ttu-id="daf15-113">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="daf15-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="daf15-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="daf15-114">See Also</span></span>  
 [<span data-ttu-id="daf15-115">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="daf15-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)