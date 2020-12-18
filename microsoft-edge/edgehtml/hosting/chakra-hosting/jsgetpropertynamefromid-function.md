---
description: 获取与属性 ID 关联的名称。
title: JsGetPropertyNameFromId 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetPropertyNameFromId
helpviewer_keywords:
- JsGetPropertyNameFromId function
ms.assetid: b4ca442c-573d-4bc3-adf7-1b8d48480b3a
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 42061ab54a70fed571740961a909a6da17fb0733
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232412"
---
# <span data-ttu-id="6c616-103">JsGetPropertyNameFromId 函数</span><span class="sxs-lookup"><span data-stu-id="6c616-103">JsGetPropertyNameFromId Function</span></span>

<span data-ttu-id="6c616-104">获取与属性 ID 关联的名称。</span><span class="sxs-lookup"><span data-stu-id="6c616-104">Gets the name associated with the property ID.</span></span>  
  
## <span data-ttu-id="6c616-105">语法</span><span class="sxs-lookup"><span data-stu-id="6c616-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyNameFromId(  
   _In_ JsPropertyIdRef propertyId,  
   _Outptr_result_z_ const wchar_t **name  
);  
```  
  
#### <span data-ttu-id="6c616-106">参数</span><span class="sxs-lookup"><span data-stu-id="6c616-106">Parameters</span></span>  
 `propertyId`  
 <span data-ttu-id="6c616-107">要获取其名称的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="6c616-107">The property ID to get the name of.</span></span>  
  
 `name`  
 <span data-ttu-id="6c616-108">与属性 ID 关联的名称。</span><span class="sxs-lookup"><span data-stu-id="6c616-108">The name associated with the property ID.</span></span>  
  
## <span data-ttu-id="6c616-109">返回值</span><span class="sxs-lookup"><span data-stu-id="6c616-109">Return Value</span></span>  
 <span data-ttu-id="6c616-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="6c616-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6c616-111">备注</span><span class="sxs-lookup"><span data-stu-id="6c616-111">Remarks</span></span>  
 <span data-ttu-id="6c616-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="6c616-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="6c616-113">只要运行时处于活动状态，返回的缓冲区就有效，并且一旦释放运行时，就无法使用。</span><span class="sxs-lookup"><span data-stu-id="6c616-113">The returned buffer is valid as long as the runtime is alive and cannot be used once the runtime has been disposed.</span></span>  
  
## <span data-ttu-id="6c616-114">要求</span><span class="sxs-lookup"><span data-stu-id="6c616-114">Requirements</span></span>  
 <span data-ttu-id="6c616-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="6c616-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6c616-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c616-116">See Also</span></span>  
 [<span data-ttu-id="6c616-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="6c616-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
