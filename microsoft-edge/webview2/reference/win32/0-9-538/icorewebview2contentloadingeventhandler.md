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
ms.openlocfilehash: 8bf8dcf40524425a7ef166c5007d60de738efb67
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698480"
---
# <span data-ttu-id="25f9d-104">interface ICoreWebView2ContentLoadingEventHandler</span><span class="sxs-lookup"><span data-stu-id="25f9d-104">interface ICoreWebView2ContentLoadingEventHandler</span></span> 

```
interface ICoreWebView2ContentLoadingEventHandler
  : public IUnknown
```

<span data-ttu-id="25f9d-105">调用方实现此接口以接收 ContentLoading 事件。</span><span class="sxs-lookup"><span data-stu-id="25f9d-105">The caller implements this interface to receive the ContentLoading event.</span></span>

## <span data-ttu-id="25f9d-106">摘要</span><span class="sxs-lookup"><span data-stu-id="25f9d-106">Summary</span></span>

 <span data-ttu-id="25f9d-107">成员</span><span class="sxs-lookup"><span data-stu-id="25f9d-107">Members</span></span>                        | <span data-ttu-id="25f9d-108">描述</span><span class="sxs-lookup"><span data-stu-id="25f9d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="25f9d-109">调用</span><span class="sxs-lookup"><span data-stu-id="25f9d-109">Invoke</span></span>](#invoke) | <span data-ttu-id="25f9d-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="25f9d-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="25f9d-111">成员</span><span class="sxs-lookup"><span data-stu-id="25f9d-111">Members</span></span>

#### <span data-ttu-id="25f9d-112">调用</span><span class="sxs-lookup"><span data-stu-id="25f9d-112">Invoke</span></span> 

<span data-ttu-id="25f9d-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="25f9d-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="25f9d-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* web 视图， [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="25f9d-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* webview, [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) \* args)</span></span>

