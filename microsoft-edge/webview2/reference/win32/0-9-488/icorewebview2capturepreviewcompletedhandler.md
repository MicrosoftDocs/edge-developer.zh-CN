---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 793dbde462e25ae0bfe0dc0bc475cc49e7237fb2
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653098"
---
# <span data-ttu-id="9f26c-104">interface ICoreWebView2CapturePreviewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="9f26c-104">interface ICoreWebView2CapturePreviewCompletedHandler</span></span> 

```
interface ICoreWebView2CapturePreviewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="9f26c-105">调用方实现此方法以接收 CapturePreview 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="9f26c-105">The caller implements this method to receive the result of the CapturePreview method.</span></span>

## <span data-ttu-id="9f26c-106">摘要</span><span class="sxs-lookup"><span data-stu-id="9f26c-106">Summary</span></span>

 <span data-ttu-id="9f26c-107">成员</span><span class="sxs-lookup"><span data-stu-id="9f26c-107">Members</span></span>                        | <span data-ttu-id="9f26c-108">描述</span><span class="sxs-lookup"><span data-stu-id="9f26c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9f26c-109">调用</span><span class="sxs-lookup"><span data-stu-id="9f26c-109">Invoke</span></span>](#invoke) | <span data-ttu-id="9f26c-110">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="9f26c-110">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="9f26c-111">将结果写入 CapturePreview 方法调用中提供的流。</span><span class="sxs-lookup"><span data-stu-id="9f26c-111">The result is written to the stream provided in the CapturePreview method call.</span></span>

## <span data-ttu-id="9f26c-112">成员</span><span class="sxs-lookup"><span data-stu-id="9f26c-112">Members</span></span>

#### <span data-ttu-id="9f26c-113">调用</span><span class="sxs-lookup"><span data-stu-id="9f26c-113">Invoke</span></span> 

<span data-ttu-id="9f26c-114">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="9f26c-114">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="9f26c-115">公共 HRESULT[调用](#invoke)（hresult 结果）</span><span class="sxs-lookup"><span data-stu-id="9f26c-115">public HRESULT [Invoke](#invoke)(HRESULT result)</span></span>

