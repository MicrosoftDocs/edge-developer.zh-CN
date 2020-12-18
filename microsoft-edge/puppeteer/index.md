---
description: 使用安装器在 Microsoft Edge 中自动执行和测试
title: Puppeteer
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge， Web 开发， 开发人员， 工具， 自动化， 测试
ms.openlocfilehash: 99d873a9b3988cb8a2827ecc9a69d574a196b037
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232054"
---
# Puppeteer 概述  

[表示器是][|::ref1::|Main][一个][NodejsMain]节点库，它提供高级 API 来控制 Microsoft Edge \ (Chromium\) [DevTools 协议][GithubChromedevtoolsProtocol]。  默认情况下，安装 [器将启动无][WikiHeadlessBrowser] 头浏览器。  无头浏览器不显示 UI，因此您必须使用命令行。  还可以将安装安装器配置为运行完全 \ (无头\) Microsoft Edge。  

默认情况下，安装器时，安装程序会下载 [最新版本的 Chromium，][ChromiumHome]这是 Microsoft Edge 也基于的开放 [源代码浏览器][MicrosoftBlogsWindowsExperience20181206]。  如果已安装 Microsoft Edge \ (Chromium\) ， [可以使用安装程序核心][PuppeteerApivscore]。  `puppeteer-core` 是启动现有浏览器安装（如 Microsoft Edge \ (Chromium\) ）的轻型版本。  若要下载 Microsoft Edge \ (Chromium\) ，请导航到"下载[Microsoft Edge 预览体验成员频道"。][MicrosoftedgeinsiderDownload]  

## 安装安装程序核心  

可以使用以下命令之一 `puppeteer-core` 添加到网站或应用。  

```shell
npm i puppeteer-core
```  

```shell
yarn add puppeteer-core
```  

## 启动具有中心处理器核心的 Microsoft Edge  

> [!NOTE]
> `puppeteer-core` 依赖于 Node v8.9.0 或更高版本。  以下示例使用仅在 Node `async` / `await` v7.6.0 或更高版本中支持的示例。  从 `node -v` 命令行运行，以确保你的应用程序具有兼容的Node.js。  

`puppeteer-core` 应熟悉其他浏览器测试框架（如 [WebDriver）的用户][WebdriverChromiumMain]。  创建浏览器实例，打开一个页面，然后使用更新程序 API 对其进行操作。  In the following code sample， `puppeteer-core` launches Microsoft Edge \ (Chromium\) ， navigates `https://www.microsoftedgeinsider.com` to， and saves a screenshot as `example.png` .  

复制以下代码段并将其另存为 `example.js` 。  

```javascript
const puppeteer = require('puppeteer-core');

(async () => {
  const browser = await puppeteer.launch({
    executablePath: 'C:\\Program Files (x86)\\Microsoft\\Edge Dev\\Application\\msedge.exe'
  });
  const page = await browser.newPage();
  await page.goto('https://www.microsoftedgeinsider.com');
  await page.screenshot({path: 'example.png'});

  await browser.close();
})();
```  

更改为 `executablePath` 指向安装 Microsoft Edge \ (Chromium\) 。  例如，在 macOS 上 `executablePath` ，Microsoft Edge Canary 应设置为 `/Applications/Microsoft\ Edge\ Canary.app/` 。  若要查找，请导航到该页面上的"可执行文件"路径并复制该路径，或者使用以下命令之一安装边缘 `executablePath` `edge://version` 路径包。 **** [][npmEdgePaths]  

```shell
npm i edge-paths
```  

```shell
yarn add edge-paths
```  
 
下面的代码示例使用 [边缘][npmEdgePaths] 路径包以编程方式查找在操作系统上安装 Microsoft Edge \ (Chromium\) 的路径。

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```

最后，在 `executablePath: EDGE_PATH` `example.js` 中设置。  保存更改。  

> [!NOTE]
> Microsoft Edge \ (EdgeHTML\) 不能与 `puppeteer-core` 。  必须安装 [Microsoft Edge 预览体验成员频道][MicrosoftedgeinsiderDownload] ，以继续遵循此示例。  

现在， `example.js` 从命令行运行。  

```shell
node example.js
```  

`puppeteer-core` 启动 Microsoft Edge，导航到 `https://www.microsoftedgeinsider.com` 并保存网页的屏幕截图。  使用 [page.setViewport () 自定义屏幕截图大小 ][PuppeteerApipagesetviewport]。  

:::image type="complex" source="./media/puppeteer-example.png" alt-text="由example.png生成的example.js" lightbox="./media/puppeteer-example.png":::
   `example.png`生成的文件 `example.js`  
:::image-end:::  

这只是一个简单的示例，演示了由一名和一名用户启用的自动化和测试方案 `puppeteer-core` 。  有关一些产品及其工作方式的信息，请参阅 ["一][|::ref2::|Main]线"。  

## 联系 Microsoft Edge DevTools 团队  

Microsoft Edge 开发人员团队希望倾听你有关使用一线和 Microsoft `puppeteer-core` Edge 的反馈。  使用**** Microsoft Edge DevTools 或推文@EdgeDevTools中的"发送反馈"[图标][TwitterIntentTweetEdgedevtools]，让 Microsoft Edge 团队了解你的想法。  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   Microsoft **Edge** DevTools 中的"发送反馈"图标  
:::image-end:::  

<!--## See also  

*   [WebDriver (Chromium)][WebdriverChromiumMain]  
*   [WebDriver (EdgeHTML)][WebdriverEdgehtmlMain]  
*   [Chrome DevTools Protocol Viewer on GitHub][GithubChromedevtoolsProtocol]  
*   [Microsoft Edge:  Making the web better through more open source collaboration on Microsoft Experience Blog][MicrosoftBlogsWindowsExperience20181206]  
*   [Download Microsoft Edge Insider Channels][MicrosoftedgeinsiderDownload]  
*   [Chromium on The Chromium Projects][ChromiumHome]  
*   [Node.js][NodejsMain]  
*   [Puppeteer][PuppeteerMain]  
*   [puppeteer vs. puppeteer-core][PuppeteerApivscore]  
*   [page.setViewport() on Puppeteer][PuppeteerApipagesetviewport]  
*   [Headless browser on Wikipedia][WikiHeadlessBrowser]  -->  

<!-- links -->  

[WebdriverChromiumMain]: ../webdriver-chromium/index.md "WebDriver (Chromium) |Microsoft Docs"  
<!--  [WebdriverEdgehtmlMain]: ../edgehtml/webdriver/index.md "WebDriver (EdgeHTML) | Microsoft Docs"  -->  

[GithubChromedevtoolsProtocol]: https://chromedevtools.github.io/devtools-protocol "Chrome DevTools 协议查看器 |GitHub"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge：通过更多开放源代码协作改善 Web |Microsoft 体验博客"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |Chromium 项目"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "边缘路径 |npm"  

[PuppeteerMain]: https://pptr.dev "一线"  
[PuppeteerApivscore]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-puppeteer-vs-puppeteer-core "与er-core |一线"  
[PuppeteerApipagesetviewport]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-pagesetviewportviewport "page.setViewport (视口) |一线"  

[TwitterIntentTweetEdgedevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools - 发布推文 |Twitter"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无头浏览器 |Wikipedia"  
