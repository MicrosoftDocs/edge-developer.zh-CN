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
# <span data-ttu-id="1eef6-104">使用 WebDriver (Chromium) 测试自动化概述</span><span class="sxs-lookup"><span data-stu-id="1eef6-104">Use WebDriver (Chromium) for test automation overview</span></span>  

<span data-ttu-id="1eef6-105">利用 WebDriver，你可以\ (开发人员\) 创建模拟用户交互的自动测试。</span><span class="sxs-lookup"><span data-stu-id="1eef6-105">WebDriver enables you \(developers\) to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="1eef6-106">由于以下原因，WebDriver 测试和模拟不同于 JavaScript 单元测试。</span><span class="sxs-lookup"><span data-stu-id="1eef6-106">WebDriver tests and simulations differ from JavaScript unit tests because of the following reasons.</span></span>  

*   <span data-ttu-id="1eef6-107">访问在浏览器中运行的 JavaScript 不可用的功能和信息。</span><span class="sxs-lookup"><span data-stu-id="1eef6-107">Accesses functionality and information not available to JavaScript running in browsers.</span></span>  
*   <span data-ttu-id="1eef6-108">更精确地模拟用户事件或操作系统级事件。</span><span class="sxs-lookup"><span data-stu-id="1eef6-108">Simulates user events or OS-level events more accurately.</span></span>  
*   <span data-ttu-id="1eef6-109">在单个测试会话中管理多个窗口、选项卡和网页。</span><span class="sxs-lookup"><span data-stu-id="1eef6-109">Manages multiple windows, tabs, and webpages in a single test session.</span></span>  
*   <span data-ttu-id="1eef6-110">在特定的计算机上运行 Microsoft Edge 的多个会话。</span><span class="sxs-lookup"><span data-stu-id="1eef6-110">Runs multiple sessions of Microsoft Edge on a specific machine.</span></span>  
    
<span data-ttu-id="1eef6-111">以下部分介绍如何开始使用适用于 Microsoft Edge 的 WebDriver \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="1eef6-111">The following section describes how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  

## <span data-ttu-id="1eef6-112">安装 Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="1eef6-112">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="1eef6-113">确保安装[Microsoft Edge (Chromium) 。 ][MicrosoftEdge]</span><span class="sxs-lookup"><span data-stu-id="1eef6-113">Ensure you install [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="1eef6-114">若要确认已安装 Microsoft Edge \ (Chromium\) ，请导航到并验证版本号是版本 `edge://settings/help` 75 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1eef6-114">To confirm that you have Microsoft Edge \(Chromium\) installed, navigate to `edge://settings/help`, and verify the version number is Version 75 or later.</span></span>  

## <span data-ttu-id="1eef6-115">下载 Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="1eef6-115">Download Microsoft Edge Driver</span></span>  

<span data-ttu-id="1eef6-116">若要开始自动执行测试，请使用以下步骤来确保安装的 WebDriver 版本与浏览器版本匹配。</span><span class="sxs-lookup"><span data-stu-id="1eef6-116">To begin automating tests, use the following steps to ensure that the WebDriver version you install matches your browser version.</span></span>  

1.  <span data-ttu-id="1eef6-117">导航 `edge://settings/help` 到获取 Microsoft Edge 的版本。</span><span class="sxs-lookup"><span data-stu-id="1eef6-117">Navigate to `edge://settings/help` to get the version of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="./media/edge-version.png" alt-text="2020 年 1 月 14 日 Microsoft Edge Canary 的生成号":::
       <span data-ttu-id="1eef6-119">2020 年 1 月 14 日 Microsoft Edge Canary 的生成号</span><span class="sxs-lookup"><span data-stu-id="1eef6-119">The build number for Microsoft Edge Canary on January 14, 2020</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="1eef6-120">导航到 [Microsoft Edge 驱动程序下载][MicrosoftDeveloperEdgeToolsWebdriverDownloads] 页面，并下载与 Microsoft Edge 的版本号匹配的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="1eef6-120">Navigate to the [Microsoft Edge Driver downloads][MicrosoftDeveloperEdgeToolsWebdriverDownloads] page and download the driver that matches the version number of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="./media/edge-driver-install.png" alt-text="Microsoft Edge 驱动程序页的"下载"部分":::
       <span data-ttu-id="1eef6-122">Microsoft Edge 驱动程序页的"下载 ["][MicrosoftDeveloperEdgeToolsWebdriver] 部分</span><span class="sxs-lookup"><span data-stu-id="1eef6-122">The Downloads section of the [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] page</span></span>
    :::image-end:::  
    
    <!--  
    > [!NOTE] 
    > For more information about test automation using Microsoft Edge (EdgeHTML), see [Microsoft WebDriver for Microsoft Edge (EdgeHTML)][Webdriver].  
    -->  

