---
description: 表示从 web 视图内容传递到应用程序的通知字符串
title: ScriptNotifyEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 164bfa7228b1f4ccf9817e4b7231361d090f1394
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752008"
---
# <span data-ttu-id="070c5-104">ScriptNotifyEvent 对象</span><span class="sxs-lookup"><span data-stu-id="070c5-104">ScriptNotifyEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="070c5-105">一个对象，表示当[web 视图](../webview.md)中包含的内容通过使用 JavaScript 将字符串传递给应用程序时引发的事件。</span><span class="sxs-lookup"><span data-stu-id="070c5-105">An object that represents an event fired when content contained in the [webview](../webview.md) passes a string to the application by using JavaScript.</span></span>  

## <span data-ttu-id="070c5-106">属性</span><span class="sxs-lookup"><span data-stu-id="070c5-106">Properties</span></span>  

### <span data-ttu-id="070c5-107">callingUri</span><span class="sxs-lookup"><span data-stu-id="070c5-107">callingUri</span></span>  

<span data-ttu-id="070c5-108">获取页面的统一资源标识符（URI），该页面包含引发**ScriptNotifyEvent**的脚本。</span><span class="sxs-lookup"><span data-stu-id="070c5-108">Gets the Uniform Resource Identifier (URI) of the page containing the script that raised the **ScriptNotifyEvent**.</span></span>  

<span data-ttu-id="070c5-109">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="070c5-109">This property is read-only.</span></span>  

```javascript
var callingUri = ScriptNotifyEvent.callingUri;
```  

#### <span data-ttu-id="070c5-110">属性值</span><span class="sxs-lookup"><span data-stu-id="070c5-110">Property value</span></span>  

<span data-ttu-id="070c5-111">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="070c5-111">Type: **DOMString**</span></span>  

### <span data-ttu-id="070c5-112">值</span><span class="sxs-lookup"><span data-stu-id="070c5-112">value</span></span>  

<span data-ttu-id="070c5-113">传递给应用程序的方法名称。</span><span class="sxs-lookup"><span data-stu-id="070c5-113">The method name as passed to the application.</span></span>  

<span data-ttu-id="070c5-114">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="070c5-114">This property is read-only.</span></span>  

```javascript
var value = ScriptNotifyEvent.value;
```  

#### <span data-ttu-id="070c5-115">属性值</span><span class="sxs-lookup"><span data-stu-id="070c5-115">Property value</span></span>  

<span data-ttu-id="070c5-116">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="070c5-116">Type: **DOMString**</span></span>  
