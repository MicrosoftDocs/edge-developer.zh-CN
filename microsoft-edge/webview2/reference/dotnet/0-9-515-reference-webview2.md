---
description: 将 Win32 应用中的 web 内容托管到 Microsoft Edge Web 部件2控件中
title: 0.9.515-WebView2 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 32092f4b434506229ffdd3612a68725b67f566a8
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879973"
---
# <span data-ttu-id="03f85-104">0-9-515 - 参考 (WebView2)</span><span class="sxs-lookup"><span data-stu-id="03f85-104">0-9-515 - Reference (WebView2)</span></span>  

> [!NOTE]
> <span data-ttu-id="03f85-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="03f85-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="03f85-106">请参阅[WEBVIEW2 api 参考](../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="03f85-106">Please refer to [WebView2 API reference](../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="03f85-107">使用 Microsoft Edge WebView2 控件，你可以使用[Microsoft edge \ （Chromium \）](https://www.microsoftedgeinsider.com)作为呈现引擎将 web 内容托管在你的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="03f85-107">The Microsoft Edge WebView2 control enables you to host web content in your application using [Microsoft Edge \(Chromium\)](https://www.microsoftedgeinsider.com) as the rendering engine.</span></span>  <span data-ttu-id="03f85-108">有关详细信息，请参阅[Microsoft Edge WebView2 概述](../../index.md)）和[WebView2 入门](../../gettingstarted/win32.md)。</span><span class="sxs-lookup"><span data-stu-id="03f85-108">For more information, see [Overview of Microsoft Edge WebView2](../../index.md)) and [Getting Started with WebView2](../../gettingstarted/win32.md).</span></span>  <span data-ttu-id="03f85-109">WebView2 是开始了解 API 的详细信息的绝佳位置[CoreWebView2。](0-9-515/microsoft-web-webview2-core-corewebview2.md)</span><span class="sxs-lookup"><span data-stu-id="03f85-109">[Microsoft.Web.WebView2.Core.CoreWebView2](0-9-515/microsoft-web-webview2-core-corewebview2.md) is a great place to start learning the details of the API.</span></span>  

## <span data-ttu-id="03f85-110">Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="03f85-110">Microsoft.Web.WebView2.Core</span></span>
*   <span data-ttu-id="03f85-111">[WebView2](0-9-515/namespace-microsoft-web-webview2-core.md)命名空间</span><span class="sxs-lookup"><span data-stu-id="03f85-111">[Microsoft.Web.WebView2.Core](0-9-515/namespace-microsoft-web-webview2-core.md) namespace</span></span>
*   [<span data-ttu-id="03f85-112">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="03f85-112">CoreWebView2</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2.md)
*   [<span data-ttu-id="03f85-113">CoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="03f85-113">CoreWebView2Controller</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2controller.md)
*   [<span data-ttu-id="03f85-114">CoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="03f85-114">CoreWebView2Deferral</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2deferral.md)
*   [<span data-ttu-id="03f85-115">CoreWebView2DevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="03f85-115">CoreWebView2DevToolsProtocolEventReceiver</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceiver.md)
*   [<span data-ttu-id="03f85-116">CoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="03f85-116">CoreWebView2Environment</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2environment.md)
*   [<span data-ttu-id="03f85-117">CoreWebView2EnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="03f85-117">CoreWebView2EnvironmentOptions</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2environmentoptions.md)
*   [<span data-ttu-id="03f85-118">CoreWebView2PhysicalKeyStatus</span><span class="sxs-lookup"><span data-stu-id="03f85-118">CoreWebView2PhysicalKeyStatus</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2physicalkeystatus.md)
*   [<span data-ttu-id="03f85-119">CoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="03f85-119">CoreWebView2Settings</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2settings.md)
*   [<span data-ttu-id="03f85-120">EdgeNotFoundException</span><span class="sxs-lookup"><span data-stu-id="03f85-120">EdgeNotFoundException</span></span>](0-9-515/microsoft-web-webview2-core-edgenotfoundexception.md)

### <span data-ttu-id="03f85-121">事件参数</span><span class="sxs-lookup"><span data-stu-id="03f85-121">Event arguments</span></span>

*   [<span data-ttu-id="03f85-122">CoreWebView2AcceleratorKeyPressedEventArgs</span><span class="sxs-lookup"><span data-stu-id="03f85-122">CoreWebView2AcceleratorKeyPressedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2acceleratorkeypressedeventargs.md)
*   [<span data-ttu-id="03f85-123">CoreWebView2ContentLoadingEventArgs</span><span class="sxs-lookup"><span data-stu-id="03f85-123">CoreWebView2ContentLoadingEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2contentloadingeventargs.md)
*   [<span data-ttu-id="03f85-124">CoreWebView2DevToolsProtocolEventReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="03f85-124">CoreWebView2DevToolsProtocolEventReceivedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)
*   [<span data-ttu-id="03f85-125">CoreWebView2MoveFocusRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="03f85-125">CoreWebView2MoveFocusRequestedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2movefocusrequestedeventargs.md)
*   [<span data-ttu-id="03f85-126">CoreWebView2NavigationCompletedEventArgs</span><span class="sxs-lookup"><span data-stu-id="03f85-126">CoreWebView2NavigationCompletedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md)
*   [<span data-ttu-id="03f85-127">CoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="03f85-127">CoreWebView2NavigationStartingEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md)
*   [<span data-ttu-id="03f85-128">CoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="03f85-128">CoreWebView2NewWindowRequestedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2newwindowrequestedeventargs.md)
*   [<span data-ttu-id="03f85-129">CoreWebView2PermissionRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="03f85-129">CoreWebView2PermissionRequestedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2permissionrequestedeventargs.md)
*   [<span data-ttu-id="03f85-130">CoreWebView2ProcessFailedEventArgs</span><span class="sxs-lookup"><span data-stu-id="03f85-130">CoreWebView2ProcessFailedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2processfailedeventargs.md)
*   [<span data-ttu-id="03f85-131">CoreWebView2ScriptDialogOpeningEventArgs</span><span class="sxs-lookup"><span data-stu-id="03f85-131">CoreWebView2ScriptDialogOpeningEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2scriptdialogopeningeventargs.md)
*   [<span data-ttu-id="03f85-132">CoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="03f85-132">CoreWebView2SourceChangedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2sourcechangedeventargs.md)
*   [<span data-ttu-id="03f85-133">CoreWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="03f85-133">CoreWebView2WebMessageReceivedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2webmessagereceivedeventargs.md)
*   [<span data-ttu-id="03f85-134">CoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="03f85-134">CoreWebView2WebResourceRequestedEventArgs</span></span>](0-9-515/microsoft-web-webview2-core-corewebview2webresourcerequestedeventargs.md)
