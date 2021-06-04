---
description: 使用 Playwright 自动执行和测试Microsoft Edge
title: 编剧
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/24/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge， Web 开发， 开发人员， 工具， 自动化， 测试， playwright， 节点， javascript， npm
ms.openlocfilehash: 5ce51864177731dd1bafb845466abb00cce1e0aa
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231081"
---
# 编剧  

[Playwright][|::ref1::|Main]是[一Node.js][NodejsMain] API 自动[Chromium、Firefox][FirefoxMain]和[WebKit][|::ref2::|Main]的一个库。 [][ChromiumHome]  Playwright 是专为启用跨浏览器 Web 自动化而构建的，该自动化功能非常绿色、功能可靠且快速。  由于[Microsoft Edge构建于开放源代码Chromium，][MicrosoftBlogsWindowsExperience20181206]因此 Playwright 还能够自动Microsoft Edge。  

默认情况下，Playwright [启动无][WikiHeadlessBrowser] 头浏览器。  无头浏览器不显示 UI，因此您必须使用命令行。  还可以将 Playwright 配置为运行完整 \(无头\) Microsoft Edge运行。  

默认情况下，安装 Playwright 时，安装程序会[Chromium、Firefox][FirefoxMain]和[WebKit。][|::ref3::|Main] [][ChromiumHome]  如果你还安装了 \Microsoft Edge \(Chromium\) ，Playwright 只需更改一行代码，在 Microsoft Edge 中测试您的网站或应用。  若要下载Microsoft Edge \(Chromium\) ，请导航到"下载[Microsoft Edge"。][MicrosoftEdgeDownload]  

##  <a name="installing-playwright--"></a>安装 Playwright  

安装 [Playwright][|::ref4::|Main] 以通过以下命令测试网站或应用。  

```shell
npm i playwright
```  

##  <a name="launch-microsoft-edge-with-playwright--"></a>启动Microsoft Edge Playwright  

> [!NOTE]
> [Playwright][|::ref5::|Main] 需要Node.js版本 10.17 或以上版本。 从 `node -v` 命令行运行，以确保具有兼容的 Node.js。  适用于 Chromium、Firefox 和 WebKit 的浏览器二进制文件跨 Windows、macOS 和 Linux 工作。 有关详细信息，请导航到["Playwright 系统要求"。][PlaywrightSystemRequirements]  

Playwright 应该为其他浏览器测试框架（如 [WebDriver][WebDriverChromiumMain] 或一台 [）的用户所熟悉][PuppeteerMain]。  创建浏览器实例，打开页面，然后使用 [Playwright API 对其进行操作][PlaywrightAPIReference]。  In the following code snippet， Playwright launchs Microsoft Edge \(Chromium\) ， navigates to `https://www.microsoft.com/edge` ， and saves a screenshot as `example.png` .  

复制以下代码段并将其另存为 `example.js` 。  

```javascript
const { chromium } = require('playwright');

(async () => {
  const browser = await chromium.launch({
    executablePath: 'C:\\Program Files (x86)\\Microsoft\\Edge Dev\\Application\\msedge.exe'
  });
  const page = await browser.newPage();
  await page.goto('https://www.microsoft.com/edge');
  await page.screenshot({path: 'example.png'});

  await browser.close();
})();
```  

更改为 `executablePath` 指向安装 Microsoft Edge \(Chromium\) 。  例如，在 macOS 上 `executablePath` ，Microsoft Edge Canary 应设置为 `/Applications/Microsoft\ Edge\ Canary.app/` 。  若要查找 ，请导航到 并复制该页面上的可执行路径，或者使用以下命令安装边缘 `executablePath` `edge://version` 路径包。 **** [][npmEdgePaths]  

```shell
npm i edge-paths
```  

以下代码段使用[边缘][npmEdgePaths]路径包以编程方式查找在操作系统上安装 Microsoft Edge \(Chromium\) 的路径。  

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```  

最后，在 `executablePath: EDGE_PATH` 中设置 `example.js` 。  保存更改。  

> [!NOTE]
> Microsoft Edge \(EdgeHTML\) 不能与 Playwright 一起工作。  必须安装[\Microsoft Edge \(Chromium\) ][MicrosoftEdgeDownload]以继续按照此示例操作。  

现在 `example.js` 从命令行运行。  

```shell
node example.js
```  

Playwright 启动Microsoft Edge，导航到 `https://www.microsoft.com/edge` ，并保存页面的屏幕截图。  可以使用 [page.setViewportSize ][PlaywrightAPIPageSetViewport]自定义页面 () 。  

:::image type="complex" source="../media/playwright-example.png" alt-text="由example.png生成的example.js" lightbox="../media/playwright-example.png":::
    `example.png`生成的文件 `example.js`  
:::image-end:::  

`example.js` 只是由 Playwright 启用的自动化和测试方案的一个简单演示。  若要在多个 Web 浏览器中拍摄屏幕截图，请更改以下代码。  

*   Chromium  `await chromium.launch()`  
*   Firefox  `await firefox.launch()`  
*   WebKit  `await webkit.launch()`  

有关 Playwright 的信息，请导航到 [Playwright 网站][|::ref6::|Main]。  请查看 GitHub 上的[Playwright][PlaywrightRepo]存储库。  若要与 Playwright 共享有关自动执行和测试网站或应用的反馈， [请提交问题][PlaywrightRepoNewIssue]。  

##  <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../devtools-guide-chromium/includes/contact-devtools-team-note.md)]  

<!-- links -->  

[WebdriverChromiumMain]: ../webdriver-chromium/index.md "WebDriver (Chromium) |Microsoft Docs"  
[PuppeteerMain]: ../puppeteer/index.md "百年|Microsoft Docs"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge：通过更多开放源代码协作功能改善|Microsoft 体验博客"  

[MicrosoftEdgeDownload]: https://microsoft.com/edge "下载Microsoft Edge"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |项目Chromium"  

[FirefoxMain]: https://www.mozilla.org/firefox "Mozilla Firefox"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "边缘路径|npm"  

[PlaywrightMain]: https://playwright.dev "Playwright"  
[PlaywrightAPIReference]: https://playwright.dev#?path=docs/api.md "Playwright API 参考"  
[PlaywrightAPIPageSetViewport]: https://playwright.dev#?path=docs%2Fapi.md&q=pagesetviewportsizeviewportsize "page.setViewportSize (viewportSize) |Playwright API 参考"    
[PlaywrightSystemRequirements]: https://playwright.dev#?path=docs/intro.md&q=system-requirements "Playwright 系统要求"  

[PlaywrightRepo]: https://github.com/microsoft/playwright "Playwright |GitHub"  
[PlaywrightRepoNewIssue]: https://github.com/microsoft/playwright/issues/new/choose "Playwright 存储库管理中的|GitHub"  

[WebKitMain]: https://webkit.org "WebKit"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无头浏览器|Wikipedia"  
