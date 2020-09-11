---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
ms.openlocfilehash: 845c3a3f0241fb66032ecf818c484b6110258327
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011796"
---
# <span data-ttu-id="524cc-104">interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="524cc-104">interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span></span> 

```
interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="524cc-105">调用方实现此接口以接收通过 CreateCoreWebView2Controller 创建的 CoreWebView2Controller。</span><span class="sxs-lookup"><span data-stu-id="524cc-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2Controller.</span></span>

## <span data-ttu-id="524cc-106">摘要</span><span class="sxs-lookup"><span data-stu-id="524cc-106">Summary</span></span>

 <span data-ttu-id="524cc-107">成员</span><span class="sxs-lookup"><span data-stu-id="524cc-107">Members</span></span>                        | <span data-ttu-id="524cc-108">描述</span><span class="sxs-lookup"><span data-stu-id="524cc-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="524cc-109">调用</span><span class="sxs-lookup"><span data-stu-id="524cc-109">Invoke</span></span>](#invoke) | <span data-ttu-id="524cc-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="524cc-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="524cc-111">成员</span><span class="sxs-lookup"><span data-stu-id="524cc-111">Members</span></span>

#### <span data-ttu-id="524cc-112">调用</span><span class="sxs-lookup"><span data-stu-id="524cc-112">Invoke</span></span> 

<span data-ttu-id="524cc-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="524cc-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="524cc-114">公共 HRESULT [调用](#invoke) (HRESULT ErrorCode， [ICoreWebView2Controller](icorewebview2controller.md) \* createdController) </span><span class="sxs-lookup"><span data-stu-id="524cc-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, [ICoreWebView2Controller](icorewebview2controller.md) \* createdController)</span></span>

