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
# <span data-ttu-id="e1a0b-104">使用 WebDriver (Chromium) 进行测试自动化</span><span class="sxs-lookup"><span data-stu-id="e1a0b-104">Use WebDriver (Chromium) for test automation</span></span>  

<span data-ttu-id="e1a0b-105">WebDriver 使你 (开发人员 \ ) 创建模拟用户交互的自动测试。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-105">WebDriver enables you \(developers\) to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="e1a0b-106">由于以下原因，WebDriver 测试和模拟与 JavaScript 单元测试不同。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-106">WebDriver tests and simulations differ from JavaScript unit tests because of the following reasons.</span></span>  

*   <span data-ttu-id="e1a0b-107">访问功能和信息在浏览器中运行的 JavaScript 不可用。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-107">Accesses functionality and information not available to JavaScript running in browsers.</span></span>  
*   <span data-ttu-id="e1a0b-108">更准确地模拟用户事件或 OS 级别的事件。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-108">Simulates user events or OS-level events more accurately.</span></span>  
*   <span data-ttu-id="e1a0b-109">在单个测试会话中管理多个窗口、选项卡和网页。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-109">Manages multiple windows, tabs, and webpages in a single test session.</span></span>  
*   <span data-ttu-id="e1a0b-110">在特定计算机上运行多个 Microsoft Edge 会话。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-110">Runs multiple sessions of Microsoft Edge on a specific machine.</span></span>  
    
<span data-ttu-id="e1a0b-111">以下部分介绍了如何开始使用 Microsoft Edge \ (Chromium \ ) 的 WebDriver。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-111">The following section describes how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  

## <span data-ttu-id="e1a0b-112">安装 Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="e1a0b-112">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="e1a0b-113">确保安装 [Microsoft Edge (Chromium) ][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-113">Ensure you install [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="e1a0b-114">若要确认已安装 Microsoft Edge \ (Chromium \ ) 已安装，请导航到版本 `edge://settings/help` 75 或更高版本，并验证版本号是版本还是更高版本。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-114">To confirm that you have Microsoft Edge \(Chromium\) installed, navigate to `edge://settings/help`, and verify the version number is Version 75 or later.</span></span>  

## <span data-ttu-id="e1a0b-115">下载 Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="e1a0b-115">Download Microsoft Edge Driver</span></span>  

<span data-ttu-id="e1a0b-116">若要开始自动测试，请使用以下步骤确保所安装的 WebDriver 版本与你的浏览器版本相匹配。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-116">To begin automating tests, use the following steps to ensure that the WebDriver version you install matches your browser version.</span></span>  

1.  <span data-ttu-id="e1a0b-117">导航到 `edge://settings/help` 以获取 Microsoft Edge 的版本。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-117">Navigate to `edge://settings/help` to get the version of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/webdriver-chromium/edge-version.png" alt-text="2020年1月14日的 Microsoft Edge 未设备的版本号" lightbox="../media/webdriver-chromium/edge-version.png":::
       <span data-ttu-id="e1a0b-119">2020年1月14日的 Microsoft Edge 未设备的版本号</span><span class="sxs-lookup"><span data-stu-id="e1a0b-119">The build number for Microsoft Edge Canary on January 14, 2020</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="e1a0b-120">导航到 [Microsoft Edge 驱动程序下载][MicrosoftDeveloperEdgeToolsWebdriverDownloads] 页面，并下载与 microsoft edge 版本号相匹配的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-120">Navigate to the [Microsoft Edge Driver downloads][MicrosoftDeveloperEdgeToolsWebdriverDownloads] page and download the driver that matches the version number of Microsoft Edge.</span></span>  
    
    :::image type="complex" source="../media/webdriver-chromium/edge-driver-install.png" alt-text="Microsoft Edge 驱动程序页面的 "下载" 部分" lightbox="../media/webdriver-chromium/edge-driver-install.png":::
       <span data-ttu-id="e1a0b-122">[Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]页面的 "下载" 部分</span><span class="sxs-lookup"><span data-stu-id="e1a0b-122">The Downloads section of the [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] page</span></span>  
    :::image-end:::  
    
    > [!NOTE] 
    > <span data-ttu-id="e1a0b-123">有关使用 Microsoft Edge \ (EdgeHTML \ ) 的测试自动化的详细信息，请参阅 [Microsoft WebDriver For Microsoft edge (EdgeHTML) ][Webdriver]。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-123">For more information about test automation using Microsoft Edge \(EdgeHTML\), see [Microsoft WebDriver for Microsoft Edge (EdgeHTML)][Webdriver].</span></span>  
    
