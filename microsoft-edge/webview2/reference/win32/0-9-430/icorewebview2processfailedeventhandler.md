---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2ProcessFailedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 9dbf6ee630db1e99a74506f377fb4e01018c340f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877593"
---
# <span data-ttu-id="0a781-104">0.9.430-接口 ICoreWebView2ProcessFailedEventHandler</span><span class="sxs-lookup"><span data-stu-id="0a781-104">0.9.430 - interface ICoreWebView2ProcessFailedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="0a781-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="0a781-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="0a781-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="0a781-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ProcessFailedEventHandler
  : public IUnknown
```

<span data-ttu-id="0a781-107">调用方实现此接口以接收 ProcessFailed 事件。</span><span class="sxs-lookup"><span data-stu-id="0a781-107">The caller implements this interface to receive ProcessFailed events.</span></span>

## <span data-ttu-id="0a781-108">摘要</span><span class="sxs-lookup"><span data-stu-id="0a781-108">Summary</span></span>

 <span data-ttu-id="0a781-109">成员</span><span class="sxs-lookup"><span data-stu-id="0a781-109">Members</span></span>                        | <span data-ttu-id="0a781-110">描述</span><span class="sxs-lookup"><span data-stu-id="0a781-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0a781-111">调用</span><span class="sxs-lookup"><span data-stu-id="0a781-111">Invoke</span></span>](#invoke) | <span data-ttu-id="0a781-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="0a781-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="0a781-113">成员</span><span class="sxs-lookup"><span data-stu-id="0a781-113">Members</span></span>

#### <span data-ttu-id="0a781-114">调用</span><span class="sxs-lookup"><span data-stu-id="0a781-114">Invoke</span></span> 

<span data-ttu-id="0a781-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="0a781-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="0a781-116">公共 HRESULT[调用](#invoke)（[ICoreWebView2](ICoreWebView2.md) \* sender、[ICoreWebView2ProcessFailedEventArgs](ICoreWebView2ProcessFailedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="0a781-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2ProcessFailedEventArgs](ICoreWebView2ProcessFailedEventArgs.md) \* args)</span></span>

