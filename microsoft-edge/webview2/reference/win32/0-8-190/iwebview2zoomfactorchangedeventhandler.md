---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2ZoomFactorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 237179df5ef704fb88516780696f3a9c10c9a198
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884664"
---
# <span data-ttu-id="e2069-104">0.8.355-接口 IWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="e2069-104">0.8.355 - interface IWebView2ZoomFactorChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="e2069-105">调用方实现此接口以接收 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="e2069-105">The caller implements this interface to receive ZoomFactorChanged events.</span></span>

## <span data-ttu-id="e2069-106">摘要</span><span class="sxs-lookup"><span data-stu-id="e2069-106">Summary</span></span>

 <span data-ttu-id="e2069-107">成员</span><span class="sxs-lookup"><span data-stu-id="e2069-107">Members</span></span>                        | <span data-ttu-id="e2069-108">描述</span><span class="sxs-lookup"><span data-stu-id="e2069-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e2069-109">调用</span><span class="sxs-lookup"><span data-stu-id="e2069-109">Invoke</span></span>](#invoke) | <span data-ttu-id="e2069-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="e2069-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="e2069-111">使用 ZoomFactor 属性获取修改的缩放系数。 IWebView2WebView</span><span class="sxs-lookup"><span data-stu-id="e2069-111">Use the IWebView2WebView.ZoomFactor property to get the modified zoom factor.</span></span>

## <span data-ttu-id="e2069-112">成员</span><span class="sxs-lookup"><span data-stu-id="e2069-112">Members</span></span>

#### <span data-ttu-id="e2069-113">调用</span><span class="sxs-lookup"><span data-stu-id="e2069-113">Invoke</span></span> 

<span data-ttu-id="e2069-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="e2069-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="e2069-115">公共 HRESULT[调用](#invoke)（[IWebView2WebView](IWebView2WebView.md) \* web 视图、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="e2069-115">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,IUnknown \* args)</span></span>

<span data-ttu-id="e2069-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="e2069-116">There are no event args and the args parameter will be null.</span></span>

