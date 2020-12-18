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
# 辅助功能 - EdgeHTML (扩展)   

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

## 为 Microsoft Edge 创建辅助扩展图标

鼓励第三方扩展开发人员使用符合 Microsoft 严格的辅助功能要求的图像资源，以便对于浅色和深色主题，图标清晰可见。 我们建议所有扩展图标在图标的背景色和图标本身的基准颜色之间具有 14：1 的比例。


Microsoft 开发的第一方扩展应用"贴纸"视觉处理来满足这些要求。

### "贴纸"的示例

"贴纸"的主要目标是使图标在任何背景颜色上均可直观访问。 白色外部笔划和图标之间的建议颜色比率应为 14：1，以支持高对比度要求。

#### 良好的图标
使用贴纸，主要深色图标在任何背景颜色上都保持可见。


![在任何背景颜色上可见的图标图像](./../media/accessibility-light-to-dark-good.png)

#### 错误图标
如果没有贴纸，图标可能会与背景混合，并且无法看到。


![混合为黑色背景的图标图像](./../media/accessibility-light-to-dark-bad.png)

### "贴纸"扩展图标

以下五个步骤概述了创建满足 Microsoft 辅助功能要求的扩展图标的建议方法：


| 步骤 1                                       | 步骤 2                                       | 步骤 3                                                                                 | 步骤 4                                                                          | 步骤 5                                                       |
|:---------------------------------------------|:---------------------------------------------|:---------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------|:-------------------------------------------------------------|
| 在指定的网格中设置图标。    | 将图标大小减小 2 像素。           | 复制图标并就地粘贴。 创建带圆角的 2 像素外部笔划。 | 大纲笔划，释放复合路径，并合并其余形状。 | 将外部笔划颜色着色为白色，并添加内部图标。 |
| ![步骤 1](./../media/accessibility-step1.png) | ![步骤 2](./../media/accessibility-step2.png) | ![步骤 3](./../media/accessibility-step3.png)                                           | ![步骤 4](./../media/accessibility-step4.png)                                    | ![步骤 5](./../media/accessibility-step5.png)                 |

