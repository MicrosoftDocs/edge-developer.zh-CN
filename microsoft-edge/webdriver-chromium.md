---
description: 了解如何在 Microsoft Edge 中测试你的网站或应用，或通过 WebDriver 自动处理浏览器。
title: WebDriver (Chromium)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge，web 开发，html，css，javascript，开发人员，webdriver，selenium，测试，工具，自动化，测试
ms.openlocfilehash: 0cb135553b04cd0cf160755eacc0dbae245d13b7
ms.sourcegitcommit: 24430258f363b7dd85f7067afd4565bf102b4a1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "10645313"
---
# <span data-ttu-id="7ca21-104">WebDriver (Chromium)</span><span class="sxs-lookup"><span data-stu-id="7ca21-104">WebDriver (Chromium)</span></span>  

<span data-ttu-id="7ca21-105">W3C [WebDriver][W3CWebdriver] API 是一个平台和语言中立的界面和线路协议，允许程序或脚本控制 web 浏览器的行为，如 Microsoft Edge \ （Chromium \）。</span><span class="sxs-lookup"><span data-stu-id="7ca21-105">The W3C [WebDriver][W3CWebdriver] API is a platform and language-neutral interface and wire protocol allowing programs or scripts to control the behavior of a web browser, like Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="7ca21-106">WebDriver 使开发人员能够创建模拟用户交互的自动测试。</span><span class="sxs-lookup"><span data-stu-id="7ca21-106">WebDriver enables developers to create automated tests that simulate user interaction.</span></span>  <span data-ttu-id="7ca21-107">WebDriver 测试和模拟不同于 JavaScript 单元测试，因为 WebDriver 有权访问在浏览器中运行的 JavaScript 不需要的功能和信息，WebDrive ia 能够更准确地模拟用户事件或操作系统级别的事件。</span><span class="sxs-lookup"><span data-stu-id="7ca21-107">WebDriver tests and simulations differ from JavaScript unit tests because WebDriver has access to functionality and information that JavaScript running in the browser does not, and WebDrive ia able to more accurately simulate user events or OS-level events.</span></span>  <span data-ttu-id="7ca21-108">WebDriver 可以在单个测试会话中跨多个窗口、选项卡和网页管理测试。</span><span class="sxs-lookup"><span data-stu-id="7ca21-108">WebDriver is able to manage testing across multiple windows, tabs and webpages in a single test session.</span></span>  

<span data-ttu-id="7ca21-109">下面介绍如何开始使用 Microsoft Edge \ （Chromium \）的 WebDriver。</span><span class="sxs-lookup"><span data-stu-id="7ca21-109">Here is how to get started with WebDriver for Microsoft Edge \(Chromium\).</span></span>  

## <span data-ttu-id="7ca21-110">安装 Microsoft Edge （Chromium）</span><span class="sxs-lookup"><span data-stu-id="7ca21-110">Install Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="7ca21-111">如果尚未安装，请[安装 Microsoft Edge （Chromium）][MicrosoftEdge]。</span><span class="sxs-lookup"><span data-stu-id="7ca21-111">If you have not already, [install Microsoft Edge (Chromium)][MicrosoftEdge].</span></span>  <span data-ttu-id="7ca21-112">如果您在您的计算机上使用预安装的 Microsoft Edge 版本，请验证您有 Microsoft Edge \ （Chromium \），而不是 Microsoft Edge \ （EdgeHTML \）。</span><span class="sxs-lookup"><span data-stu-id="7ca21-112">If you are using a pre-installed version of Microsoft Edge on your machine, verify that you have Microsoft Edge \(Chromium\) and not Microsoft Edge \(EdgeHTML\).</span></span>  <span data-ttu-id="7ca21-113">快速检查的方法是 `edge://settings/help` 在浏览器中加载并确认版本号为 v75 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7ca21-113">A quick way to check is to load `edge://settings/help` in the browser and confirm that the version number is v75 or later.</span></span>  

## <span data-ttu-id="7ca21-114">下载 Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="7ca21-114">Download Microsoft Edge Driver</span></span>  

<span data-ttu-id="7ca21-115">WebDriver 需要特定于浏览器的驱动程序才能自动处理每个浏览器。</span><span class="sxs-lookup"><span data-stu-id="7ca21-115">WebDriver requires a browser-specific driver to automate each browser.</span></span>  <span data-ttu-id="7ca21-116">对于 Microsoft Edge \ （Chromium \），WebDriver 需要合适的[Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]，以便你想要测试或自动化的 microsoft edge 内部版本。</span><span class="sxs-lookup"><span data-stu-id="7ca21-116">For Microsoft Edge \(Chromium\), WebDriver requires the appropriate [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] for the build of Microsoft Edge you want to test or automate.</span></span>  

<span data-ttu-id="7ca21-117">若要查找正确的版本号，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7ca21-117">To find your correct build number, use the following steps.</span></span>  

