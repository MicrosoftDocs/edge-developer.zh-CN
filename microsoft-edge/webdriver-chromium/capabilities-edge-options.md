---
description: EdgeDriver (Chromium) 支持的 WebDriver 功能和 Microsoft Edge 特定选项的参考。
title: 功能和 EdgeOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge，web 开发，html，css，javascript，开发人员，webdriver，selenium，测试，工具，自动化，测试
ms.openlocfilehash: 1f6dca1b7ce3eb4fab3aaaab6450eee7cbf3eae5
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "11192241"
---
# 功能和 EdgeOptions  

功能是您可以用于自定义和配置会话的选项 `EdgeDriver` 。  若要启动 `EdgeDriver` 会话，请导航到 " [驱动 Microsoft Edge][DrivingEdgeWebDriverIndex]"。  本文介绍 [Microsoft Edge][DownloadEdgeWebDriverIndex] 支持的所有功能以及将这些功能传递到会话的其他详细信息 `EdgeDriver` 。  

WebDriver 语言绑定提供将功能传递到 `EdgeDriver` 的方法。  确切的机制取决于 [你选择的语言绑定][ChooseLanguageBindingWebDriverIndex]。  在 [Selenium][SeleniumMain]中，功能通过课堂提供 `EdgeOptions` 。  

## 使用 EdgeOptions 类  

