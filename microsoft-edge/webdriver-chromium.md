---
description: 了解如何在 Microsoft Edge 中测试你的网站或应用，或通过 WebDriver 自动处理浏览器。
title: WebDriver (Chromium)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/08/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge，web 开发，html，css，javascript，开发人员，webdriver，selenium，测试，工具，自动化，测试
ms.openlocfilehash: 14537943351db144bb4839d6befbfaa62894cd85
ms.sourcegitcommit: 3f8c8a5643e416b0851254833f9771192883ec45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10699505"
---
# <span data-ttu-id="4c0d8-104">将 WebDriver （Chromium）用于测试自动化</span><span class="sxs-lookup"><span data-stu-id="4c0d8-104">Use WebDriver (Chromium) for test automation</span></span>  

<span data-ttu-id="4c0d8-105">WebDriver 使开发人员能够创建模拟用户交互的自动测试。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-105">WebDriver enables developers to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="4c0d8-106">由于以下原因，WebDriver 测试和模拟与 JavaScript 单元测试不同。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-106">WebDriver tests and simulations differ from JavaScript unit tests because of the following reasons.</span></span> 
*   <span data-ttu-id="4c0d8-107">访问功能和信息在浏览器中运行的 JavaScript 不可用。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-107">Accesses functionality and information not available to JavaScript running in browsers.</span></span>  
*   <span data-ttu-id="4c0d8-108">更准确地模拟用户事件或 OS 级别的事件。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-108">Simulates user events or OS-level events more accurately.</span></span>  
*   <span data-ttu-id="4c0d8-109">在单个测试会话中管理跨多个窗口、选项卡和网页的测试。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-109">Manages testing across multiple windows, tabs, and webpages in a single test session.</span></span>  
*   <span data-ttu-id="4c0d8-110">在特定计算机上运行多个 Microsoft Edge 会话。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-110">Runs multiple sessions of Microsoft Edge on a specific machine.</span></span>  

<span data-ttu-id="4c0d8-111">以下部分介绍了如何开始使用 Microsoft Edge \ （Chromium \）的 WebDriver。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-111">The following section describes how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  

## <span data-ttu-id="4c0d8-112">安装 Microsoft Edge （Chromium）</span><span class="sxs-lookup"><span data-stu-id="4c0d8-112">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="4c0d8-113">确保安装[Microsoft Edge （Chromium）][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-113">Ensure you install [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="4c0d8-114">若要确认安装了 Microsoft Edge （Chromium），请转到 `edge://settings/help` 浏览器，然后验证版本号是版本75或更高版本。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-114">To confirm that you have Microsoft Edge (Chromium) installed, go to `edge://settings/help` in the browser, and verify the version number is Version 75 or later.</span></span>  

## <span data-ttu-id="4c0d8-115">下载 Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="4c0d8-115">Download Microsoft Edge Driver</span></span>  

<span data-ttu-id="4c0d8-116">若要开始自动测试，请使用以下步骤确保所安装的 WebDriver 版本与你的浏览器版本相匹配。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-116">To begin automating tests, use the following steps to ensure that the WebDriver version you install matches your browser version.</span></span>  

