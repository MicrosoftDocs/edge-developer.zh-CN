---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2CreateWebView2EnvironmentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: fe81be15531cedae7a01355cbb6b6b27b52f15cc
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878629"
---
# <span data-ttu-id="02be0-104">0.8.355-接口 IWebView2CreateWebView2EnvironmentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="02be0-104">0.8.355 - interface IWebView2CreateWebView2EnvironmentCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="02be0-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="02be0-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="02be0-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="02be0-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2CreateWebView2EnvironmentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="02be0-107">调用方实现此接口以接收通过 CreateWebView2Environment 创建的 WebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="02be0-107">The caller implements this interface to receive the WebView2Environment created via CreateWebView2Environment.</span></span>

## <span data-ttu-id="02be0-108">摘要</span><span class="sxs-lookup"><span data-stu-id="02be0-108">Summary</span></span>

 <span data-ttu-id="02be0-109">成员</span><span class="sxs-lookup"><span data-stu-id="02be0-109">Members</span></span>                        | <span data-ttu-id="02be0-110">描述</span><span class="sxs-lookup"><span data-stu-id="02be0-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="02be0-111">调用</span><span class="sxs-lookup"><span data-stu-id="02be0-111">Invoke</span></span>](#invoke) | <span data-ttu-id="02be0-112">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="02be0-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="02be0-113">成员</span><span class="sxs-lookup"><span data-stu-id="02be0-113">Members</span></span>

#### <span data-ttu-id="02be0-114">调用</span><span class="sxs-lookup"><span data-stu-id="02be0-114">Invoke</span></span> 

<span data-ttu-id="02be0-115">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="02be0-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="02be0-116">公共 HRESULT[调用](#invoke)（hresult 结果，[IWebView2Environment](IWebView2Environment.md) \* webViewEnvironment）</span><span class="sxs-lookup"><span data-stu-id="02be0-116">public HRESULT [Invoke](#invoke)(HRESULT result,[IWebView2Environment](IWebView2Environment.md) \* webViewEnvironment)</span></span>

