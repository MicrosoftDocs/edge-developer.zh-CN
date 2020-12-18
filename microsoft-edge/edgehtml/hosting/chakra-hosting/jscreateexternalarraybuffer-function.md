---
description: 创建 Javascript `ArrayBuffer` 对象以访问外部内存。
title: JsCreateExternalArrayBuffer 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: 4a02aaec-0f67-4bf9-b37c-71cdb1410ca4
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 78c0d3c8b298876358f247c86a488b6f10e52c6d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232589"
---
# <span data-ttu-id="d3c61-103">JsCreateExternalArrayBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="d3c61-103">JsCreateExternalArrayBuffer Function</span></span>

<span data-ttu-id="d3c61-104">创建 Javascript `ArrayBuffer` 对象以访问外部内存。</span><span class="sxs-lookup"><span data-stu-id="d3c61-104">Creates a Javascript `ArrayBuffer` object to access external memory.</span></span>
  
## <span data-ttu-id="d3c61-105">语法</span><span class="sxs-lookup"><span data-stu-id="d3c61-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateExternalArrayBuffer(  
  _Pre_maybenull_ _Pre_writable_byte_size_(byteLength) void *data,  
  _In_ unsigned int byteLength,  
  _In_opt_ JsFinalizeCallback finalizeCallback,  
  _In_opt_ void *callbackState,  
  _Out_ JsValueRef *result  
);  
  
```  
  
#### <span data-ttu-id="d3c61-106">参数</span><span class="sxs-lookup"><span data-stu-id="d3c61-106">Parameters</span></span>  
 `data`  
 <span data-ttu-id="d3c61-107">指向外部内存的指针。</span><span class="sxs-lookup"><span data-stu-id="d3c61-107">A pointer to the external memory.</span></span>  
  
 `byteLength`  
 <span data-ttu-id="d3c61-108">外部内存中的字节数。</span><span class="sxs-lookup"><span data-stu-id="d3c61-108">The number of bytes in the external memory.</span></span>  
  
 `finalizeCallback`  
 <span data-ttu-id="d3c61-109">对象完成时回调。</span><span class="sxs-lookup"><span data-stu-id="d3c61-109">A callback for when the object is finalized.</span></span> <span data-ttu-id="d3c61-110">可能为空。</span><span class="sxs-lookup"><span data-stu-id="d3c61-110">May be null.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="d3c61-111">用户提供的状态将传递回 finalizeCallback。</span><span class="sxs-lookup"><span data-stu-id="d3c61-111">User provided state that will be passed back to finalizeCallback.</span></span>  
  
 `result`  
 <span data-ttu-id="d3c61-112">新 `ArrayBuffer` 对象。</span><span class="sxs-lookup"><span data-stu-id="d3c61-112">The new `ArrayBuffer` object.</span></span>  
  
## <span data-ttu-id="d3c61-113">返回值</span><span class="sxs-lookup"><span data-stu-id="d3c61-113">Return Value</span></span>  
 <span data-ttu-id="d3c61-114">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="d3c61-114">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d3c61-115">备注</span><span class="sxs-lookup"><span data-stu-id="d3c61-115">Remarks</span></span>  
 <span data-ttu-id="d3c61-116">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="d3c61-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="d3c61-117">要求</span><span class="sxs-lookup"><span data-stu-id="d3c61-117">Requirements</span></span>  
 <span data-ttu-id="d3c61-118">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="d3c61-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d3c61-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3c61-119">See Also</span></span>  
 [<span data-ttu-id="d3c61-120">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="d3c61-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
