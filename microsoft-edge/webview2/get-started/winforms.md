---
description: 适用于 WinForms 应用的 WebView2 入门指南
title: WinForms 应用的 WebView2 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、webview2、WebView、webview、winforms 应用、winforms、edge、CoreWebView2、浏览器控件、edge html、入门、入门、.NET、windows 窗体
ms.openlocfilehash: 704e5732ddcff02e56f49bec37a5d1ad5f11c2b5
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535878"
---
# <a name="get-started-with-webview2-in-windows-forms"></a><span data-ttu-id="91b9c-104">在表单中开始使用 WebView2 Windows表单</span><span class="sxs-lookup"><span data-stu-id="91b9c-104">Get started with WebView2 in Windows Forms</span></span>

<span data-ttu-id="91b9c-105">本文将开始创建你的第一个 WebView2 应用，并了解 [WebView2 的主要功能][MicrosoftDeveloperMicrosoftEdgeWebview2]。</span><span class="sxs-lookup"><span data-stu-id="91b9c-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2].</span></span>  <span data-ttu-id="91b9c-106">有关各个 API 的信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2Winforms]。</span><span class="sxs-lookup"><span data-stu-id="91b9c-106">For more information on individual APIs, navigate to [API reference][DotnetApiMicrosoftWebWebview2Winforms].</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="91b9c-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="91b9c-107">Prerequisites</span></span>  

<span data-ttu-id="91b9c-108">请确保先安装以下先决条件列表，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="91b9c-108">Ensure you install the following list of pre-requisites before proceeding.</span></span>  

*   <span data-ttu-id="91b9c-109">[WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2]运行时Microsoft Edge (Chromium) [][MicrosoftedgeinsiderDownload]安装在受支持的操作系统 \ (上的任意非稳定通道Windows 10、Windows 8.1和 Windows 7\) 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-109">[WebView2 Runtime][MicrosoftDeveloperMicrosoftEdgeWebview2] or any [Microsoft Edge (Chromium) non-stable channel][MicrosoftedgeinsiderDownload] installed on supported OS \(currently Windows 10, Windows 8.1, and Windows 7\).</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="91b9c-110">WebView 团队建议使用 Canary 通道，最低要求版本为 82.0.488.0。</span><span class="sxs-lookup"><span data-stu-id="91b9c-110">The WebView team recommends using the Canary channel and the minimum required version is 82.0.488.0.</span></span>  
    
*   <span data-ttu-id="91b9c-111">[Visual Studio][MicrosoftVisualstudioMain] 2017 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="91b9c-111">[Visual Studio][MicrosoftVisualstudioMain] 2017 or later.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="91b9c-112">WebView2 当前不支持 .NET 5 和 .NET Core 设计器。</span><span class="sxs-lookup"><span data-stu-id="91b9c-112">WebView2 currently does not support the .NET 5 and .NET Core designers.</span></span>  

## <a name="step-1---create-a-single-window-app"></a><span data-ttu-id="91b9c-113">步骤 1 - 创建单窗口应用</span><span class="sxs-lookup"><span data-stu-id="91b9c-113">Step 1 - Create a single-window app</span></span>

<span data-ttu-id="91b9c-114">从包含单个主窗口的基本桌面项目开始。</span><span class="sxs-lookup"><span data-stu-id="91b9c-114">Start with a basic desktop project that contains a single main window.</span></span>  

1.  <span data-ttu-id="91b9c-115">In Visual Studio， choose **Windows Forms .NET Framework App**  >  **Next**.</span><span class="sxs-lookup"><span data-stu-id="91b9c-115">In Visual Studio, choose **Windows Forms .NET Framework App** > **Next**.</span></span>
    
    :::image type="complex" source="./media/winforms-new-project.png" alt-text="新建项目" lightbox="./media/winforms-new-project.png":::
       <span data-ttu-id="91b9c-117">新建项目</span><span class="sxs-lookup"><span data-stu-id="91b9c-117">New project</span></span>  
    :::image-end:::
    
1.  <span data-ttu-id="91b9c-118">输入 name 和**location Project\*\*\*\*的值**。</span><span class="sxs-lookup"><span data-stu-id="91b9c-118">Enter values for **Project name** and **Location**.</span></span>  <span data-ttu-id="91b9c-119">选择 **.NET Framework 4.6.2**或更高版本。</span><span class="sxs-lookup"><span data-stu-id="91b9c-119">Choose **.NET Framework 4.6.2** or later.</span></span>  
    
    :::image type="complex" source="./media/winforms-start-proj.png" alt-text="启动项目" lightbox="./media/winforms-start-proj.png":::
       <span data-ttu-id="91b9c-121">启动项目</span><span class="sxs-lookup"><span data-stu-id="91b9c-121">Start project</span></span>  
    :::image-end:::
    
