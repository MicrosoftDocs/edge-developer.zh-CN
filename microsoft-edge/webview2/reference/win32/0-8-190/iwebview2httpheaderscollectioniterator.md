---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2HttpHeadersCollectionIterator
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 7abc6119d893cd1e9432d255969549f07d7e3a00
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878461"
---
# <span data-ttu-id="94e22-104">0.8.355-接口 IWebView2HttpHeadersCollectionIterator</span><span class="sxs-lookup"><span data-stu-id="94e22-104">0.8.355 - interface IWebView2HttpHeadersCollectionIterator</span></span> 

> [!NOTE]
> <span data-ttu-id="94e22-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="94e22-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="94e22-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="94e22-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

<span data-ttu-id="94e22-107">HTTP 标头集合的迭代器。</span><span class="sxs-lookup"><span data-stu-id="94e22-107">Iterator for a collection of HTTP headers.</span></span>

## <span data-ttu-id="94e22-108">摘要</span><span class="sxs-lookup"><span data-stu-id="94e22-108">Summary</span></span>

 <span data-ttu-id="94e22-109">成员</span><span class="sxs-lookup"><span data-stu-id="94e22-109">Members</span></span>                        | <span data-ttu-id="94e22-110">描述</span><span class="sxs-lookup"><span data-stu-id="94e22-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="94e22-111">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="94e22-111">GetCurrentHeader</span></span>](#getcurrentheader) | <span data-ttu-id="94e22-112">获取迭代器的当前 HTTP 标头的名称和值。</span><span class="sxs-lookup"><span data-stu-id="94e22-112">Get the name and value of the current HTTP header of the iterator.</span></span>
[<span data-ttu-id="94e22-113">MoveNext</span><span class="sxs-lookup"><span data-stu-id="94e22-113">MoveNext</span></span>](#movenext) | <span data-ttu-id="94e22-114">将迭代器移动到集合中的下一个 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="94e22-114">Move the iterator to the next HTTP header in the collection.</span></span>

<span data-ttu-id="94e22-115">请参阅[IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md)和[IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md)。</span><span class="sxs-lookup"><span data-stu-id="94e22-115">See [IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) and [IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md).</span></span>

## <span data-ttu-id="94e22-116">成员</span><span class="sxs-lookup"><span data-stu-id="94e22-116">Members</span></span>

#### <span data-ttu-id="94e22-117">GetCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="94e22-117">GetCurrentHeader</span></span> 

<span data-ttu-id="94e22-118">获取迭代器的当前 HTTP 标头的名称和值。</span><span class="sxs-lookup"><span data-stu-id="94e22-118">Get the name and value of the current HTTP header of the iterator.</span></span>

> <span data-ttu-id="94e22-119">公共 HRESULT [GetCurrentHeader](#getcurrentheader)（LPWSTR \* NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="94e22-119">public HRESULT [GetCurrentHeader](#getcurrentheader)(LPWSTR \* name,LPWSTR \* value)</span></span>

<span data-ttu-id="94e22-120">如果对 MoveNext 的最后一次调用设置 has_next 为 FALSE，此方法将失败。</span><span class="sxs-lookup"><span data-stu-id="94e22-120">This method will fail if the last call to MoveNext set has_next to FALSE.</span></span>

#### <span data-ttu-id="94e22-121">MoveNext</span><span class="sxs-lookup"><span data-stu-id="94e22-121">MoveNext</span></span> 

<span data-ttu-id="94e22-122">将迭代器移动到集合中的下一个 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="94e22-122">Move the iterator to the next HTTP header in the collection.</span></span>

> <span data-ttu-id="94e22-123">公共 HRESULT [MoveNext](#movenext)（BOOL \* has_next）</span><span class="sxs-lookup"><span data-stu-id="94e22-123">public HRESULT [MoveNext](#movenext)(BOOL \* has_next)</span></span>

<span data-ttu-id="94e22-124">如果没有更多的 HTTP 标头，则 has_next 参数将设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="94e22-124">The has_next parameter will be set to FALSE if there are no more HTTP headers.</span></span> <span data-ttu-id="94e22-125">在此情况下，如果调用 GetCurrentHeader 方法，则该方法将失败。</span><span class="sxs-lookup"><span data-stu-id="94e22-125">After this occurs the GetCurrentHeader method will fail if called.</span></span>

