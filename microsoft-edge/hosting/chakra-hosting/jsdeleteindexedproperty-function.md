---
description: 删除对象的指定索引处的值。
title: JsDeleteIndexedProperty 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDeleteIndexedProperty
helpviewer_keywords:
- JsDeleteIndexedProperty function
ms.assetid: cc876839-2ecd-41a8-82d0-c19b3de944e3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6148a9c59105749a78ece73578d4b840501c6ecc
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563139"
---
# <span data-ttu-id="a11bd-103">JsDeleteIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="a11bd-103">JsDeleteIndexedProperty Function</span></span>
<span data-ttu-id="a11bd-104">删除对象的指定索引处的值。</span><span class="sxs-lookup"><span data-stu-id="a11bd-104">Delete the value at the specified index of an object.</span></span>  
  
## <span data-ttu-id="a11bd-105">语法</span><span class="sxs-lookup"><span data-stu-id="a11bd-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDeleteIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index  
);  
```  
  
#### <span data-ttu-id="a11bd-106">参数</span><span class="sxs-lookup"><span data-stu-id="a11bd-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="a11bd-107">要操作的对象。</span><span class="sxs-lookup"><span data-stu-id="a11bd-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="a11bd-108">要删除的索引。</span><span class="sxs-lookup"><span data-stu-id="a11bd-108">The index to delete.</span></span>  
  
## <span data-ttu-id="a11bd-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a11bd-109">Return Value</span></span>  
 <span data-ttu-id="a11bd-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="a11bd-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a11bd-111">备注</span><span class="sxs-lookup"><span data-stu-id="a11bd-111">Remarks</span></span>  
 <span data-ttu-id="a11bd-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="a11bd-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="a11bd-113">要求</span><span class="sxs-lookup"><span data-stu-id="a11bd-113">Requirements</span></span>  
 <span data-ttu-id="a11bd-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="a11bd-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a11bd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a11bd-115">See Also</span></span>  
 [<span data-ttu-id="a11bd-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="a11bd-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)