1.  <span data-ttu-id="4c0d8-117">转到 `edge://settings/help` 获取边缘版本。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-117">Go to `edge://settings/help` to get the version of Edge.</span></span>  
    
    :::image type="complex" source="./media/webdriver-chromium/edge-version.png" alt-text="2020年1月14日的 Microsoft Edge 未设备的版本号":::
       <span data-ttu-id="4c0d8-119">图 1.</span><span class="sxs-lookup"><span data-stu-id="4c0d8-119">Figure 1.</span></span>  <span data-ttu-id="4c0d8-120">2020年1月14日的 Microsoft Edge 未设备的版本号</span><span class="sxs-lookup"><span data-stu-id="4c0d8-120">The build number for Microsoft Edge Canary on January 14, 2020</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="4c0d8-121">导航到[Microsoft Edge 驱动程序下载][MicrosoftDeveloperEdgeToolsWebdriverDownloads]页面并下载与 Edge 版本号匹配的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-121">Navigate to the [Microsoft Edge Driver downloads][MicrosoftDeveloperEdgeToolsWebdriverDownloads] page and download the driver that matches the Edge version number.</span></span>  
    
    :::image type="complex" source="./media/webdriver-chromium/edge-driver-install.png" alt-text="Microsoft Edge 驱动程序页面的 "下载" 部分":::
       <span data-ttu-id="4c0d8-123">图 2.</span><span class="sxs-lookup"><span data-stu-id="4c0d8-123">Figure 2.</span></span>  <span data-ttu-id="4c0d8-124">[Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]页面的 "下载" 部分</span><span class="sxs-lookup"><span data-stu-id="4c0d8-124">The Downloads section of the [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] page</span></span>
    :::image-end:::  
    
    > [!NOTE] 
    > <span data-ttu-id="4c0d8-125">有关使用 Microsoft Edge （EdgeHTML）的测试自动化的详细信息，请参阅[Microsoft WebDriver For Microsoft edge （EdgeHTML）][Webdriver]。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-125">For more information about test automation using Microsoft Edge (EdgeHTML), see [Microsoft WebDriver for Microsoft Edge (EdgeHTML)][Webdriver].</span></span>  

## <span data-ttu-id="4c0d8-126">选择 WebDriver 语言绑定</span><span class="sxs-lookup"><span data-stu-id="4c0d8-126">Choose a WebDriver language binding</span></span>  

<span data-ttu-id="4c0d8-127">你必须下载的最后一个组件是特定于语言的客户端驱动程序，用于将你的代码 \ （Python、Java、C \ #、Ruby、JavaScript \）转换为 Microsoft Edge 驱动程序在 Microsoft Edge \ （Chromium \）中运行的命令。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-127">The last component you must download is a language-specific client driver to translate your code \(Python, Java, C\#, Ruby, JavaScript\) into commands the Microsoft Edge Driver runs in Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="4c0d8-128">[下载你选择的 WebDriver 语言绑定][SeleniumDownloads]。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-128">[Download the WebDriver language binding of your choice][SeleniumDownloads].</span></span>  <span data-ttu-id="4c0d8-129">Microsoft Edge 团队建议[Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05]或更高版本，因为它支持 Microsoft edge \ （Chromium \）。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-129">The Microsoft Edge team recommends [Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05] or later, because it supports Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="4c0d8-130">但是，你可以在所有较早版本的 Selenium 中控制 Microsoft Edge \ （Chromium \），包括当前稳定 Selenium 3 版本。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-130">However, you are able to control Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="4c0d8-131">如果你以前使用和类自动执行或测试 Microsoft Edge \ （Chromium \） `ChromeDriver` `ChromeOptions` ，则你的 WebDriver 代码不会在 Microsoft edge 版本80或更高版本上运行。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-131">If you were previously automating or testing Microsoft Edge \(Chromium\) using `ChromeDriver` and `ChromeOptions` classes, your WebDriver code does not run on Microsoft Edge Version 80 or later.</span></span>  <span data-ttu-id="4c0d8-132">若要解决此问题，请更新你的测试以使用 `EdgeOptions` 该类并安装[Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-132">To solve this problem, update your tests to use the `EdgeOptions` class and install [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver].</span></span>  

### <span data-ttu-id="4c0d8-133">使用 Selenium 3</span><span class="sxs-lookup"><span data-stu-id="4c0d8-133">Use Selenium 3</span></span>  

