---
description: 适用于 Win32 应用的 WebView2 入门指南
title: Win32 应用的 WebView2 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 073a92bf10a7ead85ac91bff54b5fc405c7d577c
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535852"
---
# <a name="get-started-with-webview2"></a><span data-ttu-id="c0c1d-104">WebView2 入门</span><span class="sxs-lookup"><span data-stu-id="c0c1d-104">Get started with WebView2</span></span>  

<span data-ttu-id="c0c1d-105">本文将开始创建你的第一个 WebView2 应用，并了解 [WebView2 的主要功能][MicrosoftDeveloperMicrosoftEdgeWebview2]。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-105">In this article, get started creating your first WebView2 app and learn about the main features of [WebView2][MicrosoftDeveloperMicrosoftEdgeWebview2].</span></span>  <span data-ttu-id="c0c1d-106">有关各个 WebView2 API 的信息，请导航到 [API 参考][Webview2ReferenceWin32]。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-106">For more information about individual WebView2 APIs, navigate to [API reference][Webview2ReferenceWin32].</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="c0c1d-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="c0c1d-107">Prerequisites</span></span>  

<span data-ttu-id="c0c1d-108">请确保先安装以下先决条件列表，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-108">Ensure you install the following list of pre-requisites before proceeding.</span></span>  

*   <span data-ttu-id="c0c1d-109">[WebView2][Webview2Installer]运行时Microsoft Edge (Chromium) [][MicrosoftedgeinsiderDownload]安装在受支持的操作系统 \ (上的任意非稳定通道Windows 10、Windows 8.1和 Windows 7\) 。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-109">[WebView2 Runtime][Webview2Installer] or any [Microsoft Edge (Chromium) non-stable channel][MicrosoftedgeinsiderDownload] installed on supported OS \(currently Windows 10, Windows 8.1, and Windows 7\).</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c0c1d-110">WebView 团队建议使用 Canary 通道，最低要求版本为 82.0.488.0。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-110">The WebView team recommends using the Canary channel and the minimum required version is 82.0.488.0.</span></span>  
    
*   <span data-ttu-id="c0c1d-111">[Visual Studio][MicrosoftVisualstudioMain]安装有 C++ 支持的 2015 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-111">[Visual Studio][MicrosoftVisualstudioMain] 2015 or later with C++ support installed.</span></span>  
    
## <a name="step-1---create-a-single-window-app"></a><span data-ttu-id="c0c1d-112">步骤 1 - 创建单窗口应用</span><span class="sxs-lookup"><span data-stu-id="c0c1d-112">Step 1 - Create a single-window app</span></span>  

<span data-ttu-id="c0c1d-113">从包含单个主窗口的基本桌面项目开始。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-113">Start with a basic desktop project that contains a single main window.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="c0c1d-114">为了更好地关注演练，请使用演练：为示例应用创建传统的 Windows 桌面应用程序 ([C++][CppWindowsWalkthroughCreatingDesktopApplication]) 中修改的示例代码。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-114">To better focus the walkthrough, use modified sample code from [Walkthrough: Create a traditional Windows Desktop application (C++)][CppWindowsWalkthroughCreatingDesktopApplication] for your sample app.</span></span>  <span data-ttu-id="c0c1d-115">若要下载修改后的示例并开始，请导航到["WebView2 示例"。][GithubMicrosoftedgeWebview2samplesGettingStartedGuide]</span><span class="sxs-lookup"><span data-stu-id="c0c1d-115">To download the modified sample and get started, navigate to [WebView2 Samples][GithubMicrosoftedgeWebview2samplesGettingStartedGuide].</span></span>  

