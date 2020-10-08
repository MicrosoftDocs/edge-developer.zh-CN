---
description: 查找有关受支持的清单键以及其已知问题/Chrome 不兼容的信息。
title: 扩展-支持的清单键
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: deeff12251d25efaed1b40c98594c616a0d9c99a
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563330"
---
# 支持的清单密钥  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

每个扩展都具有一个 JSON 格式的清单文件，名为 "manifest.js"。 此文件提供扩展的重要信息，范围从其名称到其权限。 除非在下面的注释中指定，否则 Microsoft Edge 清单属性将遵循与 Chrome 相同的实现。

下面是 [Microsoft EDGE JSON 清单文件](./supported-manifest-keys/json-manifest-example.md)的示例。

## 所需密钥

需要以下注册表项：

密钥 | 已知问题 | Chrome 不兼容
:------------ | :------------- | :--------------
[授权](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/author)  | | 
[name](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/name) | | |
[version](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/version) | | |

## 推荐的密钥

建议使用以下注册表项：

密钥 | 已知问题 | Chrome 不兼容
:------------ | :------------- | :--------------
browser_specific_settings | | 指示浏览器中的扩展的首选状态。 在将来的版本中，浏览器可能或不会根据因素（如分机的声誉）或用户地址栏中已有的按钮的总数，选择在将来的版本中尊重它。 这可用于指示图标的默认位置 `browserAction` 。 </br></br> `"browser_specific_settings": {`</br>&nbsp;&nbsp;&nbsp;&nbsp;`"edge": {`</br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"browser_action_next_to_addressbar": true`</br>&nbsp;&nbsp;&nbsp;&nbsp;`}`</br>`}` </br></br> 在 Chrome 中不受支持。|
[default_locale](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/default_locale)| | |
[description](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/description) | | |
[图标](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/icons) | | |
[manifest_version](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/manifest_version) | | Microsoft Edge 中当前已被忽略。



## browser_action 或 page_action 键

您只能包括下列键之一 (或 none) ：

密钥 | 已知问题 | Chrome 不兼容
:------------ | :------------- | :--------------
[browser_action](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/browser_action)  | | Microsoft Edge 不支持以下语法：  `browser_action : {"default_icon" : "icon.png" }`   <br/>必须指定图标的大小。 <br/>首选大小：20px、25px、30px、40px。 <br/> 其他受支持的大小：19px、35px、38px。|
[page_action](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/page_action) | | Microsoft Edge 不支持以下语法：  `page_action : {"default_icon" : "icon.png" }`   <br/>必须指定图标的大小。 <br/>首选大小：20px、25px、30px、40px。 <br/>其他受支持的大小：19px、35px、38px。|

## 可选键

以下键是可选的：

密钥 | 已知问题 | Chrome 不兼容
:------------ | :------------- | :--------------
[背景](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/background) | | Persistent 是 Microsoft Edge 的必填字段。
[content_scripts](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/content_scripts)  | | |
[content_security_policy](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/content_security_policy)  | 页面的内容安全策略将阻止内容脚本中的 websocket，从而生成未定义的异常。 | Microsoft Edge 扩展目前仅支持 [默认策略限制](https://developer.mozilla.org/Add-ons/WebExtensions/Content_Security_Policy#Default_content_security_policy)： `script-src 'self'; object-src 'self'` |
[incognito](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/incognito) | | | 
key  | | |
options_page | | |
[授权](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/permissions)  | | |
short_name  | | |
[web_accessible_resources](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/web_accessible_resources) | | |

### 支持的权限
以下 [权限](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/permissions) 受支持：


| 权限         | 描述                                                                                                                                                                                                                                                                         |
|:-------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \ <all_urls \ >       | 允许背景和内容脚本与具有额外 [权限](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/permissions#Host_permissions)的所有网页交互。                                                                                  |
| contextMenus       | 提供对 `contextMenus` API 的访问权限。 这允许将项目添加到 Microsoft Edge 的上下文菜单。                                                                                                                                                                                     |
| Cookie            | 提供对 API 的访问权限 `cookies` 。 这支持查询和修改 cookie 以及在更改时收到通知。                                                                                                                                                           |
| 地理位置        | 允许扩展使用 HTML5 `geolocation` API，而不提示用户权限。                                                                                                                                                                                   |
| 着               | 提供对 API 的访问权限 `idle` 。 这样就可以检测到计算机的空闲状态何时更改。                                                                                                                                                                                    |
| 存储            | 提供对 API 的访问权限 `storage` 。 这将允许存储、检索和跟踪对用户数据所做的更改。                                                                                                                                                                             |
| 选项卡               | 提供对 API 的访问权限 `tabs` ，以便与浏览器的选项卡系统交互。 这允许在浏览器中创建、修改和重新排列选项卡，包括与每个选项卡相关联的 Url。                                                                                       |
| unlimitedStorage   | 允许 [存储的本地存储](https://developer.mozilla.org/Add-ons/WebExtensions/API/storage/local) (空间不受限制，具体取决于系统资源) ，而不是5mb。 根据系统资源) ，每个键值对的 "最大存储量" 也从5MB 增加到 " (无限"。 |
| webNavigation      | 提供对 API 的访问权限 `webNavigation` 。 这允许接收有关导航请求状态的通知。                                                                                                                                                              |
| webRequest         | 提供对 API 的访问权限 `webRequest` 。 这允许观察和分析流量，以及截获、阻止或修改正在进行的请求。                                                                                                                               |
| webRequestBlocking | 如果扩展 `webRequest` 在阻止方式中使用 API，则为必需。                                                                                                                                                                                                           |

'""'
