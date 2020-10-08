---
description: 使用计算窗格了解 CSS 在页面元素上的级联和计算
title: DevTools-计算的元素
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/10/2017
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、元素、css、计算值、框模型
ms.custom: seodec18
ms.openlocfilehash: c7b1b7c86f30e6947442c9b3d0e8856074ce4c8e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564281"
---
# <span data-ttu-id="366a3-104">已计算</span><span class="sxs-lookup"><span data-stu-id="366a3-104">Computed</span></span>

<span data-ttu-id="366a3-105">请参阅所选元素) 的 "方框模型" 图表 (宽度、填充、边框、边距和偏移值。</span><span class="sxs-lookup"><span data-stu-id="366a3-105">See a box model diagram (width, padding, border, margin and offset values) of the selected element.</span></span> <span data-ttu-id="366a3-106">如果打开 **元素突出显示** 工具 (`Ctrl+Shift+L`) ，图表中的颜色区域与 (的宽度、填充等相同，在页面上选择它时将覆盖呈现的元素 ) 。</span><span class="sxs-lookup"><span data-stu-id="366a3-106">If you turn on the **Element highlighting** tool (`Ctrl+Shift+L`), the same colored regions in the diagram (for width, padding, etc.) that will overlay the rendered element when you select it on the page.</span></span> <span data-ttu-id="366a3-107">您可以通过单击图表中的任何值来编辑它。</span><span class="sxs-lookup"><span data-stu-id="366a3-107">You can edit any value in the diagram by clicking it.</span></span> 

<span data-ttu-id="366a3-108">方框模型图下方是可筛选和可编辑的计算样式属性列表。</span><span class="sxs-lookup"><span data-stu-id="366a3-108">Below the box model diagram is a filterable and editable list of computed style properties.</span></span> <span data-ttu-id="366a3-109">关闭当前活动的属性将激活级联中的下一个属性（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="366a3-109">Turning off a currently active property activates the next property in the cascade, if one exists.</span></span> <span data-ttu-id="366a3-110">您可以在 " [**更改**](./changes.md) " 窗格中查看您的更改。</span><span class="sxs-lookup"><span data-stu-id="366a3-110">You can view your changes in the [**Changes**](./changes.md) pane.</span></span>

<span data-ttu-id="366a3-111">默认情况下，" **仅显示用户样式** " 按钮处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="366a3-111">The **Display user styles only** button is on by default.</span></span> <span data-ttu-id="366a3-112">按下按钮将在 "计算样式" 列表中包含 Microsoft Edge *默认样式表* 中的样式。</span><span class="sxs-lookup"><span data-stu-id="366a3-112">Depressing the button will include styles from the *default stylesheet* of Microsoft Edge in the computed styles list.</span></span>

![计算窗格](../media/elements_computed.png)