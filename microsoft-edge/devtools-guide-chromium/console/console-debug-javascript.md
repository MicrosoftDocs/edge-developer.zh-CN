---
description: JavaScript 错误由开发人员工具报告，在控制台中调试每个错误
title: 使用控制台跟踪错误
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: ebd12f8932332b3e63162ab6952577bdb43bbccd
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483348"
---
# <a name="debug-errors-reported-in-console"></a><span data-ttu-id="4f2cf-104">在控制台中报告的调试错误</span><span class="sxs-lookup"><span data-stu-id="4f2cf-104">Debug errors reported in Console</span></span>  

<span data-ttu-id="4f2cf-105">使用控制台的第一 **个体验** 可能是脚本中的错误。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-105">The first experience you have with the **Console** is probably an error in a script.</span></span>  <span data-ttu-id="4f2cf-106">若要试用它，请导航到控制台工具 [中报告的 JavaScript 错误][GithubMicrosoftedgeDevtoolssamplesConsoleErrorHtml]。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-106">To try it, navigate to [JavaScript error reported in the Console tool][GithubMicrosoftedgeDevtoolssamplesConsoleErrorHtml].</span></span>  

<span data-ttu-id="4f2cf-107">如果在浏览器中打开 DevTools，则右上方的按钮将显示网页的错误。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-107">If you open DevTools in the browser, a button on the top right displays an error for the webpage.</span></span>  
<span data-ttu-id="4f2cf-108">选择按钮以将你导航到 **控制台** ，并提供有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-108">Choose the button to take you to the **Console** and give you more information about the error.</span></span>  

:::image type="complex" source="../media/console-debug-displays-error.msft.png" alt-text="DevTools 提供有关控制台中错误的详细信息" lightbox="../media/console-debug-displays-error.msft.png":::
   <span data-ttu-id="4f2cf-110">DevTools 提供有关控制台中错误 **的详细信息**</span><span class="sxs-lookup"><span data-stu-id="4f2cf-110">DevTools gives detailed information about the error in the **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="4f2cf-111">从信息中，您可能会发现错误位于文件的第 16 `error.html` 行。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-111">From the information, you may gather that the error is on line 16 of the `error.html` file.</span></span>  <span data-ttu-id="4f2cf-112">如果选择控制台右侧的链接，它会将你指向"源"工具，并突出显示包含 `error.html:16` 错误的代码行。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4f2cf-112">If you choose the `error.html:16` link on the right of the **Console**, it takes you to the **Sources** tool and highlights the line of code with the error.</span></span>  

:::image type="complex" source="../media/console-debug-displays-in-sources.msft.png" alt-text="源工具突出显示导致错误的代码行" lightbox="../media/console-debug-displays-in-sources.msft.png":::
   <span data-ttu-id="4f2cf-114">源 **工具** 突出显示导致错误的代码行</span><span class="sxs-lookup"><span data-stu-id="4f2cf-114">The **Sources** tool highlights the line of code that causes the error</span></span>  
:::image-end:::  

<span data-ttu-id="4f2cf-115">该脚本尝试获取文档中的第 `h2` 一个元素，并围绕该元素绘制红色边框。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-115">The script tries to get the first `h2` element in the document and paint a red border around it.</span></span>  <span data-ttu-id="4f2cf-116">但不存在 `h2` 元素，因此脚本失败。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-116">But no `h2` element exists, so the script fails.</span></span>  

## <a name="find-and-debug-network-issues"></a><span data-ttu-id="4f2cf-117">查找和调试网络问题</span><span class="sxs-lookup"><span data-stu-id="4f2cf-117">Find and debug network issues</span></span>  

<span data-ttu-id="4f2cf-118">控制台报告 **的其他错误** 是网络错误。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-118">Other errors that the **Console** reports are network errors.</span></span>  <span data-ttu-id="4f2cf-119">若要在操作中显示它，请导航到控制台 [中报告的网络错误][GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorHtml]。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-119">To display it in action, navigate to the [Network error reported in Console][GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorHtml].</span></span>  

