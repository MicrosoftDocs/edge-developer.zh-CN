---
description: 适用于 Win32 应用的 WebView2 入门指南
title: 适用于 Win32 应用的 WebView2 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 20d830e2c8b95213b223da46f9afd9f69a137946
ms.sourcegitcommit: af91bfc3e6d8afc51f0fbbc0fe392262f424225c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2020
ms.locfileid: "11120380"
---
# <span data-ttu-id="07bf2-104">WebView2 入门</span><span class="sxs-lookup"><span data-stu-id="07bf2-104">Getting started with WebView2</span></span>  

<span data-ttu-id="07bf2-105">以下内容将指导你完成 [WebView2][Webview2Index] 的常用功能，并提供了创建你的第一个 WebView2 应用的起始点。</span><span class="sxs-lookup"><span data-stu-id="07bf2-105">The following content walks you through the commonly used functionalities of [WebView2][Webview2Index] and provides a starting point for creating your first WebView2 app.</span></span>  <span data-ttu-id="07bf2-106">有关单个 WebView2 Api 的详细信息，请参阅 [API 参考][Webview2ReferenceWin32]。</span><span class="sxs-lookup"><span data-stu-id="07bf2-106">For more information about individual WebView2 APIs, see [API reference][Webview2ReferenceWin32].</span></span>  

## <span data-ttu-id="07bf2-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="07bf2-107">Prerequisites</span></span>  

*   <span data-ttu-id="07bf2-108">[WebView2 运行时][Webview2Installer] 或任何 Microsoft Edge (Chromium 在支持的操作系统 \ (当前 windows 10、windows 8.1 和 windows 7 \ ) 上安装了 [) 非稳定通道][MicrosoftedgeinsiderDownload] 。</span><span class="sxs-lookup"><span data-stu-id="07bf2-108">[WebView2 Runtime][Webview2Installer] or any [Microsoft Edge (Chromium) non-stable channel][MicrosoftedgeinsiderDownload] installed on supported OS \(currently Windows 10, Windows 8.1, and Windows 7\).</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="07bf2-109">Web 视图团队建议使用 "82.0.488.0" 通道，并且所需的最低版本是 ""。</span><span class="sxs-lookup"><span data-stu-id="07bf2-109">The WebView team recommends using the Canary channel and the minimum required version is 82.0.488.0.</span></span>  
    
*   <span data-ttu-id="07bf2-110">安装了 c + + 支持的[Visual Studio][MicrosoftVisualstudioMain] 2015 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="07bf2-110">[Visual Studio][MicrosoftVisualstudioMain] 2015 or later with C++ support installed.</span></span>  

## <span data-ttu-id="07bf2-111">步骤 1-创建单窗口 win32 应用程序</span><span class="sxs-lookup"><span data-stu-id="07bf2-111">Step 1 - Create a single-window win32 app</span></span>  

<span data-ttu-id="07bf2-112">从包含单个主窗口的基本桌面项目开始。</span><span class="sxs-lookup"><span data-stu-id="07bf2-112">Start with a basic desktop project that contains a single main window.</span></span>  <span data-ttu-id="07bf2-113">为了更好地重点介绍本演练，你使用的是示例中的修改后的示例代码：为你的示例应用 [创建一个传统的 Windows 桌面应用程序 (c + +) ][CppWindowsWalkthroughCreatingDesktopApplication] 。</span><span class="sxs-lookup"><span data-stu-id="07bf2-113">To better focus the walkthrough, you are using modified sample code from [Walkthrough: Create a traditional Windows Desktop application (C++)][CppWindowsWalkthroughCreatingDesktopApplication] for your sample app.</span></span>  <span data-ttu-id="07bf2-114">若要下载修改后的示例并开始使用，请导航到 [WebView2 示例][GithubMicrosoftedgeWebview2samplesGettingStartedGuide]。</span><span class="sxs-lookup"><span data-stu-id="07bf2-114">To download the modified sample and get started, navigate to [WebView2 Samples][GithubMicrosoftedgeWebview2samplesGettingStartedGuide].</span></span>  

