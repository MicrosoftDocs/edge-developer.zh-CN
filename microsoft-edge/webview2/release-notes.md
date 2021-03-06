---
description: WebView2 SDK Microsoft Edge发行说明
title: Win32 Microsoft Edge WPF 和 WinForms 的 WebView2 发行说明
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 2c07430668b269dcada16c96045022fd68398508
ms.sourcegitcommit: 0e67a56b9dc1f7a86924d142db0efd36fd99d38b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "11608679"
---
# <a name="release-notes-for-webview2-sdk"></a>WebView2 SDK 发行说明  

WebView2 团队将每六周更新一次[WebView2 SDK。][NuGetGallery]  查看以下内容，了解有关产品公告、添加、修改和 API 的变更最新信息。  

> [!NOTE]
> 确保在更新应用包后重新编译NuGet程序包。  WebView 团队建议在使用预发布程序包进行开发时使用 Canary 通道，在使用发布包时使用 Evergreen WebView2 Runtime。  有关详细信息，请导航到["匹配 WebView2 运行时版本"。][Webview2ConceptsVersioningMatchingWebview2RuntimeVersions]  

> [!NOTE]
> WebView2 Bug 修复特定于运行时或 SDK。  

## <a name="10902-prerelease"></a>1.0.902-prerelease

发布日期：2021 年 6 月 1 日  

[NuGet包][NuGetGallery1.0.902-prerelease]\|要Microsoft Edge的最低版本：86.0.616.0 或更高版本 \|完整 API 兼容性：92.0.902.0 或更高版本  

### <a name="general"></a>概要  
*   改进了 WebView2 启动性能和磁盘占用。

#### <a name="experimental-features"></a>实验性功能  

*   添加了 [IsSwipeNavigationEnabled][Webview2ReferenceWin32Icorewebview2experimentalsettings5ViewWebview210902PrereleaseGetIsswipenavigationenabled] 属性以启用或禁用最终用户在支持触摸输入的设备上使用轻扫手势在 WebView2 中导航的能力。
*   添加了 [BrowserProcessExited][Webview2ReferenceWin32Icorewebview2experimentalenvironment4ViewWebview210902PrereleaseAddBrowserprocessexited] 事件。
*   添加了 [add_ClientCertificateRequested API][Webview2ReferenceWin32Icorewebview2experimental3ViewWebview210902PrereleaseAddClientcertificaterequested]。 它允许显示客户端证书对话框提示（如果需要）并允许访问所需的元数据来替换默认客户端证书对话框提示。

#### <a name="bug-fixes"></a>Bug 修复  

