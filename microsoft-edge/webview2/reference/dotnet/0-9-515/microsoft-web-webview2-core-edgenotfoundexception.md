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
ms.openlocfilehash: 7f30bda4deb0811748c65880fcc49c21bc39a732
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697292"
---
# <span data-ttu-id="6ff5e-104">EdgeNotFoundException 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="6ff5e-104">Microsoft.Web.WebView2.Core.EdgeNotFoundException class</span></span> 

> [!NOTE]
> <span data-ttu-id="6ff5e-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="6ff5e-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="6ff5e-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="6ff5e-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="6ff5e-108">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="6ff5e-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

```
class Microsoft.Web.WebView2.Core.EdgeNotFoundException
  : public Exception
```

<span data-ttu-id="6ff5e-109">缺少边缘安装时引发的异常。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-109">The exception that is thrown when an Edge installation is missing.</span></span>

## <span data-ttu-id="6ff5e-110">摘要</span><span class="sxs-lookup"><span data-stu-id="6ff5e-110">Summary</span></span>

 <span data-ttu-id="6ff5e-111">成员</span><span class="sxs-lookup"><span data-stu-id="6ff5e-111">Members</span></span>                        | <span data-ttu-id="6ff5e-112">描述</span><span class="sxs-lookup"><span data-stu-id="6ff5e-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6ff5e-113">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="6ff5e-113">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="6ff5e-114">初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-114">Initializes a new instance of the EdgeNotFoundException class.</span></span>
[<span data-ttu-id="6ff5e-115">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="6ff5e-115">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="6ff5e-116">使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-116">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>
[<span data-ttu-id="6ff5e-117">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="6ff5e-117">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="6ff5e-118">使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-118">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>
[<span data-ttu-id="6ff5e-119">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="6ff5e-119">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="6ff5e-120">使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-120">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

## <span data-ttu-id="6ff5e-121">成员</span><span class="sxs-lookup"><span data-stu-id="6ff5e-121">Members</span></span>

#### <span data-ttu-id="6ff5e-122">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="6ff5e-122">EdgeNotFoundException</span></span> 

<span data-ttu-id="6ff5e-123">初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-123">Initializes a new instance of the EdgeNotFoundException class.</span></span>

> <span data-ttu-id="6ff5e-124">公共[EdgeNotFoundException](#edgenotfoundexception)（）</span><span class="sxs-lookup"><span data-stu-id="6ff5e-124">public [EdgeNotFoundException](#edgenotfoundexception)()</span></span>

#### <span data-ttu-id="6ff5e-125">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="6ff5e-125">EdgeNotFoundException</span></span> 

<span data-ttu-id="6ff5e-126">使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-126">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="6ff5e-127">公共[EdgeNotFoundException](#edgenotfoundexception)（异常内部）</span><span class="sxs-lookup"><span data-stu-id="6ff5e-127">public [EdgeNotFoundException](#edgenotfoundexception)(Exception inner)</span></span>

##### <span data-ttu-id="6ff5e-128">参数</span><span class="sxs-lookup"><span data-stu-id="6ff5e-128">Parameters</span></span>
* `inner` <span data-ttu-id="6ff5e-129">导致当前异常的异常。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-129">The exception that is the cause of the current exception.</span></span>

#### <span data-ttu-id="6ff5e-130">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="6ff5e-130">EdgeNotFoundException</span></span> 

<span data-ttu-id="6ff5e-131">使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-131">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>

> <span data-ttu-id="6ff5e-132">公共[EdgeNotFoundException](#edgenotfoundexception)（字符串消息）</span><span class="sxs-lookup"><span data-stu-id="6ff5e-132">public [EdgeNotFoundException](#edgenotfoundexception)(string message)</span></span>

##### <span data-ttu-id="6ff5e-133">参数</span><span class="sxs-lookup"><span data-stu-id="6ff5e-133">Parameters</span></span>
* `message` <span data-ttu-id="6ff5e-134">解释异常原因的错误消息。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-134">The error message that explains the reason for the exception.</span></span>

#### <span data-ttu-id="6ff5e-135">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="6ff5e-135">EdgeNotFoundException</span></span> 

<span data-ttu-id="6ff5e-136">使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-136">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="6ff5e-137">公共[EdgeNotFoundException](#edgenotfoundexception)（字符串消息，内部异常内部）</span><span class="sxs-lookup"><span data-stu-id="6ff5e-137">public [EdgeNotFoundException](#edgenotfoundexception)(string message, Exception inner)</span></span>

##### <span data-ttu-id="6ff5e-138">参数</span><span class="sxs-lookup"><span data-stu-id="6ff5e-138">Parameters</span></span>
* `message` <span data-ttu-id="6ff5e-139">解释异常原因的错误消息。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-139">The error message that explains the reason for the exception.</span></span> 

* `inner` <span data-ttu-id="6ff5e-140">导致当前异常的异常。</span><span class="sxs-lookup"><span data-stu-id="6ff5e-140">The exception that is the cause of the current exception.</span></span>

