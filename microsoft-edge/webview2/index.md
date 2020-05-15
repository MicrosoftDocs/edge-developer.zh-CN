---
description: 将 Win32 应用中的 web 内容托管到 Microsoft Edge Web 部件2控件中
title: 适用于 Win32 应用的 Microsoft Edge Web 视图2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: b1ec0c43b57fb107490ddb34b330bb6ec378ac41
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652905"
---
# <span data-ttu-id="7d535-104">Microsoft Edge WebView2 （开发人员预览版）</span><span class="sxs-lookup"><span data-stu-id="7d535-104">Microsoft Edge WebView2 (developer preview)</span></span>

<span data-ttu-id="7d535-105">使用 Microsoft Edge WebView2 控件，你可以使用[Microsoft edge （Chromium）](https://www.microsoftedgeinsider.com/)作为呈现引擎在你的应用程序中托管 web 内容。</span><span class="sxs-lookup"><span data-stu-id="7d535-105">The Microsoft Edge WebView2 control enables you to host web content in your application using [Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/) as the rendering engine.</span></span>

<span data-ttu-id="7d535-106">WebView2 控件目前处于开发人员预览版中，在该控件中，你可以将解决方案原型并与我们共享反馈，以便对未来的稳定 API 进行整形。</span><span class="sxs-lookup"><span data-stu-id="7d535-106">The WebView2 control is currently in developer preview, during which you can prototype your solutions and share feedback with us to shape the future stable API.</span></span> <span data-ttu-id="7d535-107">由于我们在预览期间演变 API，因此可能会发生一些重大更改，并且当发生这种情况时，你需要同时更新 WebView2 SDK 和 Microsoft Edge （Chromium）浏览器。</span><span class="sxs-lookup"><span data-stu-id="7d535-107">There will likely be some breaking changes as we evolve the API during preview, and when this happens, you will need to have both the WebView2 SDK and the Microsoft Edge (Chromium) browser updated.</span></span> <span data-ttu-id="7d535-108">在 SDK 的[发行说明](./releasenotes.md)中将注明重大更改。</span><span class="sxs-lookup"><span data-stu-id="7d535-108">Breaking changes will be noted in the [release notes](./releasenotes.md) of the SDK.</span></span> <span data-ttu-id="7d535-109">这将被锁定，WebView2 方法 beta 和稳定。</span><span class="sxs-lookup"><span data-stu-id="7d535-109">This will lock down as WebView2 approaches beta and stable.</span></span>

## <span data-ttu-id="7d535-110">支持的平台</span><span class="sxs-lookup"><span data-stu-id="7d535-110">Supported Platforms</span></span>

<span data-ttu-id="7d535-111">对于 Win32 C/c + + 和适用于 .NET Framework 4.6.2 或更高版本的 Windows 窗体和 WPF 的开发人员预览版，Windows 10、Windows 8.1、Windows 8、windows 7、2016 Windows server 2012/2012R2 和 Windows Server 2008 R2 上都提供了 .NET Core 3.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7d535-111">A developer preview is available for Win32 C/C++ and Windows Forms and WPF on .NET Framework 4.6.2 or later and .NET Core 3.0 or later on Windows 10, Windows 8.1, Windows 8, Windows 7, Windows Server 2016, Windows Server 2012/2012R2, and Windows Server 2008 R2.</span></span> <span data-ttu-id="7d535-112">WinUI 3.0 的 Alpha 版本可[在此处](https://docs.microsoft.com/uwp/toolkits/winui3/)找到。</span><span class="sxs-lookup"><span data-stu-id="7d535-112">An Alpha version for WinUI 3.0 is available [here](https://docs.microsoft.com/uwp/toolkits/winui3/).</span></span>

## <span data-ttu-id="7d535-113">入门</span><span class="sxs-lookup"><span data-stu-id="7d535-113">Getting Started</span></span>

<span data-ttu-id="7d535-114">若要使用 WebView2 控件生成和测试你的应用程序，你需要安装[Microsoft Edge （Chromium）](https://www.microsoftedgeinsider.com/download/)和[WebView2 SDK](https://aka.ms/webviewnuget) 。</span><span class="sxs-lookup"><span data-stu-id="7d535-114">To build and test your application using the WebView2 control, you need to have both [Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/download/) and the [WebView2 SDK](https://aka.ms/webviewnuget) installed.</span></span> <span data-ttu-id="7d535-115">选择以下选项之一开始使用！</span><span class="sxs-lookup"><span data-stu-id="7d535-115">Select one of the options below to get started!</span></span>

* [<span data-ttu-id="7d535-116">Win32 C/c + + 入门</span><span class="sxs-lookup"><span data-stu-id="7d535-116">Getting Started with Win32 C/C++</span></span>](./gettingstarted/win32.md)
* [<span data-ttu-id="7d535-117">WPF 入门</span><span class="sxs-lookup"><span data-stu-id="7d535-117">Getting Started with WPF</span></span>](./gettingstarted/wpf.md)
* [<span data-ttu-id="7d535-118">Windows 窗体入门</span><span class="sxs-lookup"><span data-stu-id="7d535-118">Getting Started with Windows Forms</span></span>](./gettingstarted/winforms.md)

<span data-ttu-id="7d535-119">请在我们的[WebView2 反馈](https://aka.ms/webviewfeedback)存储库中留下反馈。</span><span class="sxs-lookup"><span data-stu-id="7d535-119">Please leave us feedback in our [WebView2 Feedback](https://aka.ms/webviewfeedback) repo.</span></span>

## <span data-ttu-id="7d535-120">WebView2 示例</span><span class="sxs-lookup"><span data-stu-id="7d535-120">WebView2 Samples</span></span>

<span data-ttu-id="7d535-121">[WebView2 示例](https://github.com/MicrosoftEdge/WebView2Samples)存储库包含演示 WebView2 SDK 的所有功能及其 API 使用模式的示例。</span><span class="sxs-lookup"><span data-stu-id="7d535-121">The [WebView2 Samples](https://github.com/MicrosoftEdge/WebView2Samples) repository contains samples that demonstrate all of the WebView2 SDK's features and their API use patterns.</span></span> <span data-ttu-id="7d535-122">随着我们将更多功能添加到 WebView2 SDK，我们将定期更新我们的示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d535-122">As we add more features to the WebView2 SDK, we will regularly update our sample applications.</span></span>

## <span data-ttu-id="7d535-123">应用分发</span><span class="sxs-lookup"><span data-stu-id="7d535-123">App Distribution</span></span>

<span data-ttu-id="7d535-124">WebView2 控件利用 Microsoft Edge （Chromium）浏览器。</span><span class="sxs-lookup"><span data-stu-id="7d535-124">The WebView2 control utilizes the Microsoft Edge (Chromium) browser.</span></span> <span data-ttu-id="7d535-125">当分发你的应用时，请务必确保在应用程序将运行的所有用户计算机上安装了 Edge 浏览器。</span><span class="sxs-lookup"><span data-stu-id="7d535-125">When distributing your app it is important to ensure that the Edge browser is installed on all user machines where your application will run.</span></span> <span data-ttu-id="7d535-126">此外，你还应注意安装了哪个版本和信道，例如稳定、Beta、开发或未固定。</span><span class="sxs-lookup"><span data-stu-id="7d535-126">You should also be aware of which version and channel is installed, e.g. Stable, Beta, Dev, or Canary.</span></span> <span data-ttu-id="7d535-127">当安装在计算机上时，WebView2 控制器将利用最稳定的浏览器版本。</span><span class="sxs-lookup"><span data-stu-id="7d535-127">The WebView2 controller will utilize the most stable version of the browser when installed on a machine.</span></span>

### <span data-ttu-id="7d535-128">未来的计划更改</span><span class="sxs-lookup"><span data-stu-id="7d535-128">Future Planned Changes</span></span>

<span data-ttu-id="7d535-129">我们认识到，在应用程序运行的所有用户计算机上，Edge 浏览器可能不可用，或者可能很难控制边缘浏览器安装过程。</span><span class="sxs-lookup"><span data-stu-id="7d535-129">We recognize that the Edge browser may not be available on all user machines your application is intended to run, or that control of the Edge browser install process may be difficult.</span></span> <span data-ttu-id="7d535-130">若要确保你的应用程序在所有计算机上运行，而不依赖客户端 Microsoft Edge 浏览器的安装状态，我们将发布 Microsoft Edge WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="7d535-130">To ensure your application will run on all machines, independent of the install status of the client Microsoft Edge browser, we will release the Microsoft Edge WebView2 Runtime.</span></span> <span data-ttu-id="7d535-131">我们将在搜索已安装的浏览器的预发布版本之前，进一步更新 WebView2 以搜索运行时的稳定版本。</span><span class="sxs-lookup"><span data-stu-id="7d535-131">We will further update WebView2 to search for the stable version of the Runtime before searching for pre-release versions of the installed browser.</span></span>

<span data-ttu-id="7d535-132">我们还认识到，某些应用开发人员在受限制的环境中运行，因此希望支持两种分发选项：长绿和固定版本。</span><span class="sxs-lookup"><span data-stu-id="7d535-132">We also recognize that some app developers operate in constrained environments, and so intend to support two distribution options, evergreen and fixed version.</span></span>

<span data-ttu-id="7d535-133">对于大多数开发人员来说，"长绿" 是推荐的分发模型。</span><span class="sxs-lookup"><span data-stu-id="7d535-133">Evergreen is the recommended distribution model for most developers.</span></span> <span data-ttu-id="7d535-134">在此模式下，WebView2 运行时的更新将由 Microsoft 完全管理，而不需要你的应用程序即可自动保持最新。</span><span class="sxs-lookup"><span data-stu-id="7d535-134">In this mode updates to the WebView2 Runtime will be fully managed by Microsoft keeping you up to date automatically without additional effort from your application.</span></span> <span data-ttu-id="7d535-135">使用此自我更新模型，您可以确保应用充分利用托管 web 内容的最新功能和安全更新。</span><span class="sxs-lookup"><span data-stu-id="7d535-135">With this self-updating model you can be assured that your app is taking advantage of the latest features and security updates for hosted web content.</span></span>

<span data-ttu-id="7d535-136">对于受限环境，我们还将支持固定版本分发模型。</span><span class="sxs-lookup"><span data-stu-id="7d535-136">For constrained environments we will also support a fixed version distribution model.</span></span> <span data-ttu-id="7d535-137">在此模型中，你的应用程序将选择并打包特定的 WebView2 版本。</span><span class="sxs-lookup"><span data-stu-id="7d535-137">In this model your application will select and package a specific WebView2 version.</span></span> <span data-ttu-id="7d535-138">Web 视图版本的更新将由应用程序负责，并且将独立于任何托管的 Microsoft 更新机制。</span><span class="sxs-lookup"><span data-stu-id="7d535-138">Updates to the WebView version will be the responsibility of the application and will be independent of any managed Microsoft update mechanisms.</span></span> <span data-ttu-id="7d535-139">如果能够对浏览器版本进行绝对控制和更新应用程序的使用时间，则应选择此模型。</span><span class="sxs-lookup"><span data-stu-id="7d535-139">You should choose this model if it is crucial to be able to have absolute control over the browser version and update times your application is taking advantage of.</span></span>

## <span data-ttu-id="7d535-140">Microsoft Edge WebView2 运行时</span><span class="sxs-lookup"><span data-stu-id="7d535-140">Microsoft Edge WebView2 Runtime</span></span>

<span data-ttu-id="7d535-141">Microsoft Edge WebView2 运行时是经过优化以供 WebView2 应用程序使用的浏览器二进制文件的包装。</span><span class="sxs-lookup"><span data-stu-id="7d535-141">The Microsoft Edge WebView2 Runtime is a packaging of the browser binaries optimized for use by WebView2 applications.</span></span> <span data-ttu-id="7d535-142">它将独立运行或与客户端边缘浏览器安装并排运行。</span><span class="sxs-lookup"><span data-stu-id="7d535-142">It will function stand alone or side-by-side with a client Edge Browser install.</span></span> <span data-ttu-id="7d535-143">运行时的单个安装将支持任意数量的 WebView2 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d535-143">A single install of the run-time will support any number of WebView2 applications.</span></span> <span data-ttu-id="7d535-144">运行时的安装不会显示为浏览器安装到最终用户，即没有桌面快捷方式、开始菜单项或协议注册。</span><span class="sxs-lookup"><span data-stu-id="7d535-144">Install of the runtime will not appear as a browser install to end-user, i.e. no desktop shortcuts, start menu entry, or protocol registration.</span></span>

<span data-ttu-id="7d535-145">使用 WebView2 的应用程序必须确保已发生 Microsoft Edge WebView2 运行时的安装。</span><span class="sxs-lookup"><span data-stu-id="7d535-145">An application utilizing WebView2 must ensure the installation of the Microsoft Edge WebView2 Runtime has occurred.</span></span> <span data-ttu-id="7d535-146">在应用程序安装时，应检查当前安装状态，该状态可通过使用[GetAvailableCoreWebView2BrowserVersionString](./reference/win32/0-9-488/webview2-idl.md#getavailablecorewebview2browserversionstring)确定。</span><span class="sxs-lookup"><span data-stu-id="7d535-146">At application install time you should check the current install status, which can be determined by using [GetAvailableCoreWebView2BrowserVersionString](./reference/win32/0-9-488/webview2-idl.md#getavailablecorewebview2browserversionstring).</span></span> <span data-ttu-id="7d535-147">如果 WebView2 运行时不可用，则应将 Microsoft Edge WebView2 运行时安装程序链接到你的安装流。</span><span class="sxs-lookup"><span data-stu-id="7d535-147">If the WebView2 Runtime is not available, you should chain the Microsoft Edge WebView2 Runtime Installer to your install flow.</span></span>

## <span data-ttu-id="7d535-148">Microsoft Edge WebView2 SDK</span><span class="sxs-lookup"><span data-stu-id="7d535-148">Microsoft Edge WebView2 SDK</span></span>

<span data-ttu-id="7d535-149">若要利用你的应用中的 WebView2，你需要在应用程序中安装和引用[WEBVIEW2 SDK](https://aka.ms/webviewnuget) 。</span><span class="sxs-lookup"><span data-stu-id="7d535-149">To utilize WebView2 within your app you'll need to install and reference the [WebView2 SDK](https://aka.ms/webviewnuget) in your application.</span></span> <span data-ttu-id="7d535-150">我们的 NuGet 版本将同时包含发布版本和预发布版本。</span><span class="sxs-lookup"><span data-stu-id="7d535-150">Our NuGet releases will contain both a release and pre-release version.</span></span> <span data-ttu-id="7d535-151">发布版本包含我们当前打算发布到一般可用性的公共 Api。</span><span class="sxs-lookup"><span data-stu-id="7d535-151">The release version contains the public APIs we currently intend to release to general availability.</span></span>

<span data-ttu-id="7d535-152">预发布版本将包含其他实验性[api](./reference/win32/0-9-488-reference-webview2.md#experimental)。</span><span class="sxs-lookup"><span data-stu-id="7d535-152">The pre-release version will contain additional [experimental APIs](./reference/win32/0-9-488-reference-webview2.md#experimental).</span></span> <span data-ttu-id="7d535-153">这些是我们正在评估的 Api 和功能，并希望在将它们提升到发布版本之前提供[反馈](https://aka.ms/webviewfeedback)。</span><span class="sxs-lookup"><span data-stu-id="7d535-153">These are APIs and functionality we are evaluating and would like [feedback](https://aka.ms/webviewfeedback) on before promoting them to the release version.</span></span>

## <span data-ttu-id="7d535-154">针对即将推出的版本进行开发</span><span class="sxs-lookup"><span data-stu-id="7d535-154">Development against Upcoming Versions</span></span>

<span data-ttu-id="7d535-155">对于开发，你可能希望面向 Beta、开发人员或工作场所，以确保你的应用程序可用于即将推出的版本或利用即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="7d535-155">For development you may want to target Beta, Dev, or Canary to ensure your application will work with upcoming versions or to take advantage of upcoming features.</span></span> <span data-ttu-id="7d535-156">所有预发布的频道均由已安装的客户端 Microsoft Edge 浏览器提供。</span><span class="sxs-lookup"><span data-stu-id="7d535-156">All pre-released channels are provided by the installed client Microsoft Edge browser.</span></span> <span data-ttu-id="7d535-157">若要面向这些频道之一，请确保你的开发计算机上已安装的 Edge 浏览器是你想要的频道。</span><span class="sxs-lookup"><span data-stu-id="7d535-157">To target one of these channels ensure the installed Edge browser on your development machine is the channel you'd like.</span></span> <span data-ttu-id="7d535-158">开发人员可以使用注册表键或环境变量将 WebView2 从最稳定的发现最稳定的版本更改为最小的最稳定版本。</span><span class="sxs-lookup"><span data-stu-id="7d535-158">Developers can use a registry key or environment variable to change the WebView2 from the most stable version found to the least stable found.</span></span> <span data-ttu-id="7d535-159">查看[CreateCoreWebView2EnvironmentWithOptions](./reference/win32/0-9-488/webview2-idl.md#createcorewebview2environmentwithoptions)中的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="7d535-159">See more details in [CreateCoreWebView2EnvironmentWithOptions](./reference/win32/0-9-488/webview2-idl.md#createcorewebview2environmentwithoptions).</span></span>

## <span data-ttu-id="7d535-160">调试 WebView2</span><span class="sxs-lookup"><span data-stu-id="7d535-160">Debugging WebView2</span></span>

### <span data-ttu-id="7d535-161">DevTools</span><span class="sxs-lookup"><span data-stu-id="7d535-161">DevTools</span></span>

<span data-ttu-id="7d535-162">你可以使用[Microsoft Edge （Chromium）开发人员工具](https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium)来调试在 web 视图中显示的 web 内容，就像在浏览器中一样。</span><span class="sxs-lookup"><span data-stu-id="7d535-162">You can use [Microsoft Edge (Chromium) Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium) to debug web content displayed in WebView, just as you would in the browser.</span></span> <span data-ttu-id="7d535-163">在将焦点置于 "web 视图" 窗口时，按下 `F12` 或 `Ctrl`  +  `Shift`  +  `I` 右键单击 `Inspect` 以打开 "开发工具"。</span><span class="sxs-lookup"><span data-stu-id="7d535-163">While having focus on the WebView window, press `F12`, or press `Ctrl` + `Shift` + `I`, or Right Click + choose `Inspect` to open Developer Tools.</span></span>

:::image type="complex" source="./media/f12.png" alt-text="F12":::
   <span data-ttu-id="7d535-165">F12</span><span class="sxs-lookup"><span data-stu-id="7d535-165">F12</span></span>
:::image-end:::  

<!--![F12](./media/f12.png)  -->  

**<span data-ttu-id="7d535-166">注意当在 Visual Studio 中调试应用程序时，如果附加了本机调试器，则 `F12` 可能会触发本机调试器，而不是开发人员工具。</span><span class="sxs-lookup"><span data-stu-id="7d535-166">Note when debugging application in Visual Studio with the native debugger attached, `F12` may trigger the native debugger instead of Developer Tools.</span></span> <span data-ttu-id="7d535-167">使用 `Ctrl`  +  `Shift`  +  `I` 或右键单击 + `Inspect` 以避免潜在的热键冲突。</span><span class="sxs-lookup"><span data-stu-id="7d535-167">Use `Ctrl` + `Shift` + `I`, or Right Click + `Inspect` to avoid potential hotkey conflict.</span></span>**

### <span data-ttu-id="7d535-168">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7d535-168">Visual Studio</span></span>

<span data-ttu-id="7d535-169">你可以使用 Visual Studio 2019 （最低版本16.4 预览版2）中的脚本调试程序在 WebView2 中从 IDE 直接调试你的脚本。</span><span class="sxs-lookup"><span data-stu-id="7d535-169">You can use the script debugger in Visual Studio 2019 (minimum version 16.4 Preview 2) to debug your script within WebView2 right from the IDE.</span></span> <span data-ttu-id="7d535-170">请确保安装了**包含 c + +** 工作负荷的桌面开发中的**JavaScript 诊断**组件。</span><span class="sxs-lookup"><span data-stu-id="7d535-170">Make sure the **JavaScript diagnostics** component in **Desktop development with C++** workload is installed.</span></span>

:::image type="complex" source="./media/vs-js-diagnostics.jpg" alt-text="Visual Studio JavaScript 诊断":::
   <span data-ttu-id="7d535-172">Visual Studio JavaScript 诊断</span><span class="sxs-lookup"><span data-stu-id="7d535-172">Visual Studio JavaScript diagnostics</span></span>
:::image-end:::  

<!--![vs-js-diagnostics](./media/vs-js-diagnostics.jpg)  -->  

<span data-ttu-id="7d535-173">右键单击你的项目，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="7d535-173">Right click on your project and select **Properties**.</span></span> <span data-ttu-id="7d535-174">在 "**配置属性**  >  **调试**  >  **调试器类型**" 下，选择**JavaScript （WebView2）** 选项以启用 WebView2 脚本调试。</span><span class="sxs-lookup"><span data-stu-id="7d535-174">Under **Configuration Properties** > **Debugging** > **Debugger Type**,  choose the **JavaScript (WebView2)** option to enable WebView2 script debugging.</span></span> <span data-ttu-id="7d535-175">更多详细信息，请稍后再关注。</span><span class="sxs-lookup"><span data-stu-id="7d535-175">More details to follow soon.</span></span>

:::image type="complex" source="./media/vs-script-debugger.jpg" alt-text="Visual Studio 脚本调试程序":::
   <span data-ttu-id="7d535-177">Visual Studio 脚本调试程序</span><span class="sxs-lookup"><span data-stu-id="7d535-177">Visual Studio script debugger</span></span>
:::image-end:::  

<!--![vs-script-debugger](./media/vs-script-debugger.jpg)  -->  

### <span data-ttu-id="7d535-178">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7d535-178">Visual Studio Code</span></span>

<span data-ttu-id="7d535-179">你还可以使用 Visual Studio 代码在 WebView2 中从 IDE 调试你的脚本。</span><span class="sxs-lookup"><span data-stu-id="7d535-179">You can also use Visual Studio Code to debug your script within the WebView2 right from the IDE.</span></span> <span data-ttu-id="7d535-180">有关详细信息，请单击[此处](https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications)。</span><span class="sxs-lookup"><span data-stu-id="7d535-180">For more details click [here](https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications).</span></span>

## <span data-ttu-id="7d535-181">与 WebView2 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="7d535-181">Getting in touch with the WebView2 team</span></span>  

<span data-ttu-id="7d535-182">通过分享你的反馈帮助我们构建更丰富的 WebView2 体验！</span><span class="sxs-lookup"><span data-stu-id="7d535-182">Help us build a richer WebView2 experience by sharing your feedback!</span></span> <span data-ttu-id="7d535-183">请访问我们的[反馈](https://aka.ms/webviewfeedback)存储库以提交功能请求或 bug 报告。</span><span class="sxs-lookup"><span data-stu-id="7d535-183">Visit our [feedback repo](https://aka.ms/webviewfeedback) to submit feature requests or bug reports.</span></span>

<span data-ttu-id="7d535-184">这也是搜索已知问题的好地方。</span><span class="sxs-lookup"><span data-stu-id="7d535-184">It's also a good place to search for known issues.</span></span>
<span data-ttu-id="7d535-185">在开发人员预览版中，我们还将收集遥测数据以帮助我们构建更好的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="7d535-185">During developer preview, we will also be collecting telemetry data to help us build a better WebView.</span></span> <span data-ttu-id="7d535-186">用户可以通过导航到浏览器中的 edge://settings/privacy 并关闭浏览器数据收集来关闭 Web 视图数据收集。</span><span class="sxs-lookup"><span data-stu-id="7d535-186">Users can turn off WebView data collection by navigating to edge://settings/privacy in the browser and turning off browser data collection.</span></span>
