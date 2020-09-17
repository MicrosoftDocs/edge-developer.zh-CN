---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2Environment
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2Environment
ms.openlocfilehash: 3552de59b8b349c62d61ca165141d9adddd2a5a9
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011629"
---
# <span data-ttu-id="0803a-104">interface ICoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="0803a-104">interface ICoreWebView2Environment</span></span> 

```
interface ICoreWebView2Environment
  : public IUnknown
```

<span data-ttu-id="0803a-105">这表示 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="0803a-105">This represents the WebView2 Environment.</span></span>

## <span data-ttu-id="0803a-106">摘要</span><span class="sxs-lookup"><span data-stu-id="0803a-106">Summary</span></span>

 <span data-ttu-id="0803a-107">成员</span><span class="sxs-lookup"><span data-stu-id="0803a-107">Members</span></span>                        | <span data-ttu-id="0803a-108">描述</span><span class="sxs-lookup"><span data-stu-id="0803a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0803a-109">add_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="0803a-109">add_NewBrowserVersionAvailable</span></span>](#add_newbrowserversionavailable) | <span data-ttu-id="0803a-110">为 NewBrowserVersionAvailable 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0803a-110">Add an event handler for the NewBrowserVersionAvailable event.</span></span>
[<span data-ttu-id="0803a-111">CreateCoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="0803a-111">CreateCoreWebView2Controller</span></span>](#createcorewebview2controller) | <span data-ttu-id="0803a-112">异步创建新的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="0803a-112">Asynchronously create a new WebView.</span></span>
[<span data-ttu-id="0803a-113">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="0803a-113">CreateWebResourceResponse</span></span>](#createwebresourceresponse) | <span data-ttu-id="0803a-114">创建新的 web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="0803a-114">Create a new web resource response object.</span></span>
[<span data-ttu-id="0803a-115">get_BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="0803a-115">get_BrowserVersionString</span></span>](#get_browserversionstring) | <span data-ttu-id="0803a-116">当前 [ICoreWebView2Environment]()的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="0803a-116">The browser version info of the current [ICoreWebView2Environment](), including channel name if it is not the stable channel.</span></span>
[<span data-ttu-id="0803a-117">remove_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="0803a-117">remove_NewBrowserVersionAvailable</span></span>](#remove_newbrowserversionavailable) | <span data-ttu-id="0803a-118">删除以前使用 add_NewBrowserVersionAvailable 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0803a-118">Remove an event handler previously added with add_NewBrowserVersionAvailable.</span></span>

<span data-ttu-id="0803a-119">在使用环境参数指定的浏览器进程中运行的环境中创建的 WebViews，应在同一环境中使用。</span><span class="sxs-lookup"><span data-stu-id="0803a-119">WebViews created from an environment run on the browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="0803a-120">在不同的环境中使用它不保证兼容，并且可能会失败。</span><span class="sxs-lookup"><span data-stu-id="0803a-120">Using it in different environments are not guaranteed to be compatible and may fail.</span></span>

## <span data-ttu-id="0803a-121">成员</span><span class="sxs-lookup"><span data-stu-id="0803a-121">Members</span></span>

#### <span data-ttu-id="0803a-122">add_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="0803a-122">add_NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="0803a-123">为 NewBrowserVersionAvailable 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0803a-123">Add an event handler for the NewBrowserVersionAvailable event.</span></span>

> <span data-ttu-id="0803a-124">公共 HRESULT [add_NewBrowserVersionAvailable](#add_newbrowserversionavailable) ([ICoreWebView2NewBrowserVersionAvailableEventHandler](icorewebview2newbrowserversionavailableeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="0803a-124">public HRESULT [add_NewBrowserVersionAvailable](#add_newbrowserversionavailable)([ICoreWebView2NewBrowserVersionAvailableEventHandler](icorewebview2newbrowserversionavailableeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="0803a-125">当已安装较新版本的 Edge 浏览器并可通过 WebView2 使用时，将触发 NewBrowserVersionAvailable。</span><span class="sxs-lookup"><span data-stu-id="0803a-125">NewBrowserVersionAvailable fires when a newer version of the Edge browser is installed and available for use via WebView2.</span></span> <span data-ttu-id="0803a-126">若要使用较新版本的浏览器，必须创建新的环境和 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="0803a-126">To use the newer version of the browser you must create a new environment and WebView.</span></span> <span data-ttu-id="0803a-127">将仅针对从其运行代码的同一边缘通道中的新版本引发此事件。</span><span class="sxs-lookup"><span data-stu-id="0803a-127">This event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="0803a-128">当不运行安装的边缘时，将不会触发任何事件。</span><span class="sxs-lookup"><span data-stu-id="0803a-128">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="0803a-129">由于用户数据文件夹一次只能由一个浏览器进程使用，如果要在 WebViews 中使用新版本的浏览器使用同一用户数据文件夹，则必须先关闭使用早期版本的浏览器的环境和 WebViews。</span><span class="sxs-lookup"><span data-stu-id="0803a-129">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the environment and WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="0803a-130">或者只提示用户重新启动应用。</span><span class="sxs-lookup"><span data-stu-id="0803a-130">Or simply prompt the user to restart the app.</span></span>

```cpp
    // After the environment is successfully created,
    // register a handler for the NewBrowserVersionAvailable event.
    // This handler tells when there is a new Edge version available on the machine.
    CHECK_FAILURE(m_webViewEnvironment->add_NewBrowserVersionAvailable(
        Callback<ICoreWebView2NewBrowserVersionAvailableEventHandler>(
            [this](ICoreWebView2Environment* sender, IUnknown* args) -> HRESULT {
                std::wstring message = L"We detected there is a new version for the browser.";
                if (m_webView)
                {
                    message += L"Do you want to restart the app? \n\n";
                    message += L"Click No if you only want to re-create the webviews. \n";
                    message += L"Click Cancel for no action. \n";
                }
                int response = MessageBox(
                    m_mainWindow, message.c_str(), L"New available version",
                    m_webView ? MB_YESNOCANCEL : MB_OK);

                if (response == IDYES)
                {
                    RestartApp();
                }
                else if (response == IDNO)
                {
                    ReinitializeWebViewWithNewBrowser();
                }
                else
                {
                    // do nothing
                }

                return S_OK;
            })
            .Get(),
        nullptr));
```

#### <span data-ttu-id="0803a-131">CreateCoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="0803a-131">CreateCoreWebView2Controller</span></span> 

<span data-ttu-id="0803a-132">异步创建新的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="0803a-132">Asynchronously create a new WebView.</span></span>

> <span data-ttu-id="0803a-133">公共 HRESULT [CreateCoreWebView2Controller](#createcorewebview2controller) (HWND ParentWindow， [ICoreWebView2CreateCoreWebView2ControllerCompletedHandler](icorewebview2createcorewebview2controllercompletedhandler.md) \* 处理程序) </span><span class="sxs-lookup"><span data-stu-id="0803a-133">public HRESULT [CreateCoreWebView2Controller](#createcorewebview2controller)(HWND parentWindow, [ICoreWebView2CreateCoreWebView2ControllerCompletedHandler](icorewebview2createcorewebview2controllercompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="0803a-134">parentWindow 是应在其中显示 Web 视图和接收输入的 HWND。</span><span class="sxs-lookup"><span data-stu-id="0803a-134">parentWindow is the HWND in which the WebView should be displayed and from which receive input.</span></span> <span data-ttu-id="0803a-135">在创建 Web 视图期间，Web 视图会将子窗口添加到提供的窗口中。</span><span class="sxs-lookup"><span data-stu-id="0803a-135">The WebView will add a child window to the provided window during WebView creation.</span></span> <span data-ttu-id="0803a-136">由同辈窗口顺序影响的 Z 顺序和其他项目将相应受到影响。</span><span class="sxs-lookup"><span data-stu-id="0803a-136">Z-order and other things impacted by sibling window order will be affected accordingly.</span></span>

<span data-ttu-id="0803a-137">建议为进程或应用程序窗口设置应用程序用户模型 ID。</span><span class="sxs-lookup"><span data-stu-id="0803a-137">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="0803a-138">如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。</span><span class="sxs-lookup"><span data-stu-id="0803a-138">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span> 
```cpp
// Create or recreate the WebView and its environment.
void AppWindow::InitializeWebView()
{
    // To ensure browser switches get applied correctly, we need to close
    // the existing WebView. This will result in a new browser process
    // getting created which will apply the browser switches.
    CloseWebView();
    m_dcompDevice = nullptr;
    m_wincompCompositor = nullptr;
    LPCWSTR subFolder = nullptr;

    if (m_creationModeId == IDM_CREATION_MODE_VISUAL_DCOMP ||
        m_creationModeId == IDM_CREATION_MODE_TARGET_DCOMP)
    {
        HRESULT hr = DCompositionCreateDevice2(nullptr, IID_PPV_ARGS(&m_dcompDevice));
        if (!SUCCEEDED(hr))
        {
            MessageBox(
                m_mainWindow,
                L"Attempting to create WebView using DComp Visual is not supported.\r\n"
                "DComp device creation failed.\r\n"
                "Current OS may not support DComp.",
                L"Create with Windowless DComp Visual Failed", MB_OK);
            return;
        }
    }
    else if (m_creationModeId == IDM_CREATION_MODE_VISUAL_WINCOMP)
    {
        HRESULT hr = TryCreateDispatcherQueue();
        if (!SUCCEEDED(hr))
        {
            MessageBox(
                m_mainWindow,
                L"Attempting to create WebView using WinComp Visual is not supported.\r\n"
                "WinComp compositor creation failed.\r\n"
                "Current OS may not support WinComp.",
                L"Create with Windowless WinComp Visual Failed", MB_OK);
            return;
        }
        m_wincompCompositor = winrtComp::Compositor();
    }
    auto options = Microsoft::WRL::Make<CoreWebView2EnvironmentOptions>();
    CHECK_FAILURE(options->put_AllowSingleSignOnUsingOSPrimaryAccount(
        m_AADSSOEnabled ? TRUE : FALSE));
    if (!m_language.empty())
        CHECK_FAILURE(options->put_Language(m_language.c_str()));
    HRESULT hr = CreateCoreWebView2EnvironmentWithOptions(
        subFolder, nullptr, options.Get(),
        Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
            this, &AppWindow::OnCreateEnvironmentCompleted)
            .Get());
    if (!SUCCEEDED(hr))
    {
        if (hr == HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND))
        {
            MessageBox(
                m_mainWindow,
                L"Couldn't find Edge installation. "
                "Do you have a version installed that's compatible with this "
                "WebView2 SDK version?",
                nullptr, MB_OK);
        }
        else
        {
            ShowFailure(hr, L"Failed to create webview environment");
        }
    }
}
// This is the callback passed to CreateWebViewEnvironmentWithOptions.
// Here we simply create the WebView.
HRESULT AppWindow::OnCreateEnvironmentCompleted(
    HRESULT result, ICoreWebView2Environment* environment)
{
    CHECK_FAILURE(result);
    m_webViewEnvironment = environment;

    auto webViewExperimentalEnvironment =
        m_webViewEnvironment.try_query<ICoreWebView2ExperimentalEnvironment>();
    if (webViewExperimentalEnvironment && (m_dcompDevice || m_wincompCompositor))
    {
        CHECK_FAILURE(webViewExperimentalEnvironment->CreateCoreWebView2CompositionController(
            m_mainWindow,
            Callback<
                ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler>(
                [this](
                    HRESULT result,
                    ICoreWebView2ExperimentalCompositionController* compositionController) -> HRESULT {
                    auto controller =
                        wil::com_ptr<ICoreWebView2ExperimentalCompositionController>(compositionController)
                            .query<ICoreWebView2Controller>();
                    return OnCreateCoreWebView2ControllerCompleted(result, controller.get());
                })
                .Get()));
    }
    else
    {
        CHECK_FAILURE(m_webViewEnvironment->CreateCoreWebView2Controller(
            m_mainWindow, Callback<ICoreWebView2CreateCoreWebView2ControllerCompletedHandler>(
                              this, &AppWindow::OnCreateCoreWebView2ControllerCompleted)
                              .Get()));
    }

    return S_OK;
}
```
 <span data-ttu-id="0803a-139">建议应用程序处理重启管理器消息，以便当应用在特定安装中使用 Web 视图的边缘且正在卸载该安装时，它可以正常重启。</span><span class="sxs-lookup"><span data-stu-id="0803a-139">It is recommended that the application handles restart manager messages so that it can be restarted gracefully in the case when the app is using Edge for WebView from a certain installation and that installation is being uninstalled.</span></span> <span data-ttu-id="0803a-140">例如，如果用户从开发频道安装 Edge，并使用该通道中的边缘来测试应用，然后从该通道卸载 Edge 而不关闭应用，则应用将重新启动以允许卸载开发人员通道。</span><span class="sxs-lookup"><span data-stu-id="0803a-140">For example, if a user installs Edge from Dev channel and opts to use Edge from that channel for testing the app, and then uninstalls Edge from that channel without closing the app, the app will be restarted to allow uninstallation of the dev channel to succeed.</span></span> 
```cpp
    case WM_QUERYENDSESSION:
    {
        // yes, we can shut down
        // Register how we might be restarted
        RegisterApplicationRestart(L"--restore", RESTART_NO_CRASH | RESTART_NO_HANG);
        *result = TRUE;
        return true;
    }
    break;
    case WM_ENDSESSION:
    {
        if (wParam == TRUE)
        {
            // save app state and exit.
            PostQuitMessage(0);
            return true;
        }
    }
    break;
```
 <span data-ttu-id="0803a-141">当应用程序在失败时重试 CreateCoreWebView2Controller 时，建议应用程序从创建新的 WebView2 环境中重新启动。</span><span class="sxs-lookup"><span data-stu-id="0803a-141">When the application retries CreateCoreWebView2Controller upon failure, it is recommended that the application restarts from creating a new WebView2 Environment.</span></span> <span data-ttu-id="0803a-142">如果发生边缘更新，则与 WebView2 环境相关联的版本可能已被删除，导致该对象不再工作。</span><span class="sxs-lookup"><span data-stu-id="0803a-142">If an Edge update happens, the version associated with a WebView2 Environment could have been removed and causing the object to no longer work.</span></span> <span data-ttu-id="0803a-143">创建新的 WebView2 环境将起作用，因为它使用最新版本。</span><span class="sxs-lookup"><span data-stu-id="0803a-143">Creating a new WebView2 Environment will work as it uses the latest version.</span></span>

<span data-ttu-id="0803a-144">如果已存在使用相同用户数据文件夹的正在运行的实例，并且环境对象具有不同的 EnvironmentOptions，则 Web 视图创建将失败。</span><span class="sxs-lookup"><span data-stu-id="0803a-144">WebView creation will fail if there is already a running instance using the same user data folder, and the Environment objects have different EnvironmentOptions.</span></span> <span data-ttu-id="0803a-145">例如，如果已有使用一种语言创建的 Web 视图，尝试使用同一用户数据文件夹创建使用不同语言的 Web 视图将失败。</span><span class="sxs-lookup"><span data-stu-id="0803a-145">For example, if there is already a WebView created with one language, trying to create a WebView with a different language using the same user data folder will fail.</span></span>

#### <span data-ttu-id="0803a-146">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="0803a-146">CreateWebResourceResponse</span></span> 

<span data-ttu-id="0803a-147">创建新的 web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="0803a-147">Create a new web resource response object.</span></span>

> <span data-ttu-id="0803a-148">public HRESULT [CreateWebResourceResponse](#createwebresourceresponse) (IStream \* 内容、int STATUSCODE、LPCWSTR REASONPHRASE、LPCWSTR 标头、 [ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* \* response) </span><span class="sxs-lookup"><span data-stu-id="0803a-148">public HRESULT [CreateWebResourceResponse](#createwebresourceresponse)(IStream \* content, int statusCode, LPCWSTR reasonPhrase, LPCWSTR headers, [ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \*\* response)</span></span>

<span data-ttu-id="0803a-149">标头是由换行符分隔的原始响应标题字符串。</span><span class="sxs-lookup"><span data-stu-id="0803a-149">The headers is the raw response header string delimited by newline.</span></span> <span data-ttu-id="0803a-150">也可以使用空的标头字符串创建此对象，然后使用 [ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) 来逐行构造标题。</span><span class="sxs-lookup"><span data-stu-id="0803a-150">It's also possible to create this object with empty headers string and then use the [ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) to construct the headers line by line.</span></span> <span data-ttu-id="0803a-151">有关其他参数的信息，请参阅 [ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md)。</span><span class="sxs-lookup"><span data-stu-id="0803a-151">For information on other parameters see [ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md).</span></span>

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<ICoreWebView2WebResourceRequestedEventHandler>(
                    [this](
                        ICoreWebView2* sender,
                        ICoreWebView2WebResourceRequestedEventArgs* args) {
                        COREWEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            args->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<ICoreWebView2WebResourceResponse> response;
                        CHECK_FAILURE(m_webViewEnvironment->CreateWebResourceResponse(
                            nullptr, 403 /*NoContent*/, L"Blocked", L"", &response));
                        CHECK_FAILURE(args->put_Response(response.get()));
                        return S_OK;
                    })
                    .Get(),
                &m_webResourceRequestedTokenForImageBlocking));
        }
        else
        {
            CHECK_FAILURE(m_webView->remove_WebResourceRequested(
                m_webResourceRequestedTokenForImageBlocking));
        }
```

#### <span data-ttu-id="0803a-152">get_BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="0803a-152">get_BrowserVersionString</span></span> 

<span data-ttu-id="0803a-153">当前 [ICoreWebView2Environment]()的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="0803a-153">The browser version info of the current [ICoreWebView2Environment](), including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="0803a-154">公共 HRESULT [get_BrowserVersionString](#get_browserversionstring) (LPWSTR \* versionInfo) </span><span class="sxs-lookup"><span data-stu-id="0803a-154">public HRESULT [get_BrowserVersionString](#get_browserversionstring)(LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="0803a-155">这与 GetAvailableCoreWebView2BrowserVersionString API 的格式相匹配。</span><span class="sxs-lookup"><span data-stu-id="0803a-155">This matches the format of the GetAvailableCoreWebView2BrowserVersionString API.</span></span> <span data-ttu-id="0803a-156">信道名称为 "beta"、"dev" 和 "未设备"。</span><span class="sxs-lookup"><span data-stu-id="0803a-156">Channel names are 'beta', 'dev', and 'canary'.</span></span>

```cpp
        wil::unique_cotaskmem_string version_info;
        m_webViewEnvironment->get_BrowserVersionString(&version_info);
        MessageBox(
            m_mainWindow, version_info.get(), L"Browser Version Info After WebView Creation",
            MB_OK);
```

#### <span data-ttu-id="0803a-157">remove_NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="0803a-157">remove_NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="0803a-158">删除以前使用 add_NewBrowserVersionAvailable 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0803a-158">Remove an event handler previously added with add_NewBrowserVersionAvailable.</span></span>

> <span data-ttu-id="0803a-159">公共 HRESULT [remove_NewBrowserVersionAvailable](#remove_newbrowserversionavailable) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="0803a-159">public HRESULT [remove_NewBrowserVersionAvailable](#remove_newbrowserversionavailable)(EventRegistrationToken token)</span></span>
