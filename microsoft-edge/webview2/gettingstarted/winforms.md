---
description: 适用于 WinForms 应用的 WebView2 入门指南
title: 适用于 WinForms 应用的 WebView2 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/29/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、webview2、WebView、webview、winforms 应用、winforms、edge、CoreWebView2、浏览器控件、边缘 html、入门、入门、.NET、windows 表单
ms.openlocfilehash: 45a3b59733a57975e373df2e21258198645be2d4
ms.sourcegitcommit: d89f77d4667dfbc44ed35f2ec7e3ae64ab98bf1a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2021
ms.locfileid: "11306164"
---
# <span data-ttu-id="a77c4-104">Windows 窗体中的 WebView2 入门</span><span class="sxs-lookup"><span data-stu-id="a77c4-104">Getting started with WebView2 in Windows Forms</span></span>

<span data-ttu-id="a77c4-105">本文将开始创建你的第一个 WebView2 应用，并了解 [WebView2 的主要功能][MicrosoftDeveloperMicrosoftEdgeWebview2]。</span><span class="sxs-lookup"><span data-stu-id="a77c4-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2].</span></span>  <span data-ttu-id="a77c4-106">有关各个 API 详细信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2Winforms]。</span><span class="sxs-lookup"><span data-stu-id="a77c4-106">For more information on individual APIs, navigate to [API reference][DotnetApiMicrosoftWebWebview2Winforms].</span></span>  

## <span data-ttu-id="a77c4-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="a77c4-107">Prerequisites</span></span>  

<span data-ttu-id="a77c4-108">确保先安装以下先决条件列表，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="a77c4-108">Ensure you install the following list of pre-requisites before proceeding.</span></span>  

*   <span data-ttu-id="a77c4-109">[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2] 运行时或任何 [Microsoft Edge (Chromium) ][MicrosoftedgeinsiderDownload] 安装在受支持的操作系统 \(当前为 Windows 10、Windows 8.1 和 Windows 7\) 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-109">[WebView2 Runtime][MicrosoftDeveloperMicrosoftEdgeWebview2] or any [Microsoft Edge (Chromium) non-stable channel][MicrosoftedgeinsiderDownload] installed on supported OS \(currently Windows 10, Windows 8.1, and Windows 7\).</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="a77c4-110">WebView 团队建议使用 Canary 通道，最低要求版本为 82.0.488.0。</span><span class="sxs-lookup"><span data-stu-id="a77c4-110">The WebView team recommends using the Canary channel and the minimum required version is 82.0.488.0.</span></span>  
    
*   <span data-ttu-id="a77c4-111">[Visual Studio][MicrosoftVisualstudioMain] 2017 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a77c4-111">[Visual Studio][MicrosoftVisualstudioMain] 2017 or later.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="a77c4-112">WebView2 当前不支持 .NET 5 和 .NET Core 设计器。</span><span class="sxs-lookup"><span data-stu-id="a77c4-112">WebView2 currently does not support the .NET 5 and .NET Core designers.</span></span>

## <span data-ttu-id="a77c4-113">步骤 1 - 创建单窗口应用</span><span class="sxs-lookup"><span data-stu-id="a77c4-113">Step 1 - Create a single-window app</span></span>

<span data-ttu-id="a77c4-114">从包含单个主窗口的基本桌面项目开始。</span><span class="sxs-lookup"><span data-stu-id="a77c4-114">Start with a basic desktop project that contains a single main window.</span></span>  

1.  <span data-ttu-id="a77c4-115">In Visual Studio， choose **Windows Forms .NET Framework App**  >  **Next.**</span><span class="sxs-lookup"><span data-stu-id="a77c4-115">In Visual Studio, choose **Windows Forms .NET Framework App** > **Next**.</span></span>
    
    :::image type="complex" source="./media/winforms-newproject.png" alt-text="新建项目" lightbox="./media/winforms-newproject.png":::
       <span data-ttu-id="a77c4-117">新建项目</span><span class="sxs-lookup"><span data-stu-id="a77c4-117">New project</span></span>  
    :::image-end:::
    