1.  <span data-ttu-id="7ca21-118">启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7ca21-118">Launch Microsoft Edge</span></span> 
1.  <span data-ttu-id="7ca21-119">查看 Microsoft Edge \ （Chromium \）版本。</span><span class="sxs-lookup"><span data-stu-id="7ca21-119">View the Microsoft Edge \(Chromium\) version.</span></span>  
    *   <span data-ttu-id="7ca21-120">导航到</span><span class="sxs-lookup"><span data-stu-id="7ca21-120">Navigate to</span></span> `edge://settings/help`  
    *   <span data-ttu-id="7ca21-121">选择 `...`  >  **Settings**  >   **有关 Microsoft Edge**的设置</span><span class="sxs-lookup"><span data-stu-id="7ca21-121">Select `...` > **Settings** >  **About Microsoft Edge**</span></span>  
1.  <span data-ttu-id="7ca21-122">验证你的版本的 WebDriver 的正确版本是否可确保，以便正确运行。</span><span class="sxs-lookup"><span data-stu-id="7ca21-122">Verify the correct version of WebDriver for your build ensures, so it runs correctly.</span></span>  

:::image type="complex" source="./media/webdriver-chromium/edge-version.png" alt-text="2020年1月14日的 Microsoft Edge 未设备的版本号":::
   <span data-ttu-id="7ca21-124">图 1.</span><span class="sxs-lookup"><span data-stu-id="7ca21-124">Figure 1.</span></span>  <span data-ttu-id="7ca21-125">2020年1月14日的 Microsoft Edge 未设备的版本号</span><span class="sxs-lookup"><span data-stu-id="7ca21-125">The build number for Microsoft Edge Canary on January 14, 2020</span></span>  
:::image-end:::

<!--  
> ##### Figure 1  
> The build number for Microsoft Edge Canary on January 14, 2020
> ![The build number for Microsoft Edge Canary on January 14, 2020][ImageWebdriverChromiumEdgeVersion]  
-->  

<span data-ttu-id="7ca21-126">现在，[下载 Microsoft Edge 驱动程序的匹配版本][MicrosoftDeveloperEdgeToolsWebdriverDownloads]。</span><span class="sxs-lookup"><span data-stu-id="7ca21-126">Now, [download the matching version of Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriverDownloads].</span></span>  

:::image type="complex" source="./media/webdriver-chromium/edge-driver-install.png" alt-text="Microsoft Edge 驱动程序页面的 "下载" 部分":::
   <span data-ttu-id="7ca21-128">图 2.</span><span class="sxs-lookup"><span data-stu-id="7ca21-128">Figure 2.</span></span>  <span data-ttu-id="7ca21-129">[Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriverDownloads]页面的 "下载" 部分</span><span class="sxs-lookup"><span data-stu-id="7ca21-129">The Downloads section of the [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriverDownloads] page</span></span>  
:::image-end:::

<!--  
> ##### Figure 2
> The Downloads section of the [Microsoft Edge Driver page][MicrosoftDeveloperEdgeToolsWebdriverDownloads]
> ![The Downloads section of the Microsoft Edge Driver page][ImageWebdriverChromiumEdgeDriverInstall]  
-->  

> [!NOTE]
> <span data-ttu-id="7ca21-130">Microsoft Edge \ （EdgeHTML \）不能与[Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriverDownloads]配合使用。</span><span class="sxs-lookup"><span data-stu-id="7ca21-130">Microsoft Edge \(EdgeHTML\) does not work with [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriverDownloads].</span></span>  <span data-ttu-id="7ca21-131">若要自动执行 Microsoft Edge \ （EdgeHTML \），必须下载[Microsoft WebDriver For Microsoft edge \ （EdgeHTML \）][Webdriver]。</span><span class="sxs-lookup"><span data-stu-id="7ca21-131">To automate Microsoft Edge \(EdgeHTML\), you must download [Microsoft WebDriver for Microsoft Edge \(EdgeHTML\)][Webdriver].</span></span>  

## <span data-ttu-id="7ca21-132">选择 WebDriver 语言绑定</span><span class="sxs-lookup"><span data-stu-id="7ca21-132">Choose a WebDriver language binding</span></span>  

