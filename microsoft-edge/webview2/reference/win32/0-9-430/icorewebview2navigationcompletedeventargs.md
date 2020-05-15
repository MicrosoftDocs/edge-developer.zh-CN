---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: f9d24d10d9487198988b4c6d3ad4a941a32dc396
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653205"
---
# <span data-ttu-id="d209b-104">interface ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="d209b-104">interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="d209b-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="d209b-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="d209b-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="d209b-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="d209b-107">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d209b-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="d209b-108">摘要</span><span class="sxs-lookup"><span data-stu-id="d209b-108">Summary</span></span>

 <span data-ttu-id="d209b-109">成员</span><span class="sxs-lookup"><span data-stu-id="d209b-109">Members</span></span>                        | <span data-ttu-id="d209b-110">描述</span><span class="sxs-lookup"><span data-stu-id="d209b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d209b-111">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="d209b-111">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="d209b-112">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="d209b-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="d209b-113">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="d209b-113">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="d209b-114">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="d209b-114">The error code if the navigation failed.</span></span>
[<span data-ttu-id="d209b-115">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="d209b-115">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="d209b-116">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="d209b-116">The ID of the navigation.</span></span>

## <span data-ttu-id="d209b-117">成员</span><span class="sxs-lookup"><span data-stu-id="d209b-117">Members</span></span>

#### <span data-ttu-id="d209b-118">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="d209b-118">get_IsSuccess</span></span> 

<span data-ttu-id="d209b-119">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="d209b-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="d209b-120">public HRESULT [get_IsSuccess](#get_issuccess)（BOOL \* IsSuccess）</span><span class="sxs-lookup"><span data-stu-id="d209b-120">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="d209b-121">对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。</span><span class="sxs-lookup"><span data-stu-id="d209b-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="d209b-122">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="d209b-122">get_WebErrorStatus</span></span> 

<span data-ttu-id="d209b-123">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="d209b-123">The error code if the navigation failed.</span></span>

> <span data-ttu-id="d209b-124">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)（CORE_WEBVIEW2_WEB_ERROR_STATUS \* CORE_WEBVIEW2_WEB_ERROR_STATUS）</span><span class="sxs-lookup"><span data-stu-id="d209b-124">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(CORE_WEBVIEW2_WEB_ERROR_STATUS \* CORE_WEBVIEW2_WEB_ERROR_STATUS)</span></span>

#### <span data-ttu-id="d209b-125">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="d209b-125">get_NavigationId</span></span> 

<span data-ttu-id="d209b-126">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="d209b-126">The ID of the navigation.</span></span>

> <span data-ttu-id="d209b-127">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="d209b-127">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

