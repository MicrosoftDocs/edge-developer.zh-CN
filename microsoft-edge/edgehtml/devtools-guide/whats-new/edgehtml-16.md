---
description: '在 EdgeHTML 16 中添加到 Windows 10 Fall Creators Update (Microsoft Edge DevTools) '
title: EdgeHTML 16 中的 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， edgehtml 16
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2d24b6851e843f491e470b18ccc18d559ed5533d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232102"
---
# <span data-ttu-id="6f099-104">EdgeHTML 16 (Windows 10 Fall Creators Update 中的 DevTools) </span><span class="sxs-lookup"><span data-stu-id="6f099-104">DevTools in the Windows 10 Fall Creators Update (EdgeHTML 16)</span></span>

<span data-ttu-id="6f099-105">在此版本中，我们启动了一项重大 DevTools 重构工作，以提高稳定性和性能，并添加了一组立即开始使用的新功能！</span><span class="sxs-lookup"><span data-stu-id="6f099-105">With this release we started a major DevTools refactoring effort for improved robustness and performance, and also added a bunch of new features you can start using today!</span></span> 

<span data-ttu-id="6f099-106">以下是 EdgeHTML [16 版本 Windows 10 Fall Creators Update](/windows/uwp/whats-new/windows-10-build-16299) ([附带的 Microsoft Edge](https://aka.ms/devguide_edgehtml_16) DevTools) 。</span><span class="sxs-lookup"><span data-stu-id="6f099-106">Here are the Microsoft Edge DevTools features that shipped with the [Windows 10 Fall Creators Update](/windows/uwp/whats-new/windows-10-build-16299) ([EdgeHTML 16](https://aka.ms/devguide_edgehtml_16)).</span></span>

## <span data-ttu-id="6f099-107">上级事件侦听器</span><span class="sxs-lookup"><span data-stu-id="6f099-107">Ancestor event listeners</span></span> 

<span data-ttu-id="6f099-108">除了**元素本身**上的事件侦听器之外，"事件"窗格现在还添加了查看在元素面板) 中当前选定元素 (\*\*\*\* 的任何上级上注册的事件侦听器的选项。</span><span class="sxs-lookup"><span data-stu-id="6f099-108">The **Events** pane now adds the option to view event listeners registered on any ancestor of the currently selected element (in the **Elements** panel), in addition to those on the element itself.</span></span> <span data-ttu-id="6f099-109">此外，你现在可以按 Event 或 *Element* 对事件侦听器显示 *进行分组*。</span><span class="sxs-lookup"><span data-stu-id="6f099-109">Additionally, you can now group the event listener display by either *Event* or *Element*.</span></span> 

![事件侦听器检查窗格](../media/elements_ancestor_events.png)

## <span data-ttu-id="6f099-111">DOM 破坏断点</span><span class="sxs-lookup"><span data-stu-id="6f099-111">DOM mutation breakpoints</span></span>

<span data-ttu-id="6f099-112">现在，你可以设置 DOM 分解断点，以在选定元素节点发生更改时中断调试器。</span><span class="sxs-lookup"><span data-stu-id="6f099-112">You can now set DOM mutation breakpoints to break into the Debugger whenever a selected element node changes.</span></span> <span data-ttu-id="6f099-113">从 **"元素** "面板中，rt-click on any element in the DOM tree view and select one or more of the following：</span><span class="sxs-lookup"><span data-stu-id="6f099-113">From the **Elements** panel, rt-click on any element in the DOM tree view and select one or more of the following:</span></span>

 - <span data-ttu-id="6f099-114">删除节点上的中断</span><span class="sxs-lookup"><span data-stu-id="6f099-114">Break on Node removed</span></span>
 - <span data-ttu-id="6f099-115">修改了子树上的中断</span><span class="sxs-lookup"><span data-stu-id="6f099-115">Break on Subtree modified</span></span>
 - <span data-ttu-id="6f099-116">修改属性时中断</span><span class="sxs-lookup"><span data-stu-id="6f099-116">Break on Attribute modified</span></span>

<span data-ttu-id="6f099-117">可以从"元素"或"调试器"面板中的**DOM**断点窗格\*\*\*\*\*\*管理\*\*你的分解断点。</span><span class="sxs-lookup"><span data-stu-id="6f099-117">You can manage your mutation breakpoints from the **DOM breakpoints** pane in the **Elements** or **Debugger** panels.</span></span>

![DOM 断点窗格](../media/elements_dom_breakpoints.png)

## <span data-ttu-id="6f099-119">CSS 规则支持</span><span class="sxs-lookup"><span data-stu-id="6f099-119">CSS at-rule support</span></span>

<span data-ttu-id="6f099-120">CSS "at" (@) 规则现在在"样式"窗格上的其他 CSS 规则声明中表示\*\*\*\*，包括动画规则 (当前限制为只读 `@keyframes`) 、功能查询和查询。 `@supports` `@media`</span><span class="sxs-lookup"><span data-stu-id="6f099-120">CSS "at" (@) rules are now represented among other CSS rule declarations on the **Styles** pane, including animation `@keyframes` rules (currently limited to read-only), `@supports` feature queries, and `@media` queries.</span></span>

![从"DevTools 样式"窗格进行 CSS 规则检查](../media/elements_at_rules.png)

## <span data-ttu-id="6f099-122">CSS 字体窗格</span><span class="sxs-lookup"><span data-stu-id="6f099-122">CSS fonts pane</span></span>

<span data-ttu-id="6f099-123">CSS `@font-face` 规则现在具有其自己的专用\*\*\*\*\*\*"字体"窗格，该窗格显示从本地或网络 (加载) 以及\*\* 使用它的字符数。</span><span class="sxs-lookup"><span data-stu-id="6f099-123">CSS `@font-face` rules now have their own dedicated **Fonts** pane that displays where the font is loaded from (*Local* or *Network*) and how many characters are using it.</span></span> <span data-ttu-id="6f099-124">如果从网络加载字体，DevTools 将显示导入该字体的规则及其别名和字体类型。</span><span class="sxs-lookup"><span data-stu-id="6f099-124">If a font is loaded from the network,  DevTools will display the rule that imported it along with its alias and font type.</span></span>

![CSS 字体信息](../media/elements_fonts.png)

## <span data-ttu-id="6f099-126">CSS 伪元素支持</span><span class="sxs-lookup"><span data-stu-id="6f099-126">CSS pseudo-element support</span></span>

<span data-ttu-id="6f099-127">" **样式** "窗格现在将伪元素分组在其自己的标题下，不再显示为已排除的内容。</span><span class="sxs-lookup"><span data-stu-id="6f099-127">The **Styles** pane now groups pseudo-elements under their own headings and no longer displays their content as crossed out.</span></span>

**<span data-ttu-id="6f099-128">之前：</span><span class="sxs-lookup"><span data-stu-id="6f099-128">Before:</span></span>**
<br>
![生成的内容之前已排除](../media/gc_before.png)

**<span data-ttu-id="6f099-130">之后：</span><span class="sxs-lookup"><span data-stu-id="6f099-130">After:</span></span>**
<br>
![生成的内容不再显示带删除线](../media/gc_after.png)

## <span data-ttu-id="6f099-132">控制台改进</span><span class="sxs-lookup"><span data-stu-id="6f099-132">Console improvements</span></span>

<span data-ttu-id="6f099-133">控制台 **面板** 进行了 UX 检查，以改进可用性和更快、更丰富的 Intellisense 体验。</span><span class="sxs-lookup"><span data-stu-id="6f099-133">The **Console** panel got a UX overhaul for improved usability and a faster, richer Intellisense experience.</span></span>

<span data-ttu-id="6f099-134">**之前：** 
![上一个控制台</span><span class="sxs-lookup"><span data-stu-id="6f099-134">**Before:**
![Previous console</span></span>](../media/console_old.png)

<span data-ttu-id="6f099-135">**之后：** 
![新控制台</span><span class="sxs-lookup"><span data-stu-id="6f099-135">**After:**
![New console</span></span>](../media/console_new.png)

<span data-ttu-id="6f099-136">我们还添加了以下改进：</span><span class="sxs-lookup"><span data-stu-id="6f099-136">We also added these improvements:</span></span>

 -  <span data-ttu-id="6f099-137">用于 `Shift + Enter` 向命令添加一个附加行，然后使用 `Enter` 执行命令。</span><span class="sxs-lookup"><span data-stu-id="6f099-137">Use `Shift + Enter` to add an additional line to a command before executing it with `Enter`.</span></span> <span data-ttu-id="6f099-138"> (以前有一个切换到 *多行/单行模式* 切换按钮。) </span><span class="sxs-lookup"><span data-stu-id="6f099-138">(Formerly there was a *Switch to multiline/single-line mode* toggle button.)</span></span>

 - <span data-ttu-id="6f099-139">支持以下新 API：</span><span class="sxs-lookup"><span data-stu-id="6f099-139">The following new APIs are supported:</span></span>
    - <span data-ttu-id="6f099-140">[ **console.table (**_对象) _*__*](../console/console-api.md#organizing-log-output)方法</span><span class="sxs-lookup"><span data-stu-id="6f099-140">[**console.table(**_object_*_)_*](../console/console-api.md#organizing-log-output) method</span></span>
    - <span data-ttu-id="6f099-141">[ **getEventListeners (**_对象) _*__*](../console/command-line.md#event-listeners)命令</span><span class="sxs-lookup"><span data-stu-id="6f099-141">[**getEventListeners(**_object_*_)_*](../console/command-line.md#event-listeners) command</span></span>
    - <span data-ttu-id="6f099-142">[**键 (**_对象) _*__*](../console/command-line.md#object-inspection)命令</span><span class="sxs-lookup"><span data-stu-id="6f099-142">[**keys(**_object_*_)_*](../console/command-line.md#object-inspection) command</span></span>
    - <span data-ttu-id="6f099-143">[**值 (**_对象) _*__*](../console/command-line.md#object-inspection)命令</span><span class="sxs-lookup"><span data-stu-id="6f099-143">[**values(**_object_*_)_*](../console/command-line.md#object-inspection) command</span></span>
    - <span data-ttu-id="6f099-144">[ **$x (** _xpath 表达式) _*__*](../console/command-line.md#dom-selectors)选择器</span><span class="sxs-lookup"><span data-stu-id="6f099-144">[**$x(**_xpath expression_*_)_*](../console/command-line.md#dom-selectors) selector</span></span>

 - <span data-ttu-id="6f099-145">[\*\*现在支持 %c () \*\*](../console/console-api.md#logging-custom-messages)格式参数</span><span class="sxs-lookup"><span data-stu-id="6f099-145">The [**%c()**](../console/console-api.md#logging-custom-messages) formatting parameter is now supported</span></span>

## <span data-ttu-id="6f099-146">调试改进</span><span class="sxs-lookup"><span data-stu-id="6f099-146">Debugging improvements</span></span>

<span data-ttu-id="6f099-147">除了一套用于调试 [PWA](#progressive-web-app-debugging)服务工作者和缓存的新功能外，调试器还添加了以下功能：</span><span class="sxs-lookup"><span data-stu-id="6f099-147">In addition to a suite of new features for debugging your [PWA service workers and cache](#progressive-web-app-debugging), the Debugger added these features:</span></span>

### <span data-ttu-id="6f099-148">合并共享资源的调试</span><span class="sxs-lookup"><span data-stu-id="6f099-148">Consolidated debugging for shared resources</span></span>

<span data-ttu-id="6f099-149">即使从 CDN 加载的资源（如从 CDN 加载的文件）在整个代码中多次引用，DevTools 现在也会为该文件提供单个调试实例，然后你可以设置常用断点，无论该文件引用在何处，都会命中这些断点。</span><span class="sxs-lookup"><span data-stu-id="6f099-149">Even when a resource, such as a file loaded from CDN, is referenced multiple times throughout your code,  DevTools will now provide a single debugging instance for that file where you can then set common breakpoints which will be hit regardless of where that file is referenced.</span></span> <span data-ttu-id="6f099-150"> (之前，每个脚本引用都被视为一个唯一的资源将映射到一组单独的断点。) </span><span class="sxs-lookup"><span data-stu-id="6f099-150">(Previously each script reference was considered a unique resource would map to a separate set of breakpoints.)</span></span>

### <span data-ttu-id="6f099-151">实时编辑 JavaScript（ *处于空闲状态时编辑）*</span><span class="sxs-lookup"><span data-stu-id="6f099-151">Live edit JavaScript with *Edit-on-idle*</span></span>

<span data-ttu-id="6f099-152">现在可以在调试会话期间编辑 JavaScript 实时。</span><span class="sxs-lookup"><span data-stu-id="6f099-152">You can now edit your JavaScript live during a debugging session.</span></span> <span data-ttu-id="6f099-153">此功能在实验 (上一个 [) ](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) *Windows 10* 创意者更新 () 版本中的标记后面可用，现在是一项永久性功能。</span><span class="sxs-lookup"><span data-stu-id="6f099-153">This feature was experimentally available (behind a flag) in the [previous](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) (*Windows 10 Creators Update*) release and now its a permanent feature.</span></span> <span data-ttu-id="6f099-154">只需从调试器面板中选择任何\*\*\*\* 脚本文件，进行编辑，然后单击"\*\*\*\* 保存 (或) 代码部分下次运行时 `Ctrl+S` 测试更改。</span><span class="sxs-lookup"><span data-stu-id="6f099-154">Simply select any script file from the **Debugger** panel, edit, then click **Save** (or `Ctrl+S`) to test your changes next time that section of code runs.</span></span> 

![调试器使你能够实时编辑脚本并差异更改](../media/debugger_edit_buttons.png) 

<span data-ttu-id="6f099-156">单击 **"比较文档与原始文档"** 按钮以查看您更改的内容的差异。</span><span class="sxs-lookup"><span data-stu-id="6f099-156">Click the **Compare document to original** button to view the diff of what you changed.</span></span>

![调试器中已编辑代码的差异视图](../media/debugger_edit_code.png) 

<span data-ttu-id="6f099-158">请注意以下约束：</span><span class="sxs-lookup"><span data-stu-id="6f099-158">Please be aware of the following constraints:</span></span>

- <span data-ttu-id="6f099-159">脚本编辑仅适用于外部 *.js*文件 (而未嵌入 `<script>` \*.html) \*</span><span class="sxs-lookup"><span data-stu-id="6f099-159">Script editing only works in external *.js* files (and not embedded `<script>` within *.html*)</span></span>
- <span data-ttu-id="6f099-160">编辑保存在内存中，在重新加载文档时刷新，因此无法运行处理程序中的编辑， `DOMContentLoaded` 例如</span><span class="sxs-lookup"><span data-stu-id="6f099-160">Edits are saved in memory and flushed when the document is reloaded, thus you won’t be able to run edits inside a `DOMContentLoaded` handler, for example</span></span>
- <span data-ttu-id="6f099-161">目前，无法 ("另存为"选项) 从\*\*\*\* DevTools 将编辑保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="6f099-161">Currently there’s no way (such as a **Save As** option) to save your edits to disk from  DevTools</span></span>

## <span data-ttu-id="6f099-162">快捷方式</span><span class="sxs-lookup"><span data-stu-id="6f099-162">Shortcuts</span></span>

<span data-ttu-id="6f099-163">你现在可以将 DevTools 启动到上次查看的面板 () 或直接启动到控制台 () 就像在主要浏览器上一 `Ctrl+Shift+I` `Ctrl+Shift+J` 样。</span><span class="sxs-lookup"><span data-stu-id="6f099-163">You can now launch DevTools to the last viewed panel (`Ctrl+Shift+I`) or directly to the Console (`Ctrl+Shift+J`) just like you would on other major browsers.</span></span>

## <span data-ttu-id="6f099-164">渐进式 Web 应用调试</span><span class="sxs-lookup"><span data-stu-id="6f099-164">Progressive Web App debugging</span></span>

<span data-ttu-id="6f099-165">通过从 (中选择"启用服务工作者"选项并重新启动 Microsoft Edge) ，在 Microsoft Edge 和 DevTools 中测试对渐进式 Web 应用 (PWA) 的实验性\*\*\*\* `about:flags` 支持。</span><span class="sxs-lookup"><span data-stu-id="6f099-165">Test out the experimental support for Progressive Web Apps (PWAs) in Microsoft Edge and  DevTools by selecting the **Enable service workers** option from `about:flags` (and restarting Microsoft Edge).</span></span> <span data-ttu-id="6f099-166">如果网站使用服务工作者和\*\*\*\*/或缓存**API，** 将填充每个源的调试器面板中的\*\*\*\* 条目，类似于 Web 存储和 Cookie 检查工作的方式。</span><span class="sxs-lookup"><span data-stu-id="6f099-166">If a site makes use of **Service Workers** and/or the **Cache** API,  will populate entries in the **Debugger** panel for each origin, similar to how web storage and cookie inspection work.</span></span>

<span data-ttu-id="6f099-167">单击特定服务工作线程条目将打开服务工作者概述\*\*\*\*，您可以在其中管理给定范围的服务工作者注册并强制发送测试推送通知。</span><span class="sxs-lookup"><span data-stu-id="6f099-167">Clicking on a specific service worker entry will open up the **Service Worker Overview**, where you can manage the service worker registration for the given scope and force a test push notification.</span></span> <span data-ttu-id="6f099-168">还可以停止**启动** / **各个**服务工作者，**然后从**单独的调试器窗口中检查它们：</span><span class="sxs-lookup"><span data-stu-id="6f099-168">You can also **Stop**/**Start** individual service workers and **Inspect** them from a separate debugger window:</span></span>

!["服务工作者概述"窗格](../media/debugger_sw_overview.png)

<span data-ttu-id="6f099-170">请注意以下有关服务工作器调试的信息：</span><span class="sxs-lookup"><span data-stu-id="6f099-170">Please note the following about service worker debugging:</span></span>

 - <span data-ttu-id="6f099-171">调试服务工作者将启动独立于页面工具的 DevTools 的新实例，因为服务工作者可以跨多个选项卡共享。</span><span class="sxs-lookup"><span data-stu-id="6f099-171">Debugging a service worker will launch a new instance of the DevTools separate from the page's tools because service workers can be shared across multiple tabs.</span></span> 
 - <span data-ttu-id="6f099-172">由于[服务](../elements.md)工作者[](../emulation.md)在后台运行，并且不直接控制应用的前端，因此服务工作器调试器中缺少元素和模拟面板。</span><span class="sxs-lookup"><span data-stu-id="6f099-172">The [Elements](../elements.md) and [Emulation](../emulation.md) panels are absent from the service worker debugger, given that service workers run in the background and do not directly control the front-end of your app.</span></span>
 - <span data-ttu-id="6f099-173">目前，仅从服务工作者的 DevTools 调试实例报告服务工作者的网络流量，而不是从页面本身的中央实例报告。</span><span class="sxs-lookup"><span data-stu-id="6f099-173">Currently network traffic for a service worker is only reported from the DevTools debugging instance for that worker, and not from the central instance for the page itself.</span></span>

<span data-ttu-id="6f099-174">单击特定缓存条目将打开缓存管理器，您可以在\*\*\*\* 其中检查和选择删除请求和响应 (/值对中的缓存) 。 \*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="6f099-174">Clicking on a specific cache entry will open up the **Cache** manager, where you can inspect and optionally delete cache entries (*Request* and *Response* key/value pairs).</span></span>
