---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NavigationCompletedEventArgs
ms.openlocfilehash: b45920cfdab8a01d1288fbaf566748545b8a2c98
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011685"
---
# <span data-ttu-id="7926e-104">interface ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="7926e-104">interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="7926e-105">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="7926e-105">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="7926e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="7926e-106">Summary</span></span>

 <span data-ttu-id="7926e-107">成员</span><span class="sxs-lookup"><span data-stu-id="7926e-107">Members</span></span>                        | <span data-ttu-id="7926e-108">描述</span><span class="sxs-lookup"><span data-stu-id="7926e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7926e-109">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="7926e-109">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="7926e-110">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="7926e-110">True when the navigation is successful.</span></span>
[<span data-ttu-id="7926e-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="7926e-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="7926e-112">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="7926e-112">The ID of the navigation.</span></span>
[<span data-ttu-id="7926e-113">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="7926e-113">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="7926e-114">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="7926e-114">The error code if the navigation failed.</span></span>

## <span data-ttu-id="7926e-115">成员</span><span class="sxs-lookup"><span data-stu-id="7926e-115">Members</span></span>

#### <span data-ttu-id="7926e-116">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="7926e-116">get_IsSuccess</span></span> 

<span data-ttu-id="7926e-117">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="7926e-117">True when the navigation is successful.</span></span>

> <span data-ttu-id="7926e-118">公共 HRESULT [get_IsSuccess](#get_issuccess) (BOOL \* IsSuccess) </span><span class="sxs-lookup"><span data-stu-id="7926e-118">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="7926e-119">这对于在错误页面中结束的导航是错误的，因为没有网络、DNS 查找失败、HTTP 服务器通过 4xx) 做出响应，但对于诸如 window 之类的其他方案也可能是 false (。停止在导航页上调用 ( # A3。</span><span class="sxs-lookup"><span data-stu-id="7926e-119">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional scenarios such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="7926e-120">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="7926e-120">get_NavigationId</span></span> 

<span data-ttu-id="7926e-121">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="7926e-121">The ID of the navigation.</span></span>

> <span data-ttu-id="7926e-122">公共 HRESULT [get_NavigationId](#get_navigationid) (UINT64 \* NavigationId) </span><span class="sxs-lookup"><span data-stu-id="7926e-122">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigationId)</span></span>

#### <span data-ttu-id="7926e-123">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="7926e-123">get_WebErrorStatus</span></span> 

<span data-ttu-id="7926e-124">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="7926e-124">The error code if the navigation failed.</span></span>

> <span data-ttu-id="7926e-125">公共 HRESULT [get_WebErrorStatus](#get_weberrorstatus) (COREWEBVIEW2_WEB_ERROR_STATUS \* WebErrorStatus) </span><span class="sxs-lookup"><span data-stu-id="7926e-125">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* webErrorStatus)</span></span>

