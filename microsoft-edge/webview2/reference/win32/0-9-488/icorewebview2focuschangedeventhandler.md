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
ms.openlocfilehash: e80dca6411534968822d9994f9911828a4fddeeb
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653031"
---
# <span data-ttu-id="13b90-104">interface ICoreWebView2FocusChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="13b90-104">interface ICoreWebView2FocusChangedEventHandler</span></span> 

```
interface ICoreWebView2FocusChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="13b90-105">调用方实现此方法以接收 GotFocus 和 LostFocus 事件。</span><span class="sxs-lookup"><span data-stu-id="13b90-105">The caller implements this method to receive the GotFocus and LostFocus events.</span></span>

## <span data-ttu-id="13b90-106">摘要</span><span class="sxs-lookup"><span data-stu-id="13b90-106">Summary</span></span>

 <span data-ttu-id="13b90-107">成员</span><span class="sxs-lookup"><span data-stu-id="13b90-107">Members</span></span>                        | <span data-ttu-id="13b90-108">描述</span><span class="sxs-lookup"><span data-stu-id="13b90-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="13b90-109">调用</span><span class="sxs-lookup"><span data-stu-id="13b90-109">Invoke</span></span>](#invoke) | <span data-ttu-id="13b90-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="13b90-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="13b90-111">此事件没有事件参数。</span><span class="sxs-lookup"><span data-stu-id="13b90-111">There are no event args for this event.</span></span>

## <span data-ttu-id="13b90-112">成员</span><span class="sxs-lookup"><span data-stu-id="13b90-112">Members</span></span>

#### <span data-ttu-id="13b90-113">调用</span><span class="sxs-lookup"><span data-stu-id="13b90-113">Invoke</span></span> 

<span data-ttu-id="13b90-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="13b90-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="13b90-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="13b90-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="13b90-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="13b90-116">There are no event args and the args parameter will be null.</span></span>

