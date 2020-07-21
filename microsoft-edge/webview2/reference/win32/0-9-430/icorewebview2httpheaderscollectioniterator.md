---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2HttpHeadersCollectionIterator
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 640926481e99c6571c0cbf9c345efa56d97e3f66
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885595"
---
# <span data-ttu-id="0ee42-104">0.9.430-接口 ICoreWebView2HttpHeadersCollectionIterator</span><span class="sxs-lookup"><span data-stu-id="0ee42-104">0.9.430 - interface ICoreWebView2HttpHeadersCollectionIterator</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

<span data-ttu-id="0ee42-105">HTTP 标头集合的迭代器。</span><span class="sxs-lookup"><span data-stu-id="0ee42-105">Iterator for a collection of HTTP headers.</span></span>

## <span data-ttu-id="0ee42-106">摘要</span><span class="sxs-lookup"><span data-stu-id="0ee42-106">Summary</span></span>

 <span data-ttu-id="0ee42-107">成员</span><span class="sxs-lookup"><span data-stu-id="0ee42-107">Members</span></span>                        | <span data-ttu-id="0ee42-108">描述</span><span class="sxs-lookup"><span data-stu-id="0ee42-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0ee42-109">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="0ee42-109">GetCurrentHeader</span></span>](#getcurrentheader) | <span data-ttu-id="0ee42-110">获取迭代器的当前 HTTP 标头的名称和值。</span><span class="sxs-lookup"><span data-stu-id="0ee42-110">Get the name and value of the current HTTP header of the iterator.</span></span>
[<span data-ttu-id="0ee42-111">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="0ee42-111">get_HasCurrentHeader</span></span>](#get_hascurrentheader) | <span data-ttu-id="0ee42-112">当迭代器未用完标题时，则为 True。</span><span class="sxs-lookup"><span data-stu-id="0ee42-112">True when the iterator hasn't run out of headers.</span></span>
[<span data-ttu-id="0ee42-113">MoveNext</span><span class="sxs-lookup"><span data-stu-id="0ee42-113">MoveNext</span></span>](#movenext) | <span data-ttu-id="0ee42-114">将迭代器移动到集合中的下一个 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="0ee42-114">Move the iterator to the next HTTP header in the collection.</span></span>

<span data-ttu-id="0ee42-115">请参阅[ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md)和[ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md)。</span><span class="sxs-lookup"><span data-stu-id="0ee42-115">See [ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) and [ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md).</span></span> 

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

## <span data-ttu-id="0ee42-116">成员</span><span class="sxs-lookup"><span data-stu-id="0ee42-116">Members</span></span>

#### <span data-ttu-id="0ee42-117">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="0ee42-117">GetCurrentHeader</span></span> 

<span data-ttu-id="0ee42-118">获取迭代器的当前 HTTP 标头的名称和值。</span><span class="sxs-lookup"><span data-stu-id="0ee42-118">Get the name and value of the current HTTP header of the iterator.</span></span>

> <span data-ttu-id="0ee42-119">公共 HRESULT [GetCurrentHeader](#getcurrentheader)（LPWSTR \* NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="0ee42-119">public HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* name,LPWSTR \* value)</span></span>

<span data-ttu-id="0ee42-120">如果对 MoveNext 的最后一次调用设置 has_next 为 FALSE，此方法将失败。</span><span class="sxs-lookup"><span data-stu-id="0ee42-120">This method will fail if the last call to MoveNext set has_next to FALSE.</span></span>

#### <span data-ttu-id="0ee42-121">get_HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="0ee42-121">get_HasCurrentHeader</span></span> 

<span data-ttu-id="0ee42-122">当迭代器未用完标题时，则为 True。</span><span class="sxs-lookup"><span data-stu-id="0ee42-122">True when the iterator hasn't run out of headers.</span></span>

> <span data-ttu-id="0ee42-123">public HRESULT [get_HasCurrentHeader](#get_hascurrentheader)（BOOL \* hasCurrent）</span><span class="sxs-lookup"><span data-stu-id="0ee42-123">public HRESULT [get_HasCurrentHeader](#get_hascurrentheader)(BOOL \* hasCurrent)</span></span>

<span data-ttu-id="0ee42-124">如果迭代器循环的目标集合为空或迭代程序已超过集合末尾，则为 false。</span><span class="sxs-lookup"><span data-stu-id="0ee42-124">If the collection over which the iterator is iterating is empty or if the iterator has gone past the end of the collection then this is false.</span></span>

#### <span data-ttu-id="0ee42-125">MoveNext</span><span class="sxs-lookup"><span data-stu-id="0ee42-125">MoveNext</span></span> 

<span data-ttu-id="0ee42-126">将迭代器移动到集合中的下一个 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="0ee42-126">Move the iterator to the next HTTP header in the collection.</span></span>

> <span data-ttu-id="0ee42-127">公共 HRESULT [MoveNext](#movenext)（BOOL \* hasNext）</span><span class="sxs-lookup"><span data-stu-id="0ee42-127">public HRESULT [MoveNext](#movenext)(BOOL \* hasNext)</span></span>

<span data-ttu-id="0ee42-128">如果没有更多的 HTTP 标头，则 hasNext 参数将设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="0ee42-128">The hasNext parameter will be set to FALSE if there are no more HTTP headers.</span></span> <span data-ttu-id="0ee42-129">在此情况下，如果调用 GetCurrentHeader 方法，则该方法将失败。</span><span class="sxs-lookup"><span data-stu-id="0ee42-129">After this occurs the GetCurrentHeader method will fail if called.</span></span>

