---
description: Microsoft Edge DevTools 的规范文档键盘快捷方式。
title: Microsoft Edge DevTools 键盘快捷方式
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: d24728f493b70db2db9cd9bbe2e7e7c1ef943885
ms.sourcegitcommit: 080759f68a0a158f10dc20d20c14e222ace1be84
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "11189961"
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

# Microsoft Edge DevTools 键盘快捷方式  

本文是 Microsoft Edge DevTools 中的键盘快捷方式参考。

还可以在工具提示中查找快捷方式。 将鼠标悬停在 DevTools 的 UI 元素上以显示工具提示。 如果元素具有快捷方式，则工具提示将包含该快捷方式。

## 用于打开 DevTools 的键盘快捷方式  

若要打开 DevTools，请在光标焦点位于浏览器视区上时选择以下键盘快捷方式。

| 操作 | Windows \/Linux | macOS |  
|:--- |:--- |:--- |  
| 打开最近使用的任何面板 | `F12` 或 `Control`+`Shift`+`I` | `Command`+`Option`+`I` |  
| 打开 **控制台** 面板 | `Control`+`Shift`+`J` | `Command`+`Option`+`J` |  
| 打开 " **元素** " 面板 | `Control`+`Shift`+`C` | `Command`+`Shift`+`C` 或 `Command`+`Option`+`C` |  

## 全局键盘快捷方式  

以下键盘快捷方式在大多数（如果不是全部） DevTools 面板中可用。

| 操作 | Windows \/Linux | macOS |  
|:--- |:--- |:--- |  
| 显示 **设置** | `?` 或者 `F1` | `?` 或 `Function`+`F1` |  
| 重点关注下一个面板 | `Control`+`]` | `Command`+`]` |  
| 焦点上一个面板 | `Control`+`[` | `Command`+`[` |  
| 切换回上次使用的任何 [插接位置][DevtoolsCustomizeIndexPlacement] 。  如果 DevTools 已处于整个会话的默认位置，此快捷方式会将 DevTools 取消停靠到一个单独的窗口中 | `Control`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| 切换 [设备仿真][DevtoolsDeviceModeIndex] | `Control`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| 切换 **检查元素模式** | `Control`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| 打开 " [命令" 菜单][DevtoolsCommandMenuIndex] | `Control`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| 切换 [抽屉][DevtoolsCustomizeIndexDrawer] | `Escape` | `Escape` |  
| 正常重载 | `F5` 或 `Control`+`R` | `Command`+`R` |  
| 硬重载 | `Control`+`F5` 或 `Control`+`Shift`+`R` | `Command`+`Shift`+`R` |  
| 在当前面板中搜索文本。  在 " **审核**"、" **应用程序**" 和 " **安全** " 面板中不受支持 | `Control`+`F` | `Command`+`F` |  
| 打开[抽屉][DevtoolsCustomizeIndexDrawer]中的 "**搜索**" 选项卡，可让您在所有已加载的资源中搜索文本 | `Control`+`Shift`+`F` | `Command`+`Option`+`F` |  
| 在 " **源** " 面板中打开文件 | `Control`+`O` 或 `Control`+`P` | `Command`+`O` 或 `Command`+`P` |  
| 放大 | `Control`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| 缩小 | `Control`+`-` | `Command`+`-` |  
| 还原默认缩放级别 | `Control`+`0` | `Command`+`0` |  
| 运行代码段 | 选择 `Control` + `O` 以打开 "[命令" 菜单][DevtoolsCommandMenuIndex]， `!` 然后键入脚本的名称，然后选择 `Enter` | 选择 `Command` + `O` 以打开 "[命令" 菜单][DevtoolsCommandMenuIndex]， `!` 然后键入脚本的名称，然后选择 `Enter` |  

<!-- TODO: make a bug about this UIPlacement link being ambiguous.  -->  
<!-- TODO: Link "Inspect Element Mode" when a good section exists.  -->  

## 元素面板键盘快捷方式  

