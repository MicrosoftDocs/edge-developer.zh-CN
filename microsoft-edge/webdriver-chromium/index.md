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
ms.openlocfilehash: c68a16aebcfdc6ade8838145368d32ad84a82209
ms.sourcegitcommit: d0a6959c5338cf1927093b4a9ed29a0bc0390b43
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "11615426"
---
# <a name="use-webdriver-chromium-for-test-automation"></a><span data-ttu-id="33143-104">使用 WebDriver (Chromium) 实现测试自动化</span><span class="sxs-lookup"><span data-stu-id="33143-104">Use WebDriver (Chromium) for test automation</span></span>  

<span data-ttu-id="33143-105">WebDriver 允许开发人员创建模拟用户交互的自动测试。</span><span class="sxs-lookup"><span data-stu-id="33143-105">WebDriver allows developers to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="33143-106">WebDriver 测试和模拟与 JavaScript 单元测试在以下方面有所不同。</span><span class="sxs-lookup"><span data-stu-id="33143-106">WebDriver tests and simulations differ from JavaScript unit tests in the following ways.</span></span>  

*   <span data-ttu-id="33143-107">访问在浏览器中运行的 JavaScript 不可用的功能和信息。</span><span class="sxs-lookup"><span data-stu-id="33143-107">Accesses functionality and information not available to JavaScript running in browsers.</span></span>  
*   <span data-ttu-id="33143-108">更精确地模拟用户事件或操作系统级事件。</span><span class="sxs-lookup"><span data-stu-id="33143-108">Simulates user events or OS-level events more accurately.</span></span>  
*   <span data-ttu-id="33143-109">在单个测试会话中管理多个窗口、选项卡和网页。</span><span class="sxs-lookup"><span data-stu-id="33143-109">Manages multiple windows, tabs, and webpages in a single test session.</span></span>  
*   <span data-ttu-id="33143-110">运行特定计算机上Microsoft Edge会话的会话。</span><span class="sxs-lookup"><span data-stu-id="33143-110">Runs multiple sessions of Microsoft Edge on a specific machine.</span></span>  

## <a name="relationship-between-webdriver-and-other-software"></a><span data-ttu-id="33143-111">WebDriver 和其他软件之间的关系</span><span class="sxs-lookup"><span data-stu-id="33143-111">Relationship between WebDriver and other software</span></span>

<span data-ttu-id="33143-112">若要自动Microsoft Edge WebDriver 自动执行用户交互，您需要三个组件：</span><span class="sxs-lookup"><span data-stu-id="33143-112">To automate Microsoft Edge with WebDriver to simulate user interaction, you need three components:</span></span>

*  <span data-ttu-id="33143-113">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="33143-113">Microsoft Edge</span></span>
*  <span data-ttu-id="33143-114">Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="33143-114">Microsoft Edge Driver</span></span>
*  <span data-ttu-id="33143-115">WebDriver 测试框架</span><span class="sxs-lookup"><span data-stu-id="33143-115">A WebDriver testing framework</span></span>

<span data-ttu-id="33143-116">WebDriver、Microsoft Edge Driver、Selenium 和 Internet Explorer Driver 之间的功能关系如下所示。</span><span class="sxs-lookup"><span data-stu-id="33143-116">The functional relationship between WebDriver, Microsoft Edge Driver, Selenium, and Internet Explorer Driver is as follows.</span></span>

| <span data-ttu-id="33143-117">技术</span><span class="sxs-lookup"><span data-stu-id="33143-117">Technology</span></span> | <span data-ttu-id="33143-118">角色</span><span class="sxs-lookup"><span data-stu-id="33143-118">Role</span></span> |
|---|---|
| <span data-ttu-id="33143-119">WebDriver</span><span class="sxs-lookup"><span data-stu-id="33143-119">WebDriver</span></span> | <span data-ttu-id="33143-120">适用于平台和中性语言的线路协议的 W3C 标准。</span><span class="sxs-lookup"><span data-stu-id="33143-120">A W3C standard for a platform- and language-neutral wire protocol.</span></span>  <span data-ttu-id="33143-121">此协议允许进程外程序远程指示 Web 浏览器的行为。</span><span class="sxs-lookup"><span data-stu-id="33143-121">This protocol allows out-of-process programs to remotely instruct the behavior of web browsers.</span></span> |
| <span data-ttu-id="33143-122">Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="33143-122">Microsoft Edge Driver</span></span> | <span data-ttu-id="33143-123">Microsoft 专为用户实现 WebDriver Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="33143-123">Microsoft's implementation of the WebDriver protocol specifically for Microsoft Edge.</span></span> <span data-ttu-id="33143-124">测试作者编写使用驱动程序收到的 WebDriver Microsoft Edge的测试。</span><span class="sxs-lookup"><span data-stu-id="33143-124">Test authors write tests that use WebDriver commands that Microsoft Edge Driver receives.</span></span> <span data-ttu-id="33143-125">Microsoft Edge然后，驱动程序负责将该命令与浏览器通信。</span><span class="sxs-lookup"><span data-stu-id="33143-125">Microsoft Edge Driver is then responsible for communicating that command to the browser.</span></span> |
| <span data-ttu-id="33143-126">Selenium</span><span class="sxs-lookup"><span data-stu-id="33143-126">Selenium</span></span> | <span data-ttu-id="33143-127">测试作者用于编写端到端测试和自动化浏览器的热门 WebDriver 测试框架。</span><span class="sxs-lookup"><span data-stu-id="33143-127">A popular WebDriver testing framework that test authors use to write end-to-end tests and automate browsers.</span></span> <span data-ttu-id="33143-128">Selenium 可用于任何平台，可用于 Java、Python、C#、Ruby 和 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="33143-128">Selenium can be used on any platform, and is available in Java, Python, C#, Ruby, and JavaScript.</span></span> |
| <span data-ttu-id="33143-129">Internet Explorer驱动程序</span><span class="sxs-lookup"><span data-stu-id="33143-129">Internet Explorer Driver</span></span> | <span data-ttu-id="33143-130">专用于 webDriver 协议的实现Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="33143-130">An implementation of the WebDriver protocol specifically for Internet Explorer.</span></span> <span data-ttu-id="33143-131">此产品由 Selenium 项目维护。</span><span class="sxs-lookup"><span data-stu-id="33143-131">This product is maintained by the Selenium project.</span></span> <span data-ttu-id="33143-132">若要为用户运行旧版端到端测试Internet Explorer，我们建议使用 Internet Explorer Driver。</span><span class="sxs-lookup"><span data-stu-id="33143-132">To run legacy end-to-end tests for Internet Explorer, we recommend using Internet Explorer Driver.</span></span> |