*   修复了鼠标左键单击不消除上下文菜单的问题。 此更改特定于运行时。
*   修复了当共享相同用户数据文件夹的应用的 exe 文件具有不一致的版本信息时 WebView2 创建失败的错误。
*   修复了无法由 AreBrowserAcceleratorKeysEnabled 禁用刷新、主页、后退等特殊浏览器密钥的问题。 此更改特定于运行时。
*   修复了 WebView2 .NET 控件中的一个错误，即 WebView2 窗口在后台创建时为空。 \ ([\#1077][GithubMicrosoftedgeWebviewfeedbackIssue1077]\) 。 
*   通过按"enter"或"esc"关闭文件选取器对话框将不再使使用 WebView 控件的 WPF 应用程序崩溃。 \ ([\#1099][GithubMicrosoftedgeWebviewfeedbackIssue1099]\) 。 
*   修复了在附加 WebResourceRequested 事件处理程序时 [AllowSingleSignOnUsingOSPrimaryAccount][Webview2ReferenceWin32Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount] 无法正常使用 WebView2 的问题。 此更改特定于运行时。 \ ([\#1183][GithubMicrosoftedgeWebviewfeedbackIssue1183]\) 。  
*   下载文件不再会破坏 WebView2 DefaultBackgroundColor 透明度。 此更改特定于运行时。 \ ([\#1108][GithubMicrosoftedgeWebviewfeedbackIssue1108]\) 。 
*   删除了包含 Microsoft 品牌打造的屏幕共享媒体选取器消息。 \ ([\#940][GithubMicrosoftedgeWebviewfeedbackIssue940]\) 。 
*   修复了 WebView2 WinForm 控件中隐藏父表单不会隐藏 WebView2 控件 \ ([\#828][GithubMicrosoftedgeWebviewfeedbackIssue828] 和 [\#1079][GithubMicrosoftedgeWebviewfeedbackIssue1079]\) 的 bug。
*   向 WebView2 WS_CLIPCHILDREN添加了静态样式样式。 \ ([\#1013][GithubMicrosoftedgeWebviewfeedbackIssue1013]\) 。 
*   修复了右键单击链接导致 WebView2 主机应用崩溃的 Bug。 此更改特定于运行时。
*   修复了在移动到较新的 Edge WebView2 运行时版本时可能导致主机应用进程崩溃的可靠性 Bug。
*   **DEPRECATION：** 正式弃用的默认BackgroundColor API Windows 7。


#### <a name="promotions"></a>促销

*   [下载 API][Webview2ReferenceWin32Icorewebview24ViewWebview210902PrereleaseAddDownloadstarting] 现已提升为稳定。
*   [现在，将 PinchZoom API][Webview2ReferenceWin32Icorewebview2setting5ViewWebview210902PrereleaseGetIspinchzoomenabled] 提升为稳定。
*   [AddFrameCreated][Webview2ReferenceWin32Icorewebview24ViewWebview210902PrereleaseAddFramecreated] 现已提升为稳定。
*   [AddHostObjectToScriptWithOrigins][AddHostObjectToScriptWithOriginsAPI] 通过 iFrame 元素支持将 API 提升为稳定。
*   [自动填充 API][Webview2ReferenceWin32Icorewebview2setting4ViewWebview210902PrereleaseGetIsgeneralautofillenabled] 现已提升为稳定。
    > [!NOTE]
    > 没有当前 API 可删除本地存储的常规自动填充和密码自动保存信息。  请提供用于删除数据的控件，这将涉及删除整个用户数据文件夹。 



### <a name="net"></a>.NET  
    
#### <a name="bug-fixes"></a>Bug 修复  

*   修复了 WebView2 WinForm 控件中释放父窗口后 WebView2 窗口可见性未正确更新的 Bug。 \ ([\#1282][GithubMicrosoftedgeWebviewfeedbackIssue1282] 和 [\#828][GithubMicrosoftedgeWebviewfeedbackIssue828]\) 。
*   修复了 WebView2 WPF 控件中的一个错误，即 WPF OneWay 绑定模式下的 Source 属性绑定无法正常工作。 \ ([\#619][GithubMicrosoftedgeWebviewfeedbackIssue619] 和 [\#608][GithubMicrosoftedgeWebviewfeedbackIssue608]\) 。

## <a name="1086435"></a>1.0.864.35

发布日期：2021 年 5 月 31 日  

[NuGet包][NuGetGallery1.0.864.35]\|要加载的最小运行时版本：86.0.616.0 或更高版本 \|完整 API 兼容性：91.0.864.35 或更高版本  

### <a name="general"></a>概要  

#### <a name="bug-fixes"></a>Bug 修复  

*   修复了在移动到较新的 Edge WebView2 运行时版本时可能导致主机应用进程崩溃的可靠性 Bug。
*   修复了在某些情况下阻止清除内存的 Bug。 此更改特定于运行时。
*   修复了项目找不到 WebView2.h 文件的 818 SDK 发布包中的错误。 \ ([\#1209][GithubMicrosoftedgeWebviewfeedbackIssue1209]\) 。 
*   修复了一个缺陷，该 Bug 导致对具有二进制主体的一些请求丢弃 WebResourceRequested 事件。
*   改进 NewWindowRequested 文档。 \ ([\#448][GithubMicrosoftedgeWebviewfeedbackIssue448]\) 。 

#### <a name="promotions"></a>促销
*   [UserAgent API][Webview2ReferenceWin32Icorewebview2setting2ViewWebview21086435GetUseragent] 现已稳定。
*   [AreBrowserkeysenabled][Webview2ReferenceWin32Icorewebview2setting2ViewWebview21086435GetArebrowseracceleratorkeysenabled] 现已稳定。

### <a name="net"></a>.NET  

#### <a name="bug-fixes"></a>Bug 修复  
*   修复了在 WebView2 .NET 控件中，在访问 CoreWebView2WebResourceRequest 头集合时缺少第一个标头的 bug。 \ ([\#1123][GithubMicrosoftedgeWebviewfeedbackIssue1123]\) 。 

## <a name="10865-prerelease"></a>1.0.865-prerelease  

发布日期：2021 年 4 月 26 日  

[NuGet包][NuGetGallery1.0.865-prerelease]\|要Microsoft Edge的最低版本：86.0.616.0 或更高版本 \|完整 API 兼容性：91.0.865.0 或更高版本  

### <a name="general"></a>概要  

#### <a name="experimental-features"></a>实验性功能  

*   添加了 [IsPinchZoomEnabled][Webview2ReferenceWin32Icorewebview2experimentalsettings4ViewWebview210865PrereleaseIspinchzoomenabled] 设置。 它允许你在设置中打开或关闭页面缩放缩放控件。  
*   添加了自定义 [add_DownloadStarting][Webview2ReferenceWin32Icorewebview2experimental2ViewWebview210865PrereleaseAddDownloadstarting] API。  它允许你阻止下载、保存到其他路径，并访问所需的元数据以生成自定义下载 UI。  
*   添加了 `iframe` [AddHostObjectToScriptWithOrigins 中的元素支持][Webview2ReferenceWin32Icorewebview2experimentalframeViewWebview210865PrereleaseAddhostobjecttoscriptwithorigins]。  
*   添加了 WPF 示例应用 [的示例代码][GithubMicrosoftedgeWebview2samplesWebview2wpfbrowser] ，以使用 API 关闭浏览器功能键。  
*   添加了 [UpdateRuntime][Webview2ReferenceWin32Icorewebview2experimentalenvironment3ViewWebview210865PrereleaseUpdateruntime] API，以轻松更新 WebView2 运行时。  
    
#### <a name="bug-fixes"></a>Bug 修复  

*   修复了 `Chromium DevTools Protocol` `POST` WebView2 中具有二进制数据的消息处理程序。  
*   关闭下载 `OpenSaveAsAwareness` UI，因为它包含指向 的链接 `edge://settings` 。  \ ([\#1120][GithubMicrosoftedgeWebviewfeedbackIssue1120]\) 。  
*   从屏幕共享对话框中删除了品牌。  \ ([\#940][GithubMicrosoftedgeWebviewfeedbackIssue940]\) 。  
*   修复了当 [SetWindowDisplayAffinity][WindowsWin32ApiWinuserSetWindowDisplayAffinity] 函数在 WebView2 应用中停止屏幕捕获时，它使 WebView2 成为错误。  \ ([\#841][GithubMicrosoftedgeWebviewfeedbackIssue841]\) 。
*   修复了将任何笔输入发送到 WebView2 时鼠标输入停止工作的合成托管 Bug。  
*   修复了在任何笔输入后使鼠标输入中断的 Bug。  此更改特定于运行时。  
    
### <a name="net"></a>.NET  

#### <a name="experimental-features"></a>实验性功能  

*   向 WPF 工具箱添加了 WebView2 设计器工具。  \ ([\#210][GithubMicrosoftedgeWebviewfeedbackIssue210]\) 。  
*   在 .NET Designer 模式下添加了 WebView2 UI 元素。  
    
#### <a name="bug-fixes"></a>Bug 修复  

*   改进了 COM 异常描述，将每个异常包装在更详细的 .NET 异常中。  \ ([\#338][GithubMicrosoftedgeWebviewfeedbackIssue338]\) 。  此更改特定于运行时。  
*   修复了在选择切换焦点时导致 WebView2 控件在 Microsoft Visual Studio `tab` 工具中崩溃Office。  \ ([\#589][GithubMicrosoftedgeWebviewfeedbackIssue589] 和 [\#933][GithubMicrosoftedgeWebviewfeedbackIssue933]\) 。  此更改特定于运行时。  
*   改进了 .NET framework 加载程序下层级别，更可靠。  \ ([\#946][GithubMicrosoftedgeWebviewfeedbackIssue946]\) 。
*   修复了在首次导航完成之前尝试刷新时导致崩溃的 Bug。  \ ([\#1011][GithubMicrosoftedgeWebviewfeedbackIssue1011]\) 。
*   修复了初始化，因此导航在 期间发生 `CoreWebView2InitializationCompleted` 。  \ ([\#1050][GithubMicrosoftedgeWebviewfeedbackIssue1050]\) 。
*   改进了 .NET 浏览器进程崩溃错误处理。  现在可以在未发生崩溃的情况下处理 `ProcessFailed` 事件后重新创建控件。  \ ([\#996][GithubMicrosoftedgeWebviewfeedbackIssue996]\) 。  
    
## <a name="1081841"></a>1.0.818.41  

发布日期：2021 年 4 月 21 日  

[NuGet包][NuGetGallery1.0.818.41]\|要加载的最小运行时版本：86.0.616.0 或更高版本 \|完整 API 兼容性：90.0.818.41 或更高版本  

### <a name="general"></a>概要  

#### <a name="features"></a>功能  

*   扩展 `ProcessFailed` 了事件。  它现在针对非呈现器子进程和帧呈现器引发。  
*   添加了 `iframe` 对 `AddScriptToExecuteOnDocumentCreated` 的元素支持。  
*   改进的 WebView2 代码可以更弹性地使用格式错误的版本信息 `.exe` 处理应用程序文件。  \ ([\#850][GithubMicrosoftedgeWebviewfeedbackIssue850]\) 。  
*   已从 `--winhttp-proxy-resolver` WebView 浏览器进程命令行中删除，为 WebView2 打开其他代理命令行选项。  
    
## <a name="10824-prerelease"></a>1.0.824-prerelease  

发布日期：2021 年 3 月 8 日  

[NuGet包][NuGetGallery1.0.824-prerelease]\|要Microsoft Edge的最低版本：86.0.616.0 或更高版本 \|完整 API 兼容性：91.0.824.0 或更高版本  

### <a name="general"></a>概要  

#### <a name="features"></a>功能  

*   扩展 `ProcessFailed` 了事件。  它现在针对非呈现器子进程和帧呈现器引发。  
*   添加了实验 [性 AreBrowserAcceleratorKeysEnabled][Webview2ReferenceWin32Icorewebview2experimentalsettingsViewWebview210824GetArebrowseracceleratorkeysenabled] 设置。  你可以阻止浏览器响应与导航、打印、保存和其他特定于浏览器的功能相关的键盘快捷方式。  
*   添加了 `iframe` 对 `AddScriptToExecuteOnDocumentCreated` 的元素支持。  
    
#### <a name="promotion"></a>促销  

*   [UserAgent][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddWebresourceresponsereceived] API 现已提升为稳定。  
*   Rasterization Scale API \ ([RasterizationScale][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetRasterizationscale] 属性  [、RasterizationScaleChanged][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseAddRasterizationscalechanged] 事件 [、BoundsMode 属性][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetBoundsmode]和 [ShouldDetectMonitorScaleChanges][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetShoulddetectmonitorscalechanges] 属性\) 现已提升为 Stable。  
    
#### <a name="bug-fixes"></a>Bug 修复  

*   扩展支持的 C++ 和 .NET 项目类型，如 MFC 和 ATL。  \ ([\#506][GithubMicrosoftedgeWebviewfeedbackIssue506] [、\#669][GithubMicrosoftedgeWebviewfeedbackIssue669]和 [\#851][GithubMicrosoftedgeWebviewfeedbackIssue851]\) 。  
*   修复了 Evergreen WebView2 运行时泄露入站防火墙条目的 Bug。  
*   修复了事件期间的响应 `WebResourceRequested` 设置。  \ ([\#568][GithubMicrosoftedgeWebviewfeedbackIssue568]\) 。  
*   修复了导航到导致 `edge://` 浏览器进程退出的 Bug。  \ ([\#604][GithubMicrosoftedgeWebviewfeedbackIssue604]\) 。  
*   修复了在可视托管模式下将 WebView2 限制到屏幕大小的 Bug。  
    
## <a name="1077444"></a>1.0.774.44  

发布日期：2021 年 3 月 8 日  

[NuGet包][NuGetGallery1.0.774.44]\|要加载的最小运行时版本：86.0.616.0 或更高版本 \|完整 API 兼容性：89.0.774.44 或更高版本  

### <a name="general"></a>概要  

#### <a name="features"></a>功能  

*   在 WebView2 中Microsoft Edge浏览器服务。  
*   可视化托管 API 现已普遍可用。  
    
#### <a name="promotions"></a>促销  

*   以下实验 API 现已提升为稳定。  
    *   [DPI 支持][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddWebresourceresponsereceived] 相关 API  
    *   可视托管 API  
    *   [SetVirtualHostNameToFolderMapping][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseSetvirtualhostnametofoldermapping]  
    *   [TrySuspend 和 Resume][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseTrysuspend]  
    *   [DefaultBackgroundColor][Webview2ReferenceWin32Icorewebview2controller2ViewWebview210790PrereleaseGetDefaultbackgroundcolor]  
        
#### <a name="bug-fixes"></a>Bug 修复  

*   修复了在可视托管模式下将 WebView2 限制到屏幕大小的 Bug。  
    
## <a name="10790-prerelease"></a>1.0.790-prerelease  

发布日期：2021 年 2 月 10 日  

[NuGet包][NuGetGallery1.0.790-prerelease]\|Microsoft Edge版本 86.0.616.0 或更高版本  

### <a name="general"></a>概要  

> [!IMPORTANT]
> **更改：WebView2**预发布包 1.0.781 已弃用。  停止使用程序包 1.0.781 进行开发。  

> [!IMPORTANT]
> WebView2 预发布包 0.9.430 已弃用，并且随下一版本一起删除。  如果你的 WebView 应用使用程序包，WebView 团队建议你移动到较新的程序包。  

#### <a name="features"></a>功能  

*   添加了 [TrySuspend 和 Resume][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseTrysuspend] 方法来挂起和恢复 WebViews。  
*   添加了 [SetVirtualHostNameToFolderMapping][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseSetvirtualhostnametofoldermapping] 方法，该方法将虚拟主机名映射到目录路径。  \ ([\#37][GithubMicrosoftedgeWebviewfeedbackIssue37] [、\#161][GithubMicrosoftedgeWebviewfeedbackIssue161]和 [\#212][GithubMicrosoftedgeWebviewfeedbackIssue212]\) 。  
*   添加了 [DefaultBackgroundColor][Webview2ReferenceWin32Icorewebview2controller2ViewWebview210790PrereleaseGetDefaultbackgroundcolor] 属性以设置背景的颜色和 alpha 通道。  \ ([\#414][GithubMicrosoftedgeWebviewfeedbackIssue414]\) 。  
*   添加了 [UserAgent][Webview2ReferenceWin32Icorewebview2experimentalsettingsViewWebview210790PrereleaseGetUseragent] 属性以获取或设置用户代理。  \ ([\#122][GithubMicrosoftedgeWebviewfeedbackIssue122]\) 。  
*   将 `CreateCookieWithCookie` 方法替换为 `CopyCookie` 方法。  
*   添加了使用 [ICoreWebView2CompositionController][Webview2ReferenceWin32Icorewebview2compositioncontrollerViewWebview210790Prerelease] 接口的可视托管支持，该接口是使用 中的 `CreateCoreWebView2CompositionController` 新方法创建的 `ICoreWebView2Environment3` 。  
    
#### <a name="bug-fixes"></a>Bug 修复  

*   在 WebView2 Microsoft Edge"购物"功能。  
*   在 为 时关闭 PDF 查看器中的上下文 `AreDefaultContextMenusEnabled` 菜单 `false` 。  \ ([\#605][GithubMicrosoftedgeWebviewfeedbackIssue605]\) 。  
*   修复了在查询 时 `E_NOINTERFACE` 返回的 `ICoreWebView2` `ICoreWebView2Experimental` Bug。  \ ([\#691][GithubMicrosoftedgeWebviewfeedbackIssue691]\) 。  
*   修复了将 设置为 时允许使用格式错误的 URI `CoreWebView2NavigationStartingEventArgs.Cancel` 进行导航的 `false` bug。  \ ([\#400][GithubMicrosoftedgeWebviewfeedbackIssue400]\) 。  
*   修复了在弹出窗口中阻止的 Bug，并 `window.print()` 附带事件 `NewWindowRequested` 的事件处理程序。  \ ([\#409][GithubMicrosoftedgeWebviewfeedbackIssue409]\) 。  
*   修复了在不同监视器之间移动应用时的动态 DPI 问题。  \ ([\#58][GithubMicrosoftedgeWebviewfeedbackIssue58]\)   
*   改进了 `HRESULT` [ICoreWebView2WebResourceResponseViewGetContentCompletedHandler：：Invoke][Webview2ReferenceWin32Icorewebview2webresourceresponseviewgetcontentcompletedhandlerViewWebview210790PrereleaseInvoke]传递的实例。  
*   关闭自动填充管理按钮。  \ ([\#585][GithubMicrosoftedgeWebviewfeedbackIssue585]\) 。  
*   修复Visual Studio窗口托管时运行时 `WebView2.Dispose` 崩溃的问题。  \ ([\#816][GithubMicrosoftedgeWebviewfeedbackIssue816]\) 和 [\#442][GithubMicrosoftedgeWebviewfeedbackIssue442]\) 。  
*   修复了在工具箱中显示 WebView2 Visual Studio Bug。  \ ([\#210][GithubMicrosoftedgeWebviewfeedbackIssue210]\) 。  
*   减少了高 CPU 使用率问题。  \ ([\#878][GithubMicrosoftedgeWebviewfeedbackIssue878]\) 。  
*   修复了已弃用 1.0.781-prerelease 程序包的问题。  \ ([\#875][GithubMicrosoftedgeWebviewfeedbackIssue875] 和 [\#878][GithubMicrosoftedgeWebviewfeedbackIssue878]\) 。  
    
#### <a name="promotions"></a>促销  

*   以下实验 API 现已提升为稳定。  
    *   可视托管 API  
    *   [SetVirtualHostNameToFolderMapping][Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseSetvirtualhostnametofoldermapping]  
        
### <a name="net"></a>.NET  

#### <a name="bug-fixes"></a>Bug 修复  

*   修复了使用 WPF SDK 的 WebView 应用崩溃的错误。  当你选择关闭窗口时 `F4` 发生崩溃。  \ ([\#399][GithubMicrosoftedgeWebviewfeedbackIssue399]\) 。  
*   WebView2 初始化屏幕现在是透明的，而不是灰色的。  \ ([\#196][GithubMicrosoftedgeWebviewfeedbackIssue196]\) 。  
    
## <a name="1070550"></a>1.0.705.50  

发布日期：2021 年 1 月 25 日  

[NuGet包][NuGetGallery1.0.705.50]\|WebView2 运行时版本 86.0.616.0 或更高版本  

### <a name="general"></a>概要  

#### <a name="promotions"></a>促销  

*   以下实验 API 现已提升为稳定。  
    *   [WebResourceResponseReceived API][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddWebresourceresponsereceived]  
    *   [NavigateWithWebResourceRequest API][Webview2ReferenceWin32Icorewebview2environment2ViewWebview210721PrereleaseCreatewebresourcerequest]  
    *   [Cookie 管理 API][Webview2ReferenceWin32Icorewebview2cookiemanagerViewWebview210721Prerelease]  
    *   [DOMContentLoaded API][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddDomcontentloaded]  
    *   [WebView Environment 属性][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseGetEnvironment]  
        
## <a name="10721-prerelease"></a>1.0.721-prerelease  

发布日期：2020 年 12 月 8 日  

[NuGet包][NuGetGallery1.0.721-prerelease]\|Microsoft Edge版本 86.0.616.0 或更高版本  

### <a name="general"></a>概要  

> [!IMPORTANT]
> **更改：** 已弃用 WebView2 预发行版程序包 1.0.707 和程序包 0.9.628。  停止使用程序包 1.0.707 和 package0.9.628 进行开发。  

#### <a name="features"></a>功能  

*   添加了 [WebView2 组策略][DeployedgeMicrosoftEdgeWebviewPolicies]。  有关建议做法的信息，请导航到 [WebView2 的组策略][Webview2ConceptsEnterpriseGroupPoliciesForWebview2]。  
*   > [!IMPORTANT]
    > **中断更改**：已弃用旧的注册表位置。  
    > 
    > ```text
    > {Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}
    > ```  
    
*   添加了对 WebView2 [中的][Webview2ReferenceWin32Icorewebview2experimentalcompositioncontroller3ViewWebview210721Prerelease] 拖放功能的支持。  
*   添加了 API 以处理 DPI 支持。  
    *   添加了 [RasterizationScale][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetRasterizationscale] 属性以更改 WebView 内容和 UI 弹出窗口以及关联的 [RasterizationScaleChanged 事件的][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseAddRasterizationscalechanged] DPI 比例。  
    *   添加了 [ShouldDetectMonitorScaleChanges][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetShoulddetectmonitorscalechanges] 属性以根据需要 `RasterizationScale` 自动更新属性。  
    *   添加了 [BoundsMode][Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetBoundsmode] 属性以指定边界为逻辑像素并允许 WebView 用于 `RasterizationScale` WebView2 像素显示，WebView 使用 和 获取 `RasterizationScale` `Bounds` 物理大小。  
*   更新 `NewWindowRequested` 了处理 和 `Ctrl` + `click` 的事件 `Shift` + `click` 。  \ ([\#168][GithubMicrosoftedgeWebviewfeedbackIssue168] 和 [\#371][GithubMicrosoftedgeWebviewfeedbackIssue371]\) 。  
*   以下实验 API 现已提升为稳定。  
    *   [WebResourceResponseReceived API][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddWebresourceresponsereceived]  
    *   [NavigateWithWebResourceRequest API][Webview2ReferenceWin32Icorewebview2environment2ViewWebview210721PrereleaseCreatewebresourcerequest]  
    *   [Cookie 管理 API][Webview2ReferenceWin32Icorewebview2cookiemanagerViewWebview210721Prerelease]  
    *   [DOMContentLoaded API][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddDomcontentloaded]  
    *   [WebView Environment 属性][Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseGetEnvironment]  
        
### <a name="net"></a>.NET  

#### <a name="features"></a>功能  

*   在 .NET Core 3.1+ 和 .NET 5 中打开 WinForms 设计器。  
*   改进了 .NET Cookie 管理。  \ ([\#611][GithubMicrosoftedgeWebviewfeedbackIssue611]\) 。  
*   替换为 `CoreWebView2Ready` [CoreWebView2InitializationCompleted][DotnetApiMicrosoftWebWebview2Corewebview2initializationcompletedeventargs]。  
    
#### <a name="bug-fixes"></a>Bug 修复

*   添加了 [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2WpfWebview2Acceleratorkeypressed] 事件以支持 `AcceleratorKey` 在 WebView2 中选择。  \ ([\#288][GithubMicrosoftedgeWebviewfeedbackIssue288]\) 。  
*   删除了输出到 WebView2 文件夹的不必要的文件。  \ ([\#461][GithubMicrosoftedgeWebviewfeedbackIssue461]\) 。  
*   改进了主机对象 API。  \ ([\#335][GithubMicrosoftedgeWebviewfeedbackIssue335] 和 [\#525][GithubMicrosoftedgeWebviewfeedbackIssue525]\) 。  
    
## <a name="1066437"></a>1.0.664.37  

发布日期：2020 年 11 月 20 日  

[NuGet包][NuGetGallery1.0.664.37]\|WebView2 运行时版本 86.0.616.0 或更高版本  

### <a name="general"></a>概要  

> [!IMPORTANT]
> **公告**：.NET WPF/WinForms WebView2 SDK 现已正式发布 \ (GA\) 。  从此版本开始，发布 SDK 是向前兼容的。  有关详细信息，请导航到 [GA 公告博客文章][MicrosoftDevblogDotnetAnnouncingGeneralAvailabilityForMicrosoftEdgeWebview2ForNetFixedDistributionMethod]。  

#### <a name="features"></a>功能  

*   .NET WPF/WinForms WebView2 现在是通用 \ (GA\) 。  
*   固定分发 \ (Bring-your-own\) 模式达到 GA。  
    
### <a name="net"></a>.NET  

#### <a name="bug-fixes"></a>Bug 修复  

*   `CoreWebView2NewWindowRequestedEventArgs.Handled` 阻止打开新窗口。  \ ([\#549][GithubMicrosoftedgeWebviewfeedbackIssue549] 和 [\#560][GithubMicrosoftedgeWebviewfeedbackIssue560]\) 。  
    
## <a name="10674-prerelease"></a>1.0.674-prerelease  

发布日期：2020 年 10 月 19 日  

[NuGet包][NuGetGallery1.0.674-prerelease]\|WebView2 运行时版本 86.0.616.0 或更高版本  

### <a name="general"></a>概要  

*   添加了 [NavigateWithWebResourceRequest][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseNavigatewithwebresourcerequest] 方法，可在导航期间提供 Post 数据或其他请求标头。  
*   添加了 [DOMContentLoaded][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseAddDomcontentloaded] 事件，该事件在加载和分析初始 HTML 文档时运行。  
*   在 WebView2 上添加了 [Environment][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseGetEnvironment] 属性。  此属性公开创建 WebView2 实例的 WebView2 环境。  
*   添加了 [Cookie 管理][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseGetCookiemanager] API，允许开发人员对 WebView2 会话进行身份验证，或从 WebView 检索 Cookie 以验证其他工具。  Webview 团队计划进行特定于语言或框架的改进。  有关详细信息，请导航到["API 审阅：Cookie 管理"。][GithubMicrosoftedgeWebview2AnnouncementIssue2]  
*   更新 [了 WebResourceResponseReceived][Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseAddWebresourceresponsereceived] 事件，并添加了不可变 [的 WebResourceResponseView][Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponseviewViewWebview210674Prerelease] 和 [WebResourceResponseReceivedEventArgs：:P opulateResponseContent][Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsViewWebview209628PrereleasePopulateresponsecontent] 到 [WebResourceResponseView：：GetContent][Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponseviewViewWebview210674PrereleaseGetcontent]。  
*   在 WebView2 [Microsoft Defender 应用程序防护 (WDAG) ][WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]关闭。  
*   添加了[用于可视化托管的 SystemCursorId。][Webview2ReferenceWin32Icorewebview2experimentalcompositioncontroller2ViewWebview210674PrereleaseGetSystemcursorid]  
*   为可视化托管中的输入方法添加了 bug 修复。  
*   删除了使用 `version.lib` WebView2 静态库时对 的 include 要求。  
    
### <a name="net"></a>.NET  

*   更新 [了 CoreWebView2][DotnetApiMicrosoftWebWebview2CoreCorewebview2] 类以公开 `CoreWebView2Environment` 变量。  
*   将命名空间中自定义 EventArgs 类的实现更改为 `Microsoft.Web.WebView2.Core` [System.EventArgs][DotnetApiSystemEventargs] 或 [System.ComponentModel.CancelEventArgs 的子类][DotnetApiSystemComponentmodelCancelEventargs]。  \ ([\#250][GithubMicrosoftedgeWebviewfeedbackIssue250]\)   
*   增加了对 [WinForms 中 CoreWebView2CreationProperties][DotnetApiMicrosoftWebWebview2Winforms] 的支持。  \ ([\#204][GithubMicrosoftedgeWebviewfeedbackIssue204]\) 。  
*   添加了 [WebResourceRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested] .NET API。  \ ([\#219][GithubMicrosoftedgeWebviewfeedbackIssue219]\) 。  
*   将 WinForms Designer [Source][DotnetApiMicrosoftWebWebview2WinformsWebview2Source] 属性更新为默认值或重置为 null。  \ ([\#177][GithubMicrosoftedgeWebviewfeedbackIssue177]\) 。  
*   更新了 WebView2 WebView2.Ini() ，以支持小于 100% 的 DPI 模式。  \ ([\#432][GithubMicrosoftedgeWebviewfeedbackIssue432]\) 。  
*   更新 [了 BuildWindowCore][DotnetApiMicrosoftWebWebview2WpfWebview2Buildwindowcore] 和 [DestroyWindowCore][DotnetApiMicrosoftWebWebview2WpfWebview2Destroywindowcore] 以提高稳定性。  \ ([\#382][GithubMicrosoftedgeWebviewfeedbackIssue382]\) 。  
*   更新了 .NET 加载程序基，以在进程位（而不是操作系统体系结构）上加载。  \ ([\#431][GithubMicrosoftedgeWebviewfeedbackIssue431]\) 。  
*   重命名 `EdgeNotFoundException` 为 [WebView2RuntimeNotFoundException][DotnetApiMicrosoftWebWebview2CoreWebview2runtimenotfoundexception]。  
    
## <a name="1062222"></a>1.0.622.22  

发布日期：2020 年 10 月 19 日  

[NuGet包][NuGetGallery1.0.622.22]\|WebView2 运行时版本 86.0.616.0 或更高版本  

### <a name="general"></a>概要  

> [!IMPORTANT]
> **公告**：Win32 C/C++ WebView2 现已正式发布 \ (GA\) 。  从此版本开始，发布 SDK 是向前兼容的。  有关详细信息，请导航到 [GA 公告博客文章][WindowsBlogsMsedgedevEdgeWebview2GeneralAvailability]。  

*   [Evergreen WebView2 运行时和安装程序][Webview2ConceptsDistributionUnderstandRuntimeInstaller] 是 GA。  Bootstrapper、 downlink link for the Bootstrapper， and Standalone Installer for the Evergreen WebView2 Runtime are available on [Microsoft Edge WebView2][MicrosoftDeveloperMicrosoftEdgeWebView2].  [WebView2Samples][GithubMicrosoftedgeWebview2samplesMain]存储库中也提供了安装工作流的示例代码。  
*   [固定版本模式][Webview2ConceptsDistributionFixedVersionDistributionMode] 适用于开发人员预览。  
    
## <a name="0962211"></a>0.9.622.11  

发布日期：2020 年 9 月 10 日  

[NuGet包][NuGetGallery0.9.622.11]\|WebView2 运行时版本 86.0.616.0 或更高版本  

### <a name="general"></a>概要  

*   > [!IMPORTANT]
    > **公告**：此 SDK 是 WebView2 Win32 C/C++ GA 的候选发布版。  GA 版本应该使用相同的 API 接口和功能。  
    
*   断开 [浏览器策略][DeployedgeMicrosoftEdgePolicies]。  
*   在 WebView2 环境选项上添加了 [AllowSingleSignOnUsingOSPrimaryAccount][Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209622GetAllowsinglesignonusingosprimaryaccount] 属性，以打开 WebView 的条件访问。  
*   进行了 `ICoreWebView2NewWindowRequestedEventArgs` 更新以包括 [WindowFeatures][Webview2ReferenceWin32Icorewebview2newwindowrequestedeventargsViewWebview209622GetWindowfeatures] 属性和关联的 [ICoreWebView2WindowFeatures][Webview2ReferenceWin32Icorewebview2windowfeaturesViewWebview209622]。  \ ([\#293][GithubMicrosoftedgeWebviewfeedbackIssue293]\) 。  
*   更新 `System.Windows.Rect`  为 `System.Drawing.Rectangle` 使用 ，而不是 `System.Windows.Rect` \ ([\#235][GithubMicrosoftedgeWebviewfeedbackIssue235]\) 。  
*   更新了 NewWindowRequested 事件以处理 `window.open()` 不带参数的请求。  \ ([\#293][GithubMicrosoftedgeWebviewfeedbackIssue293]\) 。  
*   [使用 指定的 AdditionalBrowserArguments][Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209622PutAdditionalbrowserarguments] `ICoreWebView2EnvironmentOptions` 不会替代环境变量或注册表值。  有关详细信息，请导航到 [CreateCoreWebView2EnvironmentWithOptions][Webview2ReferenceWin32Webview2IdlViewWebview209622Createcorewebview2environmentwithoptions]。  
    
## <a name="09579"></a>0.9.579  

发布日期：2020 年 7 月 20 日  

[NuGet包][NuGetGallery0.9.579]\|Microsoft Edge版本 86.0.579.0。  

### <a name="general"></a>概要  

*   > [!IMPORTANT]
    > **公告**：Evergreen WebView2 运行时和安装程序发布了预览版。  有关详细信息，请导航到分发 [WebView2][Webview2ConceptsDistributionUnderstandRuntimeInstaller]。  
    
*   > [!IMPORTANT]
    > **通知**：下一个 SDK 发布后，不再支持以下 WebView2 SDK 版本。  
    > 
    > *   [0.8.190](#08190)  
    > *   [0.8.230](#08230)  
    > *   [0.8.270](#08270)  
    > *   [0.8.314](#08314)  
    > *   [0.8.355](#08355)  
    > 
    > WebView2 SDK 版本在发布时也标记为 nuget.org。 WebView2 建议使用最新版本的 WebView2 保持最新。  
    
*   添加了 WebView 工作线程改进。  \ ([\#318][GithubMicrosoftedgeWebviewfeedbackIssue318]\) 。  
*   在 WebView 中关闭弹出窗口阻止程序。  有关详细信息，请导航到事件的 [IsUserInitiated][Webview2ReferenceWin32Icorewebview2newwindowrequestedeventargsViewWebview209538GetIsuserinitiated] `NewWindowRequested` 属性。  
*   确保为 运行 WebView 导航启动事件 `about:blank` 。  现在 `NavigationStarting` ，所有导航都运行事件，但不支持和忽略元素的 取消 `about:blank` `srcdoc` `iframe` 。  
*   在 `edge://` WebView 中阻止了某些 URI 方案。  
*   在 WebView2 环境选项上添加了实验性 [IsSingleSignOnUsingOSPrimaryAccountEnabled][Webview2ReferenceWin32Icorewebview2experimentalenvironmentoptionsViewWebview209538PrereleaseGetIssinglesignonusingosprimaryaccountenabled] 属性，以打开 WebView 的条件访问。  
*   添加了实验 [性 WebResourceResponseReceived][Webview2ReferenceWin32Icorewebview2experimentalViewWebview209538PrereleaseAddWebresourceresponsereceived] 事件，该事件在 WebView 接收并处理来自 WebResource 请求的响应之后运行。  响应对象中包含身份验证标头（如果有）。  
    
### <a name="net"></a>.NET  

*   改进了 WPF 焦点处理。  \ ([\#185][GithubMicrosoftedgeWebviewfeedbackIssue185]\) 。  
*   在 `ZoomFactor` WPF Webview2 控制器上添加了 属性。  
    
## <a name="09538"></a>0.9.538  

[NuGet包][NuGetGallery0.9.538]\|Microsoft Edge版本 85.0.538.0。  

### <a name="general"></a>概要  

*   放弃对 WebView2 SDK 版本 [0.8.149 的支持](#08149)。  WebView2 建议使用最新版本的 WebView2 保持最新。  
*   更新了组策略，以考虑何时修改 Microsoft Edge 浏览器的配置文件路径 (#179 [\) 。][GithubMicrosoftedgeWebviewfeedbackIssue179]  
    
### <a name="win32-cc"></a>Win32 C/C++  

*   添加了 [ICoreWebView2ExperimentalNewWindowRequestedEventArgs：：get_WindowFeatures][Webview2ReferenceWin32Icorewebview2experimentalnewwindowrequestedeventargsViewWebview209538PrereleaseGetWindowfeatures]，在运行并关联 `window.open()` [ICoreWebView2ExperimentalWindowFeatures][Webview2ReferenceWin32Icorewebview2experimentalwindowfeaturesViewWebview209538Prerelease] \ ([#70][GithubMicrosoftedgeWebviewfeedbackIssue70]\) 时触发。  
*   > [!IMPORTANT]
    > **中断更改**：弃用 [CreateCoreWebView2EnvironmentWithDetails，][Webview2ReferenceWin32Webview2IdlViewWebview209488Createcorewebview2environmentwithdetails] 并替换为 [CreateCoreWebView2EnvironmentWithOptions][Webview2ReferenceWin32Webview2IdlViewWebview209538Createcorewebview2environmentwithoptions]。  
    
*   > [!IMPORTANT]
    > **更改：** 为了确保 WebView2 API 符合 Windows API 命名约定，WebView 团队更新了以下名称。  
    > 
    > *   [AreRemoteObjectsAllowed][Webview2ReferenceWin32Icorewebview2settingsViewWebview209488GetAreremoteobjectsallowed] 现在是 [AreHostObjectsAllowed][Webview2ReferenceWin32Icorewebview2settingsViewWebview209538GetArehostobjectsallowed]。  
    
*   更新 [了 AddHostObjectToScript][Webview2ReferenceWin32Icorewebview2ViewWebview209538ddhostobjecttoscript]。  原来的主机对象序列化器标记现在设置为代理对象。  然后，当作为 JavaScript 回调 \ (#148 \) 中的参数传递时，主机 [对象序列化][GithubMicrosoftedgeWebviewfeedbackIssue148]标记将序列化回主机对象。  
    
### <a name="net-09538-pre-release"></a>.NET (0.9.538 预发行)   

*   发布的 WinForms 和 WPF WebView2API 示例是 WebView2 SDK 的全面指南。  有关详细信息，请导航到["示例""存储库"。][GithubMicrosoftedgeWebview2samplesMain]  
*   添加了对可视托管和窗口功能实验 [API 的支持][Webview2ConceptsVersioningExperimentalApis]。  
*   > [!IMPORTANT]
    > **中断更改**：以下延迟现在实现 IDisposable：ScriptDialogOpening、NewWindowRequested、WebResourceRequested 和[PermissionRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Permissionrequested]。 [][DotnetApiMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening] [][DotnetApiMicrosoftWebWebview2CoreCorewebview2Newwindowrequested] [][DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]  
    
*   添加了 [GetAvailableBrowserVersionString 和][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring] [CompareBrowserVersions][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions] 作为 [CoreWebView2Environment][DotnetApiMicrosoftWebWebview2CoreCorewebview2environment] 静态。  
    
## <a name="09515-prerelease"></a>0.9.515-prerelease  

[NuGet包][NuGetGallery0.9.515-prerelease]\|Microsoft Edge版本 84.0.515.0。  

*   > [!IMPORTANT]
    > **公告**：WebView2 现在支持 .NET Framework 4.6.2 或更高版本上的 Windows Forms 和 WPF，以及预发布包中的 .NET Core 3.0 或**更高版本。**  
    
*   有关生成 WPF 应用的信息，请导航到[WPF][Webview2GetStartedWpf]入门指南和适用于 WPF 特定 API 的 WebView2 [WPF][DotnetApiMicrosoftWebWebview2Wpf]参考。  
*   有关生成 Windows Forms 应用的信息，请导航到[Windows Forms 入门 Guide][Webview2GetStartedWinforms]和 WebView2 Windows [Forms Reference][DotnetApiMicrosoftWebWebview2Winforms] for Windows Forms specific APIs。  
*   有关 CoreWebView2 API 详细信息，请导航到 [.NET 参考][DotnetApiMicrosoftWebWebview2Core]。  
*   > [!CAUTION]
    > **已知问题**：WebView 团队已注意到预发行版中在将来版本中要解决的一些问题。  
    > 
    > *   **DPI 感知**：WebView2 for WPF 当前无法感知 DPI。  在高 DPI 监视器上初始化 WebView2 时，存在一个已知问题，即 WebView 最初初始化为窗口的一小部分，直到调整窗口大小。  
    > *   **WPF 设计器**：当前不支持 WPF 设计器。  在文本编辑器中直接修改相应的 XAML，在应用中添加 WebView2 控件。  
    
## <a name="09488"></a>0.9.488  

[NuGet包][NuGetGallery0.9.488]\|Microsoft Edge版本 84.0.488.0。  

*   > [!IMPORTANT]
    > **公告**：从即将发布的 Microsoft Edge版本 83 开始，Evergreen WebView 不再面向稳定浏览器渠道。  相反，它面向另一组二进制文件（品牌为 [Evergreen WebView2 Runtime）（][Webview2ConceptsDistributionEvergreenDistributionMode]你可能通过 WebView 团队当前正在开发的安装程序进行链接安装）。  有关详细信息，请导航到["应用分发"。][Webview2ConceptsDistribution]  
    
*   > [!IMPORTANT]
    > **通知**：今后，WebView 团队会发布两个程序包：一个包含实验性 API \ (的预发布程序包，让你试用\) 以及一个稳定 API \ (用于你的 confidence\) 的稳定发布包。  若要了解差异，请导航到了解[浏览器版本和 WebView2。][Webview2ConceptsVersioning]  
    
*   > [!IMPORTANT]
    > **更改：** 为了确保 WebView2 API 符合 Windows API 命名约定，WebView 团队更新了以下接口的名称。  
    > 
    > *   `CORE_WEBVIEW2_*` 前缀现在 `COREWEBVIEW2_*` 为 。  
    > *   [GetCoreWebView2BrowserVersionInfo][Webview2ReferenceWin32Webview2IdlViewWebview209430Getcorewebview2browserversioninfo] 现在是 [GetAvailableCoreWebView2BrowserVersionString][Webview2ReferenceWin32Webview2IdlViewWebview209488Getavailablecorewebview2browserversionstring]。  
    > *   [get_BrowserVersionInfo][Webview2ReferenceWin32Icorewebview2environmentViewWebview209430GetBrowserversioninfo][现已][Webview2ReferenceWin32Icorewebview2environmentViewWebview209488GetBrowserversionstring]get_BrowserVersionString。  
    > *   [AddRemoteObject][Webview2ReferenceWin32Icorewebview2ViewWebview209430Addremoteobject] 现在是 [AddHostObjectToScript][Webview2ReferenceWin32Icorewebview2ViewWebview209488Addhostobjecttoscript]。  
    > *   [RemoveRemoteObject][Webview2ReferenceWin32Icorewebview2ViewWebview209430Removeremoteobject] 现在是 [RemoveHostObjectFromScript][Webview2ReferenceWin32Icorewebview2ViewWebview209488Removehostobjectfromscript]。  
    > *   `chrome.webview.remoteObjects` 现在是 `chrome.webview.hostObjects` 。  
    
*   > [!IMPORTANT]
    > **中断更改** `AddRemoteObject` ：JS 代理方法也重命名。  
    > 
    > *   `getLocal` 现在是 `getLocalProperty` 。  
    > *   `setLocal` 现在是 `setLocalProperty` 。  
    > *   `getRemote` 现在是 `getHostProperty` 。  
    > *   `setRemote` 现在是 `setHostProperty` 。  
    > *   `applyRemote` 现在是 `applyHostFunction` 。  
    
*   > [!IMPORTANT]
    > **中断更改**：弃用 [CreateCoreWebView2EnvironmentWithDetails，][Webview2ReferenceWin32Webview2IdlViewWebview209488Createcorewebview2environmentwithdetails] 并替换为 [CreateCoreWebView2EnvironmentWithOptions][Webview2ReferenceWin32Webview2IdlViewWebview209488Createcorewebview2environmentwithoptions]。  
    
*   添加了 [FrameNavigationCompleted][Webview2ReferenceWin32Icorewebview2ViewWebview209488AddFramenavigationcompleted] 事件。  现在，当元素完成导航时，将运行一个事件并返回导航 `iframe` 和导航 ID 的成功。  
*   添加了 [ICoreWebView2EnvironmentOptions][Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209488] 接口，可用于确定应用面向的 Evergreen WebView2 运行时的版本。  
*   添加了 [IsBuiltInErrorPageEnabled][Webview2ReferenceWin32Icorewebview2settingsViewWebview209488GetIsbuiltinerrorpageenabled] 设置。  现在，您可以选择针对导航失败打开或关闭内置错误网页，并呈现进程失败。  
*   更新了远程对象注入以支持 .NET `IDispatch` 实现 \ ([#113][GithubMicrosoftedgeWebviewfeedbackIssue113]\) 。  
*   更新 [了 NewWindowRequested][Webview2ReferenceWin32Icorewebview2ViewWebview209488AddNewwindowrequested] 事件以处理来自上下文菜单 \ (#108 [\) ][GithubMicrosoftedgeWebviewfeedbackIssue108]的请求。  
*   发布了第一个单独的 WebView2 预发布包，你可以在这里访问可视托管 API。  WebView 团队更新 [了 APISample][GithubMicrosoftedgeWebview2samplesMain] 以包含新的实验性 API。  
    *   添加了 [ICoreWebView2ExperimentalCompositionController][Webview2ReferenceWin32Icorewebview2experimentalcompositioncontrollerViewWebview209488Prerelease] 接口，以连接到合成树并为 WebView 提供输入。  
    *   添加了 [ICoreWebView2ExperimentalPointerInfo][Webview2ReferenceWin32Icorewebview2experimentalpointerinfoViewWebview209488Prerelease]，其中包含 来自 的所有信息 `POINTER_INFO` 。  此对象传递到 SendPointerInput 以将指针输入注入 WebView。  
    *   添加了 [ICoreWebView2ExperimentalCursorChangedEventHandler][Webview2ReferenceWin32Icorewebview2experimentalcursorchangedeventhandlerViewWebview209488Prerelease]，告知应用何时应更改 WebView 上的鼠标光标。  当鼠标悬停在 WebView 中的文本框上时，光标会从箭头变为选择器。  `cursor`上的 属性 `CompositionController` 告知应用鼠标光标当前应适用于 WebView 的内容。  
        
## <a name="09430"></a>0.9.430  

[NuGet包][NuGetGallery0.9.430]\|Microsoft Edge版本 82.0.430.0。  

WebView2 SDK 是官方 Win32 C++ Beta 版本，它包含了来自反馈的多项功能请求。  WebView 团队尝试通过发生重大变化来限制发布数量。  作为一般可用性方法，Beta 版本中将包含一些重大重大更改。  

*   > [!IMPORTANT]
    > **更改：** 在最终版本接近最终发布时，WebView 团队将前缀重命名为 ，以确保 WebView2 API 符合 Windows `IWebView2WebView` `ICoreWebView2` API 命名约定。  此外，为了从 UI 框架利用 WebView2 SDK，WebView 团队分为 `ICoreWebView2` [ICoreWebView2][Webview2ReferenceWin32Icorewebview2ViewWebview209430] 和 [ICoreWebView2Host][Webview2ReferenceWin32Icorewebview2hostViewWebview209430]。  `ICoreWebView2Host` 支持调整大小、显示和隐藏、对焦以及与窗口和合成相关的其他功能。  ICoreWebView2 支持所有其他 WebView2 功能。  若要了解有关合并更改的信息，请导航到 [WebView2][GithubMicrosoftedgeWebview2samplesPr17] [APISample][GithubMicrosoftedgeWebview2samplesMain] 项目中的 WebView2 拉取请求。  
    
*   > [!IMPORTANT]
    > **重大更改**：将[DocumentStateChanged][Webview2ReferenceWin32Iwebview2webviewViewWebview208355AddDocumentstatechanged]拆分为三个组件[：SourceChanged、ContentLoading][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddSourcechanged]和[HistoryChanged][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddHistorychanged]。 [][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddContentloading]  现在，当源 URL 更改时 `SourceChanged` ，将运行事件。  当历史记录状态更改时 `HistoryChanged` ，将运行事件。  加载 `ContentLoading` 新文档时，该事件在初始脚本之前运行。  
    
*   添加了对 ARM64 体系结构的支持。  
*   添加了对触摸屏设备的软 (\) SIP\支持。  
*   增加了对 Windows Server 2008 R2、Windows Server 2012、Windows Server 2012 R2 和 Windows Server 2016 的支持。  
*   添加了 [NotifyParentWindowPositionChanged，][Webview2ReferenceWin32Icorewebview2hostViewWebview209430Notifyparentwindowpositionchanged] 使状态栏在窗口模式下跟随窗口。  此外，在无窗口模式下实现更改，以便辅助功能正常工作。  
*   添加了 [AreRemoteObjectsAllowed][Webview2ReferenceWin32Icorewebview2settingsViewWebview209430GetAreremoteobjectsallowed] 设置以全局控制是否任何远程对象可以访问网页。  默认情况下，启用 ，因此 `AreRemoteObjectsAllowed` [AddRemoteObject][Webview2ReferenceWin32Icorewebview2ViewWebview209430Addremoteobject] 添加的远程对象可从网页访问。  关闭 `AreRemoteObjectsAllowed` 后，无法从网页访问对象。  更改将应用于下一个导航事件。  
*   添加了[IsZoomControlEnabled][Webview2ReferenceWin32Icorewebview2settingsViewWebview209430GetIszoomcontrolenabled]设置，以防止用户使用 和 \ (或 + 鼠标滚轮\) 影响 WebView `ctrl` + `+` `ctrl` + `-` `ctrl` 的缩放。  当关闭该设置时 [，put_ZoomFactor][Webview2ReferenceWin32Icorewebview2hostViewWebview209430PutZoomfactor] 设置缩放。  
*   将 ZoomFactor 更改为仅应用于当前 WebView。  对当前 WebView 的缩放更改不会影响使用同一源网站导航到的其他 WebView。  有关详细信息，请导航到["get_ZoomFactor"。][Webview2ReferenceWin32Icorewebview2hostViewWebview209430GetZoomfactor]  
*   适用于 WebView 的 Hid ZoomView UI \ ([#95][GithubMicrosoftedgeWebviewfeedbackIssue95]\) 。  
*   添加了 [SetBoundsAndZoomFactor][Webview2ReferenceWin32Icorewebview2hostViewWebview209430Setboundsandzoomfactor]。  现在，你可以同时设置 WebView 的缩放系数和边界。  
*   添加了 [WindowCloseRequested][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddWindowcloserequested] 事件。  有关详细信息，请导航到 [add_WindowCloseRequested][Webview2ReferenceWin32Icorewebview2ViewWebview209430AddWindowcloserequested] \ ([#119][GithubMicrosoftedgeWebviewfeedbackIssue119]\) 。  
*   添加了对 `beforeunload` JavaScript 对话框事件对话框类型的支持，并添加了[][Webview2ReferenceWin32Icorewebview2ViewWebview209430CoreWebview2ScriptDialogKind]CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD枚举条目。  
*   向 HttpRequestHeaders 添加了 [GetHeaders，][Webview2ReferenceWin32Icorewebview2httprequestheadersViewWebview209430Getheaders] 将 [GetHeader][Webview2ReferenceWin32Icorewebview2httpresponseheadersViewWebview209430Getheader] 添加到 HttpResponseHeaders，将 get_HasCurrentHeader [属性添加到][Webview2ReferenceWin32Icorewebview2httpheaderscollectioniteratorViewWebview209430GetHascurrentheader] HttpHeadersCollectionIterator。  
*   > [!IMPORTANT]
    > **中断更改**：已修改 `DevToolsProtocolEventReceived` 的行为。  现在，你可以为特定的[DevTools 协议事件创建 DevToolsProtocolEventReceiver，][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430]然后使用 add_DevToolsProtocolEventReceived remove_DevToolsProtocolEventReceived[][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430AddDevtoolsprotocoleventreceived]订阅/ / [取消订阅此类事件][Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430RemoveDevtoolsprotocoleventreceived]。  
    
*   > [!IMPORTANT]
    > **Breaking Change**： Changed `WebMessageReceivedEventArgs` [get_WebMessageAsString][Webview2ReferenceWin32Iwebview2webmessagereceivedeventargsViewWebview208355GetWebmessageasstring] property to a [TryGetWebMessageAsString][Webview2ReferenceWin32Icorewebview2webmessagereceivedeventargsViewWebview209430Trygetwebmessageasstring] method.  
    
*   > [!IMPORTANT]
    > **Breaking Change**： Changed `AcceleratorKeyPressedEventArgs` [Handle][Webview2ReferenceWin32Iwebview2acceleratorkeypressedeventargsViewWebview208355Handle] method to a [get_Handled][Webview2ReferenceWin32Icorewebview2acceleratorkeypressedeventargsViewWebview209430GetHandled] property.  
    
## <a name="08355"></a>0.8.355  

[NuGet包][NuGetGallery0.8.355]\|Microsoft Edge版本 80.0.355.0。  

*   发布的 WebView2API 示例，WebView2 SDK 的全面指南。  有关详细信息，请导航到["API 示例"。][GithubMicrosoftedgeWebview2samplesApisample]  
*   添加了对英语 \ (#30 \) [之外][GithubMicrosoftedgeWebviewfeedbackIssue30]的所有语言的 IME 支持。  
*   更新了事件的 API `WebResourceRequested` 图面以响应 Bug 报告。  现在，已弃用创建时同时指定筛选器和事件。  若要创建 Web 资源请求的事件，add_WebResourceRequested[][Webview2ReferenceWin32Iwebview2webview5ViewWebview208355AddWebresourcerequested]添加事件，使用[AddWebResourceRequestedFilter][Webview2ReferenceWin32Iwebview2webview5ViewWebview208355Addwebresourcerequestedfilter]添加筛选器。  [RemoveWebResourceRequestedFilter][Webview2ReferenceWin32Iwebview2webview5ViewWebview208355Removewebresourcerequestedfilter]将删除 \ (#36 [\) ][GithubMicrosoftedgeWebviewfeedbackIssue36]\ (#74 [\) 。][GithubMicrosoftedgeWebviewfeedbackIssue74]  
*   > [!IMPORTANT]
    > **中断更改**：已修改全屏行为。  已弃用 [IsFullScreenAllowed][Webview2ReferenceWin32Iwebview2settingsViewWebview208355GetIsfullscreenallowedDeprecated]。  现在，默认情况下，如果 WebView \ (（如 video\) ）中的元素设置为全屏，它将填充 WebView 边界。  使用[ContainsFullScreenElementChanged][Webview2ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandlerViewWebview208355]事件[][Webview2ReferenceWin32Iwebview2webview5ViewWebview208355GetContainsfullscreenelement]和 get_ContainsFullScreenElement 指定当元素要进入全屏模式时应用应如何调整 WebView 的大小。  
    
## <a name="08314"></a>0.8.314  

[NuGet包][NuGetGallery0.8.314]\|Microsoft Edge版本 80.0.314.0。  

*   增加了对 Windows 7、Windows 8 和 Windows 8.1 的支持。  
*   添加了 Visual Studio 和 Visual Studio Code 对 WebView2 的调试支持。  现在，从 IDE 在 WebView2 中调试脚本。  有关详细信息，请导航到 [如何使用 WebView2 控件进行开发时进行调试][Webview2HowToDebug]。  
*   为 WebView2 中正在运行的脚本添加了 ，用于从应用的 Win32 组件访问 IDispatch 对象并访问 `Native Object Injection` IDispatch 对象的属性。  有关详细信息，请导航到 [AddRemoteObject][Webview2ReferenceWin32Iwebview2webview4ViewWebview208355Addremoteobject] \ ([#17][GithubMicrosoftedgeWebviewfeedbackIssue17]\) 。  
*   添加了 `AcceleratorKeyPressed` event。  有关详细信息，请导航到 [add_AcceleratorKeyPressed][Webview2ReferenceWin32Iwebview2webview4ViewWebview208355AddAcceleratorkeypressed] \ ([#57][GithubMicrosoftedgeWebviewfeedbackIssue57]\) 。  
*   已关闭 `Context Menus` 。  有关详细信息，请导航到 [\put_AreDefaultContextMenusEnabled][Webview2ReferenceWin32Iwebview2settings2ViewWebview208355PutAredefaultcontextmenusenabled] \ ([#57][GithubMicrosoftedgeWebviewfeedbackIssue57]\) 。  
*   已 `DPI Awareness` 更新 。  现在，WebView 的 DPI 感知与主机应用的 DPI 感知相同。  
    
    > [!NOTE]
    > 如果启动另一个混合应用时 DPI 感知不同于原始 WebView，则新 WebView 不会启动（如果 `user data folder` 相同 \ ([][GithubMicrosoftedgeWebviewfeedbackIssue1]#1 \) ）。  
    
*   进行了更新，以便 WebView2 自动拒绝 WebView 中托管的 Web 内容所提示的通知 `Notification Change Behavior` 权限请求。  
    
## <a name="08270"></a>0.8.270  

[NuGet包][NuGetGallery0.8.270]\|Microsoft Edge 78.0.270.0 版。  

*   添加了 `DocumentTitleChanged` 事件以指示文档标题更改 \ ([\#27][GithubMicrosoftedgeWebviewfeedbackIssue27]\) 。  
*   添加了 `GetWebView2BrowserVersionInfo` API \ ([\#18][GithubMicrosoftedgeWebviewfeedbackIssue18]\) 。  
*   添加了 `NewWindowRequested` event。  
*   更新 `CreateWebView2EnvironmentWithDetails` 了 函数以删除 `releaseChannelPreference` 。  有关 函数详细信息 `CreateWebView2EnvironmentWithDetails` ，请导航到 [CreateWebView2EnvironmentWithDetails][Webview2ReferenceWin32Webview2IdlViewWebview208355Createwebview2environmentwithdetails]。  仍然支持注册表和环境变量替代。  除非重写，否则使用默认通道首选项。  
    在频道搜索期间，WebView 团队将跳过任何与 WebView2 SDK 不兼容的以前频道版本。  
    WebView 团队选择更稳定的渠道，以确保最终用户的行为最一致。  使用最新的 Canary 版本进行测试时，应在启动应用之前创建一个脚本，将环境变量 `WEBVIEW2_RELEASE_CHANNEL_PREFERENCE` `1` 设置为 。  
*   使用 `CreateWebView2EnvironmentWithDetails` 逻辑更新了函数，以选择 `userDataFolder` 未指定时。  有关 函数详细信息 `CreateWebView2EnvironmentWithDetails` ，请导航到 [CreateWebView2EnvironmentWithDetails][Webview2ReferenceWin32Webview2IdlViewWebview208355Createwebview2environmentwithdetails]。  如果您之前使用默认位置，则切换到新 SDK 时，默认设置为 `userDataFolder` `userDataFolder` reset \ (set to a new location in the host code directory\) and your state is also reset.  如果主机进程无权写入指定目录， `CreateWebView2EnvironmentWithDetails` 则函数可能会失败。  你可以将数据从旧目录复制到 `user data folder` 新目录。  
    
## <a name="08230"></a>0.8.230  

[NuGet包][NuGetGallery0.8.230]\|Microsoft Edge 77.0.230.0 版。  

*   添加了 `Stop` API 以停止所有导航和挂起的资源提取 \ ([\#28][GithubMicrosoftedgeWebviewfeedbackIssue28]\) 。  
*   向 `.tlb` 文件包 \NuGet \ ([\#22 \) ][GithubMicrosoftedgeWebviewfeedbackIssue22]添加了文件。  
*   向程序包 \NuGet \ ([\#32 \) ][GithubMicrosoftedgeWebviewfeedbackIssue32]中的安装程序列表添加了 .NET 项目。  
    
## <a name="08190"></a>0.8.190  

[NuGet包][NuGetGallery0.8.190]\|Microsoft Edge版本 77.0.190.0。  

*   已 `get_AreDevToolsEnabled` / `put_AreDevToolsEnabled` 添加到控制用户能否打开 DevTools \ ([\#16][GithubMicrosoftedgeWebviewfeedbackIssue16]\) 。  
*   已 `get_IsStatusBarEnabled` / `put_IsStatusBarEnabled` 添加到控制状态栏是否显示 \ ([\#19][GithubMicrosoftedgeWebviewfeedbackIssue19]\) 。  
*   已 `get_CanGoBack` / `GoBack` / `get_CanGoForward` / `GoForward` 添加用于返回和向前浏览导航历史记录。  
*   添加了 HTTP 标头类型 \ (\) 以在 WebView 中查看 `IWebView2HttpHeadersCollectionIterator` / `IWebView2HttpRequestHeaders` / `IWebView2HttpRequestHeaders` 和修改 HTTP 标头。  
*   在 64 位计算机 \ ([\#13 \) ][GithubMicrosoftedgeWebviewfeedbackIssue13]上添加了 32 位 WebView 支持。  
*   向 SDK \ ([\#14 \) ][GithubMicrosoftedgeWebviewfeedbackIssue14]添加了 WebView IDL。  
*   添加了 lib 以支持 `IID\_\*` 接口 ID 对象 \ ([\#12][GithubMicrosoftedgeWebviewfeedbackIssue12]\) 。  
*   在 SDK 中添加了 DLL 文件的路径、链接和自动NuGet `TARGET` 文件。  
*   在脚本中打开 `window.open()` 请求。  
    
## <a name="08149"></a>0.8.149  

[NuGet包][NuGetGallery0.8.149]\|Microsoft Edge 76.0.149.0 版。  

初始开发人员预览版本。  

<!-- Links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "使用 WebView2 应用程序分发|Microsoft Docs"  
[Webview2ConceptsDistributionEvergreenDistributionMode]: ./concepts/distribution.md#evergreen-distribution-mode "常青分发模式 - 使用 WebView2 分发|Microsoft Docs"  
[Webview2ConceptsDistributionFixedVersionDistributionMode]: ./concepts/distribution.md#fixed-version-distribution-mode "固定版本分发模式 - 使用 WebView2 分发|Microsoft Docs"  
[Webview2ConceptsDistributionUnderstandRuntimeInstaller]: ./concepts/distribution.md#understanding-the-webview2-runtime "了解 WebView2 运行时和安装程序 - 使用 WebView2 组件分发|Microsoft Docs"  
[Webview2ConceptsEnterpriseGroupPoliciesForWebview2]: ./concepts/enterprise.md#group-policies-for-webview2 "WebView2 的组策略 - 管理 WebView2 |Microsoft Docs"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "了解浏览器版本和 WebView2 |Microsoft Docs"  
[Webview2ConceptsVersioningExperimentalApis]: ./concepts/versioning.md#experimental-apis "实验性 API - 了解浏览器版本和 WebView2 |Microsoft Docs"  
[Webview2ConceptsVersioningMatchingWebview2RuntimeVersions]: ./concepts/versioning.md#matching-webview2-runtime-versions "匹配 WebView2 运行时版本 - 了解 WebView2 SDK |Microsoft Docs"  
[Webview2GetStartedWinforms]: ./get-started/winforms.md "Windows Forms 应用中的 WebView2 |Microsoft Docs"  
[Webview2GetStartedWpf]: ./get-started/wpf.md "WPF | 中的 WebView2 入门Microsoft Docs"  
[Webview2HowToDebug]: ./how-to/debug.md "如何使用 WebView2 控件进行开发时|Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview2experimental2ViewWebview210865PrereleaseAddDownloadstarting]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental2?view=webview2-1.0.865-prerelease&preserve-view=true#add_downloadstarting  "add_DownloadStarting - 接口 ICoreWebView2Experimental2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalenvironment3ViewWebview210865PrereleaseUpdateruntime]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironment3?view=webview2-1.0.865-prerelease&preserve-view=true#updateruntime  "UpdateRuntime - 接口 ICoreWebView2ExperimentalEnvironment3 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalframeViewWebview210865PrereleaseAddhostobjecttoscriptwithorigins]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalframe?view=webview2-1.0.865-prerelease&preserve-view=true#addhostobjecttoscriptwithorigins  "AddHostObjectToScriptWithOrigins - 接口 ICoreWebView2ExperimentalFrame |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalsettings4ViewWebview210865PrereleaseIspinchzoomenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalsettings4?view=webview2-1.0.865-prerelease&preserve-view=true#ispinchzoomenabled  "IsPinchZoomEnabled - 接口 ICoreWebView2ExperimentalSettings4 |Microsoft Docs" 

[Webview2ReferenceWin32Icorewebview2experimentalsettingsViewWebview210824GetArebrowseracceleratorkeysenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalsettings2?view=webview2-1.0.824&preserve-view=true#get_arebrowseracceleratorkeysenabled "get_AreBrowserAcceleratorKeyPressed - 接口 ICoreWebView2ExperimentalSettings |Microsoft Docs" 

[Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddDomcontentloaded]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease&preserve-view=true#add_domcontentloaded "add_DOMContentLoaded - 接口ICoreWebView2_2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseAddWebresourceresponsereceived]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived - 接口 ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview22ViewWebview210721PrereleaseGetEnvironment]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease&preserve-view=true#get_environment "ICoreWebView2CookieManager |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseSetvirtualhostnametofoldermapping]: /microsoft-edge/webview2/reference/win32/icorewebview2_3?view=webview2-1.0.790-prerelease&preserve-view=true#setvirtualhostnametofoldermapping "SetVirtualHostNameToFolderMapping - 接口ICoreWebView2_3 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview23ViewWebview210790PrereleaseTrysuspend]: /microsoft-edge/webview2/reference/win32/icorewebview2_3?view=webview2-1.0.790-prerelease&preserve-view=true#trysuspend "TrySuspend - 接口ICoreWebview2_3 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2acceleratorkeypressedeventargsViewWebview209430GetHandled]: /microsoft-edge/webview2/reference/win32/icorewebview2acceleratorkeypressedeventargs?view=webview2-0.9.430&preserve-view=true#get_handled "get_Handled - 接口 ICoreWebView2AcceleratorKeyPressedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2compositioncontrollerViewWebview210790Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2compositioncontroller?view=webview2-1.0.790-prerelease&preserve-view=true "interface ICoreWebView2CompositionController |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2controller2ViewWebview210790PrereleaseGetDefaultbackgroundcolor]: /microsoft-edge/webview2/reference/win32/icorewebview2controller2?view=webview2-1.0.790-prerelease&preserve-view=true#get_defaultbackgroundcolor "get_DefaultBackgroundColor - 接口 ICoreWebView2Controller2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2cookiemanagerViewWebview210721Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2cookiemanager?view=webview2-1.0.721-prerelease&preserve-view=true "ICoreWebView2CookieManager |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430AddDevtoolsprotocoleventreceived]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#add_devtoolsprotocoleventreceived "add_DevToolsProtocolEventReceived - 接口 ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverViewWebview209430RemoveDevtoolsprotocoleventreceived]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#remove_devtoolsprotocoleventreceived "remove_DevToolsProtocolEventReceived - 接口 ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2environment2ViewWebview210721PrereleaseCreatewebresourcerequest]: /microsoft-edge/webview2/reference/win32/icorewebview2environment2?view=webview2-1.0.721-prerelease&preserve-view=true#createwebresourcerequest "CreateWebResourceRequest - 接口 ICoreWebView2Environment |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209488]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.488&preserve-view=true "interface ICoreWebView2EnvironmentOptions |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209622GetAllowsinglesignonusingosprimaryaccount]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#get_allowsinglesignonusingosprimaryaccount "get_AllowSingleSignOnUsingOSPrimaryAccount - 接口 ICoreWebView2EnvironmentOptions |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2environmentoptionsViewWebview209622PutAdditionalbrowserarguments]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#put_additionalbrowserarguments "put_AdditionalBrowserArguments - 接口 ICoreWebView2EnvironmentOptions |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2environmentViewWebview209430GetBrowserversioninfo]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.430&preserve-view=true#get_browserversioninfo "get_BrowserVersionInfo - 接口 ICoreWebView2Environment |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2environmentViewWebview209488GetBrowserversionstring]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.488&preserve-view=true#get_browserversionstring "get_BrowserVersionString - 接口 ICoreWebView2Environment |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcompositioncontroller2ViewWebview210674PrereleaseGetSystemcursorid]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller2?view=webview2-1.0.674-prerelease&preserve-view=true#get_systemcursorid "interface ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcompositioncontroller3ViewWebview210721Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller3?view=webview2-1.0.721-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCompositionController3 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcompositioncontrollerViewWebview209488Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCompositionController |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseAddRasterizationscalechanged]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#add_rasterizationscalechanged "add_RasterizationScaleChanged - 接口 ICoreWebView2ExperimentalController |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetBoundsmode]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_boundsmode "get_BoundsMode - 接口 ICoreWebView2ExperimentalController |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetRasterizationscale]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_rasterizationscale "get_RasterizationScale - 接口 ICoreWebView2ExperimentalController |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetShoulddetectmonitorscalechanges]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_shoulddetectmonitorscalechanges "get_ShouldDetectMonitorScaleChanges - 接口 ICoreWebView2ExperimentalController |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalcursorchangedeventhandlerViewWebview209488Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcursorchangedeventhandler?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCursorChangedEventHandler |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalenvironmentoptionsViewWebview209538PrereleaseGetIssinglesignonusingosprimaryaccountenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironmentoptions?view=webview2-0.9.538-prerelease&preserve-view=true#get_issinglesignonusingosprimaryaccountenabled "get_IsSingleSignOnUsingOSPrimaryAccountEnabled - 接口 ICoreWebView2ExperimentalEnvironmentOptions |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalnewwindowrequestedeventargsViewWebview209538PrereleaseGetWindowfeatures]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalnewwindowrequestedeventargs?view=webview2-0.9.538-prerelease&preserve-view=true#get_windowfeatures "get_WindowFeatures - 接口 ICoreWebView2ExperimentalNewWindowRequestedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalpointerinfoViewWebview209488Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalpointerinfo?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalPointerInfo |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalsettingsViewWebview210790PrereleaseGetUseragent]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalsettings?view=webview2-1.0.790-prerelease&preserve-view=true#get_useragent "get_UserAgent - 接口 ICoreWebView2ExperimentalSettings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalViewWebview209538PrereleaseAddWebresourceresponsereceived]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-0.9.538-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived - 接口 ICoreWebView2Experimental |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseAddDomcontentloaded]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#add_domcontentloaded "add_DOMContentLoaded - 接口 ICoreWebView2Experimental |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseAddWebresourceresponsereceived]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived - 接口 ICoreWebView2Experimental |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseGetCookiemanager]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#get_cookiemanager "get_CookieManager - 接口 ICoreWebView2Experimental |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseGetEnvironment]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#get_environment "get_Environment - 接口 ICoreWebView2Experimental |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalViewWebview210674PrereleaseNavigatewithwebresourcerequest]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#navigatewithwebresourcerequest "NavigateWithWebResourceRequest - 接口 ICoreWebView2Experimental |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsViewWebview209628PrereleasePopulateresponsecontent]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponsereceivedeventargs?view=webview2-0.9.628-prerelease&preserve-view=true#populateresponsecontent "PopulateResponseContent - 接口 ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponseviewViewWebview210674Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalwebresourceresponseviewViewWebview210674PrereleaseGetcontent]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true#getcontent "GetContent - 接口 ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2experimentalwindowfeaturesViewWebview209538Prerelease]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwindowfeatures?view=webview2-0.9.538-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWindowFeatures |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430GetZoomfactor]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#get_zoomfactor "get_ZoomFactor - 接口 ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430Notifyparentwindowpositionchanged]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#notifyparentwindowpositionchanged "NotifyParentWindowPositionChanged - 接口 ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430PutZoomfactor]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#put_zoomfactor "put_ZoomFactor - 接口 ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2hostViewWebview209430Setboundsandzoomfactor]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#setboundsandzoomfactor "SetBoundsAndZoomFactor - 接口 ICoreWebView2Host |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2httpheaderscollectioniteratorViewWebview209430GetHascurrentheader]: /microsoft-edge/webview2/reference/win32/icorewebview2httpheaderscollectioniterator?view=webview2-0.9.430&preserve-view=true#get_hascurrentheader "get_HasCurrentHeader - 接口 ICoreWebView2HttpHeadersCollectionIterator |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2httprequestheadersViewWebview209430Getheaders]: /microsoft-edge/webview2/reference/win32/icorewebview2httprequestheaders?view=webview2-0.9.430&preserve-view=true#getheaders "GetHeaders - 接口 ICoreWebView2HttpRequestHeaders |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2httpresponseheadersViewWebview209430Getheader]: /microsoft-edge/webview2/reference/win32/icorewebview2httpresponseheaders?view=webview2-0.9.430&preserve-view=true#getheader "GetHeader - 接口 ICoreWebView2HttpResponseHeaders |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2newwindowrequestedeventargsViewWebview209538GetIsuserinitiated]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.538&preserve-view=true#get_isuserinitiated "get_IsUserInitiated接口 ICoreWebView2NewWindowRequestedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2newwindowrequestedeventargsViewWebview209622GetWindowfeatures]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.622&preserve-view=true#get_windowfeatures "get_WindowFeatures - 接口 ICoreWebView2NewWindowRequestedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209430GetAreremoteobjectsallowed]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed - 接口 ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209430GetIszoomcontrolenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_iszoomcontrolenabled "get_IsZoomControlEnabled - 接口 ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209488GetAreremoteobjectsallowed]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed - 接口 ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209488GetIsbuiltinerrorpageenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_isbuiltinerrorpageenabled "get_IsBuiltInErrorPageEnabled - 接口 ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2settingsViewWebview209538GetArehostobjectsallowed]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.538&preserve-view=true#get_arehostobjectsallowed "get_AreHostObjectsAllowed - 接口 ICoreWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430AddContentloading]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_contentloading "add_ContentLoading - 接口 ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430AddHistorychanged]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_historychanged "add_HistoryChanged - 接口 ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430Addremoteobject]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#addremoteobject "AddRemoteObject - 接口 ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430AddSourcechanged]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_sourcechanged "add_SourceChanged - 接口 ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430AddWindowcloserequested]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_windowcloserequested "add_WindowCloseRequested - 接口 ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430CoreWebview2ScriptDialogKind]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#core_webview2_script_dialog_kind "CORE_WEBVIEW2_SCRIPT_DIALOG_KIND - 接口 ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209430Removeremoteobject]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#removeremoteobject "RemoveRemoteObject - 接口 ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209488AddFramenavigationcompleted]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_framenavigationcompleted "add_FrameNavigationCompleted - 接口 ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209488Addhostobjecttoscript]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#addhostobjecttoscript "AddHostObjectToScript - 接口 ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209488AddNewwindowrequested]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_newwindowrequested "add_NewWindowRequested - 接口 ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209488Removehostobjectfromscript]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#removehostobjectfromscript "RemoveHostObjectFromScript - 接口 ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2ViewWebview209538ddhostobjecttoscript]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.538&preserve-view=true#addhostobjecttoscript "AddHostObjectToScript - 接口 ICoreWebView2 |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2webmessagereceivedeventargsViewWebview209430Trygetwebmessageasstring]: /microsoft-edge/webview2/reference/win32/icorewebview2webmessagereceivedeventargs?view=webview2-0.9.430&preserve-view=true#trygetwebmessageasstring "TryGetWebMessageAsString - 接口 ICoreWebView2WebMessageReceivedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2webresourceresponseviewgetcontentcompletedhandlerViewWebview210790PrereleaseInvoke]: /microsoft-edge/webview2/reference/win32/icorewebview2webresourceresponseviewgetcontentcompletedhandler?view=webview2-1.0.790-prerelease&preserve-view=true#invoke "Invoke - 接口 ICoreWebView2WebResourceResponseViewGetContentCompletedHandler |Microsoft Docs" 
[Webview2ReferenceWin32Icorewebview2windowfeaturesViewWebview209622]: /microsoft-edge/webview2/reference/win32/icorewebview2windowfeatures?view=webview2-0.9.622&preserve-view=true "interface ICoreWebView2WindowFeatures |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2acceleratorkeypressedeventargsViewWebview208355Handle]: /microsoft-edge/webview2/reference/win32/iwebview2acceleratorkeypressedeventargs?view=webview2-0.8.355&preserve-view=true#handle "Handle - 接口 IWebView2AcceleratorKeyPressedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandlerViewWebview208355]: /microsoft-edge/webview2/reference/win32/iwebview2containsfullscreenelementchangedeventhandler?view=webview2-0.8.355&preserve-view=true "接口 IWebView2ContainsFullScreenElementChangedEventHandler |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2settings2ViewWebview208355PutAredefaultcontextmenusenabled]: /microsoft-edge/webview2/reference/win32/iwebview2settings2?view=webview2-0.8.355&preserve-view=true#put_aredefaultcontextmenusenabled "put_AreDefaultContextMenusEnabled - 接口 IWebView2Settings2 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2settingsViewWebview208355GetIsfullscreenallowedDeprecated]: /microsoft-edge/webview2/reference/win32/iwebview2settings?view=webview2-0.8.355&preserve-view=true#get_isfullscreenallowed_deprecated "get_IsFullscreenAllowed_deprecated - 接口 IWebView2Settings |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webmessagereceivedeventargsViewWebview208355GetWebmessageasstring]: /microsoft-edge/webview2/reference/win32/iwebview2webmessagereceivedeventargs?view=webview2-0.8.355&preserve-view=true#get_webmessageasstring "get_WebMessageAsString - 接口 IWebView2WebMessageReceivedEventArgs |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webview4ViewWebview208355AddAcceleratorkeypressed]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#add_acceleratorkeypressed "add_AcceleratorKeyPressed - 接口 IWebView2WebView4 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webview4ViewWebview208355Addremoteobject]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#addremoteobject "AddRemoteObject - 接口 IWebView2WebView4 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webview5ViewWebview208355AddWebresourcerequested]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#add_webresourcerequested "add_WebResourceRequested - 接口 IWebView2WebView5 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webview5ViewWebview208355Addwebresourcerequestedfilter]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#addwebresourcerequestedfilter "AddWebResourceRequestedFilter - 接口 IWebView2WebView5 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webview5ViewWebview208355GetContainsfullscreenelement]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#get_containsfullscreenelement "get_ContainsFullScreenElement - 接口 IWebView2WebView5 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webview5ViewWebview208355Removewebresourcerequestedfilter]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#removewebresourcerequestedfilter "RemoveWebResourceRequestedFilter - 接口 IWebView2WebView5 |Microsoft Docs" 
[Webview2ReferenceWin32Iwebview2webviewViewWebview208355AddDocumentstatechanged]: /microsoft-edge/webview2/reference/win32/iwebview2webview?view=webview2-0.8.355&preserve-view=true#add_documentstatechanged "add_DocumentStateChanged - 接口 IWebView2WebView |Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview208355Createwebview2environmentwithdetails]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.8.355&preserve-view=true#createwebview2environmentwithdetails "CreateWebView2EnvironmentWithDetails - 全局|Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview209430Getcorewebview2browserversioninfo]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.430&preserve-view=true#getcorewebview2browserversioninfo "GetCoreWebView2BrowserVersionInfo - 全局|Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview209488Createcorewebview2environmentwithdetails]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithdetails "CreateCoreWebView2EnvironmentWithDetails - 全局|Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview209488Createcorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - 全局|Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview209488Getavailablecorewebview2browserversionstring]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString - 全局|Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview209538Createcorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.538&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - 全局|Microsoft Docs" 
[Webview2ReferenceWin32Webview2IdlViewWebview209622Createcorewebview2environmentwithoptions]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.622&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - 全局|Microsoft Edge" 

[DeployedgeMicrosoftEdgePolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge - 策略|Microsoft Docs"  
[DeployedgeMicrosoftEdgeWebviewPolicies]: /deployedge/microsoft-edge-webview-policies "Microsoft EdgeWebView2 - 策略|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Core]: /dotnet/api/microsoft.web.webview2.core "Microsoft.Web.WebView2.Core 命名空间|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2]: /dotnet/api/microsoft.web.webview2.core.corewebview2 "CoreWebView2 类 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environment]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment "CoreWebView2Environment 类 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.comparebrowserversions "CoreWebView2Environment.CompareBrowserVersions (String， String) Method (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.getavailablebrowserversionstring "CoreWebView2Environment.GetAvailableBrowserVersionString (String) 方法 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2httprequestheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httprequestheaders "CoreWebView2HttpRequestHeaders 类 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2httpresponseheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httpresponseheaders "CoreWebView2HttpResponseHeaders 类 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Newwindowrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.newwindowrequested "CoreWebView2.NewWindowRequested 事件 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Permissionrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.permissionrequested "CoreWebView2.PermissionRequested 事件 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]: /dotnet/api/microsoft.web.webview2.core.corewebview2.scriptdialogopening "CoreWebView2.ScriptDialogOpening 事件 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.webresourcerequested "CoreWebView2.WebResourceRequested 事件 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2Corewebview2initializationcompletedeventargs]: /dotnet/api/microsoft.web.webview2.core.corewebview2initializationcompletedeventargs "CoreWebView2InitializationCompletedEventArgs 类|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreWebview2runtimenotfoundexception]: /dotnet/api/microsoft.web.webview2.core.webview2runtimenotfoundexception "CoreWebView2.WebView2RuntimeNotFound (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2Winforms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 命名空间|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.winforms.corewebview2creationproperties "CoreWebView2CreationProperties 类 (Microsoft.Web.WebView2.Winforms) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Source]: /dotnet/api/microsoft.web.webview2.winforms.webview2.source "Microsoft.Web.Web.WebView2.Winforms (Webview2.Source 类) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2Wpf]: /dotnet/api/microsoft.web.webview2.wpf "Microsoft.Web.WebView2.Wpf 命名空间|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Acceleratorkeypressed]: /dotnet/api/microsoft.web.webview2.wpf.webview2.acceleratorkeypressed "microsoft.web.webview2.wpf.webview2.acceleratorkeypressed |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Buildwindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.buildwindowcore "Microsoft.Web.WebView2.Wpf (的 WebView2.BuildWindowCore) HandleRef (方法) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Destroywindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.destroywindowcore "Microsoft.Web.WebView2.Wpf (的 WebView2.DestroyWindowCore) HandleRef (方法) |Microsoft Docs"  
[DotnetApiSystemComponentmodelCancelEventargs]: /dotnet/api/system.componentmodel.canceleventargs "System.ComponentModel (CancelEventArgs) |Microsoft Docs"  
[DotnetApiSystemEventargs]: /dotnet/api/system.eventargs "EventArgs 系统 (类) |Microsoft Docs"  

[DotnetStandardAssemblyStrongNamed]: /dotnet/standard/assembly/strong-named "强名称程序集|Microsoft Docs"  

[WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]: /windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview "Microsoft Defender 应用程序防护 (Windows 10) - Windows安全|Microsoft Docs"  
[WindowsWin32ApiWinuserSetWindowDisplayAffinity]: /windows/win32/api/winuser/nf-winuser-setwindowdisplayaffinity "SetWindowDisplayAffinity (winuser.h) - Win32 应用|Microsoft Docs"  

[GithubMicrosoftedgeWebview2AnnouncementIssue2]: https://github.com/MicrosoftEdge/WebView2Announcement/issues/2 "MicrosoftEdge/WebViewAnnouncement 问题 2 的公告存储库"  

[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesWebview2wpfbrowser]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2WpfBrowser "WebView2WpfBrowser - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesPr17]: https://github.com/MicrosoftEdge/WebView2Samples/pull/17 "移动项目以使用最新的 WebView2 SDK 0.9.430 - MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftedgeWebviewfeedbackIssue1]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1 "MicrosoftEdge/WebViewFeedback 问题 1 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue12]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/12 "MicrosoftEdge/WebViewFeedback 问题 12 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue13]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/13 "MicrosoftEdge/WebViewFeedback 问题 13 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue14]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/14 "MicrosoftEdge/WebViewFeedback 问题 14 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue16]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/16 "MicrosoftEdge/WebViewFeedback 问题 16 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue17]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/17 "MicrosoftEdge/WebViewFeedback 问题 17 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue18]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/18 "MicrosoftEdge/WebViewFeedback 问题 18 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue19]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/19 "MicrosoftEdge/WebViewFeedback 问题 19 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue22]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/22 "MicrosoftEdge/WebViewFeedback 问题 22 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue27]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/27 "MicrosoftEdge/WebViewFeedback 问题 27 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue28]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/28 "MicrosoftEdge/WebViewFeedback 问题 28 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue30]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/30 "MicrosoftEdge/WebViewFeedback 问题 30 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue32]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/32 "MicrosoftEdge/WebViewFeedback 问题 32 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue36]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/36 "MicrosoftEdge/WebViewFeedback 问题 36 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue37]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/37 "MicrosoftEdge/WebViewFeedback 问题 37 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue57]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/57 "MicrosoftEdge/WebViewFeedback 问题 57 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue58]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/58 "MicrosoftEdge/WebViewFeedback 问题 58 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue70]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/70 "MicrosoftEdge/WebViewFeedback 问题 70 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue74]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/74 "MicrosoftEdge/WebViewFeedback 问题 74 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue95]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/95 "MicrosoftEdge/WebViewFeedback 问题 95 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue108]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/108 "MicrosoftEdge/WebViewFeedback 问题 108 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue113]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/113 "MicrosoftEdge/WebViewFeedback 问题 113 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue119]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/119 "MicrosoftEdge/WebViewFeedback 问题 119 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue122]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/122 "MicrosoftEdge/WebViewFeedback 问题 122 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue131]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/131 "MicrosoftEdge/WebViewFeedback 问题 131 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue148]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/148 "MicrosoftEdge/WebViewFeedback 问题 148 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue161]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/161 "MicrosoftEdge/WebViewFeedback 问题 161 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue168]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/168 "MicrosoftEdge/WebViewFeedback 问题 168 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue177]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/177 "MicrosoftEdge/WebViewFeedback 问题 177 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue179]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/179 "MicrosoftEdge/WebViewFeedback 问题 179 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue181]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/181 "MicrosoftEdge/WebViewFeedback 问题 181 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue183]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/183 "MicrosoftEdge/WebViewFeedback 问题 183 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue185]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/185 "MicrosoftEdge/WebViewFeedback 问题 185 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue196]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/196 "MicrosoftEdge/WebViewFeedback 问题 196 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue204]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/204 "MicrosoftEdge/WebViewFeedback 问题 204 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue205]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/205 "MicrosoftEdge/WebViewFeedback 问题 205 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue210]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/210 "MicrosoftEdge/WebViewFeedback 问题 210 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue212]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/212 "MicrosoftEdge/WebViewFeedback 问题 212 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue219]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/219 "MicrosoftEdge/WebViewFeedback 问题 219 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue228]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/228 "MicrosoftEdge/WebViewFeedback 问题 228 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue235]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/235 "MicrosoftEdge/WebViewFeedback 问题 235 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue250]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/250 "MicrosoftEdge/WebViewFeedback 问题 250 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue275]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/275 "MicrosoftEdge/WebViewFeedback 问题 275 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue288]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/288 "MicrosoftEdge/WebViewFeedback 问题 288 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue293]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/293 "MicrosoftEdge/WebViewFeedback 问题 293 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue318]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/318 "MicrosoftEdge/WebViewFeedback 问题 318 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue335]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/335 "MicrosoftEdge/WebViewFeedback 问题 335 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue371]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/371 "MicrosoftEdge/WebViewFeedback 问题 371 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue382]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/382 "MicrosoftEdge/WebViewFeedback 问题 382 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue399]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/399 "MicrosoftEdge/WebViewFeedback 问题 399 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue400]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/400 "MicrosoftEdge/WebViewFeedback 问题 400 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue409]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/409 "MicrosoftEdge/WebViewFeedback 问题 409 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue414]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/414 "MicrosoftEdge/WebViewFeedback 问题 414 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue431]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/431 "MicrosoftEdge/WebViewFeedback 问题 431 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue432]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/432 "MicrosoftEdge/WebViewFeedback 问题 432 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue442]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/442 "MicrosoftEdge/WebViewFeedback 问题 442 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue461]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/461 "MicrosoftEdge/WebViewFeedback 问题 461 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue506]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/506 "MicrosoftEdge/WebViewFeedback 问题 506 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue525]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/525 "MicrosoftEdge/WebViewFeedback 问题 525 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue549]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/549 "MicrosoftEdge/WebViewFeedback 问题 549 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue560]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/560 "MicrosoftEdge/WebViewFeedback 问题 560 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue568]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/568 "MicrosoftEdge/WebViewFeedback 问题 568 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue585]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/585 "MicrosoftEdge/WebViewFeedback 问题 585 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue604]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/604 "MicrosoftEdge/WebViewFeedback 问题 604 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue605]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/605 "MicrosoftEdge/WebViewFeedback 问题 605 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue611]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/611 "MicrosoftEdge/WebViewFeedback 问题 611 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue669]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/669 "MicrosoftEdge/WebViewFeedback 问题 669 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue691]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/691 "MicrosoftEdge/WebViewFeedback 问题 691 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue816]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/816 "MicrosoftEdge/WebViewFeedback 问题 816 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue851]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/851 "MicrosoftEdge/WebViewFeedback 问题 851 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue875]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/875 "MicrosoftEdge/WebViewFeedback 问题 875 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue878]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/878 "MicrosoftEdge/WebViewFeedback 问题 878 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue1120]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1120 "MicrosoftEdge/WebViewFeedback 问题 1120 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue940]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/940 "MicrosoftEdge/WebViewFeedback 问题 940 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue841]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/841 "MicrosoftEdge/WebViewFeedback 问题 841 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue210]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/210 "MicrosoftEdge/WebViewFeedback 问题 210 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue338]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/338 "MicrosoftEdge/WebViewFeedback 问题 338 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue589]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/589 "MicrosoftEdge/WebViewFeedback 问题 589 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue933]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/933 "MicrosoftEdge/WebViewFeedback 问题 933 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue946]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/946 "MicrosoftEdge/WebViewFeedback 问题 946 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue1011]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1011 "MicrosoftEdge/WebViewFeedback 问题 1011 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue1050]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1050 "MicrosoftEdge/WebViewFeedback 问题 1050 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue996]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/996 "MicrosoftEdge/WebViewFeedback 问题 996 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue850]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/850 "MicrosoftEdge/WebViewFeedback 问题 850 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue1077]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1077 "MicrosoftEdge/WebViewFeedback 问题 1077 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue1099]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1099 "MicrosoftEdge/WebViewFeedback 问题 1099 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue1183]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1183 "MicrosoftEdge/WebViewFeedback 问题 1183 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue1108]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1108 "MicrosoftEdge/WebViewFeedback 问题 1108 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue940]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/940 "MicrosoftEdge/WebViewFeedback 问题 850 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue1079]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1079 "MicrosoftEdge/WebViewFeedback 问题 1079 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue1013]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1013 "MicrosoftEdge/WebViewFeedback 问题 1013 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue1282]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1282 "MicrosoftEdge/WebViewFeedback 问题 1282 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue828]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/828 "MicrosoftEdge/WebViewFeedback 问题 828 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue619]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/619 "MicrosoftEdge/WebViewFeedback 问题 619 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue608]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/608 "MicrosoftEdge/WebViewFeedback 问题 608 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue1209]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1209 "MicrosoftEdge/WebViewFeedback 问题 1209 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue448]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/448 "MicrosoftEdge/WebViewFeedback 问题 448 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue1123]: https://github.com/MicrosoftEdge/WebViewFeedback/issues/1123 "MicrosoftEdge/WebViewFeedback 问题 1123 的反馈存储库"

[MicrosoftDevblogDotnetAnnouncingGeneralAvailabilityForMicrosoftEdgeWebview2ForNetFixedDistributionMethod]: https://devblogs.microsoft.com/dotnet/announcing-general-availability-for-microsoft-edge-webview2-for-net-and-fixed-distribution-method "宣布正式发布适用于 .NET Microsoft Edge WebView2 和固定分发方法| .NET 博客"  

[MicrosoftDeveloperMicrosoftEdgeWebView2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft EdgeWebView2 |Microsoft Edge开发人员"  

[NuGetGallery]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "NuGet库|Microsoft.Web.WebView2"  
[NuGetGallery0.8.149]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.149 "NuGet库|Microsoft.Web.WebView2 v0.8.149"  
[NuGetGallery0.8.190]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.190 "NuGet库|Microsoft.Web.WebView2 v0.8.190"  
[NuGetGallery0.8.230]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.230 "NuGet库|Microsoft.Web.WebView2 v0.8.230"  
[NuGetGallery0.8.270]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.270 "NuGet库|Microsoft.Web.WebView2 v0.8.270"  
[NuGetGallery0.8.314]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.314 "NuGet库|Microsoft.Web.WebView2 v0.8.314"  
[NuGetGallery0.8.355]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.355 "NuGet库|Microsoft.Web.WebView2 v0.8.355"  
[NuGetGallery0.9.430]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.430 "NuGet库|Microsoft.Web.WebView2 v0.9.430"  
[NuGetGallery0.9.488]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.488 "NuGet库|Microsoft.Web.WebView2 v0.9.488"  
[NuGetGallery0.9.515-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.515-prerelease "NuGet库|Microsoft.Web.WebView2 v0.9.515 预发行"  
[NuGetGallery0.9.538]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.538 "NuGet库|Microsoft.Web.WebView2 v0.9.538"  
[NuGetGallery0.9.579]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.579 "NuGet库|Microsoft.Web.WebView2 v0.9.579"  
[NuGetGallery0.9.622.11]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.622.11 "NuGet库|Microsoft.Web.WebView2 v0.9.622.11"  
[NuGetGallery0.9.628-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.628-prerelease "NuGet库|Microsoft.Web.WebView2 v0.9.628 预发行"  
[NuGetGallery1.0.622.22]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.622.22 "NuGet库|Microsoft.Web.WebView2 v1.0.622.22"  
[NuGetGallery1.0.664.34]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.34 "NuGet库|Microsoft.Web.WebView2 v1.0.664.34"  
[NuGetGallery1.0.664.37]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.37 "NuGet库|Microsoft.Web.WebView2 v1.0.664.37"  
[NuGetGallery1.0.674-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.674-prerelease "NuGet库|Microsoft.Web.WebView2 v1.0.674 预发行"  
[NuGetGallery1.0.705.50]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.705.50 "NuGet库|Microsoft.Web.WebView2 v1.0.705.50"  
[NuGetGallery1.0.721-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.721-prerelease "NuGet库|Microsoft.Web.WebView2 v1.0.721 预发行"  
[NuGetGallery1.0.774.44]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.774.44 "NuGet库|Microsoft.Web.WebView2 v1.0.774.44"  
[NuGetGallery1.0.790-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.790-prerelease "NuGet库|Microsoft.Web.WebView2 v1.0.790 预发行"  
[NuGetGallery1.0.818.41]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.818.41 "NuGet库|Microsoft.Web.WebView2 v1.0.818.41"  
[NuGetGallery1.0.864.35]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.864.35 "NuGet库|Microsoft.Web.WebView2 v1.0.864.35"  
[NuGetGallery1.0.824-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.824-prerelease "NuGet库|Microsoft.Web.WebView2 v1.0.824 预发行"  
[NuGetGallery1.0.865-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.865-prerelease "NuGet库|Microsoft.Web.WebView2 v1.0.865 预发行"  
[NuGetGallery1.0.902-prerelease]: https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.902-prerelease "NuGet库|Microsoft.Web.WebView2 v1.0.902 预发行"  

[WindowsBlogsMsedgedevEdgeWebview2GeneralAvailability]: https://blogs.windows.com/msedgedev/edge-webview2-general-availability "宣布Microsoft Edge WebView2 通用|Microsoft Edge博客"  
[Webview2ReferenceWin32Icorewebview2experimentalsettings5ViewWebview210902PrereleaseGetIsswipenavigationenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalsettings5?view=webview2-1.0.902-prerelease&preserve-view=true#get_isswipenavigationenabled "get_IsSwipeNavigationEnabled - 接口 ICoreWebView2ExperimentalSettings5 |Microsoft Docs"
[Webview2ReferenceWin32Icorewebview2experimentalenvironment4ViewWebview210902PrereleaseAddBrowserprocessexited]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironment4?view=webview2-1.0.902-prerelease&preserve-view=true#add_browserprocessexited "add_BrowserProcessExited - 接口 ICoreWebView2ExperimentalEnvironment4 |Microsoft Docs"
[Webview2ReferenceWin32Icorewebview2experimental3ViewWebview210902PrereleaseAddClientcertificaterequested]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental3?view=webview2-1.0.902-prerelease&preserve-view=true#add_clientcertificaterequested "add_ClientCertificateRequested - 接口 ICoreWebView2Experimental3 |Microsoft Docs"


[Webview2ReferenceWin32Icorewebview24ViewWebview210902PrereleaseAddDownloadstarting]: /microsoft-edge/webview2/reference/win32/icorewebview2_4?view=webview2-1.0.902-prerelease&preserve-view=true#add_downloadstarting "add_DownloadStarting - 接口ICoreWebView2_4 |Microsoft Docs"
[Webview2ReferenceWin32Icorewebview24ViewWebview210902PrereleaseAddFramecreated]: /microsoft-edge/webview2/reference/win32/icorewebview2_4?view=webview2-1.0.902-prerelease&preserve-view=true#add_framecreated "add_FrameCreated - 接口ICoreWebView2_4 |Microsoft Docs"
[Webview2ReferenceWin32Icorewebview2setting4ViewWebview210902PrereleaseGetIsgeneralautofillenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings4?view=webview2-1.0.902-prerelease&preserve-view=true#get_isgeneralautofillenabled "get_IsGeneralAutofillEnabled - 接口 ICoreWebView2Settings4 |Microsoft Docs"

[AddHostObjectToScriptWithOriginsAPI]: /microsoft-edge/webview2/reference/win32/icorewebview2frame?view=webview2-1.0.902-prerelease&preserve-view=true#addhostobjecttoscriptwithorigins "AddHostObjectToScriptWithOrigins |Microsoft Docs"

[Webview2ReferenceWin32Icorewebview2setting5ViewWebview210902PrereleaseGetIspinchzoomenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings5?view=webview2-1.0.902-prerelease&preserve-view=true#get_ispinchzoomenabled "get_IsPinchZoomEnabled - 接口 ICoreWebView2Settings5 |Microsoft Docs"

[Webview2ReferenceWin32Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions#get_allowsinglesignonusingosprimaryaccount "get_AllowSingleSignOnUsingOSPrimaryAccount - 接口 ICoreWebView2EnvironmentOptions |Microsoft Docs"
[Webview2ReferenceWin32Icorewebview2setting2ViewWebview21086435GetUseragent]: /microsoft-edge/webview2/reference/win32/icorewebview2settings2?view=webview2-1.0.864.35&preserve-view=true#get_useragent 

/microsoft-edge/webview2/reference/win32/icorewebview2settings2？view=webview2-1.0.864.35&preserve-view=true#get_useragent 

"get_UserAgent - 接口 ICoreWebView2Setting2 |Microsoft Docs"
[Webview2ReferenceWin32Icorewebview2setting2ViewWebview21086435GetArebrowseracceleratorkeysenabled]: /microsoft-edge/webview2/reference/win32/icorewebview2settings3?view=webview2-1.0.864.35&preserve-view=true#get_arebrowseracceleratorkeysenabled "get_AreBrowserAcceleratorKeysEnabled - 接口 ICoreWebView2Settings3 |Microsoft Docs"
