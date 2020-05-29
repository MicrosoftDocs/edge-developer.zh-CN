---
description: 表示 web 视图进程。
title: MSWebViewProcess 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 7581f6da3a23295180c50f6d41cc282ce998b64e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563035"
---
# <span data-ttu-id="7e86f-104">MSWebViewProcess 对象</span><span class="sxs-lookup"><span data-stu-id="7e86f-104">MSWebViewProcess object</span></span>

<span data-ttu-id="7e86f-105">表示[web 视图](../webview.md)进程。</span><span class="sxs-lookup"><span data-stu-id="7e86f-105">Represents a [webview](../webview.md) process.</span></span>

```js
var wvprocess = new MSWebViewProcess();
```

## <span data-ttu-id="7e86f-106">属性</span><span class="sxs-lookup"><span data-stu-id="7e86f-106">Properties</span></span>

### <span data-ttu-id="7e86f-107">enterpriseId</span><span class="sxs-lookup"><span data-stu-id="7e86f-107">enterpriseId</span></span>

<span data-ttu-id="7e86f-108">流程的企业 ID。</span><span class="sxs-lookup"><span data-stu-id="7e86f-108">The enterprise ID of the process.</span></span>

```js
var enterpriseId = wvprocess.enterpriseId;
```

<span data-ttu-id="7e86f-109">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="7e86f-109">This property is read-only.</span></span>

#### <span data-ttu-id="7e86f-110">属性值</span><span class="sxs-lookup"><span data-stu-id="7e86f-110">Property value</span></span>
<span data-ttu-id="7e86f-111">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="7e86f-111">Type: **DOMString**</span></span>

### <span data-ttu-id="7e86f-112">isPrivateNetworkClientServerCapabilityEnabled</span><span class="sxs-lookup"><span data-stu-id="7e86f-112">isPrivateNetworkClientServerCapabilityEnabled</span></span>

<span data-ttu-id="7e86f-113">获取一个值，该值指示[web 视图](../webview.md)进程是否具有在应用部件清单中启用的*专用网络（客户端 & 服务器）* 通用 Windows[应用功能声明](/windows/uwp/packaging/app-capability-declarations)。</span><span class="sxs-lookup"><span data-stu-id="7e86f-113">Gets a value indicating whether the [webview](../webview.md) process has the *Private Networks (Client & Server)* Universal Windows [App capability declaration](/windows/uwp/packaging/app-capability-declarations) enabled in the app manifest.</span></span>

```js
var privateNetwork = wvprocess.isPrivateNetworkClientServerCapabilityEnabled;
```

<span data-ttu-id="7e86f-114">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="7e86f-114">This property is read-only.</span></span>

#### <span data-ttu-id="7e86f-115">属性值</span><span class="sxs-lookup"><span data-stu-id="7e86f-115">Property value</span></span>
<span data-ttu-id="7e86f-116">类型： **Boolean**</span><span class="sxs-lookup"><span data-stu-id="7e86f-116">Type: **Boolean**</span></span>

## <span data-ttu-id="7e86f-117">方法</span><span class="sxs-lookup"><span data-stu-id="7e86f-117">Methods</span></span>

### <span data-ttu-id="7e86f-118">CreateWebViewAsync</span><span class="sxs-lookup"><span data-stu-id="7e86f-118">CreateWebViewAsync</span></span>

<span data-ttu-id="7e86f-119">在特定进程中创建[web 视图](../webview.md)。</span><span class="sxs-lookup"><span data-stu-id="7e86f-119">Creates a [webview](../webview.md) in a specific process.</span></span>

```js
wvprocess.createWebviewAsync();
```

#### <span data-ttu-id="7e86f-120">返回值</span><span class="sxs-lookup"><span data-stu-id="7e86f-120">Return value</span></span>

<span data-ttu-id="7e86f-121">处理器类型**`Promise<MSHTMLWebViewElement>`**</span><span class="sxs-lookup"><span data-stu-id="7e86f-121">Type: **`Promise<MSHTMLWebViewElement>`**</span></span>

### <span data-ttu-id="7e86f-122">GetWebViews</span><span class="sxs-lookup"><span data-stu-id="7e86f-122">GetWebViews</span></span>

<span data-ttu-id="7e86f-123">返回进程中托管的**MSWebViewProcess**对象序列。</span><span class="sxs-lookup"><span data-stu-id="7e86f-123">Returns a sequence of **MSWebViewProcess** objects hosted within the process.</span></span>

#### <span data-ttu-id="7e86f-124">返回值</span><span class="sxs-lookup"><span data-stu-id="7e86f-124">Return value</span></span>

<span data-ttu-id="7e86f-125">处理器类型**`sequence<MSHTMLWebViewElement>`**</span><span class="sxs-lookup"><span data-stu-id="7e86f-125">Type: **`sequence<MSHTMLWebViewElement>`**</span></span>

### <span data-ttu-id="7e86f-126">Terminate</span><span class="sxs-lookup"><span data-stu-id="7e86f-126">Terminate</span></span>

<span data-ttu-id="7e86f-127">终止进程。</span><span class="sxs-lookup"><span data-stu-id="7e86f-127">Terminates the process.</span></span>

```js
wvprocess.terminate();
```

#### <span data-ttu-id="7e86f-128">返回值</span><span class="sxs-lookup"><span data-stu-id="7e86f-128">Return value</span></span>

<span data-ttu-id="7e86f-129">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="7e86f-129">This method does not return a value.</span></span>