<span data-ttu-id="07bf2-115">在 Visual Studio 中，打开 `WebView2GettingStarted.sln` 。</span><span class="sxs-lookup"><span data-stu-id="07bf2-115">In Visual Studio, open `WebView2GettingStarted.sln`.</span></span>  <span data-ttu-id="07bf2-116">如果使用的是早期版本的 Visual Studio，请将鼠标悬停在 **WebView2GettingStarted** 项目上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **属性**"。</span><span class="sxs-lookup"><span data-stu-id="07bf2-116">If you are using an older version of Visual Studio, hover on the **WebView2GettingStarted** project, open the contextual menu \(right-click\), and select **Properties**.</span></span>  <span data-ttu-id="07bf2-117">在 "**配置属性**" 下的 "  >  **常规**" 下，修改**Windows SDK 版本**和**平台工具集**以使用 Win10 SDK 和 Visual Studio 工具集 \ (VS 工具集 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="07bf2-117">Under **Configuration Properties** > **General**, modify **Windows SDK Version** and **Platform Toolset** to use the Win10 SDK and Visual Studio toolset \(VS toolset\) available to you.</span></span>  

:::image type="complex" source="../media/tool-version.png" alt-text="工具版本" lightbox="../media/tool-version.png":::
   <span data-ttu-id="07bf2-119">工具版本</span><span class="sxs-lookup"><span data-stu-id="07bf2-119">Tool version</span></span>  
:::image-end:::  

<span data-ttu-id="07bf2-120">Visual Studio 可能会显示一些错误，因为缺少 WebView2 头文件，该文件应在步骤2完成后消失。</span><span class="sxs-lookup"><span data-stu-id="07bf2-120">Visual Studio may show some errors because of the missing WebView2 header file, which should go away after Step 2 is completed.</span></span>  

## <span data-ttu-id="07bf2-121">步骤 2-安装 WebView2 SDK</span><span class="sxs-lookup"><span data-stu-id="07bf2-121">Step 2 - Install WebView2 SDK</span></span>  

<span data-ttu-id="07bf2-122">将 WebView2 SDK 添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="07bf2-122">Add the WebView2 SDK into the project.</span></span>  <span data-ttu-id="07bf2-123">你可以使用 NuGet 安装 Win32 SDK。</span><span class="sxs-lookup"><span data-stu-id="07bf2-123">You may install the Win32 SDK using NuGet.</span></span>  

1.  <span data-ttu-id="07bf2-124">将鼠标悬停在项目上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **管理 NuGet 程序包**"。</span><span class="sxs-lookup"><span data-stu-id="07bf2-124">Hover on the project, open the contextual menu \(right-click\), and select **Manage NuGet Packages**.</span></span>  
    
    :::image type="complex" source="../media/manage-nuget-packages.png" alt-text="工具版本" lightbox="../media/manage-nuget-packages.png":::
       <span data-ttu-id="07bf2-126">管理 NuGet 程序包</span><span class="sxs-lookup"><span data-stu-id="07bf2-126">Manage NuGet packages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="07bf2-127">安装 Windows 实现库。</span><span class="sxs-lookup"><span data-stu-id="07bf2-127">Install the Windows Implementation Library.</span></span>  
    1.  <span data-ttu-id="07bf2-128">`Microsoft.Windows.ImplementationLibrary`在搜索栏中输入 "ImplementationLibrary"，从结果中选择 "**微软**"，然后在右侧窗口中选择 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="07bf2-128">Enter `Microsoft.Windows.ImplementationLibrary` in the search bar, select **Microsoft.Windows.ImplementationLibrary** from the results, and select **Install** in the right-hand side window.</span></span>  <span data-ttu-id="07bf2-129">NuGet 将 SDK 下载到您的计算机。</span><span class="sxs-lookup"><span data-stu-id="07bf2-129">NuGet downloads the SDK to your machine.</span></span>  
        
        > [!NOTE] 
        > <span data-ttu-id="07bf2-130">[Windows 实现库][GithubMicrosoftWilMain]和[Windows 运行时 c + + 模板库][CppCxWrlTemplateLibraryVS2019]是可选的，并且已添加以使该示例更易于使用 COM。</span><span class="sxs-lookup"><span data-stu-id="07bf2-130">The [Windows Implementation Library][GithubMicrosoftWilMain] and [Windows Runtime C++ Template Library][CppCxWrlTemplateLibraryVS2019] are optional and were added to make working with COM easier for the example.</span></span>  
        
        :::image type="complex" source="../media/wil.png" alt-text="工具版本" lightbox="../media/wil.png":::
           <span data-ttu-id="07bf2-132">Windows 实现库</span><span class="sxs-lookup"><span data-stu-id="07bf2-132">Windows Implementation Library</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="07bf2-133">安装 WebView2 SDK。</span><span class="sxs-lookup"><span data-stu-id="07bf2-133">Install the WebView2 SDK.</span></span>  
    1.  <span data-ttu-id="07bf2-134">`Microsoft.Web.WebView2`在搜索栏中输入 "WebView2"，从结果中选择 "**微软**"，然后在右侧窗口中选择 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="07bf2-134">Enter `Microsoft.Web.WebView2` in the search bar, select **Microsoft.Web.WebView2** from the results, and select **Install** in the right-hand side window.</span></span>  <span data-ttu-id="07bf2-135">NuGet 将 SDK 下载到您的计算机。</span><span class="sxs-lookup"><span data-stu-id="07bf2-135">NuGet downloads the SDK to your machine.</span></span>  
        
        :::image type="complex" source="../media/nuget.png" alt-text="工具版本" lightbox="../media/nuget.png":::
           <span data-ttu-id="07bf2-137">Nuget 程序包管理器</span><span class="sxs-lookup"><span data-stu-id="07bf2-137">Nuget Package Manager</span></span>
        :::image-end:::  
        
