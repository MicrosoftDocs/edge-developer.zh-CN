---
description: 将 JavaScript 对象解包到 `IInspectable` 指针。
title: JsObjectToInspectable 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 1d15b0b8-516f-4fc6-95aa-2ddd65f8ab75
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c7127e1cf1372020e0df00b81ed172739379426f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564221"
---
# <span data-ttu-id="47826-103">JsObjectToInspectable 函数</span><span class="sxs-lookup"><span data-stu-id="47826-103">JsObjectToInspectable Function</span></span>
<span data-ttu-id="47826-104">将 JavaScript 对象解包到 `IInspectable` 指针。</span><span class="sxs-lookup"><span data-stu-id="47826-104">Unwraps a JavaScript object to an `IInspectable` pointer.</span></span>  
  
## <span data-ttu-id="47826-105">语法</span><span class="sxs-lookup"><span data-stu-id="47826-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsObjectToInspectable(  
   _In_ JsValueRef value,  
   _Out_ IInspectable  **inspectable  
);  
```  
  
#### <span data-ttu-id="47826-106">参数</span><span class="sxs-lookup"><span data-stu-id="47826-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="47826-107">应投影到的 JavaScript 值 `IInspectable` 。</span><span class="sxs-lookup"><span data-stu-id="47826-107">A JavaScript value that should be projected to `IInspectable`.</span></span>  
  
 `inspectable`  
 <span data-ttu-id="47826-108">`IInspectable`对象的值。</span><span class="sxs-lookup"><span data-stu-id="47826-108">An `IInspectable` value of the object.</span></span>  
  
## <span data-ttu-id="47826-109">返回值</span><span class="sxs-lookup"><span data-stu-id="47826-109">Return Value</span></span>  
 <span data-ttu-id="47826-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="47826-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="47826-111">备注</span><span class="sxs-lookup"><span data-stu-id="47826-111">Remarks</span></span>  
 <span data-ttu-id="47826-112">主机负责强制执行 COM 线程处理规则。</span><span class="sxs-lookup"><span data-stu-id="47826-112">Hosts are responsible for enforcing COM threading rules.</span></span>  
  
 <span data-ttu-id="47826-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="47826-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="47826-114">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="47826-114">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="47826-115">要求</span><span class="sxs-lookup"><span data-stu-id="47826-115">Requirements</span></span>  
 <span data-ttu-id="47826-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="47826-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="47826-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47826-117">See Also</span></span>  
 [<span data-ttu-id="47826-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="47826-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)