---
description: 创建一个 JavaScript 值，该值是传入指针的 `IInspectable` 投影。
title: JsInspectableToObject 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: dd0ad567-2ba8-4a63-bee4-2c6ff5ce9fa9
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a5d3d91b38c9db5de2eb8fb02526f6072f0f5147
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232582"
---
# <span data-ttu-id="ac73c-103">JsInspectableToObject 函数</span><span class="sxs-lookup"><span data-stu-id="ac73c-103">JsInspectableToObject Function</span></span>

<span data-ttu-id="ac73c-104">创建一个 JavaScript 值，该值是传入指针的 `IInspectable` 投影。</span><span class="sxs-lookup"><span data-stu-id="ac73c-104">Creates a JavaScript value that is a projection of the passed in `IInspectable` pointer.</span></span>  
  
## <span data-ttu-id="ac73c-105">语法</span><span class="sxs-lookup"><span data-stu-id="ac73c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsInspectableToObject(  
        _In_ IInspectable  *inspectable,  
        _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="ac73c-106">参数</span><span class="sxs-lookup"><span data-stu-id="ac73c-106">Parameters</span></span>  
 `inspectable`  
 <span data-ttu-id="ac73c-107">要 `IInspectable` 规划的 A。</span><span class="sxs-lookup"><span data-stu-id="ac73c-107">A `IInspectable` to be projected.</span></span>  
  
 `value`  
 <span data-ttu-id="ac73c-108">作为投影的 JavaScript 值 `IInspectable` 。</span><span class="sxs-lookup"><span data-stu-id="ac73c-108">A JavaScript value that is a projection of the `IInspectable`.</span></span>  
  
## <span data-ttu-id="ac73c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ac73c-109">Return Value</span></span>  
 <span data-ttu-id="ac73c-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="ac73c-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ac73c-111">备注</span><span class="sxs-lookup"><span data-stu-id="ac73c-111">Remarks</span></span>  
 <span data-ttu-id="ac73c-112">脚本可以使用预计值调用 WinRT 对象。</span><span class="sxs-lookup"><span data-stu-id="ac73c-112">The projected value can be used by script to call a WinRT object.</span></span> <span data-ttu-id="ac73c-113">主机负责强制实施 COM 线程规则。</span><span class="sxs-lookup"><span data-stu-id="ac73c-113">Hosts are responsible for enforcing COM threading rules.</span></span>  
  
 <span data-ttu-id="ac73c-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="ac73c-114">Requires an active script context.</span></span>  
  
 <span data-ttu-id="ac73c-115">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="ac73c-115">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="ac73c-116">要求</span><span class="sxs-lookup"><span data-stu-id="ac73c-116">Requirements</span></span>  
 <span data-ttu-id="ac73c-117">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ac73c-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ac73c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac73c-118">See Also</span></span>  
 [<span data-ttu-id="ac73c-119">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="ac73c-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
