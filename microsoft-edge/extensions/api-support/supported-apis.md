---
description: 查找有关当前和未来 Api 的信息，以及它们的已知问题/Chrome 不兼容。
title: 扩展-支持的 Api
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: b9f3764a65f2b27dc61e4e5ae8734820efb7fbd0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563333"
---
# 支持的 API  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

以下是受支持的 API 成员的详细列表。 扩展平台的开发正在进行，因此请经常查看更新！

> [!NOTE]
>  - 对于 Microsoft Edge，所有扩展 Api 均位于 `browser` 命名空间下，例如 `browser.browserAction.disable()`
>  - Microsoft Edge 扩展 Api 使用回调，而不是承诺。


## 总体问题

以下已知问题跨越扩展平台，并将在不久的将来修复：

- 使用 CSS 属性时 `url()` ，使用的绝对 url `ms-browser-extension://` 将不能像在 Chrome 中那样工作。 若要绕过此问题，请改用资源的相对路径（从根扩展目录开始）。
- `window.open()` 扩展后台脚本不起作用。 请 `browser.windows.create()` 改用。
- 共享 cookie 受支持，但扩展后台脚本将无法访问在启用扩展之前在选项卡中设置的会话 cookie。 此问题不会影响永久性 cookie。
- 如果仅为扩展指定不受支持的权限，例如 `activeTab`，尝试旁加载扩展将导致正在卸载扩展名，并显示以下消息： "您的扩展出现了错误，因此我们必须重新安装它们。 您需要重新打开它们。 "
- 通过隐藏定位点标记触发下载将从后台脚本失败。 此操作应从扩展页中执行此操作。


## 书签

以下 `bookmarks` api 受支持：

| API                                   | 已知问题                                             | Chrome 不兼容
|---------------------------------------|----------------------------------------------------------|--------------------------|
| [书签](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks) | | |
| [书签。创建](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/create) | | |
| [书签。删除](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/remove) | | |
| [getTree](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/getTree) |  | |
| [书签。移动](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/move) | | |
| [removeTree](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/removeTree) | | |
| [书签。更新](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/bookmarks/update)            | | |


## browserAction

以下 `browserAction` api 受支持：