## <span data-ttu-id="1eef6-123">选择 WebDriver 语言绑定</span><span class="sxs-lookup"><span data-stu-id="1eef6-123">Choose a WebDriver language binding</span></span>  

<span data-ttu-id="1eef6-124">必须下载的最后一个组件是特定语言的客户端驱动程序，用于将代码 \ (Python、Java、C\#、Ruby、JavaScript\) 转换为 Microsoft Edge \ (Chromium\) 中运行的命令。</span><span class="sxs-lookup"><span data-stu-id="1eef6-124">The last component you must download is a language-specific client driver to translate your code \(Python, Java, C\#, Ruby, JavaScript\) into commands the Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="1eef6-125">[下载你选择的 WebDriver 语言绑定][SeleniumDownloads]。</span><span class="sxs-lookup"><span data-stu-id="1eef6-125">[Download the WebDriver language binding of your choice][SeleniumDownloads].</span></span>  <span data-ttu-id="1eef6-126">Microsoft Edge 团队建议使用 [Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05] 或更高版本，因为它支持 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="1eef6-126">The Microsoft Edge team recommends [Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05] or later, because it supports Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="1eef6-127">但是，你可以控制所有较旧版本的 Selenium 中的 Microsoft Edge \ (Chromium\) ，包括当前稳定的 Selenium 3 版本。</span><span class="sxs-lookup"><span data-stu-id="1eef6-127">However, you may control Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="1eef6-128">如果之前使用和类自动执行或测试 Microsoft Edge \ (Chromium\) ，则 WebDriver 代码不会在 Microsoft Edge 版本 80 或更高版本中 `ChromeDriver` `ChromeOptions` 运行。</span><span class="sxs-lookup"><span data-stu-id="1eef6-128">If you were previously automating or testing Microsoft Edge \(Chromium\) using `ChromeDriver` and `ChromeOptions` classes, your WebDriver code does not run on Microsoft Edge Version 80 or later.</span></span>  <span data-ttu-id="1eef6-129">若要解决此问题，请更新测试以使用 `EdgeOptions` 该类并安装 Microsoft [Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="1eef6-129">To solve this problem, update your tests to use the `EdgeOptions` class and install [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver].</span></span>  

### <span data-ttu-id="1eef6-130">使用 Selenium 3</span><span class="sxs-lookup"><span data-stu-id="1eef6-130">Use Selenium 3</span></span>  

<span data-ttu-id="1eef6-131">如果你已使用 [Selenium 3，][|::ref1::|]你可能已有浏览器测试，并且想要添加 Microsoft Edge \ (Chromium\) 的覆盖范围，而无需更改 Selenium 版本。</span><span class="sxs-lookup"><span data-stu-id="1eef6-131">If you already use [Selenium 3][|::ref1::|], you may have existing browser tests and want to add coverage for Microsoft Edge \(Chromium\) without changing your version of Selenium.</span></span>  <span data-ttu-id="1eef6-132">若要使用 [Selenium 3][|::ref2::|] 为 Microsoft Edge \ (EdgeHTML\) 和 Microsoft Edge \ (Chromium\) 编写自动测试，请安装适用于 Microsoft Edge 的 [Selenium 工具][GithubMicrosoftEdgeSeleniumTools] 程序包以使用更新的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="1eef6-132">To use [Selenium 3][|::ref2::|] to write automated tests for both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package to use the updated driver.</span></span>  <span data-ttu-id="1eef6-133">工具 `EdgeDriver` `EdgeDriverService` 中包含的类与 Selenium 4 中的内置等效项完全兼容。</span><span class="sxs-lookup"><span data-stu-id="1eef6-133">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium 4.</span></span>  

<span data-ttu-id="1eef6-134">使用以下步骤将适用于 Microsoft Edge 和[Selenium 3][|::ref3::|]的[Selenium 工具][GithubMicrosoftEdgeSeleniumTools]添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="1eef6-134">Use the following steps to add the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] and [Selenium 3][|::ref3::|] to your project.</span></span>

