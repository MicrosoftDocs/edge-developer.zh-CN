---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: ebaab6dfe0781f544e89e86afc9f16ab50cb9222
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653076"
---
# <span data-ttu-id="59e8f-104">interface ICoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="59e8f-104">interface ICoreWebView2Deferral</span></span> 

```
interface ICoreWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="59e8f-105">此接口用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="59e8f-105">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="59e8f-106">摘要</span><span class="sxs-lookup"><span data-stu-id="59e8f-106">Summary</span></span>

 <span data-ttu-id="59e8f-107">成员</span><span class="sxs-lookup"><span data-stu-id="59e8f-107">Members</span></span>                        | <span data-ttu-id="59e8f-108">描述</span><span class="sxs-lookup"><span data-stu-id="59e8f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="59e8f-109">完成</span><span class="sxs-lookup"><span data-stu-id="59e8f-109">Complete</span></span>](#complete) | <span data-ttu-id="59e8f-110">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="59e8f-110">Completes the associated deferred event.</span></span>

## <span data-ttu-id="59e8f-111">成员</span><span class="sxs-lookup"><span data-stu-id="59e8f-111">Members</span></span>

#### <span data-ttu-id="59e8f-112">完成</span><span class="sxs-lookup"><span data-stu-id="59e8f-112">Complete</span></span> 

<span data-ttu-id="59e8f-113">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="59e8f-113">Completes the associated deferred event.</span></span>

> <span data-ttu-id="59e8f-114">公共 HRESULT[完成](#complete)（）</span><span class="sxs-lookup"><span data-stu-id="59e8f-114">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="59e8f-115">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="59e8f-115">Complete should only be called once for each deferral taken.</span></span>