<span data-ttu-id="33143-133">以下各节介绍如何开始使用 WebDriver for Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="33143-133">The following sections describe how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  

## <a name="install-microsoft-edge-chromium"></a><span data-ttu-id="33143-134">安装Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="33143-134">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="33143-135">确保安装[Microsoft Edge (Chromium) 。 ][MicrosoftEdge]</span><span class="sxs-lookup"><span data-stu-id="33143-135">Ensure you install [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="33143-136">若要确认已安装 \Microsoft Edge \ (Chromium\) ，请导航到 `edge://settings/help` ，并验证版本号是版本 75 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="33143-136">To confirm that you have Microsoft Edge \(Chromium\) installed, navigate to `edge://settings/help`, and verify the version number is version 75 or later.</span></span>  

## <a name="download-microsoft-edge-driver"></a><span data-ttu-id="33143-137">下载 Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="33143-137">Download Microsoft Edge Driver</span></span>  

<span data-ttu-id="33143-138">若要开始自动执行测试，请使用以下步骤来确保安装的 WebDriver 版本与浏览器版本相匹配。</span><span class="sxs-lookup"><span data-stu-id="33143-138">To begin automating tests, use the following steps to ensure that the WebDriver version you install matches your browser version.</span></span>  

1.  <span data-ttu-id="33143-139">查找你的Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="33143-139">Find your version of Microsoft Edge.</span></span>  
    1.  <span data-ttu-id="33143-140">导航到 `edge://settings/help`。</span><span class="sxs-lookup"><span data-stu-id="33143-140">Navigate to `edge://settings/help`.</span></span>  
        
        :::image type="complex" source="./media/microsoft-edge-version.msft.png" alt-text="2021 年 4 Microsoft Edge 15 日" lightbox="./media/microsoft-edge-version.msft.png":::
           <span data-ttu-id="33143-142">2021 年 4 Microsoft Edge 15 日</span><span class="sxs-lookup"><span data-stu-id="33143-142">The build number for Microsoft Edge on April 15, 2021</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="33143-143">导航到[Microsoft Edge驱动程序。][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]</span><span class="sxs-lookup"><span data-stu-id="33143-143">Navigate to [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver].</span></span>  
1.  <span data-ttu-id="33143-144">导航到 **获取最新版本**。</span><span class="sxs-lookup"><span data-stu-id="33143-144">Navigate to **Get the latest version**.</span></span>  
1.  <span data-ttu-id="33143-145">选择与你的版本版本号相匹配的频道Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="33143-145">Choose the build of channel that matches your version number of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="./media/microsoft-edge-driver-install.msft.png" alt-text=""获取驱动程序"网页上的"获取Microsoft Edge部分" lightbox="./media/microsoft-edge-driver-install.msft.png":::
       <span data-ttu-id="33143-147">"**获取驱动程序"网页上**的Microsoft Edge[部分][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]</span><span class="sxs-lookup"><span data-stu-id="33143-147">The **Get the latest version** section on the [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] webpage</span></span>  
    :::image-end:::  
    
    <!--  
    > [!NOTE] 
    > For more information about test automation using Microsoft Edge \(EdgeHTML\), navigate to [Microsoft Edge Driver for Microsoft Edge (EdgeHTML)][Webdriver].  
    -->  
    
## <a name="choose-a-webdriver-language-binding"></a><span data-ttu-id="33143-148">选择 WebDriver 语言绑定</span><span class="sxs-lookup"><span data-stu-id="33143-148">Choose a WebDriver language binding</span></span>  

