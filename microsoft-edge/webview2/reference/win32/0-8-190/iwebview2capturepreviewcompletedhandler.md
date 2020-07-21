---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2CapturePreviewCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 991c09167ba3fe382c74d6244c76ffae25d628a6
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886190"
---
# <span data-ttu-id="bf8f9-104">0.8.355-接口 IWebView2CapturePreviewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="bf8f9-104">0.8.355 - interface IWebView2CapturePreviewCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2CapturePreviewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="bf8f9-105">调用方实现此方法以接收 CapturePreview 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="bf8f9-105">The caller implements this method to receive the result of the CapturePreview method.</span></span>

## <span data-ttu-id="bf8f9-106">摘要</span><span class="sxs-lookup"><span data-stu-id="bf8f9-106">Summary</span></span>

 <span data-ttu-id="bf8f9-107">成员</span><span class="sxs-lookup"><span data-stu-id="bf8f9-107">Members</span></span>                        | <span data-ttu-id="bf8f9-108">描述</span><span class="sxs-lookup"><span data-stu-id="bf8f9-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bf8f9-109">调用</span><span class="sxs-lookup"><span data-stu-id="bf8f9-109">Invoke</span></span>](#invoke) | <span data-ttu-id="bf8f9-110">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="bf8f9-110">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="bf8f9-111">将结果写入 CapturePreview 方法调用中提供的流。</span><span class="sxs-lookup"><span data-stu-id="bf8f9-111">The result is written to the stream provided in the CapturePreview method call.</span></span>

## <span data-ttu-id="bf8f9-112">成员</span><span class="sxs-lookup"><span data-stu-id="bf8f9-112">Members</span></span>

#### <span data-ttu-id="bf8f9-113">调用</span><span class="sxs-lookup"><span data-stu-id="bf8f9-113">Invoke</span></span> 

<span data-ttu-id="bf8f9-114">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="bf8f9-114">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="bf8f9-115">公共 HRESULT[调用](#invoke)（hresult 结果）</span><span class="sxs-lookup"><span data-stu-id="bf8f9-115">public HRESULT [Invoke](#invoke)(HRESULT result)</span></span>

