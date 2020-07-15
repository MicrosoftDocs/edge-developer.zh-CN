---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: c13d0625669d6303c115c3d415d12278cfbe8320
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880498"
---
# <span data-ttu-id="17a9d-104">0.9.515-接口 ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="17a9d-104">0.9.515 - interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="17a9d-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="17a9d-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="17a9d-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="17a9d-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="17a9d-107">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="17a9d-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="17a9d-108">摘要</span><span class="sxs-lookup"><span data-stu-id="17a9d-108">Summary</span></span>

 <span data-ttu-id="17a9d-109">成员</span><span class="sxs-lookup"><span data-stu-id="17a9d-109">Members</span></span>                        | <span data-ttu-id="17a9d-110">描述</span><span class="sxs-lookup"><span data-stu-id="17a9d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="17a9d-111">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="17a9d-111">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="17a9d-112">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="17a9d-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="17a9d-113">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="17a9d-113">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="17a9d-114">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="17a9d-114">The ID of the navigation.</span></span>
[<span data-ttu-id="17a9d-115">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="17a9d-115">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="17a9d-116">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="17a9d-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="17a9d-117">成员</span><span class="sxs-lookup"><span data-stu-id="17a9d-117">Members</span></span>

#### <span data-ttu-id="17a9d-118">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="17a9d-118">get_IsSuccess</span></span> 

<span data-ttu-id="17a9d-119">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="17a9d-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="17a9d-120">public HRESULT [get_IsSuccess](#get_issuccess)（BOOL \* IsSuccess）</span><span class="sxs-lookup"><span data-stu-id="17a9d-120">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="17a9d-121">对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。</span><span class="sxs-lookup"><span data-stu-id="17a9d-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="17a9d-122">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="17a9d-122">get_NavigationId</span></span> 

<span data-ttu-id="17a9d-123">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="17a9d-123">The ID of the navigation.</span></span>

> <span data-ttu-id="17a9d-124">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="17a9d-124">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="17a9d-125">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="17a9d-125">get_WebErrorStatus</span></span> 

<span data-ttu-id="17a9d-126">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="17a9d-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="17a9d-127">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)（COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS）</span><span class="sxs-lookup"><span data-stu-id="17a9d-127">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span></span>

