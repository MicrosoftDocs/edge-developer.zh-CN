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
ms.openlocfilehash: 5f568c10f98a5375ffb0d0444b2b74b8a4e8c4c2
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697208"
---
# <span data-ttu-id="9ed10-104">interface ICoreWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="9ed10-104">interface ICoreWebView2AcceleratorKeyPressedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="9ed10-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="9ed10-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="9ed10-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="9ed10-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="9ed10-107">调用方实现此接口以接收 AcceleratorKeyPressed 事件。</span><span class="sxs-lookup"><span data-stu-id="9ed10-107">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="9ed10-108">摘要</span><span class="sxs-lookup"><span data-stu-id="9ed10-108">Summary</span></span>

 <span data-ttu-id="9ed10-109">成员</span><span class="sxs-lookup"><span data-stu-id="9ed10-109">Members</span></span>                        | <span data-ttu-id="9ed10-110">描述</span><span class="sxs-lookup"><span data-stu-id="9ed10-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9ed10-111">调用</span><span class="sxs-lookup"><span data-stu-id="9ed10-111">Invoke</span></span>](#invoke) | <span data-ttu-id="9ed10-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="9ed10-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="9ed10-113">成员</span><span class="sxs-lookup"><span data-stu-id="9ed10-113">Members</span></span>

#### <span data-ttu-id="9ed10-114">调用</span><span class="sxs-lookup"><span data-stu-id="9ed10-114">Invoke</span></span> 

<span data-ttu-id="9ed10-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="9ed10-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="9ed10-116">公共 HRESULT[调用](#invoke)（[ICoreWebView2Controller](icorewebview2controller.md) \* sender、 [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="9ed10-116">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span></span>

