---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2CreateWebViewCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 381f46c6682a77905d9caa720e4ba9b2d1d531b7
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886143"
---
# <span data-ttu-id="bb1c3-104">0.8.355-接口 IWebView2CreateWebViewCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="bb1c3-104">0.8.355 - interface IWebView2CreateWebViewCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2CreateWebViewCompletedHandler
  : public IUnknown
```

<span data-ttu-id="bb1c3-105">调用方实现此接口以接收通过 CreateWebView 创建的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="bb1c3-105">The caller implements this interface to receive the WebView created via CreateWebView.</span></span>

## <span data-ttu-id="bb1c3-106">摘要</span><span class="sxs-lookup"><span data-stu-id="bb1c3-106">Summary</span></span>

 <span data-ttu-id="bb1c3-107">成员</span><span class="sxs-lookup"><span data-stu-id="bb1c3-107">Members</span></span>                        | <span data-ttu-id="bb1c3-108">描述</span><span class="sxs-lookup"><span data-stu-id="bb1c3-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bb1c3-109">调用</span><span class="sxs-lookup"><span data-stu-id="bb1c3-109">Invoke</span></span>](#invoke) | <span data-ttu-id="bb1c3-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="bb1c3-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="bb1c3-111">成员</span><span class="sxs-lookup"><span data-stu-id="bb1c3-111">Members</span></span>

#### <span data-ttu-id="bb1c3-112">调用</span><span class="sxs-lookup"><span data-stu-id="bb1c3-112">Invoke</span></span> 

<span data-ttu-id="bb1c3-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="bb1c3-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="bb1c3-114">公共 HRESULT[调用](#invoke)（hresult 结果，[IWebView2WebView](IWebView2WebView.md) \* web 视图）</span><span class="sxs-lookup"><span data-stu-id="bb1c3-114">public HRESULT [Invoke](#invoke)(HRESULT result,[IWebView2WebView](IWebView2WebView.md) \* webView)</span></span>

