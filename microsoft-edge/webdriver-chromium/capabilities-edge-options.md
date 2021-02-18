---
description: EdgeDriver 支持 WebDriver 功能和 Microsoft Edge 特定选项 (Chromium) 。
title: 功能和 EdgeOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge， Web 开发， html， css， javascript， 开发人员， webdriver， selenium， 测试， 工具， 自动化， 测试
ms.openlocfilehash: 5a48ca34e46b56fa60bcacfade2add23026be144
ms.sourcegitcommit: f95812c4e1b7277f67c6c4891be2779cc1b5bdf1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "11343777"
---
# 功能和 EdgeOptions  

功能是您可以用于自定义和配置会话 `EdgeDriver` 的选项。  若要了解有关启动新 `EdgeDriver` 会话，请导航到["自动执行 Microsoft Edge"。][WebdriverIndexAutomateMicrosoftEdgeChromium]  本文介绍 [Microsoft Edge][WebdriverIndexInstallMicrosoftEdgeChromium] 的所有受支持的功能，以及将这些功能传递到 `EdgeDriver` 会话的详细信息。  

功能作为 JSON 映射传递到 WebDriver 会话。  WebDriver 语言绑定通常提供类型安全的便利方法，因此无需自己配置 JSON 映射。  不同的 WebDriver 语言绑定使用不同的机制来配置功能。  导航到首选语言绑定 [的文档][WebdriverIndexChooseWebdriverLanguageBinding] ，详细了解如何配置功能。  [Selenium][SeleniumMain] 通过类配置 `EdgeOptions` 功能。  

## 使用 EdgeOptions 类  

