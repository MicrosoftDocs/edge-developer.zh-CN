---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: d2c3b3ee179dec217418241031142549d170e440
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652795"
---
# <span data-ttu-id="f3972-104">CoreWebView2CreationProperties 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="f3972-104">Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties class</span></span> 

<span data-ttu-id="f3972-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="f3972-105">Namespace: Microsoft.Web.WebView2.Wpf</span></span>\
<span data-ttu-id="f3972-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="f3972-106">Assembly: Microsoft.Web.WebView2.Wpf.dll</span></span>

```
class Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties
  : public DependencyObject
```

<span data-ttu-id="f3972-107">此类是用于创建 CoreWebView2Environment 的最常用参数的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="f3972-107">This class is a bundle of the most common parameters used to create a CoreWebView2Environment.</span></span>

## <span data-ttu-id="f3972-108">摘要</span><span class="sxs-lookup"><span data-stu-id="f3972-108">Summary</span></span>

 <span data-ttu-id="f3972-109">成员</span><span class="sxs-lookup"><span data-stu-id="f3972-109">Members</span></span>                        | <span data-ttu-id="f3972-110">描述</span><span class="sxs-lookup"><span data-stu-id="f3972-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f3972-111">BrowserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="f3972-111">BrowserExecutableFolder</span></span>](#browserexecutablefolder) | <span data-ttu-id="f3972-112">获取或设置在使用此实例创建环境时要作为 CoreWebView2Environment 的 browserExecutableFolder 参数传递的值。</span><span class="sxs-lookup"><span data-stu-id="f3972-112">Gets or sets the value to pass as the browserExecutableFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>
[<span data-ttu-id="f3972-113">语言</span><span class="sxs-lookup"><span data-stu-id="f3972-113">Language</span></span>](#language) | <span data-ttu-id="f3972-114">获取或设置在使用此实例创建环境时，用于传递到 CoreWebView2Environment 的 CoreWebView2EnvironmentOptions 参数的 Language 属性的值。</span><span class="sxs-lookup"><span data-stu-id="f3972-114">Gets or sets the value to use for the Language property of the CoreWebView2EnvironmentOptions parameter passed to CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>
[<span data-ttu-id="f3972-115">UserDataFolder</span><span class="sxs-lookup"><span data-stu-id="f3972-115">UserDataFolder</span></span>](#userdatafolder) | <span data-ttu-id="f3972-116">获取或设置在使用此实例创建环境时要作为 CoreWebView2Environment 的 userDataFolder 参数传递的值。</span><span class="sxs-lookup"><span data-stu-id="f3972-116">Gets or sets the value to pass as the userDataFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>
[<span data-ttu-id="f3972-117">CoreWebView2CreationProperties</span><span class="sxs-lookup"><span data-stu-id="f3972-117">CoreWebView2CreationProperties</span></span>](#corewebview2creationproperties) | <span data-ttu-id="f3972-118">使用所有属性的默认数据创建 CoreWebView2CreationProperties 的新实例。</span><span class="sxs-lookup"><span data-stu-id="f3972-118">Creates a new instance of CoreWebView2CreationProperties with default data for all properties.</span></span>

<span data-ttu-id="f3972-119">它的主要用途是将 WebView2 设置为[CreationProperties](microsoft-web-webview2-wpf-webview2.md) ，以便在隐式初始化期间自定义[WebView2](microsoft-web-webview2-wpf-webview2.md)使用的环境。</span><span class="sxs-lookup"><span data-stu-id="f3972-119">Its main purpose is to be set to [WebView2.CreationProperties](microsoft-web-webview2-wpf-webview2.md) in order to customize the environment used by a [WebView2](microsoft-web-webview2-wpf-webview2.md) during implicit initialization.</span></span> <span data-ttu-id="f3972-120">它也是一个很好的 WPF 集成实用工具，它允许将常用的环境参数用作依赖属性并在标记中创建和使用。</span><span class="sxs-lookup"><span data-stu-id="f3972-120">It is also a nice WPF integration utility which allows commonly used environment parameters to be dependency properties and be created and used in markup.</span></span>

<span data-ttu-id="f3972-121">此类不用于包含所有可能的环境自定义选项。</span><span class="sxs-lookup"><span data-stu-id="f3972-121">This class isn't intended to contain all possible environment customization options.</span></span> <span data-ttu-id="f3972-122">如果你需要对 WebView2 控件使用的环境进行完全控制，则需要通过创建你自己的具有 CoreWebView2Environment 的环境并将其传递到[WebView2](microsoft-web-webview2-wpf-webview2.md)来显式初始化控件，然后*再*将[EnsureCoreWebView2Async Source](microsoft-web-webview2-wpf-webview2.md)属性设置为任何内容。</span><span class="sxs-lookup"><span data-stu-id="f3972-122">If you need complete control over the environment used by a WebView2 control then you'll need to initialize the control explicitly by creating your own environment with CoreWebView2Environment.CreateAsync and passing it to [WebView2.EnsureCoreWebView2Async](microsoft-web-webview2-wpf-webview2.md)*before* you set the [WebView2.Source](microsoft-web-webview2-wpf-webview2.md) property to anything.</span></span> <span data-ttu-id="f3972-123">有关初始化概述，请参阅[WebView2](microsoft-web-webview2-wpf-webview2.md)类文档。</span><span class="sxs-lookup"><span data-stu-id="f3972-123">See the [WebView2](microsoft-web-webview2-wpf-webview2.md) class documentation for an initialization overview.</span></span>

## <span data-ttu-id="f3972-124">成员</span><span class="sxs-lookup"><span data-stu-id="f3972-124">Members</span></span>

#### <span data-ttu-id="f3972-125">BrowserExecutableFolder</span><span class="sxs-lookup"><span data-stu-id="f3972-125">BrowserExecutableFolder</span></span> 

<span data-ttu-id="f3972-126">获取或设置在使用此实例创建环境时要作为 CoreWebView2Environment 的 browserExecutableFolder 参数传递的值。</span><span class="sxs-lookup"><span data-stu-id="f3972-126">Gets or sets the value to pass as the browserExecutableFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>

> <span data-ttu-id="f3972-127">公共字符串[BrowserExecutableFolder](#browserexecutablefolder)</span><span class="sxs-lookup"><span data-stu-id="f3972-127">public string [BrowserExecutableFolder](#browserexecutablefolder)</span></span>

#### <span data-ttu-id="f3972-128">语言</span><span class="sxs-lookup"><span data-stu-id="f3972-128">Language</span></span> 

<span data-ttu-id="f3972-129">获取或设置在使用此实例创建环境时，用于传递到 CoreWebView2Environment 的 CoreWebView2EnvironmentOptions 参数的 Language 属性的值。</span><span class="sxs-lookup"><span data-stu-id="f3972-129">Gets or sets the value to use for the Language property of the CoreWebView2EnvironmentOptions parameter passed to CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>

> <span data-ttu-id="f3972-130">公共字符串[语言](#language)</span><span class="sxs-lookup"><span data-stu-id="f3972-130">public string [Language](#language)</span></span>

#### <span data-ttu-id="f3972-131">UserDataFolder</span><span class="sxs-lookup"><span data-stu-id="f3972-131">UserDataFolder</span></span> 

<span data-ttu-id="f3972-132">获取或设置在使用此实例创建环境时要作为 CoreWebView2Environment 的 userDataFolder 参数传递的值。</span><span class="sxs-lookup"><span data-stu-id="f3972-132">Gets or sets the value to pass as the userDataFolder parameter of CoreWebView2Environment.CreateAsync when creating an environment with this instance.</span></span>

> <span data-ttu-id="f3972-133">公共字符串[UserDataFolder](#userdatafolder)</span><span class="sxs-lookup"><span data-stu-id="f3972-133">public string [UserDataFolder](#userdatafolder)</span></span>

#### <span data-ttu-id="f3972-134">CoreWebView2CreationProperties</span><span class="sxs-lookup"><span data-stu-id="f3972-134">CoreWebView2CreationProperties</span></span> 

<span data-ttu-id="f3972-135">使用所有属性的默认数据创建 CoreWebView2CreationProperties 的新实例。</span><span class="sxs-lookup"><span data-stu-id="f3972-135">Creates a new instance of CoreWebView2CreationProperties with default data for all properties.</span></span>

> <span data-ttu-id="f3972-136">公共[CoreWebView2CreationProperties](#corewebview2creationproperties)（）</span><span class="sxs-lookup"><span data-stu-id="f3972-136">public  [CoreWebView2CreationProperties](#corewebview2creationproperties)()</span></span>
