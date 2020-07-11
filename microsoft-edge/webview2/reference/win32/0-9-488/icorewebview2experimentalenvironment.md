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
ms.openlocfilehash: 4adfa6fa899ce5079f9a1dc2cad78673d2cc899d
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653105"
---
# <span data-ttu-id="aebb7-104">interface ICoreWebView2ExperimentalEnvironment</span><span class="sxs-lookup"><span data-stu-id="aebb7-104">interface ICoreWebView2ExperimentalEnvironment</span></span> 

> [!NOTE]
> <span data-ttu-id="aebb7-105">这是使用预发行 SDK 版本0.9.488 随附的实验性 API。</span><span class="sxs-lookup"><span data-stu-id="aebb7-105">This an experimental API that is shipped with our prerelease SDK version 0.9.488.</span></span>

```
interface ICoreWebView2ExperimentalEnvironment
  : public IUnknown
```

<span data-ttu-id="aebb7-106">此接口是[ICoreWebView2Environment](icorewebview2environment.md)的扩展。</span><span class="sxs-lookup"><span data-stu-id="aebb7-106">This interface is an extension of the [ICoreWebView2Environment](icorewebview2environment.md).</span></span>

## <span data-ttu-id="aebb7-107">摘要</span><span class="sxs-lookup"><span data-stu-id="aebb7-107">Summary</span></span>

 <span data-ttu-id="aebb7-108">成员</span><span class="sxs-lookup"><span data-stu-id="aebb7-108">Members</span></span>                        | <span data-ttu-id="aebb7-109">描述</span><span class="sxs-lookup"><span data-stu-id="aebb7-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="aebb7-110">CreateCoreWebView2CompositionController</span><span class="sxs-lookup"><span data-stu-id="aebb7-110">CreateCoreWebView2CompositionController</span></span>](#createcorewebview2compositioncontroller) | <span data-ttu-id="aebb7-111">异步创建用于可视化托管的新 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="aebb7-111">Asynchronously create a new WebView for use with visual hosting.</span></span>
