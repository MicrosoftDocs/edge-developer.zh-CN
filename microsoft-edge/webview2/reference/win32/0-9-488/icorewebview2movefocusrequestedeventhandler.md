---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: ac2f17c621dc6ad5093bacac685e01688a663cb1
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697950"
---
# <span data-ttu-id="a40ab-104">interface ICoreWebView2MoveFocusRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="a40ab-104">interface ICoreWebView2MoveFocusRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="a40ab-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="a40ab-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="a40ab-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="a40ab-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2MoveFocusRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="a40ab-107">调用方实现此方法以接收 MoveFocusRequested 事件。</span><span class="sxs-lookup"><span data-stu-id="a40ab-107">The caller implements this method to receive the MoveFocusRequested event.</span></span>

## <span data-ttu-id="a40ab-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a40ab-108">Summary</span></span>

 <span data-ttu-id="a40ab-109">成员</span><span class="sxs-lookup"><span data-stu-id="a40ab-109">Members</span></span>                        | <span data-ttu-id="a40ab-110">描述</span><span class="sxs-lookup"><span data-stu-id="a40ab-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a40ab-111">调用</span><span class="sxs-lookup"><span data-stu-id="a40ab-111">Invoke</span></span>](#invoke) | <span data-ttu-id="a40ab-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a40ab-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="a40ab-113">成员</span><span class="sxs-lookup"><span data-stu-id="a40ab-113">Members</span></span>

#### <span data-ttu-id="a40ab-114">调用</span><span class="sxs-lookup"><span data-stu-id="a40ab-114">Invoke</span></span> 

<span data-ttu-id="a40ab-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a40ab-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="a40ab-116">公共 HRESULT[调用](#invoke)（[ICoreWebView2Controller](icorewebview2controller.md) \* sender、 [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="a40ab-116">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* args)</span></span>

