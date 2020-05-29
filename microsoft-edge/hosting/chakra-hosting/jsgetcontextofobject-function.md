---
description: 获取对象所属的脚本上下文。
title: JsGetContextOfObject 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cea6cdcd-790f-455c-af04-026af8ae2eb7
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 4f1b996954e877d9c98ac0caf06f255af629a386
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563132"
---
# <span data-ttu-id="41e9d-103">JsGetContextOfObject 函数</span><span class="sxs-lookup"><span data-stu-id="41e9d-103">JsGetContextOfObject Function</span></span>
<span data-ttu-id="41e9d-104">获取对象所属的脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="41e9d-104">Gets the script context that the object belongs to.</span></span>  
  
## <span data-ttu-id="41e9d-105">语法</span><span class="sxs-lookup"><span data-stu-id="41e9d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetContextOfObject(  
  _In_ JsValueRef object,  
  _Out_ JsContextRef *context  
);  
```  
  
#### <span data-ttu-id="41e9d-106">参数</span><span class="sxs-lookup"><span data-stu-id="41e9d-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="41e9d-107">要从中获取上下文的对象。</span><span class="sxs-lookup"><span data-stu-id="41e9d-107">The object to get the context from.</span></span>  
  
 `context`  
 <span data-ttu-id="41e9d-108">对象所属的上下文。</span><span class="sxs-lookup"><span data-stu-id="41e9d-108">The context the object belongs to.</span></span>  
  
## <span data-ttu-id="41e9d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="41e9d-109">Return Value</span></span>  
 <span data-ttu-id="41e9d-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="41e9d-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="41e9d-111">备注</span><span class="sxs-lookup"><span data-stu-id="41e9d-111">Remarks</span></span>  
 <span data-ttu-id="41e9d-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="41e9d-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="41e9d-113">要求</span><span class="sxs-lookup"><span data-stu-id="41e9d-113">Requirements</span></span>  
 <span data-ttu-id="41e9d-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="41e9d-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="41e9d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41e9d-115">See Also</span></span>  
 [<span data-ttu-id="41e9d-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="41e9d-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)