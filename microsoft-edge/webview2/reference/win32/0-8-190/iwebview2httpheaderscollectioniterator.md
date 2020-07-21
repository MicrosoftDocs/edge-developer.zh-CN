---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2HttpHeadersCollectionIterator
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: dbcc5b10ce1973df61554f3f27174f600fb25280
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885979"
---
# <span data-ttu-id="1ca44-104">0.8.355-接口 IWebView2HttpHeadersCollectionIterator</span><span class="sxs-lookup"><span data-stu-id="1ca44-104">0.8.355 - interface IWebView2HttpHeadersCollectionIterator</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

<span data-ttu-id="1ca44-105">HTTP 标头集合的迭代器。</span><span class="sxs-lookup"><span data-stu-id="1ca44-105">Iterator for a collection of HTTP headers.</span></span>

## <span data-ttu-id="1ca44-106">摘要</span><span class="sxs-lookup"><span data-stu-id="1ca44-106">Summary</span></span>

 <span data-ttu-id="1ca44-107">成员</span><span class="sxs-lookup"><span data-stu-id="1ca44-107">Members</span></span>                        | <span data-ttu-id="1ca44-108">描述</span><span class="sxs-lookup"><span data-stu-id="1ca44-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1ca44-109">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="1ca44-109">GetCurrentHeader</span></span>](#getcurrentheader) | <span data-ttu-id="1ca44-110">获取迭代器的当前 HTTP 标头的名称和值。</span><span class="sxs-lookup"><span data-stu-id="1ca44-110">Get the name and value of the current HTTP header of the iterator.</span></span>
[<span data-ttu-id="1ca44-111">MoveNext</span><span class="sxs-lookup"><span data-stu-id="1ca44-111">MoveNext</span></span>](#movenext) | <span data-ttu-id="1ca44-112">将迭代器移动到集合中的下一个 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="1ca44-112">Move the iterator to the next HTTP header in the collection.</span></span>

<span data-ttu-id="1ca44-113">请参阅[IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md)和[IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md)。</span><span class="sxs-lookup"><span data-stu-id="1ca44-113">See [IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) and [IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md).</span></span>

## <span data-ttu-id="1ca44-114">成员</span><span class="sxs-lookup"><span data-stu-id="1ca44-114">Members</span></span>

#### <span data-ttu-id="1ca44-115">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="1ca44-115">GetCurrentHeader</span></span> 

<span data-ttu-id="1ca44-116">获取迭代器的当前 HTTP 标头的名称和值。</span><span class="sxs-lookup"><span data-stu-id="1ca44-116">Get the name and value of the current HTTP header of the iterator.</span></span>

> <span data-ttu-id="1ca44-117">公共 HRESULT [GetCurrentHeader](#getcurrentheader)（LPWSTR \* NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="1ca44-117">public HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* name,LPWSTR \* value)</span></span>

<span data-ttu-id="1ca44-118">如果对 MoveNext 的最后一次调用设置 has_next 为 FALSE，此方法将失败。</span><span class="sxs-lookup"><span data-stu-id="1ca44-118">This method will fail if the last call to MoveNext set has_next to FALSE.</span></span>

#### <span data-ttu-id="1ca44-119">MoveNext</span><span class="sxs-lookup"><span data-stu-id="1ca44-119">MoveNext</span></span> 

<span data-ttu-id="1ca44-120">将迭代器移动到集合中的下一个 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="1ca44-120">Move the iterator to the next HTTP header in the collection.</span></span>

> <span data-ttu-id="1ca44-121">公共 HRESULT [MoveNext](#movenext)（BOOL \* has_next）</span><span class="sxs-lookup"><span data-stu-id="1ca44-121">public HRESULT [MoveNext](#movenext)(BOOL \* has_next)</span></span>

<span data-ttu-id="1ca44-122">如果没有更多的 HTTP 标头，则 has_next 参数将设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="1ca44-122">The has_next parameter will be set to FALSE if there are no more HTTP headers.</span></span> <span data-ttu-id="1ca44-123">在此情况下，如果调用 GetCurrentHeader 方法，则该方法将失败。</span><span class="sxs-lookup"><span data-stu-id="1ca44-123">After this occurs the GetCurrentHeader method will fail if called.</span></span>

