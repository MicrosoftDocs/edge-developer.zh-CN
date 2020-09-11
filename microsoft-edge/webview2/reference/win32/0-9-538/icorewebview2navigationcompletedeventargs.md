---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NavigationCompletedEventArgs
ms.openlocfilehash: 482137fd0ffa10c60381d5b0f3dc3d7db6f9fdf7
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011291"
---
# <span data-ttu-id="198c3-104">0.9.579-接口 ICoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="198c3-104">0.9.579 - interface ICoreWebView2NavigationCompletedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

<span data-ttu-id="198c3-105">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="198c3-105">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="198c3-106">摘要</span><span class="sxs-lookup"><span data-stu-id="198c3-106">Summary</span></span>

 <span data-ttu-id="198c3-107">成员</span><span class="sxs-lookup"><span data-stu-id="198c3-107">Members</span></span>                        | <span data-ttu-id="198c3-108">描述</span><span class="sxs-lookup"><span data-stu-id="198c3-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="198c3-109">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="198c3-109">get_IsSuccess</span></span>](#get_issuccess) | <span data-ttu-id="198c3-110">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="198c3-110">True when the navigation is successful.</span></span>
[<span data-ttu-id="198c3-111">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="198c3-111">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="198c3-112">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="198c3-112">The ID of the navigation.</span></span>
[<span data-ttu-id="198c3-113">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="198c3-113">get_WebErrorStatus</span></span>](#get_weberrorstatus) | <span data-ttu-id="198c3-114">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="198c3-114">The error code if the navigation failed.</span></span>

## <span data-ttu-id="198c3-115">成员</span><span class="sxs-lookup"><span data-stu-id="198c3-115">Members</span></span>

#### <span data-ttu-id="198c3-116">get_IsSuccess</span><span class="sxs-lookup"><span data-stu-id="198c3-116">get_IsSuccess</span></span> 

<span data-ttu-id="198c3-117">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="198c3-117">True when the navigation is successful.</span></span>

> <span data-ttu-id="198c3-118">公共 HRESULT [get_IsSuccess](#get_issuccess) (BOOL \* IsSuccess) </span><span class="sxs-lookup"><span data-stu-id="198c3-118">public HRESULT [get_IsSuccess](#get_issuccess)(BOOL \* isSuccess)</span></span>

<span data-ttu-id="198c3-119">这对于在错误 (页面中结束的导航是错误的，因为没有网络、DNS 查找失败、HTTP 服务器通过 4xx) 做出响应，但也可能是 false，例如，在导航页面上调用 ( # A3。</span><span class="sxs-lookup"><span data-stu-id="198c3-119">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="198c3-120">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="198c3-120">get_NavigationId</span></span> 

<span data-ttu-id="198c3-121">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="198c3-121">The ID of the navigation.</span></span>

> <span data-ttu-id="198c3-122">公共 HRESULT [get_NavigationId](#get_navigationid) (UINT64 \* navigation_id) </span><span class="sxs-lookup"><span data-stu-id="198c3-122">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="198c3-123">get_WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="198c3-123">get_WebErrorStatus</span></span> 

<span data-ttu-id="198c3-124">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="198c3-124">The error code if the navigation failed.</span></span>

> <span data-ttu-id="198c3-125">公共 HRESULT [get_WebErrorStatus](#get_weberrorstatus) (COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS) </span><span class="sxs-lookup"><span data-stu-id="198c3-125">public HRESULT [get_WebErrorStatus](#get_weberrorstatus)(COREWEBVIEW2_WEB_ERROR_STATUS \* COREWEBVIEW2_WEB_ERROR_STATUS)</span></span>

