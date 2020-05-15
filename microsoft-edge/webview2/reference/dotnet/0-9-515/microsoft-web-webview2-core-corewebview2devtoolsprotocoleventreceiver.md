---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 23ee363fd90416d07c76644879a5f4b6cc2acabe
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653119"
---
# <span data-ttu-id="d643d-104">CoreWebView2DevToolsProtocolEventReceiver 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="d643d-104">Microsoft.Web.WebView2.Core.CoreWebView2DevToolsProtocolEventReceiver class</span></span> 

<span data-ttu-id="d643d-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="d643d-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="d643d-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="d643d-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="d643d-107">将为特定的 DevTools 协议事件创建一个接收器，并允许你订阅和取消订阅该事件。</span><span class="sxs-lookup"><span data-stu-id="d643d-107">A Receiver is created for a particular DevTools Protocol event and allows you to subscribe and unsubscribe from that event.</span></span>

## <span data-ttu-id="d643d-108">摘要</span><span class="sxs-lookup"><span data-stu-id="d643d-108">Summary</span></span>

 <span data-ttu-id="d643d-109">成员</span><span class="sxs-lookup"><span data-stu-id="d643d-109">Members</span></span>                        | <span data-ttu-id="d643d-110">描述</span><span class="sxs-lookup"><span data-stu-id="d643d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d643d-111">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="d643d-111">DevToolsProtocolEventReceived</span></span>](#devtoolsprotocoleventreceived) | <span data-ttu-id="d643d-112">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="d643d-112">Subscribe to a DevToolsProtocol event.</span></span>

<span data-ttu-id="d643d-113">通过 GetDevToolsProtocolEventReceiver 从 Web 视图对象中获取。</span><span class="sxs-lookup"><span data-stu-id="d643d-113">Obtained from the WebView object via GetDevToolsProtocolEventReceiver.</span></span>

## <span data-ttu-id="d643d-114">成员</span><span class="sxs-lookup"><span data-stu-id="d643d-114">Members</span></span>

#### <span data-ttu-id="d643d-115">DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="d643d-115">DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="d643d-116">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="d643d-116">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="d643d-117">公共事件 EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)  >  [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span><span class="sxs-lookup"><span data-stu-id="d643d-117">public event EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md) > [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)</span></span>

<span data-ttu-id="d643d-118">每当引发相应的 DevToolsProtocol 事件时，都将调用处理程序的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="d643d-118">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="d643d-119">将使用包含 DevTools 协议事件参数对象的事件参数对象作为 JSON 字符串调用调用。</span><span class="sxs-lookup"><span data-stu-id="d643d-119">Invoke will be called with the an event args object containing the DevTools Protocol event's parameter object as a JSON string.</span></span>