<span data-ttu-id="7ca21-133">您必须下载的最后一个组件是特定于语言的客户端驱动程序。</span><span class="sxs-lookup"><span data-stu-id="7ca21-133">The last component you must download is a language-specific client driver.</span></span>  <span data-ttu-id="7ca21-134">语言绑定将在 Python、Java、C #、Ruby 和 JavaScript 中编写的代码转换为命令，在[上一节](#download-microsoft-edge-driver)中下载的 Microsoft Edge 驱动程序能够在 microsoft edge \ （Chromium \）中运行。</span><span class="sxs-lookup"><span data-stu-id="7ca21-134">The language binding translates the code you write in Python, Java, C\#, Ruby, and JavaScript into commands that the Microsoft Edge Driver you downloaded in the [previous section](#download-microsoft-edge-driver) is able to run in Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="7ca21-135">[下载你选择的 WebDriver 语言绑定][SeleniumDownloads]。</span><span class="sxs-lookup"><span data-stu-id="7ca21-135">[Download the WebDriver language binding of your choice][SeleniumDownloads].</span></span>  <span data-ttu-id="7ca21-136">Microsoft Edge 团队强烈建议[Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05]或更高版本，因为它具有对 Microsoft Edge \ （Chromium \）的内置支持。</span><span class="sxs-lookup"><span data-stu-id="7ca21-136">The Microsoft Edge team highly recommends [Selenium 4.00-alpha05][NugetPackagesSeleniumWebdriver400alpha05] or later, since it has built-in support for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="7ca21-137">但是，你可以在所有较早版本的 Selenium 中驱动 Microsoft Edge \ （Chromium \），包括当前稳定 Selenium 3 版本。</span><span class="sxs-lookup"><span data-stu-id="7ca21-137">However, you are able to drive Microsoft Edge \(Chromium\) in all older versions of Selenium, including the current stable Selenium 3 release.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="7ca21-138">如果以前使用 and 自动执行或测试 Microsoft Edge \ （Chromium \） `ChromeDriver` ，则 `ChromeOptions` 你的 WebDriver 代码不会成功运行于 microsoft edge v80 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7ca21-138">If you were previously automating or testing Microsoft Edge \(Chromium\) by using `ChromeDriver` and `ChromeOptions`, your WebDriver code does not run successfully against Microsoft Edge v80 or later.</span></span>  <span data-ttu-id="7ca21-139">这是一种重大更改，Microsoft Edge \ （Chromium）不再接受这些命令。</span><span class="sxs-lookup"><span data-stu-id="7ca21-139">This is a breaking change and Microsoft Edge \(Chromium\) no longer accepts these commands.</span></span>  <span data-ttu-id="7ca21-140">必须更改测试才能使用 `EdgeOptions` 类和[Microsoft Edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]。</span><span class="sxs-lookup"><span data-stu-id="7ca21-140">You must change your tests to use the `EdgeOptions` class and [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver].</span></span>  

### <span data-ttu-id="7ca21-141">使用 Selenium 3</span><span class="sxs-lookup"><span data-stu-id="7ca21-141">Using Selenium 3</span></span>  

<span data-ttu-id="7ca21-142">[Selenium 3][|::ref1::|]是最新稳定的 Selenium 版本。</span><span class="sxs-lookup"><span data-stu-id="7ca21-142">[Selenium 3][|::ref1::|] is the latest stable Selenium release.</span></span>  <span data-ttu-id="7ca21-143">默认情况下，Selenium 3 驱动旧的 Microsoft Edge \ （EdgeHTML \），并且没有 Microsoft Edge 的内置支持 \ （Chromium \）。</span><span class="sxs-lookup"><span data-stu-id="7ca21-143">By default, Selenium 3 drives the old Microsoft Edge \(EdgeHTML\), and does not have built-in support for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="7ca21-144">若要将 Selenium 3 与 Microsoft Edge \ （Chromium \）配合使用，请安装[Microsoft edge 程序包的 Selenium 工具][GithubMicrosoftEdgeSeleniumTools]。</span><span class="sxs-lookup"><span data-stu-id="7ca21-144">To use Selenium 3 with Microsoft Edge \(Chromium\), install the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] package.</span></span>  <span data-ttu-id="7ca21-145">适用于 Microsoft Edge 的 Selenium 工具将 Selenium 3 与更新的驱动程序一起扩展，以帮助你为 Microsoft Edge \ （EdgeHTML \）和新的 Microsoft Edge \ （Chromium）浏览器编写自动测试。</span><span class="sxs-lookup"><span data-stu-id="7ca21-145">The Selenium Tools for Microsoft Edge extend Selenium 3 with an updated driver to help you write automated tests for both the Microsoft Edge \(EdgeHTML\) and new Microsoft Edge \(Chromium\) browsers.</span></span>  

