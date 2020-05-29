---
description: 执行 JavaScript `instanceof` 运算符测试。
title: JsInstanceOf 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 94399a62-b996-4fd2-82ce-1c26e7a4da08
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 3a7e2397abe5dcb25346e583a0fdab301b8b45f4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563097"
---
# <span data-ttu-id="ba721-103">JsInstanceOf 函数</span><span class="sxs-lookup"><span data-stu-id="ba721-103">JsInstanceOf Function</span></span>
<span data-ttu-id="ba721-104">执行 JavaScript `instanceof` 运算符测试。</span><span class="sxs-lookup"><span data-stu-id="ba721-104">Performs JavaScript `instanceof` operator test.</span></span>  
  
## <span data-ttu-id="ba721-105">语法</span><span class="sxs-lookup"><span data-stu-id="ba721-105">Syntax</span></span>  
  
```cpp  
JsInstanceOf(   
  _In_ JsValueRef object,  
  _In_ JsValueRef constructor,  
  _Out_ bool *result  
);  
  
```  
  
#### <span data-ttu-id="ba721-106">参数</span><span class="sxs-lookup"><span data-stu-id="ba721-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="ba721-107">要测试的对象。</span><span class="sxs-lookup"><span data-stu-id="ba721-107">The object to test.</span></span>  
  
 `constructor`  
 <span data-ttu-id="ba721-108">要对其进行测试的构造函数。</span><span class="sxs-lookup"><span data-stu-id="ba721-108">The constructor function to test against.</span></span>  
  
 `result`  
 <span data-ttu-id="ba721-109">"Object instanceof 构造函数" 是否为 true。</span><span class="sxs-lookup"><span data-stu-id="ba721-109">Whether the "object instanceof constructor" is true.</span></span>  
  
## <span data-ttu-id="ba721-110">返回值</span><span class="sxs-lookup"><span data-stu-id="ba721-110">Return Value</span></span>  
 <span data-ttu-id="ba721-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="ba721-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ba721-112">备注</span><span class="sxs-lookup"><span data-stu-id="ba721-112">Remarks</span></span>  
 <span data-ttu-id="ba721-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="ba721-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ba721-114">要求</span><span class="sxs-lookup"><span data-stu-id="ba721-114">Requirements</span></span>  
 <span data-ttu-id="ba721-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="ba721-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ba721-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba721-116">See Also</span></span>  
 [<span data-ttu-id="ba721-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="ba721-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)