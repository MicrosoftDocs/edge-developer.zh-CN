---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 9baf172a112f7fa84dae3a38cdbc0b0e0324473f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880799"
---
# <span data-ttu-id="f810e-104">0.9.515-接口 ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="f810e-104">0.9.515 - interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="f810e-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="f810e-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="f810e-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="f810e-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="f810e-107">调用方实现此接口以接收通过 CreateCoreWebView2Controller 创建的 CoreWebView2Controller。</span><span class="sxs-lookup"><span data-stu-id="f810e-107">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2Controller.</span></span>

## <span data-ttu-id="f810e-108">摘要</span><span class="sxs-lookup"><span data-stu-id="f810e-108">Summary</span></span>

 <span data-ttu-id="f810e-109">成员</span><span class="sxs-lookup"><span data-stu-id="f810e-109">Members</span></span>                        | <span data-ttu-id="f810e-110">描述</span><span class="sxs-lookup"><span data-stu-id="f810e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f810e-111">调用</span><span class="sxs-lookup"><span data-stu-id="f810e-111">Invoke</span></span>](#invoke) | <span data-ttu-id="f810e-112">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="f810e-112">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="f810e-113">成员</span><span class="sxs-lookup"><span data-stu-id="f810e-113">Members</span></span>

#### <span data-ttu-id="f810e-114">调用</span><span class="sxs-lookup"><span data-stu-id="f810e-114">Invoke</span></span> 

<span data-ttu-id="f810e-115">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="f810e-115">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="f810e-116">公共 HRESULT[调用](#invoke)（hresult 结果， [ICoreWebView2Controller](icorewebview2controller.md) \* createdController）</span><span class="sxs-lookup"><span data-stu-id="f810e-116">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Controller](icorewebview2controller.md) \* createdController)</span></span>

