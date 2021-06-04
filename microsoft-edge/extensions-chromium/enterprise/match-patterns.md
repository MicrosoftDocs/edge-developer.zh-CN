---
description: Enterprise Edge (Chromium) 扩展的策略文档。
title: 匹配模式
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: fcb87b62cac063c7663f575fa3d992b187408c28
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461246"
---
<!-- Copyright A. W. Fuchs

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="match-patterns"></a>匹配模式

主机权限和内容脚本匹配基于匹配模式定义的一组 URL。  匹配模式实质上是一个 URL，它以允许的方案开头， (、、或 `http` ，并且可以包含 ' ' `https` `file` `ftp` `*` 字符。  特殊模式 `<all_urls>` 与以允许方案开头的任何 URL 匹配。  每个匹配模式有 3 个部分：  

*   _方案_ — 例如 `http` ， `file` 或 或 `*`  

> [!NOTE]
> 对 `file` URL 的访问不是自动的。  用户必须访问"扩展管理"页，并针对请求它的 `file` 每个扩展选择访问。  

*   `_host_` — 例如， `www.google.com` `*.google.com` 或 `*` ;如果方案是文件，则没有主机部件。  
*   `_path_` 例如， `/*` 、 `/foo*` 或 `/foo/bar` 。  路径必须存在于主机权限中，但始终被视为 `/*` 。  

基本语法：  

```shell
<url-pattern> := <scheme>://<host><path>
<scheme> := '*' | 'http' | 'https' | 'file' | 'ftp'
<host> := '*' | '*.' <any char except '/' and '*'>+
<path> := '/' <any chars>
```  

的含义 `*` 取决于它是位于方案、主机还是路径部分。  如果方案为 `*` ，则它匹配 `http` 或 `https` ，而不是 `file` 或 `ftp` 。  如果主机只是 `*` ，它将匹配任何主机。 如果主机为 `*.hostname` ，则其与指定的主机或任何子域匹配。  在路径部分中，每个 `*` 匹配都匹配 0 个或多个字符。  下表显示了一些有效的模式。  

| 模式 | 它有什么功能 | 匹配 URL 的示例 |  
|:--- |:--- |:--- |  
| `http://*/*` | 匹配使用 http 方案的任何 URL | `http://www.google.com` `http://example.org/foo/bar.html` |  
| `http://*/foo*` | 匹配在任何主机上使用 http 方案的任何 URL，只要路径以 `/foo` | `http://example.com/foo/bar.html` `http://www.google.com/foo` |  
| `https://*.google.com/foo*bar` | 匹配使用 https 方案的任何 URL，位于主机 \(如 、 或 `google.com` `www.google.com` `docs.google.com` `google.com` \) 上，只要路径以 开头和 `/foo` 结尾 `bar` | `https://www.google.com/foo/baz/bar` `https://docs.google.com/foobar` |  
| `http://example.org/foo/bar.html` | 匹配指定的 URL | `http://example.org/foo/bar.html` |  
|`file:///foo*` | 匹配其路径以 开头的任何本地文件 `/foo` | `file:///foo/bar.html` `file:///foo` |  
| `http://127.0.0.1/*` | 匹配使用方案且位于 `http` 主机上的任何 URL `127.0.0.1` | `http://127.0.0.1` `http://127.0.0.1/foo/bar.html` |  
| `*://mail.google.com/*` | 匹配以 或 开头的任何 `http://mail.google.com` `https://mail.google.com` URL。 | `http://mail.google.com/foo/baz/bar` `https://mail.google.com/foobar` |  
| `<all_urls>` | 匹配使用允许方案的任何 URL。 \(请参阅本部分的开头，查看允许的方案列表。\)  | `http://example.org/foo/bar.html` `file:///bar/baz.html` |  

下面是模式匹配的 `_invalid_` 一些示例：

| 错误模式 | 错误的原因 |  
|:--- |:--- |  
| `http://www.foo.com` | 否 `_path_` |  
| `http://*foo/bar` | ' `*` ' in the host can be followed only by a ' ' or ' `.` `/` ' |  
| `http://foo.*.bar/baz` | 如果 ' `*` ' 位于 `_host_` 中，则它必须是第一个字符 |  
| `http:/bar` | 缺少 `_scheme_` 分隔符 \(' `/` ' 应为 `//` "\)  |  
| `foo://*` | 无效 `_scheme_` |  

某些方案并非在所有上下文中都受支持。

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/extensions/match_patterns)。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
