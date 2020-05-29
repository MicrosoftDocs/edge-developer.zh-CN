---
description: 对页面域的引用。 与已检查页面相关的操作和事件属于页面域。
title: Page Domain-DevTools 协议版本0。1
author: pelavall
ms.author: pelavall
ms.date: 12/15/2017
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: a1cd094baef4571240881a86ecccfdb319fef61b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563424"
---
# <span data-ttu-id="53c92-104">页面</span><span class="sxs-lookup"><span data-stu-id="53c92-104">Page</span></span>
<span data-ttu-id="53c92-105">与已检查页面相关的操作和事件属于页面域。</span><span class="sxs-lookup"><span data-stu-id="53c92-105">Actions and events related to the inspected page belong to the page domain.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="53c92-106">方法</span><span class="sxs-lookup"><span data-stu-id="53c92-106">Methods</span></span>**](#methods) | <span data-ttu-id="53c92-107">[启用](#enable)、[禁用](#disable)、[导航](#navigate)</span><span class="sxs-lookup"><span data-stu-id="53c92-107">[enable](#enable), [disable](#disable), [navigate](#navigate)</span></span> |
| [**<span data-ttu-id="53c92-108">类型</span><span class="sxs-lookup"><span data-stu-id="53c92-108">Types</span></span>**](#types) | [<span data-ttu-id="53c92-109">FrameId</span><span class="sxs-lookup"><span data-stu-id="53c92-109">FrameId</span></span>](#frameid) |
## <span data-ttu-id="53c92-110">方法</span><span class="sxs-lookup"><span data-stu-id="53c92-110">Methods</span></span>

### <span data-ttu-id="53c92-111">“启用”</span><span class="sxs-lookup"><span data-stu-id="53c92-111">enable</span></span>
<span data-ttu-id="53c92-112">启用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="53c92-112">Enables page domain notifications.</span></span>


---

### <span data-ttu-id="53c92-113">“禁用”</span><span class="sxs-lookup"><span data-stu-id="53c92-113">disable</span></span>
<span data-ttu-id="53c92-114">禁用页面域通知。</span><span class="sxs-lookup"><span data-stu-id="53c92-114">Disables page domain notifications.</span></span>


---

### <span data-ttu-id="53c92-115">导航</span><span class="sxs-lookup"><span data-stu-id="53c92-115">navigate</span></span>
<span data-ttu-id="53c92-116">将当前页导航到给定的 URL。</span><span class="sxs-lookup"><span data-stu-id="53c92-116">Navigates current page to the given URL.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="53c92-117">参数</span><span class="sxs-lookup"><span data-stu-id="53c92-117">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="53c92-118">url</span><span class="sxs-lookup"><span data-stu-id="53c92-118">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="53c92-119">要将页面导航到的 URL。</span><span class="sxs-lookup"><span data-stu-id="53c92-119">URL to navigate the page to.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="53c92-120">返回</span><span class="sxs-lookup"><span data-stu-id="53c92-120">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="53c92-121">frameId</span><span class="sxs-lookup"><span data-stu-id="53c92-121">frameId</span></span></td>
            <td><a href="#frameid"><code class="flyout">FrameId</code></a></td>
            <td><span><b><span data-ttu-id="53c92-122">实验.</span><span class="sxs-lookup"><span data-stu-id="53c92-122">Experimental.</span></span> </b></span><span data-ttu-id="53c92-123">将导航的帧 id。</span><span class="sxs-lookup"><span data-stu-id="53c92-123">Frame id that will be navigated.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="53c92-124">类型</span><span class="sxs-lookup"><span data-stu-id="53c92-124">Types</span></span>

### <a name="frameid"></a> <span data-ttu-id="53c92-125">FrameId</span><span class="sxs-lookup"><span data-stu-id="53c92-125">FrameId</span></span> `string`

<span data-ttu-id="53c92-126">唯一的帧标识符。</span><span class="sxs-lookup"><span data-stu-id="53c92-126">Unique frame identifier.</span></span>


---
