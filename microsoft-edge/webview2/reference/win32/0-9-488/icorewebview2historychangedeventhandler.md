---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2HistoryChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: d90f461f6c2a1e573b0514213ec34f83f0d23366
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885492"
---
# <span data-ttu-id="c6926-104">0.9.515-接口 ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="c6926-104">0.9.515 - interface ICoreWebView2HistoryChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="c6926-105">调用方实现此接口以接收 HistoryChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="c6926-105">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="c6926-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c6926-106">Summary</span></span>

 <span data-ttu-id="c6926-107">成员</span><span class="sxs-lookup"><span data-stu-id="c6926-107">Members</span></span>                        | <span data-ttu-id="c6926-108">描述</span><span class="sxs-lookup"><span data-stu-id="c6926-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c6926-109">调用</span><span class="sxs-lookup"><span data-stu-id="c6926-109">Invoke</span></span>](#invoke) | <span data-ttu-id="c6926-110">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="c6926-110">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="c6926-111">成员</span><span class="sxs-lookup"><span data-stu-id="c6926-111">Members</span></span>

#### <span data-ttu-id="c6926-112">调用</span><span class="sxs-lookup"><span data-stu-id="c6926-112">Invoke</span></span> 

<span data-ttu-id="c6926-113">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="c6926-113">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="c6926-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* web 视图、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="c6926-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, IUnknown \* args)</span></span>

