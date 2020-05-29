---
title: 打开 Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 48f80ea9f85bd3509f2ba3d834f99c25247c0761
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601885"
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





# 打开 Microsoft Edge DevTools   



打开 Microsoft Edge DevTools 有多种方法，因为不同的用户需要快速访问 DevTools UI 的不同部分。  

## 打开 "元素" 面板以检查 DOM 或 CSS   

当你想要检查某个 DOM 节点的样式或属性时，请右键单击该元素，然后选择 "**检查**"。  

> ##### 图 1  
> "**检查**" 选项  
> !["检查" 选项][ImageInspectOption]  

或按 `Control` + `Shift` + `C` \ （Windows \）或 `Command` + `Option` + `C` \ （macOS \）。  

<!--See [Get Started With Viewing And Changing CSS][GetStartedCSS].  -->  

## 打开控制台面板以查看记录的消息或运行 JavaScript   

按 `Control` + `Shift` + `J` \ （Windows \）或 `Command` + `Option` + `J` \ （macOS \）直接跳转到**控制台**面板。  

<!--See [Get Started With The Console][ConsoleGetStarted].  -->

## 打开已打开的上一个面板   

按 `Control` + `Shift` + `I` \ （Windows \）或 `Command` + `Option` + `I` \ （macOS \）。  

## 从 Microsoft Edge 主菜单打开 DevTools  

单击 "**设置" 和 "更多" \ （Alt + F \）** `...` ，然后选择 "**更多工具**  >  **开发人员工具**"。  

> ##### 图 2  
> 从 Microsoft Edge 主菜单打开 DevTools  
> ![从 Microsoft Edge 主菜单打开 DevTools][ImageOpenFromMain]  

## 在每个新选项卡上自动打开 DevTools   

从命令行打开 Microsoft Edge 并传递 `--auto-open-devtools-for-tabs` 标志。  

Windows \ （CMD \）：  

```cmd
start msedge --auto-open-devtools-for-tabs
```  

Windows \ （PowerShell \）：  

```powershell
Start-Process -FilePath "msedge" -ArgumentList "--auto-open-devtools-for-tabs"
```  

MacOS  

```bash
/Applications/Microsoft\ Edge\ Beta.app/Contents/MacOS/Microsoft\ Edge\ Beta --auto-open-devtools-for-tabs
```  

 



<!-- image links -->  

[ImagesMainIcon]: /microsoft-edge/devtools-guide-chromium/media/main-menu-icon.msft.png  

[ImageInspectOption]: /microsoft-edge/devtools-guide-chromium/media/bing-right-click-inspect.msft.png "图1： "检查" 选项"  
[ImageOpenFromMain]: /microsoft-edge/devtools-guide-chromium/media/bing-customize-more-tools-developer-tools-transparent.msft.png "图2：从 Microsoft Edge 主菜单打开 DevTools"  

<!-- links -->  

<!--[ConsoleGetStarted]: /microsoft-edge/devtools-guide-chromium/console/get-started ""  -->  
<!--[GetStartedCSS]: /microsoft-edge/devtools-guide-chromium/css "CSS"  -->

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/open)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
