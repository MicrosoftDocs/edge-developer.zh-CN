---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2ZoomFactorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: d4e565db43e9f528b690ab32a784bfd5e40f787b
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877285"
---
# <span data-ttu-id="faa08-104">0.9.515-接口 ICoreWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="faa08-104">0.9.515 - interface ICoreWebView2ZoomFactorChangedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="faa08-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="faa08-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="faa08-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="faa08-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="faa08-107">调用方实现此接口以接收 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="faa08-107">The caller implements this interface to receive ZoomFactorChanged events.</span></span>

## <span data-ttu-id="faa08-108">摘要</span><span class="sxs-lookup"><span data-stu-id="faa08-108">Summary</span></span>

 <span data-ttu-id="faa08-109">成员</span><span class="sxs-lookup"><span data-stu-id="faa08-109">Members</span></span>                        | <span data-ttu-id="faa08-110">描述</span><span class="sxs-lookup"><span data-stu-id="faa08-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="faa08-111">调用</span><span class="sxs-lookup"><span data-stu-id="faa08-111">Invoke</span></span>](#invoke) | <span data-ttu-id="faa08-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="faa08-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="faa08-113">使用 ZoomFactor 属性获取修改的缩放系数。 ICoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="faa08-113">Use the ICoreWebView2Controller.ZoomFactor property to get the modified zoom factor.</span></span>

## <span data-ttu-id="faa08-114">成员</span><span class="sxs-lookup"><span data-stu-id="faa08-114">Members</span></span>

#### <span data-ttu-id="faa08-115">调用</span><span class="sxs-lookup"><span data-stu-id="faa08-115">Invoke</span></span> 

<span data-ttu-id="faa08-116">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="faa08-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="faa08-117">公共 HRESULT[调用](#invoke)（[ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="faa08-117">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="faa08-118">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="faa08-118">There are no event args and the args parameter will be null.</span></span>

