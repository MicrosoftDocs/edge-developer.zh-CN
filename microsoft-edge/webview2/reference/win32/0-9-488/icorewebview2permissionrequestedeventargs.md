---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 88f5008dbc9a4ebfccfe96299899a2474ecc6d95
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880407"
---
# <span data-ttu-id="018df-104">0.9.515-接口 ICoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="018df-104">0.9.515 - interface ICoreWebView2PermissionRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="018df-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="018df-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="018df-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="018df-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="018df-107">Webview.permissionrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="018df-107">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="018df-108">摘要</span><span class="sxs-lookup"><span data-stu-id="018df-108">Summary</span></span>

 <span data-ttu-id="018df-109">成员</span><span class="sxs-lookup"><span data-stu-id="018df-109">Members</span></span>                        | <span data-ttu-id="018df-110">描述</span><span class="sxs-lookup"><span data-stu-id="018df-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="018df-111">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="018df-111">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="018df-112">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="018df-112">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="018df-113">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="018df-113">get_PermissionKind</span></span>](#get_permissionkind) | <span data-ttu-id="018df-114">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="018df-114">The type of the permission that is requested.</span></span>
[<span data-ttu-id="018df-115">get_State</span><span class="sxs-lookup"><span data-stu-id="018df-115">get_State</span></span>](#get_state) | <span data-ttu-id="018df-116">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="018df-116">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="018df-117">get_Uri</span><span class="sxs-lookup"><span data-stu-id="018df-117">get_Uri</span></span>](#get_uri) | <span data-ttu-id="018df-118">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="018df-118">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="018df-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="018df-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="018df-120">可调用 GetDeferral 以返回[ICoreWebView2Deferral](icorewebview2deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="018df-120">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>
[<span data-ttu-id="018df-121">put_State</span><span class="sxs-lookup"><span data-stu-id="018df-121">put_State</span></span>](#put_state) | <span data-ttu-id="018df-122">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="018df-122">Set the State property.</span></span>

## <span data-ttu-id="018df-123">成员</span><span class="sxs-lookup"><span data-stu-id="018df-123">Members</span></span>

#### <span data-ttu-id="018df-124">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="018df-124">get_IsUserInitiated</span></span> 

<span data-ttu-id="018df-125">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="018df-125">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="018df-126">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="018df-126">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="018df-127">注意，通过用户手势启动并不意味着用户打算访问关联的资源。</span><span class="sxs-lookup"><span data-stu-id="018df-127">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="018df-128">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="018df-128">get_PermissionKind</span></span> 

<span data-ttu-id="018df-129">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="018df-129">The type of the permission that is requested.</span></span>

> <span data-ttu-id="018df-130">public HRESULT [get_PermissionKind](#get_permissionkind)（COREWEBVIEW2_PERMISSION_KIND \* 值）</span><span class="sxs-lookup"><span data-stu-id="018df-130">public HRESULT [get_PermissionKind](#get_permissionkind)(COREWEBVIEW2_PERMISSION_KIND \* value)</span></span>

#### <span data-ttu-id="018df-131">get_State</span><span class="sxs-lookup"><span data-stu-id="018df-131">get_State</span></span> 

<span data-ttu-id="018df-132">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="018df-132">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="018df-133">public HRESULT [get_State](#get_state)（COREWEBVIEW2_PERMISSION_STATE \* 值）</span><span class="sxs-lookup"><span data-stu-id="018df-133">public HRESULT [get_State](#get_state)(COREWEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="018df-134">是否授予请求。</span><span class="sxs-lookup"><span data-stu-id="018df-134">whether the request is granted.</span></span> <span data-ttu-id="018df-135">默认值为 COREWEBVIEW2_PERMISSION_STATE_DEFAULT。</span><span class="sxs-lookup"><span data-stu-id="018df-135">Default value is COREWEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="018df-136">get_Uri</span><span class="sxs-lookup"><span data-stu-id="018df-136">get_Uri</span></span> 

<span data-ttu-id="018df-137">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="018df-137">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="018df-138">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="018df-138">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="018df-139">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="018df-139">GetDeferral</span></span> 

<span data-ttu-id="018df-140">可调用 GetDeferral 以返回[ICoreWebView2Deferral](icorewebview2deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="018df-140">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>

> <span data-ttu-id="018df-141">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="018df-141">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="018df-142">开发人员可以使用延迟对象在以后的时间做出权限决定。</span><span class="sxs-lookup"><span data-stu-id="018df-142">Developer can use the deferral object to make the permission decision at a later time.</span></span>

#### <span data-ttu-id="018df-143">put_State</span><span class="sxs-lookup"><span data-stu-id="018df-143">put_State</span></span> 

<span data-ttu-id="018df-144">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="018df-144">Set the State property.</span></span>

> <span data-ttu-id="018df-145">public HRESULT [put_State](#put_state)（COREWEBVIEW2_PERMISSION_STATE 值）</span><span class="sxs-lookup"><span data-stu-id="018df-145">public HRESULT [put_State](#put_state)(COREWEBVIEW2_PERMISSION_STATE value)</span></span>

