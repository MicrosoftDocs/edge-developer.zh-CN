---
ms.assetid: 8b7f362f-da09-43db-8a42-cfa128c1808c
description: 获取加载解压缩扩展插件时可能会遇到的常见问题的答案。
title: 扩展-疑难解答
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 78013876ba5c2c6c111289f46c81a9fde3ecc964
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563220"
---
# 疑难解答  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

如果你尝试加载解包扩展且遇到问题，以下信息可能会有所帮助：

## 1. 我看到错误 "无法加载此扩展"

这通常意味着 Microsoft Edge 无法访问尝试加载的扩展文件夹。

下面是可能遇到的可能错误的摘要：

错误消息 | 详细信息
:--------- | :------------
清单分析错误：清单文件缺失或格式不正确。 | `"manifest.json"`在指定位置找不到文件，或者文件有错。 若要解决此问题，请确保指定的文件夹在顶级级别包含清单，并仔细检查逗号、引号和括号。
清单分析错误： `"content_scripts"` 必须定义数组。 | 字段 `"content_scripts"` 应为数组。 若要解决此问题，请仔细检查语法。 例如： `"content_scripts": [{"matches": [...],"css": [...],"js": [...] }]`
清单分析错误： `"content_scripts"` 必须定义属性的值 `"matches"` 。 | 属性 `"matches"` 是必需的。 若要解决此问题，请使用字符串数组指定该属性的值。 例如： `"content_scripts": [ {... "matches": ["http://www.bing.com"] ...} ]`
清单分析错误： `"content_scripts"` 必须至少引用一个 .css 或 .js 文件。 | 至少有一个属性 `"css"` 或 `"js"` 需要。 若要解决此问题，请使用字符串数组指定该属性的值。 例如： `"content_scripts": [ { ... "js": ["myScript1.js", "myScript2.js"] ...} ]`
清单分析错误： `"<field>"` 必须定义 " <property> " 属性的值。 | 字段的属性 `<property>` `<field>` 是必需的。 若要解决此问题，请为指定有效的值 `<property>` 。
清单分析错误： `"content_scripts"` 引用的 "run_at" 字段的值无效。 | 该属性 `"run_at"` 指定未知值。 若要解决此问题，请指定其中一个 `"document_start"` `"document_end"` 或 `"document_idle"` 。 例如： `"content_scripts": [ {... "run_at": "document_start" ... } ]`
清单分析错误：缺少 `"<field>"` 字段。 | 此字段 `<field>` 是必需的。 若要解决此问题，请使用有效的值定义字段。
清单分析错误： `"<field1>"` 在中找到无效字段 `"<field2>"` 。 | 字段的字段 <field1> <field2> 指定未知值。 若要解决此问题，请为指定有效的值 <field1> 。
清单分析错误： "" 字段的值无效 <field> 。 | 该字段 <field> 指定未知值。 若要解决此问题，请指定一个有效值。
清单分析错误：当前版本的 Microsoft Edge 不支持扩展名。 | 该属性 `"minimum_edge_version"` 指定的 Microsoft Edge 版本比你拥有的版本更新。 可以通过打开 "..." (更多) 菜单，然后选择 "设置" (底部 "关于此应用" ) 来查找当前版本。 若要解决此问题，请将你的浏览器更新到较新版本或更改清单中的值。 例如： `"minimum_edge_version": "x.xxxx.xxxx.x"`
清单分析错误： `"background"` 必须定义 "page" 或 "scripts" 属性的值。 | 字段 "background" 需要属性 "page" 或 "scripts"。 若要解决此问题，请为 "页面" 或 "脚本" 的字符串数组指定一个字符串。 例如： `"background": { ... "scripts": ["background.js"] ... }`
清单分析错误： `"background"` 必须定义属性的值 `"persistent"` 。 | 属性 `"persistent"` 是必需的。 若要解决此问题，请指定 true 或 false 值。 例如： `"background": {... "persistent": true ...}`
清单分析错误：只有一个 `"browser_action"` 或 `"page_action"` 可以定义。 | 扩展名不能同时定义页面操作和浏览器操作。 若要解决此问题，请删除其中一个定义。
未指定的错误： `<error>` | 常规捕获-所有错误消息。 `<error>` 将替换为指定的错误。


## 2. 我看不到 "加载扩展" 按钮
通过 Microsoft Store 可以使用扩展，默认情况下，此按钮 *应* 可见。 如果打开 "更多" ( ... ") 菜单中，选择" 扩展 "菜单项，但看不到该按钮，请按照下列步骤操作：

1. 在地址栏中键入 **"关于：标志"** ，然后按 **"Enter"** 键。
2. 在标题 **"开发人员设置"** 下，确保选中 **"启用扩展开发人员功能** " 旁边的复选框。

   ![关于标志](./media/aboutflags.PNG)  

3. 关闭并重新打开 Microsoft Edge，查看 **"加载扩展"** 按钮是否可见。
