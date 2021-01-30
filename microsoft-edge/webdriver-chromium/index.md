---
description: 了解如何在 Microsoft Edge 中测试网站或应用，或者使用 WebDriver 自动执行浏览器。
title: 将 WebDriver (Chromium) 用于测试自动化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/29/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge， Web 开发， html， css， javascript， 开发人员， webdriver， selenium， 测试， 工具， 自动化， 测试
ms.openlocfilehash: 295985734d93c5912922be22c0af0c0e33e00a54
ms.sourcegitcommit: 070a60f634908eea0e29e260331f9fc0aa85ee78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2021
ms.locfileid: "11306246"
---
# <span data-ttu-id="00242-104">将 WebDriver (Chromium) 用于测试自动化</span><span class="sxs-lookup"><span data-stu-id="00242-104">Use WebDriver (Chromium) for test automation</span></span>  

<span data-ttu-id="00242-105">WebDriver 允许开发人员创建模拟用户交互的自动化测试。</span><span class="sxs-lookup"><span data-stu-id="00242-105">WebDriver allows developers to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="00242-106">WebDriver 测试和模拟与 JavaScript 单元测试不同，因为 WebDriver：</span><span class="sxs-lookup"><span data-stu-id="00242-106">WebDriver tests and simulations differ from JavaScript unit tests because WebDriver:</span></span>  

*   <span data-ttu-id="00242-107">访问在浏览器中运行的 JavaScript 不可用的功能和信息。</span><span class="sxs-lookup"><span data-stu-id="00242-107">Accesses functionality and information not available to JavaScript running in browsers.</span></span>  
*   <span data-ttu-id="00242-108">更精确地模拟用户事件或操作系统级事件。</span><span class="sxs-lookup"><span data-stu-id="00242-108">Simulates user events or OS-level events more accurately.</span></span>  
*   <span data-ttu-id="00242-109">在单个测试会话中管理多个窗口、选项卡和网页。</span><span class="sxs-lookup"><span data-stu-id="00242-109">Manages multiple windows, tabs, and webpages in a single test session.</span></span>  
*   <span data-ttu-id="00242-110">在特定的计算机上运行 Microsoft Edge 的多个会话。</span><span class="sxs-lookup"><span data-stu-id="00242-110">Runs multiple sessions of Microsoft Edge on a specific machine.</span></span>  
    
<span data-ttu-id="00242-111">以下部分介绍如何开始使用适用于 Microsoft Edge 的 WebDriver \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="00242-111">The following section describes how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  

## <span data-ttu-id="00242-112">安装 Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="00242-112">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="00242-113">确保安装[Microsoft Edge (Chromium) 。 ][MicrosoftEdge]</span><span class="sxs-lookup"><span data-stu-id="00242-113">Ensure you install [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="00242-114">若要确认已安装 Microsoft Edge \ (Chromium\) ，请导航到并验证版本号是版本 `edge://settings/help` 75 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="00242-114">To confirm that you have Microsoft Edge \(Chromium\) installed, navigate to `edge://settings/help`, and verify the version number is Version 75 or later.</span></span>  

## <span data-ttu-id="00242-115">下载 Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="00242-115">Download Microsoft Edge Driver</span></span>  

<span data-ttu-id="00242-116">若要开始自动执行测试，请使用以下步骤来确保安装的 WebDriver 版本与浏览器版本匹配。</span><span class="sxs-lookup"><span data-stu-id="00242-116">To begin automating tests, use the following steps to ensure that the WebDriver version you install matches your browser version.</span></span>  

