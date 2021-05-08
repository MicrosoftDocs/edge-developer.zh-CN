---
description: 此页面提供有关用户代理Microsoft Edge的文档
title: Microsoft Edge用户代理字符串
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， 兼容性， Web 平台， 用户代理字符串， ua 字符串， ua 替代
ms.openlocfilehash: 73401219b7708a739292a46b6131fe40765e9c8c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564599"
---
# Microsoft Edge桌面 (用户代理)   

用户代理 \ (UA\) 字符串可用于检测特定浏览器正在特定操作系统中使用的版本。  与其他浏览器一Microsoft Edge，只要向网站提出请求，就会在 `User-Agent` HTTP 标头中包含此信息。  还可通过查询 的值通过 JavaScript 访问 `navigator.userAgent` 它。  

Microsoft 建议 Web 开发人员尽可能[](https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection)利用功能检测来提高代码可维护性、减少代码错误，并在将来的 UA 字符串更新中消除代码中断的风险。  

对于功能检测不适用且必须使用 UA 检测的情况，Microsoft Edge UA 的格式如下所示：

请求 `User-Agent` 标头的格式如下：

```http
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43
``` 

的返回 `navigator.userAgent` 值采用以下格式：

```javascript
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43"
```  

平台标识符根据所使用的操作系统而更改，版本号也会随着时间推移而递增。  此格式与末尾添加Chromium标记的 UA `Edg` 格式相同。  Microsoft 选择了令牌以避免使用字符串 （由基于 EdgeHTML 的 Microsoft Edge使用）可能导致 `Edg` `Edge` 的兼容性问题。  令牌 `Edg` 还与 iOS[](https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer/)和 Android 上使用的现有令牌一致。

## 将 UA 字符串映射到浏览器名称
将 UA 字符串令牌映射到更可读的浏览器名称以用于代码是当今 Web 上的常见模式。 将新令牌映射到浏览器名称时，Microsoft 建议使用与开发人员用于旧版 Microsoft Edge 的不同名称，以避免意外应用不适用于基于 Chromium 的浏览器的任何旧解决方法。 `Edg`

## 用户代理替代  

有时，网站无法识别更新版本的 Microsoft Edge UA。  因此，该网站的一组功能可能无法正常运行。  当 Microsoft 收到有关这些类型问题的通知时，将联系网站所有者并通知他们有关更新的 UA 的信息。  

网站通常需要一些时间来更新和测试 UA 检测逻辑，以解决 Microsoft 向网站所有者报告的问题。  在这些情况下，Microsoft 在我们的 Beta 和 Stable 渠道中使用 UA 替代列表，以最大限度地提高访问这些网站的用户的兼容性。  替代指定应发送的新 UA Microsoft Edge，而不是特定站点的默认 UA。  通过导航到当前应用的 Beta 和稳定渠道中的 UA 替代列表 `edge://compat/useragent` ，Microsoft Edge。 

我们的 Canary 和 Dev 渠道当前不会收到 UA 覆盖，以便 Microsoft Edge Web 开发人员可以在其中轻松重现由默认 UA 导致的问题。  如果出于某种原因需要能够在 Microsoft Edge 的 Beta 或 Stable 渠道中禁用 UA 覆盖，可以使用以下命令行参数运行 Microsoft Edge 可执行文件：  

```shell
--disable-domain-action-user-agent-override
```  
