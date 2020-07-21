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
# interface ICoreWebView2ExperimentalEnvironmentOptions 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalEnvironmentOptions
  : public IUnknown
```

用于创建 WebView2 环境的实验选项。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_IsSingleSignOnUsingOSPrimaryAccountEnabled](#get_issinglesignonusingosprimaryaccountenabled) | IsSingleSignOnUsingOSPrimaryAccountEnabled 属性用于使用使用登录的 Windows 帐户在 web 视图中使用 Azure Active Directory （AAD）资源启用单一登录，使用与 Windows 帐户中的登录相关联的 Microsoft 帐户进行单一登录。
[put_IsSingleSignOnUsingOSPrimaryAccountEnabled](#put_issinglesignonusingosprimaryaccountenabled) | 设置 IsSingleSignOnUsingOSPrimaryAccountEnabled 属性。

默认实现在 WebView2ExperimentalEnvironmentOptions 中提供。

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

## 成员

#### get_IsSingleSignOnUsingOSPrimaryAccountEnabled 

IsSingleSignOnUsingOSPrimaryAccountEnabled 属性用于使用使用登录的 Windows 帐户在 web 视图中使用 Azure Active Directory （AAD）资源启用单一登录，使用与 Windows 帐户中的登录相关联的 Microsoft 帐户进行单一登录。

> 公共 HRESULT [get_IsSingleSignOnUsingOSPrimaryAccountEnabled](#get_issinglesignonusingosprimaryaccountenabled)（已启用 BOOL *）

默认值为 "已禁用"。 通用 Windows 平台应用还必须声明 enterpriseCloudSSO[受限功能](https://docs.microsoft.com/windows/uwp/packaging/app-capability-declarations#restricted-capabilities)才能使单一登录正常工作。

#### put_IsSingleSignOnUsingOSPrimaryAccountEnabled 

设置 IsSingleSignOnUsingOSPrimaryAccountEnabled 属性。

> public HRESULT [put_IsSingleSignOnUsingOSPrimaryAccountEnabled](#put_issinglesignonusingosprimaryaccountenabled)（已启用 BOOL）

