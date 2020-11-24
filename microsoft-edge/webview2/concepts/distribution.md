---
description: 使用 Microsoft Edge WebView2 发布应用时的分发选项
title: Microsoft Edge WebView2 应用的分发
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 0cbaaeade03feac766647c55bb5edabfe8e8456e
ms.sourcegitcommit: 7b16c3e6eb458e0b2458279c2498597fb227bc8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "11182907"
---
# <span data-ttu-id="ed1a5-104">使用 WebView2 的应用分发</span><span class="sxs-lookup"><span data-stu-id="ed1a5-104">Distribution of apps using WebView2</span></span>  

<span data-ttu-id="ed1a5-105">在分发 WebView2 应用时，请确保在应用启动之前，支持的 web 平台（ [WebView2 运行时][Webview2Installer]）存在。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-105">When distributing your WebView2 app, ensure the backing web platform, the [WebView2 Runtime][Webview2Installer], is present before the app starts.</span></span>  <span data-ttu-id="ed1a5-106">本文介绍如何 (开发人员 \ ) 安装 WebView2 运行时，并为 WebView2 应用使用两种分发模式：长  [绿](#evergreen-distribution-mode) 和 [固定版本](#fixed-version-distribution-mode)。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-106">This article describes how you \(the developer\) install the WebView2 Runtime, and use the two distribution modes for your WebView2 app:  [Evergreen](#evergreen-distribution-mode) and [Fixed Version](#fixed-version-distribution-mode).</span></span>  

## <span data-ttu-id="ed1a5-107">长绿分布模式</span><span class="sxs-lookup"><span data-stu-id="ed1a5-107">Evergreen distribution mode</span></span>  

> [!NOTE]
> <span data-ttu-id="ed1a5-108">对于大多数开发人员，建议使用长绿分布模式。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-108">The Evergreen distribution mode is recommended for most developers.</span></span>  

<span data-ttu-id="ed1a5-109">长时间分布模式可确保你的应用充分利用最新功能和安全更新。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-109">The Evergreen distribution mode ensures that your app is taking advantage of the latest features and security updates.</span></span>  <span data-ttu-id="ed1a5-110">它具有下列特征。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-110">It has the following characteristics.</span></span>  

*   <span data-ttu-id="ed1a5-111">基础 web 平台 \ (WebView2 运行时 \ ) 自动更新，无需额外的精力。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-111">The underlying web platform \(WebView2 Runtime\) updates automatically without additional effort from you.</span></span>  
*   <span data-ttu-id="ed1a5-112">所有使用长时间分布模式的应用均使用长绿 WebView2 运行时的共享副本，该副本节省磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-112">All apps that use the Evergreen distribution mode use a shared copy of the Evergreen WebView2 Runtime, which saves disk space.</span></span>  
    
### <span data-ttu-id="ed1a5-113">了解 WebView2 运行时</span><span class="sxs-lookup"><span data-stu-id="ed1a5-113">Understanding the WebView2 Runtime</span></span>  

<span data-ttu-id="ed1a5-114">WebView2 运行时是可再发行的运行时，用作 WebView2 应用的支持 web 平台。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-114">The WebView2 Runtime is a redistributable runtime and serves as the backing web platform for WebView2 apps.</span></span>  <span data-ttu-id="ed1a5-115">该概念类似于 Visual c + + 或适用于 c + +/.NET 应用的 .NET 运行时。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-115">The concept is similar to Visual C++ or the .NET Runtime for C++/.NET apps.</span></span>  <span data-ttu-id="ed1a5-116">运行时包含已修改的 Microsoft Edge \ (Chromium \ ) 二进制文件，这些二进制文件对应用进行了微调和测试。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-116">The Runtime contains modified Microsoft Edge \(Chromium\) binaries that are fine-tuned and tested for apps.</span></span>  <span data-ttu-id="ed1a5-117">在安装时，运行时不会显示为用户可见的浏览器。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-117">The Runtime does not appear as a user-visible browser upon installation.</span></span>  <span data-ttu-id="ed1a5-118">例如，用户没有浏览器桌面快捷方式或 "开始" 菜单项。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-118">For example, a user does not have a browser desktop shortcut or start menu entry.</span></span>  

<span data-ttu-id="ed1a5-119">在开发和测试期间，你可以使用作为后备 web 平台。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-119">During development and testing, you may use either as the backing web platform.</span></span>  

*   <span data-ttu-id="ed1a5-120">WebView2 运行时</span><span class="sxs-lookup"><span data-stu-id="ed1a5-120">The WebView2 Runtime</span></span>  
*   <span data-ttu-id="ed1a5-121">任何预览体验成员 \ (非稳定 \ ) Microsoft Edge \ (Chromium \ ) 浏览器频道</span><span class="sxs-lookup"><span data-stu-id="ed1a5-121">Any Insider \(non-stable\) Microsoft Edge \(Chromium\) browser channel</span></span>  
    
<span data-ttu-id="ed1a5-122">在生产环境中，必须确保用户设备上的运行时在应用启动前才存在。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-122">In production environments, you must ensure the Runtime is present on user devices before the app starts.</span></span>  <span data-ttu-id="ed1a5-123">Microsoft Edge 稳定通道不可用于 WebView2 用法。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-123">The Microsoft Edge Stable channel is unavailable for WebView2 usage.</span></span>  <span data-ttu-id="ed1a5-124">决策可防止应用在生产中的浏览器上参与依赖。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-124">The decision prevents apps from taking a dependency on the browser in production.</span></span>

<span data-ttu-id="ed1a5-125">不要在浏览器上执行依赖关系，原因如下：</span><span class="sxs-lookup"><span data-stu-id="ed1a5-125">Do not take a dependency on the browser because:</span></span>  

*   <span data-ttu-id="ed1a5-126">Microsoft Edge \ (Chromium \ ) 不保证在所有用户设备上都存在。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-126">Microsoft Edge \(Chromium\) is not guaranteed to be present on all user devices.</span></span>  <span data-ttu-id="ed1a5-127">例如，从 Windows Update 断开的设备或不是由 Microsoft 直接管理的设备，而不是由 Microsoft (直接管理的，教育机构的大型企业和市场的 ) 可能没有浏览器。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-127">For example, devices disconnected from Windows Update or not managed by Microsoft directly \(a large portion of the Enterprise and EDU market\) may not have the browser.</span></span>  <span data-ttu-id="ed1a5-128">允许你分发 WebView2 运行时，可避免将浏览器作为应用的必备项。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-128">Allowing you to distribute the WebView2 Runtime avoids taking a dependency on the browser as a pre-requisite for apps.</span></span>  
*   <span data-ttu-id="ed1a5-129">浏览器和应用具有不同的用例，因此对浏览器的依赖可能会对你的应用产生意外的副作用。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-129">Browsers and apps have different use cases, and so taking a dependency on a browser may have unintended side-effects on your apps.</span></span>  <span data-ttu-id="ed1a5-130">例如，IT 管理员可以针对内部网站兼容性版本控制浏览器。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-130">For example, IT admins may version-control the browser for internal website compatibility.</span></span>  <span data-ttu-id="ed1a5-131">WebView2 运行时允许应用在浏览器更新处于活动的管理期间保持长绿。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-131">The WebView2 Runtime allows apps to stay evergreen while browser updates are being actively managed.</span></span>  
*   <span data-ttu-id="ed1a5-132">与浏览器相反，运行时是为应用方案开发和测试的，在某些情况下，可能包括浏览器中尚不提供的 bug 修复。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-132">As opposed to the browser, the Runtime is developed and tested for app scenarios and in some cases may include bug fixes not yet available in the browser.</span></span>  
    
<span data-ttu-id="ed1a5-133">将来，长绿 WebView2 运行时计划随 Windows 将来的版本提供。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-133">In the future, the Evergreen WebView2 Runtime plans to ship with future releases of Windows.</span></span>  <span data-ttu-id="ed1a5-134">将运行时与你的生产应用进行部署，直到运行时更广泛地可用。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-134">Deploy the Runtime with your production app until the Runtime becomes more universally available.</span></span>  

### <span data-ttu-id="ed1a5-135">部署长绿 WebView2 运行时</span><span class="sxs-lookup"><span data-stu-id="ed1a5-135">Deploying the Evergreen WebView2 Runtime</span></span>  

<span data-ttu-id="ed1a5-136">设备上的所有长时间应用仅需要一个安装长绿 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-136">Only one installation of the Evergreen WebView2 Runtime is needed for all Evergreen apps on the device.</span></span>  <span data-ttu-id="ed1a5-137">[WebView2 运行时下载页面][Webview2Installer]上提供了许多工具。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-137">There are a number of tools available on the [WebView2 Runtime download page][Webview2Installer].</span></span>  <span data-ttu-id="ed1a5-138">以下工具可帮助你部署长绿运行时。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-138">The following tools help you deploy the Evergreen Runtime.</span></span>  

*   <span data-ttu-id="ed1a5-139">WebView2 运行时引导程序是大约 2 MB \ ) 安装程序的小型 (。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-139">WebView2 Runtime Bootstrapper is a tiny \(approximately 2 MB\) installer.</span></span>  <span data-ttu-id="ed1a5-140">WebView2 运行时引导程序从与用户的设备体系结构匹配的 Microsoft 服务器下载和安装长绿运行时。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-140">WebView2 Runtime Bootstrapper downloads and installs the Evergreen Runtime from Microsoft servers that matches the user's device architecture.</span></span>  
*   <span data-ttu-id="ed1a5-141">使用链接以编程方式下载引导程序。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-141">Use a link to programmatically download the bootstrapper.</span></span>  
*   <span data-ttu-id="ed1a5-142">WebView2 运行时独立安装程序是在脱机环境下安装长绿 WebView2 运行时的完整安装程序。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-142">WebView2 Runtime Standalone Installer is a full installer that installs the Evergreen WebView2 Runtime in offline environments.</span></span>  
    
<span data-ttu-id="ed1a5-143">当前，引导程序和独立安装程序仅支持每台计算机安装，这需要提升。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-143">Currently, both the bootstrapper and standalone installer only support per-machine installs, which requires elevation.</span></span>  <span data-ttu-id="ed1a5-144">如果安装程序运行时没有提升权限，系统将提示用户提升权限。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-144">If an installer is run without elevation, the user is prompted to elevate permissions.</span></span>  

<span data-ttu-id="ed1a5-145">使用以下工作流以确保在你的应用启动之前已安装运行时。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-145">Use following workflows to ensure the Runtime is already installed before your app launches.</span></span>  <span data-ttu-id="ed1a5-146">你可以根据你的方案调整工作流。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-146">You may adjust your workflow depending on your scenario.</span></span>  <span data-ttu-id="ed1a5-147">示例代码可在 [示例][GitHubMicrosoftedgeWebView2samplesWebview2Deployment]存储库中使用。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-147">Sample code is available in the [Samples repo][GitHubMicrosoftedgeWebView2samplesWebview2Deployment].</span></span>  

#### <span data-ttu-id="ed1a5-148">仅联机部署</span><span class="sxs-lookup"><span data-stu-id="ed1a5-148">Online-only deployment</span></span>  

<span data-ttu-id="ed1a5-149">如果您有一个仅联机部署方案，并且假定用户拥有 internet 访问权限，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-149">If you have an online-only deployment scenario where users are assumed to have internet access, complete the following steps.</span></span>  

1.  <span data-ttu-id="ed1a5-150">在应用设置期间，确保已安装运行时。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-150">During your app setup, ensure the Runtime is already installed.</span></span>  <span data-ttu-id="ed1a5-151">若要验证，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-151">To  verify, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="ed1a5-152">检查 regkey 是否 `pv (REG_SZ)` 存在且不是 `null` 空的。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-152">Inspect if the `pv (REG_SZ)` regkey exists and is not `null` or empty.</span></span>  <span data-ttu-id="ed1a5-153">`pv (REG_SZ)`在以下位置查找。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-153">Find  `pv (REG_SZ)` at the following location.</span></span>  
        
        <span data-ttu-id="ed1a5-154">在64位 Windows 上</span><span class="sxs-lookup"><span data-stu-id="ed1a5-154">On 64-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        <span data-ttu-id="ed1a5-155">在32位 Windows 上</span><span class="sxs-lookup"><span data-stu-id="ed1a5-155">On 32-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   <span data-ttu-id="ed1a5-156">运行 [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] 并确保 `versionInfo` 为 `NULL` 。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-156">Run [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] and ensure the `versionInfo` is `NULL`.</span></span>  
1.  <span data-ttu-id="ed1a5-157">如果未安装运行时，请使用链接以编程方式下载引导程序。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-157">If the Runtime is not installed, use the link to programmatically download the bootstrapper.</span></span>  
1.  <span data-ttu-id="ed1a5-158">使用 "静默安装" 从提升的进程或命令提示符处调用引导 `MicrosoftEdgeWebview2Setup.exe /silent /install` 程序。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-158">Invoke the bootstrapper from an elevated process or command prompt with `MicrosoftEdgeWebview2Setup.exe /silent /install` for silent install.</span></span>  
    
<span data-ttu-id="ed1a5-159">以前的工作流具有以下优点。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-159">The previous workflow has the following benefits.</span></span>  

*   <span data-ttu-id="ed1a5-160">仅在需要时或不需要打包安装程序时，才安装运行时。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-160">Install the Runtime only when needed or when you are not required to package installers.</span></span>  
*   <span data-ttu-id="ed1a5-161">引导程序将自动检测设备体系结构并安装匹配的运行时。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-161">The bootstrapper automatically detects device architecture and installs the matching Runtime.</span></span>  
*   <span data-ttu-id="ed1a5-162">以静默方式安装运行时。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-162">Install the Runtime silently.</span></span>  
    
<span data-ttu-id="ed1a5-163">你还可以选择将引导程序与你的应用打包，而不是按需以编程方式下载它。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-163">You may also choose to package the bootstrapper with your app instead of programmatically downloading it on demand.</span></span>  

#### <span data-ttu-id="ed1a5-164">脱机部署</span><span class="sxs-lookup"><span data-stu-id="ed1a5-164">Offline deployment</span></span>  

<span data-ttu-id="ed1a5-165">如果你有一个脱机部署方案，其中应用部署必须完全脱机工作，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-165">If you have an offline deployment scenario where app deployment has to work entirely offline, complete the following steps.</span></span>  

1.  <span data-ttu-id="ed1a5-166">下载 [独立安装程序][Webview2Installer]。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-166">Download the [standalone installer][Webview2Installer].</span></span>  
1.  <span data-ttu-id="ed1a5-167">在应用安装程序或更新程序中包括安装程序。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-167">Include the installer in your app installer or updater.</span></span>  
1.  <span data-ttu-id="ed1a5-168">在应用设置期间，确保已安装运行时。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-168">During your app setup, ensure the Runtime is already installed.</span></span>  <span data-ttu-id="ed1a5-169">若要验证，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-169">To  verify, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="ed1a5-170">检查 regkey 是否 `pv (REG_SZ)` 存在且不是 `null` 空的。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-170">Inspect if the `pv (REG_SZ)` regkey exists and is not `null` or empty.</span></span>  <span data-ttu-id="ed1a5-171">`pv (REG_SZ)`在以下位置查找。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-171">Find  `pv (REG_SZ)` at the following location.</span></span>  
        
        <span data-ttu-id="ed1a5-172">在64位 Windows 上</span><span class="sxs-lookup"><span data-stu-id="ed1a5-172">On 64-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        <span data-ttu-id="ed1a5-173">在32位 Windows 上</span><span class="sxs-lookup"><span data-stu-id="ed1a5-173">On 32-bit Windows</span></span>  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   <span data-ttu-id="ed1a5-174">运行 [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] 并确保 `versionInfo` 为 `NULL` 。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-174">Run [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] and ensure the `versionInfo` is `NULL`.</span></span>  
1.  <span data-ttu-id="ed1a5-175">如果未安装运行时，请运行独立安装程序。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-175">If the Runtime is not installed, run the standalone installer.</span></span>  <span data-ttu-id="ed1a5-176">如果要运行静默安装，请从提升的进程运行安装程序，或复制并运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-176">If you want to run a silent installation, either run the installer from an elevated process or copy and run the following command.</span></span>  
    
    ```shell
    MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install
    ```  
    
### <span data-ttu-id="ed1a5-177">在长绿模式下保持兼容</span><span class="sxs-lookup"><span data-stu-id="ed1a5-177">Stay compatible in Evergreen mode</span></span>  

<span data-ttu-id="ed1a5-178">Web 不断发展。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-178">The Web is constantly evolving.</span></span>  <span data-ttu-id="ed1a5-179">长时间 WebView2 运行时保持最新，为你提供最新的功能和安全修补程序。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-179">The Evergreen WebView2 Runtime is kept up to date to provide you with the latest features and security fixes.</span></span>  <span data-ttu-id="ed1a5-180">为了确保你的应用与 web 保持兼容，你应该设置测试基础结构。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-180">To ensure your app stays compatible with the web, you should set up testing infrastructure.</span></span>  

<span data-ttu-id="ed1a5-181">非稳定的 Microsoft Edge 通道 \ (Beta/Dev/sneak \ ) 提供一种可快速查看 WebView2 运行时中所进入的内容的功能。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-181">Non-stable Microsoft Edge channels \(Beta/Dev/Canary\) provide a sneak peek into what is coming next into WebView2 Runtime.</span></span>  <span data-ttu-id="ed1a5-182">与开发 Microsoft Edge 网站一样，你应该定期测试你的 WebView2 应用。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-182">Just like developing websites for Microsoft Edge, you should test your WebView2 app regularly.</span></span>  <span data-ttu-id="ed1a5-183">针对其中一个非稳定信道测试你的 WebView2 应用，如果出现问题，请更新你的应用或 [报告问题][GithubMicrosoftedgeWebviewfeedback] 。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-183">Test your WebView2 app against one of the non-stable channels, and update your app or [report issues][GithubMicrosoftedgeWebviewfeedback] if issues arise.</span></span> <span data-ttu-id="ed1a5-184">通常情况下，推荐使用开发人员和 Beta。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-184">Typically Dev and Beta are the recommended channels.</span></span>  <span data-ttu-id="ed1a5-185">若要帮助确定哪种频道正确，请导航到 [Microsoft Edge 频道概述][DeployEdgeMicrosoftEdgeChannels]。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-185">To help you decide which channel is right, navigate to [Overview of the Microsoft Edge channels][DeployEdgeMicrosoftEdgeChannels].</span></span>  <span data-ttu-id="ed1a5-186">你可以在你的测试环境中下载 [不稳定的 Microsoft Edge 通道][DownloadNonstableEdge] ，并使用 `regkey` 或环境变量指示测试应用的通道首选项。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-186">You may download the [non-stable Microsoft Edge channel][DownloadNonstableEdge] on your test environment, and use `regkey` or environment variables to indicate the channel preference for your testing app.</span></span>  <span data-ttu-id="ed1a5-187">有关详细信息，请导航到 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-187">For more information, navigate to [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions].</span></span>  <span data-ttu-id="ed1a5-188">您也可以使用 [WebDriver][HowtoWebdriver] 自动执行 WebView2 测试。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-188">You may also use [WebDriver][HowtoWebdriver] to automate WebView2 testing.</span></span>

## <span data-ttu-id="ed1a5-189">固定版本分发模式</span><span class="sxs-lookup"><span data-stu-id="ed1a5-189">Fixed Version distribution mode</span></span>   

<span data-ttu-id="ed1a5-190">对于具有严格兼容性要求的受限环境，请考虑使用固定版本分发模式。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-190">For constrained environments with strict compatibility requirements, consider using the Fixed Version distribution mode.</span></span>  <span data-ttu-id="ed1a5-191">使用固定版本分发模式选择并打包特定版本的 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-191">Choose and package a specific version of the WebView2 Runtime using the Fixed Version distribution mode.</span></span>  <span data-ttu-id="ed1a5-192">你可以指定你的应用的运行时更新的计时。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-192">You may specify the timing of Runtime updates for your app.</span></span>  <span data-ttu-id="ed1a5-193">固定版本分发模式不会接收任何自动更新。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-193">The Fixed Version distribution mode does not receive any automatic updates.</span></span> <span data-ttu-id="ed1a5-194">计划更新你的应用和运行时。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-194">Plan to update your app and the Runtime.</span></span>  

> [!NOTE] 
> <span data-ttu-id="ed1a5-195">固定版本分发模式以前称为 "携带"。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-195">The Fixed Version distribution mode was previously called bring-your-own.</span></span>  

<span data-ttu-id="ed1a5-196">若要使用 "固定版本" 模式，请完成以下操作</span><span class="sxs-lookup"><span data-stu-id="ed1a5-196">To use the Fixed Version mode, complete the following actions</span></span>

1.  <span data-ttu-id="ed1a5-197">[下载][Webview2Installer] 已修复的版本程序包。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-197">[Download][Webview2Installer] the Fixed Version package.</span></span> 
1.  <span data-ttu-id="ed1a5-198">使用命令行 `expand {path to the package} -F:* {path to the destination folder}` 或 WinRAR 之类的工具解压缩程序包。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-198">Decompress the package using command line `expand {path to the package} -F:* {path to the destination folder}` or with tools such as WinRAR.</span></span> <span data-ttu-id="ed1a5-199">避免在文件资源管理器中解压缩，因为它可能不会生成正确的文件夹结构。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-199">Avoid decompressing through the File Explorer as it may not generate the correct folder structure.</span></span>  
1.  <span data-ttu-id="ed1a5-200">在项目中包含解压缩的固定版本二进制文件。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-200">Include the decompressed Fixed Version binaries in your project.</span></span>  
1.  <span data-ttu-id="ed1a5-201">在创建 WebView2 环境时，指示固定版本二进制文件的路径。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-201">Indicate the path to the Fixed Version binaries when creating the WebView2 environment.</span></span>  
    *   <span data-ttu-id="ed1a5-202">对于 Win32 C/c + +，你可以使用 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] 函数创建环境。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-202">For Win32 C/C++, you may create the environment using the [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] function.</span></span>  <span data-ttu-id="ed1a5-203">使用 `browserExecutableFolder` 参数指示包含的文件夹的路径 `msedgewebview2.exe` 。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-203">Use the `browserExecutableFolder` parameter to indicate the path to the folder containing `msedgewebview2.exe`.</span></span>  
    *   <span data-ttu-id="ed1a5-204">对于 .NET，你可以执行以下任一选项来指定环境。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-204">For .NET, you may do either of the following options to specify the environment.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="ed1a5-205">必须先指定环境，WebView2 属性才 `Source` 会生效。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-205">You must specify the environment before the WebView2 `Source` property takes effect.</span></span>  
        
        *   <span data-ttu-id="ed1a5-206">`CreationProperties`在 WebView2 元素上设置 \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\ ) 属性。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-206">Set the `CreationProperties` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\) property on the WebView2 element.</span></span>  <span data-ttu-id="ed1a5-207">使用 `BrowserExecutableFolder` `CoreWebView2CreationProperties` \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\ ) 类中的成员指示固定版本二进制文件的路径。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-207">Use the `BrowserExecutableFolder` member in the `CoreWebView2CreationProperties` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]/[WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\) class to indicate the path to the Fixed Version binaries.</span></span>  
        *   <span data-ttu-id="ed1a5-208">使用 `EnsureCoreWebView2Async` \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async] / [WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\ ) 指定环境。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-208">Use `EnsureCoreWebView2Async` \([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]/[WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\) to specify the environment.</span></span>  <span data-ttu-id="ed1a5-209">使用 `browserExecutableFolder` [CoreWebView2Environment][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] 中的参数指示固定版本二进制文件的路径。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-209">Use the `browserExecutableFolder` parameter in [CoreWebView2Environment.CreateAsync][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] to indicate the path to the Fixed Version binaries.</span></span>  
