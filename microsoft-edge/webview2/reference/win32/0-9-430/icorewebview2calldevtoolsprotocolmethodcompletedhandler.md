---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2CallDevToolsProtocolMethodCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: b9eb90c0735f290305327b4397cf90d24c76abb5
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881149"
---
# <span data-ttu-id="1e210-104">0.9.430-接口 ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="1e210-104">0.9.430 - interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="1e210-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="1e210-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="1e210-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="1e210-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler
  : public IUnknown
```

<span data-ttu-id="1e210-107">调用方实现此接口以接收 CallDevToolsProtocolMethod 完成结果。</span><span class="sxs-lookup"><span data-stu-id="1e210-107">The caller implements this interface to receive CallDevToolsProtocolMethod completion results.</span></span>

## <span data-ttu-id="1e210-108">摘要</span><span class="sxs-lookup"><span data-stu-id="1e210-108">Summary</span></span>

 <span data-ttu-id="1e210-109">成员</span><span class="sxs-lookup"><span data-stu-id="1e210-109">Members</span></span>                        | <span data-ttu-id="1e210-110">描述</span><span class="sxs-lookup"><span data-stu-id="1e210-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1e210-111">调用</span><span class="sxs-lookup"><span data-stu-id="1e210-111">Invoke</span></span>](#invoke) | <span data-ttu-id="1e210-112">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="1e210-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="1e210-113">成员</span><span class="sxs-lookup"><span data-stu-id="1e210-113">Members</span></span>

#### <span data-ttu-id="1e210-114">调用</span><span class="sxs-lookup"><span data-stu-id="1e210-114">Invoke</span></span> 

<span data-ttu-id="1e210-115">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="1e210-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="1e210-116">公共 HRESULT[调用](#invoke)（hresult ERRORCODE，LPCWSTR returnObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="1e210-116">public HRESULT [Invoke](#invoke)(HRESULT errorCode,LPCWSTR returnObjectAsJson)</span></span>

