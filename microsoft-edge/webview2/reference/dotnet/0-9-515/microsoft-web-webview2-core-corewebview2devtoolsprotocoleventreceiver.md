---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2DevToolsProtocolEventReceiver
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 5e6e2d955dd0d52a093eea116a01961e1ee58c76
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877768"
---
# <span data-ttu-id="bbf87-104">0.9.515-WebView2 的 CoreWebView2DevToolsProtocolEventReceiver 类</span><span class="sxs-lookup"><span data-stu-id="bbf87-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2DevToolsProtocolEventReceiver class</span></span> 

> [!NOTE]
> <span data-ttu-id="bbf87-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="bbf87-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="bbf87-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="bbf87-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="bbf87-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="bbf87-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="bbf87-108">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="bbf87-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="bbf87-109">将为特定的 DevTools 协议事件创建一个接收器，并允许你订阅和取消订阅该事件。</span><span class="sxs-lookup"><span data-stu-id="bbf87-109">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubscribe from that event.</span></span>

## <span data-ttu-id="bbf87-110">摘要</span><span class="sxs-lookup"><span data-stu-id="bbf87-110">Summary</span></span>

 <span data-ttu-id="bbf87-111">成员</span><span class="sxs-lookup"><span data-stu-id="bbf87-111">Members</span></span>                        | <span data-ttu-id="bbf87-112">描述</span><span class="sxs-lookup"><span data-stu-id="bbf87-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bbf87-113">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="bbf87-113">DevToolsProtocolEventReceived</span></span>](#devtoolsprotocoleventreceived) | <span data-ttu-id="bbf87-114">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="bbf87-114">Subscribe to a DevToolsProtocol event.</span></span>

<span data-ttu-id="bbf87-115">通过 GetDevToolsProtocolEventReceiver 从 Web 视图对象中获取。</span><span class="sxs-lookup"><span data-stu-id="bbf87-115">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="bbf87-116">成员</span><span class="sxs-lookup"><span data-stu-id="bbf87-116">Members</span></span>

#### <span data-ttu-id="bbf87-117">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="bbf87-117">DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="bbf87-118">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="bbf87-118">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="bbf87-119">公共事件 EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)  >  [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span><span class="sxs-lookup"><span data-stu-id="bbf87-119">public event EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md) > [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span></span>

<span data-ttu-id="bbf87-120">每当引发相应的 DevToolsProtocol 事件时，都将调用处理程序的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="bbf87-120">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="bbf87-121">将使用包含 DevTools 协议事件参数对象的事件参数对象作为 JSON 字符串调用调用。</span><span class="sxs-lookup"><span data-stu-id="bbf87-121">Invoke will be called with the an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>