#### [<span data-ttu-id="1eef6-135">C#</span><span class="sxs-lookup"><span data-stu-id="1eef6-135">C#</span></span>](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="1eef6-136">使用[NuGet CLI][NugetCLI]或 Visual Studio 将[Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools]和[Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] [包添加到 .NET Visual Studio。][VisualStudio]</span><span class="sxs-lookup"><span data-stu-id="1eef6-136">Add the [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] and [Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] packages to your .NET project using the [NuGet CLI][NugetCLI] or [Visual Studio][VisualStudio].</span></span>  

#### [<span data-ttu-id="1eef6-137">Python</span><span class="sxs-lookup"><span data-stu-id="1eef6-137">Python</span></span>](#tab/python/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="1eef6-138">使用 [管道][PythonPip] 安装 [msedge-selenium-tools][PythonSeleniumTools] 和 [selenium][PythonSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="1eef6-138">Use [pip][PythonPip] to install the [msedge-selenium-tools][PythonSeleniumTools] and [selenium][PythonSelenium] packages.</span></span>  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<span data-ttu-id="1eef6-139">JavaScript</span><span class="sxs-lookup"><span data-stu-id="1eef6-139">JavaScript</span></span>](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="1eef6-140">使用 [npm][JavaScript|::ref4::|] 安装 [edge-selenium-tools][JavaScriptSeleniumTools] 和 [selenium-webdriver][JavaScriptSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="1eef6-140">Use [npm][JavaScript|::ref4::|] to install the [edge-selenium-tools][JavaScriptSeleniumTools] and [selenium-webdriver][JavaScriptSelenium] packages.</span></span>  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## <span data-ttu-id="1eef6-141">将 Microsoft Edge (Chromium) WebDriver</span><span class="sxs-lookup"><span data-stu-id="1eef6-141">Use Microsoft Edge (Chromium) with WebDriver</span></span>

<span data-ttu-id="1eef6-142">可以使用 Selenium 3 或 4 运行以下示例。</span><span class="sxs-lookup"><span data-stu-id="1eef6-142">You may run the following examples using either Selenium 3 or 4.</span></span>  <span data-ttu-id="1eef6-143">若要与 Selenium 3 一起使用，必须安装适用于 Microsoft Edge 的 [Selenium][GithubMicrosoftEdgeSeleniumTools] 工具包。</span><span class="sxs-lookup"><span data-stu-id="1eef6-143">To use with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package must be installed.</span></span>  

### <span data-ttu-id="1eef6-144">基本用法</span><span class="sxs-lookup"><span data-stu-id="1eef6-144">Basic Usage</span></span>  

<span data-ttu-id="1eef6-145">若要与 Microsoft Edge \ (EdgeHTML\) 一起使用，请创建类的默认 `EdgeDriver` 实例。</span><span class="sxs-lookup"><span data-stu-id="1eef6-145">To use with Microsoft Edge \(EdgeHTML\), create a default instance of the `EdgeDriver` class.</span></span>  

#### [<span data-ttu-id="1eef6-146">C#</span><span class="sxs-lookup"><span data-stu-id="1eef6-146">C#</span></span>](#tab/c-sharp/)  

<a id="basic-usage-code"></a>  

```csharp
var driver = new EdgeDriver();
```  

#### [<span data-ttu-id="1eef6-147">Python</span><span class="sxs-lookup"><span data-stu-id="1eef6-147">Python</span></span>](#tab/python/)  

<a id="basic-usage-code"></a>  

```python
driver = Edge()
```  

#### [<span data-ttu-id="1eef6-148">JavaScript</span><span class="sxs-lookup"><span data-stu-id="1eef6-148">JavaScript</span></span>](#tab/javascript/)  

<a id="basic-usage-code"></a>  

