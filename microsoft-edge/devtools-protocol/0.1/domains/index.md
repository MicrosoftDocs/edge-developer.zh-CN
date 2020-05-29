---
description: Microsoft Edge DevTools 协议版本0.1 中支持的域的引用列表。
title: 域-DevTools 协议版本0。1
author: pelavall
ms.author: pelavall
ms.date: 12/15/2017
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: b3cf3411a8402b7407012eb789f8bf267b4997a8
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563420"
---
# DevTools 协议域
## [调试器](debugger.md)
调试器域公开 JavaScript 调试功能。 它允许设置和删除断点、逐句通过执行、浏览堆栈跟踪等。
## [页面](page.md)
与已检查页面相关的操作和事件属于页面域。
## [运行时](runtime.md)
运行时域通过远程计算和镜像对象公开 JavaScript 运行时。 计算结果以镜像对象的形式返回，该对象公开可用于进一步对象引用的对象类型、字符串表示形式和唯一标识符。 原始对象将保留在内存中，除非它们被显式释放。
## [架构](schema.md)
提供有关协议架构的信息。