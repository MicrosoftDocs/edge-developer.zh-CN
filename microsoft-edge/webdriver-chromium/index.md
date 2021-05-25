---
description: 了解如何在 WebDriver 中测试网站或Microsoft Edge或自动执行浏览器
title: 使用 WebDriver (Chromium) 实现测试自动化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/20/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge， Web 开发， html， css， javascript， 开发人员， webdriver， selenium， 测试， 工具， 自动化， 测试
ms.openlocfilehash: 5d30fe14051ac8857c6ea4d64b8c8f1f8e8049ac
ms.sourcegitcommit: a7609b75a94755ed983111af7083a0d3bf64eeac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2021
ms.locfileid: "11583585"
---
# <a name="use-webdriver-chromium-for-test-automation"></a><span data-ttu-id="52b31-104">使用 WebDriver (Chromium) 实现测试自动化</span><span class="sxs-lookup"><span data-stu-id="52b31-104">Use WebDriver (Chromium) for test automation</span></span>  

<span data-ttu-id="52b31-105">WebDriver 允许开发人员创建模拟用户交互的自动测试。</span><span class="sxs-lookup"><span data-stu-id="52b31-105">WebDriver allows developers to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="52b31-106">WebDriver 测试和模拟与 JavaScript 单元测试在以下方面有所不同。</span><span class="sxs-lookup"><span data-stu-id="52b31-106">WebDriver tests and simulations differ from JavaScript unit tests in the following ways.</span></span>  

*   <span data-ttu-id="52b31-107">访问在浏览器中运行的 JavaScript 不可用的功能和信息。</span><span class="sxs-lookup"><span data-stu-id="52b31-107">Accesses functionality and information not available to JavaScript running in browsers.</span></span>  
*   <span data-ttu-id="52b31-108">更精确地模拟用户事件或操作系统级事件。</span><span class="sxs-lookup"><span data-stu-id="52b31-108">Simulates user events or OS-level events more accurately.</span></span>  
*   <span data-ttu-id="52b31-109">在单个测试会话中管理多个窗口、选项卡和网页。</span><span class="sxs-lookup"><span data-stu-id="52b31-109">Manages multiple windows, tabs, and webpages in a single test session.</span></span>  
*   <span data-ttu-id="52b31-110">运行特定计算机上Microsoft Edge会话的会话。</span><span class="sxs-lookup"><span data-stu-id="52b31-110">Runs multiple sessions of Microsoft Edge on a specific machine.</span></span>  
    
<span data-ttu-id="52b31-111">以下部分介绍如何开始使用 WebDriver for Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="52b31-111">The following section describes how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  

## <a name="install-microsoft-edge-chromium"></a><span data-ttu-id="52b31-112">安装Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="52b31-112">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="52b31-113">确保安装[Microsoft Edge (Chromium) 。 ][MicrosoftEdge]</span><span class="sxs-lookup"><span data-stu-id="52b31-113">Ensure you install [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="52b31-114">若要确认已安装 \Microsoft Edge \ (Chromium\) ，请导航到 `edge://settings/help` ，并验证版本号是版本 75 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="52b31-114">To confirm that you have Microsoft Edge \(Chromium\) installed, navigate to `edge://settings/help`, and verify the version number is version 75 or later.</span></span>  

## <a name="download-microsoft-edge-driver"></a><span data-ttu-id="52b31-115">下载 Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="52b31-115">Download Microsoft Edge Driver</span></span>  

<span data-ttu-id="52b31-116">若要开始自动执行测试，请使用以下步骤来确保安装的 WebDriver 版本与浏览器版本相匹配。</span><span class="sxs-lookup"><span data-stu-id="52b31-116">To begin automating tests, use the following steps to ensure that the WebDriver version you install matches your browser version.</span></span>  

1.  <span data-ttu-id="52b31-117">查找你的Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="52b31-117">Find your version of Microsoft Edge.</span></span>  
    1.  <span data-ttu-id="52b31-118">导航到 `edge://settings/help`。</span><span class="sxs-lookup"><span data-stu-id="52b31-118">Navigate to `edge://settings/help`.</span></span>  
        
        :::image type="complex" source="./media/microsoft-edge-version.msft.png" alt-text="2021 年 4 Microsoft Edge 15 日" lightbox="./media/microsoft-edge-version.msft.png":::
           <span data-ttu-id="52b31-120">2021 年 4 Microsoft Edge 15 日</span><span class="sxs-lookup"><span data-stu-id="52b31-120">The build number for Microsoft Edge on April 15, 2021</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="52b31-121">导航到[Microsoft Edge驱动程序。][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]</span><span class="sxs-lookup"><span data-stu-id="52b31-121">Navigate to [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver].</span></span>  
