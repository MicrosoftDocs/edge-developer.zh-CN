---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: f85444231cb04857326d1662b2b4fb957e5305fe
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884496"
---
# <span data-ttu-id="3e3fa-104">0.9.515-接口 ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="3e3fa-104">0.9.515 - interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="3e3fa-105">调用方实现此接口以接收通过 CreateCoreWebView2Controller 创建的 CoreWebView2Controller。</span><span class="sxs-lookup"><span data-stu-id="3e3fa-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2Controller.</span></span>

## <span data-ttu-id="3e3fa-106">摘要</span><span class="sxs-lookup"><span data-stu-id="3e3fa-106">Summary</span></span>

 <span data-ttu-id="3e3fa-107">成员</span><span class="sxs-lookup"><span data-stu-id="3e3fa-107">Members</span></span>                        | <span data-ttu-id="3e3fa-108">描述</span><span class="sxs-lookup"><span data-stu-id="3e3fa-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3e3fa-109">调用</span><span class="sxs-lookup"><span data-stu-id="3e3fa-109">Invoke</span></span>](#invoke) | <span data-ttu-id="3e3fa-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="3e3fa-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="3e3fa-111">成员</span><span class="sxs-lookup"><span data-stu-id="3e3fa-111">Members</span></span>

#### <span data-ttu-id="3e3fa-112">调用</span><span class="sxs-lookup"><span data-stu-id="3e3fa-112">Invoke</span></span> 

<span data-ttu-id="3e3fa-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="3e3fa-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="3e3fa-114">公共 HRESULT[调用](#invoke)（hresult 结果， [ICoreWebView2Controller](icorewebview2controller.md) \* createdController）</span><span class="sxs-lookup"><span data-stu-id="3e3fa-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Controller](icorewebview2controller.md) \* createdController)</span></span>

