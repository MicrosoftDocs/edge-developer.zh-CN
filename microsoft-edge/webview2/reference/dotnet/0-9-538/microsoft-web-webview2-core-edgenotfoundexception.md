---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: b7d738628d6627232780e003f126b45c0421d6f0
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698411"
---
# <span data-ttu-id="4a033-104">EdgeNotFoundException 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="4a033-104">Microsoft.Web.WebView2.Core.EdgeNotFoundException class</span></span> 

<span data-ttu-id="4a033-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="4a033-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="4a033-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="4a033-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

```
class Microsoft.Web.WebView2.Core.EdgeNotFoundException
  : public Exception
```

<span data-ttu-id="4a033-107">缺少边缘安装时引发的异常。</span><span class="sxs-lookup"><span data-stu-id="4a033-107">The exception that is thrown when an Edge installation is missing.</span></span>

## <span data-ttu-id="4a033-108">摘要</span><span class="sxs-lookup"><span data-stu-id="4a033-108">Summary</span></span>

 <span data-ttu-id="4a033-109">成员</span><span class="sxs-lookup"><span data-stu-id="4a033-109">Members</span></span>                        | <span data-ttu-id="4a033-110">描述</span><span class="sxs-lookup"><span data-stu-id="4a033-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4a033-111">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="4a033-111">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="4a033-112">初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="4a033-112">Initializes a new instance of the EdgeNotFoundException class.</span></span>
[<span data-ttu-id="4a033-113">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="4a033-113">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="4a033-114">使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="4a033-114">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>
[<span data-ttu-id="4a033-115">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="4a033-115">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="4a033-116">使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="4a033-116">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>
[<span data-ttu-id="4a033-117">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="4a033-117">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="4a033-118">使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="4a033-118">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

## <span data-ttu-id="4a033-119">成员</span><span class="sxs-lookup"><span data-stu-id="4a033-119">Members</span></span>

#### <span data-ttu-id="4a033-120">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="4a033-120">EdgeNotFoundException</span></span> 

<span data-ttu-id="4a033-121">初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="4a033-121">Initializes a new instance of the EdgeNotFoundException class.</span></span>

> <span data-ttu-id="4a033-122">公共[EdgeNotFoundException](#edgenotfoundexception)（）</span><span class="sxs-lookup"><span data-stu-id="4a033-122">public [EdgeNotFoundException](#edgenotfoundexception)()</span></span>

#### <span data-ttu-id="4a033-123">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="4a033-123">EdgeNotFoundException</span></span> 

<span data-ttu-id="4a033-124">使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="4a033-124">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="4a033-125">公共[EdgeNotFoundException](#edgenotfoundexception)（异常内部）</span><span class="sxs-lookup"><span data-stu-id="4a033-125">public [EdgeNotFoundException](#edgenotfoundexception)(Exception inner)</span></span>

##### <span data-ttu-id="4a033-126">参数</span><span class="sxs-lookup"><span data-stu-id="4a033-126">Parameters</span></span>
* `inner` <span data-ttu-id="4a033-127">导致当前异常的异常。</span><span class="sxs-lookup"><span data-stu-id="4a033-127">The exception that is the cause of the current exception.</span></span>

#### <span data-ttu-id="4a033-128">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="4a033-128">EdgeNotFoundException</span></span> 

<span data-ttu-id="4a033-129">使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="4a033-129">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>

> <span data-ttu-id="4a033-130">公共[EdgeNotFoundException](#edgenotfoundexception)（字符串消息）</span><span class="sxs-lookup"><span data-stu-id="4a033-130">public [EdgeNotFoundException](#edgenotfoundexception)(string message)</span></span>

##### <span data-ttu-id="4a033-131">参数</span><span class="sxs-lookup"><span data-stu-id="4a033-131">Parameters</span></span>
* `message` <span data-ttu-id="4a033-132">解释异常原因的错误消息。</span><span class="sxs-lookup"><span data-stu-id="4a033-132">The error message that explains the reason for the exception.</span></span>

#### <span data-ttu-id="4a033-133">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="4a033-133">EdgeNotFoundException</span></span> 

<span data-ttu-id="4a033-134">使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="4a033-134">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="4a033-135">公共[EdgeNotFoundException](#edgenotfoundexception)（字符串消息，内部异常内部）</span><span class="sxs-lookup"><span data-stu-id="4a033-135">public [EdgeNotFoundException](#edgenotfoundexception)(string message, Exception inner)</span></span>

##### <span data-ttu-id="4a033-136">参数</span><span class="sxs-lookup"><span data-stu-id="4a033-136">Parameters</span></span>
* `message` <span data-ttu-id="4a033-137">解释异常原因的错误消息。</span><span class="sxs-lookup"><span data-stu-id="4a033-137">The error message that explains the reason for the exception.</span></span> 

* `inner` <span data-ttu-id="4a033-138">导致当前异常的异常。</span><span class="sxs-lookup"><span data-stu-id="4a033-138">The exception that is the cause of the current exception.</span></span>

