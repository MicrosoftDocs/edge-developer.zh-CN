---
title: 通过 Microsoft Edge DevTools 模拟设备方向
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/26/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 9e8115819fa6c3209a6c82940e033113783ece0c
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607320"
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





# <span data-ttu-id="e3e1e-103">通过 Microsoft Edge DevTools 模拟设备方向</span><span class="sxs-lookup"><span data-stu-id="e3e1e-103">Simulate Device Orientation With Microsoft Edge DevTools</span></span>   



<span data-ttu-id="e3e1e-104">若要模拟 Microsoft Edge DevTools 中的不同设备方向，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e3e1e-104">To simulate different device orientations from Microsoft Edge DevTools:</span></span>  

<!--todo: update device orientation section when available -->  

1.  <span data-ttu-id="e3e1e-105">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "**命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="e3e1e-105">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    > ##### <span data-ttu-id="e3e1e-106">图 1</span><span class="sxs-lookup"><span data-stu-id="e3e1e-106">Figure 1</span></span>  
    > <span data-ttu-id="e3e1e-107">命令菜单</span><span class="sxs-lookup"><span data-stu-id="e3e1e-107">The Command Menu</span></span>  
    > ![命令菜单][ImageCommandMenu]  
    
1.  <span data-ttu-id="e3e1e-109">键入 `sensors` ，选择 "**显示传感器**"，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="e3e1e-109">Type `sensors`, select **Show Sensors**, and press `Enter`.</span></span>  <span data-ttu-id="e3e1e-110">"**传感器**" 选项卡将在 DevTools 窗口底部打开。</span><span class="sxs-lookup"><span data-stu-id="e3e1e-110">The **Sensors** tab opens at the bottom of your DevTools window.</span></span>  
1.  <span data-ttu-id="e3e1e-111">从 "**方向**" 列表中，选择一个预设方向，例如 `Portrait upside down` ，或选择 "**自定义方向**" 以提供您自己的精确方向。</span><span class="sxs-lookup"><span data-stu-id="e3e1e-111">From the **Orientation** list, select one of the preset orientations, such as `Portrait upside down`, or select **Custom orientation** to provide your own exact orientation.</span></span>  
    
    > ##### <span data-ttu-id="e3e1e-112">图 2</span><span class="sxs-lookup"><span data-stu-id="e3e1e-112">Figure 2</span></span>  
    > <span data-ttu-id="e3e1e-113">`Portrait upside down`从 "**方向**" 列表中选择</span><span class="sxs-lookup"><span data-stu-id="e3e1e-113">Selecting `Portrait upside down` from the **Orientation** list</span></span>  
    > ![从 "方向" 列表中选择 "纵向" 倒置][ImageOrientationPortraitUpsideDown]  
    
    <span data-ttu-id="e3e1e-115">选择**自定义方向**后，""、"" 和 "" `alpha` 字段已 `beta` `gamma` 启用。</span><span class="sxs-lookup"><span data-stu-id="e3e1e-115">After selecting **Custom orientation**, the `alpha`, `beta`, and `gamma` fields are enabled.</span></span>  
    <!--See [Alpha][alpha], [Beta][beta], and [Gamma][gamma] to understand how these axes work.  -->  
    <!--todo: update links to alpha, beta, and gamma section when available -->  
    <span data-ttu-id="e3e1e-116">您还可以通过拖动**方向模型**来设置自定义方向。</span><span class="sxs-lookup"><span data-stu-id="e3e1e-116">You are also able to set a custom orientation by dragging the **Orientation Model**.</span></span>  <span data-ttu-id="e3e1e-117">按住 `Shift` ，然后拖动鼠标沿 `alpha` 轴旋转。</span><span class="sxs-lookup"><span data-stu-id="e3e1e-117">Hold `Shift` before dragging to rotate along the `alpha` axis.</span></span>  
    
    > ##### <span data-ttu-id="e3e1e-118">图 3</span><span class="sxs-lookup"><span data-stu-id="e3e1e-118">Figure 3</span></span>  
    > <span data-ttu-id="e3e1e-119">**方向模型**</span><span class="sxs-lookup"><span data-stu-id="e3e1e-119">The **Orientation Model**</span></span>  
    > ![方向模型][ImageOrientationModel]  

<!--## Feedback   -->  



<!-- image links -->  

[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/device-mode-console-command-menu.msft.png "图1：命令菜单"  
[ImageOrientationPortraitUpsideDown]: /microsoft-edge/devtools-guide-chromium/media/device-mode-console-sensors-orientation-portrait-upside-down.msft.png "图2：从 "方向" 列表中选择 "纵向" 倒置"  
[ImageOrientationModel]: /microsoft-edge/devtools-guide-chromium/media/device-mode-console-sensors-orientation-custom.msft.png "图3：方向模型"  

<!-- links -->  

<!--[WebFundamentasNativeHardwareDeviceOrientationIndex]: /web/fundamentals/native-hardware/device-orientation/index "Device Orientation \& Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexAlpha]: /web/fundamentals/native-hardware/device-orientation/index#alpha "Alpha - Device Orientation \& Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexBeta]: /web/fundamentals/native-hardware/device-orientation/index#beta "Beta - Device Orientation \& Motion"  -->  
<!--[WebFundamentasNativeHardwareDeviceOrientationIndexGamma]: /web/fundamentals/native-hardware/device-orientation/index#gamma "Gamma - Device Orientation \& Motion"  -->  

> [!NOTE]
> <span data-ttu-id="e3e1e-124">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="e3e1e-124">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e3e1e-125">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/orientation)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="e3e1e-125">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/orientation) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="e3e1e-127">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="e3e1e-127">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
