---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: b7c920be1c203fe30174fccbc6736bb76fe389cb
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884559"
---
# <span data-ttu-id="0ac83-104">0.9.515-接口 ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="0ac83-104">0.9.515 - interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="0ac83-105">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="0ac83-105">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="0ac83-106">摘要</span><span class="sxs-lookup"><span data-stu-id="0ac83-106">Summary</span></span>

 <span data-ttu-id="0ac83-107">成员</span><span class="sxs-lookup"><span data-stu-id="0ac83-107">Members</span></span>                        | <span data-ttu-id="0ac83-108">描述</span><span class="sxs-lookup"><span data-stu-id="0ac83-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0ac83-109">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="0ac83-109">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="0ac83-110">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="0ac83-110">True when the navigation is successful.</span></span>
[<span data-ttu-id="0ac83-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="0ac83-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="0ac83-112">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="0ac83-112">The ID of the navigation.</span></span>
[<span data-ttu-id="0ac83-113">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="0ac83-113">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="0ac83-114">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="0ac83-114">The error code if the navigation failed.</span></span>

## <span data-ttu-id="0ac83-115">成员</span><span class="sxs-lookup"><span data-stu-id="0ac83-115">Members</span></span>

#### <span data-ttu-id="0ac83-116">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="0ac83-116">get_IsSuccess</span></span> 

<span data-ttu-id="0ac83-117">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="0ac83-117">True when the navigation is successful.</span></span>

> <span data-ttu-id="0ac83-118">public HRESULT [get_IsSuccess](#get_issuccess)（BOOL \* IsSuccess）</span><span class="sxs-lookup"><span data-stu-id="0ac83-118">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="0ac83-119">对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。</span><span class="sxs-lookup"><span data-stu-id="0ac83-119">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="0ac83-120">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="0ac83-120">get_NavigationId</span></span> 

<span data-ttu-id="0ac83-121">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="0ac83-121">The ID of the navigation.</span></span>

> <span data-ttu-id="0ac83-122">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="0ac83-122">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="0ac83-123">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="0ac83-123">get_WebErrorStatus</span></span> 

<span data-ttu-id="0ac83-124">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="0ac83-124">The error code if the navigation failed.</span></span>

> <span data-ttu-id="0ac83-125">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)（COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS）</span><span class="sxs-lookup"><span data-stu-id="0ac83-125">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span></span>

