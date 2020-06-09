---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: d8cc43e7535be94448ae100e3298e35ec47f94d3
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698048"
---
# interface ICoreWebView2Environment 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface ICoreWebView2Environment
  : public IUnknown
```

这表示 WebView2 环境。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[add_NewBrowserVersionAvailable](#add_newbrowserversionavailable) | 当已安装更高版本的 Edge 浏览器并可通过 WebView2 使用时，将引发 NewBrowserVersionAvailable 事件。
[CreateCoreWebView2Controller](#createcorewebview2controller) | 异步创建新的 Web 视图。
[CreateWebResourceResponse](#createwebresourceresponse) | 创建新的 web 资源响应对象。
[get_BrowserVersionString](#get_browserversionstring) | 当前[ICoreWebView2Environment]()的浏览器版本信息，包括频道名称（如果不是稳定频道）。
[remove_NewBrowserVersionAvailable](#remove_newbrowserversionavailable) | 删除以前使用 add_NewBrowserVersionAvailable 添加的事件处理程序。

在使用环境参数指定的浏览器进程中运行的环境中创建的 WebViews，应在同一环境中使用。 在不同的环境中使用它不保证兼容，并且可能会失败。

## 成员

#### add_NewBrowserVersionAvailable 

当已安装更高版本的 Edge 浏览器并可通过 WebView2 使用时，将引发 NewBrowserVersionAvailable 事件。

> public HRESULT [add_NewBrowserVersionAvailable](#add_newbrowserversionavailable)（[ICoreWebView2NewBrowserVersionAvailableEventHandler](icorewebview2newbrowserversionavailableeventhandler.md) * eventHandler，EventRegistrationToken * token）

若要使用较新版本的浏览器，必须创建新的环境和 Web 视图。 将仅针对从其运行代码的同一边缘通道中的新版本引发此事件。 当不运行安装的边缘时，将不会触发任何事件。

由于用户数据文件夹一次只能由一个浏览器进程使用，如果要在 WebViews 中使用新版本的浏览器使用同一用户数据文件夹，则必须先关闭使用早期版本的浏览器的环境和 WebViews。 或者只提示用户重新启动应用。

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

#### CreateCoreWebView2Controller 

异步创建新的 Web 视图。

> 公共 HRESULT [CreateCoreWebView2Controller](#createcorewebview2controller)（HWND ParentWindow， [ICoreWebView2CreateCoreWebView2ControllerCompletedHandler](icorewebview2createcorewebview2controllercompletedhandler.md) * 处理程序）

parentWindow 是应在其中显示 Web 视图和接收输入的 HWND。 在创建 Web 视图期间，Web 视图会将子窗口添加到提供的窗口中。 由同辈窗口顺序影响的 Z 顺序和其他项目将相应受到影响。

建议为进程或应用程序窗口设置应用程序用户模型 ID。 如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。 
```cpp
// Create or recreate the WebView and its environment.
void AppWindow::InitializeWebView()
{
    // To ensure browser switches get applied correctly, we need to close
    // the existing WebView. This will result in a new browser process
    // getting created which will apply the browser switches.
    CloseWebView();
    m_dcompDevice = nullptr;
    m_wincompHelper = nullptr;

    LPCWSTR subFolder = nullptr;

    if (m_creationModeId == IDM_CREATION_MODE_VISUAL_DCOMP)
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
        HRESULT hr = CreateWinCompCompositor();
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
    }
    auto options = Microsoft::WRL::Make<CoreWebView2EnvironmentOptions>();
    if(!m_language.empty())
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
    if (webViewExperimentalEnvironment && (m_dcompDevice || m_wincompHelper))
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
 建议应用程序处理重启管理器消息，以便当应用在特定安装中使用 web 视图的边缘且正在卸载该安装时，它可以正常重启。 例如，如果用户从开发频道安装 Edge，并使用该通道中的边缘来测试应用，然后从该通道卸载 Edge 而不关闭应用，则应用将重新启动以允许卸载开发人员通道。 
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
 当应用程序在失败时重试 CreateCoreWebView2Controller 时，建议应用程序从创建新的 WebView2 环境中重新启动。 如果发生边缘更新，则与 WebView2 环境相关联的版本可能已被删除，导致该对象不再工作。 创建新的 WebView2 环境将起作用，因为它使用最新版本。

如果已存在使用相同用户数据文件夹的正在运行的实例，并且环境对象具有不同的 EnvironmentOptions，则 Web 视图创建将失败。 例如，如果已有使用一种语言创建的 Web 视图，尝试使用同一用户数据文件夹创建使用不同语言的 Web 视图将失败。

#### CreateWebResourceResponse 

创建新的 web 资源响应对象。

> public HRESULT [CreateWebResourceResponse](#createwebresourceresponse)（IStream * 内容、int STATUSCODE、LPCWSTR REASONPHRASE、LPCWSTR 标头、 [ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) * * * response）

标头是由换行符分隔的原始响应标题字符串。 也可以使用空的标头字符串创建此对象，然后使用[ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md)来逐行构造标题。 有关其他参数的信息，请参阅[ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md)。

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

#### get_BrowserVersionString 

当前[ICoreWebView2Environment]()的浏览器版本信息，包括频道名称（如果不是稳定频道）。

> 公共 HRESULT [get_BrowserVersionString](#get_browserversionstring)（LPWSTR * versionInfo）

这与 GetAvailableCoreWebView2BrowserVersionString API 的格式相匹配。 信道名称为 "beta"、"dev" 和 "未设备"。

```cpp
        wil::unique_cotaskmem_string version_info;
        m_webViewEnvironment->get_BrowserVersionString(&version_info);
        MessageBox(
            m_mainWindow, version_info.get(), L"Browser Version Info After WebView Creation",
            MB_OK);
```

#### remove_NewBrowserVersionAvailable 

删除以前使用 add_NewBrowserVersionAvailable 添加的事件处理程序。

> public HRESULT [remove_NewBrowserVersionAvailable](#remove_newbrowserversionavailable)（EventRegistrationToken 标记）

