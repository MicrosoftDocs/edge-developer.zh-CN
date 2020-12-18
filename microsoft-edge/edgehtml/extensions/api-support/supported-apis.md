---
description: 查找当前和将来的 API 及其已知问题/Chrome 不兼容的信息。
title: 扩展 - 受支持的 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b8cf13f42c99779f23eaa7b941093752fb25b207
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232719"
---
# 支持的 API  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

以下是受支持的 API 成员的详细列表。 扩展平台的开发正在进行中，因此请经常回来查看更新！

> [!NOTE]
>  - 对于 Microsoft Edge，所有扩展 API 都位于 `browser` 命名空间下，例如 `browser.browserAction.disable()` 。
>  - Microsoft Edge 扩展 API 使用回调，而不是承诺。


## 总体问题

以下已知问题跨越扩展平台，并将于近期修复：

- 使用 CSS `url()` 属性时，使用的绝对 URL 将像在 Chrome 中 `ms-browser-extension://` 一样不起作用。 若要绕过此问题，请改为从根扩展目录 (资源的相对) 路径。
- `window.open()` 在扩展后台脚本中不起作用。 请 `browser.windows.create()` 改为使用。
- 支持共享 Cookie，但在启用扩展之前，扩展后台脚本将无法访问在选项卡中设置的会话 Cookie。 此问题不会影响永久性 Cookie。
- 如果仅为扩展指定不受支持的权限，即 `activeTab`，尝试旁加载扩展将导致卸载扩展，并显示以下消息："扩展出现问题，因此我们必须重新安装它们。 你需要再次打开它们。"
- 通过隐藏的定位标记触发下载将失败，来自后台脚本。 这应该从扩展页完成。


## 书签

支持 `bookmarks` 以下 API：

| API                                   | 已知问题                                             | Chrome 不兼容
|---------------------------------------|----------------------------------------------------------|--------------------------|
| [书签](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks) | | |
| [bookmarks.create](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/create) | | |
| [bookmarks.remove](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/remove) | | |
| [bookmarks.getTree](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/getTree) |  | |
| [bookmarks.move](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/move) | | |
| [bookmarks.removeTree](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/removeTree) | | |
| [bookmarks.update](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/update)            | | |


## browserAction

支持 `browserAction` 以下 API：

| API                                   | 已知问题                                             | Chrome 不兼容
|---------------------------------------|----------------------------------------------------------|--------------------------|
| [browserAction](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction) | | |
| [browserAction.disable](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/disable) | | |
| [browserAction.enable](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/enable) | | |
| [browserAction.getBadgeBackgroundColor](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getBadgeBackgroundColor) |  | |
| [browserAction.setBadgeBackgroundColor](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setBadgeBackgroundColor) | | |
| [browserAction.onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/onClicked) | | |
| [browserAction.setBadgeText](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setBadgeText)            | | |
| [browserAction.setPopup](https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setPopup)  | | |
| [browserAction.getBadgeText](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getBadgeText)   | | |
| [browserAction.setIcon](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setIcon) | `browserAction.setIcon` 不持久化。 <br/><br/> `imageData`不支持此参数。 <br/><br/> `path` 是必需参数。| |
| [browserAction.getTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getTitle) | | |
| [browserAction.setTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setTitle) | | |

## contextMenus

支持 `contextMenus` 以下 API：

