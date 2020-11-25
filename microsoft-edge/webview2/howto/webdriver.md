---
description: 使用 Microsoft Edge 驱动程序自动处理和测试 WebView2 控件
title: 通过 Microsoft Edge 驱动程序自动化和测试 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/24/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、edge、ICoreWebView2、ICoreWebView2Controller、Selenium、Microsoft Edge 驱动程序
ms.openlocfilehash: 6f7f84fa88a57e54d7b5143a489d1138c7426d88
ms.sourcegitcommit: 652c345b46aae8b7e3723eb55a01b71a4ef76bf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2020
ms.locfileid: "11191448"
---
# <span data-ttu-id="1547c-104">通过 Microsoft Edge 驱动程序自动化和测试 WebView2</span><span class="sxs-lookup"><span data-stu-id="1547c-104">Automating and testing WebView2 with Microsoft Edge Driver</span></span>  

<span data-ttu-id="1547c-105">由于 WebView2 使用的是 Microsoft Edge \ (Chromium \ ) web 平台，WebView2 开发人员 \ () 可能利用标准 web 工具进行调试和自动化。</span><span class="sxs-lookup"><span data-stu-id="1547c-105">Because WebView2 uses the Microsoft Edge \(Chromium\) web platform, WebView2 developers \(you\) may take advantage of standard web tooling for debugging and automation.</span></span>  <span data-ttu-id="1547c-106">Selenium 是一个这样的工具。</span><span class="sxs-lookup"><span data-stu-id="1547c-106">Selenium is one such tool.</span></span>  <span data-ttu-id="1547c-107">它实现了 W3C [WebDriver][W3cWebdriver2] API。</span><span class="sxs-lookup"><span data-stu-id="1547c-107">It implements the W3C [WebDriver][W3cWebdriver2] API.</span></span>  <span data-ttu-id="1547c-108">你可以使用 Selenium 创建自动测试来模拟用户交互。</span><span class="sxs-lookup"><span data-stu-id="1547c-108">You may use Selenium to create automated tests to simulate user interactions.</span></span>  

<span data-ttu-id="1547c-109">开始执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1547c-109">Get started with the following steps.</span></span>  

## <span data-ttu-id="1547c-110">步骤1：下载 WebView2API 示例</span><span class="sxs-lookup"><span data-stu-id="1547c-110">Step 1: Download WebView2API Sample</span></span>  

<span data-ttu-id="1547c-111">如果您没有现有的 WebView2 项目，请下载 [WebView2API 示例应用][GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]，该示例是最新 WebView2 SDK 的综合示例。</span><span class="sxs-lookup"><span data-stu-id="1547c-111">If you do not have an existing WebView2 project, download the [WebView2API Sample app][GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample], a comprehensive sample of the latest WebView2 SDK.</span></span>  <span data-ttu-id="1547c-112">确保已满足 [WebView2API 示例应用的先决条件][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]。</span><span class="sxs-lookup"><span data-stu-id="1547c-112">Ensure you have satisfied the [prerequisites for the WebView2API Sample app][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites].</span></span> 

<span data-ttu-id="1547c-113">克隆存储库后，在 Visual Studio 中生成项目。</span><span class="sxs-lookup"><span data-stu-id="1547c-113">Once you have cloned the repo, build the project in Visual Studio.</span></span>  <span data-ttu-id="1547c-114">其外观应如下图所示。</span><span class="sxs-lookup"><span data-stu-id="1547c-114">It should look like the following figure.</span></span>  

:::image type="complex" source="../media/webdriver/sample-app.png" alt-text="WebView2API 示例应用" lightbox="../media/webdriver/sample-app.png":::
   <span data-ttu-id="1547c-116">WebView2API 示例应用</span><span class="sxs-lookup"><span data-stu-id="1547c-116">WebView2API Sample app</span></span>  
:::image-end:::  

## <span data-ttu-id="1547c-117">步骤2：安装 Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="1547c-117">Step 2: Install Microsoft Edge Driver</span></span>  

<span data-ttu-id="1547c-118">按照说明安装 [Microsoft Edge 驱动程序][WebdriverChromiumDownloadMicrosoftEdgeDriver] 所需的浏览器特定驱动程序 Selenium 以自动化和测试 WebView2。</span><span class="sxs-lookup"><span data-stu-id="1547c-118">Follow the instructions to install [Microsoft Edge Driver][WebdriverChromiumDownloadMicrosoftEdgeDriver] the browser-specific driver required by Selenium to automate and test WebView2.</span></span>  

