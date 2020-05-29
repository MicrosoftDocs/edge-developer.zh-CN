---
description: 创建一个 Javascript 数组对象。
title: JsCreateArray 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateArray
helpviewer_keywords:
- JsCreateArray function
ms.assetid: a119949a-e427-4349-9d00-5ec20fb9319c
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: fb6a65df1484eb308224a42bb5a65443855c6215
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563178"
---
# <span data-ttu-id="6ad46-103">JsCreateArray 函数</span><span class="sxs-lookup"><span data-stu-id="6ad46-103">JsCreateArray Function</span></span>
<span data-ttu-id="6ad46-104">创建一个 Javascript 数组对象。</span><span class="sxs-lookup"><span data-stu-id="6ad46-104">Creates a Javascript array object.</span></span>  
  
## <span data-ttu-id="6ad46-105">语法</span><span class="sxs-lookup"><span data-stu-id="6ad46-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateArray(  
   _In_ unsigned int length,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="6ad46-106">参数</span><span class="sxs-lookup"><span data-stu-id="6ad46-106">Parameters</span></span>  
 `length`  
 <span data-ttu-id="6ad46-107">数组的初始长度。</span><span class="sxs-lookup"><span data-stu-id="6ad46-107">The initial length of the array.</span></span>  
  
 `result`  
 <span data-ttu-id="6ad46-108">新数组对象。</span><span class="sxs-lookup"><span data-stu-id="6ad46-108">The new array object.</span></span>  
  
## <span data-ttu-id="6ad46-109">返回值</span><span class="sxs-lookup"><span data-stu-id="6ad46-109">Return Value</span></span>  
 <span data-ttu-id="6ad46-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="6ad46-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6ad46-111">备注</span><span class="sxs-lookup"><span data-stu-id="6ad46-111">Remarks</span></span>  
 <span data-ttu-id="6ad46-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="6ad46-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="6ad46-113">要求</span><span class="sxs-lookup"><span data-stu-id="6ad46-113">Requirements</span></span>  
 <span data-ttu-id="6ad46-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="6ad46-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6ad46-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ad46-115">See Also</span></span>  
 [<span data-ttu-id="6ad46-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="6ad46-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)