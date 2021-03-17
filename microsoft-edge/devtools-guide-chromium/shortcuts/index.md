---
description: Microsoft Edge DevTools 键盘快捷方式的规范文档。
title: Microsoft Edge DevTools 键盘快捷方式
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 8197157c3024374e11db71f919cc937fed2e6b1b
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439589"
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
   limitations under the License.  -->

# <a name="microsoft-edge-devtools-keyboard-shortcuts"></a>Microsoft Edge DevTools 键盘快捷方式  

本文引用了 Microsoft Edge DevTools 中的键盘快捷方式。

还可以在工具提示中查找快捷方式。  将鼠标悬停在 DevTools 的 UI 元素上，以显示工具提示。  如果元素具有快捷方式，则工具提示会包含该快捷方式。

## <a name="keyboard-shortcuts-for-opening-devtools"></a>用于打开 DevTools 的键盘快捷方式  

若要打开 DevTools，请在光标聚焦在浏览器视口上时选择以下键盘快捷方式。

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 打开上次使用的任何面板 | `F12` 或 `Control`+`Shift`+`I` | `Command`+`Option`+`I` |  
| 打开 **控制台** 工具 | `Control`+`Shift`+`J` | `Command`+`Option`+`J` |  
| 打开 **"元素"** 工具 | `Control`+`Shift`+`C` | `Command`+`Shift`+`C` 或 `Command`+`Option`+`C` |  

## <a name="global-keyboard-shortcuts"></a>全局键盘快捷方式  

大多数（如果不是全部）DevTools 面板中都提供以下键盘快捷方式。

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 显示 **设置** | `?` or `F1` | `?` 或 `Function`+`F1` |  
| 焦点下一个面板 | `Control`+`]` | `Command`+`]` |  
| 焦点上一个面板 | `Control`+`[` | `Command`+`[` |  
| 切换回上次 [使用的任何][DevtoolsCustomizeIndexPlacement] 固定位置。  如果 DevTools 已处于整个会话的默认位置，则此快捷方式将 DevTools 撤消到单独的窗口中 | `Control`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| 切换 [设备仿真][DevtoolsDeviceModeIndex] | `Control`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| 切换 **检查元素模式** | `Control`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| 打开 [命令菜单][DevtoolsCommandMenuIndex] | `Control`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| 切换 [箱][DevtoolsCustomizeIndexDrawer] | `Escape` | `Escape` |  
| 正常刷新 | `F5` 或 `Control`+`R` | `Command`+`R` |  
| 硬刷新 | `Control`+`F5` 或 `Control`+`Shift`+`R` | `Command`+`Shift`+`R` |  
| 在当前面板中搜索文本。  在审核 **、应用程序****和安全工具**中**不受**支持 | `Control`+`F` | `Command`+`F` |  
| 在 **"箱"**[中打开][DevtoolsCustomizeIndexDrawer]"搜索"选项卡，可让你搜索所有已加载资源中的文本 | `Control`+`Shift`+`F` | `Command`+`Option`+`F` |  
| 在"源"面板 **中打开** 文件 | `Control`+`O` 或 `Control`+`P` | `Command`+`O` 或 `Command`+`P` |  
| 放大 | `Control`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| 缩小 | `Control`+`-` | `Command`+`-` |  
| 还原默认缩放级别 | `Control`+`0` | `Command`+`0` |  
| 运行代码段 | 选择 `Control` + `O` 打开命令[菜单][DevtoolsCommandMenuIndex]，键入后 `!` 跟脚本名称，然后选择 `Enter` | 选择 `Command` + `O` 打开命令[菜单][DevtoolsCommandMenuIndex]，键入后 `!` 跟脚本名称，然后选择 `Enter` |  

<!-- TODO: make a bug about this UIPlacement link being ambiguous.  -->  
<!-- TODO: Link "Inspect Element Mode" when a good section exists.  -->  