1.  <span data-ttu-id="91b9c-122">若要创建项目，请选择"创建 **"。**</span><span class="sxs-lookup"><span data-stu-id="91b9c-122">To create your project, choose **Create**.</span></span>
    
## <a name="step-2---install-webview2-sdk"></a><span data-ttu-id="91b9c-123">步骤 2 - 安装 WebView2 SDK</span><span class="sxs-lookup"><span data-stu-id="91b9c-123">Step 2 - Install WebView2 SDK</span></span>

<span data-ttu-id="91b9c-124">使用 NuGet 将 WebView2 SDK 添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="91b9c-124">Use NuGet to add the WebView2 SDK to the project.</span></span>  

1.  <span data-ttu-id="91b9c-125">将鼠标悬停在项目上，打开上下文菜单 \ (右键单击\) ，然后选择"管理NuGet**包..."。**</span><span class="sxs-lookup"><span data-stu-id="91b9c-125">Hover on the project, open the contextual menu \(right-click\), and choose **Manage NuGet Packages...**.</span></span>  
    
    :::image type="complex" source="./media/wpf-getting-started-mng-nuget.png" alt-text="管理 NuGet 包":::
       <span data-ttu-id="91b9c-127">管理 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="91b9c-127">Manage NuGet Packages</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="91b9c-128">在搜索栏中，键入"> `Microsoft.Web.WebView2` **选择"Microsoft.Web.WebView2"。**</span><span class="sxs-lookup"><span data-stu-id="91b9c-128">In the search bar, type `Microsoft.Web.WebView2` > choose **Microsoft.Web.WebView2**.</span></span>  
    
    :::image type="complex" source="./media/install-nuget.png" alt-text="NuGet" lightbox="./media/install-nuget.png":::
       <span data-ttu-id="91b9c-130">NuGet</span><span class="sxs-lookup"><span data-stu-id="91b9c-130">NuGet</span></span>  
    :::image-end:::
    
    <span data-ttu-id="91b9c-131">开始使用 WebView2 API 开发应用。</span><span class="sxs-lookup"><span data-stu-id="91b9c-131">Start developing apps using the WebView2 API.</span></span>  <span data-ttu-id="91b9c-132">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-132">To build and run the project, select `F5`.</span></span>  <span data-ttu-id="91b9c-133">正在运行的项目显示一个空窗口。</span><span class="sxs-lookup"><span data-stu-id="91b9c-133">The running project displays an empty window.</span></span>  
    
    :::image type="complex" source="./media/winforms-empty-app.png" alt-text="空应用" lightbox="./media/winforms-empty-app.png":::
       <span data-ttu-id="91b9c-135">空应用</span><span class="sxs-lookup"><span data-stu-id="91b9c-135">Empty app</span></span>  
    :::image-end:::
    
## <a name="step-3---create-a-single-webview"></a><span data-ttu-id="91b9c-136">步骤 3 - 创建单个 WebView</span><span class="sxs-lookup"><span data-stu-id="91b9c-136">Step 3 - Create a single WebView</span></span>  

<span data-ttu-id="91b9c-137">将 WebView 添加到你的应用。</span><span class="sxs-lookup"><span data-stu-id="91b9c-137">Add a WebView to your app.</span></span>  

