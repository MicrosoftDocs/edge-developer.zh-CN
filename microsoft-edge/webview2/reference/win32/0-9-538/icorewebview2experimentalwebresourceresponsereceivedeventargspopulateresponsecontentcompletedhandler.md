---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
ms.openlocfilehash: 6a854eb9ca73f45e366edfa144c273f780bcee94
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011410"
---
# <span data-ttu-id="ff87e-104">0.9.579-接口 ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="ff87e-104">0.9.579 - interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="ff87e-105">PopulateResponseContent async 方法的完成处理程序。</span><span class="sxs-lookup"><span data-stu-id="ff87e-105">Completion handler for PopulateResponseContent async method.</span></span>

## <span data-ttu-id="ff87e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="ff87e-106">Summary</span></span>

 <span data-ttu-id="ff87e-107">成员</span><span class="sxs-lookup"><span data-stu-id="ff87e-107">Members</span></span>                        | <span data-ttu-id="ff87e-108">描述</span><span class="sxs-lookup"><span data-stu-id="ff87e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ff87e-109">调用</span><span class="sxs-lookup"><span data-stu-id="ff87e-109">Invoke</span></span>](#invoke) | <span data-ttu-id="ff87e-110">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="ff87e-110">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="ff87e-111">当 WebResourceResponseReceieved 事件的响应的内容流可用时，它将被调用。</span><span class="sxs-lookup"><span data-stu-id="ff87e-111">It's invoked when the Content stream of the Response of a WebResourceResponseReceieved event is available.</span></span>

## <span data-ttu-id="ff87e-112">成员</span><span class="sxs-lookup"><span data-stu-id="ff87e-112">Members</span></span>

#### <span data-ttu-id="ff87e-113">调用</span><span class="sxs-lookup"><span data-stu-id="ff87e-113">Invoke</span></span> 

<span data-ttu-id="ff87e-114">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="ff87e-114">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="ff87e-115">公共 HRESULT [调用](#invoke) (HRESULT 结果) </span><span class="sxs-lookup"><span data-stu-id="ff87e-115">public HRESULT [Invoke](#invoke)(HRESULT result)</span></span>

