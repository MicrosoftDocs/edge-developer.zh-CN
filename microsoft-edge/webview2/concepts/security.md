---
description: 了解如何开发安全的 WebView2 应用程序
title: 开发安全 WebView2 应用程序的最佳做法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、安全性
ms.openlocfilehash: d53417cc1ac98b44565692edbaec06216f7c110b
ms.sourcegitcommit: 61cc15d2fc89aee3e09cec48ef1e0e5bbf8d289a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2020
ms.locfileid: "11119000"
---
# <span data-ttu-id="978f9-104">开发安全 WebView2 应用程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="978f9-104">Best practices for developing secure WebView2 applications</span></span>  

<span data-ttu-id="978f9-105">[WebView2 控件][Webview2Main]允许开发人员在本机应用程序中托管 web 内容。</span><span class="sxs-lookup"><span data-stu-id="978f9-105">The [WebView2 control][Webview2Main] allows developers to host web content in the native applications.</span></span> <span data-ttu-id="978f9-106">如果使用不当，托管 web 内容提供了多种优点，例如使用基于 web 的 UI、访问 web 平台的功能、共享代码跨平台等。</span><span class="sxs-lookup"><span data-stu-id="978f9-106">When used correctly, hosting web content offers several advantages, such as using web-based UI, accessing features of the web platform, sharing code cross-platform, and so on.</span></span>  <span data-ttu-id="978f9-107">若要避免托管 web 内容可能引发的漏洞，请确保设计 WebView2 应用程序以密切监视 web 内容和主机应用程序之间的交互。</span><span class="sxs-lookup"><span data-stu-id="978f9-107">To avoid vulnerabilities that can arise from hosting web content, make sure to design your WebView2 application to closely monitor interactions between the web content and the host application.</span></span>  

1.  <span data-ttu-id="978f9-108">将所有 web 内容视为不安全。</span><span class="sxs-lookup"><span data-stu-id="978f9-108">Treat all web content as insecure.</span></span>  
    *   <span data-ttu-id="978f9-109">在使用之前验证 web 消息和主机对象参数，因为 web 消息和参数可能格式不正确 \ (无意或恶意的 ) 并导致应用意外运行。</span><span class="sxs-lookup"><span data-stu-id="978f9-109">Validate web messages and host object parameters before consuming each, because web messages and parameters can be malformed \(unintentionally or maliciously\) and cause the app to behave unexpectedly.</span></span>
    *   <span data-ttu-id="978f9-110">始终检查 WebView2 内运行的文档的来源并评估内容的可信度。</span><span class="sxs-lookup"><span data-stu-id="978f9-110">Always check the origin of the document running inside WebView2 and assess the trustworthiness of the content.</span></span>  
