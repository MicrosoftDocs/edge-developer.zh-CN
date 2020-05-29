---
description: 表示对访问设备功能的用户权限的延迟请求
title: DeferredPermissionRequest 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/15/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 6013f20195fc0f5d4f33b871a9c1b01392bf023e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563045"
---
# <span data-ttu-id="9d211-104">DeferredPermissionRequest 对象</span><span class="sxs-lookup"><span data-stu-id="9d211-104">DeferredPermissionRequest object</span></span>

<span data-ttu-id="9d211-105">表示由[web 视图](../webview.md)内容的延迟请求，用于最终用户访问专用设备功能（如地理位置或指针锁定）。</span><span class="sxs-lookup"><span data-stu-id="9d211-105">Represents a deferred request by the content of the [webview](../webview.md) for end-user permission to access specialized device functionality (such as geolocation, or pointer lock).</span></span>

```js
// In this sample, when we receive a permission request we construct some basic UI to ask the
// user if they want to give permission.
webview.addEventListener("MSWebViewPermissionRequested", permissionRequestedEventArgs => {
    const permissionRequest = permissionRequestedEventArgs.permissionRequest;
    const requestContainer = document.createElement("div");

    // We use this function as the handler for the allow and deny buttons.
    function completeDeferredPermissionRequest(allow) {
        // Find the DeferredPermissionRequest using the id of the PermissionRequest we deferred.
        const deferredPermissionRequest = webview.getDeferredPermissionRequestById(permissionRequest.id);
        if (allow) {
            deferredPermissionRequest.allow();
        }
        else {
            deferredPermissionRequest.deny();
        }
        requestContainer.parentElement.removeChild(requestContainer);
    }

    // Construct some simple UI to tell the user about the permission request and get their
    // feedback via the allow and deny buttons
    const description = document.createElement("span");
    description.textContent = "Allow " + uri + " to access " + type + "?";

    const allow = document.createElement("button");
    allow.textContent = "Allow";
    allow.addEventListener("click", () => completeDeferredPermissionRequest(true));

    const deny = document.createElement("button");
    deny.textContent = "Deny";
    deny.addEventListener("click", () => completeDeferredPermissionRequest(false));

    requestContainer.appendChild(description);
    requestContainer.appendChild(allow);
    requestContainer.appendChild(deny);
    document.body.appendChild(requestContainer);

    permissionRequest.defer();
});
```

## <span data-ttu-id="9d211-106">方法</span><span class="sxs-lookup"><span data-stu-id="9d211-106">Methods</span></span>

### <span data-ttu-id="9d211-107">帮助</span><span class="sxs-lookup"><span data-stu-id="9d211-107">allow</span></span>

<span data-ttu-id="9d211-108">允许请求权限。</span><span class="sxs-lookup"><span data-stu-id="9d211-108">Allows the request for permission.</span></span>

```js
deferredPermissionRequest.allow();
```

#### <span data-ttu-id="9d211-109">参数</span><span class="sxs-lookup"><span data-stu-id="9d211-109">Parameters</span></span>

<span data-ttu-id="9d211-110">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="9d211-110">This method has no parameters.</span></span>

#### <span data-ttu-id="9d211-111">返回值</span><span class="sxs-lookup"><span data-stu-id="9d211-111">Return value</span></span>

<span data-ttu-id="9d211-112">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="9d211-112">This method does not return a value.</span></span>

### <span data-ttu-id="9d211-113">拒绝</span><span class="sxs-lookup"><span data-stu-id="9d211-113">deny</span></span>

<span data-ttu-id="9d211-114">拒绝请求权限。</span><span class="sxs-lookup"><span data-stu-id="9d211-114">Denies the request for permission.</span></span>

```js
deferredPermissionRequest.deny();
```

#### <span data-ttu-id="9d211-115">参数</span><span class="sxs-lookup"><span data-stu-id="9d211-115">Parameters</span></span>

<span data-ttu-id="9d211-116">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="9d211-116">This method has no parameters.</span></span>

#### <span data-ttu-id="9d211-117">返回值</span><span class="sxs-lookup"><span data-stu-id="9d211-117">Return value</span></span>

<span data-ttu-id="9d211-118">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="9d211-118">This method does not return a value.</span></span>

## <span data-ttu-id="9d211-119">属性</span><span class="sxs-lookup"><span data-stu-id="9d211-119">Properties</span></span>

### <span data-ttu-id="9d211-120">id</span><span class="sxs-lookup"><span data-stu-id="9d211-120">id</span></span>

<span data-ttu-id="9d211-121">可用于将当前 DeferredPermissionRequest 与 PermissionRequest 对象的唯一 ID 与上一个 MSWebViewPermissionRequested 事件关联。</span><span class="sxs-lookup"><span data-stu-id="9d211-121">A unique ID that can be used to correlate the current DeferredPermissionRequest with a PermissionRequest object from a previous MSWebViewPermissionRequested event.</span></span> <span data-ttu-id="9d211-122">请参阅**webview.permissionrequested**方法。</span><span class="sxs-lookup"><span data-stu-id="9d211-122">See the **PermissionRequested.defer** method.</span></span>

