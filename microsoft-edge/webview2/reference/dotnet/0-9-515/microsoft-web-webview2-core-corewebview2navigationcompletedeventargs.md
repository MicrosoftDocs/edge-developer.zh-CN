---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: d3b3f4e78ef37ad2101a3a8f817279e999cea3e3
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697614"
---
# <span data-ttu-id="e6b0f-104">CoreWebView2NavigationCompletedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="e6b0f-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="e6b0f-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="e6b0f-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="e6b0f-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="e6b0f-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="e6b0f-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="e6b0f-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="e6b0f-108">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="e6b0f-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="e6b0f-109">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="e6b0f-109">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="e6b0f-110">摘要</span><span class="sxs-lookup"><span data-stu-id="e6b0f-110">Summary</span></span>

 <span data-ttu-id="e6b0f-111">成员</span><span class="sxs-lookup"><span data-stu-id="e6b0f-111">Members</span></span>                        | <span data-ttu-id="e6b0f-112">描述</span><span class="sxs-lookup"><span data-stu-id="e6b0f-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e6b0f-113">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="e6b0f-113">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="e6b0f-114">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="e6b0f-114">True when the navigation is successful.</span></span>
[<span data-ttu-id="e6b0f-115">NavigationId</span><span class="sxs-lookup"><span data-stu-id="e6b0f-115">NavigationId</span></span>](#navigationid) | <span data-ttu-id="e6b0f-116">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="e6b0f-116">The ID of the navigation.</span></span>
[<span data-ttu-id="e6b0f-117">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="e6b0f-117">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="e6b0f-118">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="e6b0f-118">The error code if the navigation failed.</span></span>

## <span data-ttu-id="e6b0f-119">成员</span><span class="sxs-lookup"><span data-stu-id="e6b0f-119">Members</span></span>

#### <span data-ttu-id="e6b0f-120">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="e6b0f-120">IsSuccess</span></span> 

<span data-ttu-id="e6b0f-121">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="e6b0f-121">True when the navigation is successful.</span></span>

> <span data-ttu-id="e6b0f-122">公共 bool [IsSuccess](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="e6b0f-122">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="e6b0f-123">对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。</span><span class="sxs-lookup"><span data-stu-id="e6b0f-123">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="e6b0f-124">NavigationId</span><span class="sxs-lookup"><span data-stu-id="e6b0f-124">NavigationId</span></span> 

<span data-ttu-id="e6b0f-125">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="e6b0f-125">The ID of the navigation.</span></span>

> <span data-ttu-id="e6b0f-126">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="e6b0f-126">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="e6b0f-127">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="e6b0f-127">WebErrorStatus</span></span> 

<span data-ttu-id="e6b0f-128">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="e6b0f-128">The error code if the navigation failed.</span></span>

> <span data-ttu-id="e6b0f-129">公共 CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="e6b0f-129">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

