---
description: 由运行时调用以加载序列化脚本的源代码。 调用方必须保持脚本缓冲区有效，直到 `JsSerializedScriptUnloadCallback` .
title: JsSerializedScriptLoadSourceCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 9406c488-76ac-49e5-b305-39751f3412ea
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2bb30befc61003d20cdeaa293fd1fdfdc95b36f7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232759"
---
# <span data-ttu-id="d977d-104">JsSerializedScriptLoadSourceCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="d977d-104">JsSerializedScriptLoadSourceCallback Typedef</span></span>

<span data-ttu-id="d977d-105">由运行时调用以加载序列化脚本的源代码。</span><span class="sxs-lookup"><span data-stu-id="d977d-105">Called by the runtime to load the source code of the serialized script.</span></span> <span data-ttu-id="d977d-106">调用方必须保持脚本缓冲区有效，直到 `JsSerializedScriptUnloadCallback` .</span><span class="sxs-lookup"><span data-stu-id="d977d-106">The caller must keep the script buffer valid until the `JsSerializedScriptUnloadCallback`.</span></span>  
  
## <span data-ttu-id="d977d-107">语法</span><span class="sxs-lookup"><span data-stu-id="d977d-107">Syntax</span></span>  
  
```cpp  
typedef bool (CALLBACK * JsSerializedScriptLoadSourceCallback)(  
  _In_ JsSourceContextsourceContext,  
  _Outptr_result_z_ const wchar_t** scriptBuffer  
);  
```  
  
#### <span data-ttu-id="d977d-108">参数</span><span class="sxs-lookup"><span data-stu-id="d977d-108">Parameters</span></span>  
 `sourceContext`  
 <span data-ttu-id="d977d-109">传递给 或 `JsParseSerializedScriptWithCallback` `JsRunSerializedScriptWithCallback` 的上下文。</span><span class="sxs-lookup"><span data-stu-id="d977d-109">The context passed to `JsParseSerializedScriptWithCallback` or `JsRunSerializedScriptWithCallback`.</span></span>  
  
 `scriptBuffer`  
 <span data-ttu-id="d977d-110">返回的脚本。</span><span class="sxs-lookup"><span data-stu-id="d977d-110">The script returned.</span></span>  
  
## <span data-ttu-id="d977d-111">备注</span><span class="sxs-lookup"><span data-stu-id="d977d-111">Remarks</span></span>  
  
> [!WARNING]
## <span data-ttu-id="d977d-112">要求</span><span class="sxs-lookup"><span data-stu-id="d977d-112">Requirements</span></span>  
 <span data-ttu-id="d977d-113">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="d977d-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d977d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d977d-114">See Also</span></span>  
 [<span data-ttu-id="d977d-115">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="d977d-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
