---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler
ms.openlocfilehash: 9447420abddfdb44394042d6742ed1dafd299adf
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886518"
---
# <span data-ttu-id="6918d-104">interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="6918d-104">interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="6918d-105">在 Web 资源在 Web 资源中收到请求的响应时激发。</span><span class="sxs-lookup"><span data-stu-id="6918d-105">Fires when a response for a request is received for a Web resource in the webview.</span></span>

## <span data-ttu-id="6918d-106">摘要</span><span class="sxs-lookup"><span data-stu-id="6918d-106">Summary</span></span>

 <span data-ttu-id="6918d-107">成员</span><span class="sxs-lookup"><span data-stu-id="6918d-107">Members</span></span>                        | <span data-ttu-id="6918d-108">描述</span><span class="sxs-lookup"><span data-stu-id="6918d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6918d-109">调用</span><span class="sxs-lookup"><span data-stu-id="6918d-109">Invoke</span></span>](#invoke) | <span data-ttu-id="6918d-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="6918d-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="6918d-111">Host 可以使用此事件查看 Web 资源的实际请求和响应。</span><span class="sxs-lookup"><span data-stu-id="6918d-111">Host can use this event to view the actual request and response for a Web resource.</span></span> <span data-ttu-id="6918d-112">这包括在已触发关联请求的 WebResourceRequested 事件之后，网络堆栈所做的任何请求或响应修改（如添加授权标头）。</span><span class="sxs-lookup"><span data-stu-id="6918d-112">This includes any request or response modifications made by the network stack (such as adding of Authorization headers) after the WebResourceRequested event for the associated request has fired.</span></span> <span data-ttu-id="6918d-113">忽略对请求或响应对象所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6918d-113">Modifications made to the request or response objects are ignored.</span></span>

## <span data-ttu-id="6918d-114">成员</span><span class="sxs-lookup"><span data-stu-id="6918d-114">Members</span></span>

#### <span data-ttu-id="6918d-115">调用</span><span class="sxs-lookup"><span data-stu-id="6918d-115">Invoke</span></span> 

<span data-ttu-id="6918d-116">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="6918d-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="6918d-117">公共 HRESULT[调用](#invoke)（[ICoreWebView2Experimental](icorewebview2experimental.md) \* sender、 [ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs](icorewebview2experimentalwebresourceresponsereceivedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="6918d-117">public HRESULT [Invoke](#invoke)([ICoreWebView2Experimental](icorewebview2experimental.md) \* sender, [ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs](icorewebview2experimentalwebresourceresponsereceivedeventargs.md) \* args)</span></span>

