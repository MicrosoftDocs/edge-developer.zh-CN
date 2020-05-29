---
description: 如何在 Visual Studio 代码中使用 webhint
title: webhint 与代码扩展
author: hxlnt
ms.author: raweil
ms.date: 03/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、vs 代码、visual studio 代码 webhint
ms.openlocfilehash: d3102bf4d8d4a8bba9225d8d3f68432197f775ac
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564522"
---
# webhint 与代码扩展

使用[webhint](https://webhint.io)（一种可自定义的 linting 工具）来改进你的网站的辅助功能、性能、跨浏览器兼容性、PWA 兼容性和安全性。 它会检查代码的最佳做法和常见错误。 此开放源代码项目（最初由 Microsoft Edge 团队开发）现在是[OpenJS 基础](https://openjsf.org/)的一部分。 Microsoft Edge 团队继续参与社区中的 webhint 和 web 开发人员。

![Webhint 与代码扩展的屏幕截图](./media/webhint-extension.png)

通过添加[VS 代码的 webhint 扩展名](https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint)，识别并修复 HTML、CSS、JavaScript、TypeScript 等中的问题。 提示显示为内联下划线，并在 "问题" 窗格中进行汇总。

## 配置

此扩展使用[默认配置](https://github.com/webhintio/hint/blob/master/packages/configuration-development/index.json)json 文件，该文件激活 HTML、CSS、模板化系统（JSX/TSX、角度等）、JavaScript/TypeScript 等的提示和分析程序。

```json
{
    "connector": "local",
    "extends": [
        "accessibility",
        "progressive-web-apps"
    ],
    "formatters": [
        "html",
        "summary"
    ],
    "hints": [
        "apple-touch-icons",
        "button-type",
        "compat-api/css",
        "compat-api/html",
        "create-element-svg",
        "css-prefix-order",
        "disown-opener",
        "highest-available-document-mode",
        "manifest-exists",
        "meta-charset-utf-8",
        "meta-viewport",
        "no-bom",
        "no-protocol-relative-urls",
        "scoped-svg-styles",
        "sri",
        "typescript-config/consistent-casing",
        "typescript-config/import-helpers",
        "typescript-config/is-valid",
        "typescript-config/no-comments",
        "typescript-config/strict",
        "typescript-config/target"
    ],
    "hintsTimeout": 10000,
    "parsers": [
        "babel-config",
        "css",
        "html",
        "javascript",
        "jsx",
        "less",
        "sass",
        "typescript",
        "typescript-config",
        "webpack-config"
    ]
}
```

如果您希望更好地控制激活的提示和分析程序，请创建一个本地 `.hintrc` 文件来配置 webhint。 有关特定提示的输出的帮助，请参阅[webhint 用户指南](https://webhint.io/docs/user-guide/configuring-webhint/summary/)。

## 反馈

通过在[Webhint github](https://github.com/webhintio/hint)存储库上[归档问题](https://github.com/webhintio/hint/issues/new)来向我们发送反馈。 

若要参与扩展，请阅读[WEBHINT 和代码扩展发布指南](https://github.com/webhintio/hint/blob/master/packages/extension-vscode/CONTRIBUTING.md)。

## 另请参阅
  - [辅助功能](/microsoft-edge/accessibility)
  - [Visual Studio Code](/microsoft-edge/visual-studio-code/)