<span data-ttu-id="33143-149">必须下载的最后一个组件是特定语言的客户端驱动程序，用于将代码 \ (Python、Java、C\#、Ruby、JavaScript\) 转换为 Microsoft Edge 驱动程序在 Microsoft Edge \ (Chromium\) 中运行的命令。</span><span class="sxs-lookup"><span data-stu-id="33143-149">The last component you must download is a language-specific client driver to translate your code \(Python, Java, C\#, Ruby, JavaScript\) into commands the Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="33143-150">[下载你选择的 WebDriver 语言绑定][SeleniumDownloads]。</span><span class="sxs-lookup"><span data-stu-id="33143-150">[Download the WebDriver language binding of your choice][SeleniumDownloads].</span></span>  <span data-ttu-id="33143-151">该Microsoft Edge推荐[Selenium 4.0.0-beta2][NugetPackagesSeleniumWebdriver400beta02]或更高版本，因为它支持 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="33143-151">The Microsoft Edge team recommends [Selenium 4.0.0-beta2][NugetPackagesSeleniumWebdriver400beta02] or later, because it supports Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="33143-152">但是，你可以控制所有较旧版本的 Selenium Microsoft Edge \ (Chromium\) ，包括当前稳定的 Selenium 3 版本。</span><span class="sxs-lookup"><span data-stu-id="33143-152">However, you can control Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="33143-153">如果之前使用 和 类自动Microsoft Edge \ (Chromium\) ，WebDriver 代码将不会在 Microsoft Edge `ChromeDriver` `ChromeOptions` 版本 80 或更高版本中运行。</span><span class="sxs-lookup"><span data-stu-id="33143-153">If you previously automated or tested Microsoft Edge \(Chromium\) using `ChromeDriver` and `ChromeOptions` classes, your WebDriver code does not run on Microsoft Edge Version 80 or later.</span></span>  <span data-ttu-id="33143-154">若要解决此问题，请更新测试以使用 类 `EdgeOptions` 并下载[Microsoft Edge驱动程序][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="33143-154">To solve the problem, update your tests to use the `EdgeOptions` class and download [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver].</span></span>  

### <a name="using-selenium-4"></a><span data-ttu-id="33143-155">使用 Selenium 4</span><span class="sxs-lookup"><span data-stu-id="33143-155">Using Selenium 4</span></span>

<span data-ttu-id="33143-156">Selenium 4 内置支持 Microsoft Edge (Chromium) 。</span><span class="sxs-lookup"><span data-stu-id="33143-156">Selenium 4 has built-in support for Microsoft Edge (Chromium).</span></span>  <span data-ttu-id="33143-157">若要安装 Selenium 4，请导航到["安装 Selenium 库"。][SeleniumInstallingLibraries]</span><span class="sxs-lookup"><span data-stu-id="33143-157">To install Selenium 4, navigate to [Installing Selenium libraries][SeleniumInstallingLibraries].</span></span>

<span data-ttu-id="33143-158">使用 Selenium 4 时，无需使用 Selenium Tools for Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="33143-158">When you use Selenium 4, you don't need to use Selenium Tools for Microsoft Edge.</span></span>  <span data-ttu-id="33143-159">Selenium Tools for Microsoft Edge仅适用于 Selenium 3。</span><span class="sxs-lookup"><span data-stu-id="33143-159">Selenium Tools for Microsoft Edge are for Selenium 3 only.</span></span>  <span data-ttu-id="33143-160">如果您尝试将 Selenium 4 与 Selenium Tools for Microsoft Edge并尝试创建新实例，则 `EdgeDriver` 收到以下错误： `System.MissingMethodException: 'Method not found: 'OpenQA.Selenium.Remote.DesiredCapabilities OpenQA.Selenium.DriverOptions.GenerateDesiredCapabilities(Boolean)'` 。</span><span class="sxs-lookup"><span data-stu-id="33143-160">If you try to use Selenium 4 with Selenium Tools for Microsoft Edge and try to create a new `EdgeDriver` instance, you get the following error: `System.MissingMethodException: 'Method not found: 'OpenQA.Selenium.Remote.DesiredCapabilities OpenQA.Selenium.DriverOptions.GenerateDesiredCapabilities(Boolean)'`.</span></span>  

<span data-ttu-id="33143-161">如果你使用的是 Selenium 4 并收到此错误，请从项目中删除 ，并确保你正在使用命名空间中的 official 和 `Microsoft.Edge.SeleniumTools` `EdgeOptions` `EdgeDriver` `OpenQA.Selenium.Edge` 类。</span><span class="sxs-lookup"><span data-stu-id="33143-161">If you're using Selenium 4 and get this error, remove `Microsoft.Edge.SeleniumTools` from your project, and make sure you're using the official `EdgeOptions` and `EdgeDriver` classes from the `OpenQA.Selenium.Edge` namespace.</span></span>

### <a name="using-selenium-3"></a><span data-ttu-id="33143-162">使用 Selenium 3</span><span class="sxs-lookup"><span data-stu-id="33143-162">Using Selenium 3</span></span>  

<span data-ttu-id="33143-163">如果你已使用[Selenium 3，][|::ref1::|]你可能已有浏览器测试，并且希望添加 Microsoft Edge \ (Chromium\) 的覆盖范围，而无需更改 Selenium 版本。</span><span class="sxs-lookup"><span data-stu-id="33143-163">If you already use [Selenium 3][|::ref1::|], you may have existing browser tests and want to add coverage for Microsoft Edge \(Chromium\) without changing your version of Selenium.</span></span>  <span data-ttu-id="33143-164">若要使用[Selenium 3][|::ref2::|]为 Microsoft Edge \ (EdgeHTML\) 和 Microsoft Edge \ (Chromium\) 编写自动测试，请安装适用于 Microsoft Edge 的[Selenium 工具][GithubMicrosoftEdgeSeleniumTools]程序包以使用更新的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="33143-164">To use [Selenium 3][|::ref2::|] to write automated tests for both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package to use the updated driver.</span></span>  <span data-ttu-id="33143-165">工具 `EdgeDriver` `EdgeDriverService` 中包含的 和 类与 Selenium 4 中的内置等效项完全兼容。</span><span class="sxs-lookup"><span data-stu-id="33143-165">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium 4.</span></span>  

<span data-ttu-id="33143-166">使用以下步骤将[适用于][GithubMicrosoftEdgeSeleniumTools]Microsoft Edge 和[Selenium 3 的 Selenium][|::ref3::|]工具添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="33143-166">Use the following steps to add the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] and [Selenium 3][|::ref3::|] to your project.</span></span>  

