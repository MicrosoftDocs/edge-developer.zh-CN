---
description: 了解如何在 Microsoft Edge 中测试网站或应用，或者使用 WebDriver 自动执行浏览器
title: 使用 WebDriver (Chromium) 实现测试自动化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/20/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge， Web 开发， html， css， javascript， 开发人员， webdriver， selenium， 测试， 工具， 自动化， 测试
ms.openlocfilehash: 0a5a6cde75621f0dda1e98b0c7b471b1456bf430
ms.sourcegitcommit: 518c1116dc5e6968edf92730906aa0e72dbf945d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "11496967"
---
# <a name="use-webdriver-chromium-for-test-automation"></a><span data-ttu-id="43308-104">使用 WebDriver (Chromium) 实现测试自动化</span><span class="sxs-lookup"><span data-stu-id="43308-104">Use WebDriver (Chromium) for test automation</span></span>  

<span data-ttu-id="43308-105">WebDriver 允许开发人员创建模拟用户交互的自动测试。</span><span class="sxs-lookup"><span data-stu-id="43308-105">WebDriver allows developers to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="43308-106">WebDriver 测试和模拟与 JavaScript 单元测试在以下方面有所不同。</span><span class="sxs-lookup"><span data-stu-id="43308-106">WebDriver tests and simulations differ from JavaScript unit tests in the following ways.</span></span>  

*   <span data-ttu-id="43308-107">访问在浏览器中运行的 JavaScript 不可用的功能和信息。</span><span class="sxs-lookup"><span data-stu-id="43308-107">Accesses functionality and information not available to JavaScript running in browsers.</span></span>  
*   <span data-ttu-id="43308-108">更精确地模拟用户事件或操作系统级事件。</span><span class="sxs-lookup"><span data-stu-id="43308-108">Simulates user events or OS-level events more accurately.</span></span>  
*   <span data-ttu-id="43308-109">在单个测试会话中管理多个窗口、选项卡和网页。</span><span class="sxs-lookup"><span data-stu-id="43308-109">Manages multiple windows, tabs, and webpages in a single test session.</span></span>  
*   <span data-ttu-id="43308-110">在特定的计算机上运行 Microsoft Edge 的多个会话。</span><span class="sxs-lookup"><span data-stu-id="43308-110">Runs multiple sessions of Microsoft Edge on a specific machine.</span></span>  
    
<span data-ttu-id="43308-111">以下部分介绍如何开始使用 WebDriver for Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="43308-111">The following section describes how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  

## <a name="install-microsoft-edge-chromium"></a><span data-ttu-id="43308-112">安装 Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="43308-112">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="43308-113">确保安装[Microsoft Edge (Chromium) 。 ][MicrosoftEdge]</span><span class="sxs-lookup"><span data-stu-id="43308-113">Ensure you install [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="43308-114">若要确认已安装 Microsoft Edge \ (Chromium\) ，请导航到 `edge://settings/help` ，并验证版本号是版本 75 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="43308-114">To confirm that you have Microsoft Edge \(Chromium\) installed, navigate to `edge://settings/help`, and verify the version number is version 75 or later.</span></span>  

## <a name="download-microsoft-edge-driver"></a><span data-ttu-id="43308-115">下载 Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="43308-115">Download Microsoft Edge Driver</span></span>  

<span data-ttu-id="43308-116">若要开始自动执行测试，请使用以下步骤来确保安装的 WebDriver 版本与浏览器版本相匹配。</span><span class="sxs-lookup"><span data-stu-id="43308-116">To begin automating tests, use the following steps to ensure that the WebDriver version you install matches your browser version.</span></span>  

