---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 6fc29b620df5bcd265a7576e4b7ca1c7ebd73e6f
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698518"
---
# <span data-ttu-id="c2e53-104">interface ICoreWebView2FocusChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="c2e53-104">interface ICoreWebView2FocusChangedEventHandler</span></span> 

```
interface ICoreWebView2FocusChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="c2e53-105">调用方实现此方法以接收 GotFocus 和 LostFocus 事件。</span><span class="sxs-lookup"><span data-stu-id="c2e53-105">The caller implements this method to receive the GotFocus and LostFocus events.</span></span>

## <span data-ttu-id="c2e53-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c2e53-106">Summary</span></span>

 <span data-ttu-id="c2e53-107">成员</span><span class="sxs-lookup"><span data-stu-id="c2e53-107">Members</span></span>                        | <span data-ttu-id="c2e53-108">描述</span><span class="sxs-lookup"><span data-stu-id="c2e53-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c2e53-109">调用</span><span class="sxs-lookup"><span data-stu-id="c2e53-109">Invoke</span></span>](#invoke) | <span data-ttu-id="c2e53-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="c2e53-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="c2e53-111">此事件没有事件参数。</span><span class="sxs-lookup"><span data-stu-id="c2e53-111">There are no event args for this event.</span></span>

## <span data-ttu-id="c2e53-112">成员</span><span class="sxs-lookup"><span data-stu-id="c2e53-112">Members</span></span>

#### <span data-ttu-id="c2e53-113">调用</span><span class="sxs-lookup"><span data-stu-id="c2e53-113">Invoke</span></span> 

<span data-ttu-id="c2e53-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="c2e53-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="c2e53-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="c2e53-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="c2e53-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="c2e53-116">There are no event args and the args parameter will be null.</span></span>

