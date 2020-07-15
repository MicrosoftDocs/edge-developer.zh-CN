---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2ContainsFullScreenElementChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: ff5cedad802f0f367e694ddf5c62290276fa4aa4
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880918"
---
# <span data-ttu-id="d1263-104">0.9.515-接口 ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d1263-104">0.9.515 - interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="d1263-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="d1263-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="d1263-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="d1263-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="d1263-107">调用方实现此方法以接收 ContainsFullScreenElementChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="d1263-107">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="d1263-108">摘要</span><span class="sxs-lookup"><span data-stu-id="d1263-108">Summary</span></span>

 <span data-ttu-id="d1263-109">成员</span><span class="sxs-lookup"><span data-stu-id="d1263-109">Members</span></span>                        | <span data-ttu-id="d1263-110">描述</span><span class="sxs-lookup"><span data-stu-id="d1263-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d1263-111">调用</span><span class="sxs-lookup"><span data-stu-id="d1263-111">Invoke</span></span>](#invoke) | <span data-ttu-id="d1263-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d1263-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="d1263-113">此事件没有事件参数。</span><span class="sxs-lookup"><span data-stu-id="d1263-113">There are no event args for this event.</span></span>

## <span data-ttu-id="d1263-114">成员</span><span class="sxs-lookup"><span data-stu-id="d1263-114">Members</span></span>

#### <span data-ttu-id="d1263-115">调用</span><span class="sxs-lookup"><span data-stu-id="d1263-115">Invoke</span></span> 

<span data-ttu-id="d1263-116">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d1263-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="d1263-117">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="d1263-117">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="d1263-118">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="d1263-118">There are no event args and the args parameter will be null.</span></span>

