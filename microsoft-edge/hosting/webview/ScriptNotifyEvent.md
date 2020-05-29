---
description: 表示从 web 视图内容传递到应用程序的通知字符串
title: ScriptNotifyEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 22313f2d96ca2c5d4d3554ca40589b9a583c89cd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562559"
---
# <span data-ttu-id="3cd91-104">ScriptNotifyEvent 对象</span><span class="sxs-lookup"><span data-stu-id="3cd91-104">ScriptNotifyEvent object</span></span>

<span data-ttu-id="3cd91-105">一个对象，表示当[web 视图](../webview.md)中包含的内容通过使用 JavaScript 将字符串传递给应用程序时引发的事件。</span><span class="sxs-lookup"><span data-stu-id="3cd91-105">An object that represents an event fired when content contained in the [webview](../webview.md) passes a string to the application by using JavaScript.</span></span>

## <span data-ttu-id="3cd91-106">属性</span><span class="sxs-lookup"><span data-stu-id="3cd91-106">Properties</span></span>
    
### <span data-ttu-id="3cd91-107">callingUri</span><span class="sxs-lookup"><span data-stu-id="3cd91-107">callingUri</span></span>

<span data-ttu-id="3cd91-108">获取页面的统一资源标识符（URI），该页面包含引发**ScriptNotifyEvent**的脚本。</span><span class="sxs-lookup"><span data-stu-id="3cd91-108">Gets the Uniform Resource Identifier (URI) of the page containing the script that raised the **ScriptNotifyEvent**.</span></span>

<span data-ttu-id="3cd91-109">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="3cd91-109">This property is read-only.</span></span>

```js
var callingUri = ScriptNotifyEvent.callingUri;
```

#### <span data-ttu-id="3cd91-110">属性值</span><span class="sxs-lookup"><span data-stu-id="3cd91-110">Property value</span></span>
<span data-ttu-id="3cd91-111">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="3cd91-111">Type: **DOMString**</span></span>

### <span data-ttu-id="3cd91-112">值</span><span class="sxs-lookup"><span data-stu-id="3cd91-112">value</span></span>

<span data-ttu-id="3cd91-113">传递给应用程序的方法名称。</span><span class="sxs-lookup"><span data-stu-id="3cd91-113">The method name as passed to the application.</span></span>

<span data-ttu-id="3cd91-114">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="3cd91-114">This property is read-only.</span></span>

```js
var value = ScriptNotifyEvent.value;
```

#### <span data-ttu-id="3cd91-115">属性值</span><span class="sxs-lookup"><span data-stu-id="3cd91-115">Property value</span></span>
<span data-ttu-id="3cd91-116">类型： **DOMString**</span><span class="sxs-lookup"><span data-stu-id="3cd91-116">Type: **DOMString**</span></span>