---
description: 使用 WebView2 发布应用时Microsoft Edge选项
title: WebView2 Microsoft Edge分发
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 97ede968e066c572bb1b22e10ed7e758e38e3ca4
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535697"
---
# <a name="distribution-of-apps-using-webview2"></a><span data-ttu-id="2dd60-104">使用 WebView2 分发应用</span><span class="sxs-lookup"><span data-stu-id="2dd60-104">Distribution of apps using WebView2</span></span>  

<span data-ttu-id="2dd60-105">分发 WebView2 应用时，请确保在应用启动前存在支持 Web 平台 [WebView2][Webview2Installer]运行时。</span><span class="sxs-lookup"><span data-stu-id="2dd60-105">When distributing your WebView2 app, ensure the backing web platform, the [WebView2 Runtime][Webview2Installer], is present before the app starts.</span></span>  <span data-ttu-id="2dd60-106">本文介绍了如何 \ (开发人员\) 安装 WebView2 运行时，以及如何对 WebView2 应用使用两种分发模式[：Evergreen](#evergreen-distribution-mode)和 Fixed [Version。](#fixed-version-distribution-mode)</span><span class="sxs-lookup"><span data-stu-id="2dd60-106">This article describes how you \(the developer\) install the WebView2 Runtime, and use the two distribution modes for your WebView2 app:  [Evergreen](#evergreen-distribution-mode) and [Fixed Version](#fixed-version-distribution-mode).</span></span>  

## <a name="evergreen-distribution-mode"></a><span data-ttu-id="2dd60-107">常青分发模式</span><span class="sxs-lookup"><span data-stu-id="2dd60-107">Evergreen distribution mode</span></span>  

> [!NOTE]
> <span data-ttu-id="2dd60-108">建议大多数开发人员使用常青分发模式。</span><span class="sxs-lookup"><span data-stu-id="2dd60-108">The Evergreen distribution mode is recommended for most developers.</span></span>  

<span data-ttu-id="2dd60-109">常青分发模式可确保你的应用充分利用最新的功能和安全更新。</span><span class="sxs-lookup"><span data-stu-id="2dd60-109">The Evergreen distribution mode ensures that your app is taking advantage of the latest features and security updates.</span></span>  <span data-ttu-id="2dd60-110">它具有以下特征。</span><span class="sxs-lookup"><span data-stu-id="2dd60-110">It has the following characteristics.</span></span>  

*   <span data-ttu-id="2dd60-111">基础 Web 平台 \ (WebView2 运行时\) 自动更新，无需额外工作。</span><span class="sxs-lookup"><span data-stu-id="2dd60-111">The underlying web platform \(WebView2 Runtime\) updates automatically without additional effort from you.</span></span>  
*   <span data-ttu-id="2dd60-112">所有使用 Evergreen 分发模式的应用都使用 Evergreen WebView2 运行时的共享副本，从而节省磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="2dd60-112">All apps that use the Evergreen distribution mode use a shared copy of the Evergreen WebView2 Runtime, which saves disk space.</span></span>  
    
### <a name="understanding-the-webview2-runtime"></a><span data-ttu-id="2dd60-113">了解 WebView2 运行时</span><span class="sxs-lookup"><span data-stu-id="2dd60-113">Understanding the WebView2 Runtime</span></span>  

<span data-ttu-id="2dd60-114">WebView2 运行时是一个可再发行运行时，并用作 WebView2 应用的支持 Web 平台。</span><span class="sxs-lookup"><span data-stu-id="2dd60-114">The WebView2 Runtime is a redistributable runtime and serves as the backing web platform for WebView2 apps.</span></span>  <span data-ttu-id="2dd60-115">此概念类似于 Visual C++/.NET 应用的 .NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="2dd60-115">The concept is similar to Visual C++ or the .NET Runtime for C++/.NET apps.</span></span>  <span data-ttu-id="2dd60-116">运行时包含经过修改Microsoft Edge \ (Chromium\) 已针对应用进行优化和测试的二进制文件。</span><span class="sxs-lookup"><span data-stu-id="2dd60-116">The Runtime contains modified Microsoft Edge \(Chromium\) binaries that are fine-tuned and tested for apps.</span></span>  <span data-ttu-id="2dd60-117">运行时在安装时不会显示为用户可见的浏览器。</span><span class="sxs-lookup"><span data-stu-id="2dd60-117">The Runtime does not appear as a user-visible browser upon installation.</span></span>  <span data-ttu-id="2dd60-118">例如，用户没有浏览器桌面快捷方式或"开始"菜单条目。</span><span class="sxs-lookup"><span data-stu-id="2dd60-118">For example, a user does not have a browser desktop shortcut or start menu entry.</span></span>  

<span data-ttu-id="2dd60-119">在开发和测试期间，你可以将任一平台用作支持 Web 平台。</span><span class="sxs-lookup"><span data-stu-id="2dd60-119">During development and testing, you may use either as the backing web platform.</span></span>  

*   <span data-ttu-id="2dd60-120">WebView2 运行时</span><span class="sxs-lookup"><span data-stu-id="2dd60-120">The WebView2 Runtime</span></span>  
*   <span data-ttu-id="2dd60-121">任何预览体验成员 \ (非稳定\) Microsoft Edge \ (Chromium\) 浏览器通道</span><span class="sxs-lookup"><span data-stu-id="2dd60-121">Any Insider \(non-stable\) Microsoft Edge \(Chromium\) browser channel</span></span>  
    
<span data-ttu-id="2dd60-122">在生产环境中，在应用启动之前，必须确保运行时存在于用户设备上。</span><span class="sxs-lookup"><span data-stu-id="2dd60-122">In production environments, you must ensure the Runtime is present on user devices before the app starts.</span></span>  <span data-ttu-id="2dd60-123">Microsoft Edge Stable 渠道不可用于 WebView2。</span><span class="sxs-lookup"><span data-stu-id="2dd60-123">The Microsoft Edge Stable channel is unavailable for WebView2 usage.</span></span>  <span data-ttu-id="2dd60-124">该决定可防止应用在生产中依赖浏览器。</span><span class="sxs-lookup"><span data-stu-id="2dd60-124">The decision prevents apps from taking a dependency on the browser in production.</span></span>

<span data-ttu-id="2dd60-125">请勿依赖浏览器，因为：</span><span class="sxs-lookup"><span data-stu-id="2dd60-125">Do not take a dependency on the browser because:</span></span>  

*   <span data-ttu-id="2dd60-126">Microsoft Edge \ (Chromium\) 不一定存在于所有用户设备上。</span><span class="sxs-lookup"><span data-stu-id="2dd60-126">Microsoft Edge \(Chromium\) is not guaranteed to be present on all user devices.</span></span>  <span data-ttu-id="2dd60-127">例如，与 Windows Update 断开连接或不由 Microsoft 直接管理的设备 \ (大部分 Enterprise 和 EDU 市场\) 可能没有浏览器。</span><span class="sxs-lookup"><span data-stu-id="2dd60-127">For example, devices disconnected from Windows Update or not managed by Microsoft directly \(a large portion of the Enterprise and EDU market\) may not have the browser.</span></span>  <span data-ttu-id="2dd60-128">允许分发 WebView2 运行时可以避免依赖浏览器作为应用的先决条件。</span><span class="sxs-lookup"><span data-stu-id="2dd60-128">Allowing you to distribute the WebView2 Runtime avoids taking a dependency on the browser as a pre-requisite for apps.</span></span>  
*   <span data-ttu-id="2dd60-129">浏览器和应用具有不同的用例，因此依赖浏览器可能会对应用产生意外的负面影响。</span><span class="sxs-lookup"><span data-stu-id="2dd60-129">Browsers and apps have different use cases, and so taking a dependency on a browser may have unintended side-effects on your apps.</span></span>  <span data-ttu-id="2dd60-130">例如，IT 管理员可以对浏览器进行版本控制，以确保内部网站兼容性。</span><span class="sxs-lookup"><span data-stu-id="2dd60-130">For example, IT admins may version-control the browser for internal website compatibility.</span></span>  <span data-ttu-id="2dd60-131">WebView2 运行时允许应用在主动管理浏览器更新时保持常青。</span><span class="sxs-lookup"><span data-stu-id="2dd60-131">The WebView2 Runtime allows apps to stay evergreen while browser updates are being actively managed.</span></span>  
*   <span data-ttu-id="2dd60-132">与浏览器相反，运行时针对应用方案进行开发和测试，并且在某些情况下可能包括浏览器中尚未提供的 Bug 修复。</span><span class="sxs-lookup"><span data-stu-id="2dd60-132">As opposed to the browser, the Runtime is developed and tested for app scenarios and in some cases may include bug fixes not yet available in the browser.</span></span>  
    
<span data-ttu-id="2dd60-133">今后，Evergreen WebView2 运行时计划提供未来版本Windows。</span><span class="sxs-lookup"><span data-stu-id="2dd60-133">In the future, the Evergreen WebView2 Runtime plans to ship with future releases of Windows.</span></span>  <span data-ttu-id="2dd60-134">将运行时与生产应用一起部署，直到运行时更普遍可用。</span><span class="sxs-lookup"><span data-stu-id="2dd60-134">Deploy the Runtime with your production app until the Runtime becomes more universally available.</span></span>  

### <a name="deploying-the-evergreen-webview2-runtime"></a><span data-ttu-id="2dd60-135">部署 Evergreen WebView2 运行时</span><span class="sxs-lookup"><span data-stu-id="2dd60-135">Deploying the Evergreen WebView2 Runtime</span></span>  

<span data-ttu-id="2dd60-136">设备上的所有 Evergreen 应用只需安装一次 Evergreen WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="2dd60-136">Only one installation of the Evergreen WebView2 Runtime is needed for all Evergreen apps on the device.</span></span>  <span data-ttu-id="2dd60-137">WebView2 运行时下载页上提供了 [许多工具][Webview2Installer]。</span><span class="sxs-lookup"><span data-stu-id="2dd60-137">There are a number of tools available on the [WebView2 Runtime download page][Webview2Installer].</span></span>  <span data-ttu-id="2dd60-138">以下工具可帮助你部署常青运行时。</span><span class="sxs-lookup"><span data-stu-id="2dd60-138">The following tools help you deploy the Evergreen Runtime.</span></span>  

*   <span data-ttu-id="2dd60-139">WebView2 运行时引导程序是一个小的 \ (大约 2 MB\) 安装程序。</span><span class="sxs-lookup"><span data-stu-id="2dd60-139">WebView2 Runtime Bootstrapper is a tiny \(approximately 2 MB\) installer.</span></span>  <span data-ttu-id="2dd60-140">WebView2 运行时引导程序从与用户设备体系结构匹配的 Microsoft 服务器下载并安装 Evergreen Runtime。</span><span class="sxs-lookup"><span data-stu-id="2dd60-140">WebView2 Runtime Bootstrapper downloads and installs the Evergreen Runtime from Microsoft servers that matches the user's device architecture.</span></span>  
*   <span data-ttu-id="2dd60-141">使用链接以编程方式下载引导程序。</span><span class="sxs-lookup"><span data-stu-id="2dd60-141">Use a link to programmatically download the bootstrapper.</span></span>  
*   <span data-ttu-id="2dd60-142">WebView2 运行时独立安装程序是在脱机环境中安装 Evergreen WebView2 运行时的完整安装程序。</span><span class="sxs-lookup"><span data-stu-id="2dd60-142">WebView2 Runtime Standalone Installer is a full installer that installs the Evergreen WebView2 Runtime in offline environments.</span></span>  
    
<span data-ttu-id="2dd60-143">目前，引导程序和独立安装程序仅支持每台计算机安装，这需要提升。</span><span class="sxs-lookup"><span data-stu-id="2dd60-143">Currently, both the bootstrapper and standalone installer only support per-machine installs, which requires elevation.</span></span>  <span data-ttu-id="2dd60-144">如果安装程序在未提升权限的情况下运行，系统将提示用户提升权限。</span><span class="sxs-lookup"><span data-stu-id="2dd60-144">If an installer is run without elevation, the user is prompted to elevate permissions.</span></span>  

<span data-ttu-id="2dd60-145">使用以下工作流来确保在应用启动之前已安装运行时。</span><span class="sxs-lookup"><span data-stu-id="2dd60-145">Use following workflows to ensure the Runtime is already installed before your app launches.</span></span>  <span data-ttu-id="2dd60-146">可以根据方案调整工作流。</span><span class="sxs-lookup"><span data-stu-id="2dd60-146">You may adjust your workflow depending on your scenario.</span></span>  <span data-ttu-id="2dd60-147">示例代码在示例 [存储库中提供][GitHubMicrosoftedgeWebView2samplesWebview2Deployment]。</span><span class="sxs-lookup"><span data-stu-id="2dd60-147">Sample code is available in the [Samples repo][GitHubMicrosoftedgeWebView2samplesWebview2Deployment].</span></span>  

#### <a name="online-only-deployment"></a><span data-ttu-id="2dd60-148">仅联机部署</span><span class="sxs-lookup"><span data-stu-id="2dd60-148">Online-only deployment</span></span>  

<span data-ttu-id="2dd60-149">如果你有假定用户具有 Internet 访问权限的仅联机部署方案，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="2dd60-149">If you have an online-only deployment scenario where users are assumed to have internet access, complete the following steps.</span></span>  

1.  <span data-ttu-id="2dd60-150">在应用设置期间，请确保已安装运行时。</span><span class="sxs-lookup"><span data-stu-id="2dd60-150">During your app setup, ensure the Runtime is already installed.</span></span>  <span data-ttu-id="2dd60-151">若要进行验证，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="2dd60-151">To  verify, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="2dd60-152">检查 `pv (REG_SZ)` 注册表项是否存在且不是 `null` 或为空。</span><span class="sxs-lookup"><span data-stu-id="2dd60-152">Inspect if the `pv (REG_SZ)` regkey exists and is not `null` or empty.</span></span>  <span data-ttu-id="2dd60-153">在  `pv (REG_SZ)` 下列位置查找。</span><span class="sxs-lookup"><span data-stu-id="2dd60-153">Find  `pv (REG_SZ)` at the following location.</span></span>  
        
        <span data-ttu-id="2dd60-154">在 64 位Windows</span><span class="sxs-lookup"><span data-stu-id="2dd60-154">On 64-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        <span data-ttu-id="2dd60-155">在 32 位Windows</span><span class="sxs-lookup"><span data-stu-id="2dd60-155">On 32-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   <span data-ttu-id="2dd60-156">运行 [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] 并确保 `versionInfo` 为 `NULL` 。</span><span class="sxs-lookup"><span data-stu-id="2dd60-156">Run [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] and ensure the `versionInfo` is `NULL`.</span></span>  
1.  <span data-ttu-id="2dd60-157">如果未安装运行时，请使用链接以编程方式下载引导程序。</span><span class="sxs-lookup"><span data-stu-id="2dd60-157">If the Runtime is not installed, use the link to programmatically download the bootstrapper.</span></span>  
1.  <span data-ttu-id="2dd60-158">通过静默安装从提升的进程或命令提示符调用 `MicrosoftEdgeWebview2Setup.exe /silent /install` 引导程序。</span><span class="sxs-lookup"><span data-stu-id="2dd60-158">Invoke the bootstrapper from an elevated process or command prompt with `MicrosoftEdgeWebview2Setup.exe /silent /install` for silent install.</span></span>  
    
<span data-ttu-id="2dd60-159">以前的工作流具有以下优点。</span><span class="sxs-lookup"><span data-stu-id="2dd60-159">The previous workflow has the following benefits.</span></span>  

*   <span data-ttu-id="2dd60-160">仅在需要或不需要打包安装程序时安装运行时。</span><span class="sxs-lookup"><span data-stu-id="2dd60-160">Install the Runtime only when needed or when you are not required to package installers.</span></span>  
*   <span data-ttu-id="2dd60-161">引导程序自动检测设备体系结构并安装匹配的运行时。</span><span class="sxs-lookup"><span data-stu-id="2dd60-161">The bootstrapper automatically detects device architecture and installs the matching Runtime.</span></span>  
*   <span data-ttu-id="2dd60-162">以静默方式安装运行时。</span><span class="sxs-lookup"><span data-stu-id="2dd60-162">Install the Runtime silently.</span></span>  
    
<span data-ttu-id="2dd60-163">还可以选择将引导程序打包到你的应用中，而不是以编程方式按需下载它。</span><span class="sxs-lookup"><span data-stu-id="2dd60-163">You may also choose to package the bootstrapper with your app instead of programmatically downloading it on demand.</span></span>  

#### <a name="offline-deployment"></a><span data-ttu-id="2dd60-164">脱机部署</span><span class="sxs-lookup"><span data-stu-id="2dd60-164">Offline deployment</span></span>  

<span data-ttu-id="2dd60-165">如果你有应用部署必须完全脱机工作的脱机部署方案，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="2dd60-165">If you have an offline deployment scenario where app deployment has to work entirely offline, complete the following steps.</span></span>  

1.  <span data-ttu-id="2dd60-166">下载 [独立安装程序][Webview2Installer]。</span><span class="sxs-lookup"><span data-stu-id="2dd60-166">Download the [standalone installer][Webview2Installer].</span></span>  
1.  <span data-ttu-id="2dd60-167">在应用安装程序或更新程序中包括安装程序。</span><span class="sxs-lookup"><span data-stu-id="2dd60-167">Include the installer in your app installer or updater.</span></span>  
1.  <span data-ttu-id="2dd60-168">在应用设置期间，请确保已安装运行时。</span><span class="sxs-lookup"><span data-stu-id="2dd60-168">During your app setup, ensure the Runtime is already installed.</span></span>  <span data-ttu-id="2dd60-169">若要进行验证，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="2dd60-169">To  verify, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="2dd60-170">检查 `pv (REG_SZ)` 注册表项是否存在且不是 `null` 或为空。</span><span class="sxs-lookup"><span data-stu-id="2dd60-170">Inspect if the `pv (REG_SZ)` regkey exists and is not `null` or empty.</span></span>  <span data-ttu-id="2dd60-171">在  `pv (REG_SZ)` 下列位置查找。</span><span class="sxs-lookup"><span data-stu-id="2dd60-171">Find  `pv (REG_SZ)` at the following location.</span></span>  
        
        <span data-ttu-id="2dd60-172">在 64 位Windows</span><span class="sxs-lookup"><span data-stu-id="2dd60-172">On 64-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        <span data-ttu-id="2dd60-173">在 32 位Windows</span><span class="sxs-lookup"><span data-stu-id="2dd60-173">On 32-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   <span data-ttu-id="2dd60-174">运行 [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] 并确保 `versionInfo` 为 `NULL` 。</span><span class="sxs-lookup"><span data-stu-id="2dd60-174">Run [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] and ensure the `versionInfo` is `NULL`.</span></span>  
1.  <span data-ttu-id="2dd60-175">如果未安装运行时，请运行独立安装程序。</span><span class="sxs-lookup"><span data-stu-id="2dd60-175">If the Runtime is not installed, run the standalone installer.</span></span>  <span data-ttu-id="2dd60-176">如果要运行无提示安装，请从提升的进程运行安装程序，或者复制并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="2dd60-176">If you want to run a silent installation, either run the installer from an elevated process or copy and run the following command.</span></span>  
    
    ```shell
    MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install
    ```  
    
### <a name="stay-compatible-in-evergreen-mode"></a><span data-ttu-id="2dd60-177">在常青模式下保持兼容</span><span class="sxs-lookup"><span data-stu-id="2dd60-177">Stay compatible in Evergreen mode</span></span>  

<span data-ttu-id="2dd60-178">Web 在不断演变。</span><span class="sxs-lookup"><span data-stu-id="2dd60-178">The Web is constantly evolving.</span></span>  <span data-ttu-id="2dd60-179">Evergreen WebView2 运行时保持最新状态，以提供最新功能和安全修补程序。</span><span class="sxs-lookup"><span data-stu-id="2dd60-179">The Evergreen WebView2 Runtime is kept up to date to provide you with the latest features and security fixes.</span></span>  <span data-ttu-id="2dd60-180">若要确保应用与 Web 保持兼容，应设置测试基础结构。</span><span class="sxs-lookup"><span data-stu-id="2dd60-180">To ensure your app stays compatible with the web, you should set up testing infrastructure.</span></span>  

<span data-ttu-id="2dd60-181">非稳定 Microsoft Edge渠道 \ (Beta/Dev/Canary\) 可快速了解 WebView2 运行时即将出现的内容。</span><span class="sxs-lookup"><span data-stu-id="2dd60-181">Non-stable Microsoft Edge channels \(Beta/Dev/Canary\) provide a sneak peek into what is coming next into WebView2 Runtime.</span></span>  <span data-ttu-id="2dd60-182">就像开发 web 应用程序Microsoft Edge一样，你应该定期测试 WebView2 应用。</span><span class="sxs-lookup"><span data-stu-id="2dd60-182">Just like developing websites for Microsoft Edge, you should test your WebView2 app regularly.</span></span>  <span data-ttu-id="2dd60-183">针对其中一个非稳定渠道测试 WebView2 应用，并更新应用或报告问题 [（如果][GithubMicrosoftedgeWebviewfeedback] 出现问题）。</span><span class="sxs-lookup"><span data-stu-id="2dd60-183">Test your WebView2 app against one of the non-stable channels, and update your app or [report issues][GithubMicrosoftedgeWebviewfeedback] if issues arise.</span></span> <span data-ttu-id="2dd60-184">通常推荐使用 Dev 和 Beta 渠道。</span><span class="sxs-lookup"><span data-stu-id="2dd60-184">Typically Dev and Beta are the recommended channels.</span></span>  <span data-ttu-id="2dd60-185">若要帮助你确定哪个频道正确，请导航到"Microsoft Edge[概述"。][DeployEdgeMicrosoftEdgeChannels]</span><span class="sxs-lookup"><span data-stu-id="2dd60-185">To help you decide which channel is right, navigate to [Overview of the Microsoft Edge channels][DeployEdgeMicrosoftEdgeChannels].</span></span>  <span data-ttu-id="2dd60-186">你可以[下载测试环境中][DownloadNonstableEdge]Microsoft Edge不稳定的渠道，并使用或环境变量来指示测试 `regkey` 应用的通道首选项。</span><span class="sxs-lookup"><span data-stu-id="2dd60-186">You may download the [non-stable Microsoft Edge channel][DownloadNonstableEdge] on your test environment, and use `regkey` or environment variables to indicate the channel preference for your testing app.</span></span>  <span data-ttu-id="2dd60-187">有关详细信息，请导航到 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]。</span><span class="sxs-lookup"><span data-stu-id="2dd60-187">For more information, navigate to [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions].</span></span>  <span data-ttu-id="2dd60-188">您还可以使用 [WebDriver 自动][HowToWebdriver] 执行 WebView2 测试。</span><span class="sxs-lookup"><span data-stu-id="2dd60-188">You may also use [WebDriver][HowToWebdriver] to automate WebView2 testing.</span></span>

