---
description: 使用 Microsoft Edge WebView2 发布应用时的分发选项
title: Microsoft Edge WebView2 应用程序的分发
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 7db610ff1133b1b5b380372422f1f2f10981e583
ms.sourcegitcommit: 24151cc65bad92d751a8e7a868c102e1121456e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "11052184"
---
# <span data-ttu-id="fc5bb-104">使用 WebView2 的应用程序的分发</span><span class="sxs-lookup"><span data-stu-id="fc5bb-104">Distribution of applications using WebView2</span></span>  

<span data-ttu-id="fc5bb-105">分发 WebView2 应用程序时，请确保支持 web 平台-应用启动前存在 [WebView2 运行时](#understanding-the-webview2-runtime) 。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-105">When distributing your WebView2 application, make sure the backing web platform - the [WebView2 Runtime](#understanding-the-webview2-runtime) is present before the app starts.</span></span>  <span data-ttu-id="fc5bb-106">本文介绍开发人员如何安装 WebView2 运行时，并使用 WebView2 应用程序的两种分布模式：长  [绿](#evergreen-distribution-mode) 和 [固定版本](#fixed-version-distribution-mode)。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-106">This article describes how developers can install the WebView2 Runtime, and use the two distribution modes for your WebView2 application:  [Evergreen](#evergreen-distribution-mode) and [Fixed Version](#fixed-version-distribution-mode).</span></span>  

## <span data-ttu-id="fc5bb-107">长绿分布模式</span><span class="sxs-lookup"><span data-stu-id="fc5bb-107">Evergreen distribution mode</span></span>  

> [!NOTE]
> <span data-ttu-id="fc5bb-108">对于大多数开发人员，建议使用长绿分布模式。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-108">The Evergreen distribution mode is recommended for most developers.</span></span>  

<span data-ttu-id="fc5bb-109">长时间分布模式可确保你的应用充分利用最新功能和安全更新。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-109">The Evergreen distribution mode ensures that your app is taking advantage of the latest features and security updates.</span></span>  <span data-ttu-id="fc5bb-110">它具有下列特征。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-110">It has the following characteristics.</span></span>  

*   <span data-ttu-id="fc5bb-111">基础 web 平台 \ (WebView2 运行时 \ ) 自动更新，而不需要开发人员进行额外的工作。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-111">The underlying web platform \(WebView2 Runtime\) updates automatically without additional effort from developers.</span></span>  
*   <span data-ttu-id="fc5bb-112">所有使用长时间分布模式的应用程序都使用长绿 WebView2 运行时的共享副本，该副本节省磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-112">All applications that use the Evergreen distribution mode use a shared copy of the Evergreen WebView2 Runtime, which saves disk space.</span></span>  

### <span data-ttu-id="fc5bb-113">了解 WebView2 运行时</span><span class="sxs-lookup"><span data-stu-id="fc5bb-113">Understanding the WebView2 Runtime</span></span>  

<span data-ttu-id="fc5bb-114">WebView2 运行时是重新分发的运行时，它充当 WebView2 应用程序的支持 web 平台。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-114">WebView2 Runtime is a re-distributable runtime and serves as the backing web platform for WebView2 applications.</span></span>  <span data-ttu-id="fc5bb-115">此概念类似于 c + +/.NET 应用的 VC + + 或 .NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-115">This concept is similar to VC++ or .NET Runtime for C++/.NET apps.</span></span>  <span data-ttu-id="fc5bb-116">在该环境下，将修改运行时 Microsoft Edge \ (Chromium \ ) 二进制文件，这些二进制文件经过微调并针对应用程序进行了测试。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-116">Under the hood, the Runtime is modified Microsoft Edge \(Chromium\) binaries that are fine-tuned and tested for applications.</span></span>  <span data-ttu-id="fc5bb-117">在安装时，运行时不会显示为用户可见的浏览器，例如，用户没有浏览器桌面快捷方式或 "开始" 菜单项。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-117">The Runtime won't appear as a user-visible browser upon installation, for example, users won't have a browser desktop shortcut or start menu entry.</span></span>  

<span data-ttu-id="fc5bb-118">对于开发和测试，开发人员可以将运行时或任何非稳定的 Microsoft Edge \ (Chromium \ ) 浏览器频道用于支持的 web 平台。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-118">For development and testing, developers may use the Runtime or any non-stable Microsoft Edge \(Chromium\) browser channel for the backing web platform.</span></span>  <span data-ttu-id="fc5bb-119">在生产环境中，开发人员必须确保在应用程序启动之前用户设备上存在运行时。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-119">In production environments, developers must ensure the Runtime is present on user devices before the application starts.</span></span>  <span data-ttu-id="fc5bb-120">Microsoft Edge 稳定通道不可用于 WebView2 用法，防止应用在生产环境中依赖浏览器参与。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-120">The Microsoft Edge Stable channel is unavailable for WebView2 usage to prevent apps from taking a dependency on the browser in production.</span></span>  

<span data-ttu-id="fc5bb-121">开发人员不能在浏览器上取得依赖性，原因如下：</span><span class="sxs-lookup"><span data-stu-id="fc5bb-121">Developers must not take a dependency on the browser because:</span></span>  

*   <span data-ttu-id="fc5bb-122">Microsoft Edge \ (Chromium \ ) 不保证在所有用户设备上都存在。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-122">Microsoft Edge \(Chromium\) isn't guaranteed to be present on all user devices.</span></span>  <span data-ttu-id="fc5bb-123">例如，从 Windows Update 断开的设备或不是由 Microsoft 直接管理的设备，而不是由 Microsoft (直接在教育机构的大型企业/市场部 ) 中</span><span class="sxs-lookup"><span data-stu-id="fc5bb-123">For example, devices disconnected from Windows Update or not managed by Microsoft directly \(a large portion of the Enterprise/EDU market\) may not have the browser.</span></span>  <span data-ttu-id="fc5bb-124">允许开发人员分发 WebView2 运行时，可避免将浏览器作为应用的必备项。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-124">Allowing developers to distribute the WebView2 Runtime avoids taking a dependency on the browser as a pre-requisite for apps.</span></span>
*   <span data-ttu-id="fc5bb-125">浏览器和应用具有不同的用例，因此对浏览器的依赖可能会对你的应用产生意外的副作用。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-125">Browsers and apps have different use cases, and so taking a dependency on a browser may have unintended side-effects on your apps.</span></span>  <span data-ttu-id="fc5bb-126">例如，IT 管理员可以针对内部网站兼容性版本控制浏览器。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-126">For example, IT admins may version-control the browser for internal website compatibility.</span></span>  <span data-ttu-id="fc5bb-127">WebView2 运行时允许应用在浏览器更新处于活动的管理期间保持长绿。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-127">WebView2 Runtime allows apps to stay evergreen while browser updates are being actively managed.</span></span>  
*   <span data-ttu-id="fc5bb-128">与浏览器相反，运行时是为应用程序方案开发和测试的，在某些情况下，可能会包含在浏览器中尚不可用的 bug 修复。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-128">As opposed to the browser, the Runtime is developed and tested for application scenarios and in some cases may include bug fixes not yet available in the browser.</span></span>  

<span data-ttu-id="fc5bb-129">长时间 WebView2 运行时计划在 Windows 将来的版本中传送收件箱。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-129">The Evergreen WebView2 Runtime is planned to ship inbox in future releases of Windows.</span></span>  <span data-ttu-id="fc5bb-130">在运行库更广泛地可用之前，建议开发人员将运行时与其生产应用程序一起部署。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-130">Before the Runtime becomes more universally available, developers are recommended to deploy the Runtime along with their production application.</span></span>  

### <span data-ttu-id="fc5bb-131">部署长绿 WebView2 运行时</span><span class="sxs-lookup"><span data-stu-id="fc5bb-131">Deploying the Evergreen WebView2 Runtime</span></span>  

<span data-ttu-id="fc5bb-132">设备上的所有长时间应用仅需要一个安装长绿 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-132">Only one installation of the Evergreen WebView2 Runtime is needed for all Evergreen apps on the device.</span></span>  <span data-ttu-id="fc5bb-133">[WebView2 运行时下载页面][Webview2Installer]上提供了许多工具，可帮助开发人员部署长时间运行时，例如：</span><span class="sxs-lookup"><span data-stu-id="fc5bb-133">There are a number of tools available on the [WebView2 Runtime download page][Webview2Installer] to help developers deploy the Evergreen Runtime, such as:</span></span>  

*   <span data-ttu-id="fc5bb-134">WebView2 运行时引导程序 \ (即将发布 \ ) 是一个小的 \ (约 2 MB \ ) 安装程序。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-134">WebView2 Runtime Bootstrapper \(to be released soon\) is a tiny \(approximately 2 MB\) installer.</span></span>  <span data-ttu-id="fc5bb-135">此安装程序从与用户的设备体系结构匹配的 Microsoft 服务器下载并安装长时间运行时。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-135">This installer downloads and installs the Evergreen Runtime from Microsoft servers that matches the user's device architecture.</span></span>  
*   <span data-ttu-id="fc5bb-136">链接以下载引导程序 \ (即将发布 \n ) 是供开发人员以编程方式下载引导程序的链接。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-136">Link to download the Bootstrapper \(to be released soon\) is a link for developers to programmatically download the bootstrapper.</span></span>
*   <span data-ttu-id="fc5bb-137">WebView2 运行时独立安装程序是可在脱机环境中安装长时间 WebView2 运行时的完整安装程序。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-137">WebView2 Runtime Standalone Installer is a full installer that can install the Evergreen WebView2 Runtime in offline environments.</span></span>  

<span data-ttu-id="fc5bb-138">当前，引导程序和独立安装程序仅支持每台计算机安装，这需要提升。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-138">Currently, both the bootstrapper and standalone installer only support per-machine install, which requires elevation.</span></span>  <span data-ttu-id="fc5bb-139">如果没有提升，则会显示一个 Windows 用户帐户控制提示，要求用户提升权限。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-139">When run without elevation, a Windows User Account Control prompt appears to ask users to elevate permissions.</span></span>  

<span data-ttu-id="fc5bb-140">我们建议采用以下工作流，以确保在启动应用程序之前已安装运行时。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-140">We recommend the following workflows to ensure the Runtime is already installed before your application launches.</span></span>  <span data-ttu-id="fc5bb-141">你可以根据你的方案调整工作流。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-141">You may adjust your workflow depending on your scenario.</span></span>  <span data-ttu-id="fc5bb-142">我们还将在将来提供示例代码。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-142">We'll also provide sample code in the future.</span></span>  

#### <span data-ttu-id="fc5bb-143">仅联机部署</span><span class="sxs-lookup"><span data-stu-id="fc5bb-143">Online-only deployment</span></span>  

<span data-ttu-id="fc5bb-144">如果您有仅限联机的部署方案，而最终用户认为有 internet 访问权限，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fc5bb-144">If you have an online-only deployment scenario where end users are assumed to have internet access, perform the following steps:</span></span>  

*   <span data-ttu-id="fc5bb-145">在应用程序设置过程中，请检查运行时是否已由下列两种情况之一安装：</span><span class="sxs-lookup"><span data-stu-id="fc5bb-145">During your application setup, check if the Runtime is already installed by either:</span></span>  
    *   <span data-ttu-id="fc5bb-146">检查中是否 `pv (REG_SZ)` 存在 regkey `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}` ，或者</span><span class="sxs-lookup"><span data-stu-id="fc5bb-146">Inspecting if regkey `pv (REG_SZ)` exists under `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}`, or</span></span>  
    *   <span data-ttu-id="fc5bb-147">调用 WebView2 API [GetAvailableCoreWebView2BrowserVersionString](../reference/win32/0-9-622/webview2-idl.md#getavailablecorewebview2browserversionstring) 并检查 versionInfo 是否为 NULL。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-147">Calling WebView2 API [GetAvailableCoreWebView2BrowserVersionString](../reference/win32/0-9-622/webview2-idl.md#getavailablecorewebview2browserversionstring) and check whether the versionInfo is NULL.</span></span>  
*   <span data-ttu-id="fc5bb-148">如果未安装运行时，请使用链接以编程方式下载引导程序。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-148">If the Runtime isn't installed, use the link to programmatically download the bootstrapper.</span></span>  
*   <span data-ttu-id="fc5bb-149">使用 "静默安装" 从提升的进程或命令提示符处调用引导 `MicrosoftEdgeWebview2Setup.exe /silent /install` 程序。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-149">Invoke the bootstrapper from an elevated process or command prompt with `MicrosoftEdgeWebview2Setup.exe /silent /install` for silent install.</span></span>  

<span data-ttu-id="fc5bb-150">此工作流可确保仅在需要时安装运行时，不需要打包安装程序或检测用户设备的体系结构，并且可以无提示地安装运行时。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-150">This workflow ensures you install the Runtime only when it's needed, you're not required to package installers or detect the architecture of user devices, and can install the Runtime silently.</span></span>  <span data-ttu-id="fc5bb-151">你还可以选择将引导程序与你的应用程序打包，而不是按需以编程方式下载它。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-151">You may also choose to package the bootstrapper with your application instead of programmatically downloading it on demand.</span></span>  

#### <span data-ttu-id="fc5bb-152">脱机部署</span><span class="sxs-lookup"><span data-stu-id="fc5bb-152">Offline deployment</span></span>  

<span data-ttu-id="fc5bb-153">如果你有一个脱机部署方案，其中应用部署必须完全脱机工作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fc5bb-153">If you have an offline deployment scenario where app deployment has to work entirely offline, perform the following steps:</span></span>  

*   <span data-ttu-id="fc5bb-154">下载 [独立安装程序][Webview2Installer]。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-154">Download the [standalone installer][Webview2Installer].</span></span>  
*   <span data-ttu-id="fc5bb-155">在应用程序安装程序或更新程序中包括安装程序。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-155">Include the installer in your application installer or updater.</span></span>  
*   <span data-ttu-id="fc5bb-156">在应用程序设置过程中，请检查运行时是否已由下列两种情况之一安装：</span><span class="sxs-lookup"><span data-stu-id="fc5bb-156">During your application setup, check if the Runtime is already installed by either:</span></span>  
    *   <span data-ttu-id="fc5bb-157">检查中是否 `pv (REG_SZ)` 存在 regkey `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}` ，或者</span><span class="sxs-lookup"><span data-stu-id="fc5bb-157">Inspecting if regkey `pv (REG_SZ)` exists under `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\ClientState\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}`, or</span></span>  
    *   <span data-ttu-id="fc5bb-158">调用 WebView2 API [GetAvailableCoreWebView2BrowserVersionString](../reference/win32/0-9-622/webview2-idl.md#getavailablecorewebview2browserversionstring) 并检查 versionInfo 是否为 NULL。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-158">Calling WebView2 API [GetAvailableCoreWebView2BrowserVersionString](../reference/win32/0-9-622/webview2-idl.md#getavailablecorewebview2browserversionstring) and check whether the versionInfo is NULL.</span></span>  
*   <span data-ttu-id="fc5bb-159">如果运行时未安装，请从提升的进程或命令提示符处调用独立安装程序，以 `MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install` 进行静默式安装。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-159">If the Runtime isn't installed, invoke the standalone installer from an elevated process or command prompt with `MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install` for silent install.</span></span>  

## <span data-ttu-id="fc5bb-160">固定版本分发模式</span><span class="sxs-lookup"><span data-stu-id="fc5bb-160">Fixed Version distribution mode</span></span>  

> [!NOTE]
> <span data-ttu-id="fc5bb-161">固定版本分发模式尚不可用。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-161">The Fixed Version distribution mode is not available yet.</span></span>  

<span data-ttu-id="fc5bb-162">对于受限制的环境，有计划支持固定版本，以前称为 "携带"、"分发" 模式。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-162">For constrained environments, there are plans to support a Fixed Version, previously named bring-your-own, distribution mode.</span></span>  <span data-ttu-id="fc5bb-163">固定版本分发模式允许开发人员选择和打包特定版本的 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-163">The Fixed Version distribution mode allows developers to select and package a specific version of the WebView2 Runtime.</span></span>  <span data-ttu-id="fc5bb-164">固定版本分发模式允许你控制你的应用程序使用哪个版本的 WebView2 运行时，以及何时更新用户计算机。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-164">The Fixed Version distribution mode allows you to control which version of the WebView2 Runtime is used by your application, and when user machines are updated.</span></span>  <span data-ttu-id="fc5bb-165">固定版本分发模式不会接收任何自动更新，开发人员应计划自己应用更新。</span><span class="sxs-lookup"><span data-stu-id="fc5bb-165">The Fixed Version distribution mode doesn't receive any automatic updates, and developers should plan to apply updates themselves.</span></span>  


<!-- links -->  

[ConceptsVersioning]: ./versioning.md "了解浏览器版本和 WebView2 |Microsoft 文档"  
[ReferenceWin3209622WebviewIdl]: ../reference/win32/0-9-622/webview2-idl.md  "Globals |Microsoft 文档"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序"  