[<span data-ttu-id="aebb7-112">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="aebb7-112">CreateCoreWebView2PointerInfo</span></span>](#createcorewebview2pointerinfo) | <span data-ttu-id="aebb7-113">创建一个空[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)。</span><span class="sxs-lookup"><span data-stu-id="aebb7-113">Create an empty [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>
[<span data-ttu-id="aebb7-114">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="aebb7-114">GetProviderForHwnd</span></span>](#getproviderforhwnd) | <span data-ttu-id="aebb7-115">返回与给定 HWND 对应的 ICoreWebView2CompositionController 的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="aebb7-115">Returns the UI Automation Provider for the ICoreWebView2CompositionController that corresponds with the given HWND.</span></span>

<span data-ttu-id="aebb7-116">实现[ICoreWebView2ExperimentalEnvironment]()接口的对象也将实现[ICoreWebView2Environment](icorewebview2environment.md)。</span><span class="sxs-lookup"><span data-stu-id="aebb7-116">An object implementing the [ICoreWebView2ExperimentalEnvironment]() interface will also implement [ICoreWebView2Environment](icorewebview2environment.md).</span></span>

## <span data-ttu-id="aebb7-117">成员</span><span class="sxs-lookup"><span data-stu-id="aebb7-117">Members</span></span>

#### <span data-ttu-id="aebb7-118">CreateCoreWebView2CompositionController</span><span class="sxs-lookup"><span data-stu-id="aebb7-118">CreateCoreWebView2CompositionController</span></span> 

<span data-ttu-id="aebb7-119">异步创建用于可视化托管的新 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="aebb7-119">Asynchronously create a new WebView for use with visual hosting.</span></span>

> <span data-ttu-id="aebb7-120">公共 HRESULT [CreateCoreWebView2CompositionController](#createcorewebview2compositioncontroller) (HWND ParentWindow， [ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler](icorewebview2experimentalcreatecorewebview2compositioncontrollercompletedhandler.md) \* 处理程序) </span><span class="sxs-lookup"><span data-stu-id="aebb7-120">public HRESULT [CreateCoreWebView2CompositionController](#createcorewebview2compositioncontroller)(HWND parentWindow, [ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler](icorewebview2experimentalcreatecorewebview2compositioncontrollercompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="aebb7-121">parentWindow 是应用将连接 Web 视图的可视化树的 HWND。</span><span class="sxs-lookup"><span data-stu-id="aebb7-121">parentWindow is the HWND in which the app will connect the visual tree of the WebView.</span></span> <span data-ttu-id="aebb7-122">这将是应用将接收指向 Web 视图的指针/鼠标输入的 HWND (并且需要使用 SendMouseInput/SendPointerInput 转发) 。</span><span class="sxs-lookup"><span data-stu-id="aebb7-122">This will be the HWND that the app will receive pointer/ mouse input meant for the WebView (and will need to use SendMouseInput/ SendPointerInput to forward).</span></span> <span data-ttu-id="aebb7-123">如果应用将 Web 视图可视化树移动到另一个窗口下方，则需要调用 put_ParentWindow 以更新可视化树的新父 HWND。</span><span class="sxs-lookup"><span data-stu-id="aebb7-123">If the app moves the WebView visual tree to underneath a different window, then it needs to call put_ParentWindow to update the new parent HWND of the visual tree.</span></span>

<span data-ttu-id="aebb7-124">在创建的 CoreWebView2CompositionController 上使用 put_RootVisualTarget 来提供视觉对象以托管浏览器的可视化树。</span><span class="sxs-lookup"><span data-stu-id="aebb7-124">Use put_RootVisualTarget on the created CoreWebView2CompositionController to provide a visual to host the browser's visual tree.</span></span>

<span data-ttu-id="aebb7-125">建议为进程或应用程序窗口设置应用程序用户模型 ID。</span><span class="sxs-lookup"><span data-stu-id="aebb7-125">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="aebb7-126">如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。</span><span class="sxs-lookup"><span data-stu-id="aebb7-126">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span> 
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
 <span data-ttu-id="aebb7-127">建议应用程序处理重启管理器消息，以便当应用在特定安装中使用 web 视图的边缘且正在卸载该安装时，它可以正常重启。</span><span class="sxs-lookup"><span data-stu-id="aebb7-127">It is recommended that the application handles restart manager messages so that it can be restarted gracefully in the case when the app is using Edge for webview from a certain installation and that installation is being uninstalled.</span></span> <span data-ttu-id="aebb7-128">例如，如果用户从开发频道安装 Edge，并使用该通道中的边缘来测试应用，然后从该通道卸载 Edge 而不关闭应用，则应用将重新启动以允许卸载开发人员通道。</span><span class="sxs-lookup"><span data-stu-id="aebb7-128">For example, if a user installs Edge from Dev channel and opts to use Edge from that channel for testing the app, and then uninstalls Edge from that channel without closing the app, the app will be restarted to allow uninstallation of the dev channel to succeed.</span></span> 
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

#### <span data-ttu-id="aebb7-129">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="aebb7-129">CreateCoreWebView2PointerInfo</span></span> 

<span data-ttu-id="aebb7-130">创建一个空[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)。</span><span class="sxs-lookup"><span data-stu-id="aebb7-130">Create an empty [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>

> <span data-ttu-id="aebb7-131">公共 HRESULT [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo) ([ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* \* pointerInfo) </span><span class="sxs-lookup"><span data-stu-id="aebb7-131">public HRESULT [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)([ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \*\* pointerInfo)</span></span>

<span data-ttu-id="aebb7-132">在调用 SendPointerInput 之前，需要用所有相关信息填充返回的[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) 。</span><span class="sxs-lookup"><span data-stu-id="aebb7-132">The returned [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) needs to be populated with all of the relevant info before calling SendPointerInput.</span></span>

#### <span data-ttu-id="aebb7-133">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="aebb7-133">GetProviderForHwnd</span></span> 

<span data-ttu-id="aebb7-134">返回与给定 HWND 对应的 ICoreWebView2CompositionController 的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="aebb7-134">Returns the UI Automation Provider for the ICoreWebView2CompositionController that corresponds with the given HWND.</span></span>

> <span data-ttu-id="aebb7-135">公共 HRESULT [GetProviderForHwnd](#getproviderforhwnd) (HWND Hwnd，IUnknown \* \* 提供程序) </span><span class="sxs-lookup"><span data-stu-id="aebb7-135">public HRESULT [GetProviderForHwnd](#getproviderforhwnd)(HWND hwnd, IUnknown \*\* provider)</span></span>