## <a name="fixed-version-distribution-mode"></a><span data-ttu-id="2dd60-189">固定版本分发模式</span><span class="sxs-lookup"><span data-stu-id="2dd60-189">Fixed Version distribution mode</span></span>   

<span data-ttu-id="2dd60-190">对于具有严格兼容性要求的限制环境，请考虑使用固定版本分发模式。</span><span class="sxs-lookup"><span data-stu-id="2dd60-190">For constrained environments with strict compatibility requirements, consider using the Fixed Version distribution mode.</span></span>  <span data-ttu-id="2dd60-191">使用固定版本分发模式选择并打包特定版本的 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="2dd60-191">Choose and package a specific version of the WebView2 Runtime using the Fixed Version distribution mode.</span></span>  <span data-ttu-id="2dd60-192">你可以为你的应用指定运行时更新的时间。</span><span class="sxs-lookup"><span data-stu-id="2dd60-192">You may specify the timing of Runtime updates for your app.</span></span>  <span data-ttu-id="2dd60-193">固定版本分发模式不会接收任何自动更新。</span><span class="sxs-lookup"><span data-stu-id="2dd60-193">The Fixed Version distribution mode does not receive any automatic updates.</span></span> <span data-ttu-id="2dd60-194">计划更新你的应用和运行时。</span><span class="sxs-lookup"><span data-stu-id="2dd60-194">Plan to update your app and the Runtime.</span></span>  