<span data-ttu-id="4c0d8-134">如果你已使用[Selenium 3][|::ref1::|]，可能会有现有的浏览器测试并希望在不更改你的 Selenium 版本的情况下添加 Microsoft Edge \ （Chromium \）的覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-134">If you already use [Selenium 3][|::ref1::|], you may have existing browser tests and want to add coverage for Microsoft Edge \(Chromium\) without changing your version of Selenium.</span></span>  <span data-ttu-id="4c0d8-135">若要使用[Selenium 3][|::ref2::|]为 microsoft edge \ （EdgeHTML \）和 microsoft edge \ （Chromium \）编写自动测试，请安装[microsoft Edge 程序包的 Selenium 工具][GithubMicrosoftEdgeSeleniumTools]以使用更新的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-135">To use [Selenium 3][|::ref2::|] to write automated tests for both Microsoft Edge \(EdgeHTML\) and Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package to use the updated driver.</span></span>  <span data-ttu-id="4c0d8-136">`EdgeDriver` `EdgeDriverService` 工具中包含的和类与 Selenium 4 中的内置等效项完全兼容。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-136">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium 4.</span></span>  

## <span data-ttu-id="4c0d8-137">将 Microsoft Edge （Chromium）与 WebDriver 结合使用</span><span class="sxs-lookup"><span data-stu-id="4c0d8-137">Use Microsoft Edge (Chromium) with WebDriver</span></span>

<span data-ttu-id="4c0d8-138">你可以使用 Selenium 3 或4运行以下示例。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-138">You may run the following examples using either Selenium 3 or 4.</span></span>  <span data-ttu-id="4c0d8-139">若要与 Selenium 3 配合使用，必须安装[适用于 Microsoft Edge 程序包的 Selenium 工具][GithubMicrosoftEdgeSeleniumTools]。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-139">To use with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package must be installed.</span></span>  

### <span data-ttu-id="4c0d8-140">基本用法</span><span class="sxs-lookup"><span data-stu-id="4c0d8-140">Basic Usage</span></span>  

<span data-ttu-id="4c0d8-141">若要与 Microsoft Edge \ （EdgeHTML \）一起使用，只需创建该类的默认实例 `EdgeDriver` 。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-141">To use with Microsoft Edge \(EdgeHTML\), simply create a default instance of the `EdgeDriver` class.</span></span>

#### [<span data-ttu-id="4c0d8-142">C#</span><span class="sxs-lookup"><span data-stu-id="4c0d8-142">C#</span></span>](#tab/c-sharp/)  

<a id="basic-usage-code"></a>  

```csharp
var driver = new EdgeDriver();
```  

#### [<span data-ttu-id="4c0d8-143">Python</span><span class="sxs-lookup"><span data-stu-id="4c0d8-143">Python</span></span>](#tab/python/)  

<a id="basic-usage-code"></a>  

```python
driver = Edge()
```  

#### [<span data-ttu-id="4c0d8-144">JavaScript</span><span class="sxs-lookup"><span data-stu-id="4c0d8-144">JavaScript</span></span>](#tab/javascript/)  

<a id="basic-usage-code"></a>  

```javascript
let driver = edge.Driver.createSession();
```  

* * *  

### <span data-ttu-id="4c0d8-145">推动 Microsoft Edge （Chromium）</span><span class="sxs-lookup"><span data-stu-id="4c0d8-145">Driving Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="4c0d8-146">若要与 Microsoft Edge \ （Chromium \）一起使用，请创建一个新 `EdgeDriver` 类，并将其传递给将 `EdgeOptions` `UseChromium` 属性设置为的对象 `true` 。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-146">To use with Microsoft Edge \(Chromium\), create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<span data-ttu-id="4c0d8-147">C#</span><span class="sxs-lookup"><span data-stu-id="4c0d8-147">C#</span></span>](#tab/c-sharp/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="4c0d8-148">Python</span><span class="sxs-lookup"><span data-stu-id="4c0d8-148">Python</span></span>](#tab/python/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

#### [<span data-ttu-id="4c0d8-149">JavaScript</span><span class="sxs-lookup"><span data-stu-id="4c0d8-149">JavaScript</span></span>](#tab/javascript/)  

<a id="driving-microsoft-edge-chromium-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);

