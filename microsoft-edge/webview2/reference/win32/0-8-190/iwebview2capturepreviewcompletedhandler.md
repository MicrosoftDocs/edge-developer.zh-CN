---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2CapturePreviewCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 9e8b1cc973eefbd41c1fac0d7d9723ba35ec7302
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878678"
---
# <span data-ttu-id="e4521-104">0.8.355-接口 IWebView2CapturePreviewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="e4521-104">0.8.355 - interface IWebView2CapturePreviewCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="e4521-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="e4521-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="e4521-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="e4521-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2CapturePreviewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="e4521-107">调用方实现此方法以接收 CapturePreview 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="e4521-107">The caller implements this method to receive the result of the CapturePreview method.</span></span>

## <span data-ttu-id="e4521-108">摘要</span><span class="sxs-lookup"><span data-stu-id="e4521-108">Summary</span></span>

 <span data-ttu-id="e4521-109">成员</span><span class="sxs-lookup"><span data-stu-id="e4521-109">Members</span></span>                        | <span data-ttu-id="e4521-110">描述</span><span class="sxs-lookup"><span data-stu-id="e4521-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e4521-111">调用</span><span class="sxs-lookup"><span data-stu-id="e4521-111">Invoke</span></span>](#invoke) | <span data-ttu-id="e4521-112">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="e4521-112">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="e4521-113">将结果写入 CapturePreview 方法调用中提供的流。</span><span class="sxs-lookup"><span data-stu-id="e4521-113">The result is written to the stream provided in the CapturePreview method call.</span></span>

## <span data-ttu-id="e4521-114">成员</span><span class="sxs-lookup"><span data-stu-id="e4521-114">Members</span></span>

#### <span data-ttu-id="e4521-115">调用</span><span class="sxs-lookup"><span data-stu-id="e4521-115">Invoke</span></span> 

<span data-ttu-id="e4521-116">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="e4521-116">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="e4521-117">公共 HRESULT[调用](#invoke)（hresult 结果）</span><span class="sxs-lookup"><span data-stu-id="e4521-117">public HRESULT [Invoke](#invoke)(HRESULT result)</span></span>

