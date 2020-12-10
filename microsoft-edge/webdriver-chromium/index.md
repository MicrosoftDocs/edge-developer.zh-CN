---
description: 了解如何在 Microsoft Edge 中测试你的网站或应用，或通过 WebDriver 自动处理浏览器。
title: WebDriver (Chromium)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge，web 开发，html，css，javascript，开发人员，webdriver，selenium，测试，工具，自动化，测试
ms.openlocfilehash: 3c197a83dbf16c68102ff6e9a4ee6f33b0573af2
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "11192243"
---
# 使用 WebDriver (Chromium) 进行测试自动化  

WebDriver 使你 (开发人员 \ ) 创建模拟用户交互的自动测试。  由于以下原因，WebDriver 测试和模拟与 JavaScript 单元测试不同。  

*   访问功能和信息在浏览器中运行的 JavaScript 不可用。  
*   更准确地模拟用户事件或 OS 级别的事件。  
*   在单个测试会话中管理多个窗口、选项卡和网页。  
*   在特定计算机上运行多个 Microsoft Edge 会话。  
    
以下部分介绍了如何开始使用 Microsoft Edge \ (Chromium \ ) 的 WebDriver。  

## 安装 Microsoft Edge (Chromium)   

确保安装 [Microsoft Edge (Chromium) ][MicrosoftEdge]。  若要确认已安装 Microsoft Edge \ (Chromium \ ) 已安装，请导航到版本 `edge://settings/help` 75 或更高版本，并验证版本号是版本还是更高版本。  

## 下载 Microsoft Edge 驱动程序  

若要开始自动测试，请使用以下步骤确保所安装的 WebDriver 版本与你的浏览器版本相匹配。  

1.  导航到 `edge://settings/help` 以获取 Microsoft Edge 的版本。  
    
    :::image type="complex" source="../media/webdriver-chromium/edge-version.png" alt-text="2020年1月14日的 Microsoft Edge 未设备的版本号" lightbox="../media/webdriver-chromium/edge-version.png":::
       2020年1月14日的 Microsoft Edge 未设备的版本号  
    :::image-end:::  
    
1.  导航到 [Microsoft Edge 驱动程序下载][MicrosoftDeveloperEdgeToolsWebdriverDownloads] 页面，并下载与 microsoft edge 版本号相匹配的驱动程序。  
    
    :::image type="complex" source="../media/webdriver-chromium/edge-driver-install.png" alt-text="Microsoft Edge 驱动程序页面的 下载 部分"::: lightbox="../media/webdriver-chromium/edge-driver-install.png":::
       [Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]页面的 "下载" 部分  
    :::image-end:::  
    
    > [!NOTE] 
    > 有关使用 Microsoft Edge \ (EdgeHTML \ ) 的测试自动化的详细信息，请参阅 [Microsoft WebDriver For Microsoft edge (EdgeHTML) ][Webdriver]。  
    
## 选择 WebDriver 语言绑定  

