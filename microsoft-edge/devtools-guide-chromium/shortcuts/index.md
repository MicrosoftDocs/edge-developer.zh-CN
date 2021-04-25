---
description: Microsoft Edge 开发工具键盘快捷方式的规范文档。
title: Microsoft Edge 开发工具键盘快捷方式
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: c622d529a8008248d57a6b1b0656636a982054c1
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519406"
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

# <a name="microsoft-edge-devtools-keyboard-shortcuts"></a>Microsoft Edge 开发工具键盘快捷方式  

本文引用了 Microsoft Edge 开发工具中的键盘快捷方式。

还可以在工具提示中查找快捷方式。  将鼠标悬停在开发工具的 UI 元素上，以显示工具提示。  如果元素具有快捷方式，则工具提示中将包含快捷方式。

## <a name="keyboard-shortcuts-for-opening-devtools"></a>打开开发工具的键盘快捷方式  

如果要打开开发工具，请在光标聚焦在浏览器视口上时选择以下键盘快捷方式。

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 打开上次使用的窗格 | `F12` 或 `Control`+`Shift`+`I` | `Command`+`Option`+`I` |  
| 打开“**控制台**”工具 | `Control`+`Shift`+`J` | `Command`+`Option`+`J` |  
| 打开“**元素**”工具。 | `Control`+`Shift`+`C` | `Command`+`Shift`+`C` 或 `Command`+`Option`+`C` |  

## <a name="global-keyboard-shortcuts"></a>全局键盘快捷方式  

以下键盘快捷键在大多数（如果不是全部）开发工具窗格中可用。

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 显示“**设置**” | `?` 或 `F1` | `?` 或 `Function`+`F1` |  
| 聚焦于下一窗格 | `Control`+`]` | `Command`+`]` |  
| 聚焦于上一窗格 | `Control`+`[` | `Command`+`[` |  
| 切换回上一次使用的[对接位置][DevtoolsCustomizeIndexPlacement]。  如果开发工具已处于整个会话的默认位置，则此快捷方式将开发工具撤消到单独的窗口中 | `Control`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| 切换[设备仿真][DevtoolsDeviceModeIndex] | `Control`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| 切换**检查元素模式** | `Control`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| 打开“[命令菜单][DevtoolsCommandMenuIndex]”。 | `Control`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| 切换[抽屉][DevtoolsCustomizeIndexDrawer] | `Escape` | `Escape` |  
| 正常刷新 | `F5` 或 `Control`+`R` | `Command`+`R` |  
| 硬刷新 | `Control`+`F5` 或 `Control`+`Shift`+`R` | `Command`+`Shift`+`R` |  
| 在当前窗格中搜索文本。  **审核**、** 应用程序 **和**安全**工具不支持 | `Control`+`F` | `Command`+`F` |  
| 在“[抽屉][DevtoolsCustomizeIndexDrawer]”中打开“**搜索**”选项卡，可以在所有加载的资源中搜索文本 | `Control`+`Shift`+`F` | `Command`+`Option`+`F` |  
| 在"源"工具 **中打开** 文件 | `Control`+`O` 或 `Control`+`P` | `Command`+`O` 或 `Command`+`P` |  
| 放大 | `Control`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| 缩小 | `Control`+`-` | `Command`+`-` |  
| 还原默认缩放级别 | `Control`+`0` | `Command`+`0` |  
| 运行代码片段 | 选择 `Control`+`O` 以打开“[命令菜单][DevtoolsCommandMenuIndex]”，键入 `!`，然后输入脚本名称，然后选择 `Enter` | 选择 `Command`+`O` 以打开“[命令菜单][DevtoolsCommandMenuIndex]”，键入 `!`，然后输入脚本名称，然后选择 `Enter` |  

<!-- TODO: make a bug about this UIPlacement link being ambiguous.  -->  
<!-- TODO: Link "Inspect Element Mode" when a good section exists.  -->  