> [!NOTE] 
> <span data-ttu-id="2dd60-195">固定版本分发模式以前称为自带发布。</span><span class="sxs-lookup"><span data-stu-id="2dd60-195">The Fixed Version distribution mode was previously called bring-your-own.</span></span>  

<span data-ttu-id="2dd60-196">若要使用固定版本模式，请完成以下操作</span><span class="sxs-lookup"><span data-stu-id="2dd60-196">To use the Fixed Version mode, complete the following actions</span></span>

1.  <span data-ttu-id="2dd60-197">[下载][Webview2Installer] 固定版本程序包。</span><span class="sxs-lookup"><span data-stu-id="2dd60-197">[Download][Webview2Installer] the Fixed Version package.</span></span> 
1.  <span data-ttu-id="2dd60-198">使用命令行或 WinRAR 等 `expand {path to the package} -F:* {path to the destination folder}` 工具解压缩包。</span><span class="sxs-lookup"><span data-stu-id="2dd60-198">Decompress the package using command line `expand {path to the package} -F:* {path to the destination folder}` or with tools such as WinRAR.</span></span> <span data-ttu-id="2dd60-199">避免通过文件资源管理器解压缩，因为它可能无法生成正确的文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="2dd60-199">Avoid decompressing through the File Explorer as it may not generate the correct folder structure.</span></span>  
1.  <span data-ttu-id="2dd60-200">在项目中包括解压缩的固定版本二进制文件。</span><span class="sxs-lookup"><span data-stu-id="2dd60-200">Include the decompressed Fixed Version binaries in your project.</span></span>  
1.  <span data-ttu-id="2dd60-201">指示创建 WebView2 环境时固定版本二进制文件的路径。</span><span class="sxs-lookup"><span data-stu-id="2dd60-201">Indicate the path to the Fixed Version binaries when creating the WebView2 environment.</span></span>  
    *   <span data-ttu-id="2dd60-202">对于 Win32 C/C++，可以使用 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] 函数创建环境。</span><span class="sxs-lookup"><span data-stu-id="2dd60-202">For Win32 C/C++, you may create the environment using the [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] function.</span></span>  <span data-ttu-id="2dd60-203">使用 `browserExecutableFolder` 参数指示包含 的文件夹的路径 `msedgewebview2.exe` 。</span><span class="sxs-lookup"><span data-stu-id="2dd60-203">Use the `browserExecutableFolder` parameter to indicate the path to the folder containing `msedgewebview2.exe`.</span></span>  
    *   <span data-ttu-id="2dd60-204">对于 .NET，您可以执行以下任一选项来指定环境。</span><span class="sxs-lookup"><span data-stu-id="2dd60-204">For .NET, you may do either of the following options to specify the environment.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="2dd60-205">必须指定环境，WebView2 `Source` 属性才能生效。</span><span class="sxs-lookup"><span data-stu-id="2dd60-205">You must specify the environment before the WebView2 `Source` property takes effect.</span></span>  
        
        *   <span data-ttu-id="2dd60-206">在 `CreationProperties` [][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties] / WebView2 (设置 \) WPF[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\) 属性。</span><span class="sxs-lookup"><span data-stu-id="2dd60-206">Set the `CreationProperties` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\) property on the WebView2 element.</span></span>  <span data-ttu-id="2dd60-207">使用 `BrowserExecutableFolder` `CoreWebView2CreationProperties` \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\) 类中的成员指示固定版本二进制文件的路径。</span><span class="sxs-lookup"><span data-stu-id="2dd60-207">Use the `BrowserExecutableFolder` member in the `CoreWebView2CreationProperties` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\) class to indicate the path to the Fixed Version binaries.</span></span>  
        *   <span data-ttu-id="2dd60-208">使用 `EnsureCoreWebView2Async` \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async] / [WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\) 指定环境。</span><span class="sxs-lookup"><span data-stu-id="2dd60-208">Use `EnsureCoreWebView2Async` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]/[WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\) to specify the environment.</span></span>  <span data-ttu-id="2dd60-209">使用 `browserExecutableFolder` [CoreWebView2Environment.CreateAsync][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] 中的 参数指示固定版本二进制文件的路径。</span><span class="sxs-lookup"><span data-stu-id="2dd60-209">Use the `browserExecutableFolder` parameter in [CoreWebView2Environment.CreateAsync][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] to indicate the path to the Fixed Version binaries.</span></span>  
