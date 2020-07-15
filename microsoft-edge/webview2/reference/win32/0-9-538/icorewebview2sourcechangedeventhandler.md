---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2SourceChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2SourceChangedEventHandler
ms.openlocfilehash: b856211b8a4b4088acc741d4d5626b49340124d1
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879329"
---
# <span data-ttu-id="7fe8e-104">interface ICoreWebView2SourceChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="7fe8e-104">interface ICoreWebView2SourceChangedEventHandler</span></span> 

```
interface ICoreWebView2SourceChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="7fe8e-105">调用方实现此接口以接收 SourceChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="7fe8e-105">The caller implements this interface to receive the SourceChanged event.</span></span>

## <span data-ttu-id="7fe8e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="7fe8e-106">Summary</span></span>

 <span data-ttu-id="7fe8e-107">成员</span><span class="sxs-lookup"><span data-stu-id="7fe8e-107">Members</span></span>                        | <span data-ttu-id="7fe8e-108">描述</span><span class="sxs-lookup"><span data-stu-id="7fe8e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7fe8e-109">调用</span><span class="sxs-lookup"><span data-stu-id="7fe8e-109">Invoke</span></span>](#invoke) | <span data-ttu-id="7fe8e-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="7fe8e-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="7fe8e-111">成员</span><span class="sxs-lookup"><span data-stu-id="7fe8e-111">Members</span></span>

#### <span data-ttu-id="7fe8e-112">调用</span><span class="sxs-lookup"><span data-stu-id="7fe8e-112">Invoke</span></span> 

<span data-ttu-id="7fe8e-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="7fe8e-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="7fe8e-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* web 视图， [ICoreWebView2SourceChangedEventArgs](icorewebview2sourcechangedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="7fe8e-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, [ICoreWebView2SourceChangedEventArgs](icorewebview2sourcechangedeventargs.md) \* args)</span></span>

