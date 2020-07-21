---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExperimentalEnvironment
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalEnvironment
ms.openlocfilehash: 70e2ceab124b60c355f94161d2d25e49953520ca
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886456"
---
# <span data-ttu-id="45c3e-104">interface ICoreWebView2ExperimentalEnvironment</span><span class="sxs-lookup"><span data-stu-id="45c3e-104">interface ICoreWebView2ExperimentalEnvironment</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalEnvironment
  : public IUnknown
```

<span data-ttu-id="45c3e-105">此接口是[ICoreWebView2Environment](icorewebview2environment.md)的扩展。</span><span class="sxs-lookup"><span data-stu-id="45c3e-105">This interface is an extension of the [ICoreWebView2Environment](icorewebview2environment.md).</span></span>

## <span data-ttu-id="45c3e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="45c3e-106">Summary</span></span>

 <span data-ttu-id="45c3e-107">成员</span><span class="sxs-lookup"><span data-stu-id="45c3e-107">Members</span></span>                        | <span data-ttu-id="45c3e-108">描述</span><span class="sxs-lookup"><span data-stu-id="45c3e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="45c3e-109">CreateCoreWebView2CompositionController</span><span class="sxs-lookup"><span data-stu-id="45c3e-109">CreateCoreWebView2CompositionController</span></span>](#createcorewebview2compositioncontroller) | <span data-ttu-id="45c3e-110">异步创建用于可视化托管的新 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="45c3e-110">Asynchronously create a new WebView for use with visual hosting.</span></span>
[<span data-ttu-id="45c3e-111">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="45c3e-111">CreateCoreWebView2PointerInfo</span></span>](#createcorewebview2pointerinfo) | <span data-ttu-id="45c3e-112">创建一个空[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)。</span><span class="sxs-lookup"><span data-stu-id="45c3e-112">Create an empty [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>
[<span data-ttu-id="45c3e-113">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="45c3e-113">GetProviderForHwnd</span></span>](#getproviderforhwnd) | <span data-ttu-id="45c3e-114">返回与给定 HWND 对应的 ICoreWebView2CompositionController 的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="45c3e-114">Returns the UI Automation Provider for the ICoreWebView2CompositionController that corresponds with the given HWND.</span></span>

<span data-ttu-id="45c3e-115">实现[ICoreWebView2ExperimentalEnvironment]()接口的对象也将实现[ICoreWebView2Environment](icorewebview2environment.md)。</span><span class="sxs-lookup"><span data-stu-id="45c3e-115">An object implementing the [ICoreWebView2ExperimentalEnvironment]() interface will also implement [ICoreWebView2Environment](icorewebview2environment.md).</span></span>

## <span data-ttu-id="45c3e-116">成员</span><span class="sxs-lookup"><span data-stu-id="45c3e-116">Members</span></span>

#### <span data-ttu-id="45c3e-117">CreateCoreWebView2CompositionController</span><span class="sxs-lookup"><span data-stu-id="45c3e-117">CreateCoreWebView2CompositionController</span></span> 

<span data-ttu-id="45c3e-118">异步创建用于可视化托管的新 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="45c3e-118">Asynchronously create a new WebView for use with visual hosting.</span></span>

> <span data-ttu-id="45c3e-119">公共 HRESULT [CreateCoreWebView2CompositionController](#createcorewebview2compositioncontroller)（HWND ParentWindow， [ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler](icorewebview2experimentalcreatecorewebview2compositioncontrollercompletedhandler.md) \* 处理程序）</span><span class="sxs-lookup"><span data-stu-id="45c3e-119">public HRESULT [CreateCoreWebView2CompositionController](#createcorewebview2compositioncontroller)(HWND parentWindow, [ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler](icorewebview2experimentalcreatecorewebview2compositioncontrollercompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="45c3e-120">parentWindow 是应用将连接 Web 视图的可视化树的 HWND。</span><span class="sxs-lookup"><span data-stu-id="45c3e-120">parentWindow is the HWND in which the app will connect the visual tree of the WebView.</span></span> <span data-ttu-id="45c3e-121">这将是应用将接收指向 Web 视图的指针/鼠标输入的 HWND （并且将需要使用 SendMouseInput/SendPointerInput 转发）。</span><span class="sxs-lookup"><span data-stu-id="45c3e-121">This will be the HWND that the app will receive pointer/ mouse input meant for the WebView (and will need to use SendMouseInput/ SendPointerInput to forward).</span></span> <span data-ttu-id="45c3e-122">如果应用将 Web 视图可视化树移动到另一个窗口下方，则需要调用 put_ParentWindow 以更新可视化树的新父 HWND。</span><span class="sxs-lookup"><span data-stu-id="45c3e-122">If the app moves the WebView visual tree to underneath a different window, then it needs to call put_ParentWindow to update the new parent HWND of the visual tree.</span></span>

<span data-ttu-id="45c3e-123">在创建的 CoreWebView2CompositionController 上使用 put_RootVisualTarget 来提供视觉对象以托管浏览器的可视化树。</span><span class="sxs-lookup"><span data-stu-id="45c3e-123">Use put_RootVisualTarget on the created CoreWebView2CompositionController to provide a visual to host the browser's visual tree.</span></span>

<span data-ttu-id="45c3e-124">建议为进程或应用程序窗口设置应用程序用户模型 ID。</span><span class="sxs-lookup"><span data-stu-id="45c3e-124">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="45c3e-125">如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。</span><span class="sxs-lookup"><span data-stu-id="45c3e-125">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span> 
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
    auto options = Microsoft::WRL::Make<CoreWebView2ExperimentalEnvironmentOptions>();
    CHECK_FAILURE(options->put_IsSingleSignOnUsingOSPrimaryAccountEnabled(
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
 <span data-ttu-id="45c3e-126">建议应用程序处理重启管理器消息，以便当应用在特定安装中使用 web 视图的边缘且正在卸载该安装时，它可以正常重启。</span><span class="sxs-lookup"><span data-stu-id="45c3e-126">It is recommended that the application handles restart manager messages so that it can be restarted gracefully in the case when the app is using Edge for webview from a certain installation and that installation is being uninstalled.</span></span> <span data-ttu-id="45c3e-127">例如，如果用户从开发频道安装 Edge，并使用该通道中的边缘来测试应用，然后从该通道卸载 Edge 而不关闭应用，则应用将重新启动以允许卸载开发人员通道。</span><span class="sxs-lookup"><span data-stu-id="45c3e-127">For example, if a user installs Edge from Dev channel and opts to use Edge from that channel for testing the app, and then uninstalls Edge from that channel without closing the app, the app will be restarted to allow uninstallation of the dev channel to succeed.</span></span> 
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

#### <span data-ttu-id="45c3e-128">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="45c3e-128">CreateCoreWebView2PointerInfo</span></span> 

<span data-ttu-id="45c3e-129">创建一个空[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)。</span><span class="sxs-lookup"><span data-stu-id="45c3e-129">Create an empty [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>

> <span data-ttu-id="45c3e-130">公共 HRESULT [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)（[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* \* pointerInfo）</span><span class="sxs-lookup"><span data-stu-id="45c3e-130">public HRESULT [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)([ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \*\* pointerInfo)</span></span>

<span data-ttu-id="45c3e-131">在调用 SendPointerInput 之前，需要用所有相关信息填充返回的[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) 。</span><span class="sxs-lookup"><span data-stu-id="45c3e-131">The returned [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) needs to be populated with all of the relevant info before calling SendPointerInput.</span></span>

#### <span data-ttu-id="45c3e-132">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="45c3e-132">GetProviderForHwnd</span></span> 

<span data-ttu-id="45c3e-133">返回与给定 HWND 对应的 ICoreWebView2CompositionController 的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="45c3e-133">Returns the UI Automation Provider for the ICoreWebView2CompositionController that corresponds with the given HWND.</span></span>

> <span data-ttu-id="45c3e-134">公共 HRESULT [GetProviderForHwnd](#getproviderforhwnd)（hwnd HWND，IUnknown \* \* 提供程序）</span><span class="sxs-lookup"><span data-stu-id="45c3e-134">public HRESULT [GetProviderForHwnd](#getproviderforhwnd)(HWND hwnd, IUnknown \*\* provider)</span></span>

