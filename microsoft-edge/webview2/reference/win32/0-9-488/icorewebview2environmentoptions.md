---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2EnvironmentOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 1cac030b27164222bd1c11240cf4a92aee91ff01
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880673"
---
# <span data-ttu-id="57588-104">0.9.515-接口 ICoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="57588-104">0.9.515 - interface ICoreWebView2EnvironmentOptions</span></span> 

> [!NOTE]
> <span data-ttu-id="57588-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="57588-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="57588-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="57588-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2EnvironmentOptions
  : public IUnknown
```

<span data-ttu-id="57588-107">用于创建 WebView2 环境的选项。</span><span class="sxs-lookup"><span data-stu-id="57588-107">Options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="57588-108">摘要</span><span class="sxs-lookup"><span data-stu-id="57588-108">Summary</span></span>

 <span data-ttu-id="57588-109">成员</span><span class="sxs-lookup"><span data-stu-id="57588-109">Members</span></span>                        | <span data-ttu-id="57588-110">描述</span><span class="sxs-lookup"><span data-stu-id="57588-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="57588-111">get_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="57588-111">get_AdditionalBrowserArguments</span></span>](#get_additionalbrowserarguments) | <span data-ttu-id="57588-112">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="57588-112">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>
[<span data-ttu-id="57588-113">get_Language</span><span class="sxs-lookup"><span data-stu-id="57588-113">get_Language</span></span>](#get_language) | <span data-ttu-id="57588-114">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="57588-114">The default language that WebView will run with.</span></span>
[<span data-ttu-id="57588-115">get_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="57588-115">get_TargetCompatibleBrowserVersion</span></span>](#get_targetcompatiblebrowserversion) | <span data-ttu-id="57588-116">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="57588-116">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>
[<span data-ttu-id="57588-117">put_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="57588-117">put_AdditionalBrowserArguments</span></span>](#put_additionalbrowserarguments) | <span data-ttu-id="57588-118">设置 AdditionalBrowserArguments 属性。</span><span class="sxs-lookup"><span data-stu-id="57588-118">Set the AdditionalBrowserArguments property.</span></span>
[<span data-ttu-id="57588-119">put_Language</span><span class="sxs-lookup"><span data-stu-id="57588-119">put_Language</span></span>](#put_language) | <span data-ttu-id="57588-120">设置 "语言" 属性。</span><span class="sxs-lookup"><span data-stu-id="57588-120">Set the Language property.</span></span>
[<span data-ttu-id="57588-121">put_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="57588-121">put_TargetCompatibleBrowserVersion</span></span>](#put_targetcompatiblebrowserversion) | <span data-ttu-id="57588-122">设置 TargetCompatibleBrowserVersion。</span><span class="sxs-lookup"><span data-stu-id="57588-122">Set the TargetCompatibleBrowserVersion.</span></span>

<span data-ttu-id="57588-123">默认实现在 WebView2EnvironmentOptions 中提供。</span><span class="sxs-lookup"><span data-stu-id="57588-123">A default implementation is provided in WebView2EnvironmentOptions.h.</span></span>

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

## <span data-ttu-id="57588-124">成员</span><span class="sxs-lookup"><span data-stu-id="57588-124">Members</span></span>

#### <span data-ttu-id="57588-125">get_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="57588-125">get_AdditionalBrowserArguments</span></span> 

<span data-ttu-id="57588-126">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="57588-126">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>

> <span data-ttu-id="57588-127">public HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments)（LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="57588-127">public HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments)(LPWSTR \* value)</span></span>

<span data-ttu-id="57588-128">这些内容将作为命令行的一部分传递到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="57588-128">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="57588-129">有关命令行开关的详细信息，请参阅[用标志运行 Chromium](https://aka.ms/RunChromiumWithFlags) ，了解如何切换到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="57588-129">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="57588-130">如果使用命令行开关启动应用 `--edge-webview-switches=xxx` ，则该开关的值（上面示例中的 xxx）也将追加到浏览器进程命令行。</span><span class="sxs-lookup"><span data-stu-id="57588-130">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="57588-131">某些交换机（如 `--user-data-dir` 内部）和对 Web 视图来说很重要。</span><span class="sxs-lookup"><span data-stu-id="57588-131">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="57588-132">即使指定，这些开关也将被忽略。</span><span class="sxs-lookup"><span data-stu-id="57588-132">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="57588-133">如果多次指定同一开关，则最后一个参数将获胜。</span><span class="sxs-lookup"><span data-stu-id="57588-133">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="57588-134">除了禁用和启用的功能外，不会尝试合并同一开关的不同值。</span><span class="sxs-lookup"><span data-stu-id="57588-134">There is no attempt to merge the different values of the same switch, except for disabled and enabled features.</span></span> <span data-ttu-id="57588-135">将使用简单的逻辑合并 "" 和 "" 的功能 `--enable-features` `--disable-features` ：这些功能将是指定功能和内置功能的联合，如果某个功能被禁用，它将从 "启用的功能" 列表中删除。</span><span class="sxs-lookup"><span data-stu-id="57588-135">The features specified by `--enable-features` and `--disable-features` will be merged with simple logic: the features will be the union of the specified features and built-in features, and if a feature is disabled, it will be removed from the enabled features list.</span></span> <span data-ttu-id="57588-136">在 `--edge-webview-switches` 处理 additionalBrowserArguments 参数后，将处理应用进程的命令行值。</span><span class="sxs-lookup"><span data-stu-id="57588-136">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="57588-137">某些功能在内部禁用且无法启用。</span><span class="sxs-lookup"><span data-stu-id="57588-137">Certain features are disabled internally and can't be enabled.</span></span> <span data-ttu-id="57588-138">如果指定开关的分析失败，则将忽略它们。</span><span class="sxs-lookup"><span data-stu-id="57588-138">If parsing failed for the specified switches, they will be ignored.</span></span> <span data-ttu-id="57588-139">默认情况下，不执行任何额外的标志即可运行浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="57588-139">Default is to run browser process with no extra flags.</span></span>

#### <span data-ttu-id="57588-140">get_Language</span><span class="sxs-lookup"><span data-stu-id="57588-140">get_Language</span></span> 

<span data-ttu-id="57588-141">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="57588-141">The default language that WebView will run with.</span></span>

> <span data-ttu-id="57588-142">public HRESULT [get_Language](#get_language)（LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="57588-142">public HRESULT [get_Language](#get_language)(LPWSTR \* value)</span></span>

<span data-ttu-id="57588-143">它适用于浏览器 Ui，如上下文菜单和对话框。</span><span class="sxs-lookup"><span data-stu-id="57588-143">It applies to browser UIs like context menu and dialogs.</span></span> <span data-ttu-id="57588-144">它还适用于 web 视图发送到网站的接受语言 HTTP 头。</span><span class="sxs-lookup"><span data-stu-id="57588-144">It also applies to the accept-languages HTTP header that WebView sends to web sites.</span></span> <span data-ttu-id="57588-145">它采用的格式 `language[-country]` `language` 是 iso 639 中的2个字母代码， `country` 是 iso 3166 中的2个字母代码。</span><span class="sxs-lookup"><span data-stu-id="57588-145">It is in the format of `language[-country]` where `language` is the 2 letter code from ISO 639 and `country` is the 2 letter code from ISO 3166.</span></span>

#### <span data-ttu-id="57588-146">get_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="57588-146">get_TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="57588-147">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="57588-147">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

> <span data-ttu-id="57588-148">public HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion)（LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="57588-148">public HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion)(LPWSTR \* value)</span></span>

<span data-ttu-id="57588-149">这将默认为与应用程序所使用的 SDK 版本相对应的 Edge WebView2 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="57588-149">This defaults to the Edge WebView2 Runtime version that corresponds with the version of the SDK the application is using.</span></span> <span data-ttu-id="57588-150">此值的格式与 BrowserVersionString 属性和其他 BrowserVersion 值的格式相同。</span><span class="sxs-lookup"><span data-stu-id="57588-150">The format of this value is the same as the format of the BrowserVersionString property and other BrowserVersion values.</span></span> <span data-ttu-id="57588-151">仅考虑 BrowserVersion 值的版本部分。</span><span class="sxs-lookup"><span data-stu-id="57588-151">Only the version part of the BrowserVersion value is respected.</span></span> <span data-ttu-id="57588-152">如果存在信道后缀，则将其忽略。</span><span class="sxs-lookup"><span data-stu-id="57588-152">The channel suffix, if it exists, is ignored.</span></span> <span data-ttu-id="57588-153">实际使用的 Edge WebView2 运行时二进制文件的版本可能与指定的 TargetCompatibleBrowserVersion 不同。</span><span class="sxs-lookup"><span data-stu-id="57588-153">The version of the Edge WebView2 Runtime binaries actually used may be different from the specified TargetCompatibleBrowserVersion.</span></span> <span data-ttu-id="57588-154">它们只能保证兼容性。</span><span class="sxs-lookup"><span data-stu-id="57588-154">They are only guaranteed to be compatible.</span></span> <span data-ttu-id="57588-155">可以在 ICoreWebView2Environment 的 BrowserVersionString 属性上检查实际版本。</span><span class="sxs-lookup"><span data-stu-id="57588-155">You can check the actual version on the BrowserVersionString property on the ICoreWebView2Environment.</span></span>

#### <span data-ttu-id="57588-156">put_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="57588-156">put_AdditionalBrowserArguments</span></span> 

<span data-ttu-id="57588-157">设置 AdditionalBrowserArguments 属性。</span><span class="sxs-lookup"><span data-stu-id="57588-157">Set the AdditionalBrowserArguments property.</span></span>

> <span data-ttu-id="57588-158">public HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments)（LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="57588-158">public HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments)(LPCWSTR value)</span></span>

#### <span data-ttu-id="57588-159">put_Language</span><span class="sxs-lookup"><span data-stu-id="57588-159">put_Language</span></span> 

<span data-ttu-id="57588-160">设置 "语言" 属性。</span><span class="sxs-lookup"><span data-stu-id="57588-160">Set the Language property.</span></span>

> <span data-ttu-id="57588-161">public HRESULT [put_Language](#put_language)（LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="57588-161">public HRESULT [put_Language](#put_language)(LPCWSTR value)</span></span>

#### <span data-ttu-id="57588-162">put_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="57588-162">put_TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="57588-163">设置 TargetCompatibleBrowserVersion。</span><span class="sxs-lookup"><span data-stu-id="57588-163">Set the TargetCompatibleBrowserVersion.</span></span>

> <span data-ttu-id="57588-164">public HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion)（LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="57588-164">public HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion)(LPCWSTR value)</span></span>

