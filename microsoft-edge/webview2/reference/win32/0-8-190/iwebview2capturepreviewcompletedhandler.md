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
ms.openlocfilehash: 0cdb6dc17549022bac6ada366f5f54dd5b9b7e12
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653141"
---
# <span data-ttu-id="a3db6-104">interface IWebView2CapturePreviewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="a3db6-104">interface IWebView2CapturePreviewCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="a3db6-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="a3db6-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="a3db6-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="a3db6-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2CapturePreviewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="a3db6-107">调用方实现此方法以接收 CapturePreview 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="a3db6-107">The caller implements this method to receive the result of the CapturePreview method.</span></span>

## <span data-ttu-id="a3db6-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a3db6-108">Summary</span></span>

 <span data-ttu-id="a3db6-109">成员</span><span class="sxs-lookup"><span data-stu-id="a3db6-109">Members</span></span>                        | <span data-ttu-id="a3db6-110">描述</span><span class="sxs-lookup"><span data-stu-id="a3db6-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a3db6-111">调用</span><span class="sxs-lookup"><span data-stu-id="a3db6-111">Invoke</span></span>](#invoke) | <span data-ttu-id="a3db6-112">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="a3db6-112">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="a3db6-113">将结果写入 CapturePreview 方法调用中提供的流。</span><span class="sxs-lookup"><span data-stu-id="a3db6-113">The result is written to the stream provided in the CapturePreview method call.</span></span>

## <span data-ttu-id="a3db6-114">成员</span><span class="sxs-lookup"><span data-stu-id="a3db6-114">Members</span></span>

#### <span data-ttu-id="a3db6-115">调用</span><span class="sxs-lookup"><span data-stu-id="a3db6-115">Invoke</span></span> 

<span data-ttu-id="a3db6-116">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="a3db6-116">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="a3db6-117">公共 HRESULT[调用](#invoke)（hresult 结果）</span><span class="sxs-lookup"><span data-stu-id="a3db6-117">public HRESULT [Invoke](#invoke)(HRESULT result)</span></span>

