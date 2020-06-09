---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 2f0a41c72c6ac6f7bcfbf7a5cbd5eef61ffa3a68
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697264"
---
# <span data-ttu-id="7736b-104">interface ICoreWebView2HttpHeadersCollectionIterator</span><span class="sxs-lookup"><span data-stu-id="7736b-104">interface ICoreWebView2HttpHeadersCollectionIterator</span></span> 

> [!NOTE]
> <span data-ttu-id="7736b-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="7736b-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="7736b-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="7736b-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

<span data-ttu-id="7736b-107">HTTP 标头集合的迭代器。</span><span class="sxs-lookup"><span data-stu-id="7736b-107">Iterator for a collection of HTTP headers.</span></span>

## <span data-ttu-id="7736b-108">摘要</span><span class="sxs-lookup"><span data-stu-id="7736b-108">Summary</span></span>

 <span data-ttu-id="7736b-109">成员</span><span class="sxs-lookup"><span data-stu-id="7736b-109">Members</span></span>                        | <span data-ttu-id="7736b-110">描述</span><span class="sxs-lookup"><span data-stu-id="7736b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7736b-111">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="7736b-111">get_HasCurrentHeader</span></span>](#get_hascurrentheader) | <span data-ttu-id="7736b-112">当迭代器未用完标题时，则为 True。</span><span class="sxs-lookup"><span data-stu-id="7736b-112">True when the iterator hasn't run out of headers.</span></span>
[<span data-ttu-id="7736b-113">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="7736b-113">GetCurrentHeader</span></span>](#getcurrentheader) | <span data-ttu-id="7736b-114">获取迭代器的当前 HTTP 标头的名称和值。</span><span class="sxs-lookup"><span data-stu-id="7736b-114">Get the name and value of the current HTTP header of the iterator.</span></span>
[<span data-ttu-id="7736b-115">MoveNext</span><span class="sxs-lookup"><span data-stu-id="7736b-115">MoveNext</span></span>](#movenext) | <span data-ttu-id="7736b-116">将迭代器移动到集合中的下一个 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="7736b-116">Move the iterator to the next HTTP header in the collection.</span></span>

<span data-ttu-id="7736b-117">请参阅[ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md)和[ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md)。</span><span class="sxs-lookup"><span data-stu-id="7736b-117">See [ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) and [ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md).</span></span> 
```cpp
std::wstring RequestHeadersToJsonString(ICoreWebView2HttpRequestHeaders* requestHeaders)
{
    wil::com_ptr<ICoreWebView2HttpHeadersCollectionIterator> iterator;
    CHECK_FAILURE(requestHeaders->GetIterator(&iterator));
    BOOL hasCurrent = FALSE;
    std::wstring result = L"[";

    while (SUCCEEDED(iterator->get_HasCurrentHeader(&hasCurrent)) && hasCurrent)
    {
        wil::unique_cotaskmem_string name;
        wil::unique_cotaskmem_string value;

        CHECK_FAILURE(iterator->GetCurrentHeader(&name, &value));
        result += L"{\"name\": " + EncodeQuote(name.get())
            + L", \"value\": " + EncodeQuote(value.get()) + L"}";

        BOOL hasNext = FALSE;
        CHECK_FAILURE(iterator->MoveNext(&hasNext));
        if (hasNext)
        {
            result += L", ";
        }
    }

    return result + L"]";
}
```

## <span data-ttu-id="7736b-118">成员</span><span class="sxs-lookup"><span data-stu-id="7736b-118">Members</span></span>

#### <span data-ttu-id="7736b-119">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="7736b-119">get_HasCurrentHeader</span></span> 

<span data-ttu-id="7736b-120">当迭代器未用完标题时，则为 True。</span><span class="sxs-lookup"><span data-stu-id="7736b-120">True when the iterator hasn't run out of headers.</span></span>

> <span data-ttu-id="7736b-121">public HRESULT [get_HasCurrentHeader](#get_hascurrentheader)（BOOL \* hasCurrent）</span><span class="sxs-lookup"><span data-stu-id="7736b-121">public HRESULT [get_HasCurrentHeader](#get_hascurrentheader)(BOOL \* hasCurrent)</span></span>

<span data-ttu-id="7736b-122">如果迭代器循环的目标集合为空或迭代程序已超过集合末尾，则为 false。</span><span class="sxs-lookup"><span data-stu-id="7736b-122">If the collection over which the iterator is iterating is empty or if the iterator has gone past the end of the collection then this is false.</span></span>

#### <span data-ttu-id="7736b-123">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="7736b-123">GetCurrentHeader</span></span> 

<span data-ttu-id="7736b-124">获取迭代器的当前 HTTP 标头的名称和值。</span><span class="sxs-lookup"><span data-stu-id="7736b-124">Get the name and value of the current HTTP header of the iterator.</span></span>

> <span data-ttu-id="7736b-125">公共 HRESULT [GetCurrentHeader](#getcurrentheader)（LPWSTR \* NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="7736b-125">public HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* name, LPWSTR \* value)</span></span>

<span data-ttu-id="7736b-126">如果对 MoveNext 的最后一次调用设置 has_next 为 FALSE，此方法将失败。</span><span class="sxs-lookup"><span data-stu-id="7736b-126">This method will fail if the last call to MoveNext set has_next to FALSE.</span></span>

#### <span data-ttu-id="7736b-127">MoveNext</span><span class="sxs-lookup"><span data-stu-id="7736b-127">MoveNext</span></span> 

<span data-ttu-id="7736b-128">将迭代器移动到集合中的下一个 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="7736b-128">Move the iterator to the next HTTP header in the collection.</span></span>

> <span data-ttu-id="7736b-129">公共 HRESULT [MoveNext](#movenext)（BOOL \* hasNext）</span><span class="sxs-lookup"><span data-stu-id="7736b-129">public HRESULT [MoveNext](#movenext)(BOOL \* hasNext)</span></span>

<span data-ttu-id="7736b-130">如果没有更多的 HTTP 标头，则 hasNext 参数将设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="7736b-130">The hasNext parameter will be set to FALSE if there are no more HTTP headers.</span></span> <span data-ttu-id="7736b-131">在此情况下，如果调用 GetCurrentHeader 方法，则该方法将失败。</span><span class="sxs-lookup"><span data-stu-id="7736b-131">After this occurs the GetCurrentHeader method will fail if called.</span></span>

