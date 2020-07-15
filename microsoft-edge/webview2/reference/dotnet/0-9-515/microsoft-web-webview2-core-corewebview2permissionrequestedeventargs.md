---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 22fc8ec74c8da0a0ff072cacf91a792b9246900f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879798"
---
# <span data-ttu-id="70276-104">0.9.515-WebView2 的 CoreWebView2PermissionRequestedEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="70276-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2PermissionRequestedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="70276-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="70276-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="70276-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="70276-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="70276-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="70276-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="70276-108">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="70276-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="70276-109">Webview.permissionrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="70276-109">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="70276-110">摘要</span><span class="sxs-lookup"><span data-stu-id="70276-110">Summary</span></span>

 <span data-ttu-id="70276-111">成员</span><span class="sxs-lookup"><span data-stu-id="70276-111">Members</span></span>                        | <span data-ttu-id="70276-112">描述</span><span class="sxs-lookup"><span data-stu-id="70276-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="70276-113">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="70276-113">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="70276-114">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="70276-114">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="70276-115">PermissionKind</span><span class="sxs-lookup"><span data-stu-id="70276-115">PermissionKind</span></span>](#permissionkind) | <span data-ttu-id="70276-116">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="70276-116">The type of the permission that is requested.</span></span>
[<span data-ttu-id="70276-117">State</span><span class="sxs-lookup"><span data-stu-id="70276-117">State</span></span>](#state) | <span data-ttu-id="70276-118">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="70276-118">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="70276-119">Uri</span><span class="sxs-lookup"><span data-stu-id="70276-119">Uri</span></span>](#uri) | <span data-ttu-id="70276-120">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="70276-120">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="70276-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="70276-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="70276-122">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="70276-122">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

## <span data-ttu-id="70276-123">成员</span><span class="sxs-lookup"><span data-stu-id="70276-123">Members</span></span>

#### <span data-ttu-id="70276-124">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="70276-124">IsUserInitiated</span></span> 

<span data-ttu-id="70276-125">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="70276-125">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="70276-126">公共 bool [IsUserInitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="70276-126">public bool [IsUserInitiated](#isuserinitiated)</span></span>

<span data-ttu-id="70276-127">注意，通过用户手势启动并不意味着用户打算访问关联的资源。</span><span class="sxs-lookup"><span data-stu-id="70276-127">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="70276-128">PermissionKind</span><span class="sxs-lookup"><span data-stu-id="70276-128">PermissionKind</span></span> 

<span data-ttu-id="70276-129">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="70276-129">The type of the permission that is requested.</span></span>

> <span data-ttu-id="70276-130">公共 CoreWebView2PermissionKind [PermissionKind](#permissionkind)</span><span class="sxs-lookup"><span data-stu-id="70276-130">public CoreWebView2PermissionKind [PermissionKind](#permissionkind)</span></span>

#### <span data-ttu-id="70276-131">State</span><span class="sxs-lookup"><span data-stu-id="70276-131">State</span></span> 

<span data-ttu-id="70276-132">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="70276-132">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="70276-133">公共 CoreWebView2PermissionState[状态](#state)</span><span class="sxs-lookup"><span data-stu-id="70276-133">public CoreWebView2PermissionState [State](#state)</span></span>

<span data-ttu-id="70276-134">是否授予请求。</span><span class="sxs-lookup"><span data-stu-id="70276-134">whether the request is granted.</span></span>

<span data-ttu-id="70276-135">默认值为 CoreWebView2PermissionState。</span><span class="sxs-lookup"><span data-stu-id="70276-135">Default value is CoreWebView2PermissionState.Default.</span></span>

#### <span data-ttu-id="70276-136">Uri</span><span class="sxs-lookup"><span data-stu-id="70276-136">Uri</span></span> 

<span data-ttu-id="70276-137">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="70276-137">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="70276-138">公共字符串[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="70276-138">public string [Uri](#uri)</span></span>

#### <span data-ttu-id="70276-139">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="70276-139">GetDeferral</span></span> 

<span data-ttu-id="70276-140">可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。</span><span class="sxs-lookup"><span data-stu-id="70276-140">GetDeferral can be called to return a CoreWebView2Deferral object.</span></span>

> <span data-ttu-id="70276-141">公共 CoreWebView2Deferral [GetDeferral](#getdeferral)（）</span><span class="sxs-lookup"><span data-stu-id="70276-141">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="70276-142">开发人员可以使用延迟对象在以后的时间做出权限决定。</span><span class="sxs-lookup"><span data-stu-id="70276-142">Developer can use the deferral object to make the permission decision at a later time.</span></span>

