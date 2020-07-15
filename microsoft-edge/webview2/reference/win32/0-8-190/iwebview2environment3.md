---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2Environment3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: d16a12aae823c48b7dd4b0b5e8225cdd40c1dafc
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878524"
---
# <span data-ttu-id="4a790-104">0.8.355-接口 IWebView2Environment3</span><span class="sxs-lookup"><span data-stu-id="4a790-104">0.8.355 - interface IWebView2Environment3</span></span> 

> [!NOTE]
> <span data-ttu-id="4a790-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="4a790-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="4a790-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="4a790-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2Environment3
  : public IWebView2Environment2
```

<span data-ttu-id="4a790-107">由环境对象实现的其他功能。</span><span class="sxs-lookup"><span data-stu-id="4a790-107">Additional functionality implemented by the Environment object.</span></span>

## <span data-ttu-id="4a790-108">摘要</span><span class="sxs-lookup"><span data-stu-id="4a790-108">Summary</span></span>

 <span data-ttu-id="4a790-109">成员</span><span class="sxs-lookup"><span data-stu-id="4a790-109">Members</span></span>                        | <span data-ttu-id="4a790-110">描述</span><span class="sxs-lookup"><span data-stu-id="4a790-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4a790-111">add_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="4a790-111">add_NewVersionAvailable</span></span>](#add_newversionavailable) | <span data-ttu-id="4a790-112">当已安装更高版本的 Edge 浏览器并可通过 WebView2 使用时，将引发 NewVersionAvailable 事件。</span><span class="sxs-lookup"><span data-stu-id="4a790-112">The NewVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>
[<span data-ttu-id="4a790-113">remove_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="4a790-113">remove_NewVersionAvailable</span></span>](#remove_newversionavailable) | <span data-ttu-id="4a790-114">删除以前使用 add_NewVersionAvailable 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4a790-114">Remove an event handler previously added with add_NewVersionAvailable.</span></span>

<span data-ttu-id="4a790-115">有关详细信息，请参阅[IWebView2Environment](IWebView2Environment.md)界面。</span><span class="sxs-lookup"><span data-stu-id="4a790-115">See the [IWebView2Environment](IWebView2Environment.md) interface for more details.</span></span> <span data-ttu-id="4a790-116">你可以从实现[IWebView2Environment](IWebView2Environment.md)的对象中为此接口执行 QueryInterface。</span><span class="sxs-lookup"><span data-stu-id="4a790-116">You can QueryInterface for this interface from the object that implements [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="4a790-117">成员</span><span class="sxs-lookup"><span data-stu-id="4a790-117">Members</span></span>

#### <span data-ttu-id="4a790-118">add_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="4a790-118">add_NewVersionAvailable</span></span> 

<span data-ttu-id="4a790-119">当已安装更高版本的 Edge 浏览器并可通过 WebView2 使用时，将引发 NewVersionAvailable 事件。</span><span class="sxs-lookup"><span data-stu-id="4a790-119">The NewVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>

> <span data-ttu-id="4a790-120">public HRESULT [add_NewVersionAvailable](#add_newversionavailable)（[IWebView2NewVersionAvailableEventHandler](IWebView2NewVersionAvailableEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="4a790-120">public HRESULT [add_NewVersionAvailable](#add_newversionavailable)([IWebView2NewVersionAvailableEventHandler](IWebView2NewVersionAvailableEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="4a790-121">若要使用较新版本的浏览器，您必须创建一个新的[IWebView2Environment](IWebView2Environment.md)和[IWebView2WebView](IWebView2WebView.md)。</span><span class="sxs-lookup"><span data-stu-id="4a790-121">To use the newer version of the browser you must create a new [IWebView2Environment](IWebView2Environment.md) and [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="4a790-122">将仅从运行代码的同一边缘通道为新版本激发事件。</span><span class="sxs-lookup"><span data-stu-id="4a790-122">Event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="4a790-123">当不运行安装的边缘时，将不会触发任何事件。</span><span class="sxs-lookup"><span data-stu-id="4a790-123">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="4a790-124">由于用户数据文件夹一次只能由一个浏览器进程使用，如果要在 WebViews 中使用新版本的浏览器使用同一用户数据文件夹，则必须先关闭使用早期版本的浏览器的[IWebView2Environment](IWebView2Environment.md)和 IWebView2WebViews。</span><span class="sxs-lookup"><span data-stu-id="4a790-124">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the [IWebView2Environment](IWebView2Environment.md) and IWebView2WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="4a790-125">或者只提示用户重新启动应用。</span><span class="sxs-lookup"><span data-stu-id="4a790-125">Or simply prompt the user to restart the app.</span></span>

```cpp
    // After the environment is successfully created,
    // register a handler for the NewVersionAvailable event.
    // This handler tells when there is a new Edge version available on the machine.
    CHECK_FAILURE(m_webViewEnvironment->add_NewVersionAvailable(
        Callback<IWebView2NewVersionAvailableEventHandler>(
            [this](IWebView2Environment* sender, IWebView2NewVersionAvailableEventArgs* args)
                -> HRESULT {
                // Get the version value from args
                wil::unique_cotaskmem_string newVersion;
                CHECK_FAILURE(args->get_NewVersion(&newVersion));
                std::wstring message = L"We detected there is a new version for the browser.";
                message += L"\n\nVersion number: ";
                message += newVersion.get();
                message += L"\n\n";
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

#### <span data-ttu-id="4a790-126">remove_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="4a790-126">remove_NewVersionAvailable</span></span> 

<span data-ttu-id="4a790-127">删除以前使用 add_NewVersionAvailable 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="4a790-127">Remove an event handler previously added with add_NewVersionAvailable.</span></span>

> <span data-ttu-id="4a790-128">public HRESULT [remove_NewVersionAvailable](#remove_newversionavailable)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="4a790-128">public HRESULT [remove_NewVersionAvailable](#remove_newversionavailable)(EventRegistrationToken token)</span></span>