<span data-ttu-id="1547c-119">确保 Microsoft Edge 驱动程序版本与你的应用使用的 WebView2 运行时版本相匹配。</span><span class="sxs-lookup"><span data-stu-id="1547c-119">Ensure that the version of Microsoft Edge Driver matches the version of WebView2 Runtime that you app uses.</span></span>  <span data-ttu-id="1547c-120">若要使 WebView2API 示例正常工作，请确保你的 WebView2 运行时版本大于或等于支持的最新 WebView2 SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="1547c-120">For the WebView2API Sample to work, make sure that your version of WebView2 Runtime is greater than or equal than the supported version of the latest WebView2 SDK release.</span></span>  <span data-ttu-id="1547c-121">若要查找最新的 WebView2 SDK 版本，请导航到 " [WebView2 发行说明][Webview2Releasenotes]"。</span><span class="sxs-lookup"><span data-stu-id="1547c-121">To locate the latest WebView2 SDK release, navigate to [WebView2 release notes][Webview2Releasenotes].</span></span>  <span data-ttu-id="1547c-122">若要了解你当前拥有的 WebView2 运行时版本，请导航到 `edge://settings/help` 。</span><span class="sxs-lookup"><span data-stu-id="1547c-122">To find out what version of WebView2 Runtime you currently have, navigate to `edge://settings/help`.</span></span>  

## <span data-ttu-id="1547c-123">步骤3：将 Selenium 添加到 WebView2API 示例</span><span class="sxs-lookup"><span data-stu-id="1547c-123">Step 3: Add Selenium to the WebView2API Sample</span></span>  

<span data-ttu-id="1547c-124">此时，你应该已安装 WebView2 运行时、构建了 WebView2 项目和安装的 Microsoft Edge 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="1547c-124">At this point you should have WebView2 Runtime installed, built a WebView2 project, and installed Microsoft Edge Driver.</span></span>  <span data-ttu-id="1547c-125">现在即可开始使用 Selenium。</span><span class="sxs-lookup"><span data-stu-id="1547c-125">Now, get started using Selenium.</span></span>  

> [!NOTE]
> <span data-ttu-id="1547c-126">Selenium 支持 C \ #、Java、Python、Javascript 和 Ruby。</span><span class="sxs-lookup"><span data-stu-id="1547c-126">Selenium supports C\#, Java, Python, Javascript, and Ruby.</span></span>  <span data-ttu-id="1547c-127">但是，以下指南是使用 C \ # 编写的。</span><span class="sxs-lookup"><span data-stu-id="1547c-127">However, the following guide is written using C\#.</span></span>  

