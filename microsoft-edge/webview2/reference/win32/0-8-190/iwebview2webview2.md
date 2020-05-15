---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 62daeaab702b431f787bc800ab79664fc183c4ce
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652798"
---
# <span data-ttu-id="d1b1d-104">interface IWebView2WebView2</span><span class="sxs-lookup"><span data-stu-id="d1b1d-104">interface IWebView2WebView2</span></span> 

> [!NOTE]
> <span data-ttu-id="d1b1d-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="d1b1d-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="d1b1d-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="d1b1d-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebView2
  : public IUnknown
```

<span data-ttu-id="d1b1d-107">由主 Web 视图对象实现的附加功能。</span><span class="sxs-lookup"><span data-stu-id="d1b1d-107">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="d1b1d-108">摘要</span><span class="sxs-lookup"><span data-stu-id="d1b1d-108">Summary</span></span>

 <span data-ttu-id="d1b1d-109">成员</span><span class="sxs-lookup"><span data-stu-id="d1b1d-109">Members</span></span>                        | <span data-ttu-id="d1b1d-110">描述</span><span class="sxs-lookup"><span data-stu-id="d1b1d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d1b1d-111">停止</span><span class="sxs-lookup"><span data-stu-id="d1b1d-111">Stop</span></span>](#stop) | <span data-ttu-id="d1b1d-112">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="d1b1d-112">Stop all navigations and pending resource fetches.</span></span>

<span data-ttu-id="d1b1d-113">你可以从实现[IWebView2WebView](IWebView2WebView.md)的对象中为此接口执行 QueryInterface。</span><span class="sxs-lookup"><span data-stu-id="d1b1d-113">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="d1b1d-114">有关详细信息，请参阅[IWebView2WebView](IWebView2WebView.md)界面。</span><span class="sxs-lookup"><span data-stu-id="d1b1d-114">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="d1b1d-115">成员</span><span class="sxs-lookup"><span data-stu-id="d1b1d-115">Members</span></span>

#### <span data-ttu-id="d1b1d-116">停止</span><span class="sxs-lookup"><span data-stu-id="d1b1d-116">Stop</span></span> 

<span data-ttu-id="d1b1d-117">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="d1b1d-117">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="d1b1d-118">公共 HRESULT[停止](#stop)（）</span><span class="sxs-lookup"><span data-stu-id="d1b1d-118">public HRESULT [Stop](#stop)()</span></span>

