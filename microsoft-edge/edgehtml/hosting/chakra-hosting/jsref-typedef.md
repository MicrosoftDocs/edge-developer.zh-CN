---
description: 对由 Chakra 垃圾回收器拥有的对象的引用。
title: JsRef Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 6aafc39f-6b9c-457f-8bf0-48831bffe9b8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 69d13472b15b5d448908b5dafb2e3d7dc0ace7e4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232024"
---
# <span data-ttu-id="17fcc-103">JsRef Typedef</span><span class="sxs-lookup"><span data-stu-id="17fcc-103">JsRef Typedef</span></span>

<span data-ttu-id="17fcc-104">对由 Chakra 垃圾回收器拥有的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="17fcc-104">A reference to an object owned by the Chakra garbage collector.</span></span>  
  
## <span data-ttu-id="17fcc-105">语法</span><span class="sxs-lookup"><span data-stu-id="17fcc-105">Syntax</span></span>  
  
```cpp  
typedef void *JsRef;  
```  
  
## <span data-ttu-id="17fcc-106">备注</span><span class="sxs-lookup"><span data-stu-id="17fcc-106">Remarks</span></span>  
 <span data-ttu-id="17fcc-107">一个 Chakra 运行时将自动跟踪 JsRef 引用，只要它们存储在本地变量或参数中 (即堆栈) 。</span><span class="sxs-lookup"><span data-stu-id="17fcc-107">A Chakra runtime will automatically track JsRef references as long as they are on stored in local variables or in parameters (i.e. on the stack).</span></span> <span data-ttu-id="17fcc-108">将 JsRef 存储在堆栈上外部的某个位置需要调用 JsAddRef 和 JsRelease 来管理对象的生存期，否则垃圾回收器可能会释放仍在使用中的对象。</span><span class="sxs-lookup"><span data-stu-id="17fcc-108">Storing a JsRef somewhere other than on the stack requires calling JsAddRef and JsRelease to manage the lifetime of the object, otherwise the garbage collector may free the object while it is still in use.</span></span>  
  
## <span data-ttu-id="17fcc-109">要求</span><span class="sxs-lookup"><span data-stu-id="17fcc-109">Requirements</span></span>  
 <span data-ttu-id="17fcc-110">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="17fcc-110">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="17fcc-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17fcc-111">See Also</span></span>  
 [<span data-ttu-id="17fcc-112">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="17fcc-112">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
