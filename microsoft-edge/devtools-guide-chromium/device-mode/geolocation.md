---
description: 打开传感器工具，然后从"地理位置"列表中选择坐标。
title: 使用 DevTools Microsoft Edge地理位置
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 5e162d5591dec4013a899a16b0c56fd09d58610f
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564327"
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
# <a name="override-geolocation-with-microsoft-edge-devtools"></a><span data-ttu-id="94014-104">使用 DevTools Microsoft Edge地理位置</span><span class="sxs-lookup"><span data-stu-id="94014-104">Override geolocation with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="94014-105">许多网站利用用户位置来为用户提供更相关的体验。</span><span class="sxs-lookup"><span data-stu-id="94014-105">Many websites take advantage of user location in order to provide a more relevant experience for the users.</span></span>  <span data-ttu-id="94014-106">例如，在用户授予网站访问当前用户位置的权限后，天气网站可能会显示用户区域中的本地天气预报。</span><span class="sxs-lookup"><span data-stu-id="94014-106">For example, a weather website may show the local forecast in a user's area, after the user has granted the website permission to access the current user location.</span></span>  

<!--todo: add link to user location section when available -->  

<span data-ttu-id="94014-107">如果您要构建的 UI 根据用户所在的位置而更改，您可能需要确保网站在世界各地的不同位置正常运行。</span><span class="sxs-lookup"><span data-stu-id="94014-107">If you are building a UI that changes depending on where the user is located, you probably want to make sure that the site behaves correctly in different places around the world.</span></span>  <span data-ttu-id="94014-108">若要在 DevTools 中Microsoft Edge地理位置，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="94014-108">To override your geolocation in Microsoft Edge DevTools, complete the following actions.</span></span>  

1.  <span data-ttu-id="94014-109">选择 `Control`+`Shift`+`P` \(Windows、Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开**命令菜单**。</span><span class="sxs-lookup"><span data-stu-id="94014-109">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-command-menu.msft.png" alt-text="命令菜单" lightbox="../media/device-mode-console-command-menu.msft.png":::
       <span data-ttu-id="94014-111">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="94014-111">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="94014-112">键入 `sensors` ，选择 **显示传感器**，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="94014-112">Type `sensors`, choose **Show Sensors**, and select `Enter`.</span></span>  <span data-ttu-id="94014-113">传感器 **工具** 将在 DevTools 窗口底部打开。</span><span class="sxs-lookup"><span data-stu-id="94014-113">The **Sensors** tool opens at the bottom of your DevTools window.</span></span>  
1.  <span data-ttu-id="94014-114">从"\*\*\*\* 地理位置"列表中选择预设城市之一（如 ），或选择"自定义位置"以输入自定义经度和纬度坐标，或选择"位置不可用"以显示当用户的位置不可用时网站的行为方式。 `Tokyo` \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="94014-114">From the **Geolocation** list select one of the preset cities, like `Tokyo`, or choose **Custom location** to enter custom longitude and latitude coordinates, or choose **Location unavailable** to display how your site behaves when the user's location is not available.</span></span>  
    
    :::image type="complex" source="../media/device-mode-console-sensors-geolocation-tokyo.msft.png" alt-text="从地理位置列表中选择东京" lightbox="../media/device-mode-console-sensors-geolocation-tokyo.msft.png":::
       <span data-ttu-id="94014-116">从 `Tokyo` "**地理位置"列表中选择**</span><span class="sxs-lookup"><span data-stu-id="94014-116">Choose `Tokyo` from the **Geolocation** list</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="94014-117">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="94014-117">Getting in touch with the Microsoft Edge DevTools team</span></span>

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

<!--[WebFundamentalsNativeHardwareUserLocationIndex]: /web/fundamentals/native-hardware/user-location/index "User Location"  -->  

> [!NOTE]
> <span data-ttu-id="94014-118">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="94014-118">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="94014-119">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/device-mode/geolocation)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="94014-119">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/device-mode/geolocation) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="94014-121">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="94014-121">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