1.  <span data-ttu-id="43308-117">查找你的 Microsoft Edge 版本。</span><span class="sxs-lookup"><span data-stu-id="43308-117">Find your version of Microsoft Edge.</span></span>  
    1.  <span data-ttu-id="43308-118">导航到 `edge://settings/help`。</span><span class="sxs-lookup"><span data-stu-id="43308-118">Navigate to `edge://settings/help`.</span></span>  
        
        :::image type="complex" source="./media/microsoft-edge-version.msft.png" alt-text="Microsoft Edge 2021 年 4 月 15 日内部版本号" lightbox="./media/microsoft-edge-version.msft.png":::
           <span data-ttu-id="43308-120">Microsoft Edge 2021 年 4 月 15 日内部版本号</span><span class="sxs-lookup"><span data-stu-id="43308-120">The build number for Microsoft Edge on April 15, 2021</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="43308-121">导航到 [Microsoft Edge 驱动程序][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="43308-121">Navigate to [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver].</span></span>  
1.  <span data-ttu-id="43308-122">导航到 **获取最新版本**。</span><span class="sxs-lookup"><span data-stu-id="43308-122">Navigate to **Get the latest version**.</span></span>  
1.  <span data-ttu-id="43308-123">选择与 Microsoft Edge 的版本号匹配的频道版本。</span><span class="sxs-lookup"><span data-stu-id="43308-123">Choose the build of channel that matches your version number of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="./media/microsoft-edge-driver-install.msft.png" alt-text="Microsoft Edge 驱动程序网页上的获取最新版本部分" lightbox="./media/microsoft-edge-driver-install.msft.png":::
       <span data-ttu-id="43308-125">Microsoft **Edge 驱动程序网页上的** 获取 [最新版本][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] 部分</span><span class="sxs-lookup"><span data-stu-id="43308-125">The **Get the latest version** section on the [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] webpage</span></span>  
    :::image-end:::  
    
    <!--  
    > [!NOTE] 
    > For more information about test automation using Microsoft Edge \(EdgeHTML\), navigate to [Microsoft Edge Driver for Microsoft Edge (EdgeHTML)][Webdriver].  
    -->  
    
## <a name="choose-a-webdriver-language-binding"></a><span data-ttu-id="43308-126">选择 WebDriver 语言绑定</span><span class="sxs-lookup"><span data-stu-id="43308-126">Choose a WebDriver language binding</span></span>  

<span data-ttu-id="43308-127">必须下载的最后一个组件是特定语言的客户端驱动程序，用于将代码 \ (Python、Java、C\#、Ruby、JavaScript\) 转换为 Microsoft Edge 驱动程序在 Microsoft Edge \ (Chromium\) 中运行的命令。</span><span class="sxs-lookup"><span data-stu-id="43308-127">The last component you must download is a language-specific client driver to translate your code \(Python, Java, C\#, Ruby, JavaScript\) into commands the Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="43308-128">[下载你选择的 WebDriver 语言绑定][SeleniumDownloads]。</span><span class="sxs-lookup"><span data-stu-id="43308-128">[Download the WebDriver language binding of your choice][SeleniumDownloads].</span></span>  <span data-ttu-id="43308-129">Microsoft Edge 团队建议使用 [Selenium 4.00-alpha07][NugetPackagesSeleniumWebdriver400alpha07] 或更高版本，因为它支持 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="43308-129">The Microsoft Edge team recommends [Selenium 4.00-alpha07][NugetPackagesSeleniumWebdriver400alpha07] or later, because it supports Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="43308-130">但是，你可以控制所有旧版本 Selenium 中的 Microsoft Edge \ (Chromium\) ，包括当前稳定的 Selenium 3 版本。</span><span class="sxs-lookup"><span data-stu-id="43308-130">However, you may control Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="43308-131">如果之前使用 和 类自动或测试 Microsoft Edge \ (Chromium\) ，则 WebDriver 代码不会在 `ChromeDriver` `ChromeOptions` Microsoft Edge 版本 80 或更高版本中运行。</span><span class="sxs-lookup"><span data-stu-id="43308-131">If you previously automated or tested Microsoft Edge \(Chromium\) using `ChromeDriver` and `ChromeOptions` classes, your WebDriver code does not run on Microsoft Edge Version 80 or later.</span></span>  <span data-ttu-id="43308-132">若要解决此问题，请更新测试以使用 `EdgeOptions` 类并下载 [Microsoft Edge 驱动程序][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="43308-132">To solve the problem, update your tests to use the `EdgeOptions` class and download [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver].</span></span>  

### <a name="use-selenium-3"></a><span data-ttu-id="43308-133">使用 Selenium 3</span><span class="sxs-lookup"><span data-stu-id="43308-133">Use Selenium 3</span></span>  

<span data-ttu-id="43308-134">如果你已使用 [Selenium 3，][|::ref1::|]你可能已有浏览器测试，并且希望增加 Microsoft Edge \ (Chromium\) 的覆盖范围，而无需更改 Selenium 版本。</span><span class="sxs-lookup"><span data-stu-id="43308-134">If you already use [Selenium 3][|::ref1::|], you may have existing browser tests and want to add coverage for Microsoft Edge \(Chromium\) without changing your version of Selenium.</span></span>  <span data-ttu-id="43308-135">若要使用 [Selenium 3][|::ref2::|] 为 Microsoft Edge \ (EdgeHTML\) 和 Microsoft Edge \ (Chromium\) 编写自动测试，请安装适用于 Microsoft Edge 的 [Selenium 工具][GithubMicrosoftEdgeSeleniumTools] 程序包以使用更新的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="43308-135">To use [Selenium 3][|::ref2::|] to write automated tests for both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package to use the updated driver.</span></span>  <span data-ttu-id="43308-136">工具 `EdgeDriver` `EdgeDriverService` 中包含的 和 类与 Selenium 4 中的内置等效项完全兼容。</span><span class="sxs-lookup"><span data-stu-id="43308-136">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium 4.</span></span>  

<span data-ttu-id="43308-137">使用以下步骤将适用于 Microsoft Edge 和[Selenium 3][|::ref3::|]的[Selenium 工具][GithubMicrosoftEdgeSeleniumTools]添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="43308-137">Use the following steps to add the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] and [Selenium 3][|::ref3::|] to your project.</span></span>  

#### [<a name="c"></a><span data-ttu-id="43308-138">C#</span><span class="sxs-lookup"><span data-stu-id="43308-138">C#</span></span>](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="43308-139">使用[NuGet CLI][NugetCLI]或 Visual Studio 将[Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools]和[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] [程序包添加到 .NET 项目][VisualStudio]。</span><span class="sxs-lookup"><span data-stu-id="43308-139">Add the [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] and [Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] packages to your .NET project using the [NuGet CLI][NugetCLI] or [Visual Studio][VisualStudio].</span></span>  

#### [<a name="python"></a><span data-ttu-id="43308-140">Python</span><span class="sxs-lookup"><span data-stu-id="43308-140">Python</span></span>](#tab/python/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="43308-141">使用 [管道][PythonPip] 安装 [msedge-selenium-tools][PythonSeleniumTools] 和 [selenium][PythonSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="43308-141">Use [pip][PythonPip] to install the [msedge-selenium-tools][PythonSeleniumTools] and [selenium][PythonSelenium] packages.</span></span>  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<a name="java"></a><span data-ttu-id="43308-142">Java	</span><span class="sxs-lookup"><span data-stu-id="43308-142">Java</span></span>](#tab/java/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="43308-143">如果您的Java项目使用 Maven，将以下依赖项复制并粘贴到您的文件以添加 `pom.xml` [msedge-selenium-tools-java][SonatypeMavenRepositorySearch]。</span><span class="sxs-lookup"><span data-stu-id="43308-143">If your Java project uses Maven, copy and paste the following dependency to your `pom.xml` file to add [msedge-selenium-tools-java][SonatypeMavenRepositorySearch].</span></span>  

```xml
<dependency>
    <groupId>com.microsoft.edge</groupId>
    <artifactId>msedge-selenium-tools-java</artifactId>
    <version>[3.141.0,)</version>
</dependency>
```  

<span data-ttu-id="43308-144">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].</span><span class="sxs-lookup"><span data-stu-id="43308-144">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].</span></span>  