#### [<a name="c"></a><span data-ttu-id="33143-167">C#</span><span class="sxs-lookup"><span data-stu-id="33143-167">C#</span></span>](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="33143-168">使用 CLI 或 Visual Studio 将[Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools]和[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410]程序包添加到[NuGet .NET][NugetCLI] [项目][VisualStudio]。</span><span class="sxs-lookup"><span data-stu-id="33143-168">Add the [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] and [Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] packages to your .NET project using the [NuGet CLI][NugetCLI] or [Visual Studio][VisualStudio].</span></span>  

#### [<a name="python"></a><span data-ttu-id="33143-169">Python</span><span class="sxs-lookup"><span data-stu-id="33143-169">Python</span></span>](#tab/python/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="33143-170">使用 [管道][PythonPip] 安装 [msedge-selenium-tools][PythonSeleniumTools] 和 [selenium][PythonSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="33143-170">Use [pip][PythonPip] to install the [msedge-selenium-tools][PythonSeleniumTools] and [selenium][PythonSelenium] packages.</span></span>  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<a name="java"></a><span data-ttu-id="33143-171">Java	</span><span class="sxs-lookup"><span data-stu-id="33143-171">Java</span></span>](#tab/java/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="33143-172">如果您的Java项目使用 Maven，将以下依赖项复制并粘贴到您的文件以添加 `pom.xml` [msedge-selenium-tools-java][SonatypeMavenRepositorySearch]。</span><span class="sxs-lookup"><span data-stu-id="33143-172">If your Java project uses Maven, copy and paste the following dependency to your `pom.xml` file to add [msedge-selenium-tools-java][SonatypeMavenRepositorySearch].</span></span>  

```xml
<dependency>
    <groupId>com.microsoft.edge</groupId>
    <artifactId>msedge-selenium-tools-java</artifactId>
    <version>[3.141.0,)</version>
</dependency>
```  

<span data-ttu-id="33143-173">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].</span><span class="sxs-lookup"><span data-stu-id="33143-173">The Java package is also available to download directly on the [Selenium Tools for Microsoft Edge Releases page][GithubMicrosoftEdgeSeleniumToolsReleases].</span></span>  

#### [<a name="javascript"></a><span data-ttu-id="33143-174">JavaScript</span><span class="sxs-lookup"><span data-stu-id="33143-174">JavaScript</span></span>](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="33143-175">使用 [npm][JavaScript|::ref4::|] 安装 [edge-selenium-tools][JavaScriptSeleniumTools] 和 [selenium-webdriver][JavaScriptSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="33143-175">Use [npm][JavaScript|::ref4::|] to install the [edge-selenium-tools][JavaScriptSeleniumTools] and [selenium-webdriver][JavaScriptSelenium] packages.</span></span>  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## <a name="automate-microsoft-edge-chromium-with-webdriver"></a><span data-ttu-id="33143-176">使用 WebDriver Microsoft Edge (Chromium) 自动执行部署</span><span class="sxs-lookup"><span data-stu-id="33143-176">Automate Microsoft Edge (Chromium) with WebDriver</span></span>  

<span data-ttu-id="33143-177">若要使用 WebDriver 自动化浏览器，必须先使用首选的 WebDriver 语言绑定启动 WebDriver 会话。</span><span class="sxs-lookup"><span data-stu-id="33143-177">To automate a browser using WebDriver, you must first start a WebDriver session using your preferred WebDriver language binding.</span></span>  <span data-ttu-id="33143-178">会话是使用 WebDriver 命令控制的浏览器的单个运行实例。</span><span class="sxs-lookup"><span data-stu-id="33143-178">A session is a single running instance of a browser controlled using WebDriver commands.</span></span>  <span data-ttu-id="33143-179">启动 WebDriver 会话以启动新的浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="33143-179">Start a WebDriver session to launch a new browser instance.</span></span>  <span data-ttu-id="33143-180">在关闭 WebDriver 会话之前，启动的浏览器实例保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="33143-180">The launched browser instance remains open until you close the WebDriver session.</span></span>  

<span data-ttu-id="33143-181">以下内容将引导你使用 Selenium 启动 WebDriver 会话，Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="33143-181">The following content walks you through using Selenium to start a WebDriver session with Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="33143-182">可以使用 Selenium 3 或 4 运行这些示例。</span><span class="sxs-lookup"><span data-stu-id="33143-182">You can run the examples using either Selenium 3 or 4.</span></span>  <span data-ttu-id="33143-183">若要与 Selenium 3 一起使用，必须安装适用于 Microsoft Edge 的[Selenium][GithubMicrosoftEdgeSeleniumTools]工具。</span><span class="sxs-lookup"><span data-stu-id="33143-183">To use with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package must be installed.</span></span>  

