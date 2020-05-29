---
description: 发出 HTTP 请求时引发的事件。
title: WebResourceRequestedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 79cff0d8fd68e3b5747008f343b5b46fb8093013
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562555"
---
# <span data-ttu-id="a1978-104">WebResourceRequestedEvent 对象</span><span class="sxs-lookup"><span data-stu-id="a1978-104">WebResourceRequestedEvent object</span></span>

<span data-ttu-id="a1978-105">发出 HTTP 请求时引发的事件。</span><span class="sxs-lookup"><span data-stu-id="a1978-105">An event that is fired when an HTTP request is made.</span></span>

## <span data-ttu-id="a1978-106">属性</span><span class="sxs-lookup"><span data-stu-id="a1978-106">Properties</span></span>

### <span data-ttu-id="a1978-107">args</span><span class="sxs-lookup"><span data-stu-id="a1978-107">args</span></span>

<span data-ttu-id="a1978-108">有关资源请求的信息。</span><span class="sxs-lookup"><span data-stu-id="a1978-108">Information about the resource request.</span></span> <span data-ttu-id="a1978-109">这是[WebViewControlWebResourceRequestedEventArgs 的网站](/uwp/api/windows.web.ui.webviewcontrolwebresourcerequestedeventargs)。</span><span class="sxs-lookup"><span data-stu-id="a1978-109">This is a [Windows.Web.UI.WebViewControlWebResourceRequestedEventArgs](/uwp/api/windows.web.ui.webviewcontrolwebresourcerequestedeventargs).</span></span>

<span data-ttu-id="a1978-110">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="a1978-110">This property is read-only.</span></span>

```js
var args = webResourceRequestedEventArgs.args;
var request = args.request;
```

#### <span data-ttu-id="a1978-111">属性值</span><span class="sxs-lookup"><span data-stu-id="a1978-111">Property value</span></span>
<span data-ttu-id="a1978-112">类型：**任何**</span><span class="sxs-lookup"><span data-stu-id="a1978-112">Type: **any**</span></span>