1.  <span data-ttu-id="52b31-122">导航到 **获取最新版本**。</span><span class="sxs-lookup"><span data-stu-id="52b31-122">Navigate to **Get the latest version**.</span></span>  
1.  <span data-ttu-id="52b31-123">选择与你的版本版本号相匹配的频道Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="52b31-123">Choose the build of channel that matches your version number of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="./media/microsoft-edge-driver-install.msft.png" alt-text=""获取驱动程序"网页上的"获取Microsoft Edge部分" lightbox="./media/microsoft-edge-driver-install.msft.png":::
       <span data-ttu-id="52b31-125">"**获取驱动程序"网页上**的Microsoft Edge[部分][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]</span><span class="sxs-lookup"><span data-stu-id="52b31-125">The **Get the latest version** section on the [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] webpage</span></span>  
    :::image-end:::  
    
    <!--  
    > [!NOTE] 
    > For more information about test automation using Microsoft Edge \(EdgeHTML\), navigate to [Microsoft Edge Driver for Microsoft Edge (EdgeHTML)][Webdriver].  
    -->  
    
## <a name="choose-a-webdriver-language-binding"></a><span data-ttu-id="52b31-126">选择 WebDriver 语言绑定</span><span class="sxs-lookup"><span data-stu-id="52b31-126">Choose a WebDriver language binding</span></span>  

