---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 11d7e5ffef11a445c55cd4a9d70fcbbb8087c024
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698515"
---
# <span data-ttu-id="015d4-104">interface ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="015d4-104">interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="015d4-105">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="015d4-105">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="015d4-106">摘要</span><span class="sxs-lookup"><span data-stu-id="015d4-106">Summary</span></span>

 <span data-ttu-id="015d4-107">成员</span><span class="sxs-lookup"><span data-stu-id="015d4-107">Members</span></span>                        | <span data-ttu-id="015d4-108">描述</span><span class="sxs-lookup"><span data-stu-id="015d4-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="015d4-109">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="015d4-109">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="015d4-110">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="015d4-110">True when the navigation is successful.</span></span>
[<span data-ttu-id="015d4-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="015d4-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="015d4-112">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="015d4-112">The ID of the navigation.</span></span>
[<span data-ttu-id="015d4-113">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="015d4-113">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="015d4-114">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="015d4-114">The error code if the navigation failed.</span></span>

## <span data-ttu-id="015d4-115">成员</span><span class="sxs-lookup"><span data-stu-id="015d4-115">Members</span></span>

#### <span data-ttu-id="015d4-116">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="015d4-116">get_IsSuccess</span></span> 

<span data-ttu-id="015d4-117">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="015d4-117">True when the navigation is successful.</span></span>

> <span data-ttu-id="015d4-118">public HRESULT [get_IsSuccess](#get_issuccess)（BOOL \* IsSuccess）</span><span class="sxs-lookup"><span data-stu-id="015d4-118">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="015d4-119">对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。</span><span class="sxs-lookup"><span data-stu-id="015d4-119">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="015d4-120">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="015d4-120">get_NavigationId</span></span> 

<span data-ttu-id="015d4-121">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="015d4-121">The ID of the navigation.</span></span>

> <span data-ttu-id="015d4-122">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="015d4-122">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="015d4-123">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="015d4-123">get_WebErrorStatus</span></span> 

<span data-ttu-id="015d4-124">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="015d4-124">The error code if the navigation failed.</span></span>

> <span data-ttu-id="015d4-125">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)（COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS）</span><span class="sxs-lookup"><span data-stu-id="015d4-125">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span></span>