## <a name="elements-tool-keyboard-shortcuts"></a>元素工具键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 撤消更改 | `Control`+`Z` | `Command`+`Z` |  
| 恢复更改 | `Control`+`Y` | `Command`+`Shift`+`Z` |  
| 选择当前选定元素上方/下方的元素 | `Up Arrow` / `Down Arrow` | `Up Arrow` / `Down Arrow` |  
| 展开当前选定的节点。  如果节点已展开，则此快捷方式选择它下面的元素 | `Right Arrow` | `Right Arrow` |  
| 折叠当前选定的节点。  如果节点已折叠，则此快捷方式选择其上方的元素 | `Left Arrow` | `Left Arrow` |  
| 展开或折叠当前选定的节点及其所有子节点 | 保留 `Control` + `Alt` ，然后选择**元素**名称旁边的箭头图标 | 保留 `Option` ，然后选择 **元素** 名称旁边的箭头图标 |  
| 切换 **当前** 选定元素上的编辑属性模式 | `Enter` | `Enter` |  
| 在进入编辑属性模式后选择下 **一个/上一** 个属性 | `Tab` / `Shift`+`Tab` | `Tab` / `Shift`+`Tab` |  
| 隐藏当前选定的元素 | `H` | `H` |  
| 切换 **当前选定元素上的"** 编辑为 HTML 模式" | `Function`+`F2` | `F2` |  

### <a name="styles-panel-keyboard-shortcuts"></a>样式面板键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 导航到声明属性值的行 | 保留 `Control` ，然后选择属性值 | 保留 `Command` ，然后选择属性值 |  
| 循环使用颜色值的 RBGA、HSLA 和 Hex 表示形式 | 保留 `Shift` ，然后选择值 **旁边的"颜色** 预览"框 | 保留 `Shift` ，然后选择值 **旁边的"颜色** 预览"框 |  
| 选择下一个/上一个属性或值 | 选择属性名称或值，然后选择 `Tab` / `Shift`+`Tab` | 选择属性名称或值，然后选择 `Tab` / `Shift`+`Tab` |  
| 将属性值递增/减 0.1 | 选择值，然后选择 `Alt`+`Up Arrow` / `Alt`+`Down Arrow` | 选择值，然后选择 `Option` + `Up Arrow` /选项+向下箭头 |  
| 将属性值递增/减 1 | 选择值，然后选择 `Up Arrow` / `Down Arrow` | 选择值，然后选择 `Up Arrow` / `Down Arrow` |  
| 将属性值递增/减 10 | 选择值，然后选择 `Shift`+`Up Arrow` / `Shift`+`Down Arrow` | 选择值，然后选择 `Shift`+`Up Arrow` / `Shift`+`Down Arrow` |  
| 将属性值递增/减 100 | 选择值，然后选择 `Control`+`Up Arrow` / `Control`+`Down Arrow` | 选择值，然后选择 `Command`+`Up Arrow` / `Command`+`Down Arrow` |  

## <a name="sources-tool-keyboard-shortcuts"></a>源工具键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 如果当前正在运行\ (，请暂停脚本运行时 \) 如果当前已暂停 (请恢复 \)  | `F8` 或 `Control`+`\` | `F8` 或 `Command`+`\` |  
| 逐一执行下一个函数调用 | `F10` 或 `Control`+`'` | `F10` 或 `Command`+`'` |  
| 进入下一个函数调用 | `F11` 或 `Control`+`;` | `F11` 或 `Command`+`;` |  
| 退出当前函数 | `Shift`+`F11` 或 `Control`+`Shift`+`;` | `Shift`+`F11` 或 `Command`+`Shift`+`;` |  
| 在暂停 [时继续执行特定代码行][DevtoolsJavascriptBreakpointsLOC] | 保留 `Control` ，然后选择代码行 | 保留 `Command` ，然后选择代码行 |  
| Select the call frame below / above the currently selected frame | `Control`+`.` / `Control`+`,` | `Control`+`.` / `Control`+`,` |  
| 保存对本地修改的更改 | `Control`+`S` | `Command`+`S` |  
| 保存所有更改 | `Control`+`Alt`+`S` | `Command`+`Option`+`S` |  
| 导航到行 | `Control`+`G` | `Control`+`G` |  
| 跳转到当前打开的文件的行号 | 选择 `Control` + `O` 以打开命令[菜单][DevtoolsCommandMenuIndex]，键入 `:` 后跟行号，然后选择 `Enter` | 选择 `Command` + `O` 以打开命令[菜单][DevtoolsCommandMenuIndex]，键入 `:` 后跟行号，然后选择 `Enter` |  
| 跳转到当前打开的文件 \ (，例如第 5 行，列 9\)  | Select `Control` + `O` to open the [Command Menu][DevtoolsCommandMenuIndex]， type `:` ， then the line number， then another `:` ， then the column number， then select `Enter` | Select `Command` + `O` to open the [Command Menu][DevtoolsCommandMenuIndex]， type `:` ， then the line number， then another `:` ， then the column number， then select `Enter` |  
| 如果当前文件是 HTML 或脚本，则导航到函数声明。  <br />  导航到规则集，如果当前文件是样式表。  | 选择 `Control` + `Shift` + `O` ，然后键入声明/规则集名称，或者从选项列表中选择它 | 选择 `Command` + `Shift` + `O` ，然后键入声明/规则集名称，或者从选项列表中选择它 |  
| 关闭活动选项卡 | `Alt`+`W` | `Option`+`W` |  