#### [<a name="javascript"></a><span data-ttu-id="43308-145">JavaScript</span><span class="sxs-lookup"><span data-stu-id="43308-145">JavaScript</span></span>](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="43308-146">使用 [npm][JavaScript|::ref4::|] 安装 [edge-selenium-tools][JavaScriptSeleniumTools] 和 [selenium-webdriver][JavaScriptSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="43308-146">Use [npm][JavaScript|::ref4::|] to install the [edge-selenium-tools][JavaScriptSeleniumTools] and [selenium-webdriver][JavaScriptSelenium] packages.</span></span>  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## <a name="automate-microsoft-edge-chromium-with-webdriver"></a><span data-ttu-id="43308-147">使用 WebDriver (Microsoft Edge) Chromium</span><span class="sxs-lookup"><span data-stu-id="43308-147">Automate Microsoft Edge (Chromium) with WebDriver</span></span>  

<span data-ttu-id="43308-148">若要使用 WebDriver 自动化浏览器，必须先使用首选的 WebDriver 语言绑定启动 WebDriver 会话。</span><span class="sxs-lookup"><span data-stu-id="43308-148">To automate a browser using WebDriver, you must first start a WebDriver session using your preferred WebDriver language binding.</span></span>  <span data-ttu-id="43308-149">会话是使用 WebDriver 命令控制的浏览器的单个运行实例。</span><span class="sxs-lookup"><span data-stu-id="43308-149">A session is a single running instance of a browser controlled using WebDriver commands.</span></span>  <span data-ttu-id="43308-150">启动 WebDriver 会话以启动新的浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="43308-150">Start a WebDriver session to launch a new browser instance.</span></span>  <span data-ttu-id="43308-151">在关闭 WebDriver 会话之前，启动的浏览器实例保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="43308-151">The launched browser instance remains open until you close the WebDriver session.</span></span>  

