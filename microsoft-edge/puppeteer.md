---
description: 在 Microsoft Edge 中使用 Puppeteer 自动处理和测试
title: Puppeteer
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge，web 开发，开发人员，工具，自动化，测试
ms.openlocfilehash: a78bdc0eb96db018818ef122c772bc9023adac46
ms.sourcegitcommit: 4187d4c3fbf4ef99a3b8a63db8a182355c84c1f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601935"
---
# Puppeteer  

[Puppeteer][|::ref1::|Main]是一个[节点][NodejsMain]库，它提供了一个高级别 API，可通过[DevTools 协议][GithubChromedevtoolsProtocol]控制 Microsoft Edge \ （Chromium \）。  默认情况下，Puppeteer 运行无[头][WikiHeadlessBrowser]，这意味着你看不到 UI，而是必须使用命令行。  您也可以将 Puppeteer 配置为同时运行完整 \ （非外设 \） Microsoft Edge 或 Chromium。  

默认情况下，当你安装 Puppeteer 时，安装程序将下载[Chromium][ChromiumHome]的最新版本，[还会生成 Microsoft Edge][MicrosoftBlogsWindowsExperience20181206]的 "开放源代码浏览器"。  如果安装了 Microsoft Edge \ （Chromium \），则可以使用[puppeteer-core][PuppeteerApivscore]。  `puppeteer-core` 是一种轻量级版本的 Puppeteer，用于启动现有的浏览器安装，如 Microsoft Edge \ （Chromium \）。  若要下载 Microsoft Edge \ （Chromium \），请参阅[下载 Microsoft Edge 预览体验成员频道][MicrosoftedgeinsiderDownload]。

## 安装 puppeteer  

你可以 `puppeteer-core` 通过以下命令之一添加到你的网站或应用。  

```shell
npm i puppeteer-core
```  

```shell
yarn add puppeteer-core
```  

## 通过 puppeteer 启动 Microsoft Edge  

> [!NOTE]
> `puppeteer-core` 依赖于节点 v 8.9.0 或更高版本。  下面的示例使用 `async` / `await` 了仅在节点 v 7.6.0 或更高版本中才受支持的示例。  `node -v`从命令行运行以确保你有兼容的 node.js 版本。  

`puppeteer-core` 应熟悉其他浏览器测试框架（如[WebDriver][WebDriverEdgehtmlMain]）的用户。  创建一个浏览器实例，打开一个页面，然后使用 Puppeteer API 对其进行操作。  在以下代码示例中， `puppeteer-core` 启动 Microsoft Edge \ （Chromium \），导航到 `https://www.microsoftedgeinsider.com` 并将屏幕截图另存为 `example.png` 。  

复制下面的代码示例并将其另存为 `example.js` 。  

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

更改 `executablePath` 以指向 Microsoft Edge \ （Chromium \）的安装。  例如，在 macOS 上，" `executablePath` Microsoft Edge" 的 "关于" 应设置为 `/Applications/Microsoft\ Edge\ Canary.app/` 。  若要查找 `executablePath` ，请导航到 `edge://version` 。  保存更改。  

> [!NOTE]
> Microsoft Edge \ （EdgeHTML \）不起作用 `puppeteer-core` 。  必须安装[Microsoft Edge 预览体验成员频道][MicrosoftedgeinsiderDownload]才能继续关注此示例。  

现在 `example.js` 从命令行运行。  

```shell
node example.js
```  

`puppeteer-core` 启动 Microsoft Edge，导航到 `https://www.microsoftedgeinsider.com` 页面的 800px x 600px 屏幕截图并将其保存。  你可以通过[setViewport （）][PuppeteerApipagesetviewport]自定义页面大小。  

:::image type="complex" source="./media/puppeteer-example.png" alt-text="示例 .js 生成的 .png 文件。":::
   图1： `example.png` 生成的文件 `example.js`  
:::image-end:::  

<!--  
> ##### Figure 1  
> The `example.png` file produced by `example.js`  
> ![The example.png file produced by example.js](./media/puppeteer-example.png)  
-->  

这只是由 Puppeteer 和的自动化和测试方案所支持的简单示例 `puppeteer-core` 。  有关 Puppeteer 及其工作原理的详细信息，请参阅[Puppeteer][|::ref2::|Main]。  

## 发送反馈  

Edge 开发人员团队渴望听到有关使用 Puppeteer、 `puppeteer-core` 和 Microsoft Edge 的反馈。  使用 Microsoft Edge DevTools 或 tweet [@EdgeDevTools][TwitterIntentTweetEdgedevtools]中的 "**发送反馈**" 图标，让 Microsoft edge 团队知道您的想法。  


:::image type="complex" source="./devtools-guide-chromium/media/devtools-feedback.png" alt-text="Microsoft Edge DevTools 中的 "反馈" 图标":::
   图2： Microsoft Edge DevTools 中的 "**反馈**" 图标  
:::image-end:::  

<!--  
> ##### Figure 2  
> The **Feedback** icon in the Microsoft Edge DevTools  
> ![The Feedback icon in the Microsoft Edge DevTools](./devtools-guide-chromium/media/devtools-feedback.png)  
-->  

<!--## See also  

*   [WebDriver (Chromium)][WebdriverChromiumMain]  
*   [WebDriver (EdgeHTML)][WebdriverEdgehtmlMain]  
*   [Chrome DevTools Protocol Viewer on GitHub][GithubChromedevtoolsProtocol]  
*   [Microsoft Edge: Making the web better through more open source collaboration on Microsoft Experience Blog][MicrosoftBlogsWindowsExperience20181206]  
*   [Download Microsoft Edge Insider Channels][MicrosoftedgeinsiderDownload]  
*   [Chromium on The Chromium Projects][ChromiumHome]  
*   [Node.js][NodejsMain]  
*   [Puppeteer][PuppeteerMain]  
*   [puppeteer vs. puppeteer-core][PuppeteerApivscore]  
*   [page.setViewport() on Puppeteer][PuppeteerApipagesetviewport]  
*   [Headless browser on Wikipedia][WikiHeadlessBrowser]  -->  

<!-- image links -->  

<!-- links -->  

[WebdriverChromiumMain]: ./webdriver-chromium.md "WebDriver (Chromium)"  
[WebdriverEdgehtmlMain]: ./webdriver.md "WebDriver (EdgeHTML)"  

[GithubChromedevtoolsProtocol]: https://chromedevtools.github.io/devtools-protocol "Chrome DevTools 协议查看器 |GitHub"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge：通过更多打开源协作提高 web 效果 |Microsoft 体验博客"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |Chromium 项目"  

[NodejsMain]: https://nodejs.org "Node.js"  

[PuppeteerMain]: https://pptr.dev "Puppeteer"  
[PuppeteerApivscore]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-puppeteer-vs-puppeteer-core "puppeteer 与 puppeteer-核心 |Puppeteer"  
[PuppeteerApipagesetviewport]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-pagesetviewportviewport "setViewport （视口） |Puppeteer"  

[TwitterIntentTweetEdgedevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools 发布 Tweet |Twitter"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无外设浏览器 |科"  
