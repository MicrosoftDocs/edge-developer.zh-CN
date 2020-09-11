---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2Deferral
ms.openlocfilehash: 533aefe8b14ae3cabfddd32cb588014067bfdd42
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010283"
---
# <span data-ttu-id="0981b-104">0.9.579-接口 ICoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="0981b-104">0.9.579 - interface ICoreWebView2Deferral</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="0981b-105">此接口用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="0981b-105">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="0981b-106">摘要</span><span class="sxs-lookup"><span data-stu-id="0981b-106">Summary</span></span>

 <span data-ttu-id="0981b-107">成员</span><span class="sxs-lookup"><span data-stu-id="0981b-107">Members</span></span>                        | <span data-ttu-id="0981b-108">描述</span><span class="sxs-lookup"><span data-stu-id="0981b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0981b-109">完成</span><span class="sxs-lookup"><span data-stu-id="0981b-109">Complete</span></span>](#complete) | <span data-ttu-id="0981b-110">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="0981b-110">Completes the associated deferred event.</span></span>

## <span data-ttu-id="0981b-111">成员</span><span class="sxs-lookup"><span data-stu-id="0981b-111">Members</span></span>

#### <span data-ttu-id="0981b-112">完成</span><span class="sxs-lookup"><span data-stu-id="0981b-112">Complete</span></span> 

<span data-ttu-id="0981b-113">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="0981b-113">Completes the associated deferred event.</span></span>

> <span data-ttu-id="0981b-114">公共 HRESULT [完成](#complete) ( # A1</span><span class="sxs-lookup"><span data-stu-id="0981b-114">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="0981b-115">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="0981b-115">Complete should only be called once for each deferral taken.</span></span>