1.  <span data-ttu-id="1547c-128">首先在**Visual Studio**中创建新的**c # .net Framework**项目。</span><span class="sxs-lookup"><span data-stu-id="1547c-128">Start by creating a new **C# .NET Framework** project in **Visual Studio**.</span></span>  <span data-ttu-id="1547c-129">选择右下角的 " **下一步** " 以继续。</span><span class="sxs-lookup"><span data-stu-id="1547c-129">Choose **Next** on the bottom right-hand corner to continue.</span></span>  
    
    :::image type="complex" source="../media/webdriver/new-project.png" alt-text="创建新项目" lightbox="../media/webdriver/new-project.png":::
       <span data-ttu-id="1547c-131">创建新项目</span><span class="sxs-lookup"><span data-stu-id="1547c-131">Create a new project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1547c-132">为你的项目 **命名**，将其保存到你的首选 **位置**，然后选择 " **创建**"。</span><span class="sxs-lookup"><span data-stu-id="1547c-132">Give your project a **name**, save it to your preferred **location**, and choose **Create**.</span></span>  
    
    :::image type="complex" source="../media/webdriver/app-create.png" alt-text="配置新项目" lightbox="../media/webdriver/app-create.png":::
       <span data-ttu-id="1547c-134">配置新项目</span><span class="sxs-lookup"><span data-stu-id="1547c-134">Configure your new project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1547c-135">创建新项目。</span><span class="sxs-lookup"><span data-stu-id="1547c-135">A new project is created.</span></span>  <span data-ttu-id="1547c-136">在本指南中，所有代码都将写入 `Program.cs` 文件。</span><span class="sxs-lookup"><span data-stu-id="1547c-136">In this guide, all code is written to the `Program.cs` file.</span></span>  
    
    :::image type="complex" source="../media/webdriver/start-app.png" alt-text="新建项目" lightbox="../media/webdriver/start-app.png":::
       <span data-ttu-id="1547c-138">新建项目</span><span class="sxs-lookup"><span data-stu-id="1547c-138">New project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1547c-139">现在将 **Selenium** 添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="1547c-139">Now add **Selenium** to the project.</span></span>  <span data-ttu-id="1547c-140">使用 **Selenium WebDriver NuGet 程序包**安装 Selenium。</span><span class="sxs-lookup"><span data-stu-id="1547c-140">Install Selenium using the **Selenium.WebDriver NuGet package**.</span></span>  
    
    <span data-ttu-id="1547c-141">若要下载 **Selenium NuGet 程序包**，请在 **Visual Studio**中，将鼠标悬停在 **Project**上，然后选择 " **管理 NuGet 程序包**"。</span><span class="sxs-lookup"><span data-stu-id="1547c-141">To download the **Selenium.WebDriver NuGet package**, in **Visual Studio**, hover over **Project**, and choose **Manage NuGet Package**.</span></span>  <span data-ttu-id="1547c-142">将显示以下屏幕。</span><span class="sxs-lookup"><span data-stu-id="1547c-142">The following screen should appear.</span></span>  
    
    :::image type="complex" source="../media/webdriver/download-nuget.png" alt-text="下载 NuGet 程序包" lightbox="../media/webdriver/download-nuget.png":::
       <span data-ttu-id="1547c-144">下载 NuGet 程序包</span><span class="sxs-lookup"><span data-stu-id="1547c-144">Download NuGet package</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1547c-145">在搜索栏中输入 **Selenium** ，从结果中选择 **Selenium** ，并确保 " **包括预发布**" 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="1547c-145">Enter **Selenium.WebDriver** in the search bar, choose **Selenium.WebDriver** from the results, and make sure to checkmark the box next to **include pre-release**.</span></span> <span data-ttu-id="1547c-146">在右侧窗口中，确保已将 **版本** 设置为 **安装 4.0.0-alpha04** 或更高版本，然后选择 " **安装**"。</span><span class="sxs-lookup"><span data-stu-id="1547c-146">On the right-hand side window, ensure the **Version** is set to **install 4.0.0-alpha04** or later and choose **Install**.</span></span>  <span data-ttu-id="1547c-147">Nuget 将 Selenium 下载到您的计算机。</span><span class="sxs-lookup"><span data-stu-id="1547c-147">Nuget downloads Selenium to your machine.</span></span>  
    
    <span data-ttu-id="1547c-148">若要了解有关 Selenium WebDriver NuGet 包的详细信息，请导航到 [Selenium WebDriver 4.0.0-alpha04][NugetSeleniumWebdriver400Alpha04]。</span><span class="sxs-lookup"><span data-stu-id="1547c-148">To learn more about the Selenium.WebDriver NuGet package, navigate to [Selenium.WebDriver 4.0.0-alpha04][NugetSeleniumWebdriver400Alpha04].</span></span>  
    
    :::image type="complex" source="../media/webdriver/nuget.png" alt-text="管理 NuGet 程序包" lightbox="../media/webdriver/nuget.png":::
       <span data-ttu-id="1547c-150">管理 NuGet 程序包</span><span class="sxs-lookup"><span data-stu-id="1547c-150">Manage NuGet package</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="1547c-151">`OpenQA.Selenium.Edge`通过添加以下语句来使用： `using OpenQA.Selenium.Edge;` 在文件的开头 `Program.cs` 。</span><span class="sxs-lookup"><span data-stu-id="1547c-151">Use `OpenQA.Selenium.Edge` by adding the following statement:  `using OpenQA.Selenium.Edge;` at the beginning of `Program.cs` file.</span></span>  
    
    ```csharp
    using OpenQA.Selenium.Edge;
    
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    ```  
    
## <span data-ttu-id="1547c-152">步骤4：通过 Selenium 和 Microsoft Edge 驱动程序 WebView2 驱动器</span><span class="sxs-lookup"><span data-stu-id="1547c-152">Step 4: Drive WebView2 with Selenium and Microsoft Edge Driver</span></span>  

