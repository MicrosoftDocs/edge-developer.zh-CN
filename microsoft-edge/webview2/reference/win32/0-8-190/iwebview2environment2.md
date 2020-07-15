---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2Environment2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: d127af61bfdc9bf692fa48489d7982bf2c6cad86
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878545"
---
# <span data-ttu-id="eac14-104">0.8.355-接口 IWebView2Environment2</span><span class="sxs-lookup"><span data-stu-id="eac14-104">0.8.355 - interface IWebView2Environment2</span></span> 

> [!NOTE]
> <span data-ttu-id="eac14-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="eac14-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="eac14-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="eac14-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2Environment2
  : public IWebView2Environment
```

<span data-ttu-id="eac14-107">由环境对象实现的其他功能。</span><span class="sxs-lookup"><span data-stu-id="eac14-107">Additional functionality implemented by the Environment object.</span></span>

## <span data-ttu-id="eac14-108">摘要</span><span class="sxs-lookup"><span data-stu-id="eac14-108">Summary</span></span>

 <span data-ttu-id="eac14-109">成员</span><span class="sxs-lookup"><span data-stu-id="eac14-109">Members</span></span>                        | <span data-ttu-id="eac14-110">描述</span><span class="sxs-lookup"><span data-stu-id="eac14-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="eac14-111">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="eac14-111">get_BrowserVersionInfo</span></span>](#get_browserversioninfo) | <span data-ttu-id="eac14-112">当前[IWebView2Environment](IWebView2Environment.md)的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="eac14-112">The browser version info of the current [IWebView2Environment](IWebView2Environment.md), including channel name if it is not the stable channel.</span></span>

<span data-ttu-id="eac14-113">有关详细信息，请参阅[IWebView2Environment](IWebView2Environment.md)界面。</span><span class="sxs-lookup"><span data-stu-id="eac14-113">See the [IWebView2Environment](IWebView2Environment.md) interface for more details.</span></span> <span data-ttu-id="eac14-114">你可以从实现[IWebView2Environment](IWebView2Environment.md)的对象中为此接口执行 QueryInterface。</span><span class="sxs-lookup"><span data-stu-id="eac14-114">You can QueryInterface for this interface from the object that implements [IWebView2Environment](IWebView2Environment.md).</span></span>

## <span data-ttu-id="eac14-115">成员</span><span class="sxs-lookup"><span data-stu-id="eac14-115">Members</span></span>

#### <span data-ttu-id="eac14-116">get_BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="eac14-116">get_BrowserVersionInfo</span></span> 

<span data-ttu-id="eac14-117">当前[IWebView2Environment](IWebView2Environment.md)的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="eac14-117">The browser version info of the current [IWebView2Environment](IWebView2Environment.md), including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="eac14-118">公共 HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)（LPWSTR \* versionInfo）</span><span class="sxs-lookup"><span data-stu-id="eac14-118">public HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)(LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="eac14-119">这与 GetWebView2BrowserVersionInfo API 的格式相匹配。</span><span class="sxs-lookup"><span data-stu-id="eac14-119">This matches the format of the GetWebView2BrowserVersionInfo API.</span></span> <span data-ttu-id="eac14-120">信道名称为 "beta"、"dev" 和 "未设备"。</span><span class="sxs-lookup"><span data-stu-id="eac14-120">Channel names are 'beta', 'dev', and 'canary'.</span></span>

```cpp
        wil::unique_cotaskmem_string version_info;
        m_webViewEnvironment->get_BrowserVersionInfo(&version_info);
        MessageBox(
            m_mainWindow, version_info.get(), L"Browser Version Info After WebView Creation",
            MB_OK);
```

