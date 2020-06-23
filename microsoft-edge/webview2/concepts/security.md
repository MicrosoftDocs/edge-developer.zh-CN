---
description: 了解如何开发安全的 WebView2 应用程序
title: 开发安全 WebView2 应用程序的最佳做法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、安全性
ms.openlocfilehash: e71dbe9ad98b7156d8888da074e30a96683469d5
ms.sourcegitcommit: e49b86082da884299fdd485d3311d63a7688c0d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/22/2020
ms.locfileid: "10755391"
---
# <span data-ttu-id="fd296-104">开发安全 WebView2 应用程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="fd296-104">Best practices for developing secure WebView2 applications</span></span>

<span data-ttu-id="fd296-105">[WebView2 控件](https://docs.microsoft.com/microsoft-edge/webview2/)允许开发人员在其本机应用程序中托管 web 内容。</span><span class="sxs-lookup"><span data-stu-id="fd296-105">The [WebView2 control](https://docs.microsoft.com/microsoft-edge/webview2/) allows developers to host web content in their native applications.</span></span> <span data-ttu-id="fd296-106">如果使用不当，托管 web 内容提供了多种优点，例如使用基于 web 的 UI、访问 web 平台的功能、共享代码跨平台等。</span><span class="sxs-lookup"><span data-stu-id="fd296-106">When used correctly, hosting web content offers several advantages, such as using web-based UI, accessing features of the web platform, sharing code cross-platform, and so on.</span></span> <span data-ttu-id="fd296-107">若要避免托管 web 内容可能引发的漏洞，请确保设计 WebView2 应用程序以密切监视 web 内容和主机应用程序之间的交互。</span><span class="sxs-lookup"><span data-stu-id="fd296-107">To avoid vulnerabilities that can arise from hosting web content, make sure to design your WebView2 application to closely monitor interactions between the web content and the host application.</span></span> 

1. <span data-ttu-id="fd296-108">将所有 web 内容视为不安全</span><span class="sxs-lookup"><span data-stu-id="fd296-108">Treat all web content as insecure</span></span>
    - <span data-ttu-id="fd296-109">在使用 web 消息和宿主对象参数之前对其进行验证，因为 web 消息和参数可能不正确（无意或恶意），并导致应用意外运行。</span><span class="sxs-lookup"><span data-stu-id="fd296-109">Validate web messages and host object parameters before consuming them, because web messages and parameters can be malformed (unintentionally or maliciously) and cause the app to behave unexpectedly.</span></span>
    - <span data-ttu-id="fd296-110">始终检查 WebView2 内运行的文档的来源并评估内容的可信度。</span><span class="sxs-lookup"><span data-stu-id="fd296-110">Always check the origin of the document running inside WebView2 and assess the trustworthiness of the content.</span></span> 

2. <span data-ttu-id="fd296-111">设计特定的 web 消息和宿主对象交互，而不是使用泛型代理。</span><span class="sxs-lookup"><span data-stu-id="fd296-111">Design specific web messages and host object interactions instead of using generic proxies.</span></span>

3. <span data-ttu-id="fd296-112">通过修改[ICoreWebView2Settings](../reference/win32/0-9-538/icorewebview2settings) （Win32）或[CoreWebView2Settings](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2settings) （.net）来限制 web 内容功能，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fd296-112">Restrict web content functionality by modifying [ICoreWebView2Settings](../reference/win32/0-9-538/icorewebview2settings) (Win32) or [CoreWebView2Settings](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2settings) (.NET) as follows:</span></span>
    - <span data-ttu-id="fd296-113">`AreHostObjectsAllowed` `false` 如果不希望 web 内容访问主机对象，则设置为。</span><span class="sxs-lookup"><span data-stu-id="fd296-113">Set `AreHostObjectsAllowed` to `false`, if you don’t expect the web content to access host objects.</span></span>
    - <span data-ttu-id="fd296-114">`IsWebMessageEnabled` `false` 如果不希望 web 内容发布 web 消息到本机应用程序，请设置为。</span><span class="sxs-lookup"><span data-stu-id="fd296-114">Set `IsWebMessageEnabled` to `false`, if you don’t expect the web content to post web messages to your native application.</span></span> 
    - <span data-ttu-id="fd296-115">`IsScriptEnabled` `false` 如果不希望 web 内容运行脚本（例如，显示静态 html 内容时），则设置为。</span><span class="sxs-lookup"><span data-stu-id="fd296-115">Set `IsScriptEnabled` to `false`, if you don’t expect the web content to run scripts (for example, when showing static html content).</span></span>
    - <span data-ttu-id="fd296-116">`AreDefaultScriptDialogsEnabled` `false` 如果不希望显示 web 内容或对话框，则设置为 `alert` `prompt` 。</span><span class="sxs-lookup"><span data-stu-id="fd296-116">Set `AreDefaultScriptDialogsEnabled` to `false`, if you don’t expect the web content to show `alert` or `prompt` dialog boxes.</span></span>

4.  <span data-ttu-id="fd296-117">使用 `NavigationStarting` 和 `FrameNavigationStarting` 事件根据新页面的来源更新设置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fd296-117">Use the `NavigationStarting` and `FrameNavigationStarting` events to update settings based on the origin of the new page as follows:</span></span>
    1.  <span data-ttu-id="fd296-118">若要防止你的应用程序导航到特定页面，请使用这些事件进行检查，然后阻止页面或框架导航。</span><span class="sxs-lookup"><span data-stu-id="fd296-118">To prevent your application from navigating to certain pages, use these events to check and then block page or frame navigation.</span></span> 
    2.  <span data-ttu-id="fd296-119">导航到新页面时，你可能需要按照上述说明调整[ICoreWebView2Settings](../reference/win32/0-9-538/icorewebview2settings) （Win32）或[CoreWebView2Settings](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2settings) （.net） ' 上的属性值。</span><span class="sxs-lookup"><span data-stu-id="fd296-119">When navigating to a new page, you may need to adjust the property values on [ICoreWebView2Settings](../reference/win32/0-9-538/icorewebview2settings) (Win32) or [CoreWebView2Settings](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2settings) (.NET)\` as described above.</span></span>

5. <span data-ttu-id="fd296-120">导航到新文档时，请使用 `ContentLoading` 事件删除使用的已公开主机对象 `RemoveHostObjectFromScript` 。</span><span class="sxs-lookup"><span data-stu-id="fd296-120">When navigating to a new document, use the `ContentLoading` event to remove exposed host objects using `RemoveHostObjectFromScript`.</span></span> 