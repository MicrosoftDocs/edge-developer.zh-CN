---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 EdgeNotFoundException
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: db4a903ca430541fa9edec9d953bf28531f7c0a4
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879602"
---
# <span data-ttu-id="9ffbb-104">0.9.515-WebView2 的 EdgeNotFoundException 类</span><span class="sxs-lookup"><span data-stu-id="9ffbb-104">0.9.515 - Microsoft.Web.WebView2.Core.EdgeNotFoundException class</span></span> 

> [!NOTE]
> <span data-ttu-id="9ffbb-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="9ffbb-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="9ffbb-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="9ffbb-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="9ffbb-108">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="9ffbb-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

```
class Microsoft.Web.WebView2.Core.EdgeNotFoundException
  : public Exception
```

<span data-ttu-id="9ffbb-109">缺少边缘安装时引发的异常。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-109">The exception that is thrown when an Edge installation is missing.</span></span>

## <span data-ttu-id="9ffbb-110">摘要</span><span class="sxs-lookup"><span data-stu-id="9ffbb-110">Summary</span></span>

 <span data-ttu-id="9ffbb-111">成员</span><span class="sxs-lookup"><span data-stu-id="9ffbb-111">Members</span></span>                        | <span data-ttu-id="9ffbb-112">描述</span><span class="sxs-lookup"><span data-stu-id="9ffbb-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9ffbb-113">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="9ffbb-113">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="9ffbb-114">初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-114">Initializes a new instance of the EdgeNotFoundException class.</span></span>
[<span data-ttu-id="9ffbb-115">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="9ffbb-115">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="9ffbb-116">使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-116">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>
[<span data-ttu-id="9ffbb-117">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="9ffbb-117">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="9ffbb-118">使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-118">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>
[<span data-ttu-id="9ffbb-119">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="9ffbb-119">EdgeNotFoundException</span></span>](#edgenotfoundexception) | <span data-ttu-id="9ffbb-120">使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-120">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

## <span data-ttu-id="9ffbb-121">成员</span><span class="sxs-lookup"><span data-stu-id="9ffbb-121">Members</span></span>

#### <span data-ttu-id="9ffbb-122">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="9ffbb-122">EdgeNotFoundException</span></span> 

<span data-ttu-id="9ffbb-123">初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-123">Initializes a new instance of the EdgeNotFoundException class.</span></span>

> <span data-ttu-id="9ffbb-124">公共[EdgeNotFoundException](#edgenotfoundexception)（）</span><span class="sxs-lookup"><span data-stu-id="9ffbb-124">public [EdgeNotFoundException](#edgenotfoundexception)()</span></span>

#### <span data-ttu-id="9ffbb-125">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="9ffbb-125">EdgeNotFoundException</span></span> 

<span data-ttu-id="9ffbb-126">使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-126">Initializes a new instance of the EdgeNotFoundException class with a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="9ffbb-127">公共[EdgeNotFoundException](#edgenotfoundexception)（异常内部）</span><span class="sxs-lookup"><span data-stu-id="9ffbb-127">public [EdgeNotFoundException](#edgenotfoundexception)(Exception inner)</span></span>

##### <span data-ttu-id="9ffbb-128">参数</span><span class="sxs-lookup"><span data-stu-id="9ffbb-128">Parameters</span></span>
* `inner` <span data-ttu-id="9ffbb-129">导致当前异常的异常。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-129">The exception that is the cause of the current exception.</span></span>

#### <span data-ttu-id="9ffbb-130">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="9ffbb-130">EdgeNotFoundException</span></span> 

<span data-ttu-id="9ffbb-131">使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-131">Initializes a new instance of the EdgeNotFoundException class with a specified error message.</span></span>

> <span data-ttu-id="9ffbb-132">公共[EdgeNotFoundException](#edgenotfoundexception)（字符串消息）</span><span class="sxs-lookup"><span data-stu-id="9ffbb-132">public [EdgeNotFoundException](#edgenotfoundexception)(string message)</span></span>

##### <span data-ttu-id="9ffbb-133">参数</span><span class="sxs-lookup"><span data-stu-id="9ffbb-133">Parameters</span></span>
* `message` <span data-ttu-id="9ffbb-134">解释异常原因的错误消息。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-134">The error message that explains the reason for the exception.</span></span>

#### <span data-ttu-id="9ffbb-135">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="9ffbb-135">EdgeNotFoundException</span></span> 

<span data-ttu-id="9ffbb-136">使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-136">Initializes a new instance of the EdgeNotFoundException class with a specified error message and a reference to the inner exception that is the cause of this exception.</span></span>

> <span data-ttu-id="9ffbb-137">公共[EdgeNotFoundException](#edgenotfoundexception)（字符串消息，内部异常内部）</span><span class="sxs-lookup"><span data-stu-id="9ffbb-137">public [EdgeNotFoundException](#edgenotfoundexception)(string message, Exception inner)</span></span>

##### <span data-ttu-id="9ffbb-138">参数</span><span class="sxs-lookup"><span data-stu-id="9ffbb-138">Parameters</span></span>
* `message` <span data-ttu-id="9ffbb-139">解释异常原因的错误消息。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-139">The error message that explains the reason for the exception.</span></span> 

* `inner` <span data-ttu-id="9ffbb-140">导致当前异常的异常。</span><span class="sxs-lookup"><span data-stu-id="9ffbb-140">The exception that is the cause of the current exception.</span></span>