:::image type="complex" source="../media/console-debug-network-error.msft.png" alt-text="控制台显示网络和 JavaScript 错误" lightbox="../media/console-debug-network-error.msft.png":::
   <span data-ttu-id="4f2cf-121">**控制台** 显示网络和 JavaScript 错误</span><span class="sxs-lookup"><span data-stu-id="4f2cf-121">**Console** displays a Network and a JavaScript error</span></span>  
:::image-end:::  

<span data-ttu-id="4f2cf-122">该表显示 `loading` ，但网页上没有任何变化，因为从不检索数据。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-122">The table displays `loading`, but nothing changes on the webpage because the data is never retrieved.</span></span>  <span data-ttu-id="4f2cf-123">在控制台 **中**，发生了以下两个错误。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-123">In the **Console**, the following two errors occurred.</span></span>  

*   <span data-ttu-id="4f2cf-124">以 HTTP 方法开头，后 `GET` 跟 URI 的网络错误。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-124">A network error that starts with `GET` HTTP method followed by a URI.</span></span>  
*   <span data-ttu-id="4f2cf-125">错误 `Uncaught (in promise) TypeError: data.forEach is not a function` 。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-125">An `Uncaught (in promise) TypeError: data.forEach is not a function` error.</span></span>  
    
<span data-ttu-id="4f2cf-126">如果你在控制台 `network-error.html:40` 中选择链接，DevTools 将你指向**源**工具。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4f2cf-126">If you choose the `network-error.html:40` link in the **Console**, DevTools takes you to the **Sources** tool.</span></span>  <span data-ttu-id="4f2cf-127">有问题的代码行突出显示，后跟 `error` \ (`x` \) 按钮。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-127">The problematic line of code is highlighted and followed by an `error` \(`x`\) button.</span></span>  <span data-ttu-id="4f2cf-128">若要显示 `Failed to load resource: the server responded with a status of 404 ()` 错误消息，请选择错误 \ (\*\*\*\* `x` \) 按钮。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-128">To display the `Failed to load resource: the server responded with a status of 404 ()` error message, choose the **error** \(`x`\) button.</span></span>  


:::row:::
   :::column span="":::
      :::image type="complex" source="../media/console-debug-network-error-code-line.msft.png" alt-text="选择网页的链接和发生错误的代码行将打开"源"工具" lightbox="../media/console-debug-network-error-code-line.msft.png":::
         <span data-ttu-id="4f2cf-130">选择网页的链接和发生错误的代码行将打开 **"源"** 工具</span><span class="sxs-lookup"><span data-stu-id="4f2cf-130">Choose the link to the webpage and code where the error occurs line opens the **Sources** tool</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/console-debug-network-error-sources.msft.png" alt-text="若要在 JavaScript 中查找错误，请使用"源"工具" lightbox="../media/console-debug-network-error-sources.msft.png":::
         <span data-ttu-id="4f2cf-132">若要在 JavaScript 中查找错误，请使用 **"源"** 工具</span><span class="sxs-lookup"><span data-stu-id="4f2cf-132">To find the error in JavaScript, use the **Sources** tool</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="4f2cf-133">在示例中，错误会通知您找不到请求的 URL。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-133">In the example, the error informs you that the requested URL isn't found.</span></span>  <span data-ttu-id="4f2cf-134">接下来，完成以下操作以打开 **网络** 工具。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-134">Next, complete the following actions to open the **Network** tool.</span></span>  

1.  <span data-ttu-id="4f2cf-135">打开“**控制台**”。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-135">Open the **Console**.</span></span>  
1.  <span data-ttu-id="4f2cf-136">选择与错误关联的 URI。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-136">Choose the URI associated with the error.</span></span>  
    
:::image type="complex" source="../media/console-debug-network-error-url.msft.png" alt-text="控制台在资源未加载后显示错误的 HTTP 状态代码" lightbox="../media/console-debug-network-error-url.msft.png":::
   <span data-ttu-id="4f2cf-138">**控制台** 在资源未加载后显示错误的 HTTP 状态代码</span><span class="sxs-lookup"><span data-stu-id="4f2cf-138">**Console** displays an HTTP status code of the error after a resource isn't loaded</span></span>  
:::image-end:::  

