---
description: Microsoft Edge WebView2 SDK 的发行说明
title: Microsoft Edge WebView2 for Win32、WPF 和 WinForms 的发行说明
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/08/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 2859f931aea8963e8a50835110914a216811c191
ms.sourcegitcommit: 3234b32e73c9f8362082d995296bd1c5e4286036
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "11204017"
---
# WebView2 SDK 的发行说明  

WebView2 团队在六周的节奏上更新 [WEBVIEW2 SDK][NuGetGallery] 。  查看以下内容，了解有关 Api 的最新信息：产品发布、添加、修改以及对 Api 的重大更改。  

> [!NOTE]
> 更新 NuGet 程序包后重新编译你的应用。  

## 1.0.721-预发布  

发布日期：2020年12月8日  

[NuGet 程序包][NuGetGallery1.0.721-prerelease] \ |最低 Microsoft Edge 版本86.0.616.0。  

#### 常规  

###### 功能  

*   已添加 [WebView2 组策略][DeployedgeMicrosoftEdgeWebviewPolicies]。  有关推荐做法的详细信息，请导航到 [WebView2 的组策略][Webview2ConceptsEnterpriseGroupPoliciesForWebview2]。  
*   > [!IMPORTANT]
    > **重大更改**：已弃用旧的注册表位置。  
    > 
    > ```text
    > {Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}
    > ```  
     
*   添加了对 WebView2 内的 [拖放 & 丢弃][ReferenceWin32Icorewebview2experimentalcompositioncontroller3] 的支持。  
*   添加了用于处理 DPI 支持的 Api。  
    *   添加了 [RasterizationScale][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetRasterizationscale] 属性以更改 web 视图内容和 UI 弹出的 DPI 比例以及关联的 [RasterizationScaleChanged][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseAddRasterizationscalechanged] 事件。  
    *   将 [ShouldDetectMonitorScaleChanges][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetShouldDetectMonitorScaleChanges] 属性添加到 "自动更新" `RasterizationScale` 属性（如果需要）。  
    *   添加了 [BoundsMode 属性][ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetBoundsMode] 以指定边界为逻辑像素，并允许 web 视图使用 `RasterizationScale` for WebView2 像素显示，并让 web 视图将应用于 `RasterizationScale` `Bounds` 以获取物理大小。
