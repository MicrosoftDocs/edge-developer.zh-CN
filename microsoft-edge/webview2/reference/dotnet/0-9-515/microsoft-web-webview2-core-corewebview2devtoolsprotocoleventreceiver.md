---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2DevToolsProtocolEventReceiver
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 1982c6926d2ed8805433efc4d46ff6f3cac691ce
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885056"
---
# <span data-ttu-id="40efb-104">0.9.515-WebView2 的 CoreWebView2DevToolsProtocolEventReceiver 类</span><span class="sxs-lookup"><span data-stu-id="40efb-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2DevToolsProtocolEventReceiver class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="40efb-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="40efb-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="40efb-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="40efb-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="40efb-107">将为特定的 DevTools 协议事件创建一个接收器，并允许你订阅和取消订阅该事件。</span><span class="sxs-lookup"><span data-stu-id="40efb-107">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubscribe from that event.</span></span>

## <span data-ttu-id="40efb-108">摘要</span><span class="sxs-lookup"><span data-stu-id="40efb-108">Summary</span></span>

 <span data-ttu-id="40efb-109">成员</span><span class="sxs-lookup"><span data-stu-id="40efb-109">Members</span></span>                        | <span data-ttu-id="40efb-110">描述</span><span class="sxs-lookup"><span data-stu-id="40efb-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="40efb-111">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="40efb-111">DevToolsProtocolEventReceived</span></span>](#devtoolsprotocoleventreceived) | <span data-ttu-id="40efb-112">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="40efb-112">Subscribe to a DevToolsProtocol event.</span></span>

<span data-ttu-id="40efb-113">通过 GetDevToolsProtocolEventReceiver 从 Web 视图对象中获取。</span><span class="sxs-lookup"><span data-stu-id="40efb-113">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="40efb-114">成员</span><span class="sxs-lookup"><span data-stu-id="40efb-114">Members</span></span>

#### <span data-ttu-id="40efb-115">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="40efb-115">DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="40efb-116">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="40efb-116">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="40efb-117">公共事件 EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)  >  [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span><span class="sxs-lookup"><span data-stu-id="40efb-117">public event EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md) > [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span></span>

<span data-ttu-id="40efb-118">每当引发相应的 DevToolsProtocol 事件时，都将调用处理程序的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="40efb-118">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="40efb-119">将使用包含 DevTools 协议事件参数对象的事件参数对象作为 JSON 字符串调用调用。</span><span class="sxs-lookup"><span data-stu-id="40efb-119">Invoke will be called with the an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>