1.  <span data-ttu-id="2dd60-210">将固定版本二进制文件打包并随你的应用一起提供。</span><span class="sxs-lookup"><span data-stu-id="2dd60-210">Package and ship the Fixed Version binaries with your app.</span></span>  <span data-ttu-id="2dd60-211">根据情况更新二进制文件。</span><span class="sxs-lookup"><span data-stu-id="2dd60-211">Update the binaries as appropriate.</span></span>  
    
### <a name="known-issues-for-fixed-version"></a><span data-ttu-id="2dd60-212">固定版本的已知问题</span><span class="sxs-lookup"><span data-stu-id="2dd60-212">Known issues for Fixed Version</span></span>  

<span data-ttu-id="2dd60-213">与 Evergreen 运行时相比，固定版本没有安装过程，[这会导致][MicrosoftPlayReady]Microsoft PlayReady的情况下无法工作。</span><span class="sxs-lookup"><span data-stu-id="2dd60-213">Compared to the Evergreen Runtime, Fixed Version does not have an installation process, which causes [Microsoft PlayReady][MicrosoftPlayReady] to not work without modification.</span></span>  <span data-ttu-id="2dd60-214">可以通过完成以下操作来缓解此问题。</span><span class="sxs-lookup"><span data-stu-id="2dd60-214">You may mitigate the problem by completing the following actions.</span></span>  

