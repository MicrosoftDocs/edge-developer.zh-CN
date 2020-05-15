---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 30fc5e258c73b880009bc48e9213c647a5542917
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652980"
---
# <span data-ttu-id="2dc09-104">interface ICoreWebView2ProcessFailedEventHandler</span><span class="sxs-lookup"><span data-stu-id="2dc09-104">interface ICoreWebView2ProcessFailedEventHandler</span></span> 

```
interface ICoreWebView2ProcessFailedEventHandler
  : public IUnknown
```

<span data-ttu-id="2dc09-105">调用方实现此接口以接收 ProcessFailed 事件。</span><span class="sxs-lookup"><span data-stu-id="2dc09-105">The caller implements this interface to receive ProcessFailed events.</span></span>

## <span data-ttu-id="2dc09-106">摘要</span><span class="sxs-lookup"><span data-stu-id="2dc09-106">Summary</span></span>

 <span data-ttu-id="2dc09-107">成员</span><span class="sxs-lookup"><span data-stu-id="2dc09-107">Members</span></span>                        | <span data-ttu-id="2dc09-108">描述</span><span class="sxs-lookup"><span data-stu-id="2dc09-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2dc09-109">调用</span><span class="sxs-lookup"><span data-stu-id="2dc09-109">Invoke</span></span>](#invoke) | <span data-ttu-id="2dc09-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="2dc09-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="2dc09-111">成员</span><span class="sxs-lookup"><span data-stu-id="2dc09-111">Members</span></span>

#### <span data-ttu-id="2dc09-112">调用</span><span class="sxs-lookup"><span data-stu-id="2dc09-112">Invoke</span></span> 

<span data-ttu-id="2dc09-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="2dc09-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="2dc09-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2ProcessFailedEventArgs](icorewebview2processfailedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="2dc09-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ProcessFailedEventArgs](icorewebview2processfailedeventargs.md) \* args)</span></span>