<span data-ttu-id="9d211-123">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="9d211-123">This property is read-only.</span></span>

```js
var id = deferredPermissionRequest.id;
```

##### <span data-ttu-id="9d211-124">属性值</span><span class="sxs-lookup"><span data-stu-id="9d211-124">Property value</span></span>

<span data-ttu-id="9d211-125">类型：**无符号长**</span><span class="sxs-lookup"><span data-stu-id="9d211-125">Type: **Unsigned long**</span></span>

### <span data-ttu-id="9d211-126">类型</span><span class="sxs-lookup"><span data-stu-id="9d211-126">type</span></span>

<span data-ttu-id="9d211-127">所请求的权限类型。</span><span class="sxs-lookup"><span data-stu-id="9d211-127">The type of permission being requested.</span></span> <span data-ttu-id="9d211-128">这可以是以下字符串值之一：</span><span class="sxs-lookup"><span data-stu-id="9d211-128">This may be one of the following string values:</span></span>

- <span data-ttu-id="9d211-129">**地理位置**：通过 "navigator" 作为地理位置访问位置数据。</span><span class="sxs-lookup"><span data-stu-id="9d211-129">**geolocation**: access to location data via navigator.geolocation.</span></span>
- <span data-ttu-id="9d211-130">**unlimitedIndexedDBQuota**：允许 IndexedDB api 忽略常用的存储数据大小限制。</span><span class="sxs-lookup"><span data-stu-id="9d211-130">**unlimitedIndexedDBQuota**: allow IndexedDB APIs to ignore the usual stored data size limit.</span></span>
- <span data-ttu-id="9d211-131">**媒体**：通过 getUserMedia 访问麦克风和相机。</span><span class="sxs-lookup"><span data-stu-id="9d211-131">**media**: access to the microphone and camera via navigator.getUserMedia.</span></span>
- <span data-ttu-id="9d211-132">**pointerlock**：能够通过 requestPointerLock 元素锁定和控制鼠标指针。</span><span class="sxs-lookup"><span data-stu-id="9d211-132">**pointerlock**: ability to lock and control the mouse pointer via Element.requestPointerLock.</span></span>
- <span data-ttu-id="9d211-133">**webnotifications**：通过窗口显示桌面通知的功能。通告.</span><span class="sxs-lookup"><span data-stu-id="9d211-133">**webnotifications**: ability to show desktop notifications via window.Notification.</span></span>
- <span data-ttu-id="9d211-134">**屏幕**：能够通过媒体捕获 API 拍摄屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="9d211-134">**screen**: ability to take screen shots via the Media Capture API.</span></span>
- <span data-ttu-id="9d211-135">**immersiveview**：能够控制 VR 显示。</span><span class="sxs-lookup"><span data-stu-id="9d211-135">**immersiveview**: ability to control a VR display.</span></span>

<span data-ttu-id="9d211-136">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="9d211-136">This property is read-only.</span></span>

```js
var type = deferredPermissionRequest.type;
```

#### <span data-ttu-id="9d211-137">属性值</span><span class="sxs-lookup"><span data-stu-id="9d211-137">Property value</span></span>

<span data-ttu-id="9d211-138">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="9d211-138">Type: **String**</span></span>

### <span data-ttu-id="9d211-139">uri</span><span class="sxs-lookup"><span data-stu-id="9d211-139">uri</span></span>

<span data-ttu-id="9d211-140">请求权限的文档的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="9d211-140">The Uniform Resource Identifier (URI) of the document requesting permission.</span></span>

<span data-ttu-id="9d211-141">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="9d211-141">This property is read-only.</span></span>

```js
var uri = deferredPermissionRequest.uri;
```

##### <span data-ttu-id="9d211-142">属性值</span><span class="sxs-lookup"><span data-stu-id="9d211-142">Property value</span></span>

<span data-ttu-id="9d211-143">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="9d211-143">Type: **String**</span></span>

## <span data-ttu-id="9d211-144">要求</span><span class="sxs-lookup"><span data-stu-id="9d211-144">Requirements</span></span>

|                                           |                                      |
|-------------------------------------------|--------------------------------------|
| <strong><span data-ttu-id="9d211-145">最低受支持的客户端</span><span class="sxs-lookup"><span data-stu-id="9d211-145">Minimum supported client</span></span></strong> | <span data-ttu-id="9d211-146">Windows 10 [仅限 Windows 应用商店应用]</span><span class="sxs-lookup"><span data-stu-id="9d211-146">Windows 10 [Windows Store apps only]</span></span> |
| <strong><span data-ttu-id="9d211-147">最低受支持的服务器</span><span class="sxs-lookup"><span data-stu-id="9d211-147">Minimum supported server</span></span></strong> |            <span data-ttu-id="9d211-148">不支持</span><span class="sxs-lookup"><span data-stu-id="9d211-148">Not supported</span></span>             |
| <strong><span data-ttu-id="9d211-149">最低受支持的电话</span><span class="sxs-lookup"><span data-stu-id="9d211-149">Minimum supported phone</span></span></strong>  |            <span data-ttu-id="9d211-150">不支持</span><span class="sxs-lookup"><span data-stu-id="9d211-150">Not supported</span></span>             |
