---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 4ae58375f0158a3876b284e16a579149dc6db9a5
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698537"
---
# <span data-ttu-id="74110-104">interface ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="74110-104">interface ICoreWebView2SourceChangedEventArgs</span></span> 

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="74110-105">SourceChanged 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="74110-105">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="74110-106">摘要</span><span class="sxs-lookup"><span data-stu-id="74110-106">Summary</span></span>

 <span data-ttu-id="74110-107">成员</span><span class="sxs-lookup"><span data-stu-id="74110-107">Members</span></span>                        | <span data-ttu-id="74110-108">描述</span><span class="sxs-lookup"><span data-stu-id="74110-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="74110-109">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="74110-109">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="74110-110">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="74110-110">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="74110-111">成员</span><span class="sxs-lookup"><span data-stu-id="74110-111">Members</span></span>

#### <span data-ttu-id="74110-112">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="74110-112">get_IsNewDocument</span></span> 

<span data-ttu-id="74110-113">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="74110-113">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="74110-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)（BOOL \* IsNewDocument）</span><span class="sxs-lookup"><span data-stu-id="74110-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