1.  <span data-ttu-id="00242-117">导航 `edge://settings/help` 到获取 Microsoft Edge 的版本。</span><span class="sxs-lookup"><span data-stu-id="00242-117">Navigate to `edge://settings/help` to get the version of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="./media/edge-version.png" alt-text="2020 年 1 月 14 日 Microsoft Edge Canary 的生成号":::
       <span data-ttu-id="00242-119">2020 年 1 月 14 日 Microsoft Edge Canary 的生成号</span><span class="sxs-lookup"><span data-stu-id="00242-119">The build number for Microsoft Edge Canary on January 14, 2020</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="00242-120">导航到 [Microsoft Edge 驱动程序下载][MicrosoftDeveloperEdgeToolsWebdriverDownloads] 页面，并下载与 Microsoft Edge 的版本号匹配的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="00242-120">Navigate to the [Microsoft Edge Driver downloads][MicrosoftDeveloperEdgeToolsWebdriverDownloads] page and download the driver that matches the version number of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="./media/edge-driver-install.png" alt-text="Microsoft Edge 驱动程序页的"下载"部分":::
       <span data-ttu-id="00242-122">Microsoft Edge 驱动程序页的"下载 ["][MicrosoftDeveloperEdgeToolsWebdriver] 部分</span><span class="sxs-lookup"><span data-stu-id="00242-122">The Downloads section of the [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] page</span></span>
    :::image-end:::  
    
    <!--  
    > [!NOTE] 
    > For more information about test automation using Microsoft Edge (EdgeHTML), see [Microsoft WebDriver for Microsoft Edge (EdgeHTML)][Webdriver].  
    -->  

## <span data-ttu-id="00242-123">选择 WebDriver 语言绑定</span><span class="sxs-lookup"><span data-stu-id="00242-123">Choose a WebDriver language binding</span></span>  

<span data-ttu-id="00242-124">必须下载的最后一个组件是特定语言的客户端驱动程序，用于将代码 \ (Python、Java、C\#、Ruby、JavaScript\) 转换为 Microsoft Edge \ (Chromium\) 中运行的命令。</span><span class="sxs-lookup"><span data-stu-id="00242-124">The last component you must download is a language-specific client driver to translate your code \(Python, Java, C\#, Ruby, JavaScript\) into commands the Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="00242-125">[下载你选择的 WebDriver 语言绑定][SeleniumDownloads]。</span><span class="sxs-lookup"><span data-stu-id="00242-125">[Download the WebDriver language binding of your choice][SeleniumDownloads].</span></span>  <span data-ttu-id="00242-126">Microsoft Edge 团队建议使用 [Selenium 4.00-alpha07][NugetPackagesSeleniumWebdriver400alpha07] 或更高版本，因为它支持 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="00242-126">The Microsoft Edge team recommends [Selenium 4.00-alpha07][NugetPackagesSeleniumWebdriver400alpha07] or later, because it supports Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="00242-127">但是，你可以控制所有较旧版本的 Selenium 中的 Microsoft Edge \ (Chromium\) ，包括当前稳定的 Selenium 3 版本。</span><span class="sxs-lookup"><span data-stu-id="00242-127">However, you may control Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="00242-128">如果之前使用和类自动执行或测试 Microsoft Edge \ (Chromium\) ，则 WebDriver 代码不会在 Microsoft Edge 版本 `ChromeDriver` `ChromeOptions` 80 或更高版本中运行。</span><span class="sxs-lookup"><span data-stu-id="00242-128">If you were previously automating or testing Microsoft Edge \(Chromium\) using `ChromeDriver` and `ChromeOptions` classes, your WebDriver code does not run on Microsoft Edge Version 80 or later.</span></span>  <span data-ttu-id="00242-129">若要解决此问题，请更新测试以使用 `EdgeOptions` 该类并下载 Microsoft [Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="00242-129">To solve this problem, update your tests to use the `EdgeOptions` class and download [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver].</span></span>  

### <span data-ttu-id="00242-130">使用 Selenium 3</span><span class="sxs-lookup"><span data-stu-id="00242-130">Use Selenium 3</span></span>  

<span data-ttu-id="00242-131">如果你已使用 [Selenium 3，][|::ref1::|]你可能已有浏览器测试，并且想要添加 Microsoft Edge \ (Chromium\) 的覆盖范围，而无需更改 Selenium 版本。</span><span class="sxs-lookup"><span data-stu-id="00242-131">If you already use [Selenium 3][|::ref1::|], you may have existing browser tests and want to add coverage for Microsoft Edge \(Chromium\) without changing your version of Selenium.</span></span>  <span data-ttu-id="00242-132">若要使用 [Selenium 3][|::ref2::|] 为 Microsoft Edge \ (EdgeHTML\) 和 Microsoft Edge \ (Chromium\) 编写自动测试，请安装适用于 Microsoft Edge 的 [Selenium 工具][GithubMicrosoftEdgeSeleniumTools] 程序包以使用更新的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="00242-132">To use [Selenium 3][|::ref2::|] to write automated tests for both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package to use the updated driver.</span></span>  <span data-ttu-id="00242-133">工具 `EdgeDriver` `EdgeDriverService` 中包含的类与 Selenium 4 中的内置等效项完全兼容。</span><span class="sxs-lookup"><span data-stu-id="00242-133">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium 4.</span></span>  

<span data-ttu-id="00242-134">使用以下步骤将适用于 Microsoft Edge 和[Selenium 3][|::ref3::|]的[Selenium 工具][GithubMicrosoftEdgeSeleniumTools]添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="00242-134">Use the following steps to add the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] and [Selenium 3][|::ref3::|] to your project.</span></span>  

