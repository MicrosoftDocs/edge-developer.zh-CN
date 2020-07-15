---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 3a15232a7fe2ddf230d0463069052c55f7abc843
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879133"
---
# <span data-ttu-id="482fb-104">0.9.515-WebView2 的 CoreWebView2NavigationCompletedEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="482fb-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="482fb-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="482fb-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="482fb-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="482fb-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="482fb-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="482fb-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="482fb-108">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="482fb-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="482fb-109">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="482fb-109">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="482fb-110">摘要</span><span class="sxs-lookup"><span data-stu-id="482fb-110">Summary</span></span>

 <span data-ttu-id="482fb-111">成员</span><span class="sxs-lookup"><span data-stu-id="482fb-111">Members</span></span>                        | <span data-ttu-id="482fb-112">描述</span><span class="sxs-lookup"><span data-stu-id="482fb-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="482fb-113">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="482fb-113">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="482fb-114">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="482fb-114">True when the navigation is successful.</span></span>
[<span data-ttu-id="482fb-115">NavigationId</span><span class="sxs-lookup"><span data-stu-id="482fb-115">NavigationId</span></span>](#navigationid) | <span data-ttu-id="482fb-116">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="482fb-116">The ID of the navigation.</span></span>
[<span data-ttu-id="482fb-117">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="482fb-117">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="482fb-118">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="482fb-118">The error code if the navigation failed.</span></span>

## <span data-ttu-id="482fb-119">成员</span><span class="sxs-lookup"><span data-stu-id="482fb-119">Members</span></span>

#### <span data-ttu-id="482fb-120">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="482fb-120">IsSuccess</span></span> 

<span data-ttu-id="482fb-121">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="482fb-121">True when the navigation is successful.</span></span>

> <span data-ttu-id="482fb-122">公共 bool [IsSuccess](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="482fb-122">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="482fb-123">对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。</span><span class="sxs-lookup"><span data-stu-id="482fb-123">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="482fb-124">NavigationId</span><span class="sxs-lookup"><span data-stu-id="482fb-124">NavigationId</span></span> 

<span data-ttu-id="482fb-125">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="482fb-125">The ID of the navigation.</span></span>

> <span data-ttu-id="482fb-126">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="482fb-126">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="482fb-127">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="482fb-127">WebErrorStatus</span></span> 

<span data-ttu-id="482fb-128">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="482fb-128">The error code if the navigation failed.</span></span>

> <span data-ttu-id="482fb-129">公共 CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="482fb-129">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