1.  <span data-ttu-id="ed1a5-210">将固定版本的二进制文件打包并与你的应用一起发送。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-210">Package and ship the Fixed Version binaries with your app.</span></span>  <span data-ttu-id="ed1a5-211">根据需要更新二进制文件。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-211">Update the binaries as appropriate.</span></span>  
    
### <span data-ttu-id="ed1a5-212">修复版本的已知问题</span><span class="sxs-lookup"><span data-stu-id="ed1a5-212">Known issues for Fixed Version</span></span>  

<span data-ttu-id="ed1a5-213">与长时间运行时相比，修复的版本不具有安装过程，这将导致 [Microsoft PlayReady][MicrosoftPlayReady] 在未经修改的情况下运行。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-213">Compared to the Evergreen Runtime, Fixed Version does not have an installation process, which causes [Microsoft PlayReady][MicrosoftPlayReady] to not work without modification.</span></span>  <span data-ttu-id="ed1a5-214">你可以通过完成以下操作来缓解此问题。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-214">You may mitigate the problem by completing the following actions.</span></span>  

1.  <span data-ttu-id="ed1a5-215">找到你在用户设备上部署固定版本程序包的路径，例如以下位置。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-215">Locate the path where you deploy the Fixed Version package on the user's device, such as the following location.</span></span>
    
    ```text
    D:\myapp\Microsoft.WebView2.FixedVersionRuntime.87.0.664.8.x64
    ```  
    
