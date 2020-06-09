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
ms.openlocfilehash: 5626677c3103b4f85ea5d6417beda29337168157
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697649"
---
# <span data-ttu-id="a1439-104">CoreWebView2EnvironmentOptions 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="a1439-104">Microsoft.Web.WebView2.Core.CoreWebView2EnvironmentOptions class</span></span> 

> [!NOTE]
> <span data-ttu-id="a1439-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="a1439-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="a1439-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="a1439-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="a1439-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="a1439-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="a1439-108">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="a1439-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="a1439-109">用于创建 WebView2 环境的选项。</span><span class="sxs-lookup"><span data-stu-id="a1439-109">Options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="a1439-110">摘要</span><span class="sxs-lookup"><span data-stu-id="a1439-110">Summary</span></span>

 <span data-ttu-id="a1439-111">成员</span><span class="sxs-lookup"><span data-stu-id="a1439-111">Members</span></span>                        | <span data-ttu-id="a1439-112">描述</span><span class="sxs-lookup"><span data-stu-id="a1439-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a1439-113">AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="a1439-113">AdditionalBrowserArguments</span></span>](#additionalbrowserarguments) | <span data-ttu-id="a1439-114">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="a1439-114">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>
[<span data-ttu-id="a1439-115">语言</span><span class="sxs-lookup"><span data-stu-id="a1439-115">Language</span></span>](#language) | <span data-ttu-id="a1439-116">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="a1439-116">The default language that WebView will run with.</span></span>
[<span data-ttu-id="a1439-117">TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="a1439-117">TargetCompatibleBrowserVersion</span></span>](#targetcompatiblebrowserversion) | <span data-ttu-id="a1439-118">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="a1439-118">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>
[<span data-ttu-id="a1439-119">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="a1439-119">CoreWebView2EnvironmentOptions</span></span>](#corewebview2environmentoptions) | <span data-ttu-id="a1439-120">初始化 CoreWebView2EnvironmentOptions 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="a1439-120">Initializes a new instance of the CoreWebView2EnvironmentOptions class.</span></span>

<span data-ttu-id="a1439-121">默认实现在 WebView2EnvironmentOptions 中提供。</span><span class="sxs-lookup"><span data-stu-id="a1439-121">A default implementation is provided in WebView2EnvironmentOptions.h.</span></span>

## <span data-ttu-id="a1439-122">成员</span><span class="sxs-lookup"><span data-stu-id="a1439-122">Members</span></span>

#### <span data-ttu-id="a1439-123">AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="a1439-123">AdditionalBrowserArguments</span></span> 

<span data-ttu-id="a1439-124">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="a1439-124">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>

> <span data-ttu-id="a1439-125">公共字符串[AdditionalBrowserArguments](#additionalbrowserarguments)</span><span class="sxs-lookup"><span data-stu-id="a1439-125">public string [AdditionalBrowserArguments](#additionalbrowserarguments)</span></span>

<span data-ttu-id="a1439-126">这些内容将作为命令行的一部分传递到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="a1439-126">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="a1439-127">有关命令行开关的详细信息，请参阅[用标志运行 Chromium](https://aka.ms/RunChromiumWithFlags) ，了解如何切换到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="a1439-127">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="a1439-128">如果使用命令行开关启动应用 `--edge-webview-switches=xxx` ，则该开关的值（上面示例中的 xxx）也将追加到浏览器进程命令行。</span><span class="sxs-lookup"><span data-stu-id="a1439-128">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="a1439-129">某些交换机（如 `--user-data-dir` 内部）和对 Web 视图来说很重要。</span><span class="sxs-lookup"><span data-stu-id="a1439-129">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="a1439-130">即使指定，这些开关也将被忽略。</span><span class="sxs-lookup"><span data-stu-id="a1439-130">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="a1439-131">如果多次指定同一开关，则最后一个参数将获胜。</span><span class="sxs-lookup"><span data-stu-id="a1439-131">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="a1439-132">除了禁用和启用的功能外，不会尝试合并同一开关的不同值。</span><span class="sxs-lookup"><span data-stu-id="a1439-132">There is no attempt to merge the different values of the same switch, except for disabled and enabled features.</span></span> <span data-ttu-id="a1439-133">将使用简单的逻辑合并 "" 和 "" 的功能 `--enable-features` `--disable-features` ：这些功能将是指定功能和内置功能的联合，如果某个功能被禁用，它将从 "启用的功能" 列表中删除。</span><span class="sxs-lookup"><span data-stu-id="a1439-133">The features specified by `--enable-features` and `--disable-features` will be merged with simple logic: the features will be the union of the specified features and built-in features, and if a feature is disabled, it will be removed from the enabled features list.</span></span> <span data-ttu-id="a1439-134">在 `--edge-webview-switches` 处理 additionalBrowserArguments 参数后，将处理应用进程的命令行值。</span><span class="sxs-lookup"><span data-stu-id="a1439-134">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="a1439-135">某些功能在内部禁用且无法启用。</span><span class="sxs-lookup"><span data-stu-id="a1439-135">Certain features are disabled internally and can't be enabled.</span></span> <span data-ttu-id="a1439-136">如果指定开关的分析失败，则将忽略它们。</span><span class="sxs-lookup"><span data-stu-id="a1439-136">If parsing failed for the specified switches, they will be ignored.</span></span> <span data-ttu-id="a1439-137">默认情况下，不执行任何额外的标志即可运行浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="a1439-137">Default is to run browser process with no extra flags.</span></span>

#### <span data-ttu-id="a1439-138">语言</span><span class="sxs-lookup"><span data-stu-id="a1439-138">Language</span></span> 

<span data-ttu-id="a1439-139">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="a1439-139">The default language that WebView will run with.</span></span>

> <span data-ttu-id="a1439-140">公共字符串[语言](#language)</span><span class="sxs-lookup"><span data-stu-id="a1439-140">public string [Language](#language)</span></span>

<span data-ttu-id="a1439-141">它适用于浏览器 Ui，如上下文菜单和对话框。</span><span class="sxs-lookup"><span data-stu-id="a1439-141">It applies to browser UIs like context menu and dialogs.</span></span> <span data-ttu-id="a1439-142">它还适用于 web 视图发送到网站的接受语言 HTTP 头。</span><span class="sxs-lookup"><span data-stu-id="a1439-142">It also applies to the accept-languages HTTP header that WebView sends to web sites.</span></span> <span data-ttu-id="a1439-143">它采用的格式 `language[-country]` `language` 是 iso 639 中的2个字母代码， `country` 是 iso 3166 中的2个字母代码。</span><span class="sxs-lookup"><span data-stu-id="a1439-143">It is in the format of `language[-country]` where `language` is the 2 letter code from ISO 639 and `country` is the 2 letter code from ISO 3166.</span></span>

#### <span data-ttu-id="a1439-144">TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="a1439-144">TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="a1439-145">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="a1439-145">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

> <span data-ttu-id="a1439-146">公共字符串[TargetCompatibleBrowserVersion](#targetcompatiblebrowserversion)</span><span class="sxs-lookup"><span data-stu-id="a1439-146">public string [TargetCompatibleBrowserVersion](#targetcompatiblebrowserversion)</span></span>

<span data-ttu-id="a1439-147">这将默认为与应用程序所使用的 SDK 版本相对应的 Edge WebView2 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="a1439-147">This defaults to the Edge WebView2 Runtime version that corresponds with the version of the SDK the application is using.</span></span> <span data-ttu-id="a1439-148">此值的格式与 BrowserVersionString 属性和其他 BrowserVersion 值的格式相同。</span><span class="sxs-lookup"><span data-stu-id="a1439-148">The format of this value is the same as the format of the BrowserVersionString property and other BrowserVersion values.</span></span> <span data-ttu-id="a1439-149">仅考虑 BrowserVersion 值的版本部分。</span><span class="sxs-lookup"><span data-stu-id="a1439-149">Only the version part of the BrowserVersion value is respected.</span></span> <span data-ttu-id="a1439-150">如果存在信道后缀，则将其忽略。</span><span class="sxs-lookup"><span data-stu-id="a1439-150">The channel suffix, if it exists, is ignored.</span></span> <span data-ttu-id="a1439-151">实际使用的 Edge WebView2 运行时二进制文件的版本可能与指定的 TargetCompatibleBrowserVersion 不同。</span><span class="sxs-lookup"><span data-stu-id="a1439-151">The version of the Edge WebView2 Runtime binaries actually used may be different from the specified TargetCompatibleBrowserVersion.</span></span> <span data-ttu-id="a1439-152">它们只能保证兼容性。</span><span class="sxs-lookup"><span data-stu-id="a1439-152">They are only guaranteed to be compatible.</span></span> <span data-ttu-id="a1439-153">可以在 CoreWebView2Environment 的 BrowserVersionString 属性上检查实际版本。</span><span class="sxs-lookup"><span data-stu-id="a1439-153">You can check the actual version on the BrowserVersionString property on the CoreWebView2Environment.</span></span>

#### <span data-ttu-id="a1439-154">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="a1439-154">CoreWebView2EnvironmentOptions</span></span> 

<span data-ttu-id="a1439-155">初始化 CoreWebView2EnvironmentOptions 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="a1439-155">Initializes a new instance of the CoreWebView2EnvironmentOptions class.</span></span>

> <span data-ttu-id="a1439-156">公共[CoreWebView2EnvironmentOptions](#corewebview2environmentoptions)（字符串 additionalBrowserArguments，字符串语言，字符串 targetCompatibleBrowserVersion）</span><span class="sxs-lookup"><span data-stu-id="a1439-156">public  [CoreWebView2EnvironmentOptions](#corewebview2environmentoptions)(string additionalBrowserArguments, string language, string targetCompatibleBrowserVersion)</span></span>

##### <span data-ttu-id="a1439-157">参数</span><span class="sxs-lookup"><span data-stu-id="a1439-157">Parameters</span></span>
* `additionalBrowserArguments` <span data-ttu-id="a1439-158">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="a1439-158">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span> 

* `language` <span data-ttu-id="a1439-159">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="a1439-159">The default language that WebView will run with.</span></span> 

* `targetCompatibleBrowserVersion` <span data-ttu-id="a1439-160">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="a1439-160">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