```javascript
let driver = edge.Driver.createSession();
```  

* * *  

### <span data-ttu-id="1eef6-149">驱动 Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="1eef6-149">Driving Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="1eef6-150">若要与 Microsoft Edge \ (Chromium\) 一起使用，请创建一个新类，并传递属性设置为 `EdgeDriver` `EdgeOptions` `UseChromium` `true` 的对象。</span><span class="sxs-lookup"><span data-stu-id="1eef6-150">To use with Microsoft Edge \(Chromium\), create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<span data-ttu-id="1eef6-151">C#</span><span class="sxs-lookup"><span data-stu-id="1eef6-151">C#</span></span>](#tab/c-sharp/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="1eef6-152">Python</span><span class="sxs-lookup"><span data-stu-id="1eef6-152">Python</span></span>](#tab/python/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

#### [<span data-ttu-id="1eef6-153">JavaScript</span><span class="sxs-lookup"><span data-stu-id="1eef6-153">JavaScript</span></span>](#tab/javascript/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> <span data-ttu-id="1eef6-154">如果你的 IT 管理员将[DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability]策略设置为 ，Microsoft Edge 驱动程序无法驱动 `2` Microsoft Edge ([Chromium) ][MicrosoftEdge]因为驱动程序使用[Microsoft Edge DevTools。][DevToolsMain] [][MicrosoftDeveloperEdgeToolsWebdriver]</span><span class="sxs-lookup"><span data-stu-id="1eef6-154">If your IT admin has set the [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] policy to `2`, [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] is not be able to drive [Microsoft Edge (Chromium)][MicrosoftEdge] because the driver uses the [Microsoft Edge DevTools][DevToolsMain].</span></span>  <span data-ttu-id="1eef6-155">确保[将 DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability]策略设置为或自动执行 Microsoft Edge (`0` `1` [Chromium) 。 ][MicrosoftEdge]</span><span class="sxs-lookup"><span data-stu-id="1eef6-155">Ensure the [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] policy is set to `0` or `1` to automate [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  

### <span data-ttu-id="1eef6-156">选择特定浏览器二进制文件 (仅 Chromium) </span><span class="sxs-lookup"><span data-stu-id="1eef6-156">Choosing Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="1eef6-157">你可以将该类 `EdgeOptions` 与 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="1eef6-157">You may use the `EdgeOptions` class with specific binaries of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="1eef6-158">例如，可以使用 [Microsoft Edge][MicrosoftedgeinsiderDownload] 预览频道（如 Microsoft Edge Beta）运行测试。</span><span class="sxs-lookup"><span data-stu-id="1eef6-158">For example, you may run tests using the [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<span data-ttu-id="1eef6-159">C#</span><span class="sxs-lookup"><span data-stu-id="1eef6-159">C#</span></span>](#tab/c-sharp/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="1eef6-160">Python</span><span class="sxs-lookup"><span data-stu-id="1eef6-160">Python</span></span>](#tab/python/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

#### [<span data-ttu-id="1eef6-161">JavaScript</span><span class="sxs-lookup"><span data-stu-id="1eef6-161">JavaScript</span></span>](#tab/javascript/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <span data-ttu-id="1eef6-162">自定义 Microsoft Edge 驱动程序服务</span><span class="sxs-lookup"><span data-stu-id="1eef6-162">Customizing the Microsoft Edge Driver Service</span></span>  

