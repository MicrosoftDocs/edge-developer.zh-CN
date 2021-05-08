---
description: 生成 Microsoft Edge 扩展时使用的受支持 API 列表。
title: Microsoft Edge 扩展支持的 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 扩展 api， 开发人员， Web 开发
ms.openlocfilehash: 20e924b5c973b9ecd433feeb3a772c6d17746369
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398103"
---
# <a name="supported-apis-for-microsoft-edge-extensions"></a>Microsoft Edge 扩展支持的 API

下表提供了在构建 Microsoft Edge \ (Chromium\) 扩展时可以使用的 API 列表。

| API                                   | 说明                                            
|---------------------------------------|----------------------------------------------------------|
| [闹钟](https://developer.chrome.com/extensions/alarms) | 计划代码定期运行或在将来的指定时间运行。 |
| [书签](https://developer.chrome.com/extensions/bookmarks) | 创建、组织和操作书签。 |
| [browserAction](https://developer.chrome.com/extensions/browserAction) | 使用浏览器操作将图标放在 Microsoft Edge 中的工具栏上。 您还可以使用浏览器操作添加工具提示、锁屏提醒或弹出窗口。 |
| [browsingData](https://developer.chrome.com/extensions/browsingData) | 从用户的本地配置文件中删除浏览数据。 |
| [命令](https://developer.chrome.com/extensions/commands) | 添加在扩展中触发操作键盘快捷方式。 例如，打开浏览器或向扩展发送命令的操作。 |
| [contentSettings](https://developer.chrome.com/extensions/contentSettings) | 通常，内容设置允许您在每个站点上自定义 Microsoft Edge 的行为，而不是全局自定义。 更改控制网站是否可以使用 Cookie、JavaScript 和插件等功能的设置。 |
| [contextMenus](https://developer.chrome.com/extensions/contextMenus) | 将项目添加到 Microsoft Edge 中的上下文菜单中。 菜单项可能适用于不同的对象，如图像、超链接和页面。 |
| [Cookie](https://developer.chrome.com/extensions/cookies) | 查询和修改 Cookie，在 Cookie 更改时接收通知。 |
| [调试器](https://developer.chrome.com/extensions/debugger) | 附加到一个或多个选项卡以检测网络交互、调试 JavaScript、更改 DOM、更改 CSS 等。 使用调试器 tabId 通过 sendCommand 定位选项卡，并按 tabId 从 onEvent 回调路由事件。 |
| [declarativeContent](https://developer.chrome.com/extensions/declarativeContent) | 根据页面内容采取操作，而无需读取页面内容的权限。 |
| [declarativeNetRequest](https://developer.chrome.com/extensions/declarativeNetRequest) | 通过指定声明性规则阻止或修改网络请求，提供更多隐私。 允许扩展在不截获请求和查看内容的情况下修改网络请求。 |
| [desktopCapture](https://developer.chrome.com/extensions/desktopCapture) | 捕获屏幕、单个窗口或选项卡的内容。 |
| [devtools.inspectedWindow](https://developer.chrome.com/extensions/devtools_inspectedWindow) | 与检查的窗口交互。  例如，获取页面的选项卡 ID、评估代码、刷新页面或获取页面上的资源。 |
| [devtools.network](https://developer.chrome.com/extensions/devtools_network) | 检索有关"网络"面板中"开发人员工具"显示的网络请求的信息。 |
| [devtools.panels](https://developer.chrome.com/extensions/devtools.panels) | 通过创建自己的面板、访问现有面板或添加边栏，将扩展集成到开发人员工具窗口 UI 中。 |
| [downloads](https://developer.chrome.com/extensions/downloads) | 以编程方式启动、监视、操作和搜索下载。 |
| [enterprise.hardwarePlatform](https://developer.chrome.com/extensions/enterprise.hardwarePlatform) | 获取运行浏览器的硬件平台的制造商和型号。 此 API 仅适用于企业策略安装的扩展。 |
| [事件](https://developer.chrome.com/extensions/events) | API 用于引发事件以在感兴趣的事件发生时通知你的常见类型。 |
| [extension](https://developer.chrome.com/extensions/extension) | 任何扩展页都可以使用此 API 的实用工具。 它包括对在扩展和内容脚本之间交换消息的支持，如消息传递中所述。 |
| [extensionTypes](https://developer.chrome.com/extensions/extensionTypes) | 包含 Microsoft Edge 扩展的类型声明。 |
| [fontSettings](https://developer.chrome.com/extensions/fontSettings) | 在 Microsoft Edge 中管理字体设置。 |
| [历史记录](https://developer.chrome.com/extensions/history) | 与浏览器的已访问页面记录交互。 可以在浏览器历史记录中添加、删除或查询 URL。 若要使用自己的版本替代历史记录页面，请导航到"覆盖页面"。 |
| [i18n](https://developer.chrome.com/extensions/i18n) | 在整个应用或扩展中实现国际化。 |
| [idle](https://developer.chrome.com/extensions/idle) | 检测计算机空闲状态何时更改。 |
| [管理](https://developer.chrome.com/extensions/management) | 管理已安装或正在运行的扩展的列表。 它对于覆盖内置"新建选项卡"页的扩展非常有用。 |
| [通知](https://developer.chrome.com/extensions/notifications) | 使用模板创建丰富的通知，然后将它们显示在系统托盘中。 |
| [omnibox](https://developer.chrome.com/extensions/omnibox) | 在 Microsoft Edge 地址栏中注册关键字，也称为全能框。 |
| [pageAction](https://developer.chrome.com/extensions/pageAction) | 将图标添加到 Microsoft Edge 工具栏的地址栏右侧。 页面操作是可以在当前页面上采取的操作，并不适用于所有页面。 当处于非活动状态时，页面操作显示为灰色。 |
| [pageCapture](https://developer.chrome.com/extensions/pageCapture) | 将选项卡另存为 MHTML 文件。|
| [permissions](https://developer.chrome.com/extensions/permissions) | 在运行时检索声明的可选权限，而不是在安装时检索。 可以使用此 API 向用户显示所需的和已批准的权限。 |
| [电源](https://developer.chrome.com/extensions/power) | 覆盖系统的电源管理功能。 |
| [printerProvider](https://developer.chrome.com/extensions/printerProvider) | 使用事件查询打印机及其功能，并提交打印作业。 |
| [隐私](https://developer.chrome.com/extensions/privacy) | 控制 Microsoft Edge 中影响用户隐私的功能。 此 API 取决于 `EdgeSetting` 获取和设置 Microsoft Edge `types` 配置的原型。 |
| [代理](https://developer.chrome.com/extensions/proxy) | 管理 Microsoft Edge 的代理设置。 此 API 取决于 `EdgeSetting` API 的原型 `types` ，用于获取和设置 Microsoft Edge 的代理配置。 |
| [运行时](https://developer.chrome.com/extensions/runtime) | 检索后台页面，返回有关清单的详细信息，并侦听和响应应用或扩展生命周期中的事件。 您还可以将 URL 的相对路径转换为完全限定的 URL。 |
| [会话](https://developer.chrome.com/extensions/sessions) | 从浏览会话查询和还原选项卡和窗口。 |
| [存储](https://developer.chrome.com/extensions/storage) | 存储、检索和跟踪用户数据更改。 |
| [system.memory](https://developer.chrome.com/extensions/system_memory) | `system.memory`API。 |
| [system.storage](https://developer.chrome.com/extensions/system_storage) | 有关存储设备的查询信息。 还可以在连接或分离存储设备时收到通知。 |
| [tabCapture](https://developer.chrome.com/extensions/tabCapture) | 与选项卡媒体流交互。 |
| [选项卡](https://developer.chrome.com/extensions/tabs) | 与浏览器的选项卡系统交互以创建、修改和重新排列选项卡。 |
| [topSites](https://developer.chrome.com/extensions/topSites) | 访问显示在新选项卡页上的热门网站（也称为访问最多的网站）。 这些网站不包括用户自定义的快捷方式。 |
| [tts](https://developer.chrome.com/extensions/tts) | 在 TTS 中播放合成的文本 (语音) 。 |
| [ttsEngine](https://developer.chrome.com/extensions/ttsEngine) | 使用扩展在 TTS (实现) 到语音的语音到语音。 注册为此 API 的扩展接收包含要说出的语音和其他参数的事件。 然后，扩展可以使用任何可用的 Web 技术来合成和输出语音，并将事件发送回调用函数以报告状态。 |
| [类型](https://developer.chrome.com/extensions/types) | Microsoft Edge 的类型声明。 |
| [webNavigation](https://developer.chrome.com/extensions/webNavigation) | 接收有关导航请求状态的通知。 |
| [webRequest](https://developer.chrome.com/extensions/webRequest) | 观察和分析流量。 截获、阻止或修改请求。 |
| [windows](https://developer.chrome.com/extensions/windows) | 与浏览器窗口交互以在浏览器中创建、修改和重新排列窗口。 |



## <a name="unsupported-extension-apis"></a>不支持的扩展 API

Microsoft Edge 不支持以下扩展 API：

* `chrome.gcm`.
* `chrome.identity.getAccounts`.
* `chrome.identity.getAuthToken` - 作为备用方法，可以使用 `launchWebAuthFlow` 获取 OAuth2 令牌对用户进行身份验证。
* `chrome.instanceID`.


## <a name="additional-considerations-for-supported-apis"></a>受支持的 API 的其他注意事项

* 用户必须使用 MSA 或 Azure Active Directory 帐户登录到 Microsoft Edge，以使用 `chrome.identity.getProfileUserInfo` 。 如果用户使用本地 Active Directory 帐户登录到 Microsoft Edge，API 将返回电子邮件和 `null` ID 值。

* Microsoft Edge 不支持使用 Chrome Web Store 付款的扩展，因为它用于为 `identity.getAuthtoken` 登录用户请求令牌。 这些令牌将发送到基于 REST 的许可 API。 


<!-- links -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/apps/external_extensions)。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