1.  <span data-ttu-id="07bf2-138">将 WebView2 标头添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="07bf2-138">Add WebView2 header to your project.</span></span>  
    :::row:::
       :::column span="1":::
          <span data-ttu-id="07bf2-139">打开 `HelloWebView.cpp` 、复制以下代码片段并粘贴到 `HelloWebView.cpp` 最后一行后 `#include` 。</span><span class="sxs-lookup"><span data-stu-id="07bf2-139">Open `HelloWebView.cpp`, copy the following code snippet and paste into `HelloWebView.cpp` after last `#include` line.</span></span>  
          
          ```cpp
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
       :::column span="1":::
          <span data-ttu-id="07bf2-140">"包含" 部分应类似于以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="07bf2-140">The include section should look similar to the following code snippet.</span></span>  
          
          ```cpp
          ...
          #include <wrl.h>
          #include <wil/com.h>
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
    :::row-end:::
    
<span data-ttu-id="07bf2-141">你已设置为对 WebView2 API 使用和构建。</span><span class="sxs-lookup"><span data-stu-id="07bf2-141">You are all set to use and build against the WebView2 API.</span></span>  

### <span data-ttu-id="07bf2-142">构建空示例应用</span><span class="sxs-lookup"><span data-stu-id="07bf2-142">Build your empty sample app</span></span>  

<span data-ttu-id="07bf2-143">选择 `F5` 以生成并运行示例应用。</span><span class="sxs-lookup"><span data-stu-id="07bf2-143">Select `F5` to build and run the sample app.</span></span>  <span data-ttu-id="07bf2-144">此时将显示一个应用，显示一个空窗口。</span><span class="sxs-lookup"><span data-stu-id="07bf2-144">An app displaying an empty window appears.</span></span>  

:::image type="complex" source="../media/empty-app.png" alt-text="工具版本" lightbox="../media/empty-app.png":::
   <span data-ttu-id="07bf2-146">空应用</span><span class="sxs-lookup"><span data-stu-id="07bf2-146">Empty app</span></span>  
:::image-end:::  

## <span data-ttu-id="07bf2-147">步骤 3-在父窗口中创建单个 Web 视图</span><span class="sxs-lookup"><span data-stu-id="07bf2-147">Step 3 - Create a single WebView within the parent window</span></span>  

