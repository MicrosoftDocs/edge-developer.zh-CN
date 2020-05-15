---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: b786bae624b5f0649ec443e93f741975d672d0e0
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652962"
---
# <span data-ttu-id="d60d0-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d60d0-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="d60d0-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="d60d0-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="d60d0-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="d60d0-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="d60d0-107">调用方实现此接口以接收 Web 视图中的 DevToolsProtocolEventReceived 事件。</span><span class="sxs-lookup"><span data-stu-id="d60d0-107">The caller implements this interface to receive DevToolsProtocolEventReceived events from the WebView.</span></span>

## <span data-ttu-id="d60d0-108">摘要</span><span class="sxs-lookup"><span data-stu-id="d60d0-108">Summary</span></span>

 <span data-ttu-id="d60d0-109">成员</span><span class="sxs-lookup"><span data-stu-id="d60d0-109">Members</span></span>                        | <span data-ttu-id="d60d0-110">描述</span><span class="sxs-lookup"><span data-stu-id="d60d0-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d60d0-111">调用</span><span class="sxs-lookup"><span data-stu-id="d60d0-111">Invoke</span></span>](#invoke) | <span data-ttu-id="d60d0-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d60d0-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="d60d0-113">成员</span><span class="sxs-lookup"><span data-stu-id="d60d0-113">Members</span></span>

#### <span data-ttu-id="d60d0-114">调用</span><span class="sxs-lookup"><span data-stu-id="d60d0-114">Invoke</span></span> 

<span data-ttu-id="d60d0-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d60d0-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="d60d0-116">公共 HRESULT[调用](#invoke)（[ICoreWebView2](ICoreWebView2.md) \* sender、[ICoreWebView2DevToolsProtocolEventReceivedEventArgs](ICoreWebView2DevToolsProtocolEventReceivedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="d60d0-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2DevToolsProtocolEventReceivedEventArgs](ICoreWebView2DevToolsProtocolEventReceivedEventArgs.md) \* args)</span></span>

