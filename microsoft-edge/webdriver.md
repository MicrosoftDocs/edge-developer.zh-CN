---
ms.assetid: e56172c0-b635-4c02-8e0c-56bf8cb4c164
description: 了解如何开始使用 WebDriver，这是一种允许程序和脚本控制 web 浏览器行为的线协议。
title: WebDriver (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: 边缘、web 开发、html、css、javascript、开发人员、webdriver、selenium、测试
ms.openlocfilehash: 0a6ef78103852234a6b52dfe88e60273cc3bd3d0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564598"
---
# WebDriver (EdgeHTML)
W3C [WebDriver](https://www.w3.org/TR/webdriver/) API 是一个平台和语言中立的界面和线路协议，允许程序或脚本控制 web 浏览器的行为。

WebDriver 使开发人员能够创建模拟用户交互的自动测试。 这与 JavaScript 单元测试不同，因为 WebDriver 有权访问 JavaScript 在浏览器中运行的功能和信息，并且可以更准确地模拟用户事件或操作系统级别的事件。 WebDriver 还可以在单个测试会话中跨多个窗口、选项卡和网页管理测试。

下面介绍了如何开始使用 Microsoft Edge (EdgeHTML) 的 WebDriver。

Microsoft Edge (EdgeHTML) WebDriver 实现支持 W3C [WebDriver](https://www.w3.org/TR/webdriver/) 规范和 [JSON 线路协议](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol) ，用于向后兼容现有测试。

## WebDriver for Microsoft Edge (EdgeHTML) 入门
* 安装 Windows 10。
* 下载适用于 Windows 和 Microsoft Edge (EdgeHTML) 的 [Microsoft WebDriver](https://developer.microsoft.com/microsoft-edge/tools/webdriver/) 服务器。
* 下载你选择的 WebDriver 语言绑定。 [所有 Selenium 语言绑定都支持 Microsoft Edge (EdgeHTML) ](https://docs.seleniumhq.org/download/)。

> [!NOTE]
> 你可以在 [Microsoft Edge (EdgeHTML) 反馈 & 支持](https://developer.microsoft.com/microsoft-edge/support/)中找到帮助、报告问题和文件功能请求。


## 使用 WebDriver
若要开始使用 Microsoft Edge (EdgeHTML) 的 WebDriver，请查看以下示例：

* 用于打开浏览器窗口的[C # 代码示例](https://gist.github.com/InstyleVII/baf25274c55e891076d5#file-webdriver-cs)，导航到 bing.com 并搜索 "webdriver" (GitHub Gist) 。

## WebDriver 服务器命令行标志
WebDriver 服务器的命令行标志列表。

| 名称    | 描述                                                                                                      | 可用版本 |
|:--------|:-----------------------------------------------------------------------------------------------------------------|:------------------|
| 主机    | 用于 WebDriver 服务器的主机 IP (默认： localhost)                                                      | 14393             |
| 端口    | 用于 WebDriver 服务器的端口 (默认： 17556)                                                             | 14393             |
| package | ApplicationUserModelId (AUMID) ，应用程序将由 WebDriver 服务器启动                        | 14393             |
| 详细 | 输出由 WebDriver 服务器发送的已接收请求和响应                                             | 14393             |
| silent  | 不输出任何内容                                                                                                  | 15063             |
| version | 输出 MicrosoftWebDriver.exe 的版本                                                                    | 17763             |
| w3c     | 使用 W3C WebDriver 协议 (默认选项)                                                                       | 17763             |
| jwp     | 使用 JSON 线路协议                                                                                           | 17763             |
| 清除 | 清理 WebDriver server for-程序包设置的临时数据和注册表项。 将忽略其他参数 | 17763             |

## W3C WebDriver
[W3C WebDriver 规范](https://www.w3.org/TR/webdriver/)对每个命令的支持。

### 功能
| 功能                       | 密钥                       | 状态                   | 可用版本 |
|:---------------------------------|:--------------------------|:-------------------------|:------------------|
| 浏览器名称                     | "browserName"             | 支持                | 17763             |
| 浏览器版本                  | "browserVersion"          | 支持                | 17763             |
| 平台名称                    | "platformName"            | 支持                | 17763             |
| 接受不安全的 TLS 证书 | "acceptInsecureCerts"     | 不 &nbsp; 支持       | 不适用               |
| 页面加载策略               | "pageLoadStrategy"        | 支持                | 17763             |
| 代理配置              | 服务器                   | 不 &nbsp; 支持       | 不适用               |
| 调整窗口尺寸/定位  | "setWindowRect"           | 支持                | 17763             |
| 会话超时配置   | 超时                | 支持                | 17763             |
| 未处理的提示行为        | "unhandledPromptBehavior" | 部分 &nbsp; 支持 | 17763             |
| InPrivate                        | "ms： inPrivate"            | 支持                | 17763             |
| 扩展路径                  | "ms： extensionPaths"       | 支持                | 17763             |
| 起始页                       | "ms： startPage"            | 支持                | 17763             |

### 定位器策略
| 定位器策略                                                        | 状态    | 可用版本 |
|:------------------------------------------------------------------------|:----------|:------------------|
| [CSS 选择器](https://www.w3.org/TR/webdriver/#css-selectors)         | 支持 | 17763             |
| [链接文本](https://www.w3.org/TR/webdriver/#link-text)                 | 支持 | 17763             |
| [部分链接文本](https://www.w3.org/TR/webdriver/#partial-link-text) | 支持 | 17763             |
| [标记名称](https://www.w3.org/TR/webdriver/#tag-name)                   | 支持 | 17763             |
| [XPath](https://www.w3.org/TR/webdriver/#xpath)                         | 支持 | 17763             |

### 命令
| HTTP 方法 | URI 模板                                                   | 命令                                                                                   | 状态             | 可用版本 |
|:------------|:---------------------------------------------------------------|:------------------------------------------------------------------------------------------|:-------------------|:----------------  |
| POST        | /session                                                       | [新会话](https://www.w3.org/TR/webdriver/#new-session)                               | 支持          | 17763             |
| DELETE      | /session/{session id}                                          | [删除会话](https://www.w3.org/TR/webdriver/#delete-session)                         | 支持          | 17763             |
| GET         | /status                                                        | [状态](https://www.w3.org/TR/webdriver/#status)                                         | 支持          | 17763             |
| GET         | /session/{session id}/timeouts                                 | [获取超时](https://www.w3.org/TR/webdriver/#get-timeouts)                             | 支持          | 17763             |
| POST        | /session/{session id}/timeouts                                 | [设置超时](https://www.w3.org/TR/webdriver/#set-timeouts)                             | 支持          | 17763             |
| POST        | /session/{session id}/url                                      | [导航到](https://www.w3.org/TR/webdriver/#navigate-to)                               | 支持          | 17763             |
| GET         | /session/{session id}/url                                      | [获取当前 URL](https://www.w3.org/TR/webdriver/#get-current-url)                       | 支持          | 17763             |
| POST        | /session/{session id}/back                                     | [后退](https://www.w3.org/TR/webdriver/#back)                                             | 支持          | 17763             |
| POST        | /session/{session id}/forward                                  | [前进](https://www.w3.org/TR/webdriver/#forward)                                       | 支持          | 17763             |
| POST        | /session/{session id}/refresh                                  | [刷新](https://www.w3.org/TR/webdriver/#refresh)                                       | 支持          | 17763             |
| GET         | /session/{session id}/title                                    | [获取标题](https://www.w3.org/TR/webdriver/#get-title)                                   | 支持          | 17763             |
| GET         | /session/{session id}/window                                   | [获取窗口句柄](https://www.w3.org/TR/webdriver/#get-window-handle)                   | 支持          | 17763             |
| DELETE      | /session/{session id}/window                                   | [关闭窗口](https://www.w3.org/TR/webdriver/#close-window)                             | 支持          | 17763             |
| POST        | /session/{session id}/window                                   | [切换到窗口](https://www.w3.org/TR/webdriver/#switch-to-window)                     | 支持          | 17763             |
| GET         | /session/{session id}/window/handles                           | [获取窗口句柄](https://www.w3.org/TR/webdriver/#get-window-handles)                 | 支持          | 17763             |
| POST        | /session/{session id}/frame                                    | [切换到图文框](https://www.w3.org/TR/webdriver/#switch-to-frame)                       | 支持          | 17763             |
| POST        | /session/{session id}/frame/parent                             | [切换到父框架](https://www.w3.org/TR/webdriver/#switch-to-parent-frame)         | 支持          | 17763             |
| GET         | /session/{session id}/window/rect                              | [获取窗口矩形](https://www.w3.org/TR/webdriver/#get-window-rect)                       | 支持          | 17763             |
| POST        | /session/{session id}/window/rect                              | [设置窗口矩形](https://www.w3.org/TR/webdriver/#set-window-rect)                       | 支持          | 17763             |
| POST        | /session/{session id}/window/maximize                          | [最大化窗口](https://www.w3.org/TR/webdriver/#maximize-window)                       | 支持          | 17763             |
| POST        | /session/{session id}/window/minimize                          | [最小化窗口](https://www.w3.org/TR/webdriver/#minimize-window)                       | 支持          | 17763             |
| POST        | /session/{session id}/window/fullscreen                        | [全屏窗口](https://www.w3.org/TR/webdriver/#fullscreen-window)                   | 不 &nbsp; 支持 | 不适用               |
| GET         | /session/{session id}/element/active                           | [获取活动元素](https://www.w3.org/TR/webdriver/#get-active-element)                 | 支持          | 17763             |
| POST        | /session/{session id}/element                                  | [查找元素](https://www.w3.org/TR/webdriver/#find-element)                             | 支持          | 17763             |
| POST        | /session/{session id}/elements                                 | [查找元素](https://www.w3.org/TR/webdriver/#find-elements)                           | 支持          | 17763             |
| POST        | /session/{session id}/element/{element id}/element             | [从元素中查找元素](https://www.w3.org/TR/webdriver/#find-element-from-element)   | 支持          | 17763             |
| POST        | /session/{session id}/element/{element id}/elements            | [查找元素中的元素](https://www.w3.org/TR/webdriver/#find-elements-from-element) | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/selected            | [已选中元素](https://www.w3.org/TR/webdriver/#is-element-selected)               | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/attribute/{name}    | [获取元素属性](https://www.w3.org/TR/webdriver/#get-element-attribute)           | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/property/{name}     | [获取元素属性](https://www.w3.org/TR/webdriver/#get-element-property)             | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/css/{property name} | [获取元素 CSS 值](https://www.w3.org/TR/webdriver/#get-element-css-value)           | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/text                | [获取元素文本](https://www.w3.org/TR/webdriver/#get-element-text)                     | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/name                | [获取元素标记名称](https://www.w3.org/TR/webdriver/#get-element-tag-name)             | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/rect                | [获取元素 Rect](https://www.w3.org/TR/webdriver/#get-element-rect)                     | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/enabled             | [元素是否已启用](https://www.w3.org/TR/webdriver/#is-element-enabled)                 | 支持          | 17763             |
| POST        | /session/{session id}/element/{element id}/click               | [元素单击](https://www.w3.org/TR/webdriver/#element-click)                           | 支持          | 17763             |
| POST        | /session/{session id}/element/{element id}/clear               | [元素清除](https://www.w3.org/TR/webdriver/#element-clear)                           | 支持          | 17763             |
| POST        | /session/{session id}/element/{element id}/sendKeys            | [元素发送键](https://www.w3.org/TR/webdriver/#element-send-keys)                   | 支持          | 17763             |
| GET         | /session/{session id}/source                                   | [获取页面源](https://www.w3.org/TR/webdriver/#get-page-source)                       | 支持          | 17763             |
| POST        | /session/{session id}/execute/sync                             | [执行脚本](https://www.w3.org/TR/webdriver/#execute-script)                         | 支持          | 17763             |
| POST        | /session/{session id}/execute/async                            | [执行异步脚本](https://www.w3.org/TR/webdriver/#execute-async-script)             | 支持          | 17763             |
| GET         | /session/{session id}/cookie                                   | [获取所有 Cookie](https://www.w3.org/TR/webdriver/#get-all-cookies)                       | 支持          | 17763             |
| GET         | /session/{session id}/cookie/{name}                            | [获取命名的 Cookie](https://www.w3.org/TR/webdriver/#get-named-cookie)                     | 支持          | 17763             |
| POST        | /session/{session id}/cookie                                   | [添加 Cookie](https://www.w3.org/TR/webdriver/#add-cookie)                                 | 支持          | 17763             |
| DELETE      | /session/{session id}/cookie/{name}                            | [删除 Cookie](https://www.w3.org/TR/webdriver/#delete-cookie)                           | 支持          | 17763             |
| DELETE      | /session/{session id}/cookie                                   | [删除所有 Cookie](https://www.w3.org/TR/webdriver/#delete-all-cookies)                 | 支持          | 17763             |
| POST        | /session/{session id}/actions                                  | [执行操作](https://www.w3.org/TR/webdriver/#perform-actions)                       | 支持          | 17763             |
| DELETE      | /session/{session id}/actions                                  | [发布操作](https://www.w3.org/TR/webdriver/#release-actions)                       | 支持          | 17763             |
| POST        | /session/{session id}/alert/dismiss                            | [消除警告](https://www.w3.org/TR/webdriver/#dismiss-alert)                           | 支持          | 17763             |
| POST        | /session/{session id}/alert/accept                             | [接受通知](https://www.w3.org/TR/webdriver/#accept-alert)                             | 支持          | 17763             |
| GET         | /session/{session id}/alert/text                               | [获取通知文本](https://www.w3.org/TR/webdriver/#get-alert-text)                         | 支持          | 17763             |
| POST        | /session/{session id}/alert/text                               | [发送提醒文本](https://www.w3.org/TR/webdriver/#send-alert-text)                       | 支持          | 17763             |
| GET         | /session/{session id}/screenshot                               | [获取屏幕截图](https://www.w3.org/TR/webdriver/#take-screenshot)                       | 支持          | 17763             |
| GET         | /session/{session id}/screenshot/{element id}                  | [获取元素屏幕截图](https://www.w3.org/TR/webdriver/#take-element-screenshot)       | 支持          | 17763             |

## JSON 线路协议
针对 [JSON 线路协议](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol)对每个命令的支持。

### 命令
| HTTP 方法 | 路径                                                                                                                                                         | 状态             | 可用版本 |
|:------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------|:------------------|
| GET         | [/status](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#status)                                                                               | 支持          | 10240             |
| POST        | [/session](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#session-1)                                                                           | 支持          | 10240             |
| GET         | [/sessions](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessions)                                                                           | 支持          | 10240             |
| GET         | [/session/： sessionId](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionid)                                                         | 支持          | 10240             |
| DELETE      | [/session/： sessionId](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionid)                                                         | 支持          | 10240             |
| POST        | [/session/： sessionId/超时](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtimeouts)                                        | 支持          | 10240             |
| POST        | [/session/： sessionId/超时/async_script](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtimeoutsasync_script)               | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/超时/implicit_wait](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtimeoutsimplicit_wait)             | 支持          | 10586             |
| GET         | [/session/： sessionId/window_handle](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow_handle)                              | 支持          | 10586             |
| GET         | [/session/： sessionId/window_handles](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow_handles)                            | 支持          | 10586             |
| GET         | [/session/： sessionId/url](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidurl)                                                  | 支持          | 10240             |
| POST        | [/session/： sessionId/url](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidurl)                                                  | 支持          | 10240             |
| POST        | [/session/： sessionId/forward](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidforward)                                          | 支持          | 10240             |
| POST        | [/session/： sessionId/back](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidback)                                                | 支持          | 10240             |
| POST        | [/session/： sessionId/refresh](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidrefresh)                                          | 支持          | 10240             |
| POST        | [/session/： sessionId/execute](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidexecute)                                          | 支持          | 10240             |
| POST        | [/session/： sessionId/execute_async](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidexecute_async)                              | 支持          | 10586             |
| GET         | [/session/： sessionId/屏幕截图](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidscreenshot)                                    | 支持          | 10240             |
| GET         | [/session/： sessionId/ime/available_engines](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeavailable_engines)               | 不 &nbsp; 支持 | 不适用               |
| GET         | [/session/： sessionId/ime/active_engine](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeactive_engine)                       | 不 &nbsp; 支持 | 不适用               |
| GET         | [/session/： sessionId/ime/已激活](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeactivated)                               | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/ime/停用](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimedeactivate)                             | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/ime/激活](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeactivate)                                 | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/frame](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidframe)                                              | 支持          | 10586             |
| POST        | [/session/： sessionId/frame/parent](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidframeparent)                                 | 支持          | 10586             |
| POST        | [/session/： sessionId/window](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow)                                            | 支持          | 10586             |
| DELETE      | [/session/： sessionId/window](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow)                                            | 支持          | 10586             |
| POST        | [/session/： sessionId/window/： windowHandle/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandlesize)         | 支持          | 10586             |
| GET         | [/session/： sessionId/window/： windowHandle/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandlesize)         | 支持          | 10586             |
| POST        | [/session/： sessionId/window/： windowHandle/position](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandleposition) | 支持          | 10586             |
| GET         | [/session/： sessionId/window/： windowHandle/position](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandleposition) | 支持          | 10586             |
| GET         | [/session/： sessionId/window/： windowHandle/最大化](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandlemaximize) | 支持          | 10586             |
| GET         | [/session/： sessionId/cookie](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookie)                                            | 支持          | 10586             |
| POST        | [/session/： sessionId/cookie](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookie)                                            | 支持          | 10240             |
| DELETE      | [/session/： sessionId/cookie](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookie)                                            | 支持          | 10586             |
| DELETE      | [/session/： sessionId/cookie/： name](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookiename)                                  | 支持          | 10240             |
| GET         | [/session/： sessionId/source](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsource)                                            | 支持          | 10586             |
| GET         | [/session/： sessionId}/title](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtitle)                                             | 支持          | 10240             |
| POST        | [/session/： sessionId/element](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelement)                                          | 支持          | 10586             |
| POST        | [/session/： sessionId/元素](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelements)                                        | 支持          | 10586             |
| POST        | [/session/： sessionId/element/active](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementactive)                             | 支持          | 10586             |
| GET         | [/session/： sessionId/element/： id](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementid)                                    | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/element/： id/元素](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidelement)                     | 支持          | 10586             |
| POST        | [/session/： sessionId/element/： id/元素](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidelements)                   | 支持          | 10586             |
| POST        | [/session/： sessionId/element/： id/单击](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidclick)                         | 支持          | 10240             |
| POST        | [/session/： sessionId/element/： id/提交](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidsubmit)                       | 支持          | 10586             |
| GET         | [/session/： sessionId/element/： id/text](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidtext)                           | 支持          | 10240             |
| POST        | [/session/： sessionId/element/： id/value](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidvalue)                         | 支持          | 10240             |
| POST        | [/session/： sessionId/keys](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidkeys)                                                | 支持          | 10586             |
| GET         | [/session/： sessionId/element/： id/名称](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidname)                           | 支持          | 10240             |
| POST        | [/session/： sessionId/element/： id/clear](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidclear)                         | 支持          | 10240             |
| GET         | [/session/： sessionId/element/： id/已选中](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidselected)                   | 支持          | 10240             |
| GET         | [/session/： sessionId/element/： id/已启用](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidenabled)                     | 支持          | 10240             |
| GET         | [/session/： sessionId/element/： id/attribute/： name](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidattribute/:name)     | 支持          | 10240             |
| GET         | [/session/： sessionId/element/： id/等于/：其他](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidequals/:other)         | 支持          | 10586             |
| GET         | [/session/： sessionId/element/： id/显示](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementiddisplayed)                 | 支持          | 10240             |
| GET         | [/session/： sessionId/element/： id/location](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidlocation)                   | 支持          | 10586             |
| GET         | [/session/： sessionId/element/： id/location_in_view](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidlocation_in_view)   | 支持          | 10586             |
| GET         | [/session/： sessionId/element/： id/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidsize)                           | 支持          | 10586             |
| GET         | [/session/： sessionId/element/： id/css/:p ropertyName](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidcss/:propertyName) | 支持          | 10240             |
| GET         | [/session/： sessionId/方向](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidorientation)                                  | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/方向](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidorientation)                                  | 不 &nbsp; 支持 | 不适用               |
| GET         | [/session/： sessionId/alert_text](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidalert_text)                                    | 支持          | 10240             |
| POST        | [/session/： sessionId/alert_text](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidalert_text)                                    | 支持          | 10586             |
| POST        | [/session/： sessionId/accept_alert](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidaccept_alert)                                | 支持          | 10240             |
| POST        | [/session/： sessionId/dismiss_alert](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessioniddismiss_alert)                              | 支持          | 10240             |
| POST        | [/session/： sessionId/moveto](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidmoveto)                                            | 支持          | 10586             |
| POST        | [/session/： sessionId/click](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidclick)                                              | 支持          | 10240             |
| POST        | [/session/： sessionId/buttondown](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidbuttondown)                                    | 支持          | 10586             |
| POST        | [/session/： sessionId/buttonup](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidbuttonup)                                        | 支持          | 10586             |
| POST        | [/session/： sessionId/doubleclick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessioniddoubleclick)                                  | 支持          | 10586             |
| POST        | [/session/： sessionId/触摸/单击](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchclick)                                   | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/触控/关闭](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchdown)                                     | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/touch/up](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchup)                                         | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/触控/移动](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchmove)                                     | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/触控/滚动](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchscroll)                                 | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/触控/滚动](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchscroll-1)                               | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/触控/doubleclick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchdoubleclick)                       | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/触控/longclick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchlongclick)                           | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/触控/笔锋](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchflick)                                   | 不 &nbsp; 支持 | 不适用               |
| POST        | [/session/： sessionId/触控/笔锋](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchflick-1)                                 | 不 &nbsp; 支持 | 不适用               |
| GET         | [/session/： sessionId/location](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocation)                                        | 支持          | 10586             |
| POST        | [/session/： sessionId/location](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocation)                                        | 支持          | 10586             |
| GET         | [/session/： sessionId/local_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storage)                              | 支持          | 10586             |
| POST        | [/session/： sessionId/local_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storage)                              | 支持          | 10586             |
| DELETE      | [/session/： sessionId/local_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storage)                              | 支持          | 10586             |
| GET         | [/session/： sessionId/local_storage/key/： key](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storagekeykey)               | 支持          | 10586             |
| DELETE      | [/session/： sessionId/local_storage/key/： key](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storagekeykey)               | 支持          | 10586             |
| GET         | [/session/： sessionId/local_storage/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storagesize)                     | 支持          | 10586             |
| GET         | [/session/： sessionId/session_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storage)                          | 支持          | 10586             |
| POST        | [/session/： sessionId/session_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storage)                          | 支持          | 10586             |
| DELETE      | [/session/： sessionId/session_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storage)                          | 支持          | 10586             |
| GET         | [/session/： sessionId/session_storage/key/： key](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storagekeykey)           | 支持          | 10586             |
| DELETE      | [/session/： sessionId/session_storage/key/： key](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storagekeykey)           | 支持          | 10586             |
| GET         | [/session/： sessionId/session_storage/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storagesize)                 | 支持          | 10586             |
| GET         | [/session/： sessionId/log](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlog)                                                  | 不 &nbsp; 支持 | 不适用               |
| GET         | [/session/： sessionId/log/types](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlogtypes)                                       | 不 &nbsp; 支持 | 不适用               |
| GET         | [/session/： sessionId/application_cache/status](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidapplication_cachestatus)         | 支持          | 10586             |  