1.  <span data-ttu-id="91b9c-138">打开 **"Windows设计器"。**</span><span class="sxs-lookup"><span data-stu-id="91b9c-138">Open the **Windows Forms Designer**.</span></span>  
1.  <span data-ttu-id="91b9c-139">在工具箱**中搜索 WebView2。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="91b9c-139">Search for **WebView2** in the **Toolbox**.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="91b9c-140">如果使用的是 Visual Studio 2017，则**默认情况下 WebView2**可能不会显示在工具箱**中**。</span><span class="sxs-lookup"><span data-stu-id="91b9c-140">If you are using Visual Studio 2017, by default **WebView2** may not display in the **Toolbox**.</span></span>  <span data-ttu-id="91b9c-141">若要启用此行为，请选择"**工具**  >  **""** 选项  >  \*\*\*\*>"**自动填充工具箱**"设置设置为 `True` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-141">To enable the behavior, choose **Tools** > **Options** > **General** > set the **Automatically Populate Toolbox** setting to `True`.</span></span>  
    
    <span data-ttu-id="91b9c-142">将**WebView2 控件**拖放到 Windows Forms App。</span><span class="sxs-lookup"><span data-stu-id="91b9c-142">Drag and drop the **WebView2** control into the Windows Forms App.</span></span>
    
    :::image type="complex" source="./media/winforms-toolbox.png" alt-text="显示 WebView2 的工具箱":::
       <span data-ttu-id="91b9c-144">显示 WebView2 的工具箱</span><span class="sxs-lookup"><span data-stu-id="91b9c-144">Toolbox displaying WebView2</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="91b9c-145">将 `(Name)` 属性设置为 `webView`。</span><span class="sxs-lookup"><span data-stu-id="91b9c-145">Set the `(Name)` property to `webView`.</span></span>
    
    :::image type="complex" source="./media/winforms-properties.png" alt-text="WebView2 控件的属性":::
       <span data-ttu-id="91b9c-147">WebView2 控件的属性</span><span class="sxs-lookup"><span data-stu-id="91b9c-147">Properties of the WebView2 control</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="91b9c-148">属性 `Source` 设置 WebView2 控件中显示的初始 URI。</span><span class="sxs-lookup"><span data-stu-id="91b9c-148">The `Source` property sets the initial URI displayed in the WebView2 control.</span></span>  <span data-ttu-id="91b9c-149">将 `Source` 属性设置为 `https://www.microsoft.com`。</span><span class="sxs-lookup"><span data-stu-id="91b9c-149">Set the `Source` property to `https://www.microsoft.com`.</span></span>  
    
    :::image type="complex" source="./media/winforms-source.png" alt-text="WebView2 控件的 Source 属性":::
       <span data-ttu-id="91b9c-151">WebView2 控件的 **Source** 属性</span><span class="sxs-lookup"><span data-stu-id="91b9c-151">The **Source** property of the WebView2 control</span></span>
    :::image-end:::  

