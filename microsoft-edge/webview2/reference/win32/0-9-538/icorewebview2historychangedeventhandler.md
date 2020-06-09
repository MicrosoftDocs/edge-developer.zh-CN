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
ms.openlocfilehash: 0f14f8d281d4729d797eb5271a19cff67becafab
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698510"
---
# <span data-ttu-id="88fc7-104">interface ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="88fc7-104">interface ICoreWebView2HistoryChangedEventHandler</span></span> 

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="88fc7-105">调用方实现此接口以接收 HistoryChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="88fc7-105">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="88fc7-106">摘要</span><span class="sxs-lookup"><span data-stu-id="88fc7-106">Summary</span></span>

 <span data-ttu-id="88fc7-107">成员</span><span class="sxs-lookup"><span data-stu-id="88fc7-107">Members</span></span>                        | <span data-ttu-id="88fc7-108">描述</span><span class="sxs-lookup"><span data-stu-id="88fc7-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="88fc7-109">调用</span><span class="sxs-lookup"><span data-stu-id="88fc7-109">Invoke</span></span>](#invoke) | <span data-ttu-id="88fc7-110">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="88fc7-110">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="88fc7-111">成员</span><span class="sxs-lookup"><span data-stu-id="88fc7-111">Members</span></span>

#### <span data-ttu-id="88fc7-112">调用</span><span class="sxs-lookup"><span data-stu-id="88fc7-112">Invoke</span></span> 

<span data-ttu-id="88fc7-113">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="88fc7-113">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="88fc7-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* web 视图、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="88fc7-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, IUnknown \* args)</span></span>

