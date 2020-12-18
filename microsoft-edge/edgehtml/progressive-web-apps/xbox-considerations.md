---
description: 确保 PWA 为 Xbox 提供出色的体验
title: 适用于 Xbox One 的渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 Web 应用， PWA， Edge， Windows， UWP， Xbox， Xbox One， TVJS
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f1c46fe49f335373323de106b1b2a84418b97577
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232748"
---
# <span data-ttu-id="443c4-104">适用于 Xbox One 的渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="443c4-104">Progressive Web Apps for Xbox One</span></span>  

<span data-ttu-id="443c4-105">你可以扩展 Web 应用程序，并可通过 Microsoft Store 将其作为 Xbox One 应用提供，同时仍继续使用现有框架、CDN 和服务器后端。</span><span class="sxs-lookup"><span data-stu-id="443c4-105">You can extend a web application and make it available as an Xbox One app via Microsoft Store while still continuing to use your existing frameworks, CDN and server backend.</span></span>  <span data-ttu-id="443c4-106">就像所有通用 Windows 平台 (UWP) 应用一样，在 Xbox One 上运行的渐进式 Web () PWA 也可以调用本机 Windows 10 API。</span><span class="sxs-lookup"><span data-stu-id="443c4-106">And like all Universal Windows Platform (UWP) apps, Progressive Web Apps (PWAs) running on Xbox One can also call native Windows 10 APIs.</span></span>  <span data-ttu-id="443c4-107">已有许多适用于 Xbox One 的 PWA，尤其是在媒体播放 [应用类别中](#media-pwas-on-xbox)。</span><span class="sxs-lookup"><span data-stu-id="443c4-107">There are already a number of PWAs available for the Xbox One, particularly in the category of [media playback apps](#media-pwas-on-xbox).</span></span>  

<span data-ttu-id="443c4-108">大多数情况下，你可以像打包 [Windows](./windows-features.md)一样打包适用于 Xbox One 的 [PWA，使用 PWA](https://www.pwabuilder.com/) 生成器工具或 [Visual Studio](https://visualstudio.microsoft.com/vs/) IDE 生成将 PWA 作为 UWP 应用运行所需的 *appxmanifest* 文件。</span><span class="sxs-lookup"><span data-stu-id="443c4-108">For the most part, you can package your PWA for Xbox One in the [same way you would for Windows](./windows-features.md), using the [PWA Builder](https://www.pwabuilder.com/) tools or [Visual Studio](https://visualstudio.microsoft.com/vs/) IDE to generate the *appxmanifest* file required to run your PWA as a UWP app.</span></span> <span data-ttu-id="443c4-109">但是，本指南将引导你完成一些关键差异。</span><span class="sxs-lookup"><span data-stu-id="443c4-109">However, there are several key differences this guide will walk you through.</span></span>

## <span data-ttu-id="443c4-110">在 Xbox 上部署和测试 PWA</span><span class="sxs-lookup"><span data-stu-id="443c4-110">Deploying and testing PWAs on Xbox</span></span>

<span data-ttu-id="443c4-111">若要开始，请按照 [以下步骤激活 Xbox *One 开发人员模式*](/windows/uwp/xbox-apps/devkit-activation) 。</span><span class="sxs-lookup"><span data-stu-id="443c4-111">To get started, follow these [steps to activate *Xbox One Developer Mode*](/windows/uwp/xbox-apps/devkit-activation) .</span></span> <span data-ttu-id="443c4-112">激活开发人员模式后，为 Xbox 设置[*Device Portal，*](/windows/uwp/debug-test-perf/device-portal-xbox)以从开发环境的浏览器远程访问 Xbox。</span><span class="sxs-lookup"><span data-stu-id="443c4-112">With Developer Mode activated, [set up *Device Portal for Xbox*](/windows/uwp/debug-test-perf/device-portal-xbox) to gain remote access to your Xbox from the browser in your dev environment.</span></span>

<span data-ttu-id="443c4-113">现在，你已准备好使用*PWA*生成器或*Visual Studio。*</span><span class="sxs-lookup"><span data-stu-id="443c4-113">Now you're ready to deploy your app for testing using either *PWA Builder* or *Visual Studio*.</span></span>

### <span data-ttu-id="443c4-114">选项 1：PWA 生成器</span><span class="sxs-lookup"><span data-stu-id="443c4-114">Option 1: PWA Builder</span></span>

<span data-ttu-id="443c4-115">[PWA Builder](https://www.pwabuilder.com/) 是一Node.js从 Node 程序包管理器 (NPM) 。</span><span class="sxs-lookup"><span data-stu-id="443c4-115">[PWA Builder](https://www.pwabuilder.com/) is a Node.js app you can install from Node Package Manager (NPM).</span></span> <span data-ttu-id="443c4-116">它使用网站的元数据在 Android、iOS 和 Windows 中生成本机托管应用。</span><span class="sxs-lookup"><span data-stu-id="443c4-116">It uses the metadata of your website to generate native hosted apps across Android, iOS and Windows.</span></span> <span data-ttu-id="443c4-117">如果网站已有 Web [应用清单](https://developer.mozilla.org/docs/Web/Manifest)，PWA 生成器将使用它生成特定于平台的安装程序包。</span><span class="sxs-lookup"><span data-stu-id="443c4-117">If your site already has a [web app manifest](https://developer.mozilla.org/docs/Web/Manifest), PWA Builder will use it to generate platform-specific installation packages.</span></span> <span data-ttu-id="443c4-118">否则，PWA 生成器将基于manifest.js\* 生成基于\* 文件的基本应用程序。</span><span class="sxs-lookup"><span data-stu-id="443c4-118">Otherwise, PWA Builder will generate a basic *manifest.json* file based on the characteristics of your site.</span></span>

#### <span data-ttu-id="443c4-119">要求</span><span class="sxs-lookup"><span data-stu-id="443c4-119">Requirements</span></span>

 - <span data-ttu-id="443c4-120">[Node.js](https://nodejs.org/en/)，其中包括 NPM。</span><span class="sxs-lookup"><span data-stu-id="443c4-120">[Node.js](https://nodejs.org/en/), which includes NPM.</span></span>

#### <span data-ttu-id="443c4-121">安装</span><span class="sxs-lookup"><span data-stu-id="443c4-121">Setup</span></span>

1.  <span data-ttu-id="443c4-122">打开节点命令提示符以安装 PWA 生成器：</span><span class="sxs-lookup"><span data-stu-id="443c4-122">Open a Node command prompt to install PWA Builder:</span></span>
    
    ```shell
    npm install pwabuilder --global
    ```  
    
2.  <span data-ttu-id="443c4-123">对您的网站 URL 运行 PWA 生成器：</span><span class="sxs-lookup"><span data-stu-id="443c4-123">Run PWA Builder on your website URL:</span></span>
    
    ```shell
    pwabuilder https://example.com/ -windows10
    ```  
    
    <span data-ttu-id="443c4-124">*-windows10*标志将程序包生成限制到 UWP (Windows 10) 。</span><span class="sxs-lookup"><span data-stu-id="443c4-124">The *-windows10* flag limits package generation to Windows 10 (UWP).</span></span> <span data-ttu-id="443c4-125">你可以省略它以跨所有受支持的平台（包括 iOS 和 Android）生成程序包。</span><span class="sxs-lookup"><span data-stu-id="443c4-125">You can omit it to generate packages across all supported platforms, including iOS and Android.</span></span> <span data-ttu-id="443c4-126">有关详细信息， [请参阅 PWA 生成器](https://docs.pwabuilder.com/) 文档。</span><span class="sxs-lookup"><span data-stu-id="443c4-126">See the [PWA Builder docs](https://docs.pwabuilder.com/) for more info.</span></span>
    
3.  <span data-ttu-id="443c4-127">从适用于 Xbox 的[Device](/windows/uwp/debug-test-perf/device-portal-xbox) \*\*\*\* Portal 中，转到"我的游戏&应用添加"，选择上传松散文件的选项，然后选择当前目录中 PWA 生成器生成的  >  \*\*\*\*  >  \*\*\*\* Windows 10\*\* 应用清单文件夹。</span><span class="sxs-lookup"><span data-stu-id="443c4-127">From the [Device Portal for Xbox](/windows/uwp/debug-test-perf/device-portal-xbox), go to **Home** > **My games & apps** > **Add**, choose the option to *upload loose files*, and select the Windows 10 app manifest folder generated by PWA Builder in the current directory.</span></span>

4.  <span data-ttu-id="443c4-128">逐步完成向导以完成安装过程。</span><span class="sxs-lookup"><span data-stu-id="443c4-128">Step through the wizard to complete the installation process.</span></span> <span data-ttu-id="443c4-129">安装后。</span><span class="sxs-lookup"><span data-stu-id="443c4-129">Once installed.</span></span> <span data-ttu-id="443c4-130">你将能够从 Xbox One 仪表板查看和启动 PWA。</span><span class="sxs-lookup"><span data-stu-id="443c4-130">you'll be able to see and launch your PWA from the Xbox One dashboard.</span></span>
    
### <span data-ttu-id="443c4-131">选项 2：Visual Studio</span><span class="sxs-lookup"><span data-stu-id="443c4-131">Option 2: Visual Studio</span></span>

<span data-ttu-id="443c4-132">功能齐全的免费 Visual Studio [Community 2017](https://visualstudio.microsoft.com/vs/community/) 包括 Windows 10 开发人员工具、通用应用模板、代码编辑器、功能强大的调试器、Windows Mobile 仿真器、丰富的语言支持等，所有这些都可供生产使用。</span><span class="sxs-lookup"><span data-stu-id="443c4-132">The free, full-featured [Visual Studio Community 2017](https://visualstudio.microsoft.com/vs/community/) includes Windows 10 developer tools, universal app templates, a code editor, a powerful debugger, Windows Mobile emulators, rich language support and much more—all ready to use in production.</span></span> <span data-ttu-id="443c4-133">专业[*版\*\*和企业*](https://visualstudio.microsoft.com/vs/compare/)版提供了更多功能。</span><span class="sxs-lookup"><span data-stu-id="443c4-133">The [*Professional* and *Enterprise*](https://visualstudio.microsoft.com/vs/compare/) versions provide even more features.</span></span>

#### <span data-ttu-id="443c4-134">要求</span><span class="sxs-lookup"><span data-stu-id="443c4-134">Requirements</span></span>

-   <span data-ttu-id="443c4-135">[**Visual Studio 2017**](https://visualstudio.microsoft.com/vs/
    )年：任何版本，包括免费的 *社区* 版。</span><span class="sxs-lookup"><span data-stu-id="443c4-135">[**Visual Studio 2017**](https://visualstudio.microsoft.com/vs/
): any version, including the free *Community* edition.</span></span>
-   <span data-ttu-id="443c4-136">[**Windows 10 SDK：**](/windows/uwp/xbox-apps/development-environment-setup)在 Visual Studio *2017 安装程序中选择此可选组件*。</span><span class="sxs-lookup"><span data-stu-id="443c4-136">[**Windows 10 SDK**](/windows/uwp/xbox-apps/development-environment-setup): Select this optional component in the *Visual Studio 2017 Installer*.</span></span>
    
#### <span data-ttu-id="443c4-137">安装</span><span class="sxs-lookup"><span data-stu-id="443c4-137">Setup</span></span>

1.  <span data-ttu-id="443c4-138">按照步骤设置 [PWA 并](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#set-up-and-run-your-universal-windows-app)作为通用 Windows 应用运行。</span><span class="sxs-lookup"><span data-stu-id="443c4-138">Follow the steps to [set up and run your PWA as a Universal Windows app](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#set-up-and-run-your-universal-windows-app).</span></span> <span data-ttu-id="443c4-139">通过此操作，你将拥有能够访问通用 Windows API 的完全正常运行的 Windows 10 应用。</span><span class="sxs-lookup"><span data-stu-id="443c4-139">With this, you'll have a fully functioning Windows 10 app capable of accessing Universal Windows APIs.</span></span>
2.  <span data-ttu-id="443c4-140">现在，可以使用 [Visual Studio 远程调试器] (/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine？view=vs-2017 &preserve-view=true) 在 Xbox One (上部署和调试 PWA (作为 U) WP 应用)  (。</span><span class="sxs-lookup"><span data-stu-id="443c4-140">You can now deploy and debug your PWA (as a UWP app) on the Xbox One (as with any other Windows 10 remote device) using the [Visual Studio remote debugger](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017 &preserve-view=true).</span></span> <span data-ttu-id="443c4-141">或者，你可以按照以下步骤使用适用于 Xbox 的 [Device Portal](/windows/uwp/debug-test-perf/device-portal-xbox) 安装 PWA。</span><span class="sxs-lookup"><span data-stu-id="443c4-141">Alternately, you can install your PWA using the [Device Portal for Xbox](/windows/uwp/debug-test-perf/device-portal-xbox) using the following steps.</span></span>
3.  <span data-ttu-id="443c4-142">从适用于 Xbox 的 Device Portal 中，>"我的游戏&应用>"，选择上传 *应用包和依赖项的选项*。</span><span class="sxs-lookup"><span data-stu-id="443c4-142">From the Device Portal for Xbox, go to Home > My games & apps > Add, choose the option to upload *App Package and Dependencies*.</span></span>
4.  <span data-ttu-id="443c4-143">导航到在步骤 1 中为应用生成的程序包文件夹，然后选择 *要上载的 .appx* 文件。</span><span class="sxs-lookup"><span data-stu-id="443c4-143">Navigate to the package folder you generated for your app in Step 1 and select the *.appx* file for upload.</span></span> <span data-ttu-id="443c4-144">[ *.appx*文件](/windows/uwp/packaging/packaging-uwp-apps)是 UWP 应用包文件，可出于测试目的在任意设备上旁加载。</span><span class="sxs-lookup"><span data-stu-id="443c4-144">The [*.appx* file](/windows/uwp/packaging/packaging-uwp-apps) is a UWP app package file that can be sideloaded on any device for testing purposes.</span></span>
5.  <span data-ttu-id="443c4-145">接下来点击 **"依赖项"** 按钮 *，为你的应用* 选择依赖项子文件夹并上传每个依赖项。</span><span class="sxs-lookup"><span data-stu-id="443c4-145">Next tap the **Dependencies** button and select the *dependencies* sub-folder for your app and upload each one.</span></span> <span data-ttu-id="443c4-146">只有从适用于 Xbox 的 Device Portal 部署应用时，才需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="443c4-146">This step is only required for deploying apps from the Device Portal for Xbox.</span></span> <span data-ttu-id="443c4-147">Visual Studio从 Microsoft Store 交付时，远程调试和最终用户的计算机已经安装了这些依赖项时，它将提供依赖项。</span><span class="sxs-lookup"><span data-stu-id="443c4-147">Visual Studio delivers dependencies when remote debugging and the end user's machine will already have these installed when delivered from the Microsoft Store.</span></span>
6.  <span data-ttu-id="443c4-148">上传应用包和依赖项后，单击"部署"部分下的\*\*\*\*"转到"按钮\*\*，将安装应用。</span><span class="sxs-lookup"><span data-stu-id="443c4-148">With the app package and the dependencies uploaded, click the **Go** button under the *Deploy* section and the app will be installed.</span></span> <span data-ttu-id="443c4-149">你已准备好从 Xbox 启动应用！</span><span class="sxs-lookup"><span data-stu-id="443c4-149">You're ready to launch your app from Xbox!</span></span>
    
## <span data-ttu-id="443c4-150">Xbox 上的 PWA 的 UX 注意事项</span><span class="sxs-lookup"><span data-stu-id="443c4-150">UX considerations for PWAs on Xbox</span></span>

### <span data-ttu-id="443c4-151">"10 英尺体验"设计</span><span class="sxs-lookup"><span data-stu-id="443c4-151">Design for the "10-Foot Experience"</span></span>

<span data-ttu-id="443c4-152">Xbox One 被视为"10 英尺体验"，这意味着你的用户可能坐在离屏幕至少 10 英尺远的地方。</span><span class="sxs-lookup"><span data-stu-id="443c4-152">Xbox One is considered a "10-foot experience", meaning that your users will likely be sitting a minimum of 10 feet away from the screen.</span></span> <span data-ttu-id="443c4-153">因此，请考虑如何以该距离使用你的应用，而不是使用鼠标和键盘的传统桌面 Web 浏览器体验。</span><span class="sxs-lookup"><span data-stu-id="443c4-153">As such, consider how your app might be used at that distance as opposed to the traditional desktop web browser experience with a mouse and keyboard.</span></span> <span data-ttu-id="443c4-154">有关设计和 UX 指南，请查看"针对[Xbox 和电视进行设计"。](/windows/uwp/design/devices/designing-for-tv)</span><span class="sxs-lookup"><span data-stu-id="443c4-154">For design and UX guidance, check out [Designing for Xbox and TV](/windows/uwp/design/devices/designing-for-tv).</span></span>

### <span data-ttu-id="443c4-155">了解"TV SafeZone"</span><span class="sxs-lookup"><span data-stu-id="443c4-155">Understand the "TV SafeZone"</span></span>

<span data-ttu-id="443c4-156">电视制造商将围绕可剪裁 [你的应用](/windows/uwp/design/devices/designing-for-tv#tv-safe-area) 的内容应用"安全区域"。</span><span class="sxs-lookup"><span data-stu-id="443c4-156">Television manufacturers will apply a ["safe-zone"](/windows/uwp/design/devices/designing-for-tv#tv-safe-area) around the content that can clip your app.</span></span> <span data-ttu-id="443c4-157">默认情况下，我们在应用周围应用安全边框来说明这一点，但是，可以通过调用并指定以下项来确保你的应用采用 [`setDesiredBoundsMode`](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) 全屏大小 [`useCoreWindow`](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode) ：</span><span class="sxs-lookup"><span data-stu-id="443c4-157">By default, we apply a safe border around your app to account for this, however you can ensure that your app takes the full screen size by calling [`setDesiredBoundsMode`](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) and specifying [`useCoreWindow`](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode):</span></span>

```javascript
var applicationView = Windows.UI.ViewManagement.ApplicationView.getForCurrentView();
applicationView.setDesiredBoundsMode(Windows.UI.ViewManagement.ApplicationViewBoundsMode.useCoreWindow);
```  

<span data-ttu-id="443c4-158">有关详细信息，请查看 [`Windows.UI.ViewManagement`](/uwp/api/windows.ui.viewmanagement) 命名空间文档。</span><span class="sxs-lookup"><span data-stu-id="443c4-158">For more, check out the [`Windows.UI.ViewManagement`](/uwp/api/windows.ui.viewmanagement) namespace documentation.</span></span>

### <span data-ttu-id="443c4-159">管理 XY 焦点和导航</span><span class="sxs-lookup"><span data-stu-id="443c4-159">Manage XY focus and navigation</span></span>

<span data-ttu-id="443c4-160">Xbox 的用户输入方法是游戏板或遥控器，使用 [XY](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction)导航系统，允许用户通过上移、下移、向左和向右移动将焦点从控件转移到控件。</span><span class="sxs-lookup"><span data-stu-id="443c4-160">User input methods for Xbox are gamepad or remote control, which use a [XY navigation system](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction), allowing the user to shift the focus from control to control by moving up, down, left, and right.</span></span>

<span data-ttu-id="443c4-161">因此，你会希望确保你的应用适用于 XY 导航。</span><span class="sxs-lookup"><span data-stu-id="443c4-161">As such, you'll want to make sure your app works well with XY navigation.</span></span> <span data-ttu-id="443c4-162">此外，请务必禁用鼠标[模式\*\*](/windows/uwp/xbox-apps/how-to-disable-mouse-mode)，该模式默认适用于 UWP 应用 (并且可能不适用于应用的 Xbox 体验) 。</span><span class="sxs-lookup"><span data-stu-id="443c4-162">Also, be sure to [disable *mouse mode*](/windows/uwp/xbox-apps/how-to-disable-mouse-mode), which is on by default for UWP apps (and probably not applicable to your app's Xbox experience).</span></span>

<span data-ttu-id="443c4-163">以下代码关闭 `mouse` 模式，并启用游戏板输入以生成 DOM 键盘事件：</span><span class="sxs-lookup"><span data-stu-id="443c4-163">The following code turns off `mouse` mode and enables gamepad input to generate DOM keyboard events:</span></span>

```javascript
navigator.gamepadInputEmulation = "keyboard";
```  

<span data-ttu-id="443c4-164">或者，你可以指定，这也会关闭鼠标，不生成 DOM 键盘事件，并允许你使用标准 Web 和 `gamepad` /或 WinRT 游戏板 API。</span><span class="sxs-lookup"><span data-stu-id="443c4-164">Alternately, you can specify `gamepad`, which also turns off mouse, does not generate DOM keyboard events, and allows you to use the standard web and/or WinRT gamepad APIs.</span></span>

<span data-ttu-id="443c4-165">若要启用方向导航，请查看 [TVJS 库，](#tvjs)接下来将讨论。</span><span class="sxs-lookup"><span data-stu-id="443c4-165">To enable directional navigation, check out the [TVJS library](#tvjs), discussed next.</span></span>

### <span data-ttu-id="443c4-166">TVJS</span><span class="sxs-lookup"><span data-stu-id="443c4-166">TVJS</span></span>

<span data-ttu-id="443c4-167">[TVJS 是帮助程序](https://github.com/Microsoft/TVHelpers) 库的集合，可更轻松地为电视生成 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="443c4-167">[TVJS is a collection of helper libraries](https://github.com/Microsoft/TVHelpers) that make it easier to build web applications for the TV.</span></span> <span data-ttu-id="443c4-168">如果你要生成也将在 Xbox 上运行的托管 Web 应用，TVJS 可帮助添加对方向导航\*\* 的支持，以及提供多个控件，以便更轻松地与电视上的内容进行交互。</span><span class="sxs-lookup"><span data-stu-id="443c4-168">If you are building a hosted web app that will also run on the Xbox, TVJS can help add support for *directional navigation*, as well as provide several controls that make it easier to interact with content on the TV.</span></span>

<span data-ttu-id="443c4-169">[方向导航](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) 是 TVJS 功能，在电视应用的页面内提供自动二维导航。</span><span class="sxs-lookup"><span data-stu-id="443c4-169">[Directional navigation](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) is a TVJS feature that provides automatic two-dimensional navigation within the pages of your TV app.</span></span> <span data-ttu-id="443c4-170">借助它，无需捕获和处理应用页面中的导航，也无需为 UI 中每个元素显式指定所有有效的焦点目标。</span><span class="sxs-lookup"><span data-stu-id="443c4-170">With it, there's no need to trap and handle navigation within the pages of your app, or to explicitly specify all the valid focus targets for each element in the UI.</span></span> <span data-ttu-id="443c4-171">自动焦点处理使用户能够以直观可靠的方式四处导航。</span><span class="sxs-lookup"><span data-stu-id="443c4-171">Automatic focus handling enables users can navigate around in an intuitive and robust way.</span></span>

<span data-ttu-id="443c4-172">当用户使用控制器方向按钮导航应用 UI 时，自动对焦算法将查看一组潜在的焦点目标，确定下一个元素要移动到，然后自动将焦点设置为该元素。</span><span class="sxs-lookup"><span data-stu-id="443c4-172">As your user navigates the app UI with the controller direction buttons, the automatic focus algorithm looks at the set of potential focus targets, determines the next element to move to and then automatically sets focus to that element.</span></span> <span data-ttu-id="443c4-173">为了确定下一个元素，该算法结合了方向输入、过去的焦点历史记录和页面上 UI 元素的物理布局。</span><span class="sxs-lookup"><span data-stu-id="443c4-173">To determine the next element, the algorithm combines directional input, past focus history, and the physical layout of UI elements on the page.</span></span>

<span data-ttu-id="443c4-174">若要启用方向导航，请包含以下脚本引用：</span><span class="sxs-lookup"><span data-stu-id="443c4-174">To enable directional navigation, include the following script reference:</span></span>

```html
<script src="directionalnavigation-1.0.0.0.js"></script>
```  

<span data-ttu-id="443c4-175">默认情况下，只有 `<a>` `<button>` 、 `<input>` 、 `<select>` 和 `<textarea>` 元素是可聚焦的。</span><span class="sxs-lookup"><span data-stu-id="443c4-175">By default, only `<a>`, `<button>`, `<input>`, `<select>`, and `<textarea>` elements are focusable.</span></span> <span data-ttu-id="443c4-176">若要在其他元素上启用焦点，请为其分配有效的 [tabindex](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex)。</span><span class="sxs-lookup"><span data-stu-id="443c4-176">To enable focus on other elements, assign them a valid [tabindex](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex).</span></span>

```html
<div tabindex="0″>This div is eligible for focus</div>
```  

请查看 [DirectionalNavigation](https://github.com/Microsoft/TVHelpers/wiki/DirectionalNavigation) 文档，了解如何更改根元素、设置初始焦点、覆盖下一个焦点、针对焦点优化控件、自定义输入。 <span data-ttu-id="443c4-178">还有一些其他有用的示例。</span><span class="sxs-lookup"><span data-stu-id="443c4-178">There's also a number of other useful samples.</span></span>

## <span data-ttu-id="443c4-179">Xbox 上的媒体 PWA</span><span class="sxs-lookup"><span data-stu-id="443c4-179">Media PWAs on Xbox</span></span>

<span data-ttu-id="443c4-180">如果你要生成适用于 Xbox One 的媒体播放 PWA，请注意以下注意事项。</span><span class="sxs-lookup"><span data-stu-id="443c4-180">If you're building a media playback PWA for Xbox One, be aware of the following considerations.</span></span>

### <span data-ttu-id="443c4-181">浏览器中的 EME (加密) 扩展</span><span class="sxs-lookup"><span data-stu-id="443c4-181">Encrypted Media Extensions (EME) in the browser</span></span>

<span data-ttu-id="443c4-182">Xbox One 上的 Microsoft Edge[](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)浏览器不支持使用 EME (加密媒体) 。</span><span class="sxs-lookup"><span data-stu-id="443c4-182">The Microsoft Edge browser on Xbox One does not support [Encrypted Media Extensions](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API) (EME).</span></span> <span data-ttu-id="443c4-183">如果你的媒体 PWA 使用它 (DRM) ，你将无法从 Xbox 上的浏览器运行它。</span><span class="sxs-lookup"><span data-stu-id="443c4-183">If your media PWA uses it for digital rights management (DRM), you won't be able to run it from the browser on your Xbox.</span></span> <span data-ttu-id="443c4-184">相反，使用 [PWABuilder](#deploying-and-testing-pwas-on-xbox)或 Visual Studio原型并测试它作为 Xbox One 应用，如上所述。</span><span class="sxs-lookup"><span data-stu-id="443c4-184">Instead, prototype and test it as a [Xbox One app using PWABuilder or Visual Studio](#deploying-and-testing-pwas-on-xbox), as described above.</span></span> <span data-ttu-id="443c4-185">还可以在 Windows 上的 Microsoft Edge 浏览器（完全支持 EME）上运行它。</span><span class="sxs-lookup"><span data-stu-id="443c4-185">You can also run it on the Microsoft Edge browser on Windows, where EME is fully supported.</span></span>

### <span data-ttu-id="443c4-186">与系统媒体传输控件集成</span><span class="sxs-lookup"><span data-stu-id="443c4-186">Integrating with System Media Transport Controls</span></span>

<span data-ttu-id="443c4-187">如果你的应用是媒体应用，应用通过屏幕按钮[、Cortana](https://support.xbox.com/xbox-one/console/cortana-voice-commands)语音命令、导航窗格中的系统媒体传输控件或其他设备的[Xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
)和[Xbox One SmartGlass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2)应用[](/windows/uwp/audio-video-camera/system-media-transport-controls)响应用户启动的媒体控件，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="443c4-187">If your app is a media app, it is important that your app responds to the media controls initiated by the user via on-screen buttons, [Cortana voice commands](https://support.xbox.com/xbox-one/console/cortana-voice-commands), the [System Media Transport Controls](/windows/uwp/audio-video-camera/system-media-transport-controls) in the nav pane, or the [Xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
) and [Xbox One SmartGlass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2) apps on other devices.</span></span> <span data-ttu-id="443c4-188">查看[TVJS](#tvjs)库中的[MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview)控件，该控件会自动与这些控件集成。</span><span class="sxs-lookup"><span data-stu-id="443c4-188">Take a look at the [MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview) control from the [TVJS library](#tvjs), which automatically integrates with these controls.</span></span> <span data-ttu-id="443c4-189">或者，你可以手动 [与系统媒体传输控件集成](https://msdn.microsoft.com/windows/uwp/audio-video-camera/system-media-transport-controls)。</span><span class="sxs-lookup"><span data-stu-id="443c4-189">Alternately, you can manually [integrate with the System Media Transport Controls](https://msdn.microsoft.com/windows/uwp/audio-video-camera/system-media-transport-controls).</span></span>

### <span data-ttu-id="443c4-190">PlayReady 内容加密</span><span class="sxs-lookup"><span data-stu-id="443c4-190">PlayReady content encryption</span></span>

<span data-ttu-id="443c4-191">截至本文撰写之时，编码支持[ `cbcs` ](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme)仅限于 XBox One 版本 1709 (或更高版本的 PlayReady) 。</span><span class="sxs-lookup"><span data-stu-id="443c4-191">At the time of this writing, [`cbcs` encoding support is limited](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme) to the PlayReady client for XBox One (version 1709 or higher).</span></span> <span data-ttu-id="443c4-192">如果 PWA 的媒体仅支持 *cbcs* 加密，请注意，你的应用的功能可能受限 (或在 Windows 上) 不可用。</span><span class="sxs-lookup"><span data-stu-id="443c4-192">If the media for your PWA only supports *cbcs* encryption, be aware that your app's functionality will be likely be limited (or completely unavailable) on Windows.</span></span>

## <span data-ttu-id="443c4-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="443c4-193">See also</span></span>
<span data-ttu-id="443c4-194">[South Ridge 视频](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video)：一个适用于 Xbox 的示例视频应用，React.js托管在 Web 服务器上。</span><span class="sxs-lookup"><span data-stu-id="443c4-194">[South Ridge Video](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video): A sample video app for Xbox built with React.js and hosted on a web server.</span></span>

<span data-ttu-id="443c4-195">[针对 Xbox 和电视](/windows/uwp/design/devices/designing-for-tv)进行设计：设计通用 Windows 平台 (UWP) 应用，以便它在 Xbox One 和电视屏幕上外观良好且运行良好。</span><span class="sxs-lookup"><span data-stu-id="443c4-195">[Designing for Xbox and TV](/windows/uwp/design/devices/designing-for-tv): Design your Universal Windows Platform (UWP) app so that it looks good and functions well on Xbox One and television screens.</span></span>

<span data-ttu-id="443c4-196">[Xbox 最佳做法：](/windows/uwp/xbox-apps/tailoring-for-xbox)遵循这些最佳做法为 Xbox One 定制应用。</span><span class="sxs-lookup"><span data-stu-id="443c4-196">[Xbox best practices](/windows/uwp/xbox-apps/tailoring-for-xbox): Follow these best practices to tailor your app for Xbox One.</span></span>

<span data-ttu-id="443c4-197">[Microsoft Store 中的 PWA：](/microsoft-edge/progressive-web-apps-edgehtml/microsoft-store)下面将 (和原因！) 将 PWA 提交到 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="443c4-197">[PWAs in the Microsoft Store](/microsoft-edge/progressive-web-apps-edgehtml/microsoft-store): Here's how (and why!) to Submit your PWA to the Microsoft Store.</span></span>

<span data-ttu-id="443c4-198">[Xbox One 上的 UWP：](/windows/uwp/xbox-apps/)适用于 Xbox One 的 UWP 应用开发的完整指南。</span><span class="sxs-lookup"><span data-stu-id="443c4-198">[UWP on Xbox One](/windows/uwp/xbox-apps/): A complete guide to UWP app development for Xbox One.</span></span>
