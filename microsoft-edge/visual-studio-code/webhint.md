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
# <a name="webhint-vs-code-extension"></a><span data-ttu-id="77fee-104">Webhint 与代码扩展</span><span class="sxs-lookup"><span data-stu-id="77fee-104">Webhint Vs Code Extension</span></span>  

<span data-ttu-id="77fee-105">使用 [Webhint（][WebhintMain]一种可自定义的 linting 工具）来提高网站的辅助功能、性能、跨浏览器兼容性、PWA 兼容性和安全性。</span><span class="sxs-lookup"><span data-stu-id="77fee-105">Use [webhint][WebhintMain], a customizable linting tool, to improve the accessibility, performance, cross-browser compatibility, PWA compatibility, and security of your site.</span></span>  <span data-ttu-id="77fee-106">它会检查代码的最佳实践和常见错误。</span><span class="sxs-lookup"><span data-stu-id="77fee-106">It checks your code for best practices and common errors.</span></span> <span data-ttu-id="77fee-107">此开源项目最初由 Microsoft Edge 团队开发，现在是 [OpenJS Foundation][OpenjsFoundation]的一部分。</span><span class="sxs-lookup"><span data-stu-id="77fee-107">This open-source project, initially developed by the Microsoft Edge team, is now part of the [OpenJS Foundation][OpenjsFoundation].</span></span>  <span data-ttu-id="77fee-108">Microsoft Edge 团队将继续与社区中的 Web 开发人员一起为 WebHint 做贡献。</span><span class="sxs-lookup"><span data-stu-id="77fee-108">The Microsoft Edge team continues to contribute to webhint alongside web developers in the community.</span></span>  

:::image type="complex" source="./media/webhint-extension.png" alt-text="Webhint Visual Studio代码扩展的屏幕截图":::
   <span data-ttu-id="77fee-110">Webhint Visual Studio代码扩展的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="77fee-110">Screenshot of webhint Visual Studio Code extension</span></span>  
:::image-end:::

<!--![Screenshot of webhint Visual Studio Code extension][ImageWebhintExtension]  -->  

<span data-ttu-id="77fee-111">通过添加 [Webhint][VisualstudioMarketplaceWebhint]扩展以识别并修复 HTML、CSS、JavaScript、TypeScript 等中的问题Visual Studio代码。</span><span class="sxs-lookup"><span data-stu-id="77fee-111">Identify and fix problems in your HTML, CSS, JavaScript, TypeScript, and more by adding the [webhint extension for Visual Studio Code][VisualstudioMarketplaceWebhint].</span></span>  <span data-ttu-id="77fee-112">提示显示为内联下划线，并汇总在"问题 **"** 窗格中。</span><span class="sxs-lookup"><span data-stu-id="77fee-112">Hints appear as inline underlines and are summarized in the **Problems** pane.</span></span>  

## <a name="configuration"></a><span data-ttu-id="77fee-113">配置</span><span class="sxs-lookup"><span data-stu-id="77fee-113">Configuration</span></span>  

<span data-ttu-id="77fee-114">此扩展使用默认配置 [json][GithubWebhintioIndexjson] 文件，该文件激活 HTML、CSS、模板系统 \ (JSX/TSX、Angular 等\) 、JavaScript/TypeScript 等的提示和分析程序。</span><span class="sxs-lookup"><span data-stu-id="77fee-114">This extension uses a [default configuration][GithubWebhintioIndexjson] json file that activates hints and parsers for HTML, CSS, templating systems \(JSX/TSX, Angular, and so on\), JavaScript/TypeScript, and more.</span></span>  

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

<span data-ttu-id="77fee-115">如果希望对激活的提示和分析程序进行更多控制，请创建一个本地 `.hintrc` 文件以配置 Webhint。</span><span class="sxs-lookup"><span data-stu-id="77fee-115">If you want more control over the hints and parsers that get activated, create a local `.hintrc` file to configure webhint.</span></span>  <span data-ttu-id="77fee-116">有关特定提示输出的帮助，请导航到 [Webhint 用户指南][WebhintDocsUserguideConfiguringSummary]。</span><span class="sxs-lookup"><span data-stu-id="77fee-116">For help with output from specific hints, navigate to [webhint user guide][WebhintDocsUserguideConfiguringSummary].</span></span>  

## <a name="getting-in-touch-with-the-webhint-team"></a><span data-ttu-id="77fee-117">与 Webhint 团队联系</span><span class="sxs-lookup"><span data-stu-id="77fee-117">Getting in touch with the webhint team</span></span>  

<span data-ttu-id="77fee-118">通过向[][GithubWebhintioIssuesNew][Webhint GitHub 存储库提交问题来发送反馈][GithubWebhintio]。</span><span class="sxs-lookup"><span data-stu-id="77fee-118">Send your feedback by [filing an issue][GithubWebhintioIssuesNew] in [webhint GitHub repo][GithubWebhintio].</span></span>  

<span data-ttu-id="77fee-119">若要参与扩展，请导航到 [webhint Visual Studio代码扩展贡献指南][GithubWebhintioExtensionVscodeContributing]。</span><span class="sxs-lookup"><span data-stu-id="77fee-119">To contribute to the extension, navigate to [webhint Visual Studio Code extension contribution guide][GithubWebhintioExtensionVscodeContributing].</span></span>  

## <a name="see-also"></a><span data-ttu-id="77fee-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77fee-120">See also</span></span>  

*   [<span data-ttu-id="77fee-121">辅助功能</span><span class="sxs-lookup"><span data-stu-id="77fee-121">Accessibility</span></span>][AccessibilityIndex]  
*   [<span data-ttu-id="77fee-122">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="77fee-122">Visual Studio Code</span></span>][VisualstudiocodeIndex]  

<!-- image links -->  

<!--[ImageWebhintExtension]: ./media/webhint-extension.png "Screenshot of webhint Visual Studio Code extension"  -->  

<!--links -->  

[AccessibilityIndex]: /microsoft-edge/accessibility "辅助功能|Microsoft Docs"  

[VisualstudiocodeIndex]: /microsoft-edge/visual-studio-code/index "Visual Studio代码|Microsoft Docs"  

[GithubWebhintio]: https://github.com/webhintio/hint "webhint |GitHub"  
[GithubWebhintioExtensionVscodeContributing]: https://github.com/webhintio/hint/blob/master/packages/extension-vscode/CONTRIBUTING.md "贡献 - webhint |GitHub"  
[GithubWebhintioIndexjson]: https://github.com/webhintio/hint/blob/master/packages/configuration-development/index.json "index.js- webhintio/hint |GitHub"
[GithubWebhintioIssuesNew]: https://github.com/webhintio/hint/issues/new "新问题 - webhintio/hint |GitHub"  

[VisualstudioMarketplaceWebhint]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual Studio市场"  

[OpenjsFoundation]:  https://openjsf.org "OpenJS Foundation"  

[WebhintDocsUserguideConfiguringSummary]: https://webhint.io/docs/user-guide/configuring-webhint/summary "配置 Webhint |webhint 文档"  
[WebhintMain]:  https://webhint.io "webhint"  