#### [<span data-ttu-id="00242-135">C#</span><span class="sxs-lookup"><span data-stu-id="00242-135">C#</span></span>](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="00242-136">使用[NuGet CLI][NugetCLI]或 Visual Studio 将[Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools]和[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] [包添加到 .NET Visual Studio。][VisualStudio]</span><span class="sxs-lookup"><span data-stu-id="00242-136">Add the [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] and [Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] packages to your .NET project using the [NuGet CLI][NugetCLI] or [Visual Studio][VisualStudio].</span></span>  

#### [<span data-ttu-id="00242-137">Python</span><span class="sxs-lookup"><span data-stu-id="00242-137">Python</span></span>](#tab/python/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="00242-138">使用 [管道][PythonPip] 安装 [msedge-selenium-tools][PythonSeleniumTools] 和 [selenium][PythonSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="00242-138">Use [pip][PythonPip] to install the [msedge-selenium-tools][PythonSeleniumTools] and [selenium][PythonSelenium] packages.</span></span>  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<span data-ttu-id="00242-139">Java	</span><span class="sxs-lookup"><span data-stu-id="00242-139">Java</span></span>](#tab/java/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="00242-140">如果你Java Maven，请通过向文件添加以下依赖项来添加[msedge-selenium-tools-java：][SonatypeMavenRepositorySearch] `pom.xml`</span><span class="sxs-lookup"><span data-stu-id="00242-140">If your Java project uses Maven, add [msedge-selenium-tools-java][SonatypeMavenRepositorySearch] by coping the following dependency to your `pom.xml` file:</span></span>  

```xml
<dependency>
    <groupId>com.microsoft.edge</groupId>
    <artifactId>msedge-selenium-tools-java</artifactId>
    <version>[3.141.0,)</version>
</dependency>
```  

<span data-ttu-id="00242-141">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page.][GithubMicrosoftEdgeSeleniumToolsReleases]</span><span class="sxs-lookup"><span data-stu-id="00242-141">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].</span></span>  

#### [<span data-ttu-id="00242-142">JavaScript</span><span class="sxs-lookup"><span data-stu-id="00242-142">JavaScript</span></span>](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="00242-143">使用 [npm][JavaScript|::ref4::|] 安装 [edge-selenium-tools][JavaScriptSeleniumTools] 和 [selenium-webdriver][JavaScriptSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="00242-143">Use [npm][JavaScript|::ref4::|] to install the [edge-selenium-tools][JavaScriptSeleniumTools] and [selenium-webdriver][JavaScriptSelenium] packages.</span></span>  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## <span data-ttu-id="00242-144">使用 WebDriver (Microsoft Edge) Chromium</span><span class="sxs-lookup"><span data-stu-id="00242-144">Automate Microsoft Edge (Chromium) with WebDriver</span></span>  

