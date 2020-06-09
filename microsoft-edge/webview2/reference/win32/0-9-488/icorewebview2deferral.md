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
ms.openlocfilehash: 7d21db7c3f0a66f60f32e92b3951151b8d13a002
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698076"
---
# <span data-ttu-id="4eb3d-104">interface ICoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="4eb3d-104">interface ICoreWebView2Deferral</span></span> 

> [!NOTE]
> <span data-ttu-id="4eb3d-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="4eb3d-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="4eb3d-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="4eb3d-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="4eb3d-107">此接口用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="4eb3d-107">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="4eb3d-108">摘要</span><span class="sxs-lookup"><span data-stu-id="4eb3d-108">Summary</span></span>

 <span data-ttu-id="4eb3d-109">成员</span><span class="sxs-lookup"><span data-stu-id="4eb3d-109">Members</span></span>                        | <span data-ttu-id="4eb3d-110">描述</span><span class="sxs-lookup"><span data-stu-id="4eb3d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4eb3d-111">完成</span><span class="sxs-lookup"><span data-stu-id="4eb3d-111">Complete</span></span>](#complete) | <span data-ttu-id="4eb3d-112">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="4eb3d-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="4eb3d-113">成员</span><span class="sxs-lookup"><span data-stu-id="4eb3d-113">Members</span></span>

#### <span data-ttu-id="4eb3d-114">完成</span><span class="sxs-lookup"><span data-stu-id="4eb3d-114">Complete</span></span> 

<span data-ttu-id="4eb3d-115">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="4eb3d-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="4eb3d-116">公共 HRESULT[完成](#complete)（）</span><span class="sxs-lookup"><span data-stu-id="4eb3d-116">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="4eb3d-117">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="4eb3d-117">Complete should only be called once for each deferral taken.</span></span>

