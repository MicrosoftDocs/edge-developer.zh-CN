---
title: 自定义 Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 42c1cce2ca26c81b0482429cface83f09e34f5df
ms.sourcegitcommit: 67ce64f810afdb304844bae0f3918d4e9108dcec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2020
ms.locfileid: "10601351"
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





# <span data-ttu-id="499ff-103">自定义 Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="499ff-103">Customize Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="499ff-104">此页面列出了自定义 Microsoft Edge DevTools 的方法。</span><span class="sxs-lookup"><span data-stu-id="499ff-104">This page lists the ways to customize Microsoft Edge DevTools.</span></span>  

## <span data-ttu-id="499ff-105">“设置”</span><span class="sxs-lookup"><span data-stu-id="499ff-105">Settings</span></span>   

<span data-ttu-id="499ff-106">**设置**  > **首选项**包含用于自定义 DevTools 的许多选项。</span><span class="sxs-lookup"><span data-stu-id="499ff-106">**Settings** > **Preferences** contains many options for customizing DevTools.</span></span>  

<span data-ttu-id="499ff-107">若要打开 "设置"，请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="499ff-107">To open Settings, do one of the following:</span></span>  

*   <span data-ttu-id="499ff-108">`F1`当 DevTools 处于焦点时按下。</span><span class="sxs-lookup"><span data-stu-id="499ff-108">Press `F1` while DevTools is in focus.</span></span>  
*   <span data-ttu-id="499ff-109">打开**主菜单**，然后选择 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="499ff-109">Open the **Main Menu** and then select **Settings**.</span></span>  

> ##### <span data-ttu-id="499ff-110">图 1</span><span class="sxs-lookup"><span data-stu-id="499ff-110">Figure 1</span></span>  
> <span data-ttu-id="499ff-111">设置</span><span class="sxs-lookup"><span data-stu-id="499ff-111">Settings</span></span>  
> ![设置][ImageSettings]  

## <span data-ttu-id="499ff-113">箱</span><span class="sxs-lookup"><span data-stu-id="499ff-113">Drawer</span></span>   

<span data-ttu-id="499ff-114">**抽屉**包含许多隐藏的功能。</span><span class="sxs-lookup"><span data-stu-id="499ff-114">The **Drawer** contains many hidden features.</span></span>  

<span data-ttu-id="499ff-115">按 " `Escape` 打开" 或 "关闭" 抽屉。</span><span class="sxs-lookup"><span data-stu-id="499ff-115">Press `Escape` to open or close the Drawer.</span></span>  

> ##### <span data-ttu-id="499ff-116">图 2</span><span class="sxs-lookup"><span data-stu-id="499ff-116">Figure 2</span></span>  
> <span data-ttu-id="499ff-117">抽屉</span><span class="sxs-lookup"><span data-stu-id="499ff-117">The Drawer</span></span>  
> ![抽屉][ImageDrawerExample]  

<span data-ttu-id="499ff-119">单击 "**更** ![ 多" ][ImageMoreIcon] 以打开其他抽屉选项卡。</span><span class="sxs-lookup"><span data-stu-id="499ff-119">Click **More** ![More][ImageMoreIcon]  to open other Drawer tabs.</span></span>  

> ##### <span data-ttu-id="499ff-120">图 3</span><span class="sxs-lookup"><span data-stu-id="499ff-120">Figure 3</span></span>  
> <span data-ttu-id="499ff-121">用于打开抽屉卡舌的按钮</span><span class="sxs-lookup"><span data-stu-id="499ff-121">The button for opening Drawer tabs</span></span>  
> ![用于打开抽屉卡舌的按钮][ImageMoreDrawerTabs]  

## <span data-ttu-id="499ff-123">重新排序面板</span><span class="sxs-lookup"><span data-stu-id="499ff-123">Reorder panels</span></span>   

<span data-ttu-id="499ff-124">单击并拖动 "面板" 选项卡以更改其排序。</span><span class="sxs-lookup"><span data-stu-id="499ff-124">Click and drag a panel tab to change its ordering.</span></span>  <span data-ttu-id="499ff-125">您的自定义 tab 键顺序在 DevTools 会话中保持不变。</span><span class="sxs-lookup"><span data-stu-id="499ff-125">Your custom tab order persists across DevTools sessions.</span></span>  

