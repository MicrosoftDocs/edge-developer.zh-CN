---
description: EdgeDriver Microsoft Edge支持的 WebDriver 功能和特定选项 (Chromium) 。
title: 功能和 EdgeOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge， Web 开发， html， css， javascript， 开发人员， webdriver， selenium， 测试， 工具， 自动化， 测试
ms.openlocfilehash: 33b9d53b72a16a9c02a03a43679137d25de0025f
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624764"
---
# <a name="capabilities-and-edgeoptions"></a>功能和 EdgeOptions  

功能是您可以用于自定义和配置会话 `EdgeDriver` 的选项。  若要了解如何启动新 `EdgeDriver` 会话，请导航到自动[][WebdriverIndexAutomateMicrosoftEdgeChromium]Microsoft Edge。  本文介绍所有支持[的功能，Microsoft Edge][WebdriverIndexInstallMicrosoftEdgeChromium]将这些功能传递到 `EdgeDriver` 会话的详细信息。  

功能作为 JSON 映射传递到 WebDriver 会话。  WebDriver 测试框架提供 WebDriver 语言绑定。  WebDriver 语言绑定通常提供类型安全的便利方法，因此无需自己配置 JSON 映射。  不同的 WebDriver 语言绑定使用不同的机制来配置功能。  [Selenium][SeleniumMain] 通过 类配置 `EdgeOptions` 功能。

若要详细了解如何配置功能，请参阅文档了解首选 WebDriver 测试框架。  有关详细信息，请导航到["选择 WebDriver 测试框架"。][WebdriverIndexChooseAWebdriverTestingFramework]

## <a name="using-the-edgeoptions-class"></a>使用 EdgeOptions 类  

