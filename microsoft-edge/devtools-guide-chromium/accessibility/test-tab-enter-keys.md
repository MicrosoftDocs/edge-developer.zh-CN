---
description: 使用 Tab 键和 Enter 键检查键盘支持。
title: 使用 Tab 和 Enter 键检查键盘支持
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 48151e16a9059b5ebaadca36f29447d4ad3be8c7
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597248"
---
# <a name="check-for-keyboard-support-by-using-the-tab-and-enter-keys"></a><span data-ttu-id="53e43-104">使用 Tab 和 Enter 键检查键盘支持</span><span class="sxs-lookup"><span data-stu-id="53e43-104">Check for keyboard support by using the Tab and Enter keys</span></span>


<span data-ttu-id="53e43-105">并非所有用户都有指针或触摸设备，并且并非所有用户都可以查看我们创建的 Web 项目。</span><span class="sxs-lookup"><span data-stu-id="53e43-105">Not all users have a pointer or touch device, and not all users can see the web projects we create.</span></span>  <span data-ttu-id="53e43-106">这就是为什么用户界面至少与键盘一起工作非常重要的原因。</span><span class="sxs-lookup"><span data-stu-id="53e43-106">This is why it is important that the user interface works at least with a keyboard.</span></span>  <span data-ttu-id="53e43-107">确保可以使用键将焦点移到网页上的每个表单控件，并确保可以使用该键 `Tab` `Enter` 提交表单。</span><span class="sxs-lookup"><span data-stu-id="53e43-107">Ensure you can use the `Tab` key to move the focus to each form control on a webpage, and ensure you can use the `Enter` key to submit forms.</span></span>

<span data-ttu-id="53e43-108">可以通过多种方式测试键盘用户的网页可用性：</span><span class="sxs-lookup"><span data-stu-id="53e43-108">You can test the usability of a webpage for keyboard users in several ways:</span></span>
*  <span data-ttu-id="53e43-109">通过使用键盘，尤其是 、 `Tab` `Shift` + `Tab` 和 `Enter` 键。</span><span class="sxs-lookup"><span data-stu-id="53e43-109">By using the keyboard, particularly the `Tab`, `Shift`+`Tab`, and `Enter` keys.</span></span>  <span data-ttu-id="53e43-110">本文中介绍了此方法。</span><span class="sxs-lookup"><span data-stu-id="53e43-110">This approach is described in this article.</span></span>
*  <span data-ttu-id="53e43-111">使用 Inspect 工具检查单个元素的 **键盘** 支持。</span><span class="sxs-lookup"><span data-stu-id="53e43-111">Check for keyboard support for an individual element by using the **Inspect** tool.</span></span>  <span data-ttu-id="53e43-112">检查工具的信息覆盖包括一个 **辅助功能** 部分，其中包括 **一个键盘可聚焦** 的行。</span><span class="sxs-lookup"><span data-stu-id="53e43-112">The Inspect tool's information overlay includes an **Accessibility** section that includes a **Keyboard-focusable** row.</span></span>  
*  <span data-ttu-id="53e43-113">检查 **问题报告的** 辅助功能 **部分** ，了解键盘支持问题。</span><span class="sxs-lookup"><span data-stu-id="53e43-113">Check the **Issues** report's **Accessibility** section for keyboard support issues.</span></span>

<span data-ttu-id="53e43-114">若要使用键盘而不是鼠标检查演示页面的辅助功能问题，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="53e43-114">To check the demo page for accessibility issues by using a keyboard rather than a mouse, perform the following steps:</span></span>

1.  <span data-ttu-id="53e43-115">在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页。</span><span class="sxs-lookup"><span data-stu-id="53e43-115">Open the [accessibility-testing demo webpage][DevToolsA11yErrorsDemopage] in a new tab of the browser.</span></span>

