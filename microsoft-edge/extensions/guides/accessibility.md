---
ms.assetid: c4544a19-de78-4c69-a042-c0415726548f
description: 若要确保在 "浅色" 和 "深色" 模式下显示您的扩展名图标，请按照辅助功能指南操作。
title: '辅助功能-扩展 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 60e794467c6d054e390ce61c40559afa3a110c21
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882791"
---
# <span data-ttu-id="43431-104">辅助功能-扩展 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="43431-104">Accessibility - Extensions (EdgeHTML)</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## <span data-ttu-id="43431-105">为 Microsoft Edge 创建易于访问的扩展图标</span><span class="sxs-lookup"><span data-stu-id="43431-105">Creating accessible extension icons for Microsoft Edge</span></span>

<span data-ttu-id="43431-106">建议使用第三方扩展开发人员使用满足 Microsoft 严格的辅助功能要求的图像资产，以便在浅色和深色主题中清楚地看到图标。</span><span class="sxs-lookup"><span data-stu-id="43431-106">Third-party extension developers are encouraged to use image assets that meet Microsoft’s strict accessibility requirements so that icons are clearly visible for both light and dark themes.</span></span> <span data-ttu-id="43431-107">我们建议所有扩展图标在图标的背景色和图标本身的主颜色之间有14:1 的比率。</span><span class="sxs-lookup"><span data-stu-id="43431-107">We recommend that all extension icons have a 14:1 ratio between the icon’s background color and the dominant color of the icon itself.</span></span>


<span data-ttu-id="43431-108">Microsoft 开发的第一方扩展将应用 "stickering" 视觉处理以满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="43431-108">First-party extensions developed by Microsoft apply a “stickering” visual treatment to satisfy these requirements.</span></span>

### <span data-ttu-id="43431-109">"Stickering" 示例</span><span class="sxs-lookup"><span data-stu-id="43431-109">Examples of the "stickering"</span></span>

<span data-ttu-id="43431-110">"Stickering" 的主要目标是使图标在任何背景色上直观地易于访问。</span><span class="sxs-lookup"><span data-stu-id="43431-110">The main goal of “stickering” is to make the icon visually accessible on any background color.</span></span> <span data-ttu-id="43431-111">白色外部笔划和图标之间的推荐颜色比率应为14:1 以支持高对比度要求。</span><span class="sxs-lookup"><span data-stu-id="43431-111">The recommended color ratio between the white outer stroke and your icon should be 14:1 to support the high contrast requirements.</span></span>

#### <span data-ttu-id="43431-112">好图标</span><span class="sxs-lookup"><span data-stu-id="43431-112">Good icon</span></span>
<span data-ttu-id="43431-113">使用 stickering，主要的深色图标将保持在任何背景色上可见。</span><span class="sxs-lookup"><span data-stu-id="43431-113">With stickering, a primarily dark icon will remain visible on any background color.</span></span>


![在任何背景色上可见的图标的图像](./../media/accessibility-light-to-dark-good.png)

#### <span data-ttu-id="43431-115">错误图标</span><span class="sxs-lookup"><span data-stu-id="43431-115">Bad icon</span></span>
<span data-ttu-id="43431-116">如果没有 stickering，可能会将图标与背景混合在一起，无法看到。</span><span class="sxs-lookup"><span data-stu-id="43431-116">Without stickering, an icon could blend in with the background and become impossible to see.</span></span>


![混合到黑色背景中的图标图像](./../media/accessibility-light-to-dark-bad.png)

### <span data-ttu-id="43431-118">"Stickering" 您的扩展名图标</span><span class="sxs-lookup"><span data-stu-id="43431-118">"Stickering" your extension icon</span></span>

<span data-ttu-id="43431-119">以下五个步骤概括了创建满足 Microsoft 辅助功能要求的扩展图标的建议方法：</span><span class="sxs-lookup"><span data-stu-id="43431-119">The following five steps outline the suggested method of creating an extension icon that meets Microsoft’s accessibility requirements:</span></span>


| <span data-ttu-id="43431-120">步骤 1</span><span class="sxs-lookup"><span data-stu-id="43431-120">Step 1</span></span>                                       | <span data-ttu-id="43431-121">步骤 2</span><span class="sxs-lookup"><span data-stu-id="43431-121">Step 2</span></span>                                       | <span data-ttu-id="43431-122">步骤 3</span><span class="sxs-lookup"><span data-stu-id="43431-122">Step 3</span></span>                                                                                 | <span data-ttu-id="43431-123">步骤 4</span><span class="sxs-lookup"><span data-stu-id="43431-123">Step 4</span></span>                                                                          | <span data-ttu-id="43431-124">步骤 5</span><span class="sxs-lookup"><span data-stu-id="43431-124">Step 5</span></span>                                                       |
|:---------------------------------------------|:---------------------------------------------|:---------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------|:-------------------------------------------------------------|
| <span data-ttu-id="43431-125">在指定的网格中设置图标。</span><span class="sxs-lookup"><span data-stu-id="43431-125">Set your icon within your specified grid.</span></span>    | <span data-ttu-id="43431-126">将图标大小减小2个像素。</span><span class="sxs-lookup"><span data-stu-id="43431-126">Reduce your icon size by 2 pixels.</span></span>           | <span data-ttu-id="43431-127">复制图标并粘贴到位。</span><span class="sxs-lookup"><span data-stu-id="43431-127">Copy your icon and paste in place.</span></span> <span data-ttu-id="43431-128">创建一个带圆角的2像素外部笔划。</span><span class="sxs-lookup"><span data-stu-id="43431-128">Create a 2 pixel outer stroke with rounded corners.</span></span> | <span data-ttu-id="43431-129">分级显示笔划，释放复合路径，并合并其余形状。</span><span class="sxs-lookup"><span data-stu-id="43431-129">Outline your stroke, release the compound path, and merge the remaining shapes.</span></span> | <span data-ttu-id="43431-130">将外部笔划的白色和内部图标着色为所需的颜色。</span><span class="sxs-lookup"><span data-stu-id="43431-130">Color the outer stroke white and the inner icon as you wish.</span></span> |
| ![step1](./../media/accessibility-step1.png) | ![step2](./../media/accessibility-step2.png) | ![step3](./../media/accessibility-step3.png)                                           | ![step4](./../media/accessibility-step4.png)                                    | ![step5](./../media/accessibility-step5.png)                 |

