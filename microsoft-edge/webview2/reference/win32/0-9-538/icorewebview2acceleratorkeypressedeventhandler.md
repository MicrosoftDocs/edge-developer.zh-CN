---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2AcceleratorKeyPressedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2AcceleratorKeyPressedEventHandler
ms.openlocfilehash: 26bbc2a5c55ebe5a9b7519a87b01c4dd17af375c
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879560"
---
# <span data-ttu-id="31ae0-104">interface ICoreWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="31ae0-104">interface ICoreWebView2AcceleratorKeyPressedEventHandler</span></span> 

```
interface ICoreWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="31ae0-105">调用方实现此接口以接收 AcceleratorKeyPressed 事件。</span><span class="sxs-lookup"><span data-stu-id="31ae0-105">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="31ae0-106">摘要</span><span class="sxs-lookup"><span data-stu-id="31ae0-106">Summary</span></span>

 <span data-ttu-id="31ae0-107">成员</span><span class="sxs-lookup"><span data-stu-id="31ae0-107">Members</span></span>                        | <span data-ttu-id="31ae0-108">描述</span><span class="sxs-lookup"><span data-stu-id="31ae0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="31ae0-109">调用</span><span class="sxs-lookup"><span data-stu-id="31ae0-109">Invoke</span></span>](#invoke) | <span data-ttu-id="31ae0-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="31ae0-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="31ae0-111">成员</span><span class="sxs-lookup"><span data-stu-id="31ae0-111">Members</span></span>

#### <span data-ttu-id="31ae0-112">调用</span><span class="sxs-lookup"><span data-stu-id="31ae0-112">Invoke</span></span> 

<span data-ttu-id="31ae0-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="31ae0-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="31ae0-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2Controller](icorewebview2controller.md) \* sender、 [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="31ae0-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span></span>

