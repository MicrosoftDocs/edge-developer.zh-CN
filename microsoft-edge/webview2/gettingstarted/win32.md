---
description: 将 Win32 应用中的 web 内容托管到 Microsoft Edge Web 部件2控件中
title: 适用于 Win32 应用的 Microsoft Edge Web 视图2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/08/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 460364b0c93e80c0e3868c3b69e20ea9dcf6c129
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697194"
---
# <span data-ttu-id="239f0-104">WebView2 （开发人员预览版）入门</span><span class="sxs-lookup"><span data-stu-id="239f0-104">Getting started with WebView2 (developer preview)</span></span>

<span data-ttu-id="239f0-105">本演练将介绍[WebView2 （开发人员预览版）](https://aka.ms/webview)的常用功能，并帮助你开始创建你的第一个 WebView2 应用。</span><span class="sxs-lookup"><span data-stu-id="239f0-105">This walkthrough goes over the commonly used functionalities of [WebView2 (developer preview)](https://aka.ms/webview) and gets you started on creating your first WebView2 app.</span></span> <span data-ttu-id="239f0-106">访问[API 参考](../reference/win32/0-9-538-reference-webview2.md)以了解有关单个 api 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="239f0-106">Visit [API reference](../reference/win32/0-9-538-reference-webview2.md) to learn more about individual APIs.</span></span>  

## <span data-ttu-id="239f0-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="239f0-107">Prerequisites</span></span>

* <span data-ttu-id="239f0-108">安装在支持的操作系统（当前为 Windows 10、Windows 8.1 和 Windows 7）的[Microsoft Edge （Chromium）](https://www.microsoftedgeinsider.com/download/) 。</span><span class="sxs-lookup"><span data-stu-id="239f0-108">[Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/download/) installed on supported OS (currently Windows 10, Windows 8.1, and Windows 7).</span></span> <span data-ttu-id="239f0-109">**我们建议使用 "82.0.488.0" 通道，并且所需的最低版本为 ""**。</span><span class="sxs-lookup"><span data-stu-id="239f0-109">**We recommend using the Canary channel and the minimum required version is 82.0.488.0**.</span></span>
* <span data-ttu-id="239f0-110">安装了 c + + 支持的[Visual Studio](https://visualstudio.microsoft.com/) 2015 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="239f0-110">[Visual Studio](https://visualstudio.microsoft.com/) 2015 or later with C++ support installed.</span></span>

## <span data-ttu-id="239f0-111">步骤 1-创建单个窗口 win32 应用程序</span><span class="sxs-lookup"><span data-stu-id="239f0-111">Step 1 - Create a single window win32 app</span></span>

<span data-ttu-id="239f0-112">我们将从包含单个主窗口的基本桌面项目开始。</span><span class="sxs-lookup"><span data-stu-id="239f0-112">We will start with a basic desktop project containing a single main window.</span></span> <span data-ttu-id="239f0-113">由于这不是本演练的主要重点，因此我们将简单地使用[演练：创建传统的 Windows 桌面应用程序（c + +）](/cpp/windows/walkthrough-creating-windows-desktop-applications-cpp?view=vs-2019)中已修改的示例代码。</span><span class="sxs-lookup"><span data-stu-id="239f0-113">As this is not the main focus of this walkthrough, we will simply use modified sample code from [Walkthrough: Create a traditional Windows Desktop application (C++)](/cpp/windows/walkthrough-creating-windows-desktop-applications-cpp?view=vs-2019).</span></span> <span data-ttu-id="239f0-114">[下载](https://aka.ms/HelloWebView)修改后的示例以开始使用。</span><span class="sxs-lookup"><span data-stu-id="239f0-114">[Download](https://aka.ms/HelloWebView) the modified sample to get started.</span></span>

<span data-ttu-id="239f0-115">在 Visual Studio 中打开**WebView2GettingStarted** 。</span><span class="sxs-lookup"><span data-stu-id="239f0-115">Open **WebView2GettingStarted.sln** in Visual Studio.</span></span> <span data-ttu-id="239f0-116">如果您使用的是早期版本的 Visual Studio，请右键单击**WebView2GettingStarted**项目，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="239f0-116">If you are using an older version of Visual Studio, right click on the **WebView2GettingStarted** project and click **Properties**.</span></span> <span data-ttu-id="239f0-117">在 "**配置属性**" 下  >  **General**，修改**Windows SDK 版本**和**平台工具集**以使用可供你使用的 Win10 SDK 和 VS 工具集。</span><span class="sxs-lookup"><span data-stu-id="239f0-117">Under **Configuration Properties** > **General**, modify **Windows SDK Version** and **Platform Toolset** to use the Win10 SDK and VS toolset available to you.</span></span>

![工具-版本](../media/tool-version.png)

<span data-ttu-id="239f0-119">由于缺少 WebView2 头文件，Visual Studio 可能会显示一些错误，在步骤2完成后，该文件应消失。</span><span class="sxs-lookup"><span data-stu-id="239f0-119">Visual Studio may show some errors due to missing WebView2 header file, which should go away once Step 2 is completed.</span></span>

## <span data-ttu-id="239f0-120">步骤 2-安装 WebView2 SDK</span><span class="sxs-lookup"><span data-stu-id="239f0-120">Step 2 - Install WebView2 SDK</span></span>

<span data-ttu-id="239f0-121">现在，我们将 WebView2 SDK 添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="239f0-121">Now let's add the WebView2 SDK into the project.</span></span> <span data-ttu-id="239f0-122">对于开发人员预览版，您可以通过 Nuget 安装 Win32 SDK。</span><span class="sxs-lookup"><span data-stu-id="239f0-122">For the developer preview, you can install the Win32 SDK via Nuget.</span></span>

1. <span data-ttu-id="239f0-123">右键单击该项目，然后单击 "**管理 Nuget 程序包**"。</span><span class="sxs-lookup"><span data-stu-id="239f0-123">Right click the project and click **Manage Nuget Packages**.</span></span>

    ![管理-nuget-程序包](../media/manage-nuget-packages.png)

2. <span data-ttu-id="239f0-125">在搜索栏中输入**ImplementationLibrary** ，单击结果中的 " **ImplementationLibrary** "，然后单击右侧窗口中的 "**安装**" 并安装最新的 SDK。</span><span class="sxs-lookup"><span data-stu-id="239f0-125">Enter **Microsoft.Windows.ImplementationLibrary** in the search bar, click **Microsoft.Windows.ImplementationLibrary** from the results, and click **Install** inthe right hand side window and install the latest SDK.</span></span> <span data-ttu-id="239f0-126">Nuget 会将 SDK 下载到你的计算机。</span><span class="sxs-lookup"><span data-stu-id="239f0-126">Nuget will download the SDK to your machine.</span></span> <span data-ttu-id="239f0-127">虽然我们使用[Windows 实现库](https://github.com/Microsoft/wil)和[Windows 运行时 c + + 模板库](/cpp/cppcx/wrl/windows-runtime-cpp-template-library-wrl?view=vs-2019)在本演练中使 COM 更容易使用，但它们完全是可选的。</span><span class="sxs-lookup"><span data-stu-id="239f0-127">While we use [Windows Implementation Library](https://github.com/Microsoft/wil) and [Windows Runtime C++ Template Library](/cpp/cppcx/wrl/windows-runtime-cpp-template-library-wrl?view=vs-2019) to make working with COM easier in this walkthrough, they are completely optional.</span></span>

    ![将](../media/wil.png)

3. <span data-ttu-id="239f0-129">在搜索栏中输入 " **WebView2** "，从结果中单击 "**微软 WebView2** "，然后单击右侧窗口中的 "**安装**" 并安装最新的 SDK。</span><span class="sxs-lookup"><span data-stu-id="239f0-129">Enter **Microsoft.Web.WebView2** in the search bar, click **Microsoft.Web.WebView2** from the results, and click **Install** in the right hand side window and install the latest SDK.</span></span> <span data-ttu-id="239f0-130">Nuget 会将 SDK 下载到你的计算机。</span><span class="sxs-lookup"><span data-stu-id="239f0-130">Nuget will download the SDK to your machine.</span></span>

    ![nuget.exe](../media/nuget.png)

4. <span data-ttu-id="239f0-132">包括 WebView2 标头。</span><span class="sxs-lookup"><span data-stu-id="239f0-132">Include the WebView2 header.</span></span> <span data-ttu-id="239f0-133">在**HelloWebView**中，在 `#include "WebView2.h"` s 的行下方添加 `#include` 。</span><span class="sxs-lookup"><span data-stu-id="239f0-133">In **HelloWebView.cpp**, add `#include "WebView2.h"` below the lines of `#include`s.</span></span>

    ```cpp
    ...
    #include <wrl.h>
    #include <wil/com.h>
    // include WebView2 header
    #include "WebView2.h"
    ```

<span data-ttu-id="239f0-134">你已设置为对 WebView2 API 使用和构建。</span><span class="sxs-lookup"><span data-stu-id="239f0-134">You are all set to use and build against the WebView2 API.</span></span> <span data-ttu-id="239f0-135">按 F5 生成并运行示例应用。</span><span class="sxs-lookup"><span data-stu-id="239f0-135">Press F5 to build and run the sample app.</span></span> <span data-ttu-id="239f0-136">你应该会看到一个应用，显示一个空窗口。</span><span class="sxs-lookup"><span data-stu-id="239f0-136">You should see an app displaying an empty window.</span></span>

![空-应用](../media/empty-app.png)

## <span data-ttu-id="239f0-138">步骤 3-在父窗口中创建单个 Web 视图</span><span class="sxs-lookup"><span data-stu-id="239f0-138">Step 3 - Create a single WebView within the parent window</span></span>

<span data-ttu-id="239f0-139">现在，让我们将 Web 视图添加到主窗口。</span><span class="sxs-lookup"><span data-stu-id="239f0-139">Now let's add a WebView to the main window.</span></span> <span data-ttu-id="239f0-140">我们将用 `CreateCoreWebView2Environment` 来设置环境并找到 Microsoft Edge （Chromium）浏览器为控件供电。</span><span class="sxs-lookup"><span data-stu-id="239f0-140">We'll use `CreateCoreWebView2Environment` to set up the environment and locate the Microsoft Edge (Chromium) browser powering the control.</span></span> <span data-ttu-id="239f0-141">`CreateCoreWebView2EnvironmentWithOptions`如果你希望指定浏览器位置、用户文件夹、浏览器标记等，而不是使用默认设置，也可以使用此选项。</span><span class="sxs-lookup"><span data-stu-id="239f0-141">You can also use `CreateCoreWebView2EnvironmentWithOptions` if you want to specify browser location, user folder, browser flags, etc., instead of using the default setting.</span></span> <span data-ttu-id="239f0-142">完成后 `CreateCoreWebView2Environment` ，你将能够在 `ICoreWebView2Environment::CreateCoreWebView2Controller` `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` 回调和调用中调用 `ICoreWebView2Controller::get_CoreWebView2` 以获取关联的 web 视图。</span><span class="sxs-lookup"><span data-stu-id="239f0-142">Upon the completion of `CreateCoreWebView2Environment`, you'll be able to call `ICoreWebView2Environment::CreateCoreWebView2Controller` inside the `ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler` callback and call `ICoreWebView2Controller::get_CoreWebView2` to get the associated WebView.</span></span>

<span data-ttu-id="239f0-143">在回调中，我们还设置一些设置，调整 Web 视图大小以占用父窗口的100%，然后导航到 Bing。</span><span class="sxs-lookup"><span data-stu-id="239f0-143">In the callback, let's also set a few settings, resize the WebView to take 100% of the parent window, and navigate to Bing.</span></span>

<span data-ttu-id="239f0-144">将以下代码复制到**HelloWebView.cpp**和之间的 HelloWebView `// <-- WebView2 sample code starts here -->` 。 `// <-- WebView2 sample code ends here -->`</span><span class="sxs-lookup"><span data-stu-id="239f0-144">Copy the following code to **HelloWebView.cpp** between `// <-- WebView2 sample code starts here -->` and `// <-- WebView2 sample code ends here -->`.</span></span>

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
                // this is a redundant demo step as they are the default settings values
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

<span data-ttu-id="239f0-145">按 F5 构建并运行应用。</span><span class="sxs-lookup"><span data-stu-id="239f0-145">Press F5 to build and run the app.</span></span> <span data-ttu-id="239f0-146">现在，你已有一个显示必应的 Web 视图窗口。</span><span class="sxs-lookup"><span data-stu-id="239f0-146">Now you have a WebView window displaying Bing.</span></span>

![必应窗口](../media/bing-window.png)

## <span data-ttu-id="239f0-148">步骤 4-导航事件</span><span class="sxs-lookup"><span data-stu-id="239f0-148">Step 4 - Navigation events</span></span>

<span data-ttu-id="239f0-149">我们已经介绍 `ICoreWebView2::Navigate` 了在上一步中使用 URL 的导航。</span><span class="sxs-lookup"><span data-stu-id="239f0-149">We already covered navigating to URL using `ICoreWebView2::Navigate` in the last step.</span></span> <span data-ttu-id="239f0-150">在导航过程中，web 视图会触发主机可以侦听的事件序列- `NavigationStarting` 、、、 `SourceChanged` `ContentLoading` `HistoryChanged` 和 `NavigationCompleted` 。</span><span class="sxs-lookup"><span data-stu-id="239f0-150">During navigation, WebView fires a sequence of events that the host can listen to - `NavigationStarting`, `SourceChanged`, `ContentLoading`, `HistoryChanged`, and then `NavigationCompleted`.</span></span> <span data-ttu-id="239f0-151">单击[此处](../reference/win32/0-9-538/ICoreWebView2.md#navigation-events)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="239f0-151">Click [here](../reference/win32/0-9-538/ICoreWebView2.md#navigation-events) to learn more.</span></span>

![导航事件](../media/navigation-events.png)

<span data-ttu-id="239f0-153">在错误情况下，可能有也可能不是 `SourceChanged` 、或不是 `ContentLoading` 事件， `HistoryChanged` 具体取决于导航是否转到错误页面。</span><span class="sxs-lookup"><span data-stu-id="239f0-153">In error cases there may or may not be `SourceChanged`, `ContentLoading`, or `HistoryChanged` event(s) depending on whether the navigation is continued to an error page.</span></span> <span data-ttu-id="239f0-154">如果是 HTTP 重定向，一行中将有多个 `NavigationStarting` 事件。</span><span class="sxs-lookup"><span data-stu-id="239f0-154">In case of an HTTP redirect, there will be multiple `NavigationStarting` events in a row.</span></span>

<span data-ttu-id="239f0-155">作为利用这些事件的示例，我们将注册一个用于 `NavigationStarting` 取消任何非 https 请求的处理程序。</span><span class="sxs-lookup"><span data-stu-id="239f0-155">As an example of utilizing those events, let's register a handler for `NavigationStarting` to cancel any non-https requests.</span></span> <span data-ttu-id="239f0-156">将以下代码复制到下面的**HelloWebView** `// Step 4 - Navigation events` 。</span><span class="sxs-lookup"><span data-stu-id="239f0-156">Copy the following code to **HelloWebView.cpp** below `// Step 4 - Navigation events`.</span></span>

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

<span data-ttu-id="239f0-157">现在，应用将不会导航到任何非 https 网站。</span><span class="sxs-lookup"><span data-stu-id="239f0-157">Now the app will not navigate to any non-https sites.</span></span> <span data-ttu-id="239f0-158">可以使用类似的机制来完成其他任务，如限制导航到您自己的域内。</span><span class="sxs-lookup"><span data-stu-id="239f0-158">You can use similar mechanism to accomplish other tasks, such as restricting navigation to within your own domain.</span></span>

## <span data-ttu-id="239f0-159">步骤 5-脚本</span><span class="sxs-lookup"><span data-stu-id="239f0-159">Step 5 - Scripting</span></span>

<span data-ttu-id="239f0-160">托管应用还可以将 JavaScript 插入 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="239f0-160">The hosting app can also inject JavaScript into WebView.</span></span> <span data-ttu-id="239f0-161">你可以通过任务 Web 视图执行任意 JavaScript 或添加初始化脚本。</span><span class="sxs-lookup"><span data-stu-id="239f0-161">You can task WebView to execute arbitrary JavaScript or add initialization scripts.</span></span> <span data-ttu-id="239f0-162">已添加的初始化脚本将应用于所有未来的顶级文档和子框架导航，直到被删除，并在创建全局对象之后以及执行 HTML 文档包括的任何其他脚本之前运行。</span><span class="sxs-lookup"><span data-stu-id="239f0-162">Added initialization scripts apply to all future top level document and child frame navigation until removed, and run after the global object has been created and before any other script included by the HTML document is executed.</span></span>

<span data-ttu-id="239f0-163">复制以下代码 `// Step 5 - Scripting` 。</span><span class="sxs-lookup"><span data-stu-id="239f0-163">Copy the following code below `// Step 5 - Scripting`.</span></span>

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

<span data-ttu-id="239f0-164">现在，Web 视图将始终冻结对象对象并返回页面文档一次。</span><span class="sxs-lookup"><span data-stu-id="239f0-164">Now WebView will always freeze the Object object and return the page document once.</span></span>

**<span data-ttu-id="239f0-165">请注意，这些脚本注入 Api （和某些其他 WebView2 Api）是异步的，因此如果按特定顺序执行代码，则应使用回调。</span><span class="sxs-lookup"><span data-stu-id="239f0-165">Note that these script injection APIs (and some other WebView2 APIs) are asynchronous, you should use callbacks if code is to be executed in a particular order.</span></span>**

## <span data-ttu-id="239f0-166">步骤 6-主机和 web 内容之间的通信</span><span class="sxs-lookup"><span data-stu-id="239f0-166">Step 6 - Communication between host and web content</span></span>

<span data-ttu-id="239f0-167">宿主和 web 内容也可以通过进行通信 `postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="239f0-167">The host and the web content can also communicate with each other through `postMessage`.</span></span> <span data-ttu-id="239f0-168">在 web 视图内运行的 web 内容可以通过主机发布到主机 `window.chrome.webview.postMessage` ，并且该消息将由主机上注册的任何内容处理 `ICoreWebView2WebMessageReceivedEventHandler` 。</span><span class="sxs-lookup"><span data-stu-id="239f0-168">The web content running within a WebView can post to the host through `window.chrome.webview.postMessage`, and the message would be handled by any registered `ICoreWebView2WebMessageReceivedEventHandler` on the host.</span></span> <span data-ttu-id="239f0-169">同样，主机可以通过或将 web 内容发送 `ICoreWebView2::PostWebMessageAsString` 给 `ICoreWebView2::PostWebMessageAsJSON` ，这些内容将由从添加的处理程序捕获 `window.chrome.webview.addEventListener` 。</span><span class="sxs-lookup"><span data-stu-id="239f0-169">Likewise, the host can message the web content through `ICoreWebView2::PostWebMessageAsString` or `ICoreWebView2::PostWebMessageAsJSON`, which would be caught by handlers added from `window.chrome.webview.addEventListener`.</span></span> <span data-ttu-id="239f0-170">通信机制允许 web 内容通过将消息传递给请求主机调用本机 Api 来利用本机功能。</span><span class="sxs-lookup"><span data-stu-id="239f0-170">The communication mechanism allows the web content to utilize native capabilities by passing messages to ask the host to call native APIs.</span></span>

<span data-ttu-id="239f0-171">例如，若要了解该机制，请尝试在 Web 视图中使用很少的 detour 来打印文档 URL。</span><span class="sxs-lookup"><span data-stu-id="239f0-171">As an example to understand the mechanism, let's try printing out the document URL in WebView with a little detour,</span></span>

1. <span data-ttu-id="239f0-172">主机注册处理程序以返回收到的消息，返回到 web 内容</span><span class="sxs-lookup"><span data-stu-id="239f0-172">the host registers a handler to return received message back to the web content</span></span>
2. <span data-ttu-id="239f0-173">主机将向注册处理程序的 web 内容插入脚本，以便从主机打印消息</span><span class="sxs-lookup"><span data-stu-id="239f0-173">the host injects a script to the web content that registers a handler to print message from the host</span></span>
3. <span data-ttu-id="239f0-174">主机为将 URL 发布到主机的 web 内容插入脚本</span><span class="sxs-lookup"><span data-stu-id="239f0-174">the host injects a script to the web content that posts the URL to the host</span></span>
4. <span data-ttu-id="239f0-175">将触发主机的处理程序，并将消息（URL）返回到 web 内容</span><span class="sxs-lookup"><span data-stu-id="239f0-175">the host's handler is triggered and returns the message (the URL) to the web content</span></span>
5. <span data-ttu-id="239f0-176">web 内容的处理程序被触发，并打印宿主的消息（URL）</span><span class="sxs-lookup"><span data-stu-id="239f0-176">the web content's handler is triggered and prints the host's message (the URL)</span></span>

<span data-ttu-id="239f0-177">复制以下代码 `// Step 6 - Communication between host and web content` ，</span><span class="sxs-lookup"><span data-stu-id="239f0-177">Copy the following code below `// Step 6 - Communication between host and web content`,</span></span>

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

<span data-ttu-id="239f0-178">按 F5 构建并运行应用。</span><span class="sxs-lookup"><span data-stu-id="239f0-178">Press F5 to build and run the app.</span></span> <span data-ttu-id="239f0-179">在导航到页面之前，它现在将显示 Url。</span><span class="sxs-lookup"><span data-stu-id="239f0-179">It will now show URLs before navigating to pages.</span></span>

![show-url](../media/show-url.png)

<span data-ttu-id="239f0-181">恭喜，你刚刚构建了你的第一个 WebView2 应用！</span><span class="sxs-lookup"><span data-stu-id="239f0-181">Congratulations, you've just built your first WebView2 app!</span></span>

## <span data-ttu-id="239f0-182">后续步骤</span><span class="sxs-lookup"><span data-stu-id="239f0-182">Next Steps</span></span>

<span data-ttu-id="239f0-183">本演练中不包含大量 WebView2 功能。</span><span class="sxs-lookup"><span data-stu-id="239f0-183">There are plenty of WebView2 functionalities that are not covered in this walkthrough.</span></span>

<span data-ttu-id="239f0-184">若要了解详细信息：</span><span class="sxs-lookup"><span data-stu-id="239f0-184">To learn more:</span></span>

* <span data-ttu-id="239f0-185">签出[WEBVIEW2 API 示例](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample)，获取 WebView2's 功能的全面示例。</span><span class="sxs-lookup"><span data-stu-id="239f0-185">Checkout [WebView2 API Sample](https://github.com/MicrosoftEdge/WebView2Samples/tree/master/WebView2APISample) for a comprehensive example of WebView2's capabilities.</span></span>
* <span data-ttu-id="239f0-186">签出[WebView2Browser](https://github.com/MicrosoftEdge/WebView2Browser)使用 WebView2 创建的应用程序。</span><span class="sxs-lookup"><span data-stu-id="239f0-186">Checkout [WebView2Browser](https://github.com/MicrosoftEdge/WebView2Browser) an application built using WebView2.</span></span>
* <span data-ttu-id="239f0-187">有关我们的 API 的详细信息，请浏览[api 参考](../reference/win32/0-9-538-reference-webview2.md)。</span><span class="sxs-lookup"><span data-stu-id="239f0-187">Please explore [API reference](../reference/win32/0-9-538-reference-webview2.md) for detailed information about our API.</span></span>  

## <span data-ttu-id="239f0-188">与 WebView2 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="239f0-188">Getting in touch with the WebView2 team</span></span>  

<span data-ttu-id="239f0-189">通过分享你的反馈帮助我们构建更丰富的 WebView2 体验！</span><span class="sxs-lookup"><span data-stu-id="239f0-189">Help us build a richer WebView2 experience by sharing your feedback!</span></span> <span data-ttu-id="239f0-190">请访问我们的[反馈](https://aka.ms/webviewfeedback)存储库以提交功能请求或 bug 报告或搜索已知问题。</span><span class="sxs-lookup"><span data-stu-id="239f0-190">Visit our [feedback repo](https://aka.ms/webviewfeedback) to submit feature requests or bug reports or search for known issues.</span></span>
