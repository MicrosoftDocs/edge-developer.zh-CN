---
description: 设置一个回调函数，该函数由运行时在对象的垃圾回收之前调用。
title: JsSetObjectBeforeCollectCallback 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: ea2cbd94-d8b0-4fa9-a4a1-c75a4e338eaf
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 77a59c6ace96809c0b232c96aa9639555e7badcd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564172"
---
# <span data-ttu-id="6d8fc-103">JsSetObjectBeforeCollectCallback 函数</span><span class="sxs-lookup"><span data-stu-id="6d8fc-103">JsSetObjectBeforeCollectCallback Function</span></span>
<span data-ttu-id="6d8fc-104">设置一个回调函数，该函数由运行时在对象的垃圾回收之前调用。</span><span class="sxs-lookup"><span data-stu-id="6d8fc-104">Sets a callback function that is called by the runtime before garbage collection of an object.</span></span>  
  
## <span data-ttu-id="6d8fc-105">语法</span><span class="sxs-lookup"><span data-stu-id="6d8fc-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetObjectBeforeCollectCallback(  
   _In_ JsRef ref,  
   _In_opt_ void *callbackState,  
   _In_ JsObjectBeforeCollectCallback objectBeforeCollectCallback  
);  
```  
  
#### <span data-ttu-id="6d8fc-106">参数</span><span class="sxs-lookup"><span data-stu-id="6d8fc-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="6d8fc-107">要为其注册回调的对象。</span><span class="sxs-lookup"><span data-stu-id="6d8fc-107">The object for which to register the callback.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="6d8fc-108">用户提供的状态将传回回调。</span><span class="sxs-lookup"><span data-stu-id="6d8fc-108">User-provided state that will be passed back to the callback.</span></span>  
  
 `objectBeforeCollectCallback`  
 <span data-ttu-id="6d8fc-109">正在设置的回调函数。</span><span class="sxs-lookup"><span data-stu-id="6d8fc-109">The callback function being set.</span></span> <span data-ttu-id="6d8fc-110">使用 null 清除以前注册的回调。</span><span class="sxs-lookup"><span data-stu-id="6d8fc-110">Use null to clear previously registered callback.</span></span>  
  
## <span data-ttu-id="6d8fc-111">返回值</span><span class="sxs-lookup"><span data-stu-id="6d8fc-111">Return Value</span></span>  
 <span data-ttu-id="6d8fc-112">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="6d8fc-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6d8fc-113">备注</span><span class="sxs-lookup"><span data-stu-id="6d8fc-113">Remarks</span></span>  
 <span data-ttu-id="6d8fc-114">回调将在当前运行时执行线程上调用，因此执行会被阻止，直到回调完成。</span><span class="sxs-lookup"><span data-stu-id="6d8fc-114">The callback is invoked on the current runtime execution thread, therefore execution is blocked until the callback completes.</span></span>  
  
 <span data-ttu-id="6d8fc-115">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="6d8fc-115">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="6d8fc-116">要求</span><span class="sxs-lookup"><span data-stu-id="6d8fc-116">Requirements</span></span>  
 <span data-ttu-id="6d8fc-117">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="6d8fc-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6d8fc-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d8fc-118">See Also</span></span>  
 [<span data-ttu-id="6d8fc-119">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="6d8fc-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)