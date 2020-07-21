---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2DocumentStateChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 3d6bf8345e88dde213c15e51c26056d0239f0230
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886107"
---
# <span data-ttu-id="2c22e-104">0.8.355-接口 IWebView2DocumentStateChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="2c22e-104">0.8.355 - interface IWebView2DocumentStateChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2DocumentStateChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="2c22e-105">调用方实现此接口以接收 DocumentStateChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="2c22e-105">The caller implements this interface to receive the DocumentStateChanged event.</span></span>

## <span data-ttu-id="2c22e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="2c22e-106">Summary</span></span>

 <span data-ttu-id="2c22e-107">成员</span><span class="sxs-lookup"><span data-stu-id="2c22e-107">Members</span></span>                        | <span data-ttu-id="2c22e-108">描述</span><span class="sxs-lookup"><span data-stu-id="2c22e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2c22e-109">调用</span><span class="sxs-lookup"><span data-stu-id="2c22e-109">Invoke</span></span>](#invoke) | <span data-ttu-id="2c22e-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="2c22e-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="2c22e-111">成员</span><span class="sxs-lookup"><span data-stu-id="2c22e-111">Members</span></span>

#### <span data-ttu-id="2c22e-112">调用</span><span class="sxs-lookup"><span data-stu-id="2c22e-112">Invoke</span></span> 

<span data-ttu-id="2c22e-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="2c22e-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="2c22e-114">公共 HRESULT[调用](#invoke)（[IWebView2WebView](IWebView2WebView.md) \* web 视图，[IWebView2DocumentStateChangedEventArgs](IWebView2DocumentStateChangedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="2c22e-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2DocumentStateChangedEventArgs](IWebView2DocumentStateChangedEventArgs.md) \* args)</span></span>

