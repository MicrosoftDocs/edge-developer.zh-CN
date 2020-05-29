---
description: 释放对垃圾回收对象的引用。
title: JsRelease 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsRelease
helpviewer_keywords:
- JsRelease function
ms.assetid: 8714fd0b-5b66-48e0-927e-7b93af6cde7b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 134ba16509b6c2f0c232214d7efba4d8c8915d43
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564205"
---
# <span data-ttu-id="1936e-103">JsRelease 函数</span><span class="sxs-lookup"><span data-stu-id="1936e-103">JsRelease Function</span></span>
<span data-ttu-id="1936e-104">释放对垃圾回收对象的引用。</span><span class="sxs-lookup"><span data-stu-id="1936e-104">Releases a reference to a garbage collected object.</span></span>  
  
## <span data-ttu-id="1936e-105">语法</span><span class="sxs-lookup"><span data-stu-id="1936e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsRelease(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### <span data-ttu-id="1936e-106">参数</span><span class="sxs-lookup"><span data-stu-id="1936e-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="1936e-107">要向其添加引用的对象。</span><span class="sxs-lookup"><span data-stu-id="1936e-107">The object to add a reference to.</span></span>  
  
 `count`  
 <span data-ttu-id="1936e-108">对象的新引用计数（可以传入 null）。</span><span class="sxs-lookup"><span data-stu-id="1936e-108">The object's new reference count (can pass in null).</span></span>  
  
## <span data-ttu-id="1936e-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1936e-109">Return Value</span></span>  
 <span data-ttu-id="1936e-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="1936e-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="1936e-111">备注</span><span class="sxs-lookup"><span data-stu-id="1936e-111">Remarks</span></span>  
 <span data-ttu-id="1936e-112">删除 `JsRef` 由创建的句柄的引用 `JsAddRef` 。</span><span class="sxs-lookup"><span data-stu-id="1936e-112">Removes a reference to a `JsRef` handle that was created by `JsAddRef`.</span></span>  
  
## <span data-ttu-id="1936e-113">要求</span><span class="sxs-lookup"><span data-stu-id="1936e-113">Requirements</span></span>  
 <span data-ttu-id="1936e-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="1936e-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1936e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1936e-115">See Also</span></span>  
 [<span data-ttu-id="1936e-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="1936e-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)