创建实例 `EdgeOptions` ，从而提供设置 Microsoft Edge 特定功能的便利方法。  配置对象 `EdgeOptions` 后，传递到 `EdgeOptions` `EdgeDriver` 构造函数。  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddExtensions("/path/to/extension.crx");
var driver = new EdgeDriver(options);
```  

若要使用没有关联的便利方法的功能，请使用 `AddAdditionalCapability` 该方法。  您必须传递该功能的全名和具有正确类型的值。  若要查看接受功能和值类型的完整列表，请导航到 [EdgeOptions 对象](#edgeoptions-object)。  

```csharp
options.AddAdditionalCapability("wdpAddress", "remotehost:50080");
```  

## 可识别的功能  

对于接受的标准功能 `EdgeDriver` ，导航到 [Selenium 文档][SharedCapabilitiesSeleniumDocumentation] 和 [W3C WebDriver 标准][CapabilitiesW3cWebdriver]。  本文仅列出了特定于 Microsoft Edge 的功能。  

## EdgeOptions 对象  

大多数特定于 Microsoft Edge 的功能都通过对象 `EdgeOptions` 公开。  在某些语言中，这些功能由类 `EdgeOptions` 实现。  在其他语言中，这些功能存储在 中的 `ms:edgeOptions` 字典下 `DesiredCapabilities` 。  

| 功能 | 类型 | 默认值 | 详细信息 |  
|:--- |:--- |:--- |:--- |  
| args | 字符串列表 |  | 启动 Microsoft Edge 时使用的命令行参数列表。  具有关联值的参数应用 \ (分隔，例如 `=` `['start-maximized', 'user-data-dir=/tmp/temp_profile']` ，\) 。 |  
| binary | 字符串 |  | 在 macOS 上使用 \ (的 Microsoft Edge 二进制文件的路径，路径应为实际二进制文件，而不只是应用。  例如 `/Applications/Microsoft Edge.app/Contents/MacOS/Microsoft Edge` ，\) 。 |  
| debuggerAddress | 字符串 |  | 要连接到的调试器服务器的地址，例如 `hostname/ip:port` 。 `127.0.0.1:38947` |
| detach | 布尔型 | `false` | 如果 ，Microsoft Edge 在 WebDriver 服务关闭时退出，即使 `false` WebDriver 本地端尚未关闭会话。  如果 `true` ，Microsoft Edge 仅在 WebDriver 本地端关闭会话时退出。  如果 ，并且 WebDriver 本地端不关闭会话，则不清理 Microsoft Edge 实例使用的临时 `true` `EdgeDriver` 用户数据文件夹。 |  
| excludeSwitches | 字符串列表 |  | 启动 Microsoft Edge 时，默认情况下会传递用于排除该 EdgeDriver 的 Microsoft Edge 命令行开关列表。  避免 `--` 使用开关前缀。 |  
| extensions | 字符串列表 |  | 启动时要安装的扩展的列表。  列表中的每个项目应为 base-64 编码的打包扩展 \ (`.crx` \) 。 |  
| localState | 字典 |  | 包含首选项名称和值的每个条目的字典。  首选项将应用于用户数据文件夹中的本地状态文件。 |  
| minidumpPath | 字符串 |  | 用于存储 Microsoft Edge 小型云的目录。  \ (仅在 Linux 上受支持。\)  |  
| mobileEmulation | 字典 |  | 一个字典，其值为 `deviceName` ，或与 `deviceMetrics` `userAgent` 的值。 |  
| perfLoggingPrefs | 字典 |  | 指定性能日志记录首选项的可选字典。  有关详细信息，请导航到 [perfLoggingPrefs 对象](#perfloggingprefs-object)。 |  
| prefs | 字典 |  | 包含首选项名称和值的每个条目的字典。  首选项仅适用于使用的用户配置文件。  例如，导航到 `Preferences` Microsoft Edge 的用户数据文件夹中的文件。 |  
| wdpAddress | 字符串 |  | 连接到的 Windows Device Portal 服务器的地址，例如 `hostname/ip:port`  `127.0.0.1:50080` 。  有关详细信息，请导航到 [远程调试 - Windows 10 设备][DevtoolsRemoteDebuggingWindows]。 |  
| wdpPassword | 字符串 |  | 连接到 Windows Device Portal 服务器时使用的可选密码。  如果服务器已启用身份验证，则必需。 |  
| wdpUsername | 字符串 |  | 连接到 Windows Device Portal 服务器时使用的可选用户名。  如果服务器已启用身份验证，则必需。 |  
| windowsApp | 字符串 |  | 要启动的 Microsoft Edge 应用包的应用程序用户模型 ID，例如 `Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE` 。  使用 `windowsApp` Windows Device Portal 连接到 Windows `binary` 10X 设备或仿真器时，而不是使用。 |  
| windowTypes | 字符串列表 |  | 窗口句柄列表中显示的窗口类型列表。  若要访问 Android Webview 元素，请 `webview` 包含到列表中。 |  

## perfLoggingPrefs 对象  

词典 `perfLoggingPrefs` 具有以下格式 \ (所有键都是可选的\) 。  

| 项 | 类型 | 默认值 | 详细信息 |  
|:--- |:--- |:--- |:--- |  
| bufferUsageReportingInterval | 正整数 | 1000 | DevTools 跟踪缓冲区使用事件之间请求的毫秒数。  例如，如果为 1000，则每秒一次，DevTools 将报告跟踪缓冲区的已满。  如果报告指示缓冲区使用率为 100%，则发出警告。 |  
| enableNetwork | 布尔型 | true | 收集\ (收集\) 网络域中的事件。 |  
| enablePage | 布尔型 | true | 收集\ (收集\) 页面域中的事件。 |  
| traceCategories | 字符串 | \ (empty\)  | Microsoft Edge 跟踪类别的逗号分隔字符串，应收集跟踪事件。  未指定或空字符串禁用跟踪。 |  

## 返回的功能  

以下列表包含创建新会话时返回的所有特定于 Microsoft Edge `EdgeDriver` 的功能。  

| 功能 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| msedge.msedgedriverVersion | 字符串 | EdgeDriver 的版本。 |  
| msedge.userDataDir | 字符串 | Microsoft Edge 实例使用的用户数据文件夹的路径。 |  

<!-- links -->  

[DevtoolsRemoteDebuggingWindows]: ../devtools-guide-chromium/remote-debugging/windows.md "远程调试 Windows 10 设备|Microsoft Docs"  
[WebdriverIndexChooseWebdriverLanguageBinding]: ./index.md#choose-a-webdriver-language-binding "选择 WebDriver 语言绑定 - WebDriver (Chromium) |Microsoft Docs"
[WebdriverIndexAutomateMicrosoftEdgeChromium]: ./index.md#automate-microsoft-edge-chromium "自动执行 Microsoft Edge (Chromium) - WebDriver (Chromium) |Microsoft Docs"    
[WebdriverIndexInstallMicrosoftEdgeChromium]: ./index.md#install-microsoft-edge-chromium "安装 Microsoft Edge (Chromium) - WebDriver (Chromium) |Microsoft Docs"  

[SeleniumMain]: https://www.selenium.dev "SeleniumHQ 浏览器自动化"  
[SharedCapabilitiesSeleniumDocumentation]: https://www.selenium.dev/documentation/en/driver_idiosyncrasies/shared_capabilities/ "共享功能|Selenium 文档"   

[CapabilitiesW3cWebdriver]: https://www.w3.org/TR/webdriver#capabilities "功能 - WebDriver 规范|W3C"   