1.  <span data-ttu-id="a77c4-118">输入 **项目名称和** 位置 **的值**。</span><span class="sxs-lookup"><span data-stu-id="a77c4-118">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="a77c4-119">选择 **.NET Framework 4.6.2** 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="a77c4-119">Choose **.NET Framework 4.6.2** or later.</span></span>  
    
    :::image type="complex" source="./media/winforms-startproj.png" alt-text="启动项目" lightbox="./media/winforms-startproj.png":::
       <span data-ttu-id="a77c4-121">启动项目</span><span class="sxs-lookup"><span data-stu-id="a77c4-121">Start project</span></span>  
    :::image-end:::
    
1.  <span data-ttu-id="a77c4-122">若要创建项目，请选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="a77c4-122">To create your project, choose **Create**.</span></span>
    
## <span data-ttu-id="a77c4-123">步骤 2 - 安装 WebView2 SDK</span><span class="sxs-lookup"><span data-stu-id="a77c4-123">Step 2 - Install WebView2 SDK</span></span>

<span data-ttu-id="a77c4-124">使用 NuGet 将 WebView2 SDK 添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="a77c4-124">Use NuGet to add the WebView2 SDK to the project.</span></span>  

1.  <span data-ttu-id="a77c4-125">将鼠标悬停在项目上，打开上下文菜单 \(右键单击\) ，然后选择"管理**NuGet 程序包..."。**</span><span class="sxs-lookup"><span data-stu-id="a77c4-125">Hover on the project, open the contextual menu \(right-click\), and choose **Manage NuGet Packages...**.</span></span>  
    
    :::image type="complex" source="./media/wpf-gettingstarted-mngnuget.png" alt-text="管理 NuGet 程序包":::
       <span data-ttu-id="a77c4-127">管理 NuGet 程序包</span><span class="sxs-lookup"><span data-stu-id="a77c4-127">Manage NuGet Packages</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="a77c4-128">在搜索栏中，键入> `Microsoft.Web.WebView2` **选择 Microsoft.Web.WebView2。**</span><span class="sxs-lookup"><span data-stu-id="a77c4-128">In the search bar, type `Microsoft.Web.WebView2` > choose **Microsoft.Web.WebView2**.</span></span>  
    
    :::image type="complex" source="./media/installnuget.png" alt-text="NuGet" lightbox="./media/installnuget.png":::
       <span data-ttu-id="a77c4-130">NuGet</span><span class="sxs-lookup"><span data-stu-id="a77c4-130">NuGet</span></span>  
    :::image-end:::
    
    <span data-ttu-id="a77c4-131">开始使用 WebView2 API 开发应用。</span><span class="sxs-lookup"><span data-stu-id="a77c4-131">Start developing apps using the WebView2 API.</span></span>  <span data-ttu-id="a77c4-132">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-132">To build and run the project, select `F5`.</span></span>  <span data-ttu-id="a77c4-133">正在运行的项目显示一个空窗口。</span><span class="sxs-lookup"><span data-stu-id="a77c4-133">The running project displays an empty window.</span></span>  
    
    :::image type="complex" source="./media/winforms-emptyapp.png" alt-text="空应用" lightbox="./media/winforms-emptyapp.png":::
       <span data-ttu-id="a77c4-135">空应用</span><span class="sxs-lookup"><span data-stu-id="a77c4-135">Empty app</span></span>  
    :::image-end:::
    
## <span data-ttu-id="a77c4-136">步骤 3 - 创建单个 WebView</span><span class="sxs-lookup"><span data-stu-id="a77c4-136">Step 3 - Create a single WebView</span></span>  

<span data-ttu-id="a77c4-137">将 WebView 添加到你的应用。</span><span class="sxs-lookup"><span data-stu-id="a77c4-137">Add a WebView to your app.</span></span>  

