---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
ms.openlocfilehash: fd762c994d4c42e5e92dec09add2aa3b85b0ec80
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011681"
---
# <span data-ttu-id="de83c-104">interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="de83c-104">interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCreateCoreWebView2CompositionControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="de83c-105">调用方实现此接口以接收通过 CreateCoreWebView2CompositionController 创建的 CoreWebView2Controller。</span><span class="sxs-lookup"><span data-stu-id="de83c-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2CompositionController.</span></span>

## <span data-ttu-id="de83c-106">摘要</span><span class="sxs-lookup"><span data-stu-id="de83c-106">Summary</span></span>

 <span data-ttu-id="de83c-107">成员</span><span class="sxs-lookup"><span data-stu-id="de83c-107">Members</span></span>                        | <span data-ttu-id="de83c-108">描述</span><span class="sxs-lookup"><span data-stu-id="de83c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="de83c-109">调用</span><span class="sxs-lookup"><span data-stu-id="de83c-109">Invoke</span></span>](#invoke) | <span data-ttu-id="de83c-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="de83c-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="de83c-111">成员</span><span class="sxs-lookup"><span data-stu-id="de83c-111">Members</span></span>

#### <span data-ttu-id="de83c-112">调用</span><span class="sxs-lookup"><span data-stu-id="de83c-112">Invoke</span></span> 

<span data-ttu-id="de83c-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="de83c-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="de83c-114">公共 HRESULT [调用](#invoke) (HRESULT ErrorCode， [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* web 视图) </span><span class="sxs-lookup"><span data-stu-id="de83c-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, [ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* webView)</span></span>

