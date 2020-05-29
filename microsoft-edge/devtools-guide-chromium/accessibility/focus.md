---
title: 跟踪哪个元素具有焦点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: a1bcb7e97357d1348b363ecd4842d1b6a78feb45
ms.sourcegitcommit: 8bfa239274e7a4856b961b9cf163b08d96463c10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "10581529"
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





# <span data-ttu-id="545d1-103">跟踪哪个元素具有焦点</span><span class="sxs-lookup"><span data-stu-id="545d1-103">Track Which Element Has Focus</span></span>   



<span data-ttu-id="545d1-104">假设你要测试页面的键盘导航辅助功能。</span><span class="sxs-lookup"><span data-stu-id="545d1-104">Suppose that you are testing the keyboard navigation accessibility of a page.</span></span>  <span data-ttu-id="545d1-105">当在页面 `Tab` 上导航键时，焦点圆圈有时会消失，因为具有焦点的元素已隐藏。</span><span class="sxs-lookup"><span data-stu-id="545d1-105">When navigating the page with the `Tab` key, the focus ring sometimes disappears because the element that has focus is hidden.</span></span>  <span data-ttu-id="545d1-106">在 DevTools 中跟踪重点元素：</span><span class="sxs-lookup"><span data-stu-id="545d1-106">To track the focused element in DevTools:</span></span>  

1.  <span data-ttu-id="545d1-107">打开**控制台**。</span><span class="sxs-lookup"><span data-stu-id="545d1-107">Open the **Console**.</span></span>  
1.  <span data-ttu-id="545d1-108">单击 "**创建实时表达式**" ![ 创建实时表达式 ][ImageCreateIcon] 。</span><span class="sxs-lookup"><span data-stu-id="545d1-108">Click **Create Live Expression** ![Create Live Expression][ImageCreateIcon].</span></span>  

    > ##### <span data-ttu-id="545d1-109">图 1</span><span class="sxs-lookup"><span data-stu-id="545d1-109">Figure 1</span></span>  
    > <span data-ttu-id="545d1-110">创建**实时表达式**</span><span class="sxs-lookup"><span data-stu-id="545d1-110">Creating a **Live Expression**</span></span>  
    > ![创建实时表达式][ImageLiveExpression]  
    
1.  <span data-ttu-id="545d1-112">键入 `document.activeElement`。</span><span class="sxs-lookup"><span data-stu-id="545d1-112">Type `document.activeElement`.</span></span>
1.  <span data-ttu-id="545d1-113">在要保存的**实时表达式**UI 外部单击。</span><span class="sxs-lookup"><span data-stu-id="545d1-113">Click outside of the **Live Expression** UI to save.</span></span>

<span data-ttu-id="545d1-114">下面看到的值 `document.activeElement` 是表达式的结果。</span><span class="sxs-lookup"><span data-stu-id="545d1-114">The value that you see below `document.activeElement` is the result of the expression.</span></span>  
<span data-ttu-id="545d1-115">由于该表达式始终表示焦点元素，因此你现在可以始终跟踪哪个元素具有焦点。</span><span class="sxs-lookup"><span data-stu-id="545d1-115">Since that expression always represents the focused element, you now have a way to always keep track of which element has focus.</span></span>  

*   <span data-ttu-id="545d1-116">将鼠标悬停在结果上以突出显示视区中的焦点元素。</span><span class="sxs-lookup"><span data-stu-id="545d1-116">Hover over the result to highlight the focused element in the viewport.</span></span>  
*   <span data-ttu-id="545d1-117">右键单击结果，然后在 **"元素" 面板中选择 "显示**"，以在 "**元素**" 面板上的 DOM 树中显示该元素。</span><span class="sxs-lookup"><span data-stu-id="545d1-117">Right-click the result and select **Reveal in Elements panel** to show the element in the DOM Tree on the **Elements** panel.</span></span>  
*   <span data-ttu-id="545d1-118">右键单击结果，然后选择 "**存储为全局变量**"，创建对可以在**控制台**中使用的节点的变量引用。</span><span class="sxs-lookup"><span data-stu-id="545d1-118">Right-click the result and select **Store as global variable** to create a variable reference to the node that you are able to use in the **Console**.</span></span>  

<!--## Feedback   -->  



<!-- image links -->  

[ImageCreateIcon]: /microsoft-edge/devtools-guide-chromium/media/create-live-expression-icon.msft.png  

[ImageLiveExpression]: /microsoft-edge/devtools-guide-chromium/media/accessibility-console-create-live-expression-empty.msft.png "图1：创建实时表达式"  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="545d1-120">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="545d1-120">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="545d1-121">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="545d1-121">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="545d1-123">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="545d1-123">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
