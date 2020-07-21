---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2ContainsFullScreenElementChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: b1d0bf7ea5f472d5a1c3682c2cbef564947ee54b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886183"
---
# <span data-ttu-id="07c47-104">0.8.355-接口 IWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="07c47-104">0.8.355 - interface IWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="07c47-105">调用方实现此方法以接收 ContainsFullScreenElementChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="07c47-105">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="07c47-106">摘要</span><span class="sxs-lookup"><span data-stu-id="07c47-106">Summary</span></span>

 <span data-ttu-id="07c47-107">成员</span><span class="sxs-lookup"><span data-stu-id="07c47-107">Members</span></span>                        | <span data-ttu-id="07c47-108">描述</span><span class="sxs-lookup"><span data-stu-id="07c47-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="07c47-109">调用</span><span class="sxs-lookup"><span data-stu-id="07c47-109">Invoke</span></span>](#invoke) | <span data-ttu-id="07c47-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="07c47-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="07c47-111">此事件没有事件参数。</span><span class="sxs-lookup"><span data-stu-id="07c47-111">There are no event args for this event.</span></span>

## <span data-ttu-id="07c47-112">成员</span><span class="sxs-lookup"><span data-stu-id="07c47-112">Members</span></span>

#### <span data-ttu-id="07c47-113">调用</span><span class="sxs-lookup"><span data-stu-id="07c47-113">Invoke</span></span> 

<span data-ttu-id="07c47-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="07c47-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="07c47-115">公共 HRESULT[调用](#invoke)（[IWebView2WebView5](IWebView2WebView5.md) \* web 视图、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="07c47-115">public HRESULT [Invoke](#invoke)([IWebView2WebView5](IWebView2WebView5.md) \* webview,IUnknown \* args)</span></span>

<span data-ttu-id="07c47-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="07c47-116">There are no event args and the args parameter will be null.</span></span>

