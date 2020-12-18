---
description: '运行时的属性。 '
title: JsRuntimeAttributes 枚举 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsRuntimeAttributes
helpviewer_keywords:
- JsRuntimeAttributes enumeration
ms.assetid: f76d82e9-a695-4d6a-96c1-b3a4d27fed68
caps.latest.revision: 14
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: bbc5341c3214d9796278d334507e284989ff45dd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232322"
---
# <span data-ttu-id="2a43c-103">JsRuntimeAttributes 枚举</span><span class="sxs-lookup"><span data-stu-id="2a43c-103">JsRuntimeAttributes Enumeration</span></span>

<span data-ttu-id="2a43c-104">运行时的属性。</span><span class="sxs-lookup"><span data-stu-id="2a43c-104">Attributes of a runtime.</span></span>  
  
## <span data-ttu-id="2a43c-105">语法</span><span class="sxs-lookup"><span data-stu-id="2a43c-105">Syntax</span></span>  
  
```cpp  
enum JsRuntimeAttributes;  
```  
  
## <span data-ttu-id="2a43c-106">成员</span><span class="sxs-lookup"><span data-stu-id="2a43c-106">Members</span></span>  
  
### <span data-ttu-id="2a43c-107">值</span><span class="sxs-lookup"><span data-stu-id="2a43c-107">Values</span></span>  
  
|<span data-ttu-id="2a43c-108">名称</span><span class="sxs-lookup"><span data-stu-id="2a43c-108">Name</span></span>|<span data-ttu-id="2a43c-109">描述</span><span class="sxs-lookup"><span data-stu-id="2a43c-109">Description</span></span>|  
|----------|-----------------|  
|`JsRuntimeAttributeAllowScriptInterrupt`|<span data-ttu-id="2a43c-110">运行时应支持可靠的脚本中断。</span><span class="sxs-lookup"><span data-stu-id="2a43c-110">The runtime should support reliable script interruption.</span></span> <span data-ttu-id="2a43c-111">这将增加运行时将检查脚本中断请求的位置数量，但会花费少量运行时性能。</span><span class="sxs-lookup"><span data-stu-id="2a43c-111">This increases the number of places where the runtime will check for a script interrupt request at the cost of a small amount of runtime performance.</span></span>|  
|`JsRuntimeAttributeDisableBackgroundWork`|<span data-ttu-id="2a43c-112">运行时将不会执行任何工作 (如后台线程上的) 垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="2a43c-112">The runtime will not do any work (such as garbage collection) on background threads.</span></span>|  
|`JsRuntimeAttributeDisableEval`|<span data-ttu-id="2a43c-113">使用 `eval` 或 `function` 构造函数将引发异常。</span><span class="sxs-lookup"><span data-stu-id="2a43c-113">Using `eval` or `function` constructor will throw an exception.</span></span>|  
|`JsRuntimeAttributeDisableNativeCodeGeneration`|<span data-ttu-id="2a43c-114">运行时不会生成本机代码。</span><span class="sxs-lookup"><span data-stu-id="2a43c-114">Runtime will not generate native code.</span></span>|  
|`JsRuntimeAttributeEnableExperimentalFeatures`|<span data-ttu-id="2a43c-115">运行时将启用所有实验功能。</span><span class="sxs-lookup"><span data-stu-id="2a43c-115">Runtime will enable all experimental features.</span></span>|  
|`JsRuntimeAttributeEnableIdleProcessing`|<span data-ttu-id="2a43c-116">主机将调用 `JsIdle` ，因此启用空闲处理。</span><span class="sxs-lookup"><span data-stu-id="2a43c-116">Host will call `JsIdle`, so enable idle processing.</span></span> <span data-ttu-id="2a43c-117">否则，运行时将更积极地管理内存。</span><span class="sxs-lookup"><span data-stu-id="2a43c-117">Otherwise, the runtime will manage memory slightly more aggressively.</span></span>|  
|`JsRuntimeAttributeDispatchSetExceptionsToDebugger`|<span data-ttu-id="2a43c-118">调用 `JsSetException` 还会将异常调度到脚本调试 (如果) 为调试程序提供中断异常的机会。</span><span class="sxs-lookup"><span data-stu-id="2a43c-118">Calling `JsSetException` will also dispatch the exception to the script debugger (if any) giving the debugger a chance to break on the exception.</span></span>|  
|`JsRuntimeAttributeNone`|<span data-ttu-id="2a43c-119">无特殊属性。</span><span class="sxs-lookup"><span data-stu-id="2a43c-119">No special attributes.</span></span>|  
  
## <span data-ttu-id="2a43c-120">要求</span><span class="sxs-lookup"><span data-stu-id="2a43c-120">Requirements</span></span>  
 <span data-ttu-id="2a43c-121">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="2a43c-121">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2a43c-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a43c-122">See Also</span></span>  
 [<span data-ttu-id="2a43c-123">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="2a43c-123">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
