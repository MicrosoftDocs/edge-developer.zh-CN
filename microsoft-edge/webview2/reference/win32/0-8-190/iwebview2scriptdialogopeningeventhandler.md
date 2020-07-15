---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2ScriptDialogOpeningEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 70f1708d7cc908a761e96d14f25e0f1751d1923d
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878216"
---
# <span data-ttu-id="420b2-104">0.8.355-接口 IWebView2ScriptDialogOpeningEventHandler</span><span class="sxs-lookup"><span data-stu-id="420b2-104">0.8.355 - interface IWebView2ScriptDialogOpeningEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="420b2-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="420b2-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="420b2-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="420b2-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2ScriptDialogOpeningEventHandler
  : public IUnknown
```

<span data-ttu-id="420b2-107">调用方实现此接口以接收 ScriptDialogOpening 事件。</span><span class="sxs-lookup"><span data-stu-id="420b2-107">The caller implements this interface to receive the ScriptDialogOpening event.</span></span>

## <span data-ttu-id="420b2-108">摘要</span><span class="sxs-lookup"><span data-stu-id="420b2-108">Summary</span></span>

 <span data-ttu-id="420b2-109">成员</span><span class="sxs-lookup"><span data-stu-id="420b2-109">Members</span></span>                        | <span data-ttu-id="420b2-110">描述</span><span class="sxs-lookup"><span data-stu-id="420b2-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="420b2-111">调用</span><span class="sxs-lookup"><span data-stu-id="420b2-111">Invoke</span></span>](#invoke) | <span data-ttu-id="420b2-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="420b2-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="420b2-113">成员</span><span class="sxs-lookup"><span data-stu-id="420b2-113">Members</span></span>

#### <span data-ttu-id="420b2-114">调用</span><span class="sxs-lookup"><span data-stu-id="420b2-114">Invoke</span></span> 

<span data-ttu-id="420b2-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="420b2-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="420b2-116">公共 HRESULT[调用](#invoke)（[IWebView2WebView](IWebView2WebView.md) \* web 视图，[IWebView2ScriptDialogOpeningEventArgs](IWebView2ScriptDialogOpeningEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="420b2-116">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2ScriptDialogOpeningEventArgs](IWebView2ScriptDialogOpeningEventArgs.md) \* args)</span></span>

