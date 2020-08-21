---
ms.assetid: 4d3fa934-4fa8-4c02-b9b5-88506c76baac
description: Microsoft Edge 中浏览器功能的指南。
title: 浏览器 - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: 854b0e8ac057db3cc8b53af6205404d0841dfdb4
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942042"
---
# 浏览器功能  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

## 自动播放策略  

 Microsoft Edge 为客户提供了在网站上个性化其浏览首选项的功能，这些媒体可自动播放媒体，以便最大程度地减少 Web 上的分词并节约带宽。  用户可以使用全局和每个站点自动播放控件自定义媒体行为。  此外，Microsoft Edge 会自动断放背景选项卡中的媒体自动播放。  

有关详细信息 [和最佳做法](./browser-features/autoplay-policies.md) ，请参阅"自动播放"策略以确保获得网站中托管媒体的良好用户体验。  

## Flash  

如果在页面上使用 Flash，但用户尚未启用它，则 Microsoft Edge 通常会在地址栏中显示一个拼图饼图标。  如果要在页面加载页面后动态地添加 Flash 控件，可能不会显示拼图图标，在这种情况下，你将需要 [测试是否加载 Flash，并且在](./browser-features/flash.md) 未出现时提供优美的回退体验。  

## 阅读视图  

Microsoft Edge 提供了 [阅读视图，可](./browser-features/reading-view.md) 更简化、更类似于书页的阅读体验，在页面上不会分不分发不相关或其他辅助内容的分开。  下面是有关如何确保网站出色阅读视图体验的提示以及选择网站出阅读视图的说明。  

## 搜索提供程序发现  

丰富搜索集成内置在 Microsoft Edge 地址栏中，包括搜索建议、来自 Web 的结果、浏览历史记录和收藏夹。  [下面是关于需要向 Microsoft](./browser-features/search-provider-discovery.md) Edge 提供支持的搜索提供商的详细信息。  
