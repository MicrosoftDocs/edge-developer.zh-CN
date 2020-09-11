---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2。 EdgeNotFoundException
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: b4dc30ff741702d03796cb40e6ea6367ffdd0fc0
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010101"
---
# <span data-ttu-id="042b0-104">0.9.579-WebView2 的 EdgeNotFoundException 类</span><span class="sxs-lookup"><span data-stu-id="042b0-104">0.9.579 - Microsoft.Web.WebView2.Core.EdgeNotFoundException class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="042b0-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="042b0-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="042b0-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="042b0-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

```
class Microsoft.Web.WebView2.Core.EdgeNotFoundException
  : public Exception
```

<span data-ttu-id="042b0-107">缺少边缘安装时引发的异常。</span><span class="sxs-lookup"><span data-stu-id="042b0-107">The exception that is thrown when an Edge installation is missing.</span></span>

## <span data-ttu-id="042b0-108">摘要</span><span class="sxs-lookup"><span data-stu-id="042b0-108">Summary</span></span>

 <span data-ttu-id="042b0-109">成员</span><span class="sxs-lookup"><span data-stu-id="042b0-109">Members</span></span>                        | <span data-ttu-id="042b0-110">描述</span><span class="sxs-lookup"><span data-stu-id="042b0-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="042b0-111">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="042b0-111">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="042b0-112">初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="042b0-112">Initializes a new instance of the EdgeNotFoundException class.</span></span>
[<span data-ttu-id="042b0-113">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="042b0-113">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="042b0-114">使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="042b0-114">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>
[<span data-ttu-id="042b0-115">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="042b0-115">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="042b0-116">使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="042b0-116">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>
[<span data-ttu-id="042b0-117">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="042b0-117">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="042b0-118">使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="042b0-118">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

## <span data-ttu-id="042b0-119">成员</span><span class="sxs-lookup"><span data-stu-id="042b0-119">Members</span></span>

#### <span data-ttu-id="042b0-120">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="042b0-120">EdgeNotFoundException</span></span> 

<span data-ttu-id="042b0-121">初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="042b0-121">Initializes a new instance of the EdgeNotFoundException class.</span></span>

> <span data-ttu-id="042b0-122">公共 [EdgeNotFoundException](#edgenotfoundexception) ( # A1</span><span class="sxs-lookup"><span data-stu-id="042b0-122">public [EdgeNotFoundException](#edgenotfoundexception)()</span></span>

#### <span data-ttu-id="042b0-123">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="042b0-123">EdgeNotFoundException</span></span> 

<span data-ttu-id="042b0-124">使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="042b0-124">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="042b0-125">公共 [EdgeNotFoundException](#edgenotfoundexception) (异常内部) </span><span class="sxs-lookup"><span data-stu-id="042b0-125">public [EdgeNotFoundException](#edgenotfoundexception)(Exception inner)</span></span>

##### <span data-ttu-id="042b0-126">参数</span><span class="sxs-lookup"><span data-stu-id="042b0-126">Parameters</span></span>
* `inner` <span data-ttu-id="042b0-127">导致当前异常的异常。</span><span class="sxs-lookup"><span data-stu-id="042b0-127">The exception that is the cause of the current exception.</span></span>

#### <span data-ttu-id="042b0-128">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="042b0-128">EdgeNotFoundException</span></span> 

<span data-ttu-id="042b0-129">使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="042b0-129">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>

> <span data-ttu-id="042b0-130">公共 [EdgeNotFoundException](#edgenotfoundexception) (字符串消息) </span><span class="sxs-lookup"><span data-stu-id="042b0-130">public [EdgeNotFoundException](#edgenotfoundexception)(string message)</span></span>

##### <span data-ttu-id="042b0-131">参数</span><span class="sxs-lookup"><span data-stu-id="042b0-131">Parameters</span></span>
* `message` <span data-ttu-id="042b0-132">解释异常原因的错误消息。</span><span class="sxs-lookup"><span data-stu-id="042b0-132">The error message that explains the reason for the exception.</span></span>

#### <span data-ttu-id="042b0-133">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="042b0-133">EdgeNotFoundException</span></span> 

<span data-ttu-id="042b0-134">使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="042b0-134">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="042b0-135">公共 [EdgeNotFoundException](#edgenotfoundexception) (字符串消息，内部) 异常</span><span class="sxs-lookup"><span data-stu-id="042b0-135">public [EdgeNotFoundException](#edgenotfoundexception)(string message, Exception inner)</span></span>

##### <span data-ttu-id="042b0-136">参数</span><span class="sxs-lookup"><span data-stu-id="042b0-136">Parameters</span></span>
* `message` <span data-ttu-id="042b0-137">解释异常原因的错误消息。</span><span class="sxs-lookup"><span data-stu-id="042b0-137">The error message that explains the reason for the exception.</span></span> 

* `inner` <span data-ttu-id="042b0-138">导致当前异常的异常。</span><span class="sxs-lookup"><span data-stu-id="042b0-138">The exception that is the cause of the current exception.</span></span>

