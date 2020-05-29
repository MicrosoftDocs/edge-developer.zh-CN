---
description: 适用于 Edge （Chromium）扩展的企业策略文档。
title: 匹配模式
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/05/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: 16f54fcdc127822e89e050c367a681d886b0c8d0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563378"
---
# 匹配模式

主机权限和内容脚本匹配基于由匹配模式定义的一组 Url。  匹配模式实质上是以允许的方案（、、、或）开头的 URL， `http` `https` `file` `ftp` 其中可以包含 " `*` " 个字符。  特殊模式 `<all_urls>` 匹配以允许的方案开头的任何 URL。  每个匹配模式都有3个部分：  

*   _方案_（例如 `http` 或或） `file` `*`  

> [!NOTE]
> 对 `file` url 的访问不是自动的。  用户必须访问 "扩展管理" 页面，并选择为 `file` 请求它的每个扩展进行访问。  

*   `_host_` -例如， `www.google.com` 或 `*.google.com` `*` ; 如果方案为文件，则没有主机部件。  
*   `_path_` -例如、、 `/*` `/foo*` 或 `/foo/bar` 。  该路径必须存在于主机权限中，但始终被视为 `/*` 。  

基本语法：  

```shell
<url-pattern> := <scheme>://<host><path>
<scheme> := '*' | 'http' | 'https' | 'file' | 'ftp'
<host> := '*' | '*.' <any char except '/' and '*'>+
<path> := '/' <any chars>
```  

的含义 `*` 取决于它是属于 "方案"、"主机" 还是 "路径" 部分。  如果方案为 `*` ，则它将匹配 `http` 或 `https` ，而不 `file` `ftp` 是或。  如果主机刚刚如此 `*` ，则它匹配任何主机。 如果主机是 `*.hostname` ，则它与指定的主机或任何子域相匹配。  在 "路径" 部分中，每个 `*` 字符均匹配0个或多个字符。  下表显示了一些有效的模式。  

| 模式 | 用途 | 匹配 Url 的示例 |  
|:--- |:--- |:--- |  
| `http://*/*` | 匹配任何使用 http 方案的 URL | `http://www.google.com` `http://example.org/foo/bar.html` |  
| `http://*/foo*` | 匹配任何主机上任何使用 http 方案的 URL，只要路径开头为 `/foo` | `http://example.com/foo/bar.html` `http://www.google.com/foo` |  
| `https://*.google.com/foo*bar` | 与任何使用 https 方案的 URL 均位于 `google.com` 主机 \ （如 `www.google.com` 、 `docs.google.com` 或 `google.com` \）上，只要路径的开头 `/foo` 和结尾为 `bar` | `https://www.google.com/foo/baz/bar` `https://docs.google.com/foobar` |  
| `http://example.org/foo/bar.html` | 匹配指定的 URL | `http://example.org/foo/bar.html` |  
|`file:///foo*` | 匹配路径以下列路径开头的任何本地文件 `/foo` | `file:///foo/bar.html` `file:///foo` |  
| `http://127.0.0.1/*` | 匹配任何使用该 `http` 方案且位于主机上的 URL `127.0.0.1` | `http://127.0.0.1` `http://127.0.0.1/foo/bar.html` |  
| `*://mail.google.com/*` | 匹配以或开头的任何 `http://mail.google.com` URL `https://mail.google.com` 。 | `http://mail.google.com/foo/baz/bar` `https://mail.google.com/foobar` |  
| `<all_urls>` | 匹配任何使用允许的方案的 URL。 \ （有关允许的方案列表，请参阅本部分的开头部分。） | `http://example.org/foo/bar.html` `file:///bar/baz.html` |  

下面是一些 `_invalid_` 模式匹配的示例：

| 错误模式 | 为什么不正确 |  
|:--- |:--- |  
| `http://www.foo.com` | 否 `_path_` |  
| `http://*foo/bar` | 主机中的 "" `*` 只能后跟 " `.` " 或 " `/` " |  
| `http://foo.*.bar/baz` | 如果 " `*` " 在中 `_host_` ，则必须是第一个字符 |  
| `http:/bar` | 缺少 `_scheme_` 分隔符 \ （' `/` ' 应为 " `//` " \ "） |  
| `foo://*` | 无效 `_scheme_` |  

某些方案在所有上下文中都不受支持。

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 可在[此处](https://developer.chrome.com/extensions/match_patterns/)找到原始页面。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
