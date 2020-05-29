---
description: 创建 JavaScript 符号。
title: JsCreateSymbol 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 2fccc5d9-f857-46cd-9aeb-f0a2e7cdee6b
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: a4e634e6f0726ca32ad1056129186ce941edb77b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563151"
---
# <span data-ttu-id="3819a-103">JsCreateSymbol 函数</span><span class="sxs-lookup"><span data-stu-id="3819a-103">JsCreateSymbol Function</span></span>
<span data-ttu-id="3819a-104">创建 JavaScript 符号。</span><span class="sxs-lookup"><span data-stu-id="3819a-104">Creates a JavaScript symbol.</span></span>
  
## <span data-ttu-id="3819a-105">语法</span><span class="sxs-lookup"><span data-stu-id="3819a-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateSymbol(  
   _In_ JsValueRef description,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="3819a-106">参数</span><span class="sxs-lookup"><span data-stu-id="3819a-106">Parameters</span></span>  
 `description`  
 <span data-ttu-id="3819a-107">符号的字符串说明。</span><span class="sxs-lookup"><span data-stu-id="3819a-107">The string description of the symbol.</span></span> <span data-ttu-id="3819a-108">可以为 null。</span><span class="sxs-lookup"><span data-stu-id="3819a-108">Can be null.</span></span>  
  
 `result`  
 <span data-ttu-id="3819a-109">新符号。</span><span class="sxs-lookup"><span data-stu-id="3819a-109">The new symbol.</span></span>  
  
## <span data-ttu-id="3819a-110">返回值</span><span class="sxs-lookup"><span data-stu-id="3819a-110">Return Value</span></span>  
 <span data-ttu-id="3819a-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="3819a-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="3819a-112">备注</span><span class="sxs-lookup"><span data-stu-id="3819a-112">Remarks</span></span>  
 <span data-ttu-id="3819a-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="3819a-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="3819a-114">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="3819a-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="3819a-115">要求</span><span class="sxs-lookup"><span data-stu-id="3819a-115">Requirements</span></span>  
 <span data-ttu-id="3819a-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="3819a-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="3819a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3819a-117">See Also</span></span>  
 [<span data-ttu-id="3819a-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="3819a-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)