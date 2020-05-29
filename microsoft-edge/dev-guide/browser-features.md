---
ms.assetid: 4d3fa934-4fa8-4c02-b9b5-88506c76baac
description: Microsoft Edge 中的浏览器功能指南。
title: 开发人员指南-浏览器
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/28/2018
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: e7b13b18048e0a703ca5e2a0e5b52712f41c2101
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562637"
---
# 浏览器功能

## 自动播放策略

 Microsoft Edge 使客户能够在通过自动播放媒体和声音的网站上个性化浏览首选项，从而最大限度地减少 web 上的干扰并节省带宽。 用户可以通过全局自动播放控件和每个网站的 "自动播放" 控件自定义媒体行为。 此外，Microsoft Edge 会自动取消自动播放后台选项卡中的媒体。

查看 "[自动播放" 策略](./browser-features/autoplay-policies.md)，了解详细信息和最佳做法，以确保在您的网站上托管媒体的用户体验良好。

## Flash
如果你的页面上使用了 Flash，但用户尚未启用，则 Microsoft Edge 通常会在地址栏中显示拼图块图标。 如果你在加载页面后动态添加 Flash 控件，则拼图图标可能不会显示，在这种情况下，你将需要[测试是否已加载 Flash，并提供一个正常的回退体验](./browser-features/flash.md)（如果它不存在）。

## 阅读视图
Microsoft Edge 提供了一种[阅读视图](./browser-features/reading-view.md)，可提供更简洁的网页的书籍阅读体验，而不会干扰页面上的不相关或其他辅助内容。 以下是有关如何确保你的网站具有强大的阅读视图体验的提示，以及如何在阅读视图中选择网站的说明。

## 搜索提供程序发现

丰富的搜索集成内置于 Microsoft Edge 地址栏，包括搜索建议、web 上的结果、你的浏览历史记录和收藏夹。 下面是有关希望为 Microsoft Edge 提供支持的[搜索提供程序的详细信息](./browser-features/search-provider-discovery.md)。
