---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2CallDevToolsProtocolMethodCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: ed98aed25662a37a0cecf86eadec34361aa3efa8
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884300"
---
# <span data-ttu-id="69e38-104">0.9.430-接口 ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="69e38-104">0.9.430 - interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2CallDevToolsProtocolMethodCompletedHandler
  : public IUnknown
```

<span data-ttu-id="69e38-105">调用方实现此接口以接收 CallDevToolsProtocolMethod 完成结果。</span><span class="sxs-lookup"><span data-stu-id="69e38-105">The caller implements this interface to receive CallDevToolsProtocolMethod completion results.</span></span>

## <span data-ttu-id="69e38-106">摘要</span><span class="sxs-lookup"><span data-stu-id="69e38-106">Summary</span></span>

 <span data-ttu-id="69e38-107">成员</span><span class="sxs-lookup"><span data-stu-id="69e38-107">Members</span></span>                        | <span data-ttu-id="69e38-108">描述</span><span class="sxs-lookup"><span data-stu-id="69e38-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="69e38-109">调用</span><span class="sxs-lookup"><span data-stu-id="69e38-109">Invoke</span></span>](#invoke) | <span data-ttu-id="69e38-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="69e38-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="69e38-111">成员</span><span class="sxs-lookup"><span data-stu-id="69e38-111">Members</span></span>

#### <span data-ttu-id="69e38-112">调用</span><span class="sxs-lookup"><span data-stu-id="69e38-112">Invoke</span></span> 

<span data-ttu-id="69e38-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="69e38-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="69e38-114">公共 HRESULT[调用](#invoke)（hresult ERRORCODE，LPCWSTR returnObjectAsJson）</span><span class="sxs-lookup"><span data-stu-id="69e38-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode,LPCWSTR returnObjectAsJson)</span></span>

