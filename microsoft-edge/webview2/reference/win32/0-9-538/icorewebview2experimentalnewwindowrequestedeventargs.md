---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 1d91bb767045179a5d8de3700f86ff6d92a9ef36
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698578"
---
# interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs 

> [!NOTE]
> 这是使用预发行 SDK 版本0.9.538 随附的实验性 API。

```
interface ICoreWebView2ExperimentalNewWindowRequestedEventArgs
  : public IUnknown
```

Webview.newwindowrequested 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_WindowFeatures](#get_windowfeatures) | 窗口指定的窗口功能。打开通话。

如果 web 视图中的内容请求打开一个新窗口（通过 "打开" （）等），将引发此事件。

## 成员

#### get_WindowFeatures 

窗口指定的窗口功能。打开通话。

> 公共 HRESULT [get_WindowFeatures](#get_windowfeatures)（[ICoreWebView2ExperimentalWindowFeatures](icorewebview2experimentalwindowfeatures.md) * * WindowFeatures）

可将这些功能考虑到新的 web 视图窗口的位置和大小调整。

