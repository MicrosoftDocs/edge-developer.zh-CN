---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2CapturePreviewCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2CapturePreviewCompletedHandler
ms.openlocfilehash: e526b723f111d7212a5da4b25840c89b69eb2e52
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011618"
---
# <span data-ttu-id="b6471-104">interface ICoreWebView2CapturePreviewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="b6471-104">interface ICoreWebView2CapturePreviewCompletedHandler</span></span> 

```
interface ICoreWebView2CapturePreviewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="b6471-105">调用方实现此方法以接收 CapturePreview 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="b6471-105">The caller implements this method to receive the result of the CapturePreview method.</span></span>

## <span data-ttu-id="b6471-106">摘要</span><span class="sxs-lookup"><span data-stu-id="b6471-106">Summary</span></span>

 <span data-ttu-id="b6471-107">成员</span><span class="sxs-lookup"><span data-stu-id="b6471-107">Members</span></span>                        | <span data-ttu-id="b6471-108">描述</span><span class="sxs-lookup"><span data-stu-id="b6471-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b6471-109">调用</span><span class="sxs-lookup"><span data-stu-id="b6471-109">Invoke</span></span>](#invoke) | <span data-ttu-id="b6471-110">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="b6471-110">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="b6471-111">将结果写入 CapturePreview 方法调用中提供的流。</span><span class="sxs-lookup"><span data-stu-id="b6471-111">The result is written to the stream provided in the CapturePreview method call.</span></span>

## <span data-ttu-id="b6471-112">成员</span><span class="sxs-lookup"><span data-stu-id="b6471-112">Members</span></span>

#### <span data-ttu-id="b6471-113">调用</span><span class="sxs-lookup"><span data-stu-id="b6471-113">Invoke</span></span> 

<span data-ttu-id="b6471-114">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="b6471-114">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="b6471-115">公共 HRESULT [调用](#invoke) (HRESULT errorCode) </span><span class="sxs-lookup"><span data-stu-id="b6471-115">public HRESULT [Invoke](#invoke)(HRESULT errorCode)</span></span>

