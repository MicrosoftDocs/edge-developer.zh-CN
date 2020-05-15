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
ms.openlocfilehash: d43cbe741cc9cd8b027a21115133db9377a95658
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652990"
---
# <span data-ttu-id="25f3f-104">interface IWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="25f3f-104">interface IWebView2Deferral</span></span> 

> [!NOTE]
> <span data-ttu-id="25f3f-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="25f3f-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="25f3f-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="25f3f-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="25f3f-107">此接口用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="25f3f-107">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="25f3f-108">摘要</span><span class="sxs-lookup"><span data-stu-id="25f3f-108">Summary</span></span>

 <span data-ttu-id="25f3f-109">成员</span><span class="sxs-lookup"><span data-stu-id="25f3f-109">Members</span></span>                        | <span data-ttu-id="25f3f-110">描述</span><span class="sxs-lookup"><span data-stu-id="25f3f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="25f3f-111">完成</span><span class="sxs-lookup"><span data-stu-id="25f3f-111">Complete</span></span>](#complete) | <span data-ttu-id="25f3f-112">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="25f3f-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="25f3f-113">成员</span><span class="sxs-lookup"><span data-stu-id="25f3f-113">Members</span></span>

#### <span data-ttu-id="25f3f-114">完成</span><span class="sxs-lookup"><span data-stu-id="25f3f-114">Complete</span></span> 

<span data-ttu-id="25f3f-115">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="25f3f-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="25f3f-116">公共 HRESULT[完成](#complete)（）</span><span class="sxs-lookup"><span data-stu-id="25f3f-116">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="25f3f-117">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="25f3f-117">Complete should only be called once for each deferral taken.</span></span>

