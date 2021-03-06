---
description: 了解如何在 Microsoft Edge 中测试网站或应用，或者使用 WebDriver 自动执行浏览器
title: 使用 WebDriver (Chromium) 实现测试自动化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge， Web 开发， html， css， javascript， 开发人员， webdriver， selenium， 测试， 工具， 自动化， 测试
ms.openlocfilehash: 87855fad02243a9d86053e43b5523013644f7e35
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398831"
---
# <a name="use-webdriver-chromium-for-test-automation"></a>使用 WebDriver (Chromium) 实现测试自动化  

WebDriver 允许开发人员创建模拟用户交互的自动测试。  WebDriver 测试和模拟与 JavaScript 单元测试有以下不同。  

*   访问在浏览器中运行的 JavaScript 不可用的功能和信息。  
*   更精确地模拟用户事件或操作系统级事件。  
*   在单个测试会话中管理多个窗口、选项卡和网页。  
*   在特定的计算机上运行 Microsoft Edge 的多个会话。  
    
以下部分介绍如何开始使用 Microsoft Edge 的 WebDriver \ (Chromium\) 。  

## <a name="install-microsoft-edge-chromium"></a>安装 Microsoft Edge (Chromium)   

确保安装[Microsoft Edge (Chromium) 。 ][MicrosoftEdge]  若要确认已安装 Microsoft Edge \ (Chromium\) ，请导航到并验证版本号是 `edge://settings/help` 版本 75 或更高版本。  

## <a name="download-microsoft-edge-driver"></a>下载 Microsoft Edge 驱动程序  

若要开始自动执行测试，请使用以下步骤来确保安装的 WebDriver 版本与浏览器版本相匹配。  

1.  若要显示 Microsoft Edge 的版本，请导航到 `edge://settings/help` 。  
    
    :::image type="complex" source="./media/microsoft-edge-version.msft.png" alt-text="2021 年 2 月 10 日 Microsoft Edge Canary 的生成号" lightbox="./media/microsoft-edge-version.msft.png":::
       2021 年 2 月 10 日 Microsoft Edge Canary 的生成号  
    :::image-end:::  
    
1.  导航到[Microsoft Edge][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]驱动程序**** 的"下载"部分，并下载与 Microsoft Edge 的版本号匹配的 WebDriver。  
    
    :::image type="complex" source="./media/microsoft-edge-driver-install.msft.png" alt-text="Microsoft Edge 驱动程序上的"下载"部分" lightbox="./media/microsoft-edge-driver-install.msft.png":::
       Microsoft **Edge** 驱动程序上的 ["下载"部分][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]  
    :::image-end:::  
    
    <!--  
    > [!NOTE] 
    > For more information about test automation using Microsoft Edge \(EdgeHTML\), navigate to [Microsoft Edge Driver for Microsoft Edge \(EdgeHTML\)][Webdriver].  
    -->  
    
## <a name="choose-a-webdriver-language-binding"></a>选择 WebDriver 语言绑定  

