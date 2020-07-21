---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 EdgeNotFoundException
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: fc65d857f11a77a1d3629d40266f0453acadaa7b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886309"
---
# <span data-ttu-id="a3546-104">0.9.515-WebView2 的 EdgeNotFoundException 类</span><span class="sxs-lookup"><span data-stu-id="a3546-104">0.9.515 - Microsoft.Web.WebView2.Core.EdgeNotFoundException class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="a3546-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="a3546-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="a3546-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="a3546-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

```
class Microsoft.Web.WebView2.Core.EdgeNotFoundException
  : public Exception
```

<span data-ttu-id="a3546-107">缺少边缘安装时引发的异常。</span><span class="sxs-lookup"><span data-stu-id="a3546-107">The exception that is thrown when an Edge installation is missing.</span></span>

## <span data-ttu-id="a3546-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a3546-108">Summary</span></span>

 <span data-ttu-id="a3546-109">成员</span><span class="sxs-lookup"><span data-stu-id="a3546-109">Members</span></span>                        | <span data-ttu-id="a3546-110">描述</span><span class="sxs-lookup"><span data-stu-id="a3546-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a3546-111">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="a3546-111">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="a3546-112">初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="a3546-112">Initializes a new instance of the EdgeNotFoundException class.</span></span>
[<span data-ttu-id="a3546-113">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="a3546-113">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="a3546-114">使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="a3546-114">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>
[<span data-ttu-id="a3546-115">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="a3546-115">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="a3546-116">使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="a3546-116">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>
[<span data-ttu-id="a3546-117">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="a3546-117">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="a3546-118">使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="a3546-118">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

## <span data-ttu-id="a3546-119">成员</span><span class="sxs-lookup"><span data-stu-id="a3546-119">Members</span></span>

#### <span data-ttu-id="a3546-120">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="a3546-120">EdgeNotFoundException</span></span> 

<span data-ttu-id="a3546-121">初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="a3546-121">Initializes a new instance of the EdgeNotFoundException class.</span></span>

> <span data-ttu-id="a3546-122">公共[EdgeNotFoundException](#edgenotfoundexception)（）</span><span class="sxs-lookup"><span data-stu-id="a3546-122">public [EdgeNotFoundException](#edgenotfoundexception)()</span></span>

#### <span data-ttu-id="a3546-123">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="a3546-123">EdgeNotFoundException</span></span> 

<span data-ttu-id="a3546-124">使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="a3546-124">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="a3546-125">公共[EdgeNotFoundException](#edgenotfoundexception)（异常内部）</span><span class="sxs-lookup"><span data-stu-id="a3546-125">public [EdgeNotFoundException](#edgenotfoundexception)(Exception inner)</span></span>

##### <span data-ttu-id="a3546-126">参数</span><span class="sxs-lookup"><span data-stu-id="a3546-126">Parameters</span></span>
* `inner` <span data-ttu-id="a3546-127">导致当前异常的异常。</span><span class="sxs-lookup"><span data-stu-id="a3546-127">The exception that is the cause of the current exception.</span></span>

#### <span data-ttu-id="a3546-128">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="a3546-128">EdgeNotFoundException</span></span> 

<span data-ttu-id="a3546-129">使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="a3546-129">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>

> <span data-ttu-id="a3546-130">公共[EdgeNotFoundException](#edgenotfoundexception)（字符串消息）</span><span class="sxs-lookup"><span data-stu-id="a3546-130">public [EdgeNotFoundException](#edgenotfoundexception)(string message)</span></span>

##### <span data-ttu-id="a3546-131">参数</span><span class="sxs-lookup"><span data-stu-id="a3546-131">Parameters</span></span>
* `message` <span data-ttu-id="a3546-132">解释异常原因的错误消息。</span><span class="sxs-lookup"><span data-stu-id="a3546-132">The error message that explains the reason for the exception.</span></span>

#### <span data-ttu-id="a3546-133">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="a3546-133">EdgeNotFoundException</span></span> 

<span data-ttu-id="a3546-134">使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="a3546-134">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="a3546-135">公共[EdgeNotFoundException](#edgenotfoundexception)（字符串消息，内部异常内部）</span><span class="sxs-lookup"><span data-stu-id="a3546-135">public [EdgeNotFoundException](#edgenotfoundexception)(string message, Exception inner)</span></span>

##### <span data-ttu-id="a3546-136">参数</span><span class="sxs-lookup"><span data-stu-id="a3546-136">Parameters</span></span>
* `message` <span data-ttu-id="a3546-137">解释异常原因的错误消息。</span><span class="sxs-lookup"><span data-stu-id="a3546-137">The error message that explains the reason for the exception.</span></span> 

* `inner` <span data-ttu-id="a3546-138">导致当前异常的异常。</span><span class="sxs-lookup"><span data-stu-id="a3546-138">The exception that is the cause of the current exception.</span></span>

