---
description: 对 Chakra 垃圾回收器所拥有的对象的引用。
title: JsRef Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 6aafc39f-6b9c-457f-8bf0-48831bffe9b8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f5ce1ada67a4530ba57345b90c0b7deba6954c7c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564206"
---
# <span data-ttu-id="d8a60-103">JsRef Typedef</span><span class="sxs-lookup"><span data-stu-id="d8a60-103">JsRef Typedef</span></span>
<span data-ttu-id="d8a60-104">对 Chakra 垃圾回收器所拥有的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="d8a60-104">A reference to an object owned by the Chakra garbage collector.</span></span>  
  
## <span data-ttu-id="d8a60-105">语法</span><span class="sxs-lookup"><span data-stu-id="d8a60-105">Syntax</span></span>  
  
```cpp  
typedef void *JsRef;  
```  
  
## <span data-ttu-id="d8a60-106">备注</span><span class="sxs-lookup"><span data-stu-id="d8a60-106">Remarks</span></span>  
 <span data-ttu-id="d8a60-107">只要 Chakra 运行时存储在本地变量或参数（即堆栈）上，它就会自动跟踪 JsRef 引用。</span><span class="sxs-lookup"><span data-stu-id="d8a60-107">A Chakra runtime will automatically track JsRef references as long as they are on stored in local variables or in parameters (i.e. on the stack).</span></span> <span data-ttu-id="d8a60-108">将 JsRef 存储在堆栈之外的其他位置需要调用 JsAddRef 和 JsRelease 来管理对象的生存期，否则垃圾回收器可能会在对象仍在使用时释放该对象。</span><span class="sxs-lookup"><span data-stu-id="d8a60-108">Storing a JsRef somewhere other than on the stack requires calling JsAddRef and JsRelease to manage the lifetime of the object, otherwise the garbage collector may free the object while it is still in use.</span></span>  
  
## <span data-ttu-id="d8a60-109">要求</span><span class="sxs-lookup"><span data-stu-id="d8a60-109">Requirements</span></span>  
 <span data-ttu-id="d8a60-110">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="d8a60-110">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d8a60-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8a60-111">See Also</span></span>  
 [<span data-ttu-id="d8a60-112">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="d8a60-112">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)