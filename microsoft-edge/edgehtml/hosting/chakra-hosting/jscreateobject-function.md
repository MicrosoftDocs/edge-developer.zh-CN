---
description: 创建新的对象。
title: JsCreateObject 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateObject
helpviewer_keywords:
- JsCreateObject function
ms.assetid: 6c1d01a4-9254-443e-b974-6f0b0c861ca2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d5effe7ade1679392fcad7f2bb5cea880712ef7f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232339"
---
# <span data-ttu-id="5f989-103">JsCreateObject 函数</span><span class="sxs-lookup"><span data-stu-id="5f989-103">JsCreateObject Function</span></span>

<span data-ttu-id="5f989-104">创建新的对象。</span><span class="sxs-lookup"><span data-stu-id="5f989-104">Creates a new object.</span></span>
  
## <span data-ttu-id="5f989-105">语法</span><span class="sxs-lookup"><span data-stu-id="5f989-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateObject(  
   _Out_ JsValueRef *object  
);  
```  
  
#### <span data-ttu-id="5f989-106">参数</span><span class="sxs-lookup"><span data-stu-id="5f989-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="5f989-107">新对象。</span><span class="sxs-lookup"><span data-stu-id="5f989-107">The new object.</span></span>  
  
## <span data-ttu-id="5f989-108">返回值</span><span class="sxs-lookup"><span data-stu-id="5f989-108">Return Value</span></span>  
 <span data-ttu-id="5f989-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="5f989-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="5f989-110">备注</span><span class="sxs-lookup"><span data-stu-id="5f989-110">Remarks</span></span>  
 <span data-ttu-id="5f989-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="5f989-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="5f989-112">要求</span><span class="sxs-lookup"><span data-stu-id="5f989-112">Requirements</span></span>  
 <span data-ttu-id="5f989-113">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="5f989-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5f989-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f989-114">See Also</span></span>  
 [<span data-ttu-id="5f989-115">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="5f989-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