<span data-ttu-id="7ca21-146">适用于 Microsoft Edge 的 Selenium 工具是一种解决方案，适用于更喜欢在 Selenium 3 和具有现有浏览器测试的开发人员的开发人员，并且希望在不更改 Selenium 版本的情况下为新的 Microsoft Edge \ （Chromium）浏览器添加覆盖范围。</span><span class="sxs-lookup"><span data-stu-id="7ca21-146">Selenium Tools for Microsoft Edge is a solution for developers who prefer to remain on Selenium 3 and developers who have existing browser tests and want to add coverage for the new Microsoft Edge \(Chromium\) browser without changing Selenium versions.</span></span>  <span data-ttu-id="7ca21-147">`EdgeDriver` `EdgeDriverService` 工具中包含的和类完全兼容 Selenium 中的内置等效项，并默认运行 Microsoft Edge \ （EdgeHTML \），以便可以将工具用作 Selenium 中现有 Edge 类的无缝放置替换。</span><span class="sxs-lookup"><span data-stu-id="7ca21-147">The `EdgeDriver` and `EdgeDriverService` classes included in the tools are fully compatible with the built-in equivalents in Selenium, and run Microsoft Edge \(EdgeHTML\) by default so the tools may be used as a seamless drop-in replacement for the existing Edge classes in Selenium.</span></span>  

<span data-ttu-id="7ca21-148">[安装适用于 Microsoft edge 的 Selenium 工具][GithubMicrosoftEdgeSeleniumTools]，开始在 Selenium 3 项目中使用 microsoft edge \ （Chromium \）。</span><span class="sxs-lookup"><span data-stu-id="7ca21-148">[Install Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] to begin using Microsoft Edge \(Chromium\) with your Selenium 3 project.</span></span>  

## <span data-ttu-id="7ca21-149">将 Microsoft Edge （Chromium）与 WebDriver 结合使用</span><span class="sxs-lookup"><span data-stu-id="7ca21-149">Use Microsoft Edge (Chromium) with WebDriver</span></span>

<span data-ttu-id="7ca21-150">以下示例是使用 Selenium 3 或4的可运行示例。</span><span class="sxs-lookup"><span data-stu-id="7ca21-150">The following examples are runnable using either Selenium 3 or 4.</span></span>  <span data-ttu-id="7ca21-151">若要与 Selenium 3 配合使用，必须安装[适用于 Microsoft Edge 的 Selenium 工具][GithubMicrosoftEdgeSeleniumTools]。</span><span class="sxs-lookup"><span data-stu-id="7ca21-151">To use with Selenium 3, the [Selenium Tools for Microsoft Edge][GithubMicrosoftEdgeSeleniumTools] must be installed.</span></span>  

### <span data-ttu-id="7ca21-152">基本用法</span><span class="sxs-lookup"><span data-stu-id="7ca21-152">Basic Usage</span></span>  

<span data-ttu-id="7ca21-153">若要与 Microsoft Edge \ （EdgeHTML \）一起使用，只需创建该类的默认实例 `EdgeDriver` 。</span><span class="sxs-lookup"><span data-stu-id="7ca21-153">To use with Microsoft Edge \(EdgeHTML\), simply create a default instance of the `EdgeDriver` class.</span></span>

#### [<span data-ttu-id="7ca21-154">C#</span><span class="sxs-lookup"><span data-stu-id="7ca21-154">C#</span></span>](#tab/c-sharp/)  

<a id="basic-usage-code" />  

```csharp
var driver = new EdgeDriver();
```  

#### [<span data-ttu-id="7ca21-155">Python</span><span class="sxs-lookup"><span data-stu-id="7ca21-155">Python</span></span>](#tab/python/)  

<a id="basic-usage-code" />  

```python
driver = Edge()
```  

* * *  

### <span data-ttu-id="7ca21-156">推动 Microsoft Edge （Chromium）</span><span class="sxs-lookup"><span data-stu-id="7ca21-156">Driving Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="7ca21-157">若要改为与 Microsoft Edge \ （Chromium \）一起使用，请创建一个新 `EdgeDriver` 类并将其传递给该 `EdgeOptions` `UseChromium` 属性设置为的对象 `true` 。</span><span class="sxs-lookup"><span data-stu-id="7ca21-157">To use with Microsoft Edge \(Chromium\) instead, create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.</span></span>  

#### [<span data-ttu-id="7ca21-158">C#</span><span class="sxs-lookup"><span data-stu-id="7ca21-158">C#</span></span>](#tab/c-sharp/)  

<a id="diving-microsoft-edge-chromium-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="7ca21-159">Python</span><span class="sxs-lookup"><span data-stu-id="7ca21-159">Python</span></span>](#tab/python/)  

<a id="diving-microsoft-edge-chromium-code" />  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

* * *  

### <span data-ttu-id="7ca21-160">选择特定浏览器二进制文件（仅限 Chromium）</span><span class="sxs-lookup"><span data-stu-id="7ca21-160">Choosing Specific Browser Binaries (Chromium-Only)</span></span>  

