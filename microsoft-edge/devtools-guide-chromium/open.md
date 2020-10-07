---
description: All of the ways that you open the Microsoft Edge DevTools.
title: Open Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: ffc05a1eff2cdb7f3020a7dbb853a7520a0502dd
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993595"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License. -->

# Open Microsoft Edge DevTools  

There are many ways to open Microsoft Edge DevTools, because different users want fast access to different parts of the DevTools UI.  

## Open the Elements panel to inspect the DOM or CSS  

Each of the following tasks enable you to inspect the styles or attributes of a DOM node.

*   Hover on the element, open the contextual menu \(right-click\), and select **Inspect**.  
*   Press `Control`+`Shift`+`C` \(Windows\) or `Command`+`Option`+`C` \(macOS\).  For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].  

:::image type="complex" source="./media/bing-right-click-inspect.msft.png" alt-text="The **Inspect** option" lightbox="./media/bing-right-click-inspect.msft.png":::
   The **Inspect** option  
:::image-end:::  

<!--See [Get Started With Viewing And Changing CSS][GetStartedCSS].  -->  

## Open the Console panel  

Each of the following tasks enable you to open the [Console][DevToolsConsoleIndex] pane to view logged messages or run JavaScript.  

*   Use the following steps to open [Console][DevToolsConsoleIndex] pane.  
    
    1.  [Open DevTools](#open-microsoft-edge-devtools).  
    1.  Select the [Console][DevToolsConsoleIndex] pane.  

*   To jump straight into the [Console][DevToolsConsoleIndex] pane, press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).  For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].  

<!--See [Get Started With The Console][ConsoleGetStarted].  -->

## Open the previous panel  

To jump to the previous panel that you had open, press `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).  For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].  

## Open Microsoft Edge DevTools  

Each of the following tasks enable you to open DevTools.  

*   Use the following steps to open Microsoft Edge DevTools.  
    
    1.  Select the  `...` icon \(the **Settings and more** icon\).  
    1.  Select **More Tools**.  
    1.  Select **Developer Tools**.  
    
*   To open Microsoft Edge DevTools, press `F12` or `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\).  For more information, see [Microsoft Edge DevTools keyboard shortcuts][DevToolsShortcuts].  

:::image type="complex" source="./media/bing-customize-more-tools-developer-tools-transparent.msft.png" alt-text="The **Inspect** option" lightbox="./media/bing-customize-more-tools-developer-tools-transparent.msft.png":::
   Open DevTools from the Microsoft Edge main menu  
:::image-end:::  

## Auto-open DevTools on every new tab  

To auto-open DevTools on every new tab, open Microsoft Edge from the command-line and pass the `--auto-open-devtools-for-tabs` flag.  

#### [CMD (Windows)](#tab/cmd-windows/)  

<a id="selenium-tools-install"></a>  

```cmd
start msedge --auto-open-devtools-for-tabs
```  

#### [PowerShell (Windows)](#tab/powershell-windows/)  

<a id="selenium-tools-install"></a>  

```powershell
Start-Process -FilePath "msedge" -ArgumentList "--auto-open-devtools-for-tabs"
```  

#### [bash (macOS)](#tab/bash-macos/)  

<a id="selenium-tools-install"></a>  

```bash
/Applications/Microsoft\ Edge\ Beta.app/Contents/MacOS/Microsoft\ Edge\ Beta --auto-open-devtools-for-tabs
```  

* * *  

<!-- links -->  

[DevToolsConsoleIndex]: ./console/index.md "Console Overview | Microsoft Docs"  
[DevtoolsShortcuts]: ./shortcuts.md "Microsoft Edge DevTools keyboard shortcuts - Microsoft Docs"  

<!--[ConsoleGetStarted]: /microsoft-edge/devtools-guide-chromium/console/get-started ""  -->  
<!--[GetStartedCSS]: /microsoft-edge/devtools-guide-chromium/css "CSS"  -->

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/open)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
