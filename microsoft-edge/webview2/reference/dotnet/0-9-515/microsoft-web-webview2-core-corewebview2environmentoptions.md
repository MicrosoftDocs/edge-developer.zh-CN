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
ms.openlocfilehash: d29d5a716bb52d2e4e28fc1acf0f3bbf9874584b
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653111"
---
# <span data-ttu-id="65121-104">CoreWebView2EnvironmentOptions 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="65121-104">Microsoft.Web.WebView2.Core.CoreWebView2EnvironmentOptions class</span></span> 

<span data-ttu-id="65121-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="65121-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="65121-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="65121-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="65121-107">用于创建 WebView2 环境的选项。</span><span class="sxs-lookup"><span data-stu-id="65121-107">Options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="65121-108">摘要</span><span class="sxs-lookup"><span data-stu-id="65121-108">Summary</span></span>

 <span data-ttu-id="65121-109">成员</span><span class="sxs-lookup"><span data-stu-id="65121-109">Members</span></span>                        | <span data-ttu-id="65121-110">描述</span><span class="sxs-lookup"><span data-stu-id="65121-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="65121-111">AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="65121-111">AdditionalBrowserArguments</span></span>](#additionalbrowserarguments) | <span data-ttu-id="65121-112">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="65121-112">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>
[<span data-ttu-id="65121-113">语言</span><span class="sxs-lookup"><span data-stu-id="65121-113">Language</span></span>](#language) | <span data-ttu-id="65121-114">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="65121-114">The default language that WebView will run with.</span></span>
[<span data-ttu-id="65121-115">TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="65121-115">TargetCompatibleBrowserVersion</span></span>](#targetcompatiblebrowserversion) | <span data-ttu-id="65121-116">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="65121-116">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>
[<span data-ttu-id="65121-117">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="65121-117">CoreWebView2EnvironmentOptions</span></span>](#corewebview2environmentoptions) | <span data-ttu-id="65121-118">初始化 CoreWebView2EnvironmentOptions 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="65121-118">Initializes a new instance of the CoreWebView2EnvironmentOptions class.</span></span>

<span data-ttu-id="65121-119">默认实现在 WebView2EnvironmentOptions 中提供。</span><span class="sxs-lookup"><span data-stu-id="65121-119">A default implementation is provided in WebView2EnvironmentOptions.h.</span></span>

## <span data-ttu-id="65121-120">成员</span><span class="sxs-lookup"><span data-stu-id="65121-120">Members</span></span>

#### <span data-ttu-id="65121-121">AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="65121-121">AdditionalBrowserArguments</span></span> 

<span data-ttu-id="65121-122">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="65121-122">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>

> <span data-ttu-id="65121-123">公共字符串[AdditionalBrowserArguments](#additionalbrowserarguments)</span><span class="sxs-lookup"><span data-stu-id="65121-123">public string [AdditionalBrowserArguments](#additionalbrowserarguments)</span></span>

<span data-ttu-id="65121-124">这些内容将作为命令行的一部分传递到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="65121-124">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="65121-125">有关命令行开关的详细信息，请参阅[用标志运行 Chromium](https://aka.ms/RunChromiumWithFlags) ，了解如何切换到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="65121-125">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="65121-126">如果使用命令行开关启动应用 `--edge-webview-switches=xxx` ，则该开关的值（上面示例中的 xxx）也将追加到浏览器进程命令行。</span><span class="sxs-lookup"><span data-stu-id="65121-126">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="65121-127">某些交换机（如 `--user-data-dir` 内部）和对 Web 视图来说很重要。</span><span class="sxs-lookup"><span data-stu-id="65121-127">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="65121-128">即使指定，这些开关也将被忽略。</span><span class="sxs-lookup"><span data-stu-id="65121-128">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="65121-129">如果多次指定同一开关，则最后一个参数将获胜。</span><span class="sxs-lookup"><span data-stu-id="65121-129">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="65121-130">除了禁用和启用的功能外，不会尝试合并同一开关的不同值。</span><span class="sxs-lookup"><span data-stu-id="65121-130">There is no attempt to merge the different values of the same switch, except for disabled and enabled features.</span></span> <span data-ttu-id="65121-131">将使用简单的逻辑合并 "" 和 "" 的功能 `--enable-features` `--disable-features` ：这些功能将是指定功能和内置功能的联合，如果某个功能被禁用，它将从 "启用的功能" 列表中删除。</span><span class="sxs-lookup"><span data-stu-id="65121-131">The features specified by `--enable-features` and `--disable-features` will be merged with simple logic: the features will be the union of the specified features and built-in features, and if a feature is disabled, it will be removed from the enabled features list.</span></span> <span data-ttu-id="65121-132">在 `--edge-webview-switches` 处理 additionalBrowserArguments 参数后，将处理应用进程的命令行值。</span><span class="sxs-lookup"><span data-stu-id="65121-132">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="65121-133">某些功能在内部禁用且无法启用。</span><span class="sxs-lookup"><span data-stu-id="65121-133">Certain features are disabled internally and can't be enabled.</span></span> <span data-ttu-id="65121-134">如果指定开关的分析失败，则将忽略它们。</span><span class="sxs-lookup"><span data-stu-id="65121-134">If parsing failed for the specified switches, they will be ignored.</span></span> <span data-ttu-id="65121-135">默认情况下，不执行任何额外的标志即可运行浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="65121-135">Default is to run browser process with no extra flags.</span></span>

#### <span data-ttu-id="65121-136">语言</span><span class="sxs-lookup"><span data-stu-id="65121-136">Language</span></span> 

<span data-ttu-id="65121-137">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="65121-137">The default language that WebView will run with.</span></span>

> <span data-ttu-id="65121-138">公共字符串[语言](#language)</span><span class="sxs-lookup"><span data-stu-id="65121-138">public string [Language](#language)</span></span>

<span data-ttu-id="65121-139">它适用于浏览器 Ui，如上下文菜单和对话框。</span><span class="sxs-lookup"><span data-stu-id="65121-139">It applies to browser UIs like context menu and dialogs.</span></span> <span data-ttu-id="65121-140">它还适用于 web 视图发送到网站的接受语言 HTTP 头。</span><span class="sxs-lookup"><span data-stu-id="65121-140">It also applies to the accept-languages HTTP header that WebView sends to web sites.</span></span> <span data-ttu-id="65121-141">它采用的格式 `language[-country]` `language` 是 iso 639 中的2个字母代码， `country` 是 iso 3166 中的2个字母代码。</span><span class="sxs-lookup"><span data-stu-id="65121-141">It is in the format of `language[-country]` where `language` is the 2 letter code from ISO 639 and `country` is the 2 letter code from ISO 3166.</span></span>

#### <span data-ttu-id="65121-142">TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="65121-142">TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="65121-143">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="65121-143">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

> <span data-ttu-id="65121-144">公共字符串[TargetCompatibleBrowserVersion](#targetcompatiblebrowserversion)</span><span class="sxs-lookup"><span data-stu-id="65121-144">public string [TargetCompatibleBrowserVersion](#targetcompatiblebrowserversion)</span></span>

<span data-ttu-id="65121-145">这将默认为与应用程序所使用的 SDK 版本相对应的 Edge WebView2 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="65121-145">This defaults to the Edge WebView2 Runtime version that corresponds with the version of the SDK the application is using.</span></span> <span data-ttu-id="65121-146">此值的格式与 BrowserVersionString 属性和其他 BrowserVersion 值的格式相同。</span><span class="sxs-lookup"><span data-stu-id="65121-146">The format of this value is the same as the format of the BrowserVersionString property and other BrowserVersion values.</span></span> <span data-ttu-id="65121-147">仅考虑 BrowserVersion 值的版本部分。</span><span class="sxs-lookup"><span data-stu-id="65121-147">Only the version part of the BrowserVersion value is respected.</span></span> <span data-ttu-id="65121-148">如果存在信道后缀，则将其忽略。</span><span class="sxs-lookup"><span data-stu-id="65121-148">The channel suffix, if it exists, is ignored.</span></span> <span data-ttu-id="65121-149">实际使用的 Edge WebView2 运行时二进制文件的版本可能与指定的 TargetCompatibleBrowserVersion 不同。</span><span class="sxs-lookup"><span data-stu-id="65121-149">The version of the Edge WebView2 Runtime binaries actually used may be different from the specified TargetCompatibleBrowserVersion.</span></span> <span data-ttu-id="65121-150">它们只能保证兼容性。</span><span class="sxs-lookup"><span data-stu-id="65121-150">They are only guaranteed to be compatible.</span></span> <span data-ttu-id="65121-151">可以在 CoreWebView2Environment 的 BrowserVersionString 属性上检查实际版本。</span><span class="sxs-lookup"><span data-stu-id="65121-151">You can check the actual version on the BrowserVersionString property on the CoreWebView2Environment.</span></span>

#### <span data-ttu-id="65121-152">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="65121-152">CoreWebView2EnvironmentOptions</span></span> 

<span data-ttu-id="65121-153">初始化 CoreWebView2EnvironmentOptions 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="65121-153">Initializes a new instance of the CoreWebView2EnvironmentOptions class.</span></span>

> <span data-ttu-id="65121-154">公共[CoreWebView2EnvironmentOptions](#corewebview2environmentoptions)（字符串 additionalBrowserArguments，字符串语言，字符串 targetCompatibleBrowserVersion）</span><span class="sxs-lookup"><span data-stu-id="65121-154">public  [CoreWebView2EnvironmentOptions](#corewebview2environmentoptions)(string additionalBrowserArguments, string language, string targetCompatibleBrowserVersion)</span></span>

##### <span data-ttu-id="65121-155">参数</span><span class="sxs-lookup"><span data-stu-id="65121-155">Parameters</span></span>
* `additionalBrowserArguments` <span data-ttu-id="65121-156">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="65121-156">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span> 

* `language` <span data-ttu-id="65121-157">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="65121-157">The default language that WebView will run with.</span></span> 

* `targetCompatibleBrowserVersion` <span data-ttu-id="65121-158">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="65121-158">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