<span data-ttu-id="00242-145">若要使用 WebDriver 自动化浏览器，必须先使用首选的 WebDriver 语言绑定启动 WebDriver 会话。</span><span class="sxs-lookup"><span data-stu-id="00242-145">To automate a browser using WebDriver, you must first start a WebDriver session using your preferred WebDriver language binding.</span></span>  <span data-ttu-id="00242-146">会话是浏览器的单个运行实例，可以使用 WebDriver 命令进行控制。</span><span class="sxs-lookup"><span data-stu-id="00242-146">A session is a single running instance of a browser that can be controlled using WebDriver commands.</span></span>  <span data-ttu-id="00242-147">启动 WebDriver 会话将启动一个新的浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="00242-147">Starting a WebDriver session launches a new browser instance.</span></span>  <span data-ttu-id="00242-148">启动的浏览器将保持打开状态，直到您关闭 WebDriver 会话。</span><span class="sxs-lookup"><span data-stu-id="00242-148">The browser that is launched remains open until you close the WebDriver session.</span></span>  

<span data-ttu-id="00242-149">以下内容将引导你使用 Selenium 启动与 Microsoft Edge \ (Chromium\) 的 WebDriver 会话。</span><span class="sxs-lookup"><span data-stu-id="00242-149">The following content walks you through using Selenium to start a WebDriver session with Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="00242-150">可以使用 Selenium 3 或 4 运行这些示例。</span><span class="sxs-lookup"><span data-stu-id="00242-150">You may run theses examples using either Selenium 3 or 4.</span></span>  <span data-ttu-id="00242-151">若要与 Selenium 3 一起使用，必须安装适用于 Microsoft Edge 的 [Selenium][GithubMicrosoftEdgeSeleniumTools] 工具包。</span><span class="sxs-lookup"><span data-stu-id="00242-151">To use with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package must be installed.</span></span>  

### <span data-ttu-id="00242-152">自动化 Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="00242-152">Automating Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="00242-153">Selenium 使用 `EdgeDriver` 该类管理 Microsoft Edge \ (Chromium\) 会话。</span><span class="sxs-lookup"><span data-stu-id="00242-153">Selenium uses the `EdgeDriver` class to manage a Microsoft Edge \(Chromium\) session.</span></span> <span data-ttu-id="00242-154">若要启动会话并自动执行 Microsoft Edge \ (Chromium\) ，请创建一个新对象，并传递一个属性设置为 `EdgeDriver` `EdgeOptions` `UseChromium` `true` 的对象。</span><span class="sxs-lookup"><span data-stu-id="00242-154">To start a session and automate Microsoft Edge \(Chromium\), create a new `EdgeDriver` object and pass it an `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<span data-ttu-id="00242-155">C#</span><span class="sxs-lookup"><span data-stu-id="00242-155">C#</span></span>](#tab/c-sharp/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="00242-156">Python</span><span class="sxs-lookup"><span data-stu-id="00242-156">Python</span></span>](#tab/python/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

#### [<span data-ttu-id="00242-157">Java	</span><span class="sxs-lookup"><span data-stu-id="00242-157">Java</span></span>](#tab/java/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