<span data-ttu-id="7ca21-161">使用 `EdgeOptions` 类选择特定的二进制文件。</span><span class="sxs-lookup"><span data-stu-id="7ca21-161">Use the `EdgeOptions` class to choose a specific binary.</span></span>  <span data-ttu-id="7ca21-162">它对于测试[Microsoft edge 预览频道][MicrosoftedgeinsiderDownload]（如 Microsoft edge Beta）很有用。</span><span class="sxs-lookup"><span data-stu-id="7ca21-162">It is useful for testing [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.</span></span>  

#### [<span data-ttu-id="7ca21-163">C#</span><span class="sxs-lookup"><span data-stu-id="7ca21-163">C#</span></span>](#tab/c-sharp/)  

<a id="choosing-specific-browser-binaries-chrome-only-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### [<span data-ttu-id="7ca21-164">Python</span><span class="sxs-lookup"><span data-stu-id="7ca21-164">Python</span></span>](#tab/python/)  

<a id="choosing-specific-browser-binaries-chrome-only-code" />  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

* * *  

### <span data-ttu-id="7ca21-165">自定义 Microsoft Edge 驱动程序服务</span><span class="sxs-lookup"><span data-stu-id="7ca21-165">Customizing the Microsoft Edge Driver Service</span></span>  

#### [<span data-ttu-id="7ca21-166">C#</span><span class="sxs-lookup"><span data-stu-id="7ca21-166">C#</span></span>](#tab/c-sharp/)  

<a id="customizing-microsoft-edge-driver-services-code" />  

<span data-ttu-id="7ca21-167">`EdgeDriver`使用类创建类实例时 `EdgeOptions` ，它会自动 `EdgeDriverService` 为 microsoft Edge \ （EdgeHTML \）或 microsoft Edge \ （Chromium \）创建和启动相应的类。</span><span class="sxs-lookup"><span data-stu-id="7ca21-167">When an `EdgeDriver` class instance is created using `EdgeOptions` class, it automatically creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).</span></span>  

<span data-ttu-id="7ca21-168">如果你想要创建 `EdgeDriverService` ，请使用方法为 Microsoft Edge \ （Chromium \）配置一个 `CreateChromiumService()` 。</span><span class="sxs-lookup"><span data-stu-id="7ca21-168">If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.</span></span>  <span data-ttu-id="7ca21-169">你可能会发现它对于其他自定义非常有用，例如，在以下代码中启用详细日志输出。</span><span class="sxs-lookup"><span data-stu-id="7ca21-169">You may find it useful for additional customizations like enabling verbose log output in the following code.</span></span>  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE]
> <span data-ttu-id="7ca21-170">在 `EdgeOptions` 将类实例传递给时，不需要提供对象 `EdgeDriver` `EdgeDriverService` 。</span><span class="sxs-lookup"><span data-stu-id="7ca21-170">You do not need to provide the `EdgeOptions` object when passing the `EdgeDriver` class instance the `EdgeDriverService`.</span></span>  <span data-ttu-id="7ca21-171">`EdgeDriver`对于 Microsoft edge \ （EdgeHTML \）或 Microsoft edge \ （Chromium \），该类使用默认选项，具体取决于你提供的服务类型。</span><span class="sxs-lookup"><span data-stu-id="7ca21-171">The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) depending on what kind of service you provide.</span></span>  
> 
> <span data-ttu-id="7ca21-172">但是，如果你希望同时提供 a `EdgeDriverService` 和 `EdgeOptions` 类，则必须确保两个版本的 Microsoft Edge 都配置了这两个类。</span><span class="sxs-lookup"><span data-stu-id="7ca21-172">However, if you want to provide both an `EdgeDriverService` and `EdgeOptions` classes, you must ensure that both are configured for the same version of Microsoft Edge.</span></span>  <span data-ttu-id="7ca21-173">例如，不能在类中使用默认的 Microsoft Edge \ （EdgeHTML \） `EdgeDriverService` 类和 Chromium 属性 `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="7ca21-173">For example, it is not possible to use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.</span></span>  <span data-ttu-id="7ca21-174">`EdgeDriver`该类将引发错误以防止使用不同版本。</span><span class="sxs-lookup"><span data-stu-id="7ca21-174">The `EdgeDriver` class throws an error to prevent using different versions.</span></span>  

#### [<span data-ttu-id="7ca21-175">Python</span><span class="sxs-lookup"><span data-stu-id="7ca21-175">Python</span></span>](#tab/python/)  

<a id="customizing-microsoft-edge-driver-services-code" />  

<span data-ttu-id="7ca21-176">使用 Python 时， `Edge` 对象将创建并管理 `EdgeService` 。</span><span class="sxs-lookup"><span data-stu-id="7ca21-176">When using Python, the `Edge` object creates and manages the `EdgeService`.</span></span>  <span data-ttu-id="7ca21-177">若要配置 `EdgeService` ，请将其他参数传递给该 `Edge` 对象：</span><span class="sxs-lookup"><span data-stu-id="7ca21-177">To configure the `EdgeService`, pass additional arguments to the `Edge` object:</span></span>

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

* * *  

### <span data-ttu-id="7ca21-178">使用 Chromium 特定选项</span><span class="sxs-lookup"><span data-stu-id="7ca21-178">Using Chromium-Specific Options</span></span>  

<span data-ttu-id="7ca21-179">`EdgeOptions`将类与设置的属性结合使用，可 `UseChromium` `true` 让你访问 Selenium 中的[ChromeOptions][SeleniumWebDriverChromeoptionsClass]类中可用的所有相同方法和属性。</span><span class="sxs-lookup"><span data-stu-id="7ca21-179">Using the `EdgeOptions` class with the `UseChromium` property set to `true` gives you access to all of the same methods and properties that are available in the [ChromeOptions][SeleniumWebDriverChromeoptionsClass] class in Selenium.</span></span>  <span data-ttu-id="7ca21-180">例如，与其他 Chromium 浏览器一样，在 `EdgeOptions.AddArguments()` 以下代码中使用方法在无[外设模式][WikiHeadlessBrowser]下运行 Microsoft Edge \ （Chromium \）。</span><span class="sxs-lookup"><span data-stu-id="7ca21-180">For example, just like with other Chromium browsers, use the `EdgeOptions.AddArguments()` method to run Microsoft Edge \(Chromium\) in [headless mode][WikiHeadlessBrowser] in the following code.</span></span>  

#### [<span data-ttu-id="7ca21-181">C#</span><span class="sxs-lookup"><span data-stu-id="7ca21-181">C#</span></span>](#tab/c-sharp/)  

<a id="using-chromium-specific-options-code" />  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### [<span data-ttu-id="7ca21-182">Python</span><span class="sxs-lookup"><span data-stu-id="7ca21-182">Python</span></span>](#tab/python/)  

<a id="using-chromium-specific-options-code" />  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument('headless')
options.add_argument('disable-gpu')
```  