*   已更新 `NewWindowRequested` 事件以处理 `Ctrl` + `click` 和 `Shift` + `click` 。  \ ([\ #168][GithubMicrosoftedgeWebviewfeedbackIssue168] 和 [\ #371][GithubMicrosoftedgeWebviewfeedbackIssue371]\ ) 。  

#### .NET  

###### 功能  

*   在 .NET Core 3.1 + 和 .NET 5 中启用 WinForms 设计器。  
*   改进了 .NET cookie 管理。  \ ([\ #611][GithubMicrosoftedgeWebviewfeedbackIssue611]\ ) 。  
*   替换 `CoreWebView2Ready` 为 [CoreWebView2InitializationCompleted][DotnetApiMicrosoftWebWebview2Corewebview2initializationcompletedeventargs]。  

###### Bug 修复

*   添加了 [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2WpfWebview2Acceleratorkeypressed] 事件以支持 Automationproperties.acceleratorkey 按 WebView2。  \ ([\ #288][GithubMicrosoftedgeWebviewfeedbackIssue288]\ ) 。  
*   将不需要的文件从输出 WebView2 文件夹中删除。  \ ([\ #461][GithubMicrosoftedgeWebviewfeedbackIssue461]\ ) 。  
*   改进的主机对象 API。  \ ([\ #335][GithubMicrosoftedgeWebviewfeedbackIssue335] 和 [\ #525][GithubMicrosoftedgeWebviewfeedbackIssue525]\ ) 。  

## 1.0.664.37  

发布日期：2020年11月20日  

[NuGet 程序包][NuGetGallery1.0.664.37] \ |最低 WebView2 运行时版本86.0.616.0。  

#### 常规  

> [!IMPORTANT]
> **公告**： .net WPF/WinForms WebView2 现已正式推出 (GA \ ) 。  从本版本开始，版本 Sdk 是向前兼容的。  有关详细信息，请导航到 [GA 公告博客文章][MicrosoftDevblogDotnetAnnouncingGeneralAvailabilityForMicrosoftEdgeWebview2ForNetFixedDistributionMethod]。  

###### 功能  

*   .NET WPF/WinForms WebView2 现已正式推出 (GA \ ) 。  
*   已修复的分发 \ (携带的 \ ) 模式已达到 GA。  

#### .NET  

###### Bug 修复  

*   `CoreWebView2NewWindowRequestedEventArgs.Handled` 防止打开新窗口 \ ([\ #549][GithubMicrosoftedgeWebviewfeedbackIssue549]\ ) 和 \ ([\ #560][GithubMicrosoftedgeWebviewfeedbackIssue560]。  


## 1.0.674-预发布  

发布日期：2020年10月19日  

[NuGet 程序包][NuGetGallery1.0.674-prerelease] \ |最低 WebView2 运行时版本86.0.616.0。  

#### 常规  

*   添加了 [NavigateWithWebResourceRequest][ReferenceWin32Icorewebview2experimentalNavigatewithwebresourcerequest10674] 方法，使你可以在导航过程中提供发布数据或其他请求标头。
*   添加了加载和分析初始 HTML 文档时运行的 [DOMContentLoaded][ReferenceWin32Icorewebview2experimentalAddDomcontentloaded10674] 事件。
*   在 WebView2 上添加了 [环境][ReferenceWin32Icorewebview2experimentalGetEnvironment10674] 属性。  此属性公开创建 WebView2 实例的 WebView2 环境。
*   添加了允许开发人员对 WebView2 会话进行身份验证的 [cookie 管理][ReferenceWin32Icorewebview2experimentalGetCookiemanager10674] api，或从 web 视图检索 cookie 以对其他工具进行身份验证。  我们打算制定特定于语言/框架的改进。  有关详细信息，请导航到 [API 审阅： Cookie 管理][GithubMicrosoftedgeWebview2AnnouncementIssue2]。
*   更新了 [WebResourceResponseReceived][ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived10674] 事件，并添加了不可变的 [WebResourceResponseView][ReferenceWin32Icorewebview2experimentalwebresourceresponseview10674] 和 [WebResourceResponseReceivedEventArgs：:P Opulateresponsecontent][ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsPopulateresponsecontent09628] 成为 [WebResourceResponseView：： GetContent][ReferenceWin32Icorewebview2experimentalwebresourceresponseviewGetcontent10674]。
*   已关闭 [Microsoft Defender 应用程序防护 (WDAG) ][WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10] 在 WebView2 中。
*   为 Visual 托管添加了 [SystemCursorId][ReferenceWin32Icorewebview2experimentalcompositioncontroller2GetSystemcursorid10674] 。
*   为 Visual 托管中的输入方法添加了 bug 已修复。
*   当使用 WebView2 静态库时，开发人员不必再包含版本 .lib。

#### .NET  

*   已更新 [CoreWebView2][DotnetApiMicrosoftWebWebview2CoreCorewebview2] 类以公开 CoreWebView2Environment 变量。  
*   将命名空间中的自定义 EventArgs 类的实现更改 `Microsoft.Web.WebView2.Core` 为 [系统 EventArgs][DotnetApiSystemEventargs] 或 [CancelEventArgs][DotnetApiSystemComponentmodelCancelEventargs]的子类。  \ ([\ #250][GithubMicrosoftedgeWebviewfeedbackIssue250]\ )   
*   添加了对 WinForms 中的 [CoreWebView2CreationProperties][DotnetApiMicrosoftWebWebview2Winforms] 的支持。  \ ([\ #204][GithubMicrosoftedgeWebviewfeedbackIssue204]\ ) 
*   添加了 .NET [WebResourceRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested] api。  \ ([\ #219][GithubMicrosoftedgeWebviewfeedbackIssue219]\ ) 。  
*   已将 WinForms Designer [Source][DotnetApiMicrosoftWebWebview2WinformsWebview2Source] 属性更新为默认值或重置为 null。  \ ([\ #177][GithubMicrosoftedgeWebviewfeedbackIssue177]\ ) 。  
*   已更新 WebView2.Init 中的 WebView2 边界 ( # A1 以支持小于100% 的 DPI 模式。  \ ([\ #432][GithubMicrosoftedgeWebviewfeedbackIssue432]\ ) 。  
*   更新了 [BuildWindowCore][DotnetApiMicrosoftWebWebview2WpfWebview2Buildwindowcore] 和 [DestroyWindowCore][DotnetApiMicrosoftWebWebview2WpfWebview2Destroywindowcore] 的可靠性。  \ ([\ #382][GithubMicrosoftedgeWebviewfeedbackIssue382]\ ) 。  
*   更新了 .NET 加载程序基，以在进程位（而不是操作系统体系结构）上加载。  \ ([\ #431][GithubMicrosoftedgeWebviewfeedbackIssue431]\ ) 。  
*   重命名 `EdgeNotFoundExpection` 为 [WebView2RuntimeNotFoundException][DotnetApiMicrosoftWebWebview2CoreWebview2runtimenotfoundexception]。
 
## 1.0.622.22  

发布日期：2020年10月19日  

[NuGet 程序包][NuGetGallery1.0.622.22] \ |最低 WebView2 运行时版本86.0.616.0。  

#### 常规  

> [!IMPORTANT]
> **公告**： Win32 C/c + + WebView2 现已正式推出 (GA \ ) 。  从本版本开始，版本 Sdk 是向前兼容的。  有关详细信息，请导航到 " [公开发布博客文章][WindowsBlogsMsedgedevEdgeWebview2GeneralAvailability]"。  

*  [WebView2 运行时和安装程序][Webview2ConceptsDistributionUnderstandRuntimeInstaller] 是公开的。  [Microsoft Edge WebView2][MicrosoftDeveloperMicrosoftEdgeWebView2]中提供了引导程序、引导程序的下行链接和长时间运行时的独立安装程序。  [WebView2Samples][GithubMicrosoftedgeWebview2samplesMain]存储库中也提供了安装工作流的示例代码。  
*  "[固定版本" 模式][Webview2ConceptsDistributionFixedVersionMode]适用于开发人员预览版。  

## 0.9.628-预发布  

发布日期：2020年9月10日  

[NuGet 程序包][NuGetGallery0.9.628-prerelease] \ |最低 Microsoft Edge 版本86.0.616.0。  

> [!IMPORTANT]
> **公告**：此预发布将根据 Microsoft Edge 87 分支继续发布。  将来，预发行 SDK 版本与 Microsoft Edge 的 "未处理" 生成相匹配，正常版本与 Microsoft Edge 稳定同步。  

#### 常规  

*   > [!IMPORTANT]
    > **公告**：可视化托管 api 现在位于 "预览" 下。  WebView2 使用可视化托管与 WinComp/DComp 视觉对象一起运行，而不是使用 Hwnd。  这些接口位于实验性中。  有关详细信息，请导航到 [ICoreWebView2ExperimentalEnvironment][ReferenceWin32Icorewebview2experimentalenvironment09628]。  

#### .NET  

*   .NET 二进制文件现在具有 [强名称][DotnetStandardAssemblyStrongNamed]。  \ ([\ #181][GithubMicrosoftedgeWebviewfeedbackIssue181]\ ) 。  
*   已更新要包含的 NuGet 目标 `WebViewLoader2.dll` 。  \ ([\ #228][GithubMicrosoftedgeWebviewfeedbackIssue228]\ ) 和 \ ([\][GithubMicrosoftedgeWebviewfeedbackIssue183]#183 \ ) 。  
*   更新 `WebResourceRequested` 以在 .net 中公开 [HttpRequestHeaders][DotnetApiMicrosoftWebWebview2CoreCorewebview2httprequestheaders] 和 [HttpResponseHeaders][DotnetApiMicrosoftWebWebview2CoreCorewebview2httpresponseheaders] api。  \ ([\ #131][GithubMicrosoftedgeWebviewfeedbackIssue131]\ ) 。  

## 0.9.622.11  

发布日期：2020年9月10日  

[NuGet 程序包][NuGetGallery0.9.622.11] \ |最低 WebView2 运行时版本86.0.616.0。  

#### 常规  

*   > [!IMPORTANT]
    > **公告**：此 SDK 是 WebView2 Win32 C/c + + GA 的发布候选版本。  GA 版本应使用相同的 API 接口和功能。  

*   已断开连接的 [浏览器策略][DeployedgeMicrosoftEdgePolicies]。  
*   已添加 WebView2 环境选项的 [AllowSingleSignOnUsingOSPrimaryAccount][ReferenceWin32Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount09622] 属性以启用 web 视图的条件访问。  
*   更新 `ICoreWebView2NewWindowRequestedEventArgs` 为包括 [WindowFeatures][ReferenceWin32Icorewebview2newwindowrequestedeventargsGetWindowfeatures09622] 属性和关联的 [ICoreWebView2WindowFeatures][ReferenceWin32Icorewebview2windowfeatures09622]。  \ ([\ #293][GithubMicrosoftedgeWebviewfeedbackIssue293]\ ) 。  
*   已更新 `System.Windows.Rect`  为使用 `System.Drawing.Rectangle` `System.Windows.Rect` \ ([\ #235][GithubMicrosoftedgeWebviewfeedbackIssue235]\ ) 。  
*   更新了 Webview.newwindowrequested 事件以处理 `window.open()` 没有参数的请求。  \ ([\ #293][GithubMicrosoftedgeWebviewfeedbackIssue293]\ ) 。  
*   [AdditionalBrowserArguments][ReferenceWin32Icorewebview2environmentoptionsPutAdditionalbrowserarguments09622] set using `ICoreWebView2EnvironmentOptions` 不被环境变量或注册表值替代。  有关详细信息，请导航到 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32IdlCreatecorewebview2environmentwithoptions09622]。  

## 0.9.579  

发布日期：2020年7月20日  

[NuGet 程序包][NuGetGallery0.9.579] \ |最低 Microsoft Edge 版本86.0.579.0。  

#### 常规  

*   > [!IMPORTANT]
    > **公告**：为预览释放长绿 WebView2 运行时和安装程序。  有关详细信息，请导航到 [WebView2] 的分布] [Webview2ConceptsDistributionUnderstandRuntimeInstallerPreview]。  
*   > [!IMPORTANT]
    > **通知**：下一个 sdk 版本后，将不再支持以下 WebView2 sdk 版本。  
    > 
    > *   [0.8.190](#08190)  
    > *   [0.8.230](#08230)  
    > *   [0.8.270](#08270)  
    > *   [0.8.314](#08314)  
    > *   [0.8.355](#08355)  
    > 
    > WebView2 SDK 版本也在 nuget.org 上标记为 "已弃用"。 WebView2 建议始终更新最新版本的 WebView2。  

*   添加了 Web 视图工作线程改进。  \ ([\ #318][GithubMicrosoftedgeWebviewfeedbackIssue318]\ ) 。  
*   已禁用 Web 视图中的弹出窗口阻止。  有关详细信息，请导航到事件中的 [IsUserInitiated][ReferenceWin32Icorewebview2newwindowrequestedeventargsGetIsuserinitiated09538] 属性 `NewWindowRequested` 。  
*   已确保触发的 Web 视图导航开始事件 `about:blank` 。  现在， `NavigationStarting` 所有导航都将引发事件，但不支持取消或 srcdoc 的取消，也会忽略这些事件 `about:blank` 。  
*   `edge:// URI`Web 视图中已阻止的方案。  
*   已在 WebView2 环境选项上添加实验 [IsSingleSignOnUsingOSPrimaryAccountEnabled][ReferenceWin32Icorewebview2experimentaloptionsGetIssinglesignonusingosprimaryaccountenabled09538] 属性，以启用 web 视图的条件访问。  
*   添加了在 Web 视图接收和处理 WebResource 请求的响应后触发的实验 [WebResourceResponseReceived][ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived09538] 事件。  身份验证标头（如果有）包含在响应对象中。  

#### .NET  

*   改进了 WPF 焦点处理。  \ ([\ #185][GithubMicrosoftedgeWebviewfeedbackIssue185]\ ) 。  
*   `ZoomFactor`WPF Webview2 控制器上已添加属性。  

## 0.9.538  

[NuGet 程序包][NuGetGallery0.9.538] \ |最低 Microsoft Edge 版本85.0.538.0。  

#### 常规  

*   放弃对 WebView2 SDK 版本 [0.8.149](#08149)的支持。  WebView2 建议始终更新最新版本的 WebView2。  
*   已更新的组策略，用于在修改 Microsoft Edge 浏览器的配置文件路径时进行帐户 \ ([#179][GithubMicrosoftedgeWebviewfeedbackIssue179]\ ) 。  

#### Win32 C/c + +  

*   添加了 [ICoreWebView2ExperimentalNewWindowRequestedEventArgs：： get_WindowFeatures][ReferenceWin32Icorewebview2experimentalnewwindowrequestedeventargsGetWindowfeatures09538]，它在运行时引发， `window.open()` 并且与 [ICoreWebView2ExperimentalWindowFeatures][ReferenceWin32Icorewebview2experimentalwindowfeatures09538] \ ([#70][GithubMicrosoftedgeWebviewfeedbackIssue70]\ ) 相关联。  
*   > [!IMPORTANT]
    > **重大更改**：已弃用的 [CreateCoreWebView2EnvironmentWithDetails][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithdetails09488] ，已替换为 [CreateCoreWebView2EnvironmentWithOptions] [[ReferenceWin32IdlCreatecorewebview2environmentwithoptions09538]。  
*   > [!IMPORTANT]
    > **重大更改**：为了确保 WebView2 API 与 Windows api 命名约定相协调，web 视图团队更新了以下内容的名称。  
    > *   [AreRemoteObjectsAllowed][ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09488] 现已 [AreHostObjectsAllowed][ReferenceWin32Icorewebview2settingsGetArehostobjectsallowed09538]。  
*   已更新 [AddHostObjectToScript][ReferenceWin32Icorewebview2Addhostobjecttoscript09538] ，以确保原始主机对象序列化标记被设置为代理对象，并在 JavaScript 回调 \ ([#148][GithubMicrosoftedgeWebviewfeedbackIssue148]\ ) 中作为参数传递回主机对象。  

#### .NET (0.9.538 预发布)   

*   发布了 WinForms 和 WPF WebView2API 示例，这些示例是 WebView2 SDK 的综合指南。  有关详细信息，请导航到 [示例][GithubMicrosoftedgeWebview2samplesMain]存储库。  
*   添加了对可视化托管和窗口功能的 [实验性 api][ConceptsVersioningExperimentalApis]的支持。  
*   > [!IMPORTANT]
    > **重大更改**：以下延迟现在实现 IDisposable：  [ScriptDialogOpening][DotnetApiMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]、 [webview.newwindowrequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Newwindowrequested]、 [WebResourceRequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]和 [webview.permissionrequested][DotnetApiMicrosoftWebWebview2CoreCorewebview2Permissionrequested]。  
*   将 [GetAvailableBrowserVersionString][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring] 和 [CompareBrowserVersions][DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions] 添加为 [CoreWebView2Environment][DotnetApiMicrosoftWebWebview2CoreCorewebview2environment] 静态。  

## 0.9.515-预发布  

[NuGet 程序包][NuGetGallery0.9.515-prerelease] \ |最低 Microsoft Edge 版本84.0.515.0。  

*   > [!IMPORTANT]
    > **公告**： WebView2 现在支持 .net Framework 4.6.2 或更高版本上的 Windows 窗体和 WPF 以及 **预发布程序包**中的 .net Core 3.0 或更高版本。  
*   有关生成 WPF 应用程序的详细信息，请导航到 [Wpf 入门指南][GettingstartedWpf] 和针对特定于 WPF 的 Api 的 WebView2 [WPF 参考][DotnetApiMicrosoftWebWebview2Wpf] 。  
*   有关生成 Windows 窗体应用程序的详细信息，请导航到 [Windows 窗体入门指南][GettingstartedWinforms] 和适用于 Windows 窗体特定 Api 的 WebView2 [Windows 窗体参考][DotnetApiMicrosoftWebWebview2Winforms] 。  
*   有关 CoreWebView2 Api 的详细信息，请导航到 [.Net 参考][DotnetApiMicrosoftWebWebview2Core]。  
*   > [!CAUTION]
    > **已知问题**： web 视图团队知道在将来的版本中正在解决的预发布中有一些问题。  
    > *   **DPI 感知**： WPF 的 WebView2 当前不支持 DPI 感知。  在高 DPI 监视器上初始化 WebView2 时，存在一个已知问题，即 "Web 视图" 首次初始化为窗口的一小部分，直到调整窗口大小。  
    > *   **Wpf 设计器**：当前不支持 wpf 设计器。  通过在文本编辑器中直接修改相应的 XAML，在应用中添加 WebView2 控件。  

## 0.9.488  

[NuGet 程序包][NuGetGallery0.9.488] \ |最低 Microsoft Edge 版本84.0.488.0。  

*   > [!IMPORTANT]
    > **公告**：从即将推出的 Microsoft Edge 版本83开始，长时间浏览器不再面向稳定的浏览器通道。  相反，它面向另一组二进制文件（即品牌长 [绿 WebView2 运行时][ConceptsDistributionEvergreenMode]），你可以通过 web 视图团队当前正在开发的安装程序来进行链接。  有关详细信息，请导航到 " [应用分布][ConceptsDistribution]"。  
*   > [!IMPORTANT]
    > **公告**：向前发展，web 视图团队发布两个程序包：一个预发布程序包，其中包含实验性 api \ (为您试用 \ ) 和稳定的 api \ (以确保您的信任 \ ) 。  若要了解这些差异，请导航到 [了解浏览器版本和 WebView2][ConceptsVersioning]。  
*   > [!IMPORTANT]
    > **重大更改**：为了确保 WebView2 API 与 Windows api 命名约定相协调，web 视图团队更新了以下接口的名称。  
    > *   `CORE_WEBVIEW2_*` 前缀现在是 `COREWEBVIEW2_*` 。  
    > *   [GetCoreWebView2BrowserVersionInfo][ReferenceWin32Webview2IdlGetcorewebview2browserversioninfo09430] 现已 [GetAvailableCoreWebView2BrowserVersionString][ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring09488]。  
    > *   [get_BrowserVersionInfo][ReferenceWin32Icorewebview2environmentGetBrowserversioninfo09430] 现在 [get_BrowserVersionString][ReferenceWin32Icorewebview2environmentGetBrowserversionstring09488]。  
    > *   [AddRemoteObject][ReferenceWin32Icorewebview2Addremoteobject09430] 现已 [AddHostObjectToScript][ReferenceWin32Icorewebview2Addhostobjecttoscript09488]。  
    > *   [RemoveRemoteObject][ReferenceWin32Icorewebview2Removeremoteobject09430] 现已 [RemoveHostObjectFromScript][ReferenceWin32Icorewebview2Removehostobjectfromscript09488]。  
    > *   `chrome.webview.remoteObjects` 现已开始 `chrome.webview.hostObjects` 。  
*   > [!IMPORTANT]
    > **重大更改**： `AddRemoteObject` JS 代理方法也会被重命名。  
    > *   `getLocal` 现已开始 `getLocalProperty` 。  
    > *   `setLocal` 现已开始 `setLocalProperty` 。  
    > *   `getRemote` 现已开始 `getHostProperty` 。  
    > *   `setRemote` 现已开始 `setHostProperty` 。  
    > *   `applyRemote` 现已开始 `applyHostFunction` 。  
*   > [!IMPORTANT]
    > **重大更改**：已弃用的 [CreateCoreWebView2EnvironmentWithDetails][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithdetails09488] 和已替换为 [CreateCoreWebView2EnvironmentWithOptions][ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions09488]。  
*   已添加 [FrameNavigationCompleted][ReferenceWin32Icorewebview2AddFramenavigationcompleted09488] 事件。  现在，当 iframe 完成导航时，将引发一个事件，并返回导航和导航 ID 的成功。  
*   已添加 [ICoreWebView2EnvironmentOptions][ReferenceWin32Icorewebview2environmentoptions09488] 接口，可用于确定应用程序面向的 WebView2 运行时的版本。  
*   已添加 [IsBuiltInErrorPageEnabled][ReferenceWin32Icorewebview2settingsGetIsbuiltinerrorpageenabled09488] 设置。  现在，你可以选择启用或禁用内置错误页面，以便导航失败和呈现进程失败。  
*   更新了远程对象注入以支持 .NET `IDispatch` 实现 \ ([#113][GithubMicrosoftedgeWebviewfeedbackIssue113]\ ) 。  
*   更新了 [webview.newwindowrequested][ReferenceWin32Icorewebview2AddNewwindowrequested09488] 事件以处理来自上下文菜单 \ ([#108][GithubMicrosoftedgeWebviewfeedbackIssue108]\ ) 的请求。  
*   发布了可访问可视化托管 Api 的第一个单独的 WebView2 预发布版程序包。  Web 视图团队更新了 [APISample][GithubMicrosoftedgeWebview2samplesMain] 以包含新的实验 api。  
    *   添加了 [ICoreWebView2ExperimentalCompositionController][ReferenceWin32Icorewebview2experimentalcompositioncontroller09488] 接口，用于连接到合成树并提供 web 视图的输入。  
    *   添加了 [ICoreWebView2ExperimentalPointerInfo][ReferenceWin32Icorewebview2experimentalpointerinfo09488]，其中包含来自 a 的所有信息 `POINTER_INFO` 。  此对象将传递给 SendPointerInput 以将指针输入插入 Web 视图中。  
    *   添加了 [ICoreWebView2ExperimentalCursorChangedEventHandler][ReferenceWin32Icorewebview2experimentalcursorchangedeventhandler09488]，这将在应更改 web 视图上的鼠标光标时通知应用。  当鼠标位于 Web 视图中的文本框上方时，光标将从箭头更改为选择器。  `cursor`上的属性 `CompositionController` 指示应用在 web 视图中当前应显示的鼠标光标。  

## 0.9.430  

[NuGet 程序包][NuGetGallery0.9.430] \ |最低 Microsoft Edge 版本82.0.430.0。  

WebView2 SDK 是正式的 Win32 c + + Beta 版本，其中包含来自反馈的多个功能请求。  Web 视图团队尝试通过重大更改来限制发布数。  在我们接近一般可用性时，Beta 版本中将引入一些重大的重大更改。  

*   > [!IMPORTANT]
    > **重大更改**：作为最终版本，在最终版本中，web 视图团队将前缀 *IWebView2WebView*   重命名为 *ICOREWEBVIEW2*   ，以确保 WebView2 API 与 Windows api 命名约定对齐。  此外，为了利用来自 UI 框架的 WebView2 SDK，Web 视图团队分在 `ICoreWebView2` [ICoreWebView2][ReferenceWin32Icorewebview209430] 和 [ICoreWebView2Host][ReferenceWin32Icorewebview2host09430]中。  `ICoreWebView2Host` 支持调整大小、显示和隐藏、重点介绍以及与窗口化和合成相关的其他功能。  ICoreWebView2 支持所有其他 WebView2 功能。  若要了解有关合并更改的详细信息，请导航到 WebView2 [APISample][GithubMicrosoftedgeWebview2samplesMain]项目中的 WebView2[拉取请求][GithubMicrosoftedgeWebview2samplesPr17]。  
*   > [!IMPORTANT]
    > **重大更改**：将 [DocumentStateChanged][ReferenceWin32Iwebview2webviewAddDocumentstatechanged08190] 拆分为三个组件：  [SourceChanged][ReferenceWin32Icorewebview2AddSourcechanged09430]、 [ContentLoading][ReferenceWin32Icorewebview2AddContentloading09430]和 [HistoryChanged][ReferenceWin32Icorewebview2AddHistorychanged09430]。  现在，当源 URL 更改时， `SourceChanged` 将引发事件。  更改历史记录状态时， `HistoryChanged` 将引发事件。  在 `ContentLoading` 加载新文档时，在初始脚本之前激发事件。  
*   添加了对 ARM64 体系结构的支持。  
*   已添加软输入面板 \ (SIP \ ) 支持触摸屏设备。  
*   添加了对 Windows Server 2008 R2、Windows Server 2012、Windows Server 2012 R2 和 Windows Server 2016 的支持。  
*   添加了 [NotifyParentWindowPositionChanged][ReferenceWin32Icorewebview2hostNotifyparentwindowpositionchanged09430]，允许状态栏在窗口模式下关注窗口。  此外，在无窗口模式下实现此更改可使辅助功能正常工作。  
*   添加了 [AreRemoteObjectsAllowed][ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09430] 设置以全局控制是否可以由任何远程对象访问页面。  默认情况下，"已 `AreRemoteObjectsAllowed` 启用"，这意味着由 [AddRemoteObject][ReferenceWin32Icorewebview2Addremoteobject09430] 添加的远程对象可从页面访问。  `AreRemoteObjectsAllowed`禁用时，无法从页面访问对象。  将在下一个导航事件上应用更改。  
*   添加了[IsZoomControlEnabled][ReferenceWin32Icorewebview2settingsGetIszoomcontrolenabled09430]设置以防止用户使用 `ctrl` + `+` and `ctrl` + `-` \ (或 `ctrl` + 鼠标滚轮 \ ) 影响 web 视图的缩放。  禁用该设置时，仍可使用 [put_ZoomFactor][ReferenceWin32Icorewebview2hostPutZoomfactor09430] 设置缩放。  
*   将 ZoomFactor 更改为仅应用于当前 Web 视图。  对当前 Web 视图的缩放更改不会影响你导航到同一源站点的其他 WebViews。  有关详细信息，请导航到 [get_ZoomFactor][ReferenceWin32Icorewebview2hostGetZoomfactor09430]。  
*   用于 Web 视图的 Hid ZoomView UI \ ([#95][GithubMicrosoftedgeWebviewfeedbackIssue95]\ ) 。  
*   已添加 [SetBoundsAndZoomFactor][ReferenceWin32Icorewebview2hostSetboundsandzoomfactor09430]。  现在，你可以同时设置 Web 视图的缩放系数和边界。  
*   已添加 [WindowCloseRequested][ReferenceWin32Icorewebview2AddWindowcloserequested09430] 事件。  有关详细信息，请导航到 [add_WindowCloseRequested][ReferenceWin32Icorewebview2AddWindowcloserequested09430] \ ([#119][GithubMicrosoftedgeWebviewfeedbackIssue119]\ ) 。  
*   添加了对 `beforeunload` JavaScript 对话框事件的对话框类型的支持并添加了 [CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD][ReferenceWin32Icorewebview2CoreWebview2ScriptDialogKind09430] 枚举条目。  
*   将 [GetHeaders][ReferenceWin32Icorewebview2httprequestheadersGetheaders09430] 添加到 HttpRequestHeaders， [GetHeader][ReferenceWin32Icorewebview2httpresponseheadersGetheader09430] 到 HttpResponseHeaders，并将 [get_HasCurrentHeader][ReferenceWin32Icorewebview2httpheaderscollectioniteratorGetHascurrentheader09430] 属性添加到 HttpHeadersCollectionIterator。  
*   > [!IMPORTANT]
    > **重大更改**：已修改 `DevToolsProtocolEventReceived` 的行为。  现在，你可以为特定的 DevTools 协议事件创建[DevToolsProtocolEventReceiver][ReferenceWin32Icorewebview2devtoolsprotocoleventreceiver09430] ，并使用[add_DevToolsProtocolEventReceived][ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverAddDevtoolsprotocoleventreceived09430]remove_DevToolsProtocolEventReceived 订阅/取消订阅此类事件 / [][ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverRemoveDevtoolsprotocoleventreceived09430]。
*   > [!IMPORTANT]
    > **重大更改**：已将 `WebMessageReceivedEventArgs` [Get_WebMessageAsString][ReferenceWin32Iwebview2webmessagereceivedeventargsGetWebmessageasstring08190] 属性更改为 [TryGetWebMessageAsString][ReferenceWin32Icorewebview2webmessagereceivedeventargsTrygetwebmessageasstring09430] 方法。  
*   > [!IMPORTANT]
    > **重大更改**：将 `AcceleratorKeyPressedEventArgs` [句柄][ReferenceWin32Iwebview2acceleratorkeypressedeventargsHandle08190] 方法更改为 [get_Handled][ReferenceWin32Icorewebview2acceleratorkeypressedeventargsGetHandled09430] 属性。  

## 0.8.355

[NuGet 程序包][NuGetGallery0.8.355] \ |最低 Microsoft Edge 版本80.0.355.0。

*   发布了 WebView2API 示例，它是 WebView2 SDK 的综合指南。  有关详细信息，请导航到 [APISample][GithubMicrosoftedgeWebview2samplesApisample]。  
*   添加了除英语之外的所有语言的 IME 支持 ([#30][GithubMicrosoftedgeWebviewfeedbackIssue30]\ ) 。  
*   更新了事件的 API 图面以 `WebResourceRequested` 响应 bug 报告。  同时指定筛选器和创建事件现在已被否决。  若要创建 web 资源请求的事件，请使用 [add_WebResourceRequested][ReferenceWin32Iwebview2webview5AddWebresourcerequested08190] 添加事件和 [AddWebResourceRequestedFilter][ReferenceWin32Iwebview2webview5Addwebresourcerequestedfilter08190] 以添加筛选器。  [RemoveWebResourceRequestedFilter][ReferenceWin32Iwebview2webview5Removewebresourcerequestedfilter08190] 将删除筛选器 \ ([#36][GithubMicrosoftedgeWebviewfeedbackIssue36]\ ) \ ([#74][GithubMicrosoftedgeWebviewfeedbackIssue74]\ ) 。  
*   > [!IMPORTANT]
    > **重大更改**：已修改的全屏行为。  弃用的 [IsFullScreenAllowed][ReferenceWin32Iwebview2settingsGetIsfullscreenallowedDeprecated08190]。  现在，默认情况下，如果 Web (视图中的某个元素（如视频 \ ) 设置为全屏），它将填充 Web 视图的边界。  使用 [ContainsFullScreenElementChanged][ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandler08190] 事件和 [get_ContainsFullScreenElement][ReferenceWin32Iwebview2webview5GetContainsfullscreenelement08190] 指定如果元素要进入全屏模式，应用应如何调整 web 视图的大小。  

## 0.8.314  

[NuGet 程序包][NuGetGallery0.8.314] \ |最低 Microsoft Edge 版本80.0.314.0。  

*   添加了对 Windows 7、Windows 8 和 Windows 8.1 的支持。  
*   已添加 Visual Studio 和 Visual Studio 代码调试支持 WebView2。  现在，在 WebView2 中从 IDE 调试你的脚本。  有关详细信息，请导航到 [通过 WebView2 控件进行开发时的调试方法][HowtoDebug]。  
*   已添加 `Native Object Injection` ，允许在 WebView2 内运行的脚本从应用程序的 Win32 组件访问 IDispatch 对象，并访问 idispatch 对象的属性。  有关详细信息，请导航到 [AddRemoteObject][ReferenceWin32Iwebview2webview4Addremoteobject08190] \ ([#17][GithubMicrosoftedgeWebviewfeedbackIssue17]\ ) 。  
*   已添加 `AcceleratorKeyPressed` 事件。  有关详细信息，请导航到 [add_AcceleratorKeyPressed][ReferenceWin32Iwebview2webview4AddAcceleratorkeypressed08190] \ ([#57][GithubMicrosoftedgeWebviewfeedbackIssue57]\ ) 。  
*   已禁用 `Context Menus` 。  有关详细信息，请导航到 [put_AreDefaultContextMenusEnabled][ReferenceWin32Iwebview2settings2PutAredefaultcontextmenusenabled08190] \ ([#57][GithubMicrosoftedgeWebviewfeedbackIssue57]\ ) 。  
*   已更新 `DPI Awareness` 。  现在，Web 视图的 DPI 感知与主机应用程序的 DPI 感知相同。  
    
    > [!NOTE]
    > 如果另一个混合应用程序是使用与原始 Web 视图不同的 DPI 感知启动的，则如果用户数据目录与原始 Web 视图相同，则不会启动新的 Web 视图 ([#1][GithubMicrosoftedgeWebviewfeedbackIssue1]\ ) 。  
    
*   已更新 `Notification Change Behavior` ，WebView2 将自动拒绝由 Web 视图中托管的 web 内容提示的通知权限请求。  

## 0.8.270  

[NuGet 程序包][NuGetGallery0.8.270] \ |最低 Microsoft Edge 版本78.0.270.0。  

*   已添加 `DocumentTitleChanged` 事件以指示文档标题更改 \ ([\ #27][GithubMicrosoftedgeWebviewfeedbackIssue27]\ ) 。  
*   已添加 `GetWebView2BrowserVersionInfo` API \ ([\ #18][GithubMicrosoftedgeWebviewfeedbackIssue18]\ ) 。  
*   已添加 `NewWindowRequested` 事件。  
*   `CreateWebView2EnvironmentWithDetails`要删除的已更新函数 `releaseChannelPreference` 。  有关该函数的详细信息 `CreateWebView2EnvironmentWithDetails` ，请导航到 [CreateWebView2EnvironmentWithDetails][ReferenceWin32WebView2IdlCreatewebview2environmentwithdetails08190]。  注册表和环境变量替代仍受支持。  除非被覆盖，否则使用默认通道首选项。  
    在通道搜索期间，Web 视图团队会跳过与 WebView2 SDK 不兼容的任何以前的频道版本。  
    Web 视图团队选择更稳定的通道，以确保最终用户最一致的行为。  在使用最新的 "最新" 的新版本进行测试时，应创建一个脚本以 `WEBVIEW2_RELEASE_CHANNEL_PREFERENCE` `1` 在启动应用之前将环境变量设置为。  
*   将 `CreateWebView2EnvironmentWithDetails` 函数更新为 `userDataFolder` 在未指定时选择的逻辑。  有关该函数的详细信息 `CreateWebView2EnvironmentWithDetails` ，请导航到 [CreateWebView2EnvironmentWithDetails][ReferenceWin32WebView2IdlCreatewebview2environmentwithdetails08190]。  如果你以前使用的 `userDataFolder` 是默认位置，则当你切换到新的 SDK 时，默认 `userDataFolder` 情况下会重置 \ (设置为主机代码目录 \ ) 中的新位置，并且你的状态也会重置。  
    如果主机进程没有写入指定目录的权限，则该 `CreateWebView2EnvironmentWithDetails` 函数可能失败。  你可以将旧用户数据目录中的数据复制到新目录。  

## 0.8.230  

[NuGet 程序包][NuGetGallery0.8.230] \ |最低 Microsoft Edge 版本77.0.230.0。  

*   添加了 `Stop` 用于停止所有导航和挂起资源读取 \ ([\ #28][GithubMicrosoftedgeWebviewfeedbackIssue28]\ ) 的 API。  
*   已 `.tlb` 将文件添加到 NuGet 程序包 \ ([\ #22][GithubMicrosoftedgeWebviewfeedbackIssue22]\ ) 。  
*   已将 .NET 项目添加到 NuGet 程序包 \ ([\ #32][GithubMicrosoftedgeWebviewfeedbackIssue32]\ ) 中的安装程序列表。  

## 0.8.190  

[NuGet 程序包][NuGetGallery0.8.190] \ |最低 Microsoft Edge 版本77.0.190.0。  

*   添加 `get_AreDevToolsEnabled` / `put_AreDevToolsEnabled` 到控件，如果用户可以打开 DevTools \ ([\ #16][GithubMicrosoftedgeWebviewfeedbackIssue16]\ ) 。  
*   添加 `get_IsStatusBarEnabled` / `put_IsStatusBarEnabled` 到控件，如果状态栏显示为 \ ([\ #19][GithubMicrosoftedgeWebviewfeedbackIssue19]\ ) 。  
*   添加， `get_CanGoBack` / `GoBack` / `get_CanGoForward` / `GoForward` 用于在导航历史记录中后退和前进。  
*   已添加 `IWebView2HttpHeadersCollectionIterator` / `IWebView2HttpRequestHeaders` / `IWebView2HttpRequestHeaders` 用于在 web 视图中查看和修改 http 标头的 http 头类型 \ (\ ) 。  
*   在64位计算机上添加了32位 Web 视图支持 ([\ #13][GithubMicrosoftedgeWebviewfeedbackIssue13]\ ) 。  
*   已将 Web 视图 IDL 添加到 SDK \ ([\ #14][GithubMicrosoftedgeWebviewfeedbackIssue14]\ ) 。  
*   添加了支持 `IID\_\*` 接口 ID 对象的 lib \ ([\ #12][GithubMicrosoftedgeWebviewfeedbackIssue12]\ ) 。  
*   将 DLL 文件的包含路径、链接和 autocopying 添加到 `TARGET` SDK 中的 NuGet 文件。  
*   已启用 `window.open()` 脚本中的请求。  

## 0.8.149  

[NuGet 程序包][NuGetGallery0.8.149] \ |最低 Microsoft Edge 版本76.0.149.0。  

初始开发人员预览版。  

<!-- Links -->  

[ConceptsDistribution]: ./concepts/distribution.md "使用 WebView2 | 的应用程序的分发Microsoft 文档"  
[ConceptsDistributionEvergreenMode]: ./concepts/distribution.md#evergreen-distribution-mode "长绿分布模式-使用 WebView2 | 的应用程序分布Microsoft 文档"  
[Webview2ConceptsDistributionFixedVersionMode]: ./concepts/distribution.md#fixed-version-distribution-mode "固定版本分发模式-使用 WebView2 | 的应用程序的分发Microsoft 文档"  
[Webview2ConceptsDistributionUnderstandRuntimeInstaller]: ./concepts/distribution.md#understanding-the-webview2-runtime "了解使用 WebView2 | 的应用程序的 WebView2 运行时和安装程序分发Microsoft 文档"  
[Webview2ConceptsEnterpriseGroupPoliciesForWebview2]: ./concepts/enterprise.md#group-policies-for-webview2 "WebView2 的组策略-管理 WebView2 应用程序 |Microsoft 文档"  
[ConceptsVersioning]: ./concepts/versioning.md "了解浏览器版本和 WebView2 |Microsoft 文档"  
[ConceptsVersioningExperimentalApis]: ./concepts/versioning.md#experimental-apis "实验性 Api-了解浏览器版本和 WebView2 |Microsoft 文档"  
[GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows Forms 应用中的 WebView2 入门 |Microsoft 文档"  
[GettingstartedWpf]: ./gettingstarted/wpf.md "WPF | 中的 WebView2 入门 |Microsoft 文档"  
[HowtoDebug]: ./howto/debug.md "如何在与 WebView2 控件一起开发时进行调试 |Microsoft 文档"  

[ReferenceWin32Iwebview2acceleratorkeypressedeventargsHandle08190]: /microsoft-edge/webview2/reference/win32/iwebview2acceleratorkeypressedeventargs?view=webview2-0.8.355&preserve-view=true#handle "Handle-interface IWebView2AcceleratorKeyPressedEventArgs |Microsoft 文档"  
[ReferenceWin32Iwebview2containsfullscreenelementchangedeventhandler08190]: /microsoft-edge/webview2/reference/win32/iwebview2containsfullscreenelementchangedeventhandler?view=webview2-0.8.355&preserve-view=true "interface IWebView2ContainsFullScreenElementChangedEventHandler |Microsoft 文档"  
[ReferenceWin32Iwebview2settings2PutAredefaultcontextmenusenabled08190]: /microsoft-edge/webview2/reference/win32/iwebview2settings2?view=webview2-0.8.355&preserve-view=true#put_aredefaultcontextmenusenabled "put_AreDefaultContextMenusEnabled 接口 IWebView2Settings2 |Microsoft 文档"  
[ReferenceWin32Iwebview2settingsGetIsfullscreenallowedDeprecated08190]: /microsoft-edge/webview2/reference/win32/iwebview2settings?view=webview2-0.8.355&preserve-view=true#get_isfullscreenallowed_deprecated "get_IsFullscreenAllowed_deprecated 接口 IWebView2Settings |Microsoft 文档"  
[ReferenceWin32Iwebview2webmessagereceivedeventargsGetWebmessageasstring08190]: /microsoft-edge/webview2/reference/win32/iwebview2webmessagereceivedeventargs?view=webview2-0.8.355&preserve-view=true#get_webmessageasstring "get_WebMessageAsString 接口 IWebView2WebMessageReceivedEventArgs |Microsoft 文档"  
[ReferenceWin32Iwebview2webview4AddAcceleratorkeypressed08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#add_acceleratorkeypressed "add_AcceleratorKeyPressed 接口 IWebView2WebView4 |Microsoft 文档"  
[ReferenceWin32Iwebview2webviewAddDocumentstatechanged08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview?view=webview2-0.8.355&preserve-view=true#add_documentstatechanged "add_DocumentStateChanged 接口 IWebView2WebView |Microsoft 文档"  
[ReferenceWin32Iwebview2webview4Addremoteobject08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview4?view=webview2-0.8.355&preserve-view=true#addremoteobject "AddRemoteObject-接口 IWebView2WebView4 |Microsoft 文档"  
[ReferenceWin32Iwebview2webview5AddWebresourcerequested08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#add_webresourcerequested "add_WebResourceRequested 接口 IWebView2WebView5 |Microsoft 文档"  
[ReferenceWin32Iwebview2webview5Addwebresourcerequestedfilter08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#addwebresourcerequestedfilter "AddWebResourceRequestedFilter-接口 IWebView2WebView5 |Microsoft 文档"  
[ReferenceWin32Iwebview2webview5GetContainsfullscreenelement08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#get_containsfullscreenelement "get_ContainsFullScreenElement 接口 IWebView2WebView5 |Microsoft 文档"  
[ReferenceWin32Iwebview2webview5Removewebresourcerequestedfilter08190]: /microsoft-edge/webview2/reference/win32/iwebview2webview5?view=webview2-0.8.355&preserve-view=true#removewebresourcerequestedfilter "RemoveWebResourceRequestedFilter-接口 IWebView2WebView5 |Microsoft 文档"  
[ReferenceWin32WebView2IdlCreatewebview2environmentwithdetails08190]:  /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.8.355&preserve-view=true#createwebview2environmentwithdetails "CreateWebView2EnvironmentWithDetails-Globals |Microsoft 文档"  

[ReferenceWin32Icorewebview209430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2 |Microsoft 文档"  
[ReferenceWin32Icorewebview2acceleratorkeypressedeventargsGetHandled09430]: /microsoft-edge/webview2/reference/win32/icorewebview2acceleratorkeypressedeventargs?view=webview2-0.9.430&preserve-view=true#get_handled "get_Handled 接口 ICoreWebView2AcceleratorKeyPressedEventArgs |Microsoft 文档"  
[ReferenceWin32Icorewebview2AddContentloading09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_contentloading "add_ContentLoading 接口 ICoreWebView2 |Microsoft 文档"  
[ReferenceWin32Icorewebview2AddHistorychanged09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_historychanged "add_HistoryChanged 接口 ICoreWebView2 |Microsoft 文档"  
[ReferenceWin32Icorewebview2Addremoteobject09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#addremoteobject "AddRemoteObject-接口 ICoreWebView2 |Microsoft 文档"  
[ReferenceWin32Icorewebview2AddSourcechanged09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_sourcechanged "add_SourceChanged 接口 ICoreWebView2 |Microsoft 文档"  
[ReferenceWin32Icorewebview2AddWindowcloserequested09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#add_windowcloserequested "add_WindowCloseRequested 接口 ICoreWebView2 |Microsoft 文档"  
[ReferenceWin32Icorewebview2CoreWebview2ScriptDialogKind09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#core_webview2_script_dialog_kind "CORE_WEBVIEW2_SCRIPT_DIALOG_KIND 接口 ICoreWebView2 |Microsoft 文档"  
[ReferenceWin32Icorewebview2devtoolsprotocoleventreceiver09430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2DevToolsProtocolEventReceiver |Microsoft 文档"  
[ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverAddDevtoolsprotocoleventreceived09430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#add_devtoolsprotocoleventreceived "add_DevToolsProtocolEventReceived 接口 ICoreWebView2DevToolsProtocolEventReceiver |Microsoft 文档"  
[ReferenceWin32Icorewebview2devtoolsprotocoleventreceiverRemoveDevtoolsprotocoleventreceived09430]: /microsoft-edge/webview2/reference/win32/icorewebview2devtoolsprotocoleventreceiver?view=webview2-0.9.430&preserve-view=true#remove_devtoolsprotocoleventreceived "remove_DevToolsProtocolEventReceived 接口 ICoreWebView2DevToolsProtocolEventReceiver |Microsoft 文档"  
[ReferenceWin32Icorewebview2environmentGetBrowserversioninfo09430]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.430&preserve-view=true#get_browserversioninfo "get_BrowserVersionInfo 接口 ICoreWebView2Environment |Microsoft 文档"  
[ReferenceWin32Icorewebview2host09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true "interface ICoreWebView2Host |Microsoft 文档"  
[ReferenceWin32Webview2IdlGetcorewebview2browserversioninfo09430]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.430&preserve-view=true#getcorewebview2browserversioninfo "GetCoreWebView2BrowserVersionInfo-Globals |Microsoft 文档"  
[ReferenceWin32Icorewebview2hostGetZoomfactor09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#get_zoomfactor "get_ZoomFactor 接口 ICoreWebView2Host |Microsoft 文档"  
[ReferenceWin32Icorewebview2hostNotifyparentwindowpositionchanged09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#notifyparentwindowpositionchanged "NotifyParentWindowPositionChanged-接口 ICoreWebView2Host |Microsoft 文档"  
[ReferenceWin32Icorewebview2hostPutZoomfactor09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#put_zoomfactor "put_ZoomFactor 接口 ICoreWebView2Host |Microsoft 文档"  
[ReferenceWin32Icorewebview2hostSetboundsandzoomfactor09430]: /microsoft-edge/webview2/reference/win32/icorewebview2host?view=webview2-0.9.430&preserve-view=true#setboundsandzoomfactor "SetBoundsAndZoomFactor-接口 ICoreWebView2Host |Microsoft 文档"  
[ReferenceWin32Icorewebview2httpheaderscollectioniteratorGetHascurrentheader09430]: /microsoft-edge/webview2/reference/win32/icorewebview2httpheaderscollectioniterator?view=webview2-0.9.430&preserve-view=true#get_hascurrentheader "get_HasCurrentHeader 接口 ICoreWebView2HttpHeadersCollectionIterator |Microsoft 文档"  
[ReferenceWin32Icorewebview2httprequestheadersGetheaders09430]: /microsoft-edge/webview2/reference/win32/icorewebview2httprequestheaders?view=webview2-0.9.430&preserve-view=true#getheaders "GetHeaders-接口 ICoreWebView2HttpRequestHeaders |Microsoft 文档"  
[ReferenceWin32Icorewebview2httpresponseheadersGetheader09430]: /microsoft-edge/webview2/reference/win32/icorewebview2httpresponseheaders?view=webview2-0.9.430&preserve-view=true#getheader "GetHeader-接口 ICoreWebView2HttpResponseHeaders |Microsoft 文档"  
[ReferenceWin32Icorewebview2Removeremoteobject09430]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.430&preserve-view=true#removeremoteobject "RemoveRemoteObject-接口 ICoreWebView2 |Microsoft 文档"  
[ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09430]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed 接口 ICoreWebView2Settings |Microsoft 文档"  
[ReferenceWin32Icorewebview2settingsGetIszoomcontrolenabled09430]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.430&preserve-view=true#get_iszoomcontrolenabled "get_IsZoomControlEnabled 接口 ICoreWebView2Settings |Microsoft 文档"  
[ReferenceWin32Icorewebview2webmessagereceivedeventargsTrygetwebmessageasstring09430]: /microsoft-edge/webview2/reference/win32/icorewebview2webmessagereceivedeventargs?view=webview2-0.9.430&preserve-view=true#trygetwebmessageasstring "TryGetWebMessageAsString-接口 ICoreWebView2WebMessageReceivedEventArgs |Microsoft 文档"  

[ReferenceWin32Icorewebview2AddFramenavigationcompleted09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_framenavigationcompleted "add_FrameNavigationCompleted 接口 ICoreWebView2 |Microsoft 文档"  
[ReferenceWin32Icorewebview2Addhostobjecttoscript09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#addhostobjecttoscript "AddHostObjectToScript-接口 ICoreWebView2 |Microsoft 文档"  
[ReferenceWin32Icorewebview2AddNewwindowrequested09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#add_newwindowrequested "add_NewWindowRequested 接口 ICoreWebView2 |Microsoft 文档"  
[ReferenceWin32Icorewebview2environmentGetBrowserversionstring09488]: /microsoft-edge/webview2/reference/win32/icorewebview2environment?view=webview2-0.9.488&preserve-view=true#get_browserversionstring " |Microsoft 文档"  
[ReferenceWin32Icorewebview2environmentoptions09488]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.488&preserve-view=true "interface ICoreWebView2EnvironmentOptions |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalcompositioncontroller09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCompositionController |Microsoft 文档"
[ReferenceWin32Icorewebview2experimentalcompositioncontroller09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCompositionController |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalcursorchangedeventhandler09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcursorchangedeventhandler?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCursorChangedEventHandler |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalpointerinfo09488]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalpointerinfo?view=webview2-0.9.488-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalPointerInfo |Microsoft 文档"  
[ReferenceWin32Icorewebview2Removehostobjectfromscript09488]: /microsoft-edge/webview2/reference/win32/icorewebview2?view=webview2-0.9.488&preserve-view=true#removehostobjectfromscript "RemoveHostObjectFromScript-接口 ICoreWebView2 |Microsoft 文档"  
[ReferenceWin32Icorewebview2settingsGetAreremoteobjectsallowed09488]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_areremoteobjectsallowed "get_AreRemoteObjectsAllowed 接口 ICoreWebView2Settings |Microsoft 文档"  
[ReferenceWin32Icorewebview2settingsGetIsbuiltinerrorpageenabled09488]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.488&preserve-view=true#get_isbuiltinerrorpageenabled " |Microsoft 文档"  
[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithdetails09488]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithdetails "CreateCoreWebView2EnvironmentWithDetails-Globals |Microsoft 文档"  
[ReferenceWin32Webview2IdlCreatecorewebview2environmentwithoptions09488]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft 文档"  
[ReferenceWin32Webview2IdlGetavailablecorewebview2browserversionstring09488]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.488&preserve-view=true#getavailablecorewebview2browserversionstring "GetAvailableCoreWebView2BrowserVersionString-Globals |Microsoft 文档"  

[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseAddRasterizationscalechanged]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#add_rasterizationscalechanged "add_RasterizationScaleChanged 接口 ICoreWebView2ExperimentalController |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetBoundsMode]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_boundsmode "get_BoundsMode 接口 ICoreWebView2ExperimentalController |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetRasterizationscale]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_rasterizationscale "get_RasterizationScale 接口 ICoreWebView2ExperimentalController |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalcontrollerViewWebview210721PrereleaseGetShouldDetectMonitorScaleChanges]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcontroller?view=webview2-1.0.721-prerelease&preserve-view=true#get_shoulddetectmonitorscalechanges "get_ShouldDetectMonitorScaleChanges 接口 ICoreWebView2ExperimentalController |Microsoft 文档"  

[DotnetApiMicrosoftWebWebview2Core]: /dotnet/api/microsoft.web.webview2.core "WebView2 命名空间 |Microsoft 文档"  
[DotnetApiMicrosoftWebWebview2Wpf]: /dotnet/api/microsoft.web.webview2.wpf "WebView2 命名空间 |Microsoft 文档"  
[DotnetApiMicrosoftWebWebview2Winforms]: /dotnet/api/microsoft.web.webview2.winforms "WinForms 命名空间 | WebView2 命名空间 |Microsoft 文档"  

[DotnetApiMicrosoftWebWebview2CoreWebview2runtimenotfoundexception]: /dotnet/api/microsoft.web.webview2.core.webview2runtimenotfoundexception "CoreWebView2 WebView2RuntimeNotFound (WebView2) |Microsoft 文档"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2]: /dotnet/api/microsoft.web.webview2.core.corewebview2 "CoreWebView2 Class (WebView2) |Microsoft 文档"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environment]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment "CoreWebView2Environment Class (WebView2) |Microsoft 文档"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentComparebrowserversions]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.comparebrowserversions "CoreWebView2Environment CompareBrowserVersions (String、String) Method (WebView2) |Microsoft 文档"
[DotnetApiMicrosoftWebWebview2CoreCorewebview2environmentGetavailablebrowserversionstring]: /dotnet/api/microsoft.web.webview2.core.corewebview2environment.getavailablebrowserversionstring "CoreWebView2Environment GetAvailableBrowserVersionString (String) Method (WebView2) |Microsoft 文档"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Newwindowrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.newwindowrequested "CoreWebView2) 中的 Webview.newwindowrequested 事件 (WebView2Microsoft 文档"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Permissionrequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.permissionrequested "CoreWebView2) 中的 Webview.permissionrequested 事件 (WebView2Microsoft 文档"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Scriptdialogopening]: /dotnet/api/microsoft.web.webview2.core.corewebview2.scriptdialogopening "CoreWebView2) 中的 ScriptDialogOpening 事件 (WebView2Microsoft 文档"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2Webresourcerequested]: /dotnet/api/microsoft.web.webview2.core.corewebview2.webresourcerequested "CoreWebView2) 中的 WebResourceRequested 事件 (WebView2Microsoft 文档"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2httprequestheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httprequestheaders "CoreWebView2HttpRequestHeaders Class (WebView2) |Microsoft 文档"  
[DotnetApiMicrosoftWebWebview2CoreCorewebview2httpresponseheaders]: /dotnet/api/microsoft.web.webview2.core.corewebview2httpresponseheaders "CoreWebView2HttpResponseHeaders Class (WebView2) |Microsoft 文档"  

[DotnetApiMicrosoftWebWebview2WinformsCorewebview2creationproperties]: /dotnet/api/microsoft.web.webview2.winforms.corewebview2creationproperties "CoreWebView2CreationProperties WebView2 (Winforms) |Microsoft 文档"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Source]: /dotnet/api/microsoft.web.webview2.winforms.webview2.source "Webview2)  (Winforms 的 WebView2 |Microsoft 文档"  

[DotnetApiMicrosoftWebWebview2WpfWebview2Buildwindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.buildwindowcore "WebView2 BuildWindowCore (HandleRef) 方法 () |Microsoft 文档"  
[DotnetApiMicrosoftWebWebview2WpfWebview2Destroywindowcore]: /dotnet/api/microsoft.web.webview2.wpf.webview2.destroywindowcore "WebView2 DestroyWindowCore (HandleRef) 方法 () |Microsoft 文档"  

[DotnetApiMicrosoftWebWebview2WpfWebview2Acceleratorkeypressed]: /dotnet/api/microsoft.web.webview2.wpf.webview2.acceleratorkeypressed "acceleratorkeypressed | | webview2 |Microsoft 文档"  

[DotnetApiMicrosoftWebWebview2Corewebview2initializationcompletedeventargs]: /dotnet/api/microsoft.web.webview2.core.corewebview2initializationcompletedeventargs "CoreWebView2InitializationCompletedEventArgs 类 |Microsoft 文档"  

[ReferenceWin32Icorewebview2Addhostobjecttoscript09538]: /microsoft-edge/webview2/reference/win32/icorewebview2#addhostobjecttoscript?view=webview2-0.9.538&preserve-view=true "AddHostObjectToScript-接口 ICoreWebView2 |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-0.9.538-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived 接口 ICoreWebView2Experimental |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentaloptionsGetIssinglesignonusingosprimaryaccountenabled09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironmentoptions?view=webview2-0.9.538-prerelease&preserve-view=true#get_issinglesignonusingosprimaryaccountenabled "get_IsSingleSignOnUsingOSPrimaryAccountEnabled 接口 ICoreWebView2ExperimentalEnvironmentOptions |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalnewwindowrequestedeventargsGetWindowfeatures09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalnewwindowrequestedeventargs?view=webview2-0.9.538-prerelease&preserve-view=true#get_windowfeatures "get_WindowFeatures 接口 ICoreWebView2ExperimentalNewWindowRequestedEventArgs |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalwindowfeatures09538]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwindowfeatures?view=webview2-0.9.538-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWindowFeatures |Microsoft 文档"  
[ReferenceWin32Icorewebview2newwindowrequestedeventargsGetIsuserinitiated09538]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.538&preserve-view=true#get_isuserinitiated "get_IsUserInitiated 接口 ICoreWebView2NewWindowRequestedEventArgs |Microsoft 文档"  
[ReferenceWin32Icorewebview2settingsGetArehostobjectsallowed09538]: /microsoft-edge/webview2/reference/win32/icorewebview2settings?view=webview2-0.9.538&preserve-view=true#get_arehostobjectsallowed "get_AreHostObjectsAllowed 接口 ICoreWebView2Settings |Microsoft 文档"  
[ReferenceWin32IdlCreatecorewebview2environmentwithoptions09538]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.538&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft 文档"  

[ReferenceWin32Icorewebview2environmentoptionsGetAllowsinglesignonusingosprimaryaccount09622]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#get_allowsinglesignonusingosprimaryaccount "get_AllowSingleSignOnUsingOSPrimaryAccount 接口 ICoreWebView2EnvironmentOptions |Microsoft 文档"  
[ReferenceWin32Icorewebview2environmentoptionsPutAdditionalbrowserarguments09622]: /microsoft-edge/webview2/reference/win32/icorewebview2environmentoptions?view=webview2-0.9.622&preserve-view=true#put_additionalbrowserarguments "put_AdditionalBrowserArguments 接口 ICoreWebView2EnvironmentOptions |Microsoft 文档"  
[ReferenceWin32Icorewebview2newwindowrequestedeventargsGetWindowfeatures09622]: /microsoft-edge/webview2/reference/win32/icorewebview2newwindowrequestedeventargs?view=webview2-0.9.622&preserve-view=true#get_windowfeatures "get_WindowFeatures 接口 ICoreWebView2NewWindowRequestedEventArgs |Microsoft 文档"  
[ReferenceWin32Icorewebview2windowfeatures09622]: /microsoft-edge/webview2/reference/win32/icorewebview2windowfeatures?view=webview2-0.9.622&preserve-view=true "interface ICoreWebView2WindowFeatures |Microsoft 文档"  
[ReferenceWin32IdlCreatecorewebview2environmentwithoptions09622]: /microsoft-edge/webview2/reference/win32/webview2-idl?view=webview2-0.9.622&preserve-view=true#createcorewebview2environmentwithoptions "CreateCoreWebView2EnvironmentWithOptions-Globals |Microsoft Edge"  
[ReferenceWin32Icorewebview2experimentalenvironment09628]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalenvironment?view=webview2-0.9.628-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalEnvironment |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalwebresourceresponsereceivedeventargsPopulateresponsecontent09628]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponsereceivedeventargs?view=webview2-0.9.628-prerelease&preserve-view=true#populateresponsecontent "PopulateResponseContent-接口 ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs |Microsoft 文档"  

[ReferenceWin32Icorewebview2experimentalAddDomcontentloaded10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#add_domcontentloaded "add_DOMContentLoaded 接口 ICoreWebView2Experimental |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalAddWebresourceresponsereceived10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#add_webresourceresponsereceived "add_WebResourceResponseReceived 接口 ICoreWebView2Experimental |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalGetCookiemanager10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#get_cookiemanager "get_CookieManager 接口 ICoreWebView2Experimental |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalGetEnvironment10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#get_environment "get_Environment 接口 ICoreWebView2Experimental |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalNavigatewithwebresourcerequest10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimental?view=webview2-1.0.674-prerelease&preserve-view=true#navigatewithwebresourcerequest "NavigateWithWebResourceRequest-接口 ICoreWebView2Experimental |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalcompositioncontroller2GetSystemcursorid10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller2#get_systemcursorid?view=webview2-1.0.674-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWebResourceResponseView |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalwebresourceresponseview10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalWebResourceResponseView |Microsoft 文档"  
[ReferenceWin32Icorewebview2experimentalwebresourceresponseviewGetcontent10674]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalwebresourceresponseview?view=webview2-1.0.674-prerelease&preserve-view=true#getcontent "GetContent-接口 ICoreWebView2ExperimentalWebResourceResponseView |Microsoft 文档"  

[ReferenceWin32Icorewebview2experimentalcompositioncontroller3]: /microsoft-edge/webview2/reference/win32/icorewebview2experimentalcompositioncontroller3?view=webview2-1.0.721-prerelease&preserve-view=true "interface ICoreWebView2ExperimentalCompositionController3 |Microsoft 文档"  

[DeployedgeMicrosoftEdgePolicies]: /deployedge/microsoft-edge-policies "Microsoft Edge-策略 |Microsoft 文档"  
[DeployedgeMicrosoftEdgeWebviewPolicies]: /deployedge/microsoft-edge-webview-policies "Microsoft Edge WebView2-政策 |Microsoft 文档"  

[WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]: /windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview "Microsoft Defender 应用程序防护 (Windows 10) Windows security |Microsoft 文档"

[DotnetApiSystemComponentmodelCancelEventargs]: /dotnet/api/system.componentmodel.canceleventargs "CancelEventArgs Class (ComponentModel) |Microsoft 文档"  
[DotnetApiSystemEventargs]: /dotnet/api/system.eventargs "EventArgs 类 (System) |Microsoft 文档"  
[DotnetStandardAssemblyStrongNamed]: /dotnet/standard/assembly/strong-named "强名称程序集 |Microsoft 文档"  

[GithubMicrosoftedgeWebviewfeedbackIssue1]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/1 "MicrosoftEdge/WebViewFeedback 问题1的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue12]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/12 "MicrosoftEdge/WebViewFeedback 问题12的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue13]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/13 "MicrosoftEdge/WebViewFeedback 问题13的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue14]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/14 "MicrosoftEdge/WebViewFeedback 问题14的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue16]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/16 "MicrosoftEdge/WebViewFeedback 问题16的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue17]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/17 "MicrosoftEdge/WebViewFeedback 问题17的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue18]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/18 "MicrosoftEdge/WebViewFeedback 问题18的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue19]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/19 "MicrosoftEdge/WebViewFeedback 问题19的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue22]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/22 "MicrosoftEdge/WebViewFeedback 问题22的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue27]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/27 "MicrosoftEdge/WebViewFeedback 问题27的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue28]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/28 "MicrosoftEdge/WebViewFeedback 问题28的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue30]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/30 "MicrosoftEdge/WebViewFeedback 问题30的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue32]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/32 "MicrosoftEdge/WebViewFeedback 问题32的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue36]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/36 "MicrosoftEdge/WebViewFeedback 问题36的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue57]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/57 "MicrosoftEdge/WebViewFeedback 问题57的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue70]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/70 "MicrosoftEdge/WebViewFeedback 问题70的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue74]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/74 "MicrosoftEdge/WebViewFeedback 问题74的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue95]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/95 "MicrosoftEdge/WebViewFeedback 问题95的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue108]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/108 "MicrosoftEdge/WebViewFeedback 问题108的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue113]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/113 "MicrosoftEdge/WebViewFeedback 问题113的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue119]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/119 "MicrosoftEdge/WebViewFeedback 问题119的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue131]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/131 "MicrosoftEdge/WebViewFeedback 问题131的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue148]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/148 "MicrosoftEdge/WebViewFeedback 问题148的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue168]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/168 "MicrosoftEdge/WebViewFeedback 问题168的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue177]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/177 "MicrosoftEdge/WebViewFeedback 问题177的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue179]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/179 "MicrosoftEdge/WebViewFeedback 问题179的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue181]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/181 "MicrosoftEdge/WebViewFeedback 问题181的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue183]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/183 "MicrosoftEdge/WebViewFeedback 问题183的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue185]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/185 "MicrosoftEdge/WebViewFeedback 问题185的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue204]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/204 "MicrosoftEdge/WebViewFeedback 问题204的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue219]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/219 "MicrosoftEdge/WebViewFeedback 问题219的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue228]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/228 "MicrosoftEdge/WebViewFeedback 问题228的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue235]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/235 "MicrosoftEdge/WebViewFeedback 问题235的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue250]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/250 "MicrosoftEdge/WebViewFeedback 问题250的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue288]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/288 "MicrosoftEdge/WebViewFeedback 问题288的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue293]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/293 "MicrosoftEdge/WebViewFeedback 问题293的反馈存储库"
[GithubMicrosoftedgeWebviewfeedbackIssue318]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/318 "MicrosoftEdge/WebViewFeedback 问题318的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue335]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/335 "MicrosoftEdge/WebViewFeedback 问题335的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue371]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/371 "MicrosoftEdge/WebViewFeedback 问题371的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue382]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/382 "MicrosoftEdge/WebViewFeedback 问题382的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue431]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/431 "MicrosoftEdge/WebViewFeedback 问题431的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue432]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/432 "MicrosoftEdge/WebViewFeedback 问题432的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue461]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/461 "MicrosoftEdge/WebViewFeedback 问题461的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue525]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/525 "MicrosoftEdge/WebViewFeedback 问题525的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue549]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/549 "MicrosoftEdge/WebViewFeedback 问题549的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue560]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/560 "MicrosoftEdge/WebViewFeedback 问题560的反馈存储库"  
[GithubMicrosoftedgeWebviewfeedbackIssue611]:  https://github.com/MicrosoftEdge/WebViewFeedback/issues/611 "MicrosoftEdge/WebViewFeedback 问题611的反馈存储库"  

[GithubMicrosoftedgeWebview2AnnouncementIssue2]:  https://github.com/MicrosoftEdge/WebView2Announcement/issues/2 "MicrosoftEdge/WebViewAnnouncement 问题2的公告存储库"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesPr17]: https://github.com/MicrosoftEdge/WebView2Samples/pull/17 "将 project 移动到使用最新 WebView2 SDK 0.9.430-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API Sample-MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftDevblogDotnetAnnouncingGeneralAvailabilityForMicrosoftEdgeWebview2ForNetFixedDistributionMethod]: https://devblogs.microsoft.com/dotnet/announcing-general-availability-for-microsoft-edge-webview2-for-net-and-fixed-distribution-method "宣布适用于 .NET 和固定分发方法的 Microsoft Edge WebView2 常规可用性 | .NET 博客"  

[MicrosoftDeveloperMicrosoftEdgeWebView2]: https://developer.microsoft.com/microsoft-edge/webview2/ "Microsoft Edge WebView2 |Microsoft Edge 开发人员"  

[NuGetGallery]:  https://www.nuget.org/packages/Microsoft.Web.WebView2 "NuGet 库 |WebView2"  
[NuGetGallery0.8.149]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.149 "NuGet 库 |WebView2 v 0.8.149"  
[NuGetGallery0.8.190]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.190 "NuGet 库 |WebView2 v 0.8.190"  
[NuGetGallery0.8.230]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.230 "NuGet 库 |WebView2 v 0.8.230"  
[NuGetGallery0.8.270]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.270 "NuGet 库 |WebView2 v 0.8.270"  
[NuGetGallery0.8.314]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.314 "NuGet 库 |WebView2 v 0.8.314"  
[NuGetGallery0.8.355]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.8.355 "NuGet 库 |WebView2 v 0.8.355"  
[NuGetGallery0.9.430]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.430 "NuGet 库 |WebView2 v 0.9.430"  
[NuGetGallery0.9.488]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.488 "NuGet 库 |WebView2 v 0.9.488"  
[NuGetGallery0.9.515-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.515-prerelease "NuGet 库 |WebView2 v 0.9.515 预发布"  
[NuGetGallery0.9.538]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.538 "NuGet 库 |WebView2 v 0.9.538"  
[NuGetGallery0.9.579]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.579 "NuGet 库 |WebView2 v 0.9.579"
[NuGetGallery0.9.622.11]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.622.11 "NuGet 库 |WebView2 v 0.9.622.11"
[NuGetGallery1.0.622.22]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.622.22 "NuGet 库 |WebView2 v 1.0.622.22"
[NuGetGallery1.0.664.34]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.34 "NuGet 库 |WebView2 v 1.0.664.34"
[NuGetGallery1.0.664.37]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.664.37 "NuGet 库 |WebView2 v 1.0.664.37"
[NuGetGallery0.9.628-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/0.9.628-prerelease "NuGet 库 |WebView2 v 0.9.628 预发布"  
[NuGetGallery1.0.674-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.674-prerelease "NuGet 库 |WebView2 v 1.0.674 预发布"  
[NuGetGallery1.0.721-prerelease]:  https://www.nuget.org/packages/Microsoft.Web.WebView2/1.0.721-prerelease "NuGet 库 |WebView2 v 1.0.721 预发布"  

[WindowsBlogsMsedgedevEdgeWebview2GeneralAvailability]: https://blogs.windows.com/msedgedev/edge-webview2-general-availability "宣布 Microsoft Edge WebView2 常规可用性 |Microsoft Edge 博客"  
