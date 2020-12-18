---
description: 将已分析的脚本序列化为缓冲区，而不是重复使用。
title: JsSerializeScript 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSerializeScript
helpviewer_keywords:
- JsSerializeScript function
ms.assetid: ca42c194-e1c1-407d-b542-b9d494e3ac4e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 236cf40c91256e999d5390acd395b1e97fe538ad
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232708"
---
# <span data-ttu-id="05101-103">JsSerializeScript 函数</span><span class="sxs-lookup"><span data-stu-id="05101-103">JsSerializeScript Function</span></span>

<span data-ttu-id="05101-104">将已分析的脚本序列化为缓冲区，而不是重复使用。</span><span class="sxs-lookup"><span data-stu-id="05101-104">Serializes a parsed script to a buffer than can be reused.</span></span>  
  
## <span data-ttu-id="05101-105">语法</span><span class="sxs-lookup"><span data-stu-id="05101-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSerializeScript(  
   _In_z_ const wchar_t *script,  
   _Out_writes_to_opt_(*bufferSize,  
   *bufferSize) BYTE *buffer,  
   _Inout_ unsigned long *bufferSize  
);  
```  
  
#### <span data-ttu-id="05101-106">参数</span><span class="sxs-lookup"><span data-stu-id="05101-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="05101-107">要序列化的脚本。</span><span class="sxs-lookup"><span data-stu-id="05101-107">The script to serialize.</span></span>  
  
 `buffer`  
 <span data-ttu-id="05101-108">要放入序列化脚本的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="05101-108">The buffer to put the serialized script into.</span></span> <span data-ttu-id="05101-109">可以是 null。</span><span class="sxs-lookup"><span data-stu-id="05101-109">Can be null.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="05101-110">进入时，缓冲区的大小（以字节为单位）;退出时，保留序列化脚本所需的缓冲区大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="05101-110">On entry, the size of the buffer, in bytes; on exit, the size of the buffer, in bytes, required to hold the serialized script.</span></span>  
  
## <span data-ttu-id="05101-111">返回值</span><span class="sxs-lookup"><span data-stu-id="05101-111">Return Value</span></span>  
 <span data-ttu-id="05101-112">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="05101-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="05101-113">备注</span><span class="sxs-lookup"><span data-stu-id="05101-113">Remarks</span></span>  
 `JsSerializeScript` <span data-ttu-id="05101-114">分析脚本，然后以独立于运行时的格式存储脚本的已分析形式。</span><span class="sxs-lookup"><span data-stu-id="05101-114">parses a script and then stores the parsed form of the script in a runtime-independent format.</span></span> <span data-ttu-id="05101-115">然后，可以在任何运行时中对序列化脚本进行反序列化，而无需重新分析该脚本。</span><span class="sxs-lookup"><span data-stu-id="05101-115">The serialized script then can be deserialized in any runtime without requiring the script to be re-parsed.</span></span>  
  
 <span data-ttu-id="05101-116">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="05101-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="05101-117">要求</span><span class="sxs-lookup"><span data-stu-id="05101-117">Requirements</span></span>  
 <span data-ttu-id="05101-118">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="05101-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="05101-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05101-119">See Also</span></span>  
 [<span data-ttu-id="05101-120">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="05101-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
