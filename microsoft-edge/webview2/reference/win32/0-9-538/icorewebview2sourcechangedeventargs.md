---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2SourceChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2SourceChangedEventArgs
ms.openlocfilehash: 3e622a8fb5b8ed43e5a23eaab8bd0aa61ed7d193
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879399"
---
# <span data-ttu-id="bbe7f-104">interface ICoreWebView2SourceChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="bbe7f-104">interface ICoreWebView2SourceChangedEventArgs</span></span> 

```
interface ICoreWebView2SourceChangedEventArgs
  : public IUnknown
```

<span data-ttu-id="bbe7f-105">SourceChanged 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="bbe7f-105">Event args for the SourceChanged event.</span></span>

## <span data-ttu-id="bbe7f-106">摘要</span><span class="sxs-lookup"><span data-stu-id="bbe7f-106">Summary</span></span>

 <span data-ttu-id="bbe7f-107">成员</span><span class="sxs-lookup"><span data-stu-id="bbe7f-107">Members</span></span>                        | <span data-ttu-id="bbe7f-108">描述</span><span class="sxs-lookup"><span data-stu-id="bbe7f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bbe7f-109">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="bbe7f-109">get_IsNewDocument</span></span>](#get_isnewdocument) | <span data-ttu-id="bbe7f-110">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="bbe7f-110">True if the page being navigated to is a new document.</span></span>

## <span data-ttu-id="bbe7f-111">成员</span><span class="sxs-lookup"><span data-stu-id="bbe7f-111">Members</span></span>

#### <span data-ttu-id="bbe7f-112">get_IsNewDocument</span><span class="sxs-lookup"><span data-stu-id="bbe7f-112">get_IsNewDocument</span></span> 

<span data-ttu-id="bbe7f-113">如果要导航到的页面是新文档，则为 True。</span><span class="sxs-lookup"><span data-stu-id="bbe7f-113">True if the page being navigated to is a new document.</span></span>

> <span data-ttu-id="bbe7f-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)（BOOL \* IsNewDocument）</span><span class="sxs-lookup"><span data-stu-id="bbe7f-114">public HRESULT [get_IsNewDocument](#get_isnewdocument)(BOOL \* isNewDocument)</span></span>