let driver = edge.Driver.createSession(options);
```  

* * *  

> [!NOTE]
> <span data-ttu-id="4c0d8-150">如果[DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability]策略设置为 `2` ， [microsoft edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]将无法驱动[microsoft edge （Chromium）][MicrosoftEdge] ，因为该驱动程序使用的是[microsoft edge DevTools][DevToolsMain]。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-150">If the [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] policy is set to `2`, [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] is not be able to drive [Microsoft Edge (Chromium)][MicrosoftEdge] because the driver uses the [Microsoft Edge DevTools][DevToolsMain].</span></span>  <span data-ttu-id="4c0d8-151">确保将[DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability]策略设置为 `0` 或 `1` 自动执行[Microsoft Edge （Chromium）][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-151">Ensure you set the [DeveloperToolsAvailability][DeployedgePoliciesDevelopertoolsavailability] policy to `0` or `1` to automate [Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  

### <span data-ttu-id="4c0d8-152">选择特定浏览器二进制文件（仅限 Chromium）</span><span class="sxs-lookup"><span data-stu-id="4c0d8-152">Choosing Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="4c0d8-153">你可以将 `EdgeOptions` 该类与特定的 Microsoft Edge 二进制文件（Chromium）结合使用。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-153">You may use the `EdgeOptions` class with specific binaries of Microsoft Edge (Chromium).</span></span>  <span data-ttu-id="4c0d8-154">例如，你可以使用[Microsoft edge 预览频道][MicrosoftedgeinsiderDownload]（如 Microsoft edge Beta）运行测试。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-154">For example, you may run tests using the [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<span data-ttu-id="4c0d8-155">C#</span><span class="sxs-lookup"><span data-stu-id="4c0d8-155">C#</span></span>](#tab/c-sharp/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="4c0d8-156">Python</span><span class="sxs-lookup"><span data-stu-id="4c0d8-156">Python</span></span>](#tab/python/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

#### [<span data-ttu-id="4c0d8-157">JavaScript</span><span class="sxs-lookup"><span data-stu-id="4c0d8-157">JavaScript</span></span>](#tab/javascript/)  

<a id="choosing-specific-browser-binaries-chrome-only-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.setBinaryPath("C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe");

let driver = edge.Driver.createSession(options);
```  

* * *  

### <span data-ttu-id="4c0d8-158">自定义 Microsoft Edge 驱动程序服务</span><span class="sxs-lookup"><span data-stu-id="4c0d8-158">Customizing the Microsoft Edge Driver Service</span></span>  

#### [<span data-ttu-id="4c0d8-159">C#</span><span class="sxs-lookup"><span data-stu-id="4c0d8-159">C#</span></span>](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="4c0d8-160">`EdgeDriver`使用类创建类实例时 `EdgeOptions` ，它将 `EdgeDriverService` 为 microsoft Edge \ （EdgeHTML \）或 microsoft Edge \ （Chromium \）创建并启动相应的类。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-160">When an `EdgeDriver` class instance is created using `EdgeOptions` class, it creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="4c0d8-161">如果你想要创建 `EdgeDriverService` ，请使用方法为 Microsoft Edge \ （Chromium \）配置一个 `CreateChromiumService()` 。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-161">If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.</span></span>  <span data-ttu-id="4c0d8-162">你可能会发现它对于其他自定义非常有用，例如，在以下代码中启用详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-162">You may find it useful for additional customizations like enabling verbose log output in the following code.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE] 
><span data-ttu-id="4c0d8-163">在 `EdgeOptions` 传递到实例时无需提供对象 `EdgeDriverService` `EdgeDriver` 。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-163">You do not need to provide the `EdgeOptions` object when passing `EdgeDriverService` to the `EdgeDriver` instance.</span></span> <span data-ttu-id="4c0d8-164">`EdgeDriver`对于 Microsoft edge \ （EdgeHTML \）或 Microsoft edge \ （Chromium \），该类使用默认选项，具体取决于你提供的服务。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-164">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) depending on the service you provide.</span></span>  
> <span data-ttu-id="4c0d8-165">但是，如果你希望同时提供这两个 `EdgeDriverService` `EdgeOptions` 类和类，请确保两个版本的 Microsoft Edge 都配置了这两个类。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-165">However, if you want to provide both `EdgeDriverService` and `EdgeOptions` classes, ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="4c0d8-166">例如，不能在类中使用默认的 Microsoft Edge （EdgeHTML） `EdgeDriverService` 类和 Chromium 属性 `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-166">For example, it is not possible to use a default Microsoft Edge (EdgeHTML) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="4c0d8-167">`EdgeDriver`该类将引发错误以防止使用不同版本。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-167">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<span data-ttu-id="4c0d8-168">Python</span><span class="sxs-lookup"><span data-stu-id="4c0d8-168">Python</span></span>](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="4c0d8-169">使用 Python 时， `Edge` 对象将创建并管理 `EdgeService` 。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-169">When using Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="4c0d8-170">若要配置 `EdgeService` ，请 `Edge` 按以下代码向对象传递其他参数。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-170">To configure the `EdgeService`, pass additional arguments to the `Edge` object as indicated in the following code.</span></span>  

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### [<span data-ttu-id="4c0d8-171">JavaScript</span><span class="sxs-lookup"><span data-stu-id="4c0d8-171">JavaScript</span></span>](#tab/javascript/)  

