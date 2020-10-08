---
description: 如何在 Visual Studio 代码中使用 webhint
title: webhint 与代码扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、vs 代码、visual studio 代码 webhint
ms.openlocfilehash: ec218fab8cbfb8181a0416c8e0eadc0e00412529
ms.sourcegitcommit: c1b5fdd48d39d874a76c9b8f68309eb1b507fd0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "10695857"
---
# Webhint 与代码扩展  

使用 [webhint][WebhintMain]（一种可自定义的 linting 工具）来改进你的网站的辅助功能、性能、跨浏览器兼容性、PWA 兼容性和安全性。  它会检查代码的最佳做法和常见错误。 此开放源代码项目（最初由 Microsoft Edge 团队开发）现在是 [OpenJS 基础][OpenjsFoundation]的一部分。  Microsoft Edge 团队继续参与社区中的 webhint 和 web 开发人员。  

:::image type="complex" source="./media/webhint-extension.png" alt-text="Webhint 与代码扩展的屏幕截图&quot;:::
   Webhint 与代码扩展的屏幕截图  
:::image-end:::

<!--![Screenshot of webhint VS Code extension][ImageWebhintExtension]  -->  

通过添加 [VS 代码的 webhint 扩展名][VisualstudioMarketplaceWebhint]，识别并修复 HTML、CSS、JavaScript、TypeScript 等中的问题。  提示显示为内联下划线，并在 &quot; **问题** &quot; 窗格中进行汇总。  

## 配置  

此扩展使用 [默认配置][GithubWebhintioIndexjson] json 文件，该文件激活 HTML、CSS、模板化系统 \ (JSX/TSX、角度等 \ ) 、JavaScript/TypeScript 等的提示和分析程序。  

```json
{
    &quot;connector&quot;: &quot;local&quot;,
    &quot;extends&quot;: [
        &quot;accessibility&quot;,
        &quot;progressive-web-apps&quot;
    ],
    &quot;formatters&quot;: [
        &quot;html&quot;,
        &quot;summary&quot;
    ],
    &quot;hints&quot;: [
        &quot;apple-touch-icons&quot;,
        &quot;button-type&quot;,
        &quot;compat-api/css&quot;,
        &quot;compat-api/html&quot;,
        &quot;create-element-svg&quot;,
        &quot;css-prefix-order&quot;,
        &quot;disown-opener&quot;,
        &quot;highest-available-document-mode&quot;,
        &quot;manifest-exists&quot;,
        &quot;meta-charset-utf-8&quot;,
        &quot;meta-viewport&quot;,
        &quot;no-bom&quot;,
        &quot;no-protocol-relative-urls&quot;,
        &quot;scoped-svg-styles&quot;,
        &quot;sri&quot;,
        &quot;typescript-config/consistent-casing&quot;,
        &quot;typescript-config/import-helpers&quot;,
        &quot;typescript-config/is-valid&quot;,
        &quot;typescript-config/no-comments&quot;,
        &quot;typescript-config/strict&quot;,
        &quot;typescript-config/target&quot;
    ],
    &quot;hintsTimeout&quot;: 10000,
    &quot;parsers&quot;: [
        &quot;babel-config&quot;,
        &quot;css&quot;,
        &quot;html&quot;,
        &quot;javascript&quot;,
        &quot;jsx&quot;,
        &quot;less&quot;,
        &quot;sass&quot;,
        &quot;typescript&quot;,
        &quot;typescript-config&quot;,
        &quot;webpack-config&quot;
    ]
}
```  

如果您希望更好地控制激活的提示和分析程序，请创建一个本地 `.hintrc` 文件来配置 webhint。  有关特定提示的输出的帮助，请参阅 [webhint 用户指南][WebhintDocsUserguideConfiguringSummary]。  

## 与 webhint 团队取得联系  

通过在[Webhint github][GithubWebhintio]存储库中[归档问题][GithubWebhintioIssuesNew]来发送反馈。  

若要参与扩展，请参阅 [WEBHINT 和代码扩展发布指南][GithubWebhintioExtensionVscodeContributing]。  

## 另请参阅  

*   [辅助功能][AccessibilityIndex]  
*   [Visual Studio Code][VisualstudiocodeIndex]  

<!-- image links -->  

<!--[ImageWebhintExtension]: ./media/webhint-extension.png &quot;Screenshot of webhint VS Code extension&quot;  -->  

<!--links -->  

[AccessibilityIndex]: /microsoft-edge/accessibility &quot;辅助功能 |Microsoft 文档&quot;  

[VisualstudiocodeIndex]: /microsoft-edge/visual-studio-code/index &quot;Visual Studio 代码 |Microsoft 文档&quot;  

[GithubWebhintio]: https://github.com/webhintio/hint &quot;webhint |GitHub&quot;  
[GithubWebhintioExtensionVscodeContributing]: https://github.com/webhintio/hint/blob/master/packages/extension-vscode/CONTRIBUTING.md &quot;Webhint |GitHub&quot;  
[GithubWebhintioIndexjson]: https://github.com/webhintio/hint/blob/master/packages/configuration-development/index.json &quot;index.jswebhintio/提示 |GitHub&quot;
[GithubWebhintioIssuesNew]: https://github.com/webhintio/hint/issues/new &quot;新问题-webhintio/提示 |GitHub"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual Studio Marketplace"  

[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  

[WebhintDocsUserguideConfiguringSummary]: https://webhint.io/docs/user-guide/configuring-webhint/summary "配置 Webhint |webhint 文档"  
[WebhintMain]:  https://webhint.io "webhint"  
