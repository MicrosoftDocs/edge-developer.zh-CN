---
description: 执行 JavaScript `instanceof` 运算符测试。
title: JsInstanceOf 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 94399a62-b996-4fd2-82ce-1c26e7a4da08
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d8aec1d4512fe937d1fd48aa6f3e88294bf9850c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232580"
---
# <span data-ttu-id="0642c-103">JsInstanceOf 函数</span><span class="sxs-lookup"><span data-stu-id="0642c-103">JsInstanceOf Function</span></span>

<span data-ttu-id="0642c-104">执行 JavaScript `instanceof` 运算符测试。</span><span class="sxs-lookup"><span data-stu-id="0642c-104">Performs JavaScript `instanceof` operator test.</span></span>  
  
## <span data-ttu-id="0642c-105">语法</span><span class="sxs-lookup"><span data-stu-id="0642c-105">Syntax</span></span>  
  
```cpp  
JsInstanceOf(   
  _In_ JsValueRef object,  
  _In_ JsValueRef constructor,  
  _Out_ bool *result  
);  
  
```  
  
#### <span data-ttu-id="0642c-106">参数</span><span class="sxs-lookup"><span data-stu-id="0642c-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="0642c-107">要测试的对象。</span><span class="sxs-lookup"><span data-stu-id="0642c-107">The object to test.</span></span>  
  
 `constructor`  
 <span data-ttu-id="0642c-108">要测试的构造函数函数。</span><span class="sxs-lookup"><span data-stu-id="0642c-108">The constructor function to test against.</span></span>  
  
 `result`  
 <span data-ttu-id="0642c-109">"object instanceof 构造函数"是否为 true。</span><span class="sxs-lookup"><span data-stu-id="0642c-109">Whether the "object instanceof constructor" is true.</span></span>  
  
## <span data-ttu-id="0642c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="0642c-110">Return Value</span></span>  
 <span data-ttu-id="0642c-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="0642c-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0642c-112">备注</span><span class="sxs-lookup"><span data-stu-id="0642c-112">Remarks</span></span>  
 <span data-ttu-id="0642c-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="0642c-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="0642c-114">要求</span><span class="sxs-lookup"><span data-stu-id="0642c-114">Requirements</span></span>  
 <span data-ttu-id="0642c-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="0642c-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0642c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0642c-116">See Also</span></span>  
 [<span data-ttu-id="0642c-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="0642c-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
