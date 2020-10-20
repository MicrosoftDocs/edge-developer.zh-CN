---
description: 构建 Microsoft Edge 扩展时使用的受支持 Api 的列表。
title: Microsoft Edge 扩展支持的 Api
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘-chromium，扩展开发，浏览器扩展，加载项，扩展 api，开发人员，web 开发
ms.openlocfilehash: 868473393da6cefbf146fb7acd6c9816903bd253
ms.sourcegitcommit: af91bfc3e6d8afc51f0fbbc0fe392262f424225c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2020
ms.locfileid: "11120388"
---
# Microsoft Edge 扩展支持的 Api

下表提供了在为 Microsoft Edge \ (Chromium \ ) 浏览器构建扩展时可以使用的 Api 列表。

| API                                   | 描述                                            
|---------------------------------------|----------------------------------------------------------|
| [闹钟](https://developer.chrome.com/extensions/alarms) | 安排代码定期运行或在将来的指定时间运行。 |
| [书签](https://developer.chrome.com/extensions/bookmarks) | 创建、组织和操作书签。 |
| [browserAction](https://developer.chrome.com/extensions/browserAction) | 使用浏览器操作将图标放置在 Microsoft Edge 中的工具栏上。 你还可以使用浏览器操作添加工具提示、锁屏提醒或弹出窗口。 |
| [browsingData](https://developer.chrome.com/extensions/browsingData) | 从用户的本地配置文件中删除浏览数据。 |
| [命令](https://developer.chrome.com/extensions/commands) | 添加在扩展中触发操作的键盘快捷方式。 例如，用于打开浏览器或将命令发送到扩展的操作。 |
| [contentSettings](https://developer.chrome.com/extensions/contentSettings) | 通常，内容设置允许你自定义每个网站（而非全局）的 Microsoft Edge 的行为。 更改控制网站是否可以使用 cookie、JavaScript 和插件等功能的设置。 |
| [contextMenus](https://developer.chrome.com/extensions/contextMenus) | 将项目添加到 Microsoft Edge 中的上下文菜单。 菜单项可能会应用于不同的对象，例如图像、超链接和页面。 |
| [Cookie](https://developer.chrome.com/extensions/cookies) | 查询和修改 cookie，并在其发生更改时接收通知。 |
| [调试器](https://developer.chrome.com/extensions/debugger) | 附加到一个或多个选项卡以检测网络交互、调试 JavaScript、更改 DOM、更改 CSS 等。 使用调试程序 tabId 为 sendCommand 提供目标选项卡，并通过 tabId 从 onEvent 回调路由事件。 |
| [declarativeContent](https://developer.chrome.com/extensions/declarativeContent) | 根据页面的内容执行操作，而不需要读取页面内容的权限。 |
| [declarativeNetRequest](https://developer.chrome.com/extensions/declarativeNetRequest) | 通过指定声明性规则来阻止或修改网络请求，从而提供更多隐私。 允许扩展在不截获请求和查看内容的情况下修改网络请求。 |
| [desktopCapture](https://developer.chrome.com/extensions/desktopCapture) | 捕获屏幕、单个窗口或选项卡的内容。 |
| [devtools.inspectedWindow](https://developer.chrome.com/extensions/devtools_inspectedWindow) | 与已检查的窗口交互。 例如，获取页面的选项卡 ID，计算代码，重新装入页面，或获取页面上的资源。 |
| [devtools 网络](https://developer.chrome.com/extensions/devtools_network) | 检索有关 "网络" 面板中的开发人员工具显示的网络请求的信息。 |
| [devtools](https://developer.chrome.com/extensions/devtools.panels) | 通过创建自己的面板、访问现有面板或添加边栏，将扩展集成到开发人员工具窗口 UI 中。 |
| [downloads](https://developer.chrome.com/extensions/downloads) | 以编程方式启动、监视、操作和搜索下载。 |
| [hardwarePlatform](https://developer.chrome.com/extensions/enterprise.hardwarePlatform) | 获取运行浏览器的硬件平台的制造商和型号。 此 API 仅适用于由企业策略安装的扩展。 |
| [事件](https://developer.chrome.com/extensions/events) | 在发生有趣事件时引发事件以通知您的公共类型。 |
| [线](https://developer.chrome.com/extensions/extension) | 任何扩展页都可以使用此 API 的实用工具。 它包括对在邮件传递中介绍的扩展和内容脚本之间交换消息的支持。 |
| [extensionTypes](https://developer.chrome.com/extensions/extensionTypes) | 包含 Microsoft Edge 扩展的类型声明。 |
| [fontSettings](https://developer.chrome.com/extensions/fontSettings) | 管理 Microsoft Edge 中的字体设置。 |
| [历史记录](https://developer.chrome.com/extensions/history) | 与访问过的页面的浏览器记录进行交互。 可以在浏览器历史记录中添加、删除或查询 Url。 若要用自己的版本替代 "历史记录" 页面，请参阅覆盖页面。 |
| [国际化](https://developer.chrome.com/extensions/i18n) | 在整个应用或扩展中实现国际化。 |
| [着](https://developer.chrome.com/extensions/idle) | 检测计算机的空闲状态何时更改。 |
| [层](https://developer.chrome.com/extensions/management) | 管理已安装或正在运行的扩展的列表。 这对于替代内置的新选项卡页的扩展非常有用。 |
| [通知](https://developer.chrome.com/extensions/notifications) | 使用模板创建丰富的通知，并将其显示在系统托盘中。 |
| [omnibox](https://developer.chrome.com/extensions/omnibox) | 在 Microsoft Edge 地址栏中注册关键字，也称为 omnibox。 |
| [pageAction](https://developer.chrome.com/extensions/pageAction) | 将图标添加到 "Microsoft Edge" 工具栏，位于地址栏右侧。 页面操作是可以在当前页面上执行的操作，并且不适用于所有页面。 "页面操作" 在未激活时显示为灰色。 |
| [pageCapture](https://developer.chrome.com/extensions/pageCapture) | 将选项卡保存为 MHTML 文件。|
| [授权](https://developer.chrome.com/extensions/permissions) | 在运行时（而不是在安装时）检索声明的可选权限。 你可以使用此 API 显示你的用户所需和批准的权限。 |
| [电源](https://developer.chrome.com/extensions/power) | 替代系统的电源管理功能。 |
| [printerProvider](https://developer.chrome.com/extensions/printerProvider) | 使用事件查询打印机、其功能和提交打印作业。 |
| [隐私](https://developer.chrome.com/extensions/privacy) | Microsoft Edge 中的控制影响用户隐私的功能。 此 API 依赖于 `EdgeSetting` `types` 获取和设置 Microsoft Edge 配置的原型。 |
| [服务器](https://developer.chrome.com/extensions/proxy) | 管理 Microsoft Edge 的代理设置。 此 API 依赖于 `EdgeSetting` `types` 获取和设置 Microsoft Edge 的代理配置的 api 原型。 |
| [环境](https://developer.chrome.com/extensions/runtime) | 检索背景页，返回有关清单的详细信息，并侦听并响应应用或扩展生命周期中的事件。 你还可以将 Url 的相对路径转换为完全限定的 Url。 |
| [会议](https://developer.chrome.com/extensions/sessions) | 从浏览会话查询和还原选项卡和窗口。 |
| [存储](https://developer.chrome.com/extensions/storage) | 存储、检索和跟踪对用户数据的更改。 |
| [系统内存](https://developer.chrome.com/extensions/system_memory) | `system.memory`API。 |
| [系统存储](https://developer.chrome.com/extensions/system_storage) | 查询有关存储设备的信息。 您也可以在存储设备连接或断开连接时收到通知。 |
| [tabCapture](https://developer.chrome.com/extensions/tabCapture) | 与选项卡媒体流交互。 |
| [选项卡](https://developer.chrome.com/extensions/tabs) | 与浏览器的选项卡系统交互以创建、修改和重新排列选项卡。 |
| [topSites](https://developer.chrome.com/extensions/topSites) | 访问 "新选项卡" 页面上显示的顶级网站（也称为大多数访问过的网站）。 这些网站不包括由用户自定义的快捷方式。 |
| [tts](https://developer.chrome.com/extensions/tts) |  (TTS) 播放合成的文本到语音转换。 |
| [ttsEngine](https://developer.chrome.com/extensions/ttsEngine) | 使用扩展名实现文本到语音 (TTS) 引擎。 注册以使用此 API 的扩展将包含要朗读的 utterances 和其他参数的事件。 然后，扩展可以使用任何可用的 web 技术 synthesize 和输出语音，并将事件发送回调用函数以报告状态。 |
| [类型](https://developer.chrome.com/extensions/types) | Microsoft Edge 的类型声明。 |
| [webNavigation](https://developer.chrome.com/extensions/webNavigation) | 接收有关导航请求状态的通知。 |
| [webRequest](https://developer.chrome.com/extensions/webRequest) | 查看和分析流量。 截取、阻止或修改请求。 |
| [windows](https://developer.chrome.com/extensions/windows) | 与浏览器窗口交互，在浏览器中创建、修改和重新排列窗口。 |



## 不支持的扩展 Api

Microsoft Edge 不支持以下扩展 Api：

* `chrome.gcm`.
* `chrome.identity.getAccounts`.
* `chrome.identity.getAuthToken` -作为备用，你可以使用 `launchWebAuthFlow` 获取 OAuth2 令牌来对用户进行身份验证。
* `chrome.instanceID`.


## 支持的 Api 的其他注意事项

* 用户必须使用 MSA 或 Azure Active Directory 帐户使用 MSA 或 Azure Active Directory 帐户登录到 Microsoft Edge `chrome.identity.getProfileUserInfo` 。 如果用户使用本地 Active Directory 帐户登录到 Microsoft Edge，API 将返回 " `null` 电子邮件" 和 "ID" 值。

* Microsoft Edge 不支持使用 Chrome Web Store 付款的扩展，因为它用于 `identity.getAuthtoken` 请求登录用户的令牌。 这些令牌将发送到基于 REST 的授权 API。 


<!-- links -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 可在 [此处](https://developer.chrome.com/apps/external_extensions)找到原始页面。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