## <span data-ttu-id="e1a0b-124">选择 WebDriver 语言绑定</span><span class="sxs-lookup"><span data-stu-id="e1a0b-124">Choose a WebDriver language binding</span></span>  

<span data-ttu-id="e1a0b-125">您必须下载的最后一个组件是特定于语言的客户端驱动程序，用于转换代码 \ (Python、Java、C \ #、Ruby、JavaScript \ ) 插入 microsoft Edge 驱动程序在 Microsoft Edge \ (Chromium \ ) 中运行的命令。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-125">The last component you must download is a language-specific client driver to translate your code \(Python, Java, C\#, Ruby, JavaScript\) into commands the Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="e1a0b-126">[下载你选择的 WebDriver 语言绑定][SeleniumDownloads]。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-126">[Download the WebDriver language binding of your choice][SeleniumDownloads].</span></span>  <span data-ttu-id="e1a0b-127">Microsoft Edge 团队建议 [Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05] 或更高版本，因为它支持 Microsoft edge \ (Chromium \ ) 。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-127">The Microsoft Edge team recommends [Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05] or later, because it supports Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="e1a0b-128">但是，你可能会在所有较早版本的 Selenium 中控制 Microsoft Edge \ (Chromium \ ) ，包括当前稳定 Selenium 3 版本。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-128">However, you may control Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="e1a0b-129">如果你以前以前自动自动化或测试了 Microsoft Edge \ (Chromium \ ) 使用 `ChromeDriver` 和 `ChromeOptions` 类，则你的 WebDriver 代码不会在 Microsoft edge 版本80或更高版本上运行。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-129">If you were previously automating or testing Microsoft Edge \(Chromium\) using `ChromeDriver` and `ChromeOptions` classes, your WebDriver code does not run on Microsoft Edge Version 80 or later.</span></span>  <span data-ttu-id="e1a0b-130">若要解决此问题，请更新你的测试以使用 `EdgeOptions` 该类并安装 [Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-130">To solve this problem, update your tests to use the `EdgeOptions` class and install [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver].</span></span>  

### <span data-ttu-id="e1a0b-131">使用 Selenium 3</span><span class="sxs-lookup"><span data-stu-id="e1a0b-131">Use Selenium 3</span></span>  

<span data-ttu-id="e1a0b-132">如果你已使用 [Selenium 3][|::ref1::|]，可能会有现有的浏览器测试并希望在不更改你的 Selenium 版本的情况下添加 Microsoft Edge \ () Chromium 的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-132">If you already use [Selenium 3][|::ref1::|], you may have existing browser tests and want to add coverage for Microsoft Edge \(Chromium\) without changing your version of Selenium.</span></span>  <span data-ttu-id="e1a0b-133">若要使用 [Selenium 3][|::ref2::|] 编写 microsoft edge \ (EdgeHTML \ ) 和 microsoft edge \ (Chromium \ ) 中的自动测试，请安装 [Microsoft Edge 程序包 Selenium 工具][GithubMicrosoftEdgeSeleniumTools] 以使用更新的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-133">To use [Selenium 3][|::ref2::|] to write automated tests for both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package to use the updated driver.</span></span>  <span data-ttu-id="e1a0b-134">`EdgeDriver` `EdgeDriverService` 工具中包含的和类与 Selenium 4 中的内置等效项完全兼容。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-134">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium 4.</span></span>  

<span data-ttu-id="e1a0b-135">使用以下步骤将 [Microsoft Edge 的 Selenium 工具][GithubMicrosoftEdgeSeleniumTools] 和 [Selenium 3][|::ref3::|] 添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-135">Use the following steps to add the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] and [Selenium 3][|::ref3::|] to your project.</span></span>

#### [<span data-ttu-id="e1a0b-136">C#</span><span class="sxs-lookup"><span data-stu-id="e1a0b-136">C#</span></span>](#tab/c-sharp/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="e1a0b-137">使用[NUGET CLI][NugetCLI]或[Visual Studio][VisualStudio]将[SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools]和[Selenium WebDriver][NugetPackagesSeleniumWebdriver31410]程序包添加到 .net 项目。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-137">Add the [Microsoft.Edge.SeleniumTools][NugetPackagesMicrosoftEdgeSeleniumtools] and [Selenium.WebDriver][NugetPackagesSeleniumWebdriver31410] packages to your .NET project using the [NuGet CLI][NugetCLI] or [Visual Studio][VisualStudio].</span></span>  

#### [<span data-ttu-id="e1a0b-138">Python</span><span class="sxs-lookup"><span data-stu-id="e1a0b-138">Python</span></span>](#tab/python/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="e1a0b-139">使用 [pip][PythonPip] 安装 [msedge-selenium-tools][PythonSeleniumTools] 和 [selenium][PythonSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-139">Use [pip][PythonPip] to install the [msedge-selenium-tools][PythonSeleniumTools] and [selenium][PythonSelenium] packages.</span></span>  

```python
pip install msedge-selenium-tools selenium==3.141
```  

#### [<span data-ttu-id="e1a0b-140">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e1a0b-140">JavaScript</span></span>](#tab/javascript/)  

<a id="selenium-tools-install"></a>  

<span data-ttu-id="e1a0b-141">使用 [npm][JavaScript|::ref4::|] 安装 [edge selenium-tools][JavaScriptSeleniumTools] 和 [selenium webdriver][JavaScriptSelenium] 程序包。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-141">Use [npm][JavaScript|::ref4::|] to install the [edge-selenium-tools][JavaScriptSeleniumTools] and [selenium-webdriver][JavaScriptSelenium] packages.</span></span>  

```javascript
npm install @microsoft/edge-selenium-tools selenium-webdriver
```  

* * *  

## <span data-ttu-id="e1a0b-142">使用 Microsoft Edge (Chromium) 与 WebDriver</span><span class="sxs-lookup"><span data-stu-id="e1a0b-142">Use Microsoft Edge (Chromium) with WebDriver</span></span>

<span data-ttu-id="e1a0b-143">你可以使用 Selenium 3 或4运行以下示例。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-143">You may run the following examples using either Selenium 3 or 4.</span></span>  <span data-ttu-id="e1a0b-144">若要与 Selenium 3 配合使用，必须安装 [适用于 Microsoft Edge 程序包的 Selenium 工具][GithubMicrosoftEdgeSeleniumTools] 。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-144">To use with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package must be installed.</span></span>  

### <span data-ttu-id="e1a0b-145">基本用法</span><span class="sxs-lookup"><span data-stu-id="e1a0b-145">Basic Usage</span></span>  

<span data-ttu-id="e1a0b-146">若要与 Microsoft Edge \ (EdgeHTML \ ) 一起使用，请创建该类的默认实例 `EdgeDriver` 。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-146">To use with Microsoft Edge \(EdgeHTML\), create a default instance of the `EdgeDriver` class.</span></span>  

#### [<span data-ttu-id="e1a0b-147">C#</span><span class="sxs-lookup"><span data-stu-id="e1a0b-147">C#</span></span>](#tab/c-sharp/)  

<a id="basic-usage-code"></a>  

```csharp
var driver = new EdgeDriver();
```  

#### [<span data-ttu-id="e1a0b-148">Python</span><span class="sxs-lookup"><span data-stu-id="e1a0b-148">Python</span></span>](#tab/python/)  

<a id="basic-usage-code"></a>  

```python
driver = Edge()
```  

#### [<span data-ttu-id="e1a0b-149">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e1a0b-149">JavaScript</span></span>](#tab/javascript/)  

<a id="basic-usage-code"></a>  

```javascript
let driver = edge.Driver.createSession();
```  

* * *  

### <span data-ttu-id="e1a0b-150">推动 Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="e1a0b-150">Driving Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="e1a0b-151">若要与 Microsoft Edge \ (Chromium \ ) ，请创建一个新 `EdgeDriver` 类并将其传递给该 `EdgeOptions` `UseChromium` 属性设置为的对象 `true` 。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-151">To use with Microsoft Edge \(Chromium\), create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<span data-ttu-id="e1a0b-152">C#</span><span class="sxs-lookup"><span data-stu-id="e1a0b-152">C#</span></span>](#tab/c-sharp/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="e1a0b-153">Python</span><span class="sxs-lookup"><span data-stu-id="e1a0b-153">Python</span></span>](#tab/python/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

#### [<span data-ttu-id="e1a0b-154">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e1a0b-154">JavaScript</span></span>](#tab/javascript/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> <span data-ttu-id="e1a0b-155">如果 IT 管理员已将 [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] 策略设置为 `2` ， [microsoft edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver] 将无法推动 [Microsoft edge (Chromium) ][MicrosoftEdge] ，因为驱动程序使用 [Microsoft edge DevTools][DevToolsMain]。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-155">If your IT admin has set the [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] policy to `2`, [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] is not be able to drive [Microsoft Edge (Chromium)][MicrosoftEdge] because the driver uses the [Microsoft Edge DevTools][DevToolsMain].</span></span>  <span data-ttu-id="e1a0b-156">确保 [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] 策略已设置为 `0` 或自动运行 `1` [Microsoft Edge (Chromium) ][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-156">Ensure the [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] policy is set to `0` or `1` to automate [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  

### <span data-ttu-id="e1a0b-157">选择特定浏览器二进制文件 ("仅 Chromium") </span><span class="sxs-lookup"><span data-stu-id="e1a0b-157">Choosing Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="e1a0b-158">你可以使用 `EdgeOptions` 包含 Microsoft Edge \ (Chromium \ ) 的特定二进制文件的类。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-158">You may use the `EdgeOptions` class with specific binaries of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="e1a0b-159">例如，你可以使用 [Microsoft edge 预览频道][MicrosoftedgeinsiderDownload] （如 Microsoft edge Beta）运行测试。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-159">For example, you may run tests using the [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<span data-ttu-id="e1a0b-160">C#</span><span class="sxs-lookup"><span data-stu-id="e1a0b-160">C#</span></span>](#tab/c-sharp/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="e1a0b-161">Python</span><span class="sxs-lookup"><span data-stu-id="e1a0b-161">Python</span></span>](#tab/python/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

#### [<span data-ttu-id="e1a0b-162">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e1a0b-162">JavaScript</span></span>](#tab/javascript/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <span data-ttu-id="e1a0b-163">自定义 Microsoft Edge 驱动程序服务</span><span class="sxs-lookup"><span data-stu-id="e1a0b-163">Customizing the Microsoft Edge Driver Service</span></span>  

#### [<span data-ttu-id="e1a0b-164">C#</span><span class="sxs-lookup"><span data-stu-id="e1a0b-164">C#</span></span>](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="e1a0b-165">`EdgeDriver`使用类创建类实例时 `EdgeOptions` ，它会 `EdgeDriverService` 为 microsoft Edge \ (EdgeHTML \ ) 或 microsoft Edge \ (Chromium \ ) 创建并启动相应的类。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-165">When an `EdgeDriver` class instance is created using `EdgeOptions` class, it creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="e1a0b-166">如果要创建 `EdgeDriverService` ，请创建一个为 Microsoft Edge 配置的 (Chromium \ ) 使用 `CreateChromiumService()` 方法。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-166">If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.</span></span>  <span data-ttu-id="e1a0b-167">你可能会发现它对于其他自定义非常有用，例如，在以下代码中启用详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-167">You may find it useful for additional customizations like enabling verbose log output in the following code.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
><span data-ttu-id="e1a0b-168">在 `EdgeOptions` 传递到实例时无需提供对象 `EdgeDriverService` `EdgeDriver` 。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-168">You do not need to provide the `EdgeOptions` object when passing `EdgeDriverService` to the `EdgeDriver` instance.</span></span> <span data-ttu-id="e1a0b-169">`EdgeDriver`该类使用 Microsoft edge \ (EdgeHTML \ ) 或 Microsoft edge \ (Chromium \ ) 的默认选项，具体取决于你提供的服务。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-169">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) depending on the service you provide.</span></span>  
> <span data-ttu-id="e1a0b-170">但是，如果你希望同时提供这两个 `EdgeDriverService` `EdgeOptions` 类和类，请确保两个版本的 Microsoft Edge 都配置了这两个类。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-170">However, if you want to provide both `EdgeDriverService` and `EdgeOptions` classes, ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="e1a0b-171">例如，不能在类中使用默认的 Microsoft Edge \ (EdgeHTML \ ) `EdgeDriverService` class 和 Chromium 属性 `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-171">For example, it is not possible to use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="e1a0b-172">`EdgeDriver`该类将引发错误以防止使用不同版本。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-172">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<span data-ttu-id="e1a0b-173">Python</span><span class="sxs-lookup"><span data-stu-id="e1a0b-173">Python</span></span>](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="e1a0b-174">使用 Python 时， `Edge` 对象将创建并管理 `EdgeService` 。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-174">When using Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="e1a0b-175">若要配置 `EdgeService` ，请 `Edge` 按以下代码向对象传递其他参数。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-175">To configure the `EdgeService`, pass additional arguments to the `Edge` object as indicated in the following code.</span></span>  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<span data-ttu-id="e1a0b-176">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e1a0b-176">JavaScript</span></span>](#tab/javascript/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="e1a0b-177">使用 JavaScript 时，使用类创建和配置 `Service` `ServiceBuilder` 。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-177">When using JavaScript, create and configure a `Service` with the `ServiceBuilder` class.</span></span>  <span data-ttu-id="e1a0b-178">或者，你可以将 `Service` 对象传递给该 `Driver` 对象，该对象启动 \ (并停止为你 ) 服务。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-178">Optionally, you may pass the `Service` object to the `Driver` object, which starts \(and stops\) the service for you.</span></span>  
<span data-ttu-id="e1a0b-179">若要配置 `Service` ，请在使用方法之前在类中运行其他方法 `ServiceBuilder` `build()` 。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-179">To configure the `Service`, run additional methods in the `ServiceBuilder` class before using the `build()` method.</span></span>  <span data-ttu-id="e1a0b-180">然后 `service` 在方法中传递作为参数 `Driver.createSession()` 。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-180">Then pass the `service` as a parameter in the `Driver.createSession()` method.</span></span>  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * *  

### <span data-ttu-id="e1a0b-181">使用 Chromium-Specific 选项</span><span class="sxs-lookup"><span data-stu-id="e1a0b-181">Use Chromium-Specific Options</span></span>  

<span data-ttu-id="e1a0b-182">如果将该 `UseChromium` 属性设置为 `true` ，则可以使用 `EdgeOptions` 类访问与自动化其他 Chromium 浏览器相同的 [Chromium 特定属性和方法][SeleniumWebDriverChromeoptionsClass] 。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-182">If you set the `UseChromium` property to `true`, you may use the `EdgeOptions` class to access the same [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] as when you automate other Chromium browsers.</span></span>  

#### [<span data-ttu-id="e1a0b-183">C#</span><span class="sxs-lookup"><span data-stu-id="e1a0b-183">C#</span></span>](#tab/c-sharp/)  

<a id="using-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<span data-ttu-id="e1a0b-184">Python</span><span class="sxs-lookup"><span data-stu-id="e1a0b-184">Python</span></span>](#tab/python/)  

<a id="using-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<span data-ttu-id="e1a0b-185">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e1a0b-185">JavaScript</span></span>](#tab/javascript/)  

<a id="using-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```

* * *  

> [!NOTE]
> <span data-ttu-id="e1a0b-186">如果 `UseChromium` 属性设置为 `true` ，则无法使用 Microsoft Edge \ (EdgeHTML \ ) 的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-186">If the `UseChromium` property is set to `true`, you are not able to use properties and methods for Microsoft Edge \(EdgeHTML\).</span></span>  

## <span data-ttu-id="e1a0b-187">其他 WebDriver 安装选项</span><span class="sxs-lookup"><span data-stu-id="e1a0b-187">Additional WebDriver installation options</span></span>  

### <span data-ttu-id="e1a0b-188">Chocolatey</span><span class="sxs-lookup"><span data-stu-id="e1a0b-188">Chocolatey</span></span>  

<span data-ttu-id="e1a0b-189">如果你将 [Chocolatey][Chocolatey] 用作程序包管理器，请通过运行以下命令来安装 Microsoft Edge 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-189">If you use [Chocolatey][Chocolatey] as your package manager, install the Microsoft Edge Driver by running the following command.</span></span>  

```console
choco install selenium-chromium-edge-driver
```  

<span data-ttu-id="e1a0b-190">有关详细信息，请参阅 [Chocolatey 上的 Selenium Chromium Edge 驱动程序][ChocolateyPackagesSeleniumChromiumEdgeDriver]。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-190">For more information, see [Selenium Chromium Edge Driver on Chocolatey][ChocolateyPackagesSeleniumChromiumEdgeDriver].</span></span>  

### <span data-ttu-id="e1a0b-191">Docker</span><span class="sxs-lookup"><span data-stu-id="e1a0b-191">Docker</span></span>  

<span data-ttu-id="e1a0b-192">如果使用 [Docker][DockerHub]，请通过运行以下命令，将预配置的映像与 microsoft edge \ (Chromium \ ) 和 [Microsoft edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver] 一起下载。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-192">If you use [Docker][DockerHub], download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] pre-installed by running the following command.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="e1a0b-193">有关详细信息，请参阅 [Docker 中心上的容器][DockerHubMsedgedriver]。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-193">For more information, see [container on Docker Hub][DockerHubMsedgedriver].</span></span>  

## <span data-ttu-id="e1a0b-194">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="e1a0b-194">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="e1a0b-195">Microsoft Edge 团队渴望听到有关使用 WebDriver、Selenium 和 Microsoft Edge 的反馈。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-195">The Microsoft Edge team is eager to hear your feedback about using WebDriver, Selenium, and Microsoft Edge.</span></span>  <span data-ttu-id="e1a0b-196">若要让团队知道您的想法，请选择 Microsoft Edge DevTools 中的 " **发送反馈** " 图标或发送 tweet [@EdgeDevTools][TwitterTweetEdgeDevTools]。</span><span class="sxs-lookup"><span data-stu-id="e1a0b-196">To let the team know what you think, choose the **Send Feedback** icon in the Microsoft Edge DevTools or send a tweet [@EdgeDevTools][TwitterTweetEdgeDevTools].</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的 "发送反馈" 图标" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="e1a0b-198">Microsoft Edge DevTools 中的 " **发送反馈** " 图标</span><span class="sxs-lookup"><span data-stu-id="e1a0b-198">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
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
