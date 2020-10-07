---
ms.assetid: c4544a19-de78-4c69-a042-c0415726548f
description: To ensure your extension’s icon is visible while in both light and dark mode, follow the accessibility guide.
title: Accessibility - Extensions (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer
ms.openlocfilehash: 60e794467c6d054e390ce61c40559afa3a110c21
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882791"
---
# <span data-ttu-id="bb95c-104">Accessibility - Extensions (EdgeHTML)</span><span class="sxs-lookup"><span data-stu-id="bb95c-104">Accessibility - Extensions (EdgeHTML)</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## <span data-ttu-id="bb95c-105">Creating accessible extension icons for Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bb95c-105">Creating accessible extension icons for Microsoft Edge</span></span>

<span data-ttu-id="bb95c-106">Third-party extension developers are encouraged to use image assets that meet Microsoft’s strict accessibility requirements so that icons are clearly visible for both light and dark themes.</span><span class="sxs-lookup"><span data-stu-id="bb95c-106">Third-party extension developers are encouraged to use image assets that meet Microsoft’s strict accessibility requirements so that icons are clearly visible for both light and dark themes.</span></span> <span data-ttu-id="bb95c-107">We recommend that all extension icons have a 14:1 ratio between the icon’s background color and the dominant color of the icon itself.</span><span class="sxs-lookup"><span data-stu-id="bb95c-107">We recommend that all extension icons have a 14:1 ratio between the icon’s background color and the dominant color of the icon itself.</span></span>


<span data-ttu-id="bb95c-108">First-party extensions developed by Microsoft apply a “stickering” visual treatment to satisfy these requirements.</span><span class="sxs-lookup"><span data-stu-id="bb95c-108">First-party extensions developed by Microsoft apply a “stickering” visual treatment to satisfy these requirements.</span></span>

### <span data-ttu-id="bb95c-109">Examples of the "stickering"</span><span class="sxs-lookup"><span data-stu-id="bb95c-109">Examples of the "stickering"</span></span>

<span data-ttu-id="bb95c-110">The main goal of “stickering” is to make the icon visually accessible on any background color.</span><span class="sxs-lookup"><span data-stu-id="bb95c-110">The main goal of “stickering” is to make the icon visually accessible on any background color.</span></span> <span data-ttu-id="bb95c-111">The recommended color ratio between the white outer stroke and your icon should be 14:1 to support the high contrast requirements.</span><span class="sxs-lookup"><span data-stu-id="bb95c-111">The recommended color ratio between the white outer stroke and your icon should be 14:1 to support the high contrast requirements.</span></span>

#### <span data-ttu-id="bb95c-112">Good icon</span><span class="sxs-lookup"><span data-stu-id="bb95c-112">Good icon</span></span>
<span data-ttu-id="bb95c-113">With stickering, a primarily dark icon will remain visible on any background color.</span><span class="sxs-lookup"><span data-stu-id="bb95c-113">With stickering, a primarily dark icon will remain visible on any background color.</span></span>


![image of icon being visible on any background color](./../media/accessibility-light-to-dark-good.png)

#### <span data-ttu-id="bb95c-115">Bad icon</span><span class="sxs-lookup"><span data-stu-id="bb95c-115">Bad icon</span></span>
<span data-ttu-id="bb95c-116">Without stickering, an icon could blend in with the background and become impossible to see.</span><span class="sxs-lookup"><span data-stu-id="bb95c-116">Without stickering, an icon could blend in with the background and become impossible to see.</span></span>


![image of icon blending into black background](./../media/accessibility-light-to-dark-bad.png)

### <span data-ttu-id="bb95c-118">"Stickering" your extension icon</span><span class="sxs-lookup"><span data-stu-id="bb95c-118">"Stickering" your extension icon</span></span>

<span data-ttu-id="bb95c-119">The following five steps outline the suggested method of creating an extension icon that meets Microsoft’s accessibility requirements:</span><span class="sxs-lookup"><span data-stu-id="bb95c-119">The following five steps outline the suggested method of creating an extension icon that meets Microsoft’s accessibility requirements:</span></span>


| <span data-ttu-id="bb95c-120">Step 1</span><span class="sxs-lookup"><span data-stu-id="bb95c-120">Step 1</span></span>                                       | <span data-ttu-id="bb95c-121">步骤 2</span><span class="sxs-lookup"><span data-stu-id="bb95c-121">Step 2</span></span>                                       | <span data-ttu-id="bb95c-122">步骤 3</span><span class="sxs-lookup"><span data-stu-id="bb95c-122">Step 3</span></span>                                                                                 | <span data-ttu-id="bb95c-123">步骤 4</span><span class="sxs-lookup"><span data-stu-id="bb95c-123">Step 4</span></span>                                                                          | <span data-ttu-id="bb95c-124">Step 5</span><span class="sxs-lookup"><span data-stu-id="bb95c-124">Step 5</span></span>                                                       |
|:---------------------------------------------|:---------------------------------------------|:---------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------|:-------------------------------------------------------------|
| <span data-ttu-id="bb95c-125">Set your icon within your specified grid.</span><span class="sxs-lookup"><span data-stu-id="bb95c-125">Set your icon within your specified grid.</span></span>    | <span data-ttu-id="bb95c-126">Reduce your icon size by 2 pixels.</span><span class="sxs-lookup"><span data-stu-id="bb95c-126">Reduce your icon size by 2 pixels.</span></span>           | <span data-ttu-id="bb95c-127">Copy your icon and paste in place.</span><span class="sxs-lookup"><span data-stu-id="bb95c-127">Copy your icon and paste in place.</span></span> <span data-ttu-id="bb95c-128">Create a 2 pixel outer stroke with rounded corners.</span><span class="sxs-lookup"><span data-stu-id="bb95c-128">Create a 2 pixel outer stroke with rounded corners.</span></span> | <span data-ttu-id="bb95c-129">Outline your stroke, release the compound path, and merge the remaining shapes.</span><span class="sxs-lookup"><span data-stu-id="bb95c-129">Outline your stroke, release the compound path, and merge the remaining shapes.</span></span> | <span data-ttu-id="bb95c-130">Color the outer stroke white and the inner icon as you wish.</span><span class="sxs-lookup"><span data-stu-id="bb95c-130">Color the outer stroke white and the inner icon as you wish.</span></span> |
| ![step1](./../media/accessibility-step1.png) | ![step2](./../media/accessibility-step2.png) | ![step3](./../media/accessibility-step3.png)                                           | ![step4](./../media/accessibility-step4.png)                                    | ![step5](./../media/accessibility-step5.png)                 |

