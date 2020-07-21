---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExperimentalCursorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalCursorChangedEventHandler
ms.openlocfilehash: 67d0e6e05fb3640e141ec1ae7193746a1200bbd0
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884881"
---
# <span data-ttu-id="13dd8-104">interface ICoreWebView2ExperimentalCursorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="13dd8-104">interface ICoreWebView2ExperimentalCursorChangedEventHandler</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCursorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="13dd8-105">调用方实现此接口以接收 CursorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="13dd8-105">The caller implements this interface to receive CursorChanged events.</span></span>

## <span data-ttu-id="13dd8-106">摘要</span><span class="sxs-lookup"><span data-stu-id="13dd8-106">Summary</span></span>

 <span data-ttu-id="13dd8-107">成员</span><span class="sxs-lookup"><span data-stu-id="13dd8-107">Members</span></span>                        | <span data-ttu-id="13dd8-108">描述</span><span class="sxs-lookup"><span data-stu-id="13dd8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="13dd8-109">调用</span><span class="sxs-lookup"><span data-stu-id="13dd8-109">Invoke</span></span>](#invoke) | <span data-ttu-id="13dd8-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="13dd8-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="13dd8-111">使用 Cursor 属性获取新光标。</span><span class="sxs-lookup"><span data-stu-id="13dd8-111">Use the Cursor property to get the new cursor.</span></span>

## <span data-ttu-id="13dd8-112">成员</span><span class="sxs-lookup"><span data-stu-id="13dd8-112">Members</span></span>

#### <span data-ttu-id="13dd8-113">调用</span><span class="sxs-lookup"><span data-stu-id="13dd8-113">Invoke</span></span> 

<span data-ttu-id="13dd8-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="13dd8-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="13dd8-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="13dd8-115">public HRESULT [Invoke](#invoke)([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="13dd8-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="13dd8-116">There are no event args and the args parameter will be null.</span></span>

