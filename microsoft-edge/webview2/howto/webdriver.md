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
# <span data-ttu-id="22de4-104">通过 Microsoft Edge 驱动程序自动化和测试 WebView2</span><span class="sxs-lookup"><span data-stu-id="22de4-104">Automating and testing WebView2 with Microsoft Edge Driver</span></span>

<span data-ttu-id="22de4-105">由于 WebView2 利用 Chromium web 平台，因此 WebView2 开发人员可以利用标准的 web 工具进行调试和自动化。</span><span class="sxs-lookup"><span data-stu-id="22de4-105">Because WebView2 utilizes the Chromium web platform, WebView2 developers can take advantage of standard web tooling for debugging and automation.</span></span> <span data-ttu-id="22de4-106">一个此类工具是 Selenium，它实现了 W3C [WebDriver](https://www.w3.org/TR/webdriver2/) API，可用于创建模拟用户交互的自动测试。</span><span class="sxs-lookup"><span data-stu-id="22de4-106">One such tool is Selenium, which implements the W3C [WebDriver](https://www.w3.org/TR/webdriver2/) API, which can be used to create automated tests that simulate user interactions.</span></span>

<span data-ttu-id="22de4-107">下面介绍了如何开始使用：</span><span class="sxs-lookup"><span data-stu-id="22de4-107">Here's how to get started:</span></span>

## <span data-ttu-id="22de4-108">步骤1：下载 WebView2API 示例</span><span class="sxs-lookup"><span data-stu-id="22de4-108">Step 1: Download WebView2API Sample</span></span>

<span data-ttu-id="22de4-109">如果您没有现有的 WebView2 项目，请下载我们的 [WebView2API 示例应用程序](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample#webview2-api-sample)，该示例是最新的 WebView2 SDK 的综合示例。</span><span class="sxs-lookup"><span data-stu-id="22de4-109">If you do not have an existing WebView2 project, download our [WebView2API Sample application](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample#webview2-api-sample), a comprehensive sample of the latest WebView2 SDK.</span></span> <span data-ttu-id="22de4-110">请仔细检查是否已满足这些 [先决条件](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="22de4-110">Please double check that you have satisfied these [prerequisites](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample#prerequisites).</span></span>

<span data-ttu-id="22de4-111">克隆存储库后，在 Visual Studio 中生成项目。</span><span class="sxs-lookup"><span data-stu-id="22de4-111">Once you have cloned the repo, build the project in Visual Studio.</span></span> <span data-ttu-id="22de4-112">其外观应如下所示：</span><span class="sxs-lookup"><span data-stu-id="22de4-112">It should look like the following:</span></span>

![替换文字](../media/webdriver/sample-app.png)

## <span data-ttu-id="22de4-114">步骤2：安装 Microsoft Edge 驱动程序</span><span class="sxs-lookup"><span data-stu-id="22de4-114">Step 2: Install Microsoft Edge Driver</span></span>

<span data-ttu-id="22de4-115">按照说明安装 [Microsoft Edge 驱动程序](https://docs.microsoft.com/microsoft-edge/webdriver-chromium#download-microsoft-edge-driver) 所需的浏览器特定驱动程序 Selenium 以自动化和测试 WebView2。</span><span class="sxs-lookup"><span data-stu-id="22de4-115">Follow the instructions to install [Microsoft Edge Driver](https://docs.microsoft.com/microsoft-edge/webdriver-chromium#download-microsoft-edge-driver) the browser-specific driver required by Selenium to automate and test WebView2.</span></span>

<span data-ttu-id="22de4-116">请务必确保 Microsoft Edge 驱动程序版本与应用程序使用的 Microsoft Edge 版本相匹配。</span><span class="sxs-lookup"><span data-stu-id="22de4-116">It is important to make sure that the version of Microsoft Edge Driver matches the version of Microsoft Edge that the application uses.</span></span> <span data-ttu-id="22de4-117">若要使 WebView2API 示例正常工作，请确保你的 Microsoft Edge 版本大于或等于我们的 [发行说明中](https://docs.microsoft.com/microsoft-edge/hosting/webview2/releasenotes)找到的最新 SDK 版本的受支持版本。</span><span class="sxs-lookup"><span data-stu-id="22de4-117">For the WebView2API Sample to work, make sure that your version of Microsoft Edge is greater than or equal to the supported version of our latest SDK release found [in our Release Notes](https://docs.microsoft.com/microsoft-edge/hosting/webview2/releasenotes).</span></span> <span data-ttu-id="22de4-118">若要了解您当前拥有的 Microsoft Edge 版本，请 `edge://settings/help` 在浏览器中加载。</span><span class="sxs-lookup"><span data-stu-id="22de4-118">To find out what version of Microsoft Edge you currently have, load `edge://settings/help` in the browser.</span></span>

## <span data-ttu-id="22de4-119">步骤3：将 Selenium 添加到 WebView2API 示例</span><span class="sxs-lookup"><span data-stu-id="22de4-119">Step 3: Add Selenium to the WebView2API Sample</span></span>

<span data-ttu-id="22de4-120">此时，你应该已安装 Microsoft Edge，构建一个 WebView2 项目，并安装了 Microsoft Edge 驱动程序。</span><span class="sxs-lookup"><span data-stu-id="22de4-120">At this point you should have Microsoft Edge installed, built a WebView2 project, and installed Microsoft Edge Driver.</span></span> <span data-ttu-id="22de4-121">现在，让我们开始使用 Selenium。</span><span class="sxs-lookup"><span data-stu-id="22de4-121">Now, let's get started using Selenium.</span></span>

> [!NOTE]
> <span data-ttu-id="22de4-122">Selenium 支持 c #、Java、Python、Javascript 和 Ruby。</span><span class="sxs-lookup"><span data-stu-id="22de4-122">Selenium supports C#, Java, Python, Javascript, and Ruby.</span></span> <span data-ttu-id="22de4-123">但是，本指南将位于 c # 中。</span><span class="sxs-lookup"><span data-stu-id="22de4-123">However, this guide will be in C#.</span></span>

1. <span data-ttu-id="22de4-124">首先在**Visual Studio**中创建新的**c # .net Framework**项目。</span><span class="sxs-lookup"><span data-stu-id="22de4-124">Start by creating a new **C# .NET Framework** project in **Visual Studio**.</span></span> <span data-ttu-id="22de4-125">单击右下角的 " **下一步** " 以继续。</span><span class="sxs-lookup"><span data-stu-id="22de4-125">Click **Next** on the bottom right-hand corner to continue.</span></span>

![替换文字](../media/webdriver/new-project.png)

2. <span data-ttu-id="22de4-127">为你的项目 **命名**，将其保存到你的首选 **位置**，然后单击 " **创建**"。</span><span class="sxs-lookup"><span data-stu-id="22de4-127">Give your project a **name**, save it to your preferred **location**, and click **Create**.</span></span>

![替换文字](../media/webdriver/app-create.png)

3. <span data-ttu-id="22de4-129">将创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="22de4-129">A new project will be created.</span></span> <span data-ttu-id="22de4-130">在本指南中，将在 **Program.cs** 文件中写入所有代码。</span><span class="sxs-lookup"><span data-stu-id="22de4-130">In this guide, all code will be written in the **Program.cs** file.</span></span>

![替换文字](../media/webdriver/start-app.png)

4. <span data-ttu-id="22de4-132">现在，我们将 **Selenium** 添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="22de4-132">Now let's add **Selenium** to the project.</span></span> <span data-ttu-id="22de4-133">你可以通过 **Selenium WebDriver NuGet 程序包**安装 Selenium。</span><span class="sxs-lookup"><span data-stu-id="22de4-133">You can install Selenium via the **Selenium.WebDriver NuGet package**.</span></span>

<span data-ttu-id="22de4-134">若要下载 **Selenium NuGet 程序包**，请在 **Visual Studio**中，将鼠标悬停在 **Project** 上，然后选择 " **管理 NuGet 程序包**"。</span><span class="sxs-lookup"><span data-stu-id="22de4-134">To download the **Selenium.WebDriver NuGet package**, in **Visual Studio**, hover over **Project** and select **Manage NuGet Package**.</span></span> <span data-ttu-id="22de4-135">将显示以下屏幕：</span><span class="sxs-lookup"><span data-stu-id="22de4-135">The following screen should appear:</span></span>

![替换文字](../media/webdriver/download-nuget.png)

5. <span data-ttu-id="22de4-137">在搜索栏中输入 **Selenium** ，单击结果中的 **Selenium WebDriver** ，并确保 " **包括预发布**" 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="22de4-137">Enter **Selenium.WebDriver** in the search bar, click **Selenium.WebDriver** from the results, and make sure to checkmark the box next to **include pre-release**.</span></span> <span data-ttu-id="22de4-138">在右侧窗口中，确保已将 **版本** 设置为 **安装 4.0.0-alpha04** 或更高版本，然后单击 " **安装**"。</span><span class="sxs-lookup"><span data-stu-id="22de4-138">On the right-hand side window, ensure the **Version** is set to **install 4.0.0-alpha04** or later and click **Install**.</span></span> <span data-ttu-id="22de4-139">Nuget 将 Selenium 下载到您的计算机。</span><span class="sxs-lookup"><span data-stu-id="22de4-139">Nuget will download Selenium to your machine.</span></span>

[<span data-ttu-id="22de4-140">了解有关 Selenium WebDriver NuGet 程序包的详细信息。</span><span class="sxs-lookup"><span data-stu-id="22de4-140">Learn more about the Selenium.WebDriver NuGet package.</span></span>](https://www.nuget.org/packages/Selenium.WebDriver/4.0.0-alpha04)

![替换文字](../media/webdriver/nuget.png)

6. <span data-ttu-id="22de4-142">通过在 Program.cs 的开头添加以下语句，使用**OpenQA： Selenium** ```using OpenQA.Selenium.Edge;``` **Program.cs**</span><span class="sxs-lookup"><span data-stu-id="22de4-142">Use **OpenQA.Selenium.Edge** by adding the following statement:```using OpenQA.Selenium.Edge;``` at the beginning of **Program.cs**</span></span>

```csharp
using OpenQA.Selenium.Edge;

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## <span data-ttu-id="22de4-143">步骤4：通过 Selenium 和 Microsoft EdgeDriver 驱动器 WebView2</span><span class="sxs-lookup"><span data-stu-id="22de4-143">Step 4: Drive WebView2 with Selenium and Microsoft EdgeDriver</span></span>

1. <span data-ttu-id="22de4-144">首先， `EdgeOptions` 通过复制以下代码来创建对象：</span><span class="sxs-lookup"><span data-stu-id="22de4-144">First, create the `EdgeOptions` object, by copying the code below:</span></span>

```csharp
static void Main(string[] args)
{
    // EdgeOptions() requires using OpenQA.Selenium.Edge
    // Construct EdgeOptions with is_legacy = false and the string "webview2"
    EdgeOptions edgeOptions = new EdgeOptions(false, "webview2");
```

<span data-ttu-id="22de4-145">该 `EdgeOptions` 对象采用两个参数：</span><span class="sxs-lookup"><span data-stu-id="22de4-145">The `EdgeOptions` object takes in two parameters:</span></span>
\
    **<span data-ttu-id="22de4-146">实参</span><span class="sxs-lookup"><span data-stu-id="22de4-146">Parameters:</span></span>**
    1. `is_legacy`<span data-ttu-id="22de4-147">：设置为 `false` ，告诉 Selenium 你正在推动新的基于 Chromium 的 Microsoft Edge 浏览器。</span><span class="sxs-lookup"><span data-stu-id="22de4-147">: set to `false`, which tells Selenium that you are driving the new Chromium-based Microsoft Edge browser.</span></span>
    2. `"webview2"`<span data-ttu-id="22de4-148">：告诉 Selenium 您正在推动**WebView2**的字符串</span><span class="sxs-lookup"><span data-stu-id="22de4-148">: a string that tell Selenium you are driving **WebView2**</span></span>

2. <span data-ttu-id="22de4-149">下一步，设置 `edgeOptions.BinaryLocation` 为 WebView2 项目可执行文件的文件路径，创建一个字符串， `msedgedriverDir` 该字符串提供了安装 [Microsoft edge 驱动程序](https://developer.microsoft.com/microsoft-edge/tools/webdriver/#downloads)的位置的文件路径，并创建一个字符串， `msedgedriverExe` 用于存储 microsoft edge 驱动程序可执行文件的名称。</span><span class="sxs-lookup"><span data-stu-id="22de4-149">Next, set `edgeOptions.BinaryLocation` to the file path of your WebView2 project's executable, create a string called `msedgedriverDir` that provides the file path to where you installed [Microsoft Edge Driver](https://developer.microsoft.com/microsoft-edge/tools/webdriver/#downloads), and create a string called `msedgedriverExe` to store the name of the Microsoft Edge Driver executable.</span></span> <span data-ttu-id="22de4-150">默认情况下，将调用可执行文件 `"msedgedriver.exe"` 。</span><span class="sxs-lookup"><span data-stu-id="22de4-150">By default, the executable is called `"msedgedriver.exe"`.</span></span> <span data-ttu-id="22de4-151">使用这两个字符串构造对象，如下 `EdgeDriverService` 所示。</span><span class="sxs-lookup"><span data-stu-id="22de4-151">Use these two strings to construct the `EdgeDriverService` object as shown below.</span></span> <span data-ttu-id="22de4-152">最后， `EdgeDriver` 使用 and 创建对象 `EdgeDriverService` `EdgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="22de4-152">Finally, create the `EdgeDriver` object using `EdgeDriverService` and `EdgeOptions`.</span></span>

<span data-ttu-id="22de4-153">你可以将以下代码复制并粘贴到下面 `edgeOptions` 。</span><span class="sxs-lookup"><span data-stu-id="22de4-153">You can copy and paste the following code underneath `edgeOptions`.</span></span> <span data-ttu-id="22de4-154">请确保为你的计算机上的项目可执行文件和 Microsoft Edge 驱动程序的可执行文件指定正确的文件路径。</span><span class="sxs-lookup"><span data-stu-id="22de4-154">Make sure to specify the correct file paths to your project's executable and the Microsoft Edge Driver's executable on your machine.</span></span>

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

3. <span data-ttu-id="22de4-155">现在， **EdgeDriver** 被配置为驱动你的项目中的 **WebView2** 。</span><span class="sxs-lookup"><span data-stu-id="22de4-155">Now, **EdgeDriver** is configured to drive the **WebView2** in your project.</span></span> <span data-ttu-id="22de4-156">例如，如果你使用的是 **WebView2API 示例**，则可以通过调用 **导航** 到 <https://microsoft.com> ```e.Url = @"https://www.microsoft.com";``` 。</span><span class="sxs-lookup"><span data-stu-id="22de4-156">For example, if you are using the **WebView2API Sample**, you can **Navigate** to <https://microsoft.com> by calling ```e.Url = @"https://www.microsoft.com";```.</span></span> <span data-ttu-id="22de4-157">你可以通过在此行上设置断点并运行项目来观看 **Selenium** drive **WebView2** 。</span><span class="sxs-lookup"><span data-stu-id="22de4-157">You can watch **Selenium** drive **WebView2** by setting a breakpoint on this line and running the project.</span></span>

```csharp
    //The following will Navigate the WebView2API Sample from bing.com to microsoft.com
    e.Url = @"https://www.microsoft.com";

    //This exits the edge driver
    e.Quit();
}
```

![替换文字](../media/webdriver/microsoft.png)

<span data-ttu-id="22de4-159">恭喜你！</span><span class="sxs-lookup"><span data-stu-id="22de4-159">Congratulations!</span></span> <span data-ttu-id="22de4-160">你已成功使用 Selenium 和 Microsoft Edge 驱动程序成功自动化了 WebView2 项目和驱动的 WebView2。</span><span class="sxs-lookup"><span data-stu-id="22de4-160">You have successfully automated a WebView2 project and driven WebView2 using Selenium and Microsoft Edge Driver.</span></span>

## <span data-ttu-id="22de4-161">后续步骤</span><span class="sxs-lookup"><span data-stu-id="22de4-161">Next steps</span></span>

<span data-ttu-id="22de4-162">若要了解详细信息：</span><span class="sxs-lookup"><span data-stu-id="22de4-162">To learn more:</span></span>

- <span data-ttu-id="22de4-163">查看 [Selenium 的文档](https://www.selenium.dev/documentation/en/webdriver/) 以全面了解 Selenium 的 api 可用于推动 WebView2 或 Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="22de4-163">Check out [Selenium's documentation](https://www.selenium.dev/documentation/en/webdriver/) for a comprehensive look at the APIs Selenium has available for driving WebView2 or Microsoft Edge (Chromium)</span></span>
- <span data-ttu-id="22de4-164">了解有关 [WebView2](https://docs.microsoft.com/microsoft-edge/hosting/webview2) 控件的详细信息，以及如何在你的本机应用中嵌入 web 内容时使用它</span><span class="sxs-lookup"><span data-stu-id="22de4-164">Learn more about [WebView2](https://docs.microsoft.com/microsoft-edge/hosting/webview2) control and how to use it when embedding web content in your native app</span></span>
- <span data-ttu-id="22de4-165">查看 [Microsoft Edge 驱动程序的文档](https://docs.microsoft.com/microsoft-edge/webdriver-chromium) ，了解有关自动化 microsoft Edge (Chromium 的详细信息) </span><span class="sxs-lookup"><span data-stu-id="22de4-165">Check out [documentation for Microsoft Edge Driver](https://docs.microsoft.com/microsoft-edge/webdriver-chromium) to learn more about automating Microsoft Edge (Chromium)</span></span>

## <span data-ttu-id="22de4-166">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="22de4-166">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  
