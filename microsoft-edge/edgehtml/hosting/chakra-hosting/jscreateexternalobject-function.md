---
description: 创建一个存储一些外部数据的新对象。
title: JsCreateExternalObject 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateExternalObject
helpviewer_keywords:
- JsCreateExternalObject function
ms.assetid: 6bcef506-93fb-429b-b06a-a971ff0b71f3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4d402c3d379a16186daaba601c7f830c53a9a953
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232712"
---
# <span data-ttu-id="36d98-103">JsCreateExternalObject 函数</span><span class="sxs-lookup"><span data-stu-id="36d98-103">JsCreateExternalObject Function</span></span>

<span data-ttu-id="36d98-104">创建一个存储一些外部数据的新对象。</span><span class="sxs-lookup"><span data-stu-id="36d98-104">Creates a new object that stores some external data.</span></span>
  
## <span data-ttu-id="36d98-105">语法</span><span class="sxs-lookup"><span data-stu-id="36d98-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateExternalObject(  
   _In_opt_ void *data,  
   _In_opt_ JsFinalizeCallback finalizeCallback,  
   _Out_ JsValueRef *object  
);  
```  
  
#### <span data-ttu-id="36d98-106">参数</span><span class="sxs-lookup"><span data-stu-id="36d98-106">Parameters</span></span>  
 `data`  
 <span data-ttu-id="36d98-107">对象将表示的外部数据。</span><span class="sxs-lookup"><span data-stu-id="36d98-107">External data that the object will represent.</span></span> <span data-ttu-id="36d98-108">可能为空。</span><span class="sxs-lookup"><span data-stu-id="36d98-108">May be null.</span></span>  
  
 `finalizeCallback`  
 <span data-ttu-id="36d98-109">对象完成时回调。</span><span class="sxs-lookup"><span data-stu-id="36d98-109">A callback for when the object is finalized.</span></span> <span data-ttu-id="36d98-110">可能为空。</span><span class="sxs-lookup"><span data-stu-id="36d98-110">May be null.</span></span>  
  
 `object`  
 <span data-ttu-id="36d98-111">新对象。</span><span class="sxs-lookup"><span data-stu-id="36d98-111">The new object.</span></span>  
  
## <span data-ttu-id="36d98-112">返回值</span><span class="sxs-lookup"><span data-stu-id="36d98-112">Return Value</span></span>  
 <span data-ttu-id="36d98-113">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="36d98-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="36d98-114">备注</span><span class="sxs-lookup"><span data-stu-id="36d98-114">Remarks</span></span>  
 <span data-ttu-id="36d98-115">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="36d98-115">Requires an active script context.</span></span>  
  
## <span data-ttu-id="36d98-116">要求</span><span class="sxs-lookup"><span data-stu-id="36d98-116">Requirements</span></span>  
 <span data-ttu-id="36d98-117">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="36d98-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="36d98-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36d98-118">See Also</span></span>  
 [<span data-ttu-id="36d98-119">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="36d98-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
