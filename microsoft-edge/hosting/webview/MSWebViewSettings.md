---
description: 定义启用或禁用 web 视图功能的属性
title: MSWebViewSettings 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 147f852f8fbcb2a748c00b472814e9cc45b9c9da
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752176"
---
# <span data-ttu-id="e855e-104">MSWebViewSettings 对象</span><span class="sxs-lookup"><span data-stu-id="e855e-104">MSWebViewSettings object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="e855e-105">定义启用或禁用[web 视图](../webview.md)功能的属性。</span><span class="sxs-lookup"><span data-stu-id="e855e-105">Defines properties that enable or disable [webview](../webview.md) features.</span></span>  

## <span data-ttu-id="e855e-106">属性</span><span class="sxs-lookup"><span data-stu-id="e855e-106">Properties</span></span>  

### <span data-ttu-id="e855e-107">isIndexedDBEnabled</span><span class="sxs-lookup"><span data-stu-id="e855e-107">isIndexedDBEnabled</span></span>  

<span data-ttu-id="e855e-108">获取或设置一个值，该值指示[web 视图](../webview.md)中是否允许使用 IndexedDB。</span><span class="sxs-lookup"><span data-stu-id="e855e-108">Gets or sets a value that indicates whether the use of IndexedDB is allowed in the [webview](../webview.md).</span></span>  

```javascript
var isIndexedDBEnabled = MSWebViewSettings.isIndexedDBEnabled;
MSWebViewSettings.isIndexedDBEnabled = isIndexedDBEnabled;
```  

#### <span data-ttu-id="e855e-109">属性值</span><span class="sxs-lookup"><span data-stu-id="e855e-109">Property value</span></span>  

<span data-ttu-id="e855e-110">类型： **boolean**</span><span class="sxs-lookup"><span data-stu-id="e855e-110">Type: **boolean**</span></span>  

<span data-ttu-id="e855e-111">如果在**web 视图**中允许 IndexedDB，**则为 True** ;否则**为 false**。</span><span class="sxs-lookup"><span data-stu-id="e855e-111">**True** if IndexedDB is allowed in the **webview**; otherwise, **false**.</span></span>  

### <span data-ttu-id="e855e-112">isJavaScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="e855e-112">isJavaScriptEnabled</span></span>  

<span data-ttu-id="e855e-113">获取或设置一个值，该值指示[web 视图](../webview.md)中是否允许使用 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="e855e-113">Gets or sets a value that indicates whether the use of JavaScript is allowed in the [webview](../webview.md).</span></span>  

```javascript
var isJavaScriptEnabled = MSWebViewSettings.isJavaScriptEnabled;
MSWebViewSettings.isJavaScriptEnabled = isJavaScriptEnabled;
```  

#### <span data-ttu-id="e855e-114">属性值</span><span class="sxs-lookup"><span data-stu-id="e855e-114">Property value</span></span>  

<span data-ttu-id="e855e-115">类型： **boolean**</span><span class="sxs-lookup"><span data-stu-id="e855e-115">Type: **boolean**</span></span>  

<span data-ttu-id="e855e-116">**True**在[web 视图](../webview.md)中允许使用 JavaScript;否则**为 false**。</span><span class="sxs-lookup"><span data-stu-id="e855e-116">**True** JavaScript is allowed in the [webview](../webview.md); otherwise, **false**.</span></span>  

### <span data-ttu-id="e855e-117">isScriptNotifyAllowed</span><span class="sxs-lookup"><span data-stu-id="e855e-117">isScriptNotifyAllowed</span></span>  

<span data-ttu-id="e855e-118">获取或设置一个值，该值指示[web 视图](../webview.md)中是否允许使用[ScriptNotifyEvent](ScriptNotifyEvent.md) 。</span><span class="sxs-lookup"><span data-stu-id="e855e-118">Gets or sets a value that indicates whether the use of [ScriptNotifyEvent](ScriptNotifyEvent.md) is allowed in the [webview](../webview.md).</span></span>  

```javascript
var isScriptNotifyAllowed = MSWebViewSettings.isScriptNotifyAllowed;
MSWebViewSettings.isScriptNotifyAllowed = isScriptNotifyAllowed;
```  

#### <span data-ttu-id="e855e-119">属性值</span><span class="sxs-lookup"><span data-stu-id="e855e-119">Property value</span></span>  

<span data-ttu-id="e855e-120">类型： **boolean**</span><span class="sxs-lookup"><span data-stu-id="e855e-120">Type: **boolean**</span></span>  

<span data-ttu-id="e855e-121">在[web 视图](../webview.md)中允许使用**True** [ScriptNotifyEvent](ScriptNotifyEvent.md) ;否则**为 false**。</span><span class="sxs-lookup"><span data-stu-id="e855e-121">**True** [ScriptNotifyEvent](ScriptNotifyEvent.md) is allowed in the [webview](../webview.md); otherwise, **false**.</span></span>  
