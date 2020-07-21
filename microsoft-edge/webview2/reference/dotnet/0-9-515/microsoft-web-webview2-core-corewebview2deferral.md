---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 135289994bdfe5481018c479b7a1d9c372ecb256
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885105"
---
# <span data-ttu-id="582ce-104">0.9.515-WebView2 的 CoreWebView2Deferral 类</span><span class="sxs-lookup"><span data-stu-id="582ce-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2Deferral class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="582ce-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="582ce-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="582ce-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="582ce-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="582ce-107">此类用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="582ce-107">This class is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="582ce-108">摘要</span><span class="sxs-lookup"><span data-stu-id="582ce-108">Summary</span></span>

 <span data-ttu-id="582ce-109">成员</span><span class="sxs-lookup"><span data-stu-id="582ce-109">Members</span></span>                        | <span data-ttu-id="582ce-110">描述</span><span class="sxs-lookup"><span data-stu-id="582ce-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="582ce-111">完成</span><span class="sxs-lookup"><span data-stu-id="582ce-111">Complete</span></span>](#complete) | <span data-ttu-id="582ce-112">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="582ce-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="582ce-113">成员</span><span class="sxs-lookup"><span data-stu-id="582ce-113">Members</span></span>

#### <span data-ttu-id="582ce-114">完成</span><span class="sxs-lookup"><span data-stu-id="582ce-114">Complete</span></span> 

<span data-ttu-id="582ce-115">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="582ce-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="582ce-116">公共失效[完整](#complete)（）</span><span class="sxs-lookup"><span data-stu-id="582ce-116">public void [Complete](#complete)()</span></span>

<span data-ttu-id="582ce-117">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="582ce-117">Complete should only be called once for each deferral taken.</span></span>

