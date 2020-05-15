---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 9c0714f35fae0a11c66e50282de9586462e6f48c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653194"
---
# <span data-ttu-id="dc264-104">interface IWebView2NavigationCompletedEventHandler</span><span class="sxs-lookup"><span data-stu-id="dc264-104">interface IWebView2NavigationCompletedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="dc264-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="dc264-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="dc264-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="dc264-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2NavigationCompletedEventHandler
  : public IUnknown
```

<span data-ttu-id="dc264-107">调用方实现此接口以接收 NavigationCompleted 事件。</span><span class="sxs-lookup"><span data-stu-id="dc264-107">The caller implements this interface to receive the NavigationCompleted event.</span></span>

## <span data-ttu-id="dc264-108">摘要</span><span class="sxs-lookup"><span data-stu-id="dc264-108">Summary</span></span>

 <span data-ttu-id="dc264-109">成员</span><span class="sxs-lookup"><span data-stu-id="dc264-109">Members</span></span>                        | <span data-ttu-id="dc264-110">描述</span><span class="sxs-lookup"><span data-stu-id="dc264-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="dc264-111">调用</span><span class="sxs-lookup"><span data-stu-id="dc264-111">Invoke</span></span>](#invoke) | <span data-ttu-id="dc264-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="dc264-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="dc264-113">成员</span><span class="sxs-lookup"><span data-stu-id="dc264-113">Members</span></span>

#### <span data-ttu-id="dc264-114">调用</span><span class="sxs-lookup"><span data-stu-id="dc264-114">Invoke</span></span> 

<span data-ttu-id="dc264-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="dc264-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="dc264-116">公共 HRESULT[调用](#invoke)（[IWebView2WebView](IWebView2WebView.md) \* web 视图，[IWebView2NavigationCompletedEventArgs](IWebView2NavigationCompletedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="dc264-116">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2NavigationCompletedEventArgs](IWebView2NavigationCompletedEventArgs.md) \* args)</span></span>