1.  <span data-ttu-id="ed1a5-216">在用户的设备上运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-216">Run the following commands on the user's device.</span></span>

    ```shell
    icacls {Fixed Version path} /grant *S-1-15-2-2:(OI)(CI)(RX)
    icacls {Fixed Version path} /grant *S-1-15-2-1:(OI)(CI)(RX)
    ```  

1.  <span data-ttu-id="ed1a5-217">PlayReady 应立即在用户的设备上工作。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-217">PlayReady should be working now on the user's device.</span></span>  <span data-ttu-id="ed1a5-218">在 "**固定版本**" 文件夹的 "**安全**" 选项卡中，应包括和的权限 `ALL APPLICATION PACKAGES` `ALL RESTRICTED APPLICATION PACKAGES` 。</span><span class="sxs-lookup"><span data-stu-id="ed1a5-218">In the **Security** tab of the **Fixed Version** folder, it should include permissions for `ALL APPLICATION PACKAGES` and `ALL RESTRICTED APPLICATION PACKAGES`.</span></span>  

    :::image type="complex" source="../media/play-ready-permission.png" alt-text="PlayReady 的权限" lightbox="../media/play-ready-permission.png":::
        <span data-ttu-id="ed1a5-220">PlayReady 的权限</span><span class="sxs-lookup"><span data-stu-id="ed1a5-220">Permission for PlayReady</span></span>  
    :::image-end:::  

