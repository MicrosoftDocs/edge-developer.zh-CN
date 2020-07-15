---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2CreateWebViewCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 3459bf9c44dc4f0ce10bc383f6f695d4949023da
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878636"
---
# <span data-ttu-id="59747-104">0.8.355-接口 IWebView2CreateWebViewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="59747-104">0.8.355 - interface IWebView2CreateWebViewCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="59747-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="59747-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="59747-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="59747-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2CreateWebViewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="59747-107">调用方实现此接口以接收通过 CreateWebView 创建的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="59747-107">The caller implements this interface to receive the WebView created via CreateWebView.</span></span>

## <span data-ttu-id="59747-108">摘要</span><span class="sxs-lookup"><span data-stu-id="59747-108">Summary</span></span>

 <span data-ttu-id="59747-109">成员</span><span class="sxs-lookup"><span data-stu-id="59747-109">Members</span></span>                        | <span data-ttu-id="59747-110">描述</span><span class="sxs-lookup"><span data-stu-id="59747-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="59747-111">调用</span><span class="sxs-lookup"><span data-stu-id="59747-111">Invoke</span></span>](#invoke) | <span data-ttu-id="59747-112">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="59747-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="59747-113">成员</span><span class="sxs-lookup"><span data-stu-id="59747-113">Members</span></span>

#### <span data-ttu-id="59747-114">调用</span><span class="sxs-lookup"><span data-stu-id="59747-114">Invoke</span></span> 

<span data-ttu-id="59747-115">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="59747-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="59747-116">公共 HRESULT[调用](#invoke)（hresult 结果，[IWebView2WebView](IWebView2WebView.md) \* web 视图）</span><span class="sxs-lookup"><span data-stu-id="59747-116">public HRESULT [Invoke](#invoke)(HRESULT result,[IWebView2WebView](IWebView2WebView.md) \* webView)</span></span>

