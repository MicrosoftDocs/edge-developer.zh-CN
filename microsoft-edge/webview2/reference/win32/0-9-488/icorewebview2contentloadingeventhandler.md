---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2ContentLoadingEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 53410d7592f6a217ffd72e410d46491c78262f87
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883866"
---
# <span data-ttu-id="91b1e-104">0.9.515-接口 ICoreWebView2ContentLoadingEventHandler</span><span class="sxs-lookup"><span data-stu-id="91b1e-104">0.9.515 - interface ICoreWebView2ContentLoadingEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ContentLoadingEventHandler
  : public IUnknown
```

<span data-ttu-id="91b1e-105">调用方实现此接口以接收 ContentLoading 事件。</span><span class="sxs-lookup"><span data-stu-id="91b1e-105">The caller implements this interface to receive the ContentLoading event.</span></span>

## <span data-ttu-id="91b1e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="91b1e-106">Summary</span></span>

 <span data-ttu-id="91b1e-107">成员</span><span class="sxs-lookup"><span data-stu-id="91b1e-107">Members</span></span>                        | <span data-ttu-id="91b1e-108">描述</span><span class="sxs-lookup"><span data-stu-id="91b1e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="91b1e-109">调用</span><span class="sxs-lookup"><span data-stu-id="91b1e-109">Invoke</span></span>](#invoke) | <span data-ttu-id="91b1e-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="91b1e-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="91b1e-111">成员</span><span class="sxs-lookup"><span data-stu-id="91b1e-111">Members</span></span>

#### <span data-ttu-id="91b1e-112">调用</span><span class="sxs-lookup"><span data-stu-id="91b1e-112">Invoke</span></span> 

<span data-ttu-id="91b1e-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="91b1e-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="91b1e-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* web 视图， [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="91b1e-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) \* args)</span></span>