<span data-ttu-id="07bf2-148">将 Web 视图添加到主窗口。</span><span class="sxs-lookup"><span data-stu-id="07bf2-148">Add a WebView to the main window.</span></span>  <span data-ttu-id="07bf2-149">使用 `CreateCoreWebView2Environment` 方法设置环境并找到 Microsoft Edge \ (Chromium \ ) 浏览器为控件供电。</span><span class="sxs-lookup"><span data-stu-id="07bf2-149">Use the `CreateCoreWebView2Environment` method to set up the environment and locate the Microsoft Edge \(Chromium\) browser powering the control.</span></span>  <span data-ttu-id="07bf2-150">`CreateCoreWebView2EnvironmentWithOptions`如果你希望指定浏览器位置、用户文件夹、浏览器标记等，而不是使用默认设置，也可以使用该方法。</span><span class="sxs-lookup"><span data-stu-id="07bf2-150">You may also use the `CreateCoreWebView2EnvironmentWithOptions` method if you want to specify browser location, user folder, browser flags, and so on, instead of using the default setting.</span></span>  <span data-ttu-id="07bf2-151">完成该 `CreateCoreWebView2Environment` 方法后，你可以在 `ICoreWebView2Environment::CreateCoreWebView2Controller` 回调内运行该方法 `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` ，然后运行该 `ICoreWebView2Controller::get_CoreWebView2` 方法以获取关联的 web 视图。</span><span class="sxs-lookup"><span data-stu-id="07bf2-151">Upon the completion of the `CreateCoreWebView2Environment` method, you are able to run the `ICoreWebView2Environment::CreateCoreWebView2Controller` method inside the `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` callback and run the `ICoreWebView2Controller::get_CoreWebView2` method to get the associated WebView.</span></span>  

<span data-ttu-id="07bf2-152">在回调中，设置一些其他设置，调整 Web 视图大小以占用父窗口的100%，然后导航到 Bing。</span><span class="sxs-lookup"><span data-stu-id="07bf2-152">In the callback, set a few additional settings, resize the WebView to take 100% of the parent window, and navigate to Bing.</span></span>  

<span data-ttu-id="07bf2-153">复制以下代码片段，并将 `HelloWebView.cpp` 其粘贴到 `// <-- WebView2 sample code starts here -->` 笔记之后和注释之前 `// <-- WebView2 sample code ends here -->` 。</span><span class="sxs-lookup"><span data-stu-id="07bf2-153">Copy the following code snippet and paste into `HelloWebView.cpp` after the `// <-- WebView2 sample code starts here -->` note and before the `// <-- WebView2 sample code ends here -->` note.</span></span>  

```cpp
// Step 3 - Create a single WebView within the parent window
// Locate the browser and set up the environment for WebView
CreateCoreWebView2EnvironmentWithOptions(nullptr, nullptr, nullptr,
    Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
        [hWnd](HRESULT result, ICoreWebView2Environment* env) -> HRESULT {
        
            // Create a CoreWebView2Controller and get the associated CoreWebView2 whose parent is the main window hWnd
            env->CreateCoreWebView2Controller(hWnd, Callback<ICoreWebView2CreateCoreWebView2ControllerCompletedHandler>(
                [hWnd](HRESULT result, ICoreWebView2Controller* controller) -> HRESULT {
                if (controller != nullptr) {
                    webviewController = controller;
                    webviewController->get_CoreWebView2(&webviewWindow);
                }
                
                // Add a few settings for the webview
                // The demo step is redundant since the values are the default settings
                ICoreWebView2Settings* Settings;
                webviewWindow->get_Settings(&Settings);
                Settings->put_IsScriptEnabled(TRUE);
                Settings->put_AreDefaultScriptDialogsEnabled(TRUE);
                Settings->put_IsWebMessageEnabled(TRUE);
                
                // Resize WebView to fit the bounds of the parent window
                RECT bounds;
                GetClientRect(hWnd, &bounds);
                webviewController->put_Bounds(bounds);
                
                // Schedule an async task to navigate to Bing
                webviewWindow->Navigate(L"https://www.bing.com/");
                
                // Step 4 - Navigation events
                
                // Step 5 - Scripting
                
                // Step 6 - Communication between host and web content
                
                return S_OK;
            }).Get());
        return S_OK;
    }).Get());
```  

