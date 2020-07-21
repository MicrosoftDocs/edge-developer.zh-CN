---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2SourceChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: b3eb56101c6e69bab018cbb549339fd5deb2eb3e
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885189"
---
# <span data-ttu-id="f58e8-104">0.9.515-接口 ICoreWebView2SourceChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="f58e8-104">0.9.515 - interface ICoreWebView2SourceChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2SourceChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="f58e8-105">调用方实现此接口以接收 SourceChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="f58e8-105">The caller implements this interface to receive the SourceChanged event.</span></span>

## <span data-ttu-id="f58e8-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f58e8-106">Summary</span></span>

 <span data-ttu-id="f58e8-107">成员</span><span class="sxs-lookup"><span data-stu-id="f58e8-107">Members</span></span>                        | <span data-ttu-id="f58e8-108">描述</span><span class="sxs-lookup"><span data-stu-id="f58e8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f58e8-109">调用</span><span class="sxs-lookup"><span data-stu-id="f58e8-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f58e8-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f58e8-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="f58e8-111">成员</span><span class="sxs-lookup"><span data-stu-id="f58e8-111">Members</span></span>

#### <span data-ttu-id="f58e8-112">调用</span><span class="sxs-lookup"><span data-stu-id="f58e8-112">Invoke</span></span> 

<span data-ttu-id="f58e8-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f58e8-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="f58e8-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* web 视图， [ICoreWebView2SourceChangedEventArgs](icorewebview2sourcechangedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="f58e8-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, [ICoreWebView2SourceChangedEventArgs](icorewebview2sourcechangedeventargs.md) \* args)</span></span>

