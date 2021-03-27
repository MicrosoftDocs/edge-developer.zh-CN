---
description: 了解如何在清单中声明 API 的权限
title: 在扩展清单中声明 API 权限
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: 987279a8072388d3fd47ee8b7cbf5f9bb3c483e0
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461502"
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
# <a name="declare-api-permissions-in-extension-manifests"></a>在扩展清单中声明 API 权限  

若要使用大部分 `chrome.*` API，扩展必须在清单 `permissions` 中声明 。  您可以使用下表中的权限字符串声明权限，或使用模式来匹配类似的字符串。  如果扩展受到恶意软件的攻击，权限有助于限制扩展。  在安装使用权限警告的扩展之前，可能会向用户显示某些权限。  

如果 API 要求你在清单中声明权限，请查看该 API 的文档以了解所需的权限。  例如，"存储 API"页描述如何声明 `storage` 权限。  

以下代码段概述了如何在清单文件中声明权限。  

```json
"permissions": [
  "tabs",
  "bookmarks",
  "http://www.blogger.com/",
  "http://*.google.com/",
  "unlimitedStorage"
]
```  

下表列出了清单中当前可用的权限字符串以及说明。  

| 权限字符串 | 详细信息 |  
|:--- |:--- |  
| `activeTab` | 请求根据规范向扩展授予 `activeTab` 权限。 |  
| `alarms` | 授予对 API 的扩展 `chrome.alarms` 访问权限。 |  
| `background` | 使 Microsoft Edge 提前启动并延迟关闭，以便扩展的生命周期更长。  如果任何安装的扩展具有权限，Microsoft Edge 将在用户登录到用户计算机后以及用户启动 Microsoft Edge 之前以不明显方式 `background` 运行。  该权限还使 Microsoft Edge 继续运行，即使其最后一个窗口已关闭，直到用户显式退出 `background` Microsoft Edge。  此权限不会影响浏览器中关闭的扩展。  `background`该权限通常在背景页上使用。 |  
| `bookmarks` | 授予对 API 的扩展 `chrome.bookmarks` 访问权限。 |  
| `browsingData` | 授予对 API 的扩展 `chrome.browsingData` 访问权限。 |  
| `certificateProvider` | 授予对 API 的扩展 `chrome.certificateProvider` 访问权限。 |  
| `clipboardRead` | 如果扩展使用 ，则必需 `document.execCommand('paste')` 。 |  
| `clipboardWrite` | 指示扩展使用 `document.execCommand('copy')` 或 `document.execCommand('cut')` 。 |  
| `contentSettings` | 授予对 API 的扩展 `chrome.contentSettings` 访问权限。 |  
| `contextMenus` | 授予对 API 的扩展 `chrome.contextMenus` 访问权限。 |  
| `cookies` | 授予对 API 的扩展 `chrome.cookies` 访问权限。 |  
| `debugger` | 授予对 API 的扩展 `chrome.debugger` 访问权限。 |  
| `declarativeContent` | 授予对 API 的扩展 `chrome.declarativeContent` 访问权限。 |  
| `declarativeNetRequest` | 授予对 API 的扩展 `chrome.declarativeNetRequest` 访问权限。 |  
| `declarativeNetRequestFeedback` | 授予对 API 内事件和方法的扩展访问权限 `chrome.declarativeNetRequest` ，这将返回有关匹配的声明性规则的信息。 |  
| `declarativeWebRequest` | 授予对 API 的扩展 `chrome.declarativeWebRequest` 访问权限。 |  
| `desktopCapture` | 授予对 API 的扩展 `chrome.desktopCapture` 访问权限。 |  
| `documentScan` | 授予对 API 的扩展 `chrome.documentScan` 访问权限。 |  
| `downloads` | 授予对 API 的扩展 `chrome.downloads` 访问权限。 |  
| `enterprise.deviceAttributes` | 授予对 API 的扩展 `chrome.enterprise.deviceAttributes` 访问权限。 |  
| `enterprise.hardwarePlatform` | 授予对 API 的扩展 `chrome.enterprise.hardwarePlatform` 访问权限。 |  
| `enterprise.networkingAttributes` | 授予对 API 的扩展 `chrome.enterprise.networkingAttributes` 访问权限。 |  
| `enterprise.platformKeys` | 授予对 API 的扩展 `chrome.enterprise.platformKeys` 访问权限。 |  
| `experimental` | 如果扩展使用任意 `chrome.experimental.*` API，则必需。 |  
| `fileBrowserHandler` | 授予对 API 的扩展 `chrome.fileBrowserHandler` 访问权限。 |  
| `fileSystemProvider` | 授予对 API 的扩展 `chrome.fileSystemProvider` 访问权限。 |  
| `fontSettings` | 授予对 API 的扩展 `chrome.fontSettings` 访问权限。 |  
| `geolocation` | 允许扩展使用地理位置 API，而不提示用户授予权限。 |  
| `history` | 授予对 API 的扩展 `chrome.history` 访问权限。 |  
| `identity` | 授予对 API 的扩展 `chrome.identity` 访问权限。 |  
| `idle` | 授予对 API 的扩展 `chrome.idle` 访问权限。 |  
| `loginState` | 授予对 API 的扩展 `chrome.loginState` 访问权限。 |  
| `management` | 授予对 API 的扩展 `chrome.management` 访问权限。 |  
| `nativeMessaging` | 授予对本机消息传递 API 的扩展访问权限。 |  
| `notifications` | 授予对 API 的扩展 `chrome.notifications` 访问权限。 |  
| `pageCapture` | 授予对 API 的扩展 `chrome.pageCapture` 访问权限。 |  
| `platformKeys` | 授予对 API 的扩展 `chrome.platformKeys` 访问权限。 |  
| `power` | 授予对 API 的扩展 `chrome.power` 访问权限。 |  
| `printerProvider` | 授予对 API 的扩展 `chrome.printerProvider` 访问权限。 |  
| `printing` | 授予对 API 的扩展 `chrome.printing` 访问权限。 |  
| `printingMetrics` | 授予对 API 的扩展 `chrome.printingMetrics` 访问权限。 |  
| `privacy` | 授予对 API 的扩展 `chrome.privacy` 访问权限。 |  
| `processes` | 授予对 API 的扩展 `chrome.processes` 访问权限。 |  
| `proxy` | 授予对 API 的扩展 `chrome.proxy` 访问权限。 |  
| `scripting` | 授予对 API 的扩展 `chrome.scripting` 访问权限。 |  
| `search` | 授予对 API 的扩展 `chrome.search` 访问权限。 |  
| `sessions` | 授予对 API 的扩展 `chrome.sessions` 访问权限。 |  
| `signedInDevices` | 授予对 API 的扩展 `chrome.signedInDevices` 访问权限。 |  
| `storage` | 授予对 API 的扩展 `chrome.storage` 访问权限。 |  
| `system.cpu` | 授予对 API 的扩展 `chrome.system.cpu` 访问权限。 |  
| `system.display` | 授予对 API 的扩展 `chrome.system.display` 访问权限。 |  
| `system.memory` | 授予对 API 的扩展 `chrome.system.memory` 访问权限。 |  
| `system.storage` | 授予对 API 的扩展 `chrome.system.storage` 访问权限。 |  
| `tabCapture` | 授予对 API 的扩展 `chrome.tabCapture` 访问权限。 |  
| `tabGroups` | 授予对 API 的扩展 `chrome.tabGroups` 访问权限。 |  
| `tabs` | 向扩展授予对可能由多个 API（包括 和 ）使用的对象的特权 `Tab` 字段 `chrome.tabs` 的访问权限 `chrome.windows` 。  在许多情况下，扩展无需声明使用这些 `tabs` API 的权限。 |  
| `topSites` | 授予对 API 的扩展 `chrome.topSites` 访问权限。 |  
| `tts` | 授予对 API 的扩展 `chrome.tts` 访问权限。 |  
| `ttsEngine` | 授予对 API 的扩展 `chrome.ttsEngine` 访问权限。 |  
| `unlimitedStorage` | 提供用于存储客户端数据（如数据库和本地存储文件）的无限制配额。  如果没有此权限，扩展将限制为 5 MB 的本地存储。 |  
| `vpnProvider` | 授予对 API 的扩展 `chrome.vpnProvider` 访问权限。 |  
| `wallpaper` | 授予对 API 的扩展 `chrome.wallpaper` 访问权限。 |  
| `webNavigation` | 授予对 API 的扩展 `chrome.webNavigation` 访问权限。 |  
| `webRequest` | 授予对 API 的扩展 `chrome.webRequest` 访问权限。 |  
| `webRequestBlocking` | 如果扩展使用 API 阻止 `chrome.webRequest` 请求，此为必需项。 |  

<!-- links -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/docs/extensions/mv3/declare_permissions/)。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
