---
description: 使用 Microsoft Edge WebView2 发布应用时的分发选项
title: Microsoft Edge WebView2 应用的分发
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: cbe3fb35bdf64a3627256028940cf868b8b185c2
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182407"
---
# 使用 WebView2 的应用分发  

在分发 WebView2 应用时，请确保在应用启动之前，支持的 web 平台（ [WebView2 运行时][Webview2Installer]）存在。  本文介绍如何 (开发人员 \ ) 安装 WebView2 运行时，并为 WebView2 应用使用两种分发模式：长  [绿](#evergreen-distribution-mode) 和 [固定版本](#fixed-version-distribution-mode)。  

## 长绿分布模式  

> [!NOTE]
> 对于大多数开发人员，建议使用长绿分布模式。  

长时间分布模式可确保你的应用充分利用最新功能和安全更新。  它具有下列特征。  

*   基础 web 平台 \ (WebView2 运行时 \ ) 自动更新，无需额外的精力。  
*   所有使用长时间分布模式的应用均使用长绿 WebView2 运行时的共享副本，该副本节省磁盘空间。  
    
### 了解 WebView2 运行时  

WebView2 运行时是可再发行的运行时，用作 WebView2 应用的支持 web 平台。  该概念类似于 Visual c + + 或适用于 c + +/.NET 应用的 .NET 运行时。  运行时包含已修改的 Microsoft Edge \ (Chromium \ ) 二进制文件，这些二进制文件对应用进行了微调和测试。  在安装时，运行时不会显示为用户可见的浏览器。  例如，用户没有浏览器桌面快捷方式或 "开始" 菜单项。  

在开发和测试期间，你可以使用作为后备 web 平台。  

*   WebView2 运行时  
*   任何预览体验成员 \ (非稳定 \ ) Microsoft Edge \ (Chromium \ ) 浏览器频道  
    
在生产环境中，必须确保用户设备上的运行时在应用启动前才存在。  Microsoft Edge 稳定通道不可用于 WebView2 用法。  决策可防止应用在生产中的浏览器上参与依赖。

不要在浏览器上执行依赖关系，原因如下：  

*   Microsoft Edge \ (Chromium \ ) 不保证在所有用户设备上都存在。  例如，从 Windows Update 断开的设备或不是由 Microsoft 直接管理的设备，而不是由 Microsoft (直接管理的，教育机构的大型企业和市场的 ) 可能没有浏览器。  允许你分发 WebView2 运行时，可避免将浏览器作为应用的必备项。  
*   浏览器和应用具有不同的用例，因此对浏览器的依赖可能会对你的应用产生意外的副作用。  例如，IT 管理员可以针对内部网站兼容性版本控制浏览器。  WebView2 运行时允许应用在浏览器更新处于活动的管理期间保持长绿。  
*   与浏览器相反，运行时是为应用方案开发和测试的，在某些情况下，可能包括浏览器中尚不提供的 bug 修复。  
    
将来，长绿 WebView2 运行时计划随 Windows 将来的版本提供。  将运行时与你的生产应用进行部署，直到运行时更广泛地可用。  

### 部署长绿 WebView2 运行时  

设备上的所有长时间应用仅需要一个安装长绿 WebView2 运行时。  [WebView2 运行时下载页面][Webview2Installer]上提供了许多工具。  以下工具可帮助你部署长绿运行时。  

*   WebView2 运行时引导程序是大约 2 MB \ ) 安装程序的小型 (。  WebView2 运行时引导程序从与用户的设备体系结构匹配的 Microsoft 服务器下载和安装长绿运行时。  
*   使用链接以编程方式下载引导程序。  
*   WebView2 运行时独立安装程序是在脱机环境下安装长绿 WebView2 运行时的完整安装程序。  
    
当前，引导程序和独立安装程序仅支持每台计算机安装，这需要提升。  如果安装程序运行时没有提升权限，系统将提示用户提升权限。  

使用以下工作流以确保在你的应用启动之前已安装运行时。  你可以根据你的方案调整工作流。  示例代码在 [Samples 存储库] [GitHubMicrosoftedgeWebView2samplesWebview2Deployment] 中可用。  

#### 仅联机部署  

如果您有一个仅联机部署方案，并且假定用户拥有 internet 访问权限，请完成以下步骤。  

1.  在应用设置期间，确保已安装运行时。  若要验证，请完成以下操作之一。  
    *   检查 regkey 是否 `pv (REG_SZ)` 存在且不是 `null` 空的。  `pv (REG_SZ)`在以下位置查找。  
        
        在64位 Windows 上  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        在32位 Windows 上  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   运行 [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] 并确保 `versionInfo` 为 `NULL` 。  
1.  如果未安装运行时，请使用链接以编程方式下载引导程序。  
1.  使用 "静默安装" 从提升的进程或命令提示符处调用引导 `MicrosoftEdgeWebview2Setup.exe /silent /install` 程序。  
    
以前的工作流具有以下优点。  

*   仅在需要时或不需要打包安装程序时，才安装运行时。  
*   引导程序将自动检测设备体系结构并安装匹配的运行时。  
*   以静默方式安装运行时。  
    
你还可以选择将引导程序与你的应用打包，而不是按需以编程方式下载它。  

#### 脱机部署  

如果你有一个脱机部署方案，其中应用部署必须完全脱机工作，请完成以下步骤。  

1.  下载 [独立安装程序][Webview2Installer]。  
1.  在应用安装程序或更新程序中包括安装程序。  
1.  在应用设置期间，确保已安装运行时。  若要验证，请完成以下操作之一。  
    *   检查 regkey 是否 `pv (REG_SZ)` 存在且不是 `null` 空的。  `pv (REG_SZ)`在以下位置查找。  
        
        在64位 Windows 上  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
        在32位 Windows 上  
        
        ```text
        HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\EdgeUpdate\Clients\{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
        ```  
        
    *   运行 [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring] 并确保 `versionInfo` 为 `NULL` 。  
1.  如果未安装运行时，请运行独立安装程序。  如果要运行静默安装，请从提升的进程运行安装程序，或复制并运行以下命令。  
    
    ```shell
    MicrosoftEdgeWebView2RuntimeInstaller{X64/X86/ARM64}.exe /silent /install
    ```  
    
### 在长绿模式下保持兼容  

Web 不断发展。  长时间 WebView2 运行时保持最新，为你提供最新的功能和安全修补程序。  为了确保你的应用与 web 保持兼容，你应该设置测试基础结构。  

非稳定的 Microsoft Edge 通道 \ (Beta/Dev/sneak \ ) 提供一种可快速查看 WebView2 运行时中所进入的内容的功能。  与开发 Microsoft Edge 网站一样，你应该定期测试你的 WebView2 应用。  针对其中一个非稳定信道测试你的 WebView2 应用，如果出现问题，请更新你的应用或 [报告问题][GithubMicrosoftedgeWebviewfeedback] 。 通常情况下，推荐使用开发人员和 Beta。  若要帮助确定哪种频道正确，请导航到 [Microsoft Edge 频道概述][DeployEdgeMicrosoftEdgeChannels]。  你可以在你的测试环境中下载 [不稳定的 Microsoft Edge 通道][DownloadNonstableEdge] ，并使用 `regkey` 或环境变量指示测试应用的通道首选项。  有关详细信息，请导航到 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions]。  您也可以使用 [WebDriver][HowtoWebdriver] 自动执行 WebView2 测试。

