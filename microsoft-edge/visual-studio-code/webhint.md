---
description: How to use webhint in Visual Studio Code
title: webhint VS Code extension
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, vs code, visual studio code, webhint
ms.openlocfilehash: ec218fab8cbfb8181a0416c8e0eadc0e00412529
ms.sourcegitcommit: c1b5fdd48d39d874a76c9b8f68309eb1b507fd0b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2020
ms.locfileid: "10695857"
---
# Webhint Vs Code Extension  

Use [webhint][WebhintMain], a customizable linting tool, to improve the accessibility, performance, cross-browser compatibility, PWA compatibility, and security of your site.  It checks your code for best practices and common errors. This open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation][OpenjsFoundation].  The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.  

:::image type="complex" source="./media/webhint-extension.png" alt-text="Screenshot of webhint VS Code extension&quot;:::
   Screenshot of webhint VS Code extension  
:::image-end:::

<!--![Screenshot of webhint VS Code extension][ImageWebhintExtension]  -->  

Identify and fix problems in your HTML, CSS, JavaScript, TypeScript, and more by adding the [webhint extension for VS Code][VisualstudioMarketplaceWebhint].  Hints appear as inline underlines and are summarized in the **Problems** pane.  

## Configuration  

This extension uses a [default configuration][GithubWebhintioIndexjson] json file that activates hints and parsers for HTML, CSS, templating systems \(JSX/TSX, Angular, and so on\), JavaScript/TypeScript, and more.  

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

If you want more control over the hints and parsers that get activated, create a local `.hintrc` file to configure webhint.  For help with output from specific hints, see [webhint user guide][WebhintDocsUserguideConfiguringSummary].  

## Getting in touch with the webhint team  

Send your feedback by [filing an issue][GithubWebhintioIssuesNew] in [webhint GitHub repo][GithubWebhintio].  

To contribute to the extension, see [webhint VS Code extension contribution guide][GithubWebhintioExtensionVscodeContributing].  

## See also  

*   [Accessibility][AccessibilityIndex]  
*   [Visual Studio Code][VisualstudiocodeIndex]  

<!-- image links -->  

<!--[ImageWebhintExtension]: ./media/webhint-extension.png &quot;Screenshot of webhint VS Code extension&quot;  -->  

<!--links -->  

[AccessibilityIndex]: /microsoft-edge/accessibility &quot;Accessibility | Microsoft Docs&quot;  

[VisualstudiocodeIndex]: /microsoft-edge/visual-studio-code/index &quot;Visual Studio Code | Microsoft Docs&quot;  

[GithubWebhintio]: https://github.com/webhintio/hint &quot;webhint | GitHub&quot;  
[GithubWebhintioExtensionVscodeContributing]: https://github.com/webhintio/hint/blob/master/packages/extension-vscode/CONTRIBUTING.md &quot;Contributing - webhint | GitHub&quot;  
[GithubWebhintioIndexjson]: https://github.com/webhintio/hint/blob/master/packages/configuration-development/index.json &quot;index.json - webhintio/hint | GitHub&quot;
[GithubWebhintioIssuesNew]: https://github.com/webhintio/hint/issues/new &quot;New Issues - webhintio/hint | GitHub"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint | Visual Studio Marketplace"  

[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  

[WebhintDocsUserguideConfiguringSummary]: https://webhint.io/docs/user-guide/configuring-webhint/summary "Configuring Webhint | webhint Documentation"  
[WebhintMain]:  https://webhint.io "webhint"  
