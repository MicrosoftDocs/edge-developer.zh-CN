---
description: 发出 HTTP 请求时引发的事件。
title: WebResourceRequestedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 3d2bb54cc5d60aec5391f0e3fdd427c8ba8a3dab
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10751980"
---
# <span data-ttu-id="2b523-104">WebResourceRequestedEvent 对象</span><span class="sxs-lookup"><span data-stu-id="2b523-104">WebResourceRequestedEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="2b523-105">发出 HTTP 请求时引发的事件。</span><span class="sxs-lookup"><span data-stu-id="2b523-105">An event that is fired when an HTTP request is made.</span></span>  

## <span data-ttu-id="2b523-106">属性</span><span class="sxs-lookup"><span data-stu-id="2b523-106">Properties</span></span>  

### <span data-ttu-id="2b523-107">args</span><span class="sxs-lookup"><span data-stu-id="2b523-107">args</span></span>  

<span data-ttu-id="2b523-108">有关资源请求的信息。</span><span class="sxs-lookup"><span data-stu-id="2b523-108">Information about the resource request.</span></span>  <span data-ttu-id="2b523-109">这是[WebViewControlWebResourceRequestedEventArgs 的网站](/uwp/api/windows.web.ui.webviewcontrolwebresourcerequestedeventargs)。</span><span class="sxs-lookup"><span data-stu-id="2b523-109">This is a [Windows.Web.UI.WebViewControlWebResourceRequestedEventArgs](/uwp/api/windows.web.ui.webviewcontrolwebresourcerequestedeventargs).</span></span>  

<span data-ttu-id="2b523-110">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="2b523-110">This property is read-only.</span></span>  

```javascript
var args = webResourceRequestedEventArgs.args;
var request = args.request;
```  

#### <span data-ttu-id="2b523-111">属性值</span><span class="sxs-lookup"><span data-stu-id="2b523-111">Property value</span></span>  

<span data-ttu-id="2b523-112">类型：**任何**</span><span class="sxs-lookup"><span data-stu-id="2b523-112">Type: **any**</span></span>  