1.  <span data-ttu-id="53e43-116">使用键盘导航演示文档，使用 `Tab` 和 `Shift` + `Tab` 键从元素跳到另一个元素。</span><span class="sxs-lookup"><span data-stu-id="53e43-116">Use a keyboard to navigate the demo document, using the `Tab` and `Shift`+`Tab` keys to jump from element to element.</span></span>  <span data-ttu-id="53e43-117">在演示网页上， `Tab` 该密钥首先将焦点移到部分中的搜索 `header` 表单。</span><span class="sxs-lookup"><span data-stu-id="53e43-117">On the demo webpage, the `Tab` key first moves focus to the search form in the `header` section.</span></span>

1.  <span data-ttu-id="53e43-118">选择 `Tab` 以将焦点放在按钮上，然后选择单击 `Enter` 聚焦按钮。</span><span class="sxs-lookup"><span data-stu-id="53e43-118">Select `Tab` to put focus on a button, and then select `Enter` to click the focused button.</span></span>  <span data-ttu-id="53e43-119">例如，在演示页面中，选择将焦点放在"搜索" `Tab` 字段\*\*\*\* 上，然后选择 `Enter` 提交搜索。</span><span class="sxs-lookup"><span data-stu-id="53e43-119">For example, in the demo page, select `Tab` to put focus on the **Search** field, and then select `Enter` to submit the search.</span></span>  <span data-ttu-id="53e43-120">此方法将产生与选择"开始" **按钮相同的结果** 。</span><span class="sxs-lookup"><span data-stu-id="53e43-120">This approach produces the same result as selecting the **go** button.</span></span>  <span data-ttu-id="53e43-121">选择 `Enter` 发送搜索 **表单** 可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="53e43-121">Selecting `Enter` to send the **Search** form works correctly.</span></span>

1.  <span data-ttu-id="53e43-122">再次 `Tab` 选择。</span><span class="sxs-lookup"><span data-stu-id="53e43-122">Select `Tab` again.</span></span>  <span data-ttu-id="53e43-123">您重点关注的下一个元素是网页部分中的第一个 **"** 更多"链接， `content` 如大纲所指示。</span><span class="sxs-lookup"><span data-stu-id="53e43-123">The next element you put focus on is the first **More** link in the `content` section of the webpage, as indicated by an outline.</span></span>
    
    :::image type="complex" source="../media/a11y-testing-keyboard-focus-on-element.msft.png" alt-text="使用键盘和"Tab"键导航文档。 <span data-ttu-id="53e43-125">焦点显示在文档中的链接上。</span><span class="sxs-lookup"><span data-stu-id="53e43-125">Focus is shown on a link in the document.</span></span>" lightbox="../media/a11y-testing-keyboard-focus-on-element.msft.png":::
        <span data-ttu-id="53e43-126">使用键盘和 Tab 键导航文档。</span><span class="sxs-lookup"><span data-stu-id="53e43-126">Navigating the document using the keyboard and the tab key.</span></span> <span data-ttu-id="53e43-127">焦点显示在文档中的链接上。</span><span class="sxs-lookup"><span data-stu-id="53e43-127">Focus is shown on a link in the document.</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="53e43-128">多次 `Tab` 选择，直到传递最后一个 **"更多"** 链接。</span><span class="sxs-lookup"><span data-stu-id="53e43-128">Select `Tab` several more times until you pass the last **More** link.</span></span>  <span data-ttu-id="53e43-129">页面向上滚动，你似乎位于页面的某个元素上，但无法判断它是哪个元素。</span><span class="sxs-lookup"><span data-stu-id="53e43-129">The page scrolls up and you seem to be on an element of the page, but there's no way to tell which element it is.</span></span>

