---
description: 如何在 Web 代码中使用 webhint Visual Studio代码
title: webhint Visual Studio代码扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， vs code， visual studio code， webhint
ms.openlocfilehash: 3dfd900bf818d02dbc8123c00e7928e56d9b6ade
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399272"
---
# <a name="webhint-vs-code-extension"></a>Webhint 与代码扩展  

使用 [Webhint（][WebhintMain]一个可自定义的 Lint 工具）可改进网站的辅助功能、性能、跨浏览器兼容性、PWA 兼容性和安全性。  它会检查代码的最佳实践和常见错误。 此开源项目最初由 Microsoft Edge 团队开发，现在是 [OpenJS Foundation 的一部分][OpenjsFoundation]。  Microsoft Edge 团队将继续与社区中的 Web 开发人员一起为 webhint 做贡献。  

:::image type="complex" source="./media/webhint-extension.png" alt-text="Webhint Visual Studio代码扩展的屏幕截图":::
   Webhint Visual Studio代码扩展的屏幕截图  
:::image-end:::

<!--![Screenshot of webhint Visual Studio Code extension][ImageWebhintExtension]  -->  

通过为 HTML、CSS、JavaScript、TypeScript 等添加 [Webhint][VisualstudioMarketplaceWebhint]扩展插件来识别并修复Visual Studio代码。  提示显示为内联下划线，并汇总在"问题 **"** 窗格中。  

## <a name="configuration"></a>配置  

此扩展使用默认配置 [json][GithubWebhintioIndexjson] 文件，用于激活 HTML、CSS、模板系统 \(JSX/TSX、Angular 等的提示和分析程序\) 、JavaScript/TypeScript 等。  

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

如果你希望对激活的提示和分析程序进行更多控制，请创建一个本地 `.hintrc` 文件来配置 Webhint。  有关特定提示输出的帮助，请导航到 [Webhint 用户指南][WebhintDocsUserguideConfiguringSummary]。  

## <a name="getting-in-touch-with-the-webhint-team"></a>与 Webhint 团队联系  

通过提交 [Webhint][GithubWebhintioIssuesNew] GitHub 存储库中的问题 [发送反馈][GithubWebhintio]。  

若要参与扩展，请导航到 [webhint Visual Studio代码扩展参与指南][GithubWebhintioExtensionVscodeContributing]。  

## <a name="see-also"></a>另请参阅  

*   [辅助功能][AccessibilityIndex]  
*   [Visual Studio Code][VisualstudiocodeIndex]  

<!-- image links -->  

<!--[ImageWebhintExtension]: ./media/webhint-extension.png "Screenshot of webhint Visual Studio Code extension"  -->  

<!--links -->  

[AccessibilityIndex]: /microsoft-edge/accessibility "辅助功能|Microsoft Docs"  

[VisualstudiocodeIndex]: /microsoft-edge/visual-studio-code/index "Visual Studio代码|Microsoft Docs"  

[GithubWebhintio]: https://github.com/webhintio/hint "webhint |GitHub"  
[GithubWebhintioExtensionVscodeContributing]: https://github.com/webhintio/hint/blob/master/packages/extension-vscode/CONTRIBUTING.md "参与 - webhint |GitHub"  
[GithubWebhintioIndexjson]: https://github.com/webhintio/hint/blob/master/packages/configuration-development/index.json "index.js- webhintio/hint |GitHub"
[GithubWebhintioIssuesNew]: https://github.com/webhintio/hint/issues/new "新问题 - webhintio/hint |GitHub"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual Studio Marketplace"  

[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  

[WebhintDocsUserguideConfiguringSummary]: https://webhint.io/docs/user-guide/configuring-webhint/summary "配置 Webhint |webhint 文档"  
[WebhintMain]:  https://webhint.io "webhint"  