### <a name="automate-microsoft-edge-chromium"></a><span data-ttu-id="33143-184">自动Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="33143-184">Automate Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="33143-185">Selenium 使用 类管理 Microsoft Edge `EdgeDriver` \ (Chromium\) 会话。</span><span class="sxs-lookup"><span data-stu-id="33143-185">Selenium uses the `EdgeDriver` class to manage a Microsoft Edge \(Chromium\) session.</span></span>  <span data-ttu-id="33143-186">若要启动会话并自动Microsoft Edge \ (Chromium\) ，请创建一个新对象，并传递一个属性设置为 `EdgeDriver` `EdgeOptions` `UseChromium` 的对象 `true` 。</span><span class="sxs-lookup"><span data-stu-id="33143-186">To start a session and automate Microsoft Edge \(Chromium\), create a new `EdgeDriver` object and pass it an `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<a name="c"></a><span data-ttu-id="33143-187">C#</span><span class="sxs-lookup"><span data-stu-id="33143-187">C#</span></span>](#tab/c-sharp/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a><span data-ttu-id="33143-188">Python</span><span class="sxs-lookup"><span data-stu-id="33143-188">Python</span></span>](#tab/python/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options = options)
```  

#### [<a name="java"></a><span data-ttu-id="33143-189">Java	</span><span class="sxs-lookup"><span data-stu-id="33143-189">Java</span></span>](#tab/java/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

<span data-ttu-id="33143-190">该类 `EdgeDriver` 仅支持 Microsoft Edge \ (Chromium\) ，不支持 Microsoft Edge \ (EdgeHTML\) 。</span><span class="sxs-lookup"><span data-stu-id="33143-190">The `EdgeDriver` class only supports Microsoft Edge \(Chromium\), and doesn't support Microsoft Edge \(EdgeHTML\).</span></span>  <span data-ttu-id="33143-191">对于基本用法，可以在不提供 `EdgeDriver` 的情况下创建 `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="33143-191">For basic usage, you can create an `EdgeDriver` without providing `EdgeOptions`.</span></span>  

```java
EdgeDriver driver = new EdgeDriver();
```  

#### [<a name="javascript"></a><span data-ttu-id="33143-192">JavaScript</span><span class="sxs-lookup"><span data-stu-id="33143-192">JavaScript</span></span>](#tab/javascript/)  

<a id="drive-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> <span data-ttu-id="33143-193">如果你的 IT 管理员将[DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]策略设置为 ，Microsoft Edge 驱动程序被阻止驱动 `2` Microsoft Edge \ (Chromium\) ，因为驱动程序使用 Microsoft Edge [DevTools][DevtoolsIndex]。 [][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]</span><span class="sxs-lookup"><span data-stu-id="33143-193">If your IT admin has set the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy to `2`,  [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] is blocked from driving Microsoft Edge \(Chromium\), because the driver uses the [Microsoft Edge DevTools][DevtoolsIndex].</span></span>  <span data-ttu-id="33143-194">确保[将 DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]策略设置为 `0` 或 `1` 自动Microsoft Edge (Chromium) 。</span><span class="sxs-lookup"><span data-stu-id="33143-194">Ensure the [DeveloperToolsAvailability][DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability] policy is set to `0` or `1` to automate Microsoft Edge (Chromium).</span></span>  

### <a name="choose-specific-browser-binaries-chromium-only"></a><span data-ttu-id="33143-195">选择"特定浏览器二进制文件 (Chromium仅) </span><span class="sxs-lookup"><span data-stu-id="33143-195">Choose Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="33143-196">可以使用特定文件 \Microsoft Edge\ (Chromium\) WebDriver 会话。</span><span class="sxs-lookup"><span data-stu-id="33143-196">You can start a WebDriver session with specific Microsoft Edge \(Chromium\) binaries.</span></span>  <span data-ttu-id="33143-197">例如，可以使用预览频道（如[Microsoft Edge）][MicrosoftedgeinsiderDownload]运行Microsoft Edge Beta。</span><span class="sxs-lookup"><span data-stu-id="33143-197">For example, you can run tests using the [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<a name="c"></a><span data-ttu-id="33143-198">C#</span><span class="sxs-lookup"><span data-stu-id="33143-198">C#</span></span>](#tab/c-sharp/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<a name="python"></a><span data-ttu-id="33143-199">Python</span><span class="sxs-lookup"><span data-stu-id="33143-199">Python</span></span>](#tab/python/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options = options)
```  

#### [<a name="java"></a><span data-ttu-id="33143-200">Java	</span><span class="sxs-lookup"><span data-stu-id="33143-200">Java</span></span>](#tab/java/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.setBinary("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

EdgeDriver driver = new EdgeDriver(options);
```  

#### [<a name="javascript"></a><span data-ttu-id="33143-201">JavaScript</span><span class="sxs-lookup"><span data-stu-id="33143-201">JavaScript</span></span>](#tab/javascript/)  

