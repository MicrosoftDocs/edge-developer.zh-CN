---
description: 包含有关导航的引用信息
title: NavigationEventWithReferrer 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/22/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: b11f60724387d996d0a730965602b5ead6a84145
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563026"
---
# <span data-ttu-id="768b3-104">NavigationEventWithReferrer 对象</span><span class="sxs-lookup"><span data-stu-id="768b3-104">NavigationEventWithReferrer object</span></span>

<span data-ttu-id="768b3-105">一个对象，表示在启动导航且导航包含 referer 时激发的事件。</span><span class="sxs-lookup"><span data-stu-id="768b3-105">An object that represents an event fired when navigation is initiated and the navigation contains a referer.</span></span>

## <span data-ttu-id="768b3-106">属性</span><span class="sxs-lookup"><span data-stu-id="768b3-106">Properties</span></span>

### <span data-ttu-id="768b3-107">referer</span><span class="sxs-lookup"><span data-stu-id="768b3-107">referer</span></span>

<span data-ttu-id="768b3-108">[Web 视图](../webview.md)中请求导航的页面的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="768b3-108">The Uniform Resource Identifier (URI) of the page in the [webview](../webview.md) requesting navigation.</span></span>

<span data-ttu-id="768b3-109">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="768b3-109">This property is read-only.</span></span>

#### <span data-ttu-id="768b3-110">属性值</span><span class="sxs-lookup"><span data-stu-id="768b3-110">Property value</span></span>
<span data-ttu-id="768b3-111">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="768b3-111">Type: **DOMString**</span></span>


```js
var referer = NavigationEventWithReferrer.referer;
```

### <span data-ttu-id="768b3-112">uri</span><span class="sxs-lookup"><span data-stu-id="768b3-112">uri</span></span>

<span data-ttu-id="768b3-113">导航的目标的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="768b3-113">The Uniform Resource Identifier (URI) of the destination of the navigation.</span></span>

<span data-ttu-id="768b3-114">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="768b3-114">This property is read-only.</span></span>

```js
var uri = NavigationEventWithReferrer.uri;
```

#### <span data-ttu-id="768b3-115">属性值</span><span class="sxs-lookup"><span data-stu-id="768b3-115">Property value</span></span>
<span data-ttu-id="768b3-116">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="768b3-116">Type: **DOMString**</span></span>
