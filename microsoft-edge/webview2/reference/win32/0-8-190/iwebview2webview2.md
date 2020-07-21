---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 64dac6c56576b618cbdc84da2c8fcbcd0e41028f
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884729"
---
# <span data-ttu-id="6d00c-104">0.8.355-接口 IWebView2WebView2</span><span class="sxs-lookup"><span data-stu-id="6d00c-104">0.8.355 - interface IWebView2WebView2</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebView2
  : public IUnknown
```

<span data-ttu-id="6d00c-105">由主 Web 视图对象实现的附加功能。</span><span class="sxs-lookup"><span data-stu-id="6d00c-105">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="6d00c-106">摘要</span><span class="sxs-lookup"><span data-stu-id="6d00c-106">Summary</span></span>

 <span data-ttu-id="6d00c-107">成员</span><span class="sxs-lookup"><span data-stu-id="6d00c-107">Members</span></span>                        | <span data-ttu-id="6d00c-108">描述</span><span class="sxs-lookup"><span data-stu-id="6d00c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6d00c-109">停止</span><span class="sxs-lookup"><span data-stu-id="6d00c-109">Stop</span></span>](#stop) | <span data-ttu-id="6d00c-110">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="6d00c-110">Stop all navigations and pending resource fetches.</span></span>

<span data-ttu-id="6d00c-111">你可以从实现[IWebView2WebView](IWebView2WebView.md)的对象中为此接口执行 QueryInterface。</span><span class="sxs-lookup"><span data-stu-id="6d00c-111">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="6d00c-112">有关详细信息，请参阅[IWebView2WebView](IWebView2WebView.md)界面。</span><span class="sxs-lookup"><span data-stu-id="6d00c-112">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="6d00c-113">成员</span><span class="sxs-lookup"><span data-stu-id="6d00c-113">Members</span></span>

#### <span data-ttu-id="6d00c-114">停止</span><span class="sxs-lookup"><span data-stu-id="6d00c-114">Stop</span></span> 

<span data-ttu-id="6d00c-115">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="6d00c-115">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="6d00c-116">公共 HRESULT[停止](#stop)（）</span><span class="sxs-lookup"><span data-stu-id="6d00c-116">public HRESULT [Stop](#stop)()</span></span>

