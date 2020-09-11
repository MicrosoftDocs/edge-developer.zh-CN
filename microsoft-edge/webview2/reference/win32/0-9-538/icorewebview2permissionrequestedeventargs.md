---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2PermissionRequestedEventArgs
ms.openlocfilehash: 4abb6fb058765a05ebb32fe97474348c4aebde12
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010031"
---
# <span data-ttu-id="45bbb-104">0.9.579-接口 ICoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="45bbb-104">0.9.579 - interface ICoreWebView2PermissionRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="45bbb-105">Webview.permissionrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="45bbb-105">Event args for the PermissionRequested event.</span></span>

## <span data-ttu-id="45bbb-106">摘要</span><span class="sxs-lookup"><span data-stu-id="45bbb-106">Summary</span></span>

 <span data-ttu-id="45bbb-107">成员</span><span class="sxs-lookup"><span data-stu-id="45bbb-107">Members</span></span>                        | <span data-ttu-id="45bbb-108">描述</span><span class="sxs-lookup"><span data-stu-id="45bbb-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="45bbb-109">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="45bbb-109">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="45bbb-110">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="45bbb-110">True when the permission request was initiated through a user gesture.</span></span>
[<span data-ttu-id="45bbb-111">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="45bbb-111">get_PermissionKind</span></span>](#get_permissionkind) | <span data-ttu-id="45bbb-112">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="45bbb-112">The type of the permission that is requested.</span></span>
[<span data-ttu-id="45bbb-113">get_State</span><span class="sxs-lookup"><span data-stu-id="45bbb-113">get_State</span></span>](#get_state) | <span data-ttu-id="45bbb-114">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="45bbb-114">The status of a permission request, i.e.</span></span>
[<span data-ttu-id="45bbb-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="45bbb-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="45bbb-116">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="45bbb-116">The origin of the web content that requests the permission.</span></span>
[<span data-ttu-id="45bbb-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="45bbb-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="45bbb-118">可调用 GetDeferral 以返回 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="45bbb-118">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>
[<span data-ttu-id="45bbb-119">put_State</span><span class="sxs-lookup"><span data-stu-id="45bbb-119">put_State</span></span>](#put_state) | <span data-ttu-id="45bbb-120">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="45bbb-120">Set the State property.</span></span>

## <span data-ttu-id="45bbb-121">成员</span><span class="sxs-lookup"><span data-stu-id="45bbb-121">Members</span></span>

#### <span data-ttu-id="45bbb-122">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="45bbb-122">get_IsUserInitiated</span></span> 

<span data-ttu-id="45bbb-123">当权限请求通过用户手势启动时为 True。</span><span class="sxs-lookup"><span data-stu-id="45bbb-123">True when the permission request was initiated through a user gesture.</span></span>

> <span data-ttu-id="45bbb-124">公共 HRESULT [get_IsUserInitiated](#get_isuserinitiated) (BOOL \* IsUserInitiated) </span><span class="sxs-lookup"><span data-stu-id="45bbb-124">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="45bbb-125">注意，通过用户手势启动并不意味着用户打算访问关联的资源。</span><span class="sxs-lookup"><span data-stu-id="45bbb-125">Note that being initiated through a user gesture doesn't mean that user intended to access the associated resource.</span></span>

#### <span data-ttu-id="45bbb-126">get_PermissionKind</span><span class="sxs-lookup"><span data-stu-id="45bbb-126">get_PermissionKind</span></span> 

<span data-ttu-id="45bbb-127">所请求权限的类型。</span><span class="sxs-lookup"><span data-stu-id="45bbb-127">The type of the permission that is requested.</span></span>

> <span data-ttu-id="45bbb-128">public HRESULT [get_PermissionKind](#get_permissionkind) (COREWEBVIEW2_PERMISSION_KIND \* 值) </span><span class="sxs-lookup"><span data-stu-id="45bbb-128">public HRESULT [get_PermissionKind](#get_permissionkind)(COREWEBVIEW2_PERMISSION_KIND \* value)</span></span>

#### <span data-ttu-id="45bbb-129">get_State</span><span class="sxs-lookup"><span data-stu-id="45bbb-129">get_State</span></span> 

<span data-ttu-id="45bbb-130">权限请求的状态，即</span><span class="sxs-lookup"><span data-stu-id="45bbb-130">The status of a permission request, i.e.</span></span>

> <span data-ttu-id="45bbb-131">public HRESULT [get_State](#get_state) (COREWEBVIEW2_PERMISSION_STATE \* 值) </span><span class="sxs-lookup"><span data-stu-id="45bbb-131">public HRESULT [get_State](#get_state)(COREWEBVIEW2_PERMISSION_STATE \* value)</span></span>

<span data-ttu-id="45bbb-132">是否授予请求。</span><span class="sxs-lookup"><span data-stu-id="45bbb-132">whether the request is granted.</span></span> <span data-ttu-id="45bbb-133">默认值为 COREWEBVIEW2_PERMISSION_STATE_DEFAULT。</span><span class="sxs-lookup"><span data-stu-id="45bbb-133">Default value is COREWEBVIEW2_PERMISSION_STATE_DEFAULT.</span></span>

#### <span data-ttu-id="45bbb-134">get_Uri</span><span class="sxs-lookup"><span data-stu-id="45bbb-134">get_Uri</span></span> 

<span data-ttu-id="45bbb-135">请求权限的 web 内容的来源。</span><span class="sxs-lookup"><span data-stu-id="45bbb-135">The origin of the web content that requests the permission.</span></span>

> <span data-ttu-id="45bbb-136">公共 HRESULT [get_Uri](#get_uri) (LPWSTR \* Uri) </span><span class="sxs-lookup"><span data-stu-id="45bbb-136">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="45bbb-137">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="45bbb-137">GetDeferral</span></span> 

<span data-ttu-id="45bbb-138">可调用 GetDeferral 以返回 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象。</span><span class="sxs-lookup"><span data-stu-id="45bbb-138">GetDeferral can be called to return an [ICoreWebView2Deferral](icorewebview2deferral.md) object.</span></span>

> <span data-ttu-id="45bbb-139">公共 HRESULT [GetDeferral](#getdeferral) ([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期) </span><span class="sxs-lookup"><span data-stu-id="45bbb-139">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="45bbb-140">开发人员可以使用延迟对象在以后的时间做出权限决定。</span><span class="sxs-lookup"><span data-stu-id="45bbb-140">Developer can use the deferral object to make the permission decision at a later time.</span></span>

#### <span data-ttu-id="45bbb-141">put_State</span><span class="sxs-lookup"><span data-stu-id="45bbb-141">put_State</span></span> 

<span data-ttu-id="45bbb-142">设置 State 属性。</span><span class="sxs-lookup"><span data-stu-id="45bbb-142">Set the State property.</span></span>

> <span data-ttu-id="45bbb-143">public HRESULT [put_State](#put_state) (COREWEBVIEW2_PERMISSION_STATE 值) </span><span class="sxs-lookup"><span data-stu-id="45bbb-143">public HRESULT [put_State](#put_state)(COREWEBVIEW2_PERMISSION_STATE value)</span></span>