| API                    | 已知问题 | Chrome 不兼容
|------------------------|--------------|----------------------|
| [contextMenus](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus)  |  | |
| [contextMenus.ContextType](https://developer.mozilla.org/Add-ons/WebExtensions/API/contextMenus/ContextType) | `"page_action"` `ContextType` 将不会显示在页面操作上下文菜单中。| Microsoft Edge 不支持 `"launcher"` `ContextType` 。|
| [contextMenus.create](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/create)    | 当扩展不提供时 `contextmenuid` ，生成的 `id` 不是唯一的。 | |
| [contextMenus.onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/onClicked) | | |
| [contextMenus.remove](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/remove) | | |
| [contextMenus.removeAll](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/removeAll) | | |
| [contextMenus.update](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/update) | | |

## Cookie

支持 `cookies` 以下 API：

| API                    | 已知问题 | Chrome 不兼容
|------------------------|--------------|----------------------|
| [Cookie](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/cookies)  |  | |
| [cookies.get](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/get)    |  | |
| [cookies.getAll](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/getAll) |   | 如果未提供 URL，则仅检索当前打开的选项卡中的 URL 的 Cookie。 在 Chrome 中，这将获取用户计算机上的所有 Cookie。 |
| [cookies.getAllCookieStores](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/getAllCookieStores)  | | 始终返回 ID 为"0"的相同默认 Cookie 存储。 所有 Cookie 都属于此存储。 |
| [cookies.onChanged](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/onChanged)    | | 不支持。 |
| [cookies.remove](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/remove) |  | |
| [cookies.set](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/set)    |  | |



## extension

支持 `extension` 以下 API：

| API                                   | 已知问题 | Chrome 不兼容
|---------------------------------------|----------------------------------------------------------|-------------|
[extension](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/extension) | | |
[extension.getBackgroundPage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/extension/getBackgroundPage) | | |
[extension.getURL](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/extension/getURL) | | |
[extension.getViews](https://developer.mozilla.org/Add-ons/WebExtensions/API/extension/getViews) | | |
[extension.isAllowedIncognitoAccess](https://developer.mozilla.org/Add-ons/WebExtensions/API/extension/isAllowedIncognitoAccess) | | | 
[extension.inIncognitoContext](https://developer.mozilla.org/Add-ons/WebExtensions/API/extension/inIncognitoContext) | | | 



## i18n

支持 `i18n` 以下 API：

API | 已知问题 | Chrome 不兼容
:------| :-------- | :---------------------
[i18n](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/i18n) | | |
[i18n.getAcceptLanguages](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/i18n/getAcceptLanguages) | | |
[i18n.getMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/i18n/getMessage) | `i18n.getMessage` 如果键无效，则会引发异常，而不是正常失败。 <br/><br/> `i18n.getMessage` 参数需要字符串，但还应允许 int 或引发异常。 | |
[i18n.getUILanguage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/i18n/getUILanguage) | | |

## idle

支持 `idle` 以下 API：

API | 已知问题 | Chrome 不兼容
:------| :-------- | :---------------------
[idle](https://developer.mozilla.org/Add-ons/WebExtensions/API/idle) | | |
[idle.setDetectionInterval](https://developer.mozilla.org/Add-ons/WebExtensions/API/idle/setDetectionInterval) | | |
[idle.queryState](https://developer.mozilla.org/Add-ons/WebExtensions/API/idle/queryState) | | |

## 通知

支持 `notifications` 以下 API：

API | 已知问题 | Chrome 不兼容
:------| :-------- | :---------------------
[通知](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) | | |
[通知。NotificationOptions](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/NotificationOptions) | | |
[通知。TemplateType](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/TemplateType) | | |
[notifications.clear](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/clear) | | |
[notifications.create](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/create) | | |
[notifications.getAll](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/getAll) | | |
[notifications.update](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/update) | | |
[notifications.onButtonClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/onButtonClicked) | | |
[notifications.onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/onClicked) | | |
[notifications.onClosed](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/onClosed) | | |
notifications.onPermissionLevelChanged | | |
notifications.getPermissionLevel | | |

## pageAction

支持 `pageAction` 以下 API：

API | 已知问题 | Chrome 不兼容
:------------ | :------------- | :--------------------
[pageAction](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction) | | |
[pageAction.getPopup](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/getPopup) | | |
[pageAction.getTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/getTitle) | | |
[pageAction.hide](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/hide) | | |
[pageAction.onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/onClicked) | | |
[pageAction.setIcon](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setIcon) | | `imageData`不支持此参数。 <br/><br/> `path` 是必需参数。 |
[pageAction.setPopup](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setPopup) | | |
[pageAction.setTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setTitle) | | |
[pageAction.show](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/show) | | |



## runtime

支持 `runtime` 以下 API：

API | 已知问题 | Chrome 不兼容
:------------ | :------------- | :-------------------
[runtime](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime) | | |
[runtime.port.disconnect](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/Port) | | |
[runtime.port.onDisconnect](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/Port) | | |
[runtime.port.postMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/Port) | | |
[runtime.connect](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connect) | | |
[runtime.connectNative](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) | | |
[runtime.id](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/id) | | |
[runtime.getBackgroundPage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/getBackgroundPage) | | |
[runtime.getManifest](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/getManifest) | | |
[runtime.getURL](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/getURL) | | |
[runtime.lastError](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/lastError) | | |
[runtime.reload](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/reload) | | |
[runtime.sendMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendMessage) | Microsoft Edge 扩展页可用于 `runtime.sendMessage` / `onMessage` 向自己发送邮件。 <br/><br/> `runtime.sendmessage` 网站页面不支持。 | Microsoft Edge 不支持 `options` 此参数。|
[runtime.sendNativeMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) | | |
[runtime.setUninstallUrl](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/setUninstallUrl) | | |
[runtime.onConnect](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/onConnect) | | |
[runtime.onInstalled](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/onInstalled) | | |
[runtime.onMessage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/onMessage) | `tab` 对象 `runtime.onMessage` 未完全实现。 | `MessageSender.tlsChannelId` 在 Microsoft Edge 中不受支持。|

## 存储

支持 `storage` 以下 API：

API | 已知问题 | Chrome 不兼容
:------------ | :------------- | :------------------------
[存储](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage) |  | |
[storage.local.get](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/get)  | | |
[storage.local.remove](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/remove)  | | |
[storage.local.set](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/set)  | | |
[storage.local.clear](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/clear) | | |
[storage.local.getBytesInUse](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/getBytesInUse) | | `storage.local` 数据以与 Chrome 不同的格式保留，导致调用时返回不同的值 `storage.local.getBytesInUse` 。  <br/><br/>例如： `storage.local.set({ "k": { "s": "âas" } }` 在 Chrome 中返回 13，在 Microsoft Edge 中返回 50。|
[storage.sync.get](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/StorageArea/get) | 如果和清单字段中的字符组合数量 `name` 超过 `author` 31 个字符， `storage.sync` 命名空间可能无法正常工作。 | |
[storage.sync.remove](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/StorageArea/remove) | | |
[storage.sync.set](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/StorageArea/set) | | |
[storage.onChanged](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/onChanged) | | |

## 选项卡

支持 `tabs` 以下 API：

API | 已知问题 | Chrome 不兼容
:------------ | :------------- | :----------------
[选项卡](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs) | | |
[tabs.captureVisibleTab](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/captureVisibleTab) | | |
[tabs.create](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/create) | | `selected`， `pinned` `openerTabId` 则不受支持。 |
[tabs.detectLanguage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/detectLanguage) | | |
[tabs.executeScript](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/executeScript) | `runAt` 被忽略，但已选中。 尚不支持在特定的框架中执行脚本。 | |
[tabs.get](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/get) | 当询问不在窗口中的选项卡时，选项页将无法进行此调用。 | |
[tabs.getCurrent](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/getCurrent) | | |
[tabs.insertCSS](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/insertCSS) | `runAt` 被忽略，但已选中。 | `cssOrigin` 不受支持。 |
[tabs.onActivated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onActivated) | | |
[tabs.onAttached](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onAttached) | | |
[tabs.onCreated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onCreated) | | |
[tabs.onDetached](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs) | | |
[tabs.onRemoved](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onRemoved) | | |
[tabs.onReplaced](https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/onReplaced) | | |
[tabs.onUpdated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onUpdated) | 卸载/重新安装后，在重新启动 Microsoft Edge 之前不会收到 URL。 | |
[tabs.query](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/query) | `pinned`， `audible` `muted` 但尚不支持。 <br/><br/> `"popup"` `windowType` 尚不支持。 | `highlighted` 不受支持。 <br/><br/> `"panel"`， `"app"` `"devtools"` `windowType` 则不受支持。 |
[tabs.reload](https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/reload) | | Microsoft Edge 不支持承诺。 |
[tabs.remove](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/remove) | | |
[tabs.sendMessage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/sendMessage) | 尚不支持发送特定帧的消息。 `tabs.sendMessage` 如果接收选项卡上不存在侦听器，则从不在选项卡刷新后发送 `runtime.onMessage` 响应。 | |
[选项卡。Tab](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/Tab) | `audible``mutedInfo`、、 `inPrivate` `width` 和 `height` 属性尚不受支持。 | `openerTabId`， `selected` `highlighted` 则不支持属性。 |
[tabs.update](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/update) | `pinned` `muted`且尚不支持。 | `highlighted` `selected`且不受支持。 |


## webNavigation

支持 `webNavigation` 以下 API：


| API                                                                                                                                                           | 已知问题                                | Chrome 不兼容                                                                                                    |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------|
| [webNavigation](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation)                                                     | 选项卡 ID 不正确。                      | 不支持筛选、TransitionTypes 和 TransitionQualifiers。 <br/><br/> 对于选项卡， `processIds` 所有操作都相同。 |
| [webNavigation.getAllFrames](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/getAllFrames)                           | 不包括 object-as-iframe 元素。 |                                                                                                                             |
| [webNavigation.getFrame](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/getFrame)                                   |                                             |                                                                                                                             |
| [webNavigation.onBeforeNavigate](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onBeforeNavigate)                   |                                             |                                                                                                                             |
| [webNavigation.onCommitted](https://developer.mozilla.org/Add-ons/WebExtensions/API/webNavigation/onCommitted)                                           |                                             |                                                                                                                             |
| [webNavigation.onCompleted](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onCompleted)                             |                                             |                                                                                                                             |
| [webNavigation.onCreatedNavigationTarget](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onCreatedNavigationTarget) |                                             |                                                                                                                             |
| [webNavigation.onDOMContentLoaded](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onDOMContentLoaded)               |                                             |                                                                                                                             |
| [webNavigation.onErrorOccurred](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onErrorOccurred)                     |                                             |                                                                                                                             |
| [webNavigation.onHistoryStateUpdated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onHistoryStateUpdated)         |                                             |                                                                                                                             |
| [webNavigation.onReferenceFragmentUpdated](https://developer.mozilla.org/Add-ons/WebExtensions/API/webNavigation/onReferenceFragmentUpdated)            |                                             |                                                                                                                             |
| [webNavigation.onTabReplaced](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onTabReplaced)                         |                                             | 不支持。                                                                                                              |
| [webNavigation.TransitionType](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/TransitionType)                       |                                             |                                                                                                                             |
| [webNavigation.TransitionQualifier](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/TransitionQualifier)             |                                             |                                                                                                                             |

## webRequest

支持 `webRequest` 以下 API：

API | 已知问题 | Chrome 不兼容
:------ | :----- | :-------
[webRequest](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest) | `webRequest` 不支持同步 `XmlHttpRequests` 。 | 不支持来自扩展的网络请求，如选项、背景或弹出窗口。<br/><br/> 不支持来自 `<object>` 和 `<embed>` 元素的网络请求。<br/><br/> 无法为缓存的请求修改标头。  |
[handlerBehaviorChanged](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/handlerBehaviorChanged) | | 处理程序更改在 Microsoft Edge 中自动处理。<br/><br/>调用此功能不起作用。  |
[onAuthRequired](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onAuthRequired) | | |
[onBeforeRedirect](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onBeforeRedirect) | | |
[onBeforeRequest](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onBeforeRequest) | | `requestBody` 不受支持。 |
[onBeforeSendHeaders](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onBeforeSendHeaders) | | |
[onCompleted](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onCompleted) | | |
[onErrorOccurred](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onErrorOccurred) | | |
[onHeadersReceived](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onHeadersReceived) | |  |
[onResponseStarted](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onResponseStarted) | |  |
[onSendHeaders](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/onSendHeaders) | | |

## windows

支持 `windows` 以下 API：


| API                                                                                                                               | 已知问题                                                   | Chrome 不兼容                                                                                        |
|:----------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------|
| [windows](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows)                                     |                                                                | `Window` 对象不支持 `alwaysOnTop` Microsoft Edge 中的属性。 <br/><br/>不支持 InPrivate。 |
| [windows。CreateType](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/CreateType)                            |                                                                | `"panel"` `"detached_panel"`且在 Microsoft Edge 中不受支持。                                           |
| [windows.create](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/create)                                    |                                                                | `tabId` 不支持用于关闭选项卡的参数。                                                       |
| [windows.get](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/get)                             |                                                                |                                                                                                                 |
| [windows.getAll](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/getAll)                       | `windows.getAll({populate: true})` 缺少 `tabs` 属性。 |                                                                                                                 |
| [windows.getCurrent](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/getCurrent)               |                                                                |                                                                                                                 |
| [windows.getLastFocused](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/getLastFocused)       |                                                                |                                                                                                                 |
| [windows.update](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/update)                       | 不支持指定位置。                          | `"minimized"`/`"maximized"`/`"fullscreen"``drawAttention`且在 Microsoft Edge 中不受支持。             |
| [windows.onCreated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/onCreated)                 |                                                                | `WindowType` 筛选器不受支持。                                                                           |
| [windows.onFocusChanged](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/onFocusChanged)                    |                                                                | `WindowType` 筛选器不受支持。                                                                           |
| [windows。WindowState](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/WindowState)                          | `"minimized"`， `"maximized"` `"fullscreen"` 则不受支持。 | `"docked"` 在 Microsoft Edge 中不受支持。                                                                  |
| [windows。WindowType](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/WindowType)                            |                                                                | `"panel"`， `"app"` 在 `"devtools"` Microsoft Edge 中不受支持。                                       |
| [windows。WINDOW_ID_CURRENT](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/WINDOW_ID_CURRENT) |                                                                |                                                                                                                 |
| [windows。WINDOW_ID_NONE](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/WINDOW_ID_NONE)       |                                                                |                                                                                                                 |