| API                                   | 已知问题                                             | Chrome 不兼容
|---------------------------------------|----------------------------------------------------------|--------------------------|
| [browserAction](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction) | | |
| [browserAction 禁用](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/disable) | | |
| [browserAction 启用](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/enable) | | |
| [browserAction.getBadgeBackgroundColor](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getBadgeBackgroundColor) |  | |
| [browserAction.setBadgeBackgroundColor](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setBadgeBackgroundColor) | | |
| [browserAction.onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/onClicked) | | |
| [browserAction.setBadgeText](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setBadgeText)            | | |
| [browserAction.setPopup](https://developer.mozilla.org/Add-ons/WebExtensions/API/browserAction/setPopup)  | | |
| [browserAction.getBadgeText](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getBadgeText)   | | |
| [browserAction.setIcon](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setIcon) | `browserAction.setIcon` 不会保留。 <br/><br/> `imageData`不支持该参数。 <br/><br/> `path` 是必需的参数。| |
| [browserAction.getTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/getTitle) | | |
| [browserAction.setTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/browserAction/setTitle) | | |

## contextMenus

以下 `contextMenus` api 受支持：

| API                    | 已知问题 | Chrome 不兼容
|------------------------|--------------|----------------------|
| [contextMenus](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus)  |  | |
| [contextMenus.ContextType](https://developer.mozilla.org/Add-ons/WebExtensions/API/contextMenus/ContextType) | `"page_action"` `ContextType` 将不会显示在页面操作上下文菜单中。| Microsoft Edge 不支持 `"launcher"` `ContextType` 。|
| [contextMenus 创建](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/create)    | 当扩展不提供时 `contextmenuid` ，生成的 `id` 不是唯一的。 | |
| [contextMenus.onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/onClicked) | | |
| [contextMenus。删除](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/remove) | | |
| [contextMenus.removeAll](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/removeAll) | | |
| [contextMenus 更新](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/contextMenus/update) | | |

## Cookie

以下 `cookies` api 受支持：

| API                    | 已知问题 | Chrome 不兼容
|------------------------|--------------|----------------------|
| [Cookie](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/cookies)  |  | |
| [cookie。获取](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/get)    |  | |
| [getAll](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/getAll) |   | 如果未提供 URL，则仅检索当前打开的选项卡中的 Url 的 cookie。 在 Chrome 中，这将获取用户计算机上的所有 cookie。 |
| [getAllCookieStores](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/getAllCookieStores)  | | 始终返回 ID 为 "0" 的相同默认 cookie 存储。 所有 cookie 都属于此应用商店。 |
| [onChanged](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/onChanged)    | | 不支持。 |
| [cookie。删除](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/remove) |  | |
| [cookies。设置](https://developer.mozilla.org/Add-ons/WebExtensions/API/cookies/set)    |  | |



## 线

以下 `extension` api 受支持：

| API                                   | 已知问题 | Chrome 不兼容
|---------------------------------------|----------------------------------------------------------|-------------|
[线](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/extension) | | |
[扩展名 getBackgroundPage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/extension/getBackgroundPage) | | |
[扩展名 getURL](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/extension/getURL) | | |
[扩展名 getViews](https://developer.mozilla.org/Add-ons/WebExtensions/API/extension/getViews) | | |
[扩展名 isAllowedIncognitoAccess](https://developer.mozilla.org/Add-ons/WebExtensions/API/extension/isAllowedIncognitoAccess) | | | 
[扩展名 inIncognitoContext](https://developer.mozilla.org/Add-ons/WebExtensions/API/extension/inIncognitoContext) | | | 



## 国际化

以下 `i18n` api 受支持：

API | 已知问题 | Chrome 不兼容
:------| :-------- | :---------------------
[国际化](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/i18n) | | |
[getAcceptLanguages](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/i18n/getAcceptLanguages) | | |
[getMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/i18n/getMessage) | `i18n.getMessage` 带有无效键会引发异常，而不会正常失败。 <br/><br/> `i18n.getMessage` 参数需要字符串，但也应允许 int 或引发异常。 | |
[getUILanguage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/i18n/getUILanguage) | | |

## 着

以下 `idle` api 受支持：

API | 已知问题 | Chrome 不兼容
:------| :-------- | :---------------------
[着](https://developer.mozilla.org/Add-ons/WebExtensions/API/idle) | | |
[setDetectionInterval](https://developer.mozilla.org/Add-ons/WebExtensions/API/idle/setDetectionInterval) | | |
[queryState](https://developer.mozilla.org/Add-ons/WebExtensions/API/idle/queryState) | | |

## 通知

以下 `notifications` api 受支持：

API | 已知问题 | Chrome 不兼容
:------| :-------- | :---------------------
[通知](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) | | |
[通告.NotificationOptions](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/NotificationOptions) | | |
[通告.TemplateType](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/TemplateType) | | |
[通知。清除](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/clear) | | |
[通知。创建](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/create) | | |
[getAll](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/getAll) | | |
[通知。更新](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/update) | | |
[onButtonClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/onButtonClicked) | | |
[onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/onClicked) | | |
[onClosed](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/notifications/onClosed) | | |
onPermissionLevelChanged | | |
getPermissionLevel | | |

## pageAction

以下 `pageAction` api 受支持：

API | 已知问题 | Chrome 不兼容
:------------ | :------------- | :--------------------
[pageAction](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction) | | |
[pageAction.getPopup](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/getPopup) | | |
[pageAction.getTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/getTitle) | | |
[pageAction 隐藏](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/hide) | | |
[pageAction.onClicked](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/onClicked) | | |
[pageAction.setIcon](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setIcon) | | `imageData`不支持该参数。 <br/><br/> `path` 是必需的参数。 |
[pageAction.setPopup](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setPopup) | | |
[pageAction.setTitle](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/setTitle) | | |
[pageAction](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/pageAction/show) | | |



## 环境

以下 `runtime` api 受支持：

API | 已知问题 | Chrome 不兼容
:------------ | :------------- | :-------------------
[环境](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime) | | |
[运行时端口。断开连接](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/Port) | | |
[onDisconnect](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/Port) | | |
[postMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/Port) | | |
[运行时。连接](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connect) | | |
[connectNative](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/connectNative) | | |
[runtime.id](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/id) | | |
[getBackgroundPage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/getBackgroundPage) | | |
[getManifest](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/getManifest) | | |
[getURL](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/getURL) | | |
[lastError](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/lastError) | | |
[运行时。重新加载](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/reload) | | |
[sendMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendMessage) | Microsoft Edge 扩展页面可用于向 `runtime.sendMessage` / `onMessage` 自己发送消息。 <br/><br/> `runtime.sendmessage` 网站页面不支持。 | Microsoft Edge 不支持该 `options` 参数。|
[sendNativeMessage](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/sendNativeMessage) | | |
[setUninstallUrl](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/setUninstallUrl) | | |
[onConnect](https://developer.mozilla.org/Add-ons/WebExtensions/API/runtime/onConnect) | | |
[onInstalled](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/onInstalled) | | |
[onMessage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/runtime/onMessage) | `tab` 事件中的对象 `runtime.onMessage` 未完全实现。 | `MessageSender.tlsChannelId` Microsoft Edge 中不支持。|

## 存储

以下 `storage` api 受支持：

API | 已知问题 | Chrome 不兼容
:------------ | :------------- | :------------------------
[存储](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage) |  | |
[本地获取](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/get)  | | |
[本地、本地、删除](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/remove)  | | |
[存储在本地。设置](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/set)  | | |
[本地的存储空间。清除](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/clear) | | |
[getBytesInUse](https://developer.mozilla.org/Add-ons/WebExtensions/API/Storage/StorageArea/getBytesInUse) | | `storage.local` 数据与 Chrome 的格式保持不同，从而导致在调用时返回不同的值 `storage.local.getBytesInUse` 。  <br/><br/>Ex： `storage.local.set({ "k": { "s": "âas" } }` 在 Chrome 中返回13，在 Microsoft Edge 中返回50。|
["存储" 同步获取](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/StorageArea/get) | | |
[存储同步。删除](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/StorageArea/remove) | | |
[存储同步。设置](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/StorageArea/set) | | |
[onChanged](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/storage/onChanged) | | |

## 选项卡

以下 `tabs` api 受支持：

API | 已知问题 | Chrome 不兼容
:------------ | :------------- | :----------------
[选项卡](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs) | | |
[captureVisibleTab](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/captureVisibleTab) | | |
[选项卡。创建](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/create) | | `selected`、 `pinned` 、和 `openerTabId` 不受支持。 |
[detectLanguage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/detectLanguage) | | |
[executeScript](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/executeScript) | `runAt` 被忽略，但已选中。 尚不支持在特定帧中执行脚本。 | |
[选项卡。获取](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/get) | 选项页，询问有关不在其窗口中的选项卡时，无法进行此调用。 | |
[getCurrent](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/getCurrent) | | |
[insertCSS](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/insertCSS) | `runAt` 被忽略，但已选中。 | |
[onActivated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onActivated) | | |
[onAttached](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onAttached) | | |
[onCreated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onCreated) | | |
[onDetached](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs) | | |
[onRemoved](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onRemoved) | | |
[onReplaced](https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/onReplaced) | | |
[选项卡。 onUpdated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/onUpdated) | 卸载/重新安装后，将不会收到 URL，直到重新启动 Microsoft Edge。 | |
[选项卡。查询](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/query) | `pinned`、 `audible` 、和 `muted` 尚不受支持。 <br/><br/> `"popup"` `windowType` 尚不支持。 | `highlighted` 不受支持。 <br/><br/> `"panel"`、 `"app"` 、和 `"devtools"` `windowType` 不受支持。 |
[选项卡。重新加载](https://developer.mozilla.org/Add-ons/WebExtensions/API/tabs/reload) | | Microsoft Edge 不支持承诺。 |
[选项卡。删除](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/remove) | | |
[sendMessage](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/sendMessage) | 消息：尚不支持特定的帧。 `tabs.sendMessage` 如果 `runtime.onMessage` "接收" 选项卡上不存在任何侦听器，则从不在选项卡刷新后发送响应。 | |
[tabs.选项卡](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/Tab) | `audible``mutedInfo` `inPrivate` 尚不支持、、、 `width` 和 `height` 属性。 | `openerTabId`、 `selected` 和 `highlighted` 属性不受支持。 |
[选项卡。更新](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/tabs/update) | `pinned` 且 `muted` 尚不受支持。 | `highlighted` 且 `selected` 不受支持。 |


## webNavigation

以下 `webNavigation` api 受支持：


| API                                                                                                                                                           | 已知问题                                | Chrome 不兼容                                                                                                    |
|:--------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------|
| [webNavigation](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation)                                                     | 选项卡 id 不正确。                      | 不支持筛选、TransitionTypes 和 TransitionQualifiers。 <br/><br/> 对于选项卡，所有操作都 `processIds` 是相同的。 |
| [webNavigation.getAllFrames](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/getAllFrames)                           | 不包含对象为 iframe 元素。 |                                                                                                                             |
| [webNavigation.getFrame](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/getFrame)                                   |                                             |                                                                                                                             |
| [webNavigation.onBeforeNavigate](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onBeforeNavigate)                   |                                             |                                                                                                                             |
| [webNavigation.onCommitted](https://developer.mozilla.org/Add-ons/WebExtensions/API/webNavigation/onCommitted)                                           |                                             |                                                                                                                             |
| [webNavigation onCompleted](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onCompleted)                             |                                             |                                                                                                                             |
| [webNavigation.onCreatedNavigationTarget](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onCreatedNavigationTarget) |                                             |                                                                                                                             |
| [webNavigation.onDOMContentLoaded](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onDOMContentLoaded)               |                                             |                                                                                                                             |
| [webNavigation onErrorOccurred](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onErrorOccurred)                     |                                             |                                                                                                                             |
| [webNavigation.onHistoryStateUpdated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onHistoryStateUpdated)         |                                             |                                                                                                                             |
| [webNavigation.onReferenceFragmentUpdated](https://developer.mozilla.org/Add-ons/WebExtensions/API/webNavigation/onReferenceFragmentUpdated)            |                                             |                                                                                                                             |
| [webNavigation.onTabReplaced](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/onTabReplaced)                         |                                             | 不支持。                                                                                                              |
| [webNavigation.TransitionType](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/TransitionType)                       |                                             |                                                                                                                             |
| [webNavigation.TransitionQualifier](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/webNavigation/TransitionQualifier)             |                                             |                                                                                                                             |

## webRequest

以下 `webRequest` api 受支持：

API | 已知问题 | Chrome 不兼容
:------ | :----- | :-------
[webRequest](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest) | `webRequest` 不支持同步 `XmlHttpRequests` 。 | 不支持来自扩展（如选项、背景或弹出页面）的网络请求。<br/><br/> `<object>`不支持来自和 `<embed>` 元素的网络请求。<br/><br/> 无法修改缓存请求的标题。  |
[handlerBehaviorChanged](https://developer.mozilla.org/Add-ons/WebExtensions/API/webRequest/handlerBehaviorChanged) | | 处理程序更改将在 Microsoft Edge 中自动处理。<br/><br/>通话不起作用。  |
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

以下 `windows` api 受支持：


| API                                                                                                                               | 已知问题                                                   | Chrome 不兼容                                                                                        |
|:----------------------------------------------------------------------------------------------------------------------------------|:---------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------|
| [windows](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows)                                     |                                                                | `Window` 对象不支持 `alwaysOnTop` Microsoft Edge 中的属性。 <br/><br/>不支持 InPrivate。 |
| [windows.CreateType](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/CreateType)                            |                                                                | `"panel"` `"detached_panel"`Microsoft Edge 中不支持。                                           |
| [windows。创建](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/create)                                    |                                                                | `tabId` 不支持在选项卡上撕裂的参数。                                                       |
| [windows。获取](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/get)                             |                                                                |                                                                                                                 |
| [getAll](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/getAll)                       | `windows.getAll({populate: true})` 缺少 `tabs` 属性。 |                                                                                                                 |
| [getCurrent](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/getCurrent)               |                                                                |                                                                                                                 |
| [getLastFocused](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/getLastFocused)       |                                                                |                                                                                                                 |
| [windows。更新](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/update)                       | 不支持指定位置。                          | `"minimized"`/`"maximized"`/`"fullscreen"``drawAttention`Microsoft Edge 中不支持。             |
| [onCreated](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/onCreated)                 |                                                                | `WindowType` 不支持筛选器。                                                                           |
| [onFocusChanged](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/onFocusChanged)                    |                                                                | `WindowType` 不支持筛选器。                                                                           |
| [windows.WindowState](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/WindowState)                          | `"minimized"``"maximized"` `"fullscreen"` 不支持。 | `"docked"` Microsoft Edge 中不支持。                                                                  |
| [windows.WindowType](https://developer.mozilla.org/Add-ons/WebExtensions/API/windows/WindowType)                            |                                                                | `"panel"`、 `"app"` 、和 `"devtools"` 在 Microsoft Edge 中不受支持。                                       |
| [windows.WINDOW_ID_CURRENT](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/WINDOW_ID_CURRENT) |                                                                |                                                                                                                 |
| [windows.WINDOW_ID_NONE](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/API/windows/WINDOW_ID_NONE)       |                                                                |                                                                                                                 |
