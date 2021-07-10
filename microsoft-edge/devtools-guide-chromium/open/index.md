---
description: 在 DevTools 中打开 Microsoft Edge的所有方法。
title: 打开 Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/01/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: a6e83d0651c5611b53735447f6ddc34c90550db1
ms.sourcegitcommit: 8f37c931ecde4d58223113f7e3b42d37cc3df97f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2021
ms.locfileid: "11643439"
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
# <a name="open-microsoft-edge-devtools"></a>打开 Microsoft Edge DevTools  

有许多方法可以打开 Microsoft Edge Tools，帮助你快速访问 DevTools UI 的不同部分。 

## <a name="open-microsoft-edge-devtools"></a>打开 Microsoft Edge DevTools  

若要打开 DevTools，请使用以下任一选项。  

*   使用 Microsoft Edge UI。
    *  选择 **"设置更多工具开发人员工具**" (`...` \) 图标>**更多 \> \>**  >   **\\) "** 图标。  
    
*   使用键盘。  
    *   选择 `F12` 或 `Control` + `Shift` + `I` \ (Windows、Linux\) 或 `Command` + `Option` + `I` \ (macOS\) 。  

有关更多信息，请导航至 [Microsoft Edge DevTools 键盘快捷键][DevtoolsShortcutsIndex]。  

:::image type="complex" source="../media/bing-customize-more-tools-developer-tools-transparent.msft.png" alt-text="从主菜单中打开 devTools Microsoft Edge开发人员工具" lightbox="../media/bing-customize-more-tools-developer-tools-transparent.msft.png":::
   从主菜单中打开 devTools Microsoft Edge开发人员工具  
:::image-end:::  

## <a name="open-the-elements-panel-to-inspect-the-dom-or-css"></a>打开"元素"面板以检查 DOM 或 CSS  

通过以下任一任务，您可以检查文档对象模型 [\ (](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) DOM\) 的样式或属性。

*   将鼠标悬停在 元素上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**  
*   选择 `Control` + `Shift` + `C` \(Windows、Linux\) 或 `Command` + `Option` + `C` \(macOS\)。 有关更多信息，请导航至 [Microsoft Edge DevTools 键盘快捷键][DevtoolsShortcutsIndex]。  

<!-- :::image type="complex" source="../media/bing-right-click-inspect.msft.png" alt-text="The Inspect option" lightbox="../media/bing-right-click-inspect.msft.png":::
   The **Inspect** option  
:::image-end:::  --> 

<!--Navigate to [Get Started With Viewing And Changing CSS][GetStartedCSS].  -->  

## <a name="open-the-console-panel"></a>打开控制台面板  

若要打开控制台[面板][DevtoolsConsoleIndex]以查看记录的消息或运行 JavaScript，请选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。 有关更多信息，请导航至 [Microsoft Edge DevTools 键盘快捷键][DevtoolsShortcutsIndex]。  

<!--Navigate to [Get Started With The Console][ConsoleGetStarted].  -->

## <a name="open-the-previous-panel"></a>打开上一个面板  

若要跳转到之前打开的面板，请选择 `Control` + `Shift` + `I` \ (Windows、Linux\) 或 `Command` + `Option` + `I` \ (macOS\) 。  有关更多信息，请导航至 [Microsoft Edge DevTools 键盘快捷键][DevtoolsShortcutsIndex]。  

## <a name="auto-open-devtools-on-every-new-tab"></a>自动打开每个新选项卡上的 DevTools  

若要自动打开每个新选项卡上的 DevTools，Microsoft Edge命令行中打开"开发工具"并传递 `--auto-open-devtools-for-tabs` 标志。  

### [<a name="cmd-windows"></a>CMD (Windows) ](#tab/cmd-Windows/)  

<a id="auto-open-devtools-command-line"></a>  

```cmd
start msedge --auto-open-devtools-for-tabs
```  

### [<a name="powershell-windows"></a>PowerShell (Windows) ](#tab/powershell-Windows/)  

<a id="auto-open-devtools-command-line"></a>  

```powershell
Start-Process -FilePath "msedge" -ArgumentList "--auto-open-devtools-for-tabs"
```  

### [<a name="bash-macos"></a>bash (macOS) ](#tab/bash-macos/)  

<a id="auto-open-devtools-command-line"></a>  

```bash
/Applications/Microsoft\ Edge\ Beta.app/Contents/MacOS/Microsoft\ Edge\ Beta --auto-open-devtools-for-tabs
```  

### [<a name="bash-linux"></a>Bash (Linux) ](#tab/bash-linux/)  

<a id="auto-open-devtools-command-line"></a>  

```bash
microsoft-edge-dev --auto-open-devtools-for-tabs
```  

* * *  

## <a name="toggle-the-f12-keyboard-shortcut-on-or-off"></a>打开或关闭 F12 键盘快捷方式  

若要更改 `F12` 打开 DevTools 的键盘快捷方式设置，请完成以下操作：  

1.  导航到 `edge://settings/system`。  
1.  In `Developer Tools` ， choose Open the **DevTools when the F12 key is pressed** to toggle the setting to off or on. 将设置切换为关闭以停止 `F12` 键盘快捷方式打开 DevTools。  
1.  将开关设置为关闭后，验证 `F12` 是否不再打开 DevTools。  
    
    > [!NOTE]
    > 在关闭按 F12 键时打开 **DevTools**后，执行下列操作之一以打开 DevTools。  
    > 
    > *   选择 `Ctrl` + `Shift` + `I` 。  
    > *   打开上下文菜单 \ (右键单击\) > **检查**。  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleIndex]: ../console/index.md "控制台概述 | Microsoft Docs"  
[DevtoolsShortcutsIndex]: ../shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式 | Microsoft Docs"  

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
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