<a id="customizing-microsoft-edge-driver-services-code"></a>  

<span data-ttu-id="4c0d8-172">使用 JavaScript 时，使用类创建和配置 `Service` `ServiceBuilder` 。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-172">When using JavaScript, create and configure a `Service` with the `ServiceBuilder` class.</span></span>  <span data-ttu-id="4c0d8-173">你可以选择将 `Service` 对象传递给 `Driver` 启动和停止服务的对象。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-173">You may optionally pass the `Service` object to the `Driver` object which starts and stops the service for you.</span></span>  
<span data-ttu-id="4c0d8-174">若要配置 `Service` ，请在使用方法之前在类中运行其他方法 `ServiceBuilder` `build()` 。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-174">To configure the `Service`, run additional methods in the `ServiceBuilder` class before using the `build()` method.</span></span>  <span data-ttu-id="4c0d8-175">然后 `service` 在方法中传递作为参数 `Driver.createSession()` 。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-175">Then pass the `service` as a parameter in the `Driver.createSession()` method.</span></span>  

```javascript
let service = new edge.ServiceBuilder().enableVerboseLogging().build();
let driver = edge.Driver.createSession(options, service);
```  

* * * 

### <span data-ttu-id="4c0d8-176">使用 Chromium 特定选项</span><span class="sxs-lookup"><span data-stu-id="4c0d8-176">Use Chromium-Specific Options</span></span>  

<span data-ttu-id="4c0d8-177">如果将该 `UseChromium` 属性设置为 `true` ，则可以使用 `EdgeOptions` 类访问与在自动执行其他 Chromium 浏览器时相同的[Chromium 特定属性和方法][SeleniumWebDriverChromeoptionsClass]。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-177">If you set the `UseChromium` property to `true`, you are able to use the `EdgeOptions` class to access the same [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] as when you automate other Chromium browsers.</span></span>  

#### [<span data-ttu-id="4c0d8-178">C#</span><span class="sxs-lookup"><span data-stu-id="4c0d8-178">C#</span></span>](#tab/c-sharp/)  

