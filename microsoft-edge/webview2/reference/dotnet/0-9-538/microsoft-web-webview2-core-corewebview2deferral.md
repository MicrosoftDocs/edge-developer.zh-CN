---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2。 CoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 62cd86772d45e1bf9eee7d1821a90b723e1af7db
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011046"
---
# <span data-ttu-id="82704-104">0.9.579-WebView2 的 CoreWebView2Deferral 类</span><span class="sxs-lookup"><span data-stu-id="82704-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2Deferral class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="82704-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="82704-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="82704-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="82704-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="82704-107">此类用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="82704-107">This class is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="82704-108">摘要</span><span class="sxs-lookup"><span data-stu-id="82704-108">Summary</span></span>

 <span data-ttu-id="82704-109">成员</span><span class="sxs-lookup"><span data-stu-id="82704-109">Members</span></span>                        | <span data-ttu-id="82704-110">描述</span><span class="sxs-lookup"><span data-stu-id="82704-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="82704-111">完成</span><span class="sxs-lookup"><span data-stu-id="82704-111">Complete</span></span>](#complete) | <span data-ttu-id="82704-112">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="82704-112">Completes the associated deferred event.</span></span>

## <span data-ttu-id="82704-113">成员</span><span class="sxs-lookup"><span data-stu-id="82704-113">Members</span></span>

#### <span data-ttu-id="82704-114">完成</span><span class="sxs-lookup"><span data-stu-id="82704-114">Complete</span></span> 

<span data-ttu-id="82704-115">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="82704-115">Completes the associated deferred event.</span></span>

> <span data-ttu-id="82704-116">public void [完整](#complete) ( # A1</span><span class="sxs-lookup"><span data-stu-id="82704-116">public void [Complete](#complete)()</span></span>

<span data-ttu-id="82704-117">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="82704-117">Complete should only be called once for each deferral taken.</span></span>

