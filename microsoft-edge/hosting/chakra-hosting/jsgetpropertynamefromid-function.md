---
description: 获取与属性 ID 关联的名称。
title: JsGetPropertyNameFromId 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetPropertyNameFromId
helpviewer_keywords:
- JsGetPropertyNameFromId function
ms.assetid: b4ca442c-573d-4bc3-adf7-1b8d48480b3a
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1e76c69c1d746302bb95cd7229872845c4fbcc88
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563116"
---
# <span data-ttu-id="0eaf6-103">JsGetPropertyNameFromId 函数</span><span class="sxs-lookup"><span data-stu-id="0eaf6-103">JsGetPropertyNameFromId Function</span></span>
<span data-ttu-id="0eaf6-104">获取与属性 ID 关联的名称。</span><span class="sxs-lookup"><span data-stu-id="0eaf6-104">Gets the name associated with the property ID.</span></span>  
  
## <span data-ttu-id="0eaf6-105">语法</span><span class="sxs-lookup"><span data-stu-id="0eaf6-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyNameFromId(  
   _In_ JsPropertyIdRef propertyId,  
   _Outptr_result_z_ const wchar_t **name  
);  
```  
  
#### <span data-ttu-id="0eaf6-106">参数</span><span class="sxs-lookup"><span data-stu-id="0eaf6-106">Parameters</span></span>  
 `propertyId`  
 <span data-ttu-id="0eaf6-107">要获取其名称的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="0eaf6-107">The property ID to get the name of.</span></span>  
  
 `name`  
 <span data-ttu-id="0eaf6-108">与属性 ID 关联的名称。</span><span class="sxs-lookup"><span data-stu-id="0eaf6-108">The name associated with the property ID.</span></span>  
  
## <span data-ttu-id="0eaf6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0eaf6-109">Return Value</span></span>  
 <span data-ttu-id="0eaf6-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="0eaf6-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0eaf6-111">备注</span><span class="sxs-lookup"><span data-stu-id="0eaf6-111">Remarks</span></span>  
 <span data-ttu-id="0eaf6-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="0eaf6-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="0eaf6-113">只要运行时处于活动状态，并且在释放运行时后，返回的缓冲区才有效。</span><span class="sxs-lookup"><span data-stu-id="0eaf6-113">The returned buffer is valid as long as the runtime is alive and cannot be used once the runtime has been disposed.</span></span>  
  
## <span data-ttu-id="0eaf6-114">要求</span><span class="sxs-lookup"><span data-stu-id="0eaf6-114">Requirements</span></span>  
 <span data-ttu-id="0eaf6-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="0eaf6-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0eaf6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0eaf6-116">See Also</span></span>  
 [<span data-ttu-id="0eaf6-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="0eaf6-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)