### <span data-ttu-id="07bf2-154">构建必应示例应用</span><span class="sxs-lookup"><span data-stu-id="07bf2-154">Build your Bing sample app</span></span>  

<span data-ttu-id="07bf2-155">选择 `F5` 生成并运行应用。</span><span class="sxs-lookup"><span data-stu-id="07bf2-155">Select `F5` to build and run the app.</span></span>  <span data-ttu-id="07bf2-156">现在，你已有一个显示 "必应" 页面的 Web 视图窗口。</span><span class="sxs-lookup"><span data-stu-id="07bf2-156">Now you have a WebView window displaying the Bing page.</span></span>  

:::image type="complex" source="../media/bing-window.png" alt-text="工具版本" lightbox="../media/bing-window.png":::
   <span data-ttu-id="07bf2-158">必应窗口</span><span class="sxs-lookup"><span data-stu-id="07bf2-158">Bing window</span></span>  
:::image-end:::  

## <span data-ttu-id="07bf2-159">步骤 4-导航事件</span><span class="sxs-lookup"><span data-stu-id="07bf2-159">Step 4 - Navigation events</span></span>  

<span data-ttu-id="07bf2-160">在上一步中，Web 视图团队已涵盖使用方法导航到 URL `ICoreWebView2::Navigate` 。</span><span class="sxs-lookup"><span data-stu-id="07bf2-160">The WebView team already covered navigating to URL using the `ICoreWebView2::Navigate` method in the last step.</span></span>  <span data-ttu-id="07bf2-161">在导航过程中，Web 视图将引发主机可能侦听的一系列事件。</span><span class="sxs-lookup"><span data-stu-id="07bf2-161">During navigation, WebView fires a sequence of events to which the host may listen.</span></span>  

1.  `NavigationStarting`  
1.  `SourceChanged`  
1.  `ContentLoading`  
1.  `HistoryChanged`   
1.  `NavigationCompleted`   

<span data-ttu-id="07bf2-162">有关详细信息，请导航到 [导航事件][Webview2ConceptsNavigationEvents]。</span><span class="sxs-lookup"><span data-stu-id="07bf2-162">For more information, navigate to [Navigation events][Webview2ConceptsNavigationEvents].</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="工具版本" lightbox="../media/navigation-events.png":::
   <span data-ttu-id="07bf2-164">导航事件</span><span class="sxs-lookup"><span data-stu-id="07bf2-164">Navigation events</span></span>  
:::image-end:::  

<span data-ttu-id="07bf2-165">在错误情况下，可能会发生以下一个或多个事件，具体取决于是否将导航转到错误页面。</span><span class="sxs-lookup"><span data-stu-id="07bf2-165">In error cases, one or more of the following events may occur depending on whether the navigation is continued to an error page.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`

<span data-ttu-id="07bf2-166">如果发生 HTTP 重定向，一行中有多个 `NavigationStarting` 事件。</span><span class="sxs-lookup"><span data-stu-id="07bf2-166">If an HTTP redirect occurs, there are multiple `NavigationStarting` events in a row.</span></span>  

<span data-ttu-id="07bf2-167">作为使用事件的示例，注册事件的处理程序 `NavigationStarting` 以取消任何非 https 请求。</span><span class="sxs-lookup"><span data-stu-id="07bf2-167">As an example of using the events, register a handler for the `NavigationStarting` event to cancel any non-https requests.</span></span>  <span data-ttu-id="07bf2-168">复制以下代码片段并粘贴到其中 `HelloWebView.cpp` 。</span><span class="sxs-lookup"><span data-stu-id="07bf2-168">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>  

```cpp
// register an ICoreWebView2NavigationStartingEventHandler to cancel any non-https navigation
EventRegistrationToken token;
webviewWindow->add_NavigationStarting(Callback<ICoreWebView2NavigationStartingEventHandler>(
    [](ICoreWebView2* webview, ICoreWebView2NavigationStartingEventArgs * args) -> HRESULT {
        PWSTR uri;
        args->get_Uri(&uri);
        std::wstring source(uri);
        if (source.substr(0, 5) != L"https") {
            args->put_Cancel(true);
        }
        CoTaskMemFree(uri);
        return S_OK;
    }).Get(), &token);
