---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
ms.openlocfilehash: c021cfa866e55bfdf30185eeaf6015db1b523271
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886521"
---
# <span data-ttu-id="54d86-104">interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="54d86-104">interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgsPopulateResponseContentCompletedHandler
  : public IUnknown
```

<span data-ttu-id="54d86-105">PopulateResponseContent async 方法的完成处理程序。</span><span class="sxs-lookup"><span data-stu-id="54d86-105">Completion handler for PopulateResponseContent async method.</span></span>

## <span data-ttu-id="54d86-106">摘要</span><span class="sxs-lookup"><span data-stu-id="54d86-106">Summary</span></span>

 <span data-ttu-id="54d86-107">成员</span><span class="sxs-lookup"><span data-stu-id="54d86-107">Members</span></span>                        | <span data-ttu-id="54d86-108">描述</span><span class="sxs-lookup"><span data-stu-id="54d86-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="54d86-109">调用</span><span class="sxs-lookup"><span data-stu-id="54d86-109">Invoke</span></span>](#invoke) | <span data-ttu-id="54d86-110">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="54d86-110">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

<span data-ttu-id="54d86-111">当 WebResourceResponseReceieved 事件的响应的内容流可用时，它将被调用。</span><span class="sxs-lookup"><span data-stu-id="54d86-111">It's invoked when the Content stream of the Response of a WebResourceResponseReceieved event is available.</span></span>

## <span data-ttu-id="54d86-112">成员</span><span class="sxs-lookup"><span data-stu-id="54d86-112">Members</span></span>

#### <span data-ttu-id="54d86-113">调用</span><span class="sxs-lookup"><span data-stu-id="54d86-113">Invoke</span></span> 

<span data-ttu-id="54d86-114">调用以向实施者提供相应异步方法调用的完成状态。</span><span class="sxs-lookup"><span data-stu-id="54d86-114">Called to provide the implementer with the completion status of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="54d86-115">公共 HRESULT[调用](#invoke)（hresult 结果）</span><span class="sxs-lookup"><span data-stu-id="54d86-115">public HRESULT [Invoke](#invoke)(HRESULT result)</span></span>