:::row:::
    :::column:::
        :::image type="complex" source="../media/console-debug-network-error-network.msft.png" alt-text=""网络"工具显示有关失败请求详细信息" lightbox="../media/console-debug-network-error-network.msft.png":::
           <span data-ttu-id="4f2cf-140">" **网络** "工具显示有关失败请求详细信息</span><span class="sxs-lookup"><span data-stu-id="4f2cf-140">The **Network** tool displays more information about the failed request</span></span>  
        :::image-end:::  
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/console-debug-network-error-network-detail.msft.png" alt-text="检查"网络"工具中的标头可能会提供更多信息" lightbox="../media/console-debug-network-error-network-detail.msft.png":::
           <span data-ttu-id="4f2cf-142">检查" **网络"工具** 中的标头可能会提供更多信息</span><span class="sxs-lookup"><span data-stu-id="4f2cf-142">Inspect the headers in the **Network** tool may give more insight</span></span>  
        :::image-end:::  
    :::column-end:::
:::row-end:::  

<span data-ttu-id="4f2cf-143">问题是什么？</span><span class="sxs-lookup"><span data-stu-id="4f2cf-143">What was the problem?</span></span>  <span data-ttu-id="4f2cf-144">两个斜杠字符 `//` \ (\) 出现在请求的 URI 中的单词 `repos` 后。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-144">Two slash characters \(`//`\) occur in the requested URI after the word `repos`.</span></span>  <span data-ttu-id="4f2cf-145">打开" **源"** 工具并检查第 26 行。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-145">Open the **Sources** tool and inspect line 26.</span></span>  <span data-ttu-id="4f2cf-146">尾部斜杠字符 \ (\) 出现在基本 `/` URI 的末尾。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-146">A trailing slash character \(`/`\) occurs at the end of the base URI.</span></span>  

:::image type="complex" source="../media/console-debug-network-error-code-error.msft.png" alt-text=""源"工具显示包含错误的代码行" lightbox="../media/console-debug-network-error-code-error.msft.png":::
   <span data-ttu-id="4f2cf-148">" **源** "工具显示包含错误的代码行</span><span class="sxs-lookup"><span data-stu-id="4f2cf-148">The **Sources** tool displays the line of code with the error</span></span>  
:::image-end:::  

<span data-ttu-id="4f2cf-149">To review no errors in the **Console**， navigate to [Fixed network error reported in Console][GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorFixedHtml].</span><span class="sxs-lookup"><span data-stu-id="4f2cf-149">To review no errors in the **Console**, navigate to [Fixed network error reported in Console][GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorFixedHtml].</span></span>  

:::image type="complex" source="../media/console-debug-network-error-fixed.msft.png" alt-text="不带任何错误的示例从 GitHub并显示信息" lightbox="../media/console-debug-network-error-fixed.msft.png":::
   <span data-ttu-id="4f2cf-151">不带任何错误的示例从 GitHub并显示信息</span><span class="sxs-lookup"><span data-stu-id="4f2cf-151">The example without any errors loads information from GitHub and displays it</span></span>  
:::image-end:::  

<span data-ttu-id="4f2cf-152">确保提供防御性编码技术以避免以前的用户体验。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-152">Ensure you provide defensive coding techniques to avoid the previous user experiences.</span></span>  <span data-ttu-id="4f2cf-153">此外，请确保代码捕获错误，并显示控制台中的 **每个错误**。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-153">Also, ensure your code catches errors and display each in the **Console**.</span></span>  <span data-ttu-id="4f2cf-154">在控制台 [和 UI 中导航到网络错误报告][GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorReportedHtml] 并查看以下项目。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-154">Navigate to [Network error reporting in Console and UI][GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorReportedHtml] and review the following items.</span></span>  

*   <span data-ttu-id="4f2cf-155">向用户提供出错的 UI。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-155">Provide UI to the user that something went wrong.</span></span>  
*   <span data-ttu-id="4f2cf-156">在 **控制台中**，从代码提供有关网络错误的有用信息。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-156">In the **Console**, provide helpful information about the Network error from your code.</span></span>  
    
