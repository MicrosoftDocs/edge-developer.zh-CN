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
# Microsoft Edge WebView2 （开发人员预览版）

使用 Microsoft Edge WebView2 控件，你可以使用[Microsoft edge （Chromium）](https://www.microsoftedgeinsider.com/)作为呈现引擎在你的应用程序中托管 web 内容。

WebView2 控件目前处于开发人员预览版中，在该控件中，你可以将解决方案原型并与我们共享反馈，以便对未来的稳定 API 进行整形。 由于我们在预览期间演变 API，因此可能会发生一些重大更改，并且当发生这种情况时，你需要同时更新 WebView2 SDK 和 Microsoft Edge （Chromium）浏览器。 在 SDK 的[发行说明](./releasenotes.md)中将注明重大更改。 这将被锁定，WebView2 方法 beta 和稳定。

## 支持的平台

对于 Win32 C/c + + 和适用于 .NET Framework 4.6.2 或更高版本的 Windows 窗体和 WPF 的开发人员预览版，Windows 10、Windows 8.1、Windows 8、windows 7、2016 Windows server 2012/2012R2 和 Windows Server 2008 R2 上都提供了 .NET Core 3.0 或更高版本。 WinUI 3.0 的 Alpha 版本可[在此处](https://docs.microsoft.com/uwp/toolkits/winui3/)找到。

## 入门

若要使用 WebView2 控件生成和测试你的应用程序，你需要安装[Microsoft Edge （Chromium）](https://www.microsoftedgeinsider.com/download/)和[WebView2 SDK](https://aka.ms/webviewnuget) 。 选择以下选项之一开始使用！

* [Win32 C/c + + 入门](./gettingstarted/win32.md)
* [WPF 入门](./gettingstarted/wpf.md)
* [Windows 窗体入门](./gettingstarted/winforms.md)

请在我们的[WebView2 反馈](https://aka.ms/webviewfeedback)存储库中留下反馈。

## WebView2 示例

[WebView2 示例](https://github.com/MicrosoftEdge/WebView2Samples)存储库包含演示 WebView2 SDK 的所有功能及其 API 使用模式的示例。 随着我们将更多功能添加到 WebView2 SDK，我们将定期更新我们的示例应用程序。

## 应用分发

WebView2 控件利用 Microsoft Edge （Chromium）浏览器。 当分发你的应用时，请务必确保在应用程序将运行的所有用户计算机上安装了 Edge 浏览器。 此外，你还应注意安装了哪个版本和信道，例如稳定、Beta、开发或未固定。 当安装在计算机上时，WebView2 控制器将利用最稳定的浏览器版本。

### 未来的计划更改

我们认识到，在应用程序运行的所有用户计算机上，Edge 浏览器可能不可用，或者可能很难控制边缘浏览器安装过程。 若要确保你的应用程序在所有计算机上运行，而不依赖客户端 Microsoft Edge 浏览器的安装状态，我们将发布 Microsoft Edge WebView2 运行时。 我们将在搜索已安装的浏览器的预发布版本之前，进一步更新 WebView2 以搜索运行时的稳定版本。

我们还认识到，某些应用开发人员在受限制的环境中运行，因此希望支持两种分发选项：长绿和固定版本。

对于大多数开发人员来说，"长绿" 是推荐的分发模型。 在此模式下，WebView2 运行时的更新将由 Microsoft 完全管理，而不需要你的应用程序即可自动保持最新。 使用此自我更新模型，您可以确保应用充分利用托管 web 内容的最新功能和安全更新。

对于受限环境，我们还将支持固定版本分发模型。 在此模型中，你的应用程序将选择并打包特定的 WebView2 版本。 Web 视图版本的更新将由应用程序负责，并且将独立于任何托管的 Microsoft 更新机制。 如果能够对浏览器版本进行绝对控制和更新应用程序的使用时间，则应选择此模型。

## Microsoft Edge WebView2 运行时

Microsoft Edge WebView2 运行时是经过优化以供 WebView2 应用程序使用的浏览器二进制文件的包装。 它将独立运行或与客户端边缘浏览器安装并排运行。 运行时的单个安装将支持任意数量的 WebView2 应用程序。 运行时的安装不会显示为浏览器安装到最终用户，即没有桌面快捷方式、开始菜单项或协议注册。

使用 WebView2 的应用程序必须确保已发生 Microsoft Edge WebView2 运行时的安装。 在应用程序安装时，应检查当前安装状态，该状态可通过使用[GetAvailableCoreWebView2BrowserVersionString](./reference/win32/0-9-488/webview2-idl.md#getavailablecorewebview2browserversionstring)确定。 如果 WebView2 运行时不可用，则应将 Microsoft Edge WebView2 运行时安装程序链接到你的安装流。

## Microsoft Edge WebView2 SDK

若要利用你的应用中的 WebView2，你需要在应用程序中安装和引用[WEBVIEW2 SDK](https://aka.ms/webviewnuget) 。 我们的 NuGet 版本将同时包含发布版本和预发布版本。 发布版本包含我们当前打算发布到一般可用性的公共 Api。

预发布版本将包含其他实验性[api](./reference/win32/0-9-488-reference-webview2.md#experimental)。 这些是我们正在评估的 Api 和功能，并希望在将它们提升到发布版本之前提供[反馈](https://aka.ms/webviewfeedback)。

## 针对即将推出的版本进行开发

对于开发，你可能希望面向 Beta、开发人员或工作场所，以确保你的应用程序可用于即将推出的版本或利用即将推出的功能。 所有预发布的频道均由已安装的客户端 Microsoft Edge 浏览器提供。 若要面向这些频道之一，请确保你的开发计算机上已安装的 Edge 浏览器是你想要的频道。 开发人员可以使用注册表键或环境变量将 WebView2 从最稳定的发现最稳定的版本更改为最小的最稳定版本。 查看[CreateCoreWebView2EnvironmentWithOptions](./reference/win32/0-9-488/webview2-idl.md#createcorewebview2environmentwithoptions)中的更多详细信息。

## 调试 WebView2

### DevTools

你可以使用[Microsoft Edge （Chromium）开发人员工具](https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium)来调试在 web 视图中显示的 web 内容，就像在浏览器中一样。 在将焦点置于 "web 视图" 窗口时，按下 `F12` 或 `Ctrl`  +  `Shift`  +  `I` 右键单击 `Inspect` 以打开 "开发工具"。

:::image type="complex" source="./media/f12.png" alt-text="F12":::
   F12
:::image-end:::  

<!--![F12](./media/f12.png)  -->  

**注意当在 Visual Studio 中调试应用程序时，如果附加了本机调试器，则 `F12` 可能会触发本机调试器，而不是开发人员工具。 使用 `Ctrl`  +  `Shift`  +  `I` 或右键单击 + `Inspect` 以避免潜在的热键冲突。**

### Visual Studio

你可以使用 Visual Studio 2019 （最低版本16.4 预览版2）中的脚本调试程序在 WebView2 中从 IDE 直接调试你的脚本。 请确保安装了**包含 c + +** 工作负荷的桌面开发中的**JavaScript 诊断**组件。

:::image type="complex" source="./media/vs-js-diagnostics.jpg" alt-text="Visual Studio JavaScript 诊断":::
   Visual Studio JavaScript 诊断
:::image-end:::  

<!--![vs-js-diagnostics](./media/vs-js-diagnostics.jpg)  -->  

右键单击你的项目，然后选择 "**属性**"。 在 "**配置属性**  >  **调试**  >  **调试器类型**" 下，选择**JavaScript （WebView2）** 选项以启用 WebView2 脚本调试。 更多详细信息，请稍后再关注。

:::image type="complex" source="./media/vs-script-debugger.jpg" alt-text="Visual Studio 脚本调试程序":::
   Visual Studio 脚本调试程序
:::image-end:::  

<!--![vs-script-debugger](./media/vs-script-debugger.jpg)  -->  

### Visual Studio Code

你还可以使用 Visual Studio 代码在 WebView2 中从 IDE 调试你的脚本。 有关详细信息，请单击[此处](https://github.com/microsoft/vscode-edge-debug2/blob/master/README.md#microsoft-edge-chromium-webview-applications)。

## 与 WebView2 团队取得联系  

通过分享你的反馈帮助我们构建更丰富的 WebView2 体验！ 请访问我们的[反馈](https://aka.ms/webviewfeedback)存储库以提交功能请求或 bug 报告。

这也是搜索已知问题的好地方。
在开发人员预览版中，我们还将收集遥测数据以帮助我们构建更好的 Web 视图。 用户可以通过导航到浏览器中的 edge://settings/privacy 并关闭浏览器数据收集来关闭 Web 视图数据收集。
