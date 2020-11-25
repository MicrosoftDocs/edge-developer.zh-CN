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
# 通过 Microsoft Edge 驱动程序自动化和测试 WebView2  

由于 WebView2 使用的是 Microsoft Edge \ (Chromium \ ) web 平台，WebView2 开发人员 \ () 可能利用标准 web 工具进行调试和自动化。  Selenium 是一个这样的工具。  它实现了 W3C [WebDriver][W3cWebdriver2] API。  你可以使用 Selenium 创建自动测试来模拟用户交互。  

开始执行以下步骤。  

## 步骤1：下载 WebView2API 示例  

如果您没有现有的 WebView2 项目，请下载 [WebView2API 示例应用][GithubMicrosoftedgewebview2samplesSampleappsWebview2apisample]，该示例是最新 WebView2 SDK 的综合示例。  确保已满足 [WebView2API 示例应用的先决条件][GithubMicrosoftedgeWebview2samplesSampleappsWebview2apisamplePrerequisites]。 

克隆存储库后，在 Visual Studio 中生成项目。  其外观应如下图所示。  

:::image type="complex" source="../media/webdriver/sample-app.png" alt-text="WebView2API 示例应用" lightbox="../media/webdriver/sample-app.png":::
   WebView2API 示例应用  
:::image-end:::  

## 步骤2：安装 Microsoft Edge 驱动程序  

按照说明安装 [Microsoft Edge 驱动程序][WebdriverChromiumDownloadMicrosoftEdgeDriver] 所需的浏览器特定驱动程序 Selenium 以自动化和测试 WebView2。  

确保 Microsoft Edge 驱动程序版本与你的应用使用的 WebView2 运行时版本相匹配。  若要使 WebView2API 示例正常工作，请确保你的 WebView2 运行时版本大于或等于支持的最新 WebView2 SDK 版本。  若要查找最新的 WebView2 SDK 版本，请导航到 " [WebView2 发行说明][Webview2Releasenotes]"。  若要了解你当前拥有的 WebView2 运行时版本，请导航到 `edge://settings/help` 。  

## 步骤3：将 Selenium 添加到 WebView2API 示例  

此时，你应该已安装 WebView2 运行时、构建了 WebView2 项目和安装的 Microsoft Edge 驱动程序。  现在即可开始使用 Selenium。  

> [!NOTE]
> Selenium 支持 C \ #、Java、Python、Javascript 和 Ruby。  但是，以下指南是使用 C \ # 编写的。  

1.  首先在**Visual Studio**中创建新的**c # .net Framework**项目。  选择右下角的 " **下一步** " 以继续。  
    
    :::image type="complex" source="../media/webdriver/new-project.png" alt-text="创建新项目" lightbox="../media/webdriver/new-project.png":::
       创建新项目  
    :::image-end:::  
    
1.  为你的项目 **命名**，将其保存到你的首选 **位置**，然后选择 " **创建**"。  
    
    :::image type="complex" source="../media/webdriver/app-create.png" alt-text="配置新项目" lightbox="../media/webdriver/app-create.png":::
       配置新项目  
    :::image-end:::  
    
1.  创建新项目。  在本指南中，所有代码都将写入 `Program.cs` 文件。  
    
    :::image type="complex" source="../media/webdriver/start-app.png" alt-text="新建项目" lightbox="../media/webdriver/start-app.png":::
       新建项目  
    :::image-end:::  
    
1.  现在将 **Selenium** 添加到项目中。  使用 **Selenium WebDriver NuGet 程序包**安装 Selenium。  
    
    若要下载 **Selenium NuGet 程序包**，请在 **Visual Studio**中，将鼠标悬停在 **Project**上，然后选择 " **管理 NuGet 程序包**"。  将显示以下屏幕。  
    
    :::image type="complex" source="../media/webdriver/download-nuget.png" alt-text="下载 NuGet 程序包" lightbox="../media/webdriver/download-nuget.png":::
       下载 NuGet 程序包  
    :::image-end:::  
    
