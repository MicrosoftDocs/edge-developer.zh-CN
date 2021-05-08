---
description: 使用驱动程序自动化和测试 WebView2 Microsoft Edge
title: 使用驱动程序自动化和测试 WebView2 Microsoft Edge驱动程序
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、edge、ICoreWebView2、ICoreWebView2Controller、Selenium、Microsoft Edge Driver
ms.openlocfilehash: c23d639582d4ce550406cf955c96171167bde7c8
ms.sourcegitcommit: e3cd336c9448277e0dde3b9da1521b5cbc7c44d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536340"
---
# <a name="automating-and-testing-webview2-with-microsoft-edge-driver"></a><span data-ttu-id="1c309-104">使用驱动程序自动化和测试 WebView2 Microsoft Edge驱动程序</span><span class="sxs-lookup"><span data-stu-id="1c309-104">Automating and testing WebView2 with Microsoft Edge Driver</span></span>  

<span data-ttu-id="1c309-105">由于 WebView2 使用 Microsoft Edge \ (Chromium\) Web 平台，因此 WebView2 开发人员 \ (you\) 可以利用标准 Web 工具进行调试和自动化。</span><span class="sxs-lookup"><span data-stu-id="1c309-105">Because WebView2 uses the Microsoft Edge \(Chromium\) web platform, WebView2 developers \(you\) may take advantage of standard web tooling for debugging and automation.</span></span>  <span data-ttu-id="1c309-106">Selenium 是此类工具之一。</span><span class="sxs-lookup"><span data-stu-id="1c309-106">Selenium is one such tool.</span></span>  <span data-ttu-id="1c309-107">它实现 W3C [WebDriver][W3cWebdriver2] API。</span><span class="sxs-lookup"><span data-stu-id="1c309-107">It implements the W3C [WebDriver][W3cWebdriver2] API.</span></span>  <span data-ttu-id="1c309-108">可以使用 Selenium 创建自动测试来模拟用户交互。</span><span class="sxs-lookup"><span data-stu-id="1c309-108">You may use Selenium to create automated tests to simulate user interactions.</span></span>  

<span data-ttu-id="1c309-109">开始执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1c309-109">Get started with the following steps.</span></span>  

## <a name="step-1--download-webview2api-sample"></a><span data-ttu-id="1c309-110">步骤 1：下载 WebView2API 示例</span><span class="sxs-lookup"><span data-stu-id="1c309-110">Step 1:  Download WebView2API Sample</span></span>  

<span data-ttu-id="1c309-111">如果你没有现有的 WebView2 项目，请下载 [WebView2API 示例][GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]应用，这是最新的 WebView2 SDK 的全面示例。</span><span class="sxs-lookup"><span data-stu-id="1c309-111">If you do not have an existing WebView2 project, download the [WebView2API Sample app][GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample], a comprehensive sample of the latest WebView2 SDK.</span></span>  <span data-ttu-id="1c309-112">确保你已满足 [WebView2API 示例应用的先决条件][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]。</span><span class="sxs-lookup"><span data-stu-id="1c309-112">Ensure you have satisfied the [prerequisites for the WebView2API Sample app][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites].</span></span>  

<span data-ttu-id="1c309-113">克隆存储库后，在"文件"中生成Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="1c309-113">Once you have cloned the repo, build the project in Visual Studio.</span></span>  <span data-ttu-id="1c309-114">它应如下图所示。</span><span class="sxs-lookup"><span data-stu-id="1c309-114">It should look like the following figure.</span></span>  

:::image type="complex" source="../media/webdriver/sample-app.png" alt-text="WebView2API 示例应用" lightbox="../media/webdriver/sample-app.png":::
   <span data-ttu-id="1c309-116">WebView2API 示例应用</span><span class="sxs-lookup"><span data-stu-id="1c309-116">WebView2API Sample app</span></span>  
:::image-end:::  

## <a name="step-2--install-microsoft-edge-driver"></a><span data-ttu-id="1c309-117">步骤 2：安装Microsoft Edge驱动程序</span><span class="sxs-lookup"><span data-stu-id="1c309-117">Step 2:  Install Microsoft Edge Driver</span></span>  

<span data-ttu-id="1c309-118">按照说明安装[Microsoft Edge 驱动程序][WebdriverChromiumDownloadMicrosoftEdgeDriver]Selenium 自动化和测试 WebView2 所需的特定于浏览器的驱动程序。</span><span class="sxs-lookup"><span data-stu-id="1c309-118">Follow the instructions to install [Microsoft Edge Driver][WebdriverChromiumDownloadMicrosoftEdgeDriver] the browser-specific driver required by Selenium to automate and test WebView2.</span></span>  

