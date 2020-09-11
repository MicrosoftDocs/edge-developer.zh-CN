---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2HttpHeadersCollectionIterator 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: e7aad408372acbbd19ecab9d04312f21e2396e88
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011703"
---
# <span data-ttu-id="e7474-104">CoreWebView2HttpHeadersCollectionIterator 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="e7474-104">Microsoft.Web.WebView2.Core.CoreWebView2HttpHeadersCollectionIterator class</span></span> 

<span data-ttu-id="e7474-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="e7474-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="e7474-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="e7474-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="e7474-107">HTTP 标头集合的迭代器。</span><span class="sxs-lookup"><span data-stu-id="e7474-107">Iterator for a collection of HTTP headers.</span></span>

## <span data-ttu-id="e7474-108">摘要</span><span class="sxs-lookup"><span data-stu-id="e7474-108">Summary</span></span>

 <span data-ttu-id="e7474-109">成员</span><span class="sxs-lookup"><span data-stu-id="e7474-109">Members</span></span>                        | <span data-ttu-id="e7474-110">描述</span><span class="sxs-lookup"><span data-stu-id="e7474-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e7474-111">HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="e7474-111">HasCurrentHeader</span></span>](#hascurrentheader) | <span data-ttu-id="e7474-112">当迭代器未用完标题时，则为 True。</span><span class="sxs-lookup"><span data-stu-id="e7474-112">True when the iterator hasn't run out of headers.</span></span>
[<span data-ttu-id="e7474-113">MoveNext</span><span class="sxs-lookup"><span data-stu-id="e7474-113">MoveNext</span></span>](#movenext) | <span data-ttu-id="e7474-114">将迭代器移动到集合中的下一个 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="e7474-114">Move the iterator to the next HTTP header in the collection.</span></span>

<span data-ttu-id="e7474-115">请参阅 CoreWebView2HttpRequestHeaders 和 CoreWebView2HttpResponseHeaders。</span><span class="sxs-lookup"><span data-stu-id="e7474-115">See CoreWebView2HttpRequestHeaders and CoreWebView2HttpResponseHeaders.</span></span>

## <span data-ttu-id="e7474-116">成员</span><span class="sxs-lookup"><span data-stu-id="e7474-116">Members</span></span>

#### <span data-ttu-id="e7474-117">HasCurrentHeader</span><span class="sxs-lookup"><span data-stu-id="e7474-117">HasCurrentHeader</span></span> 

<span data-ttu-id="e7474-118">当迭代器未用完标题时，则为 True。</span><span class="sxs-lookup"><span data-stu-id="e7474-118">True when the iterator hasn't run out of headers.</span></span>

> <span data-ttu-id="e7474-119">公共 bool [HasCurrentHeader](#hascurrentheader)</span><span class="sxs-lookup"><span data-stu-id="e7474-119">public bool [HasCurrentHeader](#hascurrentheader)</span></span>

<span data-ttu-id="e7474-120">如果迭代器循环的目标集合为空或迭代程序已超过集合末尾，则为 false。</span><span class="sxs-lookup"><span data-stu-id="e7474-120">If the collection over which the iterator is iterating is empty or if the iterator has gone past the end of the collection then this is false.</span></span>

#### <span data-ttu-id="e7474-121">MoveNext</span><span class="sxs-lookup"><span data-stu-id="e7474-121">MoveNext</span></span> 

<span data-ttu-id="e7474-122">将迭代器移动到集合中的下一个 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="e7474-122">Move the iterator to the next HTTP header in the collection.</span></span>

> <span data-ttu-id="e7474-123">公共的 bool [MoveNext](#movenext) ( # A1</span><span class="sxs-lookup"><span data-stu-id="e7474-123">public bool [MoveNext](#movenext)()</span></span>

<span data-ttu-id="e7474-124">如果没有更多的 HTTP 标头，则 hasNext 参数将设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="e7474-124">The hasNext parameter will be set to FALSE if there are no more HTTP headers.</span></span> <span data-ttu-id="e7474-125">在此情况下，如果调用 GetCurrentHeader 方法，则该方法将失败。</span><span class="sxs-lookup"><span data-stu-id="e7474-125">After this occurs the GetCurrentHeader method will fail if called.</span></span>

