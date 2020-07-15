---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2CreateCoreWebView2HostCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 6a707465fa08667e9915a77fdc93ee018e0f9631
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10881121"
---
# <span data-ttu-id="a902f-104">0.9.430-接口 ICoreWebView2CreateCoreWebView2HostCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="a902f-104">0.9.430 - interface ICoreWebView2CreateCoreWebView2HostCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="a902f-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="a902f-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="a902f-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="a902f-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2CreateCoreWebView2HostCompletedHandler
  : public IUnknown
```

<span data-ttu-id="a902f-107">调用方实现此接口以接收通过 CreateCoreWebView2Host 创建的 CoreWebView2Host。</span><span class="sxs-lookup"><span data-stu-id="a902f-107">The caller implements this interface to receive the CoreWebView2Host created via CreateCoreWebView2Host.</span></span>

## <span data-ttu-id="a902f-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a902f-108">Summary</span></span>

 <span data-ttu-id="a902f-109">成员</span><span class="sxs-lookup"><span data-stu-id="a902f-109">Members</span></span>                        | <span data-ttu-id="a902f-110">描述</span><span class="sxs-lookup"><span data-stu-id="a902f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a902f-111">调用</span><span class="sxs-lookup"><span data-stu-id="a902f-111">Invoke</span></span>](#invoke) | <span data-ttu-id="a902f-112">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="a902f-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="a902f-113">成员</span><span class="sxs-lookup"><span data-stu-id="a902f-113">Members</span></span>

#### <span data-ttu-id="a902f-114">调用</span><span class="sxs-lookup"><span data-stu-id="a902f-114">Invoke</span></span> 

<span data-ttu-id="a902f-115">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="a902f-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="a902f-116">公共 HRESULT[调用](#invoke)（hresult 结果，[ICoreWebView2Host](ICoreWebView2Host.md) \* created_host）</span><span class="sxs-lookup"><span data-stu-id="a902f-116">public HRESULT [Invoke](#invoke)(HRESULT result,[ICoreWebView2Host](ICoreWebView2Host.md) \* created_host)</span></span>

