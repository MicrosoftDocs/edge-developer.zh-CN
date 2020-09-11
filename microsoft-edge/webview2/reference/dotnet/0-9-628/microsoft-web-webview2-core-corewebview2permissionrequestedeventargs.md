---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2PermissionRequestedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 87993559d4d70daef84cbd86a2305f09cc017aa9
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011671"
---
# <span data-ttu-id="5288c-104">CoreWebView2PermissionRequestedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="5288c-104">Microsoft.Web.WebView2.Core.CoreWebView2PermissionRequestedEventArgs class</span></span> 

<span data-ttu-id="5288c-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="5288c-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="5288c-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="5288c-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="5288c-107">Webview.permissionrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="5288c-107">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="5288c-108">摘要</span><span class="sxs-lookup"><span data-stu-id="5288c-108">Summary</span></span>

 <span data-ttu-id="5288c-109">成员</span><span class="sxs-lookup"><span data-stu-id="5288c-109">Members</span></span>                        | <span data-ttu-id="5288c-110">描述</span><span class="sxs-lookup"><span data-stu-id="5288c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5288c-111">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="5288c-111">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="5288c-112">当通过用户手势（如单击带有目标的锚点标记）启动新的窗口请求时，为 True。</span><span class="sxs-lookup"><span data-stu-id="5288c-112">True when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="5288c-113">PermissionKind</span><span class="sxs-lookup"><span data-stu-id="5288c-113">PermissionKind</span></span>](#permissionkind) | <span data-ttu-id="5288c-114">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="5288c-114">The type of the permission that is requested.</span></span>
[<span data-ttu-id="5288c-115">State</span><span class="sxs-lookup"><span data-stu-id="5288c-115">State</span></span>](#state) | <span data-ttu-id="5288c-116">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="5288c-116">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="5288c-117">Uri</span><span class="sxs-lookup"><span data-stu-id="5288c-117">Uri</span></span>](#uri) | <span data-ttu-id="5288c-118">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="5288c-118">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="5288c-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="5288c-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="5288c-120">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="5288c-120">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="5288c-121">成员</span><span class="sxs-lookup"><span data-stu-id="5288c-121">Members</span></span>

#### <span data-ttu-id="5288c-122">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="5288c-122">IsUserInitiated</span></span> 

<span data-ttu-id="5288c-123">当通过用户手势（如单击带有目标的锚点标记）启动新的窗口请求时，为 True。</span><span class="sxs-lookup"><span data-stu-id="5288c-123">True when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="5288c-124">公共 bool [IsUserInitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="5288c-124">public bool [IsUserInitiated](#isuserinitiated)</span></span>

<span data-ttu-id="5288c-125">对 Web 视图禁用了边缘弹出窗口阻止程序，以便应用可以使用此标志来阻止非用户启动的弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="5288c-125">The Edge popup blocker is disabled for WebView so the app can use this flag to block non-user initiated popups.</span></span>

#### <span data-ttu-id="5288c-126">PermissionKind</span><span class="sxs-lookup"><span data-stu-id="5288c-126">PermissionKind</span></span> 

<span data-ttu-id="5288c-127">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="5288c-127">The type of the permission that is requested.</span></span>

> <span data-ttu-id="5288c-128">公共 CoreWebView2PermissionKind [PermissionKind](#permissionkind)</span><span class="sxs-lookup"><span data-stu-id="5288c-128">public CoreWebView2PermissionKind [PermissionKind](#permissionkind)</span></span>

#### <span data-ttu-id="5288c-129">State</span><span class="sxs-lookup"><span data-stu-id="5288c-129">State</span></span> 

<span data-ttu-id="5288c-130">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="5288c-130">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="5288c-131">公共 CoreWebView2PermissionState [状态](#state)</span><span class="sxs-lookup"><span data-stu-id="5288c-131">public CoreWebView2PermissionState [State](#state)</span></span>

<span data-ttu-id="5288c-132">是否授予请求。</span><span class="sxs-lookup"><span data-stu-id="5288c-132">whether the request is granted.</span></span>

<span data-ttu-id="5288c-133">默认值为 CoreWebView2PermissionState。</span><span class="sxs-lookup"><span data-stu-id="5288c-133">Default value is CoreWebView2PermissionState.Default.</span></span>

#### <span data-ttu-id="5288c-134">Uri</span><span class="sxs-lookup"><span data-stu-id="5288c-134">Uri</span></span> 

<span data-ttu-id="5288c-135">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="5288c-135">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="5288c-136">公共字符串 [Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="5288c-136">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="5288c-137">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="5288c-137">GetDeferral</span></span> 

<span data-ttu-id="5288c-138">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="5288c-138">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="5288c-139">公共 CoreWebView2Deferral [GetDeferral](#getdeferral) ( # A1</span><span class="sxs-lookup"><span data-stu-id="5288c-139">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="5288c-140">开发人员可以使用延迟对象在以后的时间做出权限决定。</span><span class="sxs-lookup"><span data-stu-id="5288c-140">Developer can use the deferral object to make the permission decision at a later time.</span></span>