<span data-ttu-id="52b31-127">必须下载的最后一个组件是特定语言的客户端驱动程序，用于将代码 \ (Python、Java、C\#、Ruby、JavaScript\) 转换为 Microsoft Edge 驱动程序在 Microsoft Edge \ (Chromium\) 中运行的命令。</span><span class="sxs-lookup"><span data-stu-id="52b31-127">The last component you must download is a language-specific client driver to translate your code \(Python, Java, C\#, Ruby, JavaScript\) into commands the Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="52b31-128">[下载你选择的 WebDriver 语言绑定][SeleniumDownloads]。</span><span class="sxs-lookup"><span data-stu-id="52b31-128">[Download the WebDriver language binding of your choice][SeleniumDownloads].</span></span>  <span data-ttu-id="52b31-129">该Microsoft Edge推荐[Selenium 4.0.0-beta2][NugetPackagesSeleniumWebdriver400beta02]或更高版本，因为它支持 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="52b31-129">The Microsoft Edge team recommends [Selenium 4.0.0-beta2][NugetPackagesSeleniumWebdriver400beta02] or later, because it supports Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="52b31-130">但是，你可以控制所有较旧版本的 Selenium Microsoft Edge \ (Chromium\) ，包括当前稳定的 Selenium 3 版本。</span><span class="sxs-lookup"><span data-stu-id="52b31-130">However, you can control Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="52b31-131">如果之前使用 和 类自动Microsoft Edge \ (Chromium\) ，WebDriver 代码将不会在 Microsoft Edge `ChromeDriver` `ChromeOptions` 版本 80 或更高版本中运行。</span><span class="sxs-lookup"><span data-stu-id="52b31-131">If you previously automated or tested Microsoft Edge \(Chromium\) using `ChromeDriver` and `ChromeOptions` classes, your WebDriver code does not run on Microsoft Edge Version 80 or later.</span></span>  <span data-ttu-id="52b31-132">若要解决此问题，请更新测试以使用 类 `EdgeOptions` 并下载[Microsoft Edge驱动程序][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="52b31-132">To solve the problem, update your tests to use the `EdgeOptions` class and download [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver].</span></span>  

### <a name="using-selenium-4"></a><span data-ttu-id="52b31-133">使用 Selenium 4</span><span class="sxs-lookup"><span data-stu-id="52b31-133">Using Selenium 4</span></span>

<span data-ttu-id="52b31-134">Selenium 4 内置支持 Microsoft Edge (Chromium) 。</span><span class="sxs-lookup"><span data-stu-id="52b31-134">Selenium 4 has built-in support for Microsoft Edge (Chromium).</span></span>  <span data-ttu-id="52b31-135">若要安装 Selenium 4，请导航到["安装 Selenium 库"。][SeleniumInstallingLibraries]</span><span class="sxs-lookup"><span data-stu-id="52b31-135">To install Selenium 4, navigate to [Installing Selenium libraries][SeleniumInstallingLibraries].</span></span>

<span data-ttu-id="52b31-136">使用 Selenium 4 时，无需使用 Selenium Tools for Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="52b31-136">When you use Selenium 4, you don't need to use Selenium Tools for Microsoft Edge.</span></span>  <span data-ttu-id="52b31-137">适用于 Microsoft Edge 的 Selenium 工具仅适用于 Selenium 3。</span><span class="sxs-lookup"><span data-stu-id="52b31-137">Selenium Tools for Microsoft Edge is for Selenium 3 only.</span></span>  <span data-ttu-id="52b31-138">如果您尝试将 Selenium 4 与 Selenium Tools for Microsoft Edge并尝试创建新实例，则 `EdgeDriver` 收到以下错误： `System.MissingMethodException: 'Method not found: 'OpenQA.Selenium.Remote.DesiredCapabilities OpenQA.Selenium.DriverOptions.GenerateDesiredCapabilities(Boolean)'` 。</span><span class="sxs-lookup"><span data-stu-id="52b31-138">If you try to use Selenium 4 with Selenium Tools for Microsoft Edge and try create a new `EdgeDriver` instance, you get the following error: `System.MissingMethodException: 'Method not found: 'OpenQA.Selenium.Remote.DesiredCapabilities OpenQA.Selenium.DriverOptions.GenerateDesiredCapabilities(Boolean)'`.</span></span>  

<span data-ttu-id="52b31-139">如果你使用的是 Selenium 4 并收到此错误，请从项目中删除 ，并确保你正在使用命名空间中的 official 和 `Microsoft.Edge.SeleniumTools` `EdgeOptions` `EdgeDriver` `OpenQA.Selenium.Edge` 类。</span><span class="sxs-lookup"><span data-stu-id="52b31-139">If you're using Selenium 4 and get this error, remove `Microsoft.Edge.SeleniumTools` from your project, and make sure you're using the official `EdgeOptions` and `EdgeDriver` classes from the `OpenQA.Selenium.Edge` namespace.</span></span>

### <a name="using-selenium-3"></a><span data-ttu-id="52b31-140">使用 Selenium 3</span><span class="sxs-lookup"><span data-stu-id="52b31-140">Using Selenium 3</span></span>  

<span data-ttu-id="52b31-141">如果你已使用[Selenium 3，][|::ref1::|]你可能已有浏览器测试，并且希望添加 Microsoft Edge \ (Chromium\) 的覆盖范围，而无需更改 Selenium 版本。</span><span class="sxs-lookup"><span data-stu-id="52b31-141">If you already use [Selenium 3][|::ref1::|], you may have existing browser tests and want to add coverage for Microsoft Edge \(Chromium\) without changing your version of Selenium.</span></span>  <span data-ttu-id="52b31-142">若要使用[Selenium 3][|::ref2::|]为 Microsoft Edge \ (EdgeHTML\) 和 Microsoft Edge \ (Chromium\) 编写自动测试，请安装适用于 Microsoft Edge 的[Selenium 工具][GithubMicrosoftEdgeSeleniumTools]程序包以使用更新的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="52b31-142">To use [Selenium 3][|::ref2::|] to write automated tests for both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package to use the updated driver.</span></span>  <span data-ttu-id="52b31-143">工具 `EdgeDriver` `EdgeDriverService` 中包含的 和 类与 Selenium 4 中的内置等效项完全兼容。</span><span class="sxs-lookup"><span data-stu-id="52b31-143">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium 4.</span></span>  

<span data-ttu-id="52b31-144">使用以下步骤将[适用于][GithubMicrosoftEdgeSeleniumTools]Microsoft Edge 和[Selenium 3 的 Selenium][|::ref3::|]工具添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="52b31-144">Use the following steps to add the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] and [Selenium 3][|::ref3::|] to your project.</span></span>  