<span data-ttu-id="1c309-119">确保驱动程序的版本Microsoft Edge应用使用的 WebView2 运行时版本匹配。</span><span class="sxs-lookup"><span data-stu-id="1c309-119">Ensure that the version of Microsoft Edge Driver matches the version of WebView2 Runtime that you app uses.</span></span>  <span data-ttu-id="1c309-120">若要使 WebView2API 示例正常工作，请确保你的 WebView2 运行时版本大于或等于最新 WebView2 SDK 版本的受支持版本。</span><span class="sxs-lookup"><span data-stu-id="1c309-120">For the WebView2API Sample to work, make sure that your version of WebView2 Runtime is greater than or equal than the supported version of the latest WebView2 SDK release.</span></span>  <span data-ttu-id="1c309-121">若要查找最新的 WebView2 SDK 版本，请导航到 [WebView2 发行说明][Webview2Releasenotes]。</span><span class="sxs-lookup"><span data-stu-id="1c309-121">To locate the latest WebView2 SDK release, navigate to [WebView2 release notes][Webview2Releasenotes].</span></span>  <span data-ttu-id="1c309-122">若要了解当前具有的 WebView2 运行时版本，请导航到 `edge://settings/help` 。</span><span class="sxs-lookup"><span data-stu-id="1c309-122">To find out what version of WebView2 Runtime you currently have, navigate to `edge://settings/help`.</span></span>  

## <a name="step-3--add-selenium-to-the-webview2api-sample"></a><span data-ttu-id="1c309-123">步骤 3：将 Selenium 添加到 WebView2API 示例</span><span class="sxs-lookup"><span data-stu-id="1c309-123">Step 3:  Add Selenium to the WebView2API Sample</span></span>  

<span data-ttu-id="1c309-124">此时，你应该已安装 WebView2 运行时，生成了 WebView2 项目，并且Microsoft Edge驱动程序。</span><span class="sxs-lookup"><span data-stu-id="1c309-124">At this point you should have WebView2 Runtime installed, built a WebView2 project, and installed Microsoft Edge Driver.</span></span>  <span data-ttu-id="1c309-125">现在，开始使用 Selenium。</span><span class="sxs-lookup"><span data-stu-id="1c309-125">Now, get started using Selenium.</span></span>  

> [!NOTE]
> <span data-ttu-id="1c309-126">Selenium 支持 C\#、Java、Python、Javascript 和 Ruby。</span><span class="sxs-lookup"><span data-stu-id="1c309-126">Selenium supports C\#, Java, Python, Javascript, and Ruby.</span></span>  <span data-ttu-id="1c309-127">但是，以下指南是使用 C\# 编写的。</span><span class="sxs-lookup"><span data-stu-id="1c309-127">However, the following guide is written using C\#.</span></span>  