:::image type="complex" source="../media/console-debug-network-error-report.msft.png" alt-text="捕获和报告错误的示例" lightbox="../media/console-debug-network-error-report.msft.png":::
   <span data-ttu-id="4f2cf-158">捕获和报告错误的示例</span><span class="sxs-lookup"><span data-stu-id="4f2cf-158">An example that catches and reports errors</span></span>  
:::image-end:::  

<span data-ttu-id="4f2cf-159">以下代码段使用 方法捕获和报告错误 `handleErrors` ，特别是 行 `throw Error` 。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-159">The following code snippet catches and reports errors using the `handleErrors` method, specifically the `throw Error` line.</span></span>  

```javascript
const handleErrors = (response) => {
    if (!response.ok) {
        let message = 'Could not load the information'
        document.querySelector('tbody').innerHTML = `
        <tr><td colspan=3>Error ${message}</td></tr>
        `;
        throw Error(response.status + ' ' + response.statusText);
    }
    return response;
};
```  

## <a name="create-errors-and-traces-in-the-console"></a><span data-ttu-id="4f2cf-160">在控制台创建错误和跟踪</span><span class="sxs-lookup"><span data-stu-id="4f2cf-160">Create errors and traces in the Console</span></span>

<span data-ttu-id="4f2cf-161">除了 `throw Error` 上一部分中的示例之外，您还可以在控制台中创建不同的错误和跟踪 **问题**。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-161">Besides the `throw Error` example in the previous section, you may also create different errors and trace problems in the **Console**.</span></span>  
<span data-ttu-id="4f2cf-162">若要在控制台中显示两个创建的 **错误消息**，请导航到在控制台中创建错误报告和 [断言][GithubMicrosoftedgeDevtoolssamplesConsoleErrorAssertHtml]。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-162">To display two created error messages in the **Console**, navigate to [Creating error reports and assertions in Console][GithubMicrosoftedgeDevtoolssamplesConsoleErrorAssertHtml].</span></span>  

:::image type="complex" source="../media/console-debug-error-assert.msft.png" alt-text="从控制台创建的错误消息" lightbox="../media/console-debug-error-assert.msft.png":::
   <span data-ttu-id="4f2cf-164">从控制台创建的 **错误消息**</span><span class="sxs-lookup"><span data-stu-id="4f2cf-164">Error messages created from **Console**</span></span>  
:::image-end:::  

<span data-ttu-id="4f2cf-165">在上一示例中使用了以下代码段。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-165">The following code snippet was used in the previous example.</span></span>  