* * *  

> [!NOTE]
> <span data-ttu-id="7ca21-183">这些[特定于 Chromium 的属性和方法][SeleniumWebDriverChromeoptionsClass]始终可用，但如果 `UseChromium` 属性未设置为，则不起作用 `true` 。</span><span class="sxs-lookup"><span data-stu-id="7ca21-183">These [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] are always available but have no effect if the `UseChromium` property is not set to `true`.</span></span>  <span data-ttu-id="7ca21-184">同样，如果属性设置为，则适用于 Microsoft Edge \ （EdgeHTML \）的现有属性和方法将不起作用 `UseChromium` `true` 。</span><span class="sxs-lookup"><span data-stu-id="7ca21-184">Similarly, existing properties and methods meant for Microsoft Edge \(EdgeHTML\) have no effect if `UseChromium` property is set to `true`.</span></span>  

<!--  
### [C#](#tab/c-sharp/)  

<a id="selenium-usage" />  

#### Basic Usage  

To use with Microsoft Edge \(EdgeHTML\), simply create a default instance of the `EdgeDriver` class.

```csharp
var driver = new EdgeDriver();
```  

#### Driving Microsoft Edge (Chromium)  

To use with Microsoft Edge \(Chromium\) instead, create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### Choosing Specific Browser Binaries (Chromium-Only)  

Use the `EdgeOptions` class to choose a specific binary.  It is useful for testing [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### Customizing the Edge Driver Service  

When an `EdgeDriver` class instance is created using `EdgeOptions` class, it automatically creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).  

If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.  You may find it useful for additional customizations like enabling verbose log output in the following code.  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE]
> You do not need to provide the `EdgeOptions` object when passing the `EdgeDriver` class instance the `EdgeDriverService`.  The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) depending on what kind of service you provide.  
> 
> However, if you want to provide both an `EdgeDriverService` and `EdgeOptions` classes, you must ensure that both are configured for the same version of Microsoft Edge.  For example, it is not possible to use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.  The `EdgeDriver` class throws an error to prevent using different versions.  

#### Using Chromium-Specific Options  

Using the `EdgeOptions` class with the `UseChromium` property set to `true` gives you access to all of the same methods and properties that are available in the [ChromeOptions][SeleniumWebDriverChromeoptionsClass] class in Selenium.  For example, just like with other Chromium browsers, use the `EdgeOptions.AddArguments()` method to run Microsoft Edge \(Chromium\) in [headless mode][WikiHeadlessBrowser] in the following code.  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

> [!NOTE]
> These [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] are always available but have no effect if the `UseChromium` property is not set to `true`.  Similarly, existing properties and methods meant for Microsoft Edge \(EdgeHTML\) have no effect if `UseChromium` property is set to `true`.  

### [Python](#tab/python/)  

<a id="selenium-usage" />  

#### Basic Usage  

To use with Microsoft Edge \(EdgeHTML\), simply create a default instance of the `EdgeDriver` class.

```python
driver = Edge()
```  

#### Driving Microsoft Edge (Chromium)  

To use with Microsoft Edge \(Chromium\) instead, create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

#### Choosing Specific Browser Binaries (Chromium-Only)  