创建 实例 `EdgeOptions` ，从而提供设置特定于Microsoft Edge的便利方法。  配置对象后 `EdgeOptions` ，传递到 `EdgeOptions` `EdgeDriver` 构造函数。  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddExtensions("/path/to/extension.crx");
var driver = new EdgeDriver(options);
```  

若要使用没有关联的便利方法的功能，请使用 `AddAdditionalCapability` 方法。  您必须传递功能的完整名称和正确类型的值。  若要查看接受的功能和值类型的完整列表，请导航到 [EdgeOptions 对象](#edgeoptions-object)。  

```csharp
options.AddAdditionalCapability("wdpAddress", "remotehost:50080");
```  

## <a name="recognized-capabilities"></a>可识别的功能  

有关接受的标准 `EdgeDriver` 功能，请导航到 [Selenium 文档][SharedCapabilitiesSeleniumDocumentation] 和 [W3C WebDriver 标准][CapabilitiesW3cWebdriver]。  本文仅列出了特定于 Microsoft Edge。  

## <a name="edgeoptions-object"></a>EdgeOptions 对象  

大多数Microsoft Edge特定功能都通过 对象 `EdgeOptions` 公开。  在某些语言中，这些功能由 类 `EdgeOptions` 实现。  在其他语言中，这些功能存储在 中的 `ms:edgeOptions` 字典下 `DesiredCapabilities` 。  

| 功能 | 类型 | 默认值 | 详细信息 |  
|:--- |:--- |:--- |:--- |  
| args | 字符串列表 |  | 启动命令时要使用的命令行参数Microsoft Edge。  具有关联值的参数应用 `=` 符号 \ (例如 `['start-maximized', 'user-data-dir=/tmp/temp_profile']` \) 。 |  
| binary | 字符串 |  | 在 macOS Microsoft Edge \ (二进制文件的路径，路径应为实际的二进制文件，而不只是应用。  例如 `/Applications/Microsoft Edge.app/Contents/MacOS/Microsoft Edge` ，\) 。 |  
| debuggerAddress | 字符串 |  | 要连接到的调试器服务器的地址，格式为 `hostname/ip:port` ，例如 `127.0.0.1:38947` 。 |
| 分离 | 布尔型 | `false` | 如果为 ，Microsoft Edge WebDriver 服务关闭时退出，即使 WebDriver 本地端尚未 `false` 关闭会话。  如果 `true` 为 ，Microsoft Edge仅在 WebDriver 本地端关闭会话时退出。  如果 为 ，并且 WebDriver 本地端不关闭会话，则不清理该实例使用的临时用户 `true` `EdgeDriver` Microsoft Edge文件夹。 |  
| excludeSwitches | 字符串列表 |  | 默认情况下，Microsoft Edge切换到排除该 EdgeDriver 的命令行开关列表在启动 Microsoft Edge。  避免 `--` 使用开关前缀。 |  
| extensions | 字符串列表 |  | 启动时要安装的扩展的列表。  列表中的每个项目应为 Base64 编码的打包扩展 \ (`.crx` \) 。 |  
| localState | 字典 |  | 包含每个条目的字典，包含首选项的名称和值。  首选项将应用于用户数据文件夹中的本地状态文件。 |  
| minidumpPath | 字符串 |  | 用于存储最小Microsoft Edge的目录。  \ (仅在 Linux 上受支持。\)  |  
| mobileEmulation | 字典 |  | 值为 的字典， `deviceName` 或和 `deviceMetrics` 的值 `userAgent` 。 |  
| perfLoggingPrefs | 字典 |  | 指定性能日志记录首选项的可选字典。  有关详细信息，请导航到 [perfLoggingPrefs 对象](#perfloggingprefs-object)。 |  
| prefs | 字典 |  | 包含每个条目的字典，包含首选项的名称和值。  首选项仅适用于使用的用户配置文件。  例如，导航到 Microsoft Edge `Preferences` 的用户数据文件夹中的文件。 |  
| wdpAddress | 字符串 |  | 连接到的Windows门户服务器的地址，例如 `hostname/ip:port` `127.0.0.1:50080` 。  有关详细信息，请导航到"远程[调试 - Windows 10设备"。][DevtoolsRemoteDebuggingWindows] |  
| wdpPassword | 字符串 |  | 连接到 Device Portal 服务器时Windows可选密码。  如果服务器已启用身份验证，则必需。 |  
| wdpUsername | 字符串 |  | 连接到 Device Portal 服务器时Windows的可选用户名。  如果服务器已启用身份验证，则必需。 |  
| windowsApp | 字符串 |  | 要启动的应用包Microsoft Edge模型 ID，例如 `Microsoft.MicrosoftEdge.Stable_8wekyb3d8bbwe!MSEDGE` 。  使用 Device Portal 连接到 Windows 10X 设备或仿真器时Windows `windowsApp` `binary` 使用。 |  
| windowTypes | 字符串列表 |  | 窗口句柄列表中显示的窗口类型列表。  若要访问 Android webview 元素，请 `webview` 包含到列表中。 |  

## <a name="perfloggingprefs-object"></a>perfLoggingPrefs 对象  

词典 `perfLoggingPrefs` 具有以下格式 \ (所有键都是可选的\) 。  

| 项 | 类型 | 默认值 | 详细信息 |  
|:--- |:--- |:--- |:--- |  
| bufferUsageReportingInterval | 正整数 | 1000 | DevTools 跟踪缓冲区使用事件之间请求的毫秒数。  例如，如果为 1000，则每秒一次，DevTools 将报告跟踪缓冲区的已满。  如果报告指示缓冲区使用率为 100%，则发出警告。 |  
| enableNetwork | 布尔型 | true | 从网络 (收集 \) 事件。 |  
| enablePage | 布尔型 | true | 从页面 (收集 \) 事件。 |  
| traceCategories | 字符串 | \ (empty\)  | 一个以逗号分隔Microsoft Edge跟踪类别的字符串，应收集跟踪事件。  未指定或空字符串禁用跟踪。 |  

## <a name="returned-capabilities"></a>返回的功能  

以下列表包含创建新会话Microsoft Edge返回的所有特定于 `EdgeDriver` 会话的功能。  

| 功能 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| msedge.msedgedriverVersion | 字符串 | EdgeDriver 的版本。 |  
| msedge.userDataDir | 字符串 | 用户数据文件夹的路径，该实例Microsoft Edge。 |  

<!-- links -->  
[DevtoolsRemoteDebuggingWindows]: ../devtools-guide-chromium/remote-debugging/windows.md "远程调试设备Windows 10入门|Microsoft Docs"  
[WebdriverIndexChooseAWebdriverTestingFramework]: ./index.md#choose-a-webdriver-testing-framework "选择 WebDriver 测试框架 - 使用 WebDriver (Chromium) 实现测试自动化|Microsoft Docs"
[WebdriverIndexAutomateMicrosoftEdgeChromium]: ./index.md#automate-microsoft-edge-chromium "自动Microsoft Edge (Chromium) - WebDriver (Chromium) |Microsoft Docs"    
[WebdriverIndexInstallMicrosoftEdgeChromium]: ./index.md#install-microsoft-edge-chromium "安装Microsoft Edge (Chromium) - WebDriver (Chromium) |Microsoft Docs"  
<!-- external links -->
[SeleniumMain]: https://www.selenium.dev "SeleniumHQ 浏览器自动化"  
[SharedCapabilitiesSeleniumDocumentation]: https://www.selenium.dev/documentation/en/driver_idiosyncrasies/shared_capabilities/ "共享功能|Selenium 文档"   

[CapabilitiesW3cWebdriver]: https://www.w3.org/TR/webdriver#capabilities "功能 - WebDriver 规范|W3C"   
