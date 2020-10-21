---
description: 使用应用程序面板检查、修改和调试 web 应用清单、服务工作人员和服务工作人员缓存。
title: 调试渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 80475ebcbbdd3fb04fd0196e993c933e0bdcf090
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125389"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# 调试渐进式 Web 应用  

使用 **应用程序** 面板检查、修改和调试 web 应用清单、服务工作人员和服务工作人员缓存。  

<!--Related Guides:  

*   [Progressive Web Apps](/web/progressive-web-apps)  -->

<!--TODO:  Link web "Progressive Web Apps" section when available. -->

本指南仅讨论 **应用程序** 面板的渐进 Web 应用功能。  <!--If you're looking for help on the other panes, check out the last section of this guide, [Other Application panel guides](#other-application-panel-guides).  -->

<!--TODO:  Link to sections when available. -->

### 摘要  

*   使用 **清单** 窗格检查 web 应用清单和触发器添加到主屏幕事件。  
*   将 " **服务工作人员** " 窗格用于整个服务工作人员相关的任务，例如注销或更新服务、模拟推送事件、脱机或停止服务工作人员。  
*   从 " **缓存存储** " 窗格中查看服务工作人员缓存。  
*   从 " **清除存储** " 窗格中，注销服务工作人员并通过单个按钮单击清除所有存储和缓存。  
    
## Web app 清单  

如果你希望你的用户能够将应用添加到其移动 homescreens，你需要 web 应用清单。  该清单定义应用在主屏幕上的显示方式，在从主屏幕启动时，以及应用在启动时的外观。  

<!--Related Guides:  

*   [Improve user experiences with a Web App Manifest](/web/fundamentals/web-app-manifest)  
*   [Using App Install Banners](/web/fundamentals/app-install-banners)  -->

<!--TODO:  Link to sections when available. -->

设置清单后，可以使用 "**应用程序**" 面板的**清单**窗格检查它。  

:::image type="complex" source="./media/manifest-pane.msft.png" alt-text="清单窗格" lightbox="./media/manifest-pane.msft.png":::
   **清单**窗格  
:::image-end:::  

*   若要查看清单源，请单击上图中 " **应用清单** 标签 \ (" 下的链接 `https://airhorner.com/manifest.json` \ ) 。  
<!-- *   Press the **Add to homescreen** button to simulate an Add to Homescreen event.  Check out the next section for more information.  -->  
*   " **标识** " 和 " **演示文稿** " 部分仅在更易于用户友好的显示中显示清单源中的字段。  
*   " **图标** " 部分显示您已指定的每个图标。  
    
<!--### Simulate Add to Homescreen events  -->

<!--A web app can only be added to a homescreen when the site is visited at least twice, with at least five minutes between visits.  While developing or debugging your Add to Homescreen workflow, this criteria can be inconvenient.  
The **Add to homescreen** button on the **App Manifest** pane lets you simulate Add to Homescreen events whenever you want.  -->

