---
ms.assetid: e56172c0-b635-4c02-8e0c-56bf8cb4c164
description: 了解如何开始使用 WebDriver，这是一种允许程序和脚本控制 Web 浏览器行为的线路协议。
title: WebDriver (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: edge， Web 开发， html， css， javascript， 开发人员， webdriver， selenium， 测试
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ab26931c09ecbae41ae88734b25038d21c93c0f6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232379"
---
# WebDriver (EdgeHTML)

W3C [WebDriver](https://www.w3.org/TR/webdriver/) API 是一个平台和中性语言接口以及线路协议，允许程序或脚本控制 Web 浏览器的行为。

WebDriver 使开发人员能够创建模拟用户交互的自动测试。 这不同于 JavaScript 单元测试，因为 WebDriver 可以访问浏览器中运行的 JavaScript 所没有的功能和信息，并且它可以更加准确地模拟用户事件或操作系统级事件。 WebDriver 还可以在单个测试会话中跨多个窗口、选项卡和网页管理测试。

下面将了解如何开始使用适用于 Microsoft Edge 和 EdgeHTML (WebDriver) 。

Microsoft Edge (EdgeHTML) [WebDriver](https://www.w3.org/TR/webdriver/) 实现支持 W3C WebDriver 规范以及 [JSON 线路](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol) 协议，以与现有测试向后兼容。

## Microsoft Edge 和 EdgeHTML (WebDriver) 
* 安装 Windows 10。
* 下载适用于 [Windows](https://developer.microsoft.com/microsoft-edge/tools/webdriver/) 版本和 Microsoft Edge (EdgeHTML) 。
* 下载你选择的 WebDriver 语言绑定。 [所有 Selenium 语言绑定都支持 Microsoft Edge (EdgeHTML) 。 ](https://docs.seleniumhq.org/download/)

> [!NOTE]
> 可以在 Microsoft Edge (EdgeHTML) 反馈或支持&帮助、报告问题和 [&请求](https://developer.microsoft.com/microsoft-edge/support/)。


## 使用 WebDriver
若要开始将 WebDriver 与 Microsoft Edge (EdgeHTML) ，请查看这些示例：

* [C\# 代码示例](https://gist.github.com/InstyleVII/baf25274c55e891076d5#file-webdriver-cs) ，用于打开浏览器窗口、导航到 bing.com 并搜索 GitHub Gist ("webdriver") 。

## WebDriver 服务器命令行标志
WebDriver 服务器的命令行标志列表。

| 名称    | 描述                                                                                                      | 可用版本 |
|:--------|:-----------------------------------------------------------------------------------------------------------------|:------------------|
| host    | 要用于 WebDriver 服务器的主机 IP 默认 (：localhost)                                                      | 14393             |
| 端口    | 要用于 WebDriver 服务器的端口 (默认值：17556)                                                             | 14393             |
| package | ApplicationUserModelId (AUMID) ，供 WebDriver 服务器启动的应用程序使用 AUMID                        | 14393             |
| verbose | WebDriver 服务器接收的输出请求和发送的响应                                             | 14393             |
| silent  | 不输出任何数据                                                                                                  | 15063             |
| version | 输出版本MicrosoftWebDriver.exe                                                                    | 17763             |
| w3c     | 使用 W3C WebDriver (默认选项)                                                                       | 17763             |
| jwp     | 使用 JSON 线路协议                                                                                           | 17763             |
| cleanup | 清理 WebDriver 服务器为 --package 设置的临时数据和注册表项。 其他参数将被忽略 | 17763             |

## W3C WebDriver
基于每个命令对 [W3C WebDriver 规范的支持](https://www.w3.org/TR/webdriver/)。

### 功能
| 功能                       | 密钥                       | 状态                   | 可用版本 |
|:---------------------------------|:--------------------------|:-------------------------|:------------------|
| 浏览器名称                     | "browserName"             | 支持                | 17763             |
| 浏览器版本                  | "browserVersion"          | 支持                | 17763             |
| 平台名称                    | "platformName"            | 支持                | 17763             |
| 接受不安全的 TLS 证书 | "acceptInsecureCerts"     | 不支持 &nbsp;       | 不适用               |
| 页面加载策略               | "pageLoadStrategy"        | 支持                | 17763             |
| 代理配置              | "proxy"                   | 不支持 &nbsp;       | 不适用               |
| 窗口尺寸/定位  | "setWindowRect"           | 支持                | 17763             |
| 会话超时配置   | "timeouts"                | 支持                | 17763             |
| 未处理提示行为        | "unhandledPromptBehavior" | 部分 &nbsp; 支持 | 17763             |
| InPrivate                        | "ms：inPrivate"            | 支持                | 17763             |
| 扩展路径                  | "ms：extensionPaths"       | 支持                | 17763             |
| 起始页                       | "ms：startPage"            | 支持                | 17763             |

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
| POST        | /session                                                       | [新建会话](https://www.w3.org/TR/webdriver/#new-session)                               | 支持          | 17763             |
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
| POST        | /session/{session id}/frame                                    | [切换到帧](https://www.w3.org/TR/webdriver/#switch-to-frame)                       | 支持          | 17763             |
| POST        | /session/{session id}/frame/parent                             | [切换到父框架](https://www.w3.org/TR/webdriver/#switch-to-parent-frame)         | 支持          | 17763             |
| GET         | /session/{session id}/window/rect                              | [获取 Window Rect](https://www.w3.org/TR/webdriver/#get-window-rect)                       | 支持          | 17763             |
| POST        | /session/{session id}/window/rect                              | [设置窗口矩形](https://www.w3.org/TR/webdriver/#set-window-rect)                       | 支持          | 17763             |
| POST        | /session/{session id}/window/maximize                          | [最大化窗口](https://www.w3.org/TR/webdriver/#maximize-window)                       | 支持          | 17763             |
| POST        | /session/{session id}/window/minimize                          | [最小化窗口](https://www.w3.org/TR/webdriver/#minimize-window)                       | 支持          | 17763             |
| POST        | /session/{session id}/window/fullscreen                        | [全屏窗口](https://www.w3.org/TR/webdriver/#fullscreen-window)                   | 不支持 &nbsp; | 不适用               |
| GET         | /session/{session id}/element/active                           | [获取 Active 元素](https://www.w3.org/TR/webdriver/#get-active-element)                 | 支持          | 17763             |
| POST        | /session/{session id}/element                                  | [Find 元素](https://www.w3.org/TR/webdriver/#find-element)                             | 支持          | 17763             |
| POST        | /session/{session id}/elements                                 | [查找元素](https://www.w3.org/TR/webdriver/#find-elements)                           | 支持          | 17763             |
| POST        | /session/{session id}/element/{element id}/element             | [Find Element From Element](https://www.w3.org/TR/webdriver/#find-element-from-element)   | 支持          | 17763             |
| POST        | /session/{session id}/element/{element id}/elements            | [从元素中查找元素](https://www.w3.org/TR/webdriver/#find-elements-from-element) | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/selected            | [Is 元素已选中](https://www.w3.org/TR/webdriver/#is-element-selected)               | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/attribute/{name}    | [Get Element 属性](https://www.w3.org/TR/webdriver/#get-element-attribute)           | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/property/{name}     | [Get Element 属性](https://www.w3.org/TR/webdriver/#get-element-property)             | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/css/{property name} | [获取元素 CSS 值](https://www.w3.org/TR/webdriver/#get-element-css-value)           | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/text                | [获取元素文本](https://www.w3.org/TR/webdriver/#get-element-text)                     | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/name                | [获取元素标记名称](https://www.w3.org/TR/webdriver/#get-element-tag-name)             | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/rect                | [Get 元素 Rect](https://www.w3.org/TR/webdriver/#get-element-rect)                     | 支持          | 17763             |
| GET         | /session/{session id}/element/{element id}/enabled             | [Is 元素已启用](https://www.w3.org/TR/webdriver/#is-element-enabled)                 | 支持          | 17763             |
| POST        | /session/{session id}/element/{element id}/click               | [元素单击](https://www.w3.org/TR/webdriver/#element-click)                           | 支持          | 17763             |
| POST        | /session/{session id}/element/{element id}/clear               | [元素清除](https://www.w3.org/TR/webdriver/#element-clear)                           | 支持          | 17763             |
| POST        | /session/{session id}/element/{element id}/sendKeys            | [元素发送密钥](https://www.w3.org/TR/webdriver/#element-send-keys)                   | 支持          | 17763             |
| GET         | /session/{session id}/source                                   | [获取页面源](https://www.w3.org/TR/webdriver/#get-page-source)                       | 支持          | 17763             |
| POST        | /session/{session id}/execute/sync                             | [执行脚本](https://www.w3.org/TR/webdriver/#execute-script)                         | 支持          | 17763             |
| POST        | /session/{session id}/execute/async                            | [执行异步脚本](https://www.w3.org/TR/webdriver/#execute-async-script)             | 支持          | 17763             |
| GET         | /session/{session id}/cookie                                   | [获取所有 Cookie](https://www.w3.org/TR/webdriver/#get-all-cookies)                       | 支持          | 17763             |
| GET         | /session/{session id}/cookie/{name}                            | [获取命名 Cookie](https://www.w3.org/TR/webdriver/#get-named-cookie)                     | 支持          | 17763             |
| POST        | /session/{session id}/cookie                                   | [添加 Cookie](https://www.w3.org/TR/webdriver/#add-cookie)                                 | 支持          | 17763             |
| DELETE      | /session/{session id}/cookie/{name}                            | [删除 Cookie](https://www.w3.org/TR/webdriver/#delete-cookie)                           | 支持          | 17763             |
| DELETE      | /session/{session id}/cookie                                   | [删除所有 Cookie](https://www.w3.org/TR/webdriver/#delete-all-cookies)                 | 支持          | 17763             |
| POST        | /session/{session id}/actions                                  | [执行操作](https://www.w3.org/TR/webdriver/#perform-actions)                       | 支持          | 17763             |
| DELETE      | /session/{session id}/actions                                  | [释放操作](https://www.w3.org/TR/webdriver/#release-actions)                       | 支持          | 17763             |
| POST        | /session/{session id}/alert/dismiss                            | [消除警报](https://www.w3.org/TR/webdriver/#dismiss-alert)                           | 支持          | 17763             |
| POST        | /session/{session id}/alert/accept                             | [接受警报](https://www.w3.org/TR/webdriver/#accept-alert)                             | 支持          | 17763             |
| GET         | /session/{session id}/alert/text                               | [获取警报文本](https://www.w3.org/TR/webdriver/#get-alert-text)                         | 支持          | 17763             |
| POST        | /session/{session id}/alert/text                               | [发送通知文本](https://www.w3.org/TR/webdriver/#send-alert-text)                       | 支持          | 17763             |
| GET         | /session/{session id}/screenshot                               | [拍摄屏幕截图](https://www.w3.org/TR/webdriver/#take-screenshot)                       | 支持          | 17763             |
| GET         | /session/{session id}/screenshot/{element id}                  | [Take 元素屏幕截图](https://www.w3.org/TR/webdriver/#take-element-screenshot)       | 支持          | 17763             |

## JSON 线路协议
基于每个命令对 [JSON 线路协议的支持](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol)。

### 命令
| HTTP 方法 | 路径                                                                                                                                                         | 状态             | 可用版本 |
|:------------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------|:-------------------|:------------------|
| GET         | [/status](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#status)                                                                               | 支持          | 10240             |
| POST        | [/session](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#session-1)                                                                           | 支持          | 10240             |
| GET         | [/sessions](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessions)                                                                           | 支持          | 10240             |
| GET         | [/session/：sessionId](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionid)                                                         | 支持          | 10240             |
| DELETE      | [/session/：sessionId](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionid)                                                         | 支持          | 10240             |
| POST        | [/session/：sessionId/timeouts](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtimeouts)                                        | 支持          | 10240             |
| POST        | [/session/：sessionId/timeouts/async_script](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtimeoutsasync_script)               | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/timeouts/implicit_wait](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtimeoutsimplicit_wait)             | 支持          | 10586             |
| GET         | [/session/：sessionId/window_handle](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow_handle)                              | 支持          | 10586             |
| GET         | [/session/：sessionId/window_handles](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow_handles)                            | 支持          | 10586             |
| GET         | [/session/：sessionId/url](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidurl)                                                  | 支持          | 10240             |
| POST        | [/session/：sessionId/url](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidurl)                                                  | 支持          | 10240             |
| POST        | [/session/：sessionId/forward](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidforward)                                          | 支持          | 10240             |
| POST        | [/session/：sessionId/back](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidback)                                                | 支持          | 10240             |
| POST        | [/session/：sessionId/refresh](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidrefresh)                                          | 支持          | 10240             |
| POST        | [/session/：sessionId/execute](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidexecute)                                          | 支持          | 10240             |
| POST        | [/session/：sessionId/execute_async](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidexecute_async)                              | 支持          | 10586             |
| GET         | [/session/：sessionId/screenshot](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidscreenshot)                                    | 支持          | 10240             |
| GET         | [/session/：sessionId/ime/available_engines](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeavailable_engines)               | 不支持 &nbsp; | 不适用               |
| GET         | [/session/：sessionId/ime/active_engine](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeactive_engine)                       | 不支持 &nbsp; | 不适用               |
| GET         | [/session/：sessionId/ime/activated](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeactivated)                               | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/ime/deactivate](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimedeactivate)                             | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/ime/activate](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidimeactivate)                                 | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/frame](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidframe)                                              | 支持          | 10586             |
| POST        | [/session/：sessionId/frame/parent](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidframeparent)                                 | 支持          | 10586             |
| POST        | [/session/：sessionId/window](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow)                                            | 支持          | 10586             |
| DELETE      | [/session/：sessionId/window](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindow)                                            | 支持          | 10586             |
| POST        | [/session/：sessionId/window/：windowHandle/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandlesize)         | 支持          | 10586             |
| GET         | [/session/：sessionId/window/：windowHandle/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandlesize)         | 支持          | 10586             |
| POST        | [/session/：sessionId/window/：windowHandle/position](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandleposition) | 支持          | 10586             |
| GET         | [/session/：sessionId/window/：windowHandle/position](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandleposition) | 支持          | 10586             |
| GET         | [/session/：sessionId/window/：windowHandle/maximize](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidwindowwindowhandlemaximize) | 支持          | 10586             |
| GET         | [/session/：sessionId/cookie](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookie)                                            | 支持          | 10586             |
| POST        | [/session/：sessionId/cookie](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookie)                                            | 支持          | 10240             |
| DELETE      | [/session/：sessionId/cookie](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookie)                                            | 支持          | 10586             |
| DELETE      | [/session/：sessionId/cookie/：name](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidcookiename)                                  | 支持          | 10240             |
| GET         | [/session/：sessionId/source](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsource)                                            | 支持          | 10586             |
| GET         | [/session/：sessionId}/title](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtitle)                                             | 支持          | 10240             |
| POST        | [/session/：sessionId/element](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelement)                                          | 支持          | 10586             |
| POST        | [/session/：sessionId/elements](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelements)                                        | 支持          | 10586             |
| POST        | [/session/：sessionId/element/active](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementactive)                             | 支持          | 10586             |
| GET         | [/session/：sessionId/element/：id](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementid)                                    | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/element/：id/element](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidelement)                     | 支持          | 10586             |
| POST        | [/session/：sessionId/element/：id/elements](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidelements)                   | 支持          | 10586             |
| POST        | [/session/：sessionId/element/：id/click](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidclick)                         | 支持          | 10240             |
| POST        | [/session/：sessionId/element/：id/submit](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidsubmit)                       | 支持          | 10586             |
| GET         | [/session/：sessionId/element/：id/text](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidtext)                           | 支持          | 10240             |
| POST        | [/session/：sessionId/element/：id/value](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidvalue)                         | 支持          | 10240             |
| POST        | [/session/：sessionId/keys](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidkeys)                                                | 支持          | 10586             |
| GET         | [/session/：sessionId/element/：id/name](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidname)                           | 支持          | 10240             |
| POST        | [/session/：sessionId/element/：id/clear](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidclear)                         | 支持          | 10240             |
| GET         | [/session/：sessionId/element/：id/selected](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidselected)                   | 支持          | 10240             |
| GET         | [/session/：sessionId/element/：id/enabled](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidenabled)                     | 支持          | 10240             |
| GET         | [/session/：sessionId/element/：id/attribute/：name](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidattribute/:name)     | 支持          | 10240             |
| GET         | [/session/：sessionId/element/：id/equals/：other](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidequals/:other)         | 支持          | 10586             |
| GET         | [/session/：sessionId/element/：id/displayed](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementiddisplayed)                 | 支持          | 10240             |
| GET         | [/session/：sessionId/element/：id/location](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidlocation)                   | 支持          | 10586             |
| GET         | [/session/：sessionId/element/：id/location_in_view](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidlocation_in_view)   | 支持          | 10586             |
| GET         | [/session/：sessionId/element/：id/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidsize)                           | 支持          | 10586             |
| GET         | [/session/：sessionId/element/：id/css/:p ropertyName](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidelementidcss/:propertyName) | 支持          | 10240             |
| GET         | [/session/：sessionId/orientation](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidorientation)                                  | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/orientation](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidorientation)                                  | 不支持 &nbsp; | 不适用               |
| GET         | [/session/：sessionId/alert_text](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidalert_text)                                    | 支持          | 10240             |
| POST        | [/session/：sessionId/alert_text](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidalert_text)                                    | 支持          | 10586             |
| POST        | [/session/：sessionId/accept_alert](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidaccept_alert)                                | 支持          | 10240             |
| POST        | [/session/：sessionId/dismiss_alert](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessioniddismiss_alert)                              | 支持          | 10240             |
| POST        | [/session/：sessionId/moveto](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidmoveto)                                            | 支持          | 10586             |
| POST        | [/session/：sessionId/click](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidclick)                                              | 支持          | 10240             |
| POST        | [/session/：sessionId/buttondown](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidbuttondown)                                    | 支持          | 10586             |
| POST        | [/session/：sessionId/buttonup](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidbuttonup)                                        | 支持          | 10586             |
| POST        | [/session/：sessionId/doubleclick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessioniddoubleclick)                                  | 支持          | 10586             |
| POST        | [/session/：sessionId/touch/click](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchclick)                                   | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/touch/down](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchdown)                                     | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/touch/up](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchup)                                         | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/touch/move](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchmove)                                     | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/touch/scroll](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchscroll)                                 | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/touch/scroll](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchscroll-1)                               | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/touch/doubleclick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchdoubleclick)                       | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/touch/longclick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchlongclick)                           | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/touch/flick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchflick)                                   | 不支持 &nbsp; | 不适用               |
| POST        | [/session/：sessionId/touch/flick](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidtouchflick-1)                                 | 不支持 &nbsp; | 不适用               |
| GET         | [/session/：sessionId/location](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocation)                                        | 支持          | 10586             |
| POST        | [/session/：sessionId/location](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocation)                                        | 支持          | 10586             |
| GET         | [/session/：sessionId/local_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storage)                              | 支持          | 10586             |
| POST        | [/session/：sessionId/local_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storage)                              | 支持          | 10586             |
| DELETE      | [/session/：sessionId/local_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storage)                              | 支持          | 10586             |
| GET         | [/session/：sessionId/local_storage/key/：key](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storagekeykey)               | 支持          | 10586             |
| DELETE      | [/session/：sessionId/local_storage/key/：key](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storagekeykey)               | 支持          | 10586             |
| GET         | [/session/：sessionId/local_storage/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlocal_storagesize)                     | 支持          | 10586             |
| GET         | [/session/：sessionId/session_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storage)                          | 支持          | 10586             |
| POST        | [/session/：sessionId/session_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storage)                          | 支持          | 10586             |
| DELETE      | [/session/：sessionId/session_storage](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storage)                          | 支持          | 10586             |
| GET         | [/session/：sessionId/session_storage/key/：key](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storagekeykey)           | 支持          | 10586             |
| DELETE      | [/session/：sessionId/session_storage/key/：key](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storagekeykey)           | 支持          | 10586             |
| GET         | [/session/：sessionId/session_storage/size](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidsession_storagesize)                 | 支持          | 10586             |
| GET         | [/session/：sessionId/log](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlog)                                                  | 不支持 &nbsp; | 不适用               |
| GET         | [/session/：sessionId/log/types](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidlogtypes)                                       | 不支持 &nbsp; | 不适用               |
| GET         | [/session/：sessionId/application_cache/status](https://github.com/SeleniumHQ/selenium/wiki/JsonWireProtocol#sessionsessionidapplication_cachestatus)         | 支持          | 10586             |  
