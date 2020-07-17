---
description: Microsoft Edge DevTools 协议版本0.1 中支持的域的引用列表。
title: DevTools 协议域-DevTools 协议版本0.1 （EdgeHTML）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: de816e2b07838ba1b6151967ff7b8751789c60ea
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882945"
---
# <span data-ttu-id="b6e1a-103">DevTools 协议域-DevTools 协议版本0.1 （EdgeHTML）</span><span class="sxs-lookup"><span data-stu-id="b6e1a-103">DevTools Protocol Domains - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

## [<span data-ttu-id="b6e1a-104">调试程序</span><span class="sxs-lookup"><span data-stu-id="b6e1a-104">Debugger</span></span>](debugger.md)  

<span data-ttu-id="b6e1a-105">调试器域公开 JavaScript 调试功能。</span><span class="sxs-lookup"><span data-stu-id="b6e1a-105">Debugger domain exposes JavaScript debugging capabilities.</span></span> <span data-ttu-id="b6e1a-106">它允许设置和删除断点、逐句通过执行、浏览堆栈跟踪等。</span><span class="sxs-lookup"><span data-stu-id="b6e1a-106">It allows setting and removing breakpoints, stepping through execution, exploring stack traces, etc.</span></span>
## [<span data-ttu-id="b6e1a-107">Page</span><span class="sxs-lookup"><span data-stu-id="b6e1a-107">Page</span></span>](page.md)
<span data-ttu-id="b6e1a-108">与已检查页面相关的操作和事件属于页面域。</span><span class="sxs-lookup"><span data-stu-id="b6e1a-108">Actions and events related to the inspected page belong to the page domain.</span></span>
## [<span data-ttu-id="b6e1a-109">运行时</span><span class="sxs-lookup"><span data-stu-id="b6e1a-109">Runtime</span></span>](runtime.md)
<span data-ttu-id="b6e1a-110">运行时域通过远程计算和镜像对象公开 JavaScript 运行时。</span><span class="sxs-lookup"><span data-stu-id="b6e1a-110">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="b6e1a-111">计算结果以镜像对象的形式返回，该对象公开可用于进一步对象引用的对象类型、字符串表示形式和唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b6e1a-111">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="b6e1a-112">原始对象将保留在内存中，除非它们被显式释放。</span><span class="sxs-lookup"><span data-stu-id="b6e1a-112">Original objects are maintained in memory unless they are either explicitly released.</span></span>
## [<span data-ttu-id="b6e1a-113">架构</span><span class="sxs-lookup"><span data-stu-id="b6e1a-113">Schema</span></span>](schema.md)
<span data-ttu-id="b6e1a-114">提供有关协议架构的信息。</span><span class="sxs-lookup"><span data-stu-id="b6e1a-114">Provides information about the protocol schema.</span></span>