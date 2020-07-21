---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2HistoryChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: e47ca26475ba1b59fa4ea8c87a7aada0d8d6695f
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884132"
---
# <span data-ttu-id="6c8fd-104">0.9.430-接口 ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="6c8fd-104">0.9.430 - interface ICoreWebView2HistoryChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="6c8fd-105">调用方实现此接口以接收 HistoryChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="6c8fd-105">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="6c8fd-106">摘要</span><span class="sxs-lookup"><span data-stu-id="6c8fd-106">Summary</span></span>

 <span data-ttu-id="6c8fd-107">成员</span><span class="sxs-lookup"><span data-stu-id="6c8fd-107">Members</span></span>                        | <span data-ttu-id="6c8fd-108">描述</span><span class="sxs-lookup"><span data-stu-id="6c8fd-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6c8fd-109">调用</span><span class="sxs-lookup"><span data-stu-id="6c8fd-109">Invoke</span></span>](#invoke) | <span data-ttu-id="6c8fd-110">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="6c8fd-110">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="6c8fd-111">成员</span><span class="sxs-lookup"><span data-stu-id="6c8fd-111">Members</span></span>

#### <span data-ttu-id="6c8fd-112">调用</span><span class="sxs-lookup"><span data-stu-id="6c8fd-112">Invoke</span></span> 

<span data-ttu-id="6c8fd-113">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="6c8fd-113">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="6c8fd-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](ICoreWebView2.md) \* web 视图、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="6c8fd-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* webview,IUnknown \* args)</span></span>

