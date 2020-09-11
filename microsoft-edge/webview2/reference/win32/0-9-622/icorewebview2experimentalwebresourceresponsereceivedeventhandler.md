---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler
ms.openlocfilehash: 4111c13756783779a1ef3d223c992defadf43d66
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011725"
---
# <span data-ttu-id="db62b-104">interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="db62b-104">interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="db62b-105">在 Web 资源在 Web 资源中收到请求的响应时激发。</span><span class="sxs-lookup"><span data-stu-id="db62b-105">Fires when a response for a request is received for a Web resource in the webview.</span></span>

## <span data-ttu-id="db62b-106">摘要</span><span class="sxs-lookup"><span data-stu-id="db62b-106">Summary</span></span>

 <span data-ttu-id="db62b-107">成员</span><span class="sxs-lookup"><span data-stu-id="db62b-107">Members</span></span>                        | <span data-ttu-id="db62b-108">描述</span><span class="sxs-lookup"><span data-stu-id="db62b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="db62b-109">调用</span><span class="sxs-lookup"><span data-stu-id="db62b-109">Invoke</span></span>](#invoke) | <span data-ttu-id="db62b-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="db62b-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="db62b-111">Host 可以使用此事件查看 Web 资源的实际请求和响应。</span><span class="sxs-lookup"><span data-stu-id="db62b-111">Host can use this event to view the actual request and response for a Web resource.</span></span> <span data-ttu-id="db62b-112">这包括网络堆栈 (所做的任何请求或响应修改，例如，在关联的请求的 WebResourceRequested 事件发生后添加授权标头) 。</span><span class="sxs-lookup"><span data-stu-id="db62b-112">This includes any request or response modifications made by the network stack (such as adding of Authorization headers) after the WebResourceRequested event for the associated request has fired.</span></span> <span data-ttu-id="db62b-113">忽略对请求或响应对象所做的更改。</span><span class="sxs-lookup"><span data-stu-id="db62b-113">Modifications made to the request or response objects are ignored.</span></span>

## <span data-ttu-id="db62b-114">成员</span><span class="sxs-lookup"><span data-stu-id="db62b-114">Members</span></span>

#### <span data-ttu-id="db62b-115">调用</span><span class="sxs-lookup"><span data-stu-id="db62b-115">Invoke</span></span> 

<span data-ttu-id="db62b-116">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="db62b-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="db62b-117">public HRESULT [调用](#invoke) ([ICoreWebView2Experimental](icorewebview2experimental.md) \* sender、 [ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs](icorewebview2experimentalwebresourceresponsereceivedeventargs.md) \* 参数) </span><span class="sxs-lookup"><span data-stu-id="db62b-117">public HRESULT [Invoke](#invoke)([ICoreWebView2Experimental](icorewebview2experimental.md) \* sender, [ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs](icorewebview2experimentalwebresourceresponsereceivedeventargs.md) \* args)</span></span>

