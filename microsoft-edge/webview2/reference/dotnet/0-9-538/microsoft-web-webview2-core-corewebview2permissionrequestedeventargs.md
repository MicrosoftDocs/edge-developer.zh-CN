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
ms.openlocfilehash: 58d87d1815b81969c4424eacfcec26ffe425192e
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698418"
---
# <span data-ttu-id="f8a52-104">CoreWebView2PermissionRequestedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="f8a52-104">Microsoft.Web.WebView2.Core.CoreWebView2PermissionRequestedEventArgs class</span></span> 

<span data-ttu-id="f8a52-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="f8a52-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="f8a52-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="f8a52-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="f8a52-107">Webview.permissionrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f8a52-107">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="f8a52-108">摘要</span><span class="sxs-lookup"><span data-stu-id="f8a52-108">Summary</span></span>

 <span data-ttu-id="f8a52-109">成员</span><span class="sxs-lookup"><span data-stu-id="f8a52-109">Members</span></span>                        | <span data-ttu-id="f8a52-110">描述</span><span class="sxs-lookup"><span data-stu-id="f8a52-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f8a52-111">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="f8a52-111">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="f8a52-112">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="f8a52-112">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="f8a52-113">PermissionKind</span><span class="sxs-lookup"><span data-stu-id="f8a52-113">PermissionKind</span></span>](#permissionkind) | <span data-ttu-id="f8a52-114">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="f8a52-114">The type of the permission that is requested.</span></span>
[<span data-ttu-id="f8a52-115">State</span><span class="sxs-lookup"><span data-stu-id="f8a52-115">State</span></span>](#state) | <span data-ttu-id="f8a52-116">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="f8a52-116">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="f8a52-117">Uri</span><span class="sxs-lookup"><span data-stu-id="f8a52-117">Uri</span></span>](#uri) | <span data-ttu-id="f8a52-118">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="f8a52-118">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="f8a52-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="f8a52-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="f8a52-120">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="f8a52-120">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="f8a52-121">成员</span><span class="sxs-lookup"><span data-stu-id="f8a52-121">Members</span></span>

#### <span data-ttu-id="f8a52-122">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="f8a52-122">IsUserInitiated</span></span> 

<span data-ttu-id="f8a52-123">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="f8a52-123">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="f8a52-124">公共 bool [IsUserInitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="f8a52-124">public bool [IsUserInitiated](#isuserinitiated)</span></span>

<span data-ttu-id="f8a52-125">注意，通过用户手势启动并不意味着用户打算访问关联的资源。</span><span class="sxs-lookup"><span data-stu-id="f8a52-125">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="f8a52-126">PermissionKind</span><span class="sxs-lookup"><span data-stu-id="f8a52-126">PermissionKind</span></span> 

<span data-ttu-id="f8a52-127">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="f8a52-127">The type of the permission that is requested.</span></span>

> <span data-ttu-id="f8a52-128">公共 CoreWebView2PermissionKind [PermissionKind](#permissionkind)</span><span class="sxs-lookup"><span data-stu-id="f8a52-128">public CoreWebView2PermissionKind [PermissionKind](#permissionkind)</span></span>

#### <span data-ttu-id="f8a52-129">State</span><span class="sxs-lookup"><span data-stu-id="f8a52-129">State</span></span> 

<span data-ttu-id="f8a52-130">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="f8a52-130">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="f8a52-131">公共 CoreWebView2PermissionState[状态](#state)</span><span class="sxs-lookup"><span data-stu-id="f8a52-131">public CoreWebView2PermissionState [State](#state)</span></span>

<span data-ttu-id="f8a52-132">是否授予请求。</span><span class="sxs-lookup"><span data-stu-id="f8a52-132">whether the request is granted.</span></span>

<span data-ttu-id="f8a52-133">默认值为 CoreWebView2PermissionState。</span><span class="sxs-lookup"><span data-stu-id="f8a52-133">Default value is CoreWebView2PermissionState.Default.</span></span>

#### <span data-ttu-id="f8a52-134">Uri</span><span class="sxs-lookup"><span data-stu-id="f8a52-134">Uri</span></span> 

<span data-ttu-id="f8a52-135">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="f8a52-135">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="f8a52-136">公共字符串[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="f8a52-136">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="f8a52-137">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="f8a52-137">GetDeferral</span></span> 

<span data-ttu-id="f8a52-138">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="f8a52-138">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="f8a52-139">公共 CoreWebView2Deferral [GetDeferral](#getdeferral)（）</span><span class="sxs-lookup"><span data-stu-id="f8a52-139">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="f8a52-140">开发人员可以使用延迟对象在以后的时间做出权限决定。</span><span class="sxs-lookup"><span data-stu-id="f8a52-140">Developer can use the deferral object to make the permission decision at a later time.</span></span>

