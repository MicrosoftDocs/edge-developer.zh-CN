---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExperimentalNewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalNewWindowRequestedEventArgs
ms.openlocfilehash: d18ccc91d16213cf0a915420b406b65823b3f9d9
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886449"
---
# <span data-ttu-id="14239-104">interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="14239-104">interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="14239-105">Webview.newwindowrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="14239-105">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="14239-106">摘要</span><span class="sxs-lookup"><span data-stu-id="14239-106">Summary</span></span>

 <span data-ttu-id="14239-107">成员</span><span class="sxs-lookup"><span data-stu-id="14239-107">Members</span></span>                        | <span data-ttu-id="14239-108">描述</span><span class="sxs-lookup"><span data-stu-id="14239-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="14239-109">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="14239-109">get_WindowFeatures</span></span>](#get_windowfeatures) | <span data-ttu-id="14239-110">窗口指定的窗口功能。打开通话。</span><span class="sxs-lookup"><span data-stu-id="14239-110">Window features specified by the window.open call.</span></span>

<span data-ttu-id="14239-111">如果 web 视图中的内容请求打开一个新窗口（通过 "打开" （）等），将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="14239-111">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="14239-112">成员</span><span class="sxs-lookup"><span data-stu-id="14239-112">Members</span></span>

#### <span data-ttu-id="14239-113">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="14239-113">get_WindowFeatures</span></span> 

<span data-ttu-id="14239-114">窗口指定的窗口功能。打开通话。</span><span class="sxs-lookup"><span data-stu-id="14239-114">Window features specified by the window.open call.</span></span>

> <span data-ttu-id="14239-115">公共 HRESULT [get_WindowFeatures](#get_windowfeatures)（[ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) \* \* WindowFeatures）</span><span class="sxs-lookup"><span data-stu-id="14239-115">public HRESULT [get_WindowFeatures](#get_windowfeatures)([ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) \*\* windowFeatures)</span></span>

<span data-ttu-id="14239-116">可将这些功能考虑到新的 web 视图窗口的位置和大小调整。</span><span class="sxs-lookup"><span data-stu-id="14239-116">These features can be considered for positioning and sizing of new webview windows.</span></span>