<span data-ttu-id="00242-158">该类 `EdgeDriver` 仅支持 Microsoft Edge (Chromium) ，不支持 Microsoft Edge (EdgeHTML) 。</span><span class="sxs-lookup"><span data-stu-id="00242-158">The `EdgeDriver` class supports Microsoft Edge (Chromium) only, and does not support Microsoft Edge (EdgeHTML).</span></span> <span data-ttu-id="00242-159">对于基本用法，你可以创建一个 `EdgeDriver` 而不提供 `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="00242-159">For basic usage, you may create an `EdgeDriver` without providing `EdgeOptions`.</span></span>  

```java
EdgeDriver driver = new EdgeDriver();
```  

#### [<span data-ttu-id="00242-160">JavaScript</span><span class="sxs-lookup"><span data-stu-id="00242-160">JavaScript</span></span>](#tab/javascript/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> <span data-ttu-id="00242-161">如果你的 IT 管理员将[DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]策略设置为 ，Microsoft Edge 驱动程序无法驱动 `2` Microsoft Edge (Chromium) 因为驱动程序使用[Microsoft Edge DevTools。][DevtoolsIndex] [][MicrosoftDeveloperEdgeToolsWebdriver]</span><span class="sxs-lookup"><span data-stu-id="00242-161">If your IT admin has set the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy to `2`, [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] is not be able to drive Microsoft Edge (Chromium) because the driver uses the [Microsoft Edge DevTools][DevtoolsIndex].</span></span>  <span data-ttu-id="00242-162">确保 [将 DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] 策略设置为或自动执行 Microsoft Edge (`0` `1` Chromium) 。</span><span class="sxs-lookup"><span data-stu-id="00242-162">Ensure the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy is set to `0` or `1` to automate Microsoft Edge (Chromium).</span></span>  

### <span data-ttu-id="00242-163">选择特定浏览器二进制文件 (仅 Chromium) </span><span class="sxs-lookup"><span data-stu-id="00242-163">Choosing Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="00242-164">可以使用特定的 Microsoft Edge \ (Chromium\) 启动 WebDriver 会话。</span><span class="sxs-lookup"><span data-stu-id="00242-164">You may start a WebDriver session with specific Microsoft Edge \(Chromium\) binaries.</span></span>  <span data-ttu-id="00242-165">例如，可以使用 [Microsoft Edge][MicrosoftedgeinsiderDownload] 预览频道（如 Microsoft Edge Beta）运行测试。</span><span class="sxs-lookup"><span data-stu-id="00242-165">For example, you may run tests using the [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<span data-ttu-id="00242-166">C#</span><span class="sxs-lookup"><span data-stu-id="00242-166">C#</span></span>](#tab/c-sharp/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="00242-167">Python</span><span class="sxs-lookup"><span data-stu-id="00242-167">Python</span></span>](#tab/python/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

#### [<span data-ttu-id="00242-168">Java	</span><span class="sxs-lookup"><span data-stu-id="00242-168">Java</span></span>](#tab/java/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.setBinary("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

EdgeDriver driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="00242-169">JavaScript</span><span class="sxs-lookup"><span data-stu-id="00242-169">JavaScript</span></span>](#tab/javascript/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <span data-ttu-id="00242-170">自定义 Microsoft Edge 驱动程序服务</span><span class="sxs-lookup"><span data-stu-id="00242-170">Customizing the Microsoft Edge Driver Service</span></span>  

#### [<span data-ttu-id="00242-171">C#</span><span class="sxs-lookup"><span data-stu-id="00242-171">C#</span></span>](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="00242-172">使用类创建类实例时，它会为 `EdgeDriver` `EdgeOptions` Microsoft Edge `EdgeDriverService` \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 创建和启动相应的类。</span><span class="sxs-lookup"><span data-stu-id="00242-172">When an `EdgeDriver` class instance is created using `EdgeOptions` class, it creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="00242-173">如果要创建一个 ，请创建一个为 `EdgeDriverService` Microsoft Edge \ (Chromium\) 方法 `CreateChromiumService()` 。</span><span class="sxs-lookup"><span data-stu-id="00242-173">If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.</span></span>  <span data-ttu-id="00242-174">当您需要添加自定义项时，您可能会发现它非常有用。</span><span class="sxs-lookup"><span data-stu-id="00242-174">You may find it useful when you need to add customizations.</span></span> <span data-ttu-id="00242-175">例如，以下代码开始详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="00242-175">For example, the following code starts verbose log output.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
><span data-ttu-id="00242-176">在传递给实例时，不需要 `EdgeOptions` `EdgeDriverService` 提供 `EdgeDriver` 对象。</span><span class="sxs-lookup"><span data-stu-id="00242-176">You do not need to provide the `EdgeOptions` object when passing `EdgeDriverService` to the `EdgeDriver` instance.</span></span>  <span data-ttu-id="00242-177">该类根据你提供的服务使用 `EdgeDriver` Microsoft Edge \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 的默认选项。</span><span class="sxs-lookup"><span data-stu-id="00242-177">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) based on the service you provide.</span></span>  
> <span data-ttu-id="00242-178">但是，如果要同时提供这两个类和类，请确保为相同版本的 Microsoft Edge 配置这两 `EdgeDriverService` `EdgeOptions` 者。</span><span class="sxs-lookup"><span data-stu-id="00242-178">However, if you want to provide both `EdgeDriverService` and `EdgeOptions` classes, ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="00242-179">例如，在该类中不能使用默认的 Microsoft Edge \ (EdgeHTML\) 类和 `EdgeDriverService` Chromium `EdgeOptions` 属性。</span><span class="sxs-lookup"><span data-stu-id="00242-179">For example, it is not possible to use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="00242-180">该类 `EdgeDriver` 会引发错误，以防止使用不同的版本。</span><span class="sxs-lookup"><span data-stu-id="00242-180">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<span data-ttu-id="00242-181">Python</span><span class="sxs-lookup"><span data-stu-id="00242-181">Python</span></span>](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="00242-182">使用 Python 时 `Edge` ，对象将创建和管理 `EdgeService` 。</span><span class="sxs-lookup"><span data-stu-id="00242-182">When using Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="00242-183">若要配置 `EdgeService` ，请向对象传递 `Edge` 其他参数，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="00242-183">To configure the `EdgeService`, pass additional arguments to the `Edge` object as indicated in the following code.</span></span>  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<span data-ttu-id="00242-184">Java	</span><span class="sxs-lookup"><span data-stu-id="00242-184">Java</span></span>](#tab/java/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="00242-185">使用此方法 `createDefaultService()` 创建为 Microsoft `EdgeDriverService` Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="00242-185">Use the `createDefaultService()` method to create an `EdgeDriverService` configured for Microsoft Edge \(Chromium\).</span></span> <span data-ttu-id="00242-186">驱动程序服务Java系统属性Java自定义。</span><span class="sxs-lookup"><span data-stu-id="00242-186">Driver services in Java are customized using Java system properties.</span></span> <span data-ttu-id="00242-187">例如，以下代码使用 `"webdriver.edge.verboseLogging"` 该属性启用详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="00242-187">For example, the following code uses the `"webdriver.edge.verboseLogging"` property to enable verbose log output.</span></span>  

```java
System.setProperty("webdriver.edge.verboseLogging", "true");
EdgeDriverService service = EdgeDriverService.createDefaultService();
EdgeOptions options = new EdgeOptions();
EdgeDriver driver = new EdgeDriver(service, options);
```  

#### [<span data-ttu-id="00242-188">JavaScript</span><span class="sxs-lookup"><span data-stu-id="00242-188">JavaScript</span></span>](#tab/javascript/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="00242-189">使用 JavaScript 时，使用类 `Service` 创建和 `ServiceBuilder` 配置 。</span><span class="sxs-lookup"><span data-stu-id="00242-189">When using JavaScript, create and configure a `Service` with the `ServiceBuilder` class.</span></span>  <span data-ttu-id="00242-190">或者，你可以将对象传递给该对象，该对象将启动 `Service` `Driver` \ (并停止\) 服务。</span><span class="sxs-lookup"><span data-stu-id="00242-190">Optionally, you may pass the `Service` object to the `Driver` object, which starts \(and stops\) the service for you.</span></span>  
<span data-ttu-id="00242-191">若要配置 `Service` ，请运行类中的另一 `ServiceBuilder` 个方法，然后再 `build()` 使用该方法。</span><span class="sxs-lookup"><span data-stu-id="00242-191">To configure the `Service`, run another method in the `ServiceBuilder` class before using the `build()` method.</span></span>  <span data-ttu-id="00242-192">然后作为 `service` 参数在方法中 `Driver.createSession()` 传递。</span><span class="sxs-lookup"><span data-stu-id="00242-192">Then pass the `service` as a parameter in the `Driver.createSession()` method.</span></span>  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <span data-ttu-id="00242-193">使用Chromium-Specific选项</span><span class="sxs-lookup"><span data-stu-id="00242-193">Use Chromium-Specific Options</span></span>  

<span data-ttu-id="00242-194">如果将该属性设置为 ，则您可以使用类访问与自动执行其他 Chromium 浏览器时所使用的特定于 `UseChromium` `true` `EdgeOptions` [Chromium][WebdriverCapabilitiesEdgeOptions] 的属性和方法相同的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="00242-194">If you set the `UseChromium` property to `true`, you may use the `EdgeOptions` class to access the same [Chromium-specific properties and methods][WebdriverCapabilitiesEdgeOptions] that are used when automating other Chromium browsers.</span></span>  

#### [<span data-ttu-id="00242-195">C#</span><span class="sxs-lookup"><span data-stu-id="00242-195">C#</span></span>](#tab/c-sharp/)  

<a id="using-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<span data-ttu-id="00242-196">Python</span><span class="sxs-lookup"><span data-stu-id="00242-196">Python</span></span>](#tab/python/)  

<a id="using-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<span data-ttu-id="00242-197">Java	</span><span class="sxs-lookup"><span data-stu-id="00242-197">Java</span></span>](#tab/java/)  

<a id="using-chromium-specific-options-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

#### [<span data-ttu-id="00242-198">JavaScript</span><span class="sxs-lookup"><span data-stu-id="00242-198">JavaScript</span></span>](#tab/javascript/)  

<a id="using-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

* * *  

> [!NOTE]
> <span data-ttu-id="00242-199">如果该属性设置为，则不能对 `UseChromium` Microsoft Edge `true` \ (EdgeHTML\) 。</span><span class="sxs-lookup"><span data-stu-id="00242-199">If the `UseChromium` property is set to `true`, you are not able to use properties and methods for Microsoft Edge \(EdgeHTML\).</span></span>  

## <span data-ttu-id="00242-200">其他 WebDriver 安装选项</span><span class="sxs-lookup"><span data-stu-id="00242-200">Additional WebDriver installation options</span></span>  

### <span data-ttu-id="00242-201">百年</span><span class="sxs-lookup"><span data-stu-id="00242-201">Chocolatey</span></span>  

<span data-ttu-id="00242-202">如果你使用 [Microsofty][Chocolatey] 作为程序包管理器，请运行以下命令来安装 Microsoft Edge 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="00242-202">If you use [Chocolatey][Chocolatey] as your package manager, install the Microsoft Edge Driver by running the following command.</span></span>  

```console
choco install selenium-chromium-edge-driver
```  

<span data-ttu-id="00242-203">有关详细信息，请参阅 [Selenium Chromium Edge Driver on 一角][ChocolateyPackagesSeleniumChromiumEdgeDriver]。</span><span class="sxs-lookup"><span data-stu-id="00242-203">For more information, see [Selenium Chromium Edge Driver on Chocolatey][ChocolateyPackagesSeleniumChromiumEdgeDriver].</span></span>  

### <span data-ttu-id="00242-204">Docker</span><span class="sxs-lookup"><span data-stu-id="00242-204">Docker</span></span>  

<span data-ttu-id="00242-205">如果使用 [Docker，][DockerHub]请通过运行以下命令，下载预配置映像和 Microsoft Edge \ (Chromium\) 和预安装的 [Microsoft Edge][MicrosoftDeveloperEdgeToolsWebdriver] 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="00242-205">If you use [Docker][DockerHub], download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] pre-installed by running the following command.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="00242-206">有关详细信息，请导航到 Docker Hub 上的 [msedgedriver 容器][DockerHubMsedgedriver]。</span><span class="sxs-lookup"><span data-stu-id="00242-206">For more information, navigate to the [msedgedriver container on Docker Hub][DockerHubMsedgedriver].</span></span>  

## <span data-ttu-id="00242-207">后续步骤</span><span class="sxs-lookup"><span data-stu-id="00242-207">Next steps</span></span>

<span data-ttu-id="00242-208">若要了解有关 WebDriver 以及如何使用 Selenium 编写自动 WebDriver 测试的信息，请导航到 [Selenium 文档][SeleniumDocumentation]。</span><span class="sxs-lookup"><span data-stu-id="00242-208">To learn more about WebDriver and how to write automated WebDriver tests using Selenium, navigate to the [Selenium documentation][SeleniumDocumentation].</span></span>  

## <span data-ttu-id="00242-209">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="00242-209">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="00242-210">Microsoft Edge 团队希望倾听你有关使用 WebDriver、Selenium 和 Microsoft Edge 的反馈。</span><span class="sxs-lookup"><span data-stu-id="00242-210">The Microsoft Edge team is eager to hear your feedback about using WebDriver, Selenium, and Microsoft Edge.</span></span>  <span data-ttu-id="00242-211">若要向团队发送你的问题和意见，请选择 Microsoft \*\*\*\* Edge DevTools 中的"发送反馈"图标或发送推文[@EdgeDevTools。][TwitterTweetEdgeDevTools]</span><span class="sxs-lookup"><span data-stu-id="00242-211">To send the team your questions and comments, choose the **Send Feedback** icon in the Microsoft Edge DevTools or send a tweet [@EdgeDevTools][TwitterTweetEdgeDevTools].</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="00242-213">Microsoft **Edge** DevTools 中的"发送反馈"图标</span><span class="sxs-lookup"><span data-stu-id="00242-213">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- links -->  

[DevtoolsIndex]: ../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  
[WebdriverCapabilitiesEdgeOptions]: ./capabilities-edge-options.md "功能和 EdgeOptions |Microsoft Docs"  
<!--[Webdriver]: ../edgehtml/webdriver/index.md "WebDriver (EdgeHTML) | Microsoft Docs"  -->  

[DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability - Microsoft Edge - 策略|Microsoft Docs"  

[Chocolatey]: https://chocolatey.org "百年|百万软件"  
[ChocolateyPackagesSeleniumChromiumEdgeDriver]: https://chocolatey.org/packages/selenium-chromium-edge-driver "Selenium Chromium Edge 驱动程序|百年"  

[DockerHub]: https://hub.docker.com "Docker Hub"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker 中心"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-tools |GitHub"  
[GithubMicrosoftEdgeSeleniumToolsReleases]: https://github.com/microsoft/edge-selenium-tools/releases "microsoft/edge-selenium-tools |GitHub"  
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
[NugetPackagesSeleniumWebdriver400alpha07]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha07 "Selenium.WebDriver 4.0.0-alpha07 |NuGet 库"  

[PythonPip]: https://pypi.org/project/pip/ "管道|PyPI"  
[PythonSeleniumTools]: https://pypi.org/project/msedge-selenium-tools/ "msedge-selenium-tools |PyPI"  
[PythonSelenium]: https://pypi.org/project/selenium/ "selenium |PyPI"

[SeleniumHQ]: https://www.selenium.dev "SeleniumHQ"  
[SeleniumDocumentation]: https://www.selenium.dev/documentation "Selenium 浏览器自动化项目 ：：Selenium 文档"  
[SeleniumDownloads]: https://selenium.dev/downloads "下载|Selenium"  

[SonatypeMavenRepositorySearch]: https://search.maven.org/artifact/com.microsoft.edge/msedge-selenium-tools-java/3.141.0/jar "sonatype Maven 中央存储库搜索|com.microsoft.edge：msedge-selenium-tools-java"

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |发布推文"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |W3C"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无头浏览器|Wikipedia"  
