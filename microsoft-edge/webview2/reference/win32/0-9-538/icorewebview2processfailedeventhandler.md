---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 2c109e02de28101c88ea55d849db5701f36795a9
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698438"
---
# <span data-ttu-id="f70e1-104">interface ICoreWebView2ProcessFailedEventHandler</span><span class="sxs-lookup"><span data-stu-id="f70e1-104">interface ICoreWebView2ProcessFailedEventHandler</span></span> 

```
interface ICoreWebView2ProcessFailedEventHandler
  : public IUnknown
```

<span data-ttu-id="f70e1-105">调用方实现此接口以接收 ProcessFailed 事件。</span><span class="sxs-lookup"><span data-stu-id="f70e1-105">The caller implements this interface to receive ProcessFailed events.</span></span>

## <span data-ttu-id="f70e1-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f70e1-106">Summary</span></span>

 <span data-ttu-id="f70e1-107">成员</span><span class="sxs-lookup"><span data-stu-id="f70e1-107">Members</span></span>                        | <span data-ttu-id="f70e1-108">描述</span><span class="sxs-lookup"><span data-stu-id="f70e1-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f70e1-109">调用</span><span class="sxs-lookup"><span data-stu-id="f70e1-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f70e1-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f70e1-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="f70e1-111">成员</span><span class="sxs-lookup"><span data-stu-id="f70e1-111">Members</span></span>

#### <span data-ttu-id="f70e1-112">调用</span><span class="sxs-lookup"><span data-stu-id="f70e1-112">Invoke</span></span> 

<span data-ttu-id="f70e1-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f70e1-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="f70e1-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2ProcessFailedEventArgs](icorewebview2processfailedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="f70e1-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ProcessFailedEventArgs](icorewebview2processfailedeventargs.md) \* args)</span></span>

