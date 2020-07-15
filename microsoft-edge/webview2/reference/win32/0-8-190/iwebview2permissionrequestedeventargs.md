---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 92c08d199aa607dae9cc575955a1eb0bf016a9c0
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878328"
---
# <span data-ttu-id="ba3e8-104">0.8.355-接口 IWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="ba3e8-104">0.8.355 - interface IWebView2PermissionRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="ba3e8-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="ba3e8-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="ba3e8-107">Webview.permissionrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-107">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="ba3e8-108">摘要</span><span class="sxs-lookup"><span data-stu-id="ba3e8-108">Summary</span></span>

 <span data-ttu-id="ba3e8-109">成员</span><span class="sxs-lookup"><span data-stu-id="ba3e8-109">Members</span></span>                        | <span data-ttu-id="ba3e8-110">描述</span><span class="sxs-lookup"><span data-stu-id="ba3e8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ba3e8-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="ba3e8-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="ba3e8-112">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-112">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="ba3e8-113">get_PermissionType</span><span class="sxs-lookup"><span data-stu-id="ba3e8-113">get_PermissionType</span></span>](#get_permissiontype) | <span data-ttu-id="ba3e8-114">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-114">The type of the permission that is requested.</span></span>
[<span data-ttu-id="ba3e8-115">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="ba3e8-115">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="ba3e8-116">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-116">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="ba3e8-117">get_State</span><span class="sxs-lookup"><span data-stu-id="ba3e8-117">get_State</span></span>](#get_state) | <span data-ttu-id="ba3e8-118">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="ba3e8-118">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="ba3e8-119">put_State</span><span class="sxs-lookup"><span data-stu-id="ba3e8-119">put_State</span></span>](#put_state) | <span data-ttu-id="ba3e8-120">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-120">Set the State property.</span></span>
[<span data-ttu-id="ba3e8-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="ba3e8-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="ba3e8-122">可调用 GetDeferral 以返回[IWebView2Deferral](IWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-122">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="ba3e8-123">成员</span><span class="sxs-lookup"><span data-stu-id="ba3e8-123">Members</span></span>

#### <span data-ttu-id="ba3e8-124">get_Uri</span><span class="sxs-lookup"><span data-stu-id="ba3e8-124">get_Uri</span></span> 

<span data-ttu-id="ba3e8-125">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-125">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="ba3e8-126">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="ba3e8-126">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="ba3e8-127">get_PermissionType</span><span class="sxs-lookup"><span data-stu-id="ba3e8-127">get_PermissionType</span></span> 

<span data-ttu-id="ba3e8-128">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-128">The type of the permission that is requested.</span></span>

> <span data-ttu-id="ba3e8-129">public HRESULT [get_PermissionType](#get_permissiontype)（WEBVIEW2_PERMISSION_TYPE \* 值）</span><span class="sxs-lookup"><span data-stu-id="ba3e8-129">public HRESULT [get_PermissionType](#get_permissiontype)(WEBVIEW2_PERMISSION_TYPE \* value)</span></span>

#### <span data-ttu-id="ba3e8-130">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="ba3e8-130">get_IsUserInitiated</span></span> 

<span data-ttu-id="ba3e8-131">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-131">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="ba3e8-132">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="ba3e8-132">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="ba3e8-133">注意，通过用户手势启动并不意味着用户打算访问关联的资源。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-133">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="ba3e8-134">get_State</span><span class="sxs-lookup"><span data-stu-id="ba3e8-134">get_State</span></span> 

<span data-ttu-id="ba3e8-135">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="ba3e8-135">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="ba3e8-136">public HRESULT [get_State](#get_state)（WEBVIEW2_PERMISSION_STATE \* 值）</span><span class="sxs-lookup"><span data-stu-id="ba3e8-136">public HRESULT [get_State](#get_state)(WEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="ba3e8-137">是否授予请求。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-137">whether the request is granted.</span></span> <span data-ttu-id="ba3e8-138">默认值为 WEBVIEW2_PERMISSION_STATE_DEFAULT。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-138">Default value is WEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="ba3e8-139">put_State</span><span class="sxs-lookup"><span data-stu-id="ba3e8-139">put_State</span></span> 

<span data-ttu-id="ba3e8-140">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-140">Set the State property.</span></span>

> <span data-ttu-id="ba3e8-141">public HRESULT [put_State](#put_state)（WEBVIEW2_PERMISSION_STATE 值）</span><span class="sxs-lookup"><span data-stu-id="ba3e8-141">public HRESULT [put_State](#put_state)(WEBVIEW2_PERMISSION_STATE value)</span></span>

#### <span data-ttu-id="ba3e8-142">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="ba3e8-142">GetDeferral</span></span> 

<span data-ttu-id="ba3e8-143">可调用 GetDeferral 以返回[IWebView2Deferral](IWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-143">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="ba3e8-144">公共 HRESULT [GetDeferral](#getdeferral)（[IWebView2Deferral](IWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="ba3e8-144">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="ba3e8-145">开发人员可以使用延迟对象在以后的时间做出权限决定。</span><span class="sxs-lookup"><span data-stu-id="ba3e8-145">Developer can use the deferral object to make the permission decision at a later time.</span></span>

