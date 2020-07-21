---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2Settings2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 4ba0299f3afbc6fc2846481f52c1000cd338ecd8
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885784"
---
# <span data-ttu-id="520da-104">0.8.355-接口 IWebView2Settings2</span><span class="sxs-lookup"><span data-stu-id="520da-104">0.8.355 - interface IWebView2Settings2</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2Settings2
  : public IWebView2Settings
```

<span data-ttu-id="520da-105">定义启用、禁用或修改 Web 视图功能的属性。</span><span class="sxs-lookup"><span data-stu-id="520da-105">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="520da-106">摘要</span><span class="sxs-lookup"><span data-stu-id="520da-106">Summary</span></span>

 <span data-ttu-id="520da-107">成员</span><span class="sxs-lookup"><span data-stu-id="520da-107">Members</span></span>                        | <span data-ttu-id="520da-108">描述</span><span class="sxs-lookup"><span data-stu-id="520da-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="520da-109">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="520da-109">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="520da-110">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="520da-110">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="520da-111">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="520da-111">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="520da-112">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="520da-112">Set the AreDefaultContextMenusEnabled property.</span></span>

<span data-ttu-id="520da-113">在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。</span><span class="sxs-lookup"><span data-stu-id="520da-113">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="520da-114">成员</span><span class="sxs-lookup"><span data-stu-id="520da-114">Members</span></span>

#### <span data-ttu-id="520da-115">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="520da-115">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="520da-116">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="520da-116">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="520da-117">公共 HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="520da-117">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="520da-118">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="520da-118">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="520da-119">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="520da-119">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="520da-120">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="520da-120">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="520da-121">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="520da-121">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

