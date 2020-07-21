---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2ZoomFactorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 91cd4245ff6c75e72457410211deefd9ab7f09d1
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883691"
---
# <span data-ttu-id="3296b-104">0.9.515-接口 ICoreWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="3296b-104">0.9.515 - interface ICoreWebView2ZoomFactorChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="3296b-105">调用方实现此接口以接收 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="3296b-105">The caller implements this interface to receive ZoomFactorChanged events.</span></span>

## <span data-ttu-id="3296b-106">摘要</span><span class="sxs-lookup"><span data-stu-id="3296b-106">Summary</span></span>

 <span data-ttu-id="3296b-107">成员</span><span class="sxs-lookup"><span data-stu-id="3296b-107">Members</span></span>                        | <span data-ttu-id="3296b-108">描述</span><span class="sxs-lookup"><span data-stu-id="3296b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3296b-109">调用</span><span class="sxs-lookup"><span data-stu-id="3296b-109">Invoke</span></span>](#invoke) | <span data-ttu-id="3296b-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="3296b-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="3296b-111">使用 ZoomFactor 属性获取修改的缩放系数。 ICoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="3296b-111">Use the ICoreWebView2Controller.ZoomFactor property to get the modified zoom factor.</span></span>

## <span data-ttu-id="3296b-112">成员</span><span class="sxs-lookup"><span data-stu-id="3296b-112">Members</span></span>

#### <span data-ttu-id="3296b-113">调用</span><span class="sxs-lookup"><span data-stu-id="3296b-113">Invoke</span></span> 

<span data-ttu-id="3296b-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="3296b-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="3296b-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="3296b-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="3296b-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="3296b-116">There are no event args and the args parameter will be null.</span></span>

