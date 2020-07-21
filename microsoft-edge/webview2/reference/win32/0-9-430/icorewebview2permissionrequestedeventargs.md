---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: e29765a4b8a3e620b8c627c7b05b9f0b4ff63f95
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886409"
---
# <span data-ttu-id="cb493-104">0.9.430-接口 ICoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="cb493-104">0.9.430 - interface ICoreWebView2PermissionRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="cb493-105">Webview.permissionrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="cb493-105">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="cb493-106">摘要</span><span class="sxs-lookup"><span data-stu-id="cb493-106">Summary</span></span>

 <span data-ttu-id="cb493-107">成员</span><span class="sxs-lookup"><span data-stu-id="cb493-107">Members</span></span>                        | <span data-ttu-id="cb493-108">描述</span><span class="sxs-lookup"><span data-stu-id="cb493-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cb493-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="cb493-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="cb493-110">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="cb493-110">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="cb493-111">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="cb493-111">get_PermissionKind</span></span>](#get_permissionkind) | <span data-ttu-id="cb493-112">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="cb493-112">The type of the permission that is requested.</span></span>
[<span data-ttu-id="cb493-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="cb493-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="cb493-114">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="cb493-114">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="cb493-115">get_State</span><span class="sxs-lookup"><span data-stu-id="cb493-115">get_State</span></span>](#get_state) | <span data-ttu-id="cb493-116">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="cb493-116">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="cb493-117">put_State</span><span class="sxs-lookup"><span data-stu-id="cb493-117">put_State</span></span>](#put_state) | <span data-ttu-id="cb493-118">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="cb493-118">Set the State property.</span></span>
[<span data-ttu-id="cb493-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="cb493-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="cb493-120">可调用 GetDeferral 以返回[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="cb493-120">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="cb493-121">成员</span><span class="sxs-lookup"><span data-stu-id="cb493-121">Members</span></span>

#### <span data-ttu-id="cb493-122">get_Uri</span><span class="sxs-lookup"><span data-stu-id="cb493-122">get_Uri</span></span> 

<span data-ttu-id="cb493-123">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="cb493-123">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="cb493-124">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="cb493-124">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="cb493-125">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="cb493-125">get_PermissionKind</span></span> 

<span data-ttu-id="cb493-126">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="cb493-126">The type of the permission that is requested.</span></span>

> <span data-ttu-id="cb493-127">public HRESULT [get_PermissionKind](#get_permissionkind)（CORE_WEBVIEW2_PERMISSION_KIND \* 值）</span><span class="sxs-lookup"><span data-stu-id="cb493-127">public HRESULT [get_PermissionKind](#get_permissionkind)(CORE_WEBVIEW2_PERMISSION_KIND \* value)</span></span>

#### <span data-ttu-id="cb493-128">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="cb493-128">get_IsUserInitiated</span></span> 

<span data-ttu-id="cb493-129">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="cb493-129">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="cb493-130">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="cb493-130">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="cb493-131">注意，通过用户手势启动并不意味着用户打算访问关联的资源。</span><span class="sxs-lookup"><span data-stu-id="cb493-131">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="cb493-132">get_State</span><span class="sxs-lookup"><span data-stu-id="cb493-132">get_State</span></span> 

<span data-ttu-id="cb493-133">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="cb493-133">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="cb493-134">public HRESULT [get_State](#get_state)（CORE_WEBVIEW2_PERMISSION_STATE \* 值）</span><span class="sxs-lookup"><span data-stu-id="cb493-134">public HRESULT [get_State](#get_state)(CORE_WEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="cb493-135">是否授予请求。</span><span class="sxs-lookup"><span data-stu-id="cb493-135">whether the request is granted.</span></span> <span data-ttu-id="cb493-136">默认值为 CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT。</span><span class="sxs-lookup"><span data-stu-id="cb493-136">Default value is CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="cb493-137">put_State</span><span class="sxs-lookup"><span data-stu-id="cb493-137">put_State</span></span> 

<span data-ttu-id="cb493-138">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="cb493-138">Set the State property.</span></span>

> <span data-ttu-id="cb493-139">public HRESULT [put_State](#put_state)（CORE_WEBVIEW2_PERMISSION_STATE 值）</span><span class="sxs-lookup"><span data-stu-id="cb493-139">public HRESULT [put_State](#put_state)(CORE_WEBVIEW2_PERMISSION_STATE value)</span></span>

#### <span data-ttu-id="cb493-140">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="cb493-140">GetDeferral</span></span> 

<span data-ttu-id="cb493-141">可调用 GetDeferral 以返回[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="cb493-141">GetDeferral can be called to return an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="cb493-142">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="cb493-142">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="cb493-143">开发人员可以使用延迟对象在以后的时间做出权限决定。</span><span class="sxs-lookup"><span data-stu-id="cb493-143">Developer can use the deferral object to make the permission decision at a later time.</span></span>

