---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2EnvironmentOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2EnvironmentOptions
ms.openlocfilehash: a4e51dc08e2c31664cb77e4e6ee0136bab2f261d
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011789"
---
# <span data-ttu-id="3a86a-104">interface ICoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="3a86a-104">interface ICoreWebView2EnvironmentOptions</span></span> 

```
interface ICoreWebView2EnvironmentOptions
  : public IUnknown
```

<span data-ttu-id="3a86a-105">用于创建 WebView2 环境的选项。</span><span class="sxs-lookup"><span data-stu-id="3a86a-105">Options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="3a86a-106">摘要</span><span class="sxs-lookup"><span data-stu-id="3a86a-106">Summary</span></span>

 <span data-ttu-id="3a86a-107">成员</span><span class="sxs-lookup"><span data-stu-id="3a86a-107">Members</span></span>                        | <span data-ttu-id="3a86a-108">描述</span><span class="sxs-lookup"><span data-stu-id="3a86a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3a86a-109">get_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="3a86a-109">get_AdditionalBrowserArguments</span></span>](#get_additionalbrowserarguments) | <span data-ttu-id="3a86a-110">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="3a86a-110">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>
[<span data-ttu-id="3a86a-111">get_AllowSingleSignOnUsingOSPrimaryAccount</span><span class="sxs-lookup"><span data-stu-id="3a86a-111">get_AllowSingleSignOnUsingOSPrimaryAccount</span></span>](#get_allowsinglesignonusingosprimaryaccount) | <span data-ttu-id="3a86a-112">AllowSingleSignOnUsingOSPrimaryAccount 属性用于在使用 windows 帐户登录的 Microsoft 帐户中使用已登录的 Windows 帐户在 web 站点内使用已登录的 Windows 帐户进行单一)  (登录，并使用与 Windows 帐户中的登录相关联的 Microsoft 帐户在 web 站点上使用单一登录来启用单一登录。</span><span class="sxs-lookup"><span data-stu-id="3a86a-112">The AllowSingleSignOnUsingOSPrimaryAccount property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>
[<span data-ttu-id="3a86a-113">get_Language</span><span class="sxs-lookup"><span data-stu-id="3a86a-113">get_Language</span></span>](#get_language) | <span data-ttu-id="3a86a-114">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="3a86a-114">The default language that WebView will run with.</span></span>
[<span data-ttu-id="3a86a-115">get_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="3a86a-115">get_TargetCompatibleBrowserVersion</span></span>](#get_targetcompatiblebrowserversion) | <span data-ttu-id="3a86a-116">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="3a86a-116">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>
[<span data-ttu-id="3a86a-117">put_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="3a86a-117">put_AdditionalBrowserArguments</span></span>](#put_additionalbrowserarguments) | <span data-ttu-id="3a86a-118">设置 AdditionalBrowserArguments 属性。</span><span class="sxs-lookup"><span data-stu-id="3a86a-118">Set the AdditionalBrowserArguments property.</span></span>
[<span data-ttu-id="3a86a-119">put_AllowSingleSignOnUsingOSPrimaryAccount</span><span class="sxs-lookup"><span data-stu-id="3a86a-119">put_AllowSingleSignOnUsingOSPrimaryAccount</span></span>](#put_allowsinglesignonusingosprimaryaccount) | <span data-ttu-id="3a86a-120">设置 AllowSingleSignOnUsingOSPrimaryAccount 属性。</span><span class="sxs-lookup"><span data-stu-id="3a86a-120">Set the AllowSingleSignOnUsingOSPrimaryAccount property.</span></span>
[<span data-ttu-id="3a86a-121">put_Language</span><span class="sxs-lookup"><span data-stu-id="3a86a-121">put_Language</span></span>](#put_language) | <span data-ttu-id="3a86a-122">设置 "语言" 属性。</span><span class="sxs-lookup"><span data-stu-id="3a86a-122">Set the Language property.</span></span>
[<span data-ttu-id="3a86a-123">put_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="3a86a-123">put_TargetCompatibleBrowserVersion</span></span>](#put_targetcompatiblebrowserversion) | <span data-ttu-id="3a86a-124">设置 TargetCompatibleBrowserVersion 属性。</span><span class="sxs-lookup"><span data-stu-id="3a86a-124">Set the TargetCompatibleBrowserVersion property.</span></span>

<span data-ttu-id="3a86a-125">默认实现在 WebView2EnvironmentOptions 中提供。</span><span class="sxs-lookup"><span data-stu-id="3a86a-125">A default implementation is provided in WebView2EnvironmentOptions.h.</span></span>

```cpp
    auto options = Microsoft::WRL::Make<CoreWebView2EnvironmentOptions>();
    CHECK_FAILURE(options->put_AllowSingleSignOnUsingOSPrimaryAccount(
        m_AADSSOEnabled ? TRUE : FALSE));
    if (!m_language.empty())
        CHECK_FAILURE(options->put_Language(m_language.c_str()));
    HRESULT hr = CreateCoreWebView2EnvironmentWithOptions(
        subFolder, nullptr, options.Get(),
        Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
            this, &AppWindow::OnCreateEnvironmentCompleted)
            .Get());
```

## <span data-ttu-id="3a86a-126">成员</span><span class="sxs-lookup"><span data-stu-id="3a86a-126">Members</span></span>

#### <span data-ttu-id="3a86a-127">get_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="3a86a-127">get_AdditionalBrowserArguments</span></span> 

<span data-ttu-id="3a86a-128">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="3a86a-128">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>

> <span data-ttu-id="3a86a-129">公共 HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments) (LPWSTR \* 值) </span><span class="sxs-lookup"><span data-stu-id="3a86a-129">public HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments)(LPWSTR \* value)</span></span>

<span data-ttu-id="3a86a-130">这些内容将作为命令行的一部分传递到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="3a86a-130">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="3a86a-131">有关命令行开关的详细信息，请参阅 [用标志运行 Chromium](https://aka.ms/RunChromiumWithFlags) ，了解如何切换到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="3a86a-131">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="3a86a-132">如果使用命令行开关启动应用 `--edge-webview-switches=xxx` ，则上述) 示例中 (xxx 的开关的值也将追加到浏览器进程命令行。</span><span class="sxs-lookup"><span data-stu-id="3a86a-132">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="3a86a-133">某些交换机（如 `--user-data-dir` 内部）和对 Web 视图来说很重要。</span><span class="sxs-lookup"><span data-stu-id="3a86a-133">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="3a86a-134">即使指定，这些开关也将被忽略。</span><span class="sxs-lookup"><span data-stu-id="3a86a-134">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="3a86a-135">如果多次指定同一开关，则最后一个参数将获胜。</span><span class="sxs-lookup"><span data-stu-id="3a86a-135">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="3a86a-136">除了禁用和启用的功能外，不会尝试合并同一开关的不同值。</span><span class="sxs-lookup"><span data-stu-id="3a86a-136">There is no attempt to merge the different values of the same switch, except for disabled and enabled features.</span></span> <span data-ttu-id="3a86a-137">将使用简单的逻辑合并 "" 和 "" 的功能 `--enable-features` `--disable-features` ：这些功能将是指定功能和内置功能的联合，如果某个功能被禁用，它将从 "启用的功能" 列表中删除。</span><span class="sxs-lookup"><span data-stu-id="3a86a-137">The features specified by `--enable-features` and `--disable-features` will be merged with simple logic: the features will be the union of the specified features and built-in features, and if a feature is disabled, it will be removed from the enabled features list.</span></span> <span data-ttu-id="3a86a-138">在 `--edge-webview-switches` 处理 additionalBrowserArguments 参数后，将处理应用进程的命令行值。</span><span class="sxs-lookup"><span data-stu-id="3a86a-138">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="3a86a-139">某些功能在内部禁用且无法启用。</span><span class="sxs-lookup"><span data-stu-id="3a86a-139">Certain features are disabled internally and can't be enabled.</span></span> <span data-ttu-id="3a86a-140">如果指定开关的分析失败，则将忽略它们。</span><span class="sxs-lookup"><span data-stu-id="3a86a-140">If parsing failed for the specified switches, they will be ignored.</span></span> <span data-ttu-id="3a86a-141">默认情况下，不执行任何额外的标志即可运行浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="3a86a-141">Default is to run browser process with no extra flags.</span></span>

#### <span data-ttu-id="3a86a-142">get_AllowSingleSignOnUsingOSPrimaryAccount</span><span class="sxs-lookup"><span data-stu-id="3a86a-142">get_AllowSingleSignOnUsingOSPrimaryAccount</span></span> 

<span data-ttu-id="3a86a-143">AllowSingleSignOnUsingOSPrimaryAccount 属性用于在使用 windows 帐户登录的 Microsoft 帐户中使用已登录的 Windows 帐户在 web 站点内使用已登录的 Windows 帐户进行单一)  (登录，并使用与 Windows 帐户中的登录相关联的 Microsoft 帐户在 web 站点上使用单一登录来启用单一登录。</span><span class="sxs-lookup"><span data-stu-id="3a86a-143">The AllowSingleSignOnUsingOSPrimaryAccount property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>

> <span data-ttu-id="3a86a-144">公共 HRESULT [get_AllowSingleSignOnUsingOSPrimaryAccount](#get_allowsinglesignonusingosprimaryaccount) (BOOL \* 允许) </span><span class="sxs-lookup"><span data-stu-id="3a86a-144">public HRESULT [get_AllowSingleSignOnUsingOSPrimaryAccount](#get_allowsinglesignonusingosprimaryaccount)(BOOL \* allow)</span></span>

<span data-ttu-id="3a86a-145">默认值为 "已禁用"。</span><span class="sxs-lookup"><span data-stu-id="3a86a-145">Default is disabled.</span></span> <span data-ttu-id="3a86a-146">通用 Windows 平台应用还必须声明 enterpriseCloudSSO [受限功能](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities) 才能使单一登录正常工作。</span><span class="sxs-lookup"><span data-stu-id="3a86a-146">Universal Windows Platform apps must also declare enterpriseCloudSSO [restricted capability](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities) for the single sign on to work.</span></span>

#### <span data-ttu-id="3a86a-147">get_Language</span><span class="sxs-lookup"><span data-stu-id="3a86a-147">get_Language</span></span> 

<span data-ttu-id="3a86a-148">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="3a86a-148">The default language that WebView will run with.</span></span>

> <span data-ttu-id="3a86a-149">公共 HRESULT [get_Language](#get_language) (LPWSTR \* 值) </span><span class="sxs-lookup"><span data-stu-id="3a86a-149">public HRESULT [get_Language](#get_language)(LPWSTR \* value)</span></span>

<span data-ttu-id="3a86a-150">它适用于浏览器 Ui，如上下文菜单和对话框。</span><span class="sxs-lookup"><span data-stu-id="3a86a-150">It applies to browser UIs like context menu and dialogs.</span></span> <span data-ttu-id="3a86a-151">它还适用于 web 视图发送到网站的接受语言 HTTP 头。</span><span class="sxs-lookup"><span data-stu-id="3a86a-151">It also applies to the accept-languages HTTP header that WebView sends to web sites.</span></span> <span data-ttu-id="3a86a-152">它采用的格式 `language[-country]` `language` 是 iso 639 中的2个字母代码， `country` 是 iso 3166 中的2个字母代码。</span><span class="sxs-lookup"><span data-stu-id="3a86a-152">It is in the format of `language[-country]` where `language` is the 2 letter code from ISO 639 and `country` is the 2 letter code from ISO 3166.</span></span>

#### <span data-ttu-id="3a86a-153">get_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="3a86a-153">get_TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="3a86a-154">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="3a86a-154">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

> <span data-ttu-id="3a86a-155">公共 HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion) (LPWSTR \* 值) </span><span class="sxs-lookup"><span data-stu-id="3a86a-155">public HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion)(LPWSTR \* value)</span></span>

<span data-ttu-id="3a86a-156">这将默认为与应用程序所使用的 SDK 版本相对应的 Edge WebView2 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="3a86a-156">This defaults to the Edge WebView2 Runtime version that corresponds with the version of the SDK the application is using.</span></span> <span data-ttu-id="3a86a-157">此值的格式与 BrowserVersionString 属性和其他 BrowserVersion 值的格式相同。</span><span class="sxs-lookup"><span data-stu-id="3a86a-157">The format of this value is the same as the format of the BrowserVersionString property and other BrowserVersion values.</span></span> <span data-ttu-id="3a86a-158">仅考虑 BrowserVersion 值的版本部分。</span><span class="sxs-lookup"><span data-stu-id="3a86a-158">Only the version part of the BrowserVersion value is respected.</span></span> <span data-ttu-id="3a86a-159">如果存在信道后缀，则将其忽略。</span><span class="sxs-lookup"><span data-stu-id="3a86a-159">The channel suffix, if it exists, is ignored.</span></span> <span data-ttu-id="3a86a-160">实际使用的 Edge WebView2 运行时二进制文件的版本可能与指定的 TargetCompatibleBrowserVersion 不同。</span><span class="sxs-lookup"><span data-stu-id="3a86a-160">The version of the Edge WebView2 Runtime binaries actually used may be different from the specified TargetCompatibleBrowserVersion.</span></span> <span data-ttu-id="3a86a-161">它们只能保证兼容性。</span><span class="sxs-lookup"><span data-stu-id="3a86a-161">They are only guaranteed to be compatible.</span></span> <span data-ttu-id="3a86a-162">可以在 ICoreWebView2Environment 的 BrowserVersionString 属性上检查实际版本。</span><span class="sxs-lookup"><span data-stu-id="3a86a-162">You can check the actual version on the BrowserVersionString property on the ICoreWebView2Environment.</span></span>

#### <span data-ttu-id="3a86a-163">put_AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="3a86a-163">put_AdditionalBrowserArguments</span></span> 

<span data-ttu-id="3a86a-164">设置 AdditionalBrowserArguments 属性。</span><span class="sxs-lookup"><span data-stu-id="3a86a-164">Set the AdditionalBrowserArguments property.</span></span>

> <span data-ttu-id="3a86a-165">公共 HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments) (LPCWSTR 值) </span><span class="sxs-lookup"><span data-stu-id="3a86a-165">public HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments)(LPCWSTR value)</span></span>

#### <span data-ttu-id="3a86a-166">put_AllowSingleSignOnUsingOSPrimaryAccount</span><span class="sxs-lookup"><span data-stu-id="3a86a-166">put_AllowSingleSignOnUsingOSPrimaryAccount</span></span> 

<span data-ttu-id="3a86a-167">设置 AllowSingleSignOnUsingOSPrimaryAccount 属性。</span><span class="sxs-lookup"><span data-stu-id="3a86a-167">Set the AllowSingleSignOnUsingOSPrimaryAccount property.</span></span>

> <span data-ttu-id="3a86a-168">public HRESULT [put_AllowSingleSignOnUsingOSPrimaryAccount](#put_allowsinglesignonusingosprimaryaccount) (BOOL 允许) </span><span class="sxs-lookup"><span data-stu-id="3a86a-168">public HRESULT [put_AllowSingleSignOnUsingOSPrimaryAccount](#put_allowsinglesignonusingosprimaryaccount)(BOOL allow)</span></span>

#### <span data-ttu-id="3a86a-169">put_Language</span><span class="sxs-lookup"><span data-stu-id="3a86a-169">put_Language</span></span> 

<span data-ttu-id="3a86a-170">设置 "语言" 属性。</span><span class="sxs-lookup"><span data-stu-id="3a86a-170">Set the Language property.</span></span>

> <span data-ttu-id="3a86a-171">公共 HRESULT [put_Language](#put_language) (LPCWSTR 值) </span><span class="sxs-lookup"><span data-stu-id="3a86a-171">public HRESULT [put_Language](#put_language)(LPCWSTR value)</span></span>

#### <span data-ttu-id="3a86a-172">put_TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="3a86a-172">put_TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="3a86a-173">设置 TargetCompatibleBrowserVersion 属性。</span><span class="sxs-lookup"><span data-stu-id="3a86a-173">Set the TargetCompatibleBrowserVersion property.</span></span>

> <span data-ttu-id="3a86a-174">公共 HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion) (LPCWSTR 值) </span><span class="sxs-lookup"><span data-stu-id="3a86a-174">public HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion)(LPCWSTR value)</span></span>
