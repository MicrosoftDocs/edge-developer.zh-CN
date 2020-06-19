---
description: 执行 JavaScript `instanceof` 运算符测试。
title: JsInstanceOf 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 94399a62-b996-4fd2-82ce-1c26e7a4da08
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 4d9bf2e4c3da9f83fdf7c0ef4e2c31df04670420
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10751973"
---
# <span data-ttu-id="dc60c-103">JsInstanceOf 函数</span><span class="sxs-lookup"><span data-stu-id="dc60c-103">JsInstanceOf Function</span></span>
<span data-ttu-id="dc60c-104">执行 JavaScript `instanceof` 运算符测试。</span><span class="sxs-lookup"><span data-stu-id="dc60c-104">Performs JavaScript `instanceof` operator test.</span></span>  
  
## <span data-ttu-id="dc60c-105">语法</span><span class="sxs-lookup"><span data-stu-id="dc60c-105">Syntax</span></span>  
  
```cpp  
JsInstanceOf(   
  _In_ JsValueRef object,  
  _In_ JsValueRef constructor,  
  _Out_ bool *result  
);  
  
```  
  
#### <span data-ttu-id="dc60c-106">参数</span><span class="sxs-lookup"><span data-stu-id="dc60c-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="dc60c-107">要测试的对象。</span><span class="sxs-lookup"><span data-stu-id="dc60c-107">The object to test.</span></span>  
  
 `constructor`  
 <span data-ttu-id="dc60c-108">要对其进行测试的构造函数。</span><span class="sxs-lookup"><span data-stu-id="dc60c-108">The constructor function to test against.</span></span>  
  
 `result`  
 <span data-ttu-id="dc60c-109">"Object instanceof 构造函数" 是否为 true。</span><span class="sxs-lookup"><span data-stu-id="dc60c-109">Whether the "object instanceof constructor" is true.</span></span>  
  
## <span data-ttu-id="dc60c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="dc60c-110">Return Value</span></span>  
 <span data-ttu-id="dc60c-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="dc60c-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="dc60c-112">备注</span><span class="sxs-lookup"><span data-stu-id="dc60c-112">Remarks</span></span>  
 <span data-ttu-id="dc60c-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="dc60c-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="dc60c-114">要求</span><span class="sxs-lookup"><span data-stu-id="dc60c-114">Requirements</span></span>  
 <span data-ttu-id="dc60c-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="dc60c-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="dc60c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc60c-116">See Also</span></span>  
 [<span data-ttu-id="dc60c-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="dc60c-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)