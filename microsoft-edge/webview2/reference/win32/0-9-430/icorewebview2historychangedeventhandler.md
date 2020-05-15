---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 8fd3533d8f479866989f719be6e48c437fae4ddb
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653151"
---
# <span data-ttu-id="b10dd-104">interface ICoreWebView2HistoryChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="b10dd-104">interface ICoreWebView2HistoryChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="b10dd-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="b10dd-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="b10dd-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="b10dd-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="b10dd-107">调用方实现此接口以接收 HistoryChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="b10dd-107">The caller implements this interface to receive the HistoryChanged event.</span></span>

## <span data-ttu-id="b10dd-108">摘要</span><span class="sxs-lookup"><span data-stu-id="b10dd-108">Summary</span></span>

 <span data-ttu-id="b10dd-109">成员</span><span class="sxs-lookup"><span data-stu-id="b10dd-109">Members</span></span>                        | <span data-ttu-id="b10dd-110">描述</span><span class="sxs-lookup"><span data-stu-id="b10dd-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b10dd-111">调用</span><span class="sxs-lookup"><span data-stu-id="b10dd-111">Invoke</span></span>](#invoke) | <span data-ttu-id="b10dd-112">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="b10dd-112">There are no event args and the args parameter will be null.</span></span>

## <span data-ttu-id="b10dd-113">成员</span><span class="sxs-lookup"><span data-stu-id="b10dd-113">Members</span></span>

#### <span data-ttu-id="b10dd-114">调用</span><span class="sxs-lookup"><span data-stu-id="b10dd-114">Invoke</span></span> 

<span data-ttu-id="b10dd-115">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="b10dd-115">There are no event args and the args parameter will be null.</span></span>

> <span data-ttu-id="b10dd-116">公共 HRESULT[调用](#invoke)（[ICoreWebView2](ICoreWebView2.md) \* web 视图、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="b10dd-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* webview,IUnknown \* args)</span></span>