1.  <span data-ttu-id="c0c1d-116">在Visual Studio中，打开 `WebView2GettingStarted.sln` 。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-116">In Visual Studio, open `WebView2GettingStarted.sln`.</span></span>  
    <span data-ttu-id="c0c1d-117">如果使用早期版本的 Visual Studio，请将鼠标悬停在**WebView2GettingStarted**项目上，打开上下文菜单 \ (右键单击\) ，然后选择 **"属性**"。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-117">If you use an older version of Visual Studio, hover on the **WebView2GettingStarted** project, open the contextual menu \(right-click\), and choose **Properties**.</span></span>  <span data-ttu-id="c0c1d-118">在**配置属性**  >  **常规**下 **，Windows SDK**版本和\*\*\*\* 平台工具集，以使用 Win10 SDK 和Visual Studio可用的工具集。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-118">Under **Configuration Properties** > **General**, modify **Windows SDK Version** and **Platform Toolset** to use the Win10 SDK and Visual Studio toolset available to you.</span></span>  
    
:::image type="complex" source="../media/tool-version.png" alt-text="工具版本" lightbox="../media/tool-version.png":::
   <span data-ttu-id="c0c1d-120">工具版本</span><span class="sxs-lookup"><span data-stu-id="c0c1d-120">Tool version</span></span>  
:::image-end:::      

