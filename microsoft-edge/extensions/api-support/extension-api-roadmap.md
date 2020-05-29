---
description: 查找有关完成 Microsoft Edge 扩展 API 的当前进度的信息。
title: 扩展 API 路线图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、api、扩展、javascript、开发人员
ms.custom: seodec18
ms.openlocfilehash: ce40dd2d37b7ef446516a743286c5285ad3187a6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563334"
---
# Microsoft Edge 扩展 API 路线图  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

除了 web Api，扩展 API 还允许扩展 API 实现与浏览器主机更深的集成。 此 API 使开发人员能够访问 Microsoft Edge 的浏览器功能，例如 tab 和窗口操作。 下表详细介绍了 Windows 10 公开发布的 Microsoft Edge 版本所支持的和在开发中支持的 Api。


|     类     |                                                              描述                                                              |                状态-内部版本号                 |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
|   书签   |                                          用于创建、组织和处理书签。                                          | 支持-Microsoft Edge （40）/Windows 10 （15063） |
| browserAction |                                 启用 "扩展" 以在 Microsoft Edge 中添加一个永久按钮。                                  | 支持-Microsoft Edge （38）/Windows 10 （14393） |
| 命令      |                                                      定义键盘快捷方式。                                                      | "考虑"
| contextMenus  |                           在指定的网页上下文中的特定 URL 上添加上下文菜单项。                            | 支持-Microsoft Edge （38）/Windows 10 （14393） |
|    Cookie    |                                 用于查询和修改 cookie，以及在更改时发出通知。                                 | 支持-Microsoft Edge （38）/Windows 10 （14393） |
|   downloads   |                           用于以编程方式启动、监视、操作和搜索下载。                           |                 "考虑"                  |
|   线   |                                      包含可由任何扩展页面使用的实用工具。                                       | 支持-Microsoft Edge （38）/Windows 10 （14393） |
|    历史记录    |                                         与访问过的页面的浏览器记录进行交互。                                         |                 "考虑"                  |
|     国际化      |                                         跨扩展实现国际化。                                          | 支持-Microsoft Edge （38）/Windows 10 （14393） |
|   身份    |                                       用于获取 OAuth2 授权码或访问令牌。                                       |                 "考虑"                  |
|     着      |                                       用于检测计算机的空闲状态何时更改。                                        | 支持-Microsoft Edge （38）/Windows 10 （14393） |
|  层   |                                              获取有关已安装的加载项的信息。                                                |                 "考虑"                  |
| 通知 |                      允许创建使用模板显示在用户系统托盘中的通知。                      | 受支持-Microsoft Edge （42）/Windows 10 （17134） |
|  pageAction   |                                      启用 "扩展" 以在地址栏中添加按钮。                                       | 支持-Microsoft Edge （38）/Windows 10 （14393） |
|  授权  |                   允许用户选择要授予其扩展访问权限的可选权限。                   |                 "考虑"                  |
|    环境    | 检索背景页，返回有关清单的详细信息，并侦听并响应扩展生命周期中的事件。 | 支持-Microsoft Edge （38）/Windows 10 （14393） |
|    存储    |                                      由扩展使用，用于读取/写入数据和同步数据。                                       | 支持-Microsoft Edge （38）/Windows 10 （14393） |
|     选项卡      |                通过在浏览器中创建、修改和重新排列选项卡，与 Microsoft Edge 的选项卡系统交互。                | 支持-Microsoft Edge （38）/Windows 10 （14393） |
| webNavigation |                           用于接收有关正在进行的导航请求状态的通知。                            | 支持-Microsoft Edge （38）/Windows 10 （14393） |
|  webRequest   |        支持使用 webRequest API 观察和分析流量以及截获、阻止或修改正在进行的请求。        | 支持-Microsoft Edge （38）/Windows 10 （14393） |
|    windows    |                              通过创建、修改和重新排列窗口来与浏览器交互。                              | 支持-Microsoft Edge （38）/Windows 10 （14393） |

