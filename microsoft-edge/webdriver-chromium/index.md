---
description: 了解如何在 WebDriver 中测试网站或Microsoft Edge或自动执行浏览器
title: 使用 WebDriver (Chromium) 实现测试自动化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/24/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge， Web 开发， html， css， javascript， 开发人员， webdriver， selenium， 测试， 工具， 自动化， 测试
ms.openlocfilehash: a1ec308fc1412ead27c4776ce0ccc2e873376652
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624673"
---
# <a name="use-webdriver-chromium-for-test-automation"></a>使用 WebDriver (Chromium) 实现测试自动化  

WebDriver 允许开发人员创建模拟用户交互的自动测试。  WebDriver 测试和模拟与 JavaScript 单元测试在以下方面有所不同。  

*   访问在浏览器中运行的 JavaScript 不可用的功能和信息。  
*   更精确地模拟用户事件或操作系统级事件。  
*   在单个测试会话中管理多个窗口、选项卡和网页。  
*   运行特定计算机上Microsoft Edge会话的会话。  


## <a name="relationship-between-webdriver-and-other-software"></a>WebDriver 和其他软件之间的关系

若要自动Microsoft Edge WebDriver 自动执行用户交互，您需要三个组件：

*  Microsoft Edge
*  Microsoft Edge 驱动程序
*  WebDriver 测试框架

这些组件之间的功能关系如下所示。

| 技术 | 角色 |
|---|---|
| WebDriver | 适用于平台和中性语言的线路协议的 W3C 标准。  此协议允许进程外程序远程指示 Web 浏览器的行为。 |
| Microsoft Edge 驱动程序 | Microsoft 专为用户实现 WebDriver Microsoft Edge。  测试作者编写使用驱动程序收到的 WebDriver Microsoft Edge的测试。  Microsoft Edge然后，驱动程序负责将该命令与浏览器通信。 |
| WebDriver 测试框架 | 测试作者使用测试框架编写端到端测试并自动化浏览器。  提供一个特定语言的接口，该接口将你的代码转换为Microsoft Edge在 \ (Chromium\Microsoft Edge \) 中运行的命令。  WebDriver 测试框架适用于所有主要平台和语言。  这样的框架之一是 Selenium。 |
| Internet Explorer驱动程序 | 专用于 webDriver 协议的实现Internet Explorer。  若要为用户运行旧版端到端测试Internet Explorer，我们建议使用 Internet Explorer Driver。 |

以下各节介绍如何开始使用 WebDriver for Microsoft Edge \ (Chromium\) 。  


## <a name="install-microsoft-edge-chromium"></a>安装Microsoft Edge (Chromium)   

确保安装[Microsoft Edge (Chromium) 。 ][MicrosoftEdge]  若要确认已安装 \Microsoft Edge \ (Chromium\) ，请导航到 ，并验证版本号是 `edge://settings/help` 75 或更高版本。


## <a name="download-microsoft-edge-driver"></a>下载 Microsoft Edge 驱动程序

若要开始自动执行测试，请使用以下步骤来确保安装的 WebDriver 版本与浏览器版本相匹配。  

1.  查找你的Microsoft Edge。  
    1.  导航到 `edge://settings/help`。  
        
        :::image type="complex" source="./media/microsoft-edge-version.msft.png" alt-text="2021 年 4 Microsoft Edge 15 日" lightbox="./media/microsoft-edge-version.msft.png":::
           2021 年 4 Microsoft Edge 15 日  
        :::image-end:::  
        
1.  导航到[Microsoft Edge驱动程序。][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]  
1.  导航到 **获取最新版本**。  
1.  选择与你的版本版本号相匹配的频道Microsoft Edge。  
    
    :::image type="complex" source="./media/microsoft-edge-driver-install.msft.png" alt-text="获取驱动程序网页上的获取Microsoft Edge部分" lightbox="./media/microsoft-edge-driver-install.msft.png":::
       "**获取驱动程序"网页上**的Microsoft Edge[部分][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]  
    :::image-end:::  
   
    
## <a name="choose-a-webdriver-testing-framework"></a>选择 WebDriver 测试框架

