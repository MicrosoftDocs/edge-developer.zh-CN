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
# <a name="use-webdriver-chromium-for-test-automation"></a><span data-ttu-id="b10dd-104">使用 WebDriver (Chromium) 实现测试自动化</span><span class="sxs-lookup"><span data-stu-id="b10dd-104">Use WebDriver (Chromium) for test automation</span></span>  

<span data-ttu-id="b10dd-105">WebDriver 允许开发人员创建模拟用户交互的自动测试。</span><span class="sxs-lookup"><span data-stu-id="b10dd-105">WebDriver allows developers to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="b10dd-106">WebDriver 测试和模拟与 JavaScript 单元测试在以下方面有所不同。</span><span class="sxs-lookup"><span data-stu-id="b10dd-106">WebDriver tests and simulations differ from JavaScript unit tests in the following ways.</span></span>  

*   <span data-ttu-id="b10dd-107">访问在浏览器中运行的 JavaScript 不可用的功能和信息。</span><span class="sxs-lookup"><span data-stu-id="b10dd-107">Accesses functionality and information not available to JavaScript running in browsers.</span></span>  
*   <span data-ttu-id="b10dd-108">更精确地模拟用户事件或操作系统级事件。</span><span class="sxs-lookup"><span data-stu-id="b10dd-108">Simulates user events or OS-level events more accurately.</span></span>  
*   <span data-ttu-id="b10dd-109">在单个测试会话中管理多个窗口、选项卡和网页。</span><span class="sxs-lookup"><span data-stu-id="b10dd-109">Manages multiple windows, tabs, and webpages in a single test session.</span></span>  
*   <span data-ttu-id="b10dd-110">运行特定计算机上Microsoft Edge会话的会话。</span><span class="sxs-lookup"><span data-stu-id="b10dd-110">Runs multiple sessions of Microsoft Edge on a specific machine.</span></span>  


## <a name="relationship-between-webdriver-and-other-software"></a><span data-ttu-id="b10dd-111">WebDriver 和其他软件之间的关系</span><span class="sxs-lookup"><span data-stu-id="b10dd-111">Relationship between WebDriver and other software</span></span>

<span data-ttu-id="b10dd-112">若要自动Microsoft Edge WebDriver 自动执行用户交互，您需要三个组件：</span><span class="sxs-lookup"><span data-stu-id="b10dd-112">To automate Microsoft Edge with WebDriver to simulate user interaction, you need three components:</span></span>

*  <span data-ttu-id="b10dd-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b10dd-113">Microsoft Edge</span></span>
*  <span data-ttu-id="b10dd-114">Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="b10dd-114">Microsoft Edge Driver</span></span>
*  <span data-ttu-id="b10dd-115">WebDriver 测试框架</span><span class="sxs-lookup"><span data-stu-id="b10dd-115">A WebDriver testing framework</span></span>

<span data-ttu-id="b10dd-116">这些组件之间的功能关系如下所示。</span><span class="sxs-lookup"><span data-stu-id="b10dd-116">The functional relationship between these components is as follows.</span></span>

| <span data-ttu-id="b10dd-117">技术</span><span class="sxs-lookup"><span data-stu-id="b10dd-117">Technology</span></span> | <span data-ttu-id="b10dd-118">角色</span><span class="sxs-lookup"><span data-stu-id="b10dd-118">Role</span></span> |
|---|---|
| <span data-ttu-id="b10dd-119">WebDriver</span><span class="sxs-lookup"><span data-stu-id="b10dd-119">WebDriver</span></span> | <span data-ttu-id="b10dd-120">适用于平台和中性语言的线路协议的 W3C 标准。</span><span class="sxs-lookup"><span data-stu-id="b10dd-120">A W3C standard for a platform- and language-neutral wire protocol.</span></span>  <span data-ttu-id="b10dd-121">此协议允许进程外程序远程指示 Web 浏览器的行为。</span><span class="sxs-lookup"><span data-stu-id="b10dd-121">This protocol allows out-of-process programs to remotely instruct the behavior of web browsers.</span></span> |
| <span data-ttu-id="b10dd-122">Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="b10dd-122">Microsoft Edge Driver</span></span> | <span data-ttu-id="b10dd-123">Microsoft 专为用户实现 WebDriver Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b10dd-123">Microsoft's implementation of the WebDriver protocol specifically for Microsoft Edge.</span></span>  <span data-ttu-id="b10dd-124">测试作者编写使用驱动程序收到的 WebDriver Microsoft Edge的测试。</span><span class="sxs-lookup"><span data-stu-id="b10dd-124">Test authors write tests that use WebDriver commands that Microsoft Edge Driver receives.</span></span>  <span data-ttu-id="b10dd-125">Microsoft Edge然后，驱动程序负责将该命令与浏览器通信。</span><span class="sxs-lookup"><span data-stu-id="b10dd-125">Microsoft Edge Driver is then responsible for communicating that command to the browser.</span></span> |
| <span data-ttu-id="b10dd-126">WebDriver 测试框架</span><span class="sxs-lookup"><span data-stu-id="b10dd-126">A WebDriver testing framework</span></span> | <span data-ttu-id="b10dd-127">测试作者使用测试框架编写端到端测试并自动化浏览器。</span><span class="sxs-lookup"><span data-stu-id="b10dd-127">Test authors use a testing framework to write end-to-end tests and automate browsers.</span></span>  <span data-ttu-id="b10dd-128">提供一个特定语言的接口，该接口将你的代码转换为Microsoft Edge在 \ (Chromium\Microsoft Edge \) 中运行的命令。</span><span class="sxs-lookup"><span data-stu-id="b10dd-128">Provides a language-specific interface that translates your code into commands that Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="b10dd-129">WebDriver 测试框架适用于所有主要平台和语言。</span><span class="sxs-lookup"><span data-stu-id="b10dd-129">WebDriver testing frameworks exist for all major platforms and languages.</span></span>  <span data-ttu-id="b10dd-130">这样的框架之一是 Selenium。</span><span class="sxs-lookup"><span data-stu-id="b10dd-130">One such framework is Selenium.</span></span> |
| <span data-ttu-id="b10dd-131">Internet Explorer驱动程序</span><span class="sxs-lookup"><span data-stu-id="b10dd-131">Internet Explorer Driver</span></span> | <span data-ttu-id="b10dd-132">专用于 webDriver 协议的实现Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="b10dd-132">An implementation of the WebDriver protocol specifically for Internet Explorer.</span></span>  <span data-ttu-id="b10dd-133">若要为用户运行旧版端到端测试Internet Explorer，我们建议使用 Internet Explorer Driver。</span><span class="sxs-lookup"><span data-stu-id="b10dd-133">To run legacy end-to-end tests for Internet Explorer, we recommend using Internet Explorer Driver.</span></span> |

