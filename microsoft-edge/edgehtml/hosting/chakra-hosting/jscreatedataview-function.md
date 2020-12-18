---
description: 创建 Javascript `DataView` 对象。
title: JsCreateDataView 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 161e59eb-d429-46f7-9a38-bbf2149ccf44
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1d6d170d53f3bfaf885713b6f3abca0b066f8c1d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232196"
---
# <span data-ttu-id="15726-103">JsCreateDataView Function</span><span class="sxs-lookup"><span data-stu-id="15726-103">JsCreateDataView Function</span></span>

<span data-ttu-id="15726-104">创建 Javascript `DataView` 对象。</span><span class="sxs-lookup"><span data-stu-id="15726-104">Creates a Javascript `DataView` object.</span></span>  
  
## <span data-ttu-id="15726-105">语法</span><span class="sxs-lookup"><span data-stu-id="15726-105">Syntax</span></span>  
  
```cpp  
JsErrorCode  JsCreateDataView(  
   _In_ JsValueRef arrayBuffer,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="15726-106">参数</span><span class="sxs-lookup"><span data-stu-id="15726-106">Parameters</span></span>  
 `arrayBuffer`  
 <span data-ttu-id="15726-107">要 `ArrayBuffer` 用作结果对象的存储的现有 `DataView` 对象。</span><span class="sxs-lookup"><span data-stu-id="15726-107">An existing `ArrayBuffer` object to use as the storage for the result `DataView` object.</span></span>  
  
 `byteOffset`  
 <span data-ttu-id="15726-108">结果引用起始位置 `arrayBuffer` 的偏移量（以字节 `DataView` 为单位）。</span><span class="sxs-lookup"><span data-stu-id="15726-108">The offset in bytes from the start of `arrayBuffer` for result `DataView` to reference.</span></span>  
  
 `byteLength`  
 <span data-ttu-id="15726-109">要引用的结果 DataView 的 ArrayBuffer 中的字节数。</span><span class="sxs-lookup"><span data-stu-id="15726-109">The number of bytes in the ArrayBuffer for result DataView to reference.</span></span>  
  
 `result`  
 <span data-ttu-id="15726-110">新的 DataView 对象。</span><span class="sxs-lookup"><span data-stu-id="15726-110">The new DataView object.</span></span>  
  
## <span data-ttu-id="15726-111">返回值</span><span class="sxs-lookup"><span data-stu-id="15726-111">Return Value</span></span>  
 <span data-ttu-id="15726-112">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="15726-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="15726-113">备注</span><span class="sxs-lookup"><span data-stu-id="15726-113">Remarks</span></span>  
 <span data-ttu-id="15726-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="15726-114">Requires an active script context.</span></span>  
  
 <span data-ttu-id="15726-115">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="15726-115">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="15726-116">要求</span><span class="sxs-lookup"><span data-stu-id="15726-116">Requirements</span></span>  
 <span data-ttu-id="15726-117">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="15726-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="15726-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15726-118">See Also</span></span>  
 [<span data-ttu-id="15726-119">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="15726-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