<!--You can test out this feature with the [Microsoft I/O 2016 progressive web app](https://events.alpahabet.com/io2016/), which has proper support for Add to Homescreen.  Clicking on **Add to Homescreen** while the app is open prompts Microsoft Edge to display the "add this site to your shelf" banner, which is the desktop equivalent of the "add to homescreen" banner for mobile devices.  -->

<!--  
:::image type="complex" source="./media/io.msft.png" alt-text="清单窗格" lightbox="./media/io.msft.png":::
   Add to desktop shelf  
:::image-end:::
-->  

<!--
> [!Tip]
> Keep the **Console** drawer open while simulating Add to Homescreen events.  The Console tells you if your manifest has any issues and logs other information about the Add to Homescreen lifecycle.  -->

<!--The **Add to Homescreen** feature cannot yet simulate the workflow for mobile devices.  Notice how the "add to shelf" prompt was triggered in the screenshot above, even though DevTools is in Device Mode.  However, if you can successfully add your app to your desktop shelf, then it'll work for mobile, too.  -->

<!-- TODO: Rework content after sample app is created. -->

<!--If you want to test out the genuine mobile experience, you can connect a real mobile device to DevTools via **remote debugging**, and then click the **Add to Homescreen** button \(on DevTools\) to trigger the "add to homescreen" prompt on the connected mobile device.  -->

<!--TODO:  Link Debug "remote debugging" sections when available. -->

## 服务工作者  

服务工作者是未来 web 平台中的一种基本技术。  它们是浏览器在后台运行的脚本，这些脚本独立于网页。  这些脚本使你能够访问不需要网页或用户交互的功能，如推送通知、后台同步和脱机体验。  

<!--Related Guides:  

*   [Intro to Service Workers](/web/fundamentals/primers/service-worker)  
*   [Push Notifications: Timely, Relevant, and Precise](/web/fundamentals/push-notifications)  -->  
    
<!--TODO:  Link to sections when available. -->  

"**应用程序**" 面板中的 "**服务工作人员**" 窗格是 DevTools 检查和调试服务工作人员的主要位置。  

:::image type="complex" source="./media/service-workers-pane.msft.png" alt-text="清单窗格" lightbox="./media/service-workers-pane.msft.png":::
   " **服务工作人员** " 窗格  
:::image-end:::  

*   如果将服务工作人员安装到当前打开的页面，则会看到此窗格中列出了该工作人员。  例如，在上图中，为的作用域安装了一个服务工作线程 `https://weather-pwa-sample.firebaseapp.com` 。  
*   **脱机**复选框将 DevTools 置于脱机模式。  这等效于 " **网络** " 面板中可用的脱机模式，或 " `Go offline` [命令" 菜单][DevtoolsCommandMenuIndex]中的选项。  
*   " **重新加载时的更新** " 复选框强制服务工作者在每次加载页面时进行更新。  
*   " **绕过网络** " 复选框将绕过服务工作人员，并强制浏览器转到网络以获取请求的资源。  
*   " **更新** " 按钮对指定的服务工作人员执行一次性更新。  
*   **Push**按钮模拟没有负载的推送通知， (也称为**tickle**\ ) 。  
*   " **同步** " 按钮可模拟后台同步事件。  
*   " **注销** " 按钮将注销指定的服务工作人员。  查看 [清除存储](#clear-storage) ，了解一种注销服务工作人员的方法，并通过单个按钮单击来擦除存储和缓存。  
*   **源**行告诉你当前运行的服务工作线程何时安装。  该链接是服务工作人员的源文件的名称。  单击该链接即可将你发送到服务工作人员的源。  
*   **状态**行告诉你服务工作人员的状态。  在上图中，"绿色状态指示器 \ (" 旁边的 ID 号 \ `#36` ) 适用于当前处于活动状态的服务工作人员。  在 "状态" 旁边，你将看到 " **开始** " 按钮 \ (如果服务工作者已停止 ) 或 " **停止** " 按钮 \ (如果服务工作者正在运行 \ ) 。  服务工作人员设计为在任何时候停止和启动浏览器。  使用 **停止** 按钮显式停止服务工作人员可以模拟该情况。  停止服务工作人员是测试你的代码在服务工作人员再次启动时的行为方式的一种极佳方式。  由于有关永久全局状态的错误假设，它经常会显示 bug。  
*   " **客户端** " 行告诉你服务工作者的作用范围。  当您启用 "**全部显示**" 复选框时，"**焦点**" 按钮非常有用。  启用该复选框时，将列出所有已注册的服务工作人员。  如果单击在其他选项卡中运行的服务工作人员旁边的 " **焦点** " 按钮，则 Microsoft Edge 焦点位于该选项卡上。  
    
如果服务工作人员导致任何错误，则会显示一个名为 " **错误** " 的新标签。  

<!--  
:::image type="complex" source="./media/sw-error.msft.png" alt-text="清单窗格" lightbox="./media/sw-error.msft.png":::
   Service worker with errors  
:::image-end:::
-->  

<!--TODO:  Capture Service Worker Errors sample when available. -->
<!--TODO:  Link Web "How tickle works" sections when available. -->

## 服务工作人员缓存  

" **缓存存储** " 窗格提供使用 \ (服务工作人员 \ ) [缓存 API][MDNWebCacheAPI]缓存的资源的只读列表。  

