---
description: 查找有关受支持的清单密钥及其已知问题/Chrome 不兼容的信息。
title: 扩展 - 支持的清单键
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f8413193ddb834eb7e31e4101c2b027c48bc501d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232716"
---
# 支持的清单密钥  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

每个扩展都有一个 JSON 格式的清单文件，manifest.js打开。 此文件提供扩展名（从名称到权限）的重要信息。 除非在下面说明中指定，否则 Microsoft Edge 清单属性遵循与 Chrome 相同的实现。

下面是 Microsoft Edge [JSON 清单文件的示例](./supported-manifest-keys/json-manifest-example.md)。

## 所需键

需要以下键：

密钥 | 已知问题 | Chrome 不兼容
:------------ | :------------- | :--------------
[author](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/author)  | | 
[name](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/name) | | |
[version](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/version) | | |

## 建议的键

建议使用以下键：

密钥 | 已知问题 | Chrome 不兼容
:------------ | :------------- | :--------------
browser_specific_settings | | 指示扩展在浏览器中的首选状态。 浏览器可能会选择或可能不会选择在将来版本中遵守它，具体取决于诸如扩展信誉或用户地址栏中已有的按钮总数等因素。 这可用于指示图标的默认 `browserAction` 位置。 </br></br> `"browser_specific_settings": {`</br>&nbsp;&nbsp;&nbsp;&nbsp;`"edge": {`</br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"browser_action_next_to_addressbar": true`</br>&nbsp;&nbsp;&nbsp;&nbsp;`}`</br>`}` </br></br> 在 Chrome 中不受支持。|
[default_locale](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/default_locale)| | |
[description](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/description) | | |
[图标](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/icons) | | |
[manifest_version](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/manifest_version) | | 当前在 Microsoft Edge 中被忽略。



## browser_action或page_action键

只能包括以下键之一 (或不包含) ：

密钥 | 已知问题 | Chrome 不兼容
:------------ | :------------- | :--------------
[browser_action](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/browser_action)  | | Microsoft Edge 不支持以下语法：  `browser_action : {"default_icon" : "icon.png" }`   <br/>必须指定图标的大小。 <br/>首选大小：20px、25px、30px、40px。 <br/> 其他支持的大小：19px、35px、38px。|
[page_action](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/page_action) | | Microsoft Edge 不支持以下语法：  `page_action : {"default_icon" : "icon.png" }`   <br/>必须指定图标的大小。 <br/>首选大小：20px、25px、30px、40px。 <br/>其他支持的大小：19px、35px、38px。|

## 可选键

以下键是可选的：

密钥 | 已知问题 | Chrome 不兼容
:------------ | :------------- | :--------------
[背景](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/background) | | 永久是 Microsoft Edge 的必填字段。
[content_scripts](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/content_scripts)  | | |
[content_security_policy](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/content_security_policy)  | 页面的内容安全策略会阻止内容脚本中的 Websockets，从而生成未定义的异常。 | Microsoft Edge 扩展当前仅支持 [默认策略限制](https://developer.mozilla.org/Add-ons/WebExtensions/Content_Security_Policy#Default_content_security_policy)： `script-src 'self'; object-src 'self'` |
[incognito](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/incognito) | | | 
key  | | |
options_page | | |
[permissions](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/permissions)  | | |
short_name  | | |
[web_accessible_resources](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/web_accessible_resources) | | |

### 支持的权限
支持 [以下](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/manifest.json/permissions) 权限：


| 权限         | 描述                                                                                                                                                                                                                                                                         |
|:-------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \<all_urls\>       | 允许背景和内容脚本使用额外权限与所有 [网页交互](https://developer.mozilla.org/Add-ons/WebExtensions/manifest.json/permissions#Host_permissions)。                                                                                  |
| contextMenus       | 授予对 `contextMenus` API 的访问权限。 这允许向 Microsoft Edge 的上下文菜单添加项目。                                                                                                                                                                                     |
| Cookie            | 授予对 `cookies` API 的访问权限。 这允许查询和修改 Cookie，以及当 Cookie 更改时收到通知。                                                                                                                                                           |
| 地理位置        | 允许扩展使用 HTML5 `geolocation` API，而不提示用户授予权限。                                                                                                                                                                                   |
| idle               | 授予对 `idle` API 的访问权限。 这样，可以检测计算机空闲状态何时更改。                                                                                                                                                                                    |
| 存储            | 授予对 `storage` API 的访问权限。 这允许存储、检索和跟踪用户数据更改。                                                                                                                                                                             |
| 选项卡               | 授予对 `tabs` API 的访问权限，以与浏览器的选项卡系统交互。 这允许创建、修改和重新排列浏览器中的选项卡，包括与每个选项卡关联的 URL。                                                                                       |
| unlimitedStorage   | 允许 [storage.local](https://developer.mozilla.org/Add-ons/WebExtensions/API/storage/local) 具有无限制的存储 (取决于系统资源) 5MB。 每个键值对的最大存储量也从 5 MB 增加到无限制 (取决于系统资源) 。 |
| webNavigation      | 授予对 `webNavigation` API 的访问权限。 这允许接收有关导航请求状态的通知。                                                                                                                                                              |
| webRequest         | 授予对 `webRequest` API 的访问权限。 这允许观察和分析流量，以及截获、阻止或修改正在处理的请求。                                                                                                                               |
| webRequestBlocking | 如果扩展以阻止方式 `webRequest` 使用 API，则必需。                                                                                                                                                                                                           |

'""'
