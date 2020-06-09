---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 83f55e19c8c8c0f2fb075ff47e95e34be27c6602
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697334"
---
# <span data-ttu-id="edf9c-104">interface ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="edf9c-104">interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="edf9c-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="edf9c-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="edf9c-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="edf9c-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="edf9c-107">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="edf9c-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="edf9c-108">摘要</span><span class="sxs-lookup"><span data-stu-id="edf9c-108">Summary</span></span>

 <span data-ttu-id="edf9c-109">成员</span><span class="sxs-lookup"><span data-stu-id="edf9c-109">Members</span></span>                        | <span data-ttu-id="edf9c-110">描述</span><span class="sxs-lookup"><span data-stu-id="edf9c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="edf9c-111">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="edf9c-111">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="edf9c-112">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="edf9c-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="edf9c-113">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="edf9c-113">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="edf9c-114">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="edf9c-114">The ID of the navigation.</span></span>
[<span data-ttu-id="edf9c-115">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="edf9c-115">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="edf9c-116">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="edf9c-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="edf9c-117">成员</span><span class="sxs-lookup"><span data-stu-id="edf9c-117">Members</span></span>

#### <span data-ttu-id="edf9c-118">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="edf9c-118">get_IsSuccess</span></span> 

<span data-ttu-id="edf9c-119">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="edf9c-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="edf9c-120">public HRESULT [get_IsSuccess](#get_issuccess)（BOOL \* IsSuccess）</span><span class="sxs-lookup"><span data-stu-id="edf9c-120">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="edf9c-121">对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。</span><span class="sxs-lookup"><span data-stu-id="edf9c-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="edf9c-122">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="edf9c-122">get_NavigationId</span></span> 

<span data-ttu-id="edf9c-123">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="edf9c-123">The ID of the navigation.</span></span>

> <span data-ttu-id="edf9c-124">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="edf9c-124">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="edf9c-125">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="edf9c-125">get_WebErrorStatus</span></span> 

<span data-ttu-id="edf9c-126">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="edf9c-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="edf9c-127">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)（COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS）</span><span class="sxs-lookup"><span data-stu-id="edf9c-127">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span></span>