<span data-ttu-id="43308-152">以下内容将引导你使用 Selenium 启动与 Microsoft Edge \ (Chromium\) 的 WebDriver 会话。</span><span class="sxs-lookup"><span data-stu-id="43308-152">The following content walks you through using Selenium to start a WebDriver session with Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="43308-153">可以使用 Selenium 3 或 4 运行这些示例。</span><span class="sxs-lookup"><span data-stu-id="43308-153">You may run the examples using either Selenium 3 or 4.</span></span>  <span data-ttu-id="43308-154">若要与 Selenium 3 一同使用，必须安装适用于 Microsoft Edge 的 [Selenium][GithubMicrosoftEdgeSeleniumTools] 工具程序包。</span><span class="sxs-lookup"><span data-stu-id="43308-154">To use with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package must be installed.</span></span>  

### <a name="automate-microsoft-edge-chromium"></a><span data-ttu-id="43308-155">自动执行 Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="43308-155">Automate Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="43308-156">Selenium 使用 `EdgeDriver` 类管理 Microsoft Edge \ (Chromium\) 会话。</span><span class="sxs-lookup"><span data-stu-id="43308-156">Selenium uses the `EdgeDriver` class to manage a Microsoft Edge \(Chromium\) session.</span></span>  <span data-ttu-id="43308-157">若要启动会话并自动执行 Microsoft Edge \ (Chromium\) ，请创建一个新对象，并传递一个属性设置为 `EdgeDriver` `EdgeOptions` `UseChromium` 的对象 `true` 。</span><span class="sxs-lookup"><span data-stu-id="43308-157">To start a session and automate Microsoft Edge \(Chromium\), create a new `EdgeDriver` object and pass it an `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<a name="c"></a><span data-ttu-id="43308-158">C#</span><span class="sxs-lookup"><span data-stu-id="43308-158">C#</span></span>](#tab/c-sharp/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a><span data-ttu-id="43308-159">Python</span><span class="sxs-lookup"><span data-stu-id="43308-159">Python</span></span>](#tab/python/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options = options)
```  

#### [<a name="java"></a><span data-ttu-id="43308-160">Java	</span><span class="sxs-lookup"><span data-stu-id="43308-160">Java</span></span>](#tab/java/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

<span data-ttu-id="43308-161">该类 `EdgeDriver` 仅支持 Microsoft Edge \ (Chromium\) ，不支持 Microsoft Edge \ (EdgeHTML\) 。</span><span class="sxs-lookup"><span data-stu-id="43308-161">The `EdgeDriver` class only supports Microsoft Edge \(Chromium\), and doesn't support Microsoft Edge \(EdgeHTML\).</span></span>  <span data-ttu-id="43308-162">对于基本用法，你可以创建 ， `EdgeDriver` 而不提供 `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="43308-162">For basic usage, you may create an `EdgeDriver` without providing `EdgeOptions`.</span></span>  

