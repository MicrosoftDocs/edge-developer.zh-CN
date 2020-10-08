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
# 适用于 Xbox One 的渐进 Web 应用  

你可以扩展 web 应用程序，并通过 Microsoft Store 将其用作 Xbox One 应用，同时仍继续使用你的现有框架、CDN 和服务器后端。  与所有通用 Windows 平台 (UWP) 应用一样，在 Xbox One 上运行 (PWAs) 渐进 Web 应用还可以调用本机 Windows 10 Api。  已有许多 PWAs 可用于 Xbox One，尤其是在 [媒体播放应用](#media-pwas-on-xbox)的类别中。  

大多数情况下，你可以按照 [对 Windows 的相同方式](./windows-features.md)将 pwa 打包为 Xbox one，方法是使用 [PWA 生成器](https://www.pwabuilder.com/) 工具或 [VISUAL Studio](https://visualstudio.microsoft.com/vs/) IDE 生成将 pwa 作为 UWP 应用运行所需的 *package.appxmanifest* 文件。 但是，本指南将指导你完成几项关键的差异。

## 在 Xbox 上部署和测试 PWAs

若要开始使用，请按照以下 [步骤激活 *Xbox One 开发人员模式*](/windows/uwp/xbox-apps/devkit-activation) 。 启用开发人员模式后，[设置*Xbox 的 Device Portal* ](/windows/uwp/debug-test-perf/device-portal-xbox)以从开发人员环境中的浏览器获取对 xbox 的远程访问。

现在，你可以使用 *PWA 生成器* 或 *Visual Studio*部署你的应用以进行测试。

### 选项1： PWA 生成器

[PWA 生成器](https://www.pwabuilder.com/) 是可以从节点程序包管理器 (NPM) 安装的 Node.js 应用。 它使用您的网站的元数据在 Android、iOS 和 Windows 之间生成本机托管应用。 如果您的网站已有 [web 应用清单](https://developer.mozilla.org/docs/Web/Manifest)，PWA 生成器将使用它来生成特定于平台的安装程序包。 否则，PWA 生成器将基于你的网站的特征， * 在文件上* 生成基本manifest.js。

#### 要求
 - [Node.js](https://nodejs.org/en/)，其中包括 NPM。

#### 安装

1. 打开节点命令提示符以安装 PWA 生成器：

    ```
    npm install pwabuilder --global
    ```

2. 在网站 URL 上运行 PWA 生成器：

    ```
    pwabuilder https://example.com/ -windows10
    ```

    *-Windows10*标志将包生成限制为 Windows 10 (UWP) 。 你可以省略它以跨所有受支持的平台（包括 iOS 和 Android）生成程序包。 有关详细信息，请参阅 [PWA 生成器文档](https://docs.pwabuilder.com/) 。

3. 从[适用于 Xbox 的 Device Portal](/windows/uwp/debug-test-perf/device-portal-xbox)，转到 "**开始**  >  使用**我的游戏" & 应用**  >  "**添加**"，选择*上载松散文件*的选项，然后选择 "PWA" 生成器在当前目录中生成的 Windows 10 应用部件清单文件夹。

4. 逐步完成向导以完成安装过程。 安装后。 你将能够从 Xbox One 仪表板中查看和启动你的 PWA。


### 选项2： Visual Studio

免费的功能齐全的 [Visual Studio 社区 2017](https://visualstudio.microsoft.com/vs/community/) 包括 Windows 10 开发人员工具、通用应用模板、代码编辑器、功能强大的调试器、Windows Mobile 模拟器、丰富的语言支持等-一切都准备好在生产中使用。 [*专业*版和*企业*](https://visualstudio.microsoft.com/vs/compare/)版提供的功能更多功能。

#### 要求

 - [**Visual Studio 2017**](https://visualstudio.microsoft.com/vs/
)：任何版本，包括免费 *社区* 版本。
 - [**Windows 10 SDK**](/windows/uwp/xbox-apps/development-environment-setup)：在 *Visual Studio 2017 安装程序*中选择此可选组件。

#### 安装

1. 按照以下步骤 [将 PWA 设置和运行为通用 Windows 应用](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#set-up-and-run-your-universal-windows-app)。 使用此功能，你将拥有能够访问通用 Windows Api 的功能齐全的 Windows 10 应用。

2. 现在，你可以在 Xbox One (上部署和调试你的 PWA (作为 UWP) 应用，与使用 [Visual Studio 远程调试器](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017
)的任何其他 Windows 10 远程设备) 一样。 或者，你可以使用以下步骤使用 [Device Portal For Xbox](/windows/uwp/debug-test-perf/device-portal-xbox) 安装 PWA。

3. 从 Xbox 的 Device Portal 中，转到 "家庭 > 我的游戏" & 应用 > "添加"，选择上载 *应用包和依赖关系*的选项。

4. 导航到步骤1中为你的应用生成的程序包文件夹，并选择要上载的 *.appx* 文件。 [ *.Appx*文件](/windows/uwp/packaging/packaging-uwp-apps)是一个 UWP 应用包文件，可在任何设备上旁加载用于测试目的。

5. 接下来，点击 " **依赖项** " 按钮，然后选择应用的 " *依赖关系* " 子文件夹并上载每个子文件夹。 只有从适用于 Xbox 的 Device Portal 部署应用时，才需要执行此步骤。 当从 Microsoft Store 发送远程调试且最终用户的计算机从 Microsoft Store 发送时，Visual Studio 将提供依赖关系。

6. 在应用包和上载的依赖项的情况下，单击 "*部署*" 部分下的 "**转到**" 按钮，将安装应用。 你已准备好从 Xbox 启动你的应用！

## Xbox 上 PWAs 的 UX 注意事项

### "10 英尺体验" 的设计

Xbox One 被视为 "10 英尺体验"，这意味着你的用户可能会在离屏幕最少10英尺的位置。 因此，请考虑你的应用在该距离上的使用方式，而不是使用鼠标和键盘的传统桌面 web 浏览器体验。 有关设计和 UX 指南，请查看 [适用于 Xbox 和电视的设计](/windows/uwp/design/devices/designing-for-tv)。

### 了解 "电视 SafeZone"

电视制造商将在可剪裁你的应用的内容周围应用 ["安全区域"](/windows/uwp/design/devices/designing-for-tv#tv-safe-area) 。 默认情况下，我们会在你的应用周围应用安全边框以考虑此情况，但你可以通过调用 [`setDesiredBoundsMode`](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) 和指定以下内容来确保你的应用获得完整的屏幕大小 [`useCoreWindow`](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode) ：

```JavaScript
var applicationView = Windows.UI.ViewManagement.ApplicationView.getForCurrentView();
applicationView.setDesiredBoundsMode(Windows.UI.ViewManagement.ApplicationViewBoundsMode.useCoreWindow);
```

有关详细信息，请查看 [`Windows.UI.ViewManagement`](/uwp/api/windows.ui.viewmanagement) 命名空间文档。

### 管理 XY 焦点和导航

适用于 Xbox 的用户输入方法是游戏板或远程控制，它使用 [XY 导航系统](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction)，允许用户通过向上、向下、向左和向右移动焦点来将焦点从控件移动到控件。

因此，你将需要确保你的应用可以正常使用 XY 导航。 此外，请确保禁用默认情况下对 UWP 应用 (的[*鼠标模式*](/windows/uwp/xbox-apps/how-to-disable-mouse-mode)，并且可能不适用于你的应用的 Xbox 体验) 。

以下代码关闭 `mouse` 模式并启用游戏板输入以生成 DOM 键盘事件：

```JavaScript
navigator.gamepadInputEmulation = "keyboard";
```

或者，你也可以指定 `gamepad` 同时关闭鼠标，不生成 DOM 键盘事件，并允许你使用标准的 web 和/或 WinRT 游戏板 api。

若要启用方向导航，请查看 [TVJS 库](#tvjs)，下面将进行讨论。

### TVJS

[TVJS 是帮助程序库的集合](https://github.com/Microsoft/TVHelpers) ，便于为电视构建 web 应用程序。 如果你要生成的托管 web 应用还将在 Xbox 上运行，TVJS 可以帮助添加对 *方向导航*的支持，并提供多个控件，使你可以更轻松地与电视上的内容交互。

[方向导航](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) 是一种 TVJS 功能，可在电视应用的页面内提供自动二维导航。 利用它，无需在应用的页面内捕获和处理导航，或者为 UI 中的每个元素显式指定所有有效的焦点目标。 自动的焦点处理使用户能够以直观、稳健的方式导航。

当用户使用控制器方向按钮导航应用 UI 时，自动焦点算法将查看潜在的焦点目标集，确定要移动到的下一个元素，然后自动将焦点设置到该元素。 为了确定下一个元素，该算法将方向输入、过去的焦点历史记录和页面上的 UI 元素的物理布局结合在一起。

若要启用方向导航，请包含以下脚本引用：

```HTML
<script src="directionalnavigation-1.0.0.0.js"></script>
```

默认情况下，只有、、、 `<a>` `<button>` `<input>` `<select>` 和 `<textarea>` 元素可获得焦点。 若要对其他元素启用焦点，请为它们分配一个有效的 [tabindex](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex)。

```HTML
<div tabindex="0″>This div is eligible for focus</div>
```

查看 [DirectionalNavigation](https://github.com/Microsoft/TVHelpers/wiki/DirectionalNavigation) 文档，了解如何更改根元素、设置初始焦点、替代下一个焦点、优化控件以获得焦点、自定义输入。 还有许多其他有用的示例。

## Xbox 上的媒体 PWAs

如果你要为 Xbox One 构建媒体播放 PWA，请注意以下注意事项。

### 在浏览器中 (EME) 加密媒体扩展

Xbox One 上的 Microsoft Edge 浏览器不支持 (EME) 的 [加密媒体扩展](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API) 。 如果媒体 PWA 将其用于数字权限管理 (DRM) ，您将无法从 Xbox 上的浏览器中运行它。 相反， [使用 PWABuilder 或 Visual Studio 将其作为 Xbox one 应用](#deploying-and-testing-pwas-on-xbox)进行原型，如下所述。 您也可以在 Windows 上的 Microsoft Edge 浏览器上运行它，其中 EME 完全受支持。

### 与系统媒体传输控件集成

如果你的应用是媒体应用，你的应用必须通过屏幕按钮、 [Cortana 语音命令](https://support.xbox.com/xbox-one/console/cortana-voice-commands)、导航窗格中的 [系统媒体传输控件](/windows/uwp/audio-video-camera/system-media-transport-controls) 或其他设备上的 [xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
) 和 [xbox one SmartGlass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2) 应用来响应由用户发起的媒体控件。 查看[TVJS 库](#tvjs)中的[MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview)控件，该控件自动与这些控件集成。 或者，您也可以手动 [与系统媒体传输控件集成](https://msdn.microsoft.com/windows/uwp/audio-video-camera/system-media-transport-controls)。

### PlayReady 内容加密

在此编写时， [ `cbcs` 编码支持限制](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme)为 XBox one (版本1709或更高版本的 PlayReady 客户端) 。 如果你的 PWA 媒体仅支持 *cbcs* 加密，请注意你的应用的功能可能会受到限制 (或在 Windows 上完全不可用) 。



## 另请参阅
[南凸缘视频](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video)：使用 React.js 构建的和托管在 web 服务器上的 Xbox 视频应用示例。

[针对 xbox 和电视进行设计](/windows/uwp/design/devices/designing-for-tv)：将你的通用 Windows 平台 (UWP) 应用，使其在 Xbox one 和电视屏幕上的外观良好且功能良好。

[Xbox 最佳做法](/windows/uwp/xbox-apps/tailoring-for-xbox)：按照这些最佳做法为 Xbox one 定制你的应用。

[Microsoft store 中的 PWAs](/microsoft-edge/progressive-web-apps-edgehtml/microsoft-store)：下面介绍了如何 (和为什么！ ) 将 PWA 提交到 Microsoft Store。

[Xbox one 上的 uwp](/windows/uwp/xbox-apps/)：适用于 xbox ONE 的 uwp 应用开发的完整指南。