您必须下载的最后一个组件是特定于语言的客户端驱动程序，用于转换代码 \ (Python、Java、C \ #、Ruby、JavaScript \ ) 插入 microsoft Edge 驱动程序在 Microsoft Edge \ (Chromium \ ) 中运行的命令。  

[下载你选择的 WebDriver 语言绑定][SeleniumDownloads]。  Microsoft Edge 团队建议 [Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05] 或更高版本，因为它支持 Microsoft edge \ (Chromium \ ) 。  但是，你可能会在所有较早版本的 Selenium 中控制 Microsoft Edge \ (Chromium \ ) ，包括当前稳定 Selenium 3 版本。  

> [!IMPORTANT]
> 如果你以前以前自动自动化或测试了 Microsoft Edge \ (Chromium \ ) 使用 `ChromeDriver` 和 `ChromeOptions` 类，则你的 WebDriver 代码不会在 Microsoft edge 版本80或更高版本上运行。  若要解决此问题，请更新你的测试以使用 `EdgeOptions` 该类并安装 [Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]。  

### 使用 Selenium 3  

如果你已使用 [Selenium 3][|::ref1::|]，可能会有现有的浏览器测试并希望在不更改你的 Selenium 版本的情况下添加 Microsoft Edge \ () Chromium 的覆盖范围。  若要使用 [Selenium 3][|::ref2::|] 编写 microsoft edge \ (EdgeHTML \ ) 和 microsoft edge \ (Chromium \ ) 中的自动测试，请安装 [Microsoft Edge 程序包 Selenium 工具][GithubMicrosoftEdgeSeleniumTools] 以使用更新的驱动程序。  `EdgeDriver` `EdgeDriverService` 工具中包含的和类与 Selenium 4 中的内置等效项完全兼容。  

使用以下步骤将 [Microsoft Edge 的 Selenium 工具][GithubMicrosoftEdgeSeleniumTools] 和 [Selenium 3][|::ref3::|] 添加到你的项目。

#### [C#](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

使用[NUGET CLI][NugetCLI]或[Visual Studio][VisualStudio]将[SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools]和[Selenium WebDriver][NugetPackagesSeleniumWebdriver31410]程序包添加到 .net 项目。  

#### [Python](#tab/python/)  

<a id="selenium-tools-install"></a>  

使用 [pip][PythonPip] 安装 [msedge-selenium-tools][PythonSeleniumTools] 和 [selenium][PythonSelenium] 程序包。  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [JavaScript](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

使用 [npm][JavaScript|::ref4::|] 安装 [edge selenium-tools][JavaScriptSeleniumTools] 和 [selenium webdriver][JavaScriptSelenium] 程序包。  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## 使用 Microsoft Edge (Chromium) 与 WebDriver

你可以使用 Selenium 3 或4运行以下示例。  若要与 Selenium 3 配合使用，必须安装 [适用于 Microsoft Edge 程序包的 Selenium 工具][GithubMicrosoftEdgeSeleniumTools] 。  

### 基本用法  

若要与 Microsoft Edge \ (EdgeHTML \ ) 一起使用，请创建该类的默认实例 `EdgeDriver` 。  

#### [C#](#tab/c-sharp/)  

<a id="basic-usage-code"></a>  

```csharp
var driver = new EdgeDriver();
```  

#### [Python](#tab/python/)  

<a id="basic-usage-code"></a>  

```python
driver = Edge()
```  

#### [JavaScript](#tab/javascript/)  

<a id="basic-usage-code"></a>  

```javascript
let driver = edge.Driver.createSession();
```  

* * *  

### 推动 Microsoft Edge (Chromium)   

若要与 Microsoft Edge \ (Chromium \ ) ，请创建一个新 `EdgeDriver` 类并将其传递给该 `EdgeOptions` `UseChromium` 属性设置为的对象 `true` 。  

#### [C#](#tab/c-sharp/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [Python](#tab/python/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

#### [JavaScript](#tab/javascript/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> 如果 IT 管理员已将 [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] 策略设置为 `2` ， [microsoft edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver] 将无法推动 [Microsoft edge (Chromium) ][MicrosoftEdge] ，因为驱动程序使用 [Microsoft edge DevTools][DevToolsMain]。  确保 [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] 策略已设置为 `0` 或自动运行 `1` [Microsoft Edge (Chromium) ][MicrosoftEdge]。  

### 选择特定浏览器二进制文件 ("仅 Chromium")   

你可以使用 `EdgeOptions` 包含 Microsoft Edge \ (Chromium \ ) 的特定二进制文件的类。  例如，你可以使用 [Microsoft edge 预览频道][MicrosoftedgeinsiderDownload] （如 Microsoft edge Beta）运行测试。  

#### [C#](#tab/c-sharp/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [Python](#tab/python/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

#### [JavaScript](#tab/javascript/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### 自定义 Microsoft Edge 驱动程序服务  

#### [C#](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

`EdgeDriver`使用类创建类实例时 `EdgeOptions` ，它会 `EdgeDriverService` 为 microsoft Edge \ (EdgeHTML \ ) 或 microsoft Edge \ (Chromium \ ) 创建并启动相应的类。  

如果要创建 `EdgeDriverService` ，请创建一个为 Microsoft Edge 配置的 (Chromium \ ) 使用 `CreateChromiumService()` 方法。  你可能会发现它对于其他自定义非常有用，例如，在以下代码中启用详细日志输出。  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
>在 `EdgeOptions` 传递到实例时无需提供对象 `EdgeDriverService` `EdgeDriver` 。 `EdgeDriver`该类使用 Microsoft edge \ (EdgeHTML \ ) 或 Microsoft edge \ (Chromium \ ) 的默认选项，具体取决于你提供的服务。  
> 但是，如果你希望同时提供这两个 `EdgeDriverService` `EdgeOptions` 类和类，请确保两个版本的 Microsoft Edge 都配置了这两个类。  例如，不能在类中使用默认的 Microsoft Edge \ (EdgeHTML \ ) `EdgeDriverService` class 和 Chromium 属性 `EdgeOptions` 。  `EdgeDriver`该类将引发错误以防止使用不同版本。  

#### [Python](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

使用 Python 时， `Edge` 对象将创建并管理 `EdgeService` 。  若要配置 `EdgeService` ，请 `Edge` 按以下代码向对象传递其他参数。  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [JavaScript](#tab/javascript/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

使用 JavaScript 时，使用类创建和配置 `Service` `ServiceBuilder` 。  或者，你可以将 `Service` 对象传递给该 `Driver` 对象，该对象启动 \ (并停止为你 ) 服务。  
若要配置 `Service` ，请在使用方法之前在类中运行其他方法 `ServiceBuilder` `build()` 。  然后 `service` 在方法中传递作为参数 `Driver.createSession()` 。  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### 使用 Chromium-Specific 选项  

如果将该 `UseChromium` 属性设置为 `true` ，则可以使用 `EdgeOptions` 类访问与自动化其他 Chromium 浏览器相同的 [Chromium 特定属性和方法][SeleniumWebDriverChromeoptionsClass] 。  

#### [C#](#tab/c-sharp/)  

<a id="using-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [Python](#tab/python/)  

<a id="using-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [JavaScript](#tab/javascript/)  

<a id="using-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```

* * *  

> [!NOTE]
> 如果 `UseChromium` 属性设置为 `true` ，则无法使用 Microsoft Edge \ (EdgeHTML \ ) 的属性和方法。  

## 其他 WebDriver 安装选项  

### Chocolatey  

如果你将 [Chocolatey][Chocolatey] 用作程序包管理器，请通过运行以下命令来安装 Microsoft Edge 驱动程序。  

```console
choco install selenium-chromium-edge-driver
```  

有关详细信息，请参阅 [Chocolatey 上的 Selenium Chromium Edge 驱动程序][ChocolateyPackagesSeleniumChromiumEdgeDriver]。  

### Docker  

如果使用 [Docker][DockerHub]，请通过运行以下命令，将预配置的映像与 microsoft edge \ (Chromium \ ) 和 [Microsoft edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver] 一起下载。  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

有关详细信息，请参阅 [Docker 中心上的容器][DockerHubMsedgedriver]。  

## 与 Microsoft Edge 开发人员工具团队联系  

Microsoft Edge 团队渴望听到有关使用 WebDriver、Selenium 和 Microsoft Edge 的反馈。  若要让团队知道您的想法，请选择 Microsoft Edge DevTools 中的 " **发送反馈** " 图标或发送 tweet [@EdgeDevTools][TwitterTweetEdgeDevTools]。  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的 发送反馈 图标" ::: lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools 中的 " **发送反馈** " 图标  
:::image-end:::  

<!-- links -->  

[DevToolsMain]: ../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"
[Webdriver]: ../webdriver.md "WebDriver (EdgeHTML) |Microsoft 文档"  

[DeployedgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability-Microsoft Edge-政策 |Microsoft 文档"  

[Chocolatey]: https://chocolatey.org "Chocolatey |Chocolatey 软件"  
[ChocolateyPackagesSeleniumChromiumEdgeDriver]: https://chocolatey.org/packages/selenium-chromium-edge-driver "Selenium Chromium Edge 驱动程序 |Chocolatey"  

[DockerHub]: https://hub.docker.com "Docker 中心"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker 中心"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-工具 |GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/selenium |GitHub"  

[JavaScriptnpm]: https://www.npmjs.com/ "npm"  
[JavaScriptSeleniumTools]: https://www.npmjs.com/package/@microsoft/edge-selenium-tools "@microsoft/edge-selenium-tools |npm"  
[JavaScriptSelenium]: https://www.npmjs.com/package/selenium-webdriver "selenium-webdriver |npm"  

[MicrosoftDeveloperEdgeToolsWebdriver]: https://developer.microsoft.com/microsoft-edge/tools/webdriver "WebDriver |Microsoft 开发人员"  
[MicrosoftDeveloperEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver/#downloads "下载-WebDriver |Microsoft 开发人员"  

[MicrosoftEdge]: https://www.microsoft.com/edge "下载新版 Microsoft Edge 浏览器"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[NugetCLI]:https://www.nuget.org/packages/NuGet.CommandLine/ "NuGet。命令行 |NuGet 库"  
[NugetPackagesMicrosoftEdgeSeleniumtools]: https://www.nuget.org/packages/Microsoft.Edge.SeleniumTools "SeleniumTools |NuGet 库"  
[NugetPackagesSeleniumWebdriver31410]: https://www.nuget.org/packages/Selenium.WebDriver/3.141.0 "Selenium WebDriver 3.141.0 |NuGet 库"  
[NugetPackagesSeleniumWebdriver400alpha05]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha05 "Selenium WebDriver 4.0.0-alpha05 |NuGet 库"  

[PythonPip]: https://pypi.org/project/pip/ "pip |PyPI"  
[PythonSeleniumTools]: https://pypi.org/project/msedge-selenium-tools/ "msedge-selenium-tools |PyPI"  
[PythonSelenium]: https://pypi.org/project/selenium/ "selenium |PyPI"

[SeleniumHQ]: https://www.selenium.dev "SeleniumHQ"  
[SeleniumDownloads]: https://selenium.dev/downloads "下载 |Selenium"  
[SeleniumWebDriverChromeoptionsClass]: https://www.selenium.dev/selenium/docs/api/dotnet/?topic=html/T_OpenQA_Selenium_Chrome_ChromeOptions.htm "ChromeOptions 类-WebDriver |Selenium"  

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |发布 tweet"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |W3C"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无外设浏览器 |科"  
