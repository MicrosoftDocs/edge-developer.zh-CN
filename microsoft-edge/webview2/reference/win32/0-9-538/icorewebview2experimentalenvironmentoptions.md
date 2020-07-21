---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExperimentalEnvironmentOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalEnvironmentOptions
ms.openlocfilehash: 3e18c15e23338404720dae917cb6d009c41c3c04
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886525"
---
# <span data-ttu-id="0cd87-104">interface ICoreWebView2ExperimentalEnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="0cd87-104">interface ICoreWebView2ExperimentalEnvironmentOptions</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalEnvironmentOptions
  : public IUnknown
```

<span data-ttu-id="0cd87-105">用于创建 WebView2 环境的实验选项。</span><span class="sxs-lookup"><span data-stu-id="0cd87-105">Experimental options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="0cd87-106">摘要</span><span class="sxs-lookup"><span data-stu-id="0cd87-106">Summary</span></span>

 <span data-ttu-id="0cd87-107">成员</span><span class="sxs-lookup"><span data-stu-id="0cd87-107">Members</span></span>                        | <span data-ttu-id="0cd87-108">描述</span><span class="sxs-lookup"><span data-stu-id="0cd87-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0cd87-109">get_IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="0cd87-109">get_IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span>](#get_issinglesignonusingosprimaryaccountenabled) | <span data-ttu-id="0cd87-110">IsSingleSignOnUsingOSPrimaryAccountEnabled 属性用于使用使用登录的 Windows 帐户在 web 视图中使用 Azure Active Directory （AAD）资源启用单一登录，使用与 Windows 帐户中的登录相关联的 Microsoft 帐户进行单一登录。</span><span class="sxs-lookup"><span data-stu-id="0cd87-110">The IsSingleSignOnUsingOSPrimaryAccountEnabled property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>
[<span data-ttu-id="0cd87-111">put_IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="0cd87-111">put_IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span>](#put_issinglesignonusingosprimaryaccountenabled) | <span data-ttu-id="0cd87-112">设置 IsSingleSignOnUsingOSPrimaryAccountEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="0cd87-112">Set the IsSingleSignOnUsingOSPrimaryAccountEnabled property.</span></span>

<span data-ttu-id="0cd87-113">默认实现在 WebView2ExperimentalEnvironmentOptions 中提供。</span><span class="sxs-lookup"><span data-stu-id="0cd87-113">A default implementation is provided in WebView2ExperimentalEnvironmentOptions.h.</span></span>

```cpp
    auto options = Microsoft::WRL::Make<CoreWebView2ExperimentalEnvironmentOptions>();
    CHECK_FAILURE(options->put_IsSingleSignOnUsingOSPrimaryAccountEnabled(
        m_AADSSOEnabled ? TRUE : FALSE));
    if (!m_language.empty())
        CHECK_FAILURE(options->put_Language(m_language.c_str()));
    HRESULT hr = CreateCoreWebView2EnvironmentWithOptions(
        subFolder, nullptr, options.Get(),
        Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
            this, &AppWindow::OnCreateEnvironmentCompleted)
            .Get());
```

## <span data-ttu-id="0cd87-114">成员</span><span class="sxs-lookup"><span data-stu-id="0cd87-114">Members</span></span>

#### <span data-ttu-id="0cd87-115">get_IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="0cd87-115">get_IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span> 

<span data-ttu-id="0cd87-116">IsSingleSignOnUsingOSPrimaryAccountEnabled 属性用于使用使用登录的 Windows 帐户在 web 视图中使用 Azure Active Directory （AAD）资源启用单一登录，使用与 Windows 帐户中的登录相关联的 Microsoft 帐户进行单一登录。</span><span class="sxs-lookup"><span data-stu-id="0cd87-116">The IsSingleSignOnUsingOSPrimaryAccountEnabled property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>

> <span data-ttu-id="0cd87-117">公共 HRESULT [get_IsSingleSignOnUsingOSPrimaryAccountEnabled](#get_issinglesignonusingosprimaryaccountenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="0cd87-117">public HRESULT [get_IsSingleSignOnUsingOSPrimaryAccountEnabled](#get_issinglesignonusingosprimaryaccountenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="0cd87-118">默认值为 "已禁用"。</span><span class="sxs-lookup"><span data-stu-id="0cd87-118">Default is disabled.</span></span> <span data-ttu-id="0cd87-119">通用 Windows 平台应用还必须声明 enterpriseCloudSSO[受限功能](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities)才能使单一登录正常工作。</span><span class="sxs-lookup"><span data-stu-id="0cd87-119">Universal Windows Platform apps must also declare enterpriseCloudSSO [restricted capability](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities) for the single sign on to work.</span></span>

#### <span data-ttu-id="0cd87-120">put_IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="0cd87-120">put_IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span> 

<span data-ttu-id="0cd87-121">设置 IsSingleSignOnUsingOSPrimaryAccountEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="0cd87-121">Set the IsSingleSignOnUsingOSPrimaryAccountEnabled property.</span></span>

> <span data-ttu-id="0cd87-122">public HRESULT [put_IsSingleSignOnUsingOSPrimaryAccountEnabled](#put_issinglesignonusingosprimaryaccountenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="0cd87-122">public HRESULT [put_IsSingleSignOnUsingOSPrimaryAccountEnabled](#put_issinglesignonusingosprimaryaccountenabled)(BOOL enabled)</span></span>

