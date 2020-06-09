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
ms.openlocfilehash: bfc802d160f7516f5f65e5526fecfd9742504045
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698565"
---
# <span data-ttu-id="c8913-104">interface ICoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="c8913-104">interface ICoreWebView2PermissionRequestedEventArgs</span></span> 

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="c8913-105">Webview.permissionrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="c8913-105">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="c8913-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c8913-106">Summary</span></span>

 <span data-ttu-id="c8913-107">成员</span><span class="sxs-lookup"><span data-stu-id="c8913-107">Members</span></span>                        | <span data-ttu-id="c8913-108">描述</span><span class="sxs-lookup"><span data-stu-id="c8913-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c8913-109">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="c8913-109">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="c8913-110">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="c8913-110">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="c8913-111">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="c8913-111">get_PermissionKind</span></span>](#get_permissionkind) | <span data-ttu-id="c8913-112">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="c8913-112">The type of the permission that is requested.</span></span>
[<span data-ttu-id="c8913-113">get_State</span><span class="sxs-lookup"><span data-stu-id="c8913-113">get_State</span></span>](#get_state) | <span data-ttu-id="c8913-114">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="c8913-114">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="c8913-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="c8913-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="c8913-116">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="c8913-116">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="c8913-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="c8913-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="c8913-118">可调用 GetDeferral 以返回[ICoreWebView2Deferral](icorewebview2deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="c8913-118">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>
[<span data-ttu-id="c8913-119">put_State</span><span class="sxs-lookup"><span data-stu-id="c8913-119">put_State</span></span>](#put_state) | <span data-ttu-id="c8913-120">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="c8913-120">Set the State property.</span></span>

## <span data-ttu-id="c8913-121">成员</span><span class="sxs-lookup"><span data-stu-id="c8913-121">Members</span></span>

#### <span data-ttu-id="c8913-122">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="c8913-122">get_IsUserInitiated</span></span> 

<span data-ttu-id="c8913-123">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="c8913-123">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="c8913-124">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="c8913-124">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="c8913-125">注意，通过用户手势启动并不意味着用户打算访问关联的资源。</span><span class="sxs-lookup"><span data-stu-id="c8913-125">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="c8913-126">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="c8913-126">get_PermissionKind</span></span> 

<span data-ttu-id="c8913-127">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="c8913-127">The type of the permission that is requested.</span></span>

> <span data-ttu-id="c8913-128">public HRESULT [get_PermissionKind](#get_permissionkind)（COREWEBVIEW2_PERMISSION_KIND \* 值）</span><span class="sxs-lookup"><span data-stu-id="c8913-128">public HRESULT [get_PermissionKind](#get_permissionkind)(COREWEBVIEW2_PERMISSION_KIND \* value)</span></span>

#### <span data-ttu-id="c8913-129">get_State</span><span class="sxs-lookup"><span data-stu-id="c8913-129">get_State</span></span> 

<span data-ttu-id="c8913-130">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="c8913-130">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="c8913-131">public HRESULT [get_State](#get_state)（COREWEBVIEW2_PERMISSION_STATE \* 值）</span><span class="sxs-lookup"><span data-stu-id="c8913-131">public HRESULT [get_State](#get_state)(COREWEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="c8913-132">是否授予请求。</span><span class="sxs-lookup"><span data-stu-id="c8913-132">whether the request is granted.</span></span> <span data-ttu-id="c8913-133">默认值为 COREWEBVIEW2_PERMISSION_STATE_DEFAULT。</span><span class="sxs-lookup"><span data-stu-id="c8913-133">Default value is COREWEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="c8913-134">get_Uri</span><span class="sxs-lookup"><span data-stu-id="c8913-134">get_Uri</span></span> 

<span data-ttu-id="c8913-135">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="c8913-135">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="c8913-136">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="c8913-136">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="c8913-137">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="c8913-137">GetDeferral</span></span> 

<span data-ttu-id="c8913-138">可调用 GetDeferral 以返回[ICoreWebView2Deferral](icorewebview2deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="c8913-138">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>

> <span data-ttu-id="c8913-139">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="c8913-139">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="c8913-140">开发人员可以使用延迟对象在以后的时间做出权限决定。</span><span class="sxs-lookup"><span data-stu-id="c8913-140">Developer can use the deferral object to make the permission decision at a later time.</span></span>

#### <span data-ttu-id="c8913-141">put_State</span><span class="sxs-lookup"><span data-stu-id="c8913-141">put_State</span></span> 

<span data-ttu-id="c8913-142">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="c8913-142">Set the State property.</span></span>

> <span data-ttu-id="c8913-143">public HRESULT [put_State](#put_state)（COREWEBVIEW2_PERMISSION_STATE 值）</span><span class="sxs-lookup"><span data-stu-id="c8913-143">public HRESULT [put_State](#put_state)(COREWEBVIEW2_PERMISSION_STATE value)</span></span>

