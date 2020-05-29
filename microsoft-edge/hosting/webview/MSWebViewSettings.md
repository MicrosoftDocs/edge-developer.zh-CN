---
description: 定义启用或禁用 web 视图功能的属性
title: MSWebViewSettings 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/10/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 0e164e7eb44edc636201f283ec4bbe866a122b8e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563033"
---
# <span data-ttu-id="dd64b-104">MSWebViewSettings 对象</span><span class="sxs-lookup"><span data-stu-id="dd64b-104">MSWebViewSettings object</span></span>

<span data-ttu-id="dd64b-105">定义启用或禁用[web 视图](../webview.md)功能的属性。</span><span class="sxs-lookup"><span data-stu-id="dd64b-105">Defines properties that enable or disable [webview](../webview.md) features.</span></span>

## <span data-ttu-id="dd64b-106">属性</span><span class="sxs-lookup"><span data-stu-id="dd64b-106">Properties</span></span>

### <span data-ttu-id="dd64b-107">isIndexedDBEnabled</span><span class="sxs-lookup"><span data-stu-id="dd64b-107">isIndexedDBEnabled</span></span>

<span data-ttu-id="dd64b-108">获取或设置一个值，该值指示[web 视图](../webview.md)中是否允许使用 IndexedDB。</span><span class="sxs-lookup"><span data-stu-id="dd64b-108">Gets or sets a value that indicates whether the use of IndexedDB is allowed in the [webview](../webview.md).</span></span>

```js
var isIndexedDBEnabled = MSWebViewSettings.isIndexedDBEnabled;
MSWebViewSettings.isIndexedDBEnabled = isIndexedDBEnabled;
```

#### <span data-ttu-id="dd64b-109">属性值</span><span class="sxs-lookup"><span data-stu-id="dd64b-109">Property value</span></span>
<span data-ttu-id="dd64b-110">类型： **boolean**</span><span class="sxs-lookup"><span data-stu-id="dd64b-110">Type: **boolean**</span></span>

<span data-ttu-id="dd64b-111">如果在**web 视图**中允许 IndexedDB，**则为 True** ;否则**为 false**。</span><span class="sxs-lookup"><span data-stu-id="dd64b-111">**True** if IndexedDB is allowed in the **webview**; otherwise, **false**.</span></span> 

### <span data-ttu-id="dd64b-112">isJavaScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="dd64b-112">isJavaScriptEnabled</span></span>

<span data-ttu-id="dd64b-113">获取或设置一个值，该值指示[web 视图](../webview.md)中是否允许使用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="dd64b-113">Gets or sets a value that indicates whether the use of JavaScript is allowed in the [webview](../webview.md).</span></span>

```js
var isJavaScriptEnabled = MSWebViewSettings.isJavaScriptEnabled;
MSWebViewSettings.isJavaScriptEnabled = isJavaScriptEnabled;
```

#### <span data-ttu-id="dd64b-114">属性值</span><span class="sxs-lookup"><span data-stu-id="dd64b-114">Property value</span></span>
<span data-ttu-id="dd64b-115">类型： **boolean**</span><span class="sxs-lookup"><span data-stu-id="dd64b-115">Type: **boolean**</span></span>

<span data-ttu-id="dd64b-116">**True**在[web 视图](../webview.md)中允许使用 JavaScript;否则**为 false**。</span><span class="sxs-lookup"><span data-stu-id="dd64b-116">**True** JavaScript is allowed in the [webview](../webview.md); otherwise, **false**.</span></span> 

### <span data-ttu-id="dd64b-117">isScriptNotifyAllowed</span><span class="sxs-lookup"><span data-stu-id="dd64b-117">isScriptNotifyAllowed</span></span>

<span data-ttu-id="dd64b-118">获取或设置一个值，该值指示[web 视图](../webview.md)中是否允许使用[ScriptNotifyEvent](ScriptNotifyEvent.md) 。</span><span class="sxs-lookup"><span data-stu-id="dd64b-118">Gets or sets a value that indicates whether the use of [ScriptNotifyEvent](ScriptNotifyEvent.md) is allowed in the [webview](../webview.md).</span></span>

```js
var isScriptNotifyAllowed = MSWebViewSettings.isScriptNotifyAllowed;
MSWebViewSettings.isScriptNotifyAllowed = isScriptNotifyAllowed;
```

#### <span data-ttu-id="dd64b-119">属性值</span><span class="sxs-lookup"><span data-stu-id="dd64b-119">Property value</span></span>
<span data-ttu-id="dd64b-120">类型： **boolean**</span><span class="sxs-lookup"><span data-stu-id="dd64b-120">Type: **boolean**</span></span>

<span data-ttu-id="dd64b-121">在[web 视图](../webview.md)中允许使用**True** [ScriptNotifyEvent](ScriptNotifyEvent.md) ;否则**为 false**。</span><span class="sxs-lookup"><span data-stu-id="dd64b-121">**True** [ScriptNotifyEvent](ScriptNotifyEvent.md) is allowed in the [webview](../webview.md); otherwise, **false**.</span></span> 
