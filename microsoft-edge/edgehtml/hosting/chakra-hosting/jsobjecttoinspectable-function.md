---
description: 将 JavaScript 对象解包到 `IInspectable` 指针。
title: JsObjectToInspectable 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 1d15b0b8-516f-4fc6-95aa-2ddd65f8ab75
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0d818f798805e2afad4dc87b308258464d31bf92
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232529"
---
# <span data-ttu-id="a84d7-103">JsObjectToInspectable 函数</span><span class="sxs-lookup"><span data-stu-id="a84d7-103">JsObjectToInspectable Function</span></span>

<span data-ttu-id="a84d7-104">将 JavaScript 对象解包到 `IInspectable` 指针。</span><span class="sxs-lookup"><span data-stu-id="a84d7-104">Unwraps a JavaScript object to an `IInspectable` pointer.</span></span>  
  
## <span data-ttu-id="a84d7-105">语法</span><span class="sxs-lookup"><span data-stu-id="a84d7-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsObjectToInspectable(  
   _In_ JsValueRef value,  
   _Out_ IInspectable  **inspectable  
);  
```  
  
#### <span data-ttu-id="a84d7-106">参数</span><span class="sxs-lookup"><span data-stu-id="a84d7-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="a84d7-107">应预测到的 JavaScript 值 `IInspectable` 。</span><span class="sxs-lookup"><span data-stu-id="a84d7-107">A JavaScript value that should be projected to `IInspectable`.</span></span>  
  
 `inspectable`  
 <span data-ttu-id="a84d7-108">`IInspectable`对象的值。</span><span class="sxs-lookup"><span data-stu-id="a84d7-108">An `IInspectable` value of the object.</span></span>  
  
## <span data-ttu-id="a84d7-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a84d7-109">Return Value</span></span>  
 <span data-ttu-id="a84d7-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="a84d7-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a84d7-111">备注</span><span class="sxs-lookup"><span data-stu-id="a84d7-111">Remarks</span></span>  
 <span data-ttu-id="a84d7-112">主机负责强制实施 COM 线程规则。</span><span class="sxs-lookup"><span data-stu-id="a84d7-112">Hosts are responsible for enforcing COM threading rules.</span></span>  
  
 <span data-ttu-id="a84d7-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="a84d7-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="a84d7-114">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="a84d7-114">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="a84d7-115">要求</span><span class="sxs-lookup"><span data-stu-id="a84d7-115">Requirements</span></span>  
 <span data-ttu-id="a84d7-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="a84d7-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a84d7-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a84d7-117">See Also</span></span>  
 [<span data-ttu-id="a84d7-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="a84d7-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
