---
description: 使用 Microsoft Edge WebView2 发布应用时的分发选项
title: Microsoft Edge WebView2 应用程序的分发
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/01/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: b76ebcd4ebc30e30083e742a5e84075a5c6ef779
ms.sourcegitcommit: bb62099215e4f610f8561250fa943f58a0f836b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "10846015"
---
# <span data-ttu-id="2968b-104">使用 WebView2 的应用程序的分发</span><span class="sxs-lookup"><span data-stu-id="2968b-104">Distribution of applications using WebView2</span></span>  

<span data-ttu-id="2968b-105">WebView2 控件利用 Microsoft Edge \ （Chromium \）平台。</span><span class="sxs-lookup"><span data-stu-id="2968b-105">The WebView2 control utilizes the Microsoft Edge \(Chromium\) platform.</span></span>  <span data-ttu-id="2968b-106">打包和分发应用时，请确保在应用启动之前存在平台或 WebView2 运行时的副本。</span><span class="sxs-lookup"><span data-stu-id="2968b-106">When packaging and distributing your app, make sure a copy of the platform or the WebView2 Runtime is present before the app starts.</span></span>  <span data-ttu-id="2968b-107">下页介绍了 \ （开发人员 \）如何确保 WebView2 运行时已安装并使用 WebView2 应用程序的两种分布模式：长[绿](#evergreen-distribution-mode)和[固定版本](#fixed-version-distribution-mode)。</span><span class="sxs-lookup"><span data-stu-id="2968b-107">The following page describes how you \(the developer\) are able to ensure that the WebView2 Runtime is installed and use of the two distribution modes for your WebView2 application:  [Evergreen](#evergreen-distribution-mode) and [Fixed version](#fixed-version-distribution-mode).</span></span>  

## <span data-ttu-id="2968b-108">长绿分布模式</span><span class="sxs-lookup"><span data-stu-id="2968b-108">Evergreen distribution mode</span></span>  

<span data-ttu-id="2968b-109">长时间分布模式可确保你的应用充分利用最新功能和安全更新。</span><span class="sxs-lookup"><span data-stu-id="2968b-109">The evergreen distribution mode ensures that your app is taking advantage of the latest features and security updates.</span></span>  <span data-ttu-id="2968b-110">长绿分布模式具有以下特征。</span><span class="sxs-lookup"><span data-stu-id="2968b-110">The evergreen distribution mode has the following characteristics.</span></span>  

*   <span data-ttu-id="2968b-111">Web 平台将自动更新，无需额外的精力。</span><span class="sxs-lookup"><span data-stu-id="2968b-111">The web platform updates automatically without additional effort from you.</span></span>  
*   <span data-ttu-id="2968b-112">所有利用长绿分布模式的应用程序都使用平台二进制文件的共享副本，从而节省磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="2968b-112">All applications that leverage the evergreen distribution mode use a shared copy of the platform binaries, which saves disk space.</span></span>  

<span data-ttu-id="2968b-113">应用程序可以将多个信道 WebView2 用作 web 平台。</span><span class="sxs-lookup"><span data-stu-id="2968b-113">There are multiple channels WebView2 that applications may use as the web platform.</span></span>  <span data-ttu-id="2968b-114">默认情况下，WebView2 针对设备上提供的最稳定通道，该通道满足 WebView2 SDK 的最低版本要求。</span><span class="sxs-lookup"><span data-stu-id="2968b-114">By default, WebView2 targets the most stable channel available on the device that meets the minimum version requirement of the WebView2 SDK.</span></span>  <span data-ttu-id="2968b-115">以下频道按从最高到稳定的频道顺序列出。</span><span class="sxs-lookup"><span data-stu-id="2968b-115">The following channels are listed in order from most to least stable channel.</span></span>  

1.  <span data-ttu-id="2968b-116">WebView2 运行时 \ （预览版 \）</span><span class="sxs-lookup"><span data-stu-id="2968b-116">WebView2 Runtime \(Preview\)</span></span>  
1.  <span data-ttu-id="2968b-117">Microsoft Edge Beta 渠道</span><span class="sxs-lookup"><span data-stu-id="2968b-117">Microsoft Edge Beta Channel</span></span>  
1.  <span data-ttu-id="2968b-118">Microsoft Edge Dev 渠道</span><span class="sxs-lookup"><span data-stu-id="2968b-118">Microsoft Edge Dev Channel</span></span>  
1.  <span data-ttu-id="2968b-119">Microsoft Edge Canary 渠道</span><span class="sxs-lookup"><span data-stu-id="2968b-119">Microsoft Edge Canary Channel</span></span>    

> [!NOTE]
> <span data-ttu-id="2968b-120">对于大多数开发人员，建议使用长绿分布模型。</span><span class="sxs-lookup"><span data-stu-id="2968b-120">The evergreen distribution model is recommended for most developers.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="2968b-121">Microsoft Edge 稳定通道不是 WebView2 的有效目标，因此稍后将介绍原因。</span><span class="sxs-lookup"><span data-stu-id="2968b-121">Microsoft Edge Stable Channel is not a valid target for WebView2, and the reasons are described later.</span></span>  

<span data-ttu-id="2968b-122">有关版本控制的详细信息，请参阅[版本控制][ConceptsVersioning]和[全局][ReferenceWin3209538WebviewIdl]。</span><span class="sxs-lookup"><span data-stu-id="2968b-122">For more information about versioning, see [Versioning][ConceptsVersioning] and [Globals][ReferenceWin3209538WebviewIdl].</span></span>  

### <span data-ttu-id="2968b-123">了解 WebView2 运行时和安装程序（预览版）</span><span class="sxs-lookup"><span data-stu-id="2968b-123">Understand the WebView2 Runtime and installer (Preview)</span></span>  

<span data-ttu-id="2968b-124">Microsoft Edge 稳定频道可能未安装在应用程序运行的所有用户计算机上。</span><span class="sxs-lookup"><span data-stu-id="2968b-124">Microsoft Edge Stable Channel may not be installed on all user machines where your application runs.</span></span>  <span data-ttu-id="2968b-125">你的应用程序可能使用长绿 WebView2 运行时和安装程序 \ （Preview \），而不要求用户安装 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="2968b-125">Instead of requiring that users install Microsoft Edge, your application may use the Evergreen WebView2 Runtime and Installer \(Preview\).</span></span>  <span data-ttu-id="2968b-126">WebView2 运行时是用于运行 WebView2 应用程序的 Microsoft Edge 二进制文件的自定义副本。</span><span class="sxs-lookup"><span data-stu-id="2968b-126">The WebView2 Runtime is a customized copy of the Microsoft Edge binaries that is used to run your WebView2 applications.</span></span>  <span data-ttu-id="2968b-127">安装 WebView2 运行时时，用户无法将其用作普通浏览器。</span><span class="sxs-lookup"><span data-stu-id="2968b-127">When the WebView2 Runtime is installed, users are not able to use it as a normal browser.</span></span>  <span data-ttu-id="2968b-128">例如，没有桌面快捷方式、"开始" 菜单项、用户无法使用运行时二进制文件打开浏览器窗口等。</span><span class="sxs-lookup"><span data-stu-id="2968b-128">For example, there is no desktop shortcut, start menu entry, users are not able to open a browser window using the Runtime binaries, and so on.</span></span>  <span data-ttu-id="2968b-129">设备上的所有长绿 WebView2 应用程序都可能使用单个长时间 WebView2 运行时安装。</span><span class="sxs-lookup"><span data-stu-id="2968b-129">All Evergreen WebView2 applications on the device may use a single Evergreen WebView2 Runtime installation.</span></span>  

<span data-ttu-id="2968b-130">今天预览期间，将同时更新长绿 WebView2 运行时和 Microsoft Edge 开发频道，并具有相同的版本。</span><span class="sxs-lookup"><span data-stu-id="2968b-130">Today during the preview, the Evergreen WebView2 Runtime and Microsoft Edge Dev Channel are updated at the same time and have the same build.</span></span>  <span data-ttu-id="2968b-131">在预览期间的未来，WebView2 团队计划更新 WebView2 运行时并匹配与 Microsoft Edge Beta 通道相同的版本。</span><span class="sxs-lookup"><span data-stu-id="2968b-131">In the future during the Preview, the WebView2 Team plans to update the WebView2 Runtime and match the same build as the Microsoft Edge Beta Channel.</span></span>  <span data-ttu-id="2968b-132">将来当 WebView2 达到常规可用性 \ （GA \）时，WebView2 团队计划更新 WebView2 运行时，并与 Microsoft Edge 稳定通道匹配相同的版本。</span><span class="sxs-lookup"><span data-stu-id="2968b-132">In the future when WebView2 reaches General Availability \(GA\), the WebView2 Team plans to update the WebView2 Runtime and match the same build as the Microsoft Edge Stable Channel.</span></span>  <span data-ttu-id="2968b-133">GA 后，应用程序应在生产中使用 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="2968b-133">After GA, applications should use the WebView2 Runtime in production.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="2968b-134">预览期间不要在生产中发运 WebView2 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2968b-134">Do not ship WebView2 applications in production during the preview.</span></span>  

<span data-ttu-id="2968b-135">开发人员可以确保在应用程序启动之前安装长绿 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="2968b-135">Developers are recommended to ensure that the Evergreen WebView2 Runtime is installed before application launches.</span></span> <span data-ttu-id="2968b-136">下面是一个示例工作流。</span><span class="sxs-lookup"><span data-stu-id="2968b-136">Below is an example workflow.</span></span>  

1.  <span data-ttu-id="2968b-137">下载最新的长[绿 WebView2 运行时安装程序][Webview2Installer]。</span><span class="sxs-lookup"><span data-stu-id="2968b-137">Download the latest [Evergreen WebView2 Runtime Installer][Webview2Installer].</span></span>  
1.  <span data-ttu-id="2968b-138">在应用程序安装程序或更新程序中包括安装程序。</span><span class="sxs-lookup"><span data-stu-id="2968b-138">Include the installer in your application installer or updater.</span></span>  
1.  <span data-ttu-id="2968b-139">在应用程序安装或更新过程中，通过使用[GetAvailableCoreWebView2BrowserVersionString](https://docs.microsoft.com/en-us/microsoft-edge/webview2/reference/win32/0-9-538/webview2-idl#getavailablecorewebview2browserversionstring) API 并检查 versionInfo 是否为 NULL 来检查用户计算机上是否已安装了长时间 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="2968b-139">During your application installation or update, check if the Evergreen WebView2 Runtime is already installed on the user machine, by using the [GetAvailableCoreWebView2BrowserVersionString](https://docs.microsoft.com/en-us/microsoft-edge/webview2/reference/win32/0-9-538/webview2-idl#getavailablecorewebview2browserversionstring) API and checking whether the versionInfo is NULL.</span></span> <span data-ttu-id="2968b-140">如果未安装，应用程序安装程序/更新程序可以从提升的进程或命令提示符处无提示地调用运行时安装程序 `MicrosoftEdgeWebView2RuntimeInstallerX64.exe /silent /install` 。</span><span class="sxs-lookup"><span data-stu-id="2968b-140">If not installed, the application installer/updater can silently invoke the runtime installer from an elevated process or command prompt with `MicrosoftEdgeWebView2RuntimeInstallerX64.exe /silent /install`.</span></span> 

<span data-ttu-id="2968b-141">你可能需要更改上述工作流，具体取决于你的方案。</span><span class="sxs-lookup"><span data-stu-id="2968b-141">Depending on your scenario, you may need to change the above workflow.</span></span>  <span data-ttu-id="2968b-142">例如，你的应用程序安装程序可能会下载长绿 WebView2 运行时安装程序，而不是将其包含在你的应用程序包中。</span><span class="sxs-lookup"><span data-stu-id="2968b-142">For example, your application installer may download the Evergreen WebView2 Runtime Installer instead of including it in your application package.</span></span>  

> [!NOTE]
> <span data-ttu-id="2968b-143">WebView2 运行时和 WebView2 运行时安装程序都在预览版中。</span><span class="sxs-lookup"><span data-stu-id="2968b-143">Both the WebView2 Runtime and WebView2 Runtime installer are in preview.</span></span>  <span data-ttu-id="2968b-144">预览具有有限的初始范围，并且仅在 x64 上的 Windows 10 上以独立的单机安装的形式提供。</span><span class="sxs-lookup"><span data-stu-id="2968b-144">The preview has a limited initial scope and is only available as a standalone, per-machine install on Windows 10 on x64.</span></span>  <span data-ttu-id="2968b-145">将来，计划对 Windows 7、x86 和 ARM64 的支持。</span><span class="sxs-lookup"><span data-stu-id="2968b-145">In the future, support for Windows 7, x86, and ARM64 is planned.</span></span>  

### <span data-ttu-id="2968b-146">使用 WebView2 运行时和非稳定 Microsoft Edge 通道的最佳做法</span><span class="sxs-lookup"><span data-stu-id="2968b-146">Best practices for using WebView2 Runtime and non-stable Microsoft Edge channels</span></span>  

<span data-ttu-id="2968b-147">预览期间请考虑以下建议。</span><span class="sxs-lookup"><span data-stu-id="2968b-147">Consider the following recommendations during the preview.</span></span>  

*   <span data-ttu-id="2968b-148">请确保使用长[绿 WebView2 运行时和安装程序][Webview2Installer]来开发或测试打包和分发管道。</span><span class="sxs-lookup"><span data-stu-id="2968b-148">Make sure to use the [Evergreen WebView2 Runtime and Installer][Webview2Installer] to develop or test your packaging and distribution pipeline.</span></span>  <span data-ttu-id="2968b-149">将来，生产应用程序应包含安装程序。</span><span class="sxs-lookup"><span data-stu-id="2968b-149">In the future, your production application should include the installer.</span></span>  
*   <span data-ttu-id="2968b-150">对于开发应用程序，你可以使用长绿 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="2968b-150">For developing your application, you may use the Evergreen WebView2 Runtime.</span></span>  <span data-ttu-id="2968b-151">但是，当运行时从开发人员通道切换到 Beta 通道或稳定通道时，运行时内部版本号可能不符合最新的预览 WebView2 SDK 最低版本要求。</span><span class="sxs-lookup"><span data-stu-id="2968b-151">However, as the runtime shifts from the Dev Channel to the Beta Channel or Stable Channel, the runtime build number may not meet the most recent preview WebView2 SDK minimum version requirements.</span></span>  <span data-ttu-id="2968b-152">如果您想要使用最新的 SDK，请安装 Microsoft Edge 的 "未安装" 通道以确保设备上有兼容的版本。</span><span class="sxs-lookup"><span data-stu-id="2968b-152">If you wish to use the most recent SDK, install the Microsoft Edge Canary channel to ensure a compatible build is available on the device.</span></span>  <span data-ttu-id="2968b-153">有关版本控制的详细信息，请参阅[版本控制][ConceptsVersioning]。</span><span class="sxs-lookup"><span data-stu-id="2968b-153">For more information about versioning, see [Versioning][ConceptsVersioning].</span></span>  
*   <span data-ttu-id="2968b-154">若要测试您的 web 内容，使其与不在稳定频道中提供的平台更改兼容，请根据需要使用相应的非稳定通道。</span><span class="sxs-lookup"><span data-stu-id="2968b-154">To test your web content for compatibility with changes to the platform not available in the Stable Channel, use the appropriate non-Stable Channel as required.</span></span>  

## <span data-ttu-id="2968b-155">固定版本分发模式</span><span class="sxs-lookup"><span data-stu-id="2968b-155">Fixed version distribution mode</span></span>  

> [!NOTE]
> <span data-ttu-id="2968b-156">固定版本分发模型目前不可用。</span><span class="sxs-lookup"><span data-stu-id="2968b-156">The fixed version distribution model is currently not available.</span></span>  

<span data-ttu-id="2968b-157">对于受限制的环境，有计划支持固定版本 \ （以前命名的 "携带后" \）分发模式。</span><span class="sxs-lookup"><span data-stu-id="2968b-157">For constrained environments, there are plans to support a fixed version \(previously named bring-your-own\) distribution mode.</span></span>  <span data-ttu-id="2968b-158">固定版本分发模式允许你选择和打包特定版本的 WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="2968b-158">The fixed version distribution mode allows you to select and package a specific version of the WebView2 Runtime.</span></span>  <span data-ttu-id="2968b-159">固定版本分发模式允许你控制你的应用程序使用哪个版本的 WebView2 运行时，以及何时更新用户计算机。</span><span class="sxs-lookup"><span data-stu-id="2968b-159">The fixed version distribution mode allows you to control which version of the WebView2 Runtime is used by your application, and when user machines are updated.</span></span>  <span data-ttu-id="2968b-160">固定版本分发模式不会接收任何自动更新，你应该计划手动应用更新。</span><span class="sxs-lookup"><span data-stu-id="2968b-160">The fixed version distribution mode does not receive any automatic updates, and you should plan to manually apply updates.</span></span>  

<!-- links -->  

[ConceptsVersioning]: ./versioning.md "了解浏览器版本和 WebView2 |Microsoft 文档"  
[ReferenceWin3209538WebviewIdl]: ../reference/win32/0-9-538/webview2-idl.md  "Globals |Microsoft 文档"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序"  
