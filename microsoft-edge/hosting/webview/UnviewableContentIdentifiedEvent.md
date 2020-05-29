---
description: 指示 web 视图正在尝试下载不受支持的文件。
title: UnviewableContentIdentifiedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/25/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: cec85ca2d5458a05cfd88210907523f25fb4af95
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562558"
---
# <span data-ttu-id="aad61-104">UnviewableContentIdentifiedEvent 对象</span><span class="sxs-lookup"><span data-stu-id="aad61-104">UnviewableContentIdentifiedEvent object</span></span>

<span data-ttu-id="aad61-105">指示[web 视图](../webview.md)正在尝试导航到不受支持的内容类型的文件。</span><span class="sxs-lookup"><span data-stu-id="aad61-105">Indicates the [webview](../webview.md) is attempting to navigate to a file of an unsupported content type.</span></span> 

## <span data-ttu-id="aad61-106">属性</span><span class="sxs-lookup"><span data-stu-id="aad61-106">Properties</span></span>

### <span data-ttu-id="aad61-107">媒体</span><span class="sxs-lookup"><span data-stu-id="aad61-107">mediaType</span></span>

<span data-ttu-id="aad61-108">获取 unviewable 内容的内容类型。</span><span class="sxs-lookup"><span data-stu-id="aad61-108">Gets the content type of the unviewable content.</span></span>

<span data-ttu-id="aad61-109">此属性是只读的</span><span class="sxs-lookup"><span data-stu-id="aad61-109">This property is read-only</span></span>

```js
var mediaType = UnviewableContentIdentifiedEvent.mediaType;
```

#### <span data-ttu-id="aad61-110">属性值</span><span class="sxs-lookup"><span data-stu-id="aad61-110">Property value</span></span>
<span data-ttu-id="aad61-111">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="aad61-111">Type: **DOMString**</span></span>

### <span data-ttu-id="aad61-112">referer</span><span class="sxs-lookup"><span data-stu-id="aad61-112">referer</span></span>

<span data-ttu-id="aad61-113">[Web 视图](../webview.md)中请求导航的页面的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="aad61-113">The Uniform Resource Identifier (URI) of the page in the [webview](../webview.md) requesting navigation.</span></span>

<span data-ttu-id="aad61-114">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="aad61-114">This property is read-only.</span></span>


```js
var referer = NavigationEventWithReferrer.referer;
```

#### <span data-ttu-id="aad61-115">属性值</span><span class="sxs-lookup"><span data-stu-id="aad61-115">Property value</span></span>
<span data-ttu-id="aad61-116">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="aad61-116">Type: **DOMString**</span></span>

### <span data-ttu-id="aad61-117">uri</span><span class="sxs-lookup"><span data-stu-id="aad61-117">uri</span></span>

<span data-ttu-id="aad61-118">导航的目标的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="aad61-118">The Uniform Resource Identifier (URI) of the destination of the navigation.</span></span>

<span data-ttu-id="aad61-119">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="aad61-119">This property is read-only.</span></span>

```js
var uri = NavigationEventWithReferrer.uri;
```

#### <span data-ttu-id="aad61-120">属性值</span><span class="sxs-lookup"><span data-stu-id="aad61-120">Property value</span></span>
<span data-ttu-id="aad61-121">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="aad61-121">Type: **DOMString**</span></span>