<a id="choose-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\\Program Files (x86)\\Microsoft\\Edge Beta\\Application\\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <a name="customize-the-microsoft-edge-driver-service"></a><span data-ttu-id="33143-202">自定义 Microsoft Edge 驱动程序服务</span><span class="sxs-lookup"><span data-stu-id="33143-202">Customize the Microsoft Edge Driver Service</span></span>  

#### [<a name="c"></a><span data-ttu-id="33143-203">C#</span><span class="sxs-lookup"><span data-stu-id="33143-203">C#</span></span>](#tab/c-sharp/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="33143-204">使用 类创建类实例时，它会为 `EdgeOptions` `EdgeDriver` Microsoft Edge `EdgeDriverService` \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 创建和启动相应的类。</span><span class="sxs-lookup"><span data-stu-id="33143-204">When you use the `EdgeOptions` class to create an `EdgeDriver` class instance, it creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="33143-205">如果要创建 ，请使用 方法创建一个配置为 Microsoft Edge `EdgeDriverService` `CreateChromiumService()` \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="33143-205">If you want to create an `EdgeDriverService`, use the `CreateChromiumService()` method to create one configured for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="33143-206">`CreateChromiumService()`当您需要添加自定义项时，该方法非常有用。</span><span class="sxs-lookup"><span data-stu-id="33143-206">The `CreateChromiumService()` method is useful when you need to add customizations.</span></span>  <span data-ttu-id="33143-207">例如，以下代码开始详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="33143-207">For example, the following code starts verbose log output.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
><span data-ttu-id="33143-208">在传递给实例时，不需要 `EdgeOptions` 提供 `EdgeDriverService` `EdgeDriver` 对象。</span><span class="sxs-lookup"><span data-stu-id="33143-208">You do not need to provide the `EdgeOptions` object when you pass `EdgeDriverService` to the `EdgeDriver` instance.</span></span>  <span data-ttu-id="33143-209">该类根据你提供的服务使用 Microsoft Edge `EdgeDriver` \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 的默认选项。</span><span class="sxs-lookup"><span data-stu-id="33143-209">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) based on the service you provide.</span></span>  
> <span data-ttu-id="33143-210">但是，如果要同时提供 和 类，请确保为同一版本的 `EdgeDriverService` `EdgeOptions` Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="33143-210">However, if you want to provide both `EdgeDriverService` and `EdgeOptions` classes, ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="33143-211">例如，可以使用默认的 Microsoft Edge \ (EdgeHTML\) `EdgeDriverService` 类Chromium属性 `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="33143-211">For example, you may use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="33143-212">`EdgeDriver`该类会引发错误，以阻止使用不同的版本。</span><span class="sxs-lookup"><span data-stu-id="33143-212">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<a name="python"></a><span data-ttu-id="33143-213">Python</span><span class="sxs-lookup"><span data-stu-id="33143-213">Python</span></span>](#tab/python/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="33143-214">使用 Python 时， `Edge` 对象将创建和管理 `EdgeService` 。</span><span class="sxs-lookup"><span data-stu-id="33143-214">When you use Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="33143-215">若要配置 `EdgeService` ，请向 对象传递 `Edge` 额外参数，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="33143-215">To configure the `EdgeService`, pass extra arguments to the `Edge` object as indicated in the following code.</span></span>  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<a name="java"></a><span data-ttu-id="33143-216">Java	</span><span class="sxs-lookup"><span data-stu-id="33143-216">Java</span></span>](#tab/java/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="33143-217">使用 `createDefaultService()` 方法可创建 `EdgeDriverService` 一个配置为 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="33143-217">Use the `createDefaultService()` method to create an `EdgeDriverService` configured for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="33143-218">使用 Java 系统属性自定义 Java 中的驱动程序服务。</span><span class="sxs-lookup"><span data-stu-id="33143-218">Use Java system properties to customize driver services in Java.</span></span>  <span data-ttu-id="33143-219">例如，以下代码使用 `"webdriver.edge.verboseLogging"` 属性打开详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="33143-219">For example, the following code uses the `"webdriver.edge.verboseLogging"` property to turn on verbose log output.</span></span>  

```java
System.setProperty("webdriver.edge.verboseLogging", "true");
EdgeDriverService service = EdgeDriverService.createDefaultService();
EdgeOptions options = new EdgeOptions();
EdgeDriver driver = new EdgeDriver(service, options);
```  

#### [<a name="javascript"></a><span data-ttu-id="33143-220">JavaScript</span><span class="sxs-lookup"><span data-stu-id="33143-220">JavaScript</span></span>](#tab/javascript/)  

<a id="customize-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="33143-221">使用 JavaScript 时，请使用 类 `Service` 创建和 `ServiceBuilder` 配置 。</span><span class="sxs-lookup"><span data-stu-id="33143-221">When you use JavaScript, create and configure a `Service` with the `ServiceBuilder` class.</span></span>  <span data-ttu-id="33143-222">（可选）可以将对象传递给对象，该对象将启动 `Service` `Driver` \ (并停止\) 服务。</span><span class="sxs-lookup"><span data-stu-id="33143-222">Optionally, you can pass the `Service` object to the `Driver` object, which starts \(and stops\) the service for you.</span></span>  
<span data-ttu-id="33143-223">若要配置 `Service` ，请运行 类中的另一 `ServiceBuilder` 个方法，然后再使用 `build()` 方法。</span><span class="sxs-lookup"><span data-stu-id="33143-223">To configure the `Service`, run another method in the `ServiceBuilder` class before you use the `build()` method.</span></span>  <span data-ttu-id="33143-224">然后， `service` 在 方法中将 作为 参数 `Driver.createSession()` 传递。</span><span class="sxs-lookup"><span data-stu-id="33143-224">Then pass the `service` as a parameter in the `Driver.createSession()` method.</span></span>  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <a name="use-chromium-specific-options"></a><span data-ttu-id="33143-225">使用Chromium-Specific选项</span><span class="sxs-lookup"><span data-stu-id="33143-225">Use Chromium-Specific Options</span></span>  

<span data-ttu-id="33143-226">如果将 属性设置为 ，可以使用 类来访问Chromium自动化其他浏览器时所使用的特定于 Chromium `UseChromium` `true` `EdgeOptions` 的属性和方法。 [][WebdriverCapabilitiesEdgeOptions]</span><span class="sxs-lookup"><span data-stu-id="33143-226">If you set the `UseChromium` property to `true`, you can use the `EdgeOptions` class to access the same [Chromium-specific properties and methods][WebdriverCapabilitiesEdgeOptions] that are used when you automate other Chromium browsers.</span></span>  

#### [<a name="c"></a><span data-ttu-id="33143-227">C#</span><span class="sxs-lookup"><span data-stu-id="33143-227">C#</span></span>](#tab/c-sharp/)  

<a id="use-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<a name="python"></a><span data-ttu-id="33143-228">Python</span><span class="sxs-lookup"><span data-stu-id="33143-228">Python</span></span>](#tab/python/)  

<a id="use-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<a name="java"></a><span data-ttu-id="33143-229">Java	</span><span class="sxs-lookup"><span data-stu-id="33143-229">Java</span></span>](#tab/java/)  

<a id="use-chromium-specific-options-code"></a>  

```java
EdgeOptions options = new EdgeOptions();
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

