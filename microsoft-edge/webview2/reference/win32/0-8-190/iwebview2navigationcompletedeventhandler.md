---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2NavigationCompletedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: cf799ae12b977f66bfba4d1b7664e3abc6241304
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885917"
---
# <span data-ttu-id="bf884-104">0.8.355-接口 IWebView2NavigationCompletedEventHandler</span><span class="sxs-lookup"><span data-stu-id="bf884-104">0.8.355 - interface IWebView2NavigationCompletedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NavigationCompletedEventHandler
  : public IUnknown
```

<span data-ttu-id="bf884-105">调用方实现此接口以接收 NavigationCompleted 事件。</span><span class="sxs-lookup"><span data-stu-id="bf884-105">The caller implements this interface to receive the NavigationCompleted event.</span></span>

## <span data-ttu-id="bf884-106">摘要</span><span class="sxs-lookup"><span data-stu-id="bf884-106">Summary</span></span>

 <span data-ttu-id="bf884-107">成员</span><span class="sxs-lookup"><span data-stu-id="bf884-107">Members</span></span>                        | <span data-ttu-id="bf884-108">描述</span><span class="sxs-lookup"><span data-stu-id="bf884-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bf884-109">调用</span><span class="sxs-lookup"><span data-stu-id="bf884-109">Invoke</span></span>](#invoke) | <span data-ttu-id="bf884-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="bf884-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="bf884-111">成员</span><span class="sxs-lookup"><span data-stu-id="bf884-111">Members</span></span>

#### <span data-ttu-id="bf884-112">调用</span><span class="sxs-lookup"><span data-stu-id="bf884-112">Invoke</span></span> 

<span data-ttu-id="bf884-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="bf884-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="bf884-114">公共 HRESULT[调用](#invoke)（[IWebView2WebView](IWebView2WebView.md) \* web 视图，[IWebView2NavigationCompletedEventArgs](IWebView2NavigationCompletedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="bf884-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2NavigationCompletedEventArgs](IWebView2NavigationCompletedEventArgs.md) \* args)</span></span>

