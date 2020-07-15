---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2HttpHeadersCollectionIterator
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 29f4a09af459e80f8c299a66b24d061e79a96f92
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881023"
---
# <span data-ttu-id="e3fcd-104">0.9.430-接口 ICoreWebView2HttpHeadersCollectionIterator</span><span class="sxs-lookup"><span data-stu-id="e3fcd-104">0.9.430 - interface ICoreWebView2HttpHeadersCollectionIterator</span></span> 

> [!NOTE]
> <span data-ttu-id="e3fcd-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="e3fcd-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

<span data-ttu-id="e3fcd-107">HTTP 标头集合的迭代器。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-107">Iterator for a collection of HTTP headers.</span></span>

## <span data-ttu-id="e3fcd-108">摘要</span><span class="sxs-lookup"><span data-stu-id="e3fcd-108">Summary</span></span>

 <span data-ttu-id="e3fcd-109">成员</span><span class="sxs-lookup"><span data-stu-id="e3fcd-109">Members</span></span>                        | <span data-ttu-id="e3fcd-110">描述</span><span class="sxs-lookup"><span data-stu-id="e3fcd-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e3fcd-111">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="e3fcd-111">GetCurrentHeader</span></span>](#getcurrentheader) | <span data-ttu-id="e3fcd-112">获取迭代器的当前 HTTP 标头的名称和值。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-112">Get the name and value of the current HTTP header of the iterator.</span></span>
[<span data-ttu-id="e3fcd-113">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="e3fcd-113">get_HasCurrentHeader</span></span>](#get_hascurrentheader) | <span data-ttu-id="e3fcd-114">当迭代器未用完标题时，则为 True。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-114">True when the iterator hasn't run out of headers.</span></span>
[<span data-ttu-id="e3fcd-115">MoveNext</span><span class="sxs-lookup"><span data-stu-id="e3fcd-115">MoveNext</span></span>](#movenext) | <span data-ttu-id="e3fcd-116">将迭代器移动到集合中的下一个 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-116">Move the iterator to the next HTTP header in the collection.</span></span>

<span data-ttu-id="e3fcd-117">请参阅[ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md)和[ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md)。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-117">See [ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) and [ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md).</span></span> 

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

## <span data-ttu-id="e3fcd-118">成员</span><span class="sxs-lookup"><span data-stu-id="e3fcd-118">Members</span></span>

#### <span data-ttu-id="e3fcd-119">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="e3fcd-119">GetCurrentHeader</span></span> 

<span data-ttu-id="e3fcd-120">获取迭代器的当前 HTTP 标头的名称和值。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-120">Get the name and value of the current HTTP header of the iterator.</span></span>

> <span data-ttu-id="e3fcd-121">公共 HRESULT [GetCurrentHeader](#getcurrentheader)（LPWSTR \* NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="e3fcd-121">public HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* name,LPWSTR \* value)</span></span>

<span data-ttu-id="e3fcd-122">如果对 MoveNext 的最后一次调用设置 has_next 为 FALSE，此方法将失败。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-122">This method will fail if the last call to MoveNext set has_next to FALSE.</span></span>

#### <span data-ttu-id="e3fcd-123">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="e3fcd-123">get_HasCurrentHeader</span></span> 

<span data-ttu-id="e3fcd-124">当迭代器未用完标题时，则为 True。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-124">True when the iterator hasn't run out of headers.</span></span>

> <span data-ttu-id="e3fcd-125">public HRESULT [get_HasCurrentHeader](#get_hascurrentheader)（BOOL \* hasCurrent）</span><span class="sxs-lookup"><span data-stu-id="e3fcd-125">public HRESULT [get_HasCurrentHeader](#get_hascurrentheader)(BOOL \* hasCurrent)</span></span>

<span data-ttu-id="e3fcd-126">如果迭代器循环的目标集合为空或迭代程序已超过集合末尾，则为 false。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-126">If the collection over which the iterator is iterating is empty or if the iterator has gone past the end of the collection then this is false.</span></span>

#### <span data-ttu-id="e3fcd-127">MoveNext</span><span class="sxs-lookup"><span data-stu-id="e3fcd-127">MoveNext</span></span> 

<span data-ttu-id="e3fcd-128">将迭代器移动到集合中的下一个 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-128">Move the iterator to the next HTTP header in the collection.</span></span>

> <span data-ttu-id="e3fcd-129">公共 HRESULT [MoveNext](#movenext)（BOOL \* hasNext）</span><span class="sxs-lookup"><span data-stu-id="e3fcd-129">public HRESULT [MoveNext](#movenext)(BOOL \* hasNext)</span></span>

<span data-ttu-id="e3fcd-130">如果没有更多的 HTTP 标头，则 hasNext 参数将设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-130">The hasNext parameter will be set to FALSE if there are no more HTTP headers.</span></span> <span data-ttu-id="e3fcd-131">在此情况下，如果调用 GetCurrentHeader 方法，则该方法将失败。</span><span class="sxs-lookup"><span data-stu-id="e3fcd-131">After this occurs the GetCurrentHeader method will fail if called.</span></span>

