---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2Environment3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 327a182c5298ed6de6b9e55b407d138857dbe659
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886092"
---
# <span data-ttu-id="054c5-104">0.8.355-接口 IWebView2Environment3</span><span class="sxs-lookup"><span data-stu-id="054c5-104">0.8.355 - interface IWebView2Environment3</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2Environment3
  : public IWebView2Environment2
```

<span data-ttu-id="054c5-105">由环境对象实现的其他功能。</span><span class="sxs-lookup"><span data-stu-id="054c5-105">Additional functionality implemented by the Environment object.</span></span>

## <span data-ttu-id="054c5-106">摘要</span><span class="sxs-lookup"><span data-stu-id="054c5-106">Summary</span></span>

 <span data-ttu-id="054c5-107">成员</span><span class="sxs-lookup"><span data-stu-id="054c5-107">Members</span></span>                        | <span data-ttu-id="054c5-108">描述</span><span class="sxs-lookup"><span data-stu-id="054c5-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="054c5-109">add_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="054c5-109">add_NewVersionAvailable</span></span>](#add_newversionavailable) | <span data-ttu-id="054c5-110">当已安装更高版本的 Edge 浏览器并可通过 WebView2 使用时，将引发 NewVersionAvailable 事件。</span><span class="sxs-lookup"><span data-stu-id="054c5-110">The NewVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>
[<span data-ttu-id="054c5-111">remove_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="054c5-111">remove_NewVersionAvailable</span></span>](#remove_newversionavailable) | <span data-ttu-id="054c5-112">删除以前使用 add_NewVersionAvailable 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="054c5-112">Remove an event handler previously added with add_NewVersionAvailable.</span></span>

<span data-ttu-id="054c5-113">有关详细信息，请参阅[IWebView2Environment](IWebView2Environment.md)界面。</span><span class="sxs-lookup"><span data-stu-id="054c5-113">See the [IWebView2Environment](IWebView2Environment.md) interface for more details.</span></span> <span data-ttu-id="054c5-114">你可以从实现[IWebView2Environment](IWebView2Environment.md)的对象中为此接口执行 QueryInterface。</span><span class="sxs-lookup"><span data-stu-id="054c5-114">You can QueryInterface for this interface from the object that implements [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="054c5-115">成员</span><span class="sxs-lookup"><span data-stu-id="054c5-115">Members</span></span>

#### <span data-ttu-id="054c5-116">add_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="054c5-116">add_NewVersionAvailable</span></span> 

<span data-ttu-id="054c5-117">当已安装更高版本的 Edge 浏览器并可通过 WebView2 使用时，将引发 NewVersionAvailable 事件。</span><span class="sxs-lookup"><span data-stu-id="054c5-117">The NewVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>

> <span data-ttu-id="054c5-118">public HRESULT [add_NewVersionAvailable](#add_newversionavailable)（[IWebView2NewVersionAvailableEventHandler](IWebView2NewVersionAvailableEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="054c5-118">public HRESULT [add_NewVersionAvailable](#add_newversionavailable)([IWebView2NewVersionAvailableEventHandler](IWebView2NewVersionAvailableEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="054c5-119">若要使用较新版本的浏览器，您必须创建一个新的[IWebView2Environment](IWebView2Environment.md)和[IWebView2WebView](IWebView2WebView.md)。</span><span class="sxs-lookup"><span data-stu-id="054c5-119">To use the newer version of the browser you must create a new [IWebView2Environment](IWebView2Environment.md) and [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="054c5-120">将仅从运行代码的同一边缘通道为新版本激发事件。</span><span class="sxs-lookup"><span data-stu-id="054c5-120">Event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="054c5-121">当不运行安装的边缘时，将不会触发任何事件。</span><span class="sxs-lookup"><span data-stu-id="054c5-121">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="054c5-122">由于用户数据文件夹一次只能由一个浏览器进程使用，如果要在 WebViews 中使用新版本的浏览器使用同一用户数据文件夹，则必须先关闭使用早期版本的浏览器的[IWebView2Environment](IWebView2Environment.md)和 IWebView2WebViews。</span><span class="sxs-lookup"><span data-stu-id="054c5-122">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the [IWebView2Environment](IWebView2Environment.md) and IWebView2WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="054c5-123">或者只提示用户重新启动应用。</span><span class="sxs-lookup"><span data-stu-id="054c5-123">Or simply prompt the user to restart the app.</span></span>

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

#### <span data-ttu-id="054c5-124">remove_NewVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="054c5-124">remove_NewVersionAvailable</span></span> 

<span data-ttu-id="054c5-125">删除以前使用 add_NewVersionAvailable 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="054c5-125">Remove an event handler previously added with add_NewVersionAvailable.</span></span>

> <span data-ttu-id="054c5-126">public HRESULT [remove_NewVersionAvailable](#remove_newversionavailable)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="054c5-126">public HRESULT [remove_NewVersionAvailable](#remove_newversionavailable)(EventRegistrationToken token)</span></span>