1.  在搜索栏中输入 **Selenium** ，从结果中选择 **Selenium** ，并确保 " **包括预发布**" 旁边的复选框。 在右侧窗口中，确保已将 **版本** 设置为 **安装 4.0.0-alpha04** 或更高版本，然后选择 " **安装**"。  Nuget 将 Selenium 下载到您的计算机。  
    
    若要了解有关 Selenium WebDriver NuGet 包的详细信息，请导航到 [Selenium WebDriver 4.0.0-alpha04][NugetSeleniumWebdriver400Alpha04]。  
    
    :::image type="complex" source="../media/webdriver/nuget.png" alt-text="管理 NuGet 程序包" lightbox="../media/webdriver/nuget.png":::
       管理 NuGet 程序包  
    :::image-end:::  
    
1.  `OpenQA.Selenium.Edge`通过添加以下语句来使用： `using OpenQA.Selenium.Edge;` 在文件的开头 `Program.cs` 。  
    
    ```csharp
    using OpenQA.Selenium.Edge;
    
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    ```  
    
## 步骤4：通过 Selenium 和 Microsoft Edge 驱动程序 WebView2 驱动器  

1.  首先， `EdgeOptions` 通过复制以下代码片段来创建对象。  
    
    ```csharp
    static void Main(string[] args)
    {
        // EdgeOptions() requires using OpenQA.Selenium.Edge
        // Construct EdgeOptions with is_legacy = false and the string "webview2"
        EdgeOptions edgeOptions = new EdgeOptions(false, "webview2");
    ```  
    
    该 `EdgeOptions` 对象采用以下两个参数。  
    
    | 参数 | 详细信息 |    
    |:--- |:--- |  
    | `is_legacy` | 设置为 `false` ，告诉 Selenium 你正在推动新的基于 Chromium 的 Microsoft Edge 浏览器。 |  
    | `"webview2"` | 告诉 Selenium 你正在推动 WebView2 的字符串。 |  
    
1.  下一步，设置 `edgeOptions.BinaryLocation` 为 WebView2 project 运行时的文件路径，创建一个名为的字符串， `msedgedriverDir` 该字符串提供指向安装 [Microsoft edge 驱动程序][MicrosoftDeveloperMicrosoftEdgeWebDriverDownloads]的位置的文件路径，并创建一个名为的字符串， `msedgedriverExe` 以存储 microsoft edge 驱动程序运行时的名称。  默认情况下，运行时命名 `msedgedriver.exe` 。 使用这两个字符串构造对象，如下 `EdgeDriverService` 所示。  最后， `EdgeDriver` 使用 and 创建对象 `EdgeDriverService` `EdgeOptions` 。  
    
    你可以将以下代码复制并粘贴到下面 `edgeOptions` 。  确保在你的计算机上为你的项目运行时和 Microsoft Edge 驱动程序运行时指定正确的文件路径。  
    
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
    
3.  现在， `EdgeDriver` 配置为在你的项目中驱动 WebView2。  例如，如果你使用的是 **WebView2API 示例**，则可以 `https://microsoft.com` 通过运行命令导航到 `e.Url = @"https://www.microsoft.com";` 。  通过在线路上设置断点并运行项目来验证 Selenium 驱动器 WebView2。  
    
    ```csharp
        //The following navigates the WebView2API Sample from bing.com to microsoft.com
        e.Url = @"https://www.microsoft.com";
        
        //This exits the edge driver
        e.Quit();
    }
    ```  
    
    :::image type="complex" source="../media/webdriver/microsoft.png" alt-text="Selenium 运行 WebView2" lightbox="../media/webdriver/microsoft.png":::
       Selenium 运行 WebView2  
    :::image-end:::

得到.  你已成功使用 Selenium 和 Microsoft Edge 驱动程序成功自动化了 WebView2 项目和驱动的 WebView2。  

## 另请参阅  

*   若要全面了解 Api 如何 Selenium 驱动器 WebView2 或 Microsoft Edge \ (Chromium \ ) ，请导航到 [Selenium 文档上的 WebDriver][SeleniumWebdriver]   
*   若要了解有关 WebView2 控件以及如何在你的本机应用中嵌入 web 内容时使用它的详细信息，请导航到 [Microsoft Edge WebView2 简介][WebViewIndex]。  
*   若要了解有关自动化 Microsoft Edge \ (Chromium \ ) 的详细信息，请导航到 [使用 WebDriver (Chromium) 进行测试自动化][WebdriverChromium]   
    
## 与 Microsoft Edge Web 上的 Web Edge 团队取得联系  

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
