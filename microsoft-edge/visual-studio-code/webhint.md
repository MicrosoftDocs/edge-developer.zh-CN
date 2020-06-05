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
# <span data-ttu-id="42f9e-104">Webhint 与代码扩展</span><span class="sxs-lookup"><span data-stu-id="42f9e-104">Webhint Vs Code Extension</span></span>  

<span data-ttu-id="42f9e-105">使用[webhint][WebhintMain]（一种可自定义的 linting 工具）来改进你的网站的辅助功能、性能、跨浏览器兼容性、PWA 兼容性和安全性。</span><span class="sxs-lookup"><span data-stu-id="42f9e-105">Use [webhint][WebhintMain], a customizable linting tool, to improve the accessibility, performance, cross-browser compatibility, PWA compatibility, and security of your site.</span></span>  <span data-ttu-id="42f9e-106">它会检查代码的最佳做法和常见错误。</span><span class="sxs-lookup"><span data-stu-id="42f9e-106">It checks your code for best practices and common errors.</span></span> <span data-ttu-id="42f9e-107">此开放源代码项目（最初由 Microsoft Edge 团队开发）现在是[OpenJS 基础][OpenjsFoundation]的一部分。</span><span class="sxs-lookup"><span data-stu-id="42f9e-107">This open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation][OpenjsFoundation].</span></span>  <span data-ttu-id="42f9e-108">Microsoft Edge 团队继续参与社区中的 webhint 和 web 开发人员。</span><span class="sxs-lookup"><span data-stu-id="42f9e-108">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span></span>  

:::image type="complex" source="./media/webhint-extension.png" alt-text="Webhint 与代码扩展的屏幕截图":::
   <span data-ttu-id="42f9e-110">Webhint 与代码扩展的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="42f9e-110">Screenshot of webhint VS Code extension</span></span>  
:::image-end:::

<!--![Screenshot of webhint VS Code extension][ImageWebhintExtension]  -->  

<span data-ttu-id="42f9e-111">通过添加[VS 代码的 webhint 扩展名][VisualstudioMarketplaceWebhint]，识别并修复 HTML、CSS、JavaScript、TypeScript 等中的问题。</span><span class="sxs-lookup"><span data-stu-id="42f9e-111">Identify and fix problems in your HTML, CSS, JavaScript, TypeScript, and more by adding the [webhint extension for VS Code][VisualstudioMarketplaceWebhint].</span></span>  <span data-ttu-id="42f9e-112">提示显示为内联下划线，并在 "**问题**" 窗格中进行汇总。</span><span class="sxs-lookup"><span data-stu-id="42f9e-112">Hints appear as inline underlines and are summarized in the **Problems** pane.</span></span>  

## <span data-ttu-id="42f9e-113">配置</span><span class="sxs-lookup"><span data-stu-id="42f9e-113">Configuration</span></span>  

<span data-ttu-id="42f9e-114">此扩展使用[默认配置][GithubWebhintioIndexjson]json 文件，该文件激活 HTML、CSS、模板化系统 \ （JSX/TSX、角度等 \）、JavaScript/TypeScript 等的提示和分析程序。</span><span class="sxs-lookup"><span data-stu-id="42f9e-114">This extension uses a [default configuration][GithubWebhintioIndexjson] json file that activates hints and parsers for HTML, CSS, templating systems \(JSX/TSX, Angular, and so on\), JavaScript/TypeScript, and more.</span></span>  

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

<span data-ttu-id="42f9e-115">如果您希望更好地控制激活的提示和分析程序，请创建一个本地 `.hintrc` 文件来配置 webhint。</span><span class="sxs-lookup"><span data-stu-id="42f9e-115">If you want more control over the hints and parsers that get activated, create a local `.hintrc` file to configure webhint.</span></span>  <span data-ttu-id="42f9e-116">有关特定提示的输出的帮助，请参阅[webhint 用户指南][WebhintDocsUserguideConfiguringSummary]。</span><span class="sxs-lookup"><span data-stu-id="42f9e-116">For help with output from specific hints, see [webhint user guide][WebhintDocsUserguideConfiguringSummary].</span></span>  

## <span data-ttu-id="42f9e-117">与 webhint 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="42f9e-117">Getting in touch with the webhint team</span></span>  

<span data-ttu-id="42f9e-118">通过在[Webhint github][GithubWebhintio]存储库中[归档问题][GithubWebhintioIssuesNew]来发送反馈。</span><span class="sxs-lookup"><span data-stu-id="42f9e-118">Send your feedback by [filing an issue][GithubWebhintioIssuesNew] in [webhint GitHub repo][GithubWebhintio].</span></span>  

<span data-ttu-id="42f9e-119">若要参与扩展，请参阅[WEBHINT 和代码扩展发布指南][GithubWebhintioExtensionVscodeContributing]。</span><span class="sxs-lookup"><span data-stu-id="42f9e-119">To contribute to the extension, see [webhint VS Code extension contribution guide][GithubWebhintioExtensionVscodeContributing].</span></span>  

## <span data-ttu-id="42f9e-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42f9e-120">See also</span></span>  

*   [<span data-ttu-id="42f9e-121">辅助功能</span><span class="sxs-lookup"><span data-stu-id="42f9e-121">Accessibility</span></span>][AccessibilityIndex]  
*   [<span data-ttu-id="42f9e-122">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="42f9e-122">Visual Studio Code</span></span>][VisualstudiocodeIndex]  

<!-- image links -->  

<!--[ImageWebhintExtension]: ./media/webhint-extension.png "Screenshot of webhint VS Code extension"  -->  

<!--links -->  

[AccessibilityIndex]: /microsoft-edge/accessibility "辅助功能 |Microsoft 文档"  

[VisualstudiocodeIndex]: /microsoft-edge/visual-studio-code/index "Visual Studio 代码 |Microsoft 文档"  

[GithubWebhintio]: https://github.com/webhintio/hint "webhint |GitHub"  
[GithubWebhintioExtensionVscodeContributing]: https://github.com/webhintio/hint/blob/master/packages/extension-vscode/CONTRIBUTING.md "Webhint |GitHub"  
[GithubWebhintioIndexjson]: https://github.com/webhintio/hint/blob/master/packages/configuration-development/index.json "index-webhintio/提示 |GitHub"
[GithubWebhintioIssuesNew]: https://github.com/webhintio/hint/issues/new "新问题-webhintio/提示 |GitHub"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual Studio Marketplace"  

[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  

[WebhintDocsUserguideConfiguringSummary]: https://webhint.io/docs/user-guide/configuring-webhint/summary "配置 Webhint |webhint 文档"  
[WebhintMain]:  https://webhint.io "webhint"  