1.  <span data-ttu-id="1c309-128">首先，在**Visual Studio**新建C# .NET Framework**项目**。</span><span class="sxs-lookup"><span data-stu-id="1c309-128">Start by creating a new **C# .NET Framework** project in **Visual Studio**.</span></span>  <span data-ttu-id="1c309-129">选择 **右** 下角的"下一步"继续。</span><span class="sxs-lookup"><span data-stu-id="1c309-129">Choose **Next** on the bottom right-hand corner to continue.</span></span>  
    
    :::image type="complex" source="../media/webdriver/new-project.png" alt-text="创建新项目" lightbox="../media/webdriver/new-project.png":::
       <span data-ttu-id="1c309-131">创建新项目</span><span class="sxs-lookup"><span data-stu-id="1c309-131">Create a new project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1c309-132">为项目命名 **，** 将其保存到首选**位置**，然后选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="1c309-132">Give your project a **name**, save it to your preferred **location**, and choose **Create**.</span></span>  
    
    :::image type="complex" source="../media/webdriver/app-create.png" alt-text="配置新项目" lightbox="../media/webdriver/app-create.png":::
       <span data-ttu-id="1c309-134">配置新项目</span><span class="sxs-lookup"><span data-stu-id="1c309-134">Configure your new project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1c309-135">将创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="1c309-135">A new project is created.</span></span>  <span data-ttu-id="1c309-136">在本指南中，所有代码都写入 `Program.cs` 文件。</span><span class="sxs-lookup"><span data-stu-id="1c309-136">In this guide, all code is written to the `Program.cs` file.</span></span>  
    
    :::image type="complex" source="../media/webdriver/start-app.png" alt-text="新建项目" lightbox="../media/webdriver/start-app.png":::
       <span data-ttu-id="1c309-138">新建项目</span><span class="sxs-lookup"><span data-stu-id="1c309-138">New project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1c309-139">现在，将 **Selenium** 添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="1c309-139">Now add **Selenium** to the project.</span></span>  <span data-ttu-id="1c309-140">使用**Selenium.WebDriver NuGet安装 Selenium。**</span><span class="sxs-lookup"><span data-stu-id="1c309-140">Install Selenium using the **Selenium.WebDriver NuGet package**.</span></span>  
    
    <span data-ttu-id="1c309-141">若要下载**Selenium.WebDriver NuGet程序包**，Visual Studio**悬停在** **Project**上，然后选择"管理 NuGet**程序包"。**</span><span class="sxs-lookup"><span data-stu-id="1c309-141">To download the **Selenium.WebDriver NuGet package**, in **Visual Studio**, hover on **Project**, and choose **Manage NuGet Package**.</span></span>  <span data-ttu-id="1c309-142">应显示以下屏幕。</span><span class="sxs-lookup"><span data-stu-id="1c309-142">The following screen should appear.</span></span>  
    
    :::image type="complex" source="../media/webdriver/download-nuget.png" alt-text="下载NuGet包" lightbox="../media/webdriver/download-nuget.png":::
       <span data-ttu-id="1c309-144">下载NuGet包</span><span class="sxs-lookup"><span data-stu-id="1c309-144">Download NuGet package</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1c309-145">在 `Selenium.WebDriver` 搜索栏中输入，从结果中选择 **Selenium.WebDriver，** 并确保选中复选框以包含 **预发布**。</span><span class="sxs-lookup"><span data-stu-id="1c309-145">Enter `Selenium.WebDriver` in the search bar, choose **Selenium.WebDriver** from the results, and make sure to checkmark the box next to **include pre-release**.</span></span>  <span data-ttu-id="1c309-146">在右侧窗口中，确保"**版本**"设置为安装**4.0.0-alpha04**或更高版本，然后选择"**安装"。**</span><span class="sxs-lookup"><span data-stu-id="1c309-146">On the right-hand side window, ensure the **Version** is set to **install 4.0.0-alpha04** or later and choose **Install**.</span></span>  <span data-ttu-id="1c309-147">NuGet将 Selenium 下载到计算机。</span><span class="sxs-lookup"><span data-stu-id="1c309-147">NuGet downloads Selenium to your machine.</span></span>  
    
    <span data-ttu-id="1c309-148">若要了解有关 Selenium.WebDriver NuGet程序包，请导航到[Selenium.WebDriver 4.0.0-alpha04。][NugetSeleniumWebdriver400Alpha04]</span><span class="sxs-lookup"><span data-stu-id="1c309-148">To learn more about the Selenium.WebDriver NuGet package, navigate to [Selenium.WebDriver 4.0.0-alpha04][NugetSeleniumWebdriver400Alpha04].</span></span>  
    
    :::image type="complex" source="../media/webdriver/nuget.png" alt-text="管理NuGet包" lightbox="../media/webdriver/nuget.png":::
       <span data-ttu-id="1c309-150">管理NuGet包</span><span class="sxs-lookup"><span data-stu-id="1c309-150">Manage NuGet package</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1c309-151">`OpenQA.Selenium.Edge`通过添加以下语句来使用： `using OpenQA.Selenium.Edge;` 在文件的 `Program.cs` 开头。</span><span class="sxs-lookup"><span data-stu-id="1c309-151">Use `OpenQA.Selenium.Edge` by adding the following statement:  `using OpenQA.Selenium.Edge;` at the beginning of `Program.cs` file.</span></span>  
    
    ```csharp
    using OpenQA.Selenium.Edge;
    
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    ```  
    
## <a name="step-4-drive-webview2-with-selenium-and-microsoft-edge-driver"></a><span data-ttu-id="1c309-152">步骤 4：使用 Selenium 和 Microsoft Edge 驱动程序驱动 WebView2</span><span class="sxs-lookup"><span data-stu-id="1c309-152">Step 4: Drive WebView2 with Selenium and Microsoft Edge Driver</span></span>  

