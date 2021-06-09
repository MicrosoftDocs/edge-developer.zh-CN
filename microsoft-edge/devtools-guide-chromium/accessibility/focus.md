---
description: 打开控制台，创建一个动态表达式，然后将表达式设置为document.activeElement。
title: 跟踪哪些元素有焦点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: 2fd53caccefefb0b0bce4b5c82f30632e11a3cb6
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597109"
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
# <a name="track-which-element-has-focus"></a><span data-ttu-id="f3216-104">跟踪哪些元素有焦点</span><span class="sxs-lookup"><span data-stu-id="f3216-104">Track which element has focus</span></span>  

<span data-ttu-id="f3216-105">假设正在测试页面的键盘导航辅助功能。</span><span class="sxs-lookup"><span data-stu-id="f3216-105">Suppose that you are testing the keyboard navigation accessibility of a page.</span></span>  <span data-ttu-id="f3216-106">使用`Tab`键浏览页面时，聚焦环有时会消失，因为具有焦点的元素被隐藏。</span><span class="sxs-lookup"><span data-stu-id="f3216-106">When navigating the page with the `Tab` key, the focus ring sometimes disappears because the element that has focus is hidden.</span></span>  

<span data-ttu-id="f3216-107">若要跟踪 DevTools 中聚焦的元素：</span><span class="sxs-lookup"><span data-stu-id="f3216-107">To track the focused element in DevTools:</span></span>

1.  <span data-ttu-id="f3216-108">打开“**控制台**”。</span><span class="sxs-lookup"><span data-stu-id="f3216-108">Open the **Console**.</span></span>  
1.  <span data-ttu-id="f3216-109">Choose **Create live expression** \ (Create live expression ![ ](../media/create-live-expression-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="f3216-109">Choose **Create live expression** \(![Create live expression](../media/create-live-expression-icon.msft.png)\).</span></span>  
    
    :::image type="complex" source="../media/accessibility-console-create-live-expression-empty.msft.png" alt-text="创建动态表达式" lightbox="../media/accessibility-console-create-live-expression-empty.msft.png":::
       <span data-ttu-id="f3216-111">创建动态表达式</span><span class="sxs-lookup"><span data-stu-id="f3216-111">Create a Live Expression</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f3216-112">键入 `document.activeElement`。</span><span class="sxs-lookup"><span data-stu-id="f3216-112">Type `document.activeElement`.</span></span>  
1.  <span data-ttu-id="f3216-113">若要保存表达式，请选择活动表达式外部。</span><span class="sxs-lookup"><span data-stu-id="f3216-113">To save the expression, select outside of the live expression.</span></span>
    
<span data-ttu-id="f3216-114">`document.activeElement` 下面显示的值是表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="f3216-114">The value displayed below `document.activeElement` is the result of the expression.</span></span>  

<span data-ttu-id="f3216-115">由于该表达式始终代表着焦点的元素，因此现在可以始终跟踪哪个元素具有焦点。</span><span class="sxs-lookup"><span data-stu-id="f3216-115">Since that expression always represents the focused element, you now have a way to always keep track of which element has focus.</span></span>  

*   <span data-ttu-id="f3216-116">将鼠标悬停在结果上，以在视区中突出显示焦点元素。</span><span class="sxs-lookup"><span data-stu-id="f3216-116">Hover on the result to highlight the focused element in the viewport.</span></span>  
*   <span data-ttu-id="f3216-117">将鼠标悬停在结果上，打开上下文菜单 \(右键单击\) ，然后选择“**在元素面板显示**”以在“**元素**”工具上显示 DOM 树中的元素。</span><span class="sxs-lookup"><span data-stu-id="f3216-117">Hover on the result, open the contextual menu \(right-click\), and choose **Reveal in Elements panel** to show the element in the DOM Tree on the **Elements** tool.</span></span>  
*   <span data-ttu-id="f3216-118">将鼠标悬停在结果上，打开上下文菜单 \(右键单击\)，然后选择“**存储为全局变量**”，以创建对可以在**控制台**中所使用节点的变量引用。</span><span class="sxs-lookup"><span data-stu-id="f3216-118">Hover on the result, open the contextual menu \(right-click\), and choose **Store as global variable** to create a variable reference to the node that you are able to use in the **Console**.</span></span>  


## <a name="see-also"></a><span data-ttu-id="f3216-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3216-119">See also</span></span>

*  [<span data-ttu-id="f3216-120">分析边栏菜单中键盘焦点的缺失</span><span class="sxs-lookup"><span data-stu-id="f3216-120">Analyze the lack of indication of keyboard focus in a sidebar menu</span></span>](test-analyze-no-focus-indicator.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="f3216-121">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="f3216-121">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->  
> [!NOTE]
> <span data-ttu-id="f3216-122">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f3216-122">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f3216-123">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="f3216-123">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f3216-125">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f3216-125">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