1.  <span data-ttu-id="2dd60-215">找到在用户设备上部署固定版本程序包的路径，如以下位置。</span><span class="sxs-lookup"><span data-stu-id="2dd60-215">Locate the path where you deploy the Fixed Version package on the user's device, such as the following location.</span></span>
    
    ```text
    D:\myapp\Microsoft.WebView2.FixedVersionRuntime.87.0.664.8.x64
    ```  
    
1.  <span data-ttu-id="2dd60-216">在用户设备上运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="2dd60-216">Run the following commands on the user's device.</span></span>

    ```shell
    icacls {Fixed Version path} /grant *S-1-15-2-2:(OI)(CI)(RX)
    icacls {Fixed Version path} /grant *S-1-15-2-1:(OI)(CI)(RX)
    ```  

1.  <span data-ttu-id="2dd60-217">PlayReady 现在应在用户的设备上运行。</span><span class="sxs-lookup"><span data-stu-id="2dd60-217">PlayReady should be working now on the user's device.</span></span>  <span data-ttu-id="2dd60-218">在" **固定** 版本"文件夹 **的"** 安全"选项卡中，它应包括 和 `ALL APPLICATION PACKAGES` 的权限 `ALL RESTRICTED APPLICATION PACKAGES` 。</span><span class="sxs-lookup"><span data-stu-id="2dd60-218">In the **Security** tab of the **Fixed Version** folder, it should include permissions for `ALL APPLICATION PACKAGES` and `ALL RESTRICTED APPLICATION PACKAGES`.</span></span>  

    :::image type="complex" source="../media/play-ready-permission.png" alt-text="PlayReady 的权限" lightbox="../media/play-ready-permission.png":::
        <span data-ttu-id="2dd60-220">PlayReady 的权限</span><span class="sxs-lookup"><span data-stu-id="2dd60-220">Permission for PlayReady</span></span>  
    :::image-end:::  

