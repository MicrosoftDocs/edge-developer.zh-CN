---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2CreationProperties 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/17/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、WebView2、浏览器控件、边缘 html、。 CoreWebView2CreationProperties
ms.openlocfilehash: 04c80d3319c74d3461666b6f35fadd0481b45207
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885532"
---
# <span data-ttu-id="2ba8f-104">CoreWebView2CreationProperties 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="2ba8f-104">Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties class</span></span> 

<span data-ttu-id="2ba8f-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="2ba8f-105">Namespace: Microsoft.Web.WebView2.Wpf</span></span>\
<span data-ttu-id="2ba8f-106">程序集： Microsoft.Web.WebView2.Wpf.dll</span><span class="sxs-lookup"><span data-stu-id="2ba8f-106">Assembly: Microsoft.Web.WebView2.Wpf.dll</span></span>

```
class Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties
  : public DependencyObject
```

<span data-ttu-id="2ba8f-107">此类是用于创建 CoreWebView2Environment 的最常用参数的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-107">This class is a bundle of the most common parameters used to create a CoreWebView2Environment.</span></span>

## <span data-ttu-id="2ba8f-108">摘要</span><span class="sxs-lookup"><span data-stu-id="2ba8f-108">Summary</span></span>

 <span data-ttu-id="2ba8f-109">成员</span><span class="sxs-lookup"><span data-stu-id="2ba8f-109">Members</span></span>                        | <span data-ttu-id="2ba8f-110">描述</span><span class="sxs-lookup"><span data-stu-id="2ba8f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2ba8f-111">BrowserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="2ba8f-111">BrowserExecutableFolder</span></span>](#browserexecutablefolder) | <span data-ttu-id="2ba8f-112">获取或设置在使用此实例创建环境时要作为 CoreWebView2Environment 的 browserExecutableFolder 参数传递的值。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-112">Gets or sets the value to pass as the browserExecutableFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>
[<span data-ttu-id="2ba8f-113">语言</span><span class="sxs-lookup"><span data-stu-id="2ba8f-113">Language</span></span>](#language) | <span data-ttu-id="2ba8f-114">获取或设置在使用此实例创建环境时，用于传递到 CoreWebView2Environment 的 CoreWebView2EnvironmentOptions 参数的 Language 属性的值。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-114">Gets or sets the value to use for the Language property of the CoreWebView2EnvironmentOptions parameter passed to CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>
[<span data-ttu-id="2ba8f-115">UserDataFolder</span><span class="sxs-lookup"><span data-stu-id="2ba8f-115">UserDataFolder</span></span>](#userdatafolder) | <span data-ttu-id="2ba8f-116">获取或设置在使用此实例创建环境时要作为 CoreWebView2Environment 的 userDataFolder 参数传递的值。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-116">Gets or sets the value to pass as the userDataFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>
[<span data-ttu-id="2ba8f-117">CoreWebView2CreationProperties</span><span class="sxs-lookup"><span data-stu-id="2ba8f-117">CoreWebView2CreationProperties</span></span>](#corewebview2creationproperties) | <span data-ttu-id="2ba8f-118">使用所有属性的默认数据创建 CoreWebView2CreationProperties 的新实例。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-118">Creates a new instance of CoreWebView2CreationProperties with default data for all properties.</span></span>

<span data-ttu-id="2ba8f-119">它的主要用途是将 WebView2 设置为[CreationProperties](microsoft-web-webview2-wpf-webview2.md) ，以便在隐式初始化期间自定义[WebView2](microsoft-web-webview2-wpf-webview2.md)使用的环境。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-119">Its main purpose is to be set to [WebView2.CreationProperties](microsoft-web-webview2-wpf-webview2.md) in order to customize the environment used by a [WebView2](microsoft-web-webview2-wpf-webview2.md) during implicit initialization.</span></span> <span data-ttu-id="2ba8f-120">它也是一个很好的 WPF 集成实用工具，它允许将常用的环境参数用作依赖属性并在标记中创建和使用。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-120">It is also a nice WPF integration utility which allows commonly used environment parameters to be dependency properties and be created and used in markup.</span></span>

<span data-ttu-id="2ba8f-121">此类不用于包含所有可能的环境自定义选项。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-121">This class isn't intended to contain all possible environment customization options.</span></span> <span data-ttu-id="2ba8f-122">如果你需要对 WebView2 控件使用的环境进行完全控制，则需要通过创建你自己的具有 CoreWebView2Environment 的环境并将其传递到[WebView2](microsoft-web-webview2-wpf-webview2.md)来显式初始化控件，然后*再*将[EnsureCoreWebView2Async Source](microsoft-web-webview2-wpf-webview2.md)属性设置为任何内容。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-122">If you need complete control over the environment used by a WebView2 control then you'll need to initialize the control explicitly by creating your own environment with CoreWebView2Environment.CreateAsync and passing it to [WebView2.EnsureCoreWebView2Async](microsoft-web-webview2-wpf-webview2.md)*before* you set the [WebView2.Source](microsoft-web-webview2-wpf-webview2.md) property to anything.</span></span> <span data-ttu-id="2ba8f-123">有关初始化概述，请参阅[WebView2](microsoft-web-webview2-wpf-webview2.md)类文档。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-123">See the [WebView2](microsoft-web-webview2-wpf-webview2.md) class documentation for an initialization overview.</span></span>

## <span data-ttu-id="2ba8f-124">成员</span><span class="sxs-lookup"><span data-stu-id="2ba8f-124">Members</span></span>

#### <span data-ttu-id="2ba8f-125">BrowserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="2ba8f-125">BrowserExecutableFolder</span></span> 

<span data-ttu-id="2ba8f-126">获取或设置在使用此实例创建环境时要作为 CoreWebView2Environment 的 browserExecutableFolder 参数传递的值。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-126">Gets or sets the value to pass as the browserExecutableFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>

> <span data-ttu-id="2ba8f-127">公共字符串[BrowserExecutableFolder](#browserexecutablefolder)</span><span class="sxs-lookup"><span data-stu-id="2ba8f-127">public string [BrowserExecutableFolder](#browserexecutablefolder)</span></span>

#### <span data-ttu-id="2ba8f-128">语言</span><span class="sxs-lookup"><span data-stu-id="2ba8f-128">Language</span></span> 

<span data-ttu-id="2ba8f-129">获取或设置在使用此实例创建环境时，用于传递到 CoreWebView2Environment 的 CoreWebView2EnvironmentOptions 参数的 Language 属性的值。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-129">Gets or sets the value to use for the Language property of the CoreWebView2EnvironmentOptions parameter passed to CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>

> <span data-ttu-id="2ba8f-130">公共字符串[语言](#language)</span><span class="sxs-lookup"><span data-stu-id="2ba8f-130">public string [Language](#language)</span></span>

#### <span data-ttu-id="2ba8f-131">UserDataFolder</span><span class="sxs-lookup"><span data-stu-id="2ba8f-131">UserDataFolder</span></span> 

<span data-ttu-id="2ba8f-132">获取或设置在使用此实例创建环境时要作为 CoreWebView2Environment 的 userDataFolder 参数传递的值。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-132">Gets or sets the value to pass as the userDataFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>

> <span data-ttu-id="2ba8f-133">公共字符串[UserDataFolder](#userdatafolder)</span><span class="sxs-lookup"><span data-stu-id="2ba8f-133">public string [UserDataFolder](#userdatafolder)</span></span>

#### <span data-ttu-id="2ba8f-134">CoreWebView2CreationProperties</span><span class="sxs-lookup"><span data-stu-id="2ba8f-134">CoreWebView2CreationProperties</span></span> 

<span data-ttu-id="2ba8f-135">使用所有属性的默认数据创建 CoreWebView2CreationProperties 的新实例。</span><span class="sxs-lookup"><span data-stu-id="2ba8f-135">Creates a new instance of CoreWebView2CreationProperties with default data for all properties.</span></span>

> <span data-ttu-id="2ba8f-136">公共[CoreWebView2CreationProperties](#corewebview2creationproperties)（）</span><span class="sxs-lookup"><span data-stu-id="2ba8f-136">public [CoreWebView2CreationProperties](#corewebview2creationproperties)()</span></span>

