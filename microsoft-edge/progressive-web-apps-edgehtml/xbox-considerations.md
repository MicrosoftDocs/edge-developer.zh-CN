---
description: 确保 PWA 为 Xbox 提供了出色的体验
title: 适用于 Xbox One 的渐进 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 web 应用、PWA、Edge、Windows、UWP、Xbox、Xbox One、TVJS
ms.openlocfilehash: dfa2b2d252bb788c0010017de57ab147d407c5f7
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882847"
---
# <span data-ttu-id="62249-104">适用于 Xbox One 的渐进 Web 应用</span><span class="sxs-lookup"><span data-stu-id="62249-104">Progressive Web Apps for Xbox One</span></span>  

<span data-ttu-id="62249-105">你可以扩展 web 应用程序，并通过 Microsoft Store 将其用作 Xbox One 应用，同时仍继续使用你的现有框架、CDN 和服务器后端。</span><span class="sxs-lookup"><span data-stu-id="62249-105">You can extend a web application and make it available as an Xbox One app via Microsoft Store while still continuing to use your existing frameworks, CDN and server backend.</span></span>  <span data-ttu-id="62249-106">与所有通用 Windows 平台（UWP）应用一样，在 Xbox One 上运行的渐进式 Web 应用（PWAs）也可以调用本机 Windows 10 Api。</span><span class="sxs-lookup"><span data-stu-id="62249-106">And like all Universal Windows Platform (UWP) apps, Progressive Web Apps (PWAs) running on Xbox One can also call native Windows 10 APIs.</span></span>  <span data-ttu-id="62249-107">已有许多 PWAs 可用于 Xbox One，尤其是在[媒体播放应用](#media-pwas-on-xbox)的类别中。</span><span class="sxs-lookup"><span data-stu-id="62249-107">There are already a number of PWAs available for the Xbox One, particularly in the category of [media playback apps](#media-pwas-on-xbox).</span></span>  

<span data-ttu-id="62249-108">大多数情况下，你可以按照[对 Windows 的相同方式](./windows-features.md)将 pwa 打包为 Xbox one，方法是使用[PWA 生成器](https://www.pwabuilder.com/)工具或[VISUAL Studio](https://visualstudio.microsoft.com/vs/) IDE 生成将 pwa 作为 UWP 应用运行所需的*package.appxmanifest*文件。</span><span class="sxs-lookup"><span data-stu-id="62249-108">For the most part, you can package your PWA for Xbox One in the [same way you would for Windows](./windows-features.md), using the [PWA Builder](https://www.pwabuilder.com/) tools or [Visual Studio](https://visualstudio.microsoft.com/vs/) IDE to generate the *appxmanifest* file required to run your PWA as a UWP app.</span></span> <span data-ttu-id="62249-109">但是，本指南将指导你完成几项关键的差异。</span><span class="sxs-lookup"><span data-stu-id="62249-109">However, there are several key differences this guide will walk you through.</span></span>

## <span data-ttu-id="62249-110">在 Xbox 上部署和测试 PWAs</span><span class="sxs-lookup"><span data-stu-id="62249-110">Deploying and testing PWAs on Xbox</span></span>

<span data-ttu-id="62249-111">若要开始使用，请按照以下[步骤激活*Xbox One 开发人员模式*](/windows/uwp/xbox-apps/devkit-activation) 。</span><span class="sxs-lookup"><span data-stu-id="62249-111">To get started, follow these [steps to activate *Xbox One Developer Mode*](/windows/uwp/xbox-apps/devkit-activation) .</span></span> <span data-ttu-id="62249-112">启用开发人员模式后，[设置*Xbox 的 Device Portal* ](/windows/uwp/debug-test-perf/device-portal-xbox)以从开发人员环境中的浏览器获取对 xbox 的远程访问。</span><span class="sxs-lookup"><span data-stu-id="62249-112">With Developer Mode activated, [set up *Device Portal for Xbox*](/windows/uwp/debug-test-perf/device-portal-xbox) to gain remote access to your Xbox from the browser in your dev environment.</span></span>

<span data-ttu-id="62249-113">现在，你可以使用*PWA 生成器*或*Visual Studio*部署你的应用以进行测试。</span><span class="sxs-lookup"><span data-stu-id="62249-113">Now you're ready to deploy your app for testing using either *PWA Builder* or *Visual Studio*.</span></span>

### <span data-ttu-id="62249-114">选项1： PWA 生成器</span><span class="sxs-lookup"><span data-stu-id="62249-114">Option 1: PWA Builder</span></span>

<span data-ttu-id="62249-115">[PWA 生成器](https://www.pwabuilder.com/)是可以从节点程序包管理器（NPM）安装的 Node.js 应用。</span><span class="sxs-lookup"><span data-stu-id="62249-115">[PWA Builder](https://www.pwabuilder.com/) is a Node.js app you can install from Node Package Manager (NPM).</span></span> <span data-ttu-id="62249-116">它使用您的网站的元数据在 Android、iOS 和 Windows 之间生成本机托管应用。</span><span class="sxs-lookup"><span data-stu-id="62249-116">It uses the metadata of your website to generate native hosted apps across Android, iOS and Windows.</span></span> <span data-ttu-id="62249-117">如果您的网站已有[web 应用清单](https://developer.mozilla.org/docs/Web/Manifest)，PWA 生成器将使用它来生成特定于平台的安装程序包。</span><span class="sxs-lookup"><span data-stu-id="62249-117">If your site already has a [web app manifest](https://developer.mozilla.org/docs/Web/Manifest), PWA Builder will use it to generate platform-specific installation packages.</span></span> <span data-ttu-id="62249-118">否则，PWA 生成器将基于你的网站的特征，*在文件上*生成基本manifest.js。</span><span class="sxs-lookup"><span data-stu-id="62249-118">Otherwise, PWA Builder will generate a basic *manifest.json* file based on the characteristics of your site.</span></span>

#### <span data-ttu-id="62249-119">要求</span><span class="sxs-lookup"><span data-stu-id="62249-119">Requirements</span></span>
 - <span data-ttu-id="62249-120">[Node.js](https://nodejs.org/en/)，其中包括 NPM。</span><span class="sxs-lookup"><span data-stu-id="62249-120">[Node.js](https://nodejs.org/en/), which includes NPM.</span></span>

#### <span data-ttu-id="62249-121">安装</span><span class="sxs-lookup"><span data-stu-id="62249-121">Setup</span></span>

1. <span data-ttu-id="62249-122">打开节点命令提示符以安装 PWA 生成器：</span><span class="sxs-lookup"><span data-stu-id="62249-122">Open a Node command prompt to install PWA Builder:</span></span>

    ```
    npm install pwabuilder --global
    ```

2. <span data-ttu-id="62249-123">在网站 URL 上运行 PWA 生成器：</span><span class="sxs-lookup"><span data-stu-id="62249-123">Run PWA Builder on your website URL:</span></span>

    ```
    pwabuilder https://example.com/ -windows10
    ```

    <span data-ttu-id="62249-124">*-Windows10*标志将包生成限制为 Windows 10 （UWP）。</span><span class="sxs-lookup"><span data-stu-id="62249-124">The *-windows10* flag limits package generation to Windows 10 (UWP).</span></span> <span data-ttu-id="62249-125">你可以省略它以跨所有受支持的平台（包括 iOS 和 Android）生成程序包。</span><span class="sxs-lookup"><span data-stu-id="62249-125">You can omit it to generate packages across all supported platforms, including iOS and Android.</span></span> <span data-ttu-id="62249-126">有关详细信息，请参阅[PWA 生成器文档](https://docs.pwabuilder.com/)。</span><span class="sxs-lookup"><span data-stu-id="62249-126">See the [PWA Builder docs](https://docs.pwabuilder.com/) for more info.</span></span>

3. <span data-ttu-id="62249-127">从[适用于 Xbox 的 Device Portal](/windows/uwp/debug-test-perf/device-portal-xbox)，转到 "**开始**  >  使用**我的游戏" & 应用**  >  "**添加**"，选择*上载松散文件*的选项，然后选择 "PWA" 生成器在当前目录中生成的 Windows 10 应用部件清单文件夹。</span><span class="sxs-lookup"><span data-stu-id="62249-127">From the [Device Portal for Xbox](/windows/uwp/debug-test-perf/device-portal-xbox), go to **Home** > **My games & apps** > **Add**, choose the option to *upload loose files*, and select the Windows 10 app manifest folder generated by PWA Builder in the current directory.</span></span>

4. <span data-ttu-id="62249-128">逐步完成向导以完成安装过程。</span><span class="sxs-lookup"><span data-stu-id="62249-128">Step through the wizard to complete the installation process.</span></span> <span data-ttu-id="62249-129">安装后。</span><span class="sxs-lookup"><span data-stu-id="62249-129">Once installed.</span></span> <span data-ttu-id="62249-130">你将能够从 Xbox One 仪表板中查看和启动你的 PWA。</span><span class="sxs-lookup"><span data-stu-id="62249-130">you'll be able to see and launch your PWA from the Xbox One dashboard.</span></span>


### <span data-ttu-id="62249-131">选项2： Visual Studio</span><span class="sxs-lookup"><span data-stu-id="62249-131">Option 2: Visual Studio</span></span>

<span data-ttu-id="62249-132">免费的功能齐全的[Visual Studio 社区 2017](https://visualstudio.microsoft.com/vs/community/)包括 Windows 10 开发人员工具、通用应用模板、代码编辑器、功能强大的调试器、Windows Mobile 模拟器、丰富的语言支持等-一切都准备好在生产中使用。</span><span class="sxs-lookup"><span data-stu-id="62249-132">The free, full-featured [Visual Studio Community 2017](https://visualstudio.microsoft.com/vs/community/) includes Windows 10 developer tools, universal app templates, a code editor, a powerful debugger, Windows Mobile emulators, rich language support and much more—all ready to use in production.</span></span> <span data-ttu-id="62249-133">[*专业*版和*企业*](https://visualstudio.microsoft.com/vs/compare/)版提供的功能更多功能。</span><span class="sxs-lookup"><span data-stu-id="62249-133">The [*Professional* and *Enterprise*](https://visualstudio.microsoft.com/vs/compare/) versions provide even more features.</span></span>

#### <span data-ttu-id="62249-134">要求</span><span class="sxs-lookup"><span data-stu-id="62249-134">Requirements</span></span>

 - <span data-ttu-id="62249-135">[**Visual Studio 2017**](https://visualstudio.microsoft.com/vs/
)：任何版本，包括免费*社区*版本。</span><span class="sxs-lookup"><span data-stu-id="62249-135">[**Visual Studio 2017**](https://visualstudio.microsoft.com/vs/
): any version, including the free *Community* edition.</span></span>
 - <span data-ttu-id="62249-136">[**Windows 10 SDK**](/windows/uwp/xbox-apps/development-environment-setup)：在*Visual Studio 2017 安装程序*中选择此可选组件。</span><span class="sxs-lookup"><span data-stu-id="62249-136">[**Windows 10 SDK**](/windows/uwp/xbox-apps/development-environment-setup): Select this optional component in the *Visual Studio 2017 Installer*.</span></span>

#### <span data-ttu-id="62249-137">安装</span><span class="sxs-lookup"><span data-stu-id="62249-137">Setup</span></span>

1. <span data-ttu-id="62249-138">按照以下步骤[将 PWA 设置和运行为通用 Windows 应用](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#set-up-and-run-your-universal-windows-app)。</span><span class="sxs-lookup"><span data-stu-id="62249-138">Follow the steps to [set up and run your PWA as a Universal Windows app](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#set-up-and-run-your-universal-windows-app).</span></span> <span data-ttu-id="62249-139">使用此功能，你将拥有能够访问通用 Windows Api 的功能齐全的 Windows 10 应用。</span><span class="sxs-lookup"><span data-stu-id="62249-139">With this, you'll have a fully functioning Windows 10 app capable of accessing Universal Windows APIs.</span></span>

2. <span data-ttu-id="62249-140">现在，你可以使用[Visual Studio 远程调试器](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017
)在 Xbox one （与任何其他 Windows 10 远程设备）上部署和调试你的 PWA （作为 UWP 应用）。</span><span class="sxs-lookup"><span data-stu-id="62249-140">You can now deploy and debug your PWA (as a UWP app) on the Xbox One (as with any other Windows 10 remote device) using the [Visual Studio remote debugger](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017
).</span></span> <span data-ttu-id="62249-141">或者，你可以使用以下步骤使用[Device Portal For Xbox](/windows/uwp/debug-test-perf/device-portal-xbox)安装 PWA。</span><span class="sxs-lookup"><span data-stu-id="62249-141">Alternately, you can install your PWA using the [Device Portal for Xbox](/windows/uwp/debug-test-perf/device-portal-xbox) using the following steps.</span></span>

3. <span data-ttu-id="62249-142">从 Xbox 的 Device Portal 中，转到 "家庭 > 我的游戏" & 应用 > "添加"，选择上载*应用包和依赖关系*的选项。</span><span class="sxs-lookup"><span data-stu-id="62249-142">From the Device Portal for Xbox, go to Home > My games & apps > Add, choose the option to upload *App Package and Dependencies*.</span></span>

4. <span data-ttu-id="62249-143">导航到步骤1中为你的应用生成的程序包文件夹，并选择要上载的 *.appx*文件。</span><span class="sxs-lookup"><span data-stu-id="62249-143">Navigate to the package folder you generated for your app in Step 1 and select the *.appx* file for upload.</span></span> <span data-ttu-id="62249-144">[ *.Appx*文件](/windows/uwp/packaging/packaging-uwp-apps)是一个 UWP 应用包文件，可在任何设备上旁加载用于测试目的。</span><span class="sxs-lookup"><span data-stu-id="62249-144">The [*.appx* file](/windows/uwp/packaging/packaging-uwp-apps) is a UWP app package file that can be sideloaded on any device for testing purposes.</span></span>

5. <span data-ttu-id="62249-145">接下来，点击 "**依赖项**" 按钮，然后选择应用的 "*依赖关系*" 子文件夹并上载每个子文件夹。</span><span class="sxs-lookup"><span data-stu-id="62249-145">Next tap the **Dependencies** button and select the *dependencies* sub-folder for your app and upload each one.</span></span> <span data-ttu-id="62249-146">只有从适用于 Xbox 的 Device Portal 部署应用时，才需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="62249-146">This step is only required for deploying apps from the Device Portal for Xbox.</span></span> <span data-ttu-id="62249-147">当从 Microsoft Store 发送远程调试且最终用户的计算机从 Microsoft Store 发送时，Visual Studio 将提供依赖关系。</span><span class="sxs-lookup"><span data-stu-id="62249-147">Visual Studio delivers dependencies when remote debugging and the end user's machine will already have these installed when delivered from the Microsoft Store.</span></span>

6. <span data-ttu-id="62249-148">在应用包和上载的依赖项的情况下，单击 "*部署*" 部分下的 "**转到**" 按钮，将安装应用。</span><span class="sxs-lookup"><span data-stu-id="62249-148">With the app package and the dependencies uploaded, click the **Go** button under the *Deploy* section and the app will be installed.</span></span> <span data-ttu-id="62249-149">你已准备好从 Xbox 启动你的应用！</span><span class="sxs-lookup"><span data-stu-id="62249-149">You're ready to launch your app from Xbox!</span></span>

## <span data-ttu-id="62249-150">Xbox 上 PWAs 的 UX 注意事项</span><span class="sxs-lookup"><span data-stu-id="62249-150">UX considerations for PWAs on Xbox</span></span>

### <span data-ttu-id="62249-151">"10 英尺体验" 的设计</span><span class="sxs-lookup"><span data-stu-id="62249-151">Design for the "10-Foot Experience"</span></span>

<span data-ttu-id="62249-152">Xbox One 被视为 "10 英尺体验"，这意味着你的用户可能会在离屏幕最少10英尺的位置。</span><span class="sxs-lookup"><span data-stu-id="62249-152">Xbox One is considered a "10-foot experience", meaning that your users will likely be sitting a minimum of 10 feet away from the screen.</span></span> <span data-ttu-id="62249-153">因此，请考虑你的应用在该距离上的使用方式，而不是使用鼠标和键盘的传统桌面 web 浏览器体验。</span><span class="sxs-lookup"><span data-stu-id="62249-153">As such, consider how your app might be used at that distance as opposed to the traditional desktop web browser experience with a mouse and keyboard.</span></span> <span data-ttu-id="62249-154">有关设计和 UX 指南，请查看[适用于 Xbox 和电视的设计](/windows/uwp/design/devices/designing-for-tv)。</span><span class="sxs-lookup"><span data-stu-id="62249-154">For design and UX guidance, check out [Designing for Xbox and TV](/windows/uwp/design/devices/designing-for-tv).</span></span>

### <span data-ttu-id="62249-155">了解 "电视 SafeZone"</span><span class="sxs-lookup"><span data-stu-id="62249-155">Understand the "TV SafeZone"</span></span>

<span data-ttu-id="62249-156">电视制造商将在可剪裁你的应用的内容周围应用["安全区域"](/windows/uwp/design/devices/designing-for-tv#tv-safe-area) 。</span><span class="sxs-lookup"><span data-stu-id="62249-156">Television manufacturers will apply a ["safe-zone"](/windows/uwp/design/devices/designing-for-tv#tv-safe-area) around the content that can clip your app.</span></span> <span data-ttu-id="62249-157">默认情况下，我们会在你的应用周围应用安全边框以考虑此情况，但你可以通过调用 [`setDesiredBoundsMode`](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) 和指定以下内容来确保你的应用获得完整的屏幕大小 [`useCoreWindow`](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode) ：</span><span class="sxs-lookup"><span data-stu-id="62249-157">By default, we apply a safe border around your app to account for this, however you can ensure that your app takes the full screen size by calling [`setDesiredBoundsMode`](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) and specifying [`useCoreWindow`](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode):</span></span>

```JavaScript
var applicationView = Windows.UI.ViewManagement.ApplicationView.getForCurrentView();
applicationView.setDesiredBoundsMode(Windows.UI.ViewManagement.ApplicationViewBoundsMode.useCoreWindow);
```

<span data-ttu-id="62249-158">有关详细信息，请查看 [`Windows.UI.ViewManagement`](/uwp/api/windows.ui.viewmanagement) 命名空间文档。</span><span class="sxs-lookup"><span data-stu-id="62249-158">For more, check out the [`Windows.UI.ViewManagement`](/uwp/api/windows.ui.viewmanagement) namespace documentation.</span></span>

### <span data-ttu-id="62249-159">管理 XY 焦点和导航</span><span class="sxs-lookup"><span data-stu-id="62249-159">Manage XY focus and navigation</span></span>

<span data-ttu-id="62249-160">适用于 Xbox 的用户输入方法是游戏板或远程控制，它使用[XY 导航系统](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction)，允许用户通过向上、向下、向左和向右移动焦点来将焦点从控件移动到控件。</span><span class="sxs-lookup"><span data-stu-id="62249-160">User input methods for Xbox are gamepad or remote control, which use a [XY navigation system](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction), allowing the user to shift the focus from control to control by moving up, down, left, and right.</span></span>

<span data-ttu-id="62249-161">因此，你将需要确保你的应用可以正常使用 XY 导航。</span><span class="sxs-lookup"><span data-stu-id="62249-161">As such, you'll want to make sure your app works well with XY navigation.</span></span> <span data-ttu-id="62249-162">此外，请确保禁用默认情况下适用于 UWP 应用（并且可能不适用于你的应用的 Xbox 体验）的 " [*鼠标模式*](/windows/uwp/xbox-apps/how-to-disable-mouse-mode)"。</span><span class="sxs-lookup"><span data-stu-id="62249-162">Also, be sure to [disable *mouse mode*](/windows/uwp/xbox-apps/how-to-disable-mouse-mode), which is on by default for UWP apps (and probably not applicable to your app's Xbox experience).</span></span>

<span data-ttu-id="62249-163">以下代码关闭 `mouse` 模式并启用游戏板输入以生成 DOM 键盘事件：</span><span class="sxs-lookup"><span data-stu-id="62249-163">The following code turns off `mouse` mode and enables gamepad input to generate DOM keyboard events:</span></span>

```JavaScript
navigator.gamepadInputEmulation = "keyboard";
```

<span data-ttu-id="62249-164">或者，你也可以指定 `gamepad` 同时关闭鼠标，不生成 DOM 键盘事件，并允许你使用标准的 web 和/或 WinRT 游戏板 api。</span><span class="sxs-lookup"><span data-stu-id="62249-164">Alternately, you can specify `gamepad`, which also turns off mouse, does not generate DOM keyboard events, and allows you to use the standard web and/or WinRT gamepad APIs.</span></span>

<span data-ttu-id="62249-165">若要启用方向导航，请查看[TVJS 库](#tvjs)，下面将进行讨论。</span><span class="sxs-lookup"><span data-stu-id="62249-165">To enable directional navigation, check out the [TVJS library](#tvjs), discussed next.</span></span>

### <span data-ttu-id="62249-166">TVJS</span><span class="sxs-lookup"><span data-stu-id="62249-166">TVJS</span></span>

<span data-ttu-id="62249-167">[TVJS 是帮助程序库的集合](https://github.com/Microsoft/TVHelpers)，便于为电视构建 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="62249-167">[TVJS is a collection of helper libraries](https://github.com/Microsoft/TVHelpers) that make it easier to build web applications for the TV.</span></span> <span data-ttu-id="62249-168">如果你要生成的托管 web 应用还将在 Xbox 上运行，TVJS 可以帮助添加对*方向导航*的支持，并提供多个控件，使你可以更轻松地与电视上的内容交互。</span><span class="sxs-lookup"><span data-stu-id="62249-168">If you are building a hosted web app that will also run on the Xbox, TVJS can help add support for *directional navigation*, as well as provide several controls that make it easier to interact with content on the TV.</span></span>

<span data-ttu-id="62249-169">[方向导航](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation)是一种 TVJS 功能，可在电视应用的页面内提供自动二维导航。</span><span class="sxs-lookup"><span data-stu-id="62249-169">[Directional navigation](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) is a TVJS feature that provides automatic two-dimensional navigation within the pages of your TV app.</span></span> <span data-ttu-id="62249-170">利用它，无需在应用的页面内捕获和处理导航，或者为 UI 中的每个元素显式指定所有有效的焦点目标。</span><span class="sxs-lookup"><span data-stu-id="62249-170">With it, there's no need to trap and handle navigation within the pages of your app, or to explicitly specify all the valid focus targets for each element in the UI.</span></span> <span data-ttu-id="62249-171">自动的焦点处理使用户能够以直观、稳健的方式导航。</span><span class="sxs-lookup"><span data-stu-id="62249-171">Automatic focus handling enables users can navigate around in an intuitive and robust way.</span></span>

<span data-ttu-id="62249-172">当用户使用控制器方向按钮导航应用 UI 时，自动焦点算法将查看潜在的焦点目标集，确定要移动到的下一个元素，然后自动将焦点设置到该元素。</span><span class="sxs-lookup"><span data-stu-id="62249-172">As your user navigates the app UI with the controller direction buttons, the automatic focus algorithm looks at the set of potential focus targets, determines the next element to move to and then automatically sets focus to that element.</span></span> <span data-ttu-id="62249-173">为了确定下一个元素，该算法将方向输入、过去的焦点历史记录和页面上的 UI 元素的物理布局结合在一起。</span><span class="sxs-lookup"><span data-stu-id="62249-173">To determine the next element, the algorithm combines directional input, past focus history, and the physical layout of UI elements on the page.</span></span>

<span data-ttu-id="62249-174">若要启用方向导航，请包含以下脚本引用：</span><span class="sxs-lookup"><span data-stu-id="62249-174">To enable directional navigation, include the following script reference:</span></span>

```HTML
<script src="directionalnavigation-1.0.0.0.js"></script>
```

<span data-ttu-id="62249-175">默认情况下，只有、、、 `<a>` `<button>` `<input>` `<select>` 和 `<textarea>` 元素可获得焦点。</span><span class="sxs-lookup"><span data-stu-id="62249-175">By default, only `<a>`, `<button>`, `<input>`, `<select>`, and `<textarea>` elements are focusable.</span></span> <span data-ttu-id="62249-176">若要对其他元素启用焦点，请为它们分配一个有效的[tabindex](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex)。</span><span class="sxs-lookup"><span data-stu-id="62249-176">To enable focus on other elements, assign them a valid [tabindex](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex).</span></span>

```HTML
<div tabindex="0″>This div is eligible for focus</div>
```

查看[DirectionalNavigation](https://github.com/Microsoft/TVHelpers/wiki/DirectionalNavigation)文档，了解如何更改根元素、设置初始焦点、替代下一个焦点、优化控件以获得焦点、自定义输入。 <span data-ttu-id="62249-178">还有许多其他有用的示例。</span><span class="sxs-lookup"><span data-stu-id="62249-178">There's also a number of other useful samples.</span></span>

## <span data-ttu-id="62249-179">Xbox 上的媒体 PWAs</span><span class="sxs-lookup"><span data-stu-id="62249-179">Media PWAs on Xbox</span></span>

<span data-ttu-id="62249-180">如果你要为 Xbox One 构建媒体播放 PWA，请注意以下注意事项。</span><span class="sxs-lookup"><span data-stu-id="62249-180">If you're building a media playback PWA for Xbox One, be aware of the following considerations.</span></span>

### <span data-ttu-id="62249-181">浏览器中的加密媒体扩展（EME）</span><span class="sxs-lookup"><span data-stu-id="62249-181">Encrypted Media Extensions (EME) in the browser</span></span>

<span data-ttu-id="62249-182">Xbox One 上的 Microsoft Edge 浏览器不支持[加密媒体扩展](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)（EME）。</span><span class="sxs-lookup"><span data-stu-id="62249-182">The Microsoft Edge browser on Xbox One does not support [Encrypted Media Extensions](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API) (EME).</span></span> <span data-ttu-id="62249-183">如果你的媒体 PWA 将其用于数字权限管理（DRM），你将无法从 Xbox 上的浏览器运行它。</span><span class="sxs-lookup"><span data-stu-id="62249-183">If your media PWA uses it for digital rights management (DRM), you won't be able to run it from the browser on your Xbox.</span></span> <span data-ttu-id="62249-184">相反，[使用 PWABuilder 或 Visual Studio 将其作为 Xbox one 应用](#deploying-and-testing-pwas-on-xbox)进行原型，如下所述。</span><span class="sxs-lookup"><span data-stu-id="62249-184">Instead, prototype and test it as a [Xbox One app using PWABuilder or Visual Studio](#deploying-and-testing-pwas-on-xbox), as described above.</span></span> <span data-ttu-id="62249-185">您也可以在 Windows 上的 Microsoft Edge 浏览器上运行它，其中 EME 完全受支持。</span><span class="sxs-lookup"><span data-stu-id="62249-185">You can also run it on the Microsoft Edge browser on Windows, where EME is fully supported.</span></span>

### <span data-ttu-id="62249-186">与系统媒体传输控件集成</span><span class="sxs-lookup"><span data-stu-id="62249-186">Integrating with System Media Transport Controls</span></span>

<span data-ttu-id="62249-187">如果你的应用是媒体应用，你的应用必须通过屏幕按钮、 [Cortana 语音命令](https://support.xbox.com/xbox-one/console/cortana-voice-commands)、导航窗格中的[系统媒体传输控件](/windows/uwp/audio-video-camera/system-media-transport-controls)或其他设备上的[xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
)和[xbox one SmartGlass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2)应用来响应由用户发起的媒体控件。</span><span class="sxs-lookup"><span data-stu-id="62249-187">If your app is a media app, it is important that your app responds to the media controls initiated by the user via on-screen buttons, [Cortana voice commands](https://support.xbox.com/xbox-one/console/cortana-voice-commands), the [System Media Transport Controls](/windows/uwp/audio-video-camera/system-media-transport-controls) in the nav pane, or the [Xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
) and [Xbox One SmartGlass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2) apps on other devices.</span></span> <span data-ttu-id="62249-188">查看[TVJS 库](#tvjs)中的[MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview)控件，该控件自动与这些控件集成。</span><span class="sxs-lookup"><span data-stu-id="62249-188">Take a look at the [MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview) control from the [TVJS library](#tvjs), which automatically integrates with these controls.</span></span> <span data-ttu-id="62249-189">或者，您也可以手动[与系统媒体传输控件集成](https://msdn.microsoft.com/windows/uwp/audio-video-camera/system-media-transport-controls)。</span><span class="sxs-lookup"><span data-stu-id="62249-189">Alternately, you can manually [integrate with the System Media Transport Controls](https://msdn.microsoft.com/windows/uwp/audio-video-camera/system-media-transport-controls).</span></span>

### <span data-ttu-id="62249-190">PlayReady 内容加密</span><span class="sxs-lookup"><span data-stu-id="62249-190">PlayReady content encryption</span></span>

<span data-ttu-id="62249-191">在此编写时， [ `cbcs` 编码支持仅限于](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme)XBox one 的 PlayReady 客户端（版本1709或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="62249-191">At the time of this writing, [`cbcs` encoding support is limited](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme) to the PlayReady client for XBox One (version 1709 or higher).</span></span> <span data-ttu-id="62249-192">如果你的 PWA 媒体仅支持*cbcs*加密，请注意你的应用的功能可能会在 Windows 上受到限制（或完全不可用）。</span><span class="sxs-lookup"><span data-stu-id="62249-192">If the media for your PWA only supports *cbcs* encryption, be aware that your app's functionality will be likely be limited (or completely unavailable) on Windows.</span></span>



## <span data-ttu-id="62249-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62249-193">See also</span></span>
<span data-ttu-id="62249-194">[南凸缘视频](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video)：使用 React.js 构建的和托管在 web 服务器上的 Xbox 视频应用示例。</span><span class="sxs-lookup"><span data-stu-id="62249-194">[South Ridge Video](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video): A sample video app for Xbox built with React.js and hosted on a web server.</span></span>

<span data-ttu-id="62249-195">[针对 xbox 和电视进行设计](/windows/uwp/design/devices/designing-for-tv)：设计你的通用 Windows 平台（UWP）应用，以便它在 Xbox One 和电视屏幕上看起来不错且功能良好。</span><span class="sxs-lookup"><span data-stu-id="62249-195">[Designing for Xbox and TV](/windows/uwp/design/devices/designing-for-tv): Design your Universal Windows Platform (UWP) app so that it looks good and functions well on Xbox One and television screens.</span></span>

<span data-ttu-id="62249-196">[Xbox 最佳做法](/windows/uwp/xbox-apps/tailoring-for-xbox)：按照这些最佳做法为 Xbox one 定制你的应用。</span><span class="sxs-lookup"><span data-stu-id="62249-196">[Xbox best practices](/windows/uwp/xbox-apps/tailoring-for-xbox): Follow these best practices to tailor your app for Xbox One.</span></span>

<span data-ttu-id="62249-197">[Microsoft store 中的 PWAs](/microsoft-edge/progressive-web-apps-edgehtml/microsoft-store)：下面介绍了如何将 PWA 提交到 microsoft store。</span><span class="sxs-lookup"><span data-stu-id="62249-197">[PWAs in the Microsoft Store](/microsoft-edge/progressive-web-apps-edgehtml/microsoft-store): Here's how (and why!) to Submit your PWA to the Microsoft Store.</span></span>

<span data-ttu-id="62249-198">[Xbox one 上的 uwp](/windows/uwp/xbox-apps/)：适用于 xbox ONE 的 uwp 应用开发的完整指南。</span><span class="sxs-lookup"><span data-stu-id="62249-198">[UWP on Xbox One](/windows/uwp/xbox-apps/): A complete guide to UWP app development for Xbox One.</span></span>