<span data-ttu-id="b10dd-134">以下各节介绍如何开始使用 WebDriver for Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-134">The following sections describe how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  


## <a name="install-microsoft-edge-chromium"></a><span data-ttu-id="b10dd-135">安装Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="b10dd-135">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="b10dd-136">确保安装[Microsoft Edge (Chromium) 。 ][MicrosoftEdge]</span><span class="sxs-lookup"><span data-stu-id="b10dd-136">Ensure you install [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="b10dd-137">若要确认已安装 \Microsoft Edge \ (Chromium\) ，请导航到 ，并验证版本号是 `edge://settings/help` 75 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="b10dd-137">To confirm that you have Microsoft Edge \(Chromium\) installed, navigate to `edge://settings/help`, and verify that the version number is 75 or later.</span></span>


## <a name="download-microsoft-edge-driver"></a><span data-ttu-id="b10dd-138">下载 Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="b10dd-138">Download Microsoft Edge Driver</span></span>

<span data-ttu-id="b10dd-139">若要开始自动执行测试，请使用以下步骤来确保安装的 WebDriver 版本与浏览器版本相匹配。</span><span class="sxs-lookup"><span data-stu-id="b10dd-139">To begin automating tests, use the following steps to ensure that the WebDriver version you install matches your browser version.</span></span>  

1.  <span data-ttu-id="b10dd-140">查找你的Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b10dd-140">Find your version of Microsoft Edge.</span></span>  
    1.  <span data-ttu-id="b10dd-141">导航到 `edge://settings/help`。</span><span class="sxs-lookup"><span data-stu-id="b10dd-141">Navigate to `edge://settings/help`.</span></span>  
        
        :::image type="complex" source="./media/microsoft-edge-version.msft.png" alt-text="2021 年 4 Microsoft Edge 15 日" lightbox="./media/microsoft-edge-version.msft.png":::
           <span data-ttu-id="b10dd-143">2021 年 4 Microsoft Edge 15 日</span><span class="sxs-lookup"><span data-stu-id="b10dd-143">The build number for Microsoft Edge on April 15, 2021</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="b10dd-144">导航到[Microsoft Edge驱动程序。][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]</span><span class="sxs-lookup"><span data-stu-id="b10dd-144">Navigate to [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver].</span></span>  
1.  <span data-ttu-id="b10dd-145">导航到 **获取最新版本**。</span><span class="sxs-lookup"><span data-stu-id="b10dd-145">Navigate to **Get the latest version**.</span></span>  
1.  <span data-ttu-id="b10dd-146">选择与你的版本版本号相匹配的频道Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b10dd-146">Choose the build of channel that matches your version number of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="./media/microsoft-edge-driver-install.msft.png" alt-text=""获取驱动程序"网页上的"获取Microsoft Edge部分" lightbox="./media/microsoft-edge-driver-install.msft.png":::
       <span data-ttu-id="b10dd-148">"**获取驱动程序"网页上**的Microsoft Edge[部分][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]</span><span class="sxs-lookup"><span data-stu-id="b10dd-148">The **Get the latest version** section on the [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] webpage</span></span>  
    :::image-end:::  
   
    
## <a name="choose-a-webdriver-testing-framework"></a><span data-ttu-id="b10dd-149">选择 WebDriver 测试框架</span><span class="sxs-lookup"><span data-stu-id="b10dd-149">Choose a WebDriver testing framework</span></span>