#### [<a name="javascript"></a><span data-ttu-id="33143-230">JavaScript</span><span class="sxs-lookup"><span data-stu-id="33143-230">JavaScript</span></span>](#tab/javascript/)  

<a id="use-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```  

* * *  

> [!NOTE]
> <span data-ttu-id="33143-231">如果属性设置为 ，则不能对 Microsoft Edge `UseChromium` `true` \ (EdgeHTML\) 。</span><span class="sxs-lookup"><span data-stu-id="33143-231">If the `UseChromium` property is set to `true`, you are not able to use properties and methods for Microsoft Edge \(EdgeHTML\).</span></span>  

## <a name="other-webdriver-installation-options"></a><span data-ttu-id="33143-232">其他 WebDriver 安装选项</span><span class="sxs-lookup"><span data-stu-id="33143-232">Other WebDriver installation options</span></span>  

### <a name="docker"></a><span data-ttu-id="33143-233">Docker</span><span class="sxs-lookup"><span data-stu-id="33143-233">Docker</span></span>  

<span data-ttu-id="33143-234">如果使用[Docker，][DockerHub]请运行以下命令，下载预配置映像Microsoft Edge \ (Chromium\) Microsoft Edge[驱动程序][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver]预安装。</span><span class="sxs-lookup"><span data-stu-id="33143-234">If you use [Docker][DockerHub], run the following command to download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeToolsWebdriver] pre-installed.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="33143-235">有关详细信息，请导航到 Docker Hub 上的 [msedgedriver 容器][DockerHubMsedgedriver]。</span><span class="sxs-lookup"><span data-stu-id="33143-235">For more information, navigate to the [msedgedriver container on Docker Hub][DockerHubMsedgedriver].</span></span>  

## <a name="testing-internet-explorer"></a><span data-ttu-id="33143-236">测试Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="33143-236">Testing Internet Explorer</span></span>

<span data-ttu-id="33143-237">即使Microsoft Edge支持 IE 模式，你Microsoft Edge驱动程序Microsoft Edge IE 模式下测试站点。</span><span class="sxs-lookup"><span data-stu-id="33143-237">Even though Microsoft Edge supports IE Mode, you can't use Microsoft Edge Driver with Microsoft Edge to test sites in IE Mode.</span></span>  <span data-ttu-id="33143-238">若要测试需要更新Internet Explorer，Internet Explorer [驱动程序][GithubSeleniumHqWikiIEDriver] 和Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="33143-238">To test sites that require Internet Explorer, use [Internet Explorer Driver][GithubSeleniumHqWikiIEDriver] with Internet Explorer.</span></span>

## <a name="application-guard"></a><span data-ttu-id="33143-239">应用程序防护</span><span class="sxs-lookup"><span data-stu-id="33143-239">Application Guard</span></span>

<span data-ttu-id="33143-240">使用应用程序防护Microsoft Defender 应用程序防护 (的) 可以使用驱动程序自动Microsoft Edge站点。</span><span class="sxs-lookup"><span data-stu-id="33143-240">Trusted sites that use Microsoft Defender Application Guard (Application Guard) can be automated using Microsoft Edge Driver.</span></span>

