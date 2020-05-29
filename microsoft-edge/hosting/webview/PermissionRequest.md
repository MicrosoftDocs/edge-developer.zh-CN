---
description: 提供有关权限请求的信息
title: PermissionRequest 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/15/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 023f19170e7b5cdb52a1de9d5d4d7c755c89edbe
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563022"
---
# <span data-ttu-id="2057e-104">PermissionRequest 对象</span><span class="sxs-lookup"><span data-stu-id="2057e-104">PermissionRequest object</span></span>

<span data-ttu-id="2057e-105">提供有关权限请求的信息。</span><span class="sxs-lookup"><span data-stu-id="2057e-105">Provides information about a permission request.</span></span> <span data-ttu-id="2057e-106">此对象可从[MSWebViewPermissionRequested](../webview.md#mswebviewpermissionrequested) web 视图事件中的事件参数的 permissionRequest 属性中获取。</span><span class="sxs-lookup"><span data-stu-id="2057e-106">This object is available from the permissionRequest property of the event args from the [MSWebViewPermissionRequested](../webview.md#mswebviewpermissionrequested) webview event.</span></span>

```js
webview.addEventListener("MSWebViewPermissionRequested", permissionRequestedEventArgs => {
    const permissionRequest = permissionRequestedEventArgs.permissionRequest;
    switch (permissionRequest.type) {
        case "geolocation":
        case "media":
        case "pointerlock":
        case "webnotifications":
        case "screen":
        case "immersiveview":
            if (permissionRequest.uri.startsWith("https://www.example.com/")) {
                // Implicitly trust particular URI
                permissionRequest.allow();
            }
            else if (permissionRequest.uri.startsWith("https://")) {
                // Defer the request so we can ask the user to allow or deny the request
                permissionRequest.defer();
                // Later we'll need to use webview.getDeferredPermissionRequestById for this
                // request and call allow or deny.
                promptUserForDeferredPermissionRequest(
                    permissionRequest.id,
                    permissionRequest.uri,
                    permissionRequest.type);
            }
            else {
                // Implicitly deny non-https URIs
                permissionRequest.deny();
            }
            break;

        case "unlimitedIndexedDBQuota":
        default:
            permissionRequest.deny();
            break;
    }
});
```

## <span data-ttu-id="2057e-107">方法</span><span class="sxs-lookup"><span data-stu-id="2057e-107">Methods</span></span>

### <span data-ttu-id="2057e-108">帮助</span><span class="sxs-lookup"><span data-stu-id="2057e-108">allow</span></span>

<span data-ttu-id="2057e-109">允许请求权限。</span><span class="sxs-lookup"><span data-stu-id="2057e-109">Allows the request for permission.</span></span>

#### <span data-ttu-id="2057e-110">参数</span><span class="sxs-lookup"><span data-stu-id="2057e-110">Parameters</span></span>

<span data-ttu-id="2057e-111">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="2057e-111">This method has no parameters.</span></span>

#### <span data-ttu-id="2057e-112">返回值</span><span class="sxs-lookup"><span data-stu-id="2057e-112">Return value</span></span>

<span data-ttu-id="2057e-113">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="2057e-113">This method does not return a value.</span></span>

### <span data-ttu-id="2057e-114">延迟</span><span class="sxs-lookup"><span data-stu-id="2057e-114">defer</span></span>

<span data-ttu-id="2057e-115">如果不同步允许或禁止 PermissionRequest，则需要时间与用户交互或执行其他异步操作，请在 PermissionRequest 上调用 defer （）。</span><span class="sxs-lookup"><span data-stu-id="2057e-115">If instead of synchronously allowing or disallowing a PermissionRequest, you require time to interact with the user or take some other asynchronous action, call defer() on the PermissionRequest.</span></span> <span data-ttu-id="2057e-116">PermissionRequest 现在将以 DeferredPermissionRequest 的形式提供给 getDeferredPermissionRequests 和 getDeferredPermissionRequestById。</span><span class="sxs-lookup"><span data-stu-id="2057e-116">The PermissionRequest will now be available as a DeferredPermissionRequest from getDeferredPermissionRequests and getDeferredPermissionRequestById.</span></span> <span data-ttu-id="2057e-117">你可以通过 "匹配 id" 属性将当前 PermissionRequest 关联到相应的 DeferredPermissionRequest。</span><span class="sxs-lookup"><span data-stu-id="2057e-117">You can correlate the current PermissionRequest with the corresponding DeferredPermissionRequest via the matching id property.</span></span>

#### <span data-ttu-id="2057e-118">参数</span><span class="sxs-lookup"><span data-stu-id="2057e-118">Parameters</span></span>

<span data-ttu-id="2057e-119">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="2057e-119">This method has no parameters.</span></span>

#### <span data-ttu-id="2057e-120">返回值</span><span class="sxs-lookup"><span data-stu-id="2057e-120">Return value</span></span>

<span data-ttu-id="2057e-121">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="2057e-121">This method does not return a value.</span></span>

### <span data-ttu-id="2057e-122">拒绝</span><span class="sxs-lookup"><span data-stu-id="2057e-122">deny</span></span>

<span data-ttu-id="2057e-123">拒绝请求权限。</span><span class="sxs-lookup"><span data-stu-id="2057e-123">Denies the request for permission.</span></span>

#### <span data-ttu-id="2057e-124">参数</span><span class="sxs-lookup"><span data-stu-id="2057e-124">Parameters</span></span>

<span data-ttu-id="2057e-125">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="2057e-125">This method has no parameters.</span></span>

#### <span data-ttu-id="2057e-126">返回值</span><span class="sxs-lookup"><span data-stu-id="2057e-126">Return value</span></span>

<span data-ttu-id="2057e-127">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="2057e-127">This method does not return a value.</span></span>

## <span data-ttu-id="2057e-128">属性</span><span class="sxs-lookup"><span data-stu-id="2057e-128">Properties</span></span>

### <span data-ttu-id="2057e-129">id</span><span class="sxs-lookup"><span data-stu-id="2057e-129">id</span></span>

<span data-ttu-id="2057e-130">可用于将当前 PermissionRequest 与相应的 DeferredPermissionRequest 关联的唯一 ID （如果使用 defer 方法）。</span><span class="sxs-lookup"><span data-stu-id="2057e-130">A unique ID that can be used to correlate the current PermissionRequest with a corresponding DeferredPermissionRequest if the defer method is used.</span></span> <span data-ttu-id="2057e-131">请参阅 defer 方法。</span><span class="sxs-lookup"><span data-stu-id="2057e-131">See the defer method.</span></span>

<span data-ttu-id="2057e-132">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="2057e-132">This property is read-only.</span></span>

##### <span data-ttu-id="2057e-133">属性值</span><span class="sxs-lookup"><span data-stu-id="2057e-133">Property value</span></span>

<span data-ttu-id="2057e-134">类型：**无符号长**</span><span class="sxs-lookup"><span data-stu-id="2057e-134">Type: **Unsigned long**</span></span>

### <span data-ttu-id="2057e-135">状态</span><span class="sxs-lookup"><span data-stu-id="2057e-135">state</span></span>

<span data-ttu-id="2057e-136">返回 "unknown"、"defer"、"allow" 或 "deny" 以指示权限请求的当前状态。</span><span class="sxs-lookup"><span data-stu-id="2057e-136">Returns "unknown", "defer", "allow", or "deny" to indicate the current state of permission request.</span></span> <span data-ttu-id="2057e-137">如果没有调用任何方法，则状态字符串将对应于 "姓氏"、"拒绝" 或 "推迟" 调用的任何方法。</span><span class="sxs-lookup"><span data-stu-id="2057e-137">The state string will correspond to whichever method allow, deny, or defer was called last or "unknown" if none of the methods have been called.</span></span>

<span data-ttu-id="2057e-138">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="2057e-138">This property is read-only.</span></span>

#### <span data-ttu-id="2057e-139">属性值</span><span class="sxs-lookup"><span data-stu-id="2057e-139">Property value</span></span>

<span data-ttu-id="2057e-140">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="2057e-140">Type: **String**</span></span>

### <span data-ttu-id="2057e-141">类型</span><span class="sxs-lookup"><span data-stu-id="2057e-141">type</span></span>

<span data-ttu-id="2057e-142">所请求的权限类型。</span><span class="sxs-lookup"><span data-stu-id="2057e-142">The type of permission being requested.</span></span> <span data-ttu-id="2057e-143">这可以是以下字符串值之一：</span><span class="sxs-lookup"><span data-stu-id="2057e-143">This may be one of the following string values:</span></span>

- <span data-ttu-id="2057e-144">**地理位置**：通过 "navigator" 作为地理位置访问位置数据。</span><span class="sxs-lookup"><span data-stu-id="2057e-144">**geolocation**: access to location data via navigator.geolocation.</span></span>
- <span data-ttu-id="2057e-145">**unlimitedIndexedDBQuota**：允许 IndexedDB api 忽略常用的存储数据大小限制。</span><span class="sxs-lookup"><span data-stu-id="2057e-145">**unlimitedIndexedDBQuota**: allow IndexedDB APIs to ignore the usual stored data size limit.</span></span>
- <span data-ttu-id="2057e-146">**媒体**：通过 getUserMedia 访问麦克风和相机。</span><span class="sxs-lookup"><span data-stu-id="2057e-146">**media**: access to the microphone and camera via navigator.getUserMedia.</span></span>
- <span data-ttu-id="2057e-147">**pointerlock**：能够通过 requestPointerLock 元素锁定和控制鼠标指针。</span><span class="sxs-lookup"><span data-stu-id="2057e-147">**pointerlock**: ability to lock and control the mouse pointer via Element.requestPointerLock.</span></span>
- <span data-ttu-id="2057e-148">**webnotifications**：通过窗口显示桌面通知的功能。通告.</span><span class="sxs-lookup"><span data-stu-id="2057e-148">**webnotifications**: ability to show desktop notifications via window.Notification.</span></span>
- <span data-ttu-id="2057e-149">**屏幕**：能够通过媒体捕获 API 拍摄屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="2057e-149">**screen**: ability to take screen shots via the Media Capture API.</span></span>
- <span data-ttu-id="2057e-150">**immersiveview**：能够控制 VR 显示。</span><span class="sxs-lookup"><span data-stu-id="2057e-150">**immersiveview**: ability to control a VR display.</span></span>

<span data-ttu-id="2057e-151">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="2057e-151">This property is read-only.</span></span>

#### <span data-ttu-id="2057e-152">属性值</span><span class="sxs-lookup"><span data-stu-id="2057e-152">Property value</span></span>

<span data-ttu-id="2057e-153">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="2057e-153">Type: **String**</span></span>

### <span data-ttu-id="2057e-154">uri</span><span class="sxs-lookup"><span data-stu-id="2057e-154">uri</span></span>

<span data-ttu-id="2057e-155">请求权限的文档的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="2057e-155">The Uniform Resource Identifier (URI) of the document requesting permission.</span></span>

<span data-ttu-id="2057e-156">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="2057e-156">This property is read-only.</span></span>

#### <span data-ttu-id="2057e-157">属性值</span><span class="sxs-lookup"><span data-stu-id="2057e-157">Property value</span></span>

<span data-ttu-id="2057e-158">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="2057e-158">Type: **String**</span></span>
