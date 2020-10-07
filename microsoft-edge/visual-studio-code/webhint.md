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
# <span data-ttu-id="f27f2-104">Webhint Vs Code Extension</span><span class="sxs-lookup"><span data-stu-id="f27f2-104">Webhint Vs Code Extension</span></span>  

<span data-ttu-id="f27f2-105">Use [webhint][WebhintMain], a customizable linting tool, to improve the accessibility, performance, cross-browser compatibility, PWA compatibility, and security of your site.</span><span class="sxs-lookup"><span data-stu-id="f27f2-105">Use [webhint][WebhintMain], a customizable linting tool, to improve the accessibility, performance, cross-browser compatibility, PWA compatibility, and security of your site.</span></span>  <span data-ttu-id="f27f2-106">It checks your code for best practices and common errors.</span><span class="sxs-lookup"><span data-stu-id="f27f2-106">It checks your code for best practices and common errors.</span></span> <span data-ttu-id="f27f2-107">This open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation][OpenjsFoundation].</span><span class="sxs-lookup"><span data-stu-id="f27f2-107">This open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation][OpenjsFoundation].</span></span>  <span data-ttu-id="f27f2-108">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span><span class="sxs-lookup"><span data-stu-id="f27f2-108">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span></span>  

:::image type="complex" source="./media/webhint-extension.png" alt-text="Screenshot of webhint VS Code extension":::
   <span data-ttu-id="f27f2-110">Screenshot of webhint VS Code extension</span><span class="sxs-lookup"><span data-stu-id="f27f2-110">Screenshot of webhint VS Code extension</span></span>  
:::image-end:::

<!--![Screenshot of webhint VS Code extension][ImageWebhintExtension]  -->  

<span data-ttu-id="f27f2-111">Identify and fix problems in your HTML, CSS, JavaScript, TypeScript, and more by adding the [webhint extension for VS Code][VisualstudioMarketplaceWebhint].</span><span class="sxs-lookup"><span data-stu-id="f27f2-111">Identify and fix problems in your HTML, CSS, JavaScript, TypeScript, and more by adding the [webhint extension for VS Code][VisualstudioMarketplaceWebhint].</span></span>  <span data-ttu-id="f27f2-112">Hints appear as inline underlines and are summarized in the **Problems** pane.</span><span class="sxs-lookup"><span data-stu-id="f27f2-112">Hints appear as inline underlines and are summarized in the **Problems** pane.</span></span>  

## <span data-ttu-id="f27f2-113">Configuration</span><span class="sxs-lookup"><span data-stu-id="f27f2-113">Configuration</span></span>  

<span data-ttu-id="f27f2-114">This extension uses a [default configuration][GithubWebhintioIndexjson] json file that activates hints and parsers for HTML, CSS, templating systems \(JSX/TSX, Angular, and so on\), JavaScript/TypeScript, and more.</span><span class="sxs-lookup"><span data-stu-id="f27f2-114">This extension uses a [default configuration][GithubWebhintioIndexjson] json file that activates hints and parsers for HTML, CSS, templating systems \(JSX/TSX, Angular, and so on\), JavaScript/TypeScript, and more.</span></span>  

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

<span data-ttu-id="f27f2-115">If you want more control over the hints and parsers that get activated, create a local `.hintrc` file to configure webhint.</span><span class="sxs-lookup"><span data-stu-id="f27f2-115">If you want more control over the hints and parsers that get activated, create a local `.hintrc` file to configure webhint.</span></span>  <span data-ttu-id="f27f2-116">For help with output from specific hints, see [webhint user guide][WebhintDocsUserguideConfiguringSummary].</span><span class="sxs-lookup"><span data-stu-id="f27f2-116">For help with output from specific hints, see [webhint user guide][WebhintDocsUserguideConfiguringSummary].</span></span>  

## <span data-ttu-id="f27f2-117">Getting in touch with the webhint team</span><span class="sxs-lookup"><span data-stu-id="f27f2-117">Getting in touch with the webhint team</span></span>  

<span data-ttu-id="f27f2-118">Send your feedback by [filing an issue][GithubWebhintioIssuesNew] in [webhint GitHub repo][GithubWebhintio].</span><span class="sxs-lookup"><span data-stu-id="f27f2-118">Send your feedback by [filing an issue][GithubWebhintioIssuesNew] in [webhint GitHub repo][GithubWebhintio].</span></span>  

<span data-ttu-id="f27f2-119">To contribute to the extension, see [webhint VS Code extension contribution guide][GithubWebhintioExtensionVscodeContributing].</span><span class="sxs-lookup"><span data-stu-id="f27f2-119">To contribute to the extension, see [webhint VS Code extension contribution guide][GithubWebhintioExtensionVscodeContributing].</span></span>  

## <span data-ttu-id="f27f2-120">See also</span><span class="sxs-lookup"><span data-stu-id="f27f2-120">See also</span></span>  

*   [<span data-ttu-id="f27f2-121">Accessibility</span><span class="sxs-lookup"><span data-stu-id="f27f2-121">Accessibility</span></span>][AccessibilityIndex]  
*   [<span data-ttu-id="f27f2-122">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f27f2-122">Visual Studio Code</span></span>][VisualstudiocodeIndex]  

<!-- image links -->  

<!--[ImageWebhintExtension]: ./media/webhint-extension.png "Screenshot of webhint VS Code extension"  -->  

<!--links -->  

[AccessibilityIndex]: /microsoft-edge/accessibility "Accessibility | Microsoft Docs"  

[VisualstudiocodeIndex]: /microsoft-edge/visual-studio-code/index "Visual Studio Code | Microsoft Docs"  

[GithubWebhintio]: https://github.com/webhintio/hint "webhint | GitHub"  
[GithubWebhintioExtensionVscodeContributing]: https://github.com/webhintio/hint/blob/master/packages/extension-vscode/CONTRIBUTING.md "Contributing - webhint | GitHub"  
[GithubWebhintioIndexjson]: https://github.com/webhintio/hint/blob/master/packages/configuration-development/index.json "index.json - webhintio/hint | GitHub"
[GithubWebhintioIssuesNew]: https://github.com/webhintio/hint/issues/new "New Issues - webhintio/hint | GitHub"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint | Visual Studio Marketplace"  

[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  

[WebhintDocsUserguideConfiguringSummary]: https://webhint.io/docs/user-guide/configuring-webhint/summary "Configuring Webhint | webhint Documentation"  
[WebhintMain]:  https://webhint.io "webhint"  
