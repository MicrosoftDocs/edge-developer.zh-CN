---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2NewWindowRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 2fe743f0ffe39107252a184e2e98cc2904e3c640
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884965"
---
# <span data-ttu-id="46b41-104">0.8.355-接口 IWebView2NewWindowRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="46b41-104">0.8.355 - interface IWebView2NewWindowRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NewWindowRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="46b41-105">调用方实现此接口以接收 Webview.newwindowrequested 事件。</span><span class="sxs-lookup"><span data-stu-id="46b41-105">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="46b41-106">摘要</span><span class="sxs-lookup"><span data-stu-id="46b41-106">Summary</span></span>

 <span data-ttu-id="46b41-107">成员</span><span class="sxs-lookup"><span data-stu-id="46b41-107">Members</span></span>                        | <span data-ttu-id="46b41-108">描述</span><span class="sxs-lookup"><span data-stu-id="46b41-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="46b41-109">调用</span><span class="sxs-lookup"><span data-stu-id="46b41-109">Invoke</span></span>](#invoke) | <span data-ttu-id="46b41-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="46b41-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="46b41-111">成员</span><span class="sxs-lookup"><span data-stu-id="46b41-111">Members</span></span>

#### <span data-ttu-id="46b41-112">调用</span><span class="sxs-lookup"><span data-stu-id="46b41-112">Invoke</span></span> 

<span data-ttu-id="46b41-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="46b41-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="46b41-114">公共 HRESULT[调用](#invoke)（[IWebView2WebView](IWebView2WebView.md) \* web 视图，[IWebView2NewWindowRequestedEventArgs](IWebView2NewWindowRequestedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="46b41-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2NewWindowRequestedEventArgs](IWebView2NewWindowRequestedEventArgs.md) \* args)</span></span>

