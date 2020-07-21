---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2FocusChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 5a0c15cf56283c9d2ba71b9f8261288977c6ef39
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885469"
---
# <span data-ttu-id="ad383-104">0.9.515-接口 ICoreWebView2FocusChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="ad383-104">0.9.515 - interface ICoreWebView2FocusChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2FocusChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="ad383-105">调用方实现此方法以接收 GotFocus 和 LostFocus 事件。</span><span class="sxs-lookup"><span data-stu-id="ad383-105">The caller implements this method to receive the GotFocus and LostFocus events.</span></span>

## <span data-ttu-id="ad383-106">摘要</span><span class="sxs-lookup"><span data-stu-id="ad383-106">Summary</span></span>

 <span data-ttu-id="ad383-107">成员</span><span class="sxs-lookup"><span data-stu-id="ad383-107">Members</span></span>                        | <span data-ttu-id="ad383-108">描述</span><span class="sxs-lookup"><span data-stu-id="ad383-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ad383-109">调用</span><span class="sxs-lookup"><span data-stu-id="ad383-109">Invoke</span></span>](#invoke) | <span data-ttu-id="ad383-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="ad383-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="ad383-111">此事件没有事件参数。</span><span class="sxs-lookup"><span data-stu-id="ad383-111">There are no event args for this event.</span></span>

## <span data-ttu-id="ad383-112">成员</span><span class="sxs-lookup"><span data-stu-id="ad383-112">Members</span></span>

#### <span data-ttu-id="ad383-113">调用</span><span class="sxs-lookup"><span data-stu-id="ad383-113">Invoke</span></span> 

<span data-ttu-id="ad383-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="ad383-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="ad383-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="ad383-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="ad383-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="ad383-116">There are no event args and the args parameter will be null.</span></span>

