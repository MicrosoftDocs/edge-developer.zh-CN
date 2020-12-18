---
ms.assetid: 1319a070-c6e3-4592-9f4b-40ce1575851f
description: 了解如何使用 Microsoft Edge 扩展服务将 Chrome 扩展移植到 Microsoft Edge Toolkit。
title: 移植 Chrome 扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f226d79dbc9efdc43eb68bfb353fa12748198371
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232588"
---
# 将扩展从 Chrome 移植到 Microsoft Edge  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

借助 Microsoft Edge 扩展服务，可轻松将扩展从 Chrome 移植到 [Microsoft Edge](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)Toolkit。 此开发人员工具通过桥接 API 和显示文件的任何错误，将未打包的 Chrome 扩展转换为未打包的 Microsoft Edge `manifest.json` 扩展。


### API 桥
为了允许将 Chrome API 无缝移植到支持的 Microsoft Edge API，将两个脚本添加到扩展的文件夹中。 这些脚本在必要时 (将 API 桥接到) ，这意味着你无需担心更改后台脚本或内容脚本中任何 Chrome 特定代码。

转换后，你将看到它们包含在扩展的清单文件中，并包含 `"-ms-preload"` 密钥：

```json
"-ms-preload": {
  "backgroundScript": "backgroundScriptsAPIBridge.js",
  "contentScript": "contentScriptsAPIBridge.js"
}
```

## 使用 Microsoft Edge 扩展Toolkit

以下说明详细介绍了如何在 Windows 10 周年更新版本中将 Chrome 扩展转换为在 Microsoft Edge 上运行：

1. 安装[Microsoft Edge 扩展Toolkit。](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)
2. 创建 Chrome 扩展文件夹的副本以安全保留。 转换过程将覆盖代码。 
3. 运行 Microsoft Edge 扩展Toolkit并加载扩展副本。  
 ![加载扩展按钮](./../media/save-folder.png)
4. 更正在工具的文本编辑器中报告的所有错误。 选择"重新验证"以在更正错误后检查错误。  
 ![扩展工具包查找错误](./../media/extension-toolkit.png)
5. 选择"保存文件"。

现在可以退出工具包，在 Microsoft Edge 中加载扩展！ 

您可以使用 EdgeHTML 问题跟踪器搜索已知 [平台问题](http://issues.microsoftedge.com)。 如果认为你已找到新内容， [请打开一个问题](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)！
