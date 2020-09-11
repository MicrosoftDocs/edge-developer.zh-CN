---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2。 CoreWebView2EnvironmentOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: bec9d46f1043c9bcb721b3dd740b5fa4ab7b5700
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010983"
---
# <span data-ttu-id="b0d94-104">0.9.579-WebView2 的 CoreWebView2EnvironmentOptions 类</span><span class="sxs-lookup"><span data-stu-id="b0d94-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2EnvironmentOptions class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="b0d94-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="b0d94-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="b0d94-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="b0d94-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="b0d94-107">用于创建 WebView2 环境的选项。</span><span class="sxs-lookup"><span data-stu-id="b0d94-107">Options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="b0d94-108">摘要</span><span class="sxs-lookup"><span data-stu-id="b0d94-108">Summary</span></span>

 <span data-ttu-id="b0d94-109">成员</span><span class="sxs-lookup"><span data-stu-id="b0d94-109">Members</span></span>                        | <span data-ttu-id="b0d94-110">描述</span><span class="sxs-lookup"><span data-stu-id="b0d94-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b0d94-111">AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="b0d94-111">AdditionalBrowserArguments</span></span>](#additionalbrowserarguments) | <span data-ttu-id="b0d94-112">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="b0d94-112">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>
[<span data-ttu-id="b0d94-113">IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="b0d94-113">IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span>](#issinglesignonusingosprimaryaccountenabled) | <span data-ttu-id="b0d94-114">IsSingleSignOnUsingOSPrimaryAccountEnabled 属性用于在使用 windows 帐户登录的 Microsoft 帐户中使用已登录的 Windows 帐户在 web 站点内使用已登录的 Windows 帐户进行单一)  (登录，并使用与 Windows 帐户中的登录相关联的 Microsoft 帐户在 web 站点上使用单一登录来启用单一登录。</span><span class="sxs-lookup"><span data-stu-id="b0d94-114">The IsSingleSignOnUsingOSPrimaryAccountEnabled property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>
[<span data-ttu-id="b0d94-115">语言</span><span class="sxs-lookup"><span data-stu-id="b0d94-115">Language</span></span>](#language) | <span data-ttu-id="b0d94-116">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="b0d94-116">The default language that WebView will run with.</span></span>
[<span data-ttu-id="b0d94-117">TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="b0d94-117">TargetCompatibleBrowserVersion</span></span>](#targetcompatiblebrowserversion) | <span data-ttu-id="b0d94-118">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="b0d94-118">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>
[<span data-ttu-id="b0d94-119">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="b0d94-119">CoreWebView2EnvironmentOptions</span></span>](#corewebview2environmentoptions) | <span data-ttu-id="b0d94-120">初始化 CoreWebView2EnvironmentOptions 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="b0d94-120">Initializes a new instance of the CoreWebView2EnvironmentOptions class.</span></span>

<span data-ttu-id="b0d94-121">默认实现在 WebView2EnvironmentOptions 中提供。</span><span class="sxs-lookup"><span data-stu-id="b0d94-121">A default implementation is provided in WebView2EnvironmentOptions.h.</span></span>

## <span data-ttu-id="b0d94-122">成员</span><span class="sxs-lookup"><span data-stu-id="b0d94-122">Members</span></span>

#### <span data-ttu-id="b0d94-123">AdditionalBrowserArguments</span><span class="sxs-lookup"><span data-stu-id="b0d94-123">AdditionalBrowserArguments</span></span> 

<span data-ttu-id="b0d94-124">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="b0d94-124">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span>

> <span data-ttu-id="b0d94-125">公共字符串 [AdditionalBrowserArguments](#additionalbrowserarguments)</span><span class="sxs-lookup"><span data-stu-id="b0d94-125">public string [AdditionalBrowserArguments](#additionalbrowserarguments)</span></span>

<span data-ttu-id="b0d94-126">这些内容将作为命令行的一部分传递到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="b0d94-126">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="b0d94-127">有关命令行开关的详细信息，请参阅 [用标志运行 Chromium](https://aka.ms/RunChromiumWithFlags) ，了解如何切换到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="b0d94-127">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="b0d94-128">如果使用命令行开关启动应用 `--edge-webview-switches=xxx` ，则上述) 示例中 (xxx 的开关的值也将追加到浏览器进程命令行。</span><span class="sxs-lookup"><span data-stu-id="b0d94-128">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="b0d94-129">某些交换机（如 `--user-data-dir` 内部）和对 Web 视图来说很重要。</span><span class="sxs-lookup"><span data-stu-id="b0d94-129">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="b0d94-130">即使指定，这些开关也将被忽略。</span><span class="sxs-lookup"><span data-stu-id="b0d94-130">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="b0d94-131">如果多次指定同一开关，则最后一个参数将获胜。</span><span class="sxs-lookup"><span data-stu-id="b0d94-131">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="b0d94-132">除了禁用和启用的功能外，不会尝试合并同一开关的不同值。</span><span class="sxs-lookup"><span data-stu-id="b0d94-132">There is no attempt to merge the different values of the same switch, except for disabled and enabled features.</span></span> <span data-ttu-id="b0d94-133">将使用简单的逻辑合并 "" 和 "" 的功能 `--enable-features` `--disable-features` ：这些功能将是指定功能和内置功能的联合，如果某个功能被禁用，它将从 "启用的功能" 列表中删除。</span><span class="sxs-lookup"><span data-stu-id="b0d94-133">The features specified by `--enable-features` and `--disable-features` will be merged with simple logic: the features will be the union of the specified features and built-in features, and if a feature is disabled, it will be removed from the enabled features list.</span></span> <span data-ttu-id="b0d94-134">在 `--edge-webview-switches` 处理 additionalBrowserArguments 参数后，将处理应用进程的命令行值。</span><span class="sxs-lookup"><span data-stu-id="b0d94-134">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="b0d94-135">某些功能在内部禁用且无法启用。</span><span class="sxs-lookup"><span data-stu-id="b0d94-135">Certain features are disabled internally and can't be enabled.</span></span> <span data-ttu-id="b0d94-136">如果指定开关的分析失败，则将忽略它们。</span><span class="sxs-lookup"><span data-stu-id="b0d94-136">If parsing failed for the specified switches, they will be ignored.</span></span> <span data-ttu-id="b0d94-137">默认情况下，不执行任何额外的标志即可运行浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="b0d94-137">Default is to run browser process with no extra flags.</span></span>

#### <span data-ttu-id="b0d94-138">IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="b0d94-138">IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="b0d94-139">IsSingleSignOnUsingOSPrimaryAccountEnabled 属性用于在使用 windows 帐户登录的 Microsoft 帐户中使用已登录的 Windows 帐户在 web 站点内使用已登录的 Windows 帐户进行单一)  (登录，并使用与 Windows 帐户中的登录相关联的 Microsoft 帐户在 web 站点上使用单一登录来启用单一登录。</span><span class="sxs-lookup"><span data-stu-id="b0d94-139">The IsSingleSignOnUsingOSPrimaryAccountEnabled property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>

> <span data-ttu-id="b0d94-140">公共 bool [IsSingleSignOnUsingOSPrimaryAccountEnabled](#issinglesignonusingosprimaryaccountenabled)</span><span class="sxs-lookup"><span data-stu-id="b0d94-140">public bool [IsSingleSignOnUsingOSPrimaryAccountEnabled](#issinglesignonusingosprimaryaccountenabled)</span></span>

<span data-ttu-id="b0d94-141">默认值为 "已禁用"。</span><span class="sxs-lookup"><span data-stu-id="b0d94-141">Default is disabled.</span></span> <span data-ttu-id="b0d94-142">通用 Windows 平台应用还必须声明 enterpriseCloudSSO [受限功能](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities) 才能使单一登录正常工作。</span><span class="sxs-lookup"><span data-stu-id="b0d94-142">Universal Windows Platform apps must also declare enterpriseCloudSSO [restricted capability](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities) for the single sign on to work.</span></span>

#### <span data-ttu-id="b0d94-143">语言</span><span class="sxs-lookup"><span data-stu-id="b0d94-143">Language</span></span> 

<span data-ttu-id="b0d94-144">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="b0d94-144">The default language that WebView will run with.</span></span>

> <span data-ttu-id="b0d94-145">公共字符串 [语言](#language)</span><span class="sxs-lookup"><span data-stu-id="b0d94-145">public string [Language](#language)</span></span>

<span data-ttu-id="b0d94-146">它适用于浏览器 Ui，如上下文菜单和对话框。</span><span class="sxs-lookup"><span data-stu-id="b0d94-146">It applies to browser UIs like context menu and dialogs.</span></span> <span data-ttu-id="b0d94-147">它还适用于 web 视图发送到网站的接受语言 HTTP 头。</span><span class="sxs-lookup"><span data-stu-id="b0d94-147">It also applies to the accept-languages HTTP header that WebView sends to web sites.</span></span> <span data-ttu-id="b0d94-148">它采用的格式 `language[-country]` `language` 是 iso 639 中的2个字母代码， `country` 是 iso 3166 中的2个字母代码。</span><span class="sxs-lookup"><span data-stu-id="b0d94-148">It is in the format of `language[-country]` where `language` is the 2 letter code from ISO 639 and `country` is the 2 letter code from ISO 3166.</span></span>

#### <span data-ttu-id="b0d94-149">TargetCompatibleBrowserVersion</span><span class="sxs-lookup"><span data-stu-id="b0d94-149">TargetCompatibleBrowserVersion</span></span> 

<span data-ttu-id="b0d94-150">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="b0d94-150">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

> <span data-ttu-id="b0d94-151">公共字符串 [TargetCompatibleBrowserVersion](#targetcompatiblebrowserversion)</span><span class="sxs-lookup"><span data-stu-id="b0d94-151">public string [TargetCompatibleBrowserVersion](#targetcompatiblebrowserversion)</span></span>

<span data-ttu-id="b0d94-152">这将默认为与应用程序所使用的 SDK 版本相对应的 Edge WebView2 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="b0d94-152">This defaults to the Edge WebView2 Runtime version that corresponds with the version of the SDK the application is using.</span></span> <span data-ttu-id="b0d94-153">此值的格式与 BrowserVersionString 属性和其他 BrowserVersion 值的格式相同。</span><span class="sxs-lookup"><span data-stu-id="b0d94-153">The format of this value is the same as the format of the BrowserVersionString property and other BrowserVersion values.</span></span> <span data-ttu-id="b0d94-154">仅考虑 BrowserVersion 值的版本部分。</span><span class="sxs-lookup"><span data-stu-id="b0d94-154">Only the version part of the BrowserVersion value is respected.</span></span> <span data-ttu-id="b0d94-155">如果存在信道后缀，则将其忽略。</span><span class="sxs-lookup"><span data-stu-id="b0d94-155">The channel suffix, if it exists, is ignored.</span></span> <span data-ttu-id="b0d94-156">实际使用的 Edge WebView2 运行时二进制文件的版本可能与指定的 TargetCompatibleBrowserVersion 不同。</span><span class="sxs-lookup"><span data-stu-id="b0d94-156">The version of the Edge WebView2 Runtime binaries actually used may be different from the specified TargetCompatibleBrowserVersion.</span></span> <span data-ttu-id="b0d94-157">它们只能保证兼容性。</span><span class="sxs-lookup"><span data-stu-id="b0d94-157">They are only guaranteed to be compatible.</span></span> <span data-ttu-id="b0d94-158">可以在 CoreWebView2Environment 的 BrowserVersionString 属性上检查实际版本。</span><span class="sxs-lookup"><span data-stu-id="b0d94-158">You can check the actual version on the BrowserVersionString property on the CoreWebView2Environment.</span></span>

#### <span data-ttu-id="b0d94-159">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="b0d94-159">CoreWebView2EnvironmentOptions</span></span> 

<span data-ttu-id="b0d94-160">初始化 CoreWebView2EnvironmentOptions 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="b0d94-160">Initializes a new instance of the CoreWebView2EnvironmentOptions class.</span></span>

> <span data-ttu-id="b0d94-161">public [CoreWebView2EnvironmentOptions](#corewebview2environmentoptions) (string additionalBrowserArguments、string language、string targetCompatibleBrowserVersion) </span><span class="sxs-lookup"><span data-stu-id="b0d94-161">public [CoreWebView2EnvironmentOptions](#corewebview2environmentoptions)(string additionalBrowserArguments, string language, string targetCompatibleBrowserVersion)</span></span>

##### <span data-ttu-id="b0d94-162">参数</span><span class="sxs-lookup"><span data-stu-id="b0d94-162">Parameters</span></span>
* `additionalBrowserArguments` <span data-ttu-id="b0d94-163">可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="b0d94-163">AdditionalBrowserArguments can be specified to change the behavior of the WebView.</span></span> 

* `language` <span data-ttu-id="b0d94-164">将运行 Web 视图运行的默认语言。</span><span class="sxs-lookup"><span data-stu-id="b0d94-164">The default language that WebView will run with.</span></span> 

* `targetCompatibleBrowserVersion` <span data-ttu-id="b0d94-165">需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。</span><span class="sxs-lookup"><span data-stu-id="b0d94-165">The version of the Edge WebView2 Runtime binaries required to be compatible with the calling application.</span></span>

