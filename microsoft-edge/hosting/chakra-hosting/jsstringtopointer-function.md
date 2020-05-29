---
description: 检索字符串值的字符串指针。
title: JsStringToPointer 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStringToPointer
helpviewer_keywords:
- JsStringToPointer function
ms.assetid: c7aa7a09-489d-4435-8f8a-aeb62f8875ae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1f5997894c4ea479378a323b230492dde28ab177
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564070"
---
# <span data-ttu-id="1734c-103">JsStringToPointer 函数</span><span class="sxs-lookup"><span data-stu-id="1734c-103">JsStringToPointer Function</span></span>
<span data-ttu-id="1734c-104">检索字符串值的字符串指针。</span><span class="sxs-lookup"><span data-stu-id="1734c-104">Retrieves the string pointer of a string value.</span></span>  
  
## <span data-ttu-id="1734c-105">语法</span><span class="sxs-lookup"><span data-stu-id="1734c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStringToPointer(  
   _In_ JsValueRef value,  
   _Outptr_result_buffer_(*stringLength) const wchar_t **stringValue,  
   _Out_ size_t *stringLength  
);  
```  
  
#### <span data-ttu-id="1734c-106">参数</span><span class="sxs-lookup"><span data-stu-id="1734c-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="1734c-107">要转换为字符串指针的字符串值。</span><span class="sxs-lookup"><span data-stu-id="1734c-107">The string value to convert to a string pointer.</span></span>  
  
 `stringValue`  
 <span data-ttu-id="1734c-108">字符串指针。</span><span class="sxs-lookup"><span data-stu-id="1734c-108">The string pointer.</span></span>  
  
 `stringLength`  
 <span data-ttu-id="1734c-109">字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="1734c-109">The length of the string.</span></span>  
  
## <span data-ttu-id="1734c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="1734c-110">Return Value</span></span>  
 <span data-ttu-id="1734c-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="1734c-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="1734c-112">备注</span><span class="sxs-lookup"><span data-stu-id="1734c-112">Remarks</span></span>  
 <span data-ttu-id="1734c-113">此函数检索字符串值的字符串指针。</span><span class="sxs-lookup"><span data-stu-id="1734c-113">This function retrieves the string pointer of a string value.</span></span> <span data-ttu-id="1734c-114">`JsErrorInvalidArgument`如果值的类型不是字符串，它将失败。</span><span class="sxs-lookup"><span data-stu-id="1734c-114">It will fail with `JsErrorInvalidArgument` if the type of the value is not string.</span></span> <span data-ttu-id="1734c-115">返回的字符串的生存期将与它所来自的值的生存期相同，但字符串指针不会被视为对值的引用（因此将不会阻止回收它）。</span><span class="sxs-lookup"><span data-stu-id="1734c-115">The lifetime of the string returned will be the same as the lifetime of the value it came from, however the string pointer is not considered a reference to the value (and so will not keep it from being collected).</span></span>  
  
 <span data-ttu-id="1734c-116">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="1734c-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="1734c-117">要求</span><span class="sxs-lookup"><span data-stu-id="1734c-117">Requirements</span></span>  
 <span data-ttu-id="1734c-118">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="1734c-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1734c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1734c-119">See Also</span></span>  
 [<span data-ttu-id="1734c-120">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="1734c-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)