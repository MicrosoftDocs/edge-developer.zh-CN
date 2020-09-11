---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2ZoomFactorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ZoomFactorChangedEventHandler
ms.openlocfilehash: c941629ab8ee87c0c964b00798878bb69265669a
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011389"
---
# <span data-ttu-id="c6d69-104">0.9.579-接口 ICoreWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="c6d69-104">0.9.579 - interface ICoreWebView2ZoomFactorChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="c6d69-105">调用方实现此接口以接收 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="c6d69-105">The caller implements this interface to receive ZoomFactorChanged events.</span></span>

## <span data-ttu-id="c6d69-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c6d69-106">Summary</span></span>

 <span data-ttu-id="c6d69-107">成员</span><span class="sxs-lookup"><span data-stu-id="c6d69-107">Members</span></span>                        | <span data-ttu-id="c6d69-108">描述</span><span class="sxs-lookup"><span data-stu-id="c6d69-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c6d69-109">调用</span><span class="sxs-lookup"><span data-stu-id="c6d69-109">Invoke</span></span>](#invoke) | <span data-ttu-id="c6d69-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="c6d69-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="c6d69-111">使用 ZoomFactor 属性获取修改的缩放系数。 ICoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="c6d69-111">Use the ICoreWebView2Controller.ZoomFactor property to get the modified zoom factor.</span></span>

## <span data-ttu-id="c6d69-112">成员</span><span class="sxs-lookup"><span data-stu-id="c6d69-112">Members</span></span>

#### <span data-ttu-id="c6d69-113">调用</span><span class="sxs-lookup"><span data-stu-id="c6d69-113">Invoke</span></span> 

<span data-ttu-id="c6d69-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="c6d69-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="c6d69-115">公共 HRESULT [调用](#invoke) ([ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* 参数) </span><span class="sxs-lookup"><span data-stu-id="c6d69-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="c6d69-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="c6d69-116">There are no event args and the args parameter will be null.</span></span>

