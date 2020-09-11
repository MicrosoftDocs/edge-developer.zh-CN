---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
ms.openlocfilehash: 6c97e0591d55570f4076f6a5c4f2eebc2cc7c5ad
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011642"
---
# <span data-ttu-id="ec515-104">interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="ec515-104">interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="ec515-105">PopulateResponseContent async 方法的完成处理程序。</span><span class="sxs-lookup"><span data-stu-id="ec515-105">Completion handler for PopulateResponseContent async method.</span></span>

## <span data-ttu-id="ec515-106">摘要</span><span class="sxs-lookup"><span data-stu-id="ec515-106">Summary</span></span>

 <span data-ttu-id="ec515-107">成员</span><span class="sxs-lookup"><span data-stu-id="ec515-107">Members</span></span>                        | <span data-ttu-id="ec515-108">描述</span><span class="sxs-lookup"><span data-stu-id="ec515-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ec515-109">调用</span><span class="sxs-lookup"><span data-stu-id="ec515-109">Invoke</span></span>](#invoke) | <span data-ttu-id="ec515-110">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="ec515-110">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="ec515-111">当 WebResourceResponseReceieved 事件的响应的内容流可用时，它将被调用。</span><span class="sxs-lookup"><span data-stu-id="ec515-111">It's invoked when the Content stream of the Response of a WebResourceResponseReceieved event is available.</span></span>

## <span data-ttu-id="ec515-112">成员</span><span class="sxs-lookup"><span data-stu-id="ec515-112">Members</span></span>

#### <span data-ttu-id="ec515-113">调用</span><span class="sxs-lookup"><span data-stu-id="ec515-113">Invoke</span></span> 

<span data-ttu-id="ec515-114">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="ec515-114">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="ec515-115">公共 HRESULT [调用](#invoke) (HRESULT errorCode) </span><span class="sxs-lookup"><span data-stu-id="ec515-115">public HRESULT [Invoke](#invoke)(HRESULT errorCode)</span></span>