<!-- links -->  

[ConceptsVersioning]: ./versioning.md "了解浏览器版本和 WebView2 |Microsoft Docs"  
[HowToWebdriver]: ../how-to/webdriver.md "使用驱动程序测试工具自动Microsoft Edge WebView2 |Microsoft Docs"  

[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - 全局|Microsoft Docs"  
[ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]: /microsoft-edge/webview2/reference/win32/webview2-idl#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString - 全局|Microsoft Docs"  

[DeployEdgeMicrosoftEdgeChannels]: /deployedge/microsoft-edge-channels "频道Microsoft Edge概述|Microsoft Docs"  

[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.createasync "CreateAsync - Microsoft.Web.WebView2.Core.CoreWebView2Environment 类|Microsoft Docs"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async "EnsureCoreWebView2Async -Microsoft.Web.WebView2.Wpf.WebView2 类|Microsoft Docs"  
[ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "EnsureCoreWebView2Async - Microsoft.Web.WebView2.WinForms.WebView2 类|Microsoft Docs"  
[ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.corewebview2creationproperties "CoreWebView2CreationProperties - Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties 类|Microsoft Docs"  
[ReferenceWinFormsMicrosoftWebWebview2WinForms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 类|Microsoft Docs"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.webview2.creationproperties "CreationProperties - Microsoft.Web.WebView2.Wpf.WebView2 类|Microsoft Docs"  
[ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "Microsoft.Web.WebView2.WinForms.WebView2 类|Microsoft Docs"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序|Microsoft 开发人员"  

[DownloadNonstableEdge]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈|GitHub"  

[GitHubMicrosoftEdgeWebView2SamplesWebview2Deployment]: https://github.com/MicrosoftEdge/WebView2Samples#webview2-deployment "WebView2 部署 - MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftPlayReady]: https://www.microsoft.com/playready "Microsoft PlayReady"  