1.  <span data-ttu-id="1547c-153">首先， `EdgeOptions` 通过复制以下代码片段来创建对象。</span><span class="sxs-lookup"><span data-stu-id="1547c-153">First, create the `EdgeOptions` object, by copying the following code snippet.</span></span>  
    
    ```csharp
    static void Main(string[] args)
    {
        // EdgeOptions() requires using OpenQA.Selenium.Edge
        // Construct EdgeOptions with is_legacy = false and the string "webview2"
        EdgeOptions edgeOptions = new EdgeOptions(false, "webview2");
    ```  
    
    <span data-ttu-id="1547c-154">该 `EdgeOptions` 对象采用以下两个参数。</span><span class="sxs-lookup"><span data-stu-id="1547c-154">The `EdgeOptions` object takes in the following two parameters.</span></span>  
    
    | <span data-ttu-id="1547c-155">参数</span><span class="sxs-lookup"><span data-stu-id="1547c-155">Parameter</span></span> | <span data-ttu-id="1547c-156">详细信息</span><span class="sxs-lookup"><span data-stu-id="1547c-156">Details</span></span> |    
    |:--- |:--- |  
    | `is_legacy` | <span data-ttu-id="1547c-157">设置为 `false` ，告诉 Selenium 你正在推动新的基于 Chromium 的 Microsoft Edge 浏览器。</span><span class="sxs-lookup"><span data-stu-id="1547c-157">Set to `false`, which tells Selenium that you are driving the new Chromium-based Microsoft Edge browser.</span></span> |  
    | `"webview2"` | <span data-ttu-id="1547c-158">告诉 Selenium 你正在推动 WebView2 的字符串。</span><span class="sxs-lookup"><span data-stu-id="1547c-158">A string that tells Selenium you are driving WebView2.</span></span> |  
    
1.  <span data-ttu-id="1547c-159">下一步，设置 `edgeOptions.BinaryLocation` 为 WebView2 project 运行时的文件路径，创建一个名为的字符串， `msedgedriverDir` 该字符串提供指向安装 [Microsoft edge 驱动程序][MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads]的位置的文件路径，并创建一个名为的字符串， `msedgedriverExe` 以存储 microsoft edge 驱动程序运行时的名称。</span><span class="sxs-lookup"><span data-stu-id="1547c-159">Next, set `edgeOptions.BinaryLocation` to the file path of your WebView2 project runtime, create a string named `msedgedriverDir` that provides the file path to where you installed [Microsoft Edge Driver][MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads], and create a string named `msedgedriverExe` to store the name of the Microsoft Edge Driver runtime.</span></span>  <span data-ttu-id="1547c-160">默认情况下，运行时命名 `msedgedriver.exe` 。</span><span class="sxs-lookup"><span data-stu-id="1547c-160">By default, the runtime is named `msedgedriver.exe`.</span></span> <span data-ttu-id="1547c-161">使用这两个字符串构造对象，如下 `EdgeDriverService` 所示。</span><span class="sxs-lookup"><span data-stu-id="1547c-161">Use these two strings to construct the `EdgeDriverService` object as shown below.</span></span>  <span data-ttu-id="1547c-162">最后， `EdgeDriver` 使用 and 创建对象 `EdgeDriverService` `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="1547c-162">Finally, create the `EdgeDriver` object using `EdgeDriverService` and `EdgeOptions`.</span></span>  
    
    <span data-ttu-id="1547c-163">你可以将以下代码复制并粘贴到下面 `edgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="1547c-163">You may copy and paste the following code underneath `edgeOptions`.</span></span>  <span data-ttu-id="1547c-164">确保在你的计算机上为你的项目运行时和 Microsoft Edge 驱动程序运行时指定正确的文件路径。</span><span class="sxs-lookup"><span data-stu-id="1547c-164">Ensure you specify the correct file paths to your project runtime and the Microsoft Edge Driver runtime on your machine.</span></span>  
    
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
    
