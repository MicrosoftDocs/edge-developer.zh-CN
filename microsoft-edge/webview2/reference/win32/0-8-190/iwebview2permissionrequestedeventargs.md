---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: e2a9486011d5ef3ef480271ed32a7c8b586cf9bd
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885826"
---
# <span data-ttu-id="1da62-104">0.8.355-接口 IWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="1da62-104">0.8.355 - interface IWebView2PermissionRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="1da62-105">Webview.permissionrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="1da62-105">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="1da62-106">摘要</span><span class="sxs-lookup"><span data-stu-id="1da62-106">Summary</span></span>

 <span data-ttu-id="1da62-107">成员</span><span class="sxs-lookup"><span data-stu-id="1da62-107">Members</span></span>                        | <span data-ttu-id="1da62-108">描述</span><span class="sxs-lookup"><span data-stu-id="1da62-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1da62-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="1da62-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="1da62-110">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="1da62-110">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="1da62-111">get_PermissionType</span><span class="sxs-lookup"><span data-stu-id="1da62-111">get_PermissionType</span></span>](#get_permissiontype) | <span data-ttu-id="1da62-112">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="1da62-112">The type of the permission that is requested.</span></span>
[<span data-ttu-id="1da62-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="1da62-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="1da62-114">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="1da62-114">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="1da62-115">get_State</span><span class="sxs-lookup"><span data-stu-id="1da62-115">get_State</span></span>](#get_state) | <span data-ttu-id="1da62-116">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="1da62-116">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="1da62-117">put_State</span><span class="sxs-lookup"><span data-stu-id="1da62-117">put_State</span></span>](#put_state) | <span data-ttu-id="1da62-118">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="1da62-118">Set the State property.</span></span>
[<span data-ttu-id="1da62-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="1da62-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="1da62-120">可调用 GetDeferral 以返回[IWebView2Deferral](IWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="1da62-120">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

## <span data-ttu-id="1da62-121">成员</span><span class="sxs-lookup"><span data-stu-id="1da62-121">Members</span></span>

#### <span data-ttu-id="1da62-122">get_Uri</span><span class="sxs-lookup"><span data-stu-id="1da62-122">get_Uri</span></span> 

<span data-ttu-id="1da62-123">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="1da62-123">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="1da62-124">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="1da62-124">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="1da62-125">get_PermissionType</span><span class="sxs-lookup"><span data-stu-id="1da62-125">get_PermissionType</span></span> 

<span data-ttu-id="1da62-126">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="1da62-126">The type of the permission that is requested.</span></span>

> <span data-ttu-id="1da62-127">public HRESULT [get_PermissionType](#get_permissiontype)（WEBVIEW2_PERMISSION_TYPE \* 值）</span><span class="sxs-lookup"><span data-stu-id="1da62-127">public HRESULT [get_PermissionType](#get_permissiontype)(WEBVIEW2_PERMISSION_TYPE \* value)</span></span>

#### <span data-ttu-id="1da62-128">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="1da62-128">get_IsUserInitiated</span></span> 

<span data-ttu-id="1da62-129">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="1da62-129">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="1da62-130">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="1da62-130">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="1da62-131">注意，通过用户手势启动并不意味着用户打算访问关联的资源。</span><span class="sxs-lookup"><span data-stu-id="1da62-131">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="1da62-132">get_State</span><span class="sxs-lookup"><span data-stu-id="1da62-132">get_State</span></span> 

<span data-ttu-id="1da62-133">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="1da62-133">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="1da62-134">public HRESULT [get_State](#get_state)（WEBVIEW2_PERMISSION_STATE \* 值）</span><span class="sxs-lookup"><span data-stu-id="1da62-134">public HRESULT [get_State](#get_state)(WEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="1da62-135">是否授予请求。</span><span class="sxs-lookup"><span data-stu-id="1da62-135">whether the request is granted.</span></span> <span data-ttu-id="1da62-136">默认值为 WEBVIEW2_PERMISSION_STATE_DEFAULT。</span><span class="sxs-lookup"><span data-stu-id="1da62-136">Default value is WEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="1da62-137">put_State</span><span class="sxs-lookup"><span data-stu-id="1da62-137">put_State</span></span> 

<span data-ttu-id="1da62-138">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="1da62-138">Set the State property.</span></span>

> <span data-ttu-id="1da62-139">public HRESULT [put_State](#put_state)（WEBVIEW2_PERMISSION_STATE 值）</span><span class="sxs-lookup"><span data-stu-id="1da62-139">public HRESULT [put_State](#put_state)(WEBVIEW2_PERMISSION_STATE value)</span></span>

#### <span data-ttu-id="1da62-140">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="1da62-140">GetDeferral</span></span> 

<span data-ttu-id="1da62-141">可调用 GetDeferral 以返回[IWebView2Deferral](IWebView2Deferral.md)对象。</span><span class="sxs-lookup"><span data-stu-id="1da62-141">GetDeferral can be called to return an [IWebView2Deferral](IWebView2Deferral.md) object.</span></span>

> <span data-ttu-id="1da62-142">公共 HRESULT [GetDeferral](#getdeferral)（[IWebView2Deferral](IWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="1da62-142">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="1da62-143">开发人员可以使用延迟对象在以后的时间做出权限决定。</span><span class="sxs-lookup"><span data-stu-id="1da62-143">Developer can use the deferral object to make the permission decision at a later time.</span></span>

