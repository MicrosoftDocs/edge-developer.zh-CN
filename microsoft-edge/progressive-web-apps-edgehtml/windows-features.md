---
description: 通过本机应用功能逐步增强 PWA for Windows
title: 定制你的 PWA （EdgeHTML） for Windows
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 web 应用、PWA、Edge、Windows、WinRT、UWP、EdgeHTML
ms.openlocfilehash: 296ae0a65481edd312e06b83c1554813ec2bffae
ms.sourcegitcommit: 515522959f517e194f93a27f5d360690600edd9d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "10894715"
---
# 定制你的 PWA （EdgeHTML） for Windows  

Windows 10 上安装的 PWAs 可享受以[通用 Windows 平台 \ （UWP \）][WindowsUWPGetStartedGuide]应用的形式运行的[所有好处][PwaIndexWindows10]，包括通过 windows 应用沙盒沙盒安全和对 Windows 运行时的完全访问权限[\ （WinRT \））][UwpApiIndex] api，包括以下内容的保护：  

*   控制设备功能 \ （如相机、麦克风、GPS \）  
*   访问用户资源 \ （如 "日历"、"联系人"、"文档"、"音乐"）  
*   通过 Cortana 语音命令启动/浏览应用  
*   与 Windows 操作系统集成 \ （通过 Windows 操作中心、桌面任务栏和上下文菜单 \）  

这些只是 Windows 上的 PWA （EdgeHTML \）的几个新增可能性。  

本文介绍如何以 Windows 10 应用的形式安装、运行和增强 PWA \ （EdgeHTML \），同时还可确保跨浏览器和跨平台兼容性。  

> [!IMPORTANT]
> 本文中的示例和步骤需要 Visual Studio 2017。 Visual Studio 2019 不包含本文中使用的模板。 若要下载 Visual Studio 2017，请参阅[Visual Studio 下载-2017、2015 & 以前版本][PreviousVSDownloads]  


## 必备条件  

*   现有 PWA \ （或托管 web 应用 \），它可以是实时网站或 localhost 网站。  本指南使用[渐进式 Web 应用][PwaGetStarted]中的示例 PWA。  
*   下载 \ （免费 \） [Visual Studio 社区 2017][MicrosoftVisualStudio|::ref1::|]。  你还可以使用专业版、企业版或[预览版][MicrosoftVisualStudioPreview]版本。  从 Visual Studio 安装程序中，选择以下工作负荷：  
    *   **通用 Windows 平台开发**  

## 设置和运行通用 Windows 应用  

作为 Windows 10 应用安装的 PWA \ （EdgeHTML \）独立于浏览器运行，位于单独的 \ （ `WWAHost.exe` 进程 \）窗口中。  启用此操作只需要一个包含托管 web 应用的轻型应用包装程序，你可以使用 Visual Studio 项目模板快速设置该包装 `Progressive Web App (Universal Windows)` 。  \ （所有应用逻辑，包括发送本机 Windows 运行时 API 请求，仍在原始 web 应用代码中发生。）  

在 Visual Studio 中设置 Windows 应用开发环境。  

1.  在 Windows 设置中，启用 "[开发人员模式][WindowsUWPGetStartedEnable]"。  \ （ `developer mode` 在 Windows searchbar 中键入以找到它。）  
1.  启动 Visual Studio 并**创建新项目 ...**  
1.  选择 "c # **Windows 应用程序打包" 项目**模板。  如果你使用的是早期版本的 Visual Studio，请在 "**托管 Web 应用（通用 windows）** " 或 "**渐进 Web 应用（通用 windows）**" 下查找等效模板。  
1.  选择默认的 Windows 10 `Target version` \ （最新版本 \）和 `Minimum version` \ （内部版本10586或更高版本 \），然后单击 **"确定"**。  

    ![UWP 项目目标版本的 Visual Studio 选择对话框](media/vs-target-min-version.png)  

    新项目将在 package.appxmanifest 设计器打开的情况中加载。  你可以在此处配置应用的详细信息，包括程序包标识、程序包依赖项、所需功能、可视化元素和扩展性点。  这是在应用开发期间使用的应用包清单的一个易于配置的临时版本。  
    当你生成应用项目时， [Visual Studio][UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest]将通过此元数据生成 AppxManifest.xml文件，用于安装和运行你的应用。  每当更新文件时 `package.appxmanifest` ，请确保重新生成项目，这样两个项目都将在 `AppxManifest.xml` 运行时反映出来。  

