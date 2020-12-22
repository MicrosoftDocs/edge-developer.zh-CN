---
description: 打开 Microsoft Edge DevTools 的所有方法。
title: 打开 Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: d21ebbf0b84be757c1b7a69d36b3bd3cc8403c6d
ms.sourcegitcommit: 77c8f42cc84600c2b853b15aaaecf0749b74bb01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2020
ms.locfileid: "11238217"
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

有很多方法可以打开 Microsoft Edge DevTools，因为不同的用户希望快速访问 DevTools UI 的不同部分。  

## 打开"元素"面板以检查 DOM 或 CSS  

通过以下每个任务，您可以检查 DOM 节点的样式或属性。

*   将鼠标悬停在元素上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**  
*   选择 `Control` + `Shift` + `C` \ (Windows、Linux\) `Command` + `Option` + `C` 或 \ (macOS\) 。  有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevtoolsShortcutsIndex]。  

:::image type="complex" source="../media/bing-right-click-inspect.msft.png" alt-text=""检查"选项" lightbox="../media/bing-right-click-inspect.msft.png":::
   " **检查"** 选项  
:::image-end:::  

<!--See [Get Started With Viewing And Changing CSS][GetStartedCSS].  -->  

## 打开控制台面板  

通过以下每个任务，您可以打开 [控制台][DevtoolsConsoleIndex] 窗格以查看记录的消息或运行 JavaScript。  

*   使用以下步骤打开 [控制台][DevtoolsConsoleIndex] 窗格。  
    
    1.  [打开 DevTools。](#open-microsoft-edge-devtools)  
    1.  选择 [控制台][DevtoolsConsoleIndex] 窗格。  

*   若要直接跳转到控制台[窗格][DevtoolsConsoleIndex]，请选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。  有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevtoolsShortcutsIndex]。  

<!--See [Get Started With The Console][ConsoleGetStarted].  -->

## 打开上一个面板  

若要跳转到你打开的上一个面板，请选择 `Control` + `Shift` + `I` \ (Windows、Linux\) 或 `Command` + `Option` + `I` \ (macOS\) 。  有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevtoolsShortcutsIndex]。  

## 打开 Microsoft Edge DevTools  

若要打开 DevTools，请使用以下任一选项。  

*   使用 Microsoft Edge UI。  
    
    1.  选择" **设置"和更多 \ (** `...` \) 图标。  
    1.  选择 **"更多工具"。**  
    1.  选择 **"开发人员工具"。**  
    
*   使用键盘。  
    *   选择 `F12` 或 `Control` + `Shift` + `I` \ (Windows、Linux\) 或 `Command` + `Option` + `I` \ (macOS\) 。  

有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevtoolsShortcutsIndex]。  

:::image type="complex" source="../media/bing-customize-more-tools-developer-tools-transparent.msft.png" alt-text="从 Microsoft Edge 主菜单打开 DevTools" lightbox="../media/bing-customize-more-tools-developer-tools-transparent.msft.png":::
   从 Microsoft Edge 主菜单打开 DevTools  
:::image-end:::  

## 自动打开每个新选项卡上的 DevTools  

若要自动打开每个新选项卡上的 DevTools，请从命令行打开 Microsoft Edge 并传递 `--auto-open-devtools-for-tabs` 标志。  

### [Windows (CMD) ](#tab/cmd-Windows/)  

<a id="auto-open-devtools-command-line"></a>  

```cmd
start msedge --auto-open-devtools-for-tabs
```  

### [PowerShell (Windows) ](#tab/powershell-Windows/)  

<a id="auto-open-devtools-command-line"></a>  

```powershell
Start-Process -FilePath "msedge" -ArgumentList "--auto-open-devtools-for-tabs"
```  

### [bash (macOS) ](#tab/bash-macos/)  

<a id="auto-open-devtools-command-line"></a>  

```bash
/Applications/Microsoft\ Edge\ Beta.app/Contents/MacOS/Microsoft\ Edge\ Beta --auto-open-devtools-for-tabs
```  

### [Bash (Linux) ](#tab/bash-linux/)  

<a id="auto-open-devtools-command-line"></a>  

```bash
microsoft-edge-dev --auto-open-devtools-for-tabs
```  

* * *  

## 打开或关闭 F12 键盘快捷方式  

若要更改 `F12` 打开 DevTools 的键盘快捷方式设置，请完成以下操作。  

1.  Choose the icon the **Settings and more** \ (`...` \) icon > **Settings.**  
1.  在 **搜索设置中**，输入 `Developer Tools` 。  
    
    :::image type="complex" source="../media/settings-developer-tools-f12-on.msft.png" alt-text="按 F12 键时打开 DevTools 设置" lightbox="../media/settings-developer-tools-f12-on.msft.png":::
       按 **F12 键时打开 DevTools** 设置  
    :::image-end:::  
    
1.  选择 **"按 F12 键时打开 DevTools"** 以将设置切换为关闭 \ (或打开\) 。  将设置切换为关闭以停止 `F12` 键盘快捷方式打开 DevTools。  
    
    :::image type="complex" source="../media/settings-developer-tools-f12-off.msft.png" alt-text="按下 F12 键时打开 DevTools 设置" lightbox="../media/settings-developer-tools-f12-off.msft.png":::
       按下 **F12 键时打开 DevTools** 设置  
    :::image-end:::  
    
1.  将切换设置为关闭后，选择以确认 `F12` DevTools 不再打开。  
    
    > [!NOTE]
    > 在按下 F12 键设置时关闭"打开 **DevTools"** 设置后，若要打开 DevTools，请完成以下操作之一。  
    > 
    > *   选择 `Ctrl` + `Shift` + `I` 。  
    > *   打开上下文菜单 \ (右键单击\) > **检查**。  
    
## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "控制台概述 | Microsoft Docs"  
[DevtoolsShortcutsIndex]: ../shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式 |Microsoft Docs"  

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