| 操作 | Windows \/Linux | macOS |  
|:--- |:--- |:--- |  
| 撤消更改 | `Control`+`Z` | `Command`+`Z` |  
| 恢复更改 | `Control`+`Y` | `Command`+`Shift`+`Z` |  
| 选择当前所选元素上方/下方的元素 | `Up Arrow` / `Down Arrow` | `Up Arrow` / `Down Arrow` |  
| 展开当前选定的节点。 如果节点已展开，此快捷方式将选择其下方的元素 | `Right Arrow` | `Right Arrow` |  
| 折叠当前选定的节点。 如果节点已折叠，此快捷方式将选择其上方的元素 | `Left Arrow` | `Left Arrow` |  
| 展开或折叠当前所选的节点和所有子节点 | 按住 `Control` + `Alt` ，然后选择元素名称旁边的**箭头**图标 | 按住 `Option` ，然后选择元素名称旁边的 **箭头** 图标 |  
| 切换当前所选元素的 " **编辑属性** " 模式 | `Enter` | `Enter` |  
| 进入 " **编辑属性** " 模式后，选择 "下一个/上一个" 属性 | `Tab` / `Shift`+`Tab` | `Tab` / `Shift`+`Tab` |  
| 隐藏当前选定的元素 | `H` | `H` |  
| 在当前所选元素上将 "编辑" 切换 **为 HTML** 模式 | `Function`+`F2` | `F2` |  

### "样式" 窗格键盘快捷方式  

| 操作 | Windows \/Linux | macOS |  
|:--- |:--- |:--- |  
| 转到声明属性值的行 | 按住 `Control` ，然后选择属性值 | 按住 `Command` ，然后选择属性值 |  
| 循环浏览颜色值的 RBGA、HSLA 和十六进制表示形式 | 按住 `Shift` ，然后选择值旁边的 " **颜色预览** " 框 | 按住 `Shift` ，然后选择值旁边的 " **颜色预览** " 框 |  
| 选择下一个/上一个属性或值 | 选择属性名称或值，然后选择 `Tab` / `Shift`+`Tab` | 选择属性名称或值，然后选择 `Tab` / `Shift`+`Tab` |  
| 递增/递减0.1 的属性值 | 选择一个值，然后选择 `Alt`+`Up Arrow` / `Alt`+`Down Arrow` | 选择一个值，然后选择 `Option` + `Up Arrow` /选项 + 向下键 |  
| 将属性值递增/递减1 | 选择一个值，然后选择 `Up Arrow` / `Down Arrow` | 选择一个值，然后选择 `Up Arrow` / `Down Arrow` |  
| 将属性值递增/递减10 | 选择一个值，然后选择 `Shift`+`Up Arrow` / `Shift`+`Down Arrow` | 选择一个值，然后选择 `Shift`+`Up Arrow` / `Shift`+`Down Arrow` |  
| 递增/递减100的属性值 | 选择一个值，然后选择 `Control`+`Up Arrow` / `Control`+`Down Arrow` | 选择一个值，然后选择 `Command`+`Up Arrow` / `Command`+`Down Arrow` |  

## "源" 面板键盘快捷方式  

