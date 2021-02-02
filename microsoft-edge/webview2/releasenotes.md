---
description: Microsoft Edge WebView2 SDK 发行说明
title: 适用于 Win32、WPF 和 WinForms 的 Microsoft Edge WebView2 发行说明
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/01/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 199077b1922fd7249bd67133d55d85bc0f144926
ms.sourcegitcommit: ab4b555d30f3be05d8620e8deb3c74350b6696be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2021
ms.locfileid: "11306614"
---
# WebView2 SDK 发行说明  

WebView2 团队将每六周更新一次[WebView2 SDK。][NuGetGallery]  查看以下内容，获取有关产品公告、添加、修改和 API 的中断更改最新信息。  

> [!NOTE]
> 确保在更新 NuGet 程序包后重新编译应用。  该团队建议使用 Canary 通道使用预发行程序包进行开发，使用已发布程序包时使用常青运行时。  有关详细信息，请导航到["版本控制"。][VersioningDoc]  
 
## 1.0.781-prerelease  

发布日期：2021 年 1 月 29 日  

[NuGet 包][NuGetGallery1.0.781-prerelease] \|Microsoft Edge 版本 86.0.616.0 或更高版本  

### 常规  

> [!IMPORTANT]
> WebView2 预发行版程序包 0.9.430 已弃用，并且将从即将发布的版本中删除。  如果你的 WebView 应用使用程序包，我们建议更新到较新的程序包。  

##### 功能  