创建一个实例 `EdgeOptions` ，它具有设置 Microsoft Edge 特定功能的便利方法。  配置 `EdgeOptions` 对象后，传递 `EdgeOptions` 到 `EdgeDriver` 构造函数。  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddExtensions("/path/to/extension.crx");
var driver = new EdgeDriver(options);
```  

对于尚无便利方法的功能，请使用 `AddAdditionalCapability` 方法。  你必须知道功能的名称和它接受的值类型。  若要查看完整列表，请导航到 [EdgeOptions 对象](#edgeoptions-object)。  

```csharp
options.AddAdditionalCapability("wdpAddress", "remotehost:50080");
```  

## 公认的功能  

对于接受的标准功能 `EdgeDriver` ，请导航到 [Selenium 文档][SharedCapabilitiesSeleniumDocumentation] 和 [W3C WebDriver 标准][CapabilitiesW3cWebdriver]。  本文仅列出了特定于 Microsoft Edge 的功能。  

## EdgeOptions 对象  

大多数 Microsoft Edge 特定的功能都通过该 `EdgeOptions` 对象公开。  在某些语言中，功能由 `EdgeOptions` 类实现。  在其他语言中，功能存储 `ms:edgeOptions` 在字典中 `DesiredCapabilities` 。  

| 功能 | 类型 | 默认值 | 详细信息 |  
|:--- |:--- |:--- |:--- |  
| args | 字符串列表 |  | 要在启动 Microsoft Edge 时使用的命令行参数列表。  带有关联值的参数应使用 `=` (（例如 `['start-maximized', 'user-data-dir=/tmp/temp_profile']` \ ) ）分隔。  |  
| 二进制 | 字符串 |  | Microsoft Edge 二进制文件的路径若要在 macOS 上使用 \ (，路径应该是实际二进制，而不仅仅是应用。  例如， `/Applications/Microsoft Edge.app/Contents/MacOS/Microsoft Edge` \ ) 。  |  
| extensions | 字符串列表 |  | 要在启动时安装的扩展的列表。  列表中的每个项目都应该是一个 base-64 编码的压缩扩展 \ (`.crx` \ ) 。  |  
| localState | 字典 |  | 包含由首选项的名称和其值组成的每个条目的字典。  首选项将应用于 "用户数据" 文件夹中的本地状态文件。  |  
| prefs | 字典 |  | 包含由首选项的名称和其值组成的每个条目的字典。  首选项仅适用于使用中的用户配置文件。  有关示例，请导航到 `Preferences` Microsoft Edge 的用户数据目录中的文件。  |  
| 分离 | 布尔 | 否 | 如果为 false，Microsoft Edge 将在结束时退出 `EdgeDriver` ，无论会话是否已退出。  如果为 true，则仅当会话退出时，Microsoft Edge 才退出 (或关闭 ) 。  **注意**：如果为 true，并且会话未退出，则不 `EdgeDriver` 会清理 Microsoft Edge 实例使用的临时用户数据目录。  |  
| debuggerAddress | 字符串 |  | 要连接到的调试器服务器的地址，以 <主机名/ip： port> 的形式表示  `127.0.0.1:38947` 。  |
| excludeSwitches | 字符串列表 |  | 在启动 Microsoft Edge 时默认情况下传递的 Microsoft Edge 命令行开关列表，以排除 EdgeDriver。  不要给开关加前缀 `--` 。  |  
| minidumpPath | 字符串 |  | 用于存储 Microsoft Edge minidumps 的目录。  \ (仅在 Linux 上受支持。 \ )  |  
| mobileEmulation | 字典 |  | 包含值的字典 `deviceName` ，或 "and" 的值 `deviceMetrics` `userAgent` 。  |  
| perfLoggingPrefs | 字典 |  | 指定性能记录首选项的可选词典。  有关详细信息，请导航到 [perfLoggingPrefs 对象](#perfloggingprefs-object)。  |  
| windowTypes | 字符串列表 |  | 窗口类型列表，显示在窗口句柄列表中。  对于对 Android web 视图元素的访问权限，请将其包含 `webview` 在列表中。  |  
| wdpAddress | 字符串 |  | 要连接的 Windows Device Portal server 的地址， `hostname/ip:port` 例如形式  `127.0.0.1:50080` 。  有关详细信息，请导航到 [远程调试-Windows 10 设备][DevtoolsRemoteDebuggingWindows]。  |  
| wdpUsername | 字符串 |  | 连接到 Windows Device Portal server 时要使用的可选用户名。  如果服务器已启用身份验证，则为必需。  |  
| wdpPassword | 字符串 |  | 连接到 Windows Device Portal server 时要使用的可选密码。  如果服务器已启用身份验证，则为必需。  |  
| Windowsapp.lib | 字符串 |  | 要启动的 Microsoft Edge 应用包的应用程序用户模型 ID `Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE` 。  使用 `windowsApp` `binary` Windows device Portal，而不是连接到 Windows 10 10 设备或模拟器。  |  

## perfLoggingPrefs 对象  

`perfLoggingPrefs`字典具有下列格式 \ (所有键都是可选的 \ ) 。  

| 项 | 类型 | 默认值 | 详细信息 |  
|:--- |:--- |:--- |:--- |  
| enableNetwork | 布尔型 | true | 若要从网络域收集 \ (或不收集 \ ) 事件。  |  
| enablePage | 布尔型 | true | 若要收集 \ (或不收集来自 Page 域的 \ ) 事件。  |  
| traceCategories | 字符串 | \ (清空 \ )  | 应收集其跟踪事件的 Microsoft Edge 跟踪类别的逗号分隔字符串。  未指定或空字符串将禁用跟踪。  |  
| bufferUsageReportingInterval | 正整数 | 1000 | DevTools 跟踪缓冲区使用事件之间所请求的毫秒数。  例如，如果1000，则每秒一次，DevTools 会报告跟踪缓冲区的完整程度。  如果报表指明缓冲区使用率为100%，则会发出警告。  |  

## 返回的功能  

以下列表包含在 `EdgeDriver` 创建新会话时返回的所有 Microsoft Edge 特定的功能。  

| 功能 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| msedge.msedgedriverVersion | 字符串 | EdgeDriver 的版本。 |  
| msedge.userDataDir | 字符串 | Microsoft Edge 实例使用的用户数据目录的路径。 |  

<!-- links -->  

[DevtoolsRemoteDebuggingWindows]: ../devtools-guide-chromium/remote-debugging/windows.md "远程调试 Windows 10 设备入门 |Microsoft 文档"  
[DrivingEdgeWebDriverIndex]: ./index.md#driving-microsoft-edge-chromium "推动 Microsoft Edge (Chromium) |Microsoft 文档"    
[DownloadEdgeWebDriverIndex]: ./index.md#install-microsoft-edge-chromium "安装 Microsoft Edge (Chromium) |Microsoft 文档"  
[ChooseLanguageBindingWebDriverIndex]: ./index.md#choose-a-webdriver-language-binding "选择 WebDriver 语言绑定 |Microsoft 文档"

[SeleniumMain]: https://www.selenium.dev "SeleniumHQ 浏览器自动化"  
[SharedCapabilitiesSeleniumDocumentation]: https://www.selenium.dev/documentation/en/driver_idiosyncrasies/shared_capabilities/ "共享功能 |Selenium 文档"   

[CapabilitiesW3cWebdriver]: https://www.w3.org/TR/webdriver/#capabilities "功能-WebDriver 规范 |W3C"   
