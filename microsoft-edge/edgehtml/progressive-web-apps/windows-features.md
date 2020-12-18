---
description: 使用本机应用功能逐步增强适用于 Windows 的 PWA
title: 定制适用于 Windows (EdgeHTML) PWA
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 Web 应用， PWA， Edge， Windows， WinRT， UWP， EdgeHTML
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 59612d8292d4c4d4d7073b843386364d1ac55c5d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232438"
---
# 定制适用于 Windows (EdgeHTML) PWA  

安装在 Windows 10 上的[][PwaIndexWindows10]PWA 享受作为通用 Windows 平台[\ (UWP\) ][WindowsUWPGetStartedGuide]应用运行的所有优势，包括通过 Windows 应用沙盒安全性和对 Windows 运行时[\ (WinRT\) ) ][UwpApiIndex] API 的完全访问权限的保护，包括以下这些 API：  

*   控制设备功能 \ (例如相机、麦克风、GPS\)   
*   访问用户资源 \ (例如日历、联系人、文档、音乐\)   
*   通过 Cortana 语音命令启动/导航应用  
*   通过 Windows 操作中心 (桌面任务栏和上下文菜单\)   
    
这些只是 Windows 上 PWA \ (EdgeHTML\) 的一部分。  

本文介绍了如何作为 Windows 10 应用安装、运行和增强 PWA \ (EdgeHTML\) ，同时仍确保跨浏览器和跨平台兼容性。  

> [!IMPORTANT]
> 本文中的示例和步骤需要 Visual Studio 2017。 Visual Studio 2019 中不包含本文中使用的模板。 若要下载 Visual Studio 2017，请参阅 Visual Studio [Downloads - 2017， 2015 &旧版本][PreviousVSDownloads]  


## 必备条件  

*   现有的 PWA \ (或托管 Web 应用\) ，可以是实时或本地主机网站。  本指南使用渐进式 Web 应用入门[中的示例 PWA。][PwaGetStarted]  
*   下载 \ (free\) Visual Studio Community [2017][MicrosoftVisualStudio|::ref1::|]。  您还可以使用专业版、企业版或 [预览][MicrosoftVisualStudioPreview] 版。  从Visual Studio安装程序中，选择以下工作负载：  
    *   **通用 Windows 平台开发**  
        
## 设置并运行通用 Windows 应用  

作为 Windows 10 应用安装的 PWA \ (EdgeHTML\) 在独立的 \ (`WWAHost.exe` process\) 窗口中独立于浏览器运行。  启用此功能只需一个轻型应用包装器，其中包含托管的 Web 应用，您可以使用项目模板快速Visual Studio `Progressive Web App (Universal Windows)` 设置。  \ (所有应用逻辑（包括发送本机 Windows 运行时 API 请求）仍发生在原始 Web 应用代码中。\)   

在 windows 应用中设置 Windows 应用Visual Studio。  

1.  在 Windows 设置中，打开 [开发人员模式][WindowsUWPGetStartedEnable]。  \ (在 Windows `developer mode` 搜索栏中键入以查找它。\)   
1.  启动Visual Studio并选择 **"新建项目..."。**  
1.  Choose **Javascript**  >  **Windows Universal** and select Progressive Web App (Universal Windows **) ** from the list of project types in Visual Studio 2017.  
1.  选择默认的 Windows 10 `Target version` \ (最新版\) 和 `Minimum version` \ (版本 10586 或更高版本\) 选择"确定"。 ****  
    
    ![Visual Studio UWP 项目目标版本选择对话框](media/vs-target-min-version.png)  
    
    当 package.appxmanifest 设计器打开时，将加载新项目。  这是配置应用详细信息的地方，包括程序包标识、程序包依赖项、所需功能、视觉元素和扩展点。  这是在应用开发期间使用的应用包清单的易于配置的临时版本。  
    生成应用项目时，Visual Studio元数据[][UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest]生成一AppxManifest.xml文件，该文件用于安装和运行应用。  每当更新 `package.appxmanifest` 文件时，请务必重新生成项目，以便在运行时反映 `AppxManifest.xml` 这两者。  
    
