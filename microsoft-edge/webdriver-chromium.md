---
description: 了解如何在 Microsoft Edge 中测试你的网站或应用，或通过 WebDriver 自动处理浏览器。
title: WebDriver (Chromium)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/20/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge，web 开发，html，css，javascript，开发人员，webdriver，selenium，测试，工具，自动化，测试
ms.openlocfilehash: 1ce30ec13a4def2da67cffc80b0cc7c92845f22b
ms.sourcegitcommit: a78e285e8d0d9c570169b4e86bc4a2c2bb17871d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "10668184"
---
# WebDriver (Chromium)  

W3C [WebDriver][W3CWebdriver] API 是一个平台和语言中立的界面和线路协议，允许程序或脚本控制 web 浏览器的行为，如 Microsoft Edge \ （Chromium \）。  

WebDriver 使开发人员能够创建模拟用户交互的自动测试。  WebDriver 测试和模拟不同于 JavaScript 单元测试，因为 WebDriver 有权访问在浏览器中运行的 JavaScript 不需要的功能和信息，WebDrive 能够更准确地模拟用户事件或操作系统级别的事件。  WebDriver 可以在单个测试会话中跨多个窗口、选项卡和网页管理测试。  

下面介绍如何开始使用 Microsoft Edge \ （Chromium \）的 WebDriver。  

## 安装 Microsoft Edge （Chromium）  

如果尚未安装，请[安装 Microsoft Edge （Chromium）][MicrosoftEdge]。  如果您在您的计算机上使用预安装的 Microsoft Edge 版本，请验证您有 Microsoft Edge \ （Chromium \），而不是 Microsoft Edge \ （EdgeHTML \）。  快速检查的方法是 `edge://settings/help` 在浏览器中加载并确认版本号为 v75 或更高版本。  

## 下载 Microsoft Edge 驱动程序  

WebDriver 需要特定于浏览器的驱动程序才能自动处理每个浏览器。  对于 Microsoft Edge \ （Chromium \），WebDriver 需要合适的[Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]，以便你想要测试或自动化的 microsoft edge 内部版本。  

若要查找正确的版本号，请使用以下步骤。  

1.  启动 Microsoft Edge 
1.  查看 Microsoft Edge \ （Chromium \）版本。  
    *   导航到 `edge://settings/help`  
    *   选择 `...`  >  **Settings**  >   **有关 Microsoft Edge**的设置  
1.  验证你的版本的 WebDriver 的正确版本是否可确保，以便正确运行。  

:::image type="complex" source="./media/webdriver-chromium/edge-version.png" alt-text="2020年1月14日的 Microsoft Edge 未设备的版本号":::
   图 1.  2020年1月14日的 Microsoft Edge 未设备的版本号  
:::image-end:::  

现在，[下载 Microsoft Edge 驱动程序的匹配版本][MicrosoftDeveloperEdgeToolsWebdriverDownloads]。  

:::image type="complex" source="./media/webdriver-chromium/edge-driver-install.png" alt-text="Microsoft Edge 驱动程序页面的 "下载" 部分":::
   图 2.  [Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriverDownloads]页面的 "下载" 部分  
:::image-end:::  

> [!NOTE]
> Microsoft Edge \ （EdgeHTML \）不能与[Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriverDownloads]配合使用。  若要自动执行 Microsoft Edge \ （EdgeHTML \），必须下载[Microsoft WebDriver For Microsoft edge \ （EdgeHTML \）][Webdriver]。  

## 选择 WebDriver 语言绑定  

您必须下载的最后一个组件是特定于语言的客户端驱动程序。  语言绑定将在 Python、Java、C #、Ruby 和 JavaScript 中编写的代码转换为命令，在[上一节中下载](#download-microsoft-edge-driver)的 Microsoft Edge 驱动程序能够在 microsoft edge \ （Chromium \）中运行。  

[下载你选择的 WebDriver 语言绑定][SeleniumDownloads]。  Microsoft Edge 团队强烈建议[Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05]或更高版本，因为它具有对 Microsoft Edge \ （Chromium \）的内置支持。  但是，你可以在所有较早版本的 Selenium 中驱动 Microsoft Edge \ （Chromium \），包括当前稳定 Selenium 3 版本。  

> [!IMPORTANT]
> 如果以前使用 and 自动执行或测试 Microsoft Edge \ （Chromium \） `ChromeDriver` ，则 `ChromeOptions` 你的 WebDriver 代码不会成功运行于 microsoft edge v80 或更高版本。  这是一种重大更改，Microsoft Edge \ （Chromium \）不再接受这些命令。  必须更改测试才能使用 `EdgeOptions` 类和[Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]。  

### 使用 Selenium 3  

