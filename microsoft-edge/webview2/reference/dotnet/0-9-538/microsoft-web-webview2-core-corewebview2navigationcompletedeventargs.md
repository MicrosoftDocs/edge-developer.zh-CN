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
ms.openlocfilehash: c82c37d7127d69700f35fbf9e2a69f85159a7109
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698442"
---
# <span data-ttu-id="66e30-104">CoreWebView2NavigationCompletedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="66e30-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

<span data-ttu-id="66e30-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="66e30-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="66e30-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="66e30-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="66e30-107">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="66e30-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="66e30-108">摘要</span><span class="sxs-lookup"><span data-stu-id="66e30-108">Summary</span></span>

 <span data-ttu-id="66e30-109">成员</span><span class="sxs-lookup"><span data-stu-id="66e30-109">Members</span></span>                        | <span data-ttu-id="66e30-110">描述</span><span class="sxs-lookup"><span data-stu-id="66e30-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="66e30-111">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="66e30-111">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="66e30-112">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="66e30-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="66e30-113">NavigationId</span><span class="sxs-lookup"><span data-stu-id="66e30-113">NavigationId</span></span>](#navigationid) | <span data-ttu-id="66e30-114">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="66e30-114">The ID of the navigation.</span></span>
[<span data-ttu-id="66e30-115">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="66e30-115">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="66e30-116">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="66e30-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="66e30-117">成员</span><span class="sxs-lookup"><span data-stu-id="66e30-117">Members</span></span>

#### <span data-ttu-id="66e30-118">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="66e30-118">IsSuccess</span></span> 

<span data-ttu-id="66e30-119">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="66e30-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="66e30-120">公共 bool [IsSuccess](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="66e30-120">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="66e30-121">对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。</span><span class="sxs-lookup"><span data-stu-id="66e30-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="66e30-122">NavigationId</span><span class="sxs-lookup"><span data-stu-id="66e30-122">NavigationId</span></span> 

<span data-ttu-id="66e30-123">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="66e30-123">The ID of the navigation.</span></span>

> <span data-ttu-id="66e30-124">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="66e30-124">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="66e30-125">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="66e30-125">WebErrorStatus</span></span> 

<span data-ttu-id="66e30-126">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="66e30-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="66e30-127">公共 CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="66e30-127">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