#### [<span data-ttu-id="1eef6-163">C#</span><span class="sxs-lookup"><span data-stu-id="1eef6-163">C#</span></span>](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="1eef6-164">使用类创建类实例时，它会为 `EdgeDriver` `EdgeOptions` Microsoft Edge `EdgeDriverService` \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 创建和启动相应的类。</span><span class="sxs-lookup"><span data-stu-id="1eef6-164">When an `EdgeDriver` class instance is created using `EdgeOptions` class, it creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="1eef6-165">如果要创建一个 ，请创建一个为 `EdgeDriverService` Microsoft Edge \ (Chromium\) 方法 `CreateChromiumService()` 。</span><span class="sxs-lookup"><span data-stu-id="1eef6-165">If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.</span></span>  <span data-ttu-id="1eef6-166">您可能会发现它可用于其他自定义项，如在下面的代码中启用详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="1eef6-166">You may find it useful for additional customizations like enabling verbose log output in the following code.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
><span data-ttu-id="1eef6-167">在传递给实例时，不需要 `EdgeOptions` `EdgeDriverService` 提供 `EdgeDriver` 对象。</span><span class="sxs-lookup"><span data-stu-id="1eef6-167">You do not need to provide the `EdgeOptions` object when passing `EdgeDriverService` to the `EdgeDriver` instance.</span></span> <span data-ttu-id="1eef6-168">该类使用 `EdgeDriver` Microsoft Edge \ (EdgeHTML\) 或 Microsoft Edge \ (Chromium\) 的默认选项，具体取决于你提供的服务。</span><span class="sxs-lookup"><span data-stu-id="1eef6-168">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) depending on the service you provide.</span></span>  
> <span data-ttu-id="1eef6-169">但是，如果要同时提供这两个类和类，请确保为相同版本的 Microsoft Edge 配置这两 `EdgeDriverService` `EdgeOptions` 者。</span><span class="sxs-lookup"><span data-stu-id="1eef6-169">However, if you want to provide both `EdgeDriverService` and `EdgeOptions` classes, ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="1eef6-170">例如，在该类中不能使用默认的 Microsoft Edge \ (EdgeHTML\) 类和 `EdgeDriverService` Chromium `EdgeOptions` 属性。</span><span class="sxs-lookup"><span data-stu-id="1eef6-170">For example, it is not possible to use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="1eef6-171">该类 `EdgeDriver` 会引发错误，以防止使用不同的版本。</span><span class="sxs-lookup"><span data-stu-id="1eef6-171">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<span data-ttu-id="1eef6-172">Python</span><span class="sxs-lookup"><span data-stu-id="1eef6-172">Python</span></span>](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="1eef6-173">使用 Python 时 `Edge` ，对象将创建和管理 `EdgeService` 。</span><span class="sxs-lookup"><span data-stu-id="1eef6-173">When using Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="1eef6-174">若要配置 `EdgeService` ，请向对象传递 `Edge` 其他参数，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="1eef6-174">To configure the `EdgeService`, pass additional arguments to the `Edge` object as indicated in the following code.</span></span>  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<span data-ttu-id="1eef6-175">JavaScript</span><span class="sxs-lookup"><span data-stu-id="1eef6-175">JavaScript</span></span>](#tab/javascript/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="1eef6-176">使用 JavaScript 时，使用类 `Service` 创建和 `ServiceBuilder` 配置。</span><span class="sxs-lookup"><span data-stu-id="1eef6-176">When using JavaScript, create and configure a `Service` with the `ServiceBuilder` class.</span></span>  <span data-ttu-id="1eef6-177">或者，你可以将对象传递给该对象，该对象将启动 `Service` `Driver` \ (并停止\) 服务。</span><span class="sxs-lookup"><span data-stu-id="1eef6-177">Optionally, you may pass the `Service` object to the `Driver` object, which starts \(and stops\) the service for you.</span></span>  
<span data-ttu-id="1eef6-178">若要配置 `Service` ，请运行类中的其他 `ServiceBuilder` 方法，然后再使用 `build()` 该方法。</span><span class="sxs-lookup"><span data-stu-id="1eef6-178">To configure the `Service`, run additional methods in the `ServiceBuilder` class before using the `build()` method.</span></span>  <span data-ttu-id="1eef6-179">然后作为 `service` 参数在方法中 `Driver.createSession()` 传递。</span><span class="sxs-lookup"><span data-stu-id="1eef6-179">Then pass the `service` as a parameter in the `Driver.createSession()` method.</span></span>  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <span data-ttu-id="1eef6-180">使用Chromium-Specific选项</span><span class="sxs-lookup"><span data-stu-id="1eef6-180">Use Chromium-Specific Options</span></span>  

<span data-ttu-id="1eef6-181">如果将该属性设置为 ，可以使用类访问与自动执行其他 Chromium 浏览器时相同的 `UseChromium` `true` 特定于 `EdgeOptions` [Chromium][SeleniumWebDriverChromeoptionsClass] 的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="1eef6-181">If you set the `UseChromium` property to `true`, you may use the `EdgeOptions` class to access the same [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] as when you automate other Chromium browsers.</span></span>  

#### [<span data-ttu-id="1eef6-182">C#</span><span class="sxs-lookup"><span data-stu-id="1eef6-182">C#</span></span>](#tab/c-sharp/)  

<a id="using-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<span data-ttu-id="1eef6-183">Python</span><span class="sxs-lookup"><span data-stu-id="1eef6-183">Python</span></span>](#tab/python/)  

<a id="using-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<span data-ttu-id="1eef6-184">JavaScript</span><span class="sxs-lookup"><span data-stu-id="1eef6-184">JavaScript</span></span>](#tab/javascript/)  

<a id="using-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```

* * *  

> [!NOTE]
> <span data-ttu-id="1eef6-185">如果该属性设置为，则不能对 `UseChromium` Microsoft Edge `true` \ (EdgeHTML\) 。</span><span class="sxs-lookup"><span data-stu-id="1eef6-185">If the `UseChromium` property is set to `true`, you are not able to use properties and methods for Microsoft Edge \(EdgeHTML\).</span></span>  

## <span data-ttu-id="1eef6-186">其他 WebDriver 安装选项</span><span class="sxs-lookup"><span data-stu-id="1eef6-186">Additional WebDriver installation options</span></span>  

### <span data-ttu-id="1eef6-187">百年</span><span class="sxs-lookup"><span data-stu-id="1eef6-187">Chocolatey</span></span>  

<span data-ttu-id="1eef6-188">如果你使用 [Microsofty][Chocolatey] 作为程序包管理器，请运行以下命令来安装 Microsoft Edge 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="1eef6-188">If you use [Chocolatey][Chocolatey] as your package manager, install the Microsoft Edge Driver by running the following command.</span></span>  

```console
choco install selenium-chromium-edge-driver
```  

<span data-ttu-id="1eef6-189">有关详细信息，请参阅 [Selenium Chromium Edge Driver on 一角][ChocolateyPackagesSeleniumChromiumEdgeDriver]。</span><span class="sxs-lookup"><span data-stu-id="1eef6-189">For more information, see [Selenium Chromium Edge Driver on Chocolatey][ChocolateyPackagesSeleniumChromiumEdgeDriver].</span></span>  

### <span data-ttu-id="1eef6-190">Docker</span><span class="sxs-lookup"><span data-stu-id="1eef6-190">Docker</span></span>  

<span data-ttu-id="1eef6-191">如果使用 [Docker，][DockerHub]请通过运行以下命令，下载预配置映像和 Microsoft Edge \ (Chromium\) 和预安装的 [Microsoft Edge][MicrosoftDeveloperEdgeToolsWebdriver] 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="1eef6-191">If you use [Docker][DockerHub], download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] pre-installed by running the following command.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="1eef6-192">有关详细信息，请参阅 [Docker Hub 上的容器][DockerHubMsedgedriver]。</span><span class="sxs-lookup"><span data-stu-id="1eef6-192">For more information, see [container on Docker Hub][DockerHubMsedgedriver].</span></span>  

## <span data-ttu-id="1eef6-193">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="1eef6-193">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="1eef6-194">Microsoft Edge 团队希望倾听你有关使用 WebDriver、Selenium 和 Microsoft Edge 的反馈。</span><span class="sxs-lookup"><span data-stu-id="1eef6-194">The Microsoft Edge team is eager to hear your feedback about using WebDriver, Selenium, and Microsoft Edge.</span></span>  <span data-ttu-id="1eef6-195">若要让团队了解你的想法，请选择 Microsoft \*\*\*\* Edge DevTools 中的"发送反馈"图标或发送推文[@EdgeDevTools。][TwitterTweetEdgeDevTools]</span><span class="sxs-lookup"><span data-stu-id="1eef6-195">To let the team know what you think, choose the **Send Feedback** icon in the Microsoft Edge DevTools or send a tweet [@EdgeDevTools][TwitterTweetEdgeDevTools].</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="1eef6-197">Microsoft **Edge** DevTools 中的"发送反馈"图标</span><span class="sxs-lookup"><span data-stu-id="1eef6-197">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
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
