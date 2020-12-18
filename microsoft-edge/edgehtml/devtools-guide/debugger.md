---
description: 使用调试器逐步调试代码并排除故障。
title: 'Debugger - DevTools (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 调试程序， 调试， 断点， 监视程序， 服务工作者， 缓存 api， Web 存储， Cookie
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cc2d7ef0d3ee5c16b8cbc73745a8f9ea30bd9d09
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232732"
---
# Debugger - DevTools (EdgeHTML) 

使用 **调试器** 逐步调试代码、设置监视和断点、实时编辑代码并检查缓存。 测试代码并排除故障，方法为：

- [从](#resource-picker)[加载的](#file-search)源文件浏览和搜索代码
- [在逐步执行](#toolbar) 代码时控制执行流
- [管理页面存储资源](./storage.md#cache-manager)，包括[服务工作者和缓存](./service-workers.md)[、Cookie](./storage.md#cookies-list)和[Web 存储](./storage.md#local-and-session-storage-managers)  
- [在代码运行时设置](#debug-window) 断点并实时编辑代码
- [调试时跟踪和编辑](#watches) 本地变量
- [根据需要隐藏或显示](#call-stack) 调用代码中的异步代码和库代码
- [为](#breakpoints) XmlHttpRequests、事件和 DOM 威胁添加 [专门的断点](#dom-breakpoints)

![Microsoft Edge DevTools 调试器](./media/debugger.png)

有三种方法可以开始调试会话。

1. **设置断点。** 当代码执行完成时，你将进入调试程序，并能够逐步调试代码。
2. **在代码中启动中断。** 单击 [**工具栏按钮**](#toolbar) 或 * (的* ") "暂停图标 `Ctrl+Shift+B` 。 调试程序将在下一个执行语句上中断。
3. **设置异常行为。** 使用 [**"更改异常**](#toolbar) 行为" () 代码引发异常时中断 `Ctrl+Shift+E` 调试程序。 默认情况下，调试器设置为"从不 *中断异常*"，但它们将记录到控制台。

## 资源选取器

通常，调试的第一步是在代码中设置要排除故障的断点。 You can find all the code files currently loaded by the page from the *Resource picker* pane， including *.html， .css* and *.js* files.

 单击文件条目将在调试窗口中打开该文件的选项卡，并加粗[](#debug-window)文件名的文本以指示 (*开发人员*指南文件名如上图所示) 。 然后，可以从调试窗口设置该文件中的 [断点](#debug-window)。

![调试器资源选取器](./media/debugger_resource_picker.png)

从资源*选取*器上下文菜单中，还可以将文件标记为库代码** (**) ，从而可以选择在调试器中跳过该代码，然后从调用堆栈窗格中隐藏它 `Ctrl+L` 。 [ **** ](#call-stack) [](#debug-window) 单击 (或) 将文件切换回以前的值 `Ctrl+L` 作为 *我的代码* 或 *库代码*。

### 文件搜索

当您*在*源中尝试查找 () 字符串时，请使用"在文件中查找"命令) 命令 `Ctrl` + `Shift` + `F` 。 工具栏提供不同的搜索选项，包括正则表达式。 单击搜索结果将 *焦点在指定的* 文件和行上的调试窗口。

![调试器文件搜索窗格](./media/debugger_file_search.png)

## 调试窗口

调试 *窗口* 是设置断点、逐步调试代码和在调试时实时编辑脚本的位置。 单击任何脚本命令的左侧以添加 (或删除) **断点**。 使用右键单击上下文菜单或断[****](#breakpoints)点窗格，通过提供** 逻辑表达式将条件添加到断点，该逻辑表达式会导致调试程序在该位置计算*True*时中断。

![调试窗口命令](./media/debugger_window.png)

调试窗口的其他功能包括以下控件：

### 1. 代码编辑

可以在调试会话期间编辑 JavaScript 实时。 进行更改后，单击"保存 () 代码部分下次运行时 <strong> </strong> `Ctrl+S` 测试所做的更改。 如果更改了未保存的代码，则 (\*) 将在"调试"窗口选项卡中的文件名之前 *显示* 星号。

单击 **"比较文档与原始文档"** 按钮以查看您更改的内容的差异。

![调试器中已编辑代码的差异视图](./media/debugger_edit_code.png)

请注意以下约束：

- 脚本编辑仅适用于外部 *.js*文件 (而未嵌入 `<script>` *.html) *
- 编辑保存在内存中，在重新加载文档时刷新，因此无法运行处理程序中的编辑， `DOMContentLoaded` 例如
- 目前，无法 ("另存为"选项) 从**** DevTools 将编辑保存到磁盘

### 2. 代码格式

使用这些控件设置缩小代码的格式，以在调试时提高可读性：

#### 非常 `Ctrl+Shift+P` ()  
根据 JavaScript 约定添加换行符和花括号对齐方式。 即使通过此选项使压缩代码更具可读性，也可能具有与原始源代码中大为不同的函数、选择器和变量名称。 在这些情况下，切换 [*源映射选项*](#source-maps) 可能可用。

#### Word 自动换 `Alt+W` () 
调整代码以适应调试窗口的当前边距 (无需水平滚动) 。

### 3. 代码范围

你可以指示调试器忽略某些文件，将标记为库代码**** () `Ctrl+L` 按钮。 默认情况下，"仅调试[**我的**](#toolbar)代码工具栏"按钮打开，这意味着调试程序将跳过标记为库代码的任何文件，并且这些文件不会显示在** 调试程序调用[堆栈中](#call-stack)。 将按钮标记为 (代码 **时，) ** `Ctrl+L` 将删除此标志。

若要跨调试会话跟踪库，可以编辑这些文件以维护默认列表或为域或文件类型添加通配符：

```JavaScript
%APPDATA%\..\LocalLow\Microsoft\F12\header\MyCode.json and %APPDATA%\..\Local\Microsoft\F12\header\MyCode.json
```

#### 源映射

你将看到为用编译为 JavaScript 或 CSS 的语言编写的代码启用**切换**源映射按钮，该按钮提供源** 映射 (到原始源文件的中间) 。 此选项指示调试程序显示要用于调试 (而不是实际在浏览器中运行的已编译) 。 **

DevTools 将检查生成 JavaScript 文件的编译器是否包含包含地图文件名的注释。 例如，如果编译器将myfile.js压缩*myfile.min.js，它*也可能生成映射文件*myfile.min.js.map，* 并包含压缩文件中的注释，如下所示： **

```JavaScript
//# sourceMappingURL=myfile.min.js.map
```

![调试文件选项卡上下文菜单](./media/debug_file_contextmenu.png)

如果 DevTools 无法自动查找地图，你可以选择该文件的源映射。 右键单击文件的选项卡以查找 **"选择源映射"** 选项。 

## 工具栏

使用调试器 *工具栏* 控制如何逐步执行代码，以及要逐步执行或忽略的代码。 在此处，还可以跨代码文件对特定字符串执行全文搜索。

![调试器工具栏](./media/debugger_toolbar.png)

### 1. `F5` () / () `Ctrl+Shift+B`
 **继续** `F5` () 代码执行到下一个断点。 按住 `F5` 将反复移动过去中断，直到释放它。 

 **中断** () 运行下一 `Ctrl+Shift+B` 个语句后将中断调试器。

### 2. 步骤函数 (`F11` `Ctrl+F10` 、) `Shift+F11`
 **进入 () ** `F11` 调用的函数的步骤。 

 **逐步 () ** `Ctrl+F10` 调用的函数的步骤。 

 **退出** `Shift+F11` () 退出当前函数并进入调用函数。 

 如果使用这些命令时，调试程序将逐一执行下一语句（如果它不在函数中）。

### 3. 中断新工作线程 `Ctrl+Shift+W` () 
 在新建 Web 工作线程时 [中断](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers)。

### 4. 异常控件
**更改异常 () ** 打开选项以更改调试程序对异常 `Ctrl+Shift+E` 的反应。 默认情况下，调试程序将忽略异常并记录到 [**控制台**](./console.md)。 您可以选择中断所有异常**，或者仅中断代码中的语句未处理的异常 (未处理的异常中断 `try...catch`) 。 **

### 5. 查看搜索结果
 (禁用 **。) /隐藏** 结果切换"在文件 [*搜索结果中查找"*](#6-find-in-files-ctrlf) 的显示。

### 6. 在文件 `Ctrl+F` () 
 **在文件 () ** 在资源选取器中所有加载的文件中运行文本 `Ctrl+F` [*搜索*](#resource-picker)。 如果找到该文本，它将打开与搜索字符串匹配的第一个文件。 按 `Enter` 或 `F3` 带你进行下一个匹配。

### 7. 仅调试我的 `Ctrl+J` () 
 **调试我的代码 () **充当切换，以包含或排除在调试器中步骤中标记为库代码 `Ctrl+J` 的所有文件。 [](#3-code-scoping)

### 8. 调试器连接
**Disconnect/Connect 调试器** 实质上是调试器开/关开关。

## Watches

使用 **监视** 窗格浏览所有对象和变量的目录 (局部变量 **) （** 在本地和全局范围内）可用于作为调试器中当前中断焦点的语句。

![监视窗格](./media/debugger_watches.png)

您可以通过添加监视 (**添加**监视 、) 和通过双击它或从上下文菜单中选择编辑值来修改任何可编辑的值来跟踪特定变量的进入和超出范围的值 `Ctrl+W` 。 **** ** 使用"删除**** () / `Ctrl+D` **删除所有**按钮或从上下文菜单中清除监视。 

## 详细信息

"*详细信息*"窗格包括[**"Callstack"**](#call-stack)[**选项卡、"断点**](#breakpoints)"和[**"DOM 断点"**](#dom-breakpoints)选项卡。

### 调用堆栈

" **调用堆栈** "选项卡显示导致当前执行点的函数链。 当前函数显示在顶部，调用函数以相反顺序显示在它下方。

![调用堆栈窗格](./media/debugger_callstack.png)

" **显示/隐藏库框架** `Ctrl+Shift+J` " () 切换调用堆栈 [中的](#3-code-scoping) 库代码输出。 使用"库**代码**" () 从右键单击的"上下文"菜单中将 (或取消标记) 框架的源作为 `Ctrl+L` 库代码。 ** 

" **显示/隐藏异步帧** "按钮切换异步函数调用的根目录的显示。

### 断点

从 **断点** 选项卡中，可以管理断点和事件跟踪点，包括设置条件、禁用和删除它们。

![断点选项卡](./media/debugger_breakpoints.png)

下面汇总了可用于调试的不同类型的断点。

断点类型 | 描述 | 如何设置
:------------ | :------------ | :--------
**断点** | 在执行指定的代码行之前，中断调试程序。 如果每行有一个语句，则最易于设置常规断点。 | 在 ["调试"](#debug-window)窗口中，单击代码中任何行号旁边的左边距。 将出现一个红点，并设置断点。 可以通过单击其蓝色文本跳转到任何断点的源。
**条件断点** | 如果指定条件计算结果为 *true，* 则中断。 这实质上 `if(condition)`  是一个中断调试程序。  | 从断[点选项卡中](#breakpoints)，将鼠标悬停在现有断点上，然后单击"铅笔"按钮 (向此断点 *) *添加条件，右键单击现有断点，然后从上下文菜单中选择"条件 **..."。** 指定要计算在断点位置的"if"条件。 
**XMLHttpRequest 断点 (/** 可选条件)  | 只要满足 XHR 请求 (XMLHttpRequest) 就会中断。 可以从监视窗格中检查 XHR `response` 对象[****](#watches)。 | 在 [断点](#breakpoints) 选项卡上，单击 *XMLHttpRequest* 断点按钮 (带向上/向下箭头的) 。 你可以将其转换为条件 *断点* ，如上所述。
**事件跟踪点** | 使用 [`console.log()`](./console/console-api.md#logging-custom-messages) 指定字符串调用以响应特定事件。 将其用于不想直接保存在事件处理程序代码中的临时控制台日志记录语句。 | 在断 [点](#breakpoints) 选项卡上，单击事件 *跟踪点* 按钮 (带闪电形的菱形) 。 选择 **触发器** 的事件类型和 **用于日志记录的 Trace** 语句。
**事件断** 点 (/可选条件)  | 每当触发指定事件时中断。 | 在"[断点](#breakpoints)"选项卡上，单击**"事件断点"按钮 (带闪电状) 。 选择 **触发器** 的事件类型，也可以选择指定 **Condition** 语句。 
**DOM 断点** | 每当页面上的指定元素被更改时（例如，修改其子树、更改其属性或从 DOM 分离时）就会中断。 | 从" [元素](./elements/dom-breakpoints.md) "选项卡中，右键单击源元素，然后从 *DOM 断点选项* 中进行选择。 使用调试器面板或元素面板中的[**DOM**](#dom-breakpoints)断点** 选项卡管理断点。 ** 

当条件断点和跟踪点进入调试程序时，它们有权访问当前范围内的所有本地和全局变量。

### DOM 断点

从 DOM 断点选项卡管理 **DOM** 分解断点，包括禁用、删除和重新绑定它们。  [可以从"元素](./elements/dom-breakpoints.md) "面板中的 *HTML 树视图* 设置 DOM **断点** 。

![DOM 断点选项卡](./media/debugger_dom_breakpoints.png)

调试 *器中的 DOM* 断点 **选项卡为"** 元素"面板上的 *DOM*断点 * 选项卡 **提供等效** 功能。

下面详细了解不同类型的 [DOM 断点](./elements/dom-breakpoints.md)。

## 快捷方式

### 工具栏快捷方式

操作 | 快捷方式
:------------ | :-------------
查找 | `Ctrl` + `F`
继续 (断点)  | `F5` 或者 `F8`
快速继续 | 保留 `F5` 或 `F8`
继续并刷新 | `Ctrl` + `Shift` + `F5`
中断 | `Ctrl` + `Shift` + `B`
进入 | `F11`
逐步执行 | `F10`
退出 | `Shift` + `F11`
中断新工作线程 | `Ctrl` + `Shift` + `W`
打开菜单 (更改异常)  | `Ctrl` + `Shift` + `E`
仅调试我的代码 | `Ctrl` + `J`

### 资源选取器快捷方式

操作 | 快捷方式
:------------ | :-------------
标记为我的代码/库代码 | `Ctrl` + `L`
打开文件 | `Ctrl` + `O`, `Ctrl` + `P`
搜索所有文件 | `Ctrl` + `Shift` + `F`

### 调试窗口快捷方式

操作 | 快捷方式
:------------ | :-------------
删除断点 | `F9`
禁用断点 | `Ctrl` + `F9`
条件断点... | `Alt` + `F9`
复制 | `Ctrl` + `C`
保存 | `Ctrl` + `S`
转到行... | `Ctrl` + `G`
显示下一个语句 | `Alt` + `Num` + `*`
运行到光标 | `Ctrl` + `F10`
设置下一个语句 | `Ctrl` + `Shift` + `F10`
在文件选取器中显示 | `Ctrl` + `Alt` + `P`
转到文件中的定义 | `Ctrl`+`D`
在文件中查找引用 | `Ctrl` + `Shift` + `D`
非常的打印 | `Ctrl` + `Shift` + `P`
Word 自动换行 | `Alt` + `W`
标记为我的代码/库代码 | `Ctrl` + `L`
在编辑器中禁用/启用选项卡。 **注意** ：如果使用键盘在调试器中导航，则除非禁用 Tabbing，才能从编辑器中退出 | `Ctrl` + `M`

### "监视"窗格的快捷方式

操作 | 快捷方式
:------------ | :-------------
添加监视 | `Ctrl` + `W`
删除监视 | `Ctrl` + `D`

### "详细信息"窗格的快捷方式

| 操作                             | 快捷方式                 |
|:-----------------------------------|:-------------------------|
| 显示/隐藏库代码中的帧 | `Ctrl` + `Shift` + `J`   |
| 启用所有断点             | `Ctrl` + `Shift` + `F11` |