#### [<a name="c"></a><span data-ttu-id="52b31-145">C#</span><span class="sxs-lookup"><span data-stu-id="52b31-145">C#</span></span>](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="52b31-146">使用 CLI 或 Visual Studio 将[Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools]和[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410]程序包添加到[NuGet .NET][NugetCLI] [项目][VisualStudio]。</span><span class="sxs-lookup"><span data-stu-id="52b31-146">Add the [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] and [Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] packages to your .NET project using the [NuGet CLI][NugetCLI] or [Visual Studio][VisualStudio].</span></span>  

#### [<a name="python"></a><span data-ttu-id="52b31-147">Python</span><span class="sxs-lookup"><span data-stu-id="52b31-147">Python</span></span>](#tab/python/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="52b31-148">使用 [管道][PythonPip] 安装 [msedge-selenium-tools][PythonSeleniumTools] 和 [selenium][PythonSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="52b31-148">Use [pip][PythonPip] to install the [msedge-selenium-tools][PythonSeleniumTools] and [selenium][PythonSelenium] packages.</span></span>  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<a name="java"></a><span data-ttu-id="52b31-149">Java	</span><span class="sxs-lookup"><span data-stu-id="52b31-149">Java</span></span>](#tab/java/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="52b31-150">如果您的Java项目使用 Maven，将以下依赖项复制并粘贴到您的文件以添加 `pom.xml` [msedge-selenium-tools-java][SonatypeMavenRepositorySearch]。</span><span class="sxs-lookup"><span data-stu-id="52b31-150">If your Java project uses Maven, copy and paste the following dependency to your `pom.xml` file to add [msedge-selenium-tools-java][SonatypeMavenRepositorySearch].</span></span>  

```xml
<dependency>
    <groupId>com.microsoft.edge</groupId>
    <artifactId>msedge-selenium-tools-java</artifactId>
    <version>[3.141.0,)</version>
</dependency>
```  

<span data-ttu-id="52b31-151">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].</span><span class="sxs-lookup"><span data-stu-id="52b31-151">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].</span></span>  

#### [<a name="javascript"></a><span data-ttu-id="52b31-152">JavaScript</span><span class="sxs-lookup"><span data-stu-id="52b31-152">JavaScript</span></span>](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="52b31-153">使用 [npm][JavaScript|::ref4::|] 安装 [edge-selenium-tools][JavaScriptSeleniumTools] 和 [selenium-webdriver][JavaScriptSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="52b31-153">Use [npm][JavaScript|::ref4::|] to install the [edge-selenium-tools][JavaScriptSeleniumTools] and [selenium-webdriver][JavaScriptSelenium] packages.</span></span>  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## <a name="automate-microsoft-edge-chromium-with-webdriver"></a><span data-ttu-id="52b31-154">使用 WebDriver Microsoft Edge (Chromium) 自动执行部署</span><span class="sxs-lookup"><span data-stu-id="52b31-154">Automate Microsoft Edge (Chromium) with WebDriver</span></span>  

<span data-ttu-id="52b31-155">若要使用 WebDriver 自动化浏览器，必须先使用首选的 WebDriver 语言绑定启动 WebDriver 会话。</span><span class="sxs-lookup"><span data-stu-id="52b31-155">To automate a browser using WebDriver, you must first start a WebDriver session using your preferred WebDriver language binding.</span></span>  <span data-ttu-id="52b31-156">会话是使用 WebDriver 命令控制的浏览器的单个运行实例。</span><span class="sxs-lookup"><span data-stu-id="52b31-156">A session is a single running instance of a browser controlled using WebDriver commands.</span></span>  <span data-ttu-id="52b31-157">启动 WebDriver 会话以启动新的浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="52b31-157">Start a WebDriver session to launch a new browser instance.</span></span>  <span data-ttu-id="52b31-158">在关闭 WebDriver 会话之前，启动的浏览器实例保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="52b31-158">The launched browser instance remains open until you close the WebDriver session.</span></span>  

<span data-ttu-id="52b31-159">以下内容将引导你使用 Selenium 启动 WebDriver 会话，Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="52b31-159">The following content walks you through using Selenium to start a WebDriver session with Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="52b31-160">可以使用 Selenium 3 或 4 运行这些示例。</span><span class="sxs-lookup"><span data-stu-id="52b31-160">You can run the examples using either Selenium 3 or 4.</span></span>  <span data-ttu-id="52b31-161">若要与 Selenium 3 一起使用，必须安装适用于 Microsoft Edge 的[Selenium][GithubMicrosoftEdgeSeleniumTools]工具。</span><span class="sxs-lookup"><span data-stu-id="52b31-161">To use with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package must be installed.</span></span>  

