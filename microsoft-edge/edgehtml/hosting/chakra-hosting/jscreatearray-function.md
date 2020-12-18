---
description: 创建 Javascript 数组对象。
title: JsCreateArray 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateArray
helpviewer_keywords:
- JsCreateArray function
ms.assetid: a119949a-e427-4349-9d00-5ec20fb9319c
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 34ce07055fa3d4d24188d7edbcedc3f08973e233
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232201"
---
# <span data-ttu-id="0d96c-103">JsCreateArray 函数</span><span class="sxs-lookup"><span data-stu-id="0d96c-103">JsCreateArray Function</span></span>

<span data-ttu-id="0d96c-104">创建 Javascript 数组对象。</span><span class="sxs-lookup"><span data-stu-id="0d96c-104">Creates a Javascript array object.</span></span>  
  
## <span data-ttu-id="0d96c-105">语法</span><span class="sxs-lookup"><span data-stu-id="0d96c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateArray(  
   _In_ unsigned int length,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="0d96c-106">参数</span><span class="sxs-lookup"><span data-stu-id="0d96c-106">Parameters</span></span>  
 `length`  
 <span data-ttu-id="0d96c-107">数组的初始长度。</span><span class="sxs-lookup"><span data-stu-id="0d96c-107">The initial length of the array.</span></span>  
  
 `result`  
 <span data-ttu-id="0d96c-108">新的数组对象。</span><span class="sxs-lookup"><span data-stu-id="0d96c-108">The new array object.</span></span>  
  
## <span data-ttu-id="0d96c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0d96c-109">Return Value</span></span>  
 <span data-ttu-id="0d96c-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="0d96c-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0d96c-111">备注</span><span class="sxs-lookup"><span data-stu-id="0d96c-111">Remarks</span></span>  
 <span data-ttu-id="0d96c-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="0d96c-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="0d96c-113">要求</span><span class="sxs-lookup"><span data-stu-id="0d96c-113">Requirements</span></span>  
 <span data-ttu-id="0d96c-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="0d96c-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0d96c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d96c-115">See Also</span></span>  
 [<span data-ttu-id="0d96c-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="0d96c-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
