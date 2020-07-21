---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2AcceleratorKeyPressedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 7d510a547e43a4f04ef517c393ceeb3040d914e7
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885028"
---
# <span data-ttu-id="41f9a-104">0.8.355-接口 IWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="41f9a-104">0.8.355 - interface IWebView2AcceleratorKeyPressedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="41f9a-105">调用方实现此接口以接收 AcceleratorKeyPressed 事件。</span><span class="sxs-lookup"><span data-stu-id="41f9a-105">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="41f9a-106">摘要</span><span class="sxs-lookup"><span data-stu-id="41f9a-106">Summary</span></span>

 <span data-ttu-id="41f9a-107">成员</span><span class="sxs-lookup"><span data-stu-id="41f9a-107">Members</span></span>                        | <span data-ttu-id="41f9a-108">描述</span><span class="sxs-lookup"><span data-stu-id="41f9a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="41f9a-109">调用</span><span class="sxs-lookup"><span data-stu-id="41f9a-109">Invoke</span></span>](#invoke) | <span data-ttu-id="41f9a-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="41f9a-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="41f9a-111">成员</span><span class="sxs-lookup"><span data-stu-id="41f9a-111">Members</span></span>

#### <span data-ttu-id="41f9a-112">调用</span><span class="sxs-lookup"><span data-stu-id="41f9a-112">Invoke</span></span> 

<span data-ttu-id="41f9a-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="41f9a-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="41f9a-114">公共 HRESULT[调用](#invoke)（[IWebView2WebView](IWebView2WebView.md) \* web 视图，[IWebView2AcceleratorKeyPressedEventArgs](IWebView2AcceleratorKeyPressedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="41f9a-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2AcceleratorKeyPressedEventArgs](IWebView2AcceleratorKeyPressedEventArgs.md) \* args)</span></span>

