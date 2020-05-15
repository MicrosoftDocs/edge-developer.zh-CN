---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: fcb17996774ac9a3a0ed32810f095c828a8b5c82
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652898"
---
# <span data-ttu-id="4c322-104">interface ICoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="4c322-104">interface ICoreWebView2EnvironmentOptions</span></span> 

```
interface ICoreWebView2EnvironmentOptions
  : public IUnknown
```

<span data-ttu-id="4c322-105">用于创建 WebView2 环境的选项。</span><span class="sxs-lookup"><span data-stu-id="4c322-105">Options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="4c322-106">摘要</span><span class="sxs-lookup"><span data-stu-id="4c322-106">Summary</span></span>

 <span data-ttu-id="4c322-107">成员</span><span class="sxs-lookup"><span data-stu-id="4c322-107">Members</span></span>                        | <span data-ttu-id="4c322-108">描述</span><span class="sxs-lookup"><span data-stu-id="4c322-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4c322-109">get_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="4c322-109">get_AdditionalBrowserArguments</span></span>](#get_additionalbrowserarguments) | <span data-ttu-id="4c322-110">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="4c322-110">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>
[<span data-ttu-id="4c322-111">get_Language</span><span class="sxs-lookup"><span data-stu-id="4c322-111">get_Language</span></span>](#get_language) | <span data-ttu-id="4c322-112">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="4c322-112">The default language that WebView will run with.</span></span>
[<span data-ttu-id="4c322-113">get_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="4c322-113">get_TargetCompatibleBrowserVersion</span></span>](#get_targetcompatiblebrowserversion) | <span data-ttu-id="4c322-114">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="4c322-114">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>
[<span data-ttu-id="4c322-115">put_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="4c322-115">put_AdditionalBrowserArguments</span></span>](#put_additionalbrowserarguments) | <span data-ttu-id="4c322-116">设置 AdditionalBrowserArguments 属性。</span><span class="sxs-lookup"><span data-stu-id="4c322-116">Set the AdditionalBrowserArguments property.</span></span>
[<span data-ttu-id="4c322-117">put_Language</span><span class="sxs-lookup"><span data-stu-id="4c322-117">put_Language</span></span>](#put_language) | <span data-ttu-id="4c322-118">设置 "语言" 属性。</span><span class="sxs-lookup"><span data-stu-id="4c322-118">Set the Language property.</span></span>
[<span data-ttu-id="4c322-119">put_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="4c322-119">put_TargetCompatibleBrowserVersion</span></span>](#put_targetcompatiblebrowserversion) | <span data-ttu-id="4c322-120">设置 TargetCompatibleBrowserVersion。</span><span class="sxs-lookup"><span data-stu-id="4c322-120">Set the TargetCompatibleBrowserVersion.</span></span>

<span data-ttu-id="4c322-121">默认实现在 WebView2EnvironmentOptions 中提供。</span><span class="sxs-lookup"><span data-stu-id="4c322-121">A default implementation is provided in WebView2EnvironmentOptions.h.</span></span>

```cpp
    auto options = Microsoft::WRL::Make<CoreWebView2EnvironmentOptions>();
    if(!m_language.empty())
        CHECK_FAILURE(options->put_Language(m_language.c_str()));
    HRESULT hr = CreateCoreWebView2EnvironmentWithOptions(
        subFolder, nullptr, options.Get(),
        Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
            this, &AppWindow::OnCreateEnvironmentCompleted)
            .Get());
```

## <span data-ttu-id="4c322-122">成员</span><span class="sxs-lookup"><span data-stu-id="4c322-122">Members</span></span>

#### <span data-ttu-id="4c322-123">get_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="4c322-123">get_AdditionalBrowserArguments</span></span> 

<span data-ttu-id="4c322-124">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="4c322-124">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>

> <span data-ttu-id="4c322-125">public HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments)（LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="4c322-125">public HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments)(LPWSTR \* value)</span></span>

<span data-ttu-id="4c322-126">这些内容将作为命令行的一部分传递到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="4c322-126">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="4c322-127">有关命令行开关的详细信息，请参阅[用标志运行 Chromium](https://aka.ms/RunChromiumWithFlags) ，了解如何切换到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="4c322-127">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="4c322-128">如果使用命令行开关启动应用 `--edge-webview-switches=xxx` ，则该开关的值（上面示例中的 xxx）也将追加到浏览器进程命令行。</span><span class="sxs-lookup"><span data-stu-id="4c322-128">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="4c322-129">某些交换机（如 `--user-data-dir` 内部）和对 Web 视图来说很重要。</span><span class="sxs-lookup"><span data-stu-id="4c322-129">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="4c322-130">即使指定，这些开关也将被忽略。</span><span class="sxs-lookup"><span data-stu-id="4c322-130">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="4c322-131">如果多次指定同一开关，则最后一个参数将获胜。</span><span class="sxs-lookup"><span data-stu-id="4c322-131">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="4c322-132">除了禁用和启用的功能外，不会尝试合并同一开关的不同值。</span><span class="sxs-lookup"><span data-stu-id="4c322-132">There is no attempt to merge the different values of the same switch, except for disabled and enabled features.</span></span> <span data-ttu-id="4c322-133">将使用简单的逻辑合并 "" 和 "" 的功能 `--enable-features` `--disable-features` ：这些功能将是指定功能和内置功能的联合，如果某个功能被禁用，它将从 "启用的功能" 列表中删除。</span><span class="sxs-lookup"><span data-stu-id="4c322-133">The features specified by `--enable-features` and `--disable-features` will be merged with simple logic: the features will be the union of the specified features and built-in features, and if a feature is disabled, it will be removed from the enabled features list.</span></span> <span data-ttu-id="4c322-134">在 `--edge-webview-switches` 处理 additionalBrowserArguments 参数后，将处理应用进程的命令行值。</span><span class="sxs-lookup"><span data-stu-id="4c322-134">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="4c322-135">某些功能在内部禁用且无法启用。</span><span class="sxs-lookup"><span data-stu-id="4c322-135">Certain features are disabled internally and can't be enabled.</span></span> <span data-ttu-id="4c322-136">如果指定开关的分析失败，则将忽略它们。</span><span class="sxs-lookup"><span data-stu-id="4c322-136">If parsing failed for the specified switches, they will be ignored.</span></span> <span data-ttu-id="4c322-137">默认情况下，不执行任何额外的标志即可运行浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="4c322-137">Default is to run browser process with no extra flags.</span></span>

#### <span data-ttu-id="4c322-138">get_Language</span><span class="sxs-lookup"><span data-stu-id="4c322-138">get_Language</span></span> 

<span data-ttu-id="4c322-139">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="4c322-139">The default language that WebView will run with.</span></span>

> <span data-ttu-id="4c322-140">public HRESULT [get_Language](#get_language)（LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="4c322-140">public HRESULT [get_Language](#get_language)(LPWSTR \* value)</span></span>

<span data-ttu-id="4c322-141">它适用于浏览器 Ui，如上下文菜单和对话框。</span><span class="sxs-lookup"><span data-stu-id="4c322-141">It applies to browser UIs like context menu and dialogs.</span></span> <span data-ttu-id="4c322-142">它还适用于 web 视图发送到网站的接受语言 HTTP 头。</span><span class="sxs-lookup"><span data-stu-id="4c322-142">It also applies to the accept-languages HTTP header that WebView sends to web sites.</span></span> <span data-ttu-id="4c322-143">它采用的格式 `language[-country]` `language` 是 iso 639 中的2个字母代码， `country` 是 iso 3166 中的2个字母代码。</span><span class="sxs-lookup"><span data-stu-id="4c322-143">It is in the format of `language[-country]` where `language` is the 2 letter code from ISO 639 and `country` is the 2 letter code from ISO 3166.</span></span>

#### <span data-ttu-id="4c322-144">get_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="4c322-144">get_TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="4c322-145">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="4c322-145">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

> <span data-ttu-id="4c322-146">public HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion)（LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="4c322-146">public HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion)(LPWSTR \* value)</span></span>

<span data-ttu-id="4c322-147">这将默认为与应用程序所使用的 SDK 版本相对应的 Edge WebView2 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="4c322-147">This defaults to the Edge WebView2 Runtime version that corresponds with the version of the SDK the application is using.</span></span> <span data-ttu-id="4c322-148">此值的格式与 BrowserVersionString 属性和其他 BrowserVersion 值的格式相同。</span><span class="sxs-lookup"><span data-stu-id="4c322-148">The format of this value is the same as the format of the BrowserVersionString property and other BrowserVersion values.</span></span> <span data-ttu-id="4c322-149">仅考虑 BrowserVersion 值的版本部分。</span><span class="sxs-lookup"><span data-stu-id="4c322-149">Only the version part of the BrowserVersion value is respected.</span></span> <span data-ttu-id="4c322-150">如果存在信道后缀，则将其忽略。</span><span class="sxs-lookup"><span data-stu-id="4c322-150">The channel suffix, if it exists, is ignored.</span></span> <span data-ttu-id="4c322-151">实际使用的 Edge WebView2 运行时二进制文件的版本可能与指定的 TargetCompatibleBrowserVersion 不同。</span><span class="sxs-lookup"><span data-stu-id="4c322-151">The version of the Edge WebView2 Runtime binaries actually used may be different from the specified TargetCompatibleBrowserVersion.</span></span> <span data-ttu-id="4c322-152">它们只能保证兼容性。</span><span class="sxs-lookup"><span data-stu-id="4c322-152">They are only guaranteed to be compatible.</span></span> <span data-ttu-id="4c322-153">可以在 ICoreWebView2Environment 的 BrowserVersionString 属性上检查实际版本。</span><span class="sxs-lookup"><span data-stu-id="4c322-153">You can check the actual version on the BrowserVersionString property on the ICoreWebView2Environment.</span></span>

#### <span data-ttu-id="4c322-154">put_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="4c322-154">put_AdditionalBrowserArguments</span></span> 

<span data-ttu-id="4c322-155">设置 AdditionalBrowserArguments 属性。</span><span class="sxs-lookup"><span data-stu-id="4c322-155">Set the AdditionalBrowserArguments property.</span></span>

> <span data-ttu-id="4c322-156">public HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments)（LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="4c322-156">public HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments)(LPCWSTR value)</span></span>

#### <span data-ttu-id="4c322-157">put_Language</span><span class="sxs-lookup"><span data-stu-id="4c322-157">put_Language</span></span> 

<span data-ttu-id="4c322-158">设置 "语言" 属性。</span><span class="sxs-lookup"><span data-stu-id="4c322-158">Set the Language property.</span></span>

> <span data-ttu-id="4c322-159">public HRESULT [put_Language](#put_language)（LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="4c322-159">public HRESULT [put_Language](#put_language)(LPCWSTR value)</span></span>

#### <span data-ttu-id="4c322-160">put_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="4c322-160">put_TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="4c322-161">设置 TargetCompatibleBrowserVersion。</span><span class="sxs-lookup"><span data-stu-id="4c322-161">Set the TargetCompatibleBrowserVersion.</span></span>

> <span data-ttu-id="4c322-162">public HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion)（LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="4c322-162">public HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion)(LPCWSTR value)</span></span>