## <a name="elements-tool-keyboard-shortcuts"></a>元素工具键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 撤消更改 | `Control`+`Z` | `Command`+`Z` |  
| 恢复更改 | `Control`+`Y` | `Command`+`Shift`+`Z` |  
| 选择当前所选元素上方/下方元素 | `Up Arrow` / `Down Arrow` | `Up Arrow` / `Down Arrow` |  
| 展开当前选定的节点。  如果节点已展开，则此快捷方式将选择下方的元素 | `Right Arrow` | `Right Arrow` |  
| 折叠当前选定的节点。  如果节点已折叠，则此快捷方式将选择上方的元素 | `Left Arrow` | `Left Arrow` |  
| 展开或折叠当前选定的节点及所有子节点 | 按住 `Control`+`Alt`，然后选择元素名称旁边的**箭头**图标 | 按住 `Option`，然后选择元素名称旁边的**箭头**图标 |  
| 在当前选定的元素上切换“**编辑属性**”模式 | `Enter` | `Enter` |  
| 进入“**编辑属性**”模式后，选择下一个/上一个属性 | `Tab` / `Shift`+`Tab` | `Tab` / `Shift`+`Tab` |  
| 隐藏当前所选元素 | `H` | `H` |  
| 在当前选定的元素上切换“**编辑为 HTML**”模式 | `Function`+`F2` | `F2` |  

### <a name="styles-panel-keyboard-shortcuts"></a>样式窗格键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 导航属性值已声明的所在行 | 按住 `Control`，然后选择属性值 | 按住 `Command`，然后选择属性值 |  
| 循环显示颜色值的 RBGA、HSLA 和 Hex 表示形式 | 按住 `Shift`，然后选中值旁边的“**颜色预览**”复选框。 | 按住 `Shift`，然后选中值旁边的“**颜色预览**”复选框。 |  
| 选择下一个/上一个属性或值 | 选择属性名称或值，然后选择 `Tab` / `Shift`+`Tab` | 选择属性名称或值，然后选择 `Tab` / `Shift`+`Tab` |  
| 将属性值递增/减 0.1 | 选择一个值，然后选择 `Alt`+`Up Arrow` / `Alt`+`Down Arrow` | 选择值，然后选择 `Option`+`Up Arrow` /选项+向下箭头 |  
| 将属性值递增/减 1 | 选择一个值，然后选择 `Up Arrow` / `Down Arrow` | 选择一个值，然后选择 `Up Arrow` / `Down Arrow` |  
| 将属性值递增/减 10 | 选择一个值，然后选择 `Shift`+`Up Arrow` / `Shift`+`Down Arrow` | 选择一个值，然后选择 `Shift`+`Up Arrow` / `Shift`+`Down Arrow` |  
| 将属性值递增/减 100 | 选择一个值，然后选择 `Control`+`Up Arrow` / `Control`+`Down Arrow` | 选择一个值，然后选择 `Command`+`Up Arrow` / `Command`+`Down Arrow` |  

## <a name="sources-tool-keyboard-shortcuts"></a>源工具键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 暂停脚本运行时 \(如果当前运行\) 或恢复 \(如果当前暂停\) | `F8` 或 `Control`+`\` | `F8` 或 `Command`+`\` |  
| 单步跳过下一函数调用 | `F10` 或 `Control`+`'` | `F10` 或 `Command`+`'` |  
| 单步执行下一函数调用 | `F11` 或 `Control`+`;` | `F11` 或 `Command`+`;` |  
| 跳出当前函数 | `Shift`+`F11` 或 `Control`+`Shift`+`;` | `Shift`+`F11` 或 `Command`+`Shift`+`;` |  
| 暂停时继续至指定的代码行[][DevtoolsJavascriptBreakpointsLOC] | 按住 `Control`，然后选择代码行 | 按住 `Command`，然后选择代码行 |  
| 选择当前所选帧下方/上方的调用帧 | `Control`+`.` / `Control`+`,` | `Control`+`.` / `Control`+`,` |  
| 保存对本地修改的更改 | `Control`+`S` | `Command`+`S` |  
| 保存所有更改 | `Control`+`Alt`+`S` | `Command`+`Option`+`S` |  
| 导航到行 | `Control`+`G` | `Control`+`G` |  
| 跳转到当前打开的文件的行号 | 选择 `Control`+`O` 以打开“[命令菜单][DevtoolsCommandMenuIndex]”，键入 `:`（后跟行号），然后选择 `Enter` | 选择 `Command`+`O` 以打开“[命令菜单][DevtoolsCommandMenuIndex]”，键入 `:`（后跟行号），然后选择 `Enter` |  
| 跳至当前打开文件的列\(例如，第 5 行，列 9\) | 选择 `Control`+`O` 以打开“[命令菜单][DevtoolsCommandMenuIndex]”，键入`:`，然后输入行号，然后输入另一个`:`，然后输入列号，然后选择 `Enter` | 选择 `Command`+`O` 以打开“[命令菜单][DevtoolsCommandMenuIndex]”，键入`:`，然后输入行号，然后输入另一个`:`，然后输入列号，然后选择 `Enter` |  
| 如果当前文件为 HTML 或脚本，则导航到函数声明。  <br />  如果当前文件是样式表，请导航到规则集。  | 选择 `Control`+`Shift`+`O` ，然后键入声明/规则集名称，或者从选项列表中选择 | 选择 `Command`+`Shift`+`O` ，然后键入声明/规则集名称，或者从选项列表中选择 |  
| 关闭活动的选项卡 | `Alt`+`W` | `Option`+`W` |  