1.  <span data-ttu-id="978f9-111">设计特定的 web 消息和宿主对象交互，而不是使用泛型代理。</span><span class="sxs-lookup"><span data-stu-id="978f9-111">Design specific web messages and host object interactions instead of using generic proxies.</span></span>  
1.  <span data-ttu-id="978f9-112">通过修改 [ICoreWebView2Settings (Win32) ][Webview2ReferenceWin32Icorewebview2settings] 或 [CoreWebView2Settings ( .net) ][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings]，设置以下选项以限制 web 内容功能。</span><span class="sxs-lookup"><span data-stu-id="978f9-112">Set the following options to restrict web content functionality by modifying [ICoreWebView2Settings (Win32)][Webview2ReferenceWin32Icorewebview2settings] or [CoreWebView2Settings (.NET)][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings].</span></span>  
    *   <span data-ttu-id="978f9-113">`AreHostObjectsAllowed` `false` 如果不希望 web 内容访问主机对象，则设置为。</span><span class="sxs-lookup"><span data-stu-id="978f9-113">Set `AreHostObjectsAllowed` to `false`, if you do not expect the web content to access host objects.</span></span>  
    *   <span data-ttu-id="978f9-114">`IsWebMessageEnabled` `false` 如果不希望 web 内容将 web 消息发布到本机应用程序，则设置为。</span><span class="sxs-lookup"><span data-stu-id="978f9-114">Set `IsWebMessageEnabled` to `false`, if you do not expect the web content to post web messages to your native application.</span></span>  
    *   <span data-ttu-id="978f9-115">设置 `IsScriptEnabled` 为 `false` ，如果不希望 web 内容运行脚本，例如，当显示静态 html 内容 \ ) 时 (。</span><span class="sxs-lookup"><span data-stu-id="978f9-115">Set `IsScriptEnabled` to `false`, if you do not expect the web content to run scripts \(for example, when showing static html content\).</span></span>  
    *   <span data-ttu-id="978f9-116">`AreDefaultScriptDialogsEnabled` `false` 如果不希望显示 web 内容或对话框，则设置为 `alert` `prompt` 。</span><span class="sxs-lookup"><span data-stu-id="978f9-116">Set `AreDefaultScriptDialogsEnabled` to `false`, if you do not expect the web content to show `alert` or `prompt` dialog boxes.</span></span>  
1.  <span data-ttu-id="978f9-117">在以下步骤中，使用 `NavigationStarting` 和 `FrameNavigationStarting` 事件根据新页面的来源更新设置。</span><span class="sxs-lookup"><span data-stu-id="978f9-117">In the following steps, use the `NavigationStarting` and `FrameNavigationStarting` events to update settings based on the origin of the new page.</span></span>  
    1.  <span data-ttu-id="978f9-118">若要防止你的应用程序导航到特定页面，请使用事件进行检查，然后阻止页面或框架导航。</span><span class="sxs-lookup"><span data-stu-id="978f9-118">To prevent your application from navigating to certain pages, use the events to check and then block page or frame navigation.</span></span>  
    1.  <span data-ttu-id="978f9-119">导航到新页面时，你可能需要在 [ICoreWebView2Settings (Win32) ][Webview2ReferenceWin32Icorewebview2settings] 或 [CoreWebView2Settings ( .net) ][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings] （如上文所述）调整属性值。</span><span class="sxs-lookup"><span data-stu-id="978f9-119">When navigating to a new page, you may need to adjust the property values on [ICoreWebView2Settings (Win32)][Webview2ReferenceWin32Icorewebview2settings] or [CoreWebView2Settings (.NET)][Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings] as previously described.</span></span>  
1.  <span data-ttu-id="978f9-120">导航到新文档时，请使用 `ContentLoading` 事件删除使用的已公开主机对象 `RemoveHostObjectFromScript` 。</span><span class="sxs-lookup"><span data-stu-id="978f9-120">When navigating to a new document, use the `ContentLoading` event to remove exposed host objects using `RemoveHostObjectFromScript`.</span></span>  

<!--## Security

Always check the Source property of the WebView before using `ExecuteScript`, `PostWebMessageAsJson`, `PostWebMessageAsString`, or any other method to send information into the WebView. The WebView may have navigated to another page via the end user interacting with the page or script in the page causing navigation. Similarly, be very careful with `AddScriptToExecuteOnDocumentCreated`. All future `navigations` run the same script and if it provides access to information intended only for a certain origin, any HTML document may have access.

When examining the result of an `ExecuteScript` method call, a `WebMessageReceived` event, always check the Source of the sender, or any other mechanism of receiving information from an HTML document in a WebView validate the URI of the HTML document is what you expect.

When constructing a message to send into a WebView, prefer using `PostWebMessageAsJson` and construct the JSON string parameter using a JSON library. This avoids any potential accidents of encoding information into a JSON string or script and ensure no attacker controlled input can modify the rest of the JSON message or run arbitrary script. -->  

<!-- links -->  

[Webview2Main]: ../index.md "Microsoft Edge WebView2 简介 (预览版) |Microsoft 文档"  

[Webview2ReferenceWin32Icorewebview2settings]: /microsoft-edge/webview2/reference/win32/icorewebview2settings "interface ICoreWebView2Settings |Microsoft 文档"  

[Webview2ReferenceDotnetMicrosoftWebWebview2CoreCorewebview2settings]: /dotnet/api/microsoft.web.webview2.core.corewebview2settings "CoreWebView2Settings Class (WebView2) |Microsoft 文档"  