```  

<span data-ttu-id="07bf2-169">现在，应用不会导航到任何非 https 网站。</span><span class="sxs-lookup"><span data-stu-id="07bf2-169">Now the app is not navigating to any non-https sites.</span></span>  <span data-ttu-id="07bf2-170">您可以使用类似的机制来完成其他任务，如限制导航到您自己的域中。</span><span class="sxs-lookup"><span data-stu-id="07bf2-170">You may use similar mechanism to accomplish other tasks, such as restricting navigation to within your own domain.</span></span>  

## <span data-ttu-id="07bf2-171">步骤 5-脚本</span><span class="sxs-lookup"><span data-stu-id="07bf2-171">Step 5 - Scripting</span></span>  

<span data-ttu-id="07bf2-172">托管应用还可以将 JavaScript 插入 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="07bf2-172">The hosting app may also inject JavaScript into WebView.</span></span>  <span data-ttu-id="07bf2-173">你可以通过任务 Web 视图运行任意 JavaScript 或添加初始化脚本。</span><span class="sxs-lookup"><span data-stu-id="07bf2-173">You may task WebView to run arbitrary JavaScript or add initialization scripts.</span></span>  <span data-ttu-id="07bf2-174">已添加的初始化脚本将应用于所有未来的顶级文档和子框架导航，直到删除。</span><span class="sxs-lookup"><span data-stu-id="07bf2-174">Added initialization scripts apply to all future top-level document and child frame navigation until removed.</span></span>  <span data-ttu-id="07bf2-175">在创建全局对象之后、运行 HTML 文档包含的任何其他脚本之前，将运行初始化脚本。</span><span class="sxs-lookup"><span data-stu-id="07bf2-175">The initialization scripts run after creating the global object and before running any other script included by the HTML document.</span></span>  

<span data-ttu-id="07bf2-176">复制以下代码片段并粘贴到其中 `HelloWebView.cpp` 。</span><span class="sxs-lookup"><span data-stu-id="07bf2-176">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>  

```cpp
// Schedule an async task to add initialization script that freezes the Object object
webviewWindow->AddScriptToExecuteOnDocumentCreated(L"Object.freeze(Object);", nullptr);
// Schedule an async task to get the document URL
webviewWindow->ExecuteScript(L"window.document.URL;", Callback<ICoreWebView2ExecuteScriptCompletedHandler>(
    [](HRESULT errorCode, LPCWSTR resultObjectAsJson) -> HRESULT {
        LPCWSTR URL = resultObjectAsJson;
        //doSomethingWithURL(URL);
        return S_OK;
    }).Get());
```  

<span data-ttu-id="07bf2-177">现在，Web 视图应始终冻结 `Object` 对象并返回页面文档一次。</span><span class="sxs-lookup"><span data-stu-id="07bf2-177">Now, WebView should always freeze the `Object` object and returns the page document once.</span></span>  

> [!NOTE] 
> <span data-ttu-id="07bf2-178">脚本注入 Api \ (和某些其他 WebView2 Api \ ) 是异步的，如果必须以特定顺序运行代码，则应使用回调。</span><span class="sxs-lookup"><span data-stu-id="07bf2-178">The script injection APIs \(and some other WebView2 APIs\) are asynchronous, you should use callbacks if code is must be run in a specific order.</span></span>  

## <span data-ttu-id="07bf2-179">步骤 6-主机和 web 内容之间的通信</span><span class="sxs-lookup"><span data-stu-id="07bf2-179">Step 6 - Communication between host and web content</span></span>  

<span data-ttu-id="07bf2-180">宿主和 web 内容也可能通过该方法互相通信 `postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="07bf2-180">The host and the web content may also communicate with each other through the `postMessage` method.</span></span>  <span data-ttu-id="07bf2-181">在 web 视图内运行的 web 内容可能会通过该方法向主机发布 `window.chrome.webview.postMessage` ，并且消息由主机上任何注册的 `ICoreWebView2WebMessageReceivedEventHandler` 事件处理程序处理。</span><span class="sxs-lookup"><span data-stu-id="07bf2-181">The web content running within a WebView may post to the host through the `window.chrome.webview.postMessage` method, and the message is handled by any registered the `ICoreWebView2WebMessageReceivedEventHandler` event handler on the host.</span></span>  <span data-ttu-id="07bf2-182">同样，主机可以通过 " `ICoreWebView2::PostWebMessageAsString` 或" `ICoreWebView2::PostWebMessageAsJSON` 方法处理 web 内容，这由从侦听器添加的处理程序捕获 `window.chrome.webview.addEventListener` 。</span><span class="sxs-lookup"><span data-stu-id="07bf2-182">Likewise, the host may message the web content through `ICoreWebView2::PostWebMessageAsString` or `ICoreWebView2::PostWebMessageAsJSON` method, which is caught by handlers added from `window.chrome.webview.addEventListener` listener.</span></span>  <span data-ttu-id="07bf2-183">通信机制允许 web 内容通过传递消息来使用本机功能，以便让主机运行本机 Api。</span><span class="sxs-lookup"><span data-stu-id="07bf2-183">The communication mechanism allows the web content to use native capabilities by passing messages to ask the host to run native APIs.</span></span>  

