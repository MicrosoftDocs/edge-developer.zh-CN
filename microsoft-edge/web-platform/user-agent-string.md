---
description: 此页面提供有关 Microsoft Edge 用户代理字符串的文档
title: Microsoft Edge 用户代理字符串
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、兼容性、web 平台、用户代理字符串、ua 字符串、ua 替代
ms.openlocfilehash: 73401219b7708a739292a46b6131fe40765e9c8c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564599"
---
# Microsoft Edge 用户代理字符串（桌面）  

用户代理 \ （UA \）字符串可用于检测特定操作系统上使用的是哪个版本的浏览器。  与其他浏览器一样，在 `User-Agent` 向网站发出请求时，Microsoft Edge 将在 HTTP 标头中包含此信息。  也可以通过查询的值来通过 JavaScript 访问它 `navigator.userAgent` 。  

Microsoft 建议在任何可能的情况下，web 开发人员使用[功能检测](https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection)来改进代码可维护性、减少代码 fragility 并消除将来的 UA 字符串更新时代码破坏的风险。  

对于功能检测不适用且必须使用 UA 检测的情况，桌面上的 Microsoft Edge UA 的格式如下所示：

`User-Agent`请求标头采用以下格式：

```http
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43
``` 

返回值的 `navigator.userAgent` 格式如下所示：

```javascript
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43"
```  

根据正在使用的操作系统更改平台标识符，并且版本号也会随着时间的推移而递增。  此格式与 Chromium UA （ `Edg` 在结尾处添加新标记）相同。  Microsoft 选择该 `Edg` 令牌以避免使用字符串时可能导致的兼容性问题，该字符串由 `Edge` 基于 EdgeHTML 的 Microsoft Edge 版本所使用。  `Edg`令牌也与 iOS 和 Android 上使用的[现有令牌](https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer/)一致。

## 将 UA 字符串映射到浏览器名称
现在，将 UA 字符串标记映射到易于使用的易于使用的浏览器名称，以便在代码中使用。 将新令牌映射 `Edg` 到浏览器名称时，Microsoft 建议使用与旧版 Microsoft Edge 使用的开发人员不同的名称，以避免意外应用不适用于基于 Chromium 的浏览器的任何旧版解决方法。

## 用户代理覆盖  

有时，网站无法识别 Microsoft Edge UA 的更新版本。  因此，该网站的一组功能可能无法正常工作。  当 Microsoft 收到有关这些类型的问题的通知时，将联系和了解有关已更新的 UA 的网站所有者。  

网站经常需要一些时间来更新和测试 UA 检测逻辑，以解决 Microsoft 向网站所有者报告的问题。  在这些情况下，Microsoft 将在我们的 Beta 和稳定通道中使用 UA 替代列表来最大程度地提高访问这些网站的用户的兼容性。  替代将指定 Microsoft Edge 应发送的新 UA 值，而不是特定网站的默认 UA。  通过导航到 `edge://compat/useragent` Microsoft Edge 的 Beta 和稳定通道中，你可以查看当前正在应用的 UA 替代的列表。 

我们的 "无通道" 和 "开发渠道" 当前不会接收 UA 重写，以便 web 开发人员可以轻松地在其网站上再现由默认的 Microsoft Edge UA 导致的问题。  如果由于某种原因，你需要能够在 Microsoft Edge 的 Beta 或稳定通道中禁用 UA 替代，你可以使用以下命令行参数运行 Microsoft Edge 可执行文件：  

```shell
--disable-domain-action-user-agent-override
```  
