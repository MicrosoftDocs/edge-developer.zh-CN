---
description: 在 Microsoft Edge 中使用 Playwright 自动处理和测试
title: 编剧
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/24/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 开发、开发人员、工具、自动化、测试、playwright、node、javascript、npm
ms.openlocfilehash: ac03923fb25da00f07cb70e81ac06b106a6e1452
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "11192210"
---
# 编剧  

[Playwright][|::ref1::|Main] 是一种 [Node.js][NodejsMain] 库，可通过单个 API 自动化 [Chromium][ChromiumHome]、 [Firefox][FirefoxMain]和 [WebKit][|::ref2::|Main] 。  Playwright 的构建使跨浏览器 web 自动化功能变得非常绿、功能可靠且速度更快。  由于 [Microsoft edge 是在开放源代码 Chromium web 平台上构建][MicrosoftBlogsWindowsExperience20181206]的，因此 Playwright 也可以自动执行 Microsoft edge。  

默认情况下，Playwright 启动无 [头浏览器][WikiHeadlessBrowser] 。  无外设浏览器不显示 UI，因此必须使用命令行。  您也可以将 Playwright 配置为同时运行完全 \ (非无外设 \ ) Microsoft Edge。  

默认情况下，安装 Playwright 时，安装程序将下载 [Chromium][ChromiumHome]、 [Firefox][FirefoxMain]和 [WebKit][|::ref3::|Main]。  如果你有 Microsoft Edge \ (Chromium \ ) 已安装，Playwright 只需更改一个单行代码即可在 Microsoft Edge 中测试你的网站或应用。  若要下载 Microsoft Edge \ (Chromium \ ) ，请导航到 " [下载 Microsoft edge][MicrosoftEdgeDownload]"。  

## 安装 Playwright  

安装 [Playwright][|::ref4::|Main] 以通过以下命令测试你的网站或应用。  

```shell
npm i playwright
```  

## 通过 Playwright 启动 Microsoft Edge  

> [!NOTE]
> [Playwright][|::ref5::|Main] 需要 Node.js 版本10.17 或更高版本。 `node -v`从命令行运行以确保你有兼容版本的 Node.js。  Chromium、Firefox 和 WebKit 的浏览器二进制文件在 Windows、macOS 和 Linux 中均可正常工作。 有关详细信息，请导航到 [Playwright 系统要求][PlaywrightSystemRequirements]。  

Playwright 应熟悉其他浏览器测试框架（如 [WebDriver][WebDriverChromiumMain] 或 [Puppeteer][PuppeteerMain]）的用户。  创建一个浏览器实例，打开一个页面，然后使用 [PLAYWRIGHT API][PlaywrightAPIReference]对其进行操作。  在以下代码段中，Playwright 将启动 Microsoft Edge \ (Chromium \ ) ，导航到 `https://www.microsoft.com/edge` 并将屏幕截图另存为 `example.png` 。  

复制以下代码片段并将其另存为 `example.js` 。  

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

更改 `executablePath` 为指向 Microsoft Edge \ (Chromium \ ) 的安装。  例如，在 macOS 上，" `executablePath` Microsoft Edge" 的 "关于" 应设置为 `/Applications/Microsoft\ Edge\ Canary.app/` 。  若要查找 `executablePath` ，请导航到 `edge://version` 该页面并复制该页面上的 **可执行路径** ，或通过以下命令安装 [edge 路径][npmEdgePaths] 程序包。  

```shell
npm i edge-paths
```  

以下代码片段使用 [edge 路径][npmEdgePaths] 程序包以编程方式查找你的 Microsoft edge \ (Chromium \ ) 在你的操作系统上的安装路径。  

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```  

最后，设置 `executablePath: EDGE_PATH` `example.js` 。  保存更改。  

> [!NOTE]
> Microsoft Edge \ (EdgeHTML \ ) 与 Playwright 不配合使用。  必须安装 [Microsoft Edge \ (Chromium \ ) ][MicrosoftEdgeDownload] ，才能继续关注本示例。  

现在 `example.js` 从命令行运行。  

```shell
node example.js
```  

Playwright 启动 Microsoft Edge，导航到 `https://www.microsoft.com/edge` 并保存页面的屏幕截图。  你可以自定义 [setViewportSize ( # B1 ][PlaywrightAPIPageSetViewport]的页面大小。  

:::image type="complex" source="../media/playwright-example.png" alt-text="由 example.js 生成的 example.png 文件" lightbox="../media/playwright-example.png":::
    `example.png`生成的文件 `example.js`  
:::image-end:::  

`example.js` 只是由 Playwright 启用的自动化和测试方案的简单演示。  若要在多个 web 浏览器中拍摄屏幕截图，请更改以下代码。  

*   Chromium  `await chromium.launch()`  
*   Firefox  `await firefox.launch()`  
*   WebKit  `await webkit.launch()`  

有关 Playwright 的详细信息，请导航到 [Playwright 网站][|::ref6::|Main]。  查看 GitHub 上的  [Playwright][PlaywrightRepo] 存储库。  若要与 Playwright 共享你的网站或应用的自动化和测试反馈，请将 [问题归档][PlaywrightRepoNewIssue]。  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../devtools-guide-chromium/includes/contact-devtools-team-note.md)]  

<!-- links -->  

[WebdriverChromiumMain]: ../webdriver-chromium/index.md "WebDriver (Chromium) |Microsoft 文档"  
[PuppeteerMain]: ../puppeteer.md "Puppeteer |Microsoft 文档"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge：通过更多打开源协作提高 web 效果 |Microsoft 体验博客"  

[MicrosoftEdgeDownload]: https://microsoft.com/edge "下载 Microsoft Edge"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |Chromium 项目"  

[FirefoxMain]: https://www.mozilla.org/firefox "Mozilla Firefox"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "边缘-路径 |npm"  

[PlaywrightMain]: https://playwright.dev "Playwright"  
[PlaywrightAPIReference]: https://playwright.dev#?path=docs/api.md "Playwright API 参考"  
[PlaywrightAPIPageSetViewport]: https://playwright.dev#?path=docs%2Fapi.md&q=pagesetviewportsizeviewportsize "setViewportSize (viewportSize) |Playwright API 参考"    
[PlaywrightSystemRequirements]: https://playwright.dev#?path=docs/intro.md&q=system-requirements "Playwright 系统要求"  

[PlaywrightRepo]: https://github.com/microsoft/playwright "Playwright |GitHub"  
[PlaywrightRepoNewIssue]: https://github.com/microsoft/playwright/issues/new/choose "Playwright 存储库中的新问题 |GitHub"  

[WebKitMain]: https://webkit.org "WebKit"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无外设浏览器 |科"  
