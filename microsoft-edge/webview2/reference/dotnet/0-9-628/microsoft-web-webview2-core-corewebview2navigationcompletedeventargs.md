---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2NavigationCompletedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: dfa6aedb10e60a2af15c7b098c479f8537d6c747
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011630"
---
# <span data-ttu-id="a7fff-104">CoreWebView2NavigationCompletedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="a7fff-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

<span data-ttu-id="a7fff-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="a7fff-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="a7fff-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="a7fff-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="a7fff-107">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a7fff-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="a7fff-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a7fff-108">Summary</span></span>

 <span data-ttu-id="a7fff-109">成员</span><span class="sxs-lookup"><span data-stu-id="a7fff-109">Members</span></span>                        | <span data-ttu-id="a7fff-110">描述</span><span class="sxs-lookup"><span data-stu-id="a7fff-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a7fff-111">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="a7fff-111">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="a7fff-112">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="a7fff-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="a7fff-113">NavigationId</span><span class="sxs-lookup"><span data-stu-id="a7fff-113">NavigationId</span></span>](#navigationid) | <span data-ttu-id="a7fff-114">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="a7fff-114">The ID of the navigation.</span></span>
[<span data-ttu-id="a7fff-115">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="a7fff-115">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="a7fff-116">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="a7fff-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="a7fff-117">成员</span><span class="sxs-lookup"><span data-stu-id="a7fff-117">Members</span></span>

#### <span data-ttu-id="a7fff-118">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="a7fff-118">IsSuccess</span></span> 

<span data-ttu-id="a7fff-119">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="a7fff-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="a7fff-120">公共 bool [IsSuccess](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="a7fff-120">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="a7fff-121">这对于在错误页面中结束的导航是错误的，因为没有网络、DNS 查找失败、HTTP 服务器通过 4xx) 做出响应，但对于诸如 window 之类的其他方案也可能是 false (。停止在导航页上调用 ( # A3。</span><span class="sxs-lookup"><span data-stu-id="a7fff-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional scenarios such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="a7fff-122">NavigationId</span><span class="sxs-lookup"><span data-stu-id="a7fff-122">NavigationId</span></span> 

<span data-ttu-id="a7fff-123">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="a7fff-123">The ID of the navigation.</span></span>

> <span data-ttu-id="a7fff-124">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="a7fff-124">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="a7fff-125">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="a7fff-125">WebErrorStatus</span></span> 

<span data-ttu-id="a7fff-126">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="a7fff-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="a7fff-127">公共 CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="a7fff-127">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

