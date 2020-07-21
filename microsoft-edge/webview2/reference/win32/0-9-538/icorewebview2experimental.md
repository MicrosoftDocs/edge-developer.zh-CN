---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2Experimental
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2Experimental
ms.openlocfilehash: 98f13193e73781f9f7371db05ed3ca99ca93c128
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886522"
---
# <span data-ttu-id="b7f43-104">interface ICoreWebView2Experimental</span><span class="sxs-lookup"><span data-stu-id="b7f43-104">interface ICoreWebView2Experimental</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2Experimental
  : public IUnknown
```

## <span data-ttu-id="b7f43-105">摘要</span><span class="sxs-lookup"><span data-stu-id="b7f43-105">Summary</span></span>

 <span data-ttu-id="b7f43-106">成员</span><span class="sxs-lookup"><span data-stu-id="b7f43-106">Members</span></span>                        | <span data-ttu-id="b7f43-107">描述</span><span class="sxs-lookup"><span data-stu-id="b7f43-107">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b7f43-108">add_WebResourceResponseReceived</span><span class="sxs-lookup"><span data-stu-id="b7f43-108">add_WebResourceResponseReceived</span></span>](#add_webresourceresponsereceived) | <span data-ttu-id="b7f43-109">为 WebResourceResponseReceived 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b7f43-109">Add an event handler for the WebResourceResponseReceived event.</span></span>
[<span data-ttu-id="b7f43-110">remove_WebResourceResponseReceived</span><span class="sxs-lookup"><span data-stu-id="b7f43-110">remove_WebResourceResponseReceived</span></span>](#remove_webresourceresponsereceived) | <span data-ttu-id="b7f43-111">删除以前通过 add_WebResourceResponseReceived 添加的 WebResourceResponseReceived 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b7f43-111">Removes the WebResourceResponseReceived event handler previously added with add_WebResourceResponseReceived.</span></span>

## <span data-ttu-id="b7f43-112">成员</span><span class="sxs-lookup"><span data-stu-id="b7f43-112">Members</span></span>

#### <span data-ttu-id="b7f43-113">add_WebResourceResponseReceived</span><span class="sxs-lookup"><span data-stu-id="b7f43-113">add_WebResourceResponseReceived</span></span> 

<span data-ttu-id="b7f43-114">为 WebResourceResponseReceived 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b7f43-114">Add an event handler for the WebResourceResponseReceived event.</span></span>

> <span data-ttu-id="b7f43-115">public HRESULT [add_WebResourceResponseReceived](#add_webresourceresponsereceived)（[ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler](icorewebview2experimentalwebresourceresponsereceivedeventhandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="b7f43-115">public HRESULT [add_WebResourceResponseReceived](#add_webresourceresponsereceived)([ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler](icorewebview2experimentalwebresourceresponsereceivedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="b7f43-116">在 Web 视图收到并处理 WebResource 请求的响应后，将触发 WebResourceResponseReceived 事件。</span><span class="sxs-lookup"><span data-stu-id="b7f43-116">WebResourceResponseReceived event fires after the WebView has received and processed the response for a WebResource request.</span></span> <span data-ttu-id="b7f43-117">事件参数包括由连网和 WebResourceResponse 发送的 WebResourceRequest，包括由网络堆栈添加的任何附加标头，不包括在关联的 WebResourceRequested 事件（如身份验证头）中。</span><span class="sxs-lookup"><span data-stu-id="b7f43-117">The event args include the WebResourceRequest as sent by the wire and WebResourceResponse received, including any additional headers added by the network stack that were not be included as part of the associated WebResourceRequested event, such as Authentication headers.</span></span> 
```cpp
    wil::com_ptr<ICoreWebView2Experimental> webviewExperimental;
    CHECK_FAILURE(m_appWindow->GetWebView()->QueryInterface(IID_PPV_ARGS(&webviewExperimental)));
    CHECK_FAILURE(webviewExperimental->add_WebResourceResponseReceived(
        Callback<ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler>(
            [this](
                ICoreWebView2Experimental* sender,
                ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs* args) {           
                wil::com_ptr<ICoreWebView2WebResourceRequest> request;
                CHECK_FAILURE(args->get_Request(&request));
                wil::unique_cotaskmem_string uri;
                CHECK_FAILURE(request->get_Uri(&uri));
                if (wcscmp(uri.get(), L"https://authenticationtest.com/HTTPAuth/") == 0)
                {
                    wil::com_ptr<ICoreWebView2HttpRequestHeaders> requestHeaders;
                    CHECK_FAILURE(request->get_Headers(&requestHeaders));

                    wil::unique_cotaskmem_string authHeaderValue;
                    if (requestHeaders->GetHeader(L"Authorization", &authHeaderValue) == S_OK)
                    {
                        std::wstring message(L"Authorization: ");
                        message += authHeaderValue.get();
                        MessageBox(nullptr, message.c_str(), nullptr, MB_OK);
                        m_appWindow->DeleteComponent(this);
                    }
                }
                
                return S_OK;
            })
            .Get(),
        &m_webResourceResponseReceivedToken));
```

#### <span data-ttu-id="b7f43-118">remove_WebResourceResponseReceived</span><span class="sxs-lookup"><span data-stu-id="b7f43-118">remove_WebResourceResponseReceived</span></span> 

<span data-ttu-id="b7f43-119">删除以前通过 add_WebResourceResponseReceived 添加的 WebResourceResponseReceived 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b7f43-119">Removes the WebResourceResponseReceived event handler previously added with add_WebResourceResponseReceived.</span></span>

> <span data-ttu-id="b7f43-120">public HRESULT [remove_WebResourceResponseReceived](#remove_webresourceresponsereceived)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="b7f43-120">public HRESULT [remove_WebResourceResponseReceived](#remove_webresourceresponsereceived)(EventRegistrationToken token)</span></span>