<span data-ttu-id="b10dd-150">下载驱动程序Microsoft Edge，必须下载的最后一个组件是 WebDriver 测试框架。</span><span class="sxs-lookup"><span data-stu-id="b10dd-150">After downloading Microsoft Edge Driver, the last component you must download is a WebDriver testing framework.</span></span> <span data-ttu-id="b10dd-151">测试作者使用 WebDriver 测试框架编写端到端测试并自动化浏览器。</span><span class="sxs-lookup"><span data-stu-id="b10dd-151">Test authors use WebDriver testing frameworks to write end-to-end tests and automate browsers.</span></span> <span data-ttu-id="b10dd-152">框架提供特定于语言的接口，该接口将代码 (（如 Python、Java、C#、Ruby 或 JavaScript) ）转换为 Microsoft Edge Driver 在 Microsoft Edge \ (Chromium\) 中运行的命令。</span><span class="sxs-lookup"><span data-stu-id="b10dd-152">The framework provides a language-specific interface that translates your code (such as Python, Java, C#, Ruby, or JavaScript) into commands that Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span> <span data-ttu-id="b10dd-153">WebDriver 测试框架适用于所有主要平台和语言。</span><span class="sxs-lookup"><span data-stu-id="b10dd-153">WebDriver testing frameworks exist for all major platforms and languages.</span></span>


<span data-ttu-id="b10dd-154">本文提供了有关使用 Selenium 框架的说明，但您可以使用任何支持 WebDriver 的库、框架和编程语言。</span><span class="sxs-lookup"><span data-stu-id="b10dd-154">This article provides instructions for using the Selenium framework, but you can use any library, framework, and programming language that supports WebDriver.</span></span>  <span data-ttu-id="b10dd-155">若要使用除 Selenium 外的其他 WebDriver 测试框架完成相同的任务，请参考您所选择的框架的官方文档。</span><span class="sxs-lookup"><span data-stu-id="b10dd-155">To accomplish the same tasks using a WebDriver testing framework other than Selenium, consult the official documentation for your framework of choice.</span></span>

<span data-ttu-id="b10dd-156">如果你使用的是 Selenium，Microsoft Edge 团队建议使用[Selenium 4.0.0-beta2][NugetPackagesSeleniumWebdriver400beta02]或更高版本，因为该版本的 Selenium 支持 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-156">If you are using Selenium, the Microsoft Edge team recommends [Selenium 4.0.0-beta2][NugetPackagesSeleniumWebdriver400beta02] or later, because that version of Selenium supports Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="b10dd-157">但是，你可以控制所有较旧版本的 Selenium Microsoft Edge \ (Chromium\) ，包括当前稳定的 Selenium 3 版本。</span><span class="sxs-lookup"><span data-stu-id="b10dd-157">However, you can control Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="b10dd-158">如果之前使用 和 类自动Microsoft Edge \ (Chromium\) ，WebDriver 代码将不会在 Microsoft Edge `ChromeDriver` `ChromeOptions` 版本 80 或更高版本中运行。</span><span class="sxs-lookup"><span data-stu-id="b10dd-158">If you previously automated or tested Microsoft Edge \(Chromium\) using `ChromeDriver` and `ChromeOptions` classes, your WebDriver code does not run on Microsoft Edge Version 80 or later.</span></span>  <span data-ttu-id="b10dd-159">若要解决此问题，请更新测试以使用 类 `EdgeOptions` 并下载[Microsoft Edge驱动程序][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="b10dd-159">To solve the problem, update your tests to use the `EdgeOptions` class and download [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver].</span></span>  

### <a name="using-selenium-4"></a><span data-ttu-id="b10dd-160">使用 Selenium 4</span><span class="sxs-lookup"><span data-stu-id="b10dd-160">Using Selenium 4</span></span>

<span data-ttu-id="b10dd-161">Selenium WebDriver 测试框架可用于任何平台，可用于 Java、Python、C#、Ruby 和 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="b10dd-161">The Selenium WebDriver testing framework can be used on any platform, and is available for Java, Python, C#, Ruby, and JavaScript.</span></span>

<span data-ttu-id="b10dd-162">Selenium 4 内置支持 Microsoft Edge (Chromium) 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-162">Selenium 4 has built-in support for Microsoft Edge (Chromium).</span></span>  <span data-ttu-id="b10dd-163">若要安装 Selenium 4，请导航到["安装 Selenium 库"。][SeleniumInstallingLibraries]</span><span class="sxs-lookup"><span data-stu-id="b10dd-163">To install Selenium 4, navigate to [Installing Selenium libraries][SeleniumInstallingLibraries].</span></span>

<span data-ttu-id="b10dd-164">如果使用 Selenium 4，则无需使用 Selenium Tools for Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b10dd-164">If you use Selenium 4, you don't need to use Selenium Tools for Microsoft Edge.</span></span>  <span data-ttu-id="b10dd-165">Selenium Tools for Microsoft Edge仅适用于 Selenium 3。</span><span class="sxs-lookup"><span data-stu-id="b10dd-165">Selenium Tools for Microsoft Edge are for Selenium 3 only.</span></span>  <span data-ttu-id="b10dd-166">如果您尝试将 Selenium 4 与 Selenium Tools for Microsoft Edge并尝试创建新实例，则 `EdgeDriver` 收到以下错误： `System.MissingMethodException: 'Method not found: 'OpenQA.Selenium.Remote.DesiredCapabilities OpenQA.Selenium.DriverOptions.GenerateDesiredCapabilities(Boolean)'` 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-166">If you try to use Selenium 4 with Selenium Tools for Microsoft Edge and try to create a new `EdgeDriver` instance, you get the following error: `System.MissingMethodException: 'Method not found: 'OpenQA.Selenium.Remote.DesiredCapabilities OpenQA.Selenium.DriverOptions.GenerateDesiredCapabilities(Boolean)'`.</span></span>  

<span data-ttu-id="b10dd-167">如果你使用的是 Selenium 4 并收到此错误，请从项目中删除 ，并确保你正在使用命名空间中的 official 和 `Microsoft.Edge.SeleniumTools` `EdgeOptions` `EdgeDriver` `OpenQA.Selenium.Edge` 类。</span><span class="sxs-lookup"><span data-stu-id="b10dd-167">If you're using Selenium 4 and get this error, remove `Microsoft.Edge.SeleniumTools` from your project, and make sure you're using the official `EdgeOptions` and `EdgeDriver` classes from the `OpenQA.Selenium.Edge` namespace.</span></span>

### <a name="using-selenium-3"></a><span data-ttu-id="b10dd-168">使用 Selenium 3</span><span class="sxs-lookup"><span data-stu-id="b10dd-168">Using Selenium 3</span></span>  

<span data-ttu-id="b10dd-169">如果你已使用[Selenium 3，][|::ref1::|]你可能已有浏览器测试，并且希望添加 Microsoft Edge \ (Chromium\) 的覆盖范围，而无需更改 Selenium 版本。</span><span class="sxs-lookup"><span data-stu-id="b10dd-169">If you already use [Selenium 3][|::ref1::|], you may have existing browser tests and want to add coverage for Microsoft Edge \(Chromium\) without changing your version of Selenium.</span></span>  <span data-ttu-id="b10dd-170">若要使用[Selenium 3][|::ref2::|]为 Microsoft Edge \ (EdgeHTML\) 和 Microsoft Edge \ (Chromium\) 编写自动测试，请安装适用于 Microsoft Edge 的[Selenium 工具][GithubMicrosoftEdgeSeleniumTools]程序包以使用更新的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="b10dd-170">To use [Selenium 3][|::ref2::|] to write automated tests for both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package to use the updated driver.</span></span>  <span data-ttu-id="b10dd-171">工具 `EdgeDriver` `EdgeDriverService` 中包含的 和 类与 Selenium 4 中的内置等效项完全兼容。</span><span class="sxs-lookup"><span data-stu-id="b10dd-171">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium 4.</span></span>  

<span data-ttu-id="b10dd-172">如果使用的是 Selenium 3，请使用以下步骤将适用于 Microsoft Edge[和 Selenium 3][|::ref3::|] [的 Selenium][GithubMicrosoftEdgeSeleniumTools]工具添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="b10dd-172">If you are using Selenium 3, use the following steps to add the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] and [Selenium 3][|::ref3::|] to your project.</span></span>

