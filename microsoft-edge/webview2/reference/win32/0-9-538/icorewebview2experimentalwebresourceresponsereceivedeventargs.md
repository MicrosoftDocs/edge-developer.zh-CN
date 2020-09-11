---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs
ms.openlocfilehash: 547e9a451283de55658a95a8134ecb8a838f9e50
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011398"
---
# <span data-ttu-id="b45c0-104">0.9.579-接口 ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="b45c0-104">0.9.579 - interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="b45c0-105">WebResourceResponseReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="b45c0-105">Event args for the WebResourceResponseReceived event.</span></span>

## <span data-ttu-id="b45c0-106">摘要</span><span class="sxs-lookup"><span data-stu-id="b45c0-106">Summary</span></span>

 <span data-ttu-id="b45c0-107">成员</span><span class="sxs-lookup"><span data-stu-id="b45c0-107">Members</span></span>                        | <span data-ttu-id="b45c0-108">描述</span><span class="sxs-lookup"><span data-stu-id="b45c0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b45c0-109">get_Request</span><span class="sxs-lookup"><span data-stu-id="b45c0-109">get_Request</span></span>](#get_request) | <span data-ttu-id="b45c0-110">Web 资源请求对象。</span><span class="sxs-lookup"><span data-stu-id="b45c0-110">Web resource request object.</span></span> <span data-ttu-id="b45c0-111">对此对象所做的任何修改都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="b45c0-111">Any modifications to this object will be ignored.</span></span>
[<span data-ttu-id="b45c0-112">get_Response</span><span class="sxs-lookup"><span data-stu-id="b45c0-112">get_Response</span></span>](#get_response) | <span data-ttu-id="b45c0-113">Web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="b45c0-113">Web resource response object.</span></span>
[<span data-ttu-id="b45c0-114">PopulateResponseContent</span><span class="sxs-lookup"><span data-stu-id="b45c0-114">PopulateResponseContent</span></span>](#populateresponsecontent) | <span data-ttu-id="b45c0-115">请求响应的内容流的异步方法。</span><span class="sxs-lookup"><span data-stu-id="b45c0-115">Async method to request the Content stream of the response.</span></span>

<span data-ttu-id="b45c0-116">将包含发送的请求和收到的响应。</span><span class="sxs-lookup"><span data-stu-id="b45c0-116">Will contain the request as it was sent and the response as it was received.</span></span> <span data-ttu-id="b45c0-117">注意：若要获取响应内容流，请先调用 PopulateResponseContent 并等待异步调用完成，否则返回的内容流对象将为 null。</span><span class="sxs-lookup"><span data-stu-id="b45c0-117">Note: To get the response content stream, first call PopulateResponseContent and wait for the async call to complete, otherwise the content stream object returned will be null.</span></span>

## <span data-ttu-id="b45c0-118">成员</span><span class="sxs-lookup"><span data-stu-id="b45c0-118">Members</span></span>

#### <span data-ttu-id="b45c0-119">get_Request</span><span class="sxs-lookup"><span data-stu-id="b45c0-119">get_Request</span></span> 

<span data-ttu-id="b45c0-120">Web 资源请求对象。</span><span class="sxs-lookup"><span data-stu-id="b45c0-120">Web resource request object.</span></span> <span data-ttu-id="b45c0-121">对此对象所做的任何修改都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="b45c0-121">Any modifications to this object will be ignored.</span></span>

> <span data-ttu-id="b45c0-122">公共 HRESULT [get_Request](#get_request) (ICoreWebView2WebResourceRequest \* \* 请求) </span><span class="sxs-lookup"><span data-stu-id="b45c0-122">public HRESULT [get_Request](#get_request)(ICoreWebView2WebResourceRequest \*\* request)</span></span>

#### <span data-ttu-id="b45c0-123">get_Response</span><span class="sxs-lookup"><span data-stu-id="b45c0-123">get_Response</span></span> 

<span data-ttu-id="b45c0-124">Web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="b45c0-124">Web resource response object.</span></span>

> <span data-ttu-id="b45c0-125">公共 HRESULT [get_Response](#get_response) (ICoreWebView2WebResourceResponse \* \* 响应) </span><span class="sxs-lookup"><span data-stu-id="b45c0-125">public HRESULT [get_Response](#get_response)(ICoreWebView2WebResourceResponse \*\* response)</span></span>

<span data-ttu-id="b45c0-126">对此对象所做的任何修改都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="b45c0-126">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="b45c0-127">PopulateResponseContent</span><span class="sxs-lookup"><span data-stu-id="b45c0-127">PopulateResponseContent</span></span> 

<span data-ttu-id="b45c0-128">请求响应的内容流的异步方法。</span><span class="sxs-lookup"><span data-stu-id="b45c0-128">Async method to request the Content stream of the response.</span></span>

> <span data-ttu-id="b45c0-129">公共 HRESULT [PopulateResponseContent](#populateresponsecontent) ([ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler](icorewebview2experimentalwebresourceresponsereceivedeventargspopulateresponsecontentcompletedhandler.md) \* 处理程序) </span><span class="sxs-lookup"><span data-stu-id="b45c0-129">public HRESULT [PopulateResponseContent](#populateresponsecontent)([ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler](icorewebview2experimentalwebresourceresponsereceivedeventargspopulateresponsecontentcompletedhandler.md) \* handler)</span></span>

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