### <a name="code-editor-keyboard-shortcuts"></a>代码编辑器键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 删除最后一个单词（至光标）的所有字符 | `Control`+`Delete` | `Option`+`Delete` |  
| 添加或删除 [代码行断点][DevtoolsJavascriptBreakpointsLOC] | 将光标聚焦在行上，然后选择 `Control`+`B` | 将光标聚焦在行上，然后选择 `Command`+`B` |  
| 导航到匹配的方括号 | `Control`+`M` | `Control`+`M` |  
| 切换单行批注。  如果选择了多行，DevTools 将注释添加到每行的起始位置 | `Control`+`/` | `Command`+`/` |  
| 打开或关闭光标打开的任何单词的下一个匹配项。  每次出现时都同时突出显示 | `Control`+`D` / `Control`+`U` | `Command`+`D` / `Command`+`U` |  

## <a name="performance-tool-keyboard-shortcuts"></a>性能工具键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 开始/停止录制 | `Control`+`E` | `Command`+`E` |  
| 保存录制 | `Control`+`S` | `Command`+`S` |  
| 加载录制 | `Control`+`O` | `Command`+`O` |  

## <a name="memory-tool-keyboard-shortcuts"></a>内存工具键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 开始/停止录制 | `Control`+`E` | `Command`+`E` |  

## <a name="console-tool-keyboard-shortcuts"></a>控制台工具键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 接受自动完成建议 | `Right Arrow` or `Tab` | `Right Arrow` or `Tab` |  
| 拒绝自动完成建议 | `Escape` | `Escape` |  
| 获取上一语句 | `Up Arrow` | `Up Arrow` |  
| 获取下一个语句 | `Down Arrow` | `Down Arrow` |  
| 焦点控制台**** | `Control`+ `` ` `` | `Control`+`` ` `` |  
| 清除 **控制台** | `Control`+`L` | `Command`+`K` 或 `Option`+`L` |  
| 强制多行输入。  此快捷方式大部分是不必要的，因为默认情况下，DevTools 应检测多行方案 | `Shift`+`Enter` | `Command`+`Return` |  
| 运行 | `Enter` | `Return` |  
| 展开记录到控制台的对象的所有子属性 | 保留 `Alt` ，然后选择展开**** \ (![ 展开 ](../media/expand-icon.msft.png) \)  | 保留 `Alt` ，然后选择展开**** \ (![ 展开 ](../media/expand-icon.msft.png) \)  |  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsCommandMenuIndex]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行|Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: ../customize/index.md#drawer "箱 - 自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsCustomizeIndexPlacement]: ../customize/index.md#change-devtools-placement "更改 DevTools 位置 - 自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsDeviceModeIndex]: ../device-mode/index.md "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsJavascriptBreakpointsLOC]: ../javascript/breakpoints.md#line-of-code-breakpoints "代码行断点 - 如何在 Microsoft Edge DevTools |Microsoft Docs"  

<!--[201705ReleaseNotesContinue]: whats-new/2017/05/devtools-release-notes#continue  -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/shortcuts)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  