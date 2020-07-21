---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2ZoomFactorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 22c5e558238e4542ebe70855c3d20837838bebb8
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883957"
---
# <span data-ttu-id="e4539-104">0.9.430-接口 ICoreWebView2ZoomFactorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="e4539-104">0.9.430 - interface ICoreWebView2ZoomFactorChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ZoomFactorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="e4539-105">调用方实现此接口以接收 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="e4539-105">The caller implements this interface to receive ZoomFactorChanged events.</span></span>

## <span data-ttu-id="e4539-106">摘要</span><span class="sxs-lookup"><span data-stu-id="e4539-106">Summary</span></span>

 <span data-ttu-id="e4539-107">成员</span><span class="sxs-lookup"><span data-stu-id="e4539-107">Members</span></span>                        | <span data-ttu-id="e4539-108">描述</span><span class="sxs-lookup"><span data-stu-id="e4539-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e4539-109">调用</span><span class="sxs-lookup"><span data-stu-id="e4539-109">Invoke</span></span>](#invoke) | <span data-ttu-id="e4539-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="e4539-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="e4539-111">使用 ZoomFactor 属性获取修改的缩放系数。 ICoreWebView2Host</span><span class="sxs-lookup"><span data-stu-id="e4539-111">Use the ICoreWebView2Host.ZoomFactor property to get the modified zoom factor.</span></span>

## <span data-ttu-id="e4539-112">成员</span><span class="sxs-lookup"><span data-stu-id="e4539-112">Members</span></span>

#### <span data-ttu-id="e4539-113">调用</span><span class="sxs-lookup"><span data-stu-id="e4539-113">Invoke</span></span> 

<span data-ttu-id="e4539-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="e4539-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="e4539-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2Host](ICoreWebView2Host.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="e4539-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Host](ICoreWebView2Host.md) \* sender,IUnknown \* args)</span></span>

<span data-ttu-id="e4539-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="e4539-116">There are no event args and the args parameter will be null.</span></span>

