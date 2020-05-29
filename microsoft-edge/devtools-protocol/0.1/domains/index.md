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
# <span data-ttu-id="9c7d6-103">DevTools 协议域</span><span class="sxs-lookup"><span data-stu-id="9c7d6-103">DevTools Protocol Domains</span></span>
## [<span data-ttu-id="9c7d6-104">调试器</span><span class="sxs-lookup"><span data-stu-id="9c7d6-104">Debugger</span></span>](debugger.md)
<span data-ttu-id="9c7d6-105">调试器域公开 JavaScript 调试功能。</span><span class="sxs-lookup"><span data-stu-id="9c7d6-105">Debugger domain exposes JavaScript debugging capabilities.</span></span> <span data-ttu-id="9c7d6-106">它允许设置和删除断点、逐句通过执行、浏览堆栈跟踪等。</span><span class="sxs-lookup"><span data-stu-id="9c7d6-106">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>
## [<span data-ttu-id="9c7d6-107">页面</span><span class="sxs-lookup"><span data-stu-id="9c7d6-107">Page</span></span>](page.md)
<span data-ttu-id="9c7d6-108">与已检查页面相关的操作和事件属于页面域。</span><span class="sxs-lookup"><span data-stu-id="9c7d6-108">Actions and events related to the inspected page belong to the page domain.</span></span>
## [<span data-ttu-id="9c7d6-109">运行时</span><span class="sxs-lookup"><span data-stu-id="9c7d6-109">Runtime</span></span>](runtime.md)
<span data-ttu-id="9c7d6-110">运行时域通过远程计算和镜像对象公开 JavaScript 运行时。</span><span class="sxs-lookup"><span data-stu-id="9c7d6-110">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="9c7d6-111">计算结果以镜像对象的形式返回，该对象公开可用于进一步对象引用的对象类型、字符串表示形式和唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="9c7d6-111">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="9c7d6-112">原始对象将保留在内存中，除非它们被显式释放。</span><span class="sxs-lookup"><span data-stu-id="9c7d6-112">Original objects are maintained in memory unless they are either explicitly released.</span></span>
## [<span data-ttu-id="9c7d6-113">架构</span><span class="sxs-lookup"><span data-stu-id="9c7d6-113">Schema</span></span>](schema.md)
<span data-ttu-id="9c7d6-114">提供有关协议架构的信息。</span><span class="sxs-lookup"><span data-stu-id="9c7d6-114">Provides information about the protocol schema.</span></span>