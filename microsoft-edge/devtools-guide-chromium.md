---
description: Get to know the Microsoft Edge (Chromium) Developer Tools
title: Microsoft Edge (Chromium) Developer Tools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: ba925c402d33ba75c558006c7c43c5dc05515911
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "11003934"
---
# Microsoft Edge (Chromium) Developer Tools  

Microsoft Edge has adopted the Chromium open source project to create better web compatibility and less fragmentation of different underlying web platforms.  This change should make it easier for you to build and test your websites in Microsoft Edge and ensure that each works as expected even while viewed in a different Chromium-based browser \(such as Google Chrome, Vivaldi, Opera, or Brave\).  

As the web has grown in usage across an ever-widening array of device types, the complexity and overhead involved in testing websites has exploded. Since web developers \(particularly those at small companies\) must test against so many different systems, you may find it nearly impossible to ensure that sites work well on all device types and all browsers.  Now that Microsoft Edge is based on Chromium, the Microsoft Edge team has simplified the matrix by aligning the Microsoft Edge web platform with other Chromium-based browsers and provided a best-in-class developer tooling experience, both inside the browser and with the other developer tools you use every day \(such as Visual Studio Code\).  

If you are checking out Microsoft Edge and you mainly develop in a Chromium-based browser, you should feel right at home.  The Microsoft Edge \(Chromium\) Developer Tools function in the same way as the developer tools you already know and use.  For more information, see [What's new in the Microsoft Edge (Chromium) DevTools][DevtoolsGuideChromiumWhatsNewIndex].  

:::image type="complex" source="./devtools-guide-chromium/media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools":::
   Microsoft Edge (Chromium) DevTools  
:::image-end:::  

If you are checking out the next version of Microsoft Edge and you previously developed in Microsoft Edge \(EdgeHTML\), you now have some great new tools that should make it easier and faster to build and test your websites in Microsoft Edge!  

## Open the DevTools  

If you have never used the DevTools before, the Microsoft Edge Developer Tools are a set of tools built directly into the Microsoft Edge browser.  With these DevTools, you are able to do the following.  

*   Inspect and make changes to your HTML website  
*   Edit CSS and instantly see preview how your website renders  
*   See all the `console.log()` statements from your front-end JavaScript code  
*   Debug your script by setting breakpoints and stepping through it line by line  

all directly within the browser.  These are just examples of some of the features the DevTools provide to make it easier and faster for you to build and test your websites in Microsoft Edge.  

To open the DevTools  

*   press `F12` 
*   press `Ctrl`+`Shift`+`I` on Windows \(`Command`+`Option`+`I` on macOS\)  

If you want to see the HTML or CSS for an element on your site, right-click the element and select **Inspect** to jump into the Elements panel.  You may also press `Ctrl`+`Shift`+`C` on Windows \(`Command`+`Option`+`C` on macOS\) to open the DevTools in **Inspect Element Mode** which lets you select an element on the site and see the HTML and CSS in the **Elements** panel.  

If you want to see logs from your front-end JavaScript code or quickly run some script, press `Ctrl`+`Shift`+`J` on Windows or `Command`+`Option`+`J` on macOS to launch the Console panel in the DevTools.  

## Core tools  

:::image type="complex" source="./devtools-guide-chromium/media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools":::
   Microsoft Edge (Chromium) DevTools core tools  
:::image-end::: 

The Microsoft Edge \(Chromium\) DevTools include the following panels.  

*   An **Elements** panel to edit HTML and CSS, inspect accessibility properties, view event listeners, and set DOM mutation breakpoints  
*   **控制台**，用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点，并在所选窗口或框架的上下文中运行 JavaScript  
*   A **Sources** panel to open and live edit your code, set breakpoints, step through code, and see the state of your website one line of JavaScript at a time  
*   A **Network** panel to monitor and inspect requests and responses from the network and browser cache   
*   “**性能**”面板，用于分析网站所需的时间和系统资源  
*   A **Memory** panel to measure your use of memory resources and compare heap snapshots at different states of code runtime  
*   An **Application** panel to inspect, modify, and debug web app manifests, service workers, and service worker caches.  You may also inspect and manage storage, databases, and caches from the **Application** panel.  
*   A **Security** panel to debug security issues and ensure that you have properly implemented HTTPS on your website.  HTTPS provides critical security and data integrity for both your site and your users that provide personal information on your site.  
*   An **Audits** panel \(now renamed **Lighthouse**\) to run an audit of your website.  The results of the audit help you improve the quality of your site in the following ways.  
    *   Catch common errors related to making your website accessible, secure, performant, and so on.  
    *   Fix each error.  
    *   Build a PWA.  

[!INCLUDE [audits-panel-note](./devtools-guide-chromium/includes/audits-panel-note.md)]  

Please send your [feedback and feature requests](#getting-in-touch-with-the-microsoft-edge-devtools-team).  

## Extensions  

You may have used extensions to the DevTools to help you diagnose and debug issues when building your websites or apps.  You may acquire extensions for Microsoft Edge from the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page.  From the [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] page, you may browse DevTools extensions from the **Developer tools** category or search for a specific extension.  

You may also add extensions from the [Chrome Web Store][GoogleChromeWebstoreExtensions].  

:::image type="complex" source="./devtools-guide-chromium/media/allow-extensions-from-stores.png" alt-text="Microsoft Edge (Chromium) DevTools":::
   Chrome Web Store in Microsoft Edge  
:::image-end:::  

At the top, select **Allow extensions from other stores** and then select **Allow** in the dialog that appears.  

> [!NOTE]
> Extensions installed from sources other than the Microsoft Store are unverified, and may affect browser performance.  

Select **Add to Chrome** to add your DevTools extension to Microsoft Edge!  

:::image type="complex" source="./devtools-guide-chromium/media/install-extension-from-chrome-store.png" alt-text="Microsoft Edge (Chromium) DevTools"  