1.  在清单设计器 "**应用程序**" 面板中，输入 PWA 的 URL 作为 `Start page` 。

    > [!NOTE]
    > 对于指定为的所有 https \ （secure、remote \） url，服务工作者均受支持 `StartPage` 。  默认情况下，对于指定本地起始页的 web 应用，不支持服务工作人员。  若要启用服务工作人员对这些情况的支持，请将显式[ApplicationContentUriRules](#set-application-content-uri-rules-acurs)条目添加到清单中，例如： `<uap:Rule Match="http://web-platform.test/" Type="include" uap5:ServiceWorker="true"/>`  
    
    ![Package.appxmanifest 设计器的应用程序面板](media/vs-manifest-application.png)  
    
    您也可以根据需要修改 `Display name` 和 `Description` 。  
1.  将此文件 \ （或您选择的另一个512x512 图像）保存到您的桌面。  
    然后，在 "清单设计器**视觉资源**" 面板中，单击 " `Source` 字段 **...** " 按钮，将其选择为源文件，然后单击 "**生成**"。  \ （然后单击 **"确定"** 以覆盖默认占位符图像 \）。  
    
    ![程序包 package.appxmanifest 设计器的 "视觉资源" 面板](media/vs-manifest-visual-assets.png)  
    
    这将生成在应用商店中安装、运行、启动和分发应用的基本视觉资源。  
    如果看到 `X` 表示缺少图像的任何红色 \ （\）错误，您可以单击 "..." 按钮 **...** ，手动从生成的映像中选择文件。  
1.  在清单设计器的 "**内容 uri** " 面板中， `http://example.com` 将替换为 PWA 的位置 \ （如 `Rule`  =  `include` `WinRT Access`  =  `All` \）。  
    这将授予 PWA 在作为 Windows 10 应用运行时发送本机 Windows 运行时 \ （WinRT） API 请求的权限，稍后将对此进行介绍。   如果你的实际 PWA 不需要 WinRT 访问，你可以将 `WinRT Access` 该值转换为 `None` 。  无论是哪种情况，都要确保将默认 `http://example.com` 字符串与 PWA 的 URI 进行了细分，或者你的应用无法在运行时正确加载。  
    你已准备好将 PWA 作为 Windows 10 应用进行运行和调试。  如果您使用 localhost 网站逐步完成本指南，请确保它正在运行。  并  
1.  生成 \ （ `Ctrl` + `Shift` + `F5` \）并运行 `F5` PWA 项目。  您的网站现在应该在独立应用窗口中启动。  它不仅是托管 web 应用;它作为在 Windows 10 上安装的渐进式 Web 应用运行！  

    ![在 WWAHost.exe 窗口中运行的 PWA](media/wwahost.png)  

## 以 Windows 应用的形式调试 PWA \ （EdgeHTML \）  

由于 PWA \ （EdgeHTML \）只是一个渐进增强的托管 web 应用，因此你可以使用常规的 IDE 和工作流来调试你的服务器端代码与任意 web 应用一样。  你的实时部署更改将在你下次启动时反映在已安装的 PWA 中（无需重新部署你的通用 Windows 应用包 \）。

对于你的 Windows 10 应用中的客户端调试，你必须具有该 `Microsoft Edge DevTools Preview` 应用。  此独立应用包括原始的浏览器[Microsoft Edge DevTools][DevToolsGuide] \ （包括[PWA 工具][DevToolsGuideServiceWorkers]\），以及基本的[远程调试][DevToolsProtocol01ClientsEdgePreview]支持和[调试目标选择器][DevToolsGuideMicrosoftStoreApp]，用于附加到 EdgeHTML 引擎的任何运行的实例，包括 Office、Cortana、应用 Webviews 的加载项、当然 PWAs 在 Windows 上运行的加载项。  

下面介绍如何为 PWA 设置调试 \ （EdgeHTML \）。  

1.  从 Microsoft Store 中安装[Microsoft Edge DevTools Preview][MicrosoftStoreEdgeDevtoolsPreview]应用（如果尚未安装）。  
1.  在 PWA 网站启动并运行后，启动 DevTools 应用。  
1.  在 Visual Studio 中，通过 `Start Without Debugging` （ `Ctrl` + `F5` ）命令启动 Windows 10 应用。  \ （如果 Visual Studio 调试器处于活动状态，DevTools 应用不会正确附加。）  
1.  在 DevTools 应用中，单击本地调试目标选择器中的 "**刷新**" 按钮。  您的 PWA \ （EdgeHTML \）网站现在应该已列出。  \ （如果它也在浏览器窗口中运行，则是该网站在列表中的最后一个实例。）  
1.  单击 PWA \ （EdgeHTML \）网站清单以打开新的 DevTools "实例" 选项卡，然后开始调试。  
    
    ![Microsoft Edge DevTools 应用中的本地调试目标选择器](media/devtools-local.png)  
    
1.  你可以验证 DevTools 是否已连接到你的 PWA 运行的 Windows 应用。  在 DevTools**控制台**中，键入：  
    
    ```shell
    window.Windows
    ```  
    
    这将返回 `Windows Runtime` 包含所有[顶级 WinRT 命名空间](#find-windows-runtime-winrt-apis)的全局对象。  这是[通用 Windows 平台][WindowsUWPIndex]的 PWA \ （EdgeHTML \）入口点，并仅向作为 Windows 10 应用（在浏览器外运行）运行的 web 应用公开 `WWAHost.exe` 。  
    
## 查找 Windows 运行时 \ （WinRT） Api  

作为已安装的 Windows 应用， [PWA \ （EdgeHTML \）对本机 Windows 运行时 api 具有完全访问权限][WindowsRuntime];确定需要使用的内容，获取必要的权限，并使用功能检测在受支持的环境中发送该 API 请求。  浏览此过程，为 PWA 的 Windows 桌面用户添加渐进式增强。  

可通过多种方法来标识 Windows PWA 所需的通用 Windows 平台 Api，包括在 windows 开发人员中心上搜索全面 [UWP 文档] [UWP/api/]、下载并运行适用于 Windows 的[uwp 代码示例](#uwp-code-samples)以及浏览 PWAs 的常见任务。

有多种方法可用于标识你为 Windows PWA 所需的通用 Windows 平台 Api，包括在 windows 开发人员中心上搜索全面 [UWP 文档] [uwp/api/]、下载并运行适用于 Visual Studio 的[uwp 代码示例](#uwp-code-samples)以及[在 Windows 10 （EdgeHTML）上浏览 PWAs][PwaIndexWindows10]的常见任务的代码片段。  

总之，WinRT Api 在 JavaScript 中的工作方式与它们在 c # 中的工作方式相同，因此你可以遵循通用的[通用 Windows 平台文档][WindowsUWPIndex]和[API 参考][UwpApiIndex]以了解用法。  但是，请注意以下差异：  

*   JavaScript 中的 WinRT 功能使用[不同的大小写约定][ScriptingJsinrtUsingWinRTCasingConventions]  
*   [事件表示为][ScriptingJsinrtHandlingWinRTEvents]传递到类 `addEventListener` / `removeEventListener` 方法的字符串标识符  
*   [异步方法][ScriptingJsinrtUsingWinRT]使用 JavaScript 承诺模型  
*   `Windows.UI.Xaml`JavaScript 应用不支持命名空间中的 api，而 JavaScript 应用则使用[EdgeHTML][DevGuideWhatsNew]引擎 web 呈现堆栈 \ （HTML、CSS \）  

有关更多详细信息，请参阅[在 JavaScript 中使用 Windows 运行时][WindowRuntimeUsingJavascript]。  

### UWP 代码示例  

查看[通用 Windows 平台 \ （UWP \）代码示例][MicrosoftDeveloperWindowsSamples]存储库，浏览常见 windows 10 应用方案的 JavaScript 示例。  虽然这些示例的 JS 版本使用[WinJS][GithubWinjsWinjs]库来构造示例模板，但发送这些示例中所示的 WinRT API 请求不需要 WinJS。  

> [!NOTE]
> 如果需要侦听 [`activated`][UwpApiWindowsUiWebuiWebapplicationActivated] 应用的事件，可以使用以下本机 WINRT API 执行此操作：  
> 
> **使用此**  
> 
> ```javascript
> Windows.UI.WebUI.WebUIApplication.addEventListener("activated", function (activatedEventArgs) {
>     // Check activatedEventArgs.kind and respond as needed
> });
> ```  
> 
> ...与示例中使用的此类型的 WinJS 请求相比：  
> 
> **不是这种情况**  
> 
> ```javascript
>     var page = WinJS.UI.Pages.define("/html/scenario1-launched.html", {
>         ready: function (element, options) {
>             // Check options.activationKind and respond as needed
>         }
>     });
> ```  

## 从 PWA 发送 WinRT API 请求（EdgeHTML）  

此时，假设你想要为 PWA \ （EdgeHTML \）的 Windows 用户添加自定义上下文菜单，并且已在[WINDOWS UI 弹出][UwpApiWindowsUiPopups]命名空间中标识了所需的 api。  

为了从我们的 PWA \ （EdgeHTML \）发送任何 WinRT Api 请求，首先需要在 Windows 应用包清单 \ （\）文件中[建立必要的权限](#set-application-content-uri-rules-acurs)\ （或应用程序内容 URI 规则 \） `.appxmanifest` 。  

如果这些 API 请求中的任何一个涉及访问用户资源（如图片或音乐）或设备功能（如相机或麦克风），则还需要将[应用功能声明](#app-capability-declarations)添加到应用包清单中，以便 Windows 提示用户获得权限。  如果你后来将 PWA \ （EdgeHTML \）发布到 Microsoft Store，则你的应用商店中还会注明这些必需的[应用权限][MicrosoftSupportWindowsAppPermissions]。  

#### 设置应用程序内容 URI 规则（Acur）  

通过 Acur （也称为 URL 允许列表），你可以为 Windows 运行时 Api 提供 PWA 的 Url \ （EdgeHTML \）直接访问。  在 Windows 操作系统级别，适当的策略边界设置为允许 web 服务器上托管的代码直接发送平台 API 请求。  将 PWA Url 指定为时，可以在应用包清单文件中定义这些界限 `ApplicationContentUriRules` 。  

你的规则应包括你的应用的起始页以及你希望作为应用页面包含的任何其他页面。  如果你的用户导航到你的规则中未包含的 URL，Windows 将在 Microsoft Edge 浏览器中打开目标 URL，而不是独立的 PWA \ （EdgeHTML \）窗口 \ （ `WWAHost.exe` process \）。  您也可以排除特定的 Url。  

可通过多种方法 `Match` 在规则中指定 URL：  

*   确切的主机名  
*   已包括或排除含有某个主机名的任何子域的 URI 对应的主机名  
*   确切的 URI  
*   包含查询属性的确切 URI  
*   部分路径和用于指示包含规则的特定文件扩展名的通配符。  
*   排除规则的相对路径  

下面是一个文件中的一些 Acur 示例 `.appxmanifest` ：  

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

在你的应用的 Acur 内定义的 Url 可以通过该属性授予对 Windows 运行时的权限 `WindowsRuntimeAccess` ，这将接受以下值：  

*   `all`：远程 JavaScript 代码可以访问所有 WinRT Api 和任何本地打包的组件。  [Windows \ （WinRT））][UwpApiIndex]命名空间被注入并存在于脚本引擎中。  
*   `allowForWeb`：远程 JavaScript 代码访问仅限于本地打包的组件，包括自定义 c + +/C # 组件。  
*   `none`默认.  指定的 URL 不具有任何平台访问权限。  

在本教程中，你已经为单页应用设置了你需要的唯一 ACUR \ （上一次[设置和运行应用](#set-up-and-run-your-universal-windows-app)的第6部分）。  你可以从 Visual Studio 设计器的 "**内容 uri** " 面板中进行确认 `package.appxmanifest` 。  

![Visual Studio package.appxmanifest designer 的内容 URI 面板](media/vs-appxmanifest-editor-acurs.png)  

你还可以通过右键单击 `package.appxmanifest` Visual Studio 解决方案资源管理器中的文件并选择 "**查看代码**\ （\）" 来查看清单的原始 XML `F7` 。  若要切换回设计器视图，请选择 "**视图设计器**\ （ `Shift` + `F7` \）"。  

#### 应用功能声明  

如果你的应用需要以编程方式访问用户资源（如图片或音乐）或设备（如相机或麦克风），则必须在你的应用包清单文件中包含相应的[应用功能声明][WindowsUwpPackagingAppCapabilities]。  三种应用功能声明类别如下所示：  

*   适用于大多数常见应用场景的[通用功能][WindowsUwpPackagingAppCapabilitiesGeneralUse]。  
*   允许你的应用访问外围设备和内部设备的[设备功能][WindowsUwpPackagingAppCapabilitiesDevice]。  
*   支持企业方案并需要 Microsoft Store 公司帐户的[特殊用途功能][WindowsUwpPackagingAppCapabilitiesSpecialRestricted]。  有关公司帐户的详细信息，请参阅[帐户类型、位置和费用][WindowsUwpPublishAccountTypesLocationsFees]。

你的 Microsoft Store 应用页面列出你在应用包清单中声明的所有功能，因此请确保仅指定你的应用实际使用的功能。

某些功能为应用提供对敏感资源的访问权限。  这些资源被认为是敏感资源，因为每个资源都能够访问用户的个人资料或为用户收费。  隐私设置由 Windows 10 "[设置][BingResultsWindows10Settings]" 应用托管，让用户能够动态控制对敏感资源的访问权限。  因此，你的应用不会假设敏感资源始终可用，这一点很重要。  有关访问敏感资源的详细信息，请参阅[隐私感知应用指南][WindowsUwp|::ref2::|Index]。  

你可以通过在你的应用的程序包清单中声明功能来请求访问权限。  在 Visual Studio 中，你可以从 package.appxmanifest designer 的 "**功能**" 面板中执行此操作。  

![Visual Studio package.appxmanifest designer 的 "功能" 面板](media/vs-appxmanifest-editor-capabilities.png)  

在本教程中，仅需要默认的 Internet \ （客户端 \）功能，因此无需执行进一步操作。  

### 使用功能检测来调用 WinRT  

为了确保所有平台上的 PWA 受众的质量基准体验，你可以通过 WinRT 功能检测逐步增强你在 Windows 上的 PWA 体验。  这样，你就能够确保仅在 WinRT Api 可用且适用的上下文中运行特定于 Windows 的代码。  

功能检测可能非常简单，只需按如下方式查找 `Windows` 对象 \ （ [WinRT 命名空间][UwpApiIndex]\ 的入口点 \）：  

```javascript
if(window.Windows){
    /*Run code that sends Windows API requests */
}
```  

但是，如果并非所有 Windows Api 在所有[windows 10 设备类型][UwpExtensionSdkDeviceFamiliesOverview]上都可用，则使用更具体的功能检测来进一步限定你正在发送的 API 请求的命名空间通常非常有用：  

```javascript
if(window.Windows && Windows.Media.SpeechRecognition){
    /*Run code that sends Windows API requests */
}
```  

使用该背景，您可以添加一些 WinRT 代码来实现自定义上下文菜单。  如果你使用的是来自[开始使用渐进的 Web 应用][PwaGetStarted]的示例 PWA：

1.  打开 Visual Studio 到 PWA 网站项目。

1.  在 "解决方案资源管理器" 中，打开 `views\layout.pug` 文件并在 `script` 服务工作人员参考的下方添加以下行：
    
    ```xml
    script(src='/javascripts/site.js')
    ```  

1.  在 "解决方案资源管理器" 中，右键单击 `javascripts` 文件夹，然后单击 "**添加**  >  **新文件 ...**"。

1.  为文件命名： `site.js` ，并复制以下代码：
    
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

1.  比较在浏览器中运行 PWA 时的上下文菜单行为 \ （ `F5` 从 PWA 网站项目 \），而不是从 windows 应用窗口 \ 中（ `F5` 从通用 Windows 应用项目 \）中运行。  在浏览器中，右键单击为你提供 Microsoft Edge 默认上下文菜单，而在该 `WWAHost.exe` 过程中，你的自定义菜单现在将显示。  

    | Microsoft Edge | Windows 10 应用 |  
    |:--- |:---- |  
    | ![浏览器默认上下文菜单](media/browser-context-menu.png) | ![应用自定义上下文菜单](media/app-context-menu.png) |  

希望你现在有坚实的基础，可在 Windows 上逐步增强你的 PWAs。  如果遇到问题或不清楚任何问题，请发送评论！  

## 深入探索

[Windows 开发人员中心][MicrosoftDeveloperWindowsApps]是有关 windows 应用构建的所有[阶段的完整参考，从入门][MicrosoftDeveloperWindowsAppsGetStarted]到[设计][MicrosoftDeveloperWindowsAppsDesign]、[开发][MicrosoftDeveloperWindowsAppsDevelop]和[发布][MicrosoftDeveloperStorePublishApps]到 Microsoft Store。  

有关通用 Windows 平台 \ （UWP \）和如何面向不同的 Windows 10 设备系列的一般概述，请参阅[通用 Windows 平台简介][WindowsUWPGetStartedGuide]。  

准备就绪后，下面是如何将[PWA 提交到 Microsoft Store 的](./microsoft-store.md)"（和为什么！ \）"。  

<!-- image links -->  

<!-- links -->  

[PwaGetStarted]: ./get-started.md "渐进式 Web 应用入门"  
[PwaIndexWindows10]: ./index.md#pwas-on-windows-10-edgehtml "Windows 10 上的 PWAs （EdgeHTML）-在 Windows 上渐进 Web 应用"  
[DevToolsGuide]: ../devtools-guide.md "Microsoft Edge （EdgeHTML）开发人员工具"  
[DevToolsGuideMicrosoftStoreApp]: ../devtools-guide.md#microsoft-store-app "Microsoft Store 应用-Microsoft Edge （EdgeHTML）开发人员工具"  
[DevToolsGuideServiceWorkers]: ../devtools-guide/service-workers.md "服务工作进程"  
[DevToolsProtocol01ClientsEdgePreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview-DevTools 协议客户端"  
[DevGuideWhatsNew]: ../dev-guide/whats-new.md "EdgeHTML 中的新增功能"  
[WindowsRuntime]: ../windows-runtime/index.md "适用于 JavaScript 的 Windows 运行时（WinRT）"  
[WindowRuntimeUsingJavascript]: ../windows-runtime/using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时"  

[ScriptingJsinrtHandlingWinRTEvents]: /scripting/jswinrt/handling-windows-runtime-events-in-javascript "处理 JavaScript 中的 Windows 运行时事件"  
[ScriptingJsinrtUsingWinRT]: /scripting/jswinrt/using-windows-runtime-asynchronous-methods "使用 Windows 运行时异步方法"  
[ScriptingJsinrtUsingWinRTCasingConventions]:  /scripting/jswinrt/using-the-windows-runtime-in-javascript#casing-conventions-with-windows-runtime-features "带有 Windows 运行时功能的大小写约定-在 JavaScript 中使用 Windows 运行时"  
[UwpApiIndex]: /uwp/api/index "Windows UWP 命名空间"  
[UwpApiWindowsUiPopups]: /uwp/api/windows.ui.popups "Windows UI 弹出命名空间"  
[UwpApiWindowsUiWebuiWebapplicationActivated]: /uwp/api/windows.ui.webui.webuiapplication.activated "WebUIApplication 事件"  
[UwpExtensionSdkDeviceFamiliesOverview]: /uwp/extension-sdks/device-families-overview "设备系列概述"  
[UwpSchemasAppxpackageUapmanifestschemaGeneratePackageManifest]: /uwp/schemas/appxpackage/uapmanifestschema/generate-package-manifest "Visual Studio 如何生成应用包清单"  
[WindowsUWPIndex]: /windows/uwp/index "通用 Windows 平台文档"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide "什么是通用 Windows 平台（UWP）应用？"  
[WindowsUWPGetStartedEnable]: /windows/uwp/get-started/enable-your-device-for-development "启用设备进行开发"  
[WindowsUwpSecurityIndex]: /windows/uwp/security/index "安全"  
[WindowsUwpPublishAccountTypesLocationsFees]: /windows/uwp/publish/account-types-locations-and-fees "帐户类型、位置和费用"  
[WindowsUwpPackagingAppCapabilitiesSpecialRestricted]: /windows/uwp/packaging/app-capability-declarations#special-and-restricted-capabilities "受限功能"  
[WindowsUwpPackagingAppCapabilitiesDevice]: /windows/uwp/packaging/app-capability-declarations#device-capabilities "设备功能"  
[WindowsUwpPackagingAppCapabilitiesGeneralUse]: /windows/uwp/packaging/app-capability-declarations#general-use-capabilities "常规-使用功能"  
[WindowsUwpPackagingAppCapabilities]: /windows/uwp/packaging/app-capability-declarations "应用功能声明"  

[BingResultsWindows10Settings]: https://binged.it/2lOGSH0 "windows 10 设置-Bing"  
[GithubWinjsWinjs]: https://github.com/winjs/winjs "winjs/winjs |GitHub"  
[MicrosoftDeveloperStorePublishApps]: https://developer.microsoft.com/store/publish-apps/index "发布 Windows 应用和游戏"  
[MicrosoftDeveloperWindowsApps]: https://developer.microsoft.com/windows/apps/index "通用 Windows 平台文档"  
[MicrosoftDeveloperWindowsAppsDesign]: https://developer.microsoft.com/windows/apps/design/index "设计和代码 Windows 应用"  
[MicrosoftDeveloperWindowsAppsDevelop]: https://developer.microsoft.com/windows/apps/develop/index "开发 UWP 应用"  
[MicrosoftDeveloperWindowsAppsGetStarted]: https://developer.microsoft.com/windows/apps/getstarted/index "Windows 10 应用入门"  
[MicrosoftDeveloperWindowsSamples]: https://developer.microsoft.com/windows/samples "代码示例"  
[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools 预览"  
[MicrosoftSupportWindowsAppPermissions]: https://support.microsoft.com/help/10557/windows-10-app-permissions "应用权限"  
[MicrosoftVisualStudioDownloads]: https://visualstudio.microsoft.com/downloads "下载"  
[MicrosoftVisualStudioPreview]: https://visualstudio.microsoft.com/vs/preview "Visual Studio 预览版"  
[PreviousVSDownloads]: https://visualstudio.microsoft.com/vs/older-downloads/ "Visual Studio 下载"