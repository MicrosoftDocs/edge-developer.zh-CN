---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: EdgeNotFoundException 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: f74e28eb206458525b0043023e80aea3ac368674
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011650"
---
# <span data-ttu-id="1f5cb-104">EdgeNotFoundException 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="1f5cb-104">Microsoft.Web.WebView2.Core.EdgeNotFoundException class</span></span> 

<span data-ttu-id="1f5cb-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="1f5cb-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="1f5cb-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="1f5cb-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

```
class Microsoft.Web.WebView2.Core.EdgeNotFoundException
  : public Exception
```

<span data-ttu-id="1f5cb-107">缺少边缘安装时引发的异常。</span><span class="sxs-lookup"><span data-stu-id="1f5cb-107">The exception that is thrown when an Edge installation is missing.</span></span>

## <span data-ttu-id="1f5cb-108">摘要</span><span class="sxs-lookup"><span data-stu-id="1f5cb-108">Summary</span></span>

 <span data-ttu-id="1f5cb-109">成员</span><span class="sxs-lookup"><span data-stu-id="1f5cb-109">Members</span></span>                        | <span data-ttu-id="1f5cb-110">描述</span><span class="sxs-lookup"><span data-stu-id="1f5cb-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1f5cb-111">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="1f5cb-111">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="1f5cb-112">初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="1f5cb-112">Initializes a new instance of the EdgeNotFoundException class.</span></span>
[<span data-ttu-id="1f5cb-113">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="1f5cb-113">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="1f5cb-114">使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="1f5cb-114">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>
[<span data-ttu-id="1f5cb-115">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="1f5cb-115">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="1f5cb-116">使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="1f5cb-116">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>
[<span data-ttu-id="1f5cb-117">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="1f5cb-117">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="1f5cb-118">使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="1f5cb-118">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

## <span data-ttu-id="1f5cb-119">成员</span><span class="sxs-lookup"><span data-stu-id="1f5cb-119">Members</span></span>

#### <span data-ttu-id="1f5cb-120">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="1f5cb-120">EdgeNotFoundException</span></span> 

<span data-ttu-id="1f5cb-121">初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="1f5cb-121">Initializes a new instance of the EdgeNotFoundException class.</span></span>

> <span data-ttu-id="1f5cb-122">公共 [EdgeNotFoundException](#edgenotfoundexception) ( # A1</span><span class="sxs-lookup"><span data-stu-id="1f5cb-122">public [EdgeNotFoundException](#edgenotfoundexception)()</span></span>

#### <span data-ttu-id="1f5cb-123">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="1f5cb-123">EdgeNotFoundException</span></span> 

<span data-ttu-id="1f5cb-124">使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="1f5cb-124">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="1f5cb-125">公共 [EdgeNotFoundException](#edgenotfoundexception) (异常内部) </span><span class="sxs-lookup"><span data-stu-id="1f5cb-125">public [EdgeNotFoundException](#edgenotfoundexception)(Exception inner)</span></span>

##### <span data-ttu-id="1f5cb-126">参数</span><span class="sxs-lookup"><span data-stu-id="1f5cb-126">Parameters</span></span>
* `inner` <span data-ttu-id="1f5cb-127">导致当前异常的异常。</span><span class="sxs-lookup"><span data-stu-id="1f5cb-127">The exception that is the cause of the current exception.</span></span>

#### <span data-ttu-id="1f5cb-128">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="1f5cb-128">EdgeNotFoundException</span></span> 

<span data-ttu-id="1f5cb-129">使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="1f5cb-129">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>

> <span data-ttu-id="1f5cb-130">公共 [EdgeNotFoundException](#edgenotfoundexception) (字符串消息) </span><span class="sxs-lookup"><span data-stu-id="1f5cb-130">public [EdgeNotFoundException](#edgenotfoundexception)(string message)</span></span>

##### <span data-ttu-id="1f5cb-131">参数</span><span class="sxs-lookup"><span data-stu-id="1f5cb-131">Parameters</span></span>
* `message` <span data-ttu-id="1f5cb-132">解释异常原因的错误消息。</span><span class="sxs-lookup"><span data-stu-id="1f5cb-132">The error message that explains the reason for the exception.</span></span>

#### <span data-ttu-id="1f5cb-133">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="1f5cb-133">EdgeNotFoundException</span></span> 

<span data-ttu-id="1f5cb-134">使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="1f5cb-134">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="1f5cb-135">公共 [EdgeNotFoundException](#edgenotfoundexception) (字符串消息，内部) 异常</span><span class="sxs-lookup"><span data-stu-id="1f5cb-135">public [EdgeNotFoundException](#edgenotfoundexception)(string message, Exception inner)</span></span>

##### <span data-ttu-id="1f5cb-136">参数</span><span class="sxs-lookup"><span data-stu-id="1f5cb-136">Parameters</span></span>
* `message` <span data-ttu-id="1f5cb-137">解释异常原因的错误消息。</span><span class="sxs-lookup"><span data-stu-id="1f5cb-137">The error message that explains the reason for the exception.</span></span> 

* `inner` <span data-ttu-id="1f5cb-138">导致当前异常的异常。</span><span class="sxs-lookup"><span data-stu-id="1f5cb-138">The exception that is the cause of the current exception.</span></span>