| 操作 | Windows \/Linux | macOS |  
|:--- |:--- |:--- |  
| 暂停脚本运行时 \ (如果当前正在运行 \ ) 或恢复 \ (（如果当前已暂停 \ ) ） | `F8` 或 `Control`+`\` | `F8` 或 `Command`+`\` |  
| 跳过下一个函数调用 | `F10` 或 `Control`+`'` | `F10` 或 `Command`+`'` |  
| 单步执行下一个函数调用 | `F11` 或 `Control`+`;` | `F11` 或 `Command`+`;` |  
| 跳出当前函数 | `Shift`+`F11` 或 `Control`+`Shift`+`;` | `Shift`+`F11` 或 `Command`+`Shift`+`;` |  
| [在暂停时继续执行特定代码行][DevtoolsJavascriptBreakpointsLOC] | 按住 `Control` ，然后选择代码行 | 按住 `Command` ，然后选择代码行 |  
| 选择当前所选帧下方/上方的 "呼叫" 框 | `Control`+`.` / `Control`+`,` | `Control`+`.` / `Control`+`,` |  
| 将更改保存到本地修改 | `Control`+`S` | `Command`+`S` |  
| 保存所有更改 | `Control`+`Alt`+`S` | `Command`+`Option`+`S` |  
| 转到行 | `Control`+`G` | `Control`+`G` |  
| 跳转到当前打开的文件的行号 | 选择 `Control` + `O` 以打开 "[命令" 菜单][DevtoolsCommandMenuIndex]， `:` 然后键入 "行号"，然后依次选择 `Enter` | 选择 `Command` + `O` 以打开 "[命令" 菜单][DevtoolsCommandMenuIndex]， `:` 然后键入 "行号"，然后依次选择 `Enter` |  
| 跳转到当前打开的文件的列 \ (（例如第5行、第9列） )  | 选择 `Control` + `O` 以打开 "[命令" 菜单][DevtoolsCommandMenuIndex]， `:` 然后依次单击 "行号"、"行号" 和 `:` "列号"，然后选择 `Enter` | 选择 `Command` + `O` 以打开 "[命令" 菜单][DevtoolsCommandMenuIndex]， `:` 然后依次单击 "行号"、"行号" 和 `:` "列号"，然后选择 `Enter` |  
| 如果当前文件是 HTML 或脚本，请转到函数声明。 <br /> 转到规则集（如果当前文件是样式表）。 | 选择 `Control` + `Shift` + `O` ，然后键入声明/规则集的名称，或从选项列表中选择它。 | 选择 `Command` + `Shift` + `O` ，然后键入声明/规则集的名称，或从选项列表中选择它。 |  
| 关闭活动选项卡 | `Alt`+`W` | `Option`+`W` |  

### 代码编辑器键盘快捷方式  

| 操作 | Windows \/Linux | macOS |  
|:--- |:--- |:--- |  
| 删除最后一个单词中的所有字符，直至光标 | `Control`+`Delete` | `Option`+`Delete` |  
| 添加或删除 [代码行断点][DevtoolsJavascriptBreakpointsLOC] | 将光标聚焦在行上，然后选择 `Control`+`B` | 将光标聚焦在行上，然后选择 `Command`+`B` |  
| 转到匹配的括号 | `Control`+`M` | `Control`+`M` |  
| 切换单行注释。 如果选择了多行，DevTools 将注释添加到每一行的开头 | `Control`+`/` | `Command`+`/` |  
| 选择/取消选中光标所在的任何单词的下一个匹配项。 同时突出显示每个匹配项 | `Control`+`D` / `Control`+`U` | `Command`+`D` / `Command`+`U` |  

## 性能面板键盘快捷方式  

| 操作 | Windows \/Linux | macOS |  
|:--- |:--- |:--- |  
| 开始/停止录制 | `Control`+`E` | `Command`+`E` |  
| 保存录制 | `Control`+`S` | `Command`+`S` |  
| 加载录制 | `Control`+`O` | `Command`+`O` |  

## 内存面板键盘快捷方式  

| 操作 | Windows \/Linux | macOS |  
|:--- |:--- |:--- |  
| 开始/停止录制 | `Control`+`E` | `Command`+`E` |  

## 控制台面板键盘快捷方式  

| 操作 | Windows \/Linux | macOS |  
|:--- |:--- |:--- |  
| 接受 "自动完成" 建议 | `Right Arrow` 或者 `Tab` | `Right Arrow` 或者 `Tab` |  
| 拒绝 "自动完成" 建议 | `Escape` | `Escape` |  
| 获取上一语句 | `Up Arrow` | `Up Arrow` |  
| 获取下一条语句 | `Down Arrow` | `Down Arrow` |  
| 专注于 **控制台** | `Control`+ `` ` `` | `Control`+`` ` `` |  
| 清除 **控制台** | `Control`+`L` | `Command`+`K` 或 `Option`+`L` |  
| 强制执行多行输入。  此快捷方式主要是不必要的，因为 DevTools 默认情况下应检测多行方案 | `Shift`+`Enter` | `Command`+`Return` |  
| 运行 | `Enter` | `Return` |  
| 展开已记录到控制台的对象的所有子属性 | 按住 `Alt` ，然后选择 **展开** \ (![ 展开 ][ImageExpandIcon] \ )  | 按住 `Alt` ，然后选择 **展开** \ (![ 展开 ][ImageExpandIcon] \ )  |  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageExpandIcon]: ./media/expand-icon.msft.png  

<!-- links -->  

[DevtoolsCommandMenuIndex]: ./command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  
[DevtoolsCustomizeIndexDrawer]: ./customize/index.md#drawer "抽屉-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsCustomizeIndexPlacement]: ./customize/index.md#change-devtools-placement "更改 DevTools 放置-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsDeviceModeIndex]: ./device-mode/index.md "在 Microsoft Edge DevTools 中模拟移动设备 |Microsoft 文档"  
[DevtoolsJavascriptBreakpointsLOC]: ./javascript/breakpoints.md#line-of-code-breakpoints "代码行断点-如何在 Microsoft Edge DevTools 中暂停代码和断点 |Microsoft 文档"  

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