[Selenium 3][|::ref1::|]是最新稳定的 Selenium 版本。  默认情况下，Selenium 3 驱动旧的 Microsoft Edge \ （EdgeHTML \），并且没有 Microsoft Edge 的内置支持 \ （Chromium \）。  若要将 Selenium 3 与 Microsoft Edge \ （Chromium \）配合使用，请安装[Microsoft edge 程序包的 Selenium 工具][GithubMicrosoftEdgeSeleniumTools]。  适用于 Microsoft Edge 的 Selenium 工具将 Selenium 3 与更新的驱动程序一起扩展，以帮助你为 Microsoft Edge \ （EdgeHTML \）和新的 Microsoft Edge \ （Chromium）浏览器编写自动测试。  

适用于 Microsoft Edge 的 Selenium 工具是一种解决方案，适用于更喜欢在 Selenium 3 和具有现有浏览器测试的开发人员的开发人员，并且希望在不更改 Selenium 版本的情况下为新的 Microsoft Edge \ （Chromium）浏览器添加覆盖范围。  `EdgeDriver` `EdgeDriverService` 工具中包含的和类完全兼容 Selenium 中的内置等效项，并默认运行 Microsoft Edge \ （EdgeHTML \），以便可以将工具用作 Selenium 中现有 Edge 类的无缝放置替换。  

[安装适用于 Microsoft edge 的 Selenium 工具][GithubMicrosoftEdgeSeleniumTools]，开始在 Selenium 3 项目中使用 microsoft edge \ （Chromium \）。  

## 将 Microsoft Edge （Chromium）与 WebDriver 结合使用

以下示例是使用 Selenium 3 或4的可运行示例。  若要与 Selenium 3 配合使用，必须安装[适用于 Microsoft Edge 的 Selenium 工具][GithubMicrosoftEdgeSeleniumTools]。  

### 基本用法  

若要与 Microsoft Edge \ （EdgeHTML \）一起使用，只需创建该类的默认实例 `EdgeDriver` 。

#### [C#](#tab/c-sharp/)  

<a id="basic-usage-code" />  

```csharp
var driver = new EdgeDriver();
```  

#### [Python](#tab/python/)  

<a id="basic-usage-code" />  

```python
driver = Edge()
```  

#### [JavaScript](#tab/javascript/)  

<a id="basic-usage-code" />  

```javascript
let driver = edge.Driver.createSession();
```  

* * *  

### 推动 Microsoft Edge （Chromium）  

若要改为与 Microsoft Edge \ （Chromium \）一起使用，请创建一个新 `EdgeDriver` 类并将其传递给该 `EdgeOptions` `UseChromium` 属性设置为的对象 `true` 。  

#### [C#](#tab/c-sharp/)  

<a id="driving-microsoft-edge-chromium-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [Python](#tab/python/)  

<a id="driving-microsoft-edge-chromium-code" />  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

#### [JavaScript](#tab/javascript/)  

<a id="driving-microsoft-edge-chromium-code" />  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

### 选择特定浏览器二进制文件（仅限 Chromium）  

使用 `EdgeOptions` 类选择特定的二进制文件。  它对于测试[Microsoft edge 预览频道][MicrosoftedgeinsiderDownload]（如 Microsoft edge Beta）很有用。  

#### [C#](#tab/c-sharp/)  

<a id="choosing-specific-browser-binaries-chrome-only-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [Python](#tab/python/)  

<a id="choosing-specific-browser-binaries-chrome-only-code" />  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

#### [JavaScript](#tab/javascript/)  

<a id="choosing-specific-browser-binaries-chrome-only-code" />  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### 自定义 Microsoft Edge 驱动程序服务  

#### [C#](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code" />  

`EdgeDriver`使用类创建类实例时 `EdgeOptions` ，它会自动 `EdgeDriverService` 为 microsoft Edge \ （EdgeHTML \）或 microsoft Edge \ （Chromium \）创建和启动相应的类。  

如果你想要创建 `EdgeDriverService` ，请使用方法为 Microsoft Edge \ （Chromium \）配置一个 `CreateChromiumService()` 。  你可能会发现它对于其他自定义非常有用，例如，在以下代码中启用详细日志输出。  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE]
> 在 `EdgeOptions` 将类实例传递给时，不需要提供对象 `EdgeDriver` `EdgeDriverService` 。  `EdgeDriver`对于 Microsoft edge \ （EdgeHTML \）或 Microsoft edge \ （Chromium \），该类使用默认选项，具体取决于你提供的服务类型。  
> 
> 但是，如果你希望同时提供 a `EdgeDriverService` 和 `EdgeOptions` 类，则必须确保两个版本的 Microsoft Edge 都配置了这两个类。  例如，不能在类中使用默认的 Microsoft Edge \ （EdgeHTML \） `EdgeDriverService` 类和 Chromium 属性 `EdgeOptions` 。  `EdgeDriver`该类将引发错误以防止使用不同版本。  

#### [Python](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code" />  

