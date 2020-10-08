---
description: 创建 Javascript `ArrayBuffer` 对象以访问外部内存。
title: JsCreateExternalArrayBuffer 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a02aaec-0f67-4bf9-b37c-71cdb1410ca4
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 376eedda18393436d9dce340753586bf32599b21
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563166"
---
# <span data-ttu-id="fec1e-103">JsCreateExternalArrayBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="fec1e-103">JsCreateExternalArrayBuffer Function</span></span>
<span data-ttu-id="fec1e-104">创建 Javascript `ArrayBuffer` 对象以访问外部内存。</span><span class="sxs-lookup"><span data-stu-id="fec1e-104">Creates a Javascript `ArrayBuffer` object to access external memory.</span></span>
  
## <span data-ttu-id="fec1e-105">语法</span><span class="sxs-lookup"><span data-stu-id="fec1e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateExternalArrayBuffer(  
  _Pre_maybenull_ _Pre_writable_byte_size_(byteLength) void *data,  
  _In_ unsigned int byteLength,  
  _In_opt_ JsFinalizeCallback finalizeCallback,  
  _In_opt_ void *callbackState,  
  _Out_ JsValueRef *result  
);  
  
```  
  
#### <span data-ttu-id="fec1e-106">参数</span><span class="sxs-lookup"><span data-stu-id="fec1e-106">Parameters</span></span>  
 `data`  
 <span data-ttu-id="fec1e-107">指向外部内存的指针。</span><span class="sxs-lookup"><span data-stu-id="fec1e-107">A pointer to the external memory.</span></span>  
  
 `byteLength`  
 <span data-ttu-id="fec1e-108">外部内存中的字节数。</span><span class="sxs-lookup"><span data-stu-id="fec1e-108">The number of bytes in the external memory.</span></span>  
  
 `finalizeCallback`  
 <span data-ttu-id="fec1e-109">终止对象时的回调。</span><span class="sxs-lookup"><span data-stu-id="fec1e-109">A callback for when the object is finalized.</span></span> <span data-ttu-id="fec1e-110">可能为 null。</span><span class="sxs-lookup"><span data-stu-id="fec1e-110">May be null.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="fec1e-111">用户提供的状态将传回 finalizeCallback。</span><span class="sxs-lookup"><span data-stu-id="fec1e-111">User provided state that will be passed back to finalizeCallback.</span></span>  
  
 `result`  
 <span data-ttu-id="fec1e-112">新 `ArrayBuffer` 对象。</span><span class="sxs-lookup"><span data-stu-id="fec1e-112">The new `ArrayBuffer` object.</span></span>  
  
## <span data-ttu-id="fec1e-113">返回值</span><span class="sxs-lookup"><span data-stu-id="fec1e-113">Return Value</span></span>  
 <span data-ttu-id="fec1e-114">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="fec1e-114">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="fec1e-115">备注</span><span class="sxs-lookup"><span data-stu-id="fec1e-115">Remarks</span></span>  
 <span data-ttu-id="fec1e-116">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="fec1e-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="fec1e-117">要求</span><span class="sxs-lookup"><span data-stu-id="fec1e-117">Requirements</span></span>  
 <span data-ttu-id="fec1e-118">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="fec1e-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="fec1e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fec1e-119">See Also</span></span>  
 [<span data-ttu-id="fec1e-120">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="fec1e-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)