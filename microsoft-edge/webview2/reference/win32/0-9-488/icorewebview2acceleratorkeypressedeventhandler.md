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
ms.openlocfilehash: 5cbf358780d196168976fc0812c9845d0ec59b24
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652916"
---
# <span data-ttu-id="5f894-104">interface ICoreWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="5f894-104">interface ICoreWebView2AcceleratorKeyPressedEventHandler</span></span> 

```
interface ICoreWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="5f894-105">调用方实现此接口以接收 AcceleratorKeyPressed 事件。</span><span class="sxs-lookup"><span data-stu-id="5f894-105">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="5f894-106">摘要</span><span class="sxs-lookup"><span data-stu-id="5f894-106">Summary</span></span>

 <span data-ttu-id="5f894-107">成员</span><span class="sxs-lookup"><span data-stu-id="5f894-107">Members</span></span>                        | <span data-ttu-id="5f894-108">描述</span><span class="sxs-lookup"><span data-stu-id="5f894-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5f894-109">调用</span><span class="sxs-lookup"><span data-stu-id="5f894-109">Invoke</span></span>](#invoke) | <span data-ttu-id="5f894-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="5f894-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="5f894-111">成员</span><span class="sxs-lookup"><span data-stu-id="5f894-111">Members</span></span>

#### <span data-ttu-id="5f894-112">调用</span><span class="sxs-lookup"><span data-stu-id="5f894-112">Invoke</span></span> 

<span data-ttu-id="5f894-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="5f894-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="5f894-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2Controller](icorewebview2controller.md) \* sender、 [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="5f894-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span></span>

