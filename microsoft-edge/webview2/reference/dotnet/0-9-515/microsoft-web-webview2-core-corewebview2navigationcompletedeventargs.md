---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 2a18fe9f8f79a109047d029affab8d84a6ef845c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652818"
---
# <span data-ttu-id="7b22d-104">CoreWebView2NavigationCompletedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="7b22d-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

<span data-ttu-id="7b22d-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="7b22d-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="7b22d-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="7b22d-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="7b22d-107">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="7b22d-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="7b22d-108">摘要</span><span class="sxs-lookup"><span data-stu-id="7b22d-108">Summary</span></span>

 <span data-ttu-id="7b22d-109">成员</span><span class="sxs-lookup"><span data-stu-id="7b22d-109">Members</span></span>                        | <span data-ttu-id="7b22d-110">描述</span><span class="sxs-lookup"><span data-stu-id="7b22d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7b22d-111">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="7b22d-111">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="7b22d-112">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="7b22d-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="7b22d-113">NavigationId</span><span class="sxs-lookup"><span data-stu-id="7b22d-113">NavigationId</span></span>](#navigationid) | <span data-ttu-id="7b22d-114">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="7b22d-114">The ID of the navigation.</span></span>
[<span data-ttu-id="7b22d-115">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="7b22d-115">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="7b22d-116">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="7b22d-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="7b22d-117">成员</span><span class="sxs-lookup"><span data-stu-id="7b22d-117">Members</span></span>

#### <span data-ttu-id="7b22d-118">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="7b22d-118">IsSuccess</span></span> 

<span data-ttu-id="7b22d-119">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="7b22d-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="7b22d-120">公共 bool [IsSuccess](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="7b22d-120">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="7b22d-121">对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。</span><span class="sxs-lookup"><span data-stu-id="7b22d-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="7b22d-122">NavigationId</span><span class="sxs-lookup"><span data-stu-id="7b22d-122">NavigationId</span></span> 

<span data-ttu-id="7b22d-123">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="7b22d-123">The ID of the navigation.</span></span>

> <span data-ttu-id="7b22d-124">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="7b22d-124">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="7b22d-125">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="7b22d-125">WebErrorStatus</span></span> 

<span data-ttu-id="7b22d-126">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="7b22d-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="7b22d-127">公共 CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="7b22d-127">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

