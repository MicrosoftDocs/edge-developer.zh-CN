---
description: 了解如何在 Microsoft Edge 中测试网站或应用，或者使用 WebDriver 自动执行浏览器。
title: WebDriver (Chromium)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge， Web 开发， html， css， javascript， 开发人员， webdriver， selenium， 测试， 工具， 自动化， 测试
ms.openlocfilehash: 5e881eec59c966fd4fa6d35118032a3a51e7b9e5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231125"
---
# 使用 WebDriver (Chromium) 测试自动化概述  

利用 WebDriver，你可以\ (开发人员\) 创建模拟用户交互的自动测试。  由于以下原因，WebDriver 测试和模拟不同于 JavaScript 单元测试。  

*   访问在浏览器中运行的 JavaScript 不可用的功能和信息。  
*   更精确地模拟用户事件或操作系统级事件。  
*   在单个测试会话中管理多个窗口、选项卡和网页。  
*   在特定的计算机上运行 Microsoft Edge 的多个会话。  
    
以下部分介绍如何开始使用适用于 Microsoft Edge 的 WebDriver \ (Chromium\) 。  

## 安装 Microsoft Edge (Chromium)   

确保安装[Microsoft Edge (Chromium) 。 ][MicrosoftEdge]  若要确认已安装 Microsoft Edge \ (Chromium\) ，请导航到并验证版本号是版本 `edge://settings/help` 75 或更高版本。  

## 下载 Microsoft Edge 驱动程序  

若要开始自动执行测试，请使用以下步骤来确保安装的 WebDriver 版本与浏览器版本匹配。  

1.  导航 `edge://settings/help` 到获取 Microsoft Edge 的版本。  
    
    :::image type="complex" source="./media/edge-version.png" alt-text="2020 年 1 月 14 日 Microsoft Edge Canary 的生成号":::
       2020 年 1 月 14 日 Microsoft Edge Canary 的生成号
    :::image-end:::  
    
1.  导航到 [Microsoft Edge 驱动程序下载][MicrosoftDeveloperEdgeToolsWebdriverDownloads] 页面，并下载与 Microsoft Edge 的版本号匹配的驱动程序。  
    
    :::image type="complex" source="./media/edge-driver-install.png" alt-text="Microsoft Edge 驱动程序页的"下载"部分":::
       Microsoft Edge 驱动程序页的"下载 ["][MicrosoftDeveloperEdgeToolsWebdriver] 部分
    :::image-end:::  
    
    <!--  
    > [!NOTE] 
    > For more information about test automation using Microsoft Edge (EdgeHTML), see [Microsoft WebDriver for Microsoft Edge (EdgeHTML)][Webdriver].  
    -->  

## 选择 WebDriver 语言绑定  

