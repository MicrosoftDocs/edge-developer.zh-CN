---
description: 使用 Microsoft Edge 驱动程序自动化和测试 WebView2 控件
title: 使用 Microsoft Edge 驱动程序自动化和测试 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、edge、ICoreWebView2、ICoreWebView2Controller、Selenium、Microsoft Edge 驱动程序
ms.openlocfilehash: c23d639582d4ce550406cf955c96171167bde7c8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11470828"
---
# <a name="automating-and-testing-webview2-with-microsoft-edge-driver"></a>使用 Microsoft Edge 驱动程序自动执行和测试 WebView2  

由于 WebView2 使用 Microsoft Edge \ (Chromium\) Web 平台，因此 WebView2 开发人员 \ (you\) 可以利用标准 Web 工具进行调试和自动化。  Selenium 是此类工具之一。  它实现 W3C [WebDriver][W3cWebdriver2] API。  可以使用 Selenium 创建自动测试来模拟用户交互。  

开始执行以下步骤。  

## <a name="step-1--download-webview2api-sample"></a>步骤 1：下载 WebView2API 示例  

如果你没有现有的 WebView2 项目，请下载 [WebView2API 示例][GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]应用，这是最新的 WebView2 SDK 的全面示例。  确保你已满足 [WebView2API 示例应用的先决条件][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]。  

克隆存储库后，在"文件"中生成Visual Studio。  它应如下图所示。  

:::image type="complex" source="../media/webdriver/sample-app.png" alt-text="WebView2API 示例应用" lightbox="../media/webdriver/sample-app.png":::
   WebView2API 示例应用  
:::image-end:::  

## <a name="step-2--install-microsoft-edge-driver"></a>步骤 2：安装 Microsoft Edge 驱动程序  

按照说明安装 [Microsoft Edge 驱动程序][WebdriverChromiumDownloadMicrosoftEdgeDriver] Selenium 所需的特定于浏览器的驱动程序，以自动化和测试 WebView2。  

确保 Microsoft Edge 驱动程序的版本与应用使用的 WebView2 运行时版本匹配。  若要使 WebView2API 示例正常工作，请确保你的 WebView2 运行时版本大于或等于最新 WebView2 SDK 版本的受支持版本。  若要查找最新的 WebView2 SDK 版本，请导航到 [WebView2 发行说明][Webview2Releasenotes]。  若要了解当前具有的 WebView2 运行时版本，请导航到 `edge://settings/help` 。  

## <a name="step-3--add-selenium-to-the-webview2api-sample"></a>步骤 3：将 Selenium 添加到 WebView2API 示例  

此时，你应该已安装 WebView2 运行时，生成了 WebView2 项目，并安装了 Microsoft Edge 驱动程序。  现在，开始使用 Selenium。  

> [!NOTE]
> Selenium 支持 C\#、Java、Python、Javascript 和 Ruby。  但是，以下指南是使用 C\# 编写的。  

1.  首先，在 **Visual Studio** 中新建C# .NET Framework **项目**。  选择 **右** 下角的"下一步"继续。  
    
    :::image type="complex" source="../media/webdriver/new-project.png" alt-text="创建新项目" lightbox="../media/webdriver/new-project.png":::
       创建新项目  
    :::image-end:::  
    
1.  为项目命名 **，** 将其保存到首选**位置**，然后选择"创建 **"。**  
    
    :::image type="complex" source="../media/webdriver/app-create.png" alt-text="配置新项目" lightbox="../media/webdriver/app-create.png":::
       配置新项目  
    :::image-end:::  
    
1.  将创建一个新项目。  在本指南中，所有代码都写入 `Program.cs` 文件。  
    
    :::image type="complex" source="../media/webdriver/start-app.png" alt-text="新建项目" lightbox="../media/webdriver/start-app.png":::
       新建项目  
    :::image-end:::  
    
1.  现在，将 **Selenium** 添加到项目中。  使用 **Selenium.WebDriver NuGet**程序包安装 Selenium。  
    
    若要下载**Selenium.WebDriver NuGet**程序包 **，Visual Studio，将**鼠标悬停在**Project**上，然后选择"**管理 NuGet 程序包"。**  应显示以下屏幕。  
    
    :::image type="complex" source="../media/webdriver/download-nuget.png" alt-text="下载 NuGet 包" lightbox="../media/webdriver/download-nuget.png":::
       下载 NuGet 包  
    :::image-end:::  
    
1.  在 `Selenium.WebDriver` 搜索栏中输入，从结果中选择 **Selenium.WebDriver，** 并确保选中复选框以包含 **预发布**。  在右侧窗口中，确保"**版本**"设置为安装**4.0.0-alpha04**或更高版本，然后选择"**安装"。**  NuGet 将 Selenium 下载到计算机。  
    
    若要了解有关 Selenium.WebDriver NuGet 程序包的信息，请导航到[Selenium.WebDriver 4.0.0-alpha04。][NugetSeleniumWebdriver400Alpha04]  
    
    :::image type="complex" source="../media/webdriver/nuget.png" alt-text="管理 NuGet 包" lightbox="../media/webdriver/nuget.png":::
       管理 NuGet 包  
    :::image-end:::  
    
