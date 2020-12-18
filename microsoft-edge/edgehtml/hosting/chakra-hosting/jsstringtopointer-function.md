---
description: 检索字符串值的字符串指针。
title: JsStringToPointer 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStringToPointer
helpviewer_keywords:
- JsStringToPointer function
ms.assetid: c7aa7a09-489d-4435-8f8a-aeb62f8875ae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 77b8e16be41d8b5541129b50fa200b947f566342
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232354"
---
# <span data-ttu-id="28868-103">JsStringToPointer 函数</span><span class="sxs-lookup"><span data-stu-id="28868-103">JsStringToPointer Function</span></span>

<span data-ttu-id="28868-104">检索字符串值的字符串指针。</span><span class="sxs-lookup"><span data-stu-id="28868-104">Retrieves the string pointer of a string value.</span></span>  
  
## <span data-ttu-id="28868-105">语法</span><span class="sxs-lookup"><span data-stu-id="28868-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStringToPointer(  
   _In_ JsValueRef value,  
   _Outptr_result_buffer_(*stringLength) const wchar_t **stringValue,  
   _Out_ size_t *stringLength  
);  
```  
  
#### <span data-ttu-id="28868-106">参数</span><span class="sxs-lookup"><span data-stu-id="28868-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="28868-107">要转换为字符串指针的字符串值。</span><span class="sxs-lookup"><span data-stu-id="28868-107">The string value to convert to a string pointer.</span></span>  
  
 `stringValue`  
 <span data-ttu-id="28868-108">字符串指针。</span><span class="sxs-lookup"><span data-stu-id="28868-108">The string pointer.</span></span>  
  
 `stringLength`  
 <span data-ttu-id="28868-109">字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="28868-109">The length of the string.</span></span>  
  
## <span data-ttu-id="28868-110">返回值</span><span class="sxs-lookup"><span data-stu-id="28868-110">Return Value</span></span>  
 <span data-ttu-id="28868-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="28868-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="28868-112">备注</span><span class="sxs-lookup"><span data-stu-id="28868-112">Remarks</span></span>  
 <span data-ttu-id="28868-113">此函数检索字符串值的字符串指针。</span><span class="sxs-lookup"><span data-stu-id="28868-113">This function retrieves the string pointer of a string value.</span></span> <span data-ttu-id="28868-114">如果值的类型不是字符串，它将 `JsErrorInvalidArgument` 失败。</span><span class="sxs-lookup"><span data-stu-id="28868-114">It will fail with `JsErrorInvalidArgument` if the type of the value is not string.</span></span> <span data-ttu-id="28868-115">返回的字符串的生存期与它所返回值的生存期相同，但字符串指针不会被视为对值 (的引用，因此不会阻止从) 。</span><span class="sxs-lookup"><span data-stu-id="28868-115">The lifetime of the string returned will be the same as the lifetime of the value it came from, however the string pointer is not considered a reference to the value (and so will not keep it from being collected).</span></span>  
  
 <span data-ttu-id="28868-116">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="28868-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="28868-117">要求</span><span class="sxs-lookup"><span data-stu-id="28868-117">Requirements</span></span>  
 <span data-ttu-id="28868-118">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="28868-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="28868-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28868-119">See Also</span></span>  
 [<span data-ttu-id="28868-120">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="28868-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