```java
EdgeDriver driver = new EdgeDriver();
```  

#### [<a name="javascript"></a><span data-ttu-id="43308-163">JavaScript</span><span class="sxs-lookup"><span data-stu-id="43308-163">JavaScript</span></span>](#tab/javascript/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> <span data-ttu-id="43308-164">如果你的 IT 管理员将[DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]策略设置为 ，Microsoft Edge 驱动程序将被阻止驱动 `2` Microsoft Edge \ (Chromium\) ，因为该驱动程序使用[Microsoft Edge DevTools][DevtoolsIndex]。 [][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]</span><span class="sxs-lookup"><span data-stu-id="43308-164">If your IT admin has set the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy to `2`,  [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] is blocked from driving Microsoft Edge \(Chromium\), because the driver uses the [Microsoft Edge DevTools][DevtoolsIndex].</span></span>  <span data-ttu-id="43308-165">确保 [将 DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] 策略设置为或自动执行 Microsoft Edge (`0` `1` Chromium) 。</span><span class="sxs-lookup"><span data-stu-id="43308-165">Ensure the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy is set to `0` or `1` to automate Microsoft Edge (Chromium).</span></span>  

### <a name="choose-specific-browser-binaries-chromium-only"></a><span data-ttu-id="43308-166">选择"特定浏览器二 (仅 Chromium") </span><span class="sxs-lookup"><span data-stu-id="43308-166">Choose Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="43308-167">可以使用特定的 Microsoft Edge \ (Chromium\) 启动 WebDriver 会话。</span><span class="sxs-lookup"><span data-stu-id="43308-167">You may start a WebDriver session with specific Microsoft Edge \(Chromium\) binaries.</span></span>  <span data-ttu-id="43308-168">例如，可以使用 Microsoft Edge 预览渠道（如 [Microsoft Edge Beta）][MicrosoftedgeinsiderDownload] 运行测试。</span><span class="sxs-lookup"><span data-stu-id="43308-168">For example, you may run tests using the [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<a name="c"></a><span data-ttu-id="43308-169">C#</span><span class="sxs-lookup"><span data-stu-id="43308-169">C#</span></span>](#tab/c-sharp/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a><span data-ttu-id="43308-170">Python</span><span class="sxs-lookup"><span data-stu-id="43308-170">Python</span></span>](#tab/python/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options = options)
```  

#### [<a name="java"></a><span data-ttu-id="43308-171">Java	</span><span class="sxs-lookup"><span data-stu-id="43308-171">Java</span></span>](#tab/java/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.setBinary("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

EdgeDriver driver = new EdgeDriver(options);
```  

#### [<a name="javascript"></a><span data-ttu-id="43308-172">JavaScript</span><span class="sxs-lookup"><span data-stu-id="43308-172">JavaScript</span></span>](#tab/javascript/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <a name="customize-the-microsoft-edge-driver-service"></a><span data-ttu-id="43308-173">自定义 Microsoft Edge 驱动程序服务</span><span class="sxs-lookup"><span data-stu-id="43308-173">Customize the Microsoft Edge Driver Service</span></span>  

