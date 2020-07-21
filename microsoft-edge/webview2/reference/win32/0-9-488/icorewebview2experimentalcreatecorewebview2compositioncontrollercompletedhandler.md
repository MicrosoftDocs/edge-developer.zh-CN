---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: f2598d40afc7c7def1c3fec634016f1a64905479
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885665"
---
# <span data-ttu-id="ad6da-104">0.9.515-接口 ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="ad6da-104">0.9.515 - interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="ad6da-105">调用方实现此接口以接收通过 CreateCoreWebView2CompositionController 创建的 CoreWebView2Controller。</span><span class="sxs-lookup"><span data-stu-id="ad6da-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2CompositionController.</span></span>

## <span data-ttu-id="ad6da-106">摘要</span><span class="sxs-lookup"><span data-stu-id="ad6da-106">Summary</span></span>

 <span data-ttu-id="ad6da-107">成员</span><span class="sxs-lookup"><span data-stu-id="ad6da-107">Members</span></span>                        | <span data-ttu-id="ad6da-108">描述</span><span class="sxs-lookup"><span data-stu-id="ad6da-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ad6da-109">调用</span><span class="sxs-lookup"><span data-stu-id="ad6da-109">Invoke</span></span>](#invoke) | <span data-ttu-id="ad6da-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="ad6da-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="ad6da-111">成员</span><span class="sxs-lookup"><span data-stu-id="ad6da-111">Members</span></span>

#### <span data-ttu-id="ad6da-112">调用</span><span class="sxs-lookup"><span data-stu-id="ad6da-112">Invoke</span></span> 

<span data-ttu-id="ad6da-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="ad6da-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="ad6da-114">公共 HRESULT[调用](#invoke)（hresult 结果， [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* web 视图）</span><span class="sxs-lookup"><span data-stu-id="ad6da-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span></span>