1.  <span data-ttu-id="a77c4-138">打开 **Windows 窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="a77c4-138">Open the **Windows Forms Designer**.</span></span>  
1.  <span data-ttu-id="a77c4-139">在工具箱**中搜索 WebView2。** </span><span class="sxs-lookup"><span data-stu-id="a77c4-139">Search for **WebView2** in the **Toolbox**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="a77c4-140">如果使用的是 Visual Studio 2017，默认情况下 **，WebView2** 可能不会显示在 **工具箱中**。</span><span class="sxs-lookup"><span data-stu-id="a77c4-140">If you are using Visual Studio 2017, by default **WebView2** may not display in the **Toolbox**.</span></span>  <span data-ttu-id="a77c4-141">若要启用该行为 **，请选择"** 工具  >  **选项**常规  >  >**将"自动填充**工具箱"设置设置为 `True` 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-141">To enable the behavior, choose **Tools** > **Options** > **General** > set the **Automatically Populate Toolbox** setting to `True`.</span></span>  
    
    <span data-ttu-id="a77c4-142">将 **WebView2 控件** 拖放到 Windows 窗体应用。</span><span class="sxs-lookup"><span data-stu-id="a77c4-142">Drag and drop the **WebView2** control into the Windows Forms App.</span></span>
    
    :::image type="complex" source="./media/winforms-toolbox.png" alt-text="显示 WebView2 的工具箱":::
       <span data-ttu-id="a77c4-144">显示 WebView2 的工具箱</span><span class="sxs-lookup"><span data-stu-id="a77c4-144">Toolbox displaying WebView2</span></span>
    :::image-end:::  

1.  <span data-ttu-id="a77c4-145">将 `(Name)` 属性设置为 `webView`。</span><span class="sxs-lookup"><span data-stu-id="a77c4-145">Set the `(Name)` property to `webView`.</span></span>
    
    :::image type="complex" source="./media/winforms-properties.png" alt-text="WebView2 控件的属性":::
       <span data-ttu-id="a77c4-147">WebView2 控件的属性</span><span class="sxs-lookup"><span data-stu-id="a77c4-147">Properties of the WebView2 control</span></span>
    :::image-end:::

1.  <span data-ttu-id="a77c4-148">该属性 `Source` 设置 WebView2 控件中显示的初始 URI。</span><span class="sxs-lookup"><span data-stu-id="a77c4-148">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  <span data-ttu-id="a77c4-149">将 `Source` 属性设置为 `https://www.microsoft.com`。</span><span class="sxs-lookup"><span data-stu-id="a77c4-149">Set the `Source` property to `https://www.microsoft.com`.</span></span>  
    
    :::image type="complex" source="./media/winforms-source.png" alt-text="WebView2 控件的 Source 属性":::
       <span data-ttu-id="a77c4-151">**WebView2**控件的 Source 属性</span><span class="sxs-lookup"><span data-stu-id="a77c4-151">The **Source** property of the WebView2 control</span></span>
    :::image-end:::  

