---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2Environment2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: e3177f159ff397ee9d4781936aa32f2715d4af02
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886085"
---
# <span data-ttu-id="edba9-104">0.8.355-接口 IWebView2Environment2</span><span class="sxs-lookup"><span data-stu-id="edba9-104">0.8.355 - interface IWebView2Environment2</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2Environment2
  : public IWebView2Environment
```

<span data-ttu-id="edba9-105">由环境对象实现的其他功能。</span><span class="sxs-lookup"><span data-stu-id="edba9-105">Additional functionality implemented by the Environment object.</span></span>

## <span data-ttu-id="edba9-106">摘要</span><span class="sxs-lookup"><span data-stu-id="edba9-106">Summary</span></span>

 <span data-ttu-id="edba9-107">成员</span><span class="sxs-lookup"><span data-stu-id="edba9-107">Members</span></span>                        | <span data-ttu-id="edba9-108">描述</span><span class="sxs-lookup"><span data-stu-id="edba9-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="edba9-109">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="edba9-109">get_BrowserVersionInfo</span></span>](#get_browserversioninfo) | <span data-ttu-id="edba9-110">当前[IWebView2Environment](IWebView2Environment.md)的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="edba9-110">The browser version info of the current [IWebView2Environment](IWebView2Environment.md), including channel name if it is not the stable channel.</span></span>

<span data-ttu-id="edba9-111">有关详细信息，请参阅[IWebView2Environment](IWebView2Environment.md)界面。</span><span class="sxs-lookup"><span data-stu-id="edba9-111">See the [IWebView2Environment](IWebView2Environment.md) interface for more details.</span></span> <span data-ttu-id="edba9-112">你可以从实现[IWebView2Environment](IWebView2Environment.md)的对象中为此接口执行 QueryInterface。</span><span class="sxs-lookup"><span data-stu-id="edba9-112">You can QueryInterface for this interface from the object that implements [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="edba9-113">成员</span><span class="sxs-lookup"><span data-stu-id="edba9-113">Members</span></span>

#### <span data-ttu-id="edba9-114">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="edba9-114">get_BrowserVersionInfo</span></span> 

<span data-ttu-id="edba9-115">当前[IWebView2Environment](IWebView2Environment.md)的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="edba9-115">The browser version info of the current [IWebView2Environment](IWebView2Environment.md), including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="edba9-116">公共 HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)（LPWSTR \* versionInfo）</span><span class="sxs-lookup"><span data-stu-id="edba9-116">public HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)(LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="edba9-117">这与 GetWebView2BrowserVersionInfo API 的格式相匹配。</span><span class="sxs-lookup"><span data-stu-id="edba9-117">This matches the format of the GetWebView2BrowserVersionInfo API.</span></span> <span data-ttu-id="edba9-118">信道名称为 "beta"、"dev" 和 "未设备"。</span><span class="sxs-lookup"><span data-stu-id="edba9-118">Channel names are 'beta', 'dev', and 'canary'.</span></span>

```cpp
        wil::unique_cotaskmem_string version_info;
        m_webViewEnvironment->get_BrowserVersionInfo(&version_info);
        MessageBox(
            m_mainWindow, version_info.get(), L"Browser Version Info After WebView Creation",
            MB_OK);
```