### <a name="code-editor-keyboard-shortcuts"></a>代码编辑器键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 删除最后一个词中的所有字符，直到到达光标 | `Control`+`Delete` | `Option`+`Delete` |  
| 添加或删除[代码行断点][DevtoolsJavascriptBreakpointsLOC] | 将光标焦点放在行上，然后选择 `Control`+`B` | 将光标焦点放在行上，然后选择 `Command`+`B` |  
| 导航到匹配的括号 | `Control`+`M` | `Control`+`M` |  
| 切换单行注释。  如果选择了多行，开发工具将注释添加到每行的起始位置 | `Control`+`/` | `Command`+`/` |  
| 打开或关闭下一次出现的任何单词。  每次出现时都同时突出显示 | `Control`+`D` / `Control`+`U` | `Command`+`D` / `Command`+`U` |  

## <a name="performance-tool-keyboard-shortcuts"></a>性能工具键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 开始 /停止录制。 | `Control`+`E` | `Command`+`E` |  
| 保存录制 | `Control`+`S` | `Command`+`S` |  
| 加载录制 | `Control`+`O` | `Command`+`O` |  

## <a name="memory-tool-keyboard-shortcuts"></a>内存工具键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 开始 /停止录制。 | `Control`+`E` | `Command`+`E` |  

## <a name="console-tool-keyboard-shortcuts"></a>控制台工具键盘快捷方式  

| 操作 | Windows\/Linux | macOS |  
|:--- |:--- |:--- |  
| 接受自动完成建议 | `Right Arrow` 或 `Tab` | `Right Arrow` 或 `Tab` |  
| 拒绝自动完成建议 | `Escape` | `Escape` |  
| 获取上一语句 | `Up Arrow` | `Up Arrow` |  
| 获取下一语句 | `Down Arrow` | `Down Arrow` |  
| 聚焦于“**控制台**” | `Control`+ `` ` `` | `Control`+`` ` `` |  
| 清除“**控制台**” | `Control`+`L` | `Command`+`K` 或 `Option`+`L` |  
| 强制多行输入。  该快捷方式通常是不需要的，因为默认情况下，开发工具应该检测多行方案 | `Shift`+`Enter` | `Command`+`Return` |  
| 运行 | `Enter` | `Return` |  
| 展开记录到控制台的对象的所有子属性 | 按住`Alt`，然后选择“**展开**” \(![展开](../media/expand-icon.msft.png)\) | 按住`Alt`，然后选择“**展开**” \(![展开](../media/expand-icon.msft.png)\) |  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsCommandMenuIndex]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行命令 | Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: ../customize/index.md#drawer "设置 - 自定义 Microsoft Edge 开发工具 | Microsoft Docs"  
[DevtoolsCustomizeIndexPlacement]: ../customize/index.md#change-devtools-placement "更改开发工具位置 - 自定义 Microsoft Edge 开发工具 | Microsoft Docs"  
[DevtoolsDeviceModeIndex]: ../device-mode/index.md "在 Microsoft Edge 开发人员工具中模拟移动设备 | Microsoft Docs"  
[DevtoolsJavascriptBreakpointsLOC]: ../javascript/breakpoints.md#line-of-code-breakpoints "代码行断点 - 如何在 Microsoft Edge 开发工具中使用断点暂停代码 | Microsoft Doc"  

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