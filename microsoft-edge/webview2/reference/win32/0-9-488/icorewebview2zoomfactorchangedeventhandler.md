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
ms.openlocfilehash: e2469dd9a587735efcf88a48e0ce950cb4f85239
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653094"
---
# <span data-ttu-id="a9822-104">interface ICoreWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="a9822-104">interface ICoreWebView2ZoomFactorChangedEventHandler</span></span> 

```
interface ICoreWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="a9822-105">调用方实现此接口以接收 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="a9822-105">The caller implements this interface to receive ZoomFactorChanged events.</span></span>

## <span data-ttu-id="a9822-106">摘要</span><span class="sxs-lookup"><span data-stu-id="a9822-106">Summary</span></span>

 <span data-ttu-id="a9822-107">成员</span><span class="sxs-lookup"><span data-stu-id="a9822-107">Members</span></span>                        | <span data-ttu-id="a9822-108">描述</span><span class="sxs-lookup"><span data-stu-id="a9822-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a9822-109">调用</span><span class="sxs-lookup"><span data-stu-id="a9822-109">Invoke</span></span>](#invoke) | <span data-ttu-id="a9822-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a9822-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="a9822-111">使用 ZoomFactor 属性获取修改的缩放系数。 ICoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="a9822-111">Use the ICoreWebView2Controller.ZoomFactor property to get the modified zoom factor.</span></span>

## <span data-ttu-id="a9822-112">成员</span><span class="sxs-lookup"><span data-stu-id="a9822-112">Members</span></span>

#### <span data-ttu-id="a9822-113">调用</span><span class="sxs-lookup"><span data-stu-id="a9822-113">Invoke</span></span> 

<span data-ttu-id="a9822-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a9822-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="a9822-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="a9822-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="a9822-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="a9822-116">There are no event args and the args parameter will be null.</span></span>