<!-- links -->  

[ConceptsVersioning]: ./versioning.md "了解浏览器版本和 WebView2 |Microsoft 文档"  
[HowtoWebdriver]: ../howto/webdriver.md "通过 Microsoft Edge 驱动程序自动化和测试 WebView2 |Microsoft 文档"  

[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft 文档"  
[ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring]: /microsoft-edge/webview2/reference/win32/webview2-idl#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString-Globals |Microsoft 文档"  

[DeployEdgeMicrosoftEdgeChannels]: /deployedge/microsoft-edge-channels "Microsoft Edge 频道概述 |Microsoft 文档"  

[ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.createasync "CreateAsync-WebView2 | CoreWebView2Environment 类 |Microsoft 文档"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.wpf.webview2.ensurecorewebview2async "EnsureCoreWebView2Async-WebView2 | WebView2 类 |Microsoft 文档"  
[ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "EnsureCoreWebView2Async-WinForms 类 | WebView2 类 |Microsoft 文档"  
[ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.corewebview2creationproperties "CoreWebView2CreationProperties-WebView2 | CoreWebView2CreationProperties 类 |Microsoft 文档"  
[ReferenceWinFormsMicrosoftWebWebview2WinForms]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 类 | WebView2 类 |Microsoft 文档"  
[ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties]: /dotnet/api/microsoft.web.webview2.wpf.webview2.creationproperties "CreationProperties-WebView2 | WebView2 类 |Microsoft 文档"  
[ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "WebView2 类 | WebView2 类 |Microsoft 文档"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序 |Microsoft 开发人员"  

[DownloadNonstableEdge]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈 |GitHub"  

[GitHubMicrosoftEdgeWebView2SamplesWebview2Deployment]: https://github.com/MicrosoftEdge/WebView2Samples#webview2-deployment "WebView2 部署-MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftPlayReady]: https://www.microsoft.com/playready "Microsoft PlayReady"  