#### [<a name="c"></a><span data-ttu-id="b10dd-173">C#</span><span class="sxs-lookup"><span data-stu-id="b10dd-173">C#</span></span>](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="b10dd-174">使用 CLI 或 Visual Studio 将[Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools]和[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410]程序包添加到[NuGet .NET][NugetCLI] [项目][VisualStudio]。</span><span class="sxs-lookup"><span data-stu-id="b10dd-174">Add the [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] and [Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] packages to your .NET project using the [NuGet CLI][NugetCLI] or [Visual Studio][VisualStudio].</span></span>  

#### [<a name="python"></a><span data-ttu-id="b10dd-175">Python</span><span class="sxs-lookup"><span data-stu-id="b10dd-175">Python</span></span>](#tab/python/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="b10dd-176">使用 [管道][PythonPip] 安装 [msedge-selenium-tools][PythonSeleniumTools] 和 [selenium][PythonSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="b10dd-176">Use [pip][PythonPip] to install the [msedge-selenium-tools][PythonSeleniumTools] and [selenium][PythonSelenium] packages.</span></span>  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<a name="java"></a><span data-ttu-id="b10dd-177">Java	</span><span class="sxs-lookup"><span data-stu-id="b10dd-177">Java</span></span>](#tab/java/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="b10dd-178">如果您的Java项目使用 Maven，将以下依赖项复制并粘贴到您的文件以添加 `pom.xml` [msedge-selenium-tools-java][SonatypeMavenRepositorySearch]。</span><span class="sxs-lookup"><span data-stu-id="b10dd-178">If your Java project uses Maven, copy and paste the following dependency to your `pom.xml` file to add [msedge-selenium-tools-java][SonatypeMavenRepositorySearch].</span></span>  

```xml
<dependency>
    <groupId>com.microsoft.edge</groupId>
    <artifactId>msedge-selenium-tools-java</artifactId>
    <version>[3.141.0,)</version>
</dependency>
```  

<span data-ttu-id="b10dd-179">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].</span><span class="sxs-lookup"><span data-stu-id="b10dd-179">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].</span></span>  

#### [<a name="javascript"></a><span data-ttu-id="b10dd-180">JavaScript</span><span class="sxs-lookup"><span data-stu-id="b10dd-180">JavaScript</span></span>](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="b10dd-181">使用 [npm][JavaScript|::ref4::|] 安装 [edge-selenium-tools][JavaScriptSeleniumTools] 和 [selenium-webdriver][JavaScriptSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="b10dd-181">Use [npm][JavaScript|::ref4::|] to install the [edge-selenium-tools][JavaScriptSeleniumTools] and [selenium-webdriver][JavaScriptSelenium] packages.</span></span>  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  


## <a name="automate-microsoft-edge-chromium-with-webdriver"></a><span data-ttu-id="b10dd-182">使用 WebDriver Microsoft Edge (Chromium) 自动执行部署</span><span class="sxs-lookup"><span data-stu-id="b10dd-182">Automate Microsoft Edge (Chromium) with WebDriver</span></span>  

