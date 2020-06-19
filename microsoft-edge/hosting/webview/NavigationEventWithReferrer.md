---
description: 包含有关导航的引用信息
title: NavigationEventWithReferrer 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 72c8a213f632e9e74145de9c34b949adf074cd22
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752123"
---
# <span data-ttu-id="dfd4e-104">NavigationEventWithReferrer 对象</span><span class="sxs-lookup"><span data-stu-id="dfd4e-104">NavigationEventWithReferrer object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="dfd4e-105">一个对象，表示在启动导航且导航包含 referer 时激发的事件。</span><span class="sxs-lookup"><span data-stu-id="dfd4e-105">An object that represents an event fired when navigation is initiated and the navigation contains a referer.</span></span>  

## <span data-ttu-id="dfd4e-106">属性</span><span class="sxs-lookup"><span data-stu-id="dfd4e-106">Properties</span></span>  

### <span data-ttu-id="dfd4e-107">referer</span><span class="sxs-lookup"><span data-stu-id="dfd4e-107">referer</span></span>

<span data-ttu-id="dfd4e-108">[Web 视图](../webview.md)中请求导航的页面的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="dfd4e-108">The Uniform Resource Identifier (URI) of the page in the [webview](../webview.md) requesting navigation.</span></span>  

<span data-ttu-id="dfd4e-109">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="dfd4e-109">This property is read-only.</span></span>  

#### <span data-ttu-id="dfd4e-110">属性值</span><span class="sxs-lookup"><span data-stu-id="dfd4e-110">Property value</span></span>  

<span data-ttu-id="dfd4e-111">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="dfd4e-111">Type: **DOMString**</span></span>  

```javascript
var referer = NavigationEventWithReferrer.referer;
```  

### <span data-ttu-id="dfd4e-112">uri</span><span class="sxs-lookup"><span data-stu-id="dfd4e-112">uri</span></span>  

<span data-ttu-id="dfd4e-113">导航的目标的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="dfd4e-113">The Uniform Resource Identifier (URI) of the destination of the navigation.</span></span>  

<span data-ttu-id="dfd4e-114">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="dfd4e-114">This property is read-only.</span></span>  

```javascript
var uri = NavigationEventWithReferrer.uri;
```  

#### <span data-ttu-id="dfd4e-115">属性值</span><span class="sxs-lookup"><span data-stu-id="dfd4e-115">Property value</span></span>  

<span data-ttu-id="dfd4e-116">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="dfd4e-116">Type: **DOMString**</span></span>  