#### [<a name="c"></a><span data-ttu-id="43308-174">C#</span><span class="sxs-lookup"><span data-stu-id="43308-174">C#</span></span>](#tab/c-sharp/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="43308-175">使用类创建类实例时，它会为 `EdgeOptions` `EdgeDriver` Microsoft Edge `EdgeDriverService` \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 创建和启动相应的类。</span><span class="sxs-lookup"><span data-stu-id="43308-175">When you use the `EdgeOptions` class to create an `EdgeDriver` class instance, it creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="43308-176">如果要创建 ，请使用 方法创建一个配置为 `EdgeDriverService` `CreateChromiumService()` Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="43308-176">If you want to create an `EdgeDriverService`, use the `CreateChromiumService()` method to create one configured for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="43308-177">`CreateChromiumService()`当您需要添加自定义项时，该方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="43308-177">The `CreateChromiumService()` method is useful when you need to add customizations.</span></span>  <span data-ttu-id="43308-178">例如，以下代码开始详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="43308-178">For example, the following code starts verbose log output.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
><span data-ttu-id="43308-179">在传递给实例时，不需要 `EdgeOptions` 提供 `EdgeDriverService` `EdgeDriver` 对象。</span><span class="sxs-lookup"><span data-stu-id="43308-179">You do not need to provide the `EdgeOptions` object when you pass `EdgeDriverService` to the `EdgeDriver` instance.</span></span>  <span data-ttu-id="43308-180">该类根据你提供的服务使用 `EdgeDriver` Microsoft Edge \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 的默认选项。</span><span class="sxs-lookup"><span data-stu-id="43308-180">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) based on the service you provide.</span></span>  
> <span data-ttu-id="43308-181">但是，如果要同时提供 和 类，请确保为相同版本的 Microsoft Edge 配置这两 `EdgeDriverService` `EdgeOptions` 个类。</span><span class="sxs-lookup"><span data-stu-id="43308-181">However, if you want to provide both `EdgeDriverService` and `EdgeOptions` classes, ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="43308-182">例如，您可以在该类中使用默认的 Microsoft Edge \ (EdgeHTML\) 类和 `EdgeDriverService` Chromium `EdgeOptions` 属性。</span><span class="sxs-lookup"><span data-stu-id="43308-182">For example, you may use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="43308-183">`EdgeDriver`该类会引发错误，以阻止使用不同的版本。</span><span class="sxs-lookup"><span data-stu-id="43308-183">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<a name="python"></a><span data-ttu-id="43308-184">Python</span><span class="sxs-lookup"><span data-stu-id="43308-184">Python</span></span>](#tab/python/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="43308-185">使用 Python 时， `Edge` 对象将创建和管理 `EdgeService` 。</span><span class="sxs-lookup"><span data-stu-id="43308-185">When you use Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="43308-186">若要配置 `EdgeService` ，请向 对象传递 `Edge` 额外参数，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="43308-186">To configure the `EdgeService`, pass extra arguments to the `Edge` object as indicated in the following code.</span></span>  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<a name="java"></a><span data-ttu-id="43308-187">Java	</span><span class="sxs-lookup"><span data-stu-id="43308-187">Java</span></span>](#tab/java/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="43308-188">使用 `createDefaultService()` 方法创建为 `EdgeDriverService` Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="43308-188">Use the `createDefaultService()` method to create an `EdgeDriverService` configured for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="43308-189">使用 Java 系统属性自定义 Java 中的驱动程序服务。</span><span class="sxs-lookup"><span data-stu-id="43308-189">Use Java system properties to customize driver services in Java.</span></span>  <span data-ttu-id="43308-190">例如，以下代码使用 `"webdriver.edge.verboseLogging"` 属性打开详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="43308-190">For example, the following code uses the `"webdriver.edge.verboseLogging"` property to turn on verbose log output.</span></span>  

```java
System.setProperty("webdriver.edge.verboseLogging", "true");
EdgeDriverService service = EdgeDriverService.createDefaultService();
EdgeOptions options = new EdgeOptions();
EdgeDriver driver = new EdgeDriver(service, options);
```  

#### [<a name="javascript"></a><span data-ttu-id="43308-191">JavaScript</span><span class="sxs-lookup"><span data-stu-id="43308-191">JavaScript</span></span>](#tab/javascript/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="43308-192">使用 JavaScript 时，请使用 类 `Service` 创建和 `ServiceBuilder` 配置 。</span><span class="sxs-lookup"><span data-stu-id="43308-192">When you use JavaScript, create and configure a `Service` with the `ServiceBuilder` class.</span></span>  <span data-ttu-id="43308-193">（可选）你可以将对象传递给对象，该对象将启动 `Service` `Driver` \ (并停止\) 服务。</span><span class="sxs-lookup"><span data-stu-id="43308-193">Optionally, you may pass the `Service` object to the `Driver` object, which starts \(and stops\) the service for you.</span></span>  
<span data-ttu-id="43308-194">若要配置 `Service` ，请运行 类中的另一 `ServiceBuilder` 个方法，然后再使用 `build()` 方法。</span><span class="sxs-lookup"><span data-stu-id="43308-194">To configure the `Service`, run another method in the `ServiceBuilder` class before you use the `build()` method.</span></span>  <span data-ttu-id="43308-195">然后， `service` 在 方法中将 作为 参数 `Driver.createSession()` 传递。</span><span class="sxs-lookup"><span data-stu-id="43308-195">Then pass the `service` as a parameter in the `Driver.createSession()` method.</span></span>  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <a name="use-chromium-specific-options"></a><span data-ttu-id="43308-196">使用Chromium-Specific选项</span><span class="sxs-lookup"><span data-stu-id="43308-196">Use Chromium-Specific Options</span></span>  

<span data-ttu-id="43308-197">如果将 属性设置为 ，可以使用 类访问与自动执行其他 Chromium 浏览器时所使用的特定于 `UseChromium` `true` `EdgeOptions` [Chromium][WebdriverCapabilitiesEdgeOptions] 的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="43308-197">If you set the `UseChromium` property to `true`, you may use the `EdgeOptions` class to access the same [Chromium-specific properties and methods][WebdriverCapabilitiesEdgeOptions] that are used when you automate other Chromium browsers.</span></span>  

#### [<a name="c"></a><span data-ttu-id="43308-198">C#</span><span class="sxs-lookup"><span data-stu-id="43308-198">C#</span></span>](#tab/c-sharp/)  

<a id="use-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<a name="python"></a><span data-ttu-id="43308-199">Python</span><span class="sxs-lookup"><span data-stu-id="43308-199">Python</span></span>](#tab/python/)  

<a id="use-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<a name="java"></a><span data-ttu-id="43308-200">Java	</span><span class="sxs-lookup"><span data-stu-id="43308-200">Java</span></span>](#tab/java/)  

<a id="use-chromium-specific-options-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

#### [<a name="javascript"></a><span data-ttu-id="43308-201">JavaScript</span><span class="sxs-lookup"><span data-stu-id="43308-201">JavaScript</span></span>](#tab/javascript/)  

<a id="use-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

* * *  

> [!NOTE]
> <span data-ttu-id="43308-202">如果 `UseChromium` 属性设置为 `true` ，则不能对 Microsoft Edge \ (EdgeHTML\) 。</span><span class="sxs-lookup"><span data-stu-id="43308-202">If the `UseChromium` property is set to `true`, you are not able to use properties and methods for Microsoft Edge \(EdgeHTML\).</span></span>  

## <a name="other-webdriver-installation-options"></a><span data-ttu-id="43308-203">其他 WebDriver 安装选项</span><span class="sxs-lookup"><span data-stu-id="43308-203">Other WebDriver installation options</span></span>  

### <a name="chocolatey"></a><span data-ttu-id="43308-204">百年</span><span class="sxs-lookup"><span data-stu-id="43308-204">Chocolatey</span></span>  

<span data-ttu-id="43308-205">如果你使用 [作为程序包][Chocolatey] 管理器的部署管理程序，请运行以下命令来安装 Microsoft Edge 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="43308-205">If you use [Chocolatey][Chocolatey] as your package manager, run the following command to install the Microsoft Edge Driver.</span></span>  

```console
choco install selenium-chromium-edge-driver
```  

<span data-ttu-id="43308-206">有关详细信息，请导航到"位于 ["在"完成"上的 Selenium Chromium][ChocolateyPackagesSeleniumChromiumEdgeDriver]边缘驱动程序。</span><span class="sxs-lookup"><span data-stu-id="43308-206">For more information, navigate to [Selenium Chromium Edge Driver on Chocolatey][ChocolateyPackagesSeleniumChromiumEdgeDriver].</span></span>  