<span data-ttu-id="07bf2-184">作为了解机制的示例，当你尝试在 Web 视图中打印文档 URL 时，将发生以下步骤。</span><span class="sxs-lookup"><span data-stu-id="07bf2-184">As an example to understand the mechanism, the following steps occur when you try printing out the document URL in WebView.</span></span>  

1.  <span data-ttu-id="07bf2-185">主机注册处理程序以返回收到的消息，返回到 web 内容</span><span class="sxs-lookup"><span data-stu-id="07bf2-185">The host registers a handler to return received message back to the web content</span></span>  
1.  <span data-ttu-id="07bf2-186">主机将向注册处理程序的 web 内容插入脚本，以便从主机打印消息</span><span class="sxs-lookup"><span data-stu-id="07bf2-186">The host injects a script to the web content that registers a handler to print message from the host</span></span>  
1.  <span data-ttu-id="07bf2-187">主机为将 URL 发布到主机的 web 内容插入脚本</span><span class="sxs-lookup"><span data-stu-id="07bf2-187">The host injects a script to the web content that posts the URL to the host</span></span>  
1.  <span data-ttu-id="07bf2-188">将触发主机的处理程序，并返回消息 \ (URL \ ) 到 web 内容</span><span class="sxs-lookup"><span data-stu-id="07bf2-188">The handler of the host is triggered and returns the message \(the URL\) to the web content</span></span>  
1.  <span data-ttu-id="07bf2-189">将触发 web 内容的处理程序并打印来自主机 \ (URL \ ) 的消息</span><span class="sxs-lookup"><span data-stu-id="07bf2-189">The handler of the web content is triggered and prints message from the host \(the URL\)</span></span>  

<span data-ttu-id="07bf2-190">复制以下代码片段并粘贴到其中 `HelloWebView.cpp` 。</span><span class="sxs-lookup"><span data-stu-id="07bf2-190">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>    

```cpp
// Set an event handler for the host to return received message back to the web content
webviewWindow->add_WebMessageReceived(Callback<ICoreWebView2WebMessageReceivedEventHandler>(
    [](ICoreWebView2* webview, ICoreWebView2WebMessageReceivedEventArgs * args) -> HRESULT {
        PWSTR message;
        args->TryGetWebMessageAsString(&message);
        // processMessage(&message);
        webview->PostWebMessageAsString(message);
        CoTaskMemFree(message);
        return S_OK;
    }).Get(), &token);

// Schedule an async task to add initialization script that
// 1) Add an listener to print message from the host
// 2) Post document URL to the host
webviewWindow->AddScriptToExecuteOnDocumentCreated(
    L"window.chrome.webview.addEventListener(\'message\', event => alert(event.data));" \
    L"window.chrome.webview.postMessage(window.document.URL);",
nullptr);
```  

### <span data-ttu-id="07bf2-191">构建你的显示 URL 示例应用</span><span class="sxs-lookup"><span data-stu-id="07bf2-191">Build your show URL sample app</span></span>  

