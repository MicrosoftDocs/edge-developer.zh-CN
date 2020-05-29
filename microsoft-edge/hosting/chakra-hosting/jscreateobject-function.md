---
description: 创建新对象。
title: JsCreateObject 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateObject
helpviewer_keywords:
- JsCreateObject function
ms.assetid: 6c1d01a4-9254-443e-b974-6f0b0c861ca2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9ed988aae0921978819d379562d4a966e4a082a0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563160"
---
# <span data-ttu-id="43f57-103">JsCreateObject 函数</span><span class="sxs-lookup"><span data-stu-id="43f57-103">JsCreateObject Function</span></span>
<span data-ttu-id="43f57-104">创建新对象。</span><span class="sxs-lookup"><span data-stu-id="43f57-104">Creates a new object.</span></span>
  
## <span data-ttu-id="43f57-105">语法</span><span class="sxs-lookup"><span data-stu-id="43f57-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateObject(  
   _Out_ JsValueRef *object  
);  
```  
  
#### <span data-ttu-id="43f57-106">参数</span><span class="sxs-lookup"><span data-stu-id="43f57-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="43f57-107">新对象。</span><span class="sxs-lookup"><span data-stu-id="43f57-107">The new object.</span></span>  
  
## <span data-ttu-id="43f57-108">返回值</span><span class="sxs-lookup"><span data-stu-id="43f57-108">Return Value</span></span>  
 <span data-ttu-id="43f57-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="43f57-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="43f57-110">备注</span><span class="sxs-lookup"><span data-stu-id="43f57-110">Remarks</span></span>  
 <span data-ttu-id="43f57-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="43f57-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="43f57-112">要求</span><span class="sxs-lookup"><span data-stu-id="43f57-112">Requirements</span></span>  
 <span data-ttu-id="43f57-113">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="43f57-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="43f57-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43f57-114">See Also</span></span>  
 [<span data-ttu-id="43f57-115">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="43f57-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)