### <a name="docker"></a><span data-ttu-id="43308-207">Docker</span><span class="sxs-lookup"><span data-stu-id="43308-207">Docker</span></span>  

<span data-ttu-id="43308-208">如果使用 [Docker，][DockerHub]请运行以下命令以下载预配置映像（预安装了 Microsoft Edge \ (Chromium\) 和 [Microsoft Edge][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] 驱动程序）。</span><span class="sxs-lookup"><span data-stu-id="43308-208">If you use [Docker][DockerHub], run the following command to download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] pre-installed.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="43308-209">有关详细信息，请导航到 Docker Hub 上的 [msedgedriver 容器][DockerHubMsedgedriver]。</span><span class="sxs-lookup"><span data-stu-id="43308-209">For more information, navigate to the [msedgedriver container on Docker Hub][DockerHubMsedgedriver].</span></span>  

## <a name="next-steps"></a><span data-ttu-id="43308-210">后续步骤</span><span class="sxs-lookup"><span data-stu-id="43308-210">Next steps</span></span>  

<span data-ttu-id="43308-211">有关 WebDriver 和如何使用 Selenium 编写自动 WebDriver 测试的信息，请导航到 [Selenium 文档][SeleniumDocumentation]。</span><span class="sxs-lookup"><span data-stu-id="43308-211">For more information about WebDriver and how to write automated WebDriver tests using Selenium, navigate to the [Selenium documentation][SeleniumDocumentation].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="43308-212">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="43308-212">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="43308-213">Microsoft Edge 团队希望倾听你有关使用 WebDriver、Selenium 和 Microsoft Edge 的反馈。</span><span class="sxs-lookup"><span data-stu-id="43308-213">The Microsoft Edge team is eager to hear your feedback about using WebDriver, Selenium, and Microsoft Edge.</span></span>  <span data-ttu-id="43308-214">若要向团队发送你的问题和意见，请选择 Microsoft \*\*\*\* Edge DevTools 中的"发送反馈"图标[或][TwitterTweetEdgeDevTools]发送推文@EdgeDevTools。</span><span class="sxs-lookup"><span data-stu-id="43308-214">To send the team your questions and comments, choose the **Send Feedback** icon in the Microsoft Edge DevTools or send a tweet [@EdgeDevTools][TwitterTweetEdgeDevTools].</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="43308-216">Microsoft Edge DevTools 中的**发送反馈**图标</span><span class="sxs-lookup"><span data-stu-id="43308-216">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- links -->  

