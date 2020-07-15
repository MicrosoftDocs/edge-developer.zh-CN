---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 7c10e669b4caf13f43f858e343c9bad3da155518
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878412"
---
# <span data-ttu-id="6e020-104">0.8.355-接口 IWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="6e020-104">0.8.355 - interface IWebView2NavigationCompletedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="6e020-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="6e020-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="6e020-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="6e020-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="6e020-107">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="6e020-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="6e020-108">摘要</span><span class="sxs-lookup"><span data-stu-id="6e020-108">Summary</span></span>

 <span data-ttu-id="6e020-109">成员</span><span class="sxs-lookup"><span data-stu-id="6e020-109">Members</span></span>                        | <span data-ttu-id="6e020-110">描述</span><span class="sxs-lookup"><span data-stu-id="6e020-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6e020-111">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="6e020-111">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="6e020-112">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="6e020-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="6e020-113">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="6e020-113">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="6e020-114">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="6e020-114">The error code if the navigation failed.</span></span>

## <span data-ttu-id="6e020-115">成员</span><span class="sxs-lookup"><span data-stu-id="6e020-115">Members</span></span>

#### <span data-ttu-id="6e020-116">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="6e020-116">get_IsSuccess</span></span> 

<span data-ttu-id="6e020-117">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="6e020-117">True when the navigation is successful.</span></span>

> <span data-ttu-id="6e020-118">public HRESULT [get_IsSuccess](#get_issuccess)（BOOL \* IsSuccess）</span><span class="sxs-lookup"><span data-stu-id="6e020-118">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="6e020-119">对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。</span><span class="sxs-lookup"><span data-stu-id="6e020-119">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="6e020-120">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="6e020-120">get_WebErrorStatus</span></span> 

<span data-ttu-id="6e020-121">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="6e020-121">The error code if the navigation failed.</span></span>

> <span data-ttu-id="6e020-122">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)（WEBVIEW2_WEB_ERROR_STATUS \* WEBVIEW2_WEB_ERROR_STATUS）</span><span class="sxs-lookup"><span data-stu-id="6e020-122">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(WEBVIEW2_WEB_ERROR_STATUS \* WEBVIEW2_WEB_ERROR_STATUS)</span></span>

