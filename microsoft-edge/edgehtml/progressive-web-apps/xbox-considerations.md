---
description: 确保 PWA 为 Xbox 提供出色的体验
title: 适用于 Xbox One 的渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 Web 应用， PWA， Edge， Windows， UWP， Xbox， Xbox One， TVJS
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3ac4174c821f221d6d666a25880867275ca5cbd5
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397669"
---
# <a name="progressive-web-apps-for-xbox-one"></a>适用于 Xbox One 的渐进式 Web 应用  

你可以扩展 Web 应用程序，并可通过 Microsoft Store 将其作为 Xbox One 应用提供，同时仍继续使用现有框架、CDN 和服务器后端。  就像所有通用 Windows 平台 \ (UWP\) 应用一样，在 Xbox One 上运行的渐进式 Web 应用 \ (PWA\) 也可以调用本机 Windows 10 API。  已经有许多适用于 Xbox One 的 PWA，尤其是在媒体播放应用 [类别中](#media-pwas-on-xbox)。  

在大多数情况下，你可以采用适用于[Windows](./windows-features.md)的相同方式打包适用于 Xbox One 的[PWA，使用 PWA](https://www.pwabuilder.com)生成器工具或[Visual Studio](https://visualstudio.microsoft.com/vs) IDE 生成将 PWA 作为 UWP 应用运行所需的文件。 `appxmanifest`  但是，本指南将介绍几个主要区别。  

## <a name="deploying-and-testing-pwas-on-xbox"></a>在 Xbox 上部署和测试 PWA  

若要开始，请按照 [以下步骤激活 Xbox *One 开发人员模式*](/windows/uwp/xbox-apps/devkit-activation)。  在激活开发人员模式后，为 Xbox 设置[*Device Portal，*](/windows/uwp/debug-test-perf/device-portal-xbox)以从你的开发环境的浏览器远程访问你的 Xbox。  

现在，你已准备好使用 PWA Builder 或 Visual Studio 部署应用以进行测试。  

### <a name="option-1--pwa-builder"></a>选项 1：PWA 生成器  

[PWA 生成器](https://www.pwabuilder.com) 是一款Node.js应用，可以从 Node 程序包管理器 \ (NPM\) 。  它使用网站的元数据跨 Android、iOS 和 Windows 生成本机托管应用。  如果网站已有 Web [应用清单](https://developer.mozilla.org/docs/Web/Manifest)，PWA 生成器将使用它生成特定于平台的安装程序包。  否则，PWA 生成器将基于网站的特征 `manifest.json` 生成基本文件。  

#### <a name="requirements"></a>要求  

*   [Node.js， ](https://nodejs.org)包括 NPM。  

#### <a name="setup"></a>安装  

1.  打开节点命令提示符以安装 PWA 生成器：  
    
    ```shell
    npm install pwabuilder --global
    ```  
    
1.  对您的网站 URL 运行 PWA 生成器：  
    
    ```shell
    pwabuilder https://example.com/ -windows10
    ```  
    
    *-windows10*标志将程序包生成限制到 Windows 10 \ (UWP\) 。  你可以省略它以在所有受支持的平台（包括 iOS 和 Android）中生成程序包。  有关详细信息， [请参阅 PWA 生成器](https://docs.pwabuilder.com) 文档。  
    
1.  从适用于 Xbox 的[Device](/windows/uwp/debug-test-perf/device-portal-xbox) **** Portal 中，转到"我的游戏&应用添加"，选择上传松散文件的选项，然后选择当前目录中 PWA 生成器生成的  >  ****  >  **** Windows 10**** 应用清单文件夹。  
1.  逐步完成向导以完成安装过程。  安装后。  你将能够从 Xbox One 仪表板查看和启动 PWA。  
    
### <a name="option-2--visual-studio"></a>选项 2：Visual Studio  

功能齐全的免费 Visual Studio [Community 2017](https://visualstudio.microsoft.com/vs/community) 包括 Windows 10 开发人员工具、通用应用模板、代码编辑器、功能强大的调试器、Windows Mobile 仿真器、丰富的语言支持等，所有这些功能都已准备好在生产中使用。  专业 [版和企业](https://visualstudio.microsoft.com/vs/compare) 版提供了更多功能。  

#### <a name="requirements"></a>要求  

*   [Visual Studio 2017：](https://visualstudio.microsoft.com/vs)任何版本，包括免费社区版。  
*   [Windows 10 SDK：](/windows/uwp/xbox-apps/development-environment-setup)在 Visual Studio 2017 安装程序中选择此可选组件。  

#### <a name="setup"></a>安装  

1.  按照步骤将 [PWA](./windows-features.md#set-up-and-run-your-universal-windows-app)设置为通用 Windows 应用并运行。  这样，你将拥有能够访问通用 Windows API 的完全正常运行的 Windows 10 应用。  
1.  你现在可以在 Xbox One \ (上部署和调试 PWA \ (作为 UWP 应用\) ，就像使用 Visual Studio 远程调试器一样，任何其他 Windows 10 远程设备 [\) 一样](/visualstudio/debugger/run-windows-store-apps-on-a-remote-machine?view=vs-2017&preserve-view=true
)。  或者，你可以按照以下步骤使用适用于 Xbox 的 [Device Portal](/windows/uwp/debug-test-perf/device-portal-xbox) 安装 PWA。  
1.  从适用于 Xbox 的 Device **** Portal，转到"主页我的游戏  >  **"\&应用**  >  **"添加**"，选择上传**应用包和依赖项的选项**。  
1.  导航到你在步骤 1 中为应用生成的程序包文件夹，然后选择 `.appx` 要上载的文件。  [.appx 文件](/windows/uwp/packaging/packaging-uwp-apps)是 UWP 应用包文件，可在任何设备上旁加载以进行测试。  
1.  接下来， **点击"依赖项"** 按钮，为应用选择子 `dependencies` 文件夹并上载每个子文件夹。  只有从适用于 Xbox 的 Device Portal 部署应用时，才需要此步骤。  Visual Studio从 Microsoft Store 交付时，远程调试和最终用户的计算机已经安装了这些依赖项时，它将提供依赖项。  
1.  上传应用包和依赖项后，单击"部署"部分下的****"转到"按钮**，即可安装应用。  你已准备好从 Xbox 启动应用！  

## <a name="ux-considerations-for-pwas-on-xbox"></a>Xbox 上的 PWA 的 UX 注意事项  

### <a name="design-for-the-10-foot-experience"></a>针对"10 英尺体验"的设计  

Xbox One 被视为"10 英尺体验"，这意味着你的用户可能坐在离屏幕至少 10 英尺远的地方。  因此，请考虑如何在该距离使用你的应用，而不是使用鼠标和键盘的传统桌面 Web 浏览器体验。  有关设计和 UX 指南，请查看 [针对 Xbox 和电视进行设计](/windows/uwp/design/devices/designing-for-tv)。  

### <a name="understand-the-tv-safezone"></a>了解"TV SafeZone"  

电视制造商将围绕可剪裁 [应用](/windows/uwp/design/devices/designing-for-tv#tv-safe-area) 的内容应用安全区域。  默认情况下，我们在你的应用周围应用安全边框来说明这一点，但你可以通过调用 [setDesiredBoundsMode](/uwp/api/windows.ui.viewmanagement.applicationview.setdesiredboundsmode) 并指定 [useCoreWindow](/uwp/api/windows.ui.viewmanagement.applicationviewboundsmode)来确保你的应用采用全屏大小：  

```javascript
var applicationView = Windows.UI.ViewManagement.ApplicationView.getForCurrentView();
applicationView.setDesiredBoundsMode(Windows.UI.ViewManagement.ApplicationViewBoundsMode.useCoreWindow);
```  

有关详细信息，请查看 [Windows.UI.ViewManagement](/uwp/api/windows.ui.viewmanagement) 命名空间文档。  

### <a name="manage-xy-focus-and-navigation"></a>管理 XY 焦点和导航  

Xbox 的用户输入方法是游戏板或遥控器，使用 [XY](/windows/uwp/design/devices/designing-for-tv#xy-focus-navigation-and-interaction)导航系统，允许用户通过上移、下移、向左和向右移动将焦点从控件转移到控制。  

因此，你需要确保你的应用适用于 XY 导航。  此外，请务必禁用鼠标[](/windows/uwp/xbox-apps/how-to-disable-mouse-mode)模式，该模式默认适用于 UWP 应用 \ (并且可能不适用于应用的 Xbox 体验\) 。  

以下代码关闭 `mouse` 模式，并启用游戏板输入以生成 DOM 键盘事件：  

```javascript
navigator.gamepadInputEmulation = "keyboard";
```  

或者，你可以指定，这也会关闭鼠标，不生成 DOM 键盘事件，并允许你使用标准 Web 和 `gamepad` /或 WinRT 游戏板 API。  

若要启用方向导航，请查看 [TVJS 库，](#tvjs)接下来将讨论。  

### <a name="tvjs"></a>TVJS  

[TVJS 是帮助](https://github.com/Microsoft/TVHelpers) 程序库的集合，可更轻松地为电视生成 Web 应用程序。  如果你正在构建也将在 Xbox 上运行的托管 Web 应用，TVJS 可以帮助添加对方向导航** 的支持，并提供多个控件，以便更轻松地与电视上的内容进行交互。  

[方向导航](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) 是一项 TVJS 功能，它提供电视应用页面中的自动二维导航。  借助它，无需捕获和处理应用页面中的导航，也无需显式指定 UI 中每个元素的所有有效焦点目标。  自动焦点处理使用户能够以直观可靠的方式四处导航。  

在用户使用控制器方向按钮导航应用 UI 时，自动对焦算法将查看一组潜在的焦点目标，确定下一个要移动到的元素，然后自动设置该元素的焦点。  为了确定下一个元素，该算法结合了方向输入、过去的焦点历史记录和页面上 UI 元素的物理布局。  

若要启用方向导航，请包含以下脚本引用：  

```html
<script src="directionalnavigation-1.0.0.0.js"></script>
```  

默认情况下，只有 `<a>` 、 `<button>` `<input>` 、 `<select>` 和 `<textarea>` 元素是可聚焦的。  若要在其他元素上启用焦点，请为其分配有效的 [tabindex](https://developer.mozilla.org/docs/Web/HTML/Global_attributes/tabindex)。  

```html
<div tabindex="0″>This div is eligible for focus</div>
```  

请查看 [DirectionalNavigation](https://github.com/Microsoft/TVHelpers/wiki/DirectionalNavigation) 文档，了解如何更改根元素、设置初始焦点、覆盖下一个焦点、优化焦点控件、自定义输入。  还有其他一些有用的示例。

## <a name="media-pwas-on-xbox"></a>Xbox 上的媒体 PWA  

如果你要生成适用于 Xbox One 的媒体播放 PWA，请注意以下注意事项。  

### <a name="encrypted-media-extensions-eme-in-the-browser"></a>浏览器中的 EME (加密) 扩展  

Xbox One 上的 Microsoft Edge 浏览器不支持加密媒体扩展 [\ (](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API) EME\) 。  如果你的媒体 PWA 使用它进行数字版权管理 \ (DRM\) ，你将不能从 Xbox 上的浏览器运行它。  相反，使用 [PWABuilder](#deploying-and-testing-pwas-on-xbox)或 Visual Studio作为 Xbox One 应用进行原型制作和测试，如上所述。  还可以在 Windows 上的 Microsoft Edge 浏览器（完全支持 EME）上运行它。  

### <a name="integrating-with-system-media-transport-controls"></a>与系统媒体传输控件集成  

如果你的应用是媒体应用，你的应用通过屏幕按钮[、Cortana](https://support.xbox.com/xbox-one/console/cortana-voice-commands)语音命令、导航窗格中的系统媒体传输控件或其他设备的[Xbox](https://www.microsoft.com/p/xbox/9wzdncrfjbd8
)和[Xbox One SmartGlass](https://www.microsoft.com/p/xbox-one-smartglass/9wzdncrfhvx2)应用[](/windows/uwp/audio-video-camera/system-media-transport-controls)响应用户启动的媒体控件非常重要。  查看[TVJS](#tvjs)库中的[MediaPlayer](https://github.com/Microsoft/TVHelpers/wiki/MediaPlayer-Overview)控件，该控件会自动与这些控件集成。  或者，你可以手动 [与系统媒体传输控件集成](/windows/uwp/audio-video-camera/system-media-transport-controls)。  

### <a name="playready-content-encryption"></a>PlayReady 内容加密  

截至本文撰写之时 [，cbcs](/playready/packaging/content-encryption-modes#support-for-the-cbcs-aes-cbc-encryption-scheme) 编码支持仅限于 XBox One \ (版本 1709 或更高版本\) PlayReady 客户端。  如果 PWA 的媒体仅支持 **cbcs** 加密，请注意你的应用的功能在 Windows 上可能受限 \ (或完全不可用\) 。  

## <a name="see-also"></a>另请参阅  

[South 这一视频](https://github.com/Microsoft/uwp-experiences/tree/master/apps/video)：一个适用于 Xbox 的示例视频应用，React.js托管在 Web 服务器上。  

[针对 Xbox 和电视](/windows/uwp/design/devices/designing-for-tv)进行设计：设计通用 Windows 平台 \ (UWP\) 应用，以便它在 Xbox One 和电视屏幕上外观良好且运行良好。  

[Xbox 最佳做法：](/windows/uwp/xbox-apps/tailoring-for-xbox)遵循这些最佳做法来定制适用于 Xbox One 的应用。  

[Microsoft Store 中的 PWA：](./microsoft-store.md)下面是 \ (和原因？\) 将 PWA 提交到 Microsoft Store。  

[Xbox One 上的 UWP：](/windows/uwp/xbox-apps/index)适用于 Xbox One 的 UWP 应用开发的完整指南。  