<span data-ttu-id="b10dd-183">若要使用 WebDriver 自动化浏览器，必须先使用首选的 WebDriver 测试框架启动 WebDriver 会话。</span><span class="sxs-lookup"><span data-stu-id="b10dd-183">To automate a browser using WebDriver, you must first start a WebDriver session using your preferred WebDriver testing framework.</span></span>  <span data-ttu-id="b10dd-184">会话是使用 WebDriver 命令控制的浏览器的单个运行实例。</span><span class="sxs-lookup"><span data-stu-id="b10dd-184">A session is a single running instance of a browser controlled using WebDriver commands.</span></span>  <span data-ttu-id="b10dd-185">启动 WebDriver 会话以启动新的浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="b10dd-185">Start a WebDriver session to launch a new browser instance.</span></span>  <span data-ttu-id="b10dd-186">在关闭 WebDriver 会话之前，启动的浏览器实例保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="b10dd-186">The launched browser instance remains open until you close the WebDriver session.</span></span>  

<span data-ttu-id="b10dd-187">以下内容将引导你使用 Selenium 启动 WebDriver 会话，Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-187">The following content walks you through using Selenium to start a WebDriver session with Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="b10dd-188">可以使用 Selenium 3 或 4 运行这些示例。</span><span class="sxs-lookup"><span data-stu-id="b10dd-188">You can run these examples using either Selenium 3 or 4.</span></span>  <span data-ttu-id="b10dd-189">若要将 WebDriver 与 Selenium 3 一同使用，必须安装适用于 Microsoft Edge 的[Selenium][GithubMicrosoftEdgeSeleniumTools]工具包。</span><span class="sxs-lookup"><span data-stu-id="b10dd-189">To use WebDriver with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package must be installed.</span></span>  

> [!NOTE]
> <span data-ttu-id="b10dd-190">本文提供了有关使用 Selenium 框架的说明，但您可以使用任何支持 WebDriver 的库、框架和编程语言。</span><span class="sxs-lookup"><span data-stu-id="b10dd-190">This article provides instructions for using the Selenium framework, but you can use any library, framework, and programming language that supports WebDriver.</span></span>  <span data-ttu-id="b10dd-191">若要使用另一个框架完成相同的任务，请参阅您所选择的框架的官方文档。</span><span class="sxs-lookup"><span data-stu-id="b10dd-191">To accomplish the same tasks using another framework, consult the official documentation for your framework of choice.</span></span>

### <a name="automate-microsoft-edge-chromium"></a><span data-ttu-id="b10dd-192">自动Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="b10dd-192">Automate Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="b10dd-193">Selenium 使用 类管理 Microsoft Edge `EdgeDriver` \ (Chromium\) 会话。</span><span class="sxs-lookup"><span data-stu-id="b10dd-193">Selenium uses the `EdgeDriver` class to manage a Microsoft Edge \(Chromium\) session.</span></span>  <span data-ttu-id="b10dd-194">若要启动会话并自动Microsoft Edge \ (Chromium\) ，请创建一个新对象，并传递一个属性设置为 `EdgeDriver` `EdgeOptions` `UseChromium` 的对象 `true` 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-194">To start a session and automate Microsoft Edge \(Chromium\), create a new `EdgeDriver` object and pass it an `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<a name="c"></a><span data-ttu-id="b10dd-195">C#</span><span class="sxs-lookup"><span data-stu-id="b10dd-195">C#</span></span>](#tab/c-sharp/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a><span data-ttu-id="b10dd-196">Python</span><span class="sxs-lookup"><span data-stu-id="b10dd-196">Python</span></span>](#tab/python/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options = options)
```  

#### [<a name="java"></a><span data-ttu-id="b10dd-197">Java	</span><span class="sxs-lookup"><span data-stu-id="b10dd-197">Java</span></span>](#tab/java/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

<span data-ttu-id="b10dd-198">该类 `EdgeDriver` 仅支持 Microsoft Edge \ (Chromium\) ，不支持 Microsoft Edge \ (EdgeHTML\) 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-198">The `EdgeDriver` class only supports Microsoft Edge \(Chromium\), and doesn't support Microsoft Edge \(EdgeHTML\).</span></span>  <span data-ttu-id="b10dd-199">对于基本用法，可以在不提供 `EdgeDriver` 的情况下创建 `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-199">For basic usage, you can create an `EdgeDriver` without providing `EdgeOptions`.</span></span>  

```java
EdgeDriver driver = new EdgeDriver();
```  

#### [<a name="javascript"></a><span data-ttu-id="b10dd-200">JavaScript</span><span class="sxs-lookup"><span data-stu-id="b10dd-200">JavaScript</span></span>](#tab/javascript/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> <span data-ttu-id="b10dd-201">如果你的 IT 管理员将[DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]策略设置为 ，Microsoft Edge 驱动程序被阻止驱动 `2` Microsoft Edge \ (Chromium\) ，因为驱动程序使用 Microsoft Edge [DevTools][DevtoolsIndex]。 [][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]</span><span class="sxs-lookup"><span data-stu-id="b10dd-201">If your IT admin has set the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy to `2`,  [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] is blocked from driving Microsoft Edge \(Chromium\), because the driver uses the [Microsoft Edge DevTools][DevtoolsIndex].</span></span>  <span data-ttu-id="b10dd-202">确保[将 DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]策略设置为 `0` 或 `1` 自动Microsoft Edge (Chromium) 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-202">Ensure the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy is set to `0` or `1` to automate Microsoft Edge (Chromium).</span></span>  

