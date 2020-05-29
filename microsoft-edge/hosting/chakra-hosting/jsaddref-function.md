---
description: 添加对垃圾回收对象的引用。
title: JsAddRef 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsAddRef
helpviewer_keywords:
- JsAddRef function
ms.assetid: a7f3ed49-6a86-489a-abdf-c99428e79cae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: bd02dded6dc2877228f22b4d2800e41a78163467
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563203"
---
# <span data-ttu-id="27247-103">JsAddRef 函数</span><span class="sxs-lookup"><span data-stu-id="27247-103">JsAddRef Function</span></span>
<span data-ttu-id="27247-104">添加对垃圾回收对象的引用。</span><span class="sxs-lookup"><span data-stu-id="27247-104">Adds a reference to a garbage collected object.</span></span>  
  
## <span data-ttu-id="27247-105">语法</span><span class="sxs-lookup"><span data-stu-id="27247-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsAddRef(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### <span data-ttu-id="27247-106">参数</span><span class="sxs-lookup"><span data-stu-id="27247-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="27247-107">要向其添加引用的对象。</span><span class="sxs-lookup"><span data-stu-id="27247-107">The object to add a reference to.</span></span>  
  
 `count`  
 <span data-ttu-id="27247-108">对象的新引用计数（可以传入 null）。</span><span class="sxs-lookup"><span data-stu-id="27247-108">The object's new reference count (can pass in null).</span></span>  
  
## <span data-ttu-id="27247-109">返回值</span><span class="sxs-lookup"><span data-stu-id="27247-109">Return Value</span></span>  
 <span data-ttu-id="27247-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="27247-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="27247-111">备注</span><span class="sxs-lookup"><span data-stu-id="27247-111">Remarks</span></span>  
 <span data-ttu-id="27247-112">这只需要在 `JsRef` 不会存储在堆栈某处的句柄上调用。</span><span class="sxs-lookup"><span data-stu-id="27247-112">This only needs to be called on `JsRef` handles that are not going to be stored somewhere on the stack.</span></span> <span data-ttu-id="27247-113">调用 `JsAddRef` 可确保引用的对象在 `JsRef` 调用之前不会被释放 `JsRelease` 。</span><span class="sxs-lookup"><span data-stu-id="27247-113">Calling `JsAddRef` ensures that the object the `JsRef` refers to will not be freed until `JsRelease` is called.</span></span>  
  
## <span data-ttu-id="27247-114">要求</span><span class="sxs-lookup"><span data-stu-id="27247-114">Requirements</span></span>  
 <span data-ttu-id="27247-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="27247-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="27247-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27247-116">See Also</span></span>  
 [<span data-ttu-id="27247-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="27247-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)