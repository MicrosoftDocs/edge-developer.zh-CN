---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ContentLoadingEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ContentLoadingEventHandler
ms.openlocfilehash: fb6e3cfabae0116ac746d6e8e5cc03efa0f1c1b6
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877445"
---
# <span data-ttu-id="69695-104">interface ICoreWebView2ContentLoadingEventHandler</span><span class="sxs-lookup"><span data-stu-id="69695-104">interface ICoreWebView2ContentLoadingEventHandler</span></span> 

```
interface ICoreWebView2ContentLoadingEventHandler
  : public IUnknown
```

<span data-ttu-id="69695-105">调用方实现此接口以接收 ContentLoading 事件。</span><span class="sxs-lookup"><span data-stu-id="69695-105">The caller implements this interface to receive the ContentLoading event.</span></span>

## <span data-ttu-id="69695-106">摘要</span><span class="sxs-lookup"><span data-stu-id="69695-106">Summary</span></span>

 <span data-ttu-id="69695-107">成员</span><span class="sxs-lookup"><span data-stu-id="69695-107">Members</span></span>                        | <span data-ttu-id="69695-108">描述</span><span class="sxs-lookup"><span data-stu-id="69695-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="69695-109">调用</span><span class="sxs-lookup"><span data-stu-id="69695-109">Invoke</span></span>](#invoke) | <span data-ttu-id="69695-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="69695-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="69695-111">成员</span><span class="sxs-lookup"><span data-stu-id="69695-111">Members</span></span>

#### <span data-ttu-id="69695-112">调用</span><span class="sxs-lookup"><span data-stu-id="69695-112">Invoke</span></span> 

<span data-ttu-id="69695-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="69695-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="69695-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* web 视图， [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="69695-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) \* args)</span></span>