### <a name="automate-microsoft-edge-chromium"></a><span data-ttu-id="52b31-162">自动Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="52b31-162">Automate Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="52b31-163">Selenium 使用 类管理 Microsoft Edge `EdgeDriver` \ (Chromium\) 会话。</span><span class="sxs-lookup"><span data-stu-id="52b31-163">Selenium uses the `EdgeDriver` class to manage a Microsoft Edge \(Chromium\) session.</span></span>  <span data-ttu-id="52b31-164">若要启动会话并自动Microsoft Edge \ (Chromium\) ，请创建一个新对象，并传递一个属性设置为 `EdgeDriver` `EdgeOptions` `UseChromium` 的对象 `true` 。</span><span class="sxs-lookup"><span data-stu-id="52b31-164">To start a session and automate Microsoft Edge \(Chromium\), create a new `EdgeDriver` object and pass it an `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<a name="c"></a><span data-ttu-id="52b31-165">C#</span><span class="sxs-lookup"><span data-stu-id="52b31-165">C#</span></span>](#tab/c-sharp/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a><span data-ttu-id="52b31-166">Python</span><span class="sxs-lookup"><span data-stu-id="52b31-166">Python</span></span>](#tab/python/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options = options)
```  

#### [<a name="java"></a><span data-ttu-id="52b31-167">Java	</span><span class="sxs-lookup"><span data-stu-id="52b31-167">Java</span></span>](#tab/java/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

<span data-ttu-id="52b31-168">该类 `EdgeDriver` 仅支持 Microsoft Edge \ (Chromium\) ，不支持 Microsoft Edge \ (EdgeHTML\) 。</span><span class="sxs-lookup"><span data-stu-id="52b31-168">The `EdgeDriver` class only supports Microsoft Edge \(Chromium\), and doesn't support Microsoft Edge \(EdgeHTML\).</span></span>  <span data-ttu-id="52b31-169">对于基本用法，可以在不提供 `EdgeDriver` 的情况下创建 `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="52b31-169">For basic usage, you can create an `EdgeDriver` without providing `EdgeOptions`.</span></span>  

```java
EdgeDriver driver = new EdgeDriver();
```  

#### [<a name="javascript"></a><span data-ttu-id="52b31-170">JavaScript</span><span class="sxs-lookup"><span data-stu-id="52b31-170">JavaScript</span></span>](#tab/javascript/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> <span data-ttu-id="52b31-171">如果你的 IT 管理员将[DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]策略设置为 ，Microsoft Edge 驱动程序被阻止驱动 `2` Microsoft Edge \ (Chromium\) ，因为驱动程序使用 Microsoft Edge [DevTools][DevtoolsIndex]。 [][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]</span><span class="sxs-lookup"><span data-stu-id="52b31-171">If your IT admin has set the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy to `2`,  [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] is blocked from driving Microsoft Edge \(Chromium\), because the driver uses the [Microsoft Edge DevTools][DevtoolsIndex].</span></span>  <span data-ttu-id="52b31-172">确保[将 DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]策略设置为 `0` 或 `1` 自动Microsoft Edge (Chromium) 。</span><span class="sxs-lookup"><span data-stu-id="52b31-172">Ensure the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy is set to `0` or `1` to automate Microsoft Edge (Chromium).</span></span>  

### <a name="choose-specific-browser-binaries-chromium-only"></a><span data-ttu-id="52b31-173">选择"特定浏览器二进制文件 (Chromium仅) </span><span class="sxs-lookup"><span data-stu-id="52b31-173">Choose Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="52b31-174">可以使用特定文件 \Microsoft Edge\ (Chromium\) WebDriver 会话。</span><span class="sxs-lookup"><span data-stu-id="52b31-174">You can start a WebDriver session with specific Microsoft Edge \(Chromium\) binaries.</span></span>  <span data-ttu-id="52b31-175">例如，可以使用预览频道（如[Microsoft Edge）][MicrosoftedgeinsiderDownload]运行Microsoft Edge Beta。</span><span class="sxs-lookup"><span data-stu-id="52b31-175">For example, you can run tests using the [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<a name="c"></a><span data-ttu-id="52b31-176">C#</span><span class="sxs-lookup"><span data-stu-id="52b31-176">C#</span></span>](#tab/c-sharp/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a><span data-ttu-id="52b31-177">Python</span><span class="sxs-lookup"><span data-stu-id="52b31-177">Python</span></span>](#tab/python/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options = options)
```  

#### [<a name="java"></a><span data-ttu-id="52b31-178">Java	</span><span class="sxs-lookup"><span data-stu-id="52b31-178">Java</span></span>](#tab/java/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.setBinary("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

EdgeDriver driver = new EdgeDriver(options);
```  

