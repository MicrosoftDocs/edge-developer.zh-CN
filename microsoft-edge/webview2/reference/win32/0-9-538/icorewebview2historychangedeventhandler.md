---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2HistoryChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2HistoryChangedEventHandler
ms.openlocfilehash: 68cecdec63e64bde978156f17d6755a483abcc66
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011340"
---
# <span data-ttu-id="92df6-104">0.9.579-接口 ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="92df6-104">0.9.579 - interface ICoreWebView2HistoryChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="92df6-105">调用方实现此接口以接收 HistoryChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="92df6-105">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="92df6-106">摘要</span><span class="sxs-lookup"><span data-stu-id="92df6-106">Summary</span></span>

 <span data-ttu-id="92df6-107">成员</span><span class="sxs-lookup"><span data-stu-id="92df6-107">Members</span></span>                        | <span data-ttu-id="92df6-108">描述</span><span class="sxs-lookup"><span data-stu-id="92df6-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="92df6-109">调用</span><span class="sxs-lookup"><span data-stu-id="92df6-109">Invoke</span></span>](#invoke) | <span data-ttu-id="92df6-110">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="92df6-110">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="92df6-111">成员</span><span class="sxs-lookup"><span data-stu-id="92df6-111">Members</span></span>

#### <span data-ttu-id="92df6-112">调用</span><span class="sxs-lookup"><span data-stu-id="92df6-112">Invoke</span></span> 

<span data-ttu-id="92df6-113">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="92df6-113">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="92df6-114">public HRESULT [Invoke](#invoke) ([ICoreWebView2](icorewebview2.md) \* web 视图，IUnknown \* 参数) </span><span class="sxs-lookup"><span data-stu-id="92df6-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, IUnknown \* args)</span></span>

