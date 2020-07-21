---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: b30b6e35388ab01433b2c879db82d9c4136fae99
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885413"
---
# <span data-ttu-id="9e6d1-104">0.9.515-接口 ICoreWebView2Deferral</span><span class="sxs-lookup"><span data-stu-id="9e6d1-104">0.9.515 - interface ICoreWebView2Deferral</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2Deferral
  : public IUnknown
```

<span data-ttu-id="9e6d1-105">此接口用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。</span><span class="sxs-lookup"><span data-stu-id="9e6d1-105">This interface is used to complete deferrals on event args that support getting deferrals via their GetDeferral method.</span></span>

## <span data-ttu-id="9e6d1-106">摘要</span><span class="sxs-lookup"><span data-stu-id="9e6d1-106">Summary</span></span>

 <span data-ttu-id="9e6d1-107">成员</span><span class="sxs-lookup"><span data-stu-id="9e6d1-107">Members</span></span>                        | <span data-ttu-id="9e6d1-108">描述</span><span class="sxs-lookup"><span data-stu-id="9e6d1-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9e6d1-109">完成</span><span class="sxs-lookup"><span data-stu-id="9e6d1-109">Complete</span></span>](#complete) | <span data-ttu-id="9e6d1-110">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="9e6d1-110">Completes the associated deferred event.</span></span>

## <span data-ttu-id="9e6d1-111">成员</span><span class="sxs-lookup"><span data-stu-id="9e6d1-111">Members</span></span>

#### <span data-ttu-id="9e6d1-112">完成</span><span class="sxs-lookup"><span data-stu-id="9e6d1-112">Complete</span></span> 

<span data-ttu-id="9e6d1-113">完成关联的延迟事件。</span><span class="sxs-lookup"><span data-stu-id="9e6d1-113">Completes the associated deferred event.</span></span>

> <span data-ttu-id="9e6d1-114">公共 HRESULT[完成](#complete)（）</span><span class="sxs-lookup"><span data-stu-id="9e6d1-114">public HRESULT [Complete](#complete)()</span></span>

<span data-ttu-id="9e6d1-115">对于每个延迟的延迟，只能调用一次完成。</span><span class="sxs-lookup"><span data-stu-id="9e6d1-115">Complete should only be called once for each deferral taken.</span></span>

