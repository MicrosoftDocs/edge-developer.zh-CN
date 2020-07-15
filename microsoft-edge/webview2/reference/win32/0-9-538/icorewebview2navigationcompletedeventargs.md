---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NavigationCompletedEventArgs
ms.openlocfilehash: d40ee75eb77e8de6eab1188e6c17edacce00f635
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879805"
---
# <span data-ttu-id="4c728-104">interface ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="4c728-104">interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="4c728-105">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="4c728-105">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="4c728-106">摘要</span><span class="sxs-lookup"><span data-stu-id="4c728-106">Summary</span></span>

 <span data-ttu-id="4c728-107">成员</span><span class="sxs-lookup"><span data-stu-id="4c728-107">Members</span></span>                        | <span data-ttu-id="4c728-108">描述</span><span class="sxs-lookup"><span data-stu-id="4c728-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4c728-109">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="4c728-109">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="4c728-110">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="4c728-110">True when the navigation is successful.</span></span>
[<span data-ttu-id="4c728-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="4c728-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="4c728-112">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="4c728-112">The ID of the navigation.</span></span>
[<span data-ttu-id="4c728-113">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="4c728-113">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="4c728-114">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="4c728-114">The error code if the navigation failed.</span></span>

## <span data-ttu-id="4c728-115">成员</span><span class="sxs-lookup"><span data-stu-id="4c728-115">Members</span></span>

#### <span data-ttu-id="4c728-116">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="4c728-116">get_IsSuccess</span></span> 

<span data-ttu-id="4c728-117">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="4c728-117">True when the navigation is successful.</span></span>

> <span data-ttu-id="4c728-118">public HRESULT [get_IsSuccess](#get_issuccess)（BOOL \* IsSuccess）</span><span class="sxs-lookup"><span data-stu-id="4c728-118">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="4c728-119">对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。</span><span class="sxs-lookup"><span data-stu-id="4c728-119">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="4c728-120">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="4c728-120">get_NavigationId</span></span> 

<span data-ttu-id="4c728-121">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="4c728-121">The ID of the navigation.</span></span>

> <span data-ttu-id="4c728-122">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="4c728-122">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="4c728-123">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="4c728-123">get_WebErrorStatus</span></span> 

<span data-ttu-id="4c728-124">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="4c728-124">The error code if the navigation failed.</span></span>

> <span data-ttu-id="4c728-125">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)（COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS）</span><span class="sxs-lookup"><span data-stu-id="4c728-125">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span></span>

