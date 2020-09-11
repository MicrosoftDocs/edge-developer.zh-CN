---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2AcceleratorKeyPressedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2AcceleratorKeyPressedEventHandler
ms.openlocfilehash: 104291f2bbf285737311a205188a1b549906becf
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011214"
---
# <span data-ttu-id="b8462-104">0.9.579-接口 ICoreWebView2AcceleratorKeyPressedEventHandler</span><span class="sxs-lookup"><span data-stu-id="b8462-104">0.9.579 - interface ICoreWebView2AcceleratorKeyPressedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2AcceleratorKeyPressedEventHandler
  : public IUnknown
```

<span data-ttu-id="b8462-105">调用方实现此接口以接收 AcceleratorKeyPressed 事件。</span><span class="sxs-lookup"><span data-stu-id="b8462-105">The caller implements this interface to receive the AcceleratorKeyPressed event.</span></span>

## <span data-ttu-id="b8462-106">摘要</span><span class="sxs-lookup"><span data-stu-id="b8462-106">Summary</span></span>

 <span data-ttu-id="b8462-107">成员</span><span class="sxs-lookup"><span data-stu-id="b8462-107">Members</span></span>                        | <span data-ttu-id="b8462-108">描述</span><span class="sxs-lookup"><span data-stu-id="b8462-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b8462-109">调用</span><span class="sxs-lookup"><span data-stu-id="b8462-109">Invoke</span></span>](#invoke) | <span data-ttu-id="b8462-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="b8462-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="b8462-111">成员</span><span class="sxs-lookup"><span data-stu-id="b8462-111">Members</span></span>

#### <span data-ttu-id="b8462-112">调用</span><span class="sxs-lookup"><span data-stu-id="b8462-112">Invoke</span></span> 

<span data-ttu-id="b8462-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="b8462-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="b8462-114">public HRESULT [调用](#invoke) ([ICoreWebView2Controller](icorewebview2controller.md) \* sender、 [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* 参数) </span><span class="sxs-lookup"><span data-stu-id="b8462-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2AcceleratorKeyPressedEventArgs](icorewebview2acceleratorkeypressedeventargs.md) \* args)</span></span>

