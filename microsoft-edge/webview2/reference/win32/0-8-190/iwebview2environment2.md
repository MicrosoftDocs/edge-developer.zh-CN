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
# 0.8.355-接口 IWebView2Environment2 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

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

