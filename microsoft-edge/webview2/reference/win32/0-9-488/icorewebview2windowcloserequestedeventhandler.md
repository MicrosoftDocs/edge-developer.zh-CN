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
ms.openlocfilehash: 8d464202e224647c02953312810475b2755c530b
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698111"
---
# <span data-ttu-id="509f1-104">interface ICoreWebView2WindowCloseRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="509f1-104">interface ICoreWebView2WindowCloseRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="509f1-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="509f1-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="509f1-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="509f1-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WindowCloseRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="509f1-107">调用方实现此接口以接收 Webview.newwindowrequested 事件。</span><span class="sxs-lookup"><span data-stu-id="509f1-107">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="509f1-108">摘要</span><span class="sxs-lookup"><span data-stu-id="509f1-108">Summary</span></span>

 <span data-ttu-id="509f1-109">成员</span><span class="sxs-lookup"><span data-stu-id="509f1-109">Members</span></span>                        | <span data-ttu-id="509f1-110">描述</span><span class="sxs-lookup"><span data-stu-id="509f1-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="509f1-111">调用</span><span class="sxs-lookup"><span data-stu-id="509f1-111">Invoke</span></span>](#invoke) | <span data-ttu-id="509f1-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="509f1-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="509f1-113">成员</span><span class="sxs-lookup"><span data-stu-id="509f1-113">Members</span></span>

#### <span data-ttu-id="509f1-114">调用</span><span class="sxs-lookup"><span data-stu-id="509f1-114">Invoke</span></span> 

<span data-ttu-id="509f1-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="509f1-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="509f1-116">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="509f1-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="509f1-117">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="509f1-117">There are no event args and the args parameter will be null.</span></span>

