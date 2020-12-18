---
ms.assetid: 8b7f362f-da09-43db-8a42-cfa128c1808c
description: 获取加载未打包的扩展时可能具有的常见问题的解答。
title: 扩展 - 疑难解答
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 74743923000766473a96b56a97d302b6ab79a9e3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232238"
---
# 疑难解答  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

如果你尝试加载未打包的扩展并遇到问题，下面的信息可能会有所帮助：

## 1. 看到错误"无法加载此扩展"

这通常意味着 Microsoft Edge 无法访问您尝试加载的扩展文件夹。

以下是可能遇到的错误的摘要：

错误消息 | 详细信息
:--------- | :------------
清单分析错误：清单文件缺失或格式不正确。 | 指定 `"manifest.json"` 位置找不到文件，或者文件出错。 若要解决此问题，请确保指定的文件夹在顶级包含清单，并仔细检查逗号、引号和方括号。
清单分析错误： `"content_scripts"` 必须定义数组。 | 字段 `"content_scripts"` 应为数组。 若要解决此问题，请仔细检查语法。 例如： `"content_scripts": [{"matches": [...],"css": [...],"js": [...] }]`
清单分析错误： `"content_scripts"` 必须定义 `"matches"` 属性值。 | 属性 `"matches"` 是必需的。 若要解决此问题，请用字符串数组指定属性值。 例如： `"content_scripts": [ {... "matches": ["http://www.bing.com"] ...} ]`
清单分析错误： `"content_scripts"` 必须至少引用一个 .css 或 .js 文件。 | 至少一个属性 `"css"` 或 `"js"` 必需属性。 若要解决此问题，请用字符串数组指定属性值。 例如： `"content_scripts": [ { ... "js": ["myScript1.js", "myScript2.js"] ...} ]`
清单分析错误： `"<field>"` 必须为 <property> ""属性定义值。 | 字段 `<property>` 的属性 `<field>` 是必需的。 若要解决此问题，请为 . `<property>`
清单分析错误： `"content_scripts"` 引用"run_at"字段的值无效。 | 该属性 `"run_at"` 指定未知值。 若要解决此问题，请指定一个 `"document_start"` 或 `"document_end"` `"document_idle"` 。 例如： `"content_scripts": [ {... "run_at": "document_start" ... } ]`
清单分析错误：缺少 `"<field>"` 字段。 | 该字段 `<field>` 是必需的。 若要解决此问题，请用有效值定义字段。
清单分析错误：在 `"<field1>"` `"<field2>"` . | 该字段 <field1> 的字段 <field2> 指定未知值。 若要解决此问题，请为 . <field1>
清单分析错误："" <field> 字段的值无效。 | 该字段 <field> 指定未知值。 若要解决此问题，请指定一个有效的值。
清单分析错误：当前版本的 Microsoft Edge 不支持扩展。 | 该属性 `"minimum_edge_version"` 指定比你拥有的版本更新的 Microsoft Edge 版本。 可以通过打开"更多应用"菜单 ("..."，) "设置" ("关于此应用"部分) 。 若要解决此问题，请更新浏览器到较新版本或更改清单中的值。 例如： `"minimum_edge_version": "x.xxxx.xxxx.x"`
清单分析错误： `"background"` 必须为"page"或"scripts"属性定义值。 | 字段"background"需要属性"page"或"scripts"。 若要解决此问题，请指定"page"的字符串或"scripts"的字符串数组。 例如： `"background": { ... "scripts": ["background.js"] ... }`
清单分析错误： `"background"` 必须定义 `"persistent"` 属性值。 | 属性 `"persistent"` 是必需的。 若要解决此问题，请指定 true 或 false 值。 例如： `"background": {... "persistent": true ...}`
清单分析错误：只能定义 `"browser_action"` 一个 `"page_action"` ，也可以定义。 | 扩展不能同时定义页面操作和浏览器操作。 若要解决此问题，请删除其中一个定义。
未指定错误： `<error>` | 通用 catch-all 错误消息。 `<error>` 将替换为指定的错误。


## 2. 我看不到"加载扩展"按钮
在通过 Microsoft Store 提供扩展之前，此按钮 *默认情况下* 应该可见。 如果打开"更多" (...) 菜单，请选择"扩展"菜单项，但看不到该按钮，请按照以下步骤操作：

1. 在地址栏中键入 **"about：flags"，** 然后按 **"Enter"** 键。
2. 在标题 **"开发人员设置"下** ，确保选中了" **启用扩展开发人员功能"旁边的** 复选框。

   ![关于标志](./media/aboutflags.PNG)  

3. 关闭并重新打开 Microsoft Edge 并检查"加载**** 扩展"按钮现在是否可见。
