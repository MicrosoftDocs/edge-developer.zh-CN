---
description: 创建一个 JavaScript 值，该值是传入的指针的投影 `IInspectable` 。
title: JsInspectableToObject 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: dd0ad567-2ba8-4a63-bee4-2c6ff5ce9fa9
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 26ce17eb3abcefcf9a1f0cc773e9fe4c3aaf05cd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563099"
---
# <span data-ttu-id="7812c-103">JsInspectableToObject 函数</span><span class="sxs-lookup"><span data-stu-id="7812c-103">JsInspectableToObject Function</span></span>
<span data-ttu-id="7812c-104">创建一个 JavaScript 值，该值是传入的指针的投影 `IInspectable` 。</span><span class="sxs-lookup"><span data-stu-id="7812c-104">Creates a JavaScript value that is a projection of the passed in `IInspectable` pointer.</span></span>  
  
## <span data-ttu-id="7812c-105">语法</span><span class="sxs-lookup"><span data-stu-id="7812c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsInspectableToObject(  
        _In_ IInspectable  *inspectable,  
        _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="7812c-106">参数</span><span class="sxs-lookup"><span data-stu-id="7812c-106">Parameters</span></span>  
 `inspectable`  
 <span data-ttu-id="7812c-107">`IInspectable`要投影的。</span><span class="sxs-lookup"><span data-stu-id="7812c-107">A `IInspectable` to be projected.</span></span>  
  
 `value`  
 <span data-ttu-id="7812c-108">作为的投影的 JavaScript 值 `IInspectable` 。</span><span class="sxs-lookup"><span data-stu-id="7812c-108">A JavaScript value that is a projection of the `IInspectable`.</span></span>  
  
## <span data-ttu-id="7812c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="7812c-109">Return Value</span></span>  
 <span data-ttu-id="7812c-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="7812c-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7812c-111">备注</span><span class="sxs-lookup"><span data-stu-id="7812c-111">Remarks</span></span>  
 <span data-ttu-id="7812c-112">所投影值可由脚本用于调用 WinRT 对象。</span><span class="sxs-lookup"><span data-stu-id="7812c-112">The projected value can be used by script to call a WinRT object.</span></span> <span data-ttu-id="7812c-113">主机负责强制执行 COM 线程处理规则。</span><span class="sxs-lookup"><span data-stu-id="7812c-113">Hosts are responsible for enforcing COM threading rules.</span></span>  
  
 <span data-ttu-id="7812c-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="7812c-114">Requires an active script context.</span></span>  
  
 <span data-ttu-id="7812c-115">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="7812c-115">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="7812c-116">要求</span><span class="sxs-lookup"><span data-stu-id="7812c-116">Requirements</span></span>  
 <span data-ttu-id="7812c-117">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="7812c-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7812c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7812c-118">See Also</span></span>  
 [<span data-ttu-id="7812c-119">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="7812c-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)