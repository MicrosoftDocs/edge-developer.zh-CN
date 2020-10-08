---
description: 使用 "服务工作人员" 面板管理和调试你的服务工作人员
title: DevTools-调试程序-服务工作人员
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、调试器、调试、pwa、服务工作人员、缓存 api
ms.custom: seodec18
ms.openlocfilehash: 8e1fa62358657a47ce40d0742f95a76f2586d0c8
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563458"
---
# 服务工作进程

" **服务工作者** " 面板具有用于管理和调试网站的服务工作人员的工具，可帮助你：

 - 大致了解与您的网站相关联的所有服务工作者及其范围和状态的详细信息
 - **更新** 和管理 (**注销** 针对给定范围的服务工作人员注册) 
 - **推送** 测试通知
 - **停止** /**启动**单个服务工作人员，然后
 - 在单独的调试器窗口中**检查**所选服务工作人员

![服务工作人员概述窗格](./media/service_worker.png)

请注意以下有关 Edge DevTools 中的服务工作者调试的信息：

 - 调试服务工作人员将启动与页面工具分开的 DevTools 的新实例，因为服务工作人员可以在多个选项卡之间共享。
 - 如果服务工作者在后台运行，并且不直接控制应用的前端，则服务工作器调试器中不存在 [**元素**](./elements.md) 和 [**仿真**](./emulation.md) 面板。
 - 当前服务工作器的网络流量仅从该工作人员的 DevTools 调试实例报告，而不是从页面本身的调试器实例中报告。
 - 若要从 DevTools 模拟 **推送** ，需要将 *push* 事件侦听器添加到服务工作人员，以便观察其效果。 以下示例将在服务工作器 **控制台**中打印 "从 DevTools 测试推送消息"。

   ```JavaScript
   self.addEventListener('push', function(event){
       console.log(event.data.text());
   });
   ```

下面是使用服务工作人员时需要牢记的一些一般事项：

- **仅限 HTTPS。** 服务工作人员将无法在 HTTP 中使用;您将需要使用 HTTPS。 但是，你可以出于测试目的注册服务工作人员 `localhost` 。

- **不允许 DOM 访问。** 与 web 工作人员一样，您不能访问页面的对象模型。 这意味着，如果你需要更改有关页面的某些内容，你将需要 [`postMessage`](https://developer.mozilla.org/docs/Web/API/Worker/postMessage) 从服务工作人员到页面的使用，以便你可以从页面处理 DOM 更改。

- **独立于页面执行。** 由于这些脚本不依赖于页面的生存期，因此请务必了解它们不会与页面共享相同的上下文。 除了无法访问 DOM (（如前面) 所述），它们将无法访问页面上提供的相同变量。

- **替代 *应用缓存*。** 服务工作人员正在使用时，将忽略应用缓存。 服务工作者 API 旨在通过向 web 开发人员提供更精细的控制来完全 supplant 应用缓存。

  - **脚本不能在 CDN 上显示。** 服务工作人员的 JavaScript 文件不能托管在 (CDN) 的内容分发网络上，它必须与页面位于同一域。 但是，如果你愿意，可以从 CDN 导入脚本。

- **随时可以终止。** 服务工作者的生命周期很短，其生命周期绑定到事件。 特别是，服务工作人员有一个时间限制，它们必须完成其事件处理程序的执行。 在其他情况下，浏览器或操作系统可能会选择终止影响电池、CPU 或内存消耗的服务工作人员。 在任何一种情况下，请避免在服务工作脚本中依赖全局变量，以防在正在处理的后续事件中使用不同的服务工作者实例。

- **仅允许异步请求。** 此处不允许使用同步 XHR！ 不 localStorage，因此最好使用 IndexedDB 和前面介绍的新缓存 API。

- **作用域的服务工作人员为1:1。** 每个作用域只能有一个服务工作者。 这意味着，如果你尝试为已具有服务工作人员的作用域注册不同的服务工作人员，该服务工作人员将更新。
