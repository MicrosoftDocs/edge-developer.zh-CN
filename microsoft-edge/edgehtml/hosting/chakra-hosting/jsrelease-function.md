---
description: 释放对垃圾回收对象的引用。
title: JsRelease 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsRelease
helpviewer_keywords:
- JsRelease function
ms.assetid: 8714fd0b-5b66-48e0-927e-7b93af6cde7b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 46552a03dc56a10b1d258d8c33da1c533f38464a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232180"
---
# <span data-ttu-id="c00de-103">JsRelease 函数</span><span class="sxs-lookup"><span data-stu-id="c00de-103">JsRelease Function</span></span>

<span data-ttu-id="c00de-104">释放对垃圾回收对象的引用。</span><span class="sxs-lookup"><span data-stu-id="c00de-104">Releases a reference to a garbage collected object.</span></span>  
  
## <span data-ttu-id="c00de-105">语法</span><span class="sxs-lookup"><span data-stu-id="c00de-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsRelease(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### <span data-ttu-id="c00de-106">参数</span><span class="sxs-lookup"><span data-stu-id="c00de-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="c00de-107">要添加引用的对象。</span><span class="sxs-lookup"><span data-stu-id="c00de-107">The object to add a reference to.</span></span>  
  
 `count`  
 <span data-ttu-id="c00de-108">对象的新引用计数 (null 值) 。</span><span class="sxs-lookup"><span data-stu-id="c00de-108">The object's new reference count (can pass in null).</span></span>  
  
## <span data-ttu-id="c00de-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c00de-109">Return Value</span></span>  
 <span data-ttu-id="c00de-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="c00de-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c00de-111">备注</span><span class="sxs-lookup"><span data-stu-id="c00de-111">Remarks</span></span>  
 <span data-ttu-id="c00de-112">删除对由 `JsRef` 创建句柄的引用 `JsAddRef` 。</span><span class="sxs-lookup"><span data-stu-id="c00de-112">Removes a reference to a `JsRef` handle that was created by `JsAddRef`.</span></span>  
  
## <span data-ttu-id="c00de-113">要求</span><span class="sxs-lookup"><span data-stu-id="c00de-113">Requirements</span></span>  
 <span data-ttu-id="c00de-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="c00de-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c00de-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c00de-115">See Also</span></span>  
 [<span data-ttu-id="c00de-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="c00de-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
