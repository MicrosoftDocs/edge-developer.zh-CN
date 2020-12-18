---
description: 获取对象所属的脚本上下文。
title: JsGetContextOfObject 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: cea6cdcd-790f-455c-af04-026af8ae2eb7
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9085f9156e4e0ca9e952fe51447185239082f975
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232455"
---
# <span data-ttu-id="8334f-103">JsGetContextOfObject 函数</span><span class="sxs-lookup"><span data-stu-id="8334f-103">JsGetContextOfObject Function</span></span>

<span data-ttu-id="8334f-104">获取对象所属的脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="8334f-104">Gets the script context that the object belongs to.</span></span>  
  
## <span data-ttu-id="8334f-105">语法</span><span class="sxs-lookup"><span data-stu-id="8334f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetContextOfObject(  
  _In_ JsValueRef object,  
  _Out_ JsContextRef *context  
);  
```  
  
#### <span data-ttu-id="8334f-106">参数</span><span class="sxs-lookup"><span data-stu-id="8334f-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="8334f-107">要获取其上下文的对象。</span><span class="sxs-lookup"><span data-stu-id="8334f-107">The object to get the context from.</span></span>  
  
 `context`  
 <span data-ttu-id="8334f-108">对象所属的上下文。</span><span class="sxs-lookup"><span data-stu-id="8334f-108">The context the object belongs to.</span></span>  
  
## <span data-ttu-id="8334f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="8334f-109">Return Value</span></span>  
 <span data-ttu-id="8334f-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="8334f-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="8334f-111">备注</span><span class="sxs-lookup"><span data-stu-id="8334f-111">Remarks</span></span>  
 <span data-ttu-id="8334f-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="8334f-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="8334f-113">要求</span><span class="sxs-lookup"><span data-stu-id="8334f-113">Requirements</span></span>  
 <span data-ttu-id="8334f-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="8334f-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="8334f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8334f-115">See Also</span></span>  
 [<span data-ttu-id="8334f-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="8334f-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
