---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2ZoomFactorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: a9da2d5ff7d6bef2c49b0f78d6628157fb8ef80c
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877726"
---
# <span data-ttu-id="2db0b-104">0.9.430-接口 ICoreWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="2db0b-104">0.9.430 - interface ICoreWebView2ZoomFactorChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="2db0b-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="2db0b-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="2db0b-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="2db0b-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="2db0b-107">调用方实现此接口以接收 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="2db0b-107">The caller implements this interface to receive ZoomFactorChanged events.</span></span>

## <span data-ttu-id="2db0b-108">摘要</span><span class="sxs-lookup"><span data-stu-id="2db0b-108">Summary</span></span>

 <span data-ttu-id="2db0b-109">成员</span><span class="sxs-lookup"><span data-stu-id="2db0b-109">Members</span></span>                        | <span data-ttu-id="2db0b-110">描述</span><span class="sxs-lookup"><span data-stu-id="2db0b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2db0b-111">调用</span><span class="sxs-lookup"><span data-stu-id="2db0b-111">Invoke</span></span>](#invoke) | <span data-ttu-id="2db0b-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="2db0b-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="2db0b-113">使用 ZoomFactor 属性获取修改的缩放系数。 ICoreWebView2Host</span><span class="sxs-lookup"><span data-stu-id="2db0b-113">Use the ICoreWebView2Host.ZoomFactor property to get the modified zoom factor.</span></span>

## <span data-ttu-id="2db0b-114">成员</span><span class="sxs-lookup"><span data-stu-id="2db0b-114">Members</span></span>

#### <span data-ttu-id="2db0b-115">调用</span><span class="sxs-lookup"><span data-stu-id="2db0b-115">Invoke</span></span> 

<span data-ttu-id="2db0b-116">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="2db0b-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="2db0b-117">公共 HRESULT[调用](#invoke)（[ICoreWebView2Host](ICoreWebView2Host.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="2db0b-117">public HRESULT [Invoke](#invoke)([ICoreWebView2Host](ICoreWebView2Host.md) \* sender,IUnknown \* args)</span></span>

<span data-ttu-id="2db0b-118">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="2db0b-118">There are no event args and the args parameter will be null.</span></span>

