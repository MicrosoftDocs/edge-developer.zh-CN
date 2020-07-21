---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2Environment
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 81b6d9814af84995909112ea79f11fbfcf93b488
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886078"
---
# <span data-ttu-id="70165-104">0.8.355-接口 IWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="70165-104">0.8.355 - interface IWebView2Environment</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2Environment
  : public IUnknown
```

<span data-ttu-id="70165-105">这表示 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="70165-105">This represents the WebView2 Environment.</span></span>

## <span data-ttu-id="70165-106">摘要</span><span class="sxs-lookup"><span data-stu-id="70165-106">Summary</span></span>

 <span data-ttu-id="70165-107">成员</span><span class="sxs-lookup"><span data-stu-id="70165-107">Members</span></span>                        | <span data-ttu-id="70165-108">描述</span><span class="sxs-lookup"><span data-stu-id="70165-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="70165-109">CreateWebView</span><span class="sxs-lookup"><span data-stu-id="70165-109">CreateWebView</span></span>](#createwebview) | <span data-ttu-id="70165-110">异步创建新的[IWebView2WebView](IWebView2WebView.md)。</span><span class="sxs-lookup"><span data-stu-id="70165-110">Asynchronously create a new [IWebView2WebView](IWebView2WebView.md).</span></span>
[<span data-ttu-id="70165-111">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="70165-111">CreateWebResourceResponse</span></span>](#createwebresourceresponse) | <span data-ttu-id="70165-112">创建新的 web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="70165-112">Create a new web resource response object.</span></span>

<span data-ttu-id="70165-113">在使用环境参数指定的浏览器进程中运行的环境中创建的 WebViews，应在同一环境中使用。</span><span class="sxs-lookup"><span data-stu-id="70165-113">WebViews created from an environment run on the Browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="70165-114">在不同的环境中使用它不保证兼容，并且可能会失败。</span><span class="sxs-lookup"><span data-stu-id="70165-114">Using it in different environments are not guaranteed to be compatible and may fail.</span></span>

## <span data-ttu-id="70165-115">成员</span><span class="sxs-lookup"><span data-stu-id="70165-115">Members</span></span>

#### <span data-ttu-id="70165-116">CreateWebView</span><span class="sxs-lookup"><span data-stu-id="70165-116">CreateWebView</span></span> 

<span data-ttu-id="70165-117">异步创建新的[IWebView2WebView](IWebView2WebView.md)。</span><span class="sxs-lookup"><span data-stu-id="70165-117">Asynchronously create a new [IWebView2WebView](IWebView2WebView.md).</span></span>

> <span data-ttu-id="70165-118">公共 HRESULT [CreateWebView](#createwebview)（HWND ParentWindow，[IWebView2CreateWebViewCompletedHandler](IWebView2CreateWebViewCompletedHandler.md) \* 处理程序）</span><span class="sxs-lookup"><span data-stu-id="70165-118">public HRESULT [CreateWebView](#createwebview)(HWND parentWindow,[IWebView2CreateWebViewCompletedHandler](IWebView2CreateWebViewCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="70165-119">parentWindow 是应在其中显示 Web 视图和接收输入的 HWND。</span><span class="sxs-lookup"><span data-stu-id="70165-119">parentWindow is the HWND in which the WebView should be displayed and from which receive input.</span></span> <span data-ttu-id="70165-120">在创建 Web 视图期间，Web 视图会将子窗口添加到提供的窗口中。</span><span class="sxs-lookup"><span data-stu-id="70165-120">The WebView will add a child window to the provided window during WebView creation.</span></span> <span data-ttu-id="70165-121">由同辈窗口顺序影响的 Z 顺序和其他项目将相应受到影响。</span><span class="sxs-lookup"><span data-stu-id="70165-121">Z-order and other things impacted by sibling window order will be affected accordingly.</span></span>

<span data-ttu-id="70165-122">建议为进程或应用程序窗口设置应用程序用户模型 ID。</span><span class="sxs-lookup"><span data-stu-id="70165-122">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="70165-123">如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。</span><span class="sxs-lookup"><span data-stu-id="70165-123">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span> 

```cpp
// Create or recreate the WebView and its environment.
void AppWindow::InitializeWebView(InitializeWebViewFlags webviewInitFlags)
{
    m_lastUsedInitFlags = webviewInitFlags;
    // To ensure browser switches get applied correctly, we need to close
    // the existing WebView. This will result in a new browser process
    // getting created which will apply the browser switches.
    CloseWebView();

    LPCWSTR subFolder = nullptr;
    LPCWSTR additionalBrowserSwitches = nullptr;
    HRESULT hr = CreateWebView2EnvironmentWithDetails(
        subFolder, nullptr, additionalBrowserSwitches,
        Callback<IWebView2CreateWebView2EnvironmentCompletedHandler>(
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

// This is the callback passed to CreateWebViewEnvironmnetWithDetails.
// Here we simply create the WebView.
HRESULT AppWindow::OnCreateEnvironmentCompleted(
    HRESULT result, IWebView2Environment* environment)
{
    CHECK_FAILURE(result);

    CHECK_FAILURE(environment->QueryInterface(IID_PPV_ARGS(&m_webViewEnvironment)));
        CHECK_FAILURE(m_webViewEnvironment->CreateWebView(
            m_mainWindow, Callback<IWebView2CreateWebViewCompletedHandler>(
                              this, &AppWindow::OnCreateWebViewCompleted)
                              .Get()));
    return S_OK;
}
```

 <span data-ttu-id="70165-124">建议应用程序处理重启管理器消息，以便当应用在特定安装中使用 web 视图的边缘且正在卸载该安装时，它可以正常重启。</span><span class="sxs-lookup"><span data-stu-id="70165-124">It is recommended that the application handles restart manager messages so that it can be restarted gracefully in the case when the app is using Edge for webview from a certain installation and that installation is being uninstalled.</span></span> <span data-ttu-id="70165-125">例如，如果用户从开发频道安装 Edge，并使用该通道中的边缘来测试应用，然后从该通道卸载 Edge 而不关闭应用，则应用将重新启动以允许卸载开发人员通道。</span><span class="sxs-lookup"><span data-stu-id="70165-125">For example, if a user installs Edge from Dev channel and opts to use Edge from that channel for testing the app, and then uninstalls Edge from that channel without closing the app, the app will be restarted to allow uninstallation of the dev channel to succeed.</span></span> 

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

#### <span data-ttu-id="70165-126">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="70165-126">CreateWebResourceResponse</span></span> 

<span data-ttu-id="70165-127">创建新的 web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="70165-127">Create a new web resource response object.</span></span>

> <span data-ttu-id="70165-128">public HRESULT [CreateWebResourceResponse](#createwebresourceresponse)（IStream \* 内容、int STATUSCODE、LPCWSTR REASONPHRASE、LPCWSTR 标头、[IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* \* \* response）</span><span class="sxs-lookup"><span data-stu-id="70165-128">public HRESULT [CreateWebResourceResponse](#createwebresourceresponse)(IStream \* content,int statusCode,LPCWSTR reasonPhrase,LPCWSTR headers,[IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \*\* response)</span></span>

<span data-ttu-id="70165-129">标头是由换行符分隔的原始响应标题字符串。</span><span class="sxs-lookup"><span data-stu-id="70165-129">The headers is the raw response header string delimited by newline.</span></span> <span data-ttu-id="70165-130">也可以使用空的标头字符串创建此对象，然后使用[IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md)来逐行构造标题。</span><span class="sxs-lookup"><span data-stu-id="70165-130">It's also possible to create this object with empty headers string and then use the [IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md) to construct the headers line by line.</span></span> <span data-ttu-id="70165-131">有关其他参数的信息，请参阅[IWebView2WebResourceResponse](IWebView2WebResourceResponse.md)。</span><span class="sxs-lookup"><span data-stu-id="70165-131">For information on other parameters see [IWebView2WebResourceResponse](IWebView2WebResourceResponse.md).</span></span>

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<IWebView2WebResourceRequestedEventHandler>(
                    [this](
                        IWebView2WebView* sender,
                        IWebView2WebResourceRequestedEventArgs* args) {
                        wil::com_ptr<IWebView2WebResourceRequestedEventArgs2>
                            webResourceEventArgs2;
                        args->QueryInterface(IID_PPV_ARGS(&webResourceEventArgs2));
                        WEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            webResourceEventArgs2->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<IWebView2WebResourceResponse> response;
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

