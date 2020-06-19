---
description: 指示 web 视图正在尝试下载不受支持的文件。
title: UnviewableContentIdentifiedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 0179522f3eaf0813531084eb996ee9d392e8249d
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752011"
---
# <span data-ttu-id="ea8f6-104">UnviewableContentIdentifiedEvent 对象</span><span class="sxs-lookup"><span data-stu-id="ea8f6-104">UnviewableContentIdentifiedEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="ea8f6-105">指示[web 视图](../webview.md)正在尝试导航到不受支持的内容类型的文件。</span><span class="sxs-lookup"><span data-stu-id="ea8f6-105">Indicates the [webview](../webview.md) is attempting to navigate to a file of an unsupported content type.</span></span>  

## <span data-ttu-id="ea8f6-106">属性</span><span class="sxs-lookup"><span data-stu-id="ea8f6-106">Properties</span></span>  

### <span data-ttu-id="ea8f6-107">媒体</span><span class="sxs-lookup"><span data-stu-id="ea8f6-107">mediaType</span></span>  

<span data-ttu-id="ea8f6-108">获取 unviewable 内容的内容类型。</span><span class="sxs-lookup"><span data-stu-id="ea8f6-108">Gets the content type of the unviewable content.</span></span>  

<span data-ttu-id="ea8f6-109">此属性是只读的</span><span class="sxs-lookup"><span data-stu-id="ea8f6-109">This property is read-only</span></span>  

```javascript
var mediaType = UnviewableContentIdentifiedEvent.mediaType;
```  

#### <span data-ttu-id="ea8f6-110">属性值</span><span class="sxs-lookup"><span data-stu-id="ea8f6-110">Property value</span></span>  

<span data-ttu-id="ea8f6-111">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="ea8f6-111">Type: **DOMString**</span></span>  

### <span data-ttu-id="ea8f6-112">referer</span><span class="sxs-lookup"><span data-stu-id="ea8f6-112">referer</span></span>  

<span data-ttu-id="ea8f6-113">[Web 视图](../webview.md)中请求导航的页面的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="ea8f6-113">The Uniform Resource Identifier (URI) of the page in the [webview](../webview.md) requesting navigation.</span></span>  

<span data-ttu-id="ea8f6-114">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="ea8f6-114">This property is read-only.</span></span>  

```javascript
var referer = NavigationEventWithReferrer.referer;
```  

#### <span data-ttu-id="ea8f6-115">属性值</span><span class="sxs-lookup"><span data-stu-id="ea8f6-115">Property value</span></span>  

<span data-ttu-id="ea8f6-116">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="ea8f6-116">Type: **DOMString**</span></span>  

### <span data-ttu-id="ea8f6-117">uri</span><span class="sxs-lookup"><span data-stu-id="ea8f6-117">uri</span></span>  

<span data-ttu-id="ea8f6-118">导航的目标的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="ea8f6-118">The Uniform Resource Identifier (URI) of the destination of the navigation.</span></span>  

<span data-ttu-id="ea8f6-119">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="ea8f6-119">This property is read-only.</span></span>  

```javascript
var uri = NavigationEventWithReferrer.uri;
```  

#### <span data-ttu-id="ea8f6-120">属性值</span><span class="sxs-lookup"><span data-stu-id="ea8f6-120">Property value</span></span>  

<span data-ttu-id="ea8f6-121">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="ea8f6-121">Type: **DOMString**</span></span>  
