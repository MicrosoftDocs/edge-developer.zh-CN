---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebResourceRequestedEventArgs2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 7f710b4da71a4a4e61869f06e5d2a4a95a2d0891
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885707"
---
# <span data-ttu-id="a87a8-104">0.8.355-接口 IWebView2WebResourceRequestedEventArgs2</span><span class="sxs-lookup"><span data-stu-id="a87a8-104">0.8.355 - interface IWebView2WebResourceRequestedEventArgs2</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebResourceRequestedEventArgs2
  : public IWebView2WebResourceRequestedEventArgs
```

<span data-ttu-id="a87a8-105">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a87a8-105">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="a87a8-106">摘要</span><span class="sxs-lookup"><span data-stu-id="a87a8-106">Summary</span></span>

 <span data-ttu-id="a87a8-107">成员</span><span class="sxs-lookup"><span data-stu-id="a87a8-107">Members</span></span>                        | <span data-ttu-id="a87a8-108">描述</span><span class="sxs-lookup"><span data-stu-id="a87a8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a87a8-109">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="a87a8-109">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="a87a8-110">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="a87a8-110">The web resource request contexts.</span></span>

## <span data-ttu-id="a87a8-111">成员</span><span class="sxs-lookup"><span data-stu-id="a87a8-111">Members</span></span>

#### <span data-ttu-id="a87a8-112">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="a87a8-112">get_ResourceContext</span></span> 

<span data-ttu-id="a87a8-113">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="a87a8-113">The web resource request contexts.</span></span>

> <span data-ttu-id="a87a8-114">公共 HRESULT [get_ResourceContext](#get_resourcecontext)（WEBVIEW2_WEB_RESOURCE_CONTEXT \* 上下文）</span><span class="sxs-lookup"><span data-stu-id="a87a8-114">public HRESULT [get_ResourceContext](#get_resourcecontext)(WEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

