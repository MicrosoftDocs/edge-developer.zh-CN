---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2ProcessFailedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 372bd0f6faa3b5ed50c539a2e10809bfe9b95209
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878230"
---
# <span data-ttu-id="efee6-104">0.8.355-接口 IWebView2ProcessFailedEventHandler</span><span class="sxs-lookup"><span data-stu-id="efee6-104">0.8.355 - interface IWebView2ProcessFailedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="efee6-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="efee6-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="efee6-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="efee6-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2ProcessFailedEventHandler
  : public IUnknown
```

<span data-ttu-id="efee6-107">调用方实现此接口以接收 ProcessFailed 事件。</span><span class="sxs-lookup"><span data-stu-id="efee6-107">The caller implements this interface to receive ProcessFailed events.</span></span>

## <span data-ttu-id="efee6-108">摘要</span><span class="sxs-lookup"><span data-stu-id="efee6-108">Summary</span></span>

 <span data-ttu-id="efee6-109">成员</span><span class="sxs-lookup"><span data-stu-id="efee6-109">Members</span></span>                        | <span data-ttu-id="efee6-110">描述</span><span class="sxs-lookup"><span data-stu-id="efee6-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="efee6-111">调用</span><span class="sxs-lookup"><span data-stu-id="efee6-111">Invoke</span></span>](#invoke) | <span data-ttu-id="efee6-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="efee6-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="efee6-113">成员</span><span class="sxs-lookup"><span data-stu-id="efee6-113">Members</span></span>

#### <span data-ttu-id="efee6-114">调用</span><span class="sxs-lookup"><span data-stu-id="efee6-114">Invoke</span></span> 

<span data-ttu-id="efee6-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="efee6-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="efee6-116">公共 HRESULT[调用](#invoke)（[IWebView2WebView](IWebView2WebView.md) \* web 视图，[IWebView2ProcessFailedEventArgs](IWebView2ProcessFailedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="efee6-116">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2ProcessFailedEventArgs](IWebView2ProcessFailedEventArgs.md) \* args)</span></span>