1.  <span data-ttu-id="53e43-130">请注意左下角的 URL。</span><span class="sxs-lookup"><span data-stu-id="53e43-130">Notice the URL in the bottom left.</span></span>  <span data-ttu-id="53e43-131">如果你查看屏幕左侧的左下角 (或者如果你使用屏幕阅读器) ，你意识到你位于带蓝色链接的边栏导航菜单上，因为浏览器显示"猫"链接指向 (\*\*\*\* `#cats`) 的 URL。</span><span class="sxs-lookup"><span data-stu-id="53e43-131">If you look to the bottom left of the screen (or if you use a screen reader), you realize that you are on the sidebar navigation menu with blue links, because the browser shows the URL that the **Cats** link points to (`#cats`).</span></span>

    :::image type="complex" source="../media/a11y-testing-lack-of-focus-style.msft.png" alt-text="缺少焦点样式使无法知道您当前在文档中的什么位置。 唯一的提示是在屏幕左下角显示链接目标" lightbox="../media/a11y-testing-lack-of-focus-style.msft.png":::
        <span data-ttu-id="53e43-134">缺少焦点样式使无法知道您当前在文档中的什么位置。</span><span class="sxs-lookup"><span data-stu-id="53e43-134">A lack of focus style makes it impossible to know where you currently are in the document.</span></span> <span data-ttu-id="53e43-135">唯一的提示是在屏幕左下角显示链接目标。</span><span class="sxs-lookup"><span data-stu-id="53e43-135">The only hint is the display of the link target in the bottom left corner of the screen.</span></span>
    :::image-end:::

1.  <span data-ttu-id="53e43-136">再次 `Tab` 选择，以到达"捐赠"窗体中的条目字段。</span><span class="sxs-lookup"><span data-stu-id="53e43-136">Select `Tab` again, to get to the entry field in the donation form.</span></span>  <span data-ttu-id="53e43-137">但是，无法通过选择 到达文本框上方的按钮 `Tab` 。</span><span class="sxs-lookup"><span data-stu-id="53e43-137">However, you can't reach the buttons above the textbox by selecting `Tab`.</span></span> <span data-ttu-id="53e43-138">你不能使用键盘将焦点放在**50、100**或**200**按钮上，然后选择它们。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="53e43-138">You can't use the keyboard to put focus on the **50**, **100**, or **200** buttons and then select them.</span></span>  <span data-ttu-id="53e43-139">此外， `Enter` 选择时不会提交该资金申请。</span><span class="sxs-lookup"><span data-stu-id="53e43-139">Also, selecting `Enter` doesn't submit the donation form.</span></span>

    :::image type="complex" source="../media/a11y-testing-form-field-with-outline.msft.png" alt-text="在资金表单中，唯一一个可通过键盘访问的元素是文本输入字段" lightbox="../media/a11y-testing-form-field-with-outline.msft.png":::
        <span data-ttu-id="53e43-141">在资金表单中，唯一一个可通过键盘访问的元素是文本输入字段</span><span class="sxs-lookup"><span data-stu-id="53e43-141">The only keyboard-accessible element in the donation form is the text entry field</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="53e43-142">再次选择会将焦点放在页面的顶部导航栏上，并包含"主页"、"采用一只猫"、"我的产品"、"作业"和"关于 `Tab` **我们"的菜单按钮**。 \*\*\*\* \*\*\*\* \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="53e43-142">Selecting `Tab` again puts focus on the top navigation bar of the page, with menu buttons for **Home**, **Adopt a Pet**, **Donate**, **Jobs**, and **About Us**.</span></span>  <span data-ttu-id="53e43-143">选择 `Tab` 或 `Shift` + `Tab` 将焦点放在菜单按钮上，如焦点轮廓所指示。</span><span class="sxs-lookup"><span data-stu-id="53e43-143">Select `Tab` or `Shift`+`Tab` to put focus on a menu button, as indicated by a focus outline.</span></span>  <span data-ttu-id="53e43-144">然后选择 `Enter` 以访问网页的该部分。</span><span class="sxs-lookup"><span data-stu-id="53e43-144">Then select `Enter` to access that section of the webpage.</span></span>

    :::image type="complex" source="../media/a11y-testing-menu-with-outline.msft.png" alt-text="主菜单具有突出显示和焦点轮廓，因此键盘可访问" lightbox="../media/a11y-testing-menu-with-outline.msft.png":::
        <span data-ttu-id="53e43-146">主菜单具有突出显示和焦点轮廓，因此键盘可访问</span><span class="sxs-lookup"><span data-stu-id="53e43-146">The main menu has a highlight and a focus outline, and thus is keyboard-accessible</span></span>
    :::image-end:::
    