#### [<a name="javascript"></a><span data-ttu-id="52b31-179">JavaScript</span><span class="sxs-lookup"><span data-stu-id="52b31-179">JavaScript</span></span>](#tab/javascript/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <a name="customize-the-microsoft-edge-driver-service"></a><span data-ttu-id="52b31-180">自定义 Microsoft Edge 驱动程序服务</span><span class="sxs-lookup"><span data-stu-id="52b31-180">Customize the Microsoft Edge Driver Service</span></span>  

#### [<a name="c"></a><span data-ttu-id="52b31-181">C#</span><span class="sxs-lookup"><span data-stu-id="52b31-181">C#</span></span>](#tab/c-sharp/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="52b31-182">使用 类创建类实例时，它会为 `EdgeOptions` `EdgeDriver` Microsoft Edge `EdgeDriverService` \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 创建和启动相应的类。</span><span class="sxs-lookup"><span data-stu-id="52b31-182">When you use the `EdgeOptions` class to create an `EdgeDriver` class instance, it creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="52b31-183">如果要创建 ，请使用 方法创建一个配置为 Microsoft Edge `EdgeDriverService` `CreateChromiumService()` \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="52b31-183">If you want to create an `EdgeDriverService`, use the `CreateChromiumService()` method to create one configured for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="52b31-184">`CreateChromiumService()`当您需要添加自定义项时，该方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="52b31-184">The `CreateChromiumService()` method is useful when you need to add customizations.</span></span>  <span data-ttu-id="52b31-185">例如，以下代码开始详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="52b31-185">For example, the following code starts verbose log output.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
><span data-ttu-id="52b31-186">在传递给实例时，不需要 `EdgeOptions` 提供 `EdgeDriverService` `EdgeDriver` 对象。</span><span class="sxs-lookup"><span data-stu-id="52b31-186">You do not need to provide the `EdgeOptions` object when you pass `EdgeDriverService` to the `EdgeDriver` instance.</span></span>  <span data-ttu-id="52b31-187">该类根据你提供的服务使用 Microsoft Edge `EdgeDriver` \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 的默认选项。</span><span class="sxs-lookup"><span data-stu-id="52b31-187">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) based on the service you provide.</span></span>  
> <span data-ttu-id="52b31-188">但是，如果要同时提供 和 类，请确保为同一版本的 `EdgeDriverService` `EdgeOptions` Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="52b31-188">However, if you want to provide both `EdgeDriverService` and `EdgeOptions` classes, ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="52b31-189">例如，可以使用默认的 Microsoft Edge \ (EdgeHTML\) `EdgeDriverService` 类Chromium属性 `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="52b31-189">For example, you may use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="52b31-190">`EdgeDriver`该类会引发错误，以阻止使用不同的版本。</span><span class="sxs-lookup"><span data-stu-id="52b31-190">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<a name="python"></a><span data-ttu-id="52b31-191">Python</span><span class="sxs-lookup"><span data-stu-id="52b31-191">Python</span></span>](#tab/python/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="52b31-192">使用 Python 时， `Edge` 对象将创建和管理 `EdgeService` 。</span><span class="sxs-lookup"><span data-stu-id="52b31-192">When you use Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="52b31-193">若要配置 `EdgeService` ，请向 对象传递 `Edge` 额外参数，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="52b31-193">To configure the `EdgeService`, pass extra arguments to the `Edge` object as indicated in the following code.</span></span>  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<a name="java"></a><span data-ttu-id="52b31-194">Java	</span><span class="sxs-lookup"><span data-stu-id="52b31-194">Java</span></span>](#tab/java/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="52b31-195">使用 `createDefaultService()` 方法可创建 `EdgeDriverService` 一个配置为 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="52b31-195">Use the `createDefaultService()` method to create an `EdgeDriverService` configured for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="52b31-196">使用 Java 系统属性自定义 Java 中的驱动程序服务。</span><span class="sxs-lookup"><span data-stu-id="52b31-196">Use Java system properties to customize driver services in Java.</span></span>  <span data-ttu-id="52b31-197">例如，以下代码使用 `"webdriver.edge.verboseLogging"` 属性打开详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="52b31-197">For example, the following code uses the `"webdriver.edge.verboseLogging"` property to turn on verbose log output.</span></span>  

```java
System.setProperty("webdriver.edge.verboseLogging", "true");
EdgeDriverService service = EdgeDriverService.createDefaultService();
EdgeOptions options = new EdgeOptions();
EdgeDriver driver = new EdgeDriver(service, options);
```  

#### [<a name="javascript"></a><span data-ttu-id="52b31-198">JavaScript</span><span class="sxs-lookup"><span data-stu-id="52b31-198">JavaScript</span></span>](#tab/javascript/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="52b31-199">使用 JavaScript 时，请使用 类 `Service` 创建和 `ServiceBuilder` 配置 。</span><span class="sxs-lookup"><span data-stu-id="52b31-199">When you use JavaScript, create and configure a `Service` with the `ServiceBuilder` class.</span></span>  <span data-ttu-id="52b31-200">（可选）可以将对象传递给对象，该对象将启动 `Service` `Driver` \ (并停止\) 服务。</span><span class="sxs-lookup"><span data-stu-id="52b31-200">Optionally, you can pass the `Service` object to the `Driver` object, which starts \(and stops\) the service for you.</span></span>  
<span data-ttu-id="52b31-201">若要配置 `Service` ，请运行 类中的另一 `ServiceBuilder` 个方法，然后再使用 `build()` 方法。</span><span class="sxs-lookup"><span data-stu-id="52b31-201">To configure the `Service`, run another method in the `ServiceBuilder` class before you use the `build()` method.</span></span>  <span data-ttu-id="52b31-202">然后， `service` 在 方法中将 作为 参数 `Driver.createSession()` 传递。</span><span class="sxs-lookup"><span data-stu-id="52b31-202">Then pass the `service` as a parameter in the `Driver.createSession()` method.</span></span>  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <a name="use-chromium-specific-options"></a><span data-ttu-id="52b31-203">使用Chromium-Specific选项</span><span class="sxs-lookup"><span data-stu-id="52b31-203">Use Chromium-Specific Options</span></span>  

<span data-ttu-id="52b31-204">如果将 属性设置为 ，可以使用 类来访问Chromium自动化其他浏览器时所使用的特定于 Chromium `UseChromium` `true` `EdgeOptions` 的属性和方法。 [][WebdriverCapabilitiesEdgeOptions]</span><span class="sxs-lookup"><span data-stu-id="52b31-204">If you set the `UseChromium` property to `true`, you can use the `EdgeOptions` class to access the same [Chromium-specific properties and methods][WebdriverCapabilitiesEdgeOptions] that are used when you automate other Chromium browsers.</span></span>  

#### [<a name="c"></a><span data-ttu-id="52b31-205">C#</span><span class="sxs-lookup"><span data-stu-id="52b31-205">C#</span></span>](#tab/c-sharp/)  

<a id="use-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<a name="python"></a><span data-ttu-id="52b31-206">Python</span><span class="sxs-lookup"><span data-stu-id="52b31-206">Python</span></span>](#tab/python/)  

<a id="use-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<a name="java"></a><span data-ttu-id="52b31-207">Java	</span><span class="sxs-lookup"><span data-stu-id="52b31-207">Java</span></span>](#tab/java/)  

<a id="use-chromium-specific-options-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

#### [<a name="javascript"></a><span data-ttu-id="52b31-208">JavaScript</span><span class="sxs-lookup"><span data-stu-id="52b31-208">JavaScript</span></span>](#tab/javascript/)  

<a id="use-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

* * *  

> [!NOTE]
> <span data-ttu-id="52b31-209">如果属性设置为 ，则不能对 Microsoft Edge `UseChromium` `true` \ (EdgeHTML\) 。</span><span class="sxs-lookup"><span data-stu-id="52b31-209">If the `UseChromium` property is set to `true`, you are not able to use properties and methods for Microsoft Edge \(EdgeHTML\).</span></span>  

## <a name="other-webdriver-installation-options"></a><span data-ttu-id="52b31-210">其他 WebDriver 安装选项</span><span class="sxs-lookup"><span data-stu-id="52b31-210">Other WebDriver installation options</span></span>  

### <a name="docker"></a><span data-ttu-id="52b31-211">Docker</span><span class="sxs-lookup"><span data-stu-id="52b31-211">Docker</span></span>  

<span data-ttu-id="52b31-212">如果使用[Docker，][DockerHub]请运行以下命令，下载预配置映像Microsoft Edge \ (Chromium\) Microsoft Edge[驱动程序][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]预安装。</span><span class="sxs-lookup"><span data-stu-id="52b31-212">If you use [Docker][DockerHub], run the following command to download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] pre-installed.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="52b31-213">有关详细信息，请导航到 Docker Hub 上的 [msedgedriver 容器][DockerHubMsedgedriver]。</span><span class="sxs-lookup"><span data-stu-id="52b31-213">For more information, navigate to the [msedgedriver container on Docker Hub][DockerHubMsedgedriver].</span></span>  

## <a name="next-steps"></a><span data-ttu-id="52b31-214">后续步骤</span><span class="sxs-lookup"><span data-stu-id="52b31-214">Next steps</span></span>  

<span data-ttu-id="52b31-215">有关 WebDriver 和如何使用 Selenium 编写自动 WebDriver 测试的信息，请导航到 [Selenium 文档][SeleniumDocumentation]。</span><span class="sxs-lookup"><span data-stu-id="52b31-215">For more information about WebDriver and how to write automated WebDriver tests using Selenium, navigate to the [Selenium documentation][SeleniumDocumentation].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="52b31-216">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="52b31-216">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="52b31-217">该Microsoft Edge团队希望倾听你有关使用 WebDriver、Selenium 和 Microsoft Edge 的反馈。</span><span class="sxs-lookup"><span data-stu-id="52b31-217">The Microsoft Edge team is eager to hear your feedback about using WebDriver, Selenium, and Microsoft Edge.</span></span>  <span data-ttu-id="52b31-218">若要向团队发送你的问题和意见，请选择开发人员工具Microsoft Edge\*\*\*\* 发送反馈图标或发送推文[@EdgeDevTools。][TwitterTweetEdgeDevTools]</span><span class="sxs-lookup"><span data-stu-id="52b31-218">To send the team your questions and comments, choose the **Send Feedback** icon in the Microsoft Edge DevTools or send a tweet [@EdgeDevTools][TwitterTweetEdgeDevTools].</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="52b31-220">Microsoft Edge DevTools 中的**发送反馈**图标</span><span class="sxs-lookup"><span data-stu-id="52b31-220">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- links -->  

[DevtoolsIndex]: ../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[WebdriverCapabilitiesEdgeOptions]: ./capabilities-edge-options.md "功能和 EdgeOptions |Microsoft Docs"  

<!--[Webdriver]: /archive/microsoft-edge/legacy/developer/webdriver/index "WebDriver (EdgeHTML) | Microsoft Docs"  -->  

[DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability - Microsoft Edge - 策略|Microsoft Docs"  

[DockerHub]: https://hub.docker.com "Docker Hub"  
[DockerHubMsedgedriver]: https://hub.docker.com/_/microsoft-msedge-msedgedriver?tab=description "msedgedriver |Docker 中心"  

[GithubMicrosoftEdgeSeleniumTools]: https://github.com/microsoft/edge-selenium-tools "microsoft/edge-selenium-tools |GitHub"  
[GithubMicrosoftEdgeSeleniumToolsReleases]: https://github.com/microsoft/edge-selenium-tools/releases "microsoft/edge-selenium-tools |GitHub"  
[GithubSeleniumHq]: https://github.com/SeleniumHQ/selenium "SeleniumHQ/selenium |GitHub"  

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
[SeleniumDownloads]: https://selenium.dev/downloads "下载|Selenium"  
[SeleniumInstallingLibraries]: https://www.selenium.dev/documentation/en/selenium_installation/installing_selenium_libraries "安装 Selenium 库|Selenium"

[SonatypeMavenRepositorySearch]: https://search.maven.org/artifact/com.microsoft.edge/msedge-selenium-tools-java/3.141.0/jar "sonatype Maven Central Repository Search |com.microsoft.edge：msedge-selenium-tools-java"

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |发布推文"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |W3C"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无头浏览器|Wikipedia"  
