---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2ExperimentalEnvironmentOptions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalEnvironmentOptions
ms.openlocfilehash: ba91056fa6d2e6cf9e7da18202fb3c74d7deb827
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010241"
---
# <span data-ttu-id="a1052-104">0.9.579-接口 ICoreWebView2ExperimentalEnvironmentOptions</span><span class="sxs-lookup"><span data-stu-id="a1052-104">0.9.579 - interface ICoreWebView2ExperimentalEnvironmentOptions</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalEnvironmentOptions
  : public IUnknown
```

<span data-ttu-id="a1052-105">用于创建 WebView2 环境的实验选项。</span><span class="sxs-lookup"><span data-stu-id="a1052-105">Experimental options used to create WebView2 Environment.</span></span>

## <span data-ttu-id="a1052-106">摘要</span><span class="sxs-lookup"><span data-stu-id="a1052-106">Summary</span></span>

 <span data-ttu-id="a1052-107">成员</span><span class="sxs-lookup"><span data-stu-id="a1052-107">Members</span></span>                        | <span data-ttu-id="a1052-108">描述</span><span class="sxs-lookup"><span data-stu-id="a1052-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a1052-109">get_IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="a1052-109">get_IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span>](#get_issinglesignonusingosprimaryaccountenabled) | <span data-ttu-id="a1052-110">IsSingleSignOnUsingOSPrimaryAccountEnabled 属性用于在使用 windows 帐户登录的 Microsoft 帐户中使用已登录的 Windows 帐户在 web 站点内使用已登录的 Windows 帐户进行单一)  (登录，并使用与 Windows 帐户中的登录相关联的 Microsoft 帐户在 web 站点上使用单一登录来启用单一登录。</span><span class="sxs-lookup"><span data-stu-id="a1052-110">The IsSingleSignOnUsingOSPrimaryAccountEnabled property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>
[<span data-ttu-id="a1052-111">put_IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="a1052-111">put_IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span>](#put_issinglesignonusingosprimaryaccountenabled) | <span data-ttu-id="a1052-112">设置 IsSingleSignOnUsingOSPrimaryAccountEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="a1052-112">Set the IsSingleSignOnUsingOSPrimaryAccountEnabled property.</span></span>

<span data-ttu-id="a1052-113">默认实现在 WebView2ExperimentalEnvironmentOptions 中提供。</span><span class="sxs-lookup"><span data-stu-id="a1052-113">A default implementation is provided in WebView2ExperimentalEnvironmentOptions.h.</span></span>

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

## <span data-ttu-id="a1052-114">成员</span><span class="sxs-lookup"><span data-stu-id="a1052-114">Members</span></span>

#### <span data-ttu-id="a1052-115">get_IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="a1052-115">get_IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span> 

<span data-ttu-id="a1052-116">IsSingleSignOnUsingOSPrimaryAccountEnabled 属性用于在使用 windows 帐户登录的 Microsoft 帐户中使用已登录的 Windows 帐户在 web 站点内使用已登录的 Windows 帐户进行单一)  (登录，并使用与 Windows 帐户中的登录相关联的 Microsoft 帐户在 web 站点上使用单一登录来启用单一登录。</span><span class="sxs-lookup"><span data-stu-id="a1052-116">The IsSingleSignOnUsingOSPrimaryAccountEnabled property is used to enable single sign on with Azure Active Directory (AAD) resources inside WebView using the logged in Windows account and single sign on with web sites using Microsoft account associated with the login in Windows account.</span></span>

> <span data-ttu-id="a1052-117">公共 HRESULT [get_IsSingleSignOnUsingOSPrimaryAccountEnabled](#get_issinglesignonusingosprimaryaccountenabled) (BOOL \* 已启用) </span><span class="sxs-lookup"><span data-stu-id="a1052-117">public HRESULT [get_IsSingleSignOnUsingOSPrimaryAccountEnabled](#get_issinglesignonusingosprimaryaccountenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="a1052-118">默认值为 "已禁用"。</span><span class="sxs-lookup"><span data-stu-id="a1052-118">Default is disabled.</span></span> <span data-ttu-id="a1052-119">通用 Windows 平台应用还必须声明 enterpriseCloudSSO [受限功能](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities) 才能使单一登录正常工作。</span><span class="sxs-lookup"><span data-stu-id="a1052-119">Universal Windows Platform apps must also declare enterpriseCloudSSO [restricted capability](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities) for the single sign on to work.</span></span>

#### <span data-ttu-id="a1052-120">put_IsSingleSignOnUsingOSPrimaryAccountEnabled</span><span class="sxs-lookup"><span data-stu-id="a1052-120">put_IsSingleSignOnUsingOSPrimaryAccountEnabled</span></span> 

<span data-ttu-id="a1052-121">设置 IsSingleSignOnUsingOSPrimaryAccountEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="a1052-121">Set the IsSingleSignOnUsingOSPrimaryAccountEnabled property.</span></span>

> <span data-ttu-id="a1052-122">已启用 (BOOL 的公共 HRESULT [put_IsSingleSignOnUsingOSPrimaryAccountEnabled](#put_issinglesignonusingosprimaryaccountenabled)) </span><span class="sxs-lookup"><span data-stu-id="a1052-122">public HRESULT [put_IsSingleSignOnUsingOSPrimaryAccountEnabled](#put_issinglesignonusingosprimaryaccountenabled)(BOOL enabled)</span></span>

