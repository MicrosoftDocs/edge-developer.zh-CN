---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2Deferral 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 77a3540a64c9894f10cb0c03998dafda90e4f15b
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878930"
---
# <span data-ttu-id="87c08-104">CoreWebView2Deferral 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="87c08-104">Microsoft.Web.WebView2.Core.CoreWebView2Deferral class</span></span> 

<span data-ttu-id="87c08-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="87c08-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="87c08-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="87c08-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="87c08-107">此类用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="87c08-107">This class is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="87c08-108">摘要</span><span class="sxs-lookup"><span data-stu-id="87c08-108">Summary</span></span>

 <span data-ttu-id="87c08-109">成员</span><span class="sxs-lookup"><span data-stu-id="87c08-109">Members</span></span>                        | <span data-ttu-id="87c08-110">描述</span><span class="sxs-lookup"><span data-stu-id="87c08-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="87c08-111">完成</span><span class="sxs-lookup"><span data-stu-id="87c08-111">Complete</span></span>](#complete) | <span data-ttu-id="87c08-112">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="87c08-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="87c08-113">成员</span><span class="sxs-lookup"><span data-stu-id="87c08-113">Members</span></span>

#### <span data-ttu-id="87c08-114">完成</span><span class="sxs-lookup"><span data-stu-id="87c08-114">Complete</span></span> 

<span data-ttu-id="87c08-115">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="87c08-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="87c08-116">公共失效[完整](#complete)（）</span><span class="sxs-lookup"><span data-stu-id="87c08-116">public void [Complete](#complete)()</span></span>

<span data-ttu-id="87c08-117">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="87c08-117">Complete should only be called once for each deferral taken.</span></span>

