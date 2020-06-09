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
ms.openlocfilehash: 8c717bb57a5dc984d6cb2bbbbac79cf91d64fe2f
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698484"
---
# <span data-ttu-id="07d1c-104">interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="07d1c-104">interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

```
interface ICoreWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="07d1c-105">调用方实现此方法以接收 ContainsFullScreenElementChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="07d1c-105">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="07d1c-106">摘要</span><span class="sxs-lookup"><span data-stu-id="07d1c-106">Summary</span></span>

 <span data-ttu-id="07d1c-107">成员</span><span class="sxs-lookup"><span data-stu-id="07d1c-107">Members</span></span>                        | <span data-ttu-id="07d1c-108">描述</span><span class="sxs-lookup"><span data-stu-id="07d1c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="07d1c-109">调用</span><span class="sxs-lookup"><span data-stu-id="07d1c-109">Invoke</span></span>](#invoke) | <span data-ttu-id="07d1c-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="07d1c-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="07d1c-111">此事件没有事件参数。</span><span class="sxs-lookup"><span data-stu-id="07d1c-111">There are no event args for this event.</span></span>

## <span data-ttu-id="07d1c-112">成员</span><span class="sxs-lookup"><span data-stu-id="07d1c-112">Members</span></span>

#### <span data-ttu-id="07d1c-113">调用</span><span class="sxs-lookup"><span data-stu-id="07d1c-113">Invoke</span></span> 

<span data-ttu-id="07d1c-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="07d1c-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="07d1c-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="07d1c-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="07d1c-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="07d1c-116">There are no event args and the args parameter will be null.</span></span>

