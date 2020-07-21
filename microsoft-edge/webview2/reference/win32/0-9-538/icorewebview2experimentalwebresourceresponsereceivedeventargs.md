---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs
ms.openlocfilehash: 056667b4ee1995763fee81c8d7a9be31496f7f3e
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886514"
---
# <span data-ttu-id="ab255-104">interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="ab255-104">interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="ab255-105">WebResourceResponseReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="ab255-105">Event args for the WebResourceResponseReceived event.</span></span>

## <span data-ttu-id="ab255-106">摘要</span><span class="sxs-lookup"><span data-stu-id="ab255-106">Summary</span></span>

 <span data-ttu-id="ab255-107">成员</span><span class="sxs-lookup"><span data-stu-id="ab255-107">Members</span></span>                        | <span data-ttu-id="ab255-108">描述</span><span class="sxs-lookup"><span data-stu-id="ab255-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ab255-109">get_Request</span><span class="sxs-lookup"><span data-stu-id="ab255-109">get_Request</span></span>](#get_request) | <span data-ttu-id="ab255-110">Web 资源请求对象。</span><span class="sxs-lookup"><span data-stu-id="ab255-110">Web resource request object.</span></span> <span data-ttu-id="ab255-111">对此对象所做的任何修改都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="ab255-111">Any modifications to this object will be ignored.</span></span>
[<span data-ttu-id="ab255-112">get_Response</span><span class="sxs-lookup"><span data-stu-id="ab255-112">get_Response</span></span>](#get_response) | <span data-ttu-id="ab255-113">Web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="ab255-113">Web resource response object.</span></span>
[<span data-ttu-id="ab255-114">PopulateResponseContent</span><span class="sxs-lookup"><span data-stu-id="ab255-114">PopulateResponseContent</span></span>](#populateresponsecontent) | <span data-ttu-id="ab255-115">请求响应的内容流的异步方法。</span><span class="sxs-lookup"><span data-stu-id="ab255-115">Async method to request the Content stream of the response.</span></span>

<span data-ttu-id="ab255-116">将包含发送的请求和收到的响应。</span><span class="sxs-lookup"><span data-stu-id="ab255-116">Will contain the request as it was sent and the response as it was received.</span></span> <span data-ttu-id="ab255-117">注意：若要获取响应内容流，请先调用 PopulateResponseContent 并等待异步调用完成，否则返回的内容流对象将为 null。</span><span class="sxs-lookup"><span data-stu-id="ab255-117">Note: To get the response content stream, first call PopulateResponseContent and wait for the async call to complete, otherwise the content stream object returned will be null.</span></span>

## <span data-ttu-id="ab255-118">成员</span><span class="sxs-lookup"><span data-stu-id="ab255-118">Members</span></span>

#### <span data-ttu-id="ab255-119">get_Request</span><span class="sxs-lookup"><span data-stu-id="ab255-119">get_Request</span></span> 

<span data-ttu-id="ab255-120">Web 资源请求对象。</span><span class="sxs-lookup"><span data-stu-id="ab255-120">Web resource request object.</span></span> <span data-ttu-id="ab255-121">对此对象所做的任何修改都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="ab255-121">Any modifications to this object will be ignored.</span></span>

> <span data-ttu-id="ab255-122">公共 HRESULT [get_Request](#get_request)（ICoreWebView2WebResourceRequest \* \* 请求）</span><span class="sxs-lookup"><span data-stu-id="ab255-122">public HRESULT [get_Request](#get_request)(ICoreWebView2WebResourceRequest \*\* request)</span></span>

#### <span data-ttu-id="ab255-123">get_Response</span><span class="sxs-lookup"><span data-stu-id="ab255-123">get_Response</span></span> 

<span data-ttu-id="ab255-124">Web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="ab255-124">Web resource response object.</span></span>

> <span data-ttu-id="ab255-125">公共 HRESULT [get_Response](#get_response)（ICoreWebView2WebResourceResponse \* \* Response）</span><span class="sxs-lookup"><span data-stu-id="ab255-125">public HRESULT [get_Response](#get_response)(ICoreWebView2WebResourceResponse \*\* response)</span></span>

<span data-ttu-id="ab255-126">对此对象所做的任何修改都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="ab255-126">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="ab255-127">PopulateResponseContent</span><span class="sxs-lookup"><span data-stu-id="ab255-127">PopulateResponseContent</span></span> 

<span data-ttu-id="ab255-128">请求响应的内容流的异步方法。</span><span class="sxs-lookup"><span data-stu-id="ab255-128">Async method to request the Content stream of the response.</span></span>

> <span data-ttu-id="ab255-129">公共 HRESULT [PopulateResponseContent](#populateresponsecontent)（[ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler](icorewebview2experimentalwebresourceresponsereceivedeventargspopulateresponsecontentcompletedhandler.md) \* 处理程序）</span><span class="sxs-lookup"><span data-stu-id="ab255-129">public HRESULT [PopulateResponseContent](#populateresponsecontent)([ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler](icorewebview2experimentalwebresourceresponsereceivedeventargspopulateresponsecontentcompletedhandler.md) \* handler)</span></span>

```cpp
                    args->PopulateResponseContent(
                        Callback<
                            ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler>(
                            [this, webResourceRequest, webResourceResponse](HRESULT result) {
                                std::wstring message =
                                    L"{ \"kind\": \"event\", \"name\": "
                                    L"\"WebResourceResponseReceived\", \"args\": {"
                                    L"\"request\": " +
                                    RequestToJsonString(webResourceRequest.get()) +
                                    L", "
                                    L"\"response\": " +
                                    ResponseToJsonString(webResourceResponse.get()) + L"}";

                                message +=
                                    WebViewPropertiesToJsonString(m_webviewEventSource.get());
                                message += L"}";
                                PostEventMessage(message);
                                return S_OK;
                            })
                            .Get());
```

