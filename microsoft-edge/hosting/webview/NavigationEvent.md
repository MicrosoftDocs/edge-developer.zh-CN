---
description: 包含有关 web 视图导航的信息
title: NavigationEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 785e9646ff400e7ad229046c7030b51420b1d9ad
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752169"
---
# NavigationEvent 对象  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

一个对象，表示在启动导航时激发的事件。  

## 属性  

### uri  

目标的统一资源标识符（URI）。  

此属性为只读。  

```javascript
var uri = NavigationEvent.uri;
```  

#### 属性值  

类型： **DOMString**  