1.  `OpenQA.Selenium.Edge`通过添加以下语句来使用： `using OpenQA.Selenium.Edge;` 在文件的 `Program.cs` 开头。  
    
    ```csharp
    using OpenQA.Selenium.Edge;
    
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    ```  
    
## <a name="step-4-drive-webview2-with-selenium-and-microsoft-edge-driver"></a>步骤 4：使用 Selenium 和 Microsoft Edge 驱动程序驱动 WebView2  

1.  首先，通过 `EdgeOptions` 复制以下代码段创建对象。  
    
    ```csharp
    static void Main(string[] args)
    {
        // EdgeOptions() requires using OpenQA.Selenium.Edge
        // Construct EdgeOptions with is_legacy = false and the string "webview2"
        EdgeOptions edgeOptions = new EdgeOptions(false, "webview2");
    ```  
    
    `EdgeOptions`对象采用以下两个参数。  
    
    | 参数 | 详细信息 |    
    |:--- |:--- |  
    | `is_legacy` | 设置为 `false` ，这将告知 Selenium 你正在驱动新的基于 Chromium 的 Microsoft Edge 浏览器。 |  
    | `"webview2"` | 一个字符串，告知 Selenium 你正在驱动 WebView2。 |  
    
1.  接下来，设置为 WebView2 项目运行时的文件路径，创建一个名为 的字符串，该字符串提供安装 Microsoft Edge 驱动程序的文件路径，并创建一个名为 的字符串来存储 `edgeOptions.BinaryLocation` `msedgedriverDir` Microsoft Edge[][MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads] `msedgedriverExe` 驱动程序运行时的名称。  默认情况下，运行时命名为 `msedgedriver.exe` 。 使用以下两个字符串构造 `EdgeDriverService` 对象，如下所示。  最后，使用 `EdgeDriver` 和 `EdgeDriverService` 创建对象 `EdgeOptions` 。  
    
    你可以复制并粘贴下面的代码 `edgeOptions` 。  确保指定项目运行时和计算机上 Microsoft Edge 驱动程序运行时的正确文件路径。  
    
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
    
3.  现在 `EdgeDriver` ，配置为在项目中驱动 WebView2。  例如，如果你使用的是 **WebView2API 示例**，可以通过运行 命令 `https://microsoft.com` 导航 `e.Url = @"https://www.microsoft.com";` 到 。  通过设置线路上的断点并运行项目来验证 Selenium 驱动器 WebView2。  
    
    ```csharp
        //The following navigates the WebView2API Sample from bing.com to microsoft.com
        e.Url = @"https://www.microsoft.com";
        
        //This exits the edge driver
        e.Quit();
    }
    ```  
    
    :::image type="complex" source="../media/webdriver/microsoft.png" alt-text="运行 WebView2 的 Selenium" lightbox="../media/webdriver/microsoft.png":::
       运行 WebView2 的 Selenium  
    :::image-end:::

恭喜。  你已成功使用 Selenium 和 Microsoft Edge 驱动程序自动化 WebView2 项目和驱动 WebView2。  

## <a name="see-also"></a>另请参阅  

*   有关 API Selenium 如何驱动 WebView2 或 Microsoft Edge \ (Chromium\) 的全面信息，请导航到 Selenium 文档中的 [WebDriver][SeleniumWebdriver]   
*   若要详细了解 WebView2 控件以及如何在本机应用中嵌入 Web 内容时使用它，请导航到 [Microsoft Edge WebView2 简介][WebViewIndex]。  
*   若要了解有关自动执行 Microsoft Edge \ (Chromium\) ，请导航到"使用 [WebDriver (Chromium) 实现测试自动化"][WebdriverChromium]   
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>与 Microsoft Edge WebView 团队联系  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[WebdriverChromium]: ../../webdriver-chromium/index.md "使用 WebDriver (Chromium) 测试自动化|Microsoft Docs"  
[WebdriverChromiumDownloadMicrosoftEdgeDriver]: ../../webdriver-chromium/index.md#download-microsoft-edge-driver "下载 Microsoft Edge 驱动程序 - 使用 WebDriver (Chromium) 测试自动化|Microsoft Docs"  
[WebViewIndex]: ../index.md "Microsoft Edge WebView2 简介 - Microsoft Docs"  
[Webview2Releasenotes]: ../releasenotes.md "WebView2 SDK |Microsoft Docs"  

[MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads]: https://developer.microsoft.com/microsoft-edge/tools/webdriver#downloads "下载 WebDriver |Microsoft Edge 开发人员"  

[GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample "WebView2 API 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]: https://github.com/MicrosoftEdge/WebView2Samples/tree/master/SampleApps/WebView2APISample#prerequisites "先决条件 - WebView2 API 示例|GitHub"  

[NugetSeleniumWebdriver400Alpha04]: https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha04 "Selenium.WebDriver 4.0.0-alpha04 |NuGet 库"  

[SeleniumWebdriver]: https://www.selenium.dev/documentation/en/webdriver "WebDriver |Selenium"  

[W3cWebdriver2]: https://www.w3.org/TR/webdriver2 "WebDriver |W3C"  
