---
description: 将已分析的脚本序列化为可以重复使用的缓冲区。
title: JsSerializeScript 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSerializeScript
helpviewer_keywords:
- JsSerializeScript function
ms.assetid: ca42c194-e1c1-407d-b542-b9d494e3ac4e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1b45067fddb7ea4dff02e527e460db1270011c61
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564185"
---
# <span data-ttu-id="e37a2-103">JsSerializeScript 函数</span><span class="sxs-lookup"><span data-stu-id="e37a2-103">JsSerializeScript Function</span></span>
<span data-ttu-id="e37a2-104">将已分析的脚本序列化为可以重复使用的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e37a2-104">Serializes a parsed script to a buffer than can be reused.</span></span>  
  
## <span data-ttu-id="e37a2-105">语法</span><span class="sxs-lookup"><span data-stu-id="e37a2-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSerializeScript(  
   _In_z_ const wchar_t *script,  
   _Out_writes_to_opt_(*bufferSize,  
   *bufferSize) BYTE *buffer,  
   _Inout_ unsigned long *bufferSize  
);  
```  
  
#### <span data-ttu-id="e37a2-106">参数</span><span class="sxs-lookup"><span data-stu-id="e37a2-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="e37a2-107">要序列化的脚本。</span><span class="sxs-lookup"><span data-stu-id="e37a2-107">The script to serialize.</span></span>  
  
 `buffer`  
 <span data-ttu-id="e37a2-108">要将序列化的脚本放入的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="e37a2-108">The buffer to put the serialized script into.</span></span> <span data-ttu-id="e37a2-109">可以为 null。</span><span class="sxs-lookup"><span data-stu-id="e37a2-109">Can be null.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="e37a2-110">输入时，缓冲区的大小（以字节为单位）;退出时，保留序列化脚本所需的缓冲区大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="e37a2-110">On entry, the size of the buffer, in bytes; on exit, the size of the buffer, in bytes, required to hold the serialized script.</span></span>  
  
## <span data-ttu-id="e37a2-111">返回值</span><span class="sxs-lookup"><span data-stu-id="e37a2-111">Return Value</span></span>  
 <span data-ttu-id="e37a2-112">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="e37a2-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e37a2-113">备注</span><span class="sxs-lookup"><span data-stu-id="e37a2-113">Remarks</span></span>  
 `JsSerializeScript` <span data-ttu-id="e37a2-114">分析脚本，然后以与运行时无关的格式存储脚本的已分析形式。</span><span class="sxs-lookup"><span data-stu-id="e37a2-114">parses a script and then stores the parsed form of the script in a runtime-independent format.</span></span> <span data-ttu-id="e37a2-115">然后，可以在任何运行时反序列化脚本，而无需重新分析脚本。</span><span class="sxs-lookup"><span data-stu-id="e37a2-115">The serialized script then can be deserialized in any runtime without requiring the script to be re-parsed.</span></span>  
  
 <span data-ttu-id="e37a2-116">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="e37a2-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="e37a2-117">要求</span><span class="sxs-lookup"><span data-stu-id="e37a2-117">Requirements</span></span>  
 <span data-ttu-id="e37a2-118">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="e37a2-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e37a2-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e37a2-119">See Also</span></span>  
 [<span data-ttu-id="e37a2-120">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="e37a2-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)