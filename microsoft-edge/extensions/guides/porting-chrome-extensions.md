---
ms.assetid: 1319a070-c6e3-4592-9f4b-40ce1575851f
description: 了解如何使用 Microsoft Edge 扩展工具包将 Chrome 扩展移植到 Microsoft Edge。
title: 移植 Chrome 扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.custom: seodec18
ms.openlocfilehash: 38bf1324c2e7e6f7754912177ce0e53d6c15a276
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563237"
---
# 将扩展程序从 Chrome 移植到 Microsoft Edge  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

通过 [Microsoft Edge 扩展工具包](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)的帮助，将 Chrome 中的扩展移植到 microsoft edge 变得非常简单。 此开发工具通过桥接 Api 并在文件中呈现任何错误，将解压缩的 Chrome 扩展转换为解包的 Microsoft Edge 扩展 `manifest.json` 。


### API 桥
为了允许将 Chrome Api 无缝移植到受支持的 Microsoft Edge Api，请将两个脚本添加到扩展的文件夹。 这些脚本桥接 Api (polyfiling （需要) ），这意味着无需担心在后台脚本或内容脚本中更改任何 Chrome 特定的代码。

转换后，你将看到它们包含在具有以下键的扩展的清单文件中 `"-ms-preload"` ：

```json
"-ms-preload": {
  "backgroundScript": "backgroundScriptsAPIBridge.js",
  "contentScript": "contentScriptsAPIBridge.js"
}
```

## 使用 Microsoft Edge 扩展工具包

以下说明详细介绍了如何在 Windows 10 周年更新版本中将 Chrome 扩展转换为在 Microsoft Edge 上运行：

1. 安装 [Microsoft Edge 扩展工具包](https://www.microsoft.com/store/p/microsoft-edge-extension-toolkit/9nblggh4txvb)。
2. 制作 Chrome 扩展文件夹的副本，以便安全保留。 转换过程将覆盖代码。 
3. 运行 Microsoft Edge 扩展工具包并加载您的扩展副本。  
 !["加载扩展" 按钮](./../media/save-folder.png)
4. 更正工具的文本编辑器中报告的所有错误。 选择 "重新验证" 以在进行更正后检查错误。  
 ![扩展-工具包查找错误](./../media/extension-toolkit.png)
5. 选择 "保存文件"。

现在，你可以退出工具包并在 Microsoft Edge 中加载你的扩展！ 

你可以在 [EdgeHTML 问题跟踪](http://issues.microsoftedge.com)器中搜索已知的平台问题。 如果您认为发现了一些新功能，请 [打开一个问题](https://developer.microsoft.com/microsoft-edge/platform/issues/new/)！
