---
description: 包含有关 web 视图导航的信息
title: NavigationEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 785e9646ff400e7ad229046c7030b51420b1d9ad
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752169"
---
# <span data-ttu-id="b8292-104">NavigationEvent 对象</span><span class="sxs-lookup"><span data-stu-id="b8292-104">NavigationEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="b8292-105">一个对象，表示在启动导航时激发的事件。</span><span class="sxs-lookup"><span data-stu-id="b8292-105">An object that represents an event fired when navigation is initiated.</span></span>  

## <span data-ttu-id="b8292-106">属性</span><span class="sxs-lookup"><span data-stu-id="b8292-106">Properties</span></span>  

### <span data-ttu-id="b8292-107">uri</span><span class="sxs-lookup"><span data-stu-id="b8292-107">uri</span></span>  

<span data-ttu-id="b8292-108">目标的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="b8292-108">The Uniform Resource Identifier (URI) of the target.</span></span>  

<span data-ttu-id="b8292-109">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="b8292-109">This property is read-only.</span></span>  

```javascript
var uri = NavigationEvent.uri;
```  

#### <span data-ttu-id="b8292-110">属性值</span><span class="sxs-lookup"><span data-stu-id="b8292-110">Property value</span></span>  

<span data-ttu-id="b8292-111">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="b8292-111">Type: **DOMString**</span></span>  