Use the `EdgeOptions` class to choose a specific binary.  It is useful for testing [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

#### Customizing the Edge Driver Service  

When an `EdgeDriver` class instance is created using `EdgeOptions` class, it automatically creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).  

If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.  You may find it useful for additional customizations like enabling verbose log output in the following code.  

When using Python, the `Edge` object creates and manages the `EdgeService`.  To configure the `EdgeService`, pass additional arguments to the `Edge` object:

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

#### Using Chromium-Specific Options  

Using the `EdgeOptions` class with the `UseChromium` property set to `true` gives you access to all of the same methods and properties that are available in the [ChromeOptions][SeleniumWebDriverChromeoptionsClass] class in Selenium.  For example, just like with other Chromium browsers, use the `EdgeOptions.AddArguments()` method to run Microsoft Edge \(Chromium\) in [headless mode][WikiHeadlessBrowser] in the following code.  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument('headless')
options.add_argument('disable-gpu')
```  

> [!NOTE]
> These [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] are always available but have no effect if the `UseChromium` property is not set to `true`.  Similarly, existing properties and methods meant for Microsoft Edge \(EdgeHTML\) have no effect if `UseChromium` property is set to `true`.  

* * *  

-->  

<!--  
### Basic Usage  

To use with Microsoft Edge \(EdgeHTML\), simply create a default instance of the `EdgeDriver` class.

#### C\#  

```csharp
var driver = new EdgeDriver();
```  

#### Python  

```python
driver = Edge()
```  

### Driving Microsoft Edge (Chromium)  

To use with Microsoft Edge \(Chromium\) instead, create a new `EdgeDriver` class and pass it the `EdgeOptions` object with the `UseChromium` property set to `true`.  

#### C\#  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;

var driver = new EdgeDriver(options);
```  

#### Python  

```python
options = EdgeOptions()
options.use_chromium = True

driver = Edge(options)
```  

### Choosing Specific Browser Binaries (Chromium-Only)  

Use the `EdgeOptions` class to choose a specific binary.  It is useful for testing [Microsoft Edge preview channels][MicrosoftedgeinsiderDownload] such as Microsoft Edge Beta.  

#### C\#  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.BinaryLocation = @"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe";

var driver = new EdgeDriver(options);
```  

#### Python  

```python
options = EdgeOptions()
options.use_chromium = True
options.binary_location = r"C:\Program Files (x86)\Microsoft\Edge Beta\Application\msedge.exe"