使用 Python 时， `Edge` 对象将创建并管理 `EdgeService` 。  若要配置 `EdgeService` ，请将其他参数传递给该 `Edge` 对象：

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [JavaScript](#tab/javascript/)  

<a id="customizing-microsoft-edge-driver-services-code" />  

使用 JavaScript 时，使用类创建和配置 `Service` `ServiceBuilder` 。  你可以选择将 `Service` 对象传递给 `Driver` 启动和停止服务的对象。  

若要配置 `Service` ，请在 `ServiceBuilder` 使用该方法之前在类中运行其他方法 `build()` ，然后 `service` 在该方法中传递 as 参数 `Driver.createSession()` 。  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### 使用 Chromium 特定选项  

`EdgeOptions`将类与设置的属性结合使用，可 `UseChromium` `true` 让你访问 Selenium 中的[ChromeOptions][SeleniumWebDriverChromeoptionsClass]类中可用的所有相同方法和属性。  例如，与其他 Chromium 浏览器一样，在 `EdgeOptions.AddArguments()` 以下代码中使用方法在无[外设模式][WikiHeadlessBrowser]下运行 Microsoft Edge \ （Chromium \）。  

#### [C#](#tab/c-sharp/)  

<a id="using-chromium-specific-options-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [Python](#tab/python/)  

<a id="using-chromium-specific-options-code" />  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [JavaScript](#tab/javascript/)  

<a id="using-chromium-specific-options-code" />  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```
* * *  

> [!NOTE]
> [Chromium 特定的属性和方法][SeleniumWebDriverChromeoptionsClass]始终可用，但如果 `UseChromium` 属性未设置为，则不起作用 `true` 。  同样，如果属性设置为，则适用于 Microsoft Edge \ （EdgeHTML \）的现有属性和方法将不起作用 `UseChromium` `true` 。  

## 设置 WebDriver 的其他方法  

### Chocolatey  

如果你使用的是[Chocolatey][Chocolatey]作为程序包管理器，请通过运行以下命令来安装 Microsoft Edge 驱动程序。  

```console
choco install selenium-chromium-edge-driver
```  

有关详细信息，请参阅[Chocolatey 上的 Selenium Chromium Edge 驱动程序][ChocolateyPackagesSeleniumChromiumEdgeDriver]。  

### Docker  

如果您使用的是[Docker][DockerHub]，请通过运行以下命令，下载已安装 microsoft edge \ （Chromium \）和[Microsoft edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]的预配置图像。  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

有关详细信息，请参阅[Docker 中心上的容器][DockerHubMsedgedriver]。  

## 与 Microsoft Edge DevTools 团队取得联系    

Microsoft Edge 团队渴望听到有关使用 WebDriver、Selenium 和 Microsoft Edge 的反馈！  使用 Microsoft Edge DevTools 或 tweet [@EdgeDevTools][TwitterTweetEdgeDevTools]中的**反馈**图标，让团队知道您的想法。  


:::image type="complex" source="./devtools-guide-chromium/media/devtools-feedback.png" alt-text="Microsoft Edge DevTools 中的 "反馈" 图标":::
   Microsoft Edge DevTools 中的 "**反馈**" 图标  
:::image-end:::  

<!-- image links -->  

<!-- links -->  

[Webdriver]: ./webdriver.md "WebDriver （EdgeHTML） |Microsoft 文档"  

[Chocolatey]: https://chocolatey.org "Chocolatey |Chocolatey 软件"  
[ChocolateyPackagesSeleniumChromiumEdgeDriver]: https://chocolatey.org/packages/selenium-chromium-edge-driver "Selenium Chromium Edge 驱动程序 |Chocolatey"  

[DockerHub]: https://hub.docker.com "Docker 中心"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker 中心"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-工具 |GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/selenium |GitHub"  

[MicrosoftDeveloperEdgeToolsWebdriver]: https://developer.microsoft.com/microsoft-edge/tools/webdriver "WebDriver |Microsoft 开发人员"
[MicrosoftDeveloperEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver/#downloads "下载-WebDriver |Microsoft 开发人员"  

[MicrosoftEdge]: https://www.microsoft.com/edge "下载新的 Microsoft Edge 浏览器"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[NugetPackagesMicrosoftEdgeSeleniumtools]: https://www.nuget.org/packages/Microsoft.Edge.SeleniumTools "SeleniumTools |NuGet 库"  
[NugetPackagesSeleniumWebdriver31410]: https://www.nuget.org/packages/Selenium.WebDriver/3.141.0 "Selenium WebDriver 3.141.0 |NuGet 库"  
[NugetPackagesSeleniumWebdriver400alpha05]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha05 "Selenium WebDriver 4.0.0-alpha05 |NuGet 库"  

[SeleniumHQ]: https://www.selenium.dev "SeleniumHQ"  
[SeleniumDownloads]: https://selenium.dev/downloads "下载 |Selenium"  
[SeleniumWebDriverChromeoptionsClass]: https://www.selenium.dev/selenium/docs/api/dotnet/?topic=html/T_OpenQA_Selenium_Chrome_ChromeOptions.htm "ChromeOptions 类-WebDriver |Selenium"  

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |发布 tweet"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无外设浏览器 |科"  