> [!NOTE]
> <span data-ttu-id="499ff-126">默认情况下，"网络面板" 选项卡通常是从左侧起的第四个选项卡。</span><span class="sxs-lookup"><span data-stu-id="499ff-126">By default, the Network panel tab is usually the fourth from the left.</span></span>  <span data-ttu-id="499ff-127">在[图 4](#figure-4)中，它是第一个左侧。</span><span class="sxs-lookup"><span data-stu-id="499ff-127">In [Figure 4](#figure-4), it is the first from the left.</span></span>  

> ##### <span data-ttu-id="499ff-128">图 4</span><span class="sxs-lookup"><span data-stu-id="499ff-128">Figure 4</span></span>  
> <span data-ttu-id="499ff-129">具有自定义 tab 键顺序的 DevTools 窗口</span><span class="sxs-lookup"><span data-stu-id="499ff-129">A DevTools window with a custom tab ordering</span></span>    
> ![具有自定义面板选项卡排序的 DevTools 窗口][ImageCustomTabOrdering]  

## <span data-ttu-id="499ff-131">更改 DevTools 位置</span><span class="sxs-lookup"><span data-stu-id="499ff-131">Change DevTools placement</span></span>   

<span data-ttu-id="499ff-132">请参阅[Microsoft Edge DevTools 放置][DevToolsPlacement]。</span><span class="sxs-lookup"><span data-stu-id="499ff-132">See [Microsoft Edge DevTools Placement][DevToolsPlacement].</span></span>  

> ##### <span data-ttu-id="499ff-133">图 5</span><span class="sxs-lookup"><span data-stu-id="499ff-133">Figure 5</span></span>  
> <span data-ttu-id="499ff-134">取消停靠 DevTools</span><span class="sxs-lookup"><span data-stu-id="499ff-134">Undocked DevTools</span></span>  
> ![取消停靠 DevTools][ImageUndock]  

## <span data-ttu-id="499ff-136">深色主题</span><span class="sxs-lookup"><span data-stu-id="499ff-136">Dark theme</span></span>   

<span data-ttu-id="499ff-137">请参阅[启用深色主题][DarkTheme]。</span><span class="sxs-lookup"><span data-stu-id="499ff-137">See [Enable Dark Theme][DarkTheme].</span></span>  

> ##### <span data-ttu-id="499ff-138">图 6</span><span class="sxs-lookup"><span data-stu-id="499ff-138">Figure 6</span></span>  
> <span data-ttu-id="499ff-139">深色主题</span><span class="sxs-lookup"><span data-stu-id="499ff-139">The dark theme</span></span>  
> ![深色主题][ImageDarkTheme]  

## <span data-ttu-id="499ff-141">试验</span><span class="sxs-lookup"><span data-stu-id="499ff-141">Experiments</span></span>   

<span data-ttu-id="499ff-142">要启用 DevTools 实验，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="499ff-142">To enable DevTools experiments:</span></span>  

1.  <span data-ttu-id="499ff-143">转到 `edge://flags/#enable-devtools-experiments` 。</span><span class="sxs-lookup"><span data-stu-id="499ff-143">Go to `edge://flags/#enable-devtools-experiments`.</span></span>  
1.  <span data-ttu-id="499ff-144">单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="499ff-144">Click **Enable**.</span></span>  
1.  <span data-ttu-id="499ff-145">单击页面底部的 "**立即重新启动**"。</span><span class="sxs-lookup"><span data-stu-id="499ff-145">Click **Relaunch Now**, at the bottom of the page.</span></span>  

<span data-ttu-id="499ff-146">下次打开 DevTools 时，将在 "[设置](#settings)" 中显示一个名为 "**实验**" 的新页面。</span><span class="sxs-lookup"><span data-stu-id="499ff-146">The next time you open DevTools, a new page is displayed called **Experiments** in [Settings](#settings).</span></span>  

   

  

<!-- image links -->  

[ImageMoreIcon]: /microsoft-edge/devtools-guide-chromium/media/more-icon.msft.png  

[ImageSettings]: /microsoft-edge/devtools-guide-chromium/media/customize-settings-preferences.msft.png "图1：设置"  
[ImageDrawerExample]: /microsoft-edge/devtools-guide-chromium/media/customize-drawer-open.msft.png "图2：抽屉"  
[ImageMoreDrawerTabs]: /microsoft-edge/devtools-guide-chromium/media/customize-drawer-open-more-tools.msft.png "图3：用于打开抽屉卡舌的按钮"  
[ImageCustomTabOrdering]: /microsoft-edge/devtools-guide-chromium/media/customize-network-first-position.msft.png "图4：具有自定义面板选项卡排序的 DevTools 窗口"  
[ImageUndock]: /microsoft-edge/devtools-guide-chromium/media/customize-dev-tools-dock-side.msft.png "图5：未插接 DevTools"  
[ImageDarkTheme]: /microsoft-edge/devtools-guide-chromium/media/customize-settings-appearance-theme.msft.png "图6：深色主题"  

<!-- links -->  

[DevToolsPlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "更改 Microsoft Edge DevTools 位置（"取消停靠"、"停靠到底部"、"停靠到左侧"）"  
[DarkTheme]: /microsoft-edge/devtools-guide-chromium/customize/dark-theme "在 Microsoft Edge DevTools 中启用深色主题"  

> [!NOTE]
> <span data-ttu-id="499ff-155">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="499ff-155">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="499ff-156">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/customize/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="499ff-156">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/customize/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="499ff-158">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="499ff-158">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
