---
description: 发出 HTTP 请求时引发的事件。
title: WebResourceRequestedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 3d2bb54cc5d60aec5391f0e3fdd427c8ba8a3dab
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10751980"
---
# WebResourceRequestedEvent 对象  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

发出 HTTP 请求时引发的事件。  

## 属性  

### args  

有关资源请求的信息。  这是[WebViewControlWebResourceRequestedEventArgs 的网站](/uwp/api/windows.web.ui.webviewcontrolwebresourcerequestedeventargs)。  

此属性为只读。  

```javascript
var args = webResourceRequestedEventArgs.args;
var request = args.request;
```  

#### 属性值  

类型：**任何**  
