---
description: 公开操作是否已成功完成或失败
title: MSWebViewAsyncOperation 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: ebb89c0fc645ebcd97357af10af2be650d8218b9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563036"
---
# <span data-ttu-id="90101-104">MSWebViewAsyncOperation 对象</span><span class="sxs-lookup"><span data-stu-id="90101-104">MSWebViewAsyncOperation object</span></span>

<span data-ttu-id="90101-105">公开操作是否已成功完成或失败。</span><span class="sxs-lookup"><span data-stu-id="90101-105">Exposes whether the operation completed successfully or failed.</span></span> 

## <span data-ttu-id="90101-106">事件</span><span class="sxs-lookup"><span data-stu-id="90101-106">Events</span></span>

### <span data-ttu-id="90101-107">完成</span><span class="sxs-lookup"><span data-stu-id="90101-107">complete</span></span>

<span data-ttu-id="90101-108">指示操作已完成。</span><span class="sxs-lookup"><span data-stu-id="90101-108">Indicates that the operation completed.</span></span> 

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("complete", handler);
MSWebViewAsyncOperation.removeEventListener("complete", handler);
```

#### <span data-ttu-id="90101-109">事件信息</span><span class="sxs-lookup"><span data-stu-id="90101-109">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="90101-110">接口</span><span class="sxs-lookup"><span data-stu-id="90101-110">Interface</span></span>** | **<span data-ttu-id="90101-111">事件</span><span class="sxs-lookup"><span data-stu-id="90101-111">Event</span></span>**
|**<span data-ttu-id="90101-112">同步</span><span class="sxs-lookup"><span data-stu-id="90101-112">Synchronous</span></span>** |<span data-ttu-id="90101-113">是</span><span class="sxs-lookup"><span data-stu-id="90101-113">Yes</span></span> |    
|**<span data-ttu-id="90101-114">气泡</span><span class="sxs-lookup"><span data-stu-id="90101-114">Bubbles</span></span>**     |<span data-ttu-id="90101-115">否</span><span class="sxs-lookup"><span data-stu-id="90101-115">No</span></span> |   
|**<span data-ttu-id="90101-116">可取消</span><span class="sxs-lookup"><span data-stu-id="90101-116">Cancelable</span></span>**  |<span data-ttu-id="90101-117">否</span><span class="sxs-lookup"><span data-stu-id="90101-117">No</span></span> |        


### <span data-ttu-id="90101-118">错误</span><span class="sxs-lookup"><span data-stu-id="90101-118">error</span></span>

<span data-ttu-id="90101-119">指示操作出现错误。</span><span class="sxs-lookup"><span data-stu-id="90101-119">Indicates that there was an error with the operation.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("error", handler);
MSWebViewAsyncOperation.removeEventListener("error", handler);
```

#### <span data-ttu-id="90101-120">事件信息</span><span class="sxs-lookup"><span data-stu-id="90101-120">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="90101-121">接口</span><span class="sxs-lookup"><span data-stu-id="90101-121">Interface</span></span>** | **<span data-ttu-id="90101-122">事件</span><span class="sxs-lookup"><span data-stu-id="90101-122">Event</span></span>**
|**<span data-ttu-id="90101-123">同步</span><span class="sxs-lookup"><span data-stu-id="90101-123">Synchronous</span></span>** |<span data-ttu-id="90101-124">是</span><span class="sxs-lookup"><span data-stu-id="90101-124">Yes</span></span> |    
|**<span data-ttu-id="90101-125">气泡</span><span class="sxs-lookup"><span data-stu-id="90101-125">Bubbles</span></span>**     |<span data-ttu-id="90101-126">否</span><span class="sxs-lookup"><span data-stu-id="90101-126">No</span></span> |   
|**<span data-ttu-id="90101-127">可取消</span><span class="sxs-lookup"><span data-stu-id="90101-127">Cancelable</span></span>**  |<span data-ttu-id="90101-128">否</span><span class="sxs-lookup"><span data-stu-id="90101-128">No</span></span> |            


## <span data-ttu-id="90101-129">方法</span><span class="sxs-lookup"><span data-stu-id="90101-129">Methods</span></span>

### <span data-ttu-id="90101-130">start</span><span class="sxs-lookup"><span data-stu-id="90101-130">start</span></span>

<span data-ttu-id="90101-131">调用以启动异步任务。</span><span class="sxs-lookup"><span data-stu-id="90101-131">Called to start the async task.</span></span> 

```js
MSWebViewAsyncOperation.start();
```

### <span data-ttu-id="90101-132">参数</span><span class="sxs-lookup"><span data-stu-id="90101-132">Parameters</span></span>

<span data-ttu-id="90101-133">此方法没有参数。</span><span class="sxs-lookup"><span data-stu-id="90101-133">This method does not have parameters.</span></span>

### <span data-ttu-id="90101-134">返回值</span><span class="sxs-lookup"><span data-stu-id="90101-134">Return value</span></span>

<span data-ttu-id="90101-135">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="90101-135">This method does not return a value.</span></span>

## <span data-ttu-id="90101-136">属性</span><span class="sxs-lookup"><span data-stu-id="90101-136">Properties</span></span>