<span data-ttu-id="33143-241">使用应用程序防护的不受信任的站点无法使用应用程序驱动程序自动Microsoft Edge操作。</span><span class="sxs-lookup"><span data-stu-id="33143-241">Untrusted sites that use Application Guard cannot be automated or manipulated using Microsoft Edge Driver.</span></span>  <span data-ttu-id="33143-242">应用程序防护在容器中启动不受信任的站点，并且此容器不会公开驱动程序与站点Microsoft Edge所需的远程调试端口。</span><span class="sxs-lookup"><span data-stu-id="33143-242">Application Guard launches untrusted sites in a container, and this container doesn't expose the remote debugging port that Microsoft Edge Driver needs to communicate with the site.</span></span>

<span data-ttu-id="33143-243">企业管理员定义什么是受信任的站点，包括云资源和内部网络。</span><span class="sxs-lookup"><span data-stu-id="33143-243">Your enterprise administrator defines what are trusted sites, including cloud resources and internal networks.</span></span>  <span data-ttu-id="33143-244">不在受信任站点列表中的网站被视为不受信任的网站。</span><span class="sxs-lookup"><span data-stu-id="33143-244">Sites that aren't in the trusted sites list are considered untrusted.</span></span>  <span data-ttu-id="33143-245">Microsoft Edge驱动程序可以自动执行 InPrivate 窗口和受信任站点列表中的站点。</span><span class="sxs-lookup"><span data-stu-id="33143-245">Microsoft Edge Driver can automate both InPrivate windows, and sites in the trusted sites list.</span></span>

<span data-ttu-id="33143-246">有关应用程序防护详细信息，请导航到：</span><span class="sxs-lookup"><span data-stu-id="33143-246">For more information about Application Guard, navigate to:</span></span> 

*  [<span data-ttu-id="33143-247">Microsoft Edge 对 Microsoft Defender 应用程序防护的支持</span><span class="sxs-lookup"><span data-stu-id="33143-247">Microsoft Edge support for Microsoft Defender Application Guard</span></span>](/deployedge/microsoft-edge-security-windows-defender-application-guard)
*  [<span data-ttu-id="33143-248">Microsoft Defender 应用程序防护概述</span><span class="sxs-lookup"><span data-stu-id="33143-248">Microsoft Defender Application Guard overview</span></span>][WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]

## <a name="next-steps"></a><span data-ttu-id="33143-249">后续步骤</span><span class="sxs-lookup"><span data-stu-id="33143-249">Next steps</span></span>  

<span data-ttu-id="33143-250">有关 WebDriver 和如何使用 Selenium 编写自动 WebDriver 测试的信息，请导航到 [Selenium 文档][SeleniumDocumentation]。</span><span class="sxs-lookup"><span data-stu-id="33143-250">For more information about WebDriver and how to write automated WebDriver tests using Selenium, navigate to the [Selenium documentation][SeleniumDocumentation].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="33143-251">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="33143-251">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="33143-252">该Microsoft Edge团队希望倾听你有关使用 WebDriver、Selenium 和 Microsoft Edge 的反馈。</span><span class="sxs-lookup"><span data-stu-id="33143-252">The Microsoft Edge team is eager to hear your feedback about using WebDriver, Selenium, and Microsoft Edge.</span></span>  <span data-ttu-id="33143-253">若要向团队发送你的问题和意见，请选择开发人员工具Microsoft Edge\*\*\*\* 发送反馈图标或发送推文[@EdgeDevTools。][TwitterTweetEdgeDevTools]</span><span class="sxs-lookup"><span data-stu-id="33143-253">To send the team your questions and comments, choose the **Send Feedback** icon in the Microsoft Edge DevTools or send a tweet [@EdgeDevTools][TwitterTweetEdgeDevTools].</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="33143-255">Microsoft Edge DevTools 中的**发送反馈**图标</span><span class="sxs-lookup"><span data-stu-id="33143-255">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- links -->  

[DevtoolsIndex]: ../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[WebdriverCapabilitiesEdgeOptions]: ./capabilities-edge-options.md "功能和 EdgeOptions |Microsoft Docs"  

<!--[Webdriver]: /archive/microsoft-edge/legacy/developer/webdriver/index "WebDriver (EdgeHTML) | Microsoft Docs"  -->  

[DeployedgeMicrosoftEdgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability - Microsoft Edge - 策略|Microsoft Docs"  
[WindowsSecurityThreatProtectionMicrosoftDefenderApplicationGuardWindows10]: /windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview "Microsoft Defender 应用程序防护 (Windows 10) - Windows安全|Microsoft Docs"  
[DeployedgeMicrosoftEdgeSecurityWindowsDefenderApplicationGuard]: /deployedge/microsoft-edge-security-windows-defender-application-guard "Microsoft Edge支持Microsoft Defender 应用程序防护 |Microsoft Docs"

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
[SeleniumDownloads]: https://selenium.dev/downloads "下载|Selenium"  
[SeleniumInstallingLibraries]: https://www.selenium.dev/documentation/en/selenium_installation/installing_selenium_libraries "安装 Selenium 库|Selenium"

[SonatypeMavenRepositorySearch]: https://search.maven.org/artifact/com.microsoft.edge/msedge-selenium-tools-java/3.141.0/jar "Sonatype Maven 中央存储库搜索|com.microsoft.edge：msedge-selenium-tools-java"

[TwitterTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools |发布推文"  

[VisualStudio]: https://visualstudio.microsoft.com/ "Visual Studio"  

[W3CWebdriver]: https://w3.org/TR/webdriver2 "WebDriver |W3C"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无头浏览器|Wikipedia"  