[DevtoolsIndex]: ../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[WebdriverCapabilitiesEdgeOptions]: ./capabilities-edge-options.md "功能和 EdgeOptions |Microsoft Docs"  

<!--[Webdriver]: /archive/microsoft-edge/legacy/developer/webdriver/index "WebDriver (EdgeHTML) | Microsoft Docs"  -->  

[DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability - Microsoft Edge - 策略|Microsoft Docs"  

[Chocolatey]: https://chocolatey.org "百年|百年软件"  
[ChocolateyPackagesSeleniumChromiumEdgeDriver]: https://chocolatey.org/packages/selenium-chromium-edge-driver "Selenium Chromium 边缘驱动程序|百年"  

[DockerHub]: https://hub.docker.com "Docker Hub"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker 中心"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-tools |GitHub"  
[GithubMicrosoftEdgeSeleniumToolsReleases]: https://github.com/microsoft/edge-selenium-tools/releases "microsoft/edge-selenium-tools |GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/selenium |GitHub"  

[JavaScriptnpm]: https://www.npmjs.com/ "npm"  
[JavaScriptSeleniumTools]: https://www.npmjs.com/package/@microsoft/edge-selenium-tools "@microsoft/edge-selenium-tools |npm"  
[JavaScriptSelenium]: https://www.npmjs.com/package/selenium-webdriver "selenium-webdriver |npm"  

[MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]: https://developer.microsoft.com/microsoft-edge/tools/webdriver "Microsoft Edge 驱动程序|Microsoft Edge 开发人员"  

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

[SonatypeMavenRepositorySearch]: https://search.maven.org/artifact/com.microsoft.edge/msedge-selenium-tools-java/3.141.0/jar "sonatype Maven Central Repository Search |com.microsoft.edge：msedge-selenium-tools-java"

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |发布推文"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |W3C"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无头浏览器|Wikipedia"  