1.  在清单设计器 **应用程序面板** 中，输入 PWA 的 URL 作为 `Start page` 。
    
    > [!NOTE]
    > 所有 https \ (、remote\) url 都受支持 `StartPage` 。  默认情况下，指定本地起始页的 Web 应用不支持服务工作者。  若要为这些情况启用服务工作者支持，请向清单中添加一个显式 [ApplicationContentUriRules](#set-application-content-uri-rules-acurs) 条目，例如： `<uap:Rule Match="http://web-platform.test/" Type="include" uap5:ServiceWorker="true"/>`  
    
    ![package.appxmanifest 设计器的应用程序面板](media/vs-manifest-application.png)  
    
    您还可以根据需要修改 。 `Display name` `Description`  
1.  将此文件 \ (或选择\) 另一个 512x512 映像保存到桌面。  
    然后，在清单设计器**可视化资源**面板中，单击字段 `Source` **...** 按钮，选择它作为源文件，然后单击"生成 **"。**  \ (然后单击" **确定** "覆盖默认占位符图像\) 。  
    
    ![package.appxmanifest 设计器的可视化资源面板](media/vs-manifest-visual-assets.png)  
    
    这将生成在应用商店中安装、运行、启动和分发应用的基本视觉资源。  
    如果看到任何红色 \ (\) 错误，指示缺少图像，则你可以单击 ... 按钮，从生成的图像中手动 `X` 选择文件。 ****  
1.  在清单设计器**内容 URI**面板中，将 `http://example.com` PWA \ (的位置替换为 `Rule`  =  `include` `WinRT Access`  =  `All` \) 。  
    这将授予 PWA 在作为 Windows 10 应用运行时发送本机 Windows 运行时 \ (WinRT\) API 请求的权限，稍后将对此进行介绍。   如果你的实际 PWA 不需要 WinRT 访问，你可以将值切换到 `WinRT Access` `None` 。  无论使用哪种方式，请确保使用 PWA 的 URI 细分默认字符串，否则应用无法 `http://example.com` 在运行时正确加载。  
    你已准备好作为 Windows 10 应用运行和调试 PWA。  如果使用 localhost 网站逐步执行本指南，请确保它正在运行。  然后，  
1.  生成 \ (`Ctrl` + `Shift` + `F5` \) 并运行 \ (`F5` \) PWA 项目。  现在，你的网站应在独立应用窗口中启动。  它不仅是一个托管的 Web 应用;它作为安装在 Windows 10 上的渐进 Web 应用运行！  
    
    ![在活动窗口中WWAHost.exe PWA](media/wwahost.png)  
    
## 将 PWA \ (EdgeHTML\) 作为 Windows 应用调试  

由于 PWA \ (EdgeHTML\) 只是一个逐步增强的托管 Web 应用，因此您可以使用常用的 IDE 和工作流调试与任何 Web 应用相同的服务器端代码。  下一次启动时，实时部署的更改将反映在已安装的 PWA 中 (无需重新部署通用 Windows 应用包\) 。

对于 Windows 10 应用中的客户端调试，你必须拥有 `Microsoft Edge DevTools Preview` 该应用。  此独立应用包括原始浏览器内 Microsoft [Edge DevTools][DevToolsGuide] \ (的所有功能（包括[PWA 工具][DevToolsGuideServiceWorkers]\) ）以及基本的远程[][DevToolsProtocol01ClientsEdgePreview]调试支持和用于附加到任何正在运行的[][DevToolsGuideMicrosoftStoreApp]EdgeHTML 引擎实例的调试目标选择器，包括适用于 Office、Cortana、应用 Webview 的外接程序，当然还包括在 Windows 上运行的 PWA。  

下面是如何为 PWA \ (EdgeHTML\) 。  

1.  如果还没有 Microsoft Store，请从 Microsoft Store 安装 Microsoft [Edge DevTools][MicrosoftStoreEdgeDevtoolsPreview] Preview 应用。  
1.  PWA 网站启动并运行后，启动 DevTools 应用。  
1.  从Visual Studio，使用 () 命令启动 Windows 10 `Start Without Debugging` `Ctrl` + `F5` 应用。  \ (如果开发人员调试器处于活动状态，则 DevTools Visual Studio未正确附加。\)   
1.  在 DevTools 应用中，单击**** 本地调试目标选择器中的"刷新"按钮。  此时应列出您的 PWA \ (EdgeHTML\) 网站。  \ (如果它还在浏览器窗口中运行，则它是列表中的该网站的最后一个实例。\)   
1.  单击 PWA \ (EdgeHTML\) 列表以打开新的 DevTools 实例选项卡并开始调试。  
    
    ![Microsoft Edge DevTools 应用中的本地调试目标选择器](media/devtools-local.png)  
    
1.  你能够验证 DevTools 是否附加到 PWA-running-as-Windows-app。  在 DevTools **控制台中**，键入：  
    
    ```shell
    window.Windows
    ```  
    
    这将返回包含所有顶级 `Windows Runtime` [WinRT](#find-windows-runtime-winrt-apis)命名空间的全局对象。  这是到通用 [Windows][WindowsUWPIndex]平台的 PWA \ (EdgeHTML\) 入口点，并且仅在进程运行过程中向作为 Windows 10 应用运行的 Web 应用公开 (在浏览器外部运行 `WWAHost.exe`) 。  
    
## 查找 Windows 运行时 (WinRT) API  

作为已安装的 Windows 应用 [，PWA \ (EdgeHTML\) 具有][WindowsRuntime]本机 Windows 运行时 API 的完全访问权限;确定你需要使用哪些内容，获取必要的权限，并使用功能检测在受支持的环境中发送该 API 请求。  演练此过程，为 PWA 的 Windows 桌面用户添加渐进式增强功能。  

有很多方法可以标识 Windows PWA 所需的通用 Windows 平台 API，包括搜索全面的 [Windows 开发人员中心上的 UWP 文档][uwp/api/]、使用 Visual Studio 下载和运行 [UWP](#uwp-code-samples) 代码示例，以及浏览适用于 Windows 上的 PWA 的常见任务的代码段。

有很多方法可以标识 Windows PWA 所需的通用 Windows 平台 API，包括搜索全面的 [Windows 开发人员中心上的 UWP 文档][uwp/api/]、使用 Visual Studio 下载和运行 [UWP](#uwp-code-samples) 代码示例，以及浏览 [Windows 10 (EdgeHTML) ][PwaIndexWindows10]上的 PWA 常见任务的代码段。  

总之，WinRT API 在 JavaScript 中的运行方式与在 C# 中相同，因此你可以按照通用 [Windows][WindowsUWPIndex] 平台文档和 [API][UwpApiIndex] 参考来使用。  但是，请注意以下差异：  

*   JavaScript 中的 WinRT 功能  [使用不同的大小写约定][ScriptingJsinrtUsingWinRTCasingConventions]  
*   [事件表示为传递给类方法的][ScriptingJsinrtHandlingWinRTEvents]字符串 `addEventListener` / `removeEventListener` 标识符  
*   [异步方法][ScriptingJsinrtUsingWinRT] 使用 JavaScript Promise 模型  
*   JavaScript 应用不支持命名空间中的 API，而 JavaScript 应用改为使用 `Windows.UI.Xaml` [EdgeHTML][DevGuideWhatsNew] 引擎 Web 呈现堆栈 \ (HTML、CSS\)   
    
有关详细信息，请参阅在 [JavaScript 中使用 Windows 运行时][WindowRuntimeUsingJavascript]。  

### UWP 代码示例  

查看通用 [Windows 平台 \ (UWP\) 代码][MicrosoftDeveloperWindowsSamples] 示例存储库，以浏览常见 Windows 10 应用场景的 JavaScript 示例。  尽管这些示例的 JS 版本使用 [WinJS][GithubWinjsWinjs] 库构建示例模板，但发送这些示例中演示的 WinRT API 请求不需要 WinJS。  

> [!NOTE]
> 如果你需要侦听应用的事件，可以使用以下本机 [`activated`][UwpApiWindowsUiWebuiWebapplicationActivated] WinRT API 完成此操作：  
> 
> **使用此**  
> 
> ```javascript
> Windows.UI.WebUI.WebUIApplication.addEventListener("activated", function (activatedEventArgs) {
>     // Check activatedEventArgs.kind and respond as needed
> });
> ```  
> 
> ...与示例中使用的此类 WinJS 请求相反：  
> 
> **不是**  
> 
> ```javascript
>     var page = WinJS.UI.Pages.define("/html/scenario1-launched.html", {
>         ready: function (element, options) {
>             // Check options.activationKind and respond as needed
>         }
>     });
> ```  

## 从 PWA 发送来自 EdgeHTML (WinRT API)   

此时，假设你想要为 PWA \ (EdgeHTML\) 的 Windows 用户添加自定义上下文菜单，并且已标识 [Windows.UI.Popups][UwpApiWindowsUiPopups] 命名空间中所需的 API。  

为了从 PWA \ (EdgeHTML\) 发送任何 WinRT API 请求，首先需要在 Windows 应用包清单 [\ (](#set-application-content-uri-rules-acurs) \) 文件中建立必需的权限 \ (或应用程序内容 URI 规则 `.appxmanifest` \) 。  

如果其中任何 API 请求涉及访问用户资源（如图片或音乐）或设备功能（如相机或麦克风）的权限，则还需要将应用[](#app-capability-declarations)功能声明添加到应用包清单，以便 Windows 提示用户获取权限。  如果稍后将 PWA \ (EdgeHTML\) 发布到 Microsoft Store，这些必需的 [应用][MicrosoftSupportWindowsAppPermissions] 权限也会在应用商店一览中说明。  

#### 设置应用程序内容 URI 规则 (ACU)   

通过 ACU（也称为 URL 允许列表）您可以授予 PWA \ (EdgeHTML\) 直接访问 Windows 运行时 API 的 URL。  在 Windows 操作系统级别，将正确的策略边界设置为允许 Web 服务器上托管的代码直接发送平台 API 请求。  将 PWA URL 指定为时，在应用程序包清单文件中定义这些边界 `ApplicationContentUriRules` 。  

规则应包含应用的起始页和您希望作为应用页面包含的其他任何页面。  如果用户导航到规则中未包含的 URL，Windows 将在 Microsoft Edge 浏览器中打开目标 URL，而不是在独立 PWA \ (EdgeHTML\) 窗口 \ (process\) 中打开目标 URL。 `WWAHost.exe`  还可以排除特定 URL。  

有几种方法在规则中 `Match` 指定 URL：  

*   确切的主机名  
*   已包括或排除含有某个主机名的任何子域的 URI 对应的主机名  
*   确切的 URI  
*   包含查询属性的确切 URI  
*   部分路径和用于指示包含规则的特定文件扩展名的通配符。  
*   排除规则的相对路径  
    
下面是一个文件中 ACU 的一些 `.appxmanifest` 示例：  

```xml
<Application
Id="App"
StartPage="https://contoso.com/home">
<uap:ApplicationContentUriRules>
    <uap:Rule Type="include" Match="https://contoso.com/" WindowsRuntimeAccess="all" />
    <uap:Rule Type="include" Match="https://*.contoso.com/" WindowsRuntimeAccess="all" />
    <uap:Rule Type="exclude" Match="https://contoso.com/excludethispage.aspx" />
</uap:ApplicationContentUriRules>
```  

在应用的 ADR 中定义的 URL 可以通过属性（接受以下值）被授予对 Windows 运行时 `WindowsRuntimeAccess` 的权限：  

*   `all`：远程 JavaScript 代码可以访问所有 WinRT API 和任何本地封装组件。  [Windows \ (WinRT\) ) ][UwpApiIndex]命名空间已注入并呈现在脚本引擎中。  
*   `allowForWeb`：远程 JavaScript 代码访问仅限于本地打包组件，包括自定义 C++/C# 组件。  
*   `none`：默认值。  指定的 URL 不具有任何平台访问权限。  
    
在本教程中，你已为单页应用设置 \ (步骤 6 所需的唯一[](#set-up-and-run-your-universal-windows-app)ACUR，并运行应用部分\) 。  你可以从网站设计器的内容 **URI** 面板确认 `package.appxmanifest` Visual Studio。  

![appxmanifest Visual Studio的内容 URI 面板](media/vs-appxmanifest-editor-acurs.png)  

您还可以通过在解决方案资源管理器中右键单击文件并选择"查看代码 \ (\) "来查看清单的原始 `package.appxmanifest` Visual Studio **** `F7` XML。  若要切换回设计器视图，请选择 **"视图**设计器"\ (`Shift` + `F7` \) 。  

#### 应用功能声明  

如果你的应用需要以编程方式访问用户资源（如图片或音乐）或设备（如相机或麦克风），则必须在应用包清单文件中[][WindowsUwpPackagingAppCapabilities]包含相应的应用功能声明。  三种应用功能声明类别如下所示：  

*   适用于大多数常见应用场景的[通用功能][WindowsUwpPackagingAppCapabilitiesGeneralUse]。  
*   允许你的应用访问外围设备和内部设备的[设备功能][WindowsUwpPackagingAppCapabilitiesDevice]。  
*   [支持企业方案][WindowsUwpPackagingAppCapabilitiesSpecialRestricted] 并需要 Microsoft Store 公司帐户的特殊用途功能。  有关公司帐户的详细信息，请参阅[帐户类型、位置和费用][WindowsUwpPublishAccountTypesLocationsFees]。
    
Microsoft Store 应用页面列出了你在应用包清单中声明的所有功能，因此请务必仅指定你的应用实际使用的功能。

某些功能为应用提供对敏感资源的访问权限。  这些资源被视为敏感资源，因为每个资源都能访问用户的个人数据或花费用户金钱。  隐私设置由 Windows 10[][BingResultsWindows10Settings]设置应用管理，允许用户动态控制对敏感资源的访问权限。  因此，你的应用不要假定敏感资源始终可用，这一点很重要。  有关访问敏感资源的详细信息，请参阅[隐私感知应用指南][WindowsUwpSecurityIndex]。  

你通过声明应用的程序包清单中的功能来请求访问。  在Visual Studio中，你可以从 package.appxmanifest**** 设计器的功能面板中完成此操作。  

![appxmanifest Visual Studio的功能面板](media/vs-appxmanifest-editor-capabilities.png)  

在本教程中，只需要默认的 Internet \ (Client\) 功能，因此无需执行进一步的操作。  

### 使用功能检测调用 WinRT  

为确保 PWA 受众在所有平台上获得质量基线体验，可以使用 WinRT 功能检测逐步增强 Windows 上的 PWA 体验。  这样，你将能够确保特定于 Windows 的代码仅在 WinRT API 可用且适用的上下文中运行。  

功能检测可能与查找对象 `Windows` \ ([WinRT][UwpApiIndex]命名空间的入口点 \) 一样简单，如下所示：  

```javascript
if(window.Windows){
    /*Run code that sends Windows API requests */
}
```  

但是，鉴于并非所有 Windows API 都可用于所有 [Windows 10][UwpExtensionSdkDeviceFamiliesOverview]设备类型，使用更具体的功能检测进一步限定要发送的 API 请求的命名空间通常很有用：  

```javascript
if(window.Windows && Windows.Media.SpeechRecognition){
    /*Run code that sends Windows API requests */
}
```  

借助该背景，你已准备好添加一些 WinRT 代码来实现自定义上下文菜单。  如果你使用的是"渐进 Web 应用入门"中 [的示例][PwaGetStarted]PWA：

1.  打开Visual Studio PWA 网站项目。  
1.  在解决方案资源管理器中，打开该文件，并添加以下行，它正下方为服务 `views\layout.pug` `script` 工作者的引用：
    
    ```xml
    script(src='/javascripts/site.js')
    ```  
    
1.  在解决方案资源管理器中，右键单击 `javascripts` 该文件夹并****  >  **添加新文件...**
1.  将文件命名： `site.js` ，然后复制以下代码：
    
    ```javascript
    if (window.Windows && Windows.UI.Popups) {
        document.addEventListener('contextmenu', function (e) {

            // Build the context menu
            var menu = new Windows.UI.Popups.PopupMenu();
            menu.commands.append(new Windows.UI.Popups.UICommand("Option 1", null, 1));
            menu.commands.append(new Windows.UI.Popups.UICommandSeparator);
            menu.commands.append(new Windows.UI.Popups.UICommand("Option 2", null, 2));

            // Convert from webpage to WinRT coordinates
            function pageToWinRT(pageX, pageY) {
                var zoomFactor = document.documentElement.msContentZoomFactor;
                return {
                    x: (pageX - window.pageXOffset) * zoomFactor,
                    y: (pageY - window.pageYOffset) * zoomFactor
                };
            }

            // When the menu is invoked, execute the requested command
            menu.showAsync(pageToWinRT(e.pageX, e.pageY)).done(function (invokedCommand) {
                if (invokedCommand !== null) {
                    switch (invokedCommand.id) {
                        case 1:
                            console.log('Option 1 selected');
                            // Invoke code for option 1
                            break;
                        case 2:
                            console.log('Option 2 selected');
                            // Invoke code for option 2
                            break;
                        default:
                            break;
                    }
                } else {
                    // The command is null if no command was invoked.
                    console.log("Context menu dismissed");
                }
            });
        }, false);
    }
    ```
    
1.  比较在浏览器 \ (中从 PWA 网站项目\) 运行 PWA 时与从通用 Windows 应用项目\ (在 Windows 应用窗口 \) 中运行 `F5` PWA 时上下文菜单行为。 `F5`  在浏览器中，右键单击会为你提供 Microsoft Edge 默认上下文菜单，而此时将显示 `WWAHost.exe` 自定义菜单。  
    
    | Microsoft Edge | Windows 10 应用 |  
    |:--- |:---- |  
    | ![浏览器默认上下文菜单](media/browser-context-menu.png) | ![应用自定义上下文菜单](media/app-context-menu.png) |  
    
希望你现在有一个基础，可以逐步增强 Windows 上的 PBA。  如果遇到问题或内容不明确，请发送评论！  

## 深入探索

[Windows 开发人员中心][MicrosoftDeveloperWindowsApps]是 Windows 应用生成的所有阶段的完整参考，从入门到[][MicrosoftDeveloperWindowsAppsGetStarted]设计、开发和发布到[][MicrosoftDeveloperWindowsAppsDesign]Microsoft [][MicrosoftDeveloperWindowsAppsDevelop]Store。 [][MicrosoftDeveloperStorePublishApps]  

有关通用 Windows 平台 \ (UWP\) 以及如何面向不同 Windows 10 设备系列的通用概述，请参阅通用 Windows 平台 [简介][WindowsUWPGetStartedGuide]。  

当你准备好时，下面是 \ (和原因！\) 将 PWA 提交[到 Microsoft Store。](./microsoft-store.md)  

<!-- links -->  

[PwaGetStarted]: ./get-started.md "渐进式 Web 应用入门 |Microsoft Docs"  
[PwaIndexWindows10]: ./index.md#pwas-on-windows-10-edgehtml "Windows 10 上的 PWA (EdgeHTML) - Windows 上的渐进式 Web 应用 |Microsoft Docs"  
[DevToolsGuide]: ../devtools-guide/index.md "Microsoft Edge (EdgeHTML) 开发人员工具 |Microsoft Docs"  
[DevToolsGuideMicrosoftStoreApp]: ../devtools-guide/index.md#microsoft-store-app "Microsoft Store 应用 - Microsoft Edge (EdgeHTML) 开发人员工具 |Microsoft Docs"  
[DevToolsGuideServiceWorkers]: ../devtools-guide/service-workers.md "服务工作人员 |Microsoft Docs"  
[DevToolsProtocol01ClientsEdgePreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview - DevTools 协议客户端 |Microsoft Docs"  
[DevGuideWhatsNew]: ../dev-guide/whats-new.md "EdgeHTML 中的新增功能 |Microsoft Docs"  
[WindowsRuntime]: ../windows-runtime/index.md "适用于 JavaScript (WinRT) Windows 运行时 |Microsoft Docs"  
[WindowRuntimeUsingJavascript]: ../windows-runtime/using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时 |Microsoft Docs"  

[ScriptingJsinrtHandlingWinRTEvents]: /scripting/jswinrt/handling-windows-runtime-events-in-javascript "在 JavaScript 中处理 Windows 运行时事件 |Microsoft Docs"  
[ScriptingJsinrtUsingWinRT]: /scripting/jswinrt/using-windows-runtime-asynchronous-methods "使用 Windows 运行时异步方法 |Microsoft Docs"  
[ScriptingJsinrtUsingWinRTCasingConventions]:  /scripting/jswinrt/using-the-windows-runtime-in-javascript#casing-conventions-with-windows-runtime-features "Windows 运行时功能的大小写约定 - 在 JavaScript 中使用 Windows 运行时 |Microsoft Docs"  
[UwpApiIndex]: /uwp/api/index "Windows UWP 命名空间 |Microsoft Docs"  
[UwpApiWindowsUiPopups]: /uwp/api/windows.ui.popups "Windows.UI.Popups 命名空间 |Microsoft Docs"  
[UwpApiWindowsUiWebuiWebapplicationActivated]: /uwp/api/windows.ui.webui.webuiapplication.activated "WebUIApplication.Activated 事件 |Microsoft Docs"  
[UwpExtensionSdkDeviceFamiliesOverview]: /uwp/extension-sdks/device-families-overview "设备系列概述 |Microsoft Docs"  
[UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest]: /uwp/schemas/appxpackage/uapmanifestschema/generate-package-manifest "如何Visual Studio应用包清单 |Microsoft Docs"  
[WindowsUWPIndex]: /windows/uwp/index "通用 Windows 平台文档 |Microsoft Docs"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide "什么是通用 Windows 平台 (UWP) 应用？ |Microsoft Docs"  
[WindowsUWPGetStartedEnable]: /windows/uwp/get-started/enable-your-device-for-development "启用设备进行开发 |Microsoft Docs"  
[WindowsUwpSecurityIndex]: /windows/uwp/security/index "安全 |Microsoft Docs"  
[WindowsUwpPublishAccountTypesLocationsFees]: /windows/uwp/publish/account-types-locations-and-fees "帐户类型、位置和费用 |Microsoft Docs"  
[WindowsUwpPackagingAppCapabilitiesSpecialRestricted]: /windows/uwp/packaging/app-capability-declarations#special-and-restricted-capabilities "受限功能 |Microsoft Docs"  
[WindowsUwpPackagingAppCapabilitiesDevice]: /windows/uwp/packaging/app-capability-declarations#device-capabilities "设备功能 |Microsoft Docs"  
[WindowsUwpPackagingAppCapabilitiesGeneralUse]: /windows/uwp/packaging/app-capability-declarations#general-use-capabilities "通用功能 |Microsoft Docs"  
[WindowsUwpPackagingAppCapabilities]: /windows/uwp/packaging/app-capability-declarations "应用功能声明 |Microsoft Docs"  

[BingResultsWindows10Settings]: https://binged.it/2lOGSH0 "windows 10 设置 - 必应"  
[GithubWinjsWinjs]: https://github.com/winjs/winjs "winjs/winjs |GitHub"  
[MicrosoftDeveloperStorePublishApps]: https://developer.microsoft.com/store/publish-apps/index "发布 Windows 应用和游戏"  
[MicrosoftDeveloperWindowsApps]: https://developer.microsoft.com/windows/apps/index "通用 Windows 平台文档"  
[MicrosoftDeveloperWindowsAppsDesign]: https://developer.microsoft.com/windows/apps/design/index "设计和编码 Windows 应用"  
[MicrosoftDeveloperWindowsAppsDevelop]: https://developer.microsoft.com/windows/apps/develop/index "开发 UWP 应用"  
[MicrosoftDeveloperWindowsAppsGetStarted]: https://developer.microsoft.com/windows/apps/getstarted/index "Windows 10 应用入门"  
[MicrosoftDeveloperWindowsSamples]: https://developer.microsoft.com/windows/samples "代码示例"  
[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools Preview"  
[MicrosoftSupportWindowsAppPermissions]: https://support.microsoft.com/help/10557/windows-10-app-permissions "应用权限"  
[MicrosoftVisualStudioDownloads]: https://visualstudio.microsoft.com/downloads "下载"  
[MicrosoftVisualStudioPreview]: https://visualstudio.microsoft.com/vs/preview "Visual Studio预览"  
[PreviousVSDownloads]: https://visualstudio.microsoft.com/vs/older-downloads/ "Visual Studio下载"  
