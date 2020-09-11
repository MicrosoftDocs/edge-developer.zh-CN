---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2Deferral
ms.openlocfilehash: d8abff93df317a42c1bfe89dd32ac1d5f7e8c329
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011794"
---
# <span data-ttu-id="d95ca-104">interface ICoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="d95ca-104">interface ICoreWebView2Deferral</span></span> 

```
interface ICoreWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="d95ca-105">此接口用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="d95ca-105">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="d95ca-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d95ca-106">Summary</span></span>

 <span data-ttu-id="d95ca-107">成员</span><span class="sxs-lookup"><span data-stu-id="d95ca-107">Members</span></span>                        | <span data-ttu-id="d95ca-108">描述</span><span class="sxs-lookup"><span data-stu-id="d95ca-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d95ca-109">完成</span><span class="sxs-lookup"><span data-stu-id="d95ca-109">Complete</span></span>](#complete) | <span data-ttu-id="d95ca-110">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="d95ca-110">Completes the associated deferred event.</span></span>

## <span data-ttu-id="d95ca-111">成员</span><span class="sxs-lookup"><span data-stu-id="d95ca-111">Members</span></span>

#### <span data-ttu-id="d95ca-112">完成</span><span class="sxs-lookup"><span data-stu-id="d95ca-112">Complete</span></span> 

<span data-ttu-id="d95ca-113">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="d95ca-113">Completes the associated deferred event.</span></span>

> <span data-ttu-id="d95ca-114">公共 HRESULT [完成](#complete) ( # A1</span><span class="sxs-lookup"><span data-stu-id="d95ca-114">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="d95ca-115">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="d95ca-115">Complete should only be called once for each deferral taken.</span></span>

