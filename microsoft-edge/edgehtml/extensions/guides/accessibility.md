---
ms.assetid: c4544a19-de78-4c69-a042-c0415726548f
description: 若要确保扩展图标在浅色和深色模式下都可见，请按照辅助功能指南操作。
title: '辅助功能 - EdgeHTML (扩展) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e6e7dbd2ee66ac785be31eec7189b87e6a6bd91f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232654"
---
# <span data-ttu-id="4a742-104">辅助功能 - EdgeHTML (扩展) </span><span class="sxs-lookup"><span data-stu-id="4a742-104">Accessibility - Extensions (EdgeHTML)</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## <span data-ttu-id="4a742-105">为 Microsoft Edge 创建辅助扩展图标</span><span class="sxs-lookup"><span data-stu-id="4a742-105">Creating accessible extension icons for Microsoft Edge</span></span>

<span data-ttu-id="4a742-106">鼓励第三方扩展开发人员使用符合 Microsoft 严格的辅助功能要求的图像资源，以便对于浅色和深色主题，图标清晰可见。</span><span class="sxs-lookup"><span data-stu-id="4a742-106">Third-party extension developers are encouraged to use image assets that meet Microsoft’s strict accessibility requirements so that icons are clearly visible for both light and dark themes.</span></span> <span data-ttu-id="4a742-107">我们建议所有扩展图标在图标的背景色和图标本身的基准颜色之间具有 14：1 的比例。</span><span class="sxs-lookup"><span data-stu-id="4a742-107">We recommend that all extension icons have a 14:1 ratio between the icon’s background color and the dominant color of the icon itself.</span></span>


<span data-ttu-id="4a742-108">Microsoft 开发的第一方扩展应用"贴纸"视觉处理来满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="4a742-108">First-party extensions developed by Microsoft apply a “stickering” visual treatment to satisfy these requirements.</span></span>

### <span data-ttu-id="4a742-109">"贴纸"的示例</span><span class="sxs-lookup"><span data-stu-id="4a742-109">Examples of the "stickering"</span></span>

<span data-ttu-id="4a742-110">"贴纸"的主要目标是使图标在任何背景颜色上均可直观访问。</span><span class="sxs-lookup"><span data-stu-id="4a742-110">The main goal of “stickering” is to make the icon visually accessible on any background color.</span></span> <span data-ttu-id="4a742-111">白色外部笔划和图标之间的建议颜色比率应为 14：1，以支持高对比度要求。</span><span class="sxs-lookup"><span data-stu-id="4a742-111">The recommended color ratio between the white outer stroke and your icon should be 14:1 to support the high contrast requirements.</span></span>

#### <span data-ttu-id="4a742-112">良好的图标</span><span class="sxs-lookup"><span data-stu-id="4a742-112">Good icon</span></span>
<span data-ttu-id="4a742-113">使用贴纸，主要深色图标在任何背景颜色上都保持可见。</span><span class="sxs-lookup"><span data-stu-id="4a742-113">With stickering, a primarily dark icon will remain visible on any background color.</span></span>


![在任何背景颜色上可见的图标图像](./../media/accessibility-light-to-dark-good.png)

#### <span data-ttu-id="4a742-115">错误图标</span><span class="sxs-lookup"><span data-stu-id="4a742-115">Bad icon</span></span>
<span data-ttu-id="4a742-116">如果没有贴纸，图标可能会与背景混合，并且无法看到。</span><span class="sxs-lookup"><span data-stu-id="4a742-116">Without stickering, an icon could blend in with the background and become impossible to see.</span></span>


![混合为黑色背景的图标图像](./../media/accessibility-light-to-dark-bad.png)

### <span data-ttu-id="4a742-118">"贴纸"扩展图标</span><span class="sxs-lookup"><span data-stu-id="4a742-118">"Stickering" your extension icon</span></span>

<span data-ttu-id="4a742-119">以下五个步骤概述了创建满足 Microsoft 辅助功能要求的扩展图标的建议方法：</span><span class="sxs-lookup"><span data-stu-id="4a742-119">The following five steps outline the suggested method of creating an extension icon that meets Microsoft’s accessibility requirements:</span></span>


| <span data-ttu-id="4a742-120">步骤 1</span><span class="sxs-lookup"><span data-stu-id="4a742-120">Step 1</span></span>                                       | <span data-ttu-id="4a742-121">步骤 2</span><span class="sxs-lookup"><span data-stu-id="4a742-121">Step 2</span></span>                                       | <span data-ttu-id="4a742-122">步骤 3</span><span class="sxs-lookup"><span data-stu-id="4a742-122">Step 3</span></span>                                                                                 | <span data-ttu-id="4a742-123">步骤 4</span><span class="sxs-lookup"><span data-stu-id="4a742-123">Step 4</span></span>                                                                          | <span data-ttu-id="4a742-124">步骤 5</span><span class="sxs-lookup"><span data-stu-id="4a742-124">Step 5</span></span>                                                       |
|:---------------------------------------------|:---------------------------------------------|:---------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------|:-------------------------------------------------------------|
| <span data-ttu-id="4a742-125">在指定的网格中设置图标。</span><span class="sxs-lookup"><span data-stu-id="4a742-125">Set your icon within your specified grid.</span></span>    | <span data-ttu-id="4a742-126">将图标大小减小 2 像素。</span><span class="sxs-lookup"><span data-stu-id="4a742-126">Reduce your icon size by 2 pixels.</span></span>           | <span data-ttu-id="4a742-127">复制图标并就地粘贴。</span><span class="sxs-lookup"><span data-stu-id="4a742-127">Copy your icon and paste in place.</span></span> <span data-ttu-id="4a742-128">创建带圆角的 2 像素外部笔划。</span><span class="sxs-lookup"><span data-stu-id="4a742-128">Create a 2 pixel outer stroke with rounded corners.</span></span> | <span data-ttu-id="4a742-129">大纲笔划，释放复合路径，并合并其余形状。</span><span class="sxs-lookup"><span data-stu-id="4a742-129">Outline your stroke, release the compound path, and merge the remaining shapes.</span></span> | <span data-ttu-id="4a742-130">将外部笔划颜色着色为白色，并添加内部图标。</span><span class="sxs-lookup"><span data-stu-id="4a742-130">Color the outer stroke white and the inner icon as you wish.</span></span> |
| ![步骤 1](./../media/accessibility-step1.png) | ![步骤 2](./../media/accessibility-step2.png) | ![步骤 3](./../media/accessibility-step3.png)                                           | ![步骤 4](./../media/accessibility-step4.png)                                    | ![步骤 5](./../media/accessibility-step5.png)                 |

