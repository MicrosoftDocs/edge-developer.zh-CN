---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2CapturePreviewCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2CapturePreviewCompletedHandler
ms.openlocfilehash: 013a7076648b93bf259d28422f418365d988a586
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877438"
---
# <span data-ttu-id="627db-104">interface ICoreWebView2CapturePreviewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="627db-104">interface ICoreWebView2CapturePreviewCompletedHandler</span></span> 

```
interface ICoreWebView2CapturePreviewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="627db-105">调用方实现此方法以接收 CapturePreview 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="627db-105">The caller implements this method to receive the result of the CapturePreview method.</span></span>

## <span data-ttu-id="627db-106">摘要</span><span class="sxs-lookup"><span data-stu-id="627db-106">Summary</span></span>

 <span data-ttu-id="627db-107">成员</span><span class="sxs-lookup"><span data-stu-id="627db-107">Members</span></span>                        | <span data-ttu-id="627db-108">描述</span><span class="sxs-lookup"><span data-stu-id="627db-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="627db-109">调用</span><span class="sxs-lookup"><span data-stu-id="627db-109">Invoke</span></span>](#invoke) | <span data-ttu-id="627db-110">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="627db-110">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="627db-111">将结果写入 CapturePreview 方法调用中提供的流。</span><span class="sxs-lookup"><span data-stu-id="627db-111">The result is written to the stream provided in the CapturePreview method call.</span></span>

## <span data-ttu-id="627db-112">成员</span><span class="sxs-lookup"><span data-stu-id="627db-112">Members</span></span>

#### <span data-ttu-id="627db-113">调用</span><span class="sxs-lookup"><span data-stu-id="627db-113">Invoke</span></span> 

<span data-ttu-id="627db-114">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="627db-114">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="627db-115">公共 HRESULT[调用](#invoke)（hresult 结果）</span><span class="sxs-lookup"><span data-stu-id="627db-115">public HRESULT [Invoke](#invoke)(HRESULT result)</span></span>