<span data-ttu-id="53e43-147">基于上述演练，我们发现需要修复的以下问题。</span><span class="sxs-lookup"><span data-stu-id="53e43-147">Based on the above walkthrough, we found the following issues that need to be fixed.</span></span>

*  <span data-ttu-id="53e43-148">使用键盘时，边栏导航菜单的蓝色链接不会直观地指示哪个链接具有焦点。</span><span class="sxs-lookup"><span data-stu-id="53e43-148">When using a keyboard, the blue links of the sidebar navigation menu don't visually indicate which link has focus.</span></span>  <span data-ttu-id="53e43-149">有关详细信息，请导航到分析边栏菜单中缺少 [键盘焦点的指示](test-analyze-no-focus-indicator.md)。</span><span class="sxs-lookup"><span data-stu-id="53e43-149">For more information, navigate to [Analyze the lack of indication of keyboard focus in a sidebar menu](test-analyze-no-focus-indicator.md).</span></span>

*  <span data-ttu-id="53e43-150">在"资金"表单中，金额按钮和 **"四** 分百"按钮不能与键盘一起使用。</span><span class="sxs-lookup"><span data-stu-id="53e43-150">In the donation form, the amount buttons and the **Donate** button don't work with a keyboard.</span></span>  <span data-ttu-id="53e43-151">有关详细信息，请导航到 [分析表单中缺少键盘支持](test-analyze-no-keyboard-support.md)。</span><span class="sxs-lookup"><span data-stu-id="53e43-151">For more information, navigate to [Analyze the lack of keyboard support in a form](test-analyze-no-keyboard-support.md).</span></span>

*  <span data-ttu-id="53e43-152">键盘通过页面各部分访问的顺序不正确。</span><span class="sxs-lookup"><span data-stu-id="53e43-152">The order of the keyboard access through sections of the page is not correct.</span></span>  <span data-ttu-id="53e43-153">在到达 **边栏导航** 菜单之前，可以浏览文档中的所有"更多"链接。</span><span class="sxs-lookup"><span data-stu-id="53e43-153">You navigate through all the **More** links in the document before you reach the sidebar navigation menu.</span></span>  <span data-ttu-id="53e43-154">当键将焦点放在边栏导航菜单上时 `Tab` ，你已遍历所有页面内容。</span><span class="sxs-lookup"><span data-stu-id="53e43-154">By the time the `Tab` key puts focus on the sidebar navigation menu, you have already traversed all the page content.</span></span> <span data-ttu-id="53e43-155">边栏导航菜单旨在提供对页面内容的轻松访问。</span><span class="sxs-lookup"><span data-stu-id="53e43-155">The sidebar navigation menu was intended to provide easy access to the page content.</span></span>  <span data-ttu-id="53e43-156">若要详细了解如何解决此问题，请导航到使用源订单查看器 [测试键盘支持](test-tab-key-source-order-viewer.md)。</span><span class="sxs-lookup"><span data-stu-id="53e43-156">For more information on how to solve this issue, navigate to [Test keyboard support using the Source Order Viewer](test-tab-key-source-order-viewer.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="53e43-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53e43-157">See also</span></span>

*  [<span data-ttu-id="53e43-158">使用 DevTools 的辅助功能测试概述</span><span class="sxs-lookup"><span data-stu-id="53e43-158">Overview of accessibility testing using DevTools</span></span>](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="53e43-159">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="53e43-159">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