driver = Edge(options)
```  

### Customizing the Edge Driver Service  

#### C\#  

When an `EdgeDriver` class instance is created using `EdgeOptions` class, it automatically creates and launches the appropriate `EdgeDriverService` class for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\).  

If you want to create an `EdgeDriverService`, create one configured for Microsoft Edge \(Chromium\) using the `CreateChromiumService()` method.  You may find it useful for additional customizations like enabling verbose log output in the following code.  

```csharp
using (var service = EdgeDriverService.CreateChromiumService())
{
    service.UseVerboseLogging = true;

    var driver = new EdgeDriver(service);
}
```  

> [!NOTE]
> You do not need to provide the `EdgeOptions` object when passing the `EdgeDriver` class instance the `EdgeDriverService`.  The `EdgeDriver` class uses the default options for either Microsoft Edge \(EdgeHTML\) or Microsoft Edge \(Chromium\) depending on what kind of service you provide.  
> 
> However, if you want to provide both an `EdgeDriverService` and `EdgeOptions` classes, you must ensure that both are configured for the same version of Microsoft Edge.  For example, it is not possible to use a default Microsoft Edge \(EdgeHTML\) `EdgeDriverService` class and Chromium properties in the `EdgeOptions` class.  The `EdgeDriver` class throws an error to prevent using different versions.  

#### Python  

When using Python, the `Edge` object creates and manages the `EdgeService`.  To configure the `EdgeService`, pass additional arguments to the `Edge` object:

```python
service_args = ['--verbose']
driver = Edge(service_args = service_args)
```  

### Using Chromium-Specific Options  

Using the `EdgeOptions` class with the `UseChromium` property set to `true` gives you access to all of the same methods and properties that are available in the [ChromeOptions][SeleniumWebDriverChromeoptionsClass] class in Selenium.  For example, just like with other Chromium browsers, use the `EdgeOptions.AddArguments()` method to run Microsoft Edge \(Chromium\) in [headless mode][WikiHeadlessBrowser] in the following code.  

#### C\#  

```csharp
var options = new EdgeOptions();
options.UseChromium = true;
options.AddArgument("headless");
options.AddArgument("disable-gpu");
```  

#### Python  

```python
options = EdgeOptions()
options.use_chromium = True
options.add_argument('headless')
options.add_argument('disable-gpu')
```  

> [!NOTE]
> These [Chromium-specific properties and methods][SeleniumWebDriverChromeoptionsClass] are always available but have no effect if the `UseChromium` property is not set to `true`.  Similarly, existing properties and methods meant for Microsoft Edge \(EdgeHTML\) have no effect if `UseChromium` property is set to `true`.  
-->  

## <span data-ttu-id="7ca21-185">设置 WebDriver 的其他方法</span><span class="sxs-lookup"><span data-stu-id="7ca21-185">Other ways to set up WebDriver</span></span>  

### <span data-ttu-id="7ca21-186">Chocolatey</span><span class="sxs-lookup"><span data-stu-id="7ca21-186">Chocolatey</span></span>  

<span data-ttu-id="7ca21-187">如果你使用的是[Chocolatey][Chocolatey]作为程序包管理器，请通过运行以下命令来安装 Microsoft Edge 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="7ca21-187">If you are using [Chocolatey][Chocolatey] as your package manager, install the Microsoft Edge Driver by running the following command.</span></span>  

```console
choco install selenium-chromium-edge-driver
```  

<span data-ttu-id="7ca21-188">有关详细信息，请参阅[Chocolatey 上的 Selenium Chromium Edge 驱动程序][ChocolateyPackagesSeleniumChromiumEdgeDriver]。</span><span class="sxs-lookup"><span data-stu-id="7ca21-188">For more information, see [Selenium Chromium Edge Driver on Chocolatey][ChocolateyPackagesSeleniumChromiumEdgeDriver].</span></span>  

### <span data-ttu-id="7ca21-189">Docker</span><span class="sxs-lookup"><span data-stu-id="7ca21-189">Docker</span></span>  

<span data-ttu-id="7ca21-190">如果您使用的是[Docker][DockerHub]，请通过运行以下命令，下载已安装 microsoft edge \ （Chromium \）和[Microsoft edge 驱动程序][MicrosoftDeveloperEdgeToolsWebdriver]的预配置图像。</span><span class="sxs-lookup"><span data-stu-id="7ca21-190">If you are using [Docker][DockerHub], download a pre-configured image with Microsoft Edge \(Chromium\) and [Microsoft Edge Driver][MicrosoftDeveloperEdgeToolsWebdriver] already installed by running the following command.</span></span>  

```console
docker run -d -p 9515:9515 mcr.microsoft.com/msedge/msedgedriver
```  

<span data-ttu-id="7ca21-191">有关详细信息，请参阅[Docker 中心上的容器][DockerHubMsedgedriver]。</span><span class="sxs-lookup"><span data-stu-id="7ca21-191">For more information, see [container on Docker Hub][DockerHubMsedgedriver].</span></span>  

## <span data-ttu-id="7ca21-192">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="7ca21-192">Getting in touch with the Microsoft Edge DevTools team</span></span>    

<span data-ttu-id="7ca21-193">Microsoft Edge 团队渴望听到有关使用 WebDriver、Selenium 和 Microsoft Edge 的反馈！</span><span class="sxs-lookup"><span data-stu-id="7ca21-193">The Microsoft Edge team is eager to hear your feedback about using WebDriver, Selenium, and Microsoft Edge!</span></span>  <span data-ttu-id="7ca21-194">使用 Microsoft Edge DevTools 或 tweet [@EdgeDevTools][TwitterTweetEdgeDevTools]中的**反馈**图标，让团队知道您的想法。</span><span class="sxs-lookup"><span data-stu-id="7ca21-194">Use the **Feedback** icon in the Microsoft Edge DevTools or tweet [@EdgeDevTools][TwitterTweetEdgeDevTools] to let the team know what you think.</span></span>  


:::image type="complex" source="./devtools-guide-chromium/media/devtools-feedback.png" alt-text="Microsoft Edge DevTools 中的 "反馈" 图标":::
   <span data-ttu-id="7ca21-196">Microsoft Edge DevTools 中的 "**反馈**" 图标</span><span class="sxs-lookup"><span data-stu-id="7ca21-196">The **Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::

<!--  
> ##### Figure 3  
> The **Feedback** icon in the Microsoft Edge DevTools  
> ![The example.png file produced by example.js][ImageDevtoolsGuideChromiumMediaDevtoolsFeedback])  
-->  

<!-- image links -->  

<!--[ImageWebdriverChromiumEdgeVersion]: ./media/webdriver-chromium/edge-version.png "Figure 1: The build number for Microsoft Edge Canary on January 14, 2020"  -->  
<!--[ImageWebdriverChromiumEdgeDriverInstall]: ./media/webdriver-chromium/edge-driver-install.png "Figure 2: The Downloads section of the Microsoft Edge Driver page"  -->
<!--[ImageDevtoolsGuideChromiumMediaDevtoolsFeedback]: ./devtools-guide-chromium/media/devtools-feedback.png "Figure 3: The example.png file produced by example.js"  -->  

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
