---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2DevToolsProtocolEventReceiver 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 42ea3beb51dc315ed7ab3b7b0c04c7414adab2db
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011634"
---
# <span data-ttu-id="2d773-104">CoreWebView2DevToolsProtocolEventReceiver 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="2d773-104">Microsoft.Web.WebView2.Core.CoreWebView2DevToolsProtocolEventReceiver class</span></span> 

<span data-ttu-id="2d773-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="2d773-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="2d773-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="2d773-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="2d773-107">将为特定的 DevTools 协议事件创建一个接收器，并允许你订阅和取消订阅该事件。</span><span class="sxs-lookup"><span data-stu-id="2d773-107">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubscribe from that event.</span></span>

## <span data-ttu-id="2d773-108">摘要</span><span class="sxs-lookup"><span data-stu-id="2d773-108">Summary</span></span>

 <span data-ttu-id="2d773-109">成员</span><span class="sxs-lookup"><span data-stu-id="2d773-109">Members</span></span>                        | <span data-ttu-id="2d773-110">描述</span><span class="sxs-lookup"><span data-stu-id="2d773-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2d773-111">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="2d773-111">DevToolsProtocolEventReceived</span></span>](#devtoolsprotocoleventreceived) | <span data-ttu-id="2d773-112">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="2d773-112">Subscribe to a DevToolsProtocol event.</span></span>

<span data-ttu-id="2d773-113">通过 GetDevToolsProtocolEventReceiver 从 Web 视图对象中获取。</span><span class="sxs-lookup"><span data-stu-id="2d773-113">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="2d773-114">成员</span><span class="sxs-lookup"><span data-stu-id="2d773-114">Members</span></span>

#### <span data-ttu-id="2d773-115">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="2d773-115">DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="2d773-116">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="2d773-116">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="2d773-117">公共事件 EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)  >  [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span><span class="sxs-lookup"><span data-stu-id="2d773-117">public event EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md) > [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span></span>

<span data-ttu-id="2d773-118">每当引发相应的 DevToolsProtocol 事件时，都将调用处理程序的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="2d773-118">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="2d773-119">将调用一个事件参数对象，该对象包含将 DevTools 协议事件的参数对象作为 JSON 字符串。</span><span class="sxs-lookup"><span data-stu-id="2d773-119">Invoke will be called with an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>