```javascript
function first(name) { second(name); }
function second(name) { third(name); }
function third(name) {
    if (!name) {
        console.error(`Name isn't defined :(`)
    } else {
        console.assert(
            name.length <= 8, 
            `"${name} is not less than eight letters"`
        );
    }
}
first();
first('Console');
first('Microsoft Edge Canary');
```  

<span data-ttu-id="4f2cf-166">您具有三个连续相互请求的函数。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-166">You have three functions that request each other in succession.</span></span>  

*   `first()`  
*   `second()`  
*   `third()`  
    
<span data-ttu-id="4f2cf-167">每个参数向 `name` 另一个参数发送。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-167">Each sends a `name` argument to the other.</span></span>  <span data-ttu-id="4f2cf-168">在 函数中，检查参数是否存在，如果没有，则记录一 `third()` `name` 个未定义该名称的错误。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-168">In the `third()` function, you check if the `name` argument exists and if it doesn't, you log an error that name isn't defined.</span></span>  <span data-ttu-id="4f2cf-169">如果 `name` 已定义，则使用 方法检查参数是否少于 `assert()` `name` 8 个字母长。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-169">If `name` is defined, you use the `assert()` method to check if the `name` argument is fewer than eight letters long.</span></span>  <span data-ttu-id="4f2cf-170">使用下列 `first()` 参数请求函数三次。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-170">You request the `first()` function three times, with the following parameters.</span></span>  

*   <span data-ttu-id="4f2cf-171">没有在函数 `console.error()` 中触发方法 `third()` 的参数。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-171">No argument that triggers the `console.error()` method in the `third()` function.</span></span>  
*   <span data-ttu-id="4f2cf-172">作为函数参数的术语不会导致错误，因为 `Console` `first()` `name` 参数存在且小于八个字母。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-172">The term `Console` as a parameter to the `first()` function doesn't cause an error because `name` argument exists and is shorter than eight letters.</span></span>  
*   <span data-ttu-id="4f2cf-173">用作 `Microsoft Edge Canary` 函数参数的短语 `first()` 会导致方法报告错误， `console.assert()` 因为参数长于 8 个字母。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-173">The phrase `Microsoft Edge Canary` as a parameter to `first()` function causes the `console.assert()` method to report an error, because the parameter is longer than eight letters.</span></span>  
    
<span data-ttu-id="4f2cf-174">使用 `console.assert()` 方法创建条件错误报告。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-174">Use the `console.assert()` method to create conditional error reports.</span></span>  <span data-ttu-id="4f2cf-175">以下两个示例具有相同的结果，但其中一个示例需要一个额外的 `if{}` 语句。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-175">The following two examples have the same result, but one needs an extra `if{}` statement.</span></span>  

```javascript
let x = 20;
if (x < 40) { console.error(`${x} is too small`) };
console.assert(x >= 40, `${x} is too small`) 
```  

> [!IMPORTANT]
> <span data-ttu-id="4f2cf-176">代码的第二行和第三行执行相同的测试。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-176">The second and third lines of the code perform the same test.</span></span>  <span data-ttu-id="4f2cf-177">由于断言需要记录负结果，因此在案例和 `x < 40` `if` `x >= 40` 断言中进行测试。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-177">Because the assertion needs to record a negative result, you test for `x < 40` in the `if` case and `x >= 40` for the assertion.</span></span>  

<span data-ttu-id="4f2cf-178">如果不确定哪个函数请求另一个函数，请使用 方法跟踪请求获取当前函数 `console.trace()` 的函数。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-178">If you aren't sure which function requests another function, use the `console.trace()` method to track which functions are requested to get to the current one.</span></span>  <span data-ttu-id="4f2cf-179">若要在控制台中显示 **跟踪，** 请导航到在控制台 [中创建跟踪][GithubMicrosoftedgeDevtoolssamplesConsoleTraceHtml]。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-179">To display the trace in the **Console**, navigate to [Creating traces in Console][GithubMicrosoftedgeDevtoolssamplesConsoleTraceHtml].</span></span>  

```javascript
function here() {there()}
function there() {everywhere()}
function everywhere() {
    console.trace();
}
here();
there();
```  

<span data-ttu-id="4f2cf-180">结果是显示名为 的跟踪，然后第二个示例显示为 `here()` `there()` `everywhere()` `everywhere()` 。</span><span class="sxs-lookup"><span data-stu-id="4f2cf-180">The result is a trace to display that `here()` is named `there()` and then `everywhere()` and in the second example that it's named `everywhere()`.</span></span>  

:::image type="complex" source="../media/console-debug-trace.msft.png" alt-text="从控制台创建的跟踪" lightbox="../media/console-debug-trace.msft.png":::
   <span data-ttu-id="4f2cf-182">从控制台创建的 **跟踪**</span><span class="sxs-lookup"><span data-stu-id="4f2cf-182">A trace created from **Console**</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="4f2cf-183">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="4f2cf-183">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamplesConsoleErrorHtml]: https://microsoftedge.github.io/DevToolsSamples/console/error.html "控制台工具控制台中报告的 JavaScript |GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleErrorAssertHtml]: https://microsoftedge.github.io/DevToolsSamples/console/error-assert.html "在控制台控制台中创建错误报告和|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorHtml]: https://microsoftedge.github.io/DevToolsSamples/console/network-error.html "控制台控制台中报告的网络|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorFixedHtml]: https://microsoftedge.github.io/DevToolsSamples/console/network-error-fixed.html "修复了控制台控制台中报告的网络|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleNetworkErrorReportedHtml]: https://microsoftedge.github.io/DevToolsSamples/console/network-error-reported.html "控制台和 UI 服务中的网络错误|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleTraceHtml]: https://microsoftedge.github.io/DevToolsSamples/console/trace.html "在控制台窗口中创建|GitHub"  
