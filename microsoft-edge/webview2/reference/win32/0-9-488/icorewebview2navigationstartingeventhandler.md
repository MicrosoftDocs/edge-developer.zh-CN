---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2NavigationStartingEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 35ca64bcfdae9d82a2f5b00ef69d36f367e22efe
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884055"
---
# <span data-ttu-id="418b6-104">0.9.515-接口 ICoreWebView2NavigationStartingEventHandler</span><span class="sxs-lookup"><span data-stu-id="418b6-104">0.9.515 - interface ICoreWebView2NavigationStartingEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NavigationStartingEventHandler
  : public IUnknown
```

<span data-ttu-id="418b6-105">调用方实现此接口以接收 NavigationStarting 事件。</span><span class="sxs-lookup"><span data-stu-id="418b6-105">The caller implements this interface to receive the NavigationStarting event.</span></span>

## <span data-ttu-id="418b6-106">摘要</span><span class="sxs-lookup"><span data-stu-id="418b6-106">Summary</span></span>

 <span data-ttu-id="418b6-107">成员</span><span class="sxs-lookup"><span data-stu-id="418b6-107">Members</span></span>                        | <span data-ttu-id="418b6-108">描述</span><span class="sxs-lookup"><span data-stu-id="418b6-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="418b6-109">调用</span><span class="sxs-lookup"><span data-stu-id="418b6-109">Invoke</span></span>](#invoke) | <span data-ttu-id="418b6-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="418b6-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="418b6-111">成员</span><span class="sxs-lookup"><span data-stu-id="418b6-111">Members</span></span>

#### <span data-ttu-id="418b6-112">调用</span><span class="sxs-lookup"><span data-stu-id="418b6-112">Invoke</span></span> 

<span data-ttu-id="418b6-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="418b6-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="418b6-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="418b6-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NavigationStartingEventArgs](icorewebview2navigationstartingeventargs.md) \* args)</span></span>

