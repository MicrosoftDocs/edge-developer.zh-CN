---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2Deferral
ms.openlocfilehash: 85c8a795a79bae461ad958e6586b9bf1f6778075
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880120"
---
# <span data-ttu-id="3acc3-104">interface ICoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="3acc3-104">interface ICoreWebView2Deferral</span></span> 

```
interface ICoreWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="3acc3-105">此接口用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="3acc3-105">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="3acc3-106">摘要</span><span class="sxs-lookup"><span data-stu-id="3acc3-106">Summary</span></span>

 <span data-ttu-id="3acc3-107">成员</span><span class="sxs-lookup"><span data-stu-id="3acc3-107">Members</span></span>                        | <span data-ttu-id="3acc3-108">描述</span><span class="sxs-lookup"><span data-stu-id="3acc3-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3acc3-109">完成</span><span class="sxs-lookup"><span data-stu-id="3acc3-109">Complete</span></span>](#complete) | <span data-ttu-id="3acc3-110">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="3acc3-110">Completes the associated deferred event.</span></span>

## <span data-ttu-id="3acc3-111">成员</span><span class="sxs-lookup"><span data-stu-id="3acc3-111">Members</span></span>

#### <span data-ttu-id="3acc3-112">完成</span><span class="sxs-lookup"><span data-stu-id="3acc3-112">Complete</span></span> 

<span data-ttu-id="3acc3-113">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="3acc3-113">Completes the associated deferred event.</span></span>

> <span data-ttu-id="3acc3-114">公共 HRESULT[完成](#complete)（）</span><span class="sxs-lookup"><span data-stu-id="3acc3-114">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="3acc3-115">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="3acc3-115">Complete should only be called once for each deferral taken.</span></span>

