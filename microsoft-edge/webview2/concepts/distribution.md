---
description: 使用 Microsoft Edge WebView2 发布应用时的分发选项
title: Microsoft Edge WebView2 应用程序的分发
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: a789b0f4f9c482670f843ed21368b4168f99abe0
ms.sourcegitcommit: 5bdffe91a6594f77eeffa4e864fda90a02784771
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "10659689"
---
# 使用 WebView2 的应用程序的分发 

WebView2 控件利用 Microsoft Edge \ （Chromium \）浏览器。 当分发你的应用时，请确保应用程序运行的所有用户计算机上都安装了 Edge 浏览器。 WebView2 控件使用计算机上安装的最稳定版本的浏览器。 例如，你可能同时安装了稳定、Beta、Dev 和 WebView2，在这种情况下，控件在稳定频道中运行。 请确保查看发行说明，确保运行 WebView2 控件的计算机上安装的浏览器版本满足最低版本要求。

## 路线图

我们认识到，在应用程序运行的所有用户计算机上，或者在整个组织中安装 Edge 浏览器的情况下，Edge 浏览器可能不可用。 为了确保你的应用程序在所有计算机上运行，而不依赖于已安装的 Microsoft Edge 浏览器，我们将释放 Microsoft Edge WebView2 运行时。 此外，我们还将更新 WebView2 以搜索运行时的稳定版本，然后再搜索已安装浏览器的预发布版本。

将对使用 WebView2 运行时：长绿和固定版本的两个分发选项提供支持。

长绿将成为大多数开发人员的推荐的分发模型。 在此模式下，更新将自动推送到 WebView2 运行时，而不需要你的应用程序进行额外的工作。 长时间模型可确保你的应用充分利用托管 web 内容的最新功能和安全更新。

对于受限环境，将支持固定版本分发模型。 在此模型中，你的应用程序选择并打包特定版本的 WebView2。 对 Web 视图版本的更新不会自动发生，并且将由应用程序负责。 当你需要控制浏览器版本以及应用程序更新时，修复版本模型非常有用。 

### Microsoft Edge WebView2 运行时

Microsoft Edge WebView2 运行时将打包经优化以供 WebView2 应用程序使用的浏览器二进制文件。 它将独立运行或与安装了客户端边缘浏览器并排运行。 安装运行时一次将支持在客户端计算机上运行的许多 WebView2 应用程序。 安装运行时不会以浏览器的形式显示给最终用户，并且将没有桌面快捷方式、开始菜单入口点或协议注册。

使用 WebView2 运行时的应用程序将需要确保运行时安装已完成。 若要确保你的应用程序将运行时安装为依赖项，你可以将运行时添加到你的安装流。 
