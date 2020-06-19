---
description: 包含有关已完成的 web 视图导航的信息
title: NavigationCompletedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: eb5727ab59dbaf056f05ab4b19450c70f85d595f
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752135"
---
# <span data-ttu-id="51e61-104">NavigationCompletedEvent 对象</span><span class="sxs-lookup"><span data-stu-id="51e61-104">NavigationCompletedEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="51e61-105">一个对象，表示当[web 视图](../webview.md)已完成加载当前内容或导航失败时引发的事件。</span><span class="sxs-lookup"><span data-stu-id="51e61-105">An object that represents an event fired when the [webview](../webview.md) has finished loading the current content or if navigation has failed.</span></span>  

## <span data-ttu-id="51e61-106">属性</span><span class="sxs-lookup"><span data-stu-id="51e61-106">Properties</span></span>  

### <span data-ttu-id="51e61-107">uri</span><span class="sxs-lookup"><span data-stu-id="51e61-107">uri</span></span>  

<span data-ttu-id="51e61-108">导航的统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="51e61-108">The Uniform Resource Identifier (URI) of the navigation.</span></span>  

<span data-ttu-id="51e61-109">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="51e61-109">This property is read-only.</span></span>  

```javascript
var uri = NavigationCompletedEvent.uri;
```  

#### <span data-ttu-id="51e61-110">属性值</span><span class="sxs-lookup"><span data-stu-id="51e61-110">Property value</span></span>  

<span data-ttu-id="51e61-111">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="51e61-111">Type: **DOMString**</span></span>  

### <span data-ttu-id="51e61-112">isSuccess</span><span class="sxs-lookup"><span data-stu-id="51e61-112">isSuccess</span></span>  

<span data-ttu-id="51e61-113">获取一个值，该值指示导航是否已成功完成。</span><span class="sxs-lookup"><span data-stu-id="51e61-113">Gets a value that indicates whether the navigation completed successfully.</span></span>  

<span data-ttu-id="51e61-114">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="51e61-114">This property is read-only.</span></span>  

```javascript
var isSuccess = NavigationCompletedEvent.isSuccess;
```  

#### <span data-ttu-id="51e61-115">属性值</span><span class="sxs-lookup"><span data-stu-id="51e61-115">Property value</span></span>  

<span data-ttu-id="51e61-116">类型： **Boolean**</span><span class="sxs-lookup"><span data-stu-id="51e61-116">Type: **Boolean**</span></span>  

### <span data-ttu-id="51e61-117">webErrorStatus</span><span class="sxs-lookup"><span data-stu-id="51e61-117">webErrorStatus</span></span>  

<span data-ttu-id="51e61-118">如果导航失败，获取指示原因的值。</span><span class="sxs-lookup"><span data-stu-id="51e61-118">If the navigation was unsuccessful, gets a value that indicates why.</span></span>  

<span data-ttu-id="51e61-119">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="51e61-119">This property is read-only.</span></span>  

```javascript
var webErrorStatus = NavigationCompletedEvent.webErrorStatus;
```  

#### <span data-ttu-id="51e61-120">属性值</span><span class="sxs-lookup"><span data-stu-id="51e61-120">Property value</span></span>  

<span data-ttu-id="51e61-121">类型：**无符号长**</span><span class="sxs-lookup"><span data-stu-id="51e61-121">Type: **unsigned long**</span></span>  
