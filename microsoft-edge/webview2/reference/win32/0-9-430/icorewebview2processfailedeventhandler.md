---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2ProcessFailedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: ed9b94b5bd9015b07cf44cf2cbeec330688242ff
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884104"
---
# <span data-ttu-id="398ed-104">0.9.430-接口 ICoreWebView2ProcessFailedEventHandler</span><span class="sxs-lookup"><span data-stu-id="398ed-104">0.9.430 - interface ICoreWebView2ProcessFailedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ProcessFailedEventHandler
  : public IUnknown
```

<span data-ttu-id="398ed-105">调用方实现此接口以接收 ProcessFailed 事件。</span><span class="sxs-lookup"><span data-stu-id="398ed-105">The caller implements this interface to receive ProcessFailed events.</span></span>

## <span data-ttu-id="398ed-106">摘要</span><span class="sxs-lookup"><span data-stu-id="398ed-106">Summary</span></span>

 <span data-ttu-id="398ed-107">成员</span><span class="sxs-lookup"><span data-stu-id="398ed-107">Members</span></span>                        | <span data-ttu-id="398ed-108">描述</span><span class="sxs-lookup"><span data-stu-id="398ed-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="398ed-109">调用</span><span class="sxs-lookup"><span data-stu-id="398ed-109">Invoke</span></span>](#invoke) | <span data-ttu-id="398ed-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="398ed-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="398ed-111">成员</span><span class="sxs-lookup"><span data-stu-id="398ed-111">Members</span></span>

#### <span data-ttu-id="398ed-112">调用</span><span class="sxs-lookup"><span data-stu-id="398ed-112">Invoke</span></span> 

<span data-ttu-id="398ed-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="398ed-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="398ed-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](ICoreWebView2.md) \* sender、[ICoreWebView2ProcessFailedEventArgs](ICoreWebView2ProcessFailedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="398ed-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2ProcessFailedEventArgs](ICoreWebView2ProcessFailedEventArgs.md) \* args)</span></span>

