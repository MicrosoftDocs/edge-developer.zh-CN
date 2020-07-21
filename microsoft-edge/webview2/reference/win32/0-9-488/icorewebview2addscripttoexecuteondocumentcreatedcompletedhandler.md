---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 5a74464f841a0c8320bef7f81c83567d58f6caca
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884475"
---
# <span data-ttu-id="2fc3e-104">0.9.515-接口 ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span><span class="sxs-lookup"><span data-stu-id="2fc3e-104">0.9.515 - interface ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler
  : public IUnknown
```

<span data-ttu-id="2fc3e-105">调用方实现此接口以接收 AddScriptToExecuteOnDocumentCreated 方法的结果。</span><span class="sxs-lookup"><span data-stu-id="2fc3e-105">The caller implements this interface to receive the result of the AddScriptToExecuteOnDocumentCreated method.</span></span>

## <span data-ttu-id="2fc3e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="2fc3e-106">Summary</span></span>

 <span data-ttu-id="2fc3e-107">成员</span><span class="sxs-lookup"><span data-stu-id="2fc3e-107">Members</span></span>                        | <span data-ttu-id="2fc3e-108">描述</span><span class="sxs-lookup"><span data-stu-id="2fc3e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2fc3e-109">调用</span><span class="sxs-lookup"><span data-stu-id="2fc3e-109">Invoke</span></span>](#invoke) | <span data-ttu-id="2fc3e-110">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="2fc3e-110">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

## <span data-ttu-id="2fc3e-111">成员</span><span class="sxs-lookup"><span data-stu-id="2fc3e-111">Members</span></span>

#### <span data-ttu-id="2fc3e-112">调用</span><span class="sxs-lookup"><span data-stu-id="2fc3e-112">Invoke</span></span> 

<span data-ttu-id="2fc3e-113">调用以向实施者提供相应的异步方法调用的完成状态和结果。</span><span class="sxs-lookup"><span data-stu-id="2fc3e-113">Called to provide the implementer with the completion status and result of the corresponding asynchronous method call.</span></span>

> <span data-ttu-id="2fc3e-114">公共 HRESULT[调用](#invoke)（hresult ERRORCODE、LPCWSTR id）</span><span class="sxs-lookup"><span data-stu-id="2fc3e-114">public HRESULT [Invoke](#invoke)(HRESULT errorCode, LPCWSTR id)</span></span>