<span data-ttu-id="c0c1d-121">Visual Studio显示错误，因为项目缺少 WebView2 头文件。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-121">Visual Studio may display errors, because your project is missing the WebView2 header file.</span></span>  <span data-ttu-id="c0c1d-122">应在步骤 [2 之后修复错误](#step-2---install-webview2-sdk)。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-122">The errors should be fixed after [Step 2](#step-2---install-webview2-sdk).</span></span>  

## <a name="step-2---install-webview2-sdk"></a><span data-ttu-id="c0c1d-123">步骤 2 - 安装 WebView2 SDK</span><span class="sxs-lookup"><span data-stu-id="c0c1d-123">Step 2 - Install WebView2 SDK</span></span>  

<span data-ttu-id="c0c1d-124">将 WebView2 SDK 添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-124">Add the WebView2 SDK into the project.</span></span>  <span data-ttu-id="c0c1d-125">使用 NuGet 安装 Win32 SDK。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-125">Use NuGet to install the Win32 SDK.</span></span>  

1.  <span data-ttu-id="c0c1d-126">将鼠标悬停在项目上，打开上下文菜单 \ (右键单击\) ，然后选择"管理NuGet**包"。**</span><span class="sxs-lookup"><span data-stu-id="c0c1d-126">Hover on the project, open the contextual menu \(right-click\), and choose **Manage NuGet Packages**.</span></span>  
    
    :::image type="complex" source="../media/manage-nuget-packages.png" alt-text="管理 NuGet 程序包" lightbox="../media/manage-nuget-packages.png":::
       <span data-ttu-id="c0c1d-128">管理 NuGet 程序包</span><span class="sxs-lookup"><span data-stu-id="c0c1d-128">Manage NuGet packages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c0c1d-129">安装Windows库。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-129">Install the Windows Implementation Library.</span></span>  
    1.  <span data-ttu-id="c0c1d-130">在搜索栏中，键入 > `Microsoft.Windows.ImplementationLibrary` **Microsoft.Windows。ImplementationLibrary**。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-130">In the search bar, type `Microsoft.Windows.ImplementationLibrary` > choose **Microsoft.Windows.ImplementationLibrary**.</span></span>  
    1.  <span data-ttu-id="c0c1d-131">在右侧窗口中，选择"安装 **"。**</span><span class="sxs-lookup"><span data-stu-id="c0c1d-131">In the right-hand side window, choose **Install**.</span></span>  <span data-ttu-id="c0c1d-132">NuGet将库下载到计算机。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-132">NuGet downloads the library to your machine.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="c0c1d-133">实现[Windows库][GithubMicrosoftWilMain]和 Windows[运行时 C++ 模板][CppCxWrlTemplateLibraryVS2019]库是可选的，因此对于此示例而言，使用 COM 更为简单。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-133">The [Windows Implementation Library][GithubMicrosoftWilMain] and [Windows Runtime C++ Template Library][CppCxWrlTemplateLibraryVS2019] are optional and make working with COM easier for the example.</span></span>  
        
        :::image type="complex" source="../media/wil.png" alt-text="Windows实现库" lightbox="../media/wil.png":::
           <span data-ttu-id="c0c1d-135">Windows实现库</span><span class="sxs-lookup"><span data-stu-id="c0c1d-135">Windows Implementation Library</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="c0c1d-136">安装 WebView2 SDK。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-136">Install the WebView2 SDK.</span></span>  
    1.  <span data-ttu-id="c0c1d-137">在搜索栏中，键入"> `Microsoft.Web.WebView2` **选择"Microsoft.Web.WebView2"。**</span><span class="sxs-lookup"><span data-stu-id="c0c1d-137">In the search bar, type `Microsoft.Web.WebView2` > choose **Microsoft.Web.WebView2**.</span></span>  
    1.  <span data-ttu-id="c0c1d-138">在右侧窗口中，选择"安装 **"。**</span><span class="sxs-lookup"><span data-stu-id="c0c1d-138">In the right-hand side window, choose **Install**.</span></span>  <span data-ttu-id="c0c1d-139">NuGet将 SDK 下载到计算机。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-139">NuGet downloads the SDK to your machine.</span></span>  
        
        :::image type="complex" source="../media/nuget.png" alt-text="NuGet 程序包管理器" lightbox="../media/nuget.png":::
           <span data-ttu-id="c0c1d-141">NuGet 程序包管理器</span><span class="sxs-lookup"><span data-stu-id="c0c1d-141">NuGet Package Manager</span></span>
        :::image-end:::  
        
1.  <span data-ttu-id="c0c1d-142">将 WebView2 标头添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-142">Add WebView2 header to your project.</span></span>  
    
    :::row:::
       :::column span="1":::
          <span data-ttu-id="c0c1d-143">在 `HelloWebView.cpp` 文件中，复制以下代码段并将其粘贴到最后一 `#include` 行之后。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-143">In the `HelloWebView.cpp` file, copy the following code snippet and paste it after the last `#include` line.</span></span>  
          
          ```cpp
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
       :::column span="1":::
          <span data-ttu-id="c0c1d-144">include 部分应类似于以下代码段。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-144">The include section should look similar to the following code snippet.</span></span>  
          
          ```cpp
          ...
          #include <wrl.h>
          #include <wil/com.h>
          // include WebView2 header
          #include "WebView2.h"
          ```  
       :::column-end:::
    :::row-end:::
    
<span data-ttu-id="c0c1d-145">准备好使用 WebView2 API 并生成。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-145">Ready to use and build against the WebView2 API.</span></span>  

### <a name="build-your-empty-sample-app"></a><span data-ttu-id="c0c1d-146">生成空示例应用</span><span class="sxs-lookup"><span data-stu-id="c0c1d-146">Build your empty sample app</span></span>  

<span data-ttu-id="c0c1d-147">若要生成并运行示例应用，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-147">To build and run the sample app, select `F5`.</span></span>  <span data-ttu-id="c0c1d-148">你的应用显示一个空窗口。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-148">Your app displays an empty window.</span></span>  

:::image type="complex" source="../media/empty-app.png" alt-text="空应用" lightbox="../media/empty-app.png":::
   <span data-ttu-id="c0c1d-150">空应用</span><span class="sxs-lookup"><span data-stu-id="c0c1d-150">Empty app</span></span>  
:::image-end:::    

## <a name="step-3---create-a-single-webview-within-the-parent-window"></a><span data-ttu-id="c0c1d-151">步骤 3 - 在父窗口中创建单个 WebView</span><span class="sxs-lookup"><span data-stu-id="c0c1d-151">Step 3 - Create a single WebView within the parent window</span></span>  

<span data-ttu-id="c0c1d-152">将 WebView 添加到主窗口。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-152">Add a WebView to the main window.</span></span>  

<span data-ttu-id="c0c1d-153">使用 `CreateCoreWebView2Environment` 方法设置环境并找到支持Microsoft Edge \ (Chromium\) 的浏览器。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-153">Use the `CreateCoreWebView2Environment` method to set up the environment and locate the Microsoft Edge \(Chromium\) browser powering the control.</span></span>  <span data-ttu-id="c0c1d-154">如果要指定浏览器位置、用户文件夹、浏览器标志等，也可以使用此方法，而不是 `CreateCoreWebView2EnvironmentWithOptions` 使用默认设置。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-154">You may also use the `CreateCoreWebView2EnvironmentWithOptions` method if you want to specify browser location, user folder, browser flags, and so on, instead of using the default setting.</span></span>  <span data-ttu-id="c0c1d-155">完成该方法后，在回调中运行 方法并运行 `CreateCoreWebView2Environment` `ICoreWebView2Environment::CreateCoreWebView2Controller` `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` `ICoreWebView2Controller::get_CoreWebView2` 方法，获取关联的 WebView。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-155">Upon the completion of the `CreateCoreWebView2Environment` method, run the `ICoreWebView2Environment::CreateCoreWebView2Controller` method inside the `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` callback and run the `ICoreWebView2Controller::get_CoreWebView2` method to get the associated WebView.</span></span>  

<span data-ttu-id="c0c1d-156">在回调中，设置一些设置，调整 WebView 的大小以使用 100% 的父窗口，然后导航到必应。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-156">In the callback, set a few more settings, resize the WebView to take 100% of the parent window, and navigate to Bing.</span></span>  

<span data-ttu-id="c0c1d-157">复制以下代码段，并粘贴 `HelloWebView.cpp` 到注释之后 `// <-- WebView2 sample code starts here -->` 和注释 `// <-- WebView2 sample code ends here -->` 之前。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-157">Copy the following code snippet and paste into `HelloWebView.cpp` after the `// <-- WebView2 sample code starts here -->` comment and before the `// <-- WebView2 sample code ends here -->` comment.</span></span>  

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

### <a name="build-your-bing-sample-app"></a><span data-ttu-id="c0c1d-158">生成必应示例应用</span><span class="sxs-lookup"><span data-stu-id="c0c1d-158">Build your Bing sample app</span></span>  

<span data-ttu-id="c0c1d-159">若要生成并运行应用，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-159">To build and run the app, select `F5`.</span></span>  <span data-ttu-id="c0c1d-160">现在，你有一个 WebView 窗口，必应页面。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-160">Now you have a WebView window displaying the Bing page.</span></span>  

:::image type="complex" source="../media/bing-window.png" alt-text="必应窗口" lightbox="../media/bing-window.png":::
   <span data-ttu-id="c0c1d-162">必应窗口</span><span class="sxs-lookup"><span data-stu-id="c0c1d-162">Bing window</span></span>  
:::image-end:::    

## <a name="step-4---navigation-events"></a><span data-ttu-id="c0c1d-163">步骤 4 - 导航事件</span><span class="sxs-lookup"><span data-stu-id="c0c1d-163">Step 4 - Navigation events</span></span>  

<span data-ttu-id="c0c1d-164">WebView 团队已在上一步中介绍了使用 `ICoreWebView2::Navigate` 方法导航到 URL 的内容。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-164">The WebView team already covered navigating to URL using the `ICoreWebView2::Navigate` method in the last step.</span></span>  <span data-ttu-id="c0c1d-165">在导航过程中，WebView 会触发主机可以侦听的一系列事件。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-165">During navigation, WebView fires a sequence of events to which the host may listen.</span></span>  

1.  `NavigationStarting`  
1.  `SourceChanged`  
1.  `ContentLoading`  
1.  `HistoryChanged`   
1.  `NavigationCompleted`   
    
<span data-ttu-id="c0c1d-166">有关详细信息，请导航到["导航事件"。][Webview2ConceptsNavigationEvents]</span><span class="sxs-lookup"><span data-stu-id="c0c1d-166">For more information, navigate to [Navigation events][Webview2ConceptsNavigationEvents].</span></span>  

:::image type="complex" source="../media/navigation-events.png" alt-text="导航事件" lightbox="../media/navigation-events.png":::
   <span data-ttu-id="c0c1d-168">导航事件</span><span class="sxs-lookup"><span data-stu-id="c0c1d-168">Navigation events</span></span>  
:::image-end:::    

<span data-ttu-id="c0c1d-169">在错误情况下，可能会发生以下一个或多个事件，具体取决于导航是否继续导航到错误网页。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-169">In error cases, one or more of the following events may occur depending on whether the navigation is continued to an error webpage.</span></span>  

*   `SourceChanged`  
*   `ContentLoading`  
*   `HistoryChanged`
    
> [!NOTE]
> <span data-ttu-id="c0c1d-170">如果发生 HTTP 重定向，则一行 `NavigationStarting` 中有多个事件。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-170">If an HTTP redirect occurs, there are multiple `NavigationStarting` events in a row.</span></span>  

<span data-ttu-id="c0c1d-171">作为使用事件的示例，请为事件注册处理程序以取消 `NavigationStarting` 任何非 https 请求。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-171">As an example of using the events, register a handler for the `NavigationStarting` event to cancel any non-https requests.</span></span>  <span data-ttu-id="c0c1d-172">复制以下代码段并粘贴到 `HelloWebView.cpp` 中。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-172">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>  

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

<span data-ttu-id="c0c1d-173">现在，应用不会导航到任何非 https 网站。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-173">Now the app does not navigate to any non-https sites.</span></span>  <span data-ttu-id="c0c1d-174">您可以使用类似的机制完成其他任务，例如将导航限制到您自己的域中。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-174">You may use similar mechanism to accomplish other tasks, such as restricting navigation to within your own domain.</span></span>  

## <a name="step-5---scripting"></a><span data-ttu-id="c0c1d-175">步骤 5 - 脚本</span><span class="sxs-lookup"><span data-stu-id="c0c1d-175">Step 5 - Scripting</span></span>  

<span data-ttu-id="c0c1d-176">你可以在运行时使用主机应用将 JavaScript 代码注入 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-176">You may use host apps to inject JavaScript code into WebView2 controls at runtime.</span></span>  <span data-ttu-id="c0c1d-177">你可以任务 WebView 运行任意 JavaScript 或添加初始化脚本。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-177">You may task WebView to run arbitrary JavaScript or add initialization scripts.</span></span>  <span data-ttu-id="c0c1d-178">在删除 JavaScript 之前，注入的 JavaScript 适用于所有新的顶级文档和任何子框架。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-178">The injected JavaScript applies to all new top-level documents and any child frames until the JavaScript is removed.</span></span>  <span data-ttu-id="c0c1d-179">注入的 JavaScript 以特定计时运行。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-179">The injected JavaScript is run with specific timing.</span></span>  

*   <span data-ttu-id="c0c1d-180">创建全局对象后运行它。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-180">Run it after the creation of the global object.</span></span>  
*   <span data-ttu-id="c0c1d-181">在运行 HTML 文档中包含的任何其他脚本之前运行它。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-181">Run it before any other script included in the HTML document is run.</span></span>  
    
<span data-ttu-id="c0c1d-182">复制以下代码段并粘贴到 `HelloWebView.cpp` 中。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-182">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>  

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

<span data-ttu-id="c0c1d-183">现在，WebView 应始终冻结 `Object` 对象并返回页面文档一次。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-183">Now, WebView should always freeze the `Object` object and returns the page document once.</span></span>  

> [!NOTE] 
> <span data-ttu-id="c0c1d-184">脚本注入 API \ (和其他一些 WebView2 API\) 是异步的，如果代码必须按特定顺序运行，则应该使用回调。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-184">The script injection APIs \(and some other WebView2 APIs\) are asynchronous, you should use callbacks if code is must be run in a specific order.</span></span>  

## <a name="step-6---communication-between-host-and-web-content"></a><span data-ttu-id="c0c1d-185">步骤 6 - 主机和 Web 内容之间的通信</span><span class="sxs-lookup"><span data-stu-id="c0c1d-185">Step 6 - Communication between host and web content</span></span>  

<span data-ttu-id="c0c1d-186">主机和 Web 内容还可通过 方法相互 `postMessage` 通信。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-186">The host and the web content may also communicate with each other through the `postMessage` method.</span></span>  <span data-ttu-id="c0c1d-187">WebView 中运行的 Web 内容可以通过 方法发布给主机，消息由主机上注册的任何 `window.chrome.webview.postMessage` `ICoreWebView2WebMessageReceivedEventHandler` 事件处理程序处理。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-187">The web content running within a WebView may post to the host through the `window.chrome.webview.postMessage` method, and the message is handled by any registered the `ICoreWebView2WebMessageReceivedEventHandler` event handler on the host.</span></span>  <span data-ttu-id="c0c1d-188">同样，主机可能通过 或 方法发送 Web 内容消息，由从侦听器添加的 `ICoreWebView2::PostWebMessageAsString` `ICoreWebView2::PostWebMessageAsJSON` 处理程序捕获 `window.chrome.webview.addEventListener` 。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-188">Likewise, the host may message the web content through `ICoreWebView2::PostWebMessageAsString` or `ICoreWebView2::PostWebMessageAsJSON` method, which is caught by handlers added from `window.chrome.webview.addEventListener` listener.</span></span>  <span data-ttu-id="c0c1d-189">通信机制允许 Web 内容通过传递消息要求主机运行本机 API 来使用本机功能。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-189">The communication mechanism allows the web content to use native capabilities by passing messages to ask the host to run native APIs.</span></span>  

<span data-ttu-id="c0c1d-190">作为了解机制的示例，当您尝试在 WebView 中输出文档 URL 时，将执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-190">As an example to understand the mechanism, the following steps occur when you try to output the document URL in WebView.</span></span>  

1.  <span data-ttu-id="c0c1d-191">主机注册处理程序以将收到的消息返回给 Web 内容</span><span class="sxs-lookup"><span data-stu-id="c0c1d-191">The host registers a handler to return received message back to the web content</span></span>  
1.  <span data-ttu-id="c0c1d-192">主机将脚本注入 Web 内容，Web 内容注册处理程序以从主机打印消息</span><span class="sxs-lookup"><span data-stu-id="c0c1d-192">The host injects a script to the web content that registers a handler to print message from the host</span></span>  
1.  <span data-ttu-id="c0c1d-193">主机向将 URL 张贴到主机的 Web 内容注入脚本</span><span class="sxs-lookup"><span data-stu-id="c0c1d-193">The host injects a script to the web content that posts the URL to the host</span></span>  
1.  <span data-ttu-id="c0c1d-194">将触发主机处理程序，并返回消息 \ (URL\) Web 内容</span><span class="sxs-lookup"><span data-stu-id="c0c1d-194">The handler of the host is triggered and returns the message \(the URL\) to the web content</span></span>  
1.  <span data-ttu-id="c0c1d-195">将触发 Web 内容的处理程序，并输出来自主机 \ (URL\) </span><span class="sxs-lookup"><span data-stu-id="c0c1d-195">The handler of the web content is triggered and prints message from the host \(the URL\)</span></span>  
    
<span data-ttu-id="c0c1d-196">复制以下代码段并粘贴到 `HelloWebView.cpp` 中。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-196">Copy the following code snippet and paste into `HelloWebView.cpp`.</span></span>  

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

### <a name="build-your-display-url-sample-app"></a><span data-ttu-id="c0c1d-197">生成显示 URL 示例应用程序</span><span class="sxs-lookup"><span data-stu-id="c0c1d-197">Build your display URL sample app</span></span>  

<span data-ttu-id="c0c1d-198">若要生成并运行应用，请选择 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-198">To build and run the app, select `F5`.</span></span>  <span data-ttu-id="c0c1d-199">在导航到网页之前，URL 将显示在弹出窗口中。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-199">The URL appears in a pop-up window before navigating to a webpage.</span></span>  

:::image type="complex" source="../media/show-url.png" alt-text="显示 URL" lightbox="../media/show-url.png":::
   <span data-ttu-id="c0c1d-201">显示 URL</span><span class="sxs-lookup"><span data-stu-id="c0c1d-201">Display url</span></span>  
:::image-end:::    

<span data-ttu-id="c0c1d-202">恭喜！你生成了第一个 WebView2 应用。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-202">Congratulations, you built your first WebView2 app.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="c0c1d-203">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c0c1d-203">Next steps</span></span>  

<span data-ttu-id="c0c1d-204">有关本文未涵盖的其他 WebView2 功能，请查看以下资源。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-204">For additional WebView2 functionality that isn't covered in this article, review the following resources.</span></span>  

*   <span data-ttu-id="c0c1d-205">若要了解有关生成 WebView2 应用程序的信息，请导航到 [WebView2 开发最佳做法][WV2BestPractices]。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-205">To learn more about building WebView2 applications, navigate to [WebView2 development best practices][WV2BestPractices].</span></span>  
*   <span data-ttu-id="c0c1d-206">有关 WebView2 功能的综合示例，请导航到 [WebView2 API 示例][GithubMicrosoftedgeWebview2samplesApisample]。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-206">For a comprehensive example of WebView2 capabilities, navigate to [WebView2 API Sample][GithubMicrosoftedgeWebview2samplesApisample].</span></span>  
*   <span data-ttu-id="c0c1d-207">对于使用 WebView2 生成的示例应用，导航到 [WebView2Browser][GithubMicrosoftedgeWebview2browser]。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-207">For a sample app built using WebView2, navigate to [WebView2Browser][GithubMicrosoftedgeWebview2browser].</span></span>  
*   <span data-ttu-id="c0c1d-208">有关 WebView2 API 的详细信息，请导航到 [API 参考][Webview2ReferenceWin32]。</span><span class="sxs-lookup"><span data-stu-id="c0c1d-208">For detailed information about the WebView2 API, navigate to [API reference][Webview2ReferenceWin32].</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="c0c1d-209">与 Microsoft Edge WebView 团队联系</span><span class="sxs-lookup"><span data-stu-id="c0c1d-209">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[WV2BestPractices]: ../concepts/developer-guide.md "WebView2 开发最佳实践|Microsoft Docs"  
[MicrosoftDeveloperMicrosoftEdgeWebview2]: https://developer.microsoft.com/microsoft-edge/webview2 " WebView2 |Microsoft Edge 开发人员"  

[Webview2ReferenceWin32]: /microsoft-edge/webview2/reference/win32 "WebView2 Win32 C++ 参考|Microsoft Docs"  
[Webview2ConceptsNavigationEvents]: ../concepts/navigation-events.md "导航事件|Microsoft Docs"  

[CppCxWrlTemplateLibraryVS2019]: /cpp/cppcx/wrl/windows-runtime-cpp-template-library-wrl?view=vs-2019&preserve-view=true "Windows 运行时 C++ 模板库 (WRL) |Microsoft Docs"  
[CppWindowsWalkthroughCreatingDesktopApplication]: /cpp/windows/walkthrough-creating-windows-desktop-applications-cpp?view=vs-2019&preserve-view=true "Walkthrough： Create a traditional Windows Desktop application (C++) |Microsoft Docs"  

[GithubMicrosoftedgeWebview2browser]: https://github.com/MicrosoftEdge/WebView2Browser "WebView2Browser - MicrosoftEdge/WebView2Browser |GitHub"  

[GithubMicrosoftedgeWebviewfeedback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  

[GithubMicrosoftedgeWebview2samplesMain]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftedgeWebview2samplesApisample]: https://github.com/MicrosoftEdge/WebView2Samples/blob/master/SampleApps/WebView2APISample/README.md "WebView2 API 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebview2samplesGettingStartedGuide]: https://github.com/MicrosoftEdge/WebView2Samples#1-getting-started-guide "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  

[GithubMicrosoftWilMain]: https://github.com/Microsoft/wil "Windows 实现库 (WIL) - microsoft/wil |GitHub"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[MicrosoftVisualstudioMain]: https://visualstudio.microsoft.com "Visual Studio"  

[Webview2Installer]: https://developer.microsoft.com/microsoft-edge/webview2 "WebView2 安装程序"  