:::image type="complex" source="./media/cache-pane-cache-storage-resources.msft.png" alt-text="清单窗格" lightbox="./media/cache-pane-cache-storage-resources.msft.png":::
   " **缓存存储** " 窗格  
:::image-end:::  

> [!NOTE]
> 第一次打开缓存并向其添加资源时，DevTools 可能不会检测更改。  重新加载页面，你应该可以看到缓存。  

如果打开了两个或多个缓存，则会在 " **缓存存储** " 下拉列表下方看到它们。  

:::image type="complex" source="./media/cache-pane-cache-storage.msft.png" alt-text="清单窗格" lightbox="./media/cache-pane-cache-storage.msft.png":::
   " **缓存存储** " 下拉列表  
:::image-end:::  

## 配额使用情况  

" **缓存存储** " 窗格中的某些响应可能标记为 "不透明"。  这是指从不同来源（例如从 **CDN** 或远程 API）检索的响应未启用 [CORS][FetchHttpCorsProtocol] 。  

<!--TODO:  Link Web "CDN" section when available. -->  
<!--TODO:  Link Web "opaque" section when available. -->

为了避免跨域信息的泄漏，在用于计算存储配额 (限制的不透明响应的大小中增加了一个明显的填充，例如，是否 `QuotaExceeded` 引发了异常 \ ) 并由 `navigator.storage` API 报告。  

<!--TODO:  Link Estimating "`navigator.storage` API" sections when available. -->

此填充的详细信息因浏览器的不同而不同，但对于 Microsoft Edge，这意味着任何单个缓存的不透明响应对总体存储使用率的**最小大小**[约为7兆字节][ChromiumIssues796060#c17]。  在确定要缓存的不透明响应的数量时，应牢记这一点，因为你可以比其他预期更快地减少存储配额限制，具体取决于不透明资源的实际大小。  

相关指南：  

*   [堆栈溢出：不透明答复适用的限制是什么？][StackOverflowLimitationsForOpaqueResponses]  
<!--*   [Alphabet work container: Understanding Storage Quota](/web/tools/Alphabet-work-container/guides/storage-quota#beware_of_opaque_responses)  -->
    
<!--TODO:  Link Work container storage quota for opaque responses section when available. -->

## 清除存储空间  

在开发渐进式 web 应用时，" **清除存储** " 窗格是非常有用的功能。  此窗格允许你注销服务工作人员并通过单个按钮单击来清除所有缓存和存储。  <!--Check out the section below to learn more.  -->

<!--Related Guides:  

*   [Clear Storage](/iterate/manage-data/local-storage#clear-storage)  -->
    
<!--TODO:  Link to sections when available. -->

<!--## Other Application panel guides   

Check out the guides below for more help on the other panes of the **Application** panel.  

Related Guides:  

*   [Inspect page resources](/iterate/manage-data/page-resources)  
*   [Inspect and manage local storage and caches](/iterate/manage-data/local-storage)  -->
    
## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsCommandMenuIndex]: ./command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  

[ChromiumIssues796060#c17]: https://bugs.chromium.org/p/chromium/issues/detail?id=796060#c17 "Chromium 问题796060：当分析代码位于 html 中时，缓存存储值将在每次刷新时上升"  

[FetchHttpCorsProtocol]: https://fetch.spec.whatwg.org/#http-cors-protocol  

[MDNWebCacheAPI]: https://developer.mozilla.org/docs/Web/API/Cache "缓存-Web Api |MDN"  

[StackOverflowLimitationsForOpaqueResponses]: https://stackoverflow.com/q/39109789/385997 "堆栈溢出：不透明答复适用的限制是什么？"  

<!--[WebEstimatingAvailableStorageSpace]: whats-new/2017/08/estimating-available-storage-space  -->
<!--[RemoteDebugging]: /debug/remote-debugging/remote-debugging  -->

<!--[WebHowPushWorks]: /web/fundamentals/push-notifications/how-push-works  -->  
<!--[WebGlossaryCDN]: /web/fundamentals/glossary#CDN  -->
<!--[WebGlossaryOpaque]: /web/fundamentals/glossary#opaque-response  -->

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/progressive-web-apps)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
