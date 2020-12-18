---
description: 添加对垃圾回收对象的引用。
title: JsAddRef 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsAddRef
helpviewer_keywords:
- JsAddRef function
ms.assetid: a7f3ed49-6a86-489a-abdf-c99428e79cae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fd397dbfeacafdf12728ef0ca2a98d97405f6592
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232232"
---
# <span data-ttu-id="38900-103">JsAddRef 函数</span><span class="sxs-lookup"><span data-stu-id="38900-103">JsAddRef Function</span></span>

<span data-ttu-id="38900-104">添加对垃圾回收对象的引用。</span><span class="sxs-lookup"><span data-stu-id="38900-104">Adds a reference to a garbage collected object.</span></span>  
  
## <span data-ttu-id="38900-105">语法</span><span class="sxs-lookup"><span data-stu-id="38900-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsAddRef(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### <span data-ttu-id="38900-106">参数</span><span class="sxs-lookup"><span data-stu-id="38900-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="38900-107">要添加引用的对象。</span><span class="sxs-lookup"><span data-stu-id="38900-107">The object to add a reference to.</span></span>  
  
 `count`  
 <span data-ttu-id="38900-108">对象的新引用计数 (null 值) 。</span><span class="sxs-lookup"><span data-stu-id="38900-108">The object's new reference count (can pass in null).</span></span>  
  
## <span data-ttu-id="38900-109">返回值</span><span class="sxs-lookup"><span data-stu-id="38900-109">Return Value</span></span>  
 <span data-ttu-id="38900-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="38900-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="38900-111">备注</span><span class="sxs-lookup"><span data-stu-id="38900-111">Remarks</span></span>  
 <span data-ttu-id="38900-112">只需在不会存储在堆栈上的某一位置的句柄上 `JsRef` 调用它。</span><span class="sxs-lookup"><span data-stu-id="38900-112">This only needs to be called on `JsRef` handles that are not going to be stored somewhere on the stack.</span></span> <span data-ttu-id="38900-113">调用可确保在调用引用的对象之前 `JsAddRef` `JsRef` 不会 `JsRelease` 释放该对象。</span><span class="sxs-lookup"><span data-stu-id="38900-113">Calling `JsAddRef` ensures that the object the `JsRef` refers to will not be freed until `JsRelease` is called.</span></span>  
  
## <span data-ttu-id="38900-114">要求</span><span class="sxs-lookup"><span data-stu-id="38900-114">Requirements</span></span>  
 <span data-ttu-id="38900-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="38900-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="38900-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38900-116">See Also</span></span>  
 [<span data-ttu-id="38900-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="38900-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
