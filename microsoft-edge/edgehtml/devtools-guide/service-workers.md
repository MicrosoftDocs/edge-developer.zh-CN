---
description: 使用服务工作者面板管理和调试服务工作者
title: DevTools - 调试器 - 服务工作者
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， web development， f12 tools， devtools， debugger， debugging， pwa， service worker， cache api
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 99592f787da8bcf89d2e16231aa3f39047b4fc0b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232484"
---
# 服务工作者

服务 **工作人员** 面板具有用于管理和调试网站服务工作者的工具，可帮助你：

 - 获取与您的网站关联的所有服务工作者的概述及其范围和状态的详细信息
 - **更新** 和管理 (**作用域**) 注册服务工作线程
 - **推送** 测试通知
 - **停止** /**启动**单个服务工作者，并
 - **在** 单独的调试器窗口中检查选定的服务工作器

!["服务工作者概述"窗格](./media/service_worker.png)

请注意以下有关边缘 DevTools 中的服务工作器调试的信息：

 - 调试服务工作者将启动独立于页面工具的 DevTools 的新实例，因为服务工作者可以跨多个选项卡共享。
 - 由于[**服务**](./elements.md)工作者[****](./emulation.md)在后台运行，并且不直接控制应用的前端，因此服务工作器调试器中缺少元素和模拟面板。
 - 目前，仅从服务工作者的 DevTools 调试实例报告服务工作者的网络流量，而不是从页面本身的调试器实例中报告。
 - 若要模拟**** DevTools 中的推送，你需要将推送事件侦听器添加到服务** 工作者，以便观察其效果。 下面的示例将在服务工作控制台中打印"从 DevTools 测试推送**消息"。**

   ```JavaScript
   self.addEventListener('push', function(event){
       console.log(event.data.text());
   });
   ```

以下是在使用服务工作者时请记住的一些常规问题：

- **仅 HTTPS。** 服务工作人员将不会在 HTTP 中工作;将需要使用 HTTPS。 但是，您可以注册服务工作者 `localhost` 以进行测试。

- **不允许 DOM 访问。** 与 Web 工作者一样，你无法访问页面的对象模型。 这意味着，如果需要更改有关页面的内容，则需要从服务工作者使用到页面，以便可以处理页面 [`postMessage`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage) 的 DOM 更改。

- **独立于页面执行。** 由于这些脚本不绑定到页面的生命周期，因此了解它们不与页面共享同一上下文很重要。 除了无法像前面 (一样访问 DOM) ，他们无法访问页面上可用的相同变量。

- **替代 *应用程序缓存*。** 使用服务工作者时，将忽略应用缓存。 服务工作线程 API 旨在通过向 Web 开发人员提供更精细的控制来完全取代应用程序缓存。

  - **脚本不能位于 CDN 上。** 服务工作者的 JavaScript 文件无法托管在 CDN (CDN) 上，它必须与页面位于同一域中。 但是，如果需要，可以从 CDN 导入脚本。

- **可以随时终止。** 服务工作人员应短期工作，其生存时间与事件关联。 特别是，服务工作者有一个时间限制，必须完成其事件处理程序的执行。 在其他情况下，浏览器或操作系统可能会选择终止影响电池、CPU 或内存消耗的服务工作者。 在任一情况下，如果对正在处理的后续事件使用不同的服务工作实例，则避免依赖服务工作线程脚本中的全局变量。

- **仅允许异步请求。** 此处不允许同步 XHR！ 这两者都不是 localStorage，因此最好使用 IndexedDB 和前面介绍的新缓存 API。

- **服务工作线程范围为 1：1。** 每个作用域只能有一个服务工作线程。 这意味着，如果您尝试为已具有服务工作器的范围注册其他服务工作器，则将会更新该服务工作线程。
