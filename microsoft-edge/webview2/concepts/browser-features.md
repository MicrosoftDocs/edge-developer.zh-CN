---
description: 浏览器功能与 webView2 Microsoft Edge差异
title: 浏览器功能与 webView2 Microsoft Edge差异
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2, IWebView2WebView, WebView2, webview, wpf apps, wpf, edge, ICoreWebView2, ICoreWebView2Host, browser control, edge html
no-loc: ["Autofill for Addresses", "Autofill for Passwords", Autofill for Payments", Browser Extensions", "Browser Task Manager", "Collections", "Continue-where-I-left-off prompt", "Downloads", "Edge Shopping", "Family Safety", "Favorites", "Hotkeys", "IE Mode" ,"Immersive Reader", "Intrusive Ads", "Read Aloud", "Smart Screen", "Translate", "Tracking Prevention", "Profile and Identity", "Web Payment API", "Windows Defender Application Guard","edge:// URLs"]  
---
# <a name="browser-feature-differences-between-microsoft-edge-and-webview2"></a>浏览器功能与 webView2 Microsoft Edge差异  

WebView2 基于新Microsoft Edge浏览器。  你有机会将功能从浏览器扩展到基于 WebView2 的应用，这很有用。  但是，由于 WebView2 不限于类似浏览器的应用，因此需要修改或删除一些浏览器功能。  本文提供以下信息。  

*   修改后的浏览器功能和支持信息。   
*   启用或关闭功能的功能。  
*   有关键盘快捷方式的指南。  
    
## <a name="design-guidelines"></a>设计指南  

在 WebView2 上下文中，浏览器功能遵循以下设计准则。  

*   大多数功能在 WebView2 和 webView2 Microsoft Edge。  如果功能在 WebView2 上下文中不起作用或出于其他原因，则功能会修改或关闭。 
*   WebView2 功能不包括Microsoft Edge品牌。  
    
## <a name="features"></a>功能  

下表显示了与浏览器浏览器不同的 WebView2 Microsoft Edge功能。   

*   **默认** 状态指示功能是新 WebView2 实例上默认体验的一部分。  
*   **可** 配置指示可以使用 WebView2 API 或命令行开关打开或关闭该功能。  
    
> [!NOTE]  
> 本文不介绍使用命令行开关修改功能。  有关使用命令行开关打开和关闭功能的信息，请导航到"命令行Chromium[列表。][PeterExperimentsChromiumCommandLineSwitches]  
    