## 固定版本分发模式   

对于具有严格兼容性要求的受限环境，请考虑使用固定版本分发模式。  使用固定版本分发模式选择并打包特定版本的 WebView2 运行时。  你可以指定你的应用的运行时更新的计时。  固定版本分发模式不会接收任何自动更新。 计划更新你的应用和运行时。  

> [!NOTE] 
> 固定版本分发模式以前称为 "携带"。  

若要使用 "固定版本" 模式，请完成以下操作

1.  [下载][Webview2Installer] 已修复的版本程序包。 
1.  使用命令行 `expand {path to the package} -F:* {path to the destination folder}` 或 WinRAR 之类的工具解压缩程序包。 避免在文件资源管理器中解压缩，因为它可能不会生成正确的文件夹结构。  
1.  在项目中包含解压缩的固定版本二进制文件。  
1.  在创建 WebView2 环境时，指示固定版本二进制文件的路径。  
    *   对于 Win32 C/c + +，你可以使用 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions] 函数创建环境。  使用 `browserExecutableFolder` 参数指示包含的文件夹的路径 `msedgewebview2.exe` 。  
    *   对于 .NET，你可以执行以下任一选项来指定环境。  
        
        > [!NOTE]
        > 必须先指定环境，WebView2 属性才 `Source` 会生效。  
        
        *   `CreationProperties`在 WebView2 元素上设置 \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinFormsWebview2]\ ) 属性。  使用 `BrowserExecutableFolder` `CoreWebView2CreationProperties` \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfCorewebview2creationpropertiesCorewebview2creationproperties] / [WinForms][ReferenceWinFormsMicrosoftWebWebview2WinForms]\ ) 类中的成员指示固定版本二进制文件的路径。  
        *   使用 `EnsureCoreWebView2Async` \ ([WPF][ReferenceWpfMicrosoftWebWebview2WpfWebview2Ensurecorewebview2async] / [WinForms][ReferenceWinformsMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]\ ) 指定环境。  使用 `browserExecutableFolder` [CoreWebView2Environment][ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2environmentCreateasync] 中的参数指示固定版本二进制文件的路径。  
1.  将固定版本的二进制文件打包并与你的应用一起发送。  根据需要更新二进制文件。  
    
### 修复版本的已知问题  

与长时间运行时相比，修复的版本不具有安装过程，这将导致 [Microsoft PlayReady][MicrosoftPlayReady] 在未经修改的情况下运行。  你可以通过完成以下操作来缓解此问题。  

1.  找到你在用户设备上部署固定版本程序包的路径，例如以下位置。
    
    ```text
    D:\myapp\Microsoft.WebView2.FixedVersionRuntime.87.0.664.8.x64
    ```  
    
1.  在用户的设备上运行以下命令。

    ```shell
    icacls {Fixed Version path} /grant *S-1-15-2-2:(OI)(CI)(RX)
    icacls {Fixed Version path} /grant *S-1-15-2-1:(OI)(CI)(RX)
    ```  

1.  PlayReady 应立即在用户的设备上工作。  在 "**固定版本**" 文件夹的 "**安全**" 选项卡中，应包括和的权限 `ALL APPLICATION PACKAGES` `ALL RESTRICTED APPLICATION PACKAGES` 。  

    :::image type="complex" source="../media/play-ready-permission.png" alt-text="PlayReady 的权限" lightbox="../media/play-ready-permission.png":::
        PlayReady 的权限  
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

[GitHubMicrosoftMicrosoftEdgeWebView2SamplesWebview2Deployment]: https://github.com/MicrosoftEdge/WebView2Samples#webview2-deployment "WebView2 部署-MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftPlayReady]: https://www.microsoft.com/playready "Microsoft PlayReady"  
