---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
ms.openlocfilehash: e26d711c24758f82d42067fa28e71bc6ac1177ad
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877411"
---
# <span data-ttu-id="f9322-104">interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="f9322-104">interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler</span></span> 

```
interface ICoreWebView2CreateCoreWebView2ControllerCompletedHandler
  : public IUnknown
```

<span data-ttu-id="f9322-105">调用方实现此接口以接收通过 CreateCoreWebView2Controller 创建的 CoreWebView2Controller。</span><span class="sxs-lookup"><span data-stu-id="f9322-105">The caller implements this interface to receive the CoreWebView2Controller created via CreateCoreWebView2Controller.</span></span>

## <span data-ttu-id="f9322-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f9322-106">Summary</span></span>

 <span data-ttu-id="f9322-107">成员</span><span class="sxs-lookup"><span data-stu-id="f9322-107">Members</span></span>                        | <span data-ttu-id="f9322-108">描述</span><span class="sxs-lookup"><span data-stu-id="f9322-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f9322-109">调用</span><span class="sxs-lookup"><span data-stu-id="f9322-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f9322-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="f9322-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="f9322-111">成员</span><span class="sxs-lookup"><span data-stu-id="f9322-111">Members</span></span>

#### <span data-ttu-id="f9322-112">调用</span><span class="sxs-lookup"><span data-stu-id="f9322-112">Invoke</span></span> 

<span data-ttu-id="f9322-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="f9322-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="f9322-114">公共 HRESULT[调用](#invoke)（hresult 结果， [ICoreWebView2Controller](icorewebview2controller.md) \* createdController）</span><span class="sxs-lookup"><span data-stu-id="f9322-114">public HRESULT [Invoke](#invoke)(HRESULT result, [ICoreWebView2Controller](icorewebview2controller.md) \* createdController)</span></span>

