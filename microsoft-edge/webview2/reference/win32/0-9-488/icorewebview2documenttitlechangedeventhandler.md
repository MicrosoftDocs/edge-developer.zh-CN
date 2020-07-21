---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2DocumentTitleChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 486218dcb54281da559fb5b5f69314248a0d2cad
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883817"
---
# <span data-ttu-id="f688f-104">0.9.515-接口 ICoreWebView2DocumentTitleChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="f688f-104">0.9.515 - interface ICoreWebView2DocumentTitleChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2DocumentTitleChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="f688f-105">调用方实现此接口以接收 DocumentTitleChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="f688f-105">The caller implements this interface to receive DocumentTitleChanged events.</span></span>

## <span data-ttu-id="f688f-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f688f-106">Summary</span></span>

 <span data-ttu-id="f688f-107">成员</span><span class="sxs-lookup"><span data-stu-id="f688f-107">Members</span></span>                        | <span data-ttu-id="f688f-108">描述</span><span class="sxs-lookup"><span data-stu-id="f688f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f688f-109">调用</span><span class="sxs-lookup"><span data-stu-id="f688f-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f688f-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f688f-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="f688f-111">使用 DocumentTitle 属性获取修改后的标题。</span><span class="sxs-lookup"><span data-stu-id="f688f-111">Use the DocumentTitle property to get the modified title.</span></span>

## <span data-ttu-id="f688f-112">成员</span><span class="sxs-lookup"><span data-stu-id="f688f-112">Members</span></span>

#### <span data-ttu-id="f688f-113">调用</span><span class="sxs-lookup"><span data-stu-id="f688f-113">Invoke</span></span> 

<span data-ttu-id="f688f-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f688f-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="f688f-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="f688f-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="f688f-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="f688f-116">There are no event args and the args parameter will be null.</span></span>

