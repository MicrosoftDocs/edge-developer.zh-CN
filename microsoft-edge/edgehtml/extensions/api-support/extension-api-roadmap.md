---
description: 查找有关完成 Microsoft Edge 扩展 API 的当前进度的信息。
title: 扩展 API 路线图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， api， 扩展， javascript， 开发人员
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d3552fede729a37ff83ac4b19cfadf89d6917a75
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232720"
---
# Microsoft Edge 扩展 API 路线图  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

除了 Web API 之外，扩展 API 还允许扩展与浏览器主机进行更深入的集成。 此 API 使开发人员能够访问 Microsoft Edge 的浏览器功能，如选项卡和窗口操作。 下表详细介绍了 Windows 10 公开发布的 Microsoft Edge 版本在开发中支持/开发哪些 API。


|     类     |                                                              描述                                                              |                状态 — 内部版本号                 |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
|   书签   |                                          用于创建、组织和操作书签。                                          | 支持 - Microsoft Edge (40) /Windows 10 (15063)  |
| browserAction |                                 允许扩展在 Microsoft Edge 中添加永久性按钮。                                  | 支持 - Microsoft Edge (38) /Windows 10 (14393)  |
| 命令      |                                                      定义键盘快捷方式。                                                      | 正在考虑
| contextMenus  |                           在网页的指定上下文中，将上下文菜单项添加到特定 URL 上。                            | 支持 - Microsoft Edge (38) /Windows 10 (14393)  |
|    Cookie    |                                 用于查询和修改 Cookie，以及通知它们何时更改。                                 | 支持 - Microsoft Edge (38) /Windows 10 (14393)  |
|   downloads   |                           用于以编程方式启动、监视、操作和搜索下载。                           |                 正在考虑                  |
|   extension   |                                      包含任何扩展页都可以使用的实用程序。                                       | 支持 - Microsoft Edge (38) /Windows 10 (14393)  |
|    历史记录    |                                         与浏览器的已访问页面记录交互。                                         |                 正在考虑                  |
|     i18n      |                                         跨扩展实现国际化。                                          | 支持 - Microsoft Edge (38) /Windows 10 (14393)  |
|   身份    |                                       用于获取 OAuth2 授权代码或访问令牌。                                       |                 正在考虑                  |
|     idle      |                                       用于检测计算机空闲状态何时更改。                                        | 支持 - Microsoft Edge (38) /Windows 10 (14393)  |
|  管理   |                                              获取有关已安装的加载项的信息。                                                |                 正在考虑                  |
| 通知 |                      允许使用模板创建通知，以在用户的系统托盘中显示。                      | 支持 - Microsoft Edge (42) /Windows 10 (17134)  |
|  pageAction   |                                      允许扩展在地址栏内添加按钮。                                       | 支持 - Microsoft Edge (38) /Windows 10 (14393)  |
|  permissions  |                   允许用户选择要授予其扩展访问权限的可选权限。                   |                 正在考虑                  |
|    runtime    | 检索后台页面，返回有关清单的详细信息，并侦听和响应扩展生命周期中的事件。 | 支持 - Microsoft Edge (38) /Windows 10 (14393)  |
|    存储    |                                      由扩展用来读取/写入数据和同步数据。                                       | 支持 - Microsoft Edge (38) /Windows 10 (14393)  |
|     选项卡      |                通过创建、修改和重新排列浏览器中的选项卡，与 Microsoft Edge 的选项卡系统进行交互。                | 支持 - Microsoft Edge (38) /Windows 10 (14393)  |
| webNavigation |                           用于接收有关进行中的导航请求状态的通知。                            | 支持 - Microsoft Edge (38) /Windows 10 (14393)  |
|  webRequest   |        允许使用 webRequest API 观察和分析流量，以及截获、阻止或修改实时请求。        | 支持 - Microsoft Edge (38) /Windows 10 (14393)  |
|    windows    |                              通过创建、修改和重新设置窗口与浏览器交互。                              | 支持 - Microsoft Edge (38) /Windows 10 (14393)  |
