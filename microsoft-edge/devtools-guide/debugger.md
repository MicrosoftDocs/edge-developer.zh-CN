---
description: 使用调试程序逐句浏览代码并对代码进行故障排除。
title: DevTools-调试器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、调试器、调试、断点、监视、服务工作人员、缓存 api、web 存储、cookie
ms.custom: seodec18
ms.openlocfilehash: f82fbb057a3ad1027309d89db1a15dbcbea31292
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564307"
---
# <span data-ttu-id="d1b3e-104">调试器</span><span class="sxs-lookup"><span data-stu-id="d1b3e-104">Debugger</span></span>

<span data-ttu-id="d1b3e-105">使用**调试程序**逐句通过代码、设置监视和断点、实时编辑代码和检查缓存。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-105">Use the **Debugger** to step through code, set watches and breakpoints, live edit your code and inspect your caches.</span></span> <span data-ttu-id="d1b3e-106">通过以下方式测试和解决代码问题：</span><span class="sxs-lookup"><span data-stu-id="d1b3e-106">Test and troubleshoot your code by:</span></span>

- <span data-ttu-id="d1b3e-107">[浏览](#resource-picker)和[搜索](#file-search)加载的源文件中的代码</span><span class="sxs-lookup"><span data-stu-id="d1b3e-107">[Browsing](#resource-picker) and [searching](#file-search) code from your loaded source files</span></span>
- <span data-ttu-id="d1b3e-108">逐句通过代码时[控制执行流程](#toolbar)</span><span class="sxs-lookup"><span data-stu-id="d1b3e-108">[Controlling the execution flow](#toolbar) as you step through your code</span></span>
- <span data-ttu-id="d1b3e-109">[管理页面存储资源](./storage.md#cache-manager)，包括[服务工作人员和缓存](./service-workers.md)、 [cookie](./storage.md#cookies-list)和[web 存储](./storage.md#local-and-session-storage-managers)</span><span class="sxs-lookup"><span data-stu-id="d1b3e-109">[Managing page storage resources](./storage.md#cache-manager), including the [service workers and cache](./service-workers.md), [cookies](./storage.md#cookies-list) and [web storage](./storage.md#local-and-session-storage-managers)</span></span>  
- <span data-ttu-id="d1b3e-110">在运行时[设置断点和实时编辑](#debug-window)代码</span><span class="sxs-lookup"><span data-stu-id="d1b3e-110">[Setting breakpoints and live editing](#debug-window) your code as it runs</span></span>
- <span data-ttu-id="d1b3e-111">调试时[跟踪和编辑本地变量](#watches)</span><span class="sxs-lookup"><span data-stu-id="d1b3e-111">[Tracking and editing local variables](#watches) as you debug</span></span>
- <span data-ttu-id="d1b3e-112">根据需要从调用堆栈中[隐藏或显示异步代码和库代码](#call-stack)</span><span class="sxs-lookup"><span data-stu-id="d1b3e-112">[Hiding or showing asynchronous code and library code](#call-stack) from your callstack as needed</span></span>
- <span data-ttu-id="d1b3e-113">为 XmlHttpRequests、事件和 DOM[添加专用断点](#breakpoints) [mutations](#dom-breakpoints)</span><span class="sxs-lookup"><span data-stu-id="d1b3e-113">[Adding specialized breakpoints](#breakpoints) for XmlHttpRequests, events and [DOM mutations](#dom-breakpoints)</span></span>

![Microsoft Edge DevTools 调试器](./media/debugger.png)

<span data-ttu-id="d1b3e-115">可通过三种方式开始调试会话。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-115">There are three ways to begin a debugging session.</span></span>

1. **<span data-ttu-id="d1b3e-116">设置断点。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-116">Set a breakpoint.</span></span>** <span data-ttu-id="d1b3e-117">当代码执行到达时，你将进入调试器，并且能够逐句通过你的代码。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-117">When the execution of your code reaches it, you'll enter the debugger and be able to step through your code.</span></span>
2. **<span data-ttu-id="d1b3e-118">在代码中启动中断。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-118">Initiate a break in code.</span></span>** <span data-ttu-id="d1b3e-119">单击 "[**分隔符**](#toolbar)" （*暂停*图标）工具栏按钮或 `Ctrl+Shift+B` 。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-119">Click the [**Break**](#toolbar) (*pause* icon) toolbar button or `Ctrl+Shift+B`.</span></span> <span data-ttu-id="d1b3e-120">调试器将在下一执行语句中断。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-120">The debugger will break on the next statement of execution.</span></span>
3. **<span data-ttu-id="d1b3e-121">设置异常行为。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-121">Set exception behavior.</span></span>** <span data-ttu-id="d1b3e-122">使用 "[**更改异常行为**](#toolbar)" 菜单（ `Ctrl+Shift+E` ）在代码引发异常时中断到调试器。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-122">Use the [**Change exception behavior**](#toolbar) menu (`Ctrl+Shift+E`) to break into the debugger when your code throws an exception.</span></span> <span data-ttu-id="d1b3e-123">默认情况下，调试器设置为*永不中断异常*，但会将其记录到控制台。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-123">By default, the debugger is set to *Never break on exceptions*, but they are logged to the console.</span></span>

## <span data-ttu-id="d1b3e-124">资源选取器</span><span class="sxs-lookup"><span data-stu-id="d1b3e-124">Resource picker</span></span>

<span data-ttu-id="d1b3e-125">通常，调试的第一步是在要进行疑难解答的代码中设置断点。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-125">Often the first step in debugging is to set breakpoints in the code you're looking to troubleshoot.</span></span> <span data-ttu-id="d1b3e-126">你可以从*资源选取器*窗格（包括 *.html、.css*和 *.js*文件）查找页面上当前加载的所有代码文件。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-126">You can find all the code files currently loaded by the page from the *Resource picker* pane, including *.html, .css* and *.js* files.</span></span>

 <span data-ttu-id="d1b3e-127">单击某个文件条目将在[调试窗口](#debug-window)中打开该文件的一个选项卡，并将文件名的文本加粗，以指示这一点（如上面的插图中的*devtools*文件名）。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-127">Clicking on a file entry will open a tab for that file in the [Debug window](#debug-window) and bold the text of the file name to indicate this (as *devtools-guide* file name is in the illustration above).</span></span> <span data-ttu-id="d1b3e-128">然后，可以从 "[调试" 窗口](#debug-window)在该文件中设置断点。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-128">You can then set breakpoints within that file from the [Debug window](#debug-window).</span></span>

![调试器资源选取器](./media/debugger_resource_picker.png)

<span data-ttu-id="d1b3e-130">从*资源选取器*上下文菜单中，你还可以将文件标记为**库代码**（ `Ctrl+L` ），以便你可以选择在[调试器中跳过该代码](#debug-window)，并将[其从 "**调用堆栈**" 窗格中隐藏](#call-stack)。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-130">From the *Resource picker* context menu, you can also mark a file as **library code** (`Ctrl+L`), giving you the option to [skip over that code in the debugger](#debug-window) and [hide it from the **Call stack** pane](#call-stack).</span></span> <span data-ttu-id="d1b3e-131">再次单击（或 `Ctrl+L` ）会将文件作为*我的代码*或*库代码*切换回原来的值。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-131">Clicking (or `Ctrl+L`) again will toggle the file back to its previous value as *my code* or *library code*.</span></span>

### <span data-ttu-id="d1b3e-132">文件搜索</span><span class="sxs-lookup"><span data-stu-id="d1b3e-132">File search</span></span>

<span data-ttu-id="d1b3e-133">*Find in files* `Ctrl` + `Shift` + `F` 当你有要在源中查找的特定代码字符串时，请使用 "在文件中查找" 命令（）。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-133">Use the *Find in files* command (`Ctrl`+`Shift`+`F`) when you have a specific string of code you're trying to find in the source.</span></span> <span data-ttu-id="d1b3e-134">工具栏提供了不同的搜索选项，包括正则表达式。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-134">The toolbar provides different search options, including regular expressions.</span></span> <span data-ttu-id="d1b3e-135">单击搜索结果会将*调试窗口*重点放在指定的文件和行上。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-135">Clicking on a search result will focus the *Debug window* on the specified file and line.</span></span>

![调试器文件搜索窗格](./media/debugger_file_search.png)

## <span data-ttu-id="d1b3e-137">调试窗口</span><span class="sxs-lookup"><span data-stu-id="d1b3e-137">Debug window</span></span>

<span data-ttu-id="d1b3e-138">"*调试" 窗口*是设置断点、单步执行代码以及在调试时实时编辑脚本的位置。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-138">The *Debug window* is where you set your breakpoints, step through code, and live edit your script as you debug.</span></span> <span data-ttu-id="d1b3e-139">单击任意脚本命令左侧的以添加（或删除）**断点**。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-139">Click to the left of any script command to add (or remove) a **Breakpoint**.</span></span> <span data-ttu-id="d1b3e-140">使用右键单击上下文菜单或 "[**断点**](#breakpoints)" 窗格向断点*添加条件*，方法是提供一个逻辑表达式，该表达式会导致调试程序在该位置计算*True*时中断。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-140">Use the right-click context menu or [**Breakpoints**](#breakpoints) pane to *Add a condition* to the breakpoint by supplying a logical expression that causes the debugger to break if it evaluates *True* at that location.</span></span>

![调试窗口命令](./media/debugger_window.png)

<span data-ttu-id="d1b3e-142">"调试" 窗口的其他功能包括用于以下内容的控件：</span><span class="sxs-lookup"><span data-stu-id="d1b3e-142">Other features of the debug window include controls for:</span></span>

### <span data-ttu-id="d1b3e-143">1. 代码编辑</span><span class="sxs-lookup"><span data-stu-id="d1b3e-143">1. Code editing</span></span>

<span data-ttu-id="d1b3e-144">你可以在调试会话期间编辑 JavaScript live。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-144">You can edit your JavaScript live during a debugging session.</span></span> <span data-ttu-id="d1b3e-145">进行更改后，单击 " <strong> 保存" </strong> （ `Ctrl+S` ）以在下次运行该代码段时测试所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-145">Once you make your changes, click <strong>Save</strong> (`Ctrl+S`) to test your changes next time that section of code runs.</span></span> <span data-ttu-id="d1b3e-146">如果您有未保存的代码更改，则 "*调试窗口*" 选项卡中的文件名前面将显示星号（\ \*）。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-146">If you have unsaved code changes, an asterisk (\*) will appear before the file name in the *Debug window* tab.</span></span>

<span data-ttu-id="d1b3e-147">单击 "**将文档与原始文档比较**" 按钮以查看更改内容的差异。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-147">Click the **Compare document to original** button to view the diff of what you changed.</span></span>

![调试器中编辑代码的比较视图](./media/debugger_edit_code.png)

<span data-ttu-id="d1b3e-149">请注意以下限制：</span><span class="sxs-lookup"><span data-stu-id="d1b3e-149">Please be aware of the following constraints:</span></span>

- <span data-ttu-id="d1b3e-150">脚本编辑仅适用于外部 *.js*文件（而不是嵌入 `<script>` 在 *.html*中）</span><span class="sxs-lookup"><span data-stu-id="d1b3e-150">Script editing only works in external *.js* files (and not embedded `<script>` within *.html*)</span></span>
- <span data-ttu-id="d1b3e-151">编辑保存在内存中，并在重新加载文档时进行刷新，因此你无法在处理程序内运行编辑 `DOMContentLoaded` ，例如</span><span class="sxs-lookup"><span data-stu-id="d1b3e-151">Edits are saved in memory and flushed when the document is reloaded, thus you won't be able to run edits inside a `DOMContentLoaded` handler, for example</span></span>
- <span data-ttu-id="d1b3e-152">目前没有办法（如 "**另存为**" 选项）将您的编辑内容从 DevTools 保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-152">Currently there's no way (such as a **Save As** option) to save your edits to disk from the DevTools</span></span>

### <span data-ttu-id="d1b3e-153">2. 编码格式</span><span class="sxs-lookup"><span data-stu-id="d1b3e-153">2.Code formatting</span></span>

<span data-ttu-id="d1b3e-154">在调试时使用这些控件设置 minified 代码的格式以获得更好的可读性：</span><span class="sxs-lookup"><span data-stu-id="d1b3e-154">Use these controls to format minified code for better readability as you debug:</span></span>

#### <span data-ttu-id="d1b3e-155">整齐打印（ `Ctrl+Shift+P` ）</span><span class="sxs-lookup"><span data-stu-id="d1b3e-155">Pretty print (`Ctrl+Shift+P`)</span></span> 
<span data-ttu-id="d1b3e-156">为每个 JavaScript 约定添加换行符和花括号对齐。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-156">Adds line breaks and curly brace alignment per JavaScript conventions.</span></span> <span data-ttu-id="d1b3e-157">使用此选项使得更易读的压缩代码可能具有与原始源代码不同的函数、选择器和变量名称。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-157">Even compressed code that's been made more readable with this option may have function, selector, and variable names that are much different than in your original source code.</span></span> <span data-ttu-id="d1b3e-158">在这些情况下，"[*切换源地图*](#source-maps)" 选项可能可用。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-158">In these cases, the [*Toggle source maps*](#source-maps) option might be available.</span></span>

#### <span data-ttu-id="d1b3e-159">文字环绕（ `Alt+W` ）</span><span class="sxs-lookup"><span data-stu-id="d1b3e-159">Word wrap (`Alt+W`)</span></span>
<span data-ttu-id="d1b3e-160">调整代码以适合 "调试" 窗口的当前边距（不需要水平滚动）。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-160">Adjusts code to fit within the current margins of the debug window (eliminating the need for horizontal scrolling).</span></span>

### <span data-ttu-id="d1b3e-161">3. 代码范围</span><span class="sxs-lookup"><span data-stu-id="d1b3e-161">3. Code scoping</span></span>

<span data-ttu-id="d1b3e-162">你可以通过 "**标记为库代码**" 按钮指示调试器忽略某些文件 `Ctrl+L` 。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-162">You can direct the debugger to ignore certain files with the **Mark as library code** (`Ctrl+L`) button.</span></span> <span data-ttu-id="d1b3e-163">默认情况下，"[**仅调试**](#toolbar)" 工具栏按钮处于打开状态，这意味着调试器将跳过任何标记为*库代码*的文件，并且它们不会显示在调试器[调用堆栈](#call-stack)中。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-163">By default, the [**Debug just my code**](#toolbar) toolbar button is on, meaning that the debugger will skip over any files that you mark as *library code* and they will not appear in the debugger [call stack](#call-stack).</span></span> <span data-ttu-id="d1b3e-164">按下按钮（"**标记为我的代码**" `Ctrl+L` ）将删除此标志。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-164">Depressing the button (**Mark as my code**, `Ctrl+L`) will remove this flag.</span></span>

<span data-ttu-id="d1b3e-165">为了在调试会话期间保持对库的跟踪，可以编辑这些文件以维护默认列表，或为域或文件类型添加通配符：</span><span class="sxs-lookup"><span data-stu-id="d1b3e-165">For keeping track of libraries across debugging sessions, you can edit these files to maintain a default list or add wildcards for a domain or file type:</span></span>

```JavaScript
%APPDATA%\..\LocalLow\Microsoft\F12\header\MyCode.json and %APPDATA%\..\Local\Microsoft\F12\header\MyCode.json
```

#### <span data-ttu-id="d1b3e-166">源地图</span><span class="sxs-lookup"><span data-stu-id="d1b3e-166">Source maps</span></span>

<span data-ttu-id="d1b3e-167">你将看到 "**切换源映射**" 按钮，该按钮可用于使用编译为 JAVASCRIPT 或 CSS 的语言编写的代码，并提供*源映射*（指向原始源的中间文件映射）。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-167">You will see the **Toggle source maps** button enabled for code written in a language that compiles to JavaScript or CSS and that provides a *source map* (an intermediate file mapping to the original source).</span></span> <span data-ttu-id="d1b3e-168">此选项指示调试器显示用于调试的原始源（而不是在浏览器中*实际*运行的已编译文件）。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-168">This option directs the debugger to present the original source to use for debugging (rather than the compiled file that's *actually* running in the browser).</span></span>

<span data-ttu-id="d1b3e-169">DevTools 将检查生成 JavaScript 文件的编译器是否包含带有地图文件名称的注释。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-169">The DevTools will check if the compiler that generated the JavaScript file included a comment with the name of the map file.</span></span> <span data-ttu-id="d1b3e-170">例如，如果编译器将*myfile*压缩为*myfile*，则它可能还会生成映射文件*myfile*映射，并在压缩文件中包含注释，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1b3e-170">For example, if a compiler compressed *myfile.js* to *myfile.min.js*, it might also generate a map file, *myfile.min.js.map* and include a comment in the compressed file like this:</span></span>

```JavaScript
//# sourceMappingURL=myfile.min.js.map
```

!["调试文件" 选项卡上下文菜单](./media/debug_file_contextmenu.png)

<span data-ttu-id="d1b3e-172">如果 DevTools 无法自动找到地图，则可以选择该文件的源映射。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-172">If the DevTools can't find the map automatically, you can choose a source map for that file.</span></span> <span data-ttu-id="d1b3e-173">右键单击文件的选项卡以查找 "**选择源映射**" 选项。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-173">Right-click the file's tab to find the **Choose source map** option.</span></span> 

## <span data-ttu-id="d1b3e-174">工具栏</span><span class="sxs-lookup"><span data-stu-id="d1b3e-174">Toolbar</span></span>

<span data-ttu-id="d1b3e-175">使用调试器*工具栏*控制逐句通过代码的方式，以及要单步执行或忽略的代码。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-175">Use the debugger *Toolbar* to control how you step through code, and what code to step through or ignore.</span></span> <span data-ttu-id="d1b3e-176">在此，你还可以在代码文件中对特定字符串执行全文搜索。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-176">From here you can also do a full text search across your code files for specific strings.</span></span>

![调试器工具栏](./media/debugger_toolbar.png)

### <span data-ttu-id="d1b3e-178">1. 继续（ `F5` ）/中断（ `Ctrl+Shift+B` ）</span><span class="sxs-lookup"><span data-stu-id="d1b3e-178">1. Continue (`F5`) / Break (`Ctrl+Shift+B`)</span></span>
 <span data-ttu-id="d1b3e-179">**Continue** （ `F5` ）继续向下一个断点执行代码。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-179">**Continue** (`F5`) continues code execution to the next breakpoint.</span></span> <span data-ttu-id="d1b3e-180">按住 `F5` 将重复移动过去的工间休息，直到您释放。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-180">Holding down `F5` will repeatedly move past breaks until you release it.</span></span> 

 <span data-ttu-id="d1b3e-181">**Break** `Ctrl+Shift+B` 运行下一条语句后，中断（）将中断到调试器。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-181">**Break** (`Ctrl+Shift+B`) will break into the debugger after running the next statement.</span></span>

### <span data-ttu-id="d1b3e-182">2. 步骤函数（ `F11` 、 `Ctrl+F10` 、 `Shift+F11` ）</span><span class="sxs-lookup"><span data-stu-id="d1b3e-182">2. Step functions (`F11`, `Ctrl+F10`, `Shift+F11`)</span></span>
 <span data-ttu-id="d1b3e-183">在正在调用的函数中**单步**执行（ `F11` ）步骤。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-183">**Step into** (`F11`) steps into the function being called.</span></span> 

 <span data-ttu-id="d1b3e-184">**逐步骤**（ `Ctrl+F10` ）对正在调用的函数执行操作。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-184">**Step over** (`Ctrl+F10`) steps over the function being called.</span></span> 

 <span data-ttu-id="d1b3e-185">**跳出（** `Shift+F11` ）从当前函数到调用函数的步骤。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-185">**Step out** (`Shift+F11`) steps out of the current function and into the calling function.</span></span> 

 <span data-ttu-id="d1b3e-186">如果使用这些命令时，调试器不在函数中，则调试器将单步执行到下一条语句。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-186">The debugger will step to the next statement if it is not at a function when these commands are used.</span></span>

### <span data-ttu-id="d1b3e-187">3. 在新工作人员处中断（ `Ctrl+Shift+W` ）</span><span class="sxs-lookup"><span data-stu-id="d1b3e-187">3. Break on new worker (`Ctrl+Shift+W`)</span></span>
 <span data-ttu-id="d1b3e-188">创建新的[web 工作人员](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers)时中断。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-188">Breaks on the creation of a new [web worker](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers).</span></span>

### <span data-ttu-id="d1b3e-189">4. 异常控制</span><span class="sxs-lookup"><span data-stu-id="d1b3e-189">4. Exception control</span></span>
<span data-ttu-id="d1b3e-190">**更改异常行为**（ `Ctrl+Shift+E` ）打开选项以更改调试器对异常的反应方式。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-190">**Change exception behavior** (`Ctrl+Shift+E`) opens options to change how the debugger reacts to exceptions.</span></span> <span data-ttu-id="d1b3e-191">默认情况下，调试器会忽略异常并将其记录到[**控制台**](./console.md)。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-191">By default exceptions are ignored by the debugger and logged to the [**Console**](./console.md).</span></span> <span data-ttu-id="d1b3e-192">你可以选择*中断所有异常*，或者仅中断 `try...catch` 你的代码中的语句（*中断未经处理的异常*）处理的异常。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-192">You can choose to *Break on all exceptions*, or just those not being handled by `try...catch` statements in your code (*Break on unhandled exceptions*).</span></span>

### <span data-ttu-id="d1b3e-193">5. 查看搜索结果</span><span class="sxs-lookup"><span data-stu-id="d1b3e-193">5. View search results</span></span>
<span data-ttu-id="d1b3e-194">（当前已禁用。）"**显示/隐藏结果**" 将切换 "[*在文件中查找*](#6-find-in-files-ctrlf)" 搜索结果的显示。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-194">(Currently disabled.) **Show/Hide results** toggles the display of [*Find in files*](#6-find-in-files-ctrlf) search results.</span></span>

### <span data-ttu-id="d1b3e-195">6. 在文件中查找（ `Ctrl+F` ）</span><span class="sxs-lookup"><span data-stu-id="d1b3e-195">6. Find in files (`Ctrl+F`)</span></span>
 <span data-ttu-id="d1b3e-196">**在文件中查找**（ `Ctrl+F` ）在[*资源选取器*](#resource-picker)中的所有已加载文件中运行文本搜索。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-196">**Find in files** (`Ctrl+F`) runs a text search through all the loaded files within the [*Resource picker*](#resource-picker).</span></span> <span data-ttu-id="d1b3e-197">如果找到文本，它将打开与搜索字符串匹配的第一个文件。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-197">If the text is found, it opens the first file matching the search string.</span></span> <span data-ttu-id="d1b3e-198">按 `Enter` `F3` 下或转到下一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-198">Pressing `Enter` or `F3` takes you to the next match.</span></span>

### <span data-ttu-id="d1b3e-199">7. 调试 "仅我的代码" （ `Ctrl+J` ）</span><span class="sxs-lookup"><span data-stu-id="d1b3e-199">7. Debug just my code (`Ctrl+J`)</span></span>
 <span data-ttu-id="d1b3e-200">**调试 "仅我的代码"** （ `Ctrl+J` ）用作切换，以在逐句通过调试器时包含或排除已标记为[库代码](#3-code-scoping)的所有文件。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-200">**Debug just my code** (`Ctrl+J`) acts as a toggle to include or exclude all the files that have been marked as [library code](#3-code-scoping) as you step through the debugger.</span></span>

### <span data-ttu-id="d1b3e-201">8. 调试程序连接</span><span class="sxs-lookup"><span data-stu-id="d1b3e-201">8. Debugger connection</span></span>
<span data-ttu-id="d1b3e-202">**断开连接/连接调试器**实质上是调试器的 "开/关" 开关。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-202">**Disconnect/Connect debugger** is essentially the on/off switch for the debugger.</span></span>

## <span data-ttu-id="d1b3e-203">项目</span><span class="sxs-lookup"><span data-stu-id="d1b3e-203">Watches</span></span>

<span data-ttu-id="d1b3e-204">使用 "**监视**" 窗格浏览本地和全局范围中的所有对象和**变量（本地**）的目录，这些内容可供在调试器中作为当前中断的焦点的语句使用。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-204">Use the **Watches** pane to browse a catalog of all objects and variables (**Locals**), both in the local and global scope, available to the statement that is the focus of the current break in the debugger.</span></span>

!["监视" 窗格](./media/debugger_watches.png)

<span data-ttu-id="d1b3e-206">你可以通过添加监视（添加监视）来跟踪特定变量的值，方法是添加监视（**添加监视**， `Ctrl+W` ）并通过双击*上下文菜单*中的 "**编辑值**" 来修改任何可编辑的值。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-206">You can track the value of specific variables as they pass in and out of scope by adding a watch (**Add watch**, `Ctrl+W`) and modify any editable values by double-clicking on it or by selecting **Edit value** from the *Context menu*.</span></span> <span data-ttu-id="d1b3e-207">使用 "**删除**" （ `Ctrl+D` ）/"**全部删除**" 按钮或从上下文菜单中清除监视。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-207">Clear your watches using the **Delete** (`Ctrl+D`) / **Delete all** buttons or from the context menu.</span></span> 

## <span data-ttu-id="d1b3e-208">详细信息</span><span class="sxs-lookup"><span data-stu-id="d1b3e-208">Details</span></span>

<span data-ttu-id="d1b3e-209">*详细信息*窗格包括 "[**调用堆栈**](#call-stack)"、"[**断点**](#breakpoints)" 和 " [**DOM 断点**](#dom-breakpoints)" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-209">The *Details* pane includes the [**Callstack**](#call-stack), [**Breakpoints**](#breakpoints) and [**DOM breakpoints**](#dom-breakpoints) tabs.</span></span>

### <span data-ttu-id="d1b3e-210">调用堆栈</span><span class="sxs-lookup"><span data-stu-id="d1b3e-210">Call stack</span></span>

<span data-ttu-id="d1b3e-211">"**调用堆栈**" 选项卡显示导致当前执行点的函数链。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-211">The **Call stack** tab shows the chain of functions that led to the current point of execution.</span></span> <span data-ttu-id="d1b3e-212">当前函数显示在顶部，并且调用函数按相反顺序显示在其下方。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-212">The current function appears at the top, and the calling functions appear below it in reverse order.</span></span>

!["调用堆栈" 窗格](./media/debugger_callstack.png)

<span data-ttu-id="d1b3e-214">"**显示/隐藏库框架**" 按钮（ `Ctrl+Shift+J` ）用于切换来自调用堆栈的[库代码](#3-code-scoping)的输出。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-214">The **Show/Hide library frames** button (`Ctrl+Shift+J`) toggles the output of [library code](#3-code-scoping) from the call stack.</span></span> <span data-ttu-id="d1b3e-215">使用右键单击上下文菜单中的**库代码**选项（ `Ctrl+L` ） *Context menu* ，将所选帧的来源标记为（或取消标记）为库代码。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-215">Use the **Library code** option (`Ctrl+L`) from the right-click *Context menu* to mark (or unmark) the source of the selected frame as library code.</span></span> 

<span data-ttu-id="d1b3e-216">"**显示/隐藏异步帧**" 按钮用于切换异步函数调用的根的显示。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-216">The **Show/Hide async frames** button toggles the display of roots for asynchronous function calls.</span></span>

### <span data-ttu-id="d1b3e-217">断点</span><span class="sxs-lookup"><span data-stu-id="d1b3e-217">Breakpoints</span></span>

<span data-ttu-id="d1b3e-218">从 "**断点**" 选项卡中，你可以管理断点和事件跟踪点，包括设置条件、禁用和删除它们。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-218">From the **Breakpoints** tab, you can manage you breakpoints and event tracepoints, including setting conditions, disabling and deleting them.</span></span>

![断点选项卡](./media/debugger_breakpoints.png)

<span data-ttu-id="d1b3e-220">下面是可用于调试的不同类型的断点的摘要。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-220">Here's a summary of the different types of breakpoints you can use for debugging.</span></span>

<span data-ttu-id="d1b3e-221">断点类型</span><span class="sxs-lookup"><span data-stu-id="d1b3e-221">Breakpoint type</span></span> | <span data-ttu-id="d1b3e-222">描述</span><span class="sxs-lookup"><span data-stu-id="d1b3e-222">Description</span></span> | <span data-ttu-id="d1b3e-223">如何设置它</span><span class="sxs-lookup"><span data-stu-id="d1b3e-223">How to set it</span></span>
:------------ | :------------ | :--------
**<span data-ttu-id="d1b3e-224">处</span><span class="sxs-lookup"><span data-stu-id="d1b3e-224">Breakpoint</span></span>** | <span data-ttu-id="d1b3e-225">在执行指定的代码行之前，只需中断到调试器。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-225">Breaks into the debugger just before the specified line of code is executed.</span></span> <span data-ttu-id="d1b3e-226">如果每行有一个语句，则可以最方便地设置常规断点。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-226">Regular breakpoints are easiest to set if you have one statement per line.</span></span> | <span data-ttu-id="d1b3e-227">从 "[调试" 窗口](#debug-window)中，单击代码中任何行号旁边的左边距。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-227">From the [Debug window](#debug-window), click in the left margin next to any line number in the code.</span></span> <span data-ttu-id="d1b3e-228">将显示一个红点，并设置断点。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-228">A red dot appears and the breakpoint is set.</span></span> <span data-ttu-id="d1b3e-229">你可以通过单击其蓝色文本跳转到任何断点的源。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-229">You can jump into the source of any breakpoint by clicking on its blue text.</span></span>
**<span data-ttu-id="d1b3e-230">条件断点</span><span class="sxs-lookup"><span data-stu-id="d1b3e-230">Conditional breakpoint</span></span>** | <span data-ttu-id="d1b3e-231">如果指定条件的计算结果为*true*，则断开。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-231">Breaks if the specified condition evaluates to *true*.</span></span> <span data-ttu-id="d1b3e-232">这实际上是 `if(condition)` 用于中断调试器。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-232">This is essentially an `if(condition)`  for breaking into the debugger.</span></span>  | <span data-ttu-id="d1b3e-233">从 "[断点](#breakpoints)" 选项卡上，将鼠标悬停在现有断点上，然后单击 "铅笔" 按钮（*向此断点添加条件*），右键单击现有断点，然后从上下文菜单中选择 "**条件 ...** "。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-233">From the [Breakpoints](#breakpoints) tab, hover over an existing breakpoint and click the "pencil" button (*Add a condition to this breakpoint*), right-click an existing breakpoint and select **Condition...** from the context menu.</span></span> <span data-ttu-id="d1b3e-234">在断点位置指定要计算的 "if" 条件。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-234">Specify the "if" condition to be evaluated at the breakpoint location.</span></span> 
<span data-ttu-id="d1b3e-235">**XMLHttpRequest 断点**（w/可选条件）</span><span class="sxs-lookup"><span data-stu-id="d1b3e-235">**XMLHttpRequest breakpoint** (w/optional condition)</span></span> | <span data-ttu-id="d1b3e-236">只要满足 XMLHttpRequest （XHR）请求，就会中断。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-236">Breaks whenever a XMLHttpRequest (XHR) request has been fulfilled.</span></span> <span data-ttu-id="d1b3e-237">你可以 `response` 从 "[**监视**](#watches)" 窗格中检查 XHR 对象。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-237">You can inspect the XHR `response` object from the [**Watches**](#watches) pane.</span></span> | <span data-ttu-id="d1b3e-238">从 "[断点](#breakpoints)" 选项卡中，单击 " *XMLHttpRequest 断点*" 按钮（带有向上/向下箭头的圆圈）。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-238">From the [Breakpoints](#breakpoints) tab, click the *XMLHttpRequest breakpoint* button (circle with up/down arrows).</span></span> <span data-ttu-id="d1b3e-239">你可以按照上述说明将其转换为*条件断点*。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-239">You can turn it into a *Conditional breakpoint* as described above.</span></span>
**<span data-ttu-id="d1b3e-240">事件跟踪点</span><span class="sxs-lookup"><span data-stu-id="d1b3e-240">Event tracepoint</span></span>** | <span data-ttu-id="d1b3e-241">[`console.log()`](./console/console-api.md#logging-custom-messages)在响应特定事件时使用指定字符串的调用。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-241">Calls [`console.log()`](./console/console-api.md#logging-custom-messages) with a specified string in response to a specific event.</span></span> <span data-ttu-id="d1b3e-242">将此用于不希望直接保存在事件处理程序代码中的临时控制台日志记录语句。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-242">Use this for temporary console logging statements that you don't want to save directly in your event handler code.</span></span> | <span data-ttu-id="d1b3e-243">从 "[断点](#breakpoints)" 选项卡中，单击 "*事件跟踪点*" 按钮（带有闪电形的菱形）。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-243">From the [Breakpoints](#breakpoints) tab, click the *Event tracepoint* button (diamond with lightning bolt).</span></span> <span data-ttu-id="d1b3e-244">选择触发器的**事件**类型和用于日志记录的**跟踪**语句。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-244">Select an **Event** type for the trigger and a **Trace** statement for logging.</span></span>
<span data-ttu-id="d1b3e-245">**事件断点**（带可选条件）</span><span class="sxs-lookup"><span data-stu-id="d1b3e-245">**Event breakpoint** (w/optional condition)</span></span> | <span data-ttu-id="d1b3e-246">在引发指定事件时中断。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-246">Breaks whenever a specified event is fired.</span></span> | <span data-ttu-id="d1b3e-247">从 "[断点](#breakpoints)" 选项卡中，单击 "*事件断点*" 按钮（带有闪电形的圆圈）。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-247">From the [Breakpoints](#breakpoints) tab, click the *Event breakpoint* button (circle with lightning bolt).</span></span> <span data-ttu-id="d1b3e-248">选择触发器的**事件**类型，还可以指定**条件**语句。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-248">Select an **Event** type for the trigger and optionally, specify a **Condition** statement.</span></span> 
**<span data-ttu-id="d1b3e-249">DOM 断点</span><span class="sxs-lookup"><span data-stu-id="d1b3e-249">DOM breakpoint</span></span>** | <span data-ttu-id="d1b3e-250">只要页面上的指定元素发生改变，例如其子树被修改、其属性发生更改或从 DOM 分离时，就会中断。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-250">Breaks whenever a specified element on the page is mutated, such as when its subtree is modified, its attributes change, or when it is detached from the DOM.</span></span> | <span data-ttu-id="d1b3e-251">从 "[元素](./elements/dom-breakpoints.md)" 选项卡中，右键单击源元素，然后从 " *DOM 断点*" 选项中进行选择。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-251">From the [Elements](./elements/dom-breakpoints.md) tab, right-click on a source element and select from the *DOM Breakpoints* options.</span></span> <span data-ttu-id="d1b3e-252">使用 "*调试器*" 或 "*元素*" 面板中的 " [**DOM 断点**](#dom-breakpoints)" 选项卡来管理断点。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-252">Use the [**DOM breakpoints**](#dom-breakpoints) tab in either the *Debugger* or *Elements* panels to manage your breakpoints.</span></span> 

<span data-ttu-id="d1b3e-253">条件断点和跟踪点在其中断到调试器时可以访问当前在范围内的所有局部变量和全局变量。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-253">Conditional breakpoints and tracepoints have access to all the local and global variables currently in scope when they break into the debugger.</span></span>

### <span data-ttu-id="d1b3e-254">DOM 断点</span><span class="sxs-lookup"><span data-stu-id="d1b3e-254">DOM breakpoints</span></span>

<span data-ttu-id="d1b3e-255">从 " **dom 断点**" 选项卡管理你的 dom 转变断点，包括禁用、删除和重新绑定它们。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-255">Manage your DOM mutation breakpoints from the **DOM breakpoints** tab, including disabling, deleting and rebinding them.</span></span>  <span data-ttu-id="d1b3e-256">可以从 "**元素**" 面板中的*HTML 树视图*[设置 DOM 断点](./elements/dom-breakpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-256">[DOM breakpoints can be set](./elements/dom-breakpoints.md) from the *HTML tree view* in the **Elements** panel.</span></span>

![DOM 断点选项卡](./media/debugger_dom_breakpoints.png)

<span data-ttu-id="d1b3e-258">**调试器**中的 " *dom 断点*" 选项卡向 "**元素**" 面板上的 " *dom 断点*" 选项卡提供等效功能。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-258">The *DOM breakpoints* tab in the **Debugger** provides equivalent functionality to the *DOM breakpoints*\* tab on the **Elements** panel.</span></span>

<span data-ttu-id="d1b3e-259">下面详细介绍了不同类型的[DOM 断点](./elements/dom-breakpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-259">Here's more on the different types of [DOM breakpoints](./elements/dom-breakpoints.md).</span></span>

## <span data-ttu-id="d1b3e-260">指向</span><span class="sxs-lookup"><span data-stu-id="d1b3e-260">Shortcuts</span></span>

### <span data-ttu-id="d1b3e-261">工具栏快捷方式</span><span class="sxs-lookup"><span data-stu-id="d1b3e-261">Toolbar shortcuts</span></span>

<span data-ttu-id="d1b3e-262">操作</span><span class="sxs-lookup"><span data-stu-id="d1b3e-262">Action</span></span> | <span data-ttu-id="d1b3e-263">快捷方式</span><span class="sxs-lookup"><span data-stu-id="d1b3e-263">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="d1b3e-264">查找</span><span class="sxs-lookup"><span data-stu-id="d1b3e-264">Find</span></span> | `Ctrl` + `F`
<span data-ttu-id="d1b3e-265">继续（从断点）</span><span class="sxs-lookup"><span data-stu-id="d1b3e-265">Continue (from breakpoint)</span></span> | `F5` <span data-ttu-id="d1b3e-266">或者</span><span class="sxs-lookup"><span data-stu-id="d1b3e-266">or</span></span> `F8`
<span data-ttu-id="d1b3e-267">快速继续</span><span class="sxs-lookup"><span data-stu-id="d1b3e-267">Fast continue</span></span> | <span data-ttu-id="d1b3e-268">保留 `F5` 或</span><span class="sxs-lookup"><span data-stu-id="d1b3e-268">Hold `F5` or</span></span> `F8`
<span data-ttu-id="d1b3e-269">继续并刷新</span><span class="sxs-lookup"><span data-stu-id="d1b3e-269">Continue and refresh</span></span> | `Ctrl` + `Shift` + `F5`
<span data-ttu-id="d1b3e-270">进入</span><span class="sxs-lookup"><span data-stu-id="d1b3e-270">Break</span></span> | `Ctrl` + `Shift` + `B`
<span data-ttu-id="d1b3e-271">单步执行</span><span class="sxs-lookup"><span data-stu-id="d1b3e-271">Step into</span></span> | `F11`
<span data-ttu-id="d1b3e-272">跳过</span><span class="sxs-lookup"><span data-stu-id="d1b3e-272">Step over</span></span> | `F10`
<span data-ttu-id="d1b3e-273">跳出</span><span class="sxs-lookup"><span data-stu-id="d1b3e-273">Step out</span></span> | `Shift` + `F11`
<span data-ttu-id="d1b3e-274">新工作人员中断</span><span class="sxs-lookup"><span data-stu-id="d1b3e-274">Break on new worker</span></span> | `Ctrl` + `Shift` + `W`
<span data-ttu-id="d1b3e-275">更改异常行为（"打开" 菜单）</span><span class="sxs-lookup"><span data-stu-id="d1b3e-275">Change exception behavior (opens menu)</span></span> | `Ctrl` + `Shift` + `E`
<span data-ttu-id="d1b3e-276">调试 "仅我的代码"</span><span class="sxs-lookup"><span data-stu-id="d1b3e-276">Debug just my code</span></span> | `Ctrl` + `J`

### <span data-ttu-id="d1b3e-277">资源选取器快捷方式</span><span class="sxs-lookup"><span data-stu-id="d1b3e-277">Resource picker shortcuts</span></span>

<span data-ttu-id="d1b3e-278">操作</span><span class="sxs-lookup"><span data-stu-id="d1b3e-278">Action</span></span> | <span data-ttu-id="d1b3e-279">快捷方式</span><span class="sxs-lookup"><span data-stu-id="d1b3e-279">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="d1b3e-280">标记为我的代码/库代码</span><span class="sxs-lookup"><span data-stu-id="d1b3e-280">Mark as my code / library code</span></span> | `Ctrl` + `L`
<span data-ttu-id="d1b3e-281">打开文件</span><span class="sxs-lookup"><span data-stu-id="d1b3e-281">Open file</span></span> | `Ctrl`<span data-ttu-id="d1b3e-282"> + `O`, `Ctrl` + </span><span class="sxs-lookup"><span data-stu-id="d1b3e-282"> + `O`, `Ctrl` + </span></span>`P`
<span data-ttu-id="d1b3e-283">搜索所有文件</span><span class="sxs-lookup"><span data-stu-id="d1b3e-283">Search all files</span></span> | `Ctrl` + `Shift` + `F`

### <span data-ttu-id="d1b3e-284">调试窗口快捷方式</span><span class="sxs-lookup"><span data-stu-id="d1b3e-284">Debug window shortcuts</span></span>

<span data-ttu-id="d1b3e-285">操作</span><span class="sxs-lookup"><span data-stu-id="d1b3e-285">Action</span></span> | <span data-ttu-id="d1b3e-286">快捷方式</span><span class="sxs-lookup"><span data-stu-id="d1b3e-286">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="d1b3e-287">删除断点</span><span class="sxs-lookup"><span data-stu-id="d1b3e-287">Remove breakpoint</span></span> | `F9`
<span data-ttu-id="d1b3e-288">禁用断点</span><span class="sxs-lookup"><span data-stu-id="d1b3e-288">Disable breakpoint</span></span> | `Ctrl` + `F9`
<span data-ttu-id="d1b3e-289">条件断点 .。。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-289">Conditional breakpoint...</span></span> | `Alt` + `F9`
<span data-ttu-id="d1b3e-290">复制</span><span class="sxs-lookup"><span data-stu-id="d1b3e-290">Copy</span></span> | `Ctrl` + `C`
<span data-ttu-id="d1b3e-291">保存</span><span class="sxs-lookup"><span data-stu-id="d1b3e-291">Save</span></span> | `Ctrl` + `S`
<span data-ttu-id="d1b3e-292">转到行 .。。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-292">Go to line...</span></span> | `Ctrl` + `G`
<span data-ttu-id="d1b3e-293">显示下一条语句</span><span class="sxs-lookup"><span data-stu-id="d1b3e-293">Show next statement</span></span> | `Alt` + `Num` + `*`
<span data-ttu-id="d1b3e-294">运行到光标</span><span class="sxs-lookup"><span data-stu-id="d1b3e-294">Run to cursor</span></span> | `Ctrl` + `F10`
<span data-ttu-id="d1b3e-295">设置下一语句</span><span class="sxs-lookup"><span data-stu-id="d1b3e-295">Set next statement</span></span> | `Ctrl` + `Shift` + `F10`
<span data-ttu-id="d1b3e-296">在文件选取器中显示</span><span class="sxs-lookup"><span data-stu-id="d1b3e-296">Show in file picker</span></span> | `Ctrl` + `Alt` + `P`
<span data-ttu-id="d1b3e-297">转到文件中的定义</span><span class="sxs-lookup"><span data-stu-id="d1b3e-297">Go to definition in file</span></span> | `Ctrl`+`D`
<span data-ttu-id="d1b3e-298">在文件中查找引用</span><span class="sxs-lookup"><span data-stu-id="d1b3e-298">Find references in file</span></span> | `Ctrl` + `Shift` + `D`
<span data-ttu-id="d1b3e-299">打印整齐</span><span class="sxs-lookup"><span data-stu-id="d1b3e-299">Pretty print</span></span> | `Ctrl` + `Shift` + `P`
<span data-ttu-id="d1b3e-300">文字环绕</span><span class="sxs-lookup"><span data-stu-id="d1b3e-300">Word wrap</span></span> | `Alt` + `W`
<span data-ttu-id="d1b3e-301">标记为我的代码/库代码</span><span class="sxs-lookup"><span data-stu-id="d1b3e-301">Mark as my code/library code</span></span> | `Ctrl` + `L`
<span data-ttu-id="d1b3e-302">在编辑器中禁用/启用选项卡。</span><span class="sxs-lookup"><span data-stu-id="d1b3e-302">Disable/Enable tabs in the editor.</span></span> <span data-ttu-id="d1b3e-303">**注意：** 如果你使用键盘在调试程序中导航，则无法通过 tab 键退出编辑器，直到禁用 tab 键切换</span><span class="sxs-lookup"><span data-stu-id="d1b3e-303">**Note:** if you're using the keyboard to navigate in the Debugger, you won't be able to tab out of the editor until you disable tabbing</span></span> | `Ctrl` + `M`

### <span data-ttu-id="d1b3e-304">"监视" 窗格的快捷方式</span><span class="sxs-lookup"><span data-stu-id="d1b3e-304">Shortcuts for Watches pane</span></span>

<span data-ttu-id="d1b3e-305">操作</span><span class="sxs-lookup"><span data-stu-id="d1b3e-305">Action</span></span> | <span data-ttu-id="d1b3e-306">快捷方式</span><span class="sxs-lookup"><span data-stu-id="d1b3e-306">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="d1b3e-307">添加手表</span><span class="sxs-lookup"><span data-stu-id="d1b3e-307">Add watch</span></span> | `Ctrl` + `W`
<span data-ttu-id="d1b3e-308">删除手表</span><span class="sxs-lookup"><span data-stu-id="d1b3e-308">Delete watch</span></span> | `Ctrl` + `D`

### <span data-ttu-id="d1b3e-309">"详细信息" 窗格的快捷方式</span><span class="sxs-lookup"><span data-stu-id="d1b3e-309">Shortcuts for Details pane</span></span>

| <span data-ttu-id="d1b3e-310">操作</span><span class="sxs-lookup"><span data-stu-id="d1b3e-310">Action</span></span>                             | <span data-ttu-id="d1b3e-311">快捷方式</span><span class="sxs-lookup"><span data-stu-id="d1b3e-311">Shortcut</span></span>                 |
|:-----------------------------------|:-------------------------|
| <span data-ttu-id="d1b3e-312">显示/隐藏库代码中的框架</span><span class="sxs-lookup"><span data-stu-id="d1b3e-312">Show/Hide frames from library code</span></span> | `Ctrl` + `Shift` + `J`   |
| <span data-ttu-id="d1b3e-313">启用所有断点</span><span class="sxs-lookup"><span data-stu-id="d1b3e-313">Enable all breakpoints</span></span>             | `Ctrl` + `Shift` + `F11` |