<a id="using-chromium-specific-options-code"></a>  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<span data-ttu-id="4c0d8-179">Python</span><span class="sxs-lookup"><span data-stu-id="4c0d8-179">Python</span></span>](#tab/python/)  

<a id="using-chromium-specific-options-code"></a>  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument("headless")
options.add_argument("disable-gpu")
```  

#### [<span data-ttu-id="4c0d8-180">JavaScript</span><span class="sxs-lookup"><span data-stu-id="4c0d8-180">JavaScript</span></span>](#tab/javascript/)  

<a id="using-chromium-specific-options-code"></a>  

```javascript
let options = new edge.Options();
options.setEdgeChromium(true);
options.addArguments("headless");
options.addArguments("disable-gpu");
```

* * *  
> [!NOTE]
> <span data-ttu-id="4c0d8-181">如果 `UseChromium` 属性设置为 `true` ，则无法使用 Microsoft Edge \ （EdgeHTML \）的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-181">If the `UseChromium` property is set to `true`, you are not able to use properties and methods for Microsoft Edge \(EdgeHTML\).</span></span>  

## <span data-ttu-id="4c0d8-182">其他 WebDriver 安装选项</span><span class="sxs-lookup"><span data-stu-id="4c0d8-182">Additional WebDriver installation options</span></span>  

### <span data-ttu-id="4c0d8-183">Chocolatey</span><span class="sxs-lookup"><span data-stu-id="4c0d8-183">Chocolatey</span></span>  

<span data-ttu-id="4c0d8-184">如果你将[Chocolatey][Chocolatey]用作程序包管理器，请通过运行以下命令来安装 Microsoft Edge 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-184">If you use [Chocolatey][Chocolatey] as your package manager, install the Microsoft Edge Driver by running the following command.</span></span>  

```console
choco install selenium-chromium-edge-driver
```  

<span data-ttu-id="4c0d8-185">有关详细信息，请参阅[Chocolatey 上的 Selenium Chromium Edge 驱动程序][ChocolateyPackagesSeleniumChromiumEdgeDriver]。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-185">For more information, see [Selenium Chromium Edge Driver on Chocolatey][ChocolateyPackagesSeleniumChromiumEdgeDriver].</span></span>  

### <span data-ttu-id="4c0d8-186">Docker</span><span class="sxs-lookup"><span data-stu-id="4c0d8-186">Docker</span></span>  

<span data-ttu-id="4c0d8-187">如果你使用[Docker][DockerHub]，请通过运行以下命令，将预配置的映像下载到 microsoft edge \ （Chromium \）和[Microsoft edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-187">If you use [Docker][DockerHub], download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] pre-installed by running the following command.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="4c0d8-188">有关详细信息，请参阅[Docker 中心上的容器][DockerHubMsedgedriver]。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-188">For more information, see [container on Docker Hub][DockerHubMsedgedriver].</span></span>  

## <span data-ttu-id="4c0d8-189">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="4c0d8-189">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="4c0d8-190">Microsoft Edge 团队渴望听到有关使用 WebDriver、Selenium 和 Microsoft Edge 的反馈。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-190">The Microsoft Edge team is eager to hear your feedback about using WebDriver, Selenium, and Microsoft Edge.</span></span>  <span data-ttu-id="4c0d8-191">使用 Microsoft Edge DevTools 或 tweet [@EdgeDevTools][TwitterTweetEdgeDevTools]中的**反馈**图标，让团队知道您的想法。</span><span class="sxs-lookup"><span data-stu-id="4c0d8-191">Use the **Feedback** icon in the Microsoft Edge DevTools or tweet [@EdgeDevTools][TwitterTweetEdgeDevTools] to let the team know what you think.</span></span>  


:::image type="complex" source="./devtools-guide-chromium/media/devtools-feedback.png" alt-text="Microsoft Edge DevTools 中的 "反馈" 图标":::
   <span data-ttu-id="4c0d8-193">Microsoft Edge DevTools 中的 "**反馈**" 图标</span><span class="sxs-lookup"><span data-stu-id="4c0d8-193">The **Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- image links -->  

<!-- links -->  

[DevToolsMain]: ./devtools-guide-chromium.md "Microsoft Edge （Chromium）开发工具 |Microsoft 文档"
[Webdriver]: ./webdriver.md "WebDriver （EdgeHTML） |Microsoft 文档"  

[DeployedgePoliciesDevelopertoolsavailability]: /deployedge/microsoft-edge-policies#developertoolsavailability "DeveloperToolsAvailability-Microsoft Edge-政策 |Microsoft 文档"  

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