### <a name="choose-specific-browser-binaries-chromium-only"></a><span data-ttu-id="b10dd-203">选择"特定浏览器二进制文件 (Chromium仅) </span><span class="sxs-lookup"><span data-stu-id="b10dd-203">Choose Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="b10dd-204">可以使用特定文件 \Microsoft Edge\ (Chromium\) WebDriver 会话。</span><span class="sxs-lookup"><span data-stu-id="b10dd-204">You can start a WebDriver session with specific Microsoft Edge \(Chromium\) binaries.</span></span>  <span data-ttu-id="b10dd-205">例如，可以使用预览频道（如[Microsoft Edge）][MicrosoftedgeinsiderDownload]运行Microsoft Edge Beta。</span><span class="sxs-lookup"><span data-stu-id="b10dd-205">For example, you can run tests using the [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<a name="c"></a><span data-ttu-id="b10dd-206">C#</span><span class="sxs-lookup"><span data-stu-id="b10dd-206">C#</span></span>](#tab/c-sharp/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a><span data-ttu-id="b10dd-207">Python</span><span class="sxs-lookup"><span data-stu-id="b10dd-207">Python</span></span>](#tab/python/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options = options)
```  

#### [<a name="java"></a><span data-ttu-id="b10dd-208">Java	</span><span class="sxs-lookup"><span data-stu-id="b10dd-208">Java</span></span>](#tab/java/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.setBinary("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

EdgeDriver driver = new EdgeDriver(options);
```  

#### [<a name="javascript"></a><span data-ttu-id="b10dd-209">JavaScript</span><span class="sxs-lookup"><span data-stu-id="b10dd-209">JavaScript</span></span>](#tab/javascript/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <a name="customize-the-microsoft-edge-driver-service"></a><span data-ttu-id="b10dd-210">自定义 Microsoft Edge 驱动程序服务</span><span class="sxs-lookup"><span data-stu-id="b10dd-210">Customize the Microsoft Edge Driver Service</span></span>  