*   添加了 [TrySuspend 和 Resume][ReferenceWin32Icorewebview210781PreReleaseTrySuspendResume] 方法以暂停和恢复 WebView。  
*   添加了 [SetVirtualHostNameToFolderMapping][ReferenceWin32Icorewebview210781PreReleaseSetVirtualHostNameToFolderMapping] 方法，该方法将虚拟主机名映射到目录路径。  \ ([\#37][GithubMicrosoftedgeWebviewfeedbackIssue37] [、\#161][GithubMicrosoftedgeWebviewfeedbackIssue161]和 [\#212][GithubMicrosoftedgeWebviewfeedbackIssue212]\) 。  
*   添加了 [DefaultBackgroundColor][ReferenceWin32Icorewebview2controllerViewWebview210781PreReleaseDefaultBackgroundColor] 属性以设置背景的颜色和 alpha 通道。  \ ([\#414][GithubMicrosoftedgeWebviewfeedbackIssue414]\) 。  
*   添加了 [UserAgent][ReferenceWin32Icorewebview2experimentalsettings10781PreReleaseGetUserAgent] 属性，以获取或设置用户代理。  \ ([\#122][GithubMicrosoftedgeWebviewfeedbackIssue122]\) 。
*   用 `CreateCookieWithCookie` 该方法替换 `CopyCookie` 了该方法。  
*   添加了使用 [ICoreWebView2CompositionController][ReferenceWin32Icorewebview2controllerViewWebview210781CompositionController] 接口的可视托管支持，该接口使用来自 的 `CreateCoreWebView2CompositionController` 新方法创建 `ICoreWebView2Environment3` 。  

    
##### Bug 修复  

*   在 WebView2 中关闭 Microsoft Edge 购物功能。  
*   关闭 PDF 查看器中的 `AreDefaultContextMenusEnabled` 上下文菜单。 `false`  \ ([\#605][GithubMicrosoftedgeWebviewfeedbackIssue605]\) 。  
*   修复了查询时 `E_NOINTERFACE` 返回的 `ICoreWebView2` `ICoreWebView2Experimental` Bug。  \ ([\#691][GithubMicrosoftedgeWebviewfeedbackIssue691]\) 。  
*   修复了在设置为时允许使用格式错误的 URI `CoreWebView2NavigationStartingEventArgs.Cancel` 进行导航的 `false` bug。  \ ([\#400][GithubMicrosoftedgeWebviewfeedbackIssue400]\) 。  
*   修复了在弹出窗口中阻止的、事件处理程序附加到事件的 `window.print()` `NewWindowRequested` Bug。  \ ([\#409][GithubMicrosoftedgeWebviewfeedbackIssue409]\) 。  
*   修复了在不同监视器之间移动应用时的动态 DPI 问题。  \ ([\#58][GithubMicrosoftedgeWebviewfeedbackIssue58]\)   
*   改进了由 `HRESULT` [ICoreWebView2WebResourceResponseViewGetContentCompletedHandler：：Invoke 传递的项][ReferenceWin32Icorewebview2webresourceresponseviewgetcontentcompletedhandlerInvoke10781]。  
    
##### 促销  

*   以下实验 API 现已提升为稳定。  
    *   可视托管 API。  
    *   [SetVirtualHostNameToFolderMapping][ReferenceWin32Icorewebview210781PreReleaseSetVirtualHostNameToFolderMapping]  
    *   [TrySuspend 和 Resume][ReferenceWin32Icorewebview210781PreReleaseTrySuspendResume]  
    *   [DefaultBackgroundColor][ReferenceWin32Icorewebview2controllerViewWebview210781PreReleaseDefaultBackgroundColor]  
    
#### .NET  

##### Bug 修复  

*   修复了使用 WPF SDK 的 WebView 应用崩溃的错误。  当使用 F4 键关闭窗口时发生崩溃。  \ ([\#399][GithubMicrosoftedgeWebviewfeedbackIssue399]\) 。  
*   WebView2 初始化屏幕现在是透明的，而不是灰色的。  \ ([\#196][GithubMicrosoftedgeWebviewfeedbackIssue196]\) 。  
    
## 1.0.705.50  

发布日期：2021 年 1 月 25 日  

[NuGet 包][NuGetGallery1.0.705.50] \|WebView2 运行时版本 86.0.616.0 或更高版本  

##### 促销  

*   以下实验 API 现已提升为稳定。  
    *   [WebResourceResponseReceived API][WebResourceResponseReceivedAPI]  
    *   [NavigateWithWebResourceRequest API][NavigateWithWebResourceRequestAPI]  
    *   [Cookie 管理 API][CookiemanagementAPI]  
    *   [DOMContentLoaded API][DOMContentLoadedAPI]  
    *   [WebView 环境属性][WebViewEnvironmentproperty]  

## 1.0.721-prerelease  

发布日期：2020 年 12 月 8 日  

[NuGet 包][NuGetGallery1.0.721-prerelease] \|Microsoft Edge 版本 86.0.616.0 或更高版本  

#### 常规  

> [!IMPORTANT]
> **中断更改**：已弃用 WebView2 预发行版程序包 1.0.707 和 0.9.628。  请停止使用这些程序包进行开发。  

###### 功能  

*   添加了 [WebView2 组策略][DeployedgeMicrosoftEdgeWebviewPolicies]。  有关建议做法的信息，请导航到 [WebView2 的组策略][Webview2ConceptsEnterpriseGroupPoliciesForWebview2]。  
*   > [!IMPORTANT]
    > **Breaking Change**： Deprecated the old registry location.  
    > 
    > ```text
    > {Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}
    > ```  
    
*   添加了对 WebView2 [中的拖放][ReferenceWin32Icorewebview2experimentalcompositioncontroller3] 功能的支持。  
*   添加了 API 以处理 DPI 支持。  
    *   添加了 [RasterizationScale][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetRasterizationscale] 属性以更改 WebView 内容和 UI 弹出窗口的 DPI 缩放，以及关联的 [RasterizationScaleChanged][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseAddRasterizationscalechanged] 事件。  
    *   添加了 [ShouldDetectMonitorScaleChanges][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetShouldDetectMonitorScaleChanges] 属性以根据需要 `RasterizationScale` 自动更新属性。  
    *   添加了 [BoundsMode][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetBoundsMode] 属性，以指定边界是逻辑像素并允许 WebView 用于 `RasterizationScale` WebView2 像素显示，WebView 使用 与 获取物理 `RasterizationScale` `Bounds` 大小。  
*   已 `NewWindowRequested` 更新要处理的事件 `Ctrl` + `click` `Shift` + `click` 和 。  \ ([\#168][GithubMicrosoftedgeWebviewfeedbackIssue168] 和 [\#371][GithubMicrosoftedgeWebviewfeedbackIssue371]\) 。  
*   以下实验 API 现已提升为稳定。  
    *   [WebResourceResponseReceived API][WebResourceResponseReceivedAPI]  
    *   [NavigateWithWebResourceRequest API][NavigateWithWebResourceRequestAPI]  
    *   [Cookie 管理 API][CookiemanagementAPI]  
    *   [DOMContentLoaded API][DOMContentLoadedAPI]  
    *   [WebView 环境属性][WebViewEnvironmentproperty]  
        
#### .NET  

###### 功能  

*   在 .NET Core 3.1+ 和 .NET 5 中打开 WinForms 设计器。  
*   改进了 .NET Cookie 管理。  \ ([\#611][GithubMicrosoftedgeWebviewfeedbackIssue611]\) 。  
*   替换为 `CoreWebView2Ready` [CoreWebView2InitializationCompleted][DotnetApiMicrosoftWebWebview2Corewebview2initializationcompletedeventargs]。  

###### Bug 修复

*   添加了 [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2WpfWebview2Acceleratorkeypressed] 事件以支持 WebView2 中的 AcceleratorKey 按下。  \ ([\#288][GithubMicrosoftedgeWebviewfeedbackIssue288]\) 。  
*   将不必要的文件从输出到 WebView2 文件夹。  \ ([\#461][GithubMicrosoftedgeWebviewfeedbackIssue461]\) 。  
*   改进的主机对象 API。  \ ([\#335][GithubMicrosoftedgeWebviewfeedbackIssue335] 和 [\#525][GithubMicrosoftedgeWebviewfeedbackIssue525]\) 。  
    
## 1.0.664.37  

发布日期：2020 年 11 月 20 日  

[NuGet 包][NuGetGallery1.0.664.37] \|WebView2 运行时版本 86.0.616.0 或更高版本。  

#### 常规  

> [!IMPORTANT]
> **公告**：.NET WPF/WinForms WebView2 SDK 现已正式发布 \ (GA\) 。  从此版本开始，版本 SDK 是向前兼容的。  有关详细信息，请导航到 [GA 公告博客文章][MicrosoftDevblogDotnetAnnouncingGeneralAvailabilityForMicrosoftEdgeWebview2ForNetFixedDistributionMethod]。  

###### 功能  

*   .NET WPF/WinForms WebView2 现已发布 \ (GA\) 。  
*   固定分发 \ (Bring-your-own\) 达到 GA。  
    
#### .NET  

###### Bug 修复  

*   `CoreWebView2NewWindowRequestedEventArgs.Handled` 阻止打开新窗口。  \ ([\#549][GithubMicrosoftedgeWebviewfeedbackIssue549] 和 [\#560][GithubMicrosoftedgeWebviewfeedbackIssue560]\) 。  
    
## 1.0.674-prerelease  

发布日期：2020 年 10 月 19 日  

[NuGet 包][NuGetGallery1.0.674-prerelease] \|WebView2 运行时版本 86.0.616.0 或更高版本。  

#### 常规  

*   添加了 [NavigateWithWebResourceRequest][ReferenceWin32Icorewebview2experimentalNavigatewithwebresourcerequest10674] 方法，可在导航期间提供发布数据或其他请求标头。  
*   添加了 [DOMContentLoaded][ReferenceWin32Icorewebview2experimentalAddDomcontentloaded10674] 事件，该事件在加载和分析初始 HTML 文档时运行。  
*   在 [WebView2][ReferenceWin32Icorewebview2experimentalGetEnvironment10674] 上添加了 Environment 属性。  此属性公开创建 WebView2 实例的 WebView2 环境。  
*   添加了 [Cookie 管理][ReferenceWin32Icorewebview2experimentalGetCookiemanager10674] API，允许开发人员对 WebView2 会话进行身份验证，或从 WebView 检索 Cookie 以验证其他工具。  Webview 团队正在计划进行特定于语言或框架的改进。  有关详细信息，请导航到["API 审阅：Cookie 管理"。][GithubMicrosoftedgeWebview2AnnouncementIssue2]  
*   更新[了 WebResourceResponseReceived][ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived10674]事件，向[WebResourceResponseView：：GetContent][ReferenceWin32Icorewebview2experimentalwebresourceresponseviewGetcontent10674]添加了不可变[WebResourceResponseView][ReferenceWin32Icorewebview2experimentalwebresourceresponseview10674]和[WebResourceResponseReceivedEventArgs：:P opulateResponseContent。][ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsPopulateresponsecontent09628]  
*   在 WebView2 中 ([Microsoft Defender 应用程序防护) WDAG。][WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]  
*   添加了[用于可视化托管的 SystemCursorId。][ReferenceWin32Icorewebview2experimentalcompositioncontroller2GetSystemcursorid10674]  
*   为可视化托管中的输入方法添加了修复 Bug。  
*   删除了使用 `version.lib` WebView2 静态库时的要求。  
    
#### .NET  

*   更新 [了 CoreWebView2][DotnetApiMicrosoftWebWebview2CoreCorewebview2] 类以公开 `CoreWebView2Environment` 变量。  
*   将命名空间中自定义 EventArgs 类的实现更改为 `Microsoft.Web.WebView2.Core` [System.EventArgs][DotnetApiSystemEventargs] 或 [System.ComponentModel.CancelEventArgs 的子类][DotnetApiSystemComponentmodelCancelEventargs]。  \ ([\#250][GithubMicrosoftedgeWebviewfeedbackIssue250]\)   
*   增加了对 [WinForms 中 CoreWebView2CreationProperties][DotnetApiMicrosoftWebWebview2Winforms] 的支持。  \ ([\#204][GithubMicrosoftedgeWebviewfeedbackIssue204]\) 
*   添加了 [WebResourceRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested] .NET API。  \ ([\#219][GithubMicrosoftedgeWebviewfeedbackIssue219]\) 。  
*   将 WinForms Designer [Source][DotnetApiMicrosoftWebWebview2WinformsWebview2Source] 属性更新为默认值或重置为 null。  \ ([\#177][GithubMicrosoftedgeWebviewfeedbackIssue177]\) 。  
*   更新了 webView2 WebView2.Init () ，以支持小于 100% 的 DPI 模式。  \ ([\#432][GithubMicrosoftedgeWebviewfeedbackIssue432]\) 。  
*   更新 [了 BuildWindowCore][DotnetApiMicrosoftWebWebview2WpfWebview2Buildwindowcore] 和 [DestroyWindowCore][DotnetApiMicrosoftWebWebview2WpfWebview2Destroywindowcore] 以提高稳定性。  \ ([\#382][GithubMicrosoftedgeWebviewfeedbackIssue382]\) 。  
*   更新了 .NET 加载程序基，以在进程位（而不是操作系统体系结构）上加载。  \ ([\#431][GithubMicrosoftedgeWebviewfeedbackIssue431]\) 。  
*   重命名 `EdgeNotFoundExpection` 为 [WebView2RuntimeNotFoundException][DotnetApiMicrosoftWebWebview2CoreWebview2runtimenotfoundexception]。  
    
## 1.0.622.22  

发布日期：2020 年 10 月 19 日  

[NuGet 包][NuGetGallery1.0.622.22] \|WebView2 运行时版本 86.0.616.0 或更高版本。  

#### 常规  

> [!IMPORTANT]
> **公告**：Win32 C/C++ WebView2 现已正式发布 \ (GA\) 。  从此版本开始，发布 SDK 是向前兼容的。  有关详细信息，请导航到 [GA 公告博客文章][WindowsBlogsMsedgedevEdgeWebview2GeneralAvailability]。  

*   [常青 WebView2 运行时和安装程序][Webview2ConceptsDistributionUnderstandRuntimeInstaller] 是 GA。  适用于常青 WebView2 运行时的引导程序、引导程序下行链接和独立安装程序在 [Microsoft Edge WebView2 上可用][MicrosoftDeveloperMicrosoftEdgeWebView2]。  [WebView2Samples][GithubMicrosoftedgeWebview2samplesMain]存储库也提供了安装工作流的示例代码。  
*   [固定版本模式][Webview2ConceptsDistributionFixedVersionMode] 可用于开发人员预览。  
    
## 0.9.622.11  

发布日期：2020 年 9 月 10 日  

[NuGet 包][NuGetGallery0.9.622.11] \|WebView2 运行时版本 86.0.616.0 或更高版本。  

#### 常规  

*   > [!IMPORTANT]
    > **公告**：此 SDK 是 WebView2 Win32 C/C++ GA 候选发布。  GA 版本应该使用相同的 API 接口和功能。  
    
*   断开连接 [的浏览器策略][DeployedgeMicrosoftEdgePolicies]。  
*   在 [WebView2 环境选项上添加了 AllowSingleSignOnUsingOSPrimaryAccount][ReferenceWin32Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount09622] 属性，以打开 WebView 的条件访问。  
*   进行了 `ICoreWebView2NewWindowRequestedEventArgs` 更新以包括[WindowFeatures][ReferenceWin32Icorewebview2newwindowrequestedeventargsGetWindowfeatures09622]属性和关联的[ICoreWebView2WindowFeatures。][ReferenceWin32Icorewebview2windowfeatures09622]  \ ([\#293][GithubMicrosoftedgeWebviewfeedbackIssue293]\) 。  
*   更新 `System.Windows.Rect`  为 `System.Drawing.Rectangle` 使用 `System.Windows.Rect` \ ([\#235][GithubMicrosoftedgeWebviewfeedbackIssue235]\) 。  
*   更新了 NewWindowRequested 事件以处理 `window.open()` 不带参数的请求。  \ ([\#293][GithubMicrosoftedgeWebviewfeedbackIssue293]\) 。  
*   [使用指定的 AdditionalBrowserArguments][ReferenceWin32Icorewebview2environmentoptionsPutAdditionalbrowserarguments09622] 不会替代环境变量或 `ICoreWebView2EnvironmentOptions` 注册表值。  有关详细信息，请导航到 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32IdlCreatecorewebview2environmentwithoptions09622]。  
    
## 0.9.579  

发布日期：2020 年 7 月 20 日  

[NuGet 包][NuGetGallery0.9.579] \|Microsoft Edge 版本 86.0.579.0。  

#### 常规  

*   > [!IMPORTANT]
    > **公告**：已发布用于预览的常青 WebView2 运行时和安装程序。  有关详细信息，请导航到["WebView2 的分发"。][Webview2ConceptsDistributionUnderstandRuntimeInstaller]  
    
*   > [!IMPORTANT]
    > **公告**：下一个 SDK 发布后，不再支持以下 WebView2 SDK 版本。  
    > 
    > *   [0.8.190](#08190)  
    > *   [0.8.230](#08230)  
    > *   [0.8.270](#08270)  
    > *   [0.8.314](#08314)  
    > *   [0.8.355](#08355)  
    > 
    > WebView2 SDK 版本在发布时也标记为nuget.org。 WebView2 建议使用最新版本的 WebView2 保持最新。  
    
*   添加了 WebView 工作线程改进。  \ ([\#318][GithubMicrosoftedgeWebviewfeedbackIssue318]\) 。  
*   在 WebView 中关闭弹出窗口阻止程序。  有关详细信息，请导航到 [事件中的 IsUserInitiated][ReferenceWin32Icorewebview2newwindowrequestedeventargsGetIsuserinitiated09538] `NewWindowRequested` 属性。  
*   确保为运行 WebView 导航启动事件 `about:blank` 。  现在，所有导航都运行事件，但不支持和忽略 `NavigationStarting` `about:blank` 取消或 `srcdoc` iframe。  
*   在 `edge://` WebView 中阻止了一些 URI 方案。  
*   在 WebView2 环境选项上添加了实验性 [IsSingleSignOnUsingOSPrimaryAccountEnabled][ReferenceWin32Icorewebview2experimentaloptionsGetIssinglesignonusingosprimaryaccountenabled09538] 属性，以打开 WebView 的条件访问。  
*   添加了实验 [性 WebResourceResponseReceived][ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived09538] 事件，该事件在 WebView 接收并处理来自 WebResource 请求的响应之后运行。  响应对象中包含身份验证标头（如果有）。  
    
#### .NET  

*   改进了 WPF 焦点处理。  \ ([\#185][GithubMicrosoftedgeWebviewfeedbackIssue185]\) 。  
*   在 `ZoomFactor` WPF Webview2 控制器上添加了属性。  
    
## 0.9.538  

[NuGet 包][NuGetGallery0.9.538] \|Microsoft Edge 版本 85.0.538.0。  

#### 常规  

*   放弃对 WebView2 SDK 版本 [0.8.149 的支持](#08149)。  WebView2 建议使用最新版本的 WebView2 保持最新。  
*   更新了组策略，以考虑何时修改 Microsoft Edge 浏览器的配置文件路径 \ ([#179][GithubMicrosoftedgeWebviewfeedbackIssue179]\) 。  
    
#### Win32 C/C++  

*   添加了 [ICoreWebView2ExperimentalNewWindowRequestedEventArgs：：get_WindowFeatures，][ReferenceWin32Icorewebview2experimentalnewwindowrequestedeventargsGetWindowfeatures09538]在运行时触发，并且与 `window.open()` [ICoreWebView2ExperimentalWindowFeatures][ReferenceWin32Icorewebview2experimentalwindowfeatures09538] \ ([#70][GithubMicrosoftedgeWebviewfeedbackIssue70]\) 关联。  
*   > [!IMPORTANT]
    > **中断更改**：弃用[CreateCoreWebView2EnvironmentWithDetails，][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithdetails09488]并替换为[CreateCoreWebView2EnvironmentWithOptions。][ReferenceWin32IdlCreatecorewebview2environmentwithoptions09538]  
    
*   > [!IMPORTANT]
    > **中断更改**：为了确保 WebView2 API 与 Windows API 命名约定一致，WebView 团队更新了以下名称。  
    > 
    > *   [AreRemoteObjectsAllowed][ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09488] 现在是 [AreHostObjectsAllowed][ReferenceWin32Icorewebview2settingsGetArehostobjectsallowed09538]。  
    
*   更新 [了 AddHostObjectToScript][ReferenceWin32Icorewebview2Addhostobjecttoscript09538]。  原始主机对象序列化器标记现在设置为代理对象。  然后，当在 JavaScript 回调 \ (#148 \) 中作为参数传递时，主机 [对象序列化器][GithubMicrosoftedgeWebviewfeedbackIssue148]标记将序列化回主机) 。  
    
#### .NET (0.9.538 预发行版)   

*   发布的 WinForms 和 WPF WebView2API 示例是 WebView2 SDK 的全面指南。  有关详细信息，请导航到["示例存储库"。][GithubMicrosoftedgeWebview2samplesMain]  
*   添加了对可视托管和窗口功能实验 [API 的支持][ConceptsVersioningExperimentalApis]。  
*   > [!IMPORTANT]
    > **中断更改**：以下延迟现在实现 IDisposable：ScriptDialogOpening、NewWindowRequested、WebResourceRequested 和[PermissionRequested。][DotnetApiMicrosoftWebWebview2CoreCorewebview2Permissionrequested] [][DotnetApiMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening] [][DotnetApiMicrosoftWebWebview2CoreCorewebview2Newwindowrequested] [][DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]  
    
*   添加了 [GetAvailableBrowserVersionString 和][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring] [CompareBrowserVersions][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions] 作为 [CoreWebView2Environment][DotnetApiMicrosoftWebWebview2CoreCorewebview2environment] 静态。  
    
## 0.9.515-prerelease  

[NuGet 包][NuGetGallery0.9.515-prerelease] \|Microsoft Edge 版本 84.0.515.0。  

*   > [!IMPORTANT]
    > **公告**：WebView2 现在支持预发行包中的 .NET Framework 4.6.2 或更高版本和 .NET Core 3.0 或更高版本上的 Windows Forms **和**WPF。  
    
*   有关生成 WPF 应用的信息，请导航到 [WPF][GettingstartedWpf] 入门指南和适用于 WPF 特定 API 的 WebView2 [WPF][DotnetApiMicrosoftWebWebview2Wpf] 参考。  
*   有关生成 Windows 窗体应用的信息，请导航到 [Windows 窗体][GettingstartedWinforms] 入门指南和适用于 Windows 窗体特定 API 的 WebView2 [Windows][DotnetApiMicrosoftWebWebview2Winforms] 窗体参考。  
*   有关 CoreWebView2 API 的信息，请导航到 [.NET 参考][DotnetApiMicrosoftWebWebview2Core]。  
*   > [!CAUTION]
    > **已知问题**：WebView 团队了解预发行版中在将来版本中要解决的一些问题。  
    > 
    > *   **DPI 感知**：适用于 WPF 的 WebView2 当前无法识别 DPI。  在高 DPI 监视器上初始化 WebView2 时，存在一个已知问题，即 WebView 最初初始化为窗口的一小部分，直到调整窗口大小。  
    > *   **WPF 设计器**：WPF 设计器当前不受支持。  通过直接在文本编辑器中修改相应的 XAML，在应用中添加 WebView2 控件。  
    
## 0.9.488  

[NuGet 包][NuGetGallery0.9.488] \|Microsoft Edge 版本 84.0.488.0。  

*   > [!IMPORTANT]
    > **公告**：从即将推出的 Microsoft Edge 版本 83 开始，Evergreen WebView 不再面向稳定浏览器通道。  相反，它面向另一组二进制文件，品牌为 [Evergreen WebView2 Runtime，][ConceptsDistributionEvergreenMode]可以通过 WebView 团队当前正在开发的安装程序进行链接安装。  有关详细信息，请导航到["应用分发"。][ConceptsDistribution]  
    
*   > [!IMPORTANT]
    > 公告 **：今后**，WebView 团队将发布两个程序包：一个包含实验性 API \ (的预发布程序包，供你试用\) 以及一个稳定的发布包，其中具有稳定的 API \ (用于置信度\) 。  若要了解差异，请导航到"[了解浏览器版本和 WebView2"。][ConceptsVersioning]  
    
*   > [!IMPORTANT]
    > **中断更改**：为了确保 WebView2 API 与 Windows API 命名约定保持一致，WebView 团队更新了以下接口的名称。  
    > 
    > *   `CORE_WEBVIEW2_*` 前缀现在 `COREWEBVIEW2_*` 为 。  
    > *   [GetCoreWebView2BrowserVersionInfo][ReferenceWin32Webview2IdlGetcorewebview2browserversioninfo09430] 现在是 [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring09488]。  
    > *   [get_BrowserVersionInfo][ReferenceWin32Icorewebview2environmentGetBrowserversioninfo09430][现在][ReferenceWin32Icorewebview2environmentGetBrowserversionstring09488]get_BrowserVersionString。  
    > *   [AddRemoteObject][ReferenceWin32Icorewebview2Addremoteobject09430] 现在是 [AddHostObjectToScript][ReferenceWin32Icorewebview2Addhostobjecttoscript09488]。  
    > *   [RemoveRemoteObject][ReferenceWin32Icorewebview2Removeremoteobject09430] 现在是 [RemoveHostObjectFromScript][ReferenceWin32Icorewebview2Removehostobjectfromscript09488]。  
    > *   `chrome.webview.remoteObjects` is now `chrome.webview.hostObjects` .  
    
*   > [!IMPORTANT]
    > **中断更改** `AddRemoteObject` ：JS 代理方法也重命名。  
    > 
    > *   `getLocal` is now `getLocalProperty` .  
    > *   `setLocal` is now `setLocalProperty` .  
    > *   `getRemote` is now `getHostProperty` .  
    > *   `setRemote` is now `setHostProperty` .  
    > *   `applyRemote` is now `applyHostFunction` .  
    
*   > [!IMPORTANT]
    > **中断更改**：弃用[CreateCoreWebView2EnvironmentWithDetails，][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithdetails09488]并替换为[CreateCoreWebView2EnvironmentWithOptions。][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions09488]  
    
*   添加了 [FrameNavigationCompleted][ReferenceWin32Icorewebview2AddFramenavigationcompleted09488] 事件。  现在，当 iframe 完成导航时，将运行一个事件并返回导航和导航 ID 的成功。  
*   添加了 [ICoreWebView2EnvironmentOptions][ReferenceWin32Icorewebview2environmentoptions09488] 接口，可用于确定应用面向的 WebView2 运行时的版本。  
*   添加了 [IsBuiltInErrorPageEnabled][ReferenceWin32Icorewebview2settingsGetIsbuiltinerrorpageenabled09488] 设置。  现在，对于导航失败和呈现进程失败，您可以选择打开或关闭内置错误网页。  
*   更新了远程对象注入以支持 .NET `IDispatch` 实现 \ ([#113][GithubMicrosoftedgeWebviewfeedbackIssue113]\) 。  
*   更新 [了 NewWindowRequested][ReferenceWin32Icorewebview2AddNewwindowrequested09488] 事件以处理来自上下文菜单 \ (#108 [\) ][GithubMicrosoftedgeWebviewfeedbackIssue108]的请求。  
*   发布了第一个单独的 WebView2 预发行版包，你可以访问可视托管 API。  WebView 团队更新 [了 APISample，][GithubMicrosoftedgeWebview2samplesMain] 以包含新的实验 API。  
    
    *   添加了 [ICoreWebView2ExperimentalCompositionController][ReferenceWin32Icorewebview2experimentalcompositioncontroller09488] 接口，以连接到合成树并为 WebView 提供输入。  
    *   添加了 [ICoreWebView2ExperimentalPointerInfo，][ReferenceWin32Icorewebview2experimentalpointerinfo09488]其中包含来自 `POINTER_INFO` .  此对象将传递给 SendPointerInput，以将指针输入注入 WebView。  
    *   添加了 [ICoreWebView2ExperimentalCursorChangedEventHandler，][ReferenceWin32Icorewebview2experimentalcursorchangedeventhandler09488]告知应用何时应更改 WebView 上的鼠标光标。  当鼠标悬停在 WebView 中的文本框上时，光标会从箭头变为选择器。  The `cursor` property on the `CompositionController` tells the app what the mouse cursor should currently be for the WebView.  
    
## 0.9.430  

[NuGet 包][NuGetGallery0.9.430] \|Microsoft Edge 版本 82.0.430.0。  

WebView2 SDK 是官方 Win32 C++ Beta 版本，它包含来自反馈的多项功能请求。  WebView 团队尝试通过发生重大变化来限制发布数量。  作为一般可用性方法，Beta 版本中包含一些重大更改。  

*   > [!IMPORTANT]
    > **中断**更改：随着最终发布接近，WebView 团队将 *前缀 IWebView2WebView*   重命名为 *ICoreWebView2，*   以确保 WebView2 API 符合 Windows API 命名约定。  此外，为了从 UI 框架利用 WebView2 SDK，WebView 团队分为 `ICoreWebView2` [ICoreWebView2][ReferenceWin32Icorewebview209430]和[ICoreWebView2Host。][ReferenceWin32Icorewebview2host09430]  `ICoreWebView2Host` 支持调整大小、显示和隐藏、焦点和其他与窗口和合成相关的功能。  ICoreWebView2 支持所有其他 WebView2 功能。  若要了解有关合并更改的信息，请导航到 [WebView2][GithubMicrosoftedgeWebview2samplesPr17] [APISample][GithubMicrosoftedgeWebview2samplesMain] 项目中的 WebView2 拉取请求。  
    
*   > [!IMPORTANT]
    > **重大更改**：将[DocumentStateChanged][ReferenceWin32Iwebview2webviewAddDocumentstatechanged08190]拆分为三个组件[：SourceChanged、ContentLoading][ReferenceWin32Icorewebview2AddSourcechanged09430]和[HistoryChanged。][ReferenceWin32Icorewebview2AddHistorychanged09430] [][ReferenceWin32Icorewebview2AddContentloading09430]  现在，当源 URL 更改时 `SourceChanged` ，将运行该事件。  当历史记录状态更改时 `HistoryChanged` ，将运行事件。  加载新文档时，该事件在初始脚本 `ContentLoading` 之前运行。  
    
*   添加了对 ARM64 体系结构的支持。  
*   添加了对触摸屏设备的 (SIP\) 支持。  
*   增加了对 Windows Server 2008 R2、Windows Server 2012、Windows Server 2012 R2 和 Windows Server 2016 的支持。  
*   添加了 [NotifyParentWindowPositionChanged，][ReferenceWin32Icorewebview2hostNotifyparentwindowpositionchanged09430] 使状态栏在窗口模式下跟随窗口。  此外，在无窗口模式下实现更改，以便辅助功能正常工作。  
*   添加了 [AreRemoteObjectsAllowed][ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09430] 设置，以全局控制网页是否可以由任何远程对象访问。  默认情况下， `AreRemoteObjectsAllowed` 启用，因此 [AddRemoteObject][ReferenceWin32Icorewebview2Addremoteobject09430] 添加的远程对象可从网页访问。  关闭 `AreRemoteObjectsAllowed` 后，无法从网页访问对象。  更改将应用于下一个导航事件。  
*   添加了[IsZoomControlEnabled][ReferenceWin32Icorewebview2settingsGetIszoomcontrolenabled09430]设置，以防止用户使用 \ (或 + 鼠标滚轮 `ctrl` + `+` `ctrl` + `-` `ctrl` \) 。  关闭该设置时 [，put_ZoomFactor][ReferenceWin32Icorewebview2hostPutZoomfactor09430] 设置缩放。  
*   将 ZoomFactor 更改为仅应用于当前 WebView。  对当前 WebView 的缩放更改不会影响导航到使用同一源网站的其他 WebView。  有关详细信息，请 [导航到][ReferenceWin32Icorewebview2hostGetZoomfactor09430]get_ZoomFactor。  
*   Hid ZoomView UI for WebView \ ([#95][GithubMicrosoftedgeWebviewfeedbackIssue95]\) 。  
*   添加了 [SetBoundsAndZoomFactor][ReferenceWin32Icorewebview2hostSetboundsandzoomfactor09430]。  现在，你可以同时设置 WebView 的缩放比例和边界。  
*   添加了 [WindowCloseRequested][ReferenceWin32Icorewebview2AddWindowcloserequested09430] 事件。  有关详细信息，请导航到 [add_WindowCloseRequested][ReferenceWin32Icorewebview2AddWindowcloserequested09430] \ ([#119][GithubMicrosoftedgeWebviewfeedbackIssue119]\) 。  
*   添加了对 `beforeunload` JavaScript 对话框事件的对话框类型的支持，并添加了[][ReferenceWin32Icorewebview2CoreWebview2ScriptDialogKind09430]CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD条目。  
*   向 HttpRequestHeaders 添加了[GetHeaders，][ReferenceWin32Icorewebview2httprequestheadersGetheaders09430][将 GetHeader][ReferenceWin32Icorewebview2httpresponseheadersGetheader09430]添加到 HttpResponseHeaders，将 get_HasCurrentHeader[属性添加到][ReferenceWin32Icorewebview2httpheaderscollectioniteratorGetHascurrentheader09430]HttpHeadersCollectionIterator。  
*   > [!IMPORTANT]
    > **中断更改**： 修改 `DevToolsProtocolEventReceived` 的行为。  现在，你可以为特定的[DevTools 协议事件创建 DevToolsProtocolEventReceiver，][ReferenceWin32Icorewebview2devtoolsprotocoleventreceiver09430]并订阅/取消订阅使用[][ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverAddDevtoolsprotocoleventreceived09430]add_DevToolsProtocolEventReceived / [remove_DevToolsProtocolEventReceived。][ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverRemoveDevtoolsprotocoleventreceived09430]  
    
*   > [!IMPORTANT]
    > **Breaking Change**： Changed `WebMessageReceivedEventArgs` [get_WebMessageAsString][ReferenceWin32Iwebview2webmessagereceivedeventargsGetWebmessageasstring08190] Property to a [TryGetWebMessageAsString][ReferenceWin32Icorewebview2webmessagereceivedeventargsTrygetwebmessageasstring09430] method.  
    
*   > [!IMPORTANT]
    > **Breaking Change**： Changed `AcceleratorKeyPressedEventArgs` [Handle][ReferenceWin32Iwebview2acceleratorkeypressedeventargsHandle08190] 方法更改为 [get_Handled][ReferenceWin32Icorewebview2acceleratorkeypressedeventargsGetHandled09430] 属性。  
    
## 0.8.355  

[NuGet 包][NuGetGallery0.8.355] \|Microsoft Edge 版本 80.0.355.0。  

*   发布的 WebView2API 示例是 WebView2 SDK 的全面指南。  有关详细信息，请导航到 [API 示例][GithubMicrosoftedgeWebview2samplesApisample]。  
*   添加了对英语 \ (#30 [\) ][GithubMicrosoftedgeWebviewfeedbackIssue30]之外的所有语言的 IME 支持。  
*   更新了事件的 API 图 `WebResourceRequested` 面以响应 Bug 报告。  现在，已弃用创建时同时指定筛选器和事件。  若要创建 Web 资源请求的事件，add_WebResourceRequested[][ReferenceWin32Iwebview2webview5AddWebresourcerequested08190]添加事件，使用[AddWebResourceRequestedFilter][ReferenceWin32Iwebview2webview5Addwebresourcerequestedfilter08190]添加筛选器。  [RemoveWebResourceRequestedFilter][ReferenceWin32Iwebview2webview5Removewebresourcerequestedfilter08190] 将删除 \ ([#36][GithubMicrosoftedgeWebviewfeedbackIssue36]\) \ ([#74][GithubMicrosoftedgeWebviewfeedbackIssue74]\) 。  
*   > [!IMPORTANT]
    > **中断更改**：修改的全屏行为。  已弃用 [IsFullScreenAllowed][ReferenceWin32Iwebview2settingsGetIsfullscreenallowedDeprecated08190]。  现在，默认情况下，如果 WebView \ (中的元素（如视频\) ）设置为全屏，它将填充 WebView 的界限。  使用[ContainsFullScreenElementChanged][ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandler08190]事件[][ReferenceWin32Iwebview2webview5GetContainsfullscreenelement08190]和get_ContainsFullScreenElement指定当元素要进入全屏模式时应用应如何调整 WebView 的大小。  
    
## 0.8.314  

[NuGet 包][NuGetGallery0.8.314] \|Microsoft Edge 版本 80.0.314.0。  

*   添加了对 Windows 7、Windows 8 和 Windows 8.1 的支持。  
*   添加了Visual Studio和Visual Studio WebView2 的代码调试支持。  现在，从 IDE 在 WebView2 中调试脚本。  有关详细信息，请导航到 [使用 WebView2 控件进行开发时如何调试][HowtoDebug]。  
*   为 WebView2 中正在运行的脚本添加了该脚本，用于从应用的 Win32 组件访问 IDispatch 对象并访问 `Native Object Injection` IDispatch 对象的属性。  有关详细信息，请导航到 [AddRemoteObject][ReferenceWin32Iwebview2webview4Addremoteobject08190] \ ([#17][GithubMicrosoftedgeWebviewfeedbackIssue17]\) 。  
*   已 `AcceleratorKeyPressed` 添加事件。  有关详细信息，请导航到 [add_AcceleratorKeyPressed][ReferenceWin32Iwebview2webview4AddAcceleratorkeypressed08190] \ ([#57][GithubMicrosoftedgeWebviewfeedbackIssue57]\) 。  
*   已关闭 `Context Menus` 。  有关详细信息，请导航到 [put_AreDefaultContextMenusEnabled][ReferenceWin32Iwebview2settings2PutAredefaultcontextmenusenabled08190] \ ([#57][GithubMicrosoftedgeWebviewfeedbackIssue57]\) 。  
*   已 `DPI Awareness` 更新。  现在，WebView 的 DPI 感知与主机应用的 DPI 感知相同。  
    
    > [!NOTE]
    > 如果启动另一个混合应用时 DPI 感知不同于原始 WebView，则新 WebView 不会启动（如果 `user data folder` \ (#1 [][GithubMicrosoftedgeWebviewfeedbackIssue1]\) ）。  
    
*   进行了更新，以便 WebView2 自动拒绝 WebView 中托管的 Web 内容所提示的通知 `Notification Change Behavior` 权限请求。  
    
## 0.8.270  

[NuGet 包][NuGetGallery0.8.270] \|Microsoft Edge 版本 78.0.270.0。  

*   添加了 `DocumentTitleChanged` 事件以指示文档标题更改 \ ([\#27][GithubMicrosoftedgeWebviewfeedbackIssue27]\) 。  
*   添加了 `GetWebView2BrowserVersionInfo` API \ ([\#18][GithubMicrosoftedgeWebviewfeedbackIssue18]\) 。  
*   已 `NewWindowRequested` 添加事件。  
*   更新 `CreateWebView2EnvironmentWithDetails` 了要删除的函数 `releaseChannelPreference` 。  有关函数详细信息， `CreateWebView2EnvironmentWithDetails` 请导航到 [CreateWebView2EnvironmentWithDetails][ReferenceWin32WebView2IdlCreatewebview2environmentwithdetails08190]。  注册表和环境变量替代仍受支持。  除非重写，否则使用默认通道首选项。  
    在频道搜索期间，WebView 团队将跳过任何与 WebView2 SDK 不兼容的以前频道版本。  
    WebView 团队选择更稳定的频道，以确保最终用户的行为最一致。  使用最新的 Canary 版本进行测试时，应在启动应用之前创建一个脚本，将环境变量设置为 `WEBVIEW2_RELEASE_CHANNEL_PREFERENCE` `1` 该脚本。  
*   使用 `CreateWebView2EnvironmentWithDetails` 用于选择未指定时 `userDataFolder` 的逻辑更新函数。  有关函数详细信息， `CreateWebView2EnvironmentWithDetails` 请导航到 [CreateWebView2EnvironmentWithDetails][ReferenceWin32WebView2IdlCreatewebview2environmentwithdetails08190]。  如果您之前使用默认位置，则切换到新 SDK 时，默认设置为 \ (设置为主机代码目录中 `userDataFolder` 的新位置\) 并且您的状态也会重置 `userDataFolder` 。  如果主机进程没有写入指定目录的权限，则 `CreateWebView2EnvironmentWithDetails` 函数可能会失败。  你可以将数据从旧目录复制到 `user data folder` 新目录。  
    
## 0.8.230  

[NuGet 包][NuGetGallery0.8.230] \|Microsoft Edge 版本 77.0.230.0。  

*   添加了 `Stop` API 以停止所有导航和挂起的资源提取 \ ([\#28][GithubMicrosoftedgeWebviewfeedbackIssue28]\) 。  
*   向 `.tlb` NuGet 程序包 \ ([\#22 \) 。][GithubMicrosoftedgeWebviewfeedbackIssue22]  
*   向 NuGet 程序包 \ ([\#32 \) ][GithubMicrosoftedgeWebviewfeedbackIssue32]中的安装程序列表添加了 .NET 项目。  
    
## 0.8.190  

[NuGet 包][NuGetGallery0.8.190] \|Microsoft Edge 版本 77.0.190.0。  

*   已 `get_AreDevToolsEnabled` / `put_AreDevToolsEnabled` 添加到控制用户能否打开 DevTools \ ([\#16][GithubMicrosoftedgeWebviewfeedbackIssue16]\) 。  
*   添加到控制状态栏是否显示 `get_IsStatusBarEnabled` / `put_IsStatusBarEnabled` \ ([\#19][GithubMicrosoftedgeWebviewfeedbackIssue19]\) 。  
*   已 `get_CanGoBack` / `GoBack` / `get_CanGoForward` / `GoForward` 添加用于返回和转发导航历史记录。  
*   添加了 HTTP 标头类型 \ (`IWebView2HttpHeadersCollectionIterator` / `IWebView2HttpRequestHeaders` / `IWebView2HttpRequestHeaders` \) ，用于查看和修改 WebView 中的 HTTP 标头。  
*   在 64 位计算机 \ ([\#13 \) ][GithubMicrosoftedgeWebviewfeedbackIssue13]上添加了 32 位 WebView 支持。  
*   向 SDK \ ([\#14 \) ][GithubMicrosoftedgeWebviewfeedbackIssue14]添加了 WebView IDL。  
*   添加了 lib 以支持 `IID\_\*` 接口 ID 对象 \ ([\#12][GithubMicrosoftedgeWebviewfeedbackIssue12]\) 。  
*   添加了 DLL 文件的路径、链接和自动复制到 SDK 中的 NuGet `TARGET` 文件。  
*   在脚本中打开 `window.open()` 请求。  
    
## 0.8.149  

[NuGet 包][NuGetGallery0.8.149] \|Microsoft Edge 版本 76.0.149.0。  

初始开发人员预览版。  

<!-- Links -->  

[VersioningDoc]: ./concepts/versioning.md#matching-webview2-runtime-versions
[ConceptsDistribution]: ./concepts/distribution.md "使用 WebView2 应用程序的应用程序|Microsoft Docs"  
[ConceptsDistributionEvergreenMode]: ./concepts/distribution.md#evergreen-distribution-mode "常青分布模式 - 使用 WebView2 |Microsoft Docs"  
[Webview2ConceptsDistributionFixedVersionMode]: ./concepts/distribution.md#fixed-version-distribution-mode "固定版本分发模式 - 使用 WebView2 |Microsoft Docs"  
[Webview2ConceptsDistributionUnderstandRuntimeInstaller]: ./concepts/distribution.md#understanding-the-webview2-runtime "了解 WebView2 运行时和安装程序 - 使用 WebView2 |Microsoft Docs"  
[Webview2ConceptsEnterpriseGroupPoliciesForWebview2]: ./concepts/enterprise.md#group-policies-for-webview2 "WebView2 的组策略 - 管理 WebView2 |Microsoft Docs"  
[ConceptsVersioning]: ./concepts/versioning.md "了解浏览器版本和 WebView2 |Microsoft Docs"  
[ConceptsVersioningExperimentalApis]: ./concepts/versioning.md#experimental-apis "实验性 API - 了解浏览器版本和 WebView2 |Microsoft Docs"  
[GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows Forms 应用中 WebView2 |Microsoft Docs"  
[GettingstartedWpf]: ./gettingstarted/wpf.md "WPF 中 WebView2 |Microsoft Docs"  
[HowtoDebug]: ./howto/debug.md "如何使用 WebView2 控件进行开发时|Microsoft Docs"  

[ReferenceWin32Iwebview2acceleratorkeypressedeventargsHandle08190]: /microsoft-edge/webview2/reference/win32/iwebview2acceleratorkeypressedeventargs?view=webview2-0.8.355&preserve-view=true#handle "Handle - 接口 IWebView2AcceleratorKeyPressedEventArgs |Microsoft Docs"  
[ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandler08190]: /microsoft-edge/webview2/reference/win32/iwebview2containsfullscreenelementchangedeventhandler?view=webview2-0.8.355&preserve-view=true "interface IWebView2ContainsFullScreenElementChangedEventHandler |Microsoft Docs"  
[ReferenceWin32Iwebview2settings2PutAredefaultcontextmenusenabled08190]: /microsoft-edge/webview2/reference/win32/iwebview2settings2?view=webview2-0.8.355&preserve-view=true#put_aredefaultcontextmenusenabled "put_AreDefaultContextMenusEnabled - 接口 IWebView2Settings2 |Microsoft Docs"  
[ReferenceWin32Iwebview2settingsGetIsfullscreenallowedDeprecated08190]: /microsoft-edge/webview2/reference/win32/iwebview2settings?view=webview2-0.8.355&preserve-view=true#get_isfullscreenallowed_deprecated "get_IsFullscreenAllowed_deprecated - 接口 IWebView2Settings |Microsoft Docs"  
[ReferenceWin32Iwebview2webmessagereceivedeventargsGetWebmessageasstring08190]: /microsoft-edge/webview2/reference/win32/iwebview2webmessagereceivedeventargs?view=webview2-0.8.355&preserve-view=true#get_webmessageasstring "get_WebMessageAsString - 接口 IWebView2WebMessageReceivedEventArgs |Microsoft Docs"  
[ReferenceWin32Iwebview2webview4AddAcceleratorkeypressed08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#add_acceleratorkeypressed "add_AcceleratorKeyPressed - 接口 IWebView2WebView4 |Microsoft Docs"  
[ReferenceWin32Iwebview2webviewAddDocumentstatechanged08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview?view=webview2-0.8.355&preserve-view=true#add_documentstatechanged "add_DocumentStateChanged - 接口 IWebView2WebView |Microsoft Docs"  
[ReferenceWin32Iwebview2webview4Addremoteobject08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#addremoteobject "AddRemoteObject - 接口 IWebView2WebView4 |Microsoft Docs"  
[ReferenceWin32Iwebview2webview5AddWebresourcerequested08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#add_webresourcerequested "add_WebResourceRequested - 接口 IWebView2WebView5 |Microsoft Docs"  
[ReferenceWin32Iwebview2webview5Addwebresourcerequestedfilter08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#addwebresourcerequestedfilter "AddWebResourceRequestedFilter - 接口 IWebView2WebView5 |Microsoft Docs"  
[ReferenceWin32Iwebview2webview5GetContainsfullscreenelement08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#get_containsfullscreenelement "get_ContainsFullScreenElement - 接口 IWebView2WebView5 |Microsoft Docs"  
[ReferenceWin32Iwebview2webview5Removewebresourcerequestedfilter08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#removewebresourcerequestedfilter "RemoveWebResourceRequestedFilter - 接口 IWebView2WebView5 |Microsoft Docs"  
[ReferenceWin32WebView2IdlCreatewebview2environmentwithdetails08190]:  /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.8.355&preserve-view=true#createwebview2environmentwithdetails "CreateWebView2EnvironmentWithDetails - 全局|Microsoft Docs"  

[ReferenceWin32Icorewebview209430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2acceleratorkeypressedeventargsGetHandled09430]: /microsoft-edge/webview2/reference/win32/icorewebview2acceleratorkeypressedeventargs?view=webview2-0.9.430&preserve-view=true#get_handled "get_Handled - 接口 ICoreWebView2AcceleratorKeyPressedEventArgs |Microsoft Docs"  
[ReferenceWin32Icorewebview2AddContentloading09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_contentloading "add_ContentLoading - 接口 ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2AddHistorychanged09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_historychanged "add_HistoryChanged - 接口 ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2Addremoteobject09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#addremoteobject "AddRemoteObject - 接口 ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2AddSourcechanged09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_sourcechanged "add_SourceChanged - 接口 ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2AddWindowcloserequested09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_windowcloserequested "add_WindowCloseRequested - 接口 ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2CoreWebview2ScriptDialogKind09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#core_webview2_script_dialog_kind "CORE_WEBVIEW2_SCRIPT_DIALOG_KIND - 接口 ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2devtoolsprotocoleventreceiver09430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs"  
[ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverAddDevtoolsprotocoleventreceived09430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#add_devtoolsprotocoleventreceived "add_DevToolsProtocolEventReceived - 接口 ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs"  
[ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverRemoveDevtoolsprotocoleventreceived09430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#remove_devtoolsprotocoleventreceived "remove_DevToolsProtocolEventReceived - 接口 ICoreWebView2DevToolsProtocolEventReceiver |Microsoft Docs"  
[ReferenceWin32Icorewebview2environmentGetBrowserversioninfo09430]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.430&preserve-view=true#get_browserversioninfo "get_BrowserVersionInfo - 接口 ICoreWebView2Environment |Microsoft Docs"  
[ReferenceWin32Icorewebview2host09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2Host |Microsoft Docs"  
[ReferenceWin32Webview2IdlGetcorewebview2browserversioninfo09430]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.430&preserve-view=true#getcorewebview2browserversioninfo "GetCoreWebView2BrowserVersionInfo - 全局|Microsoft Docs"  
[ReferenceWin32Icorewebview2hostGetZoomfactor09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#get_zoomfactor "get_ZoomFactor - 接口 ICoreWebView2Host |Microsoft Docs"  
[ReferenceWin32Icorewebview2hostNotifyparentwindowpositionchanged09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#notifyparentwindowpositionchanged "NotifyParentWindowPositionChanged - 接口 ICoreWebView2Host |Microsoft Docs"  
[ReferenceWin32Icorewebview2hostPutZoomfactor09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#put_zoomfactor "put_ZoomFactor - 接口 ICoreWebView2Host |Microsoft Docs"  
[ReferenceWin32Icorewebview2hostSetboundsandzoomfactor09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#setboundsandzoomfactor "SetBoundsAndZoomFactor - 接口 ICoreWebView2Host |Microsoft Docs"  
[ReferenceWin32Icorewebview2httpheaderscollectioniteratorGetHascurrentheader09430]: /microsoft-edge/webview2/reference/win32/icorewebview2httpheaderscollectioniterator?view=webview2-0.9.430&preserve-view=true#get_hascurrentheader "get_HasCurrentHeader - 接口 ICoreWebView2HttpHeadersCollectionIterator |Microsoft Docs"  
[ReferenceWin32Icorewebview2httprequestheadersGetheaders09430]: /microsoft-edge/webview2/reference/win32/icorewebview2httprequestheaders?view=webview2-0.9.430&preserve-view=true#getheaders "GetHeaders - 接口 ICoreWebView2HttpRequestHeaders |Microsoft Docs"  
[ReferenceWin32Icorewebview2httpresponseheadersGetheader09430]: /microsoft-edge/webview2/reference/win32/icorewebview2httpresponseheaders?view=webview2-0.9.430&preserve-view=true#getheader "GetHeader - 接口 ICoreWebView2HttpResponseHeaders |Microsoft Docs"  
[ReferenceWin32Icorewebview2Removeremoteobject09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#removeremoteobject "RemoveRemoteObject - 接口 ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09430]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed - 接口 ICoreWebView2Settings |Microsoft Docs"  
[ReferenceWin32Icorewebview2settingsGetIszoomcontrolenabled09430]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_iszoomcontrolenabled "get_IsZoomControlEnabled - 接口 ICoreWebView2Settings |Microsoft Docs"  
[ReferenceWin32Icorewebview2webmessagereceivedeventargsTrygetwebmessageasstring09430]: /microsoft-edge/webview2/reference/win32/icorewebview2webmessagereceivedeventargs?view=webview2-0.9.430&preserve-view=true#trygetwebmessageasstring "TryGetWebMessageAsString - 接口 ICoreWebView2WebMessageReceivedEventArgs |Microsoft Docs"  

[ReferenceWin32Icorewebview2AddFramenavigationcompleted09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_framenavigationcompleted "add_FrameNavigationCompleted - 接口 ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2Addhostobjecttoscript09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#addhostobjecttoscript "AddHostObjectToScript - 接口 ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2AddNewwindowrequested09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_newwindowrequested "add_NewWindowRequested - 接口 ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2environmentGetBrowserversionstring09488]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.488&preserve-view=true#get_browserversionstring " |Microsoft Docs"  
[ReferenceWin32Icorewebview2environmentoptions09488]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.488&preserve-view=true "interface ICoreWebView2EnvironmentOptions |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalcompositioncontroller09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCompositionController |Microsoft Docs"
[ReferenceWin32Icorewebview2experimentalcompositioncontroller09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCompositionController |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalcursorchangedeventhandler09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcursorchangedeventhandler?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCursorChangedEventHandler |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalpointerinfo09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalpointerinfo?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalPointerInfo |Microsoft Docs"  
[ReferenceWin32Icorewebview2Removehostobjectfromscript09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#removehostobjectfromscript "RemoveHostObjectFromScript - 接口 ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09488]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed - 接口 ICoreWebView2Settings |Microsoft Docs"  
[ReferenceWin32Icorewebview2settingsGetIsbuiltinerrorpageenabled09488]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_isbuiltinerrorpageenabled " |Microsoft Docs"  
[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithdetails09488]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithdetails "CreateCoreWebView2EnvironmentWithDetails - 全局|Microsoft Docs"  
[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions09488]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - 全局|Microsoft Docs"  
[ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring09488]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString - 全局|Microsoft Docs"  

[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseAddRasterizationscalechanged]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#add_rasterizationscalechanged "add_RasterizationScaleChanged - 接口 ICoreWebView2ExperimentalController |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetBoundsMode]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_boundsmode "get_BoundsMode - 接口 ICoreWebView2ExperimentalController |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetRasterizationscale]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_rasterizationscale "get_RasterizationScale - 接口 ICoreWebView2ExperimentalController |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetShouldDetectMonitorScaleChanges]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_shoulddetectmonitorscalechanges "get_ShouldDetectMonitorScaleChanges - 接口 ICoreWebView2ExperimentalController |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Core]: /dotnet/api/microsoft.web.webview2.core "Microsoft.Web.WebView2.Core 命名空间|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2Wpf]: /dotnet/api/microsoft.web.webview2.wpf "Microsoft.Web.WebView2.Wpf 命名空间|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2Winforms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 命名空间|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2CoreWebview2runtimenotfoundexception]: /dotnet/api/microsoft.web.webview2.core.webview2runtimenotfoundexception "CoreWebView2.WebView2RuntimeNotFound (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2]: /dotnet/api/microsoft.web.webview2.core.corewebview2 "CoreWebView2 类 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environment]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment "CoreWebView2Environment 类 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.comparebrowserversions "CoreWebView2Environment.CompareBrowserVersions (String， String) Method (Microsoft.Web.WebView2.Core) |Microsoft Docs"
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.getavailablebrowserversionstring "CoreWebView2Environment.GetAvailableBrowserVersionString (String) 方法 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Newwindowrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.newwindowrequested "CoreWebView2.NewWindowRequested (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Permissionrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.permissionrequested "CoreWebView2.PermissionRequested (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]: /dotnet/api/microsoft.web.webview2.core.corewebview2.scriptdialogopening "CoreWebView2.ScriptDialogOpening (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.webresourcerequested "CoreWebView2.WebResourceRequested (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2httprequestheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httprequestheaders "CoreWebView2HttpRequestHeaders 类 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2httpresponseheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httpresponseheaders "CoreWebView2HttpResponseHeaders 类 (Microsoft.Web.WebView2.Core) |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WinformsCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.winforms.corewebview2creationproperties "CoreWebView2CreationProperties 类 (Microsoft.Web.WebView2.Winforms) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Source]: /dotnet/api/microsoft.web.webview2.winforms.webview2.source "Microsoft.Web.Web.WebView2.Winforms (Webview2.Source 类) |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2Buildwindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.buildwindowcore "Microsoft.Web.Web.WebView2.Wpf (的 WebView2.BuildWindowCore) HandleRef (方法) |Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Destroywindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.destroywindowcore "Microsoft.Web.Web.WebView2.Wpf (的 WebView2.DestroyWindowCore) HandleRef (方法) |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2Acceleratorkeypressed]: /dotnet/api/microsoft.web.webview2.wpf.webview2.acceleratorkeypressed "microsoft.web.webview2.wpf.webview2.acceleratorkeypressed |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Corewebview2initializationcompletedeventargs]: /dotnet/api/microsoft.web.webview2.core.corewebview2initializationcompletedeventargs "CoreWebView2InitializationCompletedEventArgs 类|Microsoft Docs"  

[ReferenceWin32Icorewebview2Addhostobjecttoscript09538]: /microsoft-edge/webview2/reference/win32/icorewebview2#addhostobjecttoscript?view=webview2-0.9.538&preserve-view=true "AddHostObjectToScript - 接口 ICoreWebView2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-0.9.538-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived - 接口 ICoreWebView2Experimental |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentaloptionsGetIssinglesignonusingosprimaryaccountenabled09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironmentoptions?view=webview2-0.9.538-prerelease&preserve-view=true#get_issinglesignonusingosprimaryaccountenabled "get_IsSingleSignOnUsingOSPrimaryAccountEnabled - 接口 ICoreWebView2ExperimentalEnvironmentOptions |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalnewwindowrequestedeventargsGetWindowfeatures09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalnewwindowrequestedeventargs?view=webview2-0.9.538-prerelease&preserve-view=true#get_windowfeatures "get_WindowFeatures - 接口 ICoreWebView2ExperimentalNewWindowRequestedEventArgs |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalwindowfeatures09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwindowfeatures?view=webview2-0.9.538-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWindowFeatures |Microsoft Docs"  
[ReferenceWin32Icorewebview2newwindowrequestedeventargsGetIsuserinitiated09538]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.538&preserve-view=true#get_isuserinitiated "get_IsUserInitiated ICoreWebView2NewWindowRequestedEventArgs |Microsoft Docs"  
[ReferenceWin32Icorewebview2settingsGetArehostobjectsallowed09538]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.538&preserve-view=true#get_arehostobjectsallowed "get_AreHostObjectsAllowed - 接口 ICoreWebView2Settings |Microsoft Docs"  
[ReferenceWin32IdlCreatecorewebview2environmentwithoptions09538]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.538&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - 全局|Microsoft Docs"  

[ReferenceWin32Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount09622]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#get_allowsinglesignonusingosprimaryaccount "get_AllowSingleSignOnUsingOSPrimaryAccount - 接口 ICoreWebView2EnvironmentOptions |Microsoft Docs"  
[ReferenceWin32Icorewebview2environmentoptionsPutAdditionalbrowserarguments09622]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#put_additionalbrowserarguments "put_AdditionalBrowserArguments - 接口 ICoreWebView2EnvironmentOptions |Microsoft Docs"  
[ReferenceWin32Icorewebview2newwindowrequestedeventargsGetWindowfeatures09622]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.622&preserve-view=true#get_windowfeatures "get_WindowFeatures - 接口 ICoreWebView2NewWindowRequestedEventArgs |Microsoft Docs"  
[ReferenceWin32Icorewebview2windowfeatures09622]: /microsoft-edge/webview2/reference/win32/icorewebview2windowfeatures?view=webview2-0.9.622&preserve-view=true "interface ICoreWebView2WindowFeatures |Microsoft Docs"  
[ReferenceWin32IdlCreatecorewebview2environmentwithoptions09622]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.622&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions - 全局|Microsoft Edge"  
[ReferenceWin32Icorewebview2experimentalenvironment09628]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironment?view=webview2-0.9.628-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalEnvironment |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsPopulateresponsecontent09628]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponsereceivedeventargs?view=webview2-0.9.628-prerelease&preserve-view=true#populateresponsecontent "PopulateResponseContent - 接口 ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs |Microsoft Docs"  

[ReferenceWin32Icorewebview2experimentalAddDomcontentloaded10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#add_domcontentloaded "add_DOMContentLoaded - 接口 ICoreWebView2Experimental |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived - 接口 ICoreWebView2Experimental |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalGetCookiemanager10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#get_cookiemanager "get_CookieManager - 接口 ICoreWebView2Experimental |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalGetEnvironment10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#get_environment "get_Environment - 接口 ICoreWebView2Experimental |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalNavigatewithwebresourcerequest10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#navigatewithwebresourcerequest "NavigateWithWebResourceRequest - 接口 ICoreWebView2Experimental |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalcompositioncontroller2GetSystemcursorid10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller2#get_systemcursorid?view=webview2-1.0.674-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalwebresourceresponseview10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalwebresourceresponseviewGetcontent10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true#getcontent "GetContent - 接口 ICoreWebView2ExperimentalWebResourceResponseView |Microsoft Docs"  

[ReferenceWin32Icorewebview2experimentalcompositioncontroller3]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller3?view=webview2-1.0.721-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCompositionController3 |Microsoft Docs"  

[DeployedgeMicrosoftEdgePolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge - 策略|Microsoft Docs"  
[DeployedgeMicrosoftEdgeWebviewPolicies]: /deployedge/microsoft-edge-webview-policies "Microsoft Edge WebView2 - 策略|Microsoft Docs"  

[WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]: /windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview "Microsoft Defender 应用程序防护 (Windows 10) - Windows 安全|Microsoft Docs"

[DotnetApiSystemComponentmodelCancelEventargs]: /dotnet/api/system.componentmodel.canceleventargs "System.ComponentModel (CancelEventArgs 类) |Microsoft Docs"  
[DotnetApiSystemEventargs]: /dotnet/api/system.eventargs "EventArgs 类 (系统) |Microsoft Docs"  
[DotnetStandardAssemblyStrongNamed]: /dotnet/standard/assembly/strong-named "强名称程序集|Microsoft Docs"  

[GithubMicrosoftedgeWebviewfeedbackIssue1]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/1 "MicrosoftEdge/WebViewFeedback 问题 1 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue12]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/12 "MicrosoftEdge/WebViewFeedback 问题 12 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue13]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/13 "MicrosoftEdge/WebViewFeedback 问题 13 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue14]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/14 "MicrosoftEdge/WebViewFeedback 问题 14 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue16]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/16 "MicrosoftEdge/WebViewFeedback 问题 16 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue17]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/17 "MicrosoftEdge/WebViewFeedback 问题 17 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue18]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/18 "MicrosoftEdge/WebViewFeedback 问题 18 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue19]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/19 "MicrosoftEdge/WebViewFeedback 问题 19 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue22]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/22 "MicrosoftEdge/WebViewFeedback 问题 22 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue27]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/27 "MicrosoftEdge/WebViewFeedback 问题 27 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue28]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/28 "MicrosoftEdge/WebViewFeedback 问题 28 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue30]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/30 "MicrosoftEdge/WebViewFeedback 问题 30 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue32]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/32 "MicrosoftEdge/WebViewFeedback 问题 32 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue36]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/36 "MicrosoftEdge/WebViewFeedback 问题 36 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue57]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/57 "MicrosoftEdge/WebViewFeedback 问题 57 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue70]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/70 "MicrosoftEdge/WebViewFeedback 问题 70 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue74]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/74 "MicrosoftEdge/WebViewFeedback 问题 74 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue95]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/95 "MicrosoftEdge/WebViewFeedback 问题 95 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue108]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/108 "MicrosoftEdge/WebViewFeedback 问题 108 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue113]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/113 "MicrosoftEdge/WebViewFeedback 问题 113 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue119]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/119 "MicrosoftEdge/WebViewFeedback 问题 119 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue131]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/131 "MicrosoftEdge/WebViewFeedback 问题 131 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue148]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/148 "MicrosoftEdge/WebViewFeedback 问题 148 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue168]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/168 "MicrosoftEdge/WebViewFeedback 问题 168 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue177]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/177 "MicrosoftEdge/WebViewFeedback 问题 177 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue179]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/179 "MicrosoftEdge/WebViewFeedback 问题 179 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue181]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/181 "MicrosoftEdge/WebViewFeedback 问题 181 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue183]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/183 "MicrosoftEdge/WebViewFeedback 问题 183 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue185]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/185 "MicrosoftEdge/WebViewFeedback 问题 185 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue204]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/204 "MicrosoftEdge/WebViewFeedback 问题 204 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue219]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/219 "MicrosoftEdge/WebViewFeedback 问题 219 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue228]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/228 "MicrosoftEdge/WebViewFeedback 问题 228 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue235]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/235 "MicrosoftEdge/WebViewFeedback 问题 235 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue250]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/250 "MicrosoftEdge/WebViewFeedback 问题 250 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue288]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/288 "MicrosoftEdge/WebViewFeedback 问题 288 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue293]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/293 "MicrosoftEdge/WebViewFeedback 问题 293 的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue318]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/318 "MicrosoftEdge/WebViewFeedback 问题 318 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue335]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/335 "MicrosoftEdge/WebViewFeedback 问题 335 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue371]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/371 "MicrosoftEdge/WebViewFeedback 问题 371 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue382]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/382 "MicrosoftEdge/WebViewFeedback 问题 382 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue431]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/431 "MicrosoftEdge/WebViewFeedback 问题 431 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue432]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/432 "MicrosoftEdge/WebViewFeedback 问题 432 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue461]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/461 "MicrosoftEdge/WebViewFeedback 问题 461 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue525]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/525 "MicrosoftEdge/WebViewFeedback 问题 525 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue549]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/549 "MicrosoftEdge/WebViewFeedback 问题 549 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue560]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/560 "MicrosoftEdge/WebViewFeedback 问题 560 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue611]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/611 "MicrosoftEdge/WebViewFeedback 问题 611 的反馈存储库"  

[GithubMicrosoftedgeWebview2AnnouncementIssue2]:  https://github.com/MicrosoftEdge/WebView2Announcement/issues/2 "MicrosoftEdge/WebViewAnnouncement 问题 2 的公告存储库"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesPr17]: https://github.com/MicrosoftEdge/WebView2Samples/pull/17 "移动项目以使用最新的 WebView2 SDK 0.9.430 - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API 示例 - MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftDevblogDotnetAnnouncingGeneralAvailabilityForMicrosoftEdgeWebview2ForNetFixedDistributionMethod]: https://devblogs.microsoft.com/dotnet/announcing-general-availability-for-microsoft-edge-webview2-for-net-and-fixed-distribution-method "宣布正式发布适用于 .NET 和固定分发方法的 Microsoft Edge WebView2 | .NET 博客"  

[MicrosoftDeveloperMicrosoftEdgeWebView2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft Edge 开发人员"  

[NuGetGallery]:  https://www.nuget.org/packages/Microsoft.Web.WebView2 "NuGet 库|Microsoft.Web.WebView2"  
[NuGetGallery0.8.149]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.149 "NuGet 库|Microsoft.Web.WebView2 v0.8.149"  
[NuGetGallery0.8.190]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.190 "NuGet 库|Microsoft.Web.WebView2 v0.8.190"  
[NuGetGallery0.8.230]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.230 "NuGet 库|Microsoft.Web.WebView2 v0.8.230"  
[NuGetGallery0.8.270]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.270 "NuGet 库|Microsoft.Web.WebView2 v0.8.270"  
[NuGetGallery0.8.314]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.314 "NuGet 库|Microsoft.Web.WebView2 v0.8.314"  
[NuGetGallery0.8.355]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.355 "NuGet 库|Microsoft.Web.WebView2 v0.8.355"  
[NuGetGallery0.9.430]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.430 "NuGet 库|Microsoft.Web.WebView2 v0.9.430"  
[NuGetGallery0.9.488]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.488 "NuGet 库|Microsoft.Web.WebView2 v0.9.488"  
[NuGetGallery0.9.515-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.515-prerelease "NuGet 库|Microsoft.Web.WebView2 v0.9.515 预发行"  
[NuGetGallery0.9.538]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.538 "NuGet 库|Microsoft.Web.WebView2 v0.9.538"  
[NuGetGallery0.9.579]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.579 "NuGet 库|Microsoft.Web.WebView2 v0.9.579"
[NuGetGallery0.9.622.11]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.622.11 "NuGet 库|Microsoft.Web.WebView2 v0.9.622.11"
[NuGetGallery1.0.622.22]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.622.22 "NuGet 库|Microsoft.Web.WebView2 v1.0.622.22"
[NuGetGallery1.0.664.34]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.34 "NuGet 库|Microsoft.Web.WebView2 v1.0.664.34"
[NuGetGallery1.0.664.37]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.37 "NuGet 库|Microsoft.Web.WebView2 v1.0.664.37"
[NuGetGallery0.9.628-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.628-prerelease "NuGet 库|Microsoft.Web.WebView2 v0.9.628 预发行"  
[NuGetGallery1.0.674-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.674-prerelease "NuGet 库|Microsoft.Web.WebView2 v1.0.674 预发行"  
[NuGetGallery1.0.721-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.721-prerelease "NuGet 库|Microsoft.Web.WebView2 v1.0.721 预发行"  
[WindowsBlogsMsedgedevEdgeWebview2GeneralAvailability]: https://blogs.windows.com/msedgedev/edge-webview2-general-availability "宣布推出 Microsoft Edge WebView2 通用|Microsoft Edge 博客"  

[WebResourceResponseReceivedAPI]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease#add_webresourceresponsereceived&preserve-view=true "add_WebResourceResponseReceived - 接口 ICoreWebView2 |Microsoft Docs"
[NavigateWithWebResourceRequestAPI]: /microsoft-edge/webview2/reference/win32/icorewebview2environment2?view=webview2-1.0.721-prerelease#createwebresourcerequest&preserve-view=true "CreateWebResourceRequest - 接口 ICoreWebView2Environment |Microsoft Docs"
[CookiemanagementAPI]: /microsoft-edge/webview2/reference/win32/icorewebview2cookiemanager?view=webview2-1.0.721-prerelease&preserve-view=true "ICoreWebView2CookieManager |Microsoft Docs"
[DOMContentLoadedAPI]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease#add_domcontentloaded&preserve-view=true "add_DOMContentLoaded - 接口ICoreWebView2_2 |Microsoft Docs"
[WebViewEnvironmentproperty]: /microsoft-edge/webview2/reference/win32/icorewebview2_2?view=webview2-1.0.721-prerelease#get_environment&preserve-view=true "ICoreWebView2CookieManager |Microsoft Docs"

[GithubMicrosoftedgeWebviewfeedbackIssue37]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/37 "MicrosoftEdge/WebViewFeedback 问题 37 的反馈存储库" 
[GithubMicrosoftedgeWebviewfeedbackIssue58]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/58 "MicrosoftEdge/WebViewFeedback 问题 58 的反馈存储库" 
[GithubMicrosoftedgeWebviewfeedbackIssue122]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/122 "MicrosoftEdge/WebViewFeedback 问题 122 的反馈存储库" 
[GithubMicrosoftedgeWebviewfeedbackIssue161]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/161 "MicrosoftEdge/WebViewFeedback 问题 161 的反馈存储库" 
[GithubMicrosoftedgeWebviewfeedbackIssue196]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/196 "MicrosoftEdge/WebViewFeedback 问题 196 的反馈存储库" 
[GithubMicrosoftedgeWebviewfeedbackIssue205]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/205 "MicrosoftEdge/WebViewFeedback 问题 205 的反馈存储库" 
[GithubMicrosoftedgeWebviewfeedbackIssue212]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/212 "MicrosoftEdge/WebViewFeedback 问题 212 的反馈存储库" 
[GithubMicrosoftedgeWebviewfeedbackIssue399]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/399 "MicrosoftEdge/WebViewFeedback 问题 399 的反馈存储库" 
[GithubMicrosoftedgeWebviewfeedbackIssue400]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/400 "MicrosoftEdge/WebViewFeedback 问题 400 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue409]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/409 "MicrosoftEdge/WebViewFeedback 问题 409 的反馈存储库" 
[GithubMicrosoftedgeWebviewfeedbackIssue605]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/605 "MicrosoftEdge/WebViewFeedback 问题 605 的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue691]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/691 "MicrosoftEdge/WebViewFeedback 问题 691 的反馈存储库" 
[GithubMicrosoftedgeWebviewfeedbackIssue414]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/414 "MicrosoftEdge/WebViewFeedback 问题 414 的反馈存储库" 
[NuGetGallery1.0.705.50]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.705.50 "NuGet 库|Microsoft.Web.WebView2 v1.0.705.50"
[NuGetGallery1.0.781-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.781-prerelease "NuGet 库|Microsoft.Web.WebView2 v1.0.781 预发行"  
[ReferenceWin32Icorewebview210781PreReleaseTrySuspendResume]: /microsoft-edge/webview2/reference/win32/icorewebview2_3?view=webview2-1.0.781-prerelease&preserve-view=true#trysuspend "TrySuspend - 接口ICoreWebview2_3 |Microsoft Docs"  
[ReferenceWin32Icorewebview2experimentalsettings10781PreReleaseGetUserAgent]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalsettings?view=webview2-1.0.781-prerelease#get_useragent "get_UserAgent - 接口 ICoreWebView2ExperimentalSettings |Microsoft Docs"  
[ReferenceWin32Icorewebview210781PreReleaseSetVirtualHostNameToFolderMapping]: /microsoft-edge/webview2/reference/win32/icorewebview2_3?view=webview2-1.0.781-prerelease&preserve-view=true#setvirtualhostnametofoldermapping "SetVirtualHostNameToFolderMapping - 接口ICoreWebView2_3 |Microsoft Docs"   
[ReferenceWin32Icorewebview2controllerViewWebview210781PreReleaseDefaultBackgroundColor]: /microsoft-edge/webview2/reference/win32/icorewebview2controller2?view=webview2-1.0.781-prerelease&preserve-view=true#get_defaultbackgroundcolor "get_DefaultBackgroundColor - 接口 ICoreWebView2Controller2 |Microsoft Docs"  
[ReferenceWin32Icorewebview2controllerViewWebview210781CompositionController]:  /microsoft-edge/webview2/reference/win32/icorewebview2compositioncontroller?view=webview2-1.0.781-prerelease&preserve-view=true "interface ICoreWebView2CompositionController |Microsoft Docs"  
[ReferenceWin32Icorewebview2webresourceresponseviewgetcontentcompletedhandlerInvoke10781]: /microsoft-edge/webview2/reference/win32/icorewebview2webresourceresponseviewgetcontentcompletedhandler?view=webview2-1.0.781-prerelease&preserve-view=true#invoke "Invoke - 接口 ICoreWebView2WebResourceResponseViewGetContentCompletedHandler |Microsoft Docs"  
