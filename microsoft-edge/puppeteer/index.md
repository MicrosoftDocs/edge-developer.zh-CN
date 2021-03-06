---
description: 使用安全中心在 Microsoft Edge 中自动执行和测试
title: Puppeteer
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge， Web 开发， 开发人员， 工具， 自动化， 测试
ms.openlocfilehash: 068a2289b0e3bf8fffb49c771b83337abb79ea83
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398467"
---
# <a name="puppeteer-overview"></a>Puppeteer 概述  

[开发工具是][|::ref1::|Main][一个][NodejsMain]节点库，它提供高级 API 来控制 Microsoft Edge \ (Chromium\) [DevTools 协议][GithubChromedevtoolsProtocol]。  默认情况下，分步器 [会启动][WikiHeadlessBrowser] 无头浏览器。  无头浏览器不显示 UI，因此您必须使用命令行。  还可以将开发工具配置为运行完全 \ (无头\) Microsoft Edge。  

默认情况下，当你安装一个安装时，安装程序会下载最新版本 [的 Chromium，][ChromiumHome]这是 Microsoft Edge 也基于的开放 [源代码浏览器][MicrosoftBlogsWindowsExperience20181206]。  如果已安装 Microsoft Edge \ (Chromium\) ，可以使用 [开发程序核心][PuppeteerApivscore]。  `puppeteer-core` 是启动现有浏览器安装的轻型版本，如 Microsoft Edge \ (Chromium\) 。  若要下载 Microsoft Edge \ (Chromium\) ，请导航到"下载[Microsoft Edge 预览体验成员频道"。][MicrosoftedgeinsiderDownload]  

## <a name="installing-puppeteer-core"></a>安装安装程序核心  

可以使用以下 `puppeteer-core` 命令之一添加到网站或应用。  

```shell
npm i puppeteer-core
```  

```shell
yarn add puppeteer-core
```  

## <a name="launch-microsoft-edge-with-puppeteer-core"></a>使用产品核心启动 Microsoft Edge  

> [!NOTE]
> `puppeteer-core` 依赖于 Node v8.9.0 或更高版本。  以下示例使用仅在 Node `async` / `await` v7.6.0 或更高版本中支持的示例。  从 `node -v` 命令行运行，以确保具有兼容的Node.js。  

`puppeteer-core` 其他浏览器测试框架（如 [WebDriver）的用户应该很熟悉][WebdriverChromiumMain]。  创建浏览器实例，打开一个页面，然后使用开发工具 API 对其进行操作。  在下面的代码示例中，启动 `puppeteer-core` Microsoft Edge \ (Chromium\) ，导航到 ，将屏幕截图保存 `https://www.microsoftedgeinsider.com` 为 `example.png` 。  

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

更改为 `executablePath` 指向安装 Microsoft Edge \ (Chromium\) 。  例如，在 macOS 上 `executablePath` ，Microsoft Edge Canary 应设置为 `/Applications/Microsoft\ Edge\ Canary.app/` 。  若要查找，请导航到该页面上的可执行路径并复制该路径，或者使用以下命令之一安装边缘 `executablePath` `edge://version` 路径包。 **** [][npmEdgePaths]  

```shell
npm i edge-paths
```  

```shell
yarn add edge-paths
```  
 
下面的代码示例使用 [边缘路径][npmEdgePaths] 包以编程方式查找在操作系统上安装 Microsoft Edge \ (Chromium\) 的路径。

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

`puppeteer-core` 启动 Microsoft Edge，导航到 `https://www.microsoftedgeinsider.com` 并保存网页的屏幕截图。  使用 [page.setViewport ][PuppeteerApipagesetviewport] () 自定义屏幕截图 () 。  

:::image type="complex" source="./media/puppeteer-example.png" alt-text="由example.png生成的example.js" lightbox="./media/puppeteer-example.png":::
   `example.png`由 `example.js`  
:::image-end:::  

这只是一个简单示例，演示了由一名和一名用户启用的自动化和测试方案 `puppeteer-core` 。  有关一览器及其工作原理的信息，请导航[到"小程序"。][|::ref2::|Main]  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

Microsoft Edge 开发人员团队希望倾听你有关使用小程序以及 Microsoft `puppeteer-core` Edge 的反馈。  使用**** Microsoft Edge DevTools 或推文@EdgeDevTools[][TwitterIntentTweetEdgedevtools]中的"发送反馈"图标，让 Microsoft Edge 团队了解你的想法。  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   Microsoft Edge DevTools 中的**发送反馈**图标  
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

[GithubChromedevtoolsProtocol]: https://chromedevtools.github.io/devtools-protocol "Chrome DevTools 协议查看器|GitHub"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge：通过更多开放源代码协作功能改善|Microsoft 体验博客"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |Chromium 项目"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "边缘路径|npm"  

[PuppeteerMain]: https://pptr.dev "大头车"  
[PuppeteerApivscore]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-puppeteer-vs-puppeteer-core "|大头车"  
[PuppeteerApipagesetviewport]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-pagesetviewportviewport "page.setViewport (视口) |大头车"  

[TwitterIntentTweetEdgedevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools - 发布推文|Twitter"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无头浏览器|Wikipedia"  
