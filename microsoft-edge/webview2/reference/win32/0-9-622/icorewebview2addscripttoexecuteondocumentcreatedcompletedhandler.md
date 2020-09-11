---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
ms.openlocfilehash: 1580f119a83a171f304b7b05ecbc88edfe31e26d
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011770"
---
# <span data-ttu-id="f8edb-104">interface ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="f8edb-104">interface ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span></span> 

```
interface ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
  : public IUnknown
```

<span data-ttu-id="f8edb-105">调用方实现此接口以接收 AddScriptToExecuteOnDocumentCreated 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="f8edb-105">The caller implements this interface to receive the result of the AddScriptToExecuteOnDocumentCreated method.</span></span>

## <span data-ttu-id="f8edb-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f8edb-106">Summary</span></span>

 <span data-ttu-id="f8edb-107">成员</span><span class="sxs-lookup"><span data-stu-id="f8edb-107">Members</span></span>                        | <span data-ttu-id="f8edb-108">描述</span><span class="sxs-lookup"><span data-stu-id="f8edb-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f8edb-109">调用</span><span class="sxs-lookup"><span data-stu-id="f8edb-109">Invoke</span></span>](#invoke) | <span data-ttu-id="f8edb-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="f8edb-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="f8edb-111">成员</span><span class="sxs-lookup"><span data-stu-id="f8edb-111">Members</span></span>

#### <span data-ttu-id="f8edb-112">调用</span><span class="sxs-lookup"><span data-stu-id="f8edb-112">Invoke</span></span> 

<span data-ttu-id="f8edb-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="f8edb-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="f8edb-114">公共 HRESULT [调用](#invoke) (HRESULT ERRORCODE，LPCWSTR id) </span><span class="sxs-lookup"><span data-stu-id="f8edb-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR id)</span></span>