<span data-ttu-id="a77c4-152">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-152">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="a77c4-153">确保 WebView2 控件显示 [https://www.microsoft.com][|::ref1::|Main] 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-153">Ensure your WebView2 control displays [https://www.microsoft.com][|::ref1::|Main].</span></span>

:::image type="complex" source="./media/winforms-hellowebview.png" alt-text="hello webview" lightbox="./media/winforms-hellowebview.png":::
   <span data-ttu-id="a77c4-155">hello webview</span><span class="sxs-lookup"><span data-stu-id="a77c4-155">hello webview</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="a77c4-156">如果正在处理高 DPI 监视器，可能需要将 Windows[窗体应用配置为支持高 DPI。][DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport]</span><span class="sxs-lookup"><span data-stu-id="a77c4-156">If you are working on a high DPI monitor, you may have to [configure your Windows Forms app for high DPI support][DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport].</span></span>  

## <span data-ttu-id="a77c4-157">步骤 4 - 处理窗口调整大小事件</span><span class="sxs-lookup"><span data-stu-id="a77c4-157">Step 4 - Handle Window Resize Events</span></span>

<span data-ttu-id="a77c4-158">从工具箱向 Windows 窗体添加更多控件，然后适当地处理窗口大小事件。</span><span class="sxs-lookup"><span data-stu-id="a77c4-158">Add a few more controls to your Windows Forms from the toolbox, and then handle window resize events appropriately.</span></span>

1.  <span data-ttu-id="a77c4-159">在 **Windows 窗体设计器中**，打开 **工具箱**</span><span class="sxs-lookup"><span data-stu-id="a77c4-159">In the **Windows Forms Designer**, open the **Toolbox**</span></span>
1.  <span data-ttu-id="a77c4-160">将 **TextBox 拖放** 到 Windows Forms App 中。</span><span class="sxs-lookup"><span data-stu-id="a77c4-160">Drag and drop a **TextBox** into the Windows Forms App.</span></span>  <span data-ttu-id="a77c4-161">在"**属性"选项卡**中，命名**TextBox。** `addressBar`</span><span class="sxs-lookup"><span data-stu-id="a77c4-161">In the **Properties Tab**, name the **TextBox** `addressBar` .</span></span>
1.  <span data-ttu-id="a77c4-162">将按钮 **拖放** 到 Windows 窗体应用。</span><span class="sxs-lookup"><span data-stu-id="a77c4-162">Drag and drop a **Button** into the Windows Forms App.</span></span>  <span data-ttu-id="a77c4-163">将按钮中的 **文本更改为** 属性选项卡中的 `Go!` **按钮** `goButton` 并 **命名**。</span><span class="sxs-lookup"><span data-stu-id="a77c4-163">Change the text in the **Button** to `Go!` and name the **Button** `goButton` in the **Properties Tab**.</span></span>

    <span data-ttu-id="a77c4-164">应用应如设计器中的下图所示。</span><span class="sxs-lookup"><span data-stu-id="a77c4-164">The app should look like the following image in the designer.</span></span>
    
    :::image type="complex" source="./media/winforms-designer.png" alt-text="designer" lightbox="./media/winforms-designer.png":::
       <span data-ttu-id="a77c4-166">designer</span><span class="sxs-lookup"><span data-stu-id="a77c4-166">designer</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="a77c4-167">在 `Form1.cs` 文件中，定义以在调整应用窗口 `Form_Resize` 大小时保持控件就位。</span><span class="sxs-lookup"><span data-stu-id="a77c4-167">In the `Form1.cs` file, define `Form_Resize` to keep the controls in place when the App Window is resized.</span></span>

```csharp
public Form1()
{
    InitializeComponent();
    this.Resize += new System.EventHandler(this.Form_Resize);
}

private void Form_Resize(object sender, EventArgs e)
{
    webView.Size = this.ClientSize - new System.Drawing.Size(webView.Location);
    goButton.Left = this.ClientSize.Width - goButton.Width;
    addressBar.Width = goButton.Left - addressBar.Left;
}
```

<span data-ttu-id="a77c4-168">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-168">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="a77c4-169">确保应用显示类似于以下屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="a77c4-169">Ensure the app displays similar to the following screenshot.</span></span>

:::image type="complex" source="./media/winforms-app.png" alt-text="应用" lightbox="./media/winforms-app.png":::
   <span data-ttu-id="a77c4-171">应用</span><span class="sxs-lookup"><span data-stu-id="a77c4-171">App</span></span>  
:::image-end:::

## <span data-ttu-id="a77c4-172">步骤 5 - 导航</span><span class="sxs-lookup"><span data-stu-id="a77c4-172">Step 5 - Navigation</span></span>

<span data-ttu-id="a77c4-173">添加允许用户通过向应用添加地址栏来更改 WebView2 控件显示的 URL 的能力。</span><span class="sxs-lookup"><span data-stu-id="a77c4-173">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>

1.  <span data-ttu-id="a77c4-174">在 `Form1.cs` 文件中，若要添加 `CoreWebView2` 命名空间，请将以下代码段插入顶部。</span><span class="sxs-lookup"><span data-stu-id="a77c4-174">In the `Form1.cs`file, to add the `CoreWebView2` namespace, insert the following code snippet at the top.</span></span>  

    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```

1.  <span data-ttu-id="a77c4-175">在 **Windows 窗体设计器中**，双击按钮 `Go!` 以 `goButton_Click` 在文件中创建 `Form1.cs` 方法。</span><span class="sxs-lookup"><span data-stu-id="a77c4-175">In the **Windows Forms Designer**, double-click on the `Go!` button to create the `goButton_Click` method in the `Form1.cs` file.</span></span>  <span data-ttu-id="a77c4-176">在函数中复制并粘贴以下代码段。</span><span class="sxs-lookup"><span data-stu-id="a77c4-176">Copy and paste the following snippet inside the function.</span></span>  <span data-ttu-id="a77c4-177">现在， `goButton_Click` 该函数将 WebView 导航到地址栏中输入的 URL。</span><span class="sxs-lookup"><span data-stu-id="a77c4-177">Now, the `goButton_Click` function navigates the WebView to the URL entered in the address bar.</span></span>

    ```csharp
    private void goButton_Click(object sender, EventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  

<span data-ttu-id="a77c4-178">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-178">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="a77c4-179">在地址栏中输入新 URL，然后选择 **"转到"。**</span><span class="sxs-lookup"><span data-stu-id="a77c4-179">Enter a new URL in the address bar, and select **Go**.</span></span>  <span data-ttu-id="a77c4-180">例如，输入 `https://www.bing.com` 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-180">For example, enter `https://www.bing.com`.</span></span>  <span data-ttu-id="a77c4-181">确保 WebView2 控件导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="a77c4-181">Ensure the WebView2 control navigates to the URL.</span></span>  

> [!NOTE]
> <span data-ttu-id="a77c4-182">确保在地址栏中输入完整 URL。</span><span class="sxs-lookup"><span data-stu-id="a77c4-182">Ensure a complete URL is entered in the address bar.</span></span>  <span data-ttu-id="a77c4-183">如果 `ArgumentException` URL 不以或 `http://`</span><span class="sxs-lookup"><span data-stu-id="a77c4-183">An `ArgumentException` is thrown if the URL does not start with `http://` or</span></span> `https://`

:::image type="complex" source="./media/winforms-bing.png" alt-text="bing.com" lightbox="./media/winforms-bing.png":::
   <span data-ttu-id="a77c4-185">bing.com</span><span class="sxs-lookup"><span data-stu-id="a77c4-185">bing.com</span></span>  
:::image-end:::

## <span data-ttu-id="a77c4-186">步骤 6 - 导航事件</span><span class="sxs-lookup"><span data-stu-id="a77c4-186">Step 6 - Navigation events</span></span>  

<span data-ttu-id="a77c4-187">在网页导航过程中，WebView2 控件引发事件。</span><span class="sxs-lookup"><span data-stu-id="a77c4-187">During webpage navigation, the WebView2 control raises events.</span></span>  <span data-ttu-id="a77c4-188">承载 WebView2 控件的应用侦听以下事件。</span><span class="sxs-lookup"><span data-stu-id="a77c4-188">The app that hosts WebView2 controls listens for the following events.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  

<span data-ttu-id="a77c4-189">有关详细信息，请导航到 [导航事件][Webview2ConceptsNavigationEvents]。</span><span class="sxs-lookup"><span data-stu-id="a77c4-189">For more information, navigate to [Navigation Events][Webview2ConceptsNavigationEvents].</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="导航事件":::
   <span data-ttu-id="a77c4-191">导航事件</span><span class="sxs-lookup"><span data-stu-id="a77c4-191">Navigation events</span></span>
:::image-end:::

<span data-ttu-id="a77c4-192">发生错误时，将引发以下事件，并可能依赖于导航到错误网页。</span><span class="sxs-lookup"><span data-stu-id="a77c4-192">When an error occurs, the following events are raised and may depend on navigation to an error webpage.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  

> [!NOTE]
> <span data-ttu-id="a77c4-193">如果 HTTP 重定向发生，则一行 `NavigationStarting` 中有多个事件。</span><span class="sxs-lookup"><span data-stu-id="a77c4-193">If an HTTP redirect occurs, there are multiple `NavigationStarting` events in a row.</span></span>  

<span data-ttu-id="a77c4-194">若要演示如何使用这些事件，请首先为取消不使用 HTTPS 的任何请求注册 `NavigationStarting` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="a77c4-194">To demonstrate how to use these events, start by registering a handler for `NavigationStarting` that cancels any requests that don't use HTTPS.</span></span>  

<span data-ttu-id="a77c4-195">在 `Form1.cs` 文件中，更新构造函数以匹配以下代码段并添加 `EnsureHttps` 函数。</span><span class="sxs-lookup"><span data-stu-id="a77c4-195">In the `Form1.cs` file, update the constructor to match the following code snippet and add the `EnsureHttps` function.</span></span>  

```csharp
public Form1()
{
    InitializeComponent();
    this.Resize += new System.EventHandler(this.Form_Resize);

    webView.NavigationStarting += EnsureHttps;
}

void EnsureHttps(object sender, CoreWebView2NavigationStartingEventArgs args)
{
    String uri = args.Uri;
    if (!uri.StartsWith("https://"))
    {
        args.Cancel = true;
    }
}
```

<span data-ttu-id="a77c4-196">在构造函数中，EnsureHttps 在 WebView2 控件上的事件上注册为 `NavigationStarting` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a77c4-196">In the constructor, EnsureHttps is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="a77c4-197">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-197">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="a77c4-198">确保导航到 HTTP 网站时，WebView 保持不变。</span><span class="sxs-lookup"><span data-stu-id="a77c4-198">Ensure when navigating to an HTTP site, the WebView remains unchanged.</span></span>  <span data-ttu-id="a77c4-199">但是，WebView 将导航到 HTTPS 网站。</span><span class="sxs-lookup"><span data-stu-id="a77c4-199">However, the WebView will navigate to HTTPS sites.</span></span>

## <span data-ttu-id="a77c4-200">步骤 7 - 脚本</span><span class="sxs-lookup"><span data-stu-id="a77c4-200">Step 7 - Scripting</span></span>  

<span data-ttu-id="a77c4-201">在运行时，可以使用主机应用将 JavaScript 代码注入 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="a77c4-201">You may use host apps to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="a77c4-202">你可以让 WebView 运行任意 JavaScript 或添加初始化脚本。</span><span class="sxs-lookup"><span data-stu-id="a77c4-202">You may task WebView to run arbitrary JavaScript or add initialization scripts.</span></span>  <span data-ttu-id="a77c4-203">在删除 JavaScript 之前，注入的 JavaScript 适用于所有新的顶级文档和任何子框架。</span><span class="sxs-lookup"><span data-stu-id="a77c4-203">The injected JavaScript applies to all new top-level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="a77c4-204">注入的 JavaScript 以特定计时运行。</span><span class="sxs-lookup"><span data-stu-id="a77c4-204">The injected JavaScript is run with specific timing.</span></span>  

*   <span data-ttu-id="a77c4-205">创建全局对象后运行它。</span><span class="sxs-lookup"><span data-stu-id="a77c4-205">Run it after the creation of the global object.</span></span>  
*   <span data-ttu-id="a77c4-206">在 HTML 文档中包含的任何其他脚本运行之前运行它。</span><span class="sxs-lookup"><span data-stu-id="a77c4-206">Run it before any other script included in the HTML document is run.</span></span>  

<span data-ttu-id="a77c4-207">例如，添加在用户导航到非 HTTPS 网站时发送警报的脚本。</span><span class="sxs-lookup"><span data-stu-id="a77c4-207">As an example, add scripts that send an alert when a user navigates to non-HTTPS sites.</span></span>  <span data-ttu-id="a77c4-208">修改 `EnsureHttps` 函数以将脚本注入使用 [ExecuteScriptAsync][DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync] 方法的 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="a77c4-208">Modify the `EnsureHttps` function to inject a script into the web content that uses [ExecuteScriptAsync][DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync] method.</span></span>  

```csharp
void EnsureHttps(object sender, CoreWebView2NavigationStartingEventArgs args)
{
    String uri = args.Uri;
    if (!uri.StartsWith("https://"))
    {
        webView.CoreWebView2.ExecuteScriptAsync($"alert('{uri} is not safe, try an https link')");
        args.Cancel = true;
    }
}
```  

<span data-ttu-id="a77c4-209">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-209">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="a77c4-210">确保应用在您导航到不使用 HTTPS 的网站时显示警报。</span><span class="sxs-lookup"><span data-stu-id="a77c4-210">Ensure the app displays an alert when you navigate to a website that doesn't use HTTPS.</span></span>  

:::image type="complex" source="./media/winforms-https.png" alt-text="https" lightbox="./media/winforms-https.png":::
   <span data-ttu-id="a77c4-212">https</span><span class="sxs-lookup"><span data-stu-id="a77c4-212">https</span></span>  
:::image-end:::

## <span data-ttu-id="a77c4-213">步骤 8 - 主机和 Web 内容之间的通信</span><span class="sxs-lookup"><span data-stu-id="a77c4-213">Step 8 - Communication between host and web content</span></span>  

<span data-ttu-id="a77c4-214">主机和 Web 内容可能用于相互 `postMessage` 通信，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a77c4-214">The host and web content may use `postMessage` to communicate with each other as follows:</span></span>  

*   <span data-ttu-id="a77c4-215">WebView2 控件中的 Web 内容可能 `window.chrome.webview.postMessage` 用于向主机发布消息。</span><span class="sxs-lookup"><span data-stu-id="a77c4-215">Web content in a WebView2 control may use `window.chrome.webview.postMessage` to post a message to the host.</span></span>  <span data-ttu-id="a77c4-216">主机使用主机上注册的任何邮件 `WebMessageReceived` 处理邮件。</span><span class="sxs-lookup"><span data-stu-id="a77c4-216">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
*   <span data-ttu-id="a77c4-217">使用 或 将消息张贴到 WebView2 控件中的 `CoreWebView2.PostWebMessageAsString` Web 内容 `CoreWebView2.PostWebMessageAsJSON` 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-217">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="a77c4-218">这些消息被添加到的处理程序捕获 `window.chrome.webview.addEventListener` 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-218">These messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  

<span data-ttu-id="a77c4-219">通信机制使用本机功能将消息从 Web 内容传递给主机。</span><span class="sxs-lookup"><span data-stu-id="a77c4-219">The communication mechanism passes messages from web content to the host using native capabilities.</span></span>  

<span data-ttu-id="a77c4-220">在项目中，当 WebView2 控件导航到 URL 时，它会在地址栏中显示 URL，并通知用户 WebView2 控件中显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="a77c4-220">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1.  <span data-ttu-id="a77c4-221">在 `Form1.cs` 文件中，更新构造函数并创建 `InitializeAsync` 一个函数以匹配以下代码段。</span><span class="sxs-lookup"><span data-stu-id="a77c4-221">In the `Form1.cs` file, update your constructor and create an `InitializeAsync` function to match the following code snippet.</span></span>  <span data-ttu-id="a77c4-222">该 `InitializeAsync` 函数等待 [EnsureCoreWebView2Async，][DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async] 因为初始化 `CoreWebView2` 是异步的。</span><span class="sxs-lookup"><span data-stu-id="a77c4-222">The `InitializeAsync` function awaits [EnsureCoreWebView2Async][DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async] because the initialization of `CoreWebView2` is asynchronous.</span></span>  

    ```csharp
    public Form1()
    {
        InitializeComponent();
        this.Resize += new System.EventHandler(this.Form_Resize);
        webView.NavigationStarting += EnsureHttps;
        InitializeAsync();
    }

    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
    }
    ```  

1.  <span data-ttu-id="a77c4-223">初始化 `CoreWebView2` 后，注册要响应的事件处理程序 `WebMessageReceived` 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-223">After `CoreWebView2` is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="a77c4-224">在 `Form1.cs` 文件中， `InitializeAsync` 使用下面的代码 `UpdateAddressBar` 段更新和添加。</span><span class="sxs-lookup"><span data-stu-id="a77c4-224">In the `Form1.cs` file, update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  

    ```csharp
    async void InitializeAsync()
    {
        await webView.EnsureCoreWebView2Async(null);
        webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;
    }

    void UpdateAddressBar(object sender, CoreWebView2WebMessageReceivedEventArgs args)
    {
        String uri = args.TryGetWebMessageAsString();
        addressBar.Text = uri;
        webView.CoreWebView2.PostWebMessageAsString(uri);
    }
    ```  

1.  <span data-ttu-id="a77c4-225">为了使 WebView 能够发送和响应 Web 消息，在初始化后，主机在 Web 内容中注入脚本 `CoreWebView2` 以：</span><span class="sxs-lookup"><span data-stu-id="a77c4-225">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host injects a script in the web content to:</span></span>  

    1.  <span data-ttu-id="a77c4-226">使用 将 URL 发送到主机 `postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-226">Send the URL to the host using `postMessage`.</span></span>
    1.  <span data-ttu-id="a77c4-227">注册事件处理程序以打印从主机发送的消息。</span><span class="sxs-lookup"><span data-stu-id="a77c4-227">Register an event handler to print a message sent from the host.</span></span>  

<span data-ttu-id="a77c4-228">在 `Form1.cs` 文件中，更新 `InitializeAsync` 以匹配以下代码段。</span><span class="sxs-lookup"><span data-stu-id="a77c4-228">In the `Form1.cs` file, update `InitializeAsync` to match the following code snippet.</span></span>  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

<span data-ttu-id="a77c4-229">若要生成并运行应用，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="a77c4-229">To build and run the app, select `F5`.</span></span>  <span data-ttu-id="a77c4-230">现在，地址栏在 WebView2 控件中显示 URI。</span><span class="sxs-lookup"><span data-stu-id="a77c4-230">Now, the address bar displays the URI in the WebView2 control.</span></span>  <span data-ttu-id="a77c4-231">此外，当您成功导航到新 URL 时，WebView 会向用户通知 WebView 中显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="a77c4-231">Also, when you successfully navigate to a new URL, the WebView alerts the user of the URL displayed in the WebView.</span></span>  

:::image type="complex" source="./media/winforms-finalapp.png" alt-text="最终应用" lightbox="./media/winforms-finalapp.png":::
   <span data-ttu-id="a77c4-233">最终应用</span><span class="sxs-lookup"><span data-stu-id="a77c4-233">Final app</span></span>  
:::image-end:::

<span data-ttu-id="a77c4-234">恭喜！你生成了第一个 WebView2 应用。</span><span class="sxs-lookup"><span data-stu-id="a77c4-234">Congratulations, you built your first WebView2 app.</span></span>  

## <span data-ttu-id="a77c4-235">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a77c4-235">Next steps</span></span>  

<span data-ttu-id="a77c4-236">若要继续了解有关 WebView2 的更多内容，请导航到以下资源。</span><span class="sxs-lookup"><span data-stu-id="a77c4-236">To continue learning more about WebView2, navigate to the following resources.</span></span>  

### <span data-ttu-id="a77c4-237">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a77c4-237">See also</span></span>  

*   <span data-ttu-id="a77c4-238">有关 WebView2 功能的综合示例，请导航到[WebView2Samples。][GithubMicrosoftedgeWebview2samplesMain]</span><span class="sxs-lookup"><span data-stu-id="a77c4-238">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samplesMain].</span></span>  
*   <span data-ttu-id="a77c4-239">有关 WebView2 的信息，请导航到 [WebView2 资源][Webview2IndexNextSteps]。</span><span class="sxs-lookup"><span data-stu-id="a77c4-239">For more information about WebView2, navigate to [WebView2 Resources][Webview2IndexNextSteps].</span></span>  
*   <span data-ttu-id="a77c4-240">有关 WebView2 API 的详细信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2WinformsWebview2]。</span><span class="sxs-lookup"><span data-stu-id="a77c4-240">For detailed information about the WebView2 API, navigate to [API reference][DotnetApiMicrosoftWebWebview2WinformsWebview2].</span></span>  

## <span data-ttu-id="a77c4-241">与 Microsoft Edge WebView 团队联系</span><span class="sxs-lookup"><span data-stu-id="a77c4-241">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2IndexNextSteps]: ../index.md#next-steps "下一步 - Microsoft Edge WebView2 (预览版) |Microsoft Docs"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "导航事件|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Winforms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 命名空间|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "WebView2 类|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "WebView2.EnsureCoreWebView2Async (CoreWebView2Environment) 方法|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync]: /dotnet/api/microsoft.web.webview2.winforms.webview2.executescriptasync "WebView2.ExecuteScriptAsync (String) 方法|Microsoft Docs"  

[DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport]: /dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support "为 Windows Forms 应用配置高 DPI 支持 - Windows 窗体应用程序中的高 DPI |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 " WebView2 |Microsoft Edge 开发人员"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  