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
ms.openlocfilehash: 00b19d1174a5d5ac643a04038ecdd60c82211194
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653058"
---
# interface IWebView2Environment2 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface IWebView2Environment2
  : public IWebView2Environment
```

由环境对象实现的其他功能。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_BrowserVersionInfo](#get_browserversioninfo) | 当前[IWebView2Environment](IWebView2Environment.md)的浏览器版本信息，包括频道名称（如果不是稳定频道）。

有关详细信息，请参阅[IWebView2Environment](IWebView2Environment.md)界面。 你可以从实现[IWebView2Environment](IWebView2Environment.md)的对象中为此接口执行 QueryInterface。

## 成员

#### get_BrowserVersionInfo 

当前[IWebView2Environment](IWebView2Environment.md)的浏览器版本信息，包括频道名称（如果不是稳定频道）。

> 公共 HRESULT [get_BrowserVersionInfo](#get_browserversioninfo)（LPWSTR * versionInfo）

这与 GetWebView2BrowserVersionInfo API 的格式相匹配。 信道名称为 "beta"、"dev" 和 "未设备"。

```cpp
        wil::unique_cotaskmem_string version_info;
        m_webViewEnvironment->get_BrowserVersionInfo(&version_info);
        MessageBox(
            m_mainWindow, version_info.get(), L"Browser Version Info After WebView Creation",
            MB_OK);
```

