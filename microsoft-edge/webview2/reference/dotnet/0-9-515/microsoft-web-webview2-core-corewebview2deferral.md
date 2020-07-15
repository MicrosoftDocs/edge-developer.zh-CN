---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 4df74c4a645b6bfa17228860f627910d374e19c4
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878720"
---
# <span data-ttu-id="e9ee1-104">0.9.515-WebView2 的 CoreWebView2Deferral 类</span><span class="sxs-lookup"><span data-stu-id="e9ee1-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2Deferral class</span></span> 

> [!NOTE]
> <span data-ttu-id="e9ee1-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="e9ee1-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="e9ee1-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="e9ee1-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="e9ee1-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="e9ee1-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="e9ee1-108">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="e9ee1-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="e9ee1-109">此类用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="e9ee1-109">This class is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="e9ee1-110">摘要</span><span class="sxs-lookup"><span data-stu-id="e9ee1-110">Summary</span></span>

 <span data-ttu-id="e9ee1-111">成员</span><span class="sxs-lookup"><span data-stu-id="e9ee1-111">Members</span></span>                        | <span data-ttu-id="e9ee1-112">描述</span><span class="sxs-lookup"><span data-stu-id="e9ee1-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e9ee1-113">完成</span><span class="sxs-lookup"><span data-stu-id="e9ee1-113">Complete</span></span>](#complete) | <span data-ttu-id="e9ee1-114">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="e9ee1-114">Completes the associated deferred event.</span></span>

## <span data-ttu-id="e9ee1-115">成员</span><span class="sxs-lookup"><span data-stu-id="e9ee1-115">Members</span></span>

#### <span data-ttu-id="e9ee1-116">完成</span><span class="sxs-lookup"><span data-stu-id="e9ee1-116">Complete</span></span> 

<span data-ttu-id="e9ee1-117">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="e9ee1-117">Completes the associated deferred event.</span></span>

> <span data-ttu-id="e9ee1-118">公共失效[完整](#complete)（）</span><span class="sxs-lookup"><span data-stu-id="e9ee1-118">public void [Complete](#complete)()</span></span>

<span data-ttu-id="e9ee1-119">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="e9ee1-119">Complete should only be called once for each deferral taken.</span></span>

