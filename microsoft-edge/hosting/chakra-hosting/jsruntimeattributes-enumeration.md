---
description: '运行时的属性。 '
title: JsRuntimeAttributes 枚举 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsRuntimeAttributes
helpviewer_keywords:
- JsRuntimeAttributes enumeration
ms.assetid: f76d82e9-a695-4d6a-96c1-b3a4d27fed68
caps.latest.revision: 14
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9b8f6788f1de4988e3936701cfc742a564c92cfd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564191"
---
# <span data-ttu-id="0601d-103">JsRuntimeAttributes 枚举</span><span class="sxs-lookup"><span data-stu-id="0601d-103">JsRuntimeAttributes Enumeration</span></span>
<span data-ttu-id="0601d-104">运行时的属性。</span><span class="sxs-lookup"><span data-stu-id="0601d-104">Attributes of a runtime.</span></span>  
  
## <span data-ttu-id="0601d-105">语法</span><span class="sxs-lookup"><span data-stu-id="0601d-105">Syntax</span></span>  
  
```cpp  
enum JsRuntimeAttributes;  
```  
  
## <span data-ttu-id="0601d-106">成员</span><span class="sxs-lookup"><span data-stu-id="0601d-106">Members</span></span>  
  
### <span data-ttu-id="0601d-107">值</span><span class="sxs-lookup"><span data-stu-id="0601d-107">Values</span></span>  
  
|<span data-ttu-id="0601d-108">名称</span><span class="sxs-lookup"><span data-stu-id="0601d-108">Name</span></span>|<span data-ttu-id="0601d-109">描述</span><span class="sxs-lookup"><span data-stu-id="0601d-109">Description</span></span>|  
|----------|-----------------|  
|`JsRuntimeAttributeAllowScriptInterrupt`|<span data-ttu-id="0601d-110">运行时应支持可靠的脚本中断。</span><span class="sxs-lookup"><span data-stu-id="0601d-110">The runtime should support reliable script interruption.</span></span> <span data-ttu-id="0601d-111">这会增加运行时将以少量运行时性能为代价检查脚本中断请求的位置数。</span><span class="sxs-lookup"><span data-stu-id="0601d-111">This increases the number of places where the runtime will check for a script interrupt request at the cost of a small amount of runtime performance.</span></span>|  
|`JsRuntimeAttributeDisableBackgroundWork`|<span data-ttu-id="0601d-112">运行时不会在后台线程上执行任何工作（如垃圾回收）。</span><span class="sxs-lookup"><span data-stu-id="0601d-112">The runtime will not do any work (such as garbage collection) on background threads.</span></span>|  
|`JsRuntimeAttributeDisableEval`|<span data-ttu-id="0601d-113">Using `eval` 或 `function` 构造函数将引发异常。</span><span class="sxs-lookup"><span data-stu-id="0601d-113">Using `eval` or `function` constructor will throw an exception.</span></span>|  
|`JsRuntimeAttributeDisableNativeCodeGeneration`|<span data-ttu-id="0601d-114">运行时不会生成本机代码。</span><span class="sxs-lookup"><span data-stu-id="0601d-114">Runtime will not generate native code.</span></span>|  
|`JsRuntimeAttributeEnableExperimentalFeatures`|<span data-ttu-id="0601d-115">运行时将启用所有实验功能。</span><span class="sxs-lookup"><span data-stu-id="0601d-115">Runtime will enable all experimental features.</span></span>|  
|`JsRuntimeAttributeEnableIdleProcessing`|<span data-ttu-id="0601d-116">主机将呼叫 `JsIdle` ，因此启用空闲处理。</span><span class="sxs-lookup"><span data-stu-id="0601d-116">Host will call `JsIdle`, so enable idle processing.</span></span> <span data-ttu-id="0601d-117">否则，运行时将略微严格地管理内存。</span><span class="sxs-lookup"><span data-stu-id="0601d-117">Otherwise, the runtime will manage memory slightly more aggressively.</span></span>|  
|`JsRuntimeAttributeDispatchSetExceptionsToDebugger`|<span data-ttu-id="0601d-118">调用 `JsSetException` 还会将异常调度到脚本调试程序（如果有），让调试程序有机会中断异常。</span><span class="sxs-lookup"><span data-stu-id="0601d-118">Calling `JsSetException` will also dispatch the exception to the script debugger (if any) giving the debugger a chance to break on the exception.</span></span>|  
|`JsRuntimeAttributeNone`|<span data-ttu-id="0601d-119">无特殊属性。</span><span class="sxs-lookup"><span data-stu-id="0601d-119">No special attributes.</span></span>|  
  
## <span data-ttu-id="0601d-120">要求</span><span class="sxs-lookup"><span data-stu-id="0601d-120">Requirements</span></span>  
 <span data-ttu-id="0601d-121">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="0601d-121">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0601d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0601d-122">See Also</span></span>  
 [<span data-ttu-id="0601d-123">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="0601d-123">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)