#### [<a name="c"></a><span data-ttu-id="b10dd-211">C#</span><span class="sxs-lookup"><span data-stu-id="b10dd-211">C#</span></span>](#tab/c-sharp/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="b10dd-212">使用 类创建类实例时，它会为 `EdgeOptions` `EdgeDriver` Microsoft Edge `EdgeDriverService` \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 创建和启动相应的类。</span><span class="sxs-lookup"><span data-stu-id="b10dd-212">When you use the `EdgeOptions` class to create an `EdgeDriver` class instance, it creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="b10dd-213">如果要创建 ，请使用 方法创建一个配置为 Microsoft Edge `EdgeDriverService` `CreateChromiumService()` \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-213">If you want to create an `EdgeDriverService`, use the `CreateChromiumService()` method to create one configured for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="b10dd-214">`CreateChromiumService()`当您需要添加自定义项时，该方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="b10dd-214">The `CreateChromiumService()` method is useful when you need to add customizations.</span></span>  <span data-ttu-id="b10dd-215">例如，以下代码开始详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="b10dd-215">For example, the following code starts verbose log output.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
><span data-ttu-id="b10dd-216">在传递给实例时，不需要 `EdgeOptions` 提供 `EdgeDriverService` `EdgeDriver` 对象。</span><span class="sxs-lookup"><span data-stu-id="b10dd-216">You do not need to provide the `EdgeOptions` object when you pass `EdgeDriverService` to the `EdgeDriver` instance.</span></span>  <span data-ttu-id="b10dd-217">该类根据你提供的服务使用 Microsoft Edge `EdgeDriver` \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 的默认选项。</span><span class="sxs-lookup"><span data-stu-id="b10dd-217">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) based on the service you provide.</span></span>  
> <span data-ttu-id="b10dd-218">但是，如果要同时提供 和 类，请确保为同一版本的 `EdgeDriverService` `EdgeOptions` Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b10dd-218">However, if you want to provide both `EdgeDriverService` and `EdgeOptions` classes, ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="b10dd-219">例如，可以使用默认的 Microsoft Edge \ (EdgeHTML\) `EdgeDriverService` 类Chromium属性 `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-219">For example, you may use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="b10dd-220">`EdgeDriver`该类会引发错误，以阻止使用不同的版本。</span><span class="sxs-lookup"><span data-stu-id="b10dd-220">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<a name="python"></a><span data-ttu-id="b10dd-221">Python</span><span class="sxs-lookup"><span data-stu-id="b10dd-221">Python</span></span>](#tab/python/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="b10dd-222">使用 Python 时， `Edge` 对象将创建和管理 `EdgeService` 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-222">When you use Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="b10dd-223">若要配置 `EdgeService` ，请向 对象传递 `Edge` 额外参数，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="b10dd-223">To configure the `EdgeService`, pass extra arguments to the `Edge` object as indicated in the following code.</span></span>  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<a name="java"></a><span data-ttu-id="b10dd-224">Java	</span><span class="sxs-lookup"><span data-stu-id="b10dd-224">Java</span></span>](#tab/java/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="b10dd-225">使用 `createDefaultService()` 方法可创建 `EdgeDriverService` 一个配置为 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-225">Use the `createDefaultService()` method to create an `EdgeDriverService` configured for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="b10dd-226">使用 Java 系统属性自定义 Java 中的驱动程序服务。</span><span class="sxs-lookup"><span data-stu-id="b10dd-226">Use Java system properties to customize driver services in Java.</span></span>  <span data-ttu-id="b10dd-227">例如，以下代码使用 `"webdriver.edge.verboseLogging"` 属性打开详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="b10dd-227">For example, the following code uses the `"webdriver.edge.verboseLogging"` property to turn on verbose log output.</span></span>  

```java
System.setProperty("webdriver.edge.verboseLogging", "true");
EdgeDriverService service = EdgeDriverService.createDefaultService();
EdgeOptions options = new EdgeOptions();
EdgeDriver driver = new EdgeDriver(service, options);
```  

#### [<a name="javascript"></a><span data-ttu-id="b10dd-228">JavaScript</span><span class="sxs-lookup"><span data-stu-id="b10dd-228">JavaScript</span></span>](#tab/javascript/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="b10dd-229">使用 JavaScript 时，请使用 类 `Service` 创建和 `ServiceBuilder` 配置 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-229">When you use JavaScript, create and configure a `Service` with the `ServiceBuilder` class.</span></span>  <span data-ttu-id="b10dd-230">（可选）可以将对象传递给对象，该对象将启动 `Service` `Driver` \ (并停止\) 服务。</span><span class="sxs-lookup"><span data-stu-id="b10dd-230">Optionally, you can pass the `Service` object to the `Driver` object, which starts \(and stops\) the service for you.</span></span>  
<span data-ttu-id="b10dd-231">若要配置 `Service` ，请运行 类中的另一 `ServiceBuilder` 个方法，然后再使用 `build()` 方法。</span><span class="sxs-lookup"><span data-stu-id="b10dd-231">To configure the `Service`, run another method in the `ServiceBuilder` class before you use the `build()` method.</span></span>  <span data-ttu-id="b10dd-232">然后， `service` 在 方法中将 作为 参数 `Driver.createSession()` 传递。</span><span class="sxs-lookup"><span data-stu-id="b10dd-232">Then pass the `service` as a parameter in the `Driver.createSession()` method.</span></span>  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <a name="use-chromium-specific-options"></a><span data-ttu-id="b10dd-233">使用Chromium-Specific选项</span><span class="sxs-lookup"><span data-stu-id="b10dd-233">Use Chromium-Specific Options</span></span>  

<span data-ttu-id="b10dd-234">如果将 属性设置为 ，可以使用 类来访问Chromium自动化其他浏览器时所使用的特定于 Chromium `UseChromium` `true` `EdgeOptions` 的属性和方法。 [][WebdriverCapabilitiesEdgeOptions]</span><span class="sxs-lookup"><span data-stu-id="b10dd-234">If you set the `UseChromium` property to `true`, you can use the `EdgeOptions` class to access the same [Chromium-specific properties and methods][WebdriverCapabilitiesEdgeOptions] that are used when you automate other Chromium browsers.</span></span>  

#### [<a name="c"></a><span data-ttu-id="b10dd-235">C#</span><span class="sxs-lookup"><span data-stu-id="b10dd-235">C#</span></span>](#tab/c-sharp/)  

<a id="use-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<a name="python"></a><span data-ttu-id="b10dd-236">Python</span><span class="sxs-lookup"><span data-stu-id="b10dd-236">Python</span></span>](#tab/python/)  

<a id="use-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<a name="java"></a><span data-ttu-id="b10dd-237">Java	</span><span class="sxs-lookup"><span data-stu-id="b10dd-237">Java</span></span>](#tab/java/)  

<a id="use-chromium-specific-options-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

#### [<a name="javascript"></a><span data-ttu-id="b10dd-238">JavaScript</span><span class="sxs-lookup"><span data-stu-id="b10dd-238">JavaScript</span></span>](#tab/javascript/)  

<a id="use-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

* * *  

> [!NOTE]
> <span data-ttu-id="b10dd-239">如果属性设置为 ，则不能对 Microsoft Edge `UseChromium` `true` \ (EdgeHTML\) 。</span><span class="sxs-lookup"><span data-stu-id="b10dd-239">If the `UseChromium` property is set to `true`, you are not able to use properties and methods for Microsoft Edge \(EdgeHTML\).</span></span>  


## <a name="other-webdriver-installation-options"></a><span data-ttu-id="b10dd-240">其他 WebDriver 安装选项</span><span class="sxs-lookup"><span data-stu-id="b10dd-240">Other WebDriver installation options</span></span>  

### <a name="docker"></a><span data-ttu-id="b10dd-241">Docker</span><span class="sxs-lookup"><span data-stu-id="b10dd-241">Docker</span></span>  

<span data-ttu-id="b10dd-242">如果使用[Docker，][DockerHub]请运行以下命令，下载预配置映像Microsoft Edge \ (Chromium\) Microsoft Edge[驱动程序][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]预安装。</span><span class="sxs-lookup"><span data-stu-id="b10dd-242">If you use [Docker][DockerHub], run the following command to download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] pre-installed.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="b10dd-243">有关详细信息，请导航到 Docker Hub 上的 [msedgedriver 容器][DockerHubMsedgedriver]。</span><span class="sxs-lookup"><span data-stu-id="b10dd-243">For more information, navigate to the [msedgedriver container on Docker Hub][DockerHubMsedgedriver].</span></span>  


## <a name="testing-internet-explorer"></a><span data-ttu-id="b10dd-244">测试Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="b10dd-244">Testing Internet Explorer</span></span>

