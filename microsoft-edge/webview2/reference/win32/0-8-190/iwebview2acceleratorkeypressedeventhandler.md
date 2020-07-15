---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2AcceleratorKeyPressedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 6b5cf77e8091d79b582907b4cbfe7c9aa415de9c
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879063"
---
# <span data-ttu-id="53f84-104">0.8.355-接口 IWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="53f84-104">0.8.355 - interface IWebView2AcceleratorKeyPressedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="53f84-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="53f84-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="53f84-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="53f84-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="53f84-107">调用方实现此接口以接收 AcceleratorKeyPressed 事件。</span><span class="sxs-lookup"><span data-stu-id="53f84-107">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="53f84-108">摘要</span><span class="sxs-lookup"><span data-stu-id="53f84-108">Summary</span></span>

 <span data-ttu-id="53f84-109">成员</span><span class="sxs-lookup"><span data-stu-id="53f84-109">Members</span></span>                        | <span data-ttu-id="53f84-110">描述</span><span class="sxs-lookup"><span data-stu-id="53f84-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="53f84-111">调用</span><span class="sxs-lookup"><span data-stu-id="53f84-111">Invoke</span></span>](#invoke) | <span data-ttu-id="53f84-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="53f84-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="53f84-113">成员</span><span class="sxs-lookup"><span data-stu-id="53f84-113">Members</span></span>

#### <span data-ttu-id="53f84-114">调用</span><span class="sxs-lookup"><span data-stu-id="53f84-114">Invoke</span></span> 

<span data-ttu-id="53f84-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="53f84-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="53f84-116">公共 HRESULT[调用](#invoke)（[IWebView2WebView](IWebView2WebView.md) \* web 视图，[IWebView2AcceleratorKeyPressedEventArgs](IWebView2AcceleratorKeyPressedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="53f84-116">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2AcceleratorKeyPressedEventArgs](IWebView2AcceleratorKeyPressedEventArgs.md) \* args)</span></span>

