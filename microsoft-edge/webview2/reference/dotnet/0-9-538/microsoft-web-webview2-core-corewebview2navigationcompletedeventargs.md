---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2。 CoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 01102cc9aa9d6fbec7f4d223e1115892dabe2899
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010969"
---
# <span data-ttu-id="eb31c-104">0.9.579-WebView2 的 CoreWebView2NavigationCompletedEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="eb31c-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2NavigationCompletedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="eb31c-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="eb31c-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="eb31c-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="eb31c-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="eb31c-107">NavigationCompleted 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="eb31c-107">Event args for the NavigationCompleted event.</span></span>

## <span data-ttu-id="eb31c-108">摘要</span><span class="sxs-lookup"><span data-stu-id="eb31c-108">Summary</span></span>

 <span data-ttu-id="eb31c-109">成员</span><span class="sxs-lookup"><span data-stu-id="eb31c-109">Members</span></span>                        | <span data-ttu-id="eb31c-110">描述</span><span class="sxs-lookup"><span data-stu-id="eb31c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="eb31c-111">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="eb31c-111">IsSuccess</span></span>](#issuccess) | <span data-ttu-id="eb31c-112">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="eb31c-112">True when the navigation is successful.</span></span>
[<span data-ttu-id="eb31c-113">NavigationId</span><span class="sxs-lookup"><span data-stu-id="eb31c-113">NavigationId</span></span>](#navigationid) | <span data-ttu-id="eb31c-114">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="eb31c-114">The ID of the navigation.</span></span>
[<span data-ttu-id="eb31c-115">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="eb31c-115">WebErrorStatus</span></span>](#weberrorstatus) | <span data-ttu-id="eb31c-116">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="eb31c-116">The error code if the navigation failed.</span></span>

## <span data-ttu-id="eb31c-117">成员</span><span class="sxs-lookup"><span data-stu-id="eb31c-117">Members</span></span>

#### <span data-ttu-id="eb31c-118">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="eb31c-118">IsSuccess</span></span> 

<span data-ttu-id="eb31c-119">导航成功时为 True。</span><span class="sxs-lookup"><span data-stu-id="eb31c-119">True when the navigation is successful.</span></span>

> <span data-ttu-id="eb31c-120">公共 bool [IsSuccess](#issuccess)</span><span class="sxs-lookup"><span data-stu-id="eb31c-120">public bool [IsSuccess](#issuccess)</span></span>

<span data-ttu-id="eb31c-121">这对于在错误 (页面中结束的导航是错误的，因为没有网络、DNS 查找失败、HTTP 服务器通过 4xx) 做出响应，但也可能是 false，例如，在导航页面上调用 ( # A3。</span><span class="sxs-lookup"><span data-stu-id="eb31c-121">This is false for a navigation that ended up in an error page (failures due to no network, DNS lookup failure, HTTP server responds with 4xx), but could also be false for additional things such as window.stop() called on navigated page.</span></span>

#### <span data-ttu-id="eb31c-122">NavigationId</span><span class="sxs-lookup"><span data-stu-id="eb31c-122">NavigationId</span></span> 

<span data-ttu-id="eb31c-123">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="eb31c-123">The ID of the navigation.</span></span>

> <span data-ttu-id="eb31c-124">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="eb31c-124">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="eb31c-125">WebErrorStatus</span><span class="sxs-lookup"><span data-stu-id="eb31c-125">WebErrorStatus</span></span> 

<span data-ttu-id="eb31c-126">导航失败时的错误代码。</span><span class="sxs-lookup"><span data-stu-id="eb31c-126">The error code if the navigation failed.</span></span>

> <span data-ttu-id="eb31c-127">公共 CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span><span class="sxs-lookup"><span data-stu-id="eb31c-127">public CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)</span></span>