1.  <span data-ttu-id="1c309-153">首先，通过 `EdgeOptions` 复制以下代码段创建对象。</span><span class="sxs-lookup"><span data-stu-id="1c309-153">First, create the `EdgeOptions` object, by copying the following code snippet.</span></span>  
    
    ```csharp
    static void Main(string[] args)
    {
        // EdgeOptions() requires using OpenQA.Selenium.Edge
        // Construct EdgeOptions with is_legacy = false and the string "webview2"
        EdgeOptions edgeOptions = new EdgeOptions(false, "webview2");
    ```  
    
    <span data-ttu-id="1c309-154">`EdgeOptions`对象采用以下两个参数。</span><span class="sxs-lookup"><span data-stu-id="1c309-154">The `EdgeOptions` object takes in the following two parameters.</span></span>  
    
    | <span data-ttu-id="1c309-155">参数</span><span class="sxs-lookup"><span data-stu-id="1c309-155">Parameter</span></span> | <span data-ttu-id="1c309-156">详细信息</span><span class="sxs-lookup"><span data-stu-id="1c309-156">Details</span></span> |    
    |:--- |:--- |  
    | `is_legacy` | <span data-ttu-id="1c309-157">设置为 `false` ，这将告知 Selenium 你正在驱动基于Chromium的新Microsoft Edge浏览器。</span><span class="sxs-lookup"><span data-stu-id="1c309-157">Set to `false`, which tells Selenium that you are driving the new Chromium-based Microsoft Edge browser.</span></span> |  
    | `"webview2"` | <span data-ttu-id="1c309-158">一个字符串，告知 Selenium 你正在驱动 WebView2。</span><span class="sxs-lookup"><span data-stu-id="1c309-158">A string that tells Selenium you are driving WebView2.</span></span> |  
    
1.  <span data-ttu-id="1c309-159">接下来，设置为 WebView2 项目运行时的文件路径，创建一个名为 的字符串，该字符串提供安装 Microsoft Edge Driver 的文件路径，并创建一个名为 的字符串来存储 Microsoft Edge Driver 运行时 `edgeOptions.BinaryLocation` `msedgedriverDir` [][MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads] `msedgedriverExe` 的名称。</span><span class="sxs-lookup"><span data-stu-id="1c309-159">Next, set `edgeOptions.BinaryLocation` to the file path of your WebView2 project runtime, create a string named `msedgedriverDir` that provides the file path to where you installed [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads], and create a string named `msedgedriverExe` to store the name of the Microsoft Edge Driver runtime.</span></span>  <span data-ttu-id="1c309-160">默认情况下，运行时命名为 `msedgedriver.exe` 。</span><span class="sxs-lookup"><span data-stu-id="1c309-160">By default, the runtime is named `msedgedriver.exe`.</span></span> <span data-ttu-id="1c309-161">使用以下两个字符串构造 `EdgeDriverService` 对象，如下所示。</span><span class="sxs-lookup"><span data-stu-id="1c309-161">Use these two strings to construct the `EdgeDriverService` object as shown below.</span></span>  <span data-ttu-id="1c309-162">最后，使用 `EdgeDriver` 和 `EdgeDriverService` 创建对象 `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="1c309-162">Finally, create the `EdgeDriver` object using `EdgeDriverService` and `EdgeOptions`.</span></span>  
    
    <span data-ttu-id="1c309-163">你可以复制并粘贴下面的代码 `edgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="1c309-163">You may copy and paste the following code underneath `edgeOptions`.</span></span>  <span data-ttu-id="1c309-164">确保为项目运行时指定正确的文件路径，并指定Microsoft Edge驱动程序运行时。</span><span class="sxs-lookup"><span data-stu-id="1c309-164">Ensure you specify the correct file paths to your project runtime and the Microsoft Edge Driver runtime on your machine.</span></span>  
    
    ```csharp
    //Set the BinaryLocation to the filepath of the WebView2API Sample runtime
    edgeOptions.BinaryLocation = @"C:\path\to\your\webview2\project.exe";
    
    //Set msedgedriverDir to the filepath of the directory housing msedgedriver.exe
    string msedgedriverDir = @"C:\path\to\your\msededriver.exe's\directory";
    
    //Set msedgedriverExe to the name of the Edge Driver. By default it is:
    string msedgedriverExe = @"msedgedriver.exe";
    
    // Construct EdgeDriverService with is_legacy = false  
    EdgeDriverService service = EdgeDriverService.CreateDefaultService(msedgedriverDir, msedgedriverExe, false);
    
    EdgeDriver e = new EdgeDriver(service, edgeOptions);
    ```
    