<span data-ttu-id="91b9c-152">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-152">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="91b9c-153">确保 WebView2 控件显示 [https://www.microsoft.com][|::ref1::|Main] 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-153">Ensure your WebView2 control displays [https://www.microsoft.com][|::ref1::|Main].</span></span>

:::image type="complex" source="./media/winforms-hello-webview.png" alt-text="hello webview" lightbox="./media/winforms-hello-webview.png":::
   <span data-ttu-id="91b9c-155">hello webview</span><span class="sxs-lookup"><span data-stu-id="91b9c-155">hello webview</span></span>  
:::image-end:::    

> [!NOTE]
> <span data-ttu-id="91b9c-156">如果正在处理高 DPI 监视器，可能需要将 Windows [Forms 应用配置为高 DPI 支持][DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport]。</span><span class="sxs-lookup"><span data-stu-id="91b9c-156">If you are working on a high DPI monitor, you may have to [configure your Windows Forms app for high DPI support][DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport].</span></span>  

## <a name="step-4---handle-window-resize-events"></a><span data-ttu-id="91b9c-157">步骤 4 - 处理窗口大小事件</span><span class="sxs-lookup"><span data-stu-id="91b9c-157">Step 4 - Handle Window Resize Events</span></span>  

<span data-ttu-id="91b9c-158">从工具箱向窗体中添加Windows控件，然后适当地处理窗口大小事件。</span><span class="sxs-lookup"><span data-stu-id="91b9c-158">Add a few more controls to your Windows Forms from the toolbox, and then handle window resize events appropriately.</span></span>  

1.  <span data-ttu-id="91b9c-159">在 **"Windows设计器"中**，打开"工具箱 **"。**</span><span class="sxs-lookup"><span data-stu-id="91b9c-159">In the **Windows Forms Designer**, open the **Toolbox**.</span></span>  
1.  <span data-ttu-id="91b9c-160">将**TextBox 拖放**到 Windows Forms 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="91b9c-160">Drag and Drop a **TextBox** into the Windows Forms App.</span></span>  <span data-ttu-id="91b9c-161">将 **"属性"选项卡中的 TextBox** `addressBar` **命名**。</span><span class="sxs-lookup"><span data-stu-id="91b9c-161">Name the **TextBox** `addressBar` in the **Properties Tab**.</span></span>  
1.  <span data-ttu-id="91b9c-162">将**按钮拖放到**Windows Forms 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="91b9c-162">Drag and Drop a **Button** into the Windows Forms App.</span></span>  <span data-ttu-id="91b9c-163">将"按钮"中的**文本** `Go!` 更改为 ，并\*\*\*\* 命名"属性"选项卡 `goButton` **中的"按钮"。**</span><span class="sxs-lookup"><span data-stu-id="91b9c-163">Change the text in the **Button** to `Go!` and name the **Button** `goButton` in the **Properties Tab**.</span></span>  
    
    <span data-ttu-id="91b9c-164">应用应如设计器中的下图所示。</span><span class="sxs-lookup"><span data-stu-id="91b9c-164">The app should look like the following image in the designer.</span></span>  
    
    :::image type="complex" source="./media/winforms-designer.png" alt-text="WinForms 设计器" lightbox="./media/winforms-designer.png":::
       <span data-ttu-id="91b9c-166">WinForms 设计器</span><span class="sxs-lookup"><span data-stu-id="91b9c-166">WinForms designer</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="91b9c-167">在 `Form1.cs` 文件中，定义 `Form_Resize` 以在调整应用窗口大小时保持控件就位。</span><span class="sxs-lookup"><span data-stu-id="91b9c-167">In the `Form1.cs` file, define `Form_Resize` to keep the controls in place when the App Window is resized.</span></span>
    
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

<span data-ttu-id="91b9c-168">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-168">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="91b9c-169">确保应用显示类似于以下屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="91b9c-169">Ensure the app displays similar to the following screenshot.</span></span>

:::image type="complex" source="./media/winforms-app.png" alt-text="应用" lightbox="./media/winforms-app.png":::
   <span data-ttu-id="91b9c-171">应用</span><span class="sxs-lookup"><span data-stu-id="91b9c-171">App</span></span>  
:::image-end:::  

## <a name="step-5---navigation"></a><span data-ttu-id="91b9c-172">步骤 5 - 导航</span><span class="sxs-lookup"><span data-stu-id="91b9c-172">Step 5 - Navigation</span></span>

<span data-ttu-id="91b9c-173">添加允许用户通过向应用添加地址栏来更改 WebView2 控件显示的 URL 的能力。</span><span class="sxs-lookup"><span data-stu-id="91b9c-173">Add the ability to allow users to change the URL that the WebView2 control displays by adding an address bar to the app.</span></span>  

1.  <span data-ttu-id="91b9c-174">选择 `F5` 以生成并运行项目。</span><span class="sxs-lookup"><span data-stu-id="91b9c-174">Select `F5` to build and run your project.</span></span>  <span data-ttu-id="91b9c-175">确认应用显示类似于以下屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="91b9c-175">Confirm that the app displays similar to the following screenshot.</span></span>  
    
    :::image type="complex" source="./media/winforms-app.png" alt-text="WinForms 应用" lightbox="./media/winforms-app.png":::
       <span data-ttu-id="91b9c-177">WinForms 应用</span><span class="sxs-lookup"><span data-stu-id="91b9c-177">WinForms App</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="91b9c-178">在 `Form1.cs` 文件中，若要添加 `CoreWebView2` 命名空间，请将以下代码段插入顶部。</span><span class="sxs-lookup"><span data-stu-id="91b9c-178">In the `Form1.cs`file, to add the `CoreWebView2` namespace, insert the following code snippet at the top.</span></span>  
1.  <span data-ttu-id="91b9c-179">在 `Form1.cs` 添加 `CoreWebView2` 命名空间时，在 的顶部插入以下代码段 `Form1.cs` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-179">In `Form1.cs` add the `CoreWebView2` namespace by inserting the following code snippet at the top of `Form1.cs`.</span></span>  
    
    ```csharp
    using Microsoft.Web.WebView2.Core;
    ```
    
1.  <span data-ttu-id="91b9c-180">在 **"Windows设计器**"中，双击按钮 `Go!` 以 `goButton_Click` 在文件中创建 `Form1.cs` 方法。</span><span class="sxs-lookup"><span data-stu-id="91b9c-180">In the **Windows Forms Designer**, double-click on the `Go!` button to create the `goButton_Click` method in the `Form1.cs` file.</span></span>  <span data-ttu-id="91b9c-181">复制以下代码段并将其粘贴到 函数中。</span><span class="sxs-lookup"><span data-stu-id="91b9c-181">Copy and paste the following snippet inside the function.</span></span>  <span data-ttu-id="91b9c-182">现在， `goButton_Click` 函数将 WebView 导航到地址栏中输入的 URL。</span><span class="sxs-lookup"><span data-stu-id="91b9c-182">Now, the `goButton_Click` function navigates the WebView to the URL entered in the address bar.</span></span>
    
    ```csharp
    private void goButton_Click(object sender, EventArgs e)
    {
        if (webView != null && webView.CoreWebView2 != null)
        {
            webView.CoreWebView2.Navigate(addressBar.Text);
        }
    }
    ```  
    
<span data-ttu-id="91b9c-183">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-183">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="91b9c-184">在地址栏中输入新 URL，然后选择"转到 **"。**</span><span class="sxs-lookup"><span data-stu-id="91b9c-184">Enter a new URL in the address bar, and select **Go**.</span></span>  <span data-ttu-id="91b9c-185">例如，输入 `https://www.bing.com` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-185">For example, enter `https://www.bing.com`.</span></span>  <span data-ttu-id="91b9c-186">确保 WebView2 控件导航到 URL。</span><span class="sxs-lookup"><span data-stu-id="91b9c-186">Ensure the WebView2 control navigates to the URL.</span></span>  

> [!NOTE]
> <span data-ttu-id="91b9c-187">确保在地址栏中输入完整 URL。</span><span class="sxs-lookup"><span data-stu-id="91b9c-187">Ensure a complete URL is entered in the address bar.</span></span>  <span data-ttu-id="91b9c-188">如果 `ArgumentException` URL 不以 或 为起始，则 `http://` 会引发 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-188">An `ArgumentException` is thrown if the URL does not start with `http://` or</span></span> `https://`

:::image type="complex" source="./media/winforms-bing.png" alt-text="bing.com" lightbox="./media/winforms-bing.png":::
   <span data-ttu-id="91b9c-190">bing.com</span><span class="sxs-lookup"><span data-stu-id="91b9c-190">bing.com</span></span>  
:::image-end:::  

## <a name="step-6---navigation-events"></a><span data-ttu-id="91b9c-191">步骤 6 - 导航事件</span><span class="sxs-lookup"><span data-stu-id="91b9c-191">Step 6 - Navigation events</span></span>  

<span data-ttu-id="91b9c-192">在网页导航期间，WebView2 控件将引发事件。</span><span class="sxs-lookup"><span data-stu-id="91b9c-192">During webpage navigation, the WebView2 control raises events.</span></span>  <span data-ttu-id="91b9c-193">承载 WebView2 控件的应用侦听以下事件。</span><span class="sxs-lookup"><span data-stu-id="91b9c-193">The app that hosts WebView2 controls listens for the following events.</span></span>  

*   `NavigationStarting`  
*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
*   `NavigationCompleted`  
    
<span data-ttu-id="91b9c-194">有关详细信息，请导航到["导航事件"。][Webview2ConceptsNavigationEvents]</span><span class="sxs-lookup"><span data-stu-id="91b9c-194">For more information, navigate to [Navigation Events][Webview2ConceptsNavigationEvents].</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="导航事件":::
   <span data-ttu-id="91b9c-196">导航事件</span><span class="sxs-lookup"><span data-stu-id="91b9c-196">Navigation events</span></span>
:::image-end:::

<span data-ttu-id="91b9c-197">发生错误时，将引发以下事件，并可能依赖于导航到错误网页。</span><span class="sxs-lookup"><span data-stu-id="91b9c-197">When an error occurs, the following events are raised and may depend on navigation to an error webpage.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`  
    
> [!NOTE]
> <span data-ttu-id="91b9c-198">如果发生 HTTP 重定向，则一行 `NavigationStarting` 中有多个事件。</span><span class="sxs-lookup"><span data-stu-id="91b9c-198">If an HTTP redirect occurs, there are multiple `NavigationStarting` events in a row.</span></span>  

<span data-ttu-id="91b9c-199">若要演示如何使用事件，请首先注册一个处理程序，以取消不使用 `NavigationStarting` HTTPS 的任何请求。</span><span class="sxs-lookup"><span data-stu-id="91b9c-199">To demonstrate how to use the events, start by registering a handler for `NavigationStarting` that cancels any requests not using HTTPS.</span></span>  

<span data-ttu-id="91b9c-200">在 `Form1.cs` 文件中，更新构造函数以匹配以下代码段并添加 `EnsureHttps` 函数。</span><span class="sxs-lookup"><span data-stu-id="91b9c-200">In the `Form1.cs` file, update the constructor to match the following code snippet and add the `EnsureHttps` function.</span></span>  

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

<span data-ttu-id="91b9c-201">在构造函数中 `EnsureHttps` ，注册为 WebView2 控件上事件 `NavigationStarting` 的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="91b9c-201">In the constructor, `EnsureHttps` is registered as the event handler on the `NavigationStarting` event on the WebView2 control.</span></span>  

<span data-ttu-id="91b9c-202">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-202">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="91b9c-203">确保导航到 HTTP 网站时，WebView 保持不变。</span><span class="sxs-lookup"><span data-stu-id="91b9c-203">Ensure when navigating to an HTTP site, the WebView remains unchanged.</span></span>  <span data-ttu-id="91b9c-204">但是，WebView 将导航到 HTTPS 网站。</span><span class="sxs-lookup"><span data-stu-id="91b9c-204">However, the WebView will navigate to HTTPS sites.</span></span>

## <a name="step-7---scripting"></a><span data-ttu-id="91b9c-205">步骤 7 - 脚本</span><span class="sxs-lookup"><span data-stu-id="91b9c-205">Step 7 - Scripting</span></span>  

<span data-ttu-id="91b9c-206">你可以在运行时使用主机应用将 JavaScript 代码注入 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="91b9c-206">You may use host apps to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="91b9c-207">你可以任务 WebView 运行任意 JavaScript 或添加初始化脚本。</span><span class="sxs-lookup"><span data-stu-id="91b9c-207">You may task WebView to run arbitrary JavaScript or add initialization scripts.</span></span>  <span data-ttu-id="91b9c-208">在删除 JavaScript 之前，注入的 JavaScript 适用于所有新的顶级文档和任何子框架。</span><span class="sxs-lookup"><span data-stu-id="91b9c-208">The injected JavaScript applies to all new top-level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="91b9c-209">注入的 JavaScript 以特定计时运行。</span><span class="sxs-lookup"><span data-stu-id="91b9c-209">The injected JavaScript is run with specific timing.</span></span>  

*   <span data-ttu-id="91b9c-210">创建全局对象后运行它。</span><span class="sxs-lookup"><span data-stu-id="91b9c-210">Run it after the creation of the global object.</span></span>  
*   <span data-ttu-id="91b9c-211">在运行 HTML 文档中包含的任何其他脚本之前运行它。</span><span class="sxs-lookup"><span data-stu-id="91b9c-211">Run it before any other script included in the HTML document is run.</span></span>  
    
<span data-ttu-id="91b9c-212">例如，添加在用户导航到非 HTTPS 网站时发送警报的脚本。</span><span class="sxs-lookup"><span data-stu-id="91b9c-212">As an example, add scripts that send an alert when a user navigates to non-HTTPS sites.</span></span>  <span data-ttu-id="91b9c-213">修改 `EnsureHttps` 函数以将脚本注入到使用 [ExecuteScriptAsync][DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync] 方法的 Web 内容中。</span><span class="sxs-lookup"><span data-stu-id="91b9c-213">Modify the `EnsureHttps` function to inject a script into the web content that uses [ExecuteScriptAsync][DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync] method.</span></span>  

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

<span data-ttu-id="91b9c-214">若要生成并运行项目，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-214">To build and run your project, select `F5`.</span></span>  <span data-ttu-id="91b9c-215">当你导航到不使用 HTTPS 的网站时，请确保应用显示一个警报。</span><span class="sxs-lookup"><span data-stu-id="91b9c-215">Ensure the app displays an alert when you navigate to a website that doesn't use HTTPS.</span></span>  

:::image type="complex" source="./media/winforms-https.png" alt-text="https" lightbox="./media/winforms-https.png":::
   <span data-ttu-id="91b9c-217">https</span><span class="sxs-lookup"><span data-stu-id="91b9c-217">https</span></span>  
:::image-end:::  

## <a name="step-8---communication-between-host-and-web-content"></a><span data-ttu-id="91b9c-218">步骤 8 - 主机和 Web 内容之间的通信</span><span class="sxs-lookup"><span data-stu-id="91b9c-218">Step 8 - Communication between host and web content</span></span>  

<span data-ttu-id="91b9c-219">主机和 Web 内容可能 `postMessage` 用于相互通信，如下所示：</span><span class="sxs-lookup"><span data-stu-id="91b9c-219">The host and web content may use `postMessage` to communicate with each other as follows:</span></span>  

*   <span data-ttu-id="91b9c-220">WebView2 控件中的 Web 内容可能 `window.chrome.webview.postMessage` 用于向主机发布消息。</span><span class="sxs-lookup"><span data-stu-id="91b9c-220">Web content in a WebView2 control may use `window.chrome.webview.postMessage` to post a message to the host.</span></span>  <span data-ttu-id="91b9c-221">主机使用主机上注册的任何消息 `WebMessageReceived` 处理邮件。</span><span class="sxs-lookup"><span data-stu-id="91b9c-221">The host handles the message using any registered `WebMessageReceived` on the host.</span></span>  
*   <span data-ttu-id="91b9c-222">使用 或 将消息张贴到 WebView2 控件中的 `CoreWebView2.PostWebMessageAsString` Web 内容 `CoreWebView2.PostWebMessageAsJSON` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-222">Hosts post messages to web content in a WebView2 control using `CoreWebView2.PostWebMessageAsString` or `CoreWebView2.PostWebMessageAsJSON`.</span></span>  <span data-ttu-id="91b9c-223">添加到 的处理程序会捕获这些消息 `window.chrome.webview.addEventListener` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-223">These messages are caught by handlers added to `window.chrome.webview.addEventListener`.</span></span>  
    
<span data-ttu-id="91b9c-224">通信机制使用本机功能将来自 Web 内容的消息传递给主机。</span><span class="sxs-lookup"><span data-stu-id="91b9c-224">The communication mechanism passes messages from web content to the host using native capabilities.</span></span>  

<span data-ttu-id="91b9c-225">在项目中，当 WebView2 控件导航到 URL 时，它会在地址栏中显示 URL，并通知用户 WebView2 控件中显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="91b9c-225">In your project, when the WebView2 control navigates to a URL, it displays the URL in the address bar and alerts the user of the URL displayed in the WebView2 control.</span></span>  

1.  <span data-ttu-id="91b9c-226">在 `Form1.cs` 文件中，更新构造函数并创建 `InitializeAsync` 一个函数以匹配以下代码段。</span><span class="sxs-lookup"><span data-stu-id="91b9c-226">In the `Form1.cs` file, update your constructor and create an `InitializeAsync` function to match the following code snippet.</span></span>  <span data-ttu-id="91b9c-227">函数 `InitializeAsync` awaits [EnsureCoreWebView2Async，][DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async] 因为 的初始化 `CoreWebView2` 是异步的。</span><span class="sxs-lookup"><span data-stu-id="91b9c-227">The `InitializeAsync` function awaits [EnsureCoreWebView2Async][DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async] because the initialization of `CoreWebView2` is asynchronous.</span></span>  
    
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
    
1.  <span data-ttu-id="91b9c-228">初始化 `CoreWebView2` 后，注册事件处理程序以响应 `WebMessageReceived` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-228">After `CoreWebView2` is initialized, register an event handler to respond to `WebMessageReceived`.</span></span>  <span data-ttu-id="91b9c-229">在 `Form1.cs` 文件中， `InitializeAsync` 使用下面的代码 `UpdateAddressBar` 段更新和添加。</span><span class="sxs-lookup"><span data-stu-id="91b9c-229">In the `Form1.cs` file, update `InitializeAsync` and add `UpdateAddressBar` using the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="91b9c-230">为了使 WebView 能够发送和响应 Web 消息，在初始化后，主机将 Web 内容中的脚本注入 `CoreWebView2` 到：</span><span class="sxs-lookup"><span data-stu-id="91b9c-230">In order for the WebView to send and respond to the web message, after `CoreWebView2` is initialized, the host injects a script in the web content to:</span></span>  
    1.  <span data-ttu-id="91b9c-231">使用 将 URL 发送到主机 `postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-231">Send the URL to the host using `postMessage`.</span></span>
    1.  <span data-ttu-id="91b9c-232">注册事件处理程序以打印从主机发送的消息。</span><span class="sxs-lookup"><span data-stu-id="91b9c-232">Register an event handler to print a message sent from the host.</span></span>  
        
<span data-ttu-id="91b9c-233">在 `Form1.cs` 文件中，进行更新 `InitializeAsync` 以匹配以下代码段。</span><span class="sxs-lookup"><span data-stu-id="91b9c-233">In the `Form1.cs` file, update `InitializeAsync` to match the following code snippet.</span></span>  

```csharp
async void InitializeAsync()
{
    await webView.EnsureCoreWebView2Async(null);
    webView.CoreWebView2.WebMessageReceived += UpdateAddressBar;

    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.postMessage(window.document.URL);");
    await webView.CoreWebView2.AddScriptToExecuteOnDocumentCreatedAsync("window.chrome.webview.addEventListener(\'message\', event => alert(event.data));");
}
```  

<span data-ttu-id="91b9c-234">若要生成并运行应用，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="91b9c-234">To build and run the app, select `F5`.</span></span>  <span data-ttu-id="91b9c-235">现在，地址栏在 WebView2 控件中显示 URI。</span><span class="sxs-lookup"><span data-stu-id="91b9c-235">Now, the address bar displays the URI in the WebView2 control.</span></span>  <span data-ttu-id="91b9c-236">此外，当你成功导航到新 URL 时，WebView 会向用户通知 WebView 中显示的 URL。</span><span class="sxs-lookup"><span data-stu-id="91b9c-236">Also, when you successfully navigate to a new URL, the WebView alerts the user of the URL displayed in the WebView.</span></span>  

:::image type="complex" source="./media/winforms-final-app.png" alt-text="最终应用" lightbox="./media/winforms-final-app.png":::
   <span data-ttu-id="91b9c-238">最终应用</span><span class="sxs-lookup"><span data-stu-id="91b9c-238">Final app</span></span>  
:::image-end:::  

<span data-ttu-id="91b9c-239">恭喜！你生成了第一个 WebView2 应用。</span><span class="sxs-lookup"><span data-stu-id="91b9c-239">Congratulations, you built your first WebView2 app.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="91b9c-240">后续步骤</span><span class="sxs-lookup"><span data-stu-id="91b9c-240">Next steps</span></span>  

<span data-ttu-id="91b9c-241">若要继续了解有关 WebView2 的更多内容，请导航到以下资源。</span><span class="sxs-lookup"><span data-stu-id="91b9c-241">To continue learning more about WebView2, navigate to the following resources.</span></span>  

*   <span data-ttu-id="91b9c-242">若要了解有关生成 WebView2 应用程序的信息，请导航到 [WebView2 开发最佳做法][WV2BestPractices]。</span><span class="sxs-lookup"><span data-stu-id="91b9c-242">To learn more about building WebView2 applications, navigate to [WebView2 development best practices][WV2BestPractices].</span></span>  
*   <span data-ttu-id="91b9c-243">有关 WebView2 功能的综合示例，请导航到 [WebView2Samples][GithubMicrosoftedgeWebview2samplesMain]。</span><span class="sxs-lookup"><span data-stu-id="91b9c-243">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples][GithubMicrosoftedgeWebview2samplesMain].</span></span>  
*   <span data-ttu-id="91b9c-244">有关 WebView2 的信息，请导航到["WebView2 资源"。][Webview2IndexNextSteps]</span><span class="sxs-lookup"><span data-stu-id="91b9c-244">For more information about WebView2, navigate to [WebView2 Resources][Webview2IndexNextSteps].</span></span>  
*   <span data-ttu-id="91b9c-245">有关 WebView2 API 的详细信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2WinformsWebview2]。</span><span class="sxs-lookup"><span data-stu-id="91b9c-245">For detailed information about the WebView2 API, navigate to [API reference][DotnetApiMicrosoftWebWebview2WinformsWebview2].</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="91b9c-246">与 WebView 团队Microsoft Edge联系</span><span class="sxs-lookup"><span data-stu-id="91b9c-246">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[WV2BestPractices]: ../concepts/developer-guide.md "WebView2 开发最佳实践|Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "下一步 - WebView2 Microsoft Edge预览 (简介) |Microsoft Docs"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "导航事件|Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2Winforms]: /dotnet/api/microsoft.web.webview2.winforms "Microsoft.Web.WebView2.WinForms 命名空间|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2]: /dotnet/api/microsoft.web.webview2.winforms.webview2 "WebView2 类|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Ensurecorewebview2async]: /dotnet/api/microsoft.web.webview2.winforms.webview2.ensurecorewebview2async "WebView2.EnsureCoreWebView2Async (CoreWebView2Environment) 方法|Microsoft Docs"  
[DotnetApiMicrosoftWebWebview2WinformsWebview2Executescriptasync]: /dotnet/api/microsoft.web.webview2.winforms.webview2.executescriptasync "WebView2.ExecuteScriptAsync (String) 方法|Microsoft Docs"  

[DotnetFrameworkWinformsHighDpiSupportWindowsFormsConfiguringYourWindowsFormsAppForHighDpiSupport]: /dotnet/framework/winforms/high-dpi-support-in-windows-forms#configuring-your-windows-forms-app-for-high-dpi-support "Configuring your Windows Forms app for high DPI support - Windows Forms |Microsoft Docs"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 |Microsoft Edge开发人员"  

[MicrosoftMain]: https://www.microsoft.com "Microsoft"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  