| 功能 | 默认状态 | 可配置 | 详细信息 |  
|:--- |:--- |:--- | :--- |  
| Autofill for Addresses | 开 | 是 | 默认情况下，此功能已打开，可以使用 WebView2 自动填充 API 将其打开或关闭。  |  
| Autofill for Passwords | 开 | 是 | 默认情况下，此功能已打开，可以使用 WebView2 自动填充 API 将其打开或关闭。  |  
| 付款自动填充 | 关闭 | 否 | 此功能已关闭。  |  
| 浏览器扩展 | 关闭 | 否 | 此功能已关闭。  |  
| Browser Task Manager | 关闭 | 否 | 此功能已关闭。  |  
| Collections | 关闭 | 否 | 此功能已关闭。  |  
| Continue-where-I-left-off prompt | 关闭 | 否 | 此功能已关闭。  |  
| Downloads | 开 | 是 | WebView2 提供了一个 API，允许你自定义下载 UI 以操作下载。 例如，可以阻止、重定向、保存、暂停等。  <!--For more information, navigate to [download API][Webview2ReferenceDownloadApi].--> |  
| Edge Shopping | 关闭 | 否 | 此功能已关闭。  |  
| Family Safety | 关闭 | 否 | 此功能已关闭。  |  
| Favorites | 关闭 | 否 | 此功能已关闭。  |  
| IE Mode | 关闭 | 否 | 此功能已关闭。 与 IE 模式（如 MHT 或 BIN 支持）相比，WebView2 不支持 IE 模式 (行为) 。 |  
| Immersive Reader | 关闭 | 否 | 此功能取决于用于交互的浏览器 UI。  此功能已关闭。  |  
| Intrusive Ads | 关闭 | 否 | 此功能已关闭。  |  
| 键盘快捷方式 | 查看详细信息 | 查看详细信息 | 默认情况下关闭的键盘快捷方式在 WebView2 中没有意义或导致问题。  不得打开或关闭这些快捷方式。  相反，您可以使用 事件侦听组合键 `AcceleratorKeyPressed` ，并根据需要创建自定义响应。  有关详细信息，请导航到"[其他键盘快捷方式信息"。](#additional-keyboard-shortcuts-information) |  
| 推送通知 | 关闭 | 否 | WebView2 中未实现此功能。  有关详细信息，请导航到添加对[HTML5 通知 API (#308) 。 ][GithubMicrosoftedgeWebview2feedbackIssues308] |  
| Read Aloud | 关闭 | 否 | 此功能已关闭。  |  
| Smart Screen | 开`*` | 否 | `*` 此功能的 UI 已删除，但基础功能仍然可用。  此外，您还可以关闭 Smart Screen 使用命令行开关。  |  
| Translate | 关闭 | 否 | 此功能已关闭。  |  
| Tracking Prevention | 开`*` | 否 | `*` 此功能的 UI 已删除，但基础功能仍然可用。  跟踪防护始终设置为平衡。|  
| Profile and Identity | 关闭 | 否 | 同步收藏夹、Cookie 等的功能已关闭。  |  
| Web Payment API | 关闭 | 否 | 此功能已关闭。  | 
| Windows Defender Application Guard | 关闭 | 否 | 此功能已关闭。  |  
| edge:// URLs | 查看详细信息 | 否 | 设置浏览器Microsoft Edge URL `edge://` 上。  由于这些网页中的大多数Microsoft Edge WebView2 上下文中具有品牌或没有意义，因此其中一些 URL 已关闭。  有关详细信息，请导航到["阻止的内部 URL"。](#blocked-internal-urls)  |  

## <a name="blocked-internal-urls"></a>阻止的内部 URL  

以下Microsoft Edge和 Google Chrome 设置网页在 WebView2 中不可用。  

*   `chrome-search://local-ntp/local-ntp.html`  
*   `edge://application-guard-internals`  
*   `edge://apps`  
*   `edge://compat`  
*   `edge://extensions`  
*   `edge://favorites`  
*   `edge://help`  
*   `edge://management`  
*   `edge://network-error`  
*   `edge://new-tab-page`  
*   `edge://newtab`  
*   `edge://omnibox`  
*   `edge://settings`  
*   `edge://supervised-user-internals`  
*   `edge://version`  
    
## <a name="additional-keyboard-shortcuts-information"></a>其他键盘快捷方式信息  

键盘快捷方式或键绑定在 Microsoft Edge 和 WebView2 中受支持。  当Microsoft Edge时，默认键绑定可能会更改。  此外，如果 WebView2 现在支持此功能，则默认情况下关闭的键盘快捷方式可能会打开。  若要避免更改键盘快捷方式，可以设置为 ，这将关闭访问浏览器功能的所有键，但会启用所有基本的文本编辑和移动 `AreBrowserAcceleratorKeysEnabled` `FALSE` 快捷方式。  

下表列出了 WebView2 中始终关闭的快捷方式。  星号 \ (\) 字符指示快捷方式未关闭，但它访问的功能已关闭或不适用于 `*` WebView2。  

| 操作 | Windows |  
|:--- |:--- |  
| 添加到 Favorites | `Ctrl`+`D` |  
| 将所有选项卡添加到 Favorites | `Ctrl`+`Shift`+`D` |  
| 焦点位置 | `Ctrl`+`L, Alt`+`D` |  
| 粘贴并转到 | `Ctrl`+`Shift`+`L` |  
| 打开文件 | `Ctrl`+`O` |  
| Read Aloud `*` | `Ctrl`+`Shift`+`U` |  
| Web 捕获 `*` | `Ctrl`+`Shift`+`S` |  
| 边栏 `*` | `Ctrl`+`Shift`+`E` |  
| 保存页面 | `Ctrl`+`S` |  
| 选择最后一个选项卡 | `Ctrl`+`9` |  
| 选择下一个选项卡 | `Ctrl`+`Tab` |  
| 选择上一个选项卡 | `Ctrl`+`Shift`+`Tab` |  
| 选择选项卡 \ (1 - 8\)  | `Ctrl`+`(1-8)` |  
| 显示 Favorites 栏 `*` | `Ctrl`+`Shift`+`B` |  
| 帮助 | `F1` |  
| 焦点下一个窗格 `*` | `F6` |  
| 焦点上一个窗格 `*` | `Shift`+`F6` |  
| 项目浏览 `*` | `F7` |  
| 阅读视图 `*` | `F9` |  
| 焦点菜单栏 | `F10` |  
| 显示标识菜单 `*` | `Ctrl`+`Shift`+`M` |  
| Browser Task Manager `*` | `Shift`+`Escape` |  
| Edge 反馈 `*` | `Shift`+`Alt`+`I` |  
| 静音选项卡 `*` | `Ctrl`+`M` |  
| 新建隐身窗口 | `Ctrl`+`Shift`+`N` |  
| 新建选项卡 | `Ctrl`+`T` |  
| 新建窗口 | `Ctrl`+`N` |  
| "还原上次关闭"选项卡 | `Ctrl`+`Shift`+`T` |  
| 对焦 Favorites | `Alt`+`Shift`+`B` |  
| 焦点非活动弹出窗口 | `Alt`+`Shift`+`A` |  
| 焦点搜索 | `Ctrl`+`E`, `Ctrl`+`K`, `Search Key` |  
| "重复"选项卡 | `Ctrl`+`Shift`+`K` |  
| 焦点工具栏 `*` | `Alt`+`Shift`+`T` |  
| 主页 | `Alt`+`Home`, `Browser Home Key` |  
| 显示应用菜单 | `Alt`+`E, Alt`+`F` |  
| 显示 Favorites | `Ctrl`+`Shift`+`O` |  
| 显示 Downloads | `Ctrl`+`J` |  
| 显示历史记录 | `Ctrl`+`H` |  
| 显示阅读模式栏 `*` | `Shift`+`Alt`+`R` |  
| 显示 Collections `*` | `Ctrl`+`Shift`+`Y` |  

以下键盘快捷方式始终关闭，在未处理事件时显示的窗口中 `NewWindowRequested` 除外。

| 操作 | Windows |  
|:--- |:--- |  
| 关闭选项卡 | `Ctrl`+`W, Ctrl`+`F4` |  
| 关闭窗口 | `Ctrl`+`Shift`+`W` |  
| 全屏 | `F11` |  

如果设置为 `AreBrowserAcceleratorKeysEnabled` `FALSE` ，则以下其他键盘快捷方式将关闭。  

| 操作 | Windows |  
|:--- |:--- |  
| 停止 | `Escape` |  
| 在页面上查找 | `Ctrl`+`F` |  
| 查找下一个 | `Ctrl`+`G` |  
| 查找上一个 | `Ctrl`+`Shift`+`G` |  
| Print | `Ctrl`+`P` |  
| 刷新 | `Ctrl`+`R`, `F5`, `Reload Key` |  
| 刷新（不含缓存） | `Ctrl`+`Shift`+`R`, `Ctrl`+`F5`, `Shift`+`F5`, `Ctrl`+`Refresh`, `Shift`+`Refresh` |  
| 缩小 | `Ctrl`+`-` |  
| 放大 | `Ctrl`+`+` |  
| 重置缩放 | `Ctrl`+`0` |  
| 查找下一个 | `F3` |  
| 查找上一个 | `Shift`+`F3` |  
| 后退 | `Alt`+`Left, Browser Back Key` |  
| 前进 | `Alt`+`Right`, `Browser Forward Key` |  
| Print | `Ctrl`+`P` |  
| 打开/关闭 DevTools | `Ctrl`+`Shift`+`I` |  
| 打开 DevTools 控制台 | `Ctrl`+`Shift`+`J` |  
| 打开 DevTools Inspect | `Ctrl`+`Shift`+`C` |  

> [!Note] 
> 若要单独自定义任何键，请使用 [AcceleratorKeyPressed][DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444] 事件。  

## <a name="getting-in-touch-with-the-microsoft-edge-webview2-team"></a>与 WebView2 Microsoft Edge联系  

[!INCLUDE [contact WebView2 team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

<!--[Webview2ReferenceDownloadApi]: ./download-api.md "download API | Microsoft Docs"  -->  

[DotnetApiMicrosoftWebWebview2CoreCorewebview2controllerAcceleratorkeypressedViewWebview2Dotnet1077444]: /dotnet/api/microsoft.web.webview2.core.corewebview2controller.acceleratorkeypressed?view=webview2-dotnet-1.0.774.44&preserve-view=true "CoreWebView2Controller.AcceleratorKeyPressed 事件|Microsoft Docs"  

[DevtoolsShortcutsIndex]: ../../devtools-guide-chromium/shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式 | Microsoft Docs"  

[GithubMicrosoftedgeWebview2feedbackIssues308]: https://github.com/MicrosoftEdge/WebView2Feedback/issues/308 "添加对 HTML5 通知 API (#308) |GitHub"  

[PeterExperimentsChromiumCommandLineSwitches]: https://peter.sh/experiments/chromium-command-line-switches "命令行Chromium列表|Peter Beverloo"  