<span data-ttu-id="b10dd-245">若要测试需要更新Internet Explorer，Internet Explorer [驱动程序][GithubSeleniumHqWikiIEDriver] 和Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="b10dd-245">To test sites that require Internet Explorer, use [Internet Explorer Driver][GithubSeleniumHqWikiIEDriver] with Internet Explorer.</span></span>  <span data-ttu-id="b10dd-246">Internet Explorer驱动程序由 Selenium 项目维护。</span><span class="sxs-lookup"><span data-stu-id="b10dd-246">Internet Explorer Driver is maintained by the Selenium project.</span></span>  <span data-ttu-id="b10dd-247">即使Microsoft Edge支持 IE 模式，你Microsoft Edge驱动程序Microsoft Edge IE 模式下测试站点。</span><span class="sxs-lookup"><span data-stu-id="b10dd-247">Even though Microsoft Edge supports IE Mode, you can't use Microsoft Edge Driver with Microsoft Edge to test sites in IE Mode.</span></span>


## <a name="application-guard"></a><span data-ttu-id="b10dd-248">应用程序防护</span><span class="sxs-lookup"><span data-stu-id="b10dd-248">Application Guard</span></span>

<span data-ttu-id="b10dd-249">使用应用程序防护Microsoft Defender 应用程序防护 (的) 可以使用驱动程序自动Microsoft Edge站点。</span><span class="sxs-lookup"><span data-stu-id="b10dd-249">Trusted sites that use Microsoft Defender Application Guard (Application Guard) can be automated using Microsoft Edge Driver.</span></span>

<span data-ttu-id="b10dd-250">使用应用程序防护的不受信任的站点无法使用应用程序驱动程序自动Microsoft Edge操作。</span><span class="sxs-lookup"><span data-stu-id="b10dd-250">Untrusted sites that use Application Guard cannot be automated or manipulated using Microsoft Edge Driver.</span></span>  <span data-ttu-id="b10dd-251">应用程序防护在容器中启动不受信任的站点，并且此容器不会公开驱动程序与站点Microsoft Edge所需的远程调试端口。</span><span class="sxs-lookup"><span data-stu-id="b10dd-251">Application Guard launches untrusted sites in a container, and this container doesn't expose the remote debugging port that Microsoft Edge Driver needs to communicate with the site.</span></span>

<span data-ttu-id="b10dd-252">企业管理员定义什么是受信任的站点，包括云资源和内部网络。</span><span class="sxs-lookup"><span data-stu-id="b10dd-252">Your enterprise administrator defines what are trusted sites, including cloud resources and internal networks.</span></span>  <span data-ttu-id="b10dd-253">不在受信任站点列表中的网站被视为不受信任的网站。</span><span class="sxs-lookup"><span data-stu-id="b10dd-253">Sites that aren't in the trusted sites list are considered untrusted.</span></span>  <span data-ttu-id="b10dd-254">Microsoft Edge驱动程序可以自动执行 InPrivate 窗口和受信任站点列表中的站点。</span><span class="sxs-lookup"><span data-stu-id="b10dd-254">Microsoft Edge Driver can automate both InPrivate windows, and sites in the trusted sites list.</span></span>

<span data-ttu-id="b10dd-255">有关应用程序防护详细信息，请导航到：</span><span class="sxs-lookup"><span data-stu-id="b10dd-255">For more information about Application Guard, navigate to:</span></span> 

*  [<span data-ttu-id="b10dd-256">Microsoft Edge 对 Microsoft Defender 应用程序防护的支持</span><span class="sxs-lookup"><span data-stu-id="b10dd-256">Microsoft Edge support for Microsoft Defender Application Guard</span></span>][DeployedgeMicrosoftEdgeSecurityWindowsDefenderApplicationGuard]
*  [<span data-ttu-id="b10dd-257">Microsoft Defender 应用程序防护概述</span><span class="sxs-lookup"><span data-stu-id="b10dd-257">Microsoft Defender Application Guard overview</span></span>][WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]


## <a name="see-also"></a><span data-ttu-id="b10dd-258">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b10dd-258">See also</span></span>

*  <span data-ttu-id="b10dd-259">[Selenium 文档][SeleniumDocumentation] - 有关 Selenium 上下文中的 WebDriver 以及如何使用 Selenium 编写自动 WebDriver 测试的信息。</span><span class="sxs-lookup"><span data-stu-id="b10dd-259">[Selenium documentation][SeleniumDocumentation] - Information about WebDriver in the context of Selenium, and how to write automated WebDriver tests using Selenium.</span></span>


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="b10dd-260">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="b10dd-260">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="b10dd-261">Microsoft Edge团队希望听到你有关使用 WebDriver、WebDriver 测试框架 (如 Selenium) 和 Microsoft Edge 的反馈。</span><span class="sxs-lookup"><span data-stu-id="b10dd-261">The Microsoft Edge team is eager to hear your feedback about using WebDriver, WebDriver testing frameworks (such as Selenium), and Microsoft Edge.</span></span>  <span data-ttu-id="b10dd-262">若要向团队发送你的问题和意见，请选择开发人员工具Microsoft Edge\*\*\*\* 发送反馈图标或发送推文[@EdgeDevTools。][TwitterTweetEdgeDevTools]</span><span class="sxs-lookup"><span data-stu-id="b10dd-262">To send the team your questions and comments, choose the **Send Feedback** icon in the Microsoft Edge DevTools or send a tweet [@EdgeDevTools][TwitterTweetEdgeDevTools].</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="b10dd-264">Microsoft Edge DevTools 中的**发送反馈**图标</span><span class="sxs-lookup"><span data-stu-id="b10dd-264">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
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
