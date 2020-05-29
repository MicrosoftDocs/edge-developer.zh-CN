---
description: 创建 Javascript `DataView` 对象。
title: JsCreateDataView 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 161e59eb-d429-46f7-9a38-bbf2149ccf44
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1bf237458e8561b7070e4f3f0d4a14050f028375
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563172"
---
# <span data-ttu-id="47915-103">JsCreateDataView 函数</span><span class="sxs-lookup"><span data-stu-id="47915-103">JsCreateDataView Function</span></span>
<span data-ttu-id="47915-104">创建 Javascript `DataView` 对象。</span><span class="sxs-lookup"><span data-stu-id="47915-104">Creates a Javascript `DataView` object.</span></span>  
  
## <span data-ttu-id="47915-105">语法</span><span class="sxs-lookup"><span data-stu-id="47915-105">Syntax</span></span>  
  
```cpp  
JsErrorCode  JsCreateDataView(  
   _In_ JsValueRef arrayBuffer,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="47915-106">参数</span><span class="sxs-lookup"><span data-stu-id="47915-106">Parameters</span></span>  
 `arrayBuffer`  
 <span data-ttu-id="47915-107">将 `ArrayBuffer` 用作结果对象的存储的现有对象 `DataView` 。</span><span class="sxs-lookup"><span data-stu-id="47915-107">An existing `ArrayBuffer` object to use as the storage for the result `DataView` object.</span></span>  
  
 `byteOffset`  
 <span data-ttu-id="47915-108">从结果的起始位置到引用的开始处的偏移量（以字节为单位） `arrayBuffer` `DataView` 。</span><span class="sxs-lookup"><span data-stu-id="47915-108">The offset in bytes from the start of `arrayBuffer` for result `DataView` to reference.</span></span>  
  
 `byteLength`  
 <span data-ttu-id="47915-109">结果 DataView 引用的 ArrayBuffer 中的字节数。</span><span class="sxs-lookup"><span data-stu-id="47915-109">The number of bytes in the ArrayBuffer for result DataView to reference.</span></span>  
  
 `result`  
 <span data-ttu-id="47915-110">新的 DataView 对象。</span><span class="sxs-lookup"><span data-stu-id="47915-110">The new DataView object.</span></span>  
  
## <span data-ttu-id="47915-111">返回值</span><span class="sxs-lookup"><span data-stu-id="47915-111">Return Value</span></span>  
 <span data-ttu-id="47915-112">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="47915-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="47915-113">备注</span><span class="sxs-lookup"><span data-stu-id="47915-113">Remarks</span></span>  
 <span data-ttu-id="47915-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="47915-114">Requires an active script context.</span></span>  
  
 <span data-ttu-id="47915-115">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="47915-115">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="47915-116">要求</span><span class="sxs-lookup"><span data-stu-id="47915-116">Requirements</span></span>  
 <span data-ttu-id="47915-117">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="47915-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="47915-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47915-118">See Also</span></span>  
 [<span data-ttu-id="47915-119">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="47915-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)