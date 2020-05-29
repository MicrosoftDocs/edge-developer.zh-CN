---
description: 发出 HTTP 请求时引发的事件。
title: WebResourceRequestedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 79cff0d8fd68e3b5747008f343b5b46fb8093013
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562555"
---
# WebResourceRequestedEvent 对象

发出 HTTP 请求时引发的事件。

## 属性

### args

有关资源请求的信息。 这是[WebViewControlWebResourceRequestedEventArgs 的网站](/uwp/api/windows.web.ui.webviewcontrolwebresourcerequestedeventargs)。

此属性为只读。

```js
var args = webResourceRequestedEventArgs.args;
var request = args.request;
```

#### 属性值
类型：**任何**

