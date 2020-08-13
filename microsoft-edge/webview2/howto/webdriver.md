---
description: 使用 Microsoft Edge 驱动程序自动处理和测试 WebView2 控件
title: 通过 Microsoft Edge 驱动程序自动化和测试 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/10/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、edge、ICoreWebView2、ICoreWebView2Controller、Selenium、Microsoft Edge 驱动程序
ms.openlocfilehash: a91c01d1ad765dae45061e382daedc2295d70bb8
ms.sourcegitcommit: 4bc904c5d54347185f275bd76441975be471c320
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "10926442"
---
# 通过 Microsoft Edge 驱动程序自动化和测试 WebView2

由于 WebView2 利用 Chromium web 平台，因此 WebView2 开发人员可以利用标准的 web 工具进行调试和自动化。 一个此类工具是 Selenium，它实现了 W3C [WebDriver](https://www.w3.org/TR/webdriver2/) API，可用于创建模拟用户交互的自动测试。

下面介绍了如何开始使用：

## 步骤1：下载 WebView2API 示例

如果您没有现有的 WebView2 项目，请下载我们的 [WebView2API 示例应用程序](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample#webview2-api-sample)，该示例是最新的 WebView2 SDK 的综合示例。 请仔细检查是否已满足这些 [先决条件](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample#prerequisites)。

克隆存储库后，在 Visual Studio 中生成项目。 其外观应如下所示：

![替换文字](../media/webdriver/sample-app.png)

## 步骤2：安装 Microsoft Edge 驱动程序

按照说明安装 [Microsoft Edge 驱动程序](https://docs.microsoft.com/microsoft-edge/webdriver-chromium#download-microsoft-edge-driver) 所需的浏览器特定驱动程序 Selenium 以自动化和测试 WebView2。

请务必确保 Microsoft Edge 驱动程序版本与应用程序使用的 Microsoft Edge 版本相匹配。 若要使 WebView2API 示例正常工作，请确保你的 Microsoft Edge 版本大于或等于我们的 [发行说明中](https://docs.microsoft.com/microsoft-edge/hosting/webview2/releasenotes)找到的最新 SDK 版本的受支持版本。 若要了解您当前拥有的 Microsoft Edge 版本，请 `edge://settings/help` 在浏览器中加载。

## 步骤3：将 Selenium 添加到 WebView2API 示例

此时，你应该已安装 Microsoft Edge，构建一个 WebView2 项目，并安装了 Microsoft Edge 驱动程序。 现在，让我们开始使用 Selenium。

> [!NOTE]
> Selenium 支持 c #、Java、Python、Javascript 和 Ruby。 但是，本指南将位于 c # 中。

1. 首先在**Visual Studio**中创建新的**c # .net Framework**项目。 单击右下角的 " **下一步** " 以继续。

![替换文字](../media/webdriver/new-project.png)

2. 为你的项目 **命名**，将其保存到你的首选 **位置**，然后单击 " **创建**"。

![替换文字](../media/webdriver/app-create.png)

3. 将创建一个新项目。 在本指南中，将在 **Program.cs** 文件中写入所有代码。

![替换文字](../media/webdriver/start-app.png)

4. 现在，我们将 **Selenium** 添加到项目中。 你可以通过 **Selenium WebDriver NuGet 程序包**安装 Selenium。

若要下载 **Selenium NuGet 程序包**，请在 **Visual Studio**中，将鼠标悬停在 **Project** 上，然后选择 " **管理 NuGet 程序包**"。 将显示以下屏幕：

![替换文字](../media/webdriver/download-nuget.png)

5. 在搜索栏中输入 **Selenium** ，单击结果中的 **Selenium WebDriver** ，并确保 " **包括预发布**" 旁边的复选框。 在右侧窗口中，确保已将 **版本** 设置为 **安装 4.0.0-alpha04** 或更高版本，然后单击 " **安装**"。 Nuget 将 Selenium 下载到您的计算机。

[了解有关 Selenium WebDriver NuGet 程序包的详细信息。](https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha04)

![替换文字](../media/webdriver/nuget.png)

6. 通过在 Program.cs 的开头添加以下语句，使用**OpenQA： Selenium** ```using OpenQA.Selenium.Edge;``` **Program.cs**

```csharp
using OpenQA.Selenium.Edge;

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 步骤4：通过 Selenium 和 Microsoft EdgeDriver 驱动器 WebView2

1. 首先， `EdgeOptions` 通过复制以下代码来创建对象：

```csharp
static void Main(string[] args)
{
    // EdgeOptions() requires using OpenQA.Selenium.Edge
    // Construct EdgeOptions with is_legacy = false and the string "webview2"
    EdgeOptions edgeOptions = new EdgeOptions(false, "webview2");
```

该 `EdgeOptions` 对象采用两个参数：
\
    **实参**
    1. `is_legacy`：设置为 `false` ，告诉 Selenium 你正在推动新的基于 Chromium 的 Microsoft Edge 浏览器。
    2. `"webview2"`：告诉 Selenium 您正在推动**WebView2**的字符串

2. 下一步，设置 `edgeOptions.BinaryLocation` 为 WebView2 项目可执行文件的文件路径，创建一个字符串， `msedgedriverDir` 该字符串提供了安装 [Microsoft edge 驱动程序](https://developer.microsoft.com/microsoft-edge/tools/webdriver/#downloads)的位置的文件路径，并创建一个字符串， `msedgedriverExe` 用于存储 microsoft edge 驱动程序可执行文件的名称。 默认情况下，将调用可执行文件 `"msedgedriver.exe"` 。 使用这两个字符串构造对象，如下 `EdgeDriverService` 所示。 最后， `EdgeDriver` 使用 and 创建对象 `EdgeDriverService` `EdgeOptions` 。

你可以将以下代码复制并粘贴到下面 `edgeOptions` 。 请确保为你的计算机上的项目可执行文件和 Microsoft Edge 驱动程序的可执行文件指定正确的文件路径。

```csharp
    //Set the BinaryLocation to the filepath of the WebView2API Sample's executable
    edgeOptions.BinaryLocation = @"C:\path\to\your\webview2\project.exe";

    //Set msedgedriverDir to the filepath of the directory housing msedgedriver.exe
    string msedgedriverDir = @"C:\path\to\your\msededriver.exe's\directory";

    //Set msedgedriverExe to the name of the Edge Driver. By default it is:
    string msedgedriverExe = @"msedgedriver.exe";

    // Construct EdgeDriverService with is_legacy = false  
    EdgeDriverService service = EdgeDriverService.CreateDefaultService(msedgedriverDir, msedgedriverExe, false);

    EdgeDriver e = new EdgeDriver(service, edgeOptions);
```

3. 现在， **EdgeDriver** 被配置为驱动你的项目中的 **WebView2** 。 例如，如果你使用的是 **WebView2API 示例**，则可以通过调用 **导航** 到 <https://microsoft.com> ```e.Url = @"https://www.microsoft.com";``` 。 你可以通过在此行上设置断点并运行项目来观看 **Selenium** drive **WebView2** 。

```csharp
    //The following will Navigate the WebView2API Sample from bing.com to microsoft.com
    e.Url = @"https://www.microsoft.com";

    //This exits the edge driver
    e.Quit();
}
```

![替换文字](../media/webdriver/microsoft.png)

恭喜你！ 你已成功使用 Selenium 和 Microsoft Edge 驱动程序成功自动化了 WebView2 项目和驱动的 WebView2。

## 后续步骤

若要了解详细信息：

- 查看 [Selenium 的文档](https://www.selenium.dev/documentation/en/webdriver/) 以全面了解 Selenium 的 api 可用于推动 WebView2 或 Microsoft Edge (Chromium) 
- 了解有关 [WebView2](https://docs.microsoft.com/microsoft-edge/hosting/webview2) 控件的详细信息，以及如何在你的本机应用中嵌入 web 内容时使用它
- 查看 [Microsoft Edge 驱动程序的文档](https://docs.microsoft.com/microsoft-edge/webdriver-chromium) ，了解有关自动化 microsoft Edge (Chromium 的详细信息) 

## 与 Microsoft Edge Web 上的 Web Edge 团队取得联系  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  