必须下载的最后一个组件是特定语言的客户端驱动程序，用于将代码 \ (Python、Java、C\#、Ruby、JavaScript\) 转换为 Microsoft Edge \ (Chromium\) 中运行的命令。  

[下载你选择的 WebDriver 语言绑定][SeleniumDownloads]。  Microsoft Edge 团队建议使用 [Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05] 或更高版本，因为它支持 Microsoft Edge \ (Chromium\) 。  但是，你可以控制所有较旧版本的 Selenium 中的 Microsoft Edge \ (Chromium\) ，包括当前稳定的 Selenium 3 版本。  

> [!IMPORTANT]
> 如果之前使用和类自动执行或测试 Microsoft Edge \ (Chromium\) ，则 WebDriver 代码不会在 Microsoft Edge 版本 80 或更高版本中 `ChromeDriver` `ChromeOptions` 运行。  若要解决此问题，请更新测试以使用 `EdgeOptions` 该类并安装 Microsoft [Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]。  

### 使用 Selenium 3  

如果你已使用 [Selenium 3，][|::ref1::|]你可能已有浏览器测试，并且想要添加 Microsoft Edge \ (Chromium\) 的覆盖范围，而无需更改 Selenium 版本。  若要使用 [Selenium 3][|::ref2::|] 为 Microsoft Edge \ (EdgeHTML\) 和 Microsoft Edge \ (Chromium\) 编写自动测试，请安装适用于 Microsoft Edge 的 [Selenium 工具][GithubMicrosoftEdgeSeleniumTools] 程序包以使用更新的驱动程序。  工具 `EdgeDriver` `EdgeDriverService` 中包含的类与 Selenium 4 中的内置等效项完全兼容。  

使用以下步骤将适用于 Microsoft Edge 和[Selenium 3][|::ref3::|]的[Selenium 工具][GithubMicrosoftEdgeSeleniumTools]添加到项目中。

#### [C#](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

使用[NuGet CLI][NugetCLI]或 Visual Studio 将[Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools]和[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] [包添加到 .NET Visual Studio。][VisualStudio]  

#### [Python](#tab/python/)  

<a id="selenium-tools-install"></a>  

使用 [管道][PythonPip] 安装 [msedge-selenium-tools][PythonSeleniumTools] 和 [selenium][PythonSelenium] 程序包。  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [JavaScript](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

使用 [npm][JavaScript|::ref4::|] 安装 [edge-selenium-tools][JavaScriptSeleniumTools] 和 [selenium-webdriver][JavaScriptSelenium] 程序包。  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## 将 Microsoft Edge (Chromium) WebDriver

可以使用 Selenium 3 或 4 运行以下示例。  若要与 Selenium 3 一起使用，必须安装适用于 Microsoft Edge 的 [Selenium][GithubMicrosoftEdgeSeleniumTools] 工具包。  

### 基本用法  

若要与 Microsoft Edge \ (EdgeHTML\) 一起使用，请创建类的默认 `EdgeDriver` 实例。  

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

### 驱动 Microsoft Edge (Chromium)   

若要与 Microsoft Edge \ (Chromium\) 一起使用，请创建一个新类，并传递属性设置为 `EdgeDriver` `EdgeOptions` `UseChromium` `true` 的对象。  

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
> 如果你的 IT 管理员将[DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability]策略设置为 ，Microsoft Edge 驱动程序无法驱动 `2` Microsoft Edge ([Chromium) ][MicrosoftEdge]因为驱动程序使用[Microsoft Edge DevTools。][DevToolsMain] [][MicrosoftDeveloperEdgeToolsWebdriver]  确保[将 DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability]策略设置为或自动执行 Microsoft Edge (`0` `1` [Chromium) 。 ][MicrosoftEdge]  

### 选择特定浏览器二进制文件 (仅 Chromium)   

你可以将该类 `EdgeOptions` 与 Microsoft Edge \ (Chromium\) 。  例如，可以使用 [Microsoft Edge][MicrosoftedgeinsiderDownload] 预览频道（如 Microsoft Edge Beta）运行测试。  

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

使用类创建类实例时，它会为 `EdgeDriver` `EdgeOptions` Microsoft Edge `EdgeDriverService` \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 创建和启动相应的类。  

如果要创建一个 ，请创建一个为 `EdgeDriverService` Microsoft Edge \ (Chromium\) 方法 `CreateChromiumService()` 。  您可能会发现它可用于其他自定义项，如在下面的代码中启用详细日志输出。  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
>在传递给实例时，不需要 `EdgeOptions` `EdgeDriverService` 提供 `EdgeDriver` 对象。 该类使用 `EdgeDriver` Microsoft Edge \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 的默认选项，具体取决于你提供的服务。  
> 但是，如果要同时提供这两个类和类，请确保为相同版本的 Microsoft Edge 配置这两 `EdgeDriverService` `EdgeOptions` 者。  例如，在该类中不能使用默认的 Microsoft Edge \ (EdgeHTML\) 类和 `EdgeDriverService` Chromium `EdgeOptions` 属性。  该类 `EdgeDriver` 会引发错误，以防止使用不同的版本。  

#### [Python](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

使用 Python 时 `Edge` ，对象将创建和管理 `EdgeService` 。  若要配置 `EdgeService` ，请向对象传递 `Edge` 其他参数，如以下代码所示。  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [JavaScript](#tab/javascript/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

使用 JavaScript 时，使用类 `Service` 创建和 `ServiceBuilder` 配置。  或者，你可以将对象传递给该对象，该对象将启动 `Service` `Driver` \ (并停止\) 服务。  
若要配置 `Service` ，请运行类中的其他 `ServiceBuilder` 方法，然后再使用 `build()` 该方法。  然后作为 `service` 参数在方法中 `Driver.createSession()` 传递。  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### 使用Chromium-Specific选项  

如果将该属性设置为 ，可以使用类访问与自动执行其他 Chromium 浏览器时相同的 `UseChromium` `true` 特定于 `EdgeOptions` [Chromium][SeleniumWebDriverChromeoptionsClass] 的属性和方法。  

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
> 如果该属性设置为，则不能对 `UseChromium` Microsoft Edge `true` \ (EdgeHTML\) 。  

## 其他 WebDriver 安装选项  

### 百年  

如果你使用 [Microsofty][Chocolatey] 作为程序包管理器，请运行以下命令来安装 Microsoft Edge 驱动程序。  

```console
choco install selenium-chromium-edge-driver
```  

有关详细信息，请参阅 [Selenium Chromium Edge Driver on 一角][ChocolateyPackagesSeleniumChromiumEdgeDriver]。  

### Docker  

如果使用 [Docker，][DockerHub]请通过运行以下命令，下载预配置映像和 Microsoft Edge \ (Chromium\) 和预安装的 [Microsoft Edge][MicrosoftDeveloperEdgeToolsWebdriver] 驱动程序。  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

有关详细信息，请参阅 [Docker Hub 上的容器][DockerHubMsedgedriver]。  

## 联系 Microsoft Edge DevTools 团队  

Microsoft Edge 团队希望倾听你有关使用 WebDriver、Selenium 和 Microsoft Edge 的反馈。  若要让团队了解你的想法，请选择 Microsoft **** Edge DevTools 中的"发送反馈"图标或发送推文[@EdgeDevTools。][TwitterTweetEdgeDevTools]  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   Microsoft **Edge** DevTools 中的"发送反馈"图标  
:::image-end:::  

<!-- links -->  

[DevToolsMain]: ../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"
[Webdriver]: ../webdriver/index.md "WebDriver (EdgeHTML) |Microsoft Docs"  

[DeployedgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability - Microsoft Edge - 策略 |Microsoft Docs"  

[Chocolatey]: https://chocolatey.org "百年 |百万软件"  
[ChocolateyPackagesSeleniumChromiumEdgeDriver]: https://chocolatey.org/packages/selenium-chromium-edge-driver "Selenium Chromium Edge 驱动程序 |百年"  

[DockerHub]: https://hub.docker.com "Docker Hub"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker 中心"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-tools |GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/selenium |GitHub"  

[JavaScriptnpm]: https://www.npmjs.com/ "npm"  
[JavaScriptSeleniumTools]: https://www.npmjs.com/package/@microsoft/edge-selenium-tools "@microsoft/edge-selenium-tools |npm"  
[JavaScriptSelenium]: https://www.npmjs.com/package/selenium-webdriver "selenium-webdriver |npm"  

[MicrosoftDeveloperEdgeToolsWebdriver]: https://developer.microsoft.com/microsoft-edge/tools/webdriver "WebDriver |Microsoft 开发人员"  
[MicrosoftDeveloperEdgeToolsWebdriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver/#downloads "下载 - WebDriver |Microsoft 开发人员"  

[MicrosoftEdge]: https://www.microsoft.com/edge "下载新版 Microsoft Edge 浏览器"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[NugetCLI]:https://www.nuget.org/packages/NuGet.CommandLine/ "NuGet.CommandLine |NuGet 库"  
[NugetPackagesMicrosoftEdgeSeleniumtools]: https://www.nuget.org/packages/Microsoft.Edge.SeleniumTools "Microsoft.Edge.SeleniumTools |NuGet 库"  
[NugetPackagesSeleniumWebdriver31410]: https://www.nuget.org/packages/Selenium.WebDriver/3.141.0 "Selenium.WebDriver 3.141.0 |NuGet 库"  
[NugetPackagesSeleniumWebdriver400alpha05]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha05 "Selenium.WebDriver 4.0.0-alpha05 |NuGet 库"  

[PythonPip]: https://pypi.org/project/pip/ "pip |PyPI"  
[PythonSeleniumTools]: https://pypi.org/project/msedge-selenium-tools/ "msedge-selenium-tools |PyPI"  
[PythonSelenium]: https://pypi.org/project/selenium/ "selenium |PyPI"

[SeleniumHQ]: https://www.selenium.dev "SeleniumHQ"  
[SeleniumDownloads]: https://selenium.dev/downloads "下载 |Selenium"  
[SeleniumWebDriverChromeoptionsClass]: https://www.selenium.dev/selenium/docs/api/dotnet/?topic=html/T_OpenQA_Selenium_Chrome_ChromeOptions.htm "ChromeOptions 类 - WebDriver |Selenium"  

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |发布推文"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |W3C"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无头浏览器 |Wikipedia"  