必须下载的最后一个组件是特定语言的客户端驱动程序，用于将代码 \ (Python、Java、C\#、Ruby、JavaScript\) 转换为 Microsoft Edge \ (Chromium\) 中运行的命令。  

[下载你选择的 WebDriver 语言绑定][SeleniumDownloads]。  Microsoft Edge 团队建议使用 [Selenium 4.00-alpha07][NugetPackagesSeleniumWebdriver400alpha07] 或更高版本，因为它支持 Microsoft Edge \ (Chromium\) 。  但是，你可以控制 Microsoft Edge \ (Chromium\) 在所有旧版本的 Selenium 中，包括当前稳定的 Selenium 3 版本。  

> [!IMPORTANT]
> 如果您之前使用和类自动或测试了 Microsoft Edge \ (Chromium\) ，则 WebDriver 代码不会在 Microsoft Edge 版本 `ChromeDriver` `ChromeOptions` 80 或更高版本中运行。  若要解决此问题，请更新测试以使用 `EdgeOptions` 该类并下载 Microsoft [Edge 驱动程序][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。  

### <a name="use-selenium-3"></a>使用 Selenium 3  

如果你已使用 [Selenium 3，][|::ref1::|]你可能已有浏览器测试，并且想要添加 Microsoft Edge \ (Chromium\) 的覆盖范围，而无需更改 Selenium 版本。  若要使用 [Selenium 3][|::ref2::|] 为 Microsoft Edge \ (EdgeHTML\) 和 Microsoft Edge \ (Chromium\) 编写自动测试，请安装适用于 Microsoft Edge 的 [Selenium 工具][GithubMicrosoftEdgeSeleniumTools] 包以使用更新的驱动程序。  工具 `EdgeDriver` 中包含的类与 Selenium 4 中的内置等效项 `EdgeDriverService` 完全兼容。  

使用以下步骤将适用于 Microsoft Edge 和[Selenium 3][|::ref3::|]的[Selenium 工具][GithubMicrosoftEdgeSeleniumTools]添加到项目中。  

#### [<a name="c"></a>C#](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

使用[NuGet CLI][NugetCLI]或 Visual Studio 将[Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools]和[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] [包添加到 .NET Visual Studio。][VisualStudio]  

#### [<a name="python"></a>Python](#tab/python/)  

<a id="selenium-tools-install"></a>  

使用 [管道][PythonPip] 安装 [msedge-selenium-tools][PythonSeleniumTools] 和 [selenium][PythonSelenium] 程序包。  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<a name="java"></a>Java	](#tab/java/)  

<a id="selenium-tools-install"></a>  

如果你Java Maven，将以下依赖项复制并粘贴到文件以添加 `pom.xml` [msedge-selenium-tools-java][SonatypeMavenRepositorySearch]。  

```xml
<dependency>
    <groupId>com.microsoft.edge</groupId>
    <artifactId>msedge-selenium-tools-java</artifactId>
    <version>[3.141.0,)</version>
</dependency>
```  

The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page.][GithubMicrosoftEdgeSeleniumToolsReleases]  

#### [<a name="javascript"></a>JavaScript](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

使用 [npm][JavaScript|::ref4::|] 安装 [edge-selenium-tools][JavaScriptSeleniumTools] 和 [selenium-webdriver][JavaScriptSelenium] 程序包。  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## <a name="automate-microsoft-edge-chromium-with-webdriver"></a>使用 WebDriver (Microsoft Edge) Chromium  

若要使用 WebDriver 自动执行浏览器，必须先使用首选的 WebDriver 语言绑定启动 WebDriver 会话。  会话是使用 WebDriver 命令控制的浏览器的单个运行实例。  启动 WebDriver 会话以启动新的浏览器实例。  在关闭 WebDriver 会话之前，启动的浏览器实例保持打开状态。  

以下内容将引导你使用 Selenium 启动与 Microsoft Edge \ (Chromium\) 的 WebDriver 会话。  可以使用 Selenium 3 或 4 运行示例。  若要与 Selenium 3 一起使用，必须安装适用于 Microsoft Edge 的 [Selenium][GithubMicrosoftEdgeSeleniumTools] 工具包。  

### <a name="automate-microsoft-edge-chromium"></a>自动执行 Microsoft Edge (Chromium)   

Selenium 使用 `EdgeDriver` 类管理 Microsoft Edge \ (Chromium\) 会话。  若要启动会话并自动执行 Microsoft Edge \ (Chromium\) ，请创建一个新对象，并传递一个属性设置为 `EdgeDriver` `EdgeOptions` `UseChromium` `true` 的对象。  

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

该类 `EdgeDriver` 仅支持 Microsoft Edge \ (Chromium\) ，并且不支持 Microsoft Edge \ (EdgeHTML\) 。  对于基本用法，你可以创建一个 `EdgeDriver` 而不提供 `EdgeOptions` 。  

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
> 如果你的 IT 管理员将[DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]策略设置为 ，Microsoft Edge 驱动程序将被阻止驱动 `2` Microsoft Edge \ (Chromium\) ，因为驱动程序使用[Microsoft Edge DevTools。][DevtoolsIndex] [][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]  确保 [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] 策略设置为或自动执行 Microsoft Edge (`0` `1` Chromium) 。  

### <a name="choose-specific-browser-binaries-chromium-only"></a>选择"特定浏览器二进制文件 (仅 chromium")   

可以使用特定的 Microsoft Edge \ (Chromium\) 启动 WebDriver 会话。  例如，可以使用 [Microsoft Edge][MicrosoftedgeinsiderDownload] 预览频道（如 Microsoft Edge Beta）运行测试。  

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

使用类创建类实例时，它会为 `EdgeOptions` `EdgeDriver` Microsoft Edge `EdgeDriverService` \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 创建和启动相应的类。  

如果要创建一个，请使用该方法创建一个为 `EdgeDriverService` `CreateChromiumService()` Microsoft Edge \ (Chromium\) 。  `CreateChromiumService()`当您需要添加自定义项时，此方法非常有用。  例如，以下代码开始详细日志输出。  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
>当传递到实例时， `EdgeOptions` 不需要提供 `EdgeDriverService` `EdgeDriver` 对象。  该类根据你提供的服务使用 `EdgeDriver` Microsoft Edge \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 的默认选项。  
> 但是，如果要同时提供这两个类和类，请确保为相同版本的 Microsoft Edge 配置 `EdgeDriverService` `EdgeOptions` 这两者。  例如，可以使用类中的默认 Microsoft Edge \ (EdgeHTML\) 类和 `EdgeDriverService` Chromium `EdgeOptions` 属性。  该类 `EdgeDriver` 将引发错误，以防止使用不同的版本。  

#### [<a name="python"></a>Python](#tab/python/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

使用 Python 时， `Edge` 对象将创建和管理 `EdgeService` 。  若要配置 `EdgeService` ，请向对象传递 `Edge` 额外参数，如以下代码所示。  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<a name="java"></a>Java	](#tab/java/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

使用此方法 `createDefaultService()` 创建为 Microsoft `EdgeDriverService` Edge \ (Chromium\) 。  使用Java属性自定义驱动程序服务Java。  例如，以下代码使用 `"webdriver.edge.verboseLogging"` 该属性打开详细日志输出。  

```java
System.setProperty("webdriver.edge.verboseLogging", "true");
EdgeDriverService service = EdgeDriverService.createDefaultService();
EdgeOptions options = new EdgeOptions();
EdgeDriver driver = new EdgeDriver(service, options);
```  

#### [<a name="javascript"></a>JavaScript](#tab/javascript/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

使用 JavaScript 时，使用类 `Service` 创建和 `ServiceBuilder` 配置。  （可选）你可以将对象传递给该对象，该对象将启动 `Service` `Driver` \ (并停止\) 服务。  
若要配置 `Service` ，请使用方法之前在 `ServiceBuilder` 类中运行另一 `build()` 个方法。  然后作为 `service` 参数在方法中 `Driver.createSession()` 传递。  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <a name="use-chromium-specific-options"></a>使用Chromium-Specific选项  

如果将该属性设置为 ，可以使用类访问与自动执行其他 Chromium 浏览器时所使用的相同 `UseChromium` `true` `EdgeOptions` [Chromium][WebdriverCapabilitiesEdgeOptions] 特定属性和方法。  

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
> 如果该属性设置为 ，则不能对 `UseChromium` `true` Microsoft Edge \ (EdgeHTML\) 。  

## <a name="other-webdriver-installation-options"></a>其他 WebDriver 安装选项  

### <a name="chocolatey"></a>百年  

如果使用 ["小天][Chocolatey] "作为程序包管理器，请运行以下命令来安装 Microsoft Edge 驱动程序。  

```console
choco install selenium-chromium-edge-driver
```  

有关详细信息，请导航到 [Selenium Chromium Edge Driver onMiumy][ChocolateyPackagesSeleniumChromiumEdgeDriver]。  

### <a name="docker"></a>Docker  

如果使用 [Docker，][DockerHub]请运行以下命令来下载预配置映像（预安装 Microsoft Edge \ (Chromium\) 和 [Microsoft Edge][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] 驱动程序）。  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

有关详细信息，请导航到 Docker Hub 上的 [msedgedriver 容器][DockerHubMsedgedriver]。  

## <a name="next-steps"></a>后续步骤  

若要了解有关 WebDriver 以及如何使用 Selenium 编写自动 WebDriver 测试的信息，请导航到 [Selenium 文档][SeleniumDocumentation]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

Microsoft Edge 团队希望倾听你有关使用 WebDriver、Selenium 和 Microsoft Edge 的反馈。  若要向团队发送问题和意见，请选择 Microsoft Edge **** DevTools 中的"发送反馈"图标或发送推文[@EdgeDevTools。][TwitterTweetEdgeDevTools]  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools 中的**发送反馈**图标  
:::image-end:::  

<!-- links -->  

[DevtoolsIndex]: ../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[WebdriverCapabilitiesEdgeOptions]: ./capabilities-edge-options.md "功能和 EdgeOptions |Microsoft Docs"  
<!--[Webdriver]: ../edgehtml/webdriver/index.md "WebDriver (EdgeHTML) | Microsoft Docs"  -->  

[DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability - Microsoft Edge - 策略|Microsoft Docs"  

[Chocolatey]: https://chocolatey.org "花|云软件"  
[ChocolateyPackagesSeleniumChromiumEdgeDriver]: https://chocolatey.org/packages/selenium-chromium-edge-driver "Selenium Chromium Edge 驱动程序|百年"  

[DockerHub]: https://hub.docker.com "Docker Hub"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker 中心"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-tools |GitHub"  
[GithubMicrosoftEdgeSeleniumToolsReleases]: https://github.com/microsoft/edge-selenium-tools/releases "microsoft/edge-selenium-tools |GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/selenium |GitHub"  

[JavaScriptnpm]: https://www.npmjs.com/ "npm"  
[JavaScriptSeleniumTools]: https://www.npmjs.com/package/@microsoft/edge-selenium-tools "@microsoft/edge-selenium-tools |npm"  
[JavaScriptSelenium]: https://www.npmjs.com/package/selenium-webdriver "selenium-webdriver |npm"  

[MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]: https://developer.microsoft.com/microsoft-edge/tools/webdriver "WebDriver |Microsoft 开发人员"  

[MicrosoftEdge]: https://www.microsoft.com/edge "下载新版 Microsoft Edge 浏览器"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[NugetCLI]:https://www.nuget.org/packages/NuGet.CommandLine/ "NuGet.CommandLine |NuGet 库"  
[NugetPackagesMicrosoftEdgeSeleniumtools]: https://www.nuget.org/packages/Microsoft.Edge.SeleniumTools "Microsoft.Edge.SeleniumTools |NuGet 库"  
[NugetPackagesSeleniumWebdriver31410]: https://www.nuget.org/packages/Selenium.WebDriver/3.141.0 "Selenium.WebDriver 3.141.0 |NuGet 库"  
[NugetPackagesSeleniumWebdriver400alpha07]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha07 "Selenium.WebDriver 4.0.0-alpha07 |NuGet 库"  

[PythonPip]: https://pypi.org/project/pip/ "管道|PyPI"  
[PythonSeleniumTools]: https://pypi.org/project/msedge-selenium-tools/ "msedge-selenium-tools |PyPI"  
[PythonSelenium]: https://pypi.org/project/selenium/ "selenium |PyPI"

[SeleniumHQ]: https://www.selenium.dev "SeleniumHQ"  
[SeleniumDocumentation]: https://www.selenium.dev/documentation "Selenium 浏览器自动化项目|Selenium 文档"  
[SeleniumDownloads]: https://selenium.dev/downloads "下载|Selenium"  

[SonatypeMavenRepositorySearch]: https://search.maven.org/artifact/com.microsoft.edge/msedge-selenium-tools-java/3.141.0/jar "sonatype Maven 中央存储库搜索|com.microsoft.edge：msedge-selenium-tools-java"

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |发布推文"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |W3C"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无头浏览器|Wikipedia"  