<span data-ttu-id="07bf2-192">选择 `F5` 生成并运行应用。</span><span class="sxs-lookup"><span data-stu-id="07bf2-192">Select `F5` to build and run the app.</span></span>  <span data-ttu-id="07bf2-193">在导航到页面之前，该 URL 显示在弹出窗口中。</span><span class="sxs-lookup"><span data-stu-id="07bf2-193">The URL appears in a pop-up window before navigating to a page.</span></span>  

:::image type="complex" source="../media/show-url.png" alt-text="工具版本" lightbox="../media/show-url.png":::
   <span data-ttu-id="07bf2-195">显示 url</span><span class="sxs-lookup"><span data-stu-id="07bf2-195">Show url</span></span>  
:::image-end:::  

<span data-ttu-id="07bf2-196">恭喜，你刚刚构建了你的第一个 WebView2 应用。</span><span class="sxs-lookup"><span data-stu-id="07bf2-196">Congratulations, you just built your first WebView2 app.</span></span>  

## <span data-ttu-id="07bf2-197">后续步骤</span><span class="sxs-lookup"><span data-stu-id="07bf2-197">Next steps</span></span>  

<span data-ttu-id="07bf2-198">此页面上未介绍的许多 WebView2 功能，以下部分提供了其他资源。</span><span class="sxs-lookup"><span data-stu-id="07bf2-198">Many of the WebView2 functionalities that are not covered on this page, the following section provided additional resources.</span></span>  

### <span data-ttu-id="07bf2-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07bf2-199">See also</span></span>  

*   <span data-ttu-id="07bf2-200">有关 WebView2 功能的完整示例，请导航到 [WEBVIEW2 API 示例][GithubMicrosoftedgeWebview2samplesApisample]。</span><span class="sxs-lookup"><span data-stu-id="07bf2-200">For a comprehensive example of WebView2 capabilities, navigate to [WebView2 API Sample][GithubMicrosoftedgeWebview2samplesApisample].</span></span>  
*   <span data-ttu-id="07bf2-201">对于使用 WebView2 生成的示例应用程序，请导航到 [WebView2Browser][GithubMicrosoftedgeWebview2browser]。</span><span class="sxs-lookup"><span data-stu-id="07bf2-201">For a sample application built using WebView2, navigate to [WebView2Browser][GithubMicrosoftedgeWebview2browser].</span></span>  
*   <span data-ttu-id="07bf2-202">有关 WebView2 API 的详细信息，请导航到 [API 参考][Webview2ReferenceWin32]。</span><span class="sxs-lookup"><span data-stu-id="07bf2-202">For detailed information about the WebView2 API, navigate to [API reference][Webview2ReferenceWin32].</span></span>  

## <span data-ttu-id="07bf2-203">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="07bf2-203">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2Index]: ../index.md "Microsoft Edge WebView2 简介 (预览版) |Microsoft 文档"  
[Webview2ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 c + + 参考 |Microsoft 文档"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "导航事件 |Microsoft 文档"  

[CppCxWrlTemplateLibraryVS2019]: /cpp/cppcx/wrl/windows-runtime-cpp-template-library-wrl?view=vs-2019&preserve-view=true "Windows 运行时 c + + 模板库 (WRL) |Microsoft 文档"  
[CppWindowsWalkthroughCreatingDesktopApplication]: /cpp/windows/walkthrough-creating-windows-desktop-applications-cpp?view=vs-2019&preserve-view=true "演练：创建传统的 Windows 桌面应用程序 (c + +) |Microsoft 文档"  

[GithubMicrosoftedgeWebview2browser]: https://github.com/MicrosoftEdge/WebView2Browser "WebView2Browser-MicrosoftEdge/WebView2Browser |GitHub"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/blob/master/SampleApps/WebView2APISample/README.md "WebView2 API Sample-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesGettingStartedGuide]: https://github.com/MicrosoftEdge/WebView2Samples#1-getting-started-guide "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftWilMain]: https://github.com/Microsoft/wil "Windows 实施库 () -microsoft/中 |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序"  
