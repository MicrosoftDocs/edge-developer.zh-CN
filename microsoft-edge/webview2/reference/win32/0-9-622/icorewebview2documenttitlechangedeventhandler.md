---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2DocumentTitleChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2DocumentTitleChangedEventHandler
ms.openlocfilehash: 9332786935ba79adfd6ef215c9e11afa24c5ceb2
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011619"
---
# <span data-ttu-id="9ea1b-104">interface ICoreWebView2DocumentTitleChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="9ea1b-104">interface ICoreWebView2DocumentTitleChangedEventHandler</span></span> 

```
interface ICoreWebView2DocumentTitleChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="9ea1b-105">调用方实现此接口以接收 DocumentTitleChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="9ea1b-105">The caller implements this interface to receive DocumentTitleChanged events.</span></span>

## <span data-ttu-id="9ea1b-106">摘要</span><span class="sxs-lookup"><span data-stu-id="9ea1b-106">Summary</span></span>

 <span data-ttu-id="9ea1b-107">成员</span><span class="sxs-lookup"><span data-stu-id="9ea1b-107">Members</span></span>                        | <span data-ttu-id="9ea1b-108">描述</span><span class="sxs-lookup"><span data-stu-id="9ea1b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9ea1b-109">调用</span><span class="sxs-lookup"><span data-stu-id="9ea1b-109">Invoke</span></span>](#invoke) | <span data-ttu-id="9ea1b-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="9ea1b-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="9ea1b-111">使用 DocumentTitle 属性获取修改后的标题。</span><span class="sxs-lookup"><span data-stu-id="9ea1b-111">Use the DocumentTitle property to get the modified title.</span></span>

## <span data-ttu-id="9ea1b-112">成员</span><span class="sxs-lookup"><span data-stu-id="9ea1b-112">Members</span></span>

#### <span data-ttu-id="9ea1b-113">调用</span><span class="sxs-lookup"><span data-stu-id="9ea1b-113">Invoke</span></span> 

<span data-ttu-id="9ea1b-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="9ea1b-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="9ea1b-115">公共 HRESULT [调用](#invoke) ([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* 参数) </span><span class="sxs-lookup"><span data-stu-id="9ea1b-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="9ea1b-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="9ea1b-116">There are no event args and the args parameter will be null.</span></span>

