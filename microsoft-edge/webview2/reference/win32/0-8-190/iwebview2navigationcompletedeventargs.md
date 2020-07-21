---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: b496c37949e934fadf0af736059566edcab9f5c3
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885931"
---
# <span data-ttu-id="bd17f-104">0.8.355-接口 IWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="bd17f-104">0.8.355 - interface IWebView2NavigationCompletedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="bd17f-105">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="bd17f-105">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="bd17f-106">摘要</span><span class="sxs-lookup"><span data-stu-id="bd17f-106">Summary</span></span>

 <span data-ttu-id="bd17f-107">成员</span><span class="sxs-lookup"><span data-stu-id="bd17f-107">Members</span></span>                        | <span data-ttu-id="bd17f-108">描述</span><span class="sxs-lookup"><span data-stu-id="bd17f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bd17f-109">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="bd17f-109">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="bd17f-110">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="bd17f-110">True when the navigation is successful.</span></span>
[<span data-ttu-id="bd17f-111">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="bd17f-111">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="bd17f-112">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="bd17f-112">The error code if the navigation failed.</span></span>

## <span data-ttu-id="bd17f-113">成员</span><span class="sxs-lookup"><span data-stu-id="bd17f-113">Members</span></span>

#### <span data-ttu-id="bd17f-114">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="bd17f-114">get_IsSuccess</span></span> 

<span data-ttu-id="bd17f-115">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="bd17f-115">True when the navigation is successful.</span></span>

> <span data-ttu-id="bd17f-116">public HRESULT [get_IsSuccess](#get_issuccess)（BOOL \* IsSuccess）</span><span class="sxs-lookup"><span data-stu-id="bd17f-116">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="bd17f-117">对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。</span><span class="sxs-lookup"><span data-stu-id="bd17f-117">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="bd17f-118">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="bd17f-118">get_WebErrorStatus</span></span> 

<span data-ttu-id="bd17f-119">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="bd17f-119">The error code if the navigation failed.</span></span>

> <span data-ttu-id="bd17f-120">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)（WEBVIEW2_WEB_ERROR_STATUS \* WEBVIEW2_WEB_ERROR_STATUS）</span><span class="sxs-lookup"><span data-stu-id="bd17f-120">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(WEBVIEW2_WEB_ERROR_STATUS \* WEBVIEW2_WEB_ERROR_STATUS)</span></span>

