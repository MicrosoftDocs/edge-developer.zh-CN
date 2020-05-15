---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: cb317e9078e48ed14091eb2eda6ff9d59a19c6ce
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652945"
---
# <span data-ttu-id="2a6e0-104">interface IWebView2Settings2</span><span class="sxs-lookup"><span data-stu-id="2a6e0-104">interface IWebView2Settings2</span></span> 

> [!NOTE]
> <span data-ttu-id="2a6e0-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="2a6e0-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="2a6e0-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="2a6e0-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2Settings2
  : public IWebView2Settings
```

<span data-ttu-id="2a6e0-107">定义启用、禁用或修改 Web 视图功能的属性。</span><span class="sxs-lookup"><span data-stu-id="2a6e0-107">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="2a6e0-108">摘要</span><span class="sxs-lookup"><span data-stu-id="2a6e0-108">Summary</span></span>

 <span data-ttu-id="2a6e0-109">成员</span><span class="sxs-lookup"><span data-stu-id="2a6e0-109">Members</span></span>                        | <span data-ttu-id="2a6e0-110">描述</span><span class="sxs-lookup"><span data-stu-id="2a6e0-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2a6e0-111">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="2a6e0-111">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="2a6e0-112">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="2a6e0-112">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="2a6e0-113">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="2a6e0-113">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="2a6e0-114">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="2a6e0-114">Set the AreDefaultContextMenusEnabled property.</span></span>

<span data-ttu-id="2a6e0-115">在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。</span><span class="sxs-lookup"><span data-stu-id="2a6e0-115">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="2a6e0-116">成员</span><span class="sxs-lookup"><span data-stu-id="2a6e0-116">Members</span></span>

#### <span data-ttu-id="2a6e0-117">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="2a6e0-117">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="2a6e0-118">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="2a6e0-118">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="2a6e0-119">公共 HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="2a6e0-119">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="2a6e0-120">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="2a6e0-120">Defaults to TRUE.</span></span>

```cpp
            BOOL allowContextMenus;
            CHECK_FAILURE(m_settings->get_AreDefaultContextMenusEnabled(
                &allowContextMenus));
            if (allowContextMenus) {
                CHECK_FAILURE(m_settings->put_AreDefaultContextMenusEnabled(FALSE));
                MessageBox(nullptr,
                L"Context menus will be disabled after the next navigation.",
                L"Settings change", MB_OK);
            }
            else {
                CHECK_FAILURE(m_settings->put_AreDefaultContextMenusEnabled(TRUE));
                MessageBox(nullptr,
                    L"Context menus will be enabled after the next navigation.",
                    L"Settings change", MB_OK);
            }
```

#### <span data-ttu-id="2a6e0-121">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="2a6e0-121">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="2a6e0-122">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="2a6e0-122">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="2a6e0-123">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="2a6e0-123">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