下载驱动程序Microsoft Edge，必须下载的最后一个组件是 WebDriver 测试框架。 测试作者使用 WebDriver 测试框架编写端到端测试并自动化浏览器。 框架提供特定于语言的接口，该接口将代码 (（如 Python、Java、C#、Ruby 或 JavaScript) ）转换为 Microsoft Edge Driver 在 Microsoft Edge \ (Chromium\) 中运行的命令。 WebDriver 测试框架适用于所有主要平台和语言。


本文提供了有关使用 Selenium 框架的说明，但您可以使用任何支持 WebDriver 的库、框架和编程语言。  若要使用除 Selenium 外的其他 WebDriver 测试框架完成相同的任务，请参考您所选择的框架的官方文档。

如果你使用的是 Selenium，Microsoft Edge 团队建议使用[Selenium 4.0.0-beta2][NugetPackagesSeleniumWebdriver400beta02]或更高版本，因为该版本的 Selenium 支持 Microsoft Edge \ (Chromium\) 。  但是，你可以控制所有较旧版本的 Selenium Microsoft Edge \ (Chromium\) ，包括当前稳定的 Selenium 3 版本。  

> [!IMPORTANT]
> 如果之前使用 和 类自动Microsoft Edge \ (Chromium\) ，WebDriver 代码将不会在 Microsoft Edge `ChromeDriver` `ChromeOptions` 版本 80 或更高版本中运行。  若要解决此问题，请更新测试以使用 类 `EdgeOptions` 并下载[Microsoft Edge驱动程序][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。  

### <a name="using-selenium-4"></a>使用 Selenium 4

Selenium WebDriver 测试框架可用于任何平台，可用于 Java、Python、C#、Ruby 和 JavaScript。

Selenium 4 内置支持 Microsoft Edge (Chromium) 。  若要安装 Selenium 4，请导航到["安装 Selenium 库"。][SeleniumInstallingLibraries]

如果使用 Selenium 4，则无需使用 Selenium Tools for Microsoft Edge。  Selenium Tools for Microsoft Edge仅适用于 Selenium 3。  如果您尝试将 Selenium 4 与 Selenium Tools for Microsoft Edge并尝试创建新实例，则 `EdgeDriver` 收到以下错误： `System.MissingMethodException: 'Method not found: 'OpenQA.Selenium.Remote.DesiredCapabilities OpenQA.Selenium.DriverOptions.GenerateDesiredCapabilities(Boolean)'` 。  

如果你使用的是 Selenium 4 并收到此错误，请从项目中删除 ，并确保你正在使用命名空间中的 official 和 `Microsoft.Edge.SeleniumTools` `EdgeOptions` `EdgeDriver` `OpenQA.Selenium.Edge` 类。

### <a name="using-selenium-3"></a>使用 Selenium 3  

如果你已使用[Selenium 3，][|::ref1::|]你可能已有浏览器测试，并且希望添加 Microsoft Edge \ (Chromium\) 的覆盖范围，而无需更改 Selenium 版本。  若要使用[Selenium 3][|::ref2::|]为 Microsoft Edge \ (EdgeHTML\) 和 Microsoft Edge \ (Chromium\) 编写自动测试，请安装适用于 Microsoft Edge 的[Selenium 工具][GithubMicrosoftEdgeSeleniumTools]程序包以使用更新的驱动程序。  工具 `EdgeDriver` `EdgeDriverService` 中包含的 和 类与 Selenium 4 中的内置等效项完全兼容。  

如果使用的是 Selenium 3，请使用以下步骤将适用于 Microsoft Edge[和 Selenium 3][|::ref3::|] [的 Selenium][GithubMicrosoftEdgeSeleniumTools]工具添加到项目中。

#### [<a name="c"></a>C#](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

使用 CLI 或 Visual Studio 将[Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools]和[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410]程序包添加到[NuGet .NET][NugetCLI] [项目][VisualStudio]。  

#### [<a name="python"></a>Python](#tab/python/)  

<a id="selenium-tools-install"></a>  

使用 [管道][PythonPip] 安装 [msedge-selenium-tools][PythonSeleniumTools] 和 [selenium][PythonSelenium] 程序包。  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<a name="java"></a>Java	](#tab/java/)  

<a id="selenium-tools-install"></a>  

如果您的Java项目使用 Maven，将以下依赖项复制并粘贴到您的文件以添加 `pom.xml` [msedge-selenium-tools-java][SonatypeMavenRepositorySearch]。  

```xml
<dependency>
    <groupId>com.microsoft.edge</groupId>
    <artifactId>msedge-selenium-tools-java</artifactId>
    <version>[3.141.0,)</version>
</dependency>
```  

The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].  

#### [<a name="javascript"></a>JavaScript](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

使用 [npm][JavaScript|::ref4::|] 安装 [edge-selenium-tools][JavaScriptSeleniumTools] 和 [selenium-webdriver][JavaScriptSelenium] 程序包。  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  


## <a name="automate-microsoft-edge-chromium-with-webdriver"></a>使用 WebDriver Microsoft Edge (Chromium) 自动执行部署  

若要使用 WebDriver 自动化浏览器，必须先使用首选的 WebDriver 测试框架启动 WebDriver 会话。  会话是使用 WebDriver 命令控制的浏览器的单个运行实例。  启动 WebDriver 会话以启动新的浏览器实例。  在关闭 WebDriver 会话之前，启动的浏览器实例保持打开状态。  

以下内容将引导你使用 Selenium 启动 WebDriver 会话，Microsoft Edge \ (Chromium\) 。  可以使用 Selenium 3 或 4 运行这些示例。  若要将 WebDriver 与 Selenium 3 一同使用，必须安装适用于 Microsoft Edge 的[Selenium][GithubMicrosoftEdgeSeleniumTools]工具包。  

> [!NOTE]
> 本文提供了有关使用 Selenium 框架的说明，但您可以使用任何支持 WebDriver 的库、框架和编程语言。  若要使用另一个框架完成相同的任务，请参阅您所选择的框架的官方文档。

### <a name="automate-microsoft-edge-chromium"></a>自动Microsoft Edge (Chromium)   

Selenium 使用 类管理 Microsoft Edge `EdgeDriver` \ (Chromium\) 会话。  若要启动会话并自动Microsoft Edge \ (Chromium\) ，请创建一个新对象，并传递一个属性设置为 `EdgeDriver` `EdgeOptions` `UseChromium` 的对象 `true` 。  

#### [<a name="c"></a>C#](#tab/c-sharp/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a>Python](#tab/python/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options = options)
```  

#### [<a name="java"></a>Java	](#tab/java/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

该类 `EdgeDriver` 仅支持 Microsoft Edge \ (Chromium\) ，不支持 Microsoft Edge \ (EdgeHTML\) 。  对于基本用法，可以在不提供 `EdgeDriver` 的情况下创建 `EdgeOptions` 。  

```java
EdgeDriver driver = new EdgeDriver();
```  

#### [<a name="javascript"></a>JavaScript](#tab/javascript/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> 如果你的 IT 管理员将[DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]策略设置为 ，Microsoft Edge 驱动程序被阻止驱动 `2` Microsoft Edge \ (Chromium\) ，因为驱动程序使用 Microsoft Edge [DevTools][DevtoolsIndex]。 [][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]  确保[将 DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]策略设置为 `0` 或 `1` 自动Microsoft Edge (Chromium) 。  

### <a name="choose-specific-browser-binaries-chromium-only"></a>选择"特定浏览器二进制文件 (Chromium仅)   

可以使用特定文件 \Microsoft Edge\ (Chromium\) WebDriver 会话。  例如，可以使用预览频道（如[Microsoft Edge）][MicrosoftedgeinsiderDownload]运行Microsoft Edge Beta。  

#### [<a name="c"></a>C#](#tab/c-sharp/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a>Python](#tab/python/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options = options)
```  

#### [<a name="java"></a>Java	](#tab/java/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.setBinary("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

EdgeDriver driver = new EdgeDriver(options);
```  

#### [<a name="javascript"></a>JavaScript](#tab/javascript/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <a name="customize-the-microsoft-edge-driver-service"></a>自定义 Microsoft Edge 驱动程序服务  

#### [<a name="c"></a>C#](#tab/c-sharp/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

使用 类创建类实例时，它会为 `EdgeOptions` `EdgeDriver` Microsoft Edge `EdgeDriverService` \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 创建和启动相应的类。  

如果要创建 ，请使用 方法创建一个配置为 Microsoft Edge `EdgeDriverService` `CreateChromiumService()` \ (Chromium\) 。  `CreateChromiumService()`当您需要添加自定义项时，该方法非常有用。  例如，以下代码开始详细日志输出。  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
>在传递给实例时，不需要 `EdgeOptions` 提供 `EdgeDriverService` `EdgeDriver` 对象。  该类根据你提供的服务使用 Microsoft Edge `EdgeDriver` \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 的默认选项。  
> 但是，如果要同时提供 和 类，请确保为同一版本的 `EdgeDriverService` `EdgeOptions` Microsoft Edge。  例如，可以使用默认的 Microsoft Edge \ (EdgeHTML\) `EdgeDriverService` 类Chromium属性 `EdgeOptions` 。  `EdgeDriver`该类会引发错误，以阻止使用不同的版本。  

#### [<a name="python"></a>Python](#tab/python/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

使用 Python 时， `Edge` 对象将创建和管理 `EdgeService` 。  若要配置 `EdgeService` ，请向 对象传递 `Edge` 额外参数，如以下代码所示。  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<a name="java"></a>Java	](#tab/java/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

使用 `createDefaultService()` 方法可创建 `EdgeDriverService` 一个配置为 Microsoft Edge \ (Chromium\) 。  使用 Java 系统属性自定义 Java 中的驱动程序服务。  例如，以下代码使用 `"webdriver.edge.verboseLogging"` 属性打开详细日志输出。  

```java
System.setProperty("webdriver.edge.verboseLogging", "true");
EdgeDriverService service = EdgeDriverService.createDefaultService();
EdgeOptions options = new EdgeOptions();
EdgeDriver driver = new EdgeDriver(service, options);
```  

#### [<a name="javascript"></a>JavaScript](#tab/javascript/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

使用 JavaScript 时，请使用 类 `Service` 创建和 `ServiceBuilder` 配置 。  （可选）可以将对象传递给对象，该对象将启动 `Service` `Driver` \ (并停止\) 服务。  
若要配置 `Service` ，请运行 类中的另一 `ServiceBuilder` 个方法，然后再使用 `build()` 方法。  然后， `service` 在 方法中将 作为 参数 `Driver.createSession()` 传递。  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <a name="use-chromium-specific-options"></a>使用Chromium-Specific选项  

如果将 属性设置为 ，可以使用 类来访问Chromium自动化其他浏览器时所使用的特定于 Chromium `UseChromium` `true` `EdgeOptions` 的属性和方法。 [][WebdriverCapabilitiesEdgeOptions]  

#### [<a name="c"></a>C#](#tab/c-sharp/)  

<a id="use-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<a name="python"></a>Python](#tab/python/)  

<a id="use-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<a name="java"></a>Java	](#tab/java/)  

<a id="use-chromium-specific-options-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

#### [<a name="javascript"></a>JavaScript](#tab/javascript/)  

<a id="use-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

* * *  

> [!NOTE]
> 如果属性设置为 ，则不能对 Microsoft Edge `UseChromium` `true` \ (EdgeHTML\) 。  


## <a name="other-webdriver-installation-options"></a>其他 WebDriver 安装选项  

### <a name="docker"></a>Docker  

如果使用[Docker，][DockerHub]请运行以下命令，下载预配置映像Microsoft Edge \ (Chromium\) Microsoft Edge[驱动程序][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]预安装。  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

有关详细信息，请导航到 Docker Hub 上的 [msedgedriver 容器][DockerHubMsedgedriver]。  


## <a name="testing-internet-explorer"></a>测试Internet Explorer

若要测试需要更新Internet Explorer，Internet Explorer [驱动程序][GithubSeleniumHqWikiIEDriver] 和Internet Explorer。  Internet Explorer驱动程序由 Selenium 项目维护。  即使Microsoft Edge支持 IE 模式，你Microsoft Edge驱动程序Microsoft Edge IE 模式下测试站点。


## <a name="application-guard"></a>应用程序防护

使用应用程序防护Microsoft Defender 应用程序防护 (的) 可以使用驱动程序自动Microsoft Edge站点。

使用应用程序防护的不受信任的站点无法使用应用程序驱动程序自动Microsoft Edge操作。  应用程序防护在容器中启动不受信任的站点，并且此容器不会公开驱动程序与站点Microsoft Edge所需的远程调试端口。

企业管理员定义什么是受信任的站点，包括云资源和内部网络。  不在受信任站点列表中的网站被视为不受信任的网站。  Microsoft Edge驱动程序可以自动执行 InPrivate 窗口和受信任站点列表中的站点。

有关应用程序防护详细信息，请导航到： 

*  [Microsoft Edge 对 Microsoft Defender 应用程序防护的支持][DeployedgeMicrosoftEdgeSecurityWindowsDefenderApplicationGuard]
*  [Microsoft Defender 应用程序防护概述][WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]


## <a name="see-also"></a>另请参阅

*  [Selenium 文档][SeleniumDocumentation] - 有关 Selenium 上下文中的 WebDriver 以及如何使用 Selenium 编写自动 WebDriver 测试的信息。


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

Microsoft Edge团队希望听到你有关使用 WebDriver、WebDriver 测试框架 (如 Selenium) 和 Microsoft Edge 的反馈。  若要向团队发送你的问题和意见，请选择开发人员工具Microsoft Edge**** 发送反馈图标或发送推文[@EdgeDevTools。][TwitterTweetEdgeDevTools]  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的发送反馈图标" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools 中的**发送反馈**图标  
:::image-end:::  


<!-- links -->  
[DevtoolsIndex]: ../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[WebdriverCapabilitiesEdgeOptions]: ./capabilities-edge-options.md "功能和 EdgeOptions |Microsoft Docs"  
<!-- external links -->
[DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability - Microsoft Edge - 策略|Microsoft Docs"  
[DeployedgeMicrosoftEdgeSecurityWindowsDefenderApplicationGuard]: /deployedge/microsoft-edge-security-windows-defender-application-guard "Microsoft Edge支持Microsoft Defender 应用程序防护 |Microsoft Docs"

[WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]: /windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview "Microsoft Defender 应用程序防护 (Windows 10) - Windows安全|Microsoft Docs"  

[DockerHub]: https://hub.docker.com "Docker Hub"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker 中心"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-tools |GitHub"  
[GithubMicrosoftEdgeSeleniumToolsReleases]: https://github.com/microsoft/edge-selenium-tools/releases "microsoft/edge-selenium-tools |GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/selenium |GitHub"  
[GithubSeleniumHqWikiIEDriver]: https://github.com/SeleniumHQ/selenium/wiki/InternetExplorerDriver "Internet Explorer Driver - Selenium |GitHub"

[JavaScriptnpm]: https://www.npmjs.com/ "npm"  
[JavaScriptSeleniumTools]: https://www.npmjs.com/package/@microsoft/edge-selenium-tools "@microsoft/edge-selenium-tools |npm"  
[JavaScriptSelenium]: https://www.npmjs.com/package/selenium-webdriver "selenium-webdriver |npm"  

[MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]: https://developer.microsoft.com/microsoft-edge/tools/webdriver "Microsoft Edge驱动程序|Microsoft Edge开发人员"  

[MicrosoftEdge]: https://www.microsoft.com/edge "下载新版 Microsoft Edge 浏览器"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[NugetCLI]:https://www.nuget.org/packages/NuGet.CommandLine/ "NuGet。CommandLine |NuGet库"  
[NugetPackagesMicrosoftEdgeSeleniumtools]: https://www.nuget.org/packages/Microsoft.Edge.SeleniumTools "Microsoft.Edge.SeleniumTools |NuGet库"  
[NugetPackagesSeleniumWebdriver31410]: https://www.nuget.org/packages/Selenium.WebDriver/3.141.0 "Selenium.WebDriver 3.141.0 |NuGet库"  
[NugetPackagesSeleniumWebdriver400beta02]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-beta2 "Selenium.WebDriver 4.0.0-beta2 |NuGet库"  

[PythonPip]: https://pypi.org/project/pip/ "管道|PyPI"  
[PythonSeleniumTools]: https://pypi.org/project/msedge-selenium-tools/ "msedge-selenium-tools |PyPI"  
[PythonSelenium]: https://pypi.org/project/selenium/ "selenium |PyPI"

[SeleniumHQ]: https://www.selenium.dev "SeleniumHQ"  
[SeleniumDocumentation]: https://www.selenium.dev/documentation "Selenium 浏览器自动化Project |Selenium 文档"  
[SeleniumInstallingLibraries]: https://www.selenium.dev/documentation/en/selenium_installation/installing_selenium_libraries "安装 Selenium 库|Selenium"

[SonatypeMavenRepositorySearch]: https://search.maven.org/artifact/com.microsoft.edge/msedge-selenium-tools-java/3.141.0/jar "Sonatype Maven 中央存储库搜索|com.microsoft.edge：msedge-selenium-tools-java"

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |发布推文"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |W3C"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无头浏览器|Wikipedia"  
