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
ms.openlocfilehash: 5b3258ea7d9607d6197e66b18b55b54ecdf82a54
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697173"
---
# <span data-ttu-id="c345e-104">interface ICoreWebView2NavigationCompletedEventHandler</span><span class="sxs-lookup"><span data-stu-id="c345e-104">interface ICoreWebView2NavigationCompletedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="c345e-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="c345e-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="c345e-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="c345e-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationCompletedEventHandler
  : public IUnknown
```

<span data-ttu-id="c345e-107">调用方实现此接口以接收 NavigationCompleted 事件。</span><span class="sxs-lookup"><span data-stu-id="c345e-107">The caller implements this interface to receive the NavigationCompleted event.</span></span>

## <span data-ttu-id="c345e-108">摘要</span><span class="sxs-lookup"><span data-stu-id="c345e-108">Summary</span></span>

 <span data-ttu-id="c345e-109">成员</span><span class="sxs-lookup"><span data-stu-id="c345e-109">Members</span></span>                        | <span data-ttu-id="c345e-110">描述</span><span class="sxs-lookup"><span data-stu-id="c345e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c345e-111">调用</span><span class="sxs-lookup"><span data-stu-id="c345e-111">Invoke</span></span>](#invoke) | <span data-ttu-id="c345e-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="c345e-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="c345e-113">成员</span><span class="sxs-lookup"><span data-stu-id="c345e-113">Members</span></span>

#### <span data-ttu-id="c345e-114">调用</span><span class="sxs-lookup"><span data-stu-id="c345e-114">Invoke</span></span> 

<span data-ttu-id="c345e-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="c345e-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="c345e-116">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="c345e-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationCompletedEventArgs](icorewebview2navigationcompletedeventargs.md) \* args)</span></span>

