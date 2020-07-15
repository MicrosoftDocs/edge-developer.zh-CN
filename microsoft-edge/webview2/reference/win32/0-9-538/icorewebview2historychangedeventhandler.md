---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2HistoryChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2HistoryChangedEventHandler
ms.openlocfilehash: cf9d04c14f39a9ba1686d5cc9b002041313b645d
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879910"
---
# <span data-ttu-id="679a8-104">interface ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="679a8-104">interface ICoreWebView2HistoryChangedEventHandler</span></span> 

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="679a8-105">调用方实现此接口以接收 HistoryChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="679a8-105">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="679a8-106">摘要</span><span class="sxs-lookup"><span data-stu-id="679a8-106">Summary</span></span>

 <span data-ttu-id="679a8-107">成员</span><span class="sxs-lookup"><span data-stu-id="679a8-107">Members</span></span>                        | <span data-ttu-id="679a8-108">描述</span><span class="sxs-lookup"><span data-stu-id="679a8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="679a8-109">调用</span><span class="sxs-lookup"><span data-stu-id="679a8-109">Invoke</span></span>](#invoke) | <span data-ttu-id="679a8-110">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="679a8-110">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="679a8-111">成员</span><span class="sxs-lookup"><span data-stu-id="679a8-111">Members</span></span>

#### <span data-ttu-id="679a8-112">调用</span><span class="sxs-lookup"><span data-stu-id="679a8-112">Invoke</span></span> 

<span data-ttu-id="679a8-113">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="679a8-113">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="679a8-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* web 视图、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="679a8-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, IUnknown \* args)</span></span>

