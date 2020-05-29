---
description: 从值创建一个数值 `int` 。
title: JsIntToNumber 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 1393c4ac-7189-4e9c-8e54-b0e041c22112
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: dd8f51638292346ec3058f9537d72b8fd21bebc6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563096"
---
# <span data-ttu-id="79565-103">JsIntToNumber 函数</span><span class="sxs-lookup"><span data-stu-id="79565-103">JsIntToNumber Function</span></span>
<span data-ttu-id="79565-104">从值创建一个数值 `int` 。</span><span class="sxs-lookup"><span data-stu-id="79565-104">Creates a number value from an `int` value.</span></span>  
  
## <span data-ttu-id="79565-105">语法</span><span class="sxs-lookup"><span data-stu-id="79565-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIntToNumber(  
   _In_ int intValue,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="79565-106">参数</span><span class="sxs-lookup"><span data-stu-id="79565-106">Parameters</span></span>  
 `intValue`  
 <span data-ttu-id="79565-107">`int`要转换为数字值的。</span><span class="sxs-lookup"><span data-stu-id="79565-107">The `int` to convert to a number value.</span></span>  
  
 `value`  
 <span data-ttu-id="79565-108">新的数字值。</span><span class="sxs-lookup"><span data-stu-id="79565-108">The new number value.</span></span>  
  
## <span data-ttu-id="79565-109">返回值</span><span class="sxs-lookup"><span data-stu-id="79565-109">Return Value</span></span>  
 <span data-ttu-id="79565-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="79565-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="79565-111">备注</span><span class="sxs-lookup"><span data-stu-id="79565-111">Remarks</span></span>  
 <span data-ttu-id="79565-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="79565-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="79565-113">要求</span><span class="sxs-lookup"><span data-stu-id="79565-113">Requirements</span></span>  
 <span data-ttu-id="79565-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="79565-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="79565-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79565-115">See Also</span></span>  
 [<span data-ttu-id="79565-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="79565-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)