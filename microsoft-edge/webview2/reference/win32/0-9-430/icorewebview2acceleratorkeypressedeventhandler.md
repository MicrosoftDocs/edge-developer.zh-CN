---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2AcceleratorKeyPressedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 2e12f96307b86fe4c3416c4bde2379869b269cb8
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884356"
---
# <span data-ttu-id="f6532-104">0.9.430-接口 ICoreWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="f6532-104">0.9.430 - interface ICoreWebView2AcceleratorKeyPressedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="f6532-105">调用方实现此接口以接收 AcceleratorKeyPressed 事件。</span><span class="sxs-lookup"><span data-stu-id="f6532-105">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="f6532-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f6532-106">Summary</span></span>

 <span data-ttu-id="f6532-107">成员</span><span class="sxs-lookup"><span data-stu-id="f6532-107">Members</span></span>                        | <span data-ttu-id="f6532-108">描述</span><span class="sxs-lookup"><span data-stu-id="f6532-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f6532-109">调用</span><span class="sxs-lookup"><span data-stu-id="f6532-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f6532-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f6532-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="f6532-111">成员</span><span class="sxs-lookup"><span data-stu-id="f6532-111">Members</span></span>

#### <span data-ttu-id="f6532-112">调用</span><span class="sxs-lookup"><span data-stu-id="f6532-112">Invoke</span></span> 

<span data-ttu-id="f6532-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f6532-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="f6532-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2Host](ICoreWebView2Host.md) \* sender、[ICoreWebView2AcceleratorKeyPressedEventArgs](ICoreWebView2AcceleratorKeyPressedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="f6532-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Host](ICoreWebView2Host.md) \* sender,[ICoreWebView2AcceleratorKeyPressedEventArgs](ICoreWebView2AcceleratorKeyPressedEventArgs.md) \* args)</span></span>

