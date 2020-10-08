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
# 辅助功能-扩展 (EdgeHTML)   

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## 为 Microsoft Edge 创建易于访问的扩展图标

建议使用第三方扩展开发人员使用满足 Microsoft 严格的辅助功能要求的图像资产，以便在浅色和深色主题中清楚地看到图标。 我们建议所有扩展图标在图标的背景色和图标本身的主颜色之间有14:1 的比率。


Microsoft 开发的第一方扩展将应用 "stickering" 视觉处理以满足这些要求。

### "Stickering" 示例

"Stickering" 的主要目标是使图标在任何背景色上直观地易于访问。 白色外部笔划和图标之间的推荐颜色比率应为14:1 以支持高对比度要求。

#### 好图标
使用 stickering，主要的深色图标将保持在任何背景色上可见。


![在任何背景色上可见的图标的图像](./../media/accessibility-light-to-dark-good.png)

#### 错误图标
如果没有 stickering，可能会将图标与背景混合在一起，无法看到。


![混合到黑色背景中的图标图像](./../media/accessibility-light-to-dark-bad.png)

### "Stickering" 您的扩展名图标

以下五个步骤概括了创建满足 Microsoft 辅助功能要求的扩展图标的建议方法：


| 步骤 1                                       | 步骤 2                                       | 步骤 3                                                                                 | 步骤 4                                                                          | 步骤 5                                                       |
|:---------------------------------------------|:---------------------------------------------|:---------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------|:-------------------------------------------------------------|
| 在指定的网格中设置图标。    | 将图标大小减小2个像素。           | 复制图标并粘贴到位。 创建一个带圆角的2像素外部笔划。 | 分级显示笔划，释放复合路径，并合并其余形状。 | 将外部笔划的白色和内部图标着色为所需的颜色。 |
| ![step1](./../media/accessibility-step1.png) | ![step2](./../media/accessibility-step2.png) | ![step3](./../media/accessibility-step3.png)                                           | ![step4](./../media/accessibility-step4.png)                                    | ![step5](./../media/accessibility-step5.png)                 |

