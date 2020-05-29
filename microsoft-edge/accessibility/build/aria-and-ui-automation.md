---
ms.assetid: ffd1bc60-2ef1-4f11-8156-b63544cede77
description: 了解 Microsoft Edge 如何识别 ARIA 信息，然后将其公开给可使用 Microsoft UI 自动化 Api 的辅助技术。
title: 辅助功能-ARIA 和 UI 自动化
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 辅助功能，面向开发人员的辅助功能，辅助网站，边缘，web 开发，ARIA，开发人员，UIA，UI 自动化
ms.custom: seodec18
ms.openlocfilehash: 2fcc8160c830b5a62d8023a5cb7cc9df376c49ca
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562608"
---
# Microsoft Edge 中的 ARIA 和 UI 自动化

W3C 定义易于访问的富 Internet 应用程序（ARIA）作为使动态 web 内容和自定义 UI 易于访问的语法。 Microsoft Edge 识别 ARIA 角色、状态和属性信息，并将其公开给辅助技术，这些辅助技术又可以使用[MICROSOFT UI 自动化](https://blogs.msdn.microsoft.com/winuiautomation/)api 检索信息。

有关 Microsoft Edge 支持的新 HTML5 功能 accessibly 的信息，请访问[HTML5Accessibility](https://html5accessibility.com) 。

Microsoft Edge 呈现引擎（EdgeHTML）构建网页的易于访问的投影，符合以下 W3C 规范：

1. [Html 辅助功能 API 映射](https://w3.org/TR/html-aam-1.0/)规范定义了 html 元素和属性映射到 ARIA 和 UI 自动化对象的方式。
   * [工作草稿](https://w3.org/TR/html-aam-1.0/)-规范版本的稳定版本
   * [编辑者草稿](https://w3c.github.io/html-aam/)-正在进行中工作。 请注意，虽然此规范具有最新更改，但这些更改可能不会在 Microsoft Edge 中使用。


2. [核心辅助功能 API 映射](https://w3.org/TR/core-aam-1.1/)规范定义了构建辅助功能树以及将 ARIA 元素和属性映射到 UI 自动化对象的一般原则。
   * [工作草稿](https://w3.org/TR/core-aam-1.1/)-规范版本的稳定版本
   * [编辑者草稿](https://w3c.github.io/core-aam/)-正在进行中工作。 请注意，虽然此规范具有最新更改，但这些更改可能不会在 Microsoft Edge 中使用。  

3. [辅助名称和说明：计算和 API 映射](https://w3.org/TR/accname-aam-1.1/)规范定义如何在给定 HTML 和可用于辅助元素的 ARIA 元素和属性值的情况中计算辅助对象的名称和说明。
   * [工作草稿](https://w3.org/TR/accname-aam-1.1/)-规范版本的稳定版本  
   * [编辑者草稿](https://w3c.github.io/accname/)-正在进行中工作。 请注意，虽然此规范具有最新更改，但这些更改可能不会在 Microsoft Edge 中使用。   

有关 Microsoft Edge 中的辅助功能体系结构的详细信息，请参阅[构建更易于访问的 web 平台](https://blogs.windows.com/msedgedev/2016/04/20/building-a-more-accessible-web-platform/)博客文章。  有关新体系结构如何改善最终用户体验的示例，以及特定如何标记定义使用辅助技术（如屏幕阅读器）导航的体验，请参阅[使用 HTML5 和 UIA 构建更易于访问的用户体验](https://blogs.windows.com/msedgedev/2016/05/12/accessible-ux-with-html5-and-uia/)。