3.  <span data-ttu-id="1c309-165">现在 `EdgeDriver` ，配置为在项目中驱动 WebView2。</span><span class="sxs-lookup"><span data-stu-id="1c309-165">Now, `EdgeDriver` is configured to drive the WebView2 in your project.</span></span>  <span data-ttu-id="1c309-166">例如，如果你使用的是 **WebView2API 示例**，可以通过运行 命令 `https://microsoft.com` 导航 `e.Url = @"https://www.microsoft.com";` 到 。</span><span class="sxs-lookup"><span data-stu-id="1c309-166">For example, if you are using the **WebView2API Sample**, you may navigate to `https://microsoft.com` by running the `e.Url = @"https://www.microsoft.com";` command.</span></span>  <span data-ttu-id="1c309-167">通过设置线路上的断点并运行项目来验证 Selenium 驱动器 WebView2。</span><span class="sxs-lookup"><span data-stu-id="1c309-167">Verify the Selenium drive WebView2 by setting a breakpoint on the line and running the project.</span></span>  
    
    ```csharp
        //The following navigates the WebView2API Sample from bing.com to microsoft.com
        e.Url = @"https://www.microsoft.com";
        
        //This exits the edge driver
        e.Quit();
    }
    ```  
    
    :::image type="complex" source="../media/webdriver/microsoft.png" alt-text="运行 WebView2 的 Selenium" lightbox="../media/webdriver/microsoft.png":::
       <span data-ttu-id="1c309-169">运行 WebView2 的 Selenium</span><span class="sxs-lookup"><span data-stu-id="1c309-169">Selenium running WebView2</span></span>  
    :::image-end:::

<span data-ttu-id="1c309-170">恭喜。</span><span class="sxs-lookup"><span data-stu-id="1c309-170">Congratulations.</span></span>  <span data-ttu-id="1c309-171">已使用 Selenium 和 Microsoft Edge Driver 成功自动化 WebView2 项目和驱动 WebView2。</span><span class="sxs-lookup"><span data-stu-id="1c309-171">You have successfully automated a WebView2 project and driven WebView2 using Selenium and Microsoft Edge Driver.</span></span>  

## <a name="see-also"></a><span data-ttu-id="1c309-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c309-172">See also</span></span>  

*   <span data-ttu-id="1c309-173">若要全面了解 API Selenium 如何驱动 WebView2 或 Microsoft Edge \ (Chromium\) ，请导航到[Selenium 文档中的 WebDriver][SeleniumWebdriver]</span><span class="sxs-lookup"><span data-stu-id="1c309-173">For a comprehensive look at how the APIs Selenium drives WebView2 or Microsoft Edge \(Chromium\), navigate to [WebDriver on Selenium documentation][SeleniumWebdriver]</span></span>   
*   <span data-ttu-id="1c309-174">若要了解有关 WebView2 控件以及如何在本机应用中嵌入 Web 内容时使用它，请导航到"Microsoft Edge [WebView2"。][WebViewIndex]</span><span class="sxs-lookup"><span data-stu-id="1c309-174">To learn more about WebView2 control and how to use it when embedding web content in your native app, navigate to [Introduction to Microsoft Edge WebView2][WebViewIndex].</span></span>  
*   <span data-ttu-id="1c309-175">若要了解有关自动执行 Microsoft Edge \ (Chromium\) ，请导航到"使用[WebDriver (Chromium) 实现测试自动化"][WebdriverChromium]</span><span class="sxs-lookup"><span data-stu-id="1c309-175">To learn more about automating Microsoft Edge \(Chromium\), navigate to [Use WebDriver (Chromium) for test automation][WebdriverChromium]</span></span>   
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="1c309-176">与 WebView 团队Microsoft Edge联系</span><span class="sxs-lookup"><span data-stu-id="1c309-176">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[WebdriverChromium]: ../../webdriver-chromium/index.md "将 WebDriver (Chromium) 用于测试自动化|Microsoft Docs"  
[WebdriverChromiumDownloadMicrosoftEdgeDriver]: ../../webdriver-chromium/index.md#download-microsoft-edge-driver "下载Microsoft Edge驱动程序 - 使用 WebDriver (Chromium) 测试自动化|Microsoft Docs"  
[WebViewIndex]: ../index.md "WebView2 Microsoft Edge简介 - Microsoft Docs"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK |Microsoft Docs"  

[MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "下载 WebDriver |Microsoft Edge开发人员"  

[GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample#prerequisites "先决条件 - WebView2 API 示例|GitHub"  

[NugetSeleniumWebdriver400Alpha04]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha04 "Selenium.WebDriver 4.0.0-alpha04 |NuGet库"  

[SeleniumWebdriver]: https://www.selenium.dev/documentation/en/webdriver "WebDriver |Selenium"  

[W3cWebdriver2]: https://www.w3.org/TR/webdriver2 "WebDriver |W3C"  