3.  <span data-ttu-id="1547c-165">现在， `EdgeDriver` 配置为在你的项目中驱动 WebView2。</span><span class="sxs-lookup"><span data-stu-id="1547c-165">Now, `EdgeDriver` is configured to drive the WebView2 in your project.</span></span>  <span data-ttu-id="1547c-166">例如，如果你使用的是 **WebView2API 示例**，则可以 `https://microsoft.com` 通过运行命令导航到 `e.Url = @"https://www.microsoft.com";` 。</span><span class="sxs-lookup"><span data-stu-id="1547c-166">For example, if you are using the **WebView2API Sample**, you may navigate to `https://microsoft.com` by running the `e.Url = @"https://www.microsoft.com";` command.</span></span>  <span data-ttu-id="1547c-167">通过在线路上设置断点并运行项目来验证 Selenium 驱动器 WebView2。</span><span class="sxs-lookup"><span data-stu-id="1547c-167">Verify the Selenium drive WebView2 by setting a breakpoint on the line and running the project.</span></span>  
    
    ```csharp
        //The following navigates the WebView2API Sample from bing.com to microsoft.com
        e.Url = @"https://www.microsoft.com";
        
        //This exits the edge driver
        e.Quit();
    }
    ```  
    
    :::image type="complex" source="../media/webdriver/microsoft.png" alt-text="Selenium 运行 WebView2" lightbox="../media/webdriver/microsoft.png":::
       <span data-ttu-id="1547c-169">Selenium 运行 WebView2</span><span class="sxs-lookup"><span data-stu-id="1547c-169">Selenium running WebView2</span></span>  
    :::image-end:::

<span data-ttu-id="1547c-170">得到.</span><span class="sxs-lookup"><span data-stu-id="1547c-170">Congratulations.</span></span>  <span data-ttu-id="1547c-171">你已成功使用 Selenium 和 Microsoft Edge 驱动程序成功自动化了 WebView2 项目和驱动的 WebView2。</span><span class="sxs-lookup"><span data-stu-id="1547c-171">You have successfully automated a WebView2 project and driven WebView2 using Selenium and Microsoft Edge Driver.</span></span>  

## <span data-ttu-id="1547c-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1547c-172">See also</span></span>  

*   <span data-ttu-id="1547c-173">若要全面了解 Api 如何 Selenium 驱动器 WebView2 或 Microsoft Edge \ (Chromium \ ) ，请导航到 [Selenium 文档上的 WebDriver][SeleniumWebdriver]</span><span class="sxs-lookup"><span data-stu-id="1547c-173">For a comprehensive look at how the APIs Selenium drives WebView2 or Microsoft Edge \(Chromium\), navigate to [WebDriver on Selenium documentation][SeleniumWebdriver]</span></span>   
*   <span data-ttu-id="1547c-174">若要了解有关 WebView2 控件以及如何在你的本机应用中嵌入 web 内容时使用它的详细信息，请导航到 [Microsoft Edge WebView2 简介][WebViewIndex]。</span><span class="sxs-lookup"><span data-stu-id="1547c-174">To learn more about WebView2 control and how to use it when embedding web content in your native app, navigate to [Introduction to Microsoft Edge WebView2][WebViewIndex].</span></span>  
*   <span data-ttu-id="1547c-175">若要了解有关自动化 Microsoft Edge \ (Chromium \ ) 的详细信息，请导航到 [使用 WebDriver (Chromium) 进行测试自动化][WebdriverChromium]</span><span class="sxs-lookup"><span data-stu-id="1547c-175">To learn more about automating Microsoft Edge \(Chromium\), navigate to [Use WebDriver (Chromium) for test automation][WebdriverChromium]</span></span>   
    
## <span data-ttu-id="1547c-176">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="1547c-176">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[WebdriverChromium]: ../../webdriver-chromium.md "使用 WebDriver (Chromium) 进行测试自动化 |Microsoft 文档"  
[WebdriverChromiumDownloadMicrosoftEdgeDriver]: ../../webdriver-chromium.md#download-microsoft-edge-driver "下载 Microsoft Edge 驱动程序-使用 WebDriver (Chromium) 测试自动化 |Microsoft 文档"  
[WebViewIndex]: ../index.md "Microsoft Edge WebView2 简介-Microsoft 文档"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "下载 WebDriver |Microsoft Edge 开发人员"  

[GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API Sample-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample#prerequisites "先决条件-WebView2 API 示例 |GitHub"  

[NugetSeleniumWebdriver400Alpha04]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha04 "Selenium WebDriver 4.0.0-alpha04 |NuGet 库"  

[SeleniumWebdriver]: https://www.selenium.dev/documentation/en/webdriver "WebDriver |Selenium"  

[W3cWebdriver2]: https://www.w3.org/TR/webdriver2 "WebDriver |W3C"  