### <span data-ttu-id="90101-137">错误</span><span class="sxs-lookup"><span data-stu-id="90101-137">error</span></span>

<span data-ttu-id="90101-138">出现的错误。</span><span class="sxs-lookup"><span data-stu-id="90101-138">The error that occured.</span></span>

<span data-ttu-id="90101-139">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="90101-139">This property is read-only.</span></span>

```js
var error = MSWebViewAsyncOperation.error;
```

#### <span data-ttu-id="90101-140">属性值</span><span class="sxs-lookup"><span data-stu-id="90101-140">Property value</span></span>
<span data-ttu-id="90101-141">类型： **DOMError**</span><span class="sxs-lookup"><span data-stu-id="90101-141">Type: **DOMError**</span></span>

### <span data-ttu-id="90101-142">oncomplete</span><span class="sxs-lookup"><span data-stu-id="90101-142">oncomplete</span></span>

<span data-ttu-id="90101-143">**完整**的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="90101-143">The **complete** event handler.</span></span> 

```js
var oncomplete = MSWebViewAsyncOperation.oncomplete;
```

#### <span data-ttu-id="90101-144">属性值</span><span class="sxs-lookup"><span data-stu-id="90101-144">Property value</span></span>
<span data-ttu-id="90101-145">类型： **EventHandler**</span><span class="sxs-lookup"><span data-stu-id="90101-145">Type: **EventHandler**</span></span>

### <span data-ttu-id="90101-146">onerror</span><span class="sxs-lookup"><span data-stu-id="90101-146">onerror</span></span>

<span data-ttu-id="90101-147">**错误**事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="90101-147">The **error** event handler.</span></span> 

```js
var onerror = MSWebViewAsyncOperation.onerror;
```

#### <span data-ttu-id="90101-148">属性值</span><span class="sxs-lookup"><span data-stu-id="90101-148">Property value</span></span>
<span data-ttu-id="90101-149">类型： **EventHandler**</span><span class="sxs-lookup"><span data-stu-id="90101-149">Type: **EventHandler**</span></span>

### <span data-ttu-id="90101-150">readyState</span><span class="sxs-lookup"><span data-stu-id="90101-150">readyState</span></span>

<span data-ttu-id="90101-151">描述对象的准备状态。</span><span class="sxs-lookup"><span data-stu-id="90101-151">Describes the ready state of the object.</span></span>

<span data-ttu-id="90101-152">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="90101-152">This property is read-only.</span></span>

```js
var readyState = MSWebViewAsyncOperation.readyState;
```

#### <span data-ttu-id="90101-153">属性值</span><span class="sxs-lookup"><span data-stu-id="90101-153">Property value</span></span>
<span data-ttu-id="90101-154">类型：**无符号的短**</span><span class="sxs-lookup"><span data-stu-id="90101-154">Type: **unsigned short**</span></span>

### <span data-ttu-id="90101-155">结果</span><span class="sxs-lookup"><span data-stu-id="90101-155">result</span></span>

<span data-ttu-id="90101-156">操作的结果。</span><span class="sxs-lookup"><span data-stu-id="90101-156">The result of the operation.</span></span>

<span data-ttu-id="90101-157">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="90101-157">This property is read-only.</span></span>

```js
var result = MSWebViewAsyncOperation.result;
```

#### <span data-ttu-id="90101-158">属性值</span><span class="sxs-lookup"><span data-stu-id="90101-158">Property value</span></span>
<span data-ttu-id="90101-159">类型：任何</span><span class="sxs-lookup"><span data-stu-id="90101-159">Type: any</span></span>

### <span data-ttu-id="90101-160">target</span><span class="sxs-lookup"><span data-stu-id="90101-160">target</span></span>

<span data-ttu-id="90101-161">操作的目标。</span><span class="sxs-lookup"><span data-stu-id="90101-161">The target of the operation.</span></span> 

<span data-ttu-id="90101-162">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="90101-162">This property is read-only.</span></span>

```js
var target = MSWebViewAsyncOperation.target;
```

#### <span data-ttu-id="90101-163">属性值</span><span class="sxs-lookup"><span data-stu-id="90101-163">Property value</span></span>
<span data-ttu-id="90101-164">类型： [ **MSHTMLWebViewElement**](../webview.md)</span><span class="sxs-lookup"><span data-stu-id="90101-164">Type: [**MSHTMLWebViewElement**](../webview.md)</span></span>

### <span data-ttu-id="90101-165">类型</span><span class="sxs-lookup"><span data-stu-id="90101-165">type</span></span>

<span data-ttu-id="90101-166">操作的类型。</span><span class="sxs-lookup"><span data-stu-id="90101-166">The type of the operation.</span></span>

<span data-ttu-id="90101-167">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="90101-167">This property is read-only.</span></span>

```js
var type = MSWebViewAsyncOperation.type;
```

#### <span data-ttu-id="90101-168">属性值</span><span class="sxs-lookup"><span data-stu-id="90101-168">Property value</span></span>
<span data-ttu-id="90101-169">类型：**无符号的短**</span><span class="sxs-lookup"><span data-stu-id="90101-169">Type: **unsigned short**</span></span>
