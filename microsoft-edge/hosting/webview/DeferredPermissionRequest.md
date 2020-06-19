---
description: 表示对访问设备功能的用户权限的延迟请求
title: DeferredPermissionRequest 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: dc1f0753f879f511fdc380c806eb88b6be358016
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752137"
---
# <span data-ttu-id="8fa30-104">DeferredPermissionRequest 对象</span><span class="sxs-lookup"><span data-stu-id="8fa30-104">DeferredPermissionRequest object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="8fa30-105">表示由[web 视图](../webview.md)内容的延迟请求，用于最终用户访问专用设备功能（如地理位置或指针锁定）。</span><span class="sxs-lookup"><span data-stu-id="8fa30-105">Represents a deferred request by the content of the [webview](../webview.md) for end-user permission to access specialized device functionality (such as geolocation, or pointer lock).</span></span>  

```javascript
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

## <span data-ttu-id="8fa30-106">方法</span><span class="sxs-lookup"><span data-stu-id="8fa30-106">Methods</span></span>  

### <span data-ttu-id="8fa30-107">帮助</span><span class="sxs-lookup"><span data-stu-id="8fa30-107">allow</span></span>  

<span data-ttu-id="8fa30-108">允许请求权限。</span><span class="sxs-lookup"><span data-stu-id="8fa30-108">Allows the request for permission.</span></span>  

```javascript
deferredPermissionRequest.allow();
```  

#### <span data-ttu-id="8fa30-109">参数</span><span class="sxs-lookup"><span data-stu-id="8fa30-109">Parameters</span></span>  

<span data-ttu-id="8fa30-110">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="8fa30-110">This method has no parameters.</span></span>  

#### <span data-ttu-id="8fa30-111">返回值</span><span class="sxs-lookup"><span data-stu-id="8fa30-111">Return value</span></span>  

<span data-ttu-id="8fa30-112">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="8fa30-112">This method does not return a value.</span></span>  

### <span data-ttu-id="8fa30-113">拒绝</span><span class="sxs-lookup"><span data-stu-id="8fa30-113">deny</span></span>  

<span data-ttu-id="8fa30-114">拒绝请求权限。</span><span class="sxs-lookup"><span data-stu-id="8fa30-114">Denies the request for permission.</span></span>  

```javascript
deferredPermissionRequest.deny();
```  

#### <span data-ttu-id="8fa30-115">参数</span><span class="sxs-lookup"><span data-stu-id="8fa30-115">Parameters</span></span>  

<span data-ttu-id="8fa30-116">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="8fa30-116">This method has no parameters.</span></span>  

#### <span data-ttu-id="8fa30-117">返回值</span><span class="sxs-lookup"><span data-stu-id="8fa30-117">Return value</span></span>  

<span data-ttu-id="8fa30-118">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="8fa30-118">This method does not return a value.</span></span>  

## <span data-ttu-id="8fa30-119">属性</span><span class="sxs-lookup"><span data-stu-id="8fa30-119">Properties</span></span>  

### <span data-ttu-id="8fa30-120">id</span><span class="sxs-lookup"><span data-stu-id="8fa30-120">id</span></span>  

<span data-ttu-id="8fa30-121">可用于将当前 DeferredPermissionRequest 与 PermissionRequest 对象的唯一 ID 与上一个 MSWebViewPermissionRequested 事件关联。</span><span class="sxs-lookup"><span data-stu-id="8fa30-121">A unique ID that can be used to correlate the current DeferredPermissionRequest with a PermissionRequest object from a previous MSWebViewPermissionRequested event.</span></span> <span data-ttu-id="8fa30-122">请参阅**webview.permissionrequested**方法。</span><span class="sxs-lookup"><span data-stu-id="8fa30-122">See the **PermissionRequested.defer** method.</span></span>  

<span data-ttu-id="8fa30-123">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="8fa30-123">This property is read-only.</span></span>  

```javascript
var id = deferredPermissionRequest.id;
```  

##### <span data-ttu-id="8fa30-124">属性值</span><span class="sxs-lookup"><span data-stu-id="8fa30-124">Property value</span></span>  

<span data-ttu-id="8fa30-125">类型：**无符号长**</span><span class="sxs-lookup"><span data-stu-id="8fa30-125">Type: **Unsigned long**</span></span>  

### <span data-ttu-id="8fa30-126">类型</span><span class="sxs-lookup"><span data-stu-id="8fa30-126">type</span></span>  

<span data-ttu-id="8fa30-127">所请求的权限类型。</span><span class="sxs-lookup"><span data-stu-id="8fa30-127">The type of permission being requested.</span></span> <span data-ttu-id="8fa30-128">这可以是以下字符串值之一：</span><span class="sxs-lookup"><span data-stu-id="8fa30-128">This may be one of the following string values:</span></span>  

*   <span data-ttu-id="8fa30-129">**地理位置**：通过 "navigator" 作为地理位置访问位置数据。</span><span class="sxs-lookup"><span data-stu-id="8fa30-129">**geolocation**: access to location data via navigator.geolocation.</span></span>  
*   <span data-ttu-id="8fa30-130">**unlimitedIndexedDBQuota**：允许 IndexedDB api 忽略常用的存储数据大小限制。</span><span class="sxs-lookup"><span data-stu-id="8fa30-130">**unlimitedIndexedDBQuota**: allow IndexedDB APIs to ignore the usual stored data size limit.</span></span>  
*   <span data-ttu-id="8fa30-131">**媒体**：通过 getUserMedia 访问麦克风和相机。</span><span class="sxs-lookup"><span data-stu-id="8fa30-131">**media**: access to the microphone and camera via navigator.getUserMedia.</span></span>  
*   <span data-ttu-id="8fa30-132">**pointerlock**：能够通过 requestPointerLock 元素锁定和控制鼠标指针。</span><span class="sxs-lookup"><span data-stu-id="8fa30-132">**pointerlock**: ability to lock and control the mouse pointer via Element.requestPointerLock.</span></span>  
*   <span data-ttu-id="8fa30-133">**webnotifications**：通过窗口显示桌面通知的功能。通告.</span><span class="sxs-lookup"><span data-stu-id="8fa30-133">**webnotifications**: ability to show desktop notifications via window.Notification.</span></span>  
*   <span data-ttu-id="8fa30-134">**屏幕**：能够通过媒体捕获 API 拍摄屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="8fa30-134">**screen**: ability to take screen shots via the Media Capture API.</span></span>  
*   <span data-ttu-id="8fa30-135">**immersiveview**：能够控制 VR 显示。</span><span class="sxs-lookup"><span data-stu-id="8fa30-135">**immersiveview**: ability to control a VR display.</span></span>  

<span data-ttu-id="8fa30-136">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="8fa30-136">This property is read-only.</span></span>  

```javascript
var type = deferredPermissionRequest.type;
```  

#### <span data-ttu-id="8fa30-137">属性值</span><span class="sxs-lookup"><span data-stu-id="8fa30-137">Property value</span></span>  

<span data-ttu-id="8fa30-138">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="8fa30-138">Type: **String**</span></span>  

### <span data-ttu-id="8fa30-139">uri</span><span class="sxs-lookup"><span data-stu-id="8fa30-139">uri</span></span>  

<span data-ttu-id="8fa30-140">请求权限的文档的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="8fa30-140">The Uniform Resource Identifier (URI) of the document requesting permission.</span></span>  

<span data-ttu-id="8fa30-141">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="8fa30-141">This property is read-only.</span></span>  

```javascript
var uri = deferredPermissionRequest.uri;
```  

##### <span data-ttu-id="8fa30-142">属性值</span><span class="sxs-lookup"><span data-stu-id="8fa30-142">Property value</span></span>  

<span data-ttu-id="8fa30-143">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="8fa30-143">Type: **String**</span></span>  

## <span data-ttu-id="8fa30-144">要求</span><span class="sxs-lookup"><span data-stu-id="8fa30-144">Requirements</span></span>  

|  |  |  
|:--- |:--- |  
| **<span data-ttu-id="8fa30-145">最低受支持的客户端</span><span class="sxs-lookup"><span data-stu-id="8fa30-145">Minimum supported client</span></span>** | <span data-ttu-id="8fa30-146">Windows 10 [仅限 Windows 应用商店应用]</span><span class="sxs-lookup"><span data-stu-id="8fa30-146">Windows 10 [Windows Store apps only]</span></span> |  
| **<span data-ttu-id="8fa30-147">最低受支持的服务器</span><span class="sxs-lookup"><span data-stu-id="8fa30-147">Minimum supported server</span></span>** | <span data-ttu-id="8fa30-148">不支持</span><span class="sxs-lookup"><span data-stu-id="8fa30-148">Not supported</span></span> |  
| **<span data-ttu-id="8fa30-149">最低受支持的电话</span><span class="sxs-lookup"><span data-stu-id="8fa30-149">Minimum supported phone</span></span>** | <span data-ttu-id="8fa30-150">不支持</span><span class="sxs-lookup"><span data-stu-id="8fa30-150">Not supported</